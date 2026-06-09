# CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem(std::function<long (void)> const &&,ulong)

- ea: `0x18001d3a4`
- end: `0x18001d5ec`
- name: `?_SubmitAndWaitOnThreadpoolWorkItem@CCellularSettingsPublisher@@AEAAJ$$QEBV?$function@$$A6AJXZ@std@@K@Z`
- size: `584`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `44`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018030`
- `0x180018110`
- `0x180018210`
- `0x180018300`
- `0x180018430`
- `0x180018510`
- `0x1800185f0`
- `0x180018740`
- `0x1800188a0`
- `0x180018990`
- `0x180018a80`
- `0x180018b70`
- `0x180018c60`
- `0x180018d60`
- `0x180018e70`
- `0x180018f60`
- `0x180019050`
- `0x180019140`
- `0x180019230`
- `0x180019320`
- `0x180019410`
- `0x180019500`
- `0x180019640`
- `0x180019730`
- `0x180019820`
- `0x180019910`
- `0x180019a00`
- `0x180019af0`
- `0x180019bf0`
- `0x180019ce0`
- `0x180019dd0`
- `0x180019f60`
- `0x18001a060`
- `0x18001a160`
- `0x18001a260`
- `0x18001a360`
- `0x18001a450`
- `0x18001a580`
- `0x18001a710`
- `0x18001a880`
- `0x18001a970`
- `0x18001aa60`
- `0x18001ab50`
- `0x18001ac40`

## callees

- `0x1800069d8`
- `0x180009474`
- `0x180016754`
- `0x18001ae38`
- `0x18001d3a4`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001d467`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001d467`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001d455`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001d455`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001d435`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001d435`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d401`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d4e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d401`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d4e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d3c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d3c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem(__int64 a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v6; // r14
  DWORD v7; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int v10; // edi
  int v11; // r14d
  volatile signed __int32 *v12; // rsi
  volatile signed __int32 *v13; // rsi
  unsigned int v14; // r14d
  volatile signed __int32 *v15; // rsi
  int v16; // [rsp+20h] [rbp-48h]
  const char *v17; // [rsp+28h] [rbp-40h]
  __int64 v18; // [rsp+38h] [rbp-30h] BYREF
  volatile signed __int32 *v19; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v21; // [rsp+70h] [rbp+8h] BYREF
  __int64 v22; // [rsp+88h] [rbp+20h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 400);
  v22 = a1 + 400;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 400));
  if ( !*(_BYTE *)(a1 + 112) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccspublisher.cpp",
      (const char *)0x8007139FLL,
      v16);
    if ( v4 )
      LeaveCriticalSection(v4);
    return 2147947423LL;
  }
  v21 = a2;
  WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1___(
    a1 + 120,
    &v18,
    &v21);
  v6 = v18;
  v7 = WaitForSingleObjectEx(*(HANDLE *)(v18 + 72), 0xFFFFFFFF, 0);
  if ( v7 == 258 )
  {
    v10 = 1460;
  }
  else
  {
    if ( v7 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v8, v9);
    AcquireSRWLockShared((PSRWLOCK)(v6 + 80));
    v10 = *(_DWORD *)(v6 + 92);
    if ( v6 != -80 )
      ReleaseSRWLockShared((PSRWLOCK)(v6 + 80));
    if ( !v10 )
    {
      v11 = *(_DWORD *)(v6 + 88);
      if ( v11 >= 0 )
      {
        v13 = v19;
        if ( v19 )
        {
          if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
            if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          }
        }
        if ( v4 )
          LeaveCriticalSection(v4);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccspublisher.cpp",
          (const char *)(unsigned int)v11,
          v16);
        v12 = v19;
        if ( v19 )
        {
          if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
        if ( v4 )
          LeaveCriticalSection(v4);
        return (unsigned int)v11;
      }
    }
  }
  v14 = wil::details::in1diag3::Return_Win32Msg(
          retaddr,
          (void *)0xB9,
          (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccspublisher.cpp",
          (const char *)v10,
          (unsigned int)"[Publisher]Failed",
          v17);
  v15 = v19;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return v14;
}

```

## disassembly

```asm
0x18001d3a4  mov     [rsp+arg_8], rbx
0x18001d3a9  push    rsi
0x18001d3aa  push    rdi
0x18001d3ab  push    r14
0x18001d3ad  sub     rsp, 50h
0x18001d3b1  mov     rsi, rdx
0x18001d3b4  mov     rdi, rcx
0x18001d3b7  lea     rbx, [rcx+190h]
0x18001d3be  mov     [rsp+68h+arg_18], rbx
0x18001d3c6  mov     rcx, rbx; lpCriticalSection
0x18001d3c9  call    cs:__imp_EnterCriticalSection
0x18001d3cf  mov     [rsp+68h+var_38], rbx
0x18001d3d4  cmp     byte ptr [rdi+70h], 0
0x18001d3d8  jnz     short loc_18001D40E
0x18001d3da  mov     rcx, [rsp+68h]; this
0x18001d3df  mov     edi, 8007139Fh
0x18001d3e4  mov     r9d, edi; char *
0x18001d3e7  lea     r8, aOnecoreuapNetM_0; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18001d3ee  mov     edx, 0ACh; void *
0x18001d3f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3f8  nop
0x18001d3f9  test    rbx, rbx
0x18001d3fc  jz      short loc_18001D407
0x18001d3fe  mov     rcx, rbx; lpCriticalSection
0x18001d401  call    cs:__imp_LeaveCriticalSection
0x18001d407  mov     eax, edi
0x18001d409  jmp     loc_18001D5CD
0x18001d40e  mov     [rsp+68h+arg_0], rsi
0x18001d413  lea     rcx, [rdi+78h]
0x18001d417  lea     r8, [rsp+68h+arg_0]
0x18001d41c  lea     rdx, [rsp+68h+var_30]
0x18001d421  call    WcmCommon__ThreadPoolWorkQueue__SubmitWorkWithResults_long__CCellularSettingsPublisher___SubmitAndWaitOnThreadpoolWorkItem____13____lambda_1___
0x18001d426  mov     r14, [rsp+68h+var_30]
0x18001d42b  xor     r8d, r8d; bAlertable
0x18001d42e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001d431  mov     rcx, [r14+48h]; hHandle
0x18001d435  call    cs:__imp_WaitForSingleObjectEx
0x18001d43b  cmp     eax, 102h
0x18001d440  jz      loc_18001D534
0x18001d446  test    eax, eax
0x18001d448  jnz     loc_18001D5DB
0x18001d44e  lea     rsi, [r14+50h]
0x18001d452  mov     rcx, rsi; SRWLock
0x18001d455  call    cs:__imp_AcquireSRWLockShared
0x18001d45b  mov     edi, [r14+5Ch]
0x18001d45f  test    rsi, rsi
0x18001d462  jz      short loc_18001D46D
0x18001d464  mov     rcx, rsi; SRWLock
0x18001d467  call    cs:__imp_ReleaseSRWLockShared
0x18001d46d  test    edi, edi
0x18001d46f  jnz     loc_18001D539
0x18001d475  mov     r14d, [r14+58h]
0x18001d479  test    r14d, r14d
0x18001d47c  jns     short loc_18001D4EE
0x18001d47e  mov     rcx, [rsp+68h]; this
0x18001d483  mov     r9d, r14d; char *
0x18001d486  lea     r8, aOnecoreuapNetM_0; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18001d48d  mov     edx, 0BAh; void *
0x18001d492  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d497  mov     rsi, [rsp+68h+var_28]
0x18001d49c  test    rsi, rsi
0x18001d49f  jz      short loc_18001D4D8
0x18001d4a1  or      edi, 0FFFFFFFFh
0x18001d4a4  mov     eax, edi
0x18001d4a6  lock xadd [rsi+8], eax
0x18001d4ab  add     eax, edi
0x18001d4ad  jnz     short loc_18001D4D8
0x18001d4af  mov     rax, [rsi]
0x18001d4b2  mov     rcx, rsi
0x18001d4b5  mov     rax, [rax]
0x18001d4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4bd  mov     eax, edi
0x18001d4bf  lock xadd [rsi+0Ch], eax
0x18001d4c4  add     eax, edi
0x18001d4c6  jnz     short loc_18001D4D8
0x18001d4c8  mov     rax, [rsi]
0x18001d4cb  mov     rcx, rsi
0x18001d4ce  mov     rax, [rax+8]
0x18001d4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4d7  nop
0x18001d4d8  test    rbx, rbx
0x18001d4db  jz      short loc_18001D4E6
0x18001d4dd  mov     rcx, rbx; lpCriticalSection
0x18001d4e0  call    cs:__imp_LeaveCriticalSection
0x18001d4e6  mov     eax, r14d
0x18001d4e9  jmp     loc_18001D5CD
0x18001d4ee  mov     rsi, [rsp+68h+var_28]
0x18001d4f3  test    rsi, rsi
0x18001d4f6  jz      short loc_18001D52F
0x18001d4f8  or      edi, 0FFFFFFFFh
0x18001d4fb  mov     eax, edi
0x18001d4fd  lock xadd [rsi+8], eax
0x18001d502  add     eax, edi
0x18001d504  jnz     short loc_18001D52F
0x18001d506  mov     rax, [rsi]
0x18001d509  mov     rcx, rsi
0x18001d50c  mov     rax, [rax]
0x18001d50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d514  mov     eax, edi
0x18001d516  lock xadd [rsi+0Ch], eax
0x18001d51b  add     eax, edi
0x18001d51d  jnz     short loc_18001D52F
0x18001d51f  mov     rax, [rsi]
0x18001d522  mov     rcx, rsi
0x18001d525  mov     rax, [rax+8]
0x18001d529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d52e  nop
0x18001d52f  jmp     loc_18001D5BD
0x18001d534  mov     edi, 5B4h
0x18001d539  mov     rcx, [rsp+68h]; this
0x18001d53e  lea     rax, aPublisherFaile; "[Publisher]Failed"
0x18001d545  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18001d54a  mov     r9d, edi; char *
0x18001d54d  lea     r8, aOnecoreuapNetM_0; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18001d554  mov     edx, 0B9h; void *
0x18001d559  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001d55e  mov     r14d, eax
0x18001d561  mov     rsi, [rsp+68h+var_28]
0x18001d566  test    rsi, rsi
0x18001d569  jz      short loc_18001D5A2
0x18001d56b  or      edi, 0FFFFFFFFh
0x18001d56e  mov     ecx, edi
0x18001d570  lock xadd [rsi+8], ecx
0x18001d575  add     ecx, edi
0x18001d577  jnz     short loc_18001D5A2
0x18001d579  mov     rdx, [rsi]
0x18001d57c  mov     rcx, rsi
0x18001d57f  mov     rax, [rdx]
0x18001d582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d587  mov     eax, edi
0x18001d589  lock xadd [rsi+0Ch], eax
0x18001d58e  add     eax, edi
0x18001d590  jnz     short loc_18001D5A2
0x18001d592  mov     rax, [rsi]
0x18001d595  mov     rcx, rsi
0x18001d598  mov     rax, [rax+8]
0x18001d59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5a1  nop
0x18001d5a2  test    rbx, rbx
0x18001d5a5  jz      short loc_18001D5B0
0x18001d5a7  mov     rcx, rbx; lpCriticalSection
0x18001d5aa  call    cs:__imp_LeaveCriticalSection
0x18001d5b0  mov     eax, r14d
0x18001d5b3  jmp     short loc_18001D5CD
0x18001d5b5  mov     rbx, [rsp+68h+arg_18]
0x18001d5bd  test    rbx, rbx
0x18001d5c0  jz      short loc_18001D5CB
0x18001d5c2  mov     rcx, rbx; lpCriticalSection
0x18001d5c5  call    cs:__imp_LeaveCriticalSection
0x18001d5cb  xor     eax, eax
0x18001d5cd  mov     rbx, [rsp+68h+arg_8]
0x18001d5d2  add     rsp, 50h
0x18001d5d6  pop     r14
0x18001d5d8  pop     rdi
0x18001d5d9  pop     rsi
0x18001d5da  retn
0x18001d5db  mov     rcx, [rsp+68h]; this
0x18001d5e0  mov     edx, 0B0Fh; void *
0x18001d5e5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
