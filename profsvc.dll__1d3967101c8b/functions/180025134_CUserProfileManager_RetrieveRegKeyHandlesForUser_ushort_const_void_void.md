# CUserProfileManager::RetrieveRegKeyHandlesForUser(ushort const *,void * *,void * *)

- ea: `0x180025134`
- end: `0x18002524c`
- name: `?RetrieveRegKeyHandlesForUser@CUserProfileManager@@QEAAJPEBGPEAPEAX1@Z`
- size: `280`
- prototype: `int(CUserProfileManager *__hidden this, const unsigned __int16 *, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x180025134`
- `0x180025254`
- `0x18002db38`
- `0x1800510f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800251ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800251ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002522d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002522d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800251cd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800251cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002519d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002519d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180025171`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180025171`

## string_xrefs

- `0x180025180`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileManager::RetrieveRegKeyHandlesForUser(
        CUserProfileManager *this,
        const unsigned __int16 *a2,
        void **a3,
        void **a4)
{
  PSRWLOCK v4; // rbx
  const char *v7; // r9
  unsigned int LastError; // ebx
  unsigned int i; // esi
  __int64 v11; // r14
  unsigned __int64 Ptr; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  PSID Sid; // [rsp+60h] [rbp+8h] BYREF

  v4 = g_pProfMgr;
  *a3 = 0;
  *a4 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    AcquireSRWLockExclusive(v4);
    for ( i = 0; (PVOID)i < v4[2].Ptr; ++i )
    {
      v11 = 88LL * i;
      if ( EqualSid(Sid, (char *)v4[1].Ptr + v11) )
      {
        *a3 = *(void **)((char *)v4[1].Ptr + v11 + 72);
        *a4 = *(void **)((char *)v4[1].Ptr + v11 + 80);
        Ptr = (unsigned __int64)v4[2].Ptr;
        if ( i < Ptr )
        {
          if ( i != Ptr - 1 )
            memmove_0((char *)v4[1].Ptr + v11, (char *)v4[1].Ptr + v11 + 88, 88 * (Ptr - i) - 88);
          --v4[2].Ptr;
        }
        break;
      }
    }
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xC2,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
                  v7);
    if ( Sid )
      LocalFree(Sid);
    return LastError;
  }
}

```

## disassembly

```asm
0x180025134  mov     [rsp+Sid], rcx
0x180025139  push    rbx
0x18002513a  push    rbp
0x18002513b  push    rsi
0x18002513c  push    rdi
0x18002513d  push    r14
0x18002513f  push    r15
0x180025141  sub     rsp, 28h
0x180025145  mov     rbx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x18002514c  mov     rcx, rdx; StringSid
0x18002514f  mov     qword ptr [r8], 0
0x180025156  lea     rdx, [rsp+58h+Sid]; Sid
0x18002515b  mov     r15, r9
0x18002515e  mov     qword ptr [r9], 0
0x180025165  mov     rbp, r8
0x180025168  mov     [rsp+58h+Sid], 0
0x180025171  call    cs:__imp_ConvertStringSidToSidW
0x180025177  test    eax, eax
0x180025179  jnz     short loc_1800251AA
0x18002517b  mov     rcx, [rsp+58h]; this
0x180025180  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180025187  mov     edx, 0C2h; void *
0x18002518c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025191  mov     rcx, [rsp+58h+Sid]; hMem
0x180025196  mov     ebx, eax
0x180025198  test    rcx, rcx
0x18002519b  jz      short loc_1800251A3
0x18002519d  call    cs:__imp_LocalFree
0x1800251a3  mov     eax, ebx
0x1800251a5  jmp     loc_18002523F
0x1800251aa  mov     rcx, rbx; SRWLock
0x1800251ad  call    cs:__imp_AcquireSRWLockExclusive
0x1800251b3  xor     esi, esi
0x1800251b5  mov     edi, esi
0x1800251b7  cmp     rdi, [rbx+10h]
0x1800251bb  jnb     short loc_180025225
0x1800251bd  mov     rdx, [rbx+8]
0x1800251c1  mov     rcx, [rsp+58h+Sid]; pSid1
0x1800251c6  imul    r14, rdi, 58h ; 'X'
0x1800251ca  add     rdx, r14; pSid2
0x1800251cd  call    cs:__imp_EqualSid
0x1800251d3  test    eax, eax
0x1800251d5  jnz     short loc_1800251DB
0x1800251d7  inc     esi
0x1800251d9  jmp     short loc_1800251B5
0x1800251db  mov     rax, [rbx+8]
0x1800251df  mov     rcx, [r14+rax+48h]
0x1800251e4  mov     [rbp+0], rcx
0x1800251e8  mov     rax, [rbx+8]
0x1800251ec  mov     rcx, [r14+rax+50h]
0x1800251f1  mov     [r15], rcx
0x1800251f4  mov     rdx, [rbx+10h]
0x1800251f8  cmp     rdi, rdx
0x1800251fb  jnb     short loc_180025225
0x1800251fd  lea     rax, [rdx-1]
0x180025201  cmp     rdi, rax
0x180025204  jz      short loc_180025221
0x180025206  mov     rcx, [rbx+8]
0x18002520a  sub     rdx, rdi
0x18002520d  imul    r8, rdx, 58h ; 'X'
0x180025211  add     rcx, r14; void *
0x180025214  sub     r8, 58h ; 'X'; Size
0x180025218  lea     rdx, [rcx+58h]; Src
0x18002521c  call    memmove_0
0x180025221  dec     qword ptr [rbx+10h]
0x180025225  test    rbx, rbx
0x180025228  jz      short loc_180025233
0x18002522a  mov     rcx, rbx; SRWLock
0x18002522d  call    cs:__imp_ReleaseSRWLockExclusive
0x180025233  lea     rcx, [rsp+58h+Sid]
0x180025238  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002523d  xor     eax, eax
0x18002523f  add     rsp, 28h
0x180025243  pop     r15
0x180025245  pop     r14
0x180025247  pop     rdi
0x180025248  pop     rsi
0x180025249  pop     rbp
0x18002524a  pop     rbx
0x18002524b  retn
```
