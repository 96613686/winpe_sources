# BthServLocalRadioInsertion(ushort const *,int)

- ea: `0x18000d498`
- end: `0x18000d87e`
- name: `?BthServLocalRadioInsertion@@YAHPEBGH@Z`
- size: `998`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180014310`

## callees

- `0x180001b94`
- `0x180001bcc`
- `0x180009c50`
- `0x18000ad90`
- `0x18000b194`
- `0x18000c0cc`
- `0x18000d498`
- `0x18000db08`
- `0x180011c5c`
- `0x180012004`
- `0x1800120b8`
- `0x180012384`
- `0x18001268c`
- `0x18001ac64`
- `0x180022a74`
- `0x1800348d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d7eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d7eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d732`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d7ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d7ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d7ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d7ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d79a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d79a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d559`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d559`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d53d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d673`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d53d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d673`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BthServLocalRadioInsertion(char *a1, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  char v5; // si
  __int64 v6; // rbx
  unsigned __int64 v7; // rbx
  unsigned int v8; // r14d
  _WORD *v9; // rax
  int v10; // r8d
  _WORD *v11; // rcx
  unsigned __int64 v12; // rdx
  char *v13; // r15
  __int16 v14; // ax
  int v15; // edx
  int v16; // r8d
  bool LocalRadioAddressInfo; // al
  _BYTE *v18; // rcx
  char v19; // bl
  bool v20; // r15
  int v21; // r8d
  int v22; // edx
  void *v23; // rax
  LocalCorePerformanceTelemetryCollector *v24; // rax
  struct _TP_TIMER **v25; // r15
  struct _TP_TIMER *v26; // rbx
  __int64 *v27; // rdx
  bool v29; // dl
  int v30; // [rsp+20h] [rbp-78h]
  int v31; // [rsp+A8h] [rbp+10h]
  struct _TP_TIMER **v32; // [rsp+B0h] [rbp+18h] BYREF
  RTL_SRWLOCK *v33; // [rsp+B8h] [rbp+20h] BYREF

  v31 = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
  {
    LOBYTE(a2) = 0;
    v5 = 1;
  }
  else
  {
    v5 = 1;
    LOBYTE(a2) = 1;
  }
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 5));
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)&a1[2 * v6] );
  v7 = v6 + 1;
  v8 = 0;
  if ( *(&pv + 1) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v4, a2, a3);
    LocalFree(*(&pv + 1));
    *(&pv + 1) = 0;
  }
  v9 = LocalAlloc(0x40u, 2 * v7);
  v11 = v9;
  *(&pv + 1) = v9;
  if ( !v9 )
    goto LABEL_45;
  if ( v7 )
  {
    if ( v7 <= 0x7FFFFFFF )
    {
      v12 = 2147483646 - v7;
      v13 = (char *)(a1 - (char *)v9);
      while ( v12 + v7 )
      {
        v14 = *(_WORD *)((char *)v11 + (_QWORD)v13);
        if ( v14 )
        {
          *v11++ = v14;
          if ( --v7 )
            continue;
        }
        if ( !v7 )
          --v11;
        break;
      }
      *v11 = 0;
    }
    else
    {
      *v9 = 0;
    }
  }
  v8 = BthServOpenLocalRadio((LPCWSTR)*(&pv + 1));
  BthServRestoreTemporaryScanState();
  if ( v31 )
  {
    LODWORD(v33) = 0;
    LODWORD(v32) = 0;
    DafBthSynchronize((unsigned int *)&v33, (unsigned int *)&v32);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v15) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
    {
      LOBYTE(v15) = 0;
    }
    if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v30);
    }
  }
  if ( !v8 )
  {
    LocalFree(*(&pv + 1));
    *(&pv + 1) = 0;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49201598>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49201598>::GetImpl'::`2'::impl) )
    goto LABEL_45;
  v32 = 0;
  LocalRadioAddressInfo = BthServGetLocalRadioAddressInfo((unsigned __int64 *)&v32);
  v8 = LocalRadioAddressInfo;
  if ( LocalRadioAddressInfo )
  {
    try
    {
      AcquireSRWLockExclusive(&stru_180047118);
      v33 = &stru_180047118;
      v23 = operator new(0x10u);
      v24 = LocalCorePerformanceTelemetryCollector::LocalCorePerformanceTelemetryCollector(v23, (unsigned __int64)v32);
      v32 = 0;
      v25 = (struct _TP_TIMER **)qword_180047130;
      qword_180047130 = v24;
      if ( v25 )
      {
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          v25 + 1,
          0);
        v26 = v25[1];
        if ( v26 )
        {
          SetThreadpoolTimer(v25[1], 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(v26, 1);
          CloseThreadpoolTimer(v26);
        }
        operator delete(v25, (const struct std::nothrow_t *)0x10);
      }
      std::unique_ptr<LocalCorePerformanceTelemetryCollector>::~unique_ptr<LocalCorePerformanceTelemetryCollector>(&v32);
      ReleaseSRWLockExclusive(&stru_180047118);
    }
    catch ( ... )
    {
      v29 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v29,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      LODWORD(v32) = 0;
      SetLastError(0xEu);
      v5 = 1;
      v8 = (unsigned int)v32;
      goto LABEL_45;
    }
    goto LABEL_45;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v19 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
    v19 = 0;
  v20 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    GetLastError();
    LOBYTE(v21) = v20;
    LOBYTE(v22) = v19;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v21, *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_45:
    v18 = WPP_GLOBAL_Control;
  }
  v27 = WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids;
  if ( v18 == (_BYTE *)&WPP_GLOBAL_Control || v18[25] < 5u )
    v5 = 0;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v27) = v5;
    LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v18 + 2), (_DWORD)v27, v10, *((_QWORD *)v18 + 5));
  }
  return v8;
}

```

## disassembly

```asm
0x18000d498  mov     [rsp+arg_8], edx
0x18000d49c  push    rbx
0x18000d49d  push    rsi
0x18000d49e  push    rdi
0x18000d49f  push    r12
0x18000d4a1  push    r13
0x18000d4a3  push    r14
0x18000d4a5  push    r15
0x18000d4a7  sub     rsp, 60h
0x18000d4ab  mov     r15, rcx
0x18000d4ae  xor     edi, edi
0x18000d4b0  lea     r12, WPP_GLOBAL_Control
0x18000d4b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4be  cmp     rcx, r12
0x18000d4c1  jz      short loc_18000D4D1
0x18000d4c3  cmp     byte ptr [rcx+19h], 5
0x18000d4c7  jb      short loc_18000D4D1
0x18000d4c9  lea     esi, [rdi+1]
0x18000d4cc  mov     dl, sil
0x18000d4cf  jmp     short loc_18000D4D9
0x18000d4d1  mov     dl, dil
0x18000d4d4  mov     esi, 1
0x18000d4d9  lea     r13, WPP_RECORDER_INITIALIZED
0x18000d4e0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000d4e7  setnz   r8b
0x18000d4eb  test    dl, dl
0x18000d4ed  jnz     short loc_18000D4F4
0x18000d4ef  test    r8b, r8b
0x18000d4f2  jz      short loc_18000D514
0x18000d4f4  lea     r14, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d4fb  mov     [rsp+98h+var_60], r14
0x18000d500  mov     [rsp+98h+var_68], 63h ; 'c'
0x18000d507  mov     r9, [rcx+28h]
0x18000d50b  mov     rcx, [rcx+10h]
0x18000d50f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000d514  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d518  inc     rbx
0x18000d51b  cmp     [r15+rbx*2], di
0x18000d520  jnz     short loc_18000D518
0x18000d522  add     rbx, rsi
0x18000d525  mov     r14d, edi
0x18000d528  cmp     qword ptr cs:pv+8, rdi
0x18000d52f  jz      short loc_18000D550
0x18000d531  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d536  mov     rcx, qword ptr cs:pv+8; hMem
0x18000d53d  call    cs:__imp_LocalFree
0x18000d544  nop     dword ptr [rax+rax+00h]
0x18000d549  mov     qword ptr cs:pv+8, rdi
0x18000d550  lea     rdx, [rbx+rbx]; uBytes
0x18000d554  mov     ecx, 40h ; '@'; uFlags
0x18000d559  call    cs:__imp_LocalAlloc
0x18000d560  nop     dword ptr [rax+rax+00h]
0x18000d565  mov     rcx, rax
0x18000d568  mov     qword ptr cs:pv+8, rax
0x18000d56f  test    rax, rax
0x18000d572  jz      loc_18000D815
0x18000d578  test    rbx, rbx
0x18000d57b  jz      short loc_18000D5C1
0x18000d57d  cmp     rbx, 7FFFFFFFh
0x18000d584  jbe     short loc_18000D58B
0x18000d586  mov     [rax], di
0x18000d589  jmp     short loc_18000D5C1
0x18000d58b  mov     edx, 7FFFFFFEh
0x18000d590  sub     rdx, rbx
0x18000d593  sub     r15, rax
0x18000d596  lea     rax, [rdx+rbx]
0x18000d59a  test    rax, rax
0x18000d59d  jz      short loc_18000D5BE
0x18000d59f  movzx   eax, word ptr [r15+rcx]
0x18000d5a4  test    ax, ax
0x18000d5a7  jz      short loc_18000D5B5
0x18000d5a9  mov     [rcx], ax
0x18000d5ac  add     rcx, 2
0x18000d5b0  sub     rbx, rsi
0x18000d5b3  jnz     short loc_18000D596
0x18000d5b5  test    rbx, rbx
0x18000d5b8  jnz     short loc_18000D5BE
0x18000d5ba  sub     rcx, 2
0x18000d5be  mov     [rcx], di
0x18000d5c1  mov     rcx, qword ptr cs:pv+8; lpFileName
0x18000d5c8  call    ?BthServOpenLocalRadio@@YAHPEBG@Z; BthServOpenLocalRadio(ushort const *)
0x18000d5cd  mov     r14d, eax
0x18000d5d0  call    ?BthServRestoreTemporaryScanState@@YAKXZ; BthServRestoreTemporaryScanState(void)
0x18000d5d5  cmp     [rsp+98h+arg_8], edi
0x18000d5dc  jz      loc_18000D667
0x18000d5e2  mov     dword ptr [rsp+98h+arg_18], edi
0x18000d5e9  mov     dword ptr [rsp+98h+arg_10], edi
0x18000d5f0  lea     rdx, [rsp+98h+arg_10]; unsigned int *
0x18000d5f8  lea     rcx, [rsp+98h+arg_18]; unsigned int *
0x18000d600  call    ?DafBthSynchronize@@YAJPEAK0@Z; DafBthSynchronize(ulong *,ulong *)
0x18000d605  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d60c  cmp     rcx, r12
0x18000d60f  jz      short loc_18000D61A
0x18000d611  cmp     byte ptr [rcx+19h], 4
0x18000d615  mov     dl, sil
0x18000d618  jnb     short loc_18000D61D
0x18000d61a  mov     dl, dil
0x18000d61d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000d624  setnz   r8b
0x18000d628  test    dl, dl
0x18000d62a  jnz     short loc_18000D631
0x18000d62c  test    r8b, r8b
0x18000d62f  jz      short loc_18000D667
0x18000d631  mov     eax, dword ptr [rsp+98h+arg_10]
0x18000d638  mov     [rsp+98h+var_48], eax
0x18000d63c  mov     eax, dword ptr [rsp+98h+arg_18]
0x18000d643  mov     dword ptr [rsp+98h+var_50], eax
0x18000d647  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d64e  mov     [rsp+98h+var_60], rax
0x18000d653  mov     [rsp+98h+var_68], 64h ; 'd'
0x18000d65a  mov     r9, [rcx+28h]
0x18000d65e  mov     rcx, [rcx+10h]
0x18000d662  call    WPP_RECORDER_AND_TRACE_SF_sdd
0x18000d667  test    r14d, r14d
0x18000d66a  jnz     short loc_18000D686
0x18000d66c  mov     rcx, qword ptr cs:pv+8; hMem
0x18000d673  call    cs:__imp_LocalFree
0x18000d67a  nop     dword ptr [rax+rax+00h]
0x18000d67f  mov     qword ptr cs:pv+8, rdi
0x18000d686  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49201598@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49201598@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49201598> `wil::Feature<__WilFeatureTraits_Feature_49201598>::GetImpl(void)'::`2'::impl
0x18000d68d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49201598@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49201598>::__private_IsEnabled(void)
0x18000d692  test    al, al
0x18000d694  jz      loc_18000D815
0x18000d69a  mov     [rsp+98h+arg_10], rdi
0x18000d6a2  lea     rcx, [rsp+98h+arg_10]; unsigned __int64 *
0x18000d6aa  call    ?BthServGetLocalRadioAddressInfo@@YA_NPEA_K@Z; BthServGetLocalRadioAddressInfo(unsigned __int64 *)
0x18000d6af  movzx   r14d, al
0x18000d6b3  test    al, al
0x18000d6b5  jnz     short loc_18000D728
0x18000d6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6be  cmp     rcx, r12
0x18000d6c1  jz      short loc_18000D6CC
0x18000d6c3  cmp     byte ptr [rcx+19h], 2
0x18000d6c7  mov     bl, sil
0x18000d6ca  jnb     short loc_18000D6CF
0x18000d6cc  mov     bl, dil
0x18000d6cf  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000d6d6  setnz   r15b
0x18000d6da  test    bl, bl
0x18000d6dc  jnz     short loc_18000D6E7
0x18000d6de  test    r15b, r15b
0x18000d6e1  jz      loc_18000D81C
0x18000d6e7  call    cs:__imp_GetLastError
0x18000d6ee  nop     dword ptr [rax+rax+00h]
0x18000d6f3  mov     dword ptr [rsp+98h+var_50], eax
0x18000d6f7  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d6fe  mov     [rsp+98h+var_60], rax
0x18000d703  mov     [rsp+98h+var_68], 65h ; 'e'
0x18000d70a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d711  mov     r9, [rcx+28h]
0x18000d715  mov     r8b, r15b
0x18000d718  mov     dl, bl
0x18000d71a  mov     rcx, [rcx+10h]
0x18000d71e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000d723  jmp     loc_18000D815
0x18000d728  lea     rbx, stru_180047118
0x18000d72f  mov     rcx, rbx; SRWLock
0x18000d732  call    cs:__imp_AcquireSRWLockExclusive
0x18000d739  nop     dword ptr [rax+rax+00h]
0x18000d73e  mov     [rsp+98h+arg_18], rbx
0x18000d746  mov     ecx, 10h; Size
0x18000d74b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d750  mov     rdx, [rsp+98h+arg_10]; unsigned __int64
0x18000d758  mov     rcx, rax; pv
0x18000d75b  call    ??0LocalCorePerformanceTelemetryCollector@@QEAA@_K@Z; LocalCorePerformanceTelemetryCollector::LocalCorePerformanceTelemetryCollector(unsigned __int64)
0x18000d760  mov     [rsp+98h+arg_10], rdi
0x18000d768  mov     r15, cs:qword_180047130
0x18000d76f  mov     cs:qword_180047130, rax
0x18000d776  test    r15, r15
0x18000d779  jz      short loc_18000D7DA
0x18000d77b  xor     edx, edx
0x18000d77d  lea     rcx, [r15+8]
0x18000d781  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000d786  mov     rbx, [r15+8]
0x18000d78a  test    rbx, rbx
0x18000d78d  jz      short loc_18000D7C6
0x18000d78f  xor     r9d, r9d; msWindowLength
0x18000d792  xor     r8d, r8d; msPeriod
0x18000d795  xor     edx, edx; pftDueTime
0x18000d797  mov     rcx, rbx; pti
0x18000d79a  call    cs:__imp_SetThreadpoolTimer
0x18000d7a1  nop     dword ptr [rax+rax+00h]
0x18000d7a6  mov     edx, esi; fCancelPendingCallbacks
0x18000d7a8  mov     rcx, rbx; pti
0x18000d7ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d7b2  nop     dword ptr [rax+rax+00h]
0x18000d7b7  mov     rcx, rbx; pti
0x18000d7ba  call    cs:__imp_CloseThreadpoolTimer
0x18000d7c1  nop     dword ptr [rax+rax+00h]
0x18000d7c6  mov     edx, 10h; struct std::nothrow_t *
0x18000d7cb  mov     rcx, r15; void *
0x18000d7ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d7d3  lea     rbx, stru_180047118
0x18000d7da  lea     rcx, [rsp+98h+arg_10]
0x18000d7e2  call    ??1?$unique_ptr@VLocalCorePerformanceTelemetryCollector@@U?$default_delete@VLocalCorePerformanceTelemetryCollector@@@std@@@std@@QEAA@XZ; std::unique_ptr<LocalCorePerformanceTelemetryCollector>::~unique_ptr<LocalCorePerformanceTelemetryCollector>(void)
0x18000d7e7  nop
0x18000d7e8  mov     rcx, rbx; SRWLock
0x18000d7eb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d7f2  nop     dword ptr [rax+rax+00h]
0x18000d7f7  nop
0x18000d7f8  jmp     short loc_18000D815
0x18000d7fa  xor     edi, edi
0x18000d7fc  lea     r12, WPP_GLOBAL_Control
0x18000d803  lea     esi, [rdi+1]
0x18000d806  lea     r13, WPP_RECORDER_INITIALIZED
0x18000d80d  mov     r14d, dword ptr [rsp+98h+arg_10]
0x18000d815  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d81c  lea     rdx, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d823  cmp     rcx, r12
0x18000d826  jz      short loc_18000D82E
0x18000d828  cmp     byte ptr [rcx+19h], 5
0x18000d82c  jnb     short loc_18000D831
0x18000d82e  mov     sil, dil
0x18000d831  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18000d838  setnz   r8b
0x18000d83c  test    sil, sil
0x18000d83f  jnz     short loc_18000D846
0x18000d841  test    r8b, r8b
0x18000d844  jz      short loc_18000D86A
0x18000d846  movsxd  rax, r14d
0x18000d849  mov     [rsp+98h+var_50], rax
0x18000d84e  mov     [rsp+98h+var_60], rdx
0x18000d853  mov     [rsp+98h+var_68], 67h ; 'g'
0x18000d85a  mov     r9, [rcx+28h]
0x18000d85e  mov     dl, sil
0x18000d861  mov     rcx, [rcx+10h]
0x18000d865  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000d86a  mov     eax, r14d
0x18000d86d  add     rsp, 60h
0x18000d871  pop     r15
0x18000d873  pop     r14
0x18000d875  pop     r13
0x18000d877  pop     r12
0x18000d879  pop     rdi
0x18000d87a  pop     rsi
0x18000d87b  pop     rbx
0x18000d87c  retn
```
