# CUserProfileManager::StoreRegKeyHandlesForUser(ushort const *,void *,void *)

- ea: `0x180024fc8`
- end: `0x18002512e`
- name: `?StoreRegKeyHandlesForUser@CUserProfileManager@@QEAAJPEBGPEAX1@Z`
- size: `358`
- prototype: `int(CUserProfileManager *__hidden this, const unsigned __int16 *, void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002bf94`

## callees

- `0x180024fc8`
- `0x180025254`
- `0x18002db38`
- `0x18003a730`
- `0x18003b310`
- `0x180048f54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025089`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025089`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800250fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800250fc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025063`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025063`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025034`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025034`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180025006`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180025006`

## string_xrefs

- `0x180025014`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x180025071`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

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
  SIZE_T v10; // r8
  PVOID Ptr; // rdx
  __int64 v12; // rdx
  PSID Sid[2]; // [rsp+20h] [rbp-39h] BYREF
  _OWORD pDestinationSid[4]; // [rsp+30h] [rbp-29h] BYREF
  __int128 v16; // [rsp+70h] [rbp+17h]
  void *v17; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v6 = g_pProfMgr;
  Sid[0] = 0;
  if ( ConvertStringSidToSidW(a2, Sid) )
  {
    memset_0(pDestinationSid, 0, 0x58u);
    *((_QWORD *)&v16 + 1) = a3;
    v17 = a4;
    if ( CopySid(0x44u, pDestinationSid, Sid[0]) )
    {
      AcquireSRWLockExclusive(v6);
      Sid[1] = v6;
      Ptr = v6[2].Ptr;
      if ( Ptr != v6[4].Ptr
        || (int)CTSimpleArray<CUserProfileManager::UserToRegKeyHandleMapping,4294967294,CTPolicyCoTaskMem<CUserProfileManager::UserToRegKeyHandleMapping>,CSimpleArrayStandardCompareHelper<CUserProfileManager::UserToRegKeyHandleMapping>,CSimpleArrayStandardMergeHelper<CUserProfileManager::UserToRegKeyHandleMapping>>::_EnsureCapacity(
                  &v6[1].Ptr,
                  (unsigned __int64)Ptr + 1,
                  v10) >= 0 )
      {
        v12 = (__int64)v6[1].Ptr + 88 * (__int64)++v6[2].Ptr - 88;
        if ( v12 )
        {
          *(_OWORD *)v12 = pDestinationSid[0];
          *(_OWORD *)(v12 + 16) = pDestinationSid[1];
          *(_OWORD *)(v12 + 32) = pDestinationSid[2];
          *(_OWORD *)(v12 + 48) = pDestinationSid[3];
          *(_OWORD *)(v12 + 64) = v16;
          *(_QWORD *)(v12 + 80) = v17;
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
0x180024fc8  mov     [rsp-8+arg_0], rbx
0x180024fcd  push    rbp
0x180024fce  push    rsi
0x180024fcf  push    rdi
0x180024fd0  lea     rbp, [rsp-47h]
0x180024fd5  sub     rsp, 0A0h
0x180024fdc  mov     rax, cs:__security_cookie
0x180024fe3  xor     rax, rsp
0x180024fe6  mov     [rbp+57h+var_20], rax
0x180024fea  mov     rsi, r9
0x180024fed  mov     rbx, r8
0x180024ff0  mov     rcx, rdx; StringSid
0x180024ff3  mov     rdi, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x180024ffa  mov     [rbp+57h+Sid], 0
0x180025002  lea     rdx, [rbp+57h+Sid]; Sid
0x180025006  call    cs:__imp_ConvertStringSidToSidW
0x18002500c  test    eax, eax
0x18002500e  jnz     short loc_18002503F
0x180025010  mov     rcx, [rbp+5Fh]; this
0x180025014  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002501b  mov     edx, 0A9h; void *
0x180025020  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025025  mov     ebx, eax
0x180025027  mov     rcx, [rbp+57h+Sid]; hMem
0x18002502b  test    rcx, rcx
0x18002502e  jz      loc_18002510D
0x180025034  call    cs:__imp_LocalFree
0x18002503a  jmp     loc_18002510D
0x18002503f  xor     edx, edx; Val
0x180025041  lea     r8d, [rdx+58h]; Size
0x180025045  lea     rcx, [rbp+57h+pDestinationSid]; void *
0x180025049  call    memset_0
0x18002504e  mov     [rbp+57h+var_38], rbx
0x180025052  mov     [rbp+57h+var_30], rsi
0x180025056  mov     r8, [rbp+57h+Sid]; pSourceSid
0x18002505a  lea     rdx, [rbp+57h+pDestinationSid]; pDestinationSid
0x18002505e  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180025063  call    cs:__imp_CopySid
0x180025069  test    eax, eax
0x18002506b  jnz     short loc_180025086
0x18002506d  mov     rcx, [rbp+5Fh]; this
0x180025071  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180025078  mov     edx, 0AEh; void *
0x18002507d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025082  mov     ebx, eax
0x180025084  jmp     short loc_180025104
0x180025086  mov     rcx, rdi; SRWLock
0x180025089  call    cs:__imp_AcquireSRWLockExclusive
0x18002508f  mov     [rbp+57h+var_88], rdi
0x180025093  mov     rdx, [rdi+10h]
0x180025097  cmp     rdx, [rdi+20h]
0x18002509b  jnz     short loc_1800250AD
0x18002509d  inc     rdx
0x1800250a0  lea     rcx, [rdi+8]
0x1800250a4  call    ?_EnsureCapacity@?$CTSimpleArray@UUserToRegKeyHandleMapping@CUserProfileManager@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UUserToRegKeyHandleMapping@CUserProfileManager@@@@V?$CSimpleArrayStandardCompareHelper@UUserToRegKeyHandleMapping@CUserProfileManager@@@@V?$CSimpleArrayStandardMergeHelper@UUserToRegKeyHandleMapping@CUserProfileManager@@@@@@QEAAJ_K0@Z; CTSimpleArray<CUserProfileManager::UserToRegKeyHandleMapping,4294967294,CTPolicyCoTaskMem<CUserProfileManager::UserToRegKeyHandleMapping>,CSimpleArrayStandardCompareHelper<CUserProfileManager::UserToRegKeyHandleMapping>,CSimpleArrayStandardMergeHelper<CUserProfileManager::UserToRegKeyHandleMapping>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800250a9  test    eax, eax
0x1800250ab  js      short loc_1800250F4
0x1800250ad  inc     qword ptr [rdi+10h]
0x1800250b1  imul    rcx, [rdi+10h], 58h ; 'X'
0x1800250b6  mov     rdx, [rdi+8]
0x1800250ba  add     rdx, 0FFFFFFFFFFFFFFA8h
0x1800250be  add     rdx, rcx
0x1800250c1  jz      short loc_1800250F4
0x1800250c3  movaps  xmm0, [rbp+57h+pDestinationSid]
0x1800250c7  movups  xmmword ptr [rdx], xmm0
0x1800250ca  movaps  xmm1, [rbp+57h+var_70]
0x1800250ce  movups  xmmword ptr [rdx+10h], xmm1
0x1800250d2  movaps  xmm0, [rbp+57h+var_60]
0x1800250d6  movups  xmmword ptr [rdx+20h], xmm0
0x1800250da  movaps  xmm1, [rbp+57h+var_50]
0x1800250de  movups  xmmword ptr [rdx+30h], xmm1
0x1800250e2  movaps  xmm0, xmmword ptr [rbp+17h]
0x1800250e6  movups  xmmword ptr [rdx+40h], xmm0
0x1800250ea  movsd   xmm1, [rbp+57h+var_30]
0x1800250ef  movsd   qword ptr [rdx+50h], xmm1
0x1800250f4  test    rdi, rdi
0x1800250f7  jz      short loc_180025102
0x1800250f9  mov     rcx, rdi; SRWLock
0x1800250fc  call    cs:__imp_ReleaseSRWLockExclusive
0x180025102  xor     ebx, ebx
0x180025104  lea     rcx, [rbp+57h+Sid]
0x180025108  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002510d  mov     eax, ebx
0x18002510f  mov     rcx, [rbp+57h+var_20]
0x180025113  xor     rcx, rsp; StackCookie
0x180025116  call    __security_check_cookie
0x18002511b  mov     rbx, [rsp+0B0h+arg_0]
0x180025123  add     rsp, 0A0h
0x18002512a  pop     rdi
0x18002512b  pop     rsi
0x18002512c  pop     rbp
0x18002512d  retn
```
