# Helper::CanDeleteFileWithoutElevation(ushort *,int *)

- ea: `0x180013c00`
- end: `0x180013ebb`
- name: `?CanDeleteFileWithoutElevation@Helper@@YAJPEAGPEAH@Z`
- size: `699`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPBOOL AccessStatus, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000f654`

## callees

- `0x180001340`
- `0x18000138c`
- `0x180013c00`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180013c91`
- `KERNEL32!GetLastError` at `0x180013cf3`
- `KERNEL32!GetLastError` at `0x180013d6c`
- `KERNEL32!GetLastError` at `0x180013db4`
- `KERNEL32!GetLastError` at `0x180013df7`
- `KERNEL32!GetLastError` at `0x180013e4f`
- `KERNEL32!GetLastError` at `0x180013c91`
- `KERNEL32!GetLastError` at `0x180013cf3`
- `KERNEL32!GetLastError` at `0x180013d6c`
- `KERNEL32!GetLastError` at `0x180013db4`
- `KERNEL32!GetLastError` at `0x180013df7`
- `KERNEL32!GetLastError` at `0x180013e4f`
- `KERNEL32!CloseHandle` at `0x180013e7c`
- `KERNEL32!CloseHandle` at `0x180013e8b`
- `KERNEL32!CloseHandle` at `0x180013e7c`
- `KERNEL32!CloseHandle` at `0x180013e8b`
- `KERNEL32!GetFileAttributesW` at `0x180013c80`
- `KERNEL32!GetFileAttributesW` at `0x180013c80`
- `KERNEL32!GetCurrentProcess` at `0x180013d90`
- `KERNEL32!GetCurrentProcess` at `0x180013d90`
- `ADVAPI32!DuplicateToken` at `0x180013de5`
- `ADVAPI32!DuplicateToken` at `0x180013de5`
- `ADVAPI32!GetFileSecurityW` at `0x180013cdf`
- `ADVAPI32!GetFileSecurityW` at `0x180013d62`
- `ADVAPI32!GetFileSecurityW` at `0x180013cdf`
- `ADVAPI32!GetFileSecurityW` at `0x180013d62`
- `ADVAPI32!OpenProcessToken` at `0x180013da2`
- `ADVAPI32!OpenProcessToken` at `0x180013da2`
- `ADVAPI32!AccessCheck` at `0x180013e45`
- `ADVAPI32!AccessCheck` at `0x180013e45`

## pseudocode

```c
__int64 __fastcall Helper::CanDeleteFileWithoutElevation(LPCWSTR lpFileName, LPBOOL AccessStatus, int *a3)
{
  void *v5; // r14
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  signed int v8; // ebx
  DWORD v9; // edi
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  HANDLE CurrentProcess; // rax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-19h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-11h] BYREF
  void *DuplicateTokenHandle; // [rsp+50h] [rbp-9h] BYREF
  DWORD GrantedAccess; // [rsp+58h] [rbp-1h] BYREF
  DWORD PrivilegeSetLength; // [rsp+5Ch] [rbp+3h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+7h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+17h] BYREF

  TokenHandle = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GrantedAccess = 0;
  *AccessStatus = 0;
  DuplicateTokenHandle = 0;
  v5 = 0;
  nLengthNeeded = 0;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  PrivilegeSetLength = 20;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    v9 = 0x10000;
    if ( v8 < 0 )
      goto LABEL_44;
  }
  else
  {
    v9 = 0x10000;
    if ( (FileAttributesW & 1) != 0 )
      v9 = 65792;
  }
  if ( GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded) )
  {
    v8 = -2147418113;
    goto LABEL_44;
  }
  v10 = GetLastError();
  v8 = v10;
  if ( !v10 )
  {
LABEL_43:
    v8 = -2147467259;
    goto LABEL_44;
  }
  if ( v10 > 0 )
    v8 = (unsigned __int16)v10 | 0x80070000;
  if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147024774 )
  {
    v11 = 0;
    if ( v8 != -2147024774 )
      v11 = v8;
    v8 = v11;
    v5 = operator new[](nLengthNeeded);
    if ( !v5 )
    {
      v8 = -2147024882;
      goto LABEL_44;
    }
    if ( GetFileSecurityW(lpFileName, 7u, v5, nLengthNeeded, &nLengthNeeded) )
      goto LABEL_51;
    v12 = GetLastError();
    v8 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    if ( v8 >= 0 )
    {
LABEL_51:
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
        goto LABEL_52;
      TokenHandle = 0;
      v14 = GetLastError();
      v8 = v14;
      if ( v14 )
      {
        if ( v14 > 0 )
          v8 = (unsigned __int16)v14 | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      if ( v8 >= 0 )
      {
LABEL_52:
        if ( DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
          goto LABEL_53;
        DuplicateTokenHandle = 0;
        v15 = GetLastError();
        v8 = v15;
        if ( v15 )
        {
          if ( v15 > 0 )
            v8 = (unsigned __int16)v15 | 0x80070000;
        }
        else
        {
          v8 = -2147467259;
        }
        if ( v8 >= 0 )
        {
LABEL_53:
          if ( !AccessCheck(
                  v5,
                  DuplicateTokenHandle,
                  v9,
                  &GenericMapping,
                  &PrivilegeSet,
                  &PrivilegeSetLength,
                  &GrantedAccess,
                  AccessStatus) )
          {
            v16 = GetLastError();
            v8 = v16;
            if ( v16 )
            {
              if ( v16 > 0 )
                v8 = (unsigned __int16)v16 | 0x80070000;
              goto LABEL_44;
            }
            goto LABEL_43;
          }
        }
      }
    }
  }
LABEL_44:
  operator delete[](v5);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180013c00  mov     [rsp-8+arg_10], rbx
0x180013c05  mov     [rsp-8+arg_18], rsi
0x180013c0a  push    rbp
0x180013c0b  push    rdi
0x180013c0c  push    r13
0x180013c0e  push    r14
0x180013c10  push    r15
0x180013c12  lea     rbp, [rsp-37h]
0x180013c17  sub     rsp, 90h
0x180013c1e  mov     rax, cs:__security_cookie
0x180013c25  xor     rax, rsp
0x180013c28  mov     [rbp+57h+var_28], rax
0x180013c2c  xor     eax, eax
0x180013c2e  mov     [rbp+57h+TokenHandle], 0
0x180013c36  xorps   xmm0, xmm0
0x180013c39  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x180013c3c  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x180013c40  mov     [rbp+57h+var_58], eax
0x180013c43  mov     r15, rdx
0x180013c46  mov     [rdx], eax
0x180013c48  mov     rsi, rcx
0x180013c4b  mov     [rbp+57h+DuplicateTokenHandle], 0
0x180013c53  xor     r14d, r14d
0x180013c56  mov     [rbp+57h+nLengthNeeded], 0
0x180013c5d  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x180013c64  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x180013c6b  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x180013c72  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x180013c79  mov     [rbp+57h+var_54], 14h
0x180013c80  call    cs:__imp_GetFileAttributesW
0x180013c86  mov     r13d, 80004005h
0x180013c8c  cmp     eax, 0FFFFFFFFh
0x180013c8f  jnz     short loc_180013CBB
0x180013c91  call    cs:__imp_GetLastError
0x180013c97  mov     ebx, eax
0x180013c99  test    eax, eax
0x180013c9b  jz      short loc_180013CAA
0x180013c9d  jle     short loc_180013CAD
0x180013c9f  movzx   ebx, ax
0x180013ca2  or      ebx, 80070000h
0x180013ca8  jmp     short loc_180013CAD
0x180013caa  mov     ebx, r13d
0x180013cad  mov     edi, 10000h
0x180013cb2  test    ebx, ebx
0x180013cb4  jns     short loc_180013CC9
0x180013cb6  jmp     loc_180013E6B
0x180013cbb  mov     edi, 10000h
0x180013cc0  test    al, 1
0x180013cc2  jz      short loc_180013CC9
0x180013cc4  mov     edi, 10100h
0x180013cc9  xor     r9d, r9d; nLength
0x180013ccc  lea     rax, [rbp+57h+nLengthNeeded]
0x180013cd0  xor     r8d, r8d; pSecurityDescriptor
0x180013cd3  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180013cd8  mov     rcx, rsi; lpFileName
0x180013cdb  lea     edx, [r9+7]; RequestedInformation
0x180013cdf  call    cs:__imp_GetFileSecurityW
0x180013ce5  test    eax, eax
0x180013ce7  jz      short loc_180013CF3
0x180013ce9  mov     ebx, 8000FFFFh
0x180013cee  jmp     loc_180013E6B
0x180013cf3  call    cs:__imp_GetLastError
0x180013cf9  mov     ebx, eax
0x180013cfb  test    eax, eax
0x180013cfd  jz      loc_180013E68
0x180013d03  jle     short loc_180013D0E
0x180013d05  movzx   ebx, ax
0x180013d08  or      ebx, 80070000h
0x180013d0e  mov     ecx, 80000000h
0x180013d13  mov     edx, 8007007Ah
0x180013d18  lea     eax, [rbx+rcx]
0x180013d1b  test    ecx, eax
0x180013d1d  jnz     short loc_180013D27
0x180013d1f  cmp     ebx, edx
0x180013d21  jnz     loc_180013E6B
0x180013d27  mov     ecx, [rbp+57h+nLengthNeeded]; unsigned __int64
0x180013d2a  xor     eax, eax
0x180013d2c  cmp     ebx, edx
0x180013d2e  cmovnz  eax, ebx
0x180013d31  mov     ebx, eax
0x180013d33  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013d38  mov     r14, rax
0x180013d3b  test    rax, rax
0x180013d3e  jnz     short loc_180013D4A
0x180013d40  mov     ebx, 8007000Eh
0x180013d45  jmp     loc_180013E6B
0x180013d4a  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180013d4e  lea     rax, [rbp+57h+nLengthNeeded]
0x180013d52  mov     r8, r14; pSecurityDescriptor
0x180013d55  mov     [rsp+0B0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180013d5a  mov     edx, 7; RequestedInformation
0x180013d5f  mov     rcx, rsi; lpFileName
0x180013d62  call    cs:__imp_GetFileSecurityW
0x180013d68  test    eax, eax
0x180013d6a  jnz     short loc_180013D90
0x180013d6c  call    cs:__imp_GetLastError
0x180013d72  mov     ebx, eax
0x180013d74  test    eax, eax
0x180013d76  jz      short loc_180013D85
0x180013d78  jle     short loc_180013D88
0x180013d7a  movzx   ebx, ax
0x180013d7d  or      ebx, 80070000h
0x180013d83  jmp     short loc_180013D88
0x180013d85  mov     ebx, r13d
0x180013d88  test    ebx, ebx
0x180013d8a  js      loc_180013E6B
0x180013d90  call    cs:__imp_GetCurrentProcess
0x180013d96  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180013d9a  mov     edx, 0Ah; DesiredAccess
0x180013d9f  mov     rcx, rax; ProcessHandle
0x180013da2  call    cs:__imp_OpenProcessToken
0x180013da8  test    eax, eax
0x180013daa  jnz     short loc_180013DD8
0x180013dac  mov     [rbp+57h+TokenHandle], 0
0x180013db4  call    cs:__imp_GetLastError
0x180013dba  mov     ebx, eax
0x180013dbc  test    eax, eax
0x180013dbe  jz      short loc_180013DCD
0x180013dc0  jle     short loc_180013DD0
0x180013dc2  movzx   ebx, ax
0x180013dc5  or      ebx, 80070000h
0x180013dcb  jmp     short loc_180013DD0
0x180013dcd  mov     ebx, r13d
0x180013dd0  test    ebx, ebx
0x180013dd2  js      loc_180013E6B
0x180013dd8  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180013ddc  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180013de0  mov     edx, 2; ImpersonationLevel
0x180013de5  call    cs:__imp_DuplicateToken
0x180013deb  test    eax, eax
0x180013ded  jnz     short loc_180013E17
0x180013def  mov     [rbp+57h+DuplicateTokenHandle], 0
0x180013df7  call    cs:__imp_GetLastError
0x180013dfd  mov     ebx, eax
0x180013dff  test    eax, eax
0x180013e01  jz      short loc_180013E10
0x180013e03  jle     short loc_180013E13
0x180013e05  movzx   ebx, ax
0x180013e08  or      ebx, 80070000h
0x180013e0e  jmp     short loc_180013E13
0x180013e10  mov     ebx, r13d
0x180013e13  test    ebx, ebx
0x180013e15  js      short loc_180013E6B
0x180013e17  mov     rdx, [rbp+57h+DuplicateTokenHandle]; ClientToken
0x180013e1b  lea     rax, [rbp+57h+var_58]
0x180013e1f  mov     [rsp+0B0h+AccessStatus], r15; AccessStatus
0x180013e24  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180013e28  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180013e2d  mov     r8d, edi; DesiredAccess
0x180013e30  lea     rax, [rbp+57h+var_54]
0x180013e34  mov     rcx, r14; pSecurityDescriptor
0x180013e37  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180013e3c  lea     rax, [rbp+57h+PrivilegeSet]
0x180013e40  mov     [rsp+0B0h+lpnLengthNeeded], rax; PrivilegeSet
0x180013e45  call    cs:__imp_AccessCheck
0x180013e4b  test    eax, eax
0x180013e4d  jnz     short loc_180013E6B
0x180013e4f  call    cs:__imp_GetLastError
0x180013e55  mov     ebx, eax
0x180013e57  test    eax, eax
0x180013e59  jz      short loc_180013E68
0x180013e5b  jle     short loc_180013E6B
0x180013e5d  movzx   ebx, ax
0x180013e60  or      ebx, 80070000h
0x180013e66  jmp     short loc_180013E6B
0x180013e68  mov     ebx, r13d
0x180013e6b  mov     rcx, r14; Block
0x180013e6e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180013e73  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180013e77  test    rcx, rcx
0x180013e7a  jz      short loc_180013E82
0x180013e7c  call    cs:__imp_CloseHandle
0x180013e82  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x180013e86  test    rcx, rcx
0x180013e89  jz      short loc_180013E91
0x180013e8b  call    cs:__imp_CloseHandle
0x180013e91  mov     eax, ebx
0x180013e93  mov     rcx, [rbp+57h+var_28]
0x180013e97  xor     rcx, rsp; StackCookie
0x180013e9a  call    __security_check_cookie
0x180013e9f  lea     r11, [rsp+0B0h+var_20]
0x180013ea7  mov     rbx, [r11+40h]
0x180013eab  mov     rsi, [r11+48h]
0x180013eaf  mov     rsp, r11
0x180013eb2  pop     r15
0x180013eb4  pop     r14
0x180013eb6  pop     r13
0x180013eb8  pop     rdi
0x180013eb9  pop     rbp
0x180013eba  retn
```
