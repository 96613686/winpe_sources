# LoadTypeLibFromIID(ushort const *,ITypeLib * *)

- ea: `0x1800065b0`
- end: `0x180006823`
- name: `?LoadTypeLibFromIID@@YAJPEBGPEAPEAUITypeLib@@@Z`
- size: `627`
- prototype: `int(const unsigned __int16 *, struct ITypeLib **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001cdfc`

## callees

- `0x180006194`
- `0x1800065b0`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006662`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800066d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006662`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800066d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000662b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000662b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043762`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043762`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000674a`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180006771`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000674a`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180006771`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000668b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000668b`

## pseudocode

```c
__int64 __fastcall LoadTypeLibFromIID(const unsigned __int16 *a1, struct ITypeLib **a2)
{
  HRESULT v3; // ebx
  WORD v4; // di
  WORD v5; // si
  BYTE *i; // rax
  unsigned __int16 v7; // cx
  __int16 v8; // di
  unsigned __int16 v9; // cx
  __int16 v10; // si
  DWORD cbData; // [rsp+34h] [rbp-134h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-130h] BYREF
  BYTE *v14; // [rsp+40h] [rbp-128h]
  GUID pclsid; // [rsp+48h] [rbp-120h] BYREF
  BYTE v16[24]; // [rsp+58h] [rbp-110h] BYREF
  OLECHAR Data[39]; // [rsp+70h] [rbp-F8h] BYREF
  __int16 v18; // [rsp+BEh] [rbp-AAh]
  WCHAR SubKey[64]; // [rsp+C0h] [rbp-A8h] BYREF

  hKey = 0;
  v3 = StringCchPrintfW(SubKey, 0x3Cu, L"Interface\\%s\\TypeLib", a1);
  if ( v3 >= 0 )
  {
    if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
    {
      v3 = -2147319779;
    }
    else
    {
      cbData = 80;
      if ( RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData) )
      {
        v3 = -2147319779;
      }
      else
      {
        v18 = 0;
        pclsid = 0;
        v3 = CLSIDFromString(Data, &pclsid);
        if ( v3 >= 0 )
        {
          memset(v16, 0, 22);
          cbData = 22;
          if ( RegQueryValueExW(hKey, L"Version", 0, 0, v16, &cbData) )
          {
            v3 = -2147319779;
          }
          else
          {
            *(_WORD *)&v16[20] = 0;
            v4 = 0;
            v5 = 0;
            v14 = 0;
            for ( i = v16; ; i += 2 )
            {
              v14 = i;
              v7 = *(_WORD *)i;
              if ( !*(_WORD *)i )
                break;
              if ( v7 == 46 )
              {
                while ( 1 )
                {
                  i += 2;
                  v14 = i;
                  v9 = *(_WORD *)i;
                  if ( !*(_WORD *)i )
                    break;
                  v10 = v9 + 16 * v5;
                  if ( v9 > 0x39u )
                  {
                    if ( v9 > 0x46u )
                      v5 = v10 - 87;
                    else
                      v5 = v10 - 55;
                  }
                  else
                  {
                    v5 = v10 - 48;
                  }
                }
                break;
              }
              v8 = v7 + 16 * v4;
              if ( v7 > 0x39u )
              {
                if ( v7 > 0x46u )
                  v4 = v8 - 87;
                else
                  v4 = v8 - 55;
              }
              else
              {
                v4 = v8 - 48;
              }
            }
            v3 = LoadRegTypeLib(&pclsid, v4, v5, 0, a2);
            if ( v3 < 0 )
              v3 = LoadRegTypeLib(&pclsid, v4, v5, 9u, a2);
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800065b0  mov     [rsp+arg_10], rbx
0x1800065b5  mov     [rsp+arg_18], rsi
0x1800065ba  push    rdi
0x1800065bb  push    r14
0x1800065bd  push    r15
0x1800065bf  sub     rsp, 150h
0x1800065c6  mov     rax, cs:__security_cookie
0x1800065cd  xor     rax, rsp
0x1800065d0  mov     [rsp+168h+var_28], rax
0x1800065d8  mov     r14, rdx
0x1800065db  xor     r15d, r15d
0x1800065de  mov     [rsp+168h+hKey], r15
0x1800065e3  mov     r9, rcx
0x1800065e6  lea     r8, aInterfaceSType; "Interface\\%s\\TypeLib"
0x1800065ed  mov     edx, 3Ch ; '<'; unsigned __int64
0x1800065f2  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x1800065fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800065ff  mov     ebx, eax
0x180006601  test    eax, eax
0x180006603  js      loc_1800067E8
0x180006609  lea     rax, [rsp+168h+hKey]
0x18000660e  mov     [rsp+168h+phkResult], rax; phkResult
0x180006613  mov     r9d, 20019h; samDesired
0x180006619  xor     r8d, r8d; ulOptions
0x18000661c  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x180006624  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000662b  call    cs:__imp_RegOpenKeyExW
0x180006631  test    eax, eax
0x180006633  jnz     loc_1800067B7
0x180006639  mov     [rsp+168h+cbData], 50h ; 'P'
0x180006641  lea     rax, [rsp+168h+cbData]
0x180006646  mov     [rsp+168h+lpcbData], rax; lpcbData
0x18000664b  lea     rax, [rsp+168h+Data]
0x180006650  mov     [rsp+168h+phkResult], rax; lpData
0x180006655  xor     r9d, r9d; lpType
0x180006658  xor     r8d, r8d; lpReserved
0x18000665b  xor     edx, edx; lpValueName
0x18000665d  mov     rcx, [rsp+168h+hKey]; hKey
0x180006662  call    cs:__imp_RegQueryValueExW
0x180006668  test    eax, eax
0x18000666a  jnz     loc_1800067A9
0x180006670  mov     [rsp+168h+var_AA], r15w
0x180006679  xorps   xmm0, xmm0
0x18000667c  movups  xmmword ptr [rsp+168h+pclsid.Data1], xmm0
0x180006681  lea     rdx, [rsp+168h+pclsid]; pclsid
0x180006686  lea     rcx, [rsp+168h+Data]; lpsz
0x18000668b  call    cs:__imp_CLSIDFromString
0x180006691  mov     ebx, eax
0x180006693  test    eax, eax
0x180006695  js      loc_1800067E8
0x18000669b  xorps   xmm0, xmm0
0x18000669e  xor     eax, eax
0x1800066a0  movups  xmmword ptr [rsp+168h+var_110], xmm0
0x1800066a5  mov     qword ptr [rsp+168h+var_110+0Eh], rax
0x1800066aa  mov     [rsp+168h+cbData], 16h
0x1800066b2  lea     rax, [rsp+168h+cbData]
0x1800066b7  mov     [rsp+168h+lpcbData], rax; lpcbData
0x1800066bc  lea     rax, [rsp+168h+var_110]
0x1800066c1  mov     [rsp+168h+phkResult], rax; lpData
0x1800066c6  xor     r9d, r9d; lpType
0x1800066c9  xor     r8d, r8d; lpReserved
0x1800066cc  lea     rdx, aVersion; "Version"
0x1800066d3  mov     rcx, [rsp+168h+hKey]; hKey
0x1800066d8  call    cs:__imp_RegQueryValueExW
0x1800066de  test    eax, eax
0x1800066e0  jnz     loc_1800067B0
0x1800066e6  mov     [rsp+168h+var_FC], r15w
0x1800066ec  mov     edi, r15d
0x1800066ef  mov     esi, r15d
0x1800066f2  mov     [rsp+168h+var_138], r15w
0x1800066f8  mov     [rsp+168h+var_128], r15
0x1800066fd  lea     rax, [rsp+168h+var_110]
0x180006702  mov     [rsp+168h+var_128], rax
0x180006707  movzx   ecx, word ptr [rax]
0x18000670a  test    cx, cx
0x18000670d  jz      short loc_180006730
0x18000670f  cmp     cx, 2Eh ; '.'
0x180006713  jz      short loc_18000677B
0x180006715  shl     di, 4
0x180006719  add     di, cx
0x18000671c  cmp     cx, 39h ; '9'
0x180006720  ja      loc_1800067BE
0x180006726  sub     di, 30h ; '0'
0x18000672a  add     rax, 2
0x18000672e  jmp     short loc_180006702
0x180006730  cmp     cx, 2Eh ; '.'
0x180006734  jz      short loc_18000677B
0x180006736  mov     [rsp+168h+phkResult], r14; pptlib
0x18000673b  xor     r9d, r9d; lcid
0x18000673e  movzx   r8d, si; wVerMinor
0x180006742  movzx   edx, di; wVerMajor
0x180006745  lea     rcx, [rsp+168h+pclsid]; rguid
0x18000674a  call    cs:__imp_LoadRegTypeLib
0x180006750  mov     ebx, eax
0x180006752  test    eax, eax
0x180006754  jns     loc_1800067E8
0x18000675a  mov     [rsp+168h+phkResult], r14; pptlib
0x18000675f  mov     r9d, 9; lcid
0x180006765  movzx   r8d, si; wVerMinor
0x180006769  movzx   edx, di; wVerMajor
0x18000676c  lea     rcx, [rsp+168h+pclsid]; rguid
0x180006771  call    cs:__imp_LoadRegTypeLib
0x180006777  mov     ebx, eax
0x180006779  jmp     short loc_1800067E8
0x18000677b  add     rax, 2
0x18000677f  mov     [rsp+168h+var_128], rax
0x180006784  movzx   ecx, word ptr [rax]
0x180006787  test    cx, cx
0x18000678a  jz      short loc_180006736
0x18000678c  shl     si, 4
0x180006790  mov     [rsp+168h+var_138], si
0x180006795  add     si, cx
0x180006798  cmp     cx, 39h ; '9'
0x18000679c  ja      short loc_1800067D6
0x18000679e  sub     si, 30h ; '0'
0x1800067a2  mov     [rsp+168h+var_138], si
0x1800067a7  jmp     short loc_18000677B
0x1800067a9  mov     ebx, 8002801Dh
0x1800067ae  jmp     short loc_1800067E8
0x1800067b0  mov     ebx, 8002801Dh
0x1800067b5  jmp     short loc_1800067E8
0x1800067b7  mov     ebx, 8002801Dh
0x1800067bc  jmp     short loc_1800067E8
0x1800067be  cmp     cx, 46h ; 'F'
0x1800067c2  ja      short loc_1800067CD
0x1800067c4  sub     di, 37h ; '7'
0x1800067c8  jmp     loc_18000672A
0x1800067cd  sub     di, 57h ; 'W'
0x1800067d1  jmp     loc_18000672A
0x1800067d6  cmp     cx, 46h ; 'F'
0x1800067da  ja      short loc_1800067E2
0x1800067dc  sub     si, 37h ; '7'
0x1800067e0  jmp     short loc_1800067A2
0x1800067e2  sub     si, 57h ; 'W'
0x1800067e6  jmp     short loc_1800067A2
0x1800067e8  mov     rcx, [rsp+168h+hKey]; hKey
0x1800067ed  test    rcx, rcx
0x1800067f0  jz      short loc_1800067F8
0x1800067f2  call    cs:__imp_RegCloseKey
0x1800067f8  mov     eax, ebx
0x1800067fa  mov     rcx, [rsp+168h+var_28]
0x180006802  xor     rcx, rsp; StackCookie
0x180006805  call    __security_check_cookie
0x18000680a  lea     r11, [rsp+168h+var_18]
0x180006812  mov     rbx, [r11+30h]
0x180006816  mov     rsi, [r11+38h]
0x18000681a  mov     rsp, r11
0x18000681d  pop     r15
0x18000681f  pop     r14
0x180006821  pop     rdi
0x180006822  retn
0x180043750  push    rbp
0x180043752  sub     rsp, 30h
0x180043756  mov     rbp, rdx
0x180043759  mov     rcx, [rbp+38h]; hKey
0x18004375d  test    rcx, rcx
0x180043760  jz      short loc_180043769
0x180043762  call    cs:__imp_RegCloseKey
0x180043768  nop
0x180043769  add     rsp, 30h
0x18004376d  pop     rbp
0x18004376e  retn
```
