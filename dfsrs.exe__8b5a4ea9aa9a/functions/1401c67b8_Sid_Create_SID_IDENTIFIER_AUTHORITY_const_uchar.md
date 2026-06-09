# Sid::Create(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x1401c67b8`
- end: `0x1401c6912`
- name: `?Create@Sid@@QEAAPEAVFrsStatus@@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `346`
- prototype: `struct FrsStatus *(Sid *__hidden this, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, UCHAR nSubAuthorityCount, ...)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b2fc`
- `0x1400c06b8`

## callees

- `0x1400036a0`
- `0x1401b9494`
- `0x1401c67b8`
- `0x1401c8070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c683f`
- `KERNEL32!GetLastError` at `0x1401c683f`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6831`
- `KERNEL32!GetCurrentThreadId` at `0x1401c68ac`
- `KERNEL32!GetCurrentThreadId` at `0x1401c6831`
- `KERNEL32!GetCurrentThreadId` at `0x1401c68ac`
- `ADVAPI32!GetSidSubAuthority` at `0x1401c6882`
- `ADVAPI32!GetSidSubAuthority` at `0x1401c6882`
- `ADVAPI32!InitializeSid` at `0x1401c6821`
- `ADVAPI32!InitializeSid` at `0x1401c6821`
- `ADVAPI32!GetSidLengthRequired` at `0x1401c67fd`
- `ADVAPI32!GetSidLengthRequired` at `0x1401c67fd`

## string_xrefs

- `0x1401c68e3`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c68ce`: `Sid::Create`

## pseudocode

```c
struct FrsStatus *Sid::Create(Sid *this, PSID_IDENTIFIER_AUTHORITY pIdentifierAuthority, UCHAR nSubAuthorityCount, ...)
{
  unsigned __int64 v3; // rbp
  DWORD v4; // edi
  DWORD CurrentThreadId; // ebx
  __int64 LastError; // rdx
  BYTE *p_nSubAuthorityCounta; // rsi
  DWORD v11; // ebx
  PDWORD SidSubAuthority; // rax
  DWORD v13; // eax
  __int64 v14; // [rsp+70h] [rbp+0h] BYREF
  BYTE nSubAuthorityCounta; // [rsp+140h] [rbp+D0h] BYREF

  nSubAuthorityCounta = nSubAuthorityCount;
  v3 = (unsigned __int64)&v14 & 0xFFFFFFFFFFFFFFE0uLL;
  v4 = 0;
  if ( nSubAuthorityCount && GetSidLengthRequired(nSubAuthorityCount) <= 0x44 )
  {
    if ( InitializeSid((PSID)(v3 + 32), pIdentifierAuthority, nSubAuthorityCounta) )
    {
      if ( nSubAuthorityCounta )
      {
        p_nSubAuthorityCounta = &nSubAuthorityCounta;
        do
        {
          p_nSubAuthorityCounta += 8;
          v11 = *(_DWORD *)p_nSubAuthorityCounta;
          SidSubAuthority = GetSidSubAuthority((PSID)(v3 + 32), v4++);
          *SidSubAuthority = v11;
        }
        while ( v4 < nSubAuthorityCounta );
      }
      return Sid::Set(this, (struct _SID *)(v3 + 32));
    }
    else
    {
      CurrentThreadId = GetCurrentThreadId();
      LastError = GetLastError();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                   LastError,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                   "Sid::Create",
                                   140,
                                   CurrentThreadId,
                                   0);
    }
  }
  else
  {
    v13 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 87,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Sid::Create",
                                 134,
                                 v13,
                                 0);
  }
}

```

## disassembly

```asm
0x1401c67b8  mov     [rsp-8+nSubAuthorityCount], r8b
0x1401c67bd  mov     [rsp-8+arg_18], r9
0x1401c67c2  push    rbp
0x1401c67c3  push    rbx
0x1401c67c4  push    rsi
0x1401c67c5  push    rdi
0x1401c67c6  push    r14
0x1401c67c8  sub     rsp, 100h
0x1401c67cf  lea     rbp, [rsp+70h]
0x1401c67d4  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1401c67d8  mov     rax, cs:__security_cookie
0x1401c67df  xor     rax, rsp
0x1401c67e2  mov     [rbp+0B0h+var_30], rax
0x1401c67e9  xor     edi, edi
0x1401c67eb  mov     rbx, rdx
0x1401c67ee  mov     r14, rcx
0x1401c67f1  test    r8b, r8b
0x1401c67f4  jz      loc_1401C68AC
0x1401c67fa  mov     cl, r8b; nSubAuthorityCount
0x1401c67fd  call    cs:__imp_GetSidLengthRequired
0x1401c6804  nop     dword ptr [rax+rax+00h]
0x1401c6809  cmp     eax, 44h ; 'D'
0x1401c680c  ja      loc_1401C68AC
0x1401c6812  mov     r8b, [rsp+120h+nSubAuthorityCount]; nSubAuthorityCount
0x1401c681a  lea     rcx, [rbp+0B0h+Sid]; Sid
0x1401c681e  mov     rdx, rbx; pIdentifierAuthority
0x1401c6821  call    cs:__imp_InitializeSid
0x1401c6828  nop     dword ptr [rax+rax+00h]
0x1401c682d  test    eax, eax
0x1401c682f  jnz     short loc_1401C6860
0x1401c6831  call    cs:__imp_GetCurrentThreadId
0x1401c6838  nop     dword ptr [rax+rax+00h]
0x1401c683d  mov     ebx, eax
0x1401c683f  call    cs:__imp_GetLastError
0x1401c6846  nop     dword ptr [rax+rax+00h]
0x1401c684b  mov     [rsp+120h+var_E0], rdi
0x1401c6850  mov     edx, eax
0x1401c6852  mov     [rsp+120h+var_E8], ebx
0x1401c6856  mov     [rsp+120h+var_F0], 8Ch
0x1401c685e  jmp     short loc_1401C68CE
0x1401c6860  lea     rsi, [rsp+120h+arg_18]
0x1401c6868  cmp     [rsp+120h+nSubAuthorityCount], dil
0x1401c6870  jbe     short loc_1401C689E
0x1401c6872  add     rsi, 0FFFFFFFFFFFFFFF8h
0x1401c6876  lea     rsi, [rsi+8]
0x1401c687a  mov     edx, edi; nSubAuthority
0x1401c687c  mov     ebx, [rsi]
0x1401c687e  lea     rcx, [rbp+0B0h+Sid]; pSid
0x1401c6882  call    cs:__imp_GetSidSubAuthority
0x1401c6889  nop     dword ptr [rax+rax+00h]
0x1401c688e  inc     edi
0x1401c6890  mov     [rax], ebx
0x1401c6892  movzx   eax, [rsp+120h+nSubAuthorityCount]
0x1401c689a  cmp     edi, eax
0x1401c689c  jb      short loc_1401C6876
0x1401c689e  lea     rdx, [rbp+0B0h+Sid]; struct _SID *
0x1401c68a2  mov     rcx, r14; this
0x1401c68a5  call    ?Set@Sid@@QEAAPEAVFrsStatus@@PEBU_SID@@@Z; Sid::Set(_SID const *)
0x1401c68aa  jmp     short loc_1401C68F4
0x1401c68ac  call    cs:__imp_GetCurrentThreadId
0x1401c68b3  nop     dword ptr [rax+rax+00h]
0x1401c68b8  mov     [rsp+120h+var_E0], rdi
0x1401c68bd  mov     edx, 57h ; 'W'
0x1401c68c2  mov     [rsp+120h+var_E8], eax
0x1401c68c6  mov     [rsp+120h+var_F0], 86h
0x1401c68ce  lea     rcx, aSidCreate; "Sid::Create"
0x1401c68d5  mov     r9d, 1
0x1401c68db  mov     [rsp+120h+var_F8], rcx
0x1401c68e0  xor     r8d, r8d
0x1401c68e3  lea     rcx, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c68ea  mov     [rsp+120h+var_100], rcx
0x1401c68ef  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c68f4  mov     rcx, [rbp+0B0h+var_30]
0x1401c68fb  xor     rcx, rsp; StackCookie
0x1401c68fe  call    __security_check_cookie
0x1401c6903  add     rsp, 100h
0x1401c690a  pop     r14
0x1401c690c  pop     rdi
0x1401c690d  pop     rsi
0x1401c690e  pop     rbx
0x1401c690f  pop     rbp
0x1401c6910  retn
```
