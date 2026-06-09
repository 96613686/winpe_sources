# GetRegSettingsBool(HKEY__ *,ushort const *,bool *)

- ea: `0x140004b50`
- end: `0x140004ee8`
- name: `?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z`
- size: `920`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, bool *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400043bc`
- `0x1400046bc`
- `0x140004a90`
- `0x1400051cc`
- `0x140005418`

## callees

- `0x140004b50`
- `0x140009fb8`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x140004d1b`
- `KERNEL32!MultiByteToWideChar` at `0x140004d1b`
- `KERNEL32!WideCharToMultiByte` at `0x140004c07`
- `KERNEL32!WideCharToMultiByte` at `0x140004c58`
- `KERNEL32!WideCharToMultiByte` at `0x140004c07`
- `KERNEL32!WideCharToMultiByte` at `0x140004c58`
- `KERNEL32!GetLastError` at `0x140004c62`
- `KERNEL32!GetLastError` at `0x140004c62`
- `ADVAPI32!RegQueryValueExW` at `0x140004bb8`
- `ADVAPI32!RegQueryValueExW` at `0x140004bb8`
- `ADVAPI32!RegQueryValueExA` at `0x140004cbe`
- `ADVAPI32!RegQueryValueExA` at `0x140004cbe`

## pseudocode

```c
signed int __fastcall GetRegSettingsBool(HKEY hKey, LPCWCH lpWideCharStr, bool *a3)
{
  signed int result; // eax
  bool v7; // cc
  WCHAR *v8; // rdi
  unsigned __int64 v9; // rbx
  int v10; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  DWORD *p_cbData; // r15
  DWORD v16; // ecx
  __int64 v17; // rax
  bool v18; // al
  const wchar_t *v19; // r9
  WCHAR *v20; // r10
  __int64 v21; // r8
  WCHAR v22; // cx
  wchar_t v23; // dx
  const wchar_t *v24; // r9
  WCHAR *v25; // r10
  __int64 v26; // r8
  WCHAR v27; // cx
  wchar_t v28; // dx
  const wchar_t *v29; // r8
  WCHAR *v30; // r9
  WCHAR v31; // cx
  wchar_t v32; // dx
  DWORD cbData; // [rsp+40h] [rbp+0h] BYREF
  DWORD Type[3]; // [rsp+44h] [rbp+4h] BYREF
  CHAR lpData[1024]; // [rsp+50h] [rbp+10h] BYREF
  WCHAR Data[1024]; // [rsp+450h] [rbp+410h] BYREF

  Type[0] = 0;
  cbData = 0;
  if ( Global::g_fWindowsNT )
  {
    cbData = 1024;
    result = RegQueryValueExW(hKey, lpWideCharStr, 0, Type, (LPBYTE)Data, &cbData);
    v7 = result <= 0;
    if ( !result )
    {
      v8 = Data;
      v9 = -1;
      goto LABEL_21;
    }
LABEL_10:
    if ( !v7 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v9 = -1;
  if ( lpWideCharStr )
  {
    v10 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v10 )
      goto LABEL_9;
    v11 = v10 + 15LL;
    if ( v11 < v10 )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
    v13 = alloca(v12);
    v14 = alloca(v12);
    p_cbData = &cbData;
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, (LPSTR)&cbData, v10, 0, 0) )
      goto LABEL_9;
  }
  else
  {
    p_cbData = 0;
  }
  cbData = 1024;
  result = RegQueryValueExA(hKey, (LPCSTR)p_cbData, 0, Type, (LPBYTE)lpData, &cbData);
  v7 = result <= 0;
  if ( result )
    goto LABEL_10;
  v16 = cbData;
  if ( !cbData )
    return -2147467259;
  v17 = cbData - 1;
  if ( (unsigned int)v17 >= 0x400 )
    _report_rangecheckfailure();
  lpData[v17] = 0;
  if ( Type[0] - 1 > 1 )
  {
    v8 = (WCHAR *)lpData;
    goto LABEL_22;
  }
  v8 = 0;
  if ( !MultiByteToWideChar(0, 0, lpData, -1, Data, 1024) )
  {
LABEL_9:
    result = GetLastError();
    v7 = result <= 0;
    goto LABEL_10;
  }
LABEL_21:
  v16 = cbData;
LABEL_22:
  if ( Type[0] == 2 || Type[0] == 1 )
  {
    *a3 = 1;
    v19 = L"0";
    v20 = Data;
    do
      ++v9;
    while ( Data[v9] );
    if ( v9 <= 1 )
      v21 = 1;
    else
      v21 = v9;
    while ( v21 )
    {
      v22 = *v20;
      v23 = *v19;
      if ( *v20 == *v19 )
      {
        if ( !v22 )
          break;
      }
      else
      {
        if ( !v23 || !v22 )
          goto LABEL_42;
        if ( (unsigned __int16)(v22 - 65) <= 0x19u )
          v22 += 32;
        if ( (unsigned __int16)(v23 - 65) <= 0x19u )
          v23 += 32;
        if ( v22 != v23 )
        {
LABEL_42:
          v24 = L"no";
          v25 = Data;
          if ( v9 <= 2 )
            v26 = 2;
          else
            v26 = v9;
          while ( v26 )
          {
            v27 = *v25;
            v28 = *v24;
            if ( *v25 == *v24 )
            {
              if ( !v27 )
                goto LABEL_72;
            }
            else
            {
              if ( !v28 || !v27 )
                goto LABEL_56;
              if ( (unsigned __int16)(v27 - 65) <= 0x19u )
                v27 += 32;
              if ( (unsigned __int16)(v28 - 65) <= 0x19u )
                v28 += 32;
              if ( v27 != v28 )
              {
LABEL_56:
                v29 = L"false";
                v30 = Data;
                if ( v9 <= 5 )
                  v9 = 5;
                while ( v9 )
                {
                  v31 = *v30;
                  v32 = *v29;
                  if ( *v30 == *v29 )
                  {
                    if ( !v31 )
                      goto LABEL_72;
                  }
                  else
                  {
                    if ( !v32 || !v31 )
                      goto LABEL_67;
                    if ( (unsigned __int16)(v31 - 65) <= 0x19u )
                      v31 += 32;
                    if ( (unsigned __int16)(v32 - 65) <= 0x19u )
                      v32 += 32;
                    if ( v31 != v32 )
                    {
LABEL_67:
                      *a3 = 1;
                      return 0;
                    }
                  }
                  --v9;
                  ++v30;
                  ++v29;
                }
                goto LABEL_72;
              }
            }
            --v26;
            ++v25;
            ++v24;
          }
          break;
        }
      }
      --v21;
      ++v20;
      ++v19;
    }
LABEL_72:
    v18 = 0;
  }
  else
  {
    if ( Type[0] != 4 || v16 != 4 )
      return -2147221165;
    v18 = *(_DWORD *)v8 != 0;
  }
  *a3 = v18;
  return 0;
}

```

## disassembly

```asm
0x140004b50  push    rbp
0x140004b52  push    rbx
0x140004b53  push    rsi
0x140004b54  push    rdi
0x140004b55  push    r12
0x140004b57  push    r14
0x140004b59  push    r15
0x140004b5b  sub     rsp, 0C60h
0x140004b62  lea     rbp, [rsp+40h]
0x140004b67  mov     rax, cs:__security_cookie
0x140004b6e  xor     rax, rbp
0x140004b71  mov     [rbp+0C50h+var_40], rax
0x140004b78  xor     r12d, r12d
0x140004b7b  mov     r14, r8
0x140004b7e  cmp     cs:?g_fWindowsNT@Global@@2_NA, r12b; bool Global::g_fWindowsNT
0x140004b85  mov     rdi, rdx
0x140004b88  mov     rsi, rcx
0x140004b8b  mov     [rbp+0C50h+Type], r12d
0x140004b8f  mov     [rbp+0C50h+cbData], r12d
0x140004b93  jz      short loc_140004BD9
0x140004b95  lea     rax, [rbp+0C50h+cbData]
0x140004b99  mov     [rbp+0C50h+cbData], 400h
0x140004ba0  mov     [rsp+0C90h+lpcbData], rax; lpcbData
0x140004ba5  lea     r9, [rbp+0C50h+Type]; lpType
0x140004ba9  lea     rax, [rbp+0C50h+Data]
0x140004bb0  xor     r8d, r8d; lpReserved
0x140004bb3  mov     [rsp+0C90h+lpData], rax; lpData
0x140004bb8  call    cs:__imp_RegQueryValueExW
0x140004bbe  test    eax, eax
0x140004bc0  jnz     loc_140004C6A
0x140004bc6  lea     rdi, [rbp+0C50h+Data]
0x140004bcd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140004bd4  jmp     loc_140004D29
0x140004bd9  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140004be0  test    rdi, rdi
0x140004be3  jz      loc_140004C95
0x140004be9  mov     [rsp+0C90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140004bee  mov     r9d, ebx; cchWideChar
0x140004bf1  mov     [rsp+0C90h+lpDefaultChar], r12; lpDefaultChar
0x140004bf6  mov     r8, rdi; lpWideCharStr
0x140004bf9  mov     dword ptr [rsp+0C90h+lpcbData], r12d; cbMultiByte
0x140004bfe  xor     edx, edx; dwFlags
0x140004c00  xor     ecx, ecx; CodePage
0x140004c02  mov     [rsp+0C90h+lpData], r12; lpMultiByteStr
0x140004c07  call    cs:__imp_WideCharToMultiByte
0x140004c0d  movsxd  rdx, eax
0x140004c10  test    eax, eax
0x140004c12  jz      short loc_140004C62
0x140004c14  lea     rcx, [rdx+0Fh]
0x140004c18  cmp     rcx, rdx
0x140004c1b  ja      short loc_140004C27
0x140004c1d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140004c27  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140004c2b  mov     rax, rcx
0x140004c2e  call    _alloca_probe
0x140004c33  sub     rsp, rcx
0x140004c36  mov     r9d, ebx; cchWideChar
0x140004c39  mov     r8, rdi; lpWideCharStr
0x140004c3c  xor     ecx, ecx; CodePage
0x140004c3e  mov     [rsp+0C90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140004c43  lea     r15, [rsp+0C90h+cbData]
0x140004c48  mov     [rsp+0C90h+lpDefaultChar], r12; lpDefaultChar
0x140004c4d  mov     dword ptr [rsp+0C90h+lpcbData], edx; cbMultiByte
0x140004c51  xor     edx, edx; dwFlags
0x140004c53  mov     [rsp+0C90h+lpData], r15; lpMultiByteStr
0x140004c58  call    cs:__imp_WideCharToMultiByte
0x140004c5e  test    eax, eax
0x140004c60  jnz     short loc_140004C98
0x140004c62  call    cs:__imp_GetLastError
0x140004c68  test    eax, eax
0x140004c6a  jle     short loc_140004C74
0x140004c6c  movzx   eax, ax
0x140004c6f  or      eax, 80070000h
0x140004c74  mov     rcx, [rbp+0C50h+var_40]
0x140004c7b  xor     rcx, rbp; StackCookie
0x140004c7e  call    __security_check_cookie
0x140004c83  lea     rsp, [rbp+0C20h]
0x140004c8a  pop     r15
0x140004c8c  pop     r14
0x140004c8e  pop     r12
0x140004c90  pop     rdi
0x140004c91  pop     rsi
0x140004c92  pop     rbx
0x140004c93  pop     rbp
0x140004c94  retn
0x140004c95  mov     r15, r12
0x140004c98  lea     rax, [rbp+0C50h+cbData]
0x140004c9c  mov     [rbp+0C50h+cbData], 400h
0x140004ca3  mov     [rsp+0C90h+lpcbData], rax; lpcbData
0x140004ca8  lea     r9, [rbp+0C50h+Type]; lpType
0x140004cac  lea     rax, [rbp+0C50h+var_C40]
0x140004cb0  xor     r8d, r8d; lpReserved
0x140004cb3  mov     rdx, r15; lpValueName
0x140004cb6  mov     [rsp+0C90h+lpData], rax; lpData
0x140004cbb  mov     rcx, rsi; hKey
0x140004cbe  call    cs:__imp_RegQueryValueExA
0x140004cc4  test    eax, eax
0x140004cc6  jnz     short loc_140004C6A
0x140004cc8  mov     ecx, [rbp+0C50h+cbData]
0x140004ccb  test    ecx, ecx
0x140004ccd  jnz     short loc_140004CD6
0x140004ccf  mov     eax, 80004005h
0x140004cd4  jmp     short loc_140004C74
0x140004cd6  lea     eax, [rcx-1]
0x140004cd9  cmp     eax, 400h
0x140004cde  jnb     loc_140004EE2
0x140004ce4  mov     [rbp+rax+0C50h+var_C40], r12b
0x140004ce9  mov     eax, [rbp+0C50h+Type]
0x140004cec  dec     eax
0x140004cee  cmp     eax, 1
0x140004cf1  jbe     short loc_140004CF9
0x140004cf3  lea     rdi, [rbp+0C50h+var_C40]
0x140004cf7  jmp     short loc_140004D2C
0x140004cf9  lea     rax, [rbp+0C50h+Data]
0x140004d00  mov     dword ptr [rsp+0C90h+lpcbData], 400h; cchWideChar
0x140004d08  mov     r9d, ebx; cbMultiByte
0x140004d0b  mov     [rsp+0C90h+lpData], rax; lpWideCharStr
0x140004d10  lea     r8, [rbp+0C50h+var_C40]; lpMultiByteStr
0x140004d14  xor     edx, edx; dwFlags
0x140004d16  xor     ecx, ecx; CodePage
0x140004d18  mov     rdi, r12
0x140004d1b  call    cs:__imp_MultiByteToWideChar
0x140004d21  test    eax, eax
0x140004d23  jz      loc_140004C62
0x140004d29  mov     ecx, [rbp+0C50h+cbData]
0x140004d2c  mov     eax, [rbp+0C50h+Type]
0x140004d2f  cmp     eax, 2
0x140004d32  jz      short loc_140004D58
0x140004d34  sub     eax, 1
0x140004d37  jz      short loc_140004D58
0x140004d39  cmp     eax, 3
0x140004d3c  jnz     short loc_140004D4E
0x140004d3e  cmp     ecx, 4
0x140004d41  jnz     short loc_140004D4E
0x140004d43  cmp     [rdi], r12d
0x140004d46  setnz   al
0x140004d49  jmp     loc_140004ED8
0x140004d4e  mov     eax, 80040153h
0x140004d53  jmp     loc_140004C74
0x140004d58  mov     byte ptr [r14], 1
0x140004d5c  lea     r9, a0; "0"
0x140004d63  lea     r10, [rbp+0C50h+Data]
0x140004d6a  lea     rax, [rbp+0C50h+Data]
0x140004d71  inc     rbx
0x140004d74  cmp     [rax+rbx*2], r12w
0x140004d79  jnz     short loc_140004D71
0x140004d7b  cmp     rbx, 1
0x140004d7f  jbe     short loc_140004D86
0x140004d81  mov     r8, rbx
0x140004d84  jmp     short loc_140004D8C
0x140004d86  mov     r8d, 1
0x140004d8c  cmp     r8, 1
0x140004d90  jb      loc_140004ED6
0x140004d96  movzx   ecx, word ptr [r10]
0x140004d9a  movzx   edx, word ptr [r9]
0x140004d9e  cmp     cx, dx
0x140004da1  jz      short loc_140004DE7
0x140004da3  cmp     r12w, dx
0x140004da7  jz      short loc_140004DCE
0x140004da9  cmp     r12w, cx
0x140004dad  jz      short loc_140004DCE
0x140004daf  lea     eax, [rcx-41h]
0x140004db2  cmp     ax, 19h
0x140004db6  ja      short loc_140004DBC
0x140004db8  add     cx, 20h ; ' '
0x140004dbc  lea     eax, [rdx-41h]
0x140004dbf  cmp     ax, 19h
0x140004dc3  ja      short loc_140004DC9
0x140004dc5  add     dx, 20h ; ' '
0x140004dc9  cmp     cx, dx
0x140004dcc  jz      short loc_140004DF1
0x140004dce  lea     r9, aNo_0; "no"
0x140004dd5  lea     r10, [rbp+0C50h+Data]
0x140004ddc  cmp     rbx, 2
0x140004de0  jbe     short loc_140004DFE
0x140004de2  mov     r8, rbx
0x140004de5  jmp     short loc_140004E04
0x140004de7  cmp     r12w, cx
0x140004deb  jz      loc_140004ED6
0x140004df1  dec     r8
0x140004df4  add     r10, 2
0x140004df8  add     r9, 2
0x140004dfc  jmp     short loc_140004D8C
0x140004dfe  mov     r8d, 2
0x140004e04  cmp     r8, 1
0x140004e08  jb      loc_140004ED6
0x140004e0e  movzx   ecx, word ptr [r10]
0x140004e12  movzx   edx, word ptr [r9]
0x140004e16  cmp     cx, dx
0x140004e19  jz      loc_140004EAD
0x140004e1f  cmp     r12w, dx
0x140004e23  jz      short loc_140004E4A
0x140004e25  cmp     r12w, cx
0x140004e29  jz      short loc_140004E4A
0x140004e2b  lea     eax, [rcx-41h]
0x140004e2e  cmp     ax, 19h
0x140004e32  ja      short loc_140004E38
0x140004e34  add     cx, 20h ; ' '
0x140004e38  lea     eax, [rdx-41h]
0x140004e3b  cmp     ax, 19h
0x140004e3f  ja      short loc_140004E45
0x140004e41  add     dx, 20h ; ' '
0x140004e45  cmp     cx, dx
0x140004e48  jz      short loc_140004EB3
0x140004e4a  lea     r8, aFalse; "false"
0x140004e51  lea     r9, [rbp+0C50h+Data]
0x140004e58  cmp     rbx, 5
0x140004e5c  ja      short loc_140004E63
0x140004e5e  mov     ebx, 5
0x140004e63  cmp     rbx, 1
0x140004e67  jb      short loc_140004ED6
0x140004e69  movzx   ecx, word ptr [r9]
0x140004e6d  movzx   edx, word ptr [r8]
0x140004e71  cmp     cx, dx
0x140004e74  jz      short loc_140004EC3
0x140004e76  cmp     r12w, dx
0x140004e7a  jz      short loc_140004EA1
0x140004e7c  cmp     r12w, cx
0x140004e80  jz      short loc_140004EA1
0x140004e82  lea     eax, [rcx-41h]
0x140004e85  cmp     ax, 19h
0x140004e89  ja      short loc_140004E8F
0x140004e8b  add     cx, 20h ; ' '
0x140004e8f  lea     eax, [rdx-41h]
0x140004e92  cmp     ax, 19h
0x140004e96  ja      short loc_140004E9C
0x140004e98  add     dx, 20h ; ' '
0x140004e9c  cmp     cx, dx
0x140004e9f  jz      short loc_140004EC9
0x140004ea1  mov     al, 1
0x140004ea3  mov     [r14], al
0x140004ea6  xor     eax, eax
0x140004ea8  jmp     loc_140004C74
0x140004ead  cmp     r12w, cx
0x140004eb1  jz      short loc_140004ED6
0x140004eb3  dec     r8
0x140004eb6  add     r10, 2
0x140004eba  add     r9, 2
0x140004ebe  jmp     loc_140004E04
0x140004ec3  cmp     r12w, cx
0x140004ec7  jz      short loc_140004ED6
0x140004ec9  dec     rbx
0x140004ecc  add     r9, 2
0x140004ed0  add     r8, 2
0x140004ed4  jmp     short loc_140004E63
0x140004ed6  xor     al, al
0x140004ed8  mov     [r14], al
0x140004edb  xor     eax, eax
0x140004edd  jmp     loc_140004C74
0x140004ee2  call    __report_rangecheckfailure
```
