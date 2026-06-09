# registerSnapshotInstance

- ea: `0x1800b6c44`
- end: `0x1800b7005`
- name: `registerSnapshotInstance`
- size: `961`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a504c`

## callees

- `0x18001e090`
- `0x18003cf0c`
- `0x1800b6c44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b6fd3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18045a7c9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b6fd3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18045a7c9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b6d10`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800b6d10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b6cb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b6e6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b6cb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b6e6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6eb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6fab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6fc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18045a797`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18045a7af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6eb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6fab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b6fc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18045a797`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18045a7af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b6cf3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b6f01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b6cf3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800b6f01`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x1800b6e87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x1800b6f83`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x1800b6e87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x1800b6f83`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b6f36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b6f6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b6f36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800b6f6b`

## string_xrefs

- `0x1800b6ca3`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Active Directory\DMT\`
- `0x1800b6ce5`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Active Directory\DMT\`

## pseudocode

```c
__int64 __fastcall registerSnapshotInstance(int a1, int a2)
{
  char *v2; // rsi
  unsigned int v3; // ebx
  __int64 v4; // rax
  const char *v5; // r10
  __int64 v6; // r9
  char *v7; // rcx
  int v8; // edx
  __int64 v9; // r8
  int v10; // eax
  HKEY hKey; // [rsp+58h] [rbp-190h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-188h] BYREF
  int v14; // [rsp+68h] [rbp-180h]
  BYTE Data[8]; // [rsp+70h] [rbp-178h] BYREF
  BYTE v16[8]; // [rsp+78h] [rbp-170h] BYREF
  char *v17; // [rsp+80h] [rbp-168h]
  char *v18; // [rsp+88h] [rbp-160h]
  __int64 v19; // [rsp+90h] [rbp-158h]
  const char *v20; // [rsp+98h] [rbp-150h]
  __int64 v21; // [rsp+A0h] [rbp-148h]
  __int64 v22; // [rsp+A8h] [rbp-140h]
  CHAR SubKey[272]; // [rsp+B0h] [rbp-138h] BYREF

  *(_DWORD *)Data = a1;
  *(_DWORD *)v16 = a2;
  v2 = 0;
  v17 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v3 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Active Directory\\DMT\\",
         0,
         0x20006u,
         &hKey);
  if ( v3 == 2 )
    v3 = RegCreateKeyExA(
           HKEY_LOCAL_MACHINE,
           "SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Active Directory\\DMT\\",
           0,
           0,
           0,
           0x20006u,
           0,
           &hKey,
           0);
  if ( !v3 )
  {
    v2 = (char *)malloc(0x104u);
    v17 = v2;
    v14 = 0;
    v4 = 6;
    v22 = 6;
    v5 = "$SNAP_";
    v20 = "$SNAP_";
    v6 = 260;
    v21 = 260;
    v7 = v2;
    v18 = v2;
    v8 = 0;
    v9 = 0;
    v19 = 0;
    while ( v6 )
    {
      if ( !v4 || !*v5 )
        goto LABEL_11;
      *v7++ = *v5;
      v18 = v7;
      v20 = ++v5;
      v21 = --v6;
      v22 = --v4;
      v19 = ++v9;
    }
    v18 = --v7;
    v19 = v9 - 1;
    v8 = -2147024774;
LABEL_11:
    *v7 = 0;
    v14 = v8;
    if ( v8 < 0 )
    {
      v3 = (unsigned __int16)v8;
    }
    else
    {
      v10 = StringCchPrintfA(gfRegSnapshotKeyName, 0x104u, "%s%d", v2, *(_DWORD *)Data);
      v3 = v10;
      if ( v10 >= 0 )
      {
        v10 = StringCchPrintfA(SubKey, 0x104u, "%s%s", gfRegSnapshotKeyName, "\\Parameters");
        v3 = v10;
        if ( v10 >= 0 )
        {
          v3 = RegOpenKeyExA(hKey, gfRegSnapshotKeyName, 0, 0x20006u, &phkResult);
          if ( !v3 )
          {
            v3 = RegDeleteTreeA(hKey, gfRegSnapshotKeyName);
            if ( (v3 & 0xFFFFFFFD) != 0 )
              goto LABEL_29;
            v3 = 2;
          }
          if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          {
            RegCloseKey(phkResult);
            phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
          }
          if ( v3 == 2 )
          {
            v3 = RegCreateKeyExA(hKey, SubKey, 0, 0, 1u, 0x20006u, 0, &phkResult, 0);
            if ( !v3 )
              v3 = RegSetValueExA(phkResult, "Port LDAP", 0, 4u, Data, 4u);
            if ( v3 )
            {
LABEL_27:
              RegDeleteTreeA(hKey, gfRegSnapshotKeyName);
              goto LABEL_29;
            }
            v3 = RegSetValueExA(phkResult, "Port SSL", 0, 4u, v16, 4u);
          }
          if ( !v3 )
            goto LABEL_29;
          goto LABEL_27;
        }
      }
      if ( (v10 & 0x1FFF0000) == 0x70000 )
        v3 = (unsigned __int16)v3;
    }
  }
LABEL_29:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(phkResult);
    phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( v2 )
    free(v2);
  return v3;
}

```

## disassembly

```asm
0x1800b6c44  mov     [rsp+arg_10], rbx
0x1800b6c49  mov     [rsp+arg_18], rsi
0x1800b6c4e  push    r12
0x1800b6c50  push    r13
0x1800b6c52  push    r15
0x1800b6c54  sub     rsp, 1D0h
0x1800b6c5b  mov     rax, cs:__security_cookie
0x1800b6c62  xor     rax, rsp
0x1800b6c65  mov     [rsp+1E8h+var_28], rax
0x1800b6c6d  mov     dword ptr [rsp+1E8h+Data], ecx
0x1800b6c71  mov     dword ptr [rsp+1E8h+var_170], edx
0x1800b6c75  xor     esi, esi
0x1800b6c77  mov     [rsp+1E8h+var_168], rsi
0x1800b6c7f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800b6c83  mov     [rsp+1E8h+hKey], r15
0x1800b6c88  mov     [rsp+1E8h+var_188], r15
0x1800b6c8d  lea     rax, [rsp+1E8h+hKey]
0x1800b6c92  mov     [rsp+1E8h+phkResult], rax; phkResult
0x1800b6c97  mov     r12d, 20006h
0x1800b6c9d  mov     r9d, r12d; samDesired
0x1800b6ca0  xor     r8d, r8d; ulOptions
0x1800b6ca3  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800b6caa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b6cb1  call    cs:__imp_RegOpenKeyExA
0x1800b6cb7  mov     ebx, eax
0x1800b6cb9  mov     [rsp+1E8h+var_198], eax
0x1800b6cbd  cmp     eax, 2
0x1800b6cc0  jnz     short loc_1800B6CFF
0x1800b6cc2  mov     [rsp+1E8h+lpdwDisposition], rsi; lpdwDisposition
0x1800b6cc7  lea     rax, [rsp+1E8h+hKey]
0x1800b6ccc  mov     [rsp+1E8h+var_1B0], rax; phkResult
0x1800b6cd1  mov     [rsp+1E8h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800b6cd6  mov     [rsp+1E8h+samDesired], r12d; samDesired
0x1800b6cdb  mov     dword ptr [rsp+1E8h+phkResult], esi; dwOptions
0x1800b6cdf  xor     r9d, r9d; lpClass
0x1800b6ce2  xor     r8d, r8d; Reserved
0x1800b6ce5  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800b6cec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b6cf3  call    cs:__imp_RegCreateKeyExA
0x1800b6cf9  mov     ebx, eax
0x1800b6cfb  mov     [rsp+1E8h+var_198], eax
0x1800b6cff  test    ebx, ebx
0x1800b6d01  jnz     loc_1800B6FA1
0x1800b6d07  mov     r13d, 104h
0x1800b6d0d  mov     ecx, r13d; Size
0x1800b6d10  call    cs:__imp_malloc
0x1800b6d16  mov     rsi, rax
0x1800b6d19  mov     [rsp+1E8h+var_168], rax
0x1800b6d21  mov     [rsp+1E8h+var_180], ebx
0x1800b6d25  mov     [rsp+1E8h+var_180], ebx
0x1800b6d29  lea     eax, [rbx+6]
0x1800b6d2c  mov     [rsp+1E8h+var_140], rax
0x1800b6d34  lea     r10, aSnap; "$SNAP_"
0x1800b6d3b  mov     [rsp+1E8h+var_150], r10
0x1800b6d43  mov     r9d, r13d
0x1800b6d46  mov     [rsp+1E8h+var_148], r13
0x1800b6d4e  mov     rcx, rsi
0x1800b6d51  mov     [rsp+1E8h+var_160], rcx
0x1800b6d59  xor     edx, edx
0x1800b6d5b  xor     r8d, r8d
0x1800b6d5e  mov     [rsp+1E8h+var_158], r8
0x1800b6d66  test    r9, r9
0x1800b6d69  jz      short loc_1800B6DB9
0x1800b6d6b  test    rax, rax
0x1800b6d6e  jz      short loc_1800B6DB4
0x1800b6d70  mov     r11b, [r10]
0x1800b6d73  test    r11b, r11b
0x1800b6d76  jz      short loc_1800B6DB4
0x1800b6d78  mov     [rcx], r11b
0x1800b6d7b  inc     rcx
0x1800b6d7e  mov     [rsp+1E8h+var_160], rcx
0x1800b6d86  inc     r10
0x1800b6d89  mov     [rsp+1E8h+var_150], r10
0x1800b6d91  dec     r9
0x1800b6d94  mov     [rsp+1E8h+var_148], r9
0x1800b6d9c  dec     rax
0x1800b6d9f  mov     [rsp+1E8h+var_140], rax
0x1800b6da7  inc     r8
0x1800b6daa  mov     [rsp+1E8h+var_158], r8
0x1800b6db2  jmp     short loc_1800B6D66
0x1800b6db4  test    r9, r9
0x1800b6db7  jnz     short loc_1800B6DD4
0x1800b6db9  dec     rcx
0x1800b6dbc  mov     [rsp+1E8h+var_160], rcx
0x1800b6dc4  dec     r8
0x1800b6dc7  mov     [rsp+1E8h+var_158], r8
0x1800b6dcf  mov     edx, 8007007Ah
0x1800b6dd4  mov     byte ptr [rcx], 0
0x1800b6dd7  mov     [rsp+1E8h+var_180], edx
0x1800b6ddb  test    edx, edx
0x1800b6ddd  js      loc_1800B6F8B
0x1800b6de3  mov     eax, dword ptr [rsp+1E8h+Data]
0x1800b6de7  mov     dword ptr [rsp+1E8h+phkResult], eax
0x1800b6deb  mov     r9, rsi
0x1800b6dee  lea     r8, aSD; "%s%d"
0x1800b6df5  mov     rdx, r13; unsigned __int64
0x1800b6df8  lea     r12, gfRegSnapshotKeyName
0x1800b6dff  mov     rcx, r12; char *
0x1800b6e02  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800b6e07  mov     ebx, eax
0x1800b6e09  test    eax, eax
0x1800b6e0b  jns     short loc_1800B6E25
0x1800b6e0d  and     eax, 1FFF0000h
0x1800b6e12  cmp     eax, 70000h
0x1800b6e17  jnz     loc_1800B6F9D
0x1800b6e1d  movzx   ebx, bx
0x1800b6e20  jmp     loc_1800B6F9D
0x1800b6e25  lea     rax, aParameters; "\\Parameters"
0x1800b6e2c  mov     [rsp+1E8h+phkResult], rax
0x1800b6e31  mov     r9, r12
0x1800b6e34  lea     r8, aSS_2; "%s%s"
0x1800b6e3b  mov     rdx, r13; unsigned __int64
0x1800b6e3e  lea     rcx, [rsp+1E8h+SubKey]; char *
0x1800b6e46  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800b6e4b  mov     ebx, eax
0x1800b6e4d  test    eax, eax
0x1800b6e4f  js      short loc_1800B6E0D
0x1800b6e51  lea     rax, [rsp+1E8h+var_188]
0x1800b6e56  mov     [rsp+1E8h+phkResult], rax; phkResult
0x1800b6e5b  mov     r13d, 20006h
0x1800b6e61  mov     r9d, r13d; samDesired
0x1800b6e64  xor     r8d, r8d; ulOptions
0x1800b6e67  mov     rdx, r12; lpSubKey
0x1800b6e6a  mov     rcx, [rsp+1E8h+hKey]; hKey
0x1800b6e6f  call    cs:__imp_RegOpenKeyExA
0x1800b6e75  mov     ebx, eax
0x1800b6e77  mov     [rsp+1E8h+var_198], eax
0x1800b6e7b  test    eax, eax
0x1800b6e7d  jnz     short loc_1800B6EA7
0x1800b6e7f  mov     rdx, r12; lpSubKey
0x1800b6e82  mov     rcx, [rsp+1E8h+hKey]; hKey
0x1800b6e87  call    cs:__imp_RegDeleteTreeA
0x1800b6e8d  mov     ebx, eax
0x1800b6e8f  mov     [rsp+1E8h+var_198], eax
0x1800b6e93  test    eax, 0FFFFFFFDh
0x1800b6e98  jnz     loc_1800B6FA1
0x1800b6e9e  mov     ebx, 2
0x1800b6ea3  mov     [rsp+1E8h+var_198], ebx
0x1800b6ea7  mov     rcx, [rsp+1E8h+var_188]; hKey
0x1800b6eac  cmp     rcx, r15
0x1800b6eaf  jz      short loc_1800B6EBC
0x1800b6eb1  call    cs:__imp_RegCloseKey
0x1800b6eb7  mov     [rsp+1E8h+var_188], r15
0x1800b6ebc  cmp     ebx, 2
0x1800b6ebf  jnz     loc_1800B6F77
0x1800b6ec5  mov     [rsp+1E8h+lpdwDisposition], 0; lpdwDisposition
0x1800b6ece  lea     rax, [rsp+1E8h+var_188]
0x1800b6ed3  mov     [rsp+1E8h+var_1B0], rax; phkResult
0x1800b6ed8  mov     [rsp+1E8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b6ee1  mov     [rsp+1E8h+samDesired], r13d; samDesired
0x1800b6ee6  mov     dword ptr [rsp+1E8h+phkResult], 1; dwOptions
0x1800b6eee  xor     r9d, r9d; lpClass
0x1800b6ef1  xor     r8d, r8d; Reserved
0x1800b6ef4  lea     rdx, [rsp+1E8h+SubKey]; lpSubKey
0x1800b6efc  mov     rcx, [rsp+1E8h+hKey]; hKey
0x1800b6f01  call    cs:__imp_RegCreateKeyExA
0x1800b6f07  mov     ebx, eax
0x1800b6f09  mov     [rsp+1E8h+var_198], eax
0x1800b6f0d  test    eax, eax
0x1800b6f0f  jnz     short loc_1800B6F42
0x1800b6f11  mov     [rsp+1E8h+samDesired], 4; cbData
0x1800b6f19  lea     rax, [rsp+1E8h+Data]
0x1800b6f1e  mov     [rsp+1E8h+phkResult], rax; lpData
0x1800b6f23  lea     r9d, [rbx+4]; dwType
0x1800b6f27  xor     r8d, r8d; Reserved
0x1800b6f2a  lea     rdx, aPortLdap; "Port LDAP"
0x1800b6f31  mov     rcx, [rsp+1E8h+var_188]; hKey
0x1800b6f36  call    cs:__imp_RegSetValueExA
0x1800b6f3c  mov     ebx, eax
0x1800b6f3e  mov     [rsp+1E8h+var_198], eax
0x1800b6f42  test    ebx, ebx
0x1800b6f44  jnz     short loc_1800B6F7B
0x1800b6f46  mov     [rsp+1E8h+samDesired], 4; cbData
0x1800b6f4e  lea     rax, [rsp+1E8h+var_170]
0x1800b6f53  mov     [rsp+1E8h+phkResult], rax; lpData
0x1800b6f58  lea     r9d, [rbx+4]; dwType
0x1800b6f5c  xor     r8d, r8d; Reserved
0x1800b6f5f  lea     rdx, aPortSsl; "Port SSL"
0x1800b6f66  mov     rcx, [rsp+1E8h+var_188]; hKey
0x1800b6f6b  call    cs:__imp_RegSetValueExA
0x1800b6f71  mov     ebx, eax
0x1800b6f73  mov     [rsp+1E8h+var_198], eax
0x1800b6f77  test    ebx, ebx
0x1800b6f79  jz      short loc_1800B6FA1
0x1800b6f7b  mov     rdx, r12; lpSubKey
0x1800b6f7e  mov     rcx, [rsp+1E8h+hKey]; hKey
0x1800b6f83  call    cs:__imp_RegDeleteTreeA
0x1800b6f89  jmp     short loc_1800B6FA1
0x1800b6f8b  mov     eax, edx
0x1800b6f8d  and     eax, 1FFF0000h
0x1800b6f92  movzx   ebx, dx
0x1800b6f95  cmp     eax, 70000h
0x1800b6f9a  cmovnz  ebx, edx
0x1800b6f9d  mov     [rsp+1E8h+var_198], ebx
0x1800b6fa1  mov     rcx, [rsp+1E8h+hKey]; hKey
0x1800b6fa6  cmp     rcx, r15
0x1800b6fa9  jz      short loc_1800B6FB6
0x1800b6fab  call    cs:__imp_RegCloseKey
0x1800b6fb1  mov     [rsp+1E8h+hKey], r15
0x1800b6fb6  mov     rcx, [rsp+1E8h+var_188]; hKey
0x1800b6fbb  cmp     rcx, r15
0x1800b6fbe  jz      short loc_1800B6FCB
0x1800b6fc0  call    cs:__imp_RegCloseKey
0x1800b6fc6  mov     [rsp+1E8h+var_188], r15
0x1800b6fcb  test    rsi, rsi
0x1800b6fce  jz      short loc_1800B6FD9
0x1800b6fd0  mov     rcx, rsi; Block
0x1800b6fd3  call    cs:__imp_free
0x1800b6fd9  mov     eax, ebx
0x1800b6fdb  mov     rcx, [rsp+1E8h+var_28]
0x1800b6fe3  xor     rcx, rsp; StackCookie
0x1800b6fe6  call    __security_check_cookie
0x1800b6feb  lea     r11, [rsp+1E8h+var_18]
0x1800b6ff3  mov     rbx, [r11+30h]
0x1800b6ff7  mov     rsi, [r11+38h]
0x1800b6ffb  mov     rsp, r11
0x1800b6ffe  pop     r15
0x1800b7000  pop     r13
0x1800b7002  pop     r12
0x1800b7004  retn
0x18045a784  push    rbp
0x18045a786  sub     rsp, 50h
0x18045a78a  mov     rbp, rdx
0x18045a78d  mov     rcx, [rbp+58h]; hKey
0x18045a791  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18045a795  jz      short loc_18045A7A5
0x18045a797  call    cs:__imp_RegCloseKey
0x18045a79d  mov     qword ptr [rbp+58h], 0FFFFFFFFFFFFFFFFh
0x18045a7a5  mov     rcx, [rbp+60h]; hKey
0x18045a7a9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18045a7ad  jz      short loc_18045A7BD
0x18045a7af  call    cs:__imp_RegCloseKey
0x18045a7b5  mov     qword ptr [rbp+60h], 0FFFFFFFFFFFFFFFFh
0x18045a7bd  mov     rcx, [rbp+80h]; Block
0x18045a7c4  test    rcx, rcx
0x18045a7c7  jz      short loc_18045A7DA
0x18045a7c9  call    cs:__imp_free
0x18045a7cf  mov     qword ptr [rbp+80h], 0
0x18045a7da  add     rsp, 50h
0x18045a7de  pop     rbp
0x18045a7df  retn
```
