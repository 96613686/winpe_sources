# FolderAccessCheck(ushort const *,void *,ulong)

- ea: `0x1801a25c4`
- end: `0x1801a273f`
- name: `?FolderAccessCheck@@YAJPEBGPEAXK@Z`
- size: `379`
- prototype: `int(const unsigned __int16 *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801a2748`

## callees

- `0x180026980`
- `0x1800269f8`
- `0x1801a25c4`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2708`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1801a26ee`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1801a26ee`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1801a2607`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1801a2677`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1801a2607`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1801a2677`

## pseudocode

```c
int __fastcall FolderAccessCheck(const unsigned __int16 *a1, void *a2)
{
  int result; // eax
  unsigned int v4; // ebx
  void *v5; // rdi
  signed int LastError; // eax
  DWORD nLengthNeeded; // [rsp+40h] [rbp-9h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-5h] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-1h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp+3h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp+7h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp+17h] BYREF

  nLengthNeeded = 0;
  if ( GetFileSecurityW(&PathName, 7u, 0, 0, &nLengthNeeded) || (result = GetLastError(), result == 122) )
  {
    v4 = -2147024891;
    if ( nLengthNeeded )
    {
      v5 = operator new[](nLengthNeeded, (const struct std::nothrow_t *)&std::nothrow);
      if ( v5 )
      {
        if ( GetFileSecurityW(&PathName, 7u, v5, nLengthNeeded, &nLengthNeeded) )
        {
          GenericMapping.GenericRead = 1179785;
          AccessStatus = 0;
          GrantedAccess = 0;
          GenericMapping.GenericWrite = 1179926;
          GenericMapping.GenericExecute = 1179808;
          GenericMapping.GenericAll = 2032127;
          memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
          PrivilegeSetLength = 20;
          if ( AccessCheck(
                 v5,
                 a2,
                 2u,
                 &GenericMapping,
                 &PrivilegeSet,
                 &PrivilegeSetLength,
                 &GrantedAccess,
                 &AccessStatus)
            && AccessStatus
            && (GrantedAccess & 2) != 0 )
          {
            v4 = 0;
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
        PSGSI1::EnumPubsByAddr::release((PSGSI1::EnumPubsByAddr *)v5);
      }
    }
    return v4;
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
0x1801a25c4  push    rbp
0x1801a25c6  push    rbx
0x1801a25c7  push    rsi
0x1801a25c8  push    rdi
0x1801a25c9  lea     rbp, [rsp-3Fh]
0x1801a25ce  sub     rsp, 88h
0x1801a25d5  mov     rax, cs:__security_cookie
0x1801a25dc  xor     rax, rsp
0x1801a25df  mov     [rbp+57h+var_28], rax
0x1801a25e3  xor     r9d, r9d; nLength
0x1801a25e6  mov     [rbp+57h+nLengthNeeded], 0
0x1801a25ed  mov     rsi, rdx
0x1801a25f0  lea     rax, [rbp+57h+nLengthNeeded]
0x1801a25f4  xor     r8d, r8d; pSecurityDescriptor
0x1801a25f7  mov     [rsp+0A0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1801a25fc  lea     rcx, PathName; lpFileName
0x1801a2603  lea     edx, [r9+7]; RequestedInformation
0x1801a2607  call    cs:__imp_GetFileSecurityW
0x1801a260d  test    eax, eax
0x1801a260f  jnz     short loc_1801A2631
0x1801a2611  call    cs:__imp_GetLastError
0x1801a2617  cmp     eax, 7Ah ; 'z'
0x1801a261a  jz      short loc_1801A2631
0x1801a261c  test    eax, eax
0x1801a261e  jle     loc_1801A2727
0x1801a2624  movzx   eax, ax
0x1801a2627  or      eax, 80070000h
0x1801a262c  jmp     loc_1801A2727
0x1801a2631  mov     eax, [rbp+57h+nLengthNeeded]
0x1801a2634  mov     ebx, 80070005h
0x1801a2639  test    eax, eax
0x1801a263b  jz      loc_1801A2725
0x1801a2641  mov     ecx, eax; unsigned __int64
0x1801a2643  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801a264a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801a264f  mov     rdi, rax
0x1801a2652  test    rax, rax
0x1801a2655  jz      loc_1801A2725
0x1801a265b  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1801a265f  lea     rax, [rbp+57h+nLengthNeeded]
0x1801a2663  mov     r8, rdi; pSecurityDescriptor
0x1801a2666  mov     [rsp+0A0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1801a266b  mov     edx, 7; RequestedInformation
0x1801a2670  lea     rcx, PathName; lpFileName
0x1801a2677  call    cs:__imp_GetFileSecurityW
0x1801a267d  test    eax, eax
0x1801a267f  jz      loc_1801A2708
0x1801a2685  xor     eax, eax
0x1801a2687  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x1801a268e  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x1801a2691  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1801a2695  mov     [rbp+57h+var_5C], eax
0x1801a2698  xorps   xmm0, xmm0
0x1801a269b  mov     [rbp+57h+var_58], eax
0x1801a269e  mov     r8d, 2; DesiredAccess
0x1801a26a4  lea     rax, [rbp+57h+var_5C]
0x1801a26a8  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x1801a26af  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x1801a26b4  mov     rdx, rsi; ClientToken
0x1801a26b7  lea     rax, [rbp+57h+var_58]
0x1801a26bb  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x1801a26c2  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x1801a26c7  mov     rcx, rdi; pSecurityDescriptor
0x1801a26ca  lea     rax, [rbp+57h+var_54]
0x1801a26ce  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x1801a26d5  mov     [rsp+0A0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1801a26da  lea     rax, [rbp+57h+PrivilegeSet]
0x1801a26de  mov     [rsp+0A0h+lpnLengthNeeded], rax; PrivilegeSet
0x1801a26e3  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x1801a26e7  mov     [rbp+57h+var_54], 14h
0x1801a26ee  call    cs:__imp_AccessCheck
0x1801a26f4  test    eax, eax
0x1801a26f6  jz      short loc_1801A271D
0x1801a26f8  cmp     [rbp+57h+var_5C], 0
0x1801a26fc  jz      short loc_1801A271D
0x1801a26fe  test    byte ptr [rbp+57h+var_58], 2
0x1801a2702  jz      short loc_1801A271D
0x1801a2704  xor     ebx, ebx
0x1801a2706  jmp     short loc_1801A271D
0x1801a2708  call    cs:__imp_GetLastError
0x1801a270e  mov     ebx, eax
0x1801a2710  test    eax, eax
0x1801a2712  jle     short loc_1801A271D
0x1801a2714  movzx   ebx, ax
0x1801a2717  or      ebx, 80070000h
0x1801a271d  mov     rcx, rdi; this
0x1801a2720  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x1801a2725  mov     eax, ebx
0x1801a2727  mov     rcx, [rbp+57h+var_28]
0x1801a272b  xor     rcx, rsp; StackCookie
0x1801a272e  call    __security_check_cookie
0x1801a2733  add     rsp, 88h
0x1801a273a  pop     rdi
0x1801a273b  pop     rsi
0x1801a273c  pop     rbx
0x1801a273d  pop     rbp
0x1801a273e  retn
```
