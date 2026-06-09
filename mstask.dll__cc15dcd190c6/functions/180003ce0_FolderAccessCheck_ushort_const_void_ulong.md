# FolderAccessCheck(ushort const *,void *,ulong)

- ea: `0x180003ce0`
- end: `0x180003ea0`
- name: `?FolderAccessCheck@@YAJPEBGPEAXK@Z`
- size: `448`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, HANDLE ClientToken, DWORD DesiredAccess)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003830`

## callees

- `0x180003ce0`
- `0x180009ef8`
- `0x180009f38`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180003d3c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180003d9c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180003d3c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180003d9c`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003e20`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180003e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e5e`

## pseudocode

```c
signed int __fastcall FolderAccessCheck(LPCWSTR lpFileName, HANDLE ClientToken, DWORD DesiredAccess)
{
  signed int result; // eax
  unsigned int v7; // esi
  void *v8; // rbx
  signed int LastError; // eax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-68h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-64h] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-60h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp-5Ch] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-58h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-48h] BYREF

  if ( !DesiredAccess || !lpFileName )
    return -2147024891;
  nLengthNeeded = 0;
  if ( GetFileSecurityW(lpFileName, 7u, 0, 0, &nLengthNeeded) || (result = GetLastError(), result == 122) )
  {
    v7 = -2147024891;
    if ( nLengthNeeded )
    {
      v8 = operator new(nLengthNeeded + 1);
      if ( v8 )
      {
        if ( GetFileSecurityW(lpFileName, 7u, v8, nLengthNeeded, &nLengthNeeded) )
        {
          GenericMapping.GenericRead = 1179785;
          GenericMapping.GenericWrite = 1179926;
          GenericMapping.GenericExecute = 1179808;
          GenericMapping.GenericAll = 2032127;
          PrivilegeSetLength = 20;
          memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
          AccessStatus = 0;
          GrantedAccess = 0;
          if ( AccessCheck(
                 v8,
                 ClientToken,
                 DesiredAccess,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus)
            && AccessStatus
            && (GrantedAccess & DesiredAccess) == DesiredAccess )
          {
            v7 = 0;
          }
        }
        else
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
        }
        operator delete(v8);
      }
    }
    return v7;
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180003ce0  push    rbp
0x180003ce2  push    rsi
0x180003ce3  push    rdi
0x180003ce4  push    r14
0x180003ce6  sub     rsp, 88h
0x180003ced  mov     rax, cs:__security_cookie
0x180003cf4  xor     rax, rsp
0x180003cf7  mov     [rsp+0A8h+var_30], rax
0x180003cfc  mov     ebp, r8d
0x180003cff  mov     r14, rdx
0x180003d02  mov     rdi, rcx
0x180003d05  test    r8d, r8d
0x180003d08  jz      loc_180003E99
0x180003d0e  test    rcx, rcx
0x180003d11  jz      loc_180003E99
0x180003d17  lea     rax, [rsp+0A8h+nLengthNeeded]
0x180003d1c  mov     [rsp+0A8h+var_28], r15
0x180003d24  xor     r15d, r15d
0x180003d27  mov     [rsp+0A8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180003d2c  xor     r9d, r9d; nLength
0x180003d2f  mov     [rsp+0A8h+nLengthNeeded], r15d
0x180003d34  xor     r8d, r8d; pSecurityDescriptor
0x180003d37  mov     edx, 7; RequestedInformation
0x180003d3c  call    cs:__imp_GetFileSecurityW
0x180003d42  test    eax, eax
0x180003d44  jnz     short loc_180003D55
0x180003d46  call    cs:__imp_GetLastError
0x180003d4c  cmp     eax, 7Ah ; 'z'
0x180003d4f  jnz     loc_180003E75
0x180003d55  mov     eax, [rsp+0A8h+nLengthNeeded]
0x180003d59  mov     esi, 80070005h
0x180003d5e  test    eax, eax
0x180003d60  jz      loc_180003E3A
0x180003d66  lea     ecx, [rax+1]; Size
0x180003d69  mov     [rsp+0A8h+arg_18], rbx
0x180003d71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003d76  mov     rbx, rax
0x180003d79  test    rax, rax
0x180003d7c  jz      loc_180003E32
0x180003d82  mov     r9d, [rsp+0A8h+nLengthNeeded]; nLength
0x180003d87  lea     rax, [rsp+0A8h+nLengthNeeded]
0x180003d8c  mov     r8, rbx; pSecurityDescriptor
0x180003d8f  mov     [rsp+0A8h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180003d94  mov     edx, 7; RequestedInformation
0x180003d99  mov     rcx, rdi; lpFileName
0x180003d9c  call    cs:__imp_GetFileSecurityW
0x180003da2  test    eax, eax
0x180003da4  jz      loc_180003E5E
0x180003daa  xor     eax, eax
0x180003dac  mov     [rsp+0A8h+GenericMapping.GenericRead], 120089h
0x180003db4  mov     [rsp+0A8h+PrivilegeSet.Privilege.Attributes], eax
0x180003db8  lea     r9, [rsp+0A8h+GenericMapping]; GenericMapping
0x180003dbd  lea     rax, [rsp+0A8h+var_64]
0x180003dc2  mov     [rsp+0A8h+GenericMapping.GenericWrite], 120116h
0x180003dca  mov     [rsp+0A8h+AccessStatus], rax; AccessStatus
0x180003dcf  xorps   xmm0, xmm0
0x180003dd2  lea     rax, [rsp+0A8h+var_60]
0x180003dd7  mov     [rsp+0A8h+GenericMapping.GenericExecute], 1200A0h
0x180003ddf  mov     [rsp+0A8h+GrantedAccess], rax; GrantedAccess
0x180003de4  mov     r8d, ebp; DesiredAccess
0x180003de7  lea     rax, [rsp+0A8h+var_5C]
0x180003dec  mov     [rsp+0A8h+GenericMapping.GenericAll], 1F01FFh
0x180003df4  mov     [rsp+0A8h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180003df9  mov     rdx, r14; ClientToken
0x180003dfc  lea     rax, [rsp+0A8h+PrivilegeSet]
0x180003e01  mov     [rsp+0A8h+var_5C], 14h
0x180003e09  mov     rcx, rbx; pSecurityDescriptor
0x180003e0c  mov     [rsp+0A8h+lpnLengthNeeded], rax; PrivilegeSet
0x180003e11  movups  xmmword ptr [rsp+0A8h+PrivilegeSet.PrivilegeCount], xmm0
0x180003e16  mov     [rsp+0A8h+var_64], r15d
0x180003e1b  mov     [rsp+0A8h+var_60], r15d
0x180003e20  call    cs:__imp_AccessCheck
0x180003e26  test    eax, eax
0x180003e28  jnz     short loc_180003E83
0x180003e2a  mov     rcx, rbx; Block
0x180003e2d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003e32  mov     rbx, [rsp+0A8h+arg_18]
0x180003e3a  mov     eax, esi
0x180003e3c  mov     r15, [rsp+0A8h+var_28]
0x180003e44  mov     rcx, [rsp+0A8h+var_30]
0x180003e49  xor     rcx, rsp; StackCookie
0x180003e4c  call    __security_check_cookie
0x180003e51  add     rsp, 88h
0x180003e58  pop     r14
0x180003e5a  pop     rdi
0x180003e5b  pop     rsi
0x180003e5c  pop     rbp
0x180003e5d  retn
0x180003e5e  call    cs:__imp_GetLastError
0x180003e64  mov     esi, eax
0x180003e66  test    eax, eax
0x180003e68  jle     short loc_180003E2A
0x180003e6a  movzx   esi, ax
0x180003e6d  or      esi, 80070000h
0x180003e73  jmp     short loc_180003E2A
0x180003e75  test    eax, eax
0x180003e77  jle     short loc_180003E3C
0x180003e79  movzx   eax, ax
0x180003e7c  or      eax, 80070000h
0x180003e81  jmp     short loc_180003E3C
0x180003e83  cmp     [rsp+0A8h+var_64], r15d
0x180003e88  jz      short loc_180003E2A
0x180003e8a  mov     eax, ebp
0x180003e8c  and     eax, [rsp+0A8h+var_60]
0x180003e90  cmp     eax, ebp
0x180003e92  jnz     short loc_180003E2A
0x180003e94  mov     esi, r15d
0x180003e97  jmp     short loc_180003E2A
0x180003e99  mov     eax, 80070005h
0x180003e9e  jmp     short loc_180003E44
```
