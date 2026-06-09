# RegOpenRDInterfaceKey

- ea: `0x18000a4dc`
- end: `0x18000a79d`
- name: `RegOpenRDInterfaceKey`
- size: `705`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD dwIndex, PHKEY phkResult, LPBYTE lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009270`

## callees

- `0x180007b7c`
- `0x18000a4dc`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000a57b`
- `ADVAPI32!RegEnumKeyExW` at `0x18000a57b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000a632`
- `ADVAPI32!RegOpenKeyExW` at `0x18000a632`
- `ADVAPI32!RegQueryValueExW` at `0x18000a6b6`
- `ADVAPI32!RegQueryValueExW` at `0x18000a6b6`
- `ADVAPI32!RegCloseKey` at `0x18000a773`
- `ADVAPI32!RegCloseKey` at `0x18000a773`

## string_xrefs

- `0x18000a5a3`: `RegOpenRDInterfaceKey: RegEnumKeyEx failed with error = %d`
- `0x18000a65b`: `RegOpenRDInterfaceKey: RegOpenKeyEx (%s) failed with error = %d`
- `0x18000a6ef`: `RegOpenRDInterfaceKey: RegQueryValueEx (%s) failed with error = %d`

## pseudocode

```c
__int64 __fastcall RegOpenRDInterfaceKey(HKEY hKey, DWORD dwIndex, PHKEY phkResult, LPBYTE lpData)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp-B0h] BYREF
  int *v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+6Ch] [rbp-94h]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v25[2044]; // [rsp+284h] [rbp+184h] BYREF

  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  memset_0(Name, 0, 0x202u);
  cchName = 257;
  Type = 0;
  cbData = 514;
  *phkResult = 0;
  v8 = RegEnumKeyExW(hKey, dwIndex, Name, &cchName, 0, 0, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"RegOpenRDInterfaceKey: RegEnumKeyEx failed with error = %d", v8);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v25[2 * v11 - 4] );
LABEL_6:
        v22 = 0;
        v21 = 2 * v11 + 2;
        v20 = &v24;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v10, 2, v19);
        goto LABEL_22;
      }
    }
    goto LABEL_22;
  }
  v12 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, phkResult);
  v9 = v12;
  if ( !v12 )
  {
    v9 = RegQueryValueExW(*phkResult, L"InterfaceName", 0, &Type, lpData, &cbData);
    if ( !v9 )
    {
      if ( Type == 1 )
        goto LABEL_21;
      v9 = 1015;
    }
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"RegOpenRDInterfaceKey: RegQueryValueEx (%s) failed with error = %d", Name, v9);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&v25[2 * v14 - 4] );
        v22 = 0;
        v21 = 2 * v14 + 2;
        v20 = &v24;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v13, 2, v19);
      }
    }
LABEL_21:
    *((_WORD *)lpData + 256) = 0;
    if ( !v9 )
      return v9;
    goto LABEL_22;
  }
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"RegOpenRDInterfaceKey: RegOpenKeyEx (%s) failed with error = %d", Name, v12);
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&v25[2 * v11 - 4] );
      goto LABEL_6;
    }
  }
LABEL_22:
  if ( *phkResult )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18000a4dc  push    rbp
0x18000a4de  push    rbx
0x18000a4df  push    rsi
0x18000a4e0  push    rdi
0x18000a4e1  push    r12
0x18000a4e3  push    r14
0x18000a4e5  lea     rbp, [rsp-998h]
0x18000a4ed  sub     rsp, 0A98h
0x18000a4f4  mov     rax, cs:__security_cookie
0x18000a4fb  xor     rax, rsp
0x18000a4fe  mov     [rbp+9C0h+var_40], rax
0x18000a505  mov     rdi, r8
0x18000a508  mov     ebx, edx
0x18000a50a  mov     r14, rcx
0x18000a50d  xor     r12d, r12d
0x18000a510  xor     edx, edx; Val
0x18000a512  mov     [rbp+9C0h+var_840], r12d
0x18000a519  mov     r8d, 7FCh; Size
0x18000a51f  lea     rcx, [rbp+9C0h+var_83C]; void *
0x18000a526  mov     rsi, r9
0x18000a529  call    memset_0
0x18000a52e  xor     edx, edx; Val
0x18000a530  lea     rcx, [rsp+0AC0h+Name]; void *
0x18000a535  mov     r8d, 202h; Size
0x18000a53b  call    memset_0
0x18000a540  mov     [rsp+0AC0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000a545  lea     r9, [rsp+0AC0h+cchName]; lpcchName
0x18000a54a  mov     [rsp+0AC0h+lpcchClass], r12; lpcchClass
0x18000a54f  lea     r8, [rsp+0AC0h+Name]; lpName
0x18000a554  mov     [rsp+0AC0h+lpClass], r12; lpClass
0x18000a559  mov     edx, ebx; dwIndex
0x18000a55b  mov     rcx, r14; hKey
0x18000a55e  mov     [rsp+0AC0h+lpReserved], r12; lpReserved
0x18000a563  mov     [rsp+0AC0h+cchName], 101h
0x18000a56b  mov     [rsp+0AC0h+Type], r12d
0x18000a570  mov     [rsp+0AC0h+cbData], 202h
0x18000a578  mov     [rdi], r12
0x18000a57b  call    cs:__imp_RegEnumKeyExW
0x18000a581  mov     ebx, eax
0x18000a583  test    eax, eax
0x18000a585  jz      loc_18000A61C
0x18000a58b  test    cs:byte_1800C8404, 8
0x18000a592  jz      loc_18000A76B
0x18000a598  mov     r8d, eax
0x18000a59b  mov     word ptr [rbp+9C0h+var_840], r12w
0x18000a5a3  lea     rdx, aRegopenrdinter; "RegOpenRDInterfaceKey: RegEnumKeyEx fai"...
0x18000a5aa  lea     rcx, [rbp+9C0h+var_840]
0x18000a5b1  call    FormatRRASErrorString
0x18000a5b6  test    cs:byte_1800C8404, 8
0x18000a5bd  jz      loc_18000A76B
0x18000a5c3  lea     rcx, [rbp+9C0h+var_840]
0x18000a5ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a5ce  inc     rax
0x18000a5d1  cmp     [rcx+rax*2], r12w
0x18000a5d6  jnz     short loc_18000A5CE
0x18000a5d8  lea     eax, ds:2[rax*2]
0x18000a5df  mov     [rsp+0AC0h+var_A54], r12d
0x18000a5e4  lea     rcx, [rbp+9C0h+var_840]
0x18000a5eb  mov     [rsp+0AC0h+var_A58], eax
0x18000a5ef  lea     rax, [rsp+0AC0h+var_A70]
0x18000a5f4  mov     [rsp+0AC0h+var_A60], rcx
0x18000a5f9  mov     r9d, 2
0x18000a5ff  mov     [rsp+0AC0h+lpReserved], rax
0x18000a604  lea     rdx, RasDdmTraceError
0x18000a60b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a612  call    McGenEventWrite_EventWriteTransfer
0x18000a617  jmp     loc_18000A76B
0x18000a61c  mov     r9d, 20019h; samDesired
0x18000a622  mov     [rsp+0AC0h+lpReserved], rdi; phkResult
0x18000a627  xor     r8d, r8d; ulOptions
0x18000a62a  lea     rdx, [rsp+0AC0h+Name]; lpSubKey
0x18000a62f  mov     rcx, r14; hKey
0x18000a632  call    cs:__imp_RegOpenKeyExW
0x18000a638  mov     ebx, eax
0x18000a63a  test    eax, eax
0x18000a63c  jz      short loc_18000A695
0x18000a63e  test    cs:byte_1800C8404, 8
0x18000a645  jz      loc_18000A76B
0x18000a64b  mov     r9d, eax
0x18000a64e  mov     word ptr [rbp+9C0h+var_840], r12w
0x18000a656  lea     r8, [rsp+0AC0h+Name]
0x18000a65b  lea     rdx, aRegopenrdinter_0; "RegOpenRDInterfaceKey: RegOpenKeyEx (%s"...
0x18000a662  lea     rcx, [rbp+9C0h+var_840]
0x18000a669  call    FormatRRASErrorString
0x18000a66e  test    cs:byte_1800C8404, 8
0x18000a675  jz      loc_18000A76B
0x18000a67b  lea     rcx, [rbp+9C0h+var_840]
0x18000a682  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a686  inc     rax
0x18000a689  cmp     [rcx+rax*2], r12w
0x18000a68e  jnz     short loc_18000A686
0x18000a690  jmp     loc_18000A5D8
0x18000a695  mov     rcx, [rdi]; hKey
0x18000a698  lea     rax, [rsp+0AC0h+cbData]
0x18000a69d  mov     [rsp+0AC0h+lpClass], rax; lpcbData
0x18000a6a2  lea     r9, [rsp+0AC0h+Type]; lpType
0x18000a6a7  xor     r8d, r8d; lpReserved
0x18000a6aa  mov     [rsp+0AC0h+lpReserved], rsi; lpData
0x18000a6af  lea     rdx, aInterfacename; "InterfaceName"
0x18000a6b6  call    cs:__imp_RegQueryValueExW
0x18000a6bc  mov     ebx, eax
0x18000a6be  test    eax, eax
0x18000a6c0  jnz     short loc_18000A6D2
0x18000a6c2  cmp     [rsp+0AC0h+Type], 1
0x18000a6c7  jz      loc_18000A75F
0x18000a6cd  mov     ebx, 3F7h
0x18000a6d2  test    cs:byte_1800C8404, 8
0x18000a6d9  jz      loc_18000A75F
0x18000a6df  mov     r9d, ebx
0x18000a6e2  mov     word ptr [rbp+9C0h+var_840], r12w
0x18000a6ea  lea     r8, [rsp+0AC0h+Name]
0x18000a6ef  lea     rdx, aRegopenrdinter_1; "RegOpenRDInterfaceKey: RegQueryValueEx "...
0x18000a6f6  lea     rcx, [rbp+9C0h+var_840]
0x18000a6fd  call    FormatRRASErrorString
0x18000a702  test    cs:byte_1800C8404, 8
0x18000a709  jz      short loc_18000A75F
0x18000a70b  lea     rcx, [rbp+9C0h+var_840]
0x18000a712  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a716  inc     rax
0x18000a719  cmp     [rcx+rax*2], r12w
0x18000a71e  jnz     short loc_18000A716
0x18000a720  lea     eax, ds:2[rax*2]
0x18000a727  mov     [rsp+0AC0h+var_A54], r12d
0x18000a72c  lea     rcx, [rbp+9C0h+var_840]
0x18000a733  mov     [rsp+0AC0h+var_A58], eax
0x18000a737  lea     rax, [rsp+0AC0h+var_A70]
0x18000a73c  mov     [rsp+0AC0h+var_A60], rcx
0x18000a741  mov     r9d, 2
0x18000a747  mov     [rsp+0AC0h+lpReserved], rax
0x18000a74c  lea     rdx, RasDdmTraceError
0x18000a753  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a75a  call    McGenEventWrite_EventWriteTransfer
0x18000a75f  mov     [rsi+200h], r12w
0x18000a767  test    ebx, ebx
0x18000a769  jz      short loc_18000A77C
0x18000a76b  mov     rcx, [rdi]; hKey
0x18000a76e  test    rcx, rcx
0x18000a771  jz      short loc_18000A77C
0x18000a773  call    cs:__imp_RegCloseKey
0x18000a779  mov     [rdi], r12
0x18000a77c  mov     eax, ebx
0x18000a77e  mov     rcx, [rbp+9C0h+var_40]
0x18000a785  xor     rcx, rsp; StackCookie
0x18000a788  call    __security_check_cookie
0x18000a78d  add     rsp, 0A98h
0x18000a794  pop     r14
0x18000a796  pop     r12
0x18000a798  pop     rdi
0x18000a799  pop     rsi
0x18000a79a  pop     rbx
0x18000a79b  pop     rbp
0x18000a79c  retn
```
