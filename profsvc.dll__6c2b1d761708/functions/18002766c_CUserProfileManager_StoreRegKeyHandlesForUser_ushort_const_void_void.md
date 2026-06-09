# CUserProfileManager::StoreRegKeyHandlesForUser(ushort const *,void *,void *)

- ea: `0x18002766c`
- end: `0x1800277f4`
- name: `?StoreRegKeyHandlesForUser@CUserProfileManager@@QEAAJPEBGPEAX1@Z`
- size: `392`
- prototype: `int(CUserProfileManager *__hidden this, const unsigned __int16 *, void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180030744`

## callees

- `0x18002766c`
- `0x18002793c`
- `0x18002df48`
- `0x18003bc70`
- `0x18003c870`
- `0x18004b418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027742`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027742`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800277bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800277bb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180027713`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180027713`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800276de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800276de`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800276aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800276aa`

## string_xrefs

- `0x1800276be`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x180027727`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserProfileManager::StoreRegKeyHandlesForUser(
        CUserProfileManager *this,
        const unsigned __int16 *a2,
        void *a3,
        void *a4)
{
  PSRWLOCK v6; // rdi
  const char *v7; // r9
  unsigned int LastError; // ebx
  const char *v9; // r9
  char *Ptr; // rdx
  __int64 v11; // rdx
  PSID Sid[2]; // [rsp+20h] [rbp-39h] BYREF
  _OWORD pDestinationSid[4]; // [rsp+30h] [rbp-29h] BYREF
  __int128 v15; // [rsp+70h] [rbp+17h]
  void *v16; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v6 = g_pProfMgr;
  Sid[0] = 0;
  if ( ConvertStringSidToSidW(a2, Sid) )
  {
    memset_0(pDestinationSid, 0, 0x58u);
    *((_QWORD *)&v15 + 1) = a3;
    v16 = a4;
    if ( CopySid(0x44u, pDestinationSid, Sid[0]) )
    {
      AcquireSRWLockExclusive(v6);
      Sid[1] = v6;
      Ptr = (char *)v6[2].Ptr;
      if ( Ptr != v6[4].Ptr
        || (int)CTSimpleArray<CUserProfileManager::UserToRegKeyHandleMapping,4294967294,CTPolicyCoTaskMem<CUserProfileManager::UserToRegKeyHandleMapping>,CSimpleArrayStandardCompareHelper<CUserProfileManager::UserToRegKeyHandleMapping>,CSimpleArrayStandardMergeHelper<CUserProfileManager::UserToRegKeyHandleMapping>>::_EnsureCapacity(
                  &v6[1],
                  Ptr + 1) >= 0 )
      {
        v11 = (__int64)v6[1].Ptr + 88 * (__int64)++v6[2].Ptr - 88;
        if ( v11 )
        {
          *(_OWORD *)v11 = pDestinationSid[0];
          *(_OWORD *)(v11 + 16) = pDestinationSid[1];
          *(_OWORD *)(v11 + 32) = pDestinationSid[2];
          *(_OWORD *)(v11 + 48) = pDestinationSid[3];
          *(_OWORD *)(v11 + 64) = v15;
          *(_QWORD *)(v11 + 80) = v16;
        }
      }
      if ( v6 )
        ReleaseSRWLockExclusive(v6);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xAE,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
                    v9);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(Sid);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA9,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
                  v7);
    if ( Sid[0] )
      LocalFree(Sid[0]);
  }
  return LastError;
}

```

## disassembly

```asm
0x18002766c  mov     [rsp-8+arg_0], rbx
0x180027671  push    rbp
0x180027672  push    rsi
0x180027673  push    rdi
0x180027674  lea     rbp, [rsp-47h]
0x180027679  sub     rsp, 0A0h
0x180027680  mov     rax, cs:__security_cookie
0x180027687  xor     rax, rsp
0x18002768a  mov     [rbp+57h+var_20], rax
0x18002768e  mov     rsi, r9
0x180027691  mov     rbx, r8
0x180027694  mov     rcx, rdx; StringSid
0x180027697  mov     rdi, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x18002769e  mov     [rbp+57h+Sid], 0
0x1800276a6  lea     rdx, [rbp+57h+Sid]; Sid
0x1800276aa  call    cs:__imp_ConvertStringSidToSidW
0x1800276b1  nop     dword ptr [rax+rax+00h]
0x1800276b6  test    eax, eax
0x1800276b8  jnz     short loc_1800276EF
0x1800276ba  mov     rcx, [rbp+5Fh]; this
0x1800276be  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800276c5  mov     edx, 0A9h; void *
0x1800276ca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800276cf  mov     ebx, eax
0x1800276d1  mov     rcx, [rbp+57h+Sid]; hMem
0x1800276d5  test    rcx, rcx
0x1800276d8  jz      loc_1800277D2
0x1800276de  call    cs:__imp_LocalFree
0x1800276e5  nop     dword ptr [rax+rax+00h]
0x1800276ea  jmp     loc_1800277D2
0x1800276ef  xor     edx, edx; Val
0x1800276f1  lea     r8d, [rdx+58h]; Size
0x1800276f5  lea     rcx, [rbp+57h+pDestinationSid]; void *
0x1800276f9  call    memset_0
0x1800276fe  mov     [rbp+57h+var_38], rbx
0x180027702  mov     [rbp+57h+var_30], rsi
0x180027706  mov     r8, [rbp+57h+Sid]; pSourceSid
0x18002770a  lea     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x18002770e  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180027713  call    cs:__imp_CopySid
0x18002771a  nop     dword ptr [rax+rax+00h]
0x18002771f  test    eax, eax
0x180027721  jnz     short loc_18002773F
0x180027723  mov     rcx, [rbp+5Fh]; this
0x180027727  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002772e  mov     edx, 0AEh; void *
0x180027733  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027738  mov     ebx, eax
0x18002773a  jmp     loc_1800277C9
0x18002773f  mov     rcx, rdi; SRWLock
0x180027742  call    cs:__imp_AcquireSRWLockExclusive
0x180027749  nop     dword ptr [rax+rax+00h]
0x18002774e  mov     [rbp+57h+var_88], rdi
0x180027752  mov     rdx, [rdi+10h]
0x180027756  cmp     rdx, [rdi+20h]
0x18002775a  jnz     short loc_18002776C
0x18002775c  inc     rdx
0x18002775f  lea     rcx, [rdi+8]
0x180027763  call    ?_EnsureCapacity@?$CTSimpleArray@UUserToRegKeyHandleMapping@CUserProfileManager@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UUserToRegKeyHandleMapping@CUserProfileManager@@@@V?$CSimpleArrayStandardCompareHelper@UUserToRegKeyHandleMapping@CUserProfileManager@@@@V?$CSimpleArrayStandardMergeHelper@UUserToRegKeyHandleMapping@CUserProfileManager@@@@@@QEAAJ_K0@Z; CTSimpleArray<CUserProfileManager::UserToRegKeyHandleMapping,4294967294,CTPolicyCoTaskMem<CUserProfileManager::UserToRegKeyHandleMapping>,CSimpleArrayStandardCompareHelper<CUserProfileManager::UserToRegKeyHandleMapping>,CSimpleArrayStandardMergeHelper<CUserProfileManager::UserToRegKeyHandleMapping>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180027768  test    eax, eax
0x18002776a  js      short loc_1800277B3
0x18002776c  inc     qword ptr [rdi+10h]
0x180027770  imul    rcx, [rdi+10h], 58h ; 'X'
0x180027775  mov     rdx, [rdi+8]
0x180027779  add     rdx, 0FFFFFFFFFFFFFFA8h
0x18002777d  add     rdx, rcx
0x180027780  jz      short loc_1800277B3
0x180027782  movaps  xmm0, [rbp+57h+pDestinationSid]
0x180027786  movups  xmmword ptr [rdx], xmm0
0x180027789  movaps  xmm1, [rbp+57h+var_70]
0x18002778d  movups  xmmword ptr [rdx+10h], xmm1
0x180027791  movaps  xmm0, [rbp+57h+var_60]
0x180027795  movups  xmmword ptr [rdx+20h], xmm0
0x180027799  movaps  xmm1, [rbp+57h+var_50]
0x18002779d  movups  xmmword ptr [rdx+30h], xmm1
0x1800277a1  movaps  xmm0, xmmword ptr [rbp+17h]
0x1800277a5  movups  xmmword ptr [rdx+40h], xmm0
0x1800277a9  movsd   xmm1, [rbp+57h+var_30]
0x1800277ae  movsd   qword ptr [rdx+50h], xmm1
0x1800277b3  test    rdi, rdi
0x1800277b6  jz      short loc_1800277C7
0x1800277b8  mov     rcx, rdi; SRWLock
0x1800277bb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800277c2  nop     dword ptr [rax+rax+00h]
0x1800277c7  xor     ebx, ebx
0x1800277c9  lea     rcx, [rbp+57h+Sid]
0x1800277cd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800277d2  mov     eax, ebx
0x1800277d4  mov     rcx, [rbp+57h+var_20]
0x1800277d8  xor     rcx, rsp; StackCookie
0x1800277db  call    __security_check_cookie
0x1800277e0  mov     rbx, [rsp+0B0h+arg_0]
0x1800277e8  add     rsp, 0A0h
0x1800277ef  pop     rdi
0x1800277f0  pop     rsi
0x1800277f1  pop     rbp
0x1800277f2  retn
```
