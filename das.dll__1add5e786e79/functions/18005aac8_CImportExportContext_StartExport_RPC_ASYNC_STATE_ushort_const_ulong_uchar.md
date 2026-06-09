# CImportExportContext::StartExport(_RPC_ASYNC_STATE *,ushort const *,ulong *,uchar * *)

- ea: `0x18005aac8`
- end: `0x18005ae4d`
- name: `?StartExport@CImportExportContext@@QEAAJPEAU_RPC_ASYNC_STATE@@PEBGPEAKPEAPEAE@Z`
- size: `901`
- prototype: `__int64 __usercall@<rax>(CImportExportContext *__hidden this@<rcx>, PRPC_ASYNC_STATE pAsync@<rdx>, const unsigned __int16 *@<r8>, unsigned int *@<r9>, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004b3b0`

## callees

- `0x180007500`
- `0x1800095bc`
- `0x18002394c`
- `0x180023f34`
- `0x1800452a4`
- `0x180059d7c`
- `0x18005a688`
- `0x18005aac8`
- `0x18005b428`
- `0x18005b674`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ab50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ab50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005aba3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ac11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005aba3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ac11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005addc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005addc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005adec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005adec`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005ab9a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005ab9a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005acb9`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005acb9`

## pseudocode

```c
__int64 __fastcall CImportExportContext::StartExport(
        CImportExportContext *this,
        PRPC_ASYNC_STATE pAsync,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  int v8; // edx
  int v9; // r8d
  int ProviderAepIdFromAepId; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  HANDLE ProcessHeap; // rax
  int v16; // [rsp+28h] [rbp-70h]
  int Reply; // [rsp+40h] [rbp-58h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v19[9]; // [rsp+50h] [rbp-48h] BYREF

  Reply = 0;
  lpMem = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)pAsync,
      (int)a3,
      39,
      &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
      v16,
      (char)this);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    if ( *((_DWORD *)this + 10) != 1 )
    {
      Reply = -2140930020;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v8,
          v9,
          40,
          &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
          28);
      RpcAsyncCompleteCall(pAsync, &Reply);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
      (*(void (__fastcall **)(CImportExportContext *))(*(_QWORD *)this + 16LL))(this);
      return (unsigned int)Reply;
    }
    *((_DWORD *)this + 10) = 3;
  }
  *((_QWORD *)this + 4) = pAsync;
  *((_QWORD *)this + 7) = a4;
  *((_QWORD *)this + 8) = a5;
  *((_QWORD *)this + 28) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  ProviderAepIdFromAepId = CImportExportContext::SubscribeForNotifications(this);
  Reply = ProviderAepIdFromAepId;
  if ( ProviderAepIdFromAepId )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v13 = 41;
LABEL_27:
      WPP_RECORDER_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v11,
        v12,
        v13,
        &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
        (__int64)a3,
        ProviderAepIdFromAepId);
    }
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl)
         || _InterlockedExchange((volatile __int32 *)this + 10, 3) == 1 )
  {
    Reply = CImportExportContext::SetupAsyncOp(this, a3);
    if ( Reply >= 0 )
    {
      if ( *((_DWORD *)this + 11) )
      {
        v16 = (int)a3;
        Ndr64AsyncClientCall(
          (MIDL_STUBLESS_PROXY_INFO *)&stru_180083280,
          0x1Fu,
          0,
          (char *)this + 96,
          (char *)this + 88);
      }
      else
      {
        v19[0] = 0;
        ProviderAepIdFromAepId = DafGetProviderAepIdFromAepId(a3, &lpMem);
        Reply = ProviderAepIdFromAepId;
        if ( ProviderAepIdFromAepId >= 0 )
        {
          Reply = (***((__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))this + 12))(
                    *((_QWORD *)this + 12),
                    &GUID_0c512544_e485_46b6_b339_7a301e1e412d,
                    v19);
          if ( Reply < 0 )
            goto LABEL_28;
          ProviderAepIdFromAepId = (*(__int64 (__fastcall **)(_QWORD, LPVOID, _QWORD))(**((_QWORD **)this + 11) + 32LL))(
                                     *((_QWORD *)this + 11),
                                     lpMem,
                                     v19[0]);
          Reply = ProviderAepIdFromAepId;
          if ( ProviderAepIdFromAepId >= 0 || *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            goto LABEL_28;
          v13 = 44;
          goto LABEL_27;
        }
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v13 = 43;
          goto LABEL_27;
        }
      }
    }
  }
  else
  {
    Reply = -2140930020;
  }
LABEL_28:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( Reply < 0 )
    OnAepExportCompleteStub(0, 0, Reply, (char *)this);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v11,
      v12,
      45,
      &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
      v16,
      (char)this,
      Reply);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18005aac8  mov     rax, rsp
0x18005aacb  mov     [rax+20h], r9
0x18005aacf  mov     [rax+18h], r8
0x18005aad3  mov     [rax+10h], rdx
0x18005aad7  mov     [rax+8], rcx
0x18005aadb  push    rbx
0x18005aadc  push    rsi
0x18005aadd  push    r12
0x18005aadf  push    r13
0x18005aae1  push    r14
0x18005aae3  push    r15
0x18005aae5  sub     rsp, 68h
0x18005aae9  mov     r12, r8
0x18005aaec  mov     r15, rdx
0x18005aaef  mov     rbx, rcx
0x18005aaf2  mov     dword ptr [rax-58h], 0
0x18005aaf9  mov     qword ptr [rax-50h], 0
0x18005ab01  lea     r14, WPP_RECORDER_INITIALIZED
0x18005ab08  lea     rsi, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005ab0f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ab16  jz      short loc_18005AB36
0x18005ab18  mov     r9d, 27h ; '''; int
0x18005ab1e  mov     [rax-68h], rcx
0x18005ab22  mov     [rax-78h], rsi
0x18005ab26  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab2d  mov     rcx, [rcx+28h]; int
0x18005ab31  call    WPP_RECORDER_SF_sq
0x18005ab36  lea     r13, [rbx+0E8h]
0x18005ab3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005ab44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005ab49  test    al, al
0x18005ab4b  jz      short loc_18005ABC9
0x18005ab4d  mov     rcx, r13; lpCriticalSection
0x18005ab50  call    cs:__imp_EnterCriticalSection
0x18005ab56  mov     eax, [rbx+28h]
0x18005ab59  cmp     eax, 1
0x18005ab5c  jz      short loc_18005ABBD
0x18005ab5e  mov     [rsp+98h+Reply], 8064001Ch
0x18005ab66  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ab6d  jz      short loc_18005AB92
0x18005ab6f  mov     r9d, 28h ; '('; int
0x18005ab75  mov     dword ptr [rsp+98h+var_70], 8064001Ch; char
0x18005ab7d  mov     [rsp+98h+MessageGuid], rsi; MessageGuid
0x18005ab82  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab89  mov     rcx, [rcx+28h]; int
0x18005ab8d  call    WPP_RECORDER_SF_D
0x18005ab92  lea     rdx, [rsp+98h+Reply]; Reply
0x18005ab97  mov     rcx, r15; pAsync
0x18005ab9a  call    cs:__imp_RpcAsyncCompleteCall
0x18005aba0  mov     rcx, r13; lpCriticalSection
0x18005aba3  call    cs:__imp_LeaveCriticalSection
0x18005aba9  mov     rax, [rbx]
0x18005abac  mov     rcx, rbx
0x18005abaf  mov     rax, [rax+10h]
0x18005abb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abb8  jmp     loc_18005AE3A
0x18005abbd  mov     r15d, 3
0x18005abc3  mov     [rbx+28h], r15d
0x18005abc7  jmp     short loc_18005ABCF
0x18005abc9  mov     r15d, 3
0x18005abcf  mov     rax, [rsp+98h+arg_8]
0x18005abd7  mov     [rbx+20h], rax
0x18005abdb  mov     rax, [rsp+98h+arg_18]
0x18005abe3  mov     [rbx+38h], rax
0x18005abe7  mov     rax, [rsp+98h+arg_20]
0x18005abef  mov     [rbx+40h], rax
0x18005abf3  mov     qword ptr [rbx+0E0h], 0
0x18005abfe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005ac05  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005ac0a  test    al, al
0x18005ac0c  jz      short loc_18005AC17
0x18005ac0e  mov     rcx, r13; lpCriticalSection
0x18005ac11  call    cs:__imp_LeaveCriticalSection
0x18005ac17  mov     rcx, rbx; pv
0x18005ac1a  call    ?SubscribeForNotifications@CImportExportContext@@IEAAJXZ; CImportExportContext::SubscribeForNotifications(void)
0x18005ac1f  mov     [rsp+98h+Reply], eax
0x18005ac23  test    eax, eax
0x18005ac25  jz      short loc_18005AC3F
0x18005ac27  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ac2e  jz      loc_18005ADD4
0x18005ac34  mov     r9d, 29h ; ')'
0x18005ac3a  jmp     loc_18005ADB6
0x18005ac3f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005ac46  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005ac4b  test    al, al
0x18005ac4d  jnz     short loc_18005AC66
0x18005ac4f  xchg    r15d, [rbx+28h]
0x18005ac53  cmp     r15d, 1
0x18005ac57  jz      short loc_18005AC66
0x18005ac59  mov     [rsp+98h+Reply], 8064001Ch
0x18005ac61  jmp     loc_18005ADD4
0x18005ac66  mov     rdx, r12; unsigned __int16 *
0x18005ac69  mov     rcx, rbx; this
0x18005ac6c  call    ?SetupAsyncOp@CImportExportContext@@IEAAJPEBG@Z; CImportExportContext::SetupAsyncOp(ushort const *)
0x18005ac71  mov     [rsp+98h+Reply], eax
0x18005ac75  test    eax, eax
0x18005ac77  js      loc_18005ADD4
0x18005ac7d  cmp     dword ptr [rbx+2Ch], 0
0x18005ac81  jz      loc_18005AD33
0x18005ac87  lea     rdx, [rbx+58h]
0x18005ac8b  lea     rax, [rbx+50h]
0x18005ac8f  lea     rcx, [rbx+48h]
0x18005ac93  lea     r9, [rdx+8]
0x18005ac97  mov     qword ptr [rsp+98h+var_60], rax
0x18005ac9c  mov     qword ptr [rsp+98h+var_68], rcx
0x18005aca1  mov     qword ptr [rsp+98h+var_70], r12
0x18005aca6  mov     [rsp+98h+MessageGuid], rdx
0x18005acab  xor     r8d, r8d; pReturnValue
0x18005acae  lea     edx, [r8+1Fh]; nProcNum
0x18005acb2  lea     rcx, stru_180083280; pProxyInfo
0x18005acb9  call    cs:__imp_Ndr64AsyncClientCall
0x18005acbf  jmp     loc_18005ADD4
0x18005acc4  cmp     eax, 1
0x18005acc7  jl      short loc_18005ACD1
0x18005acc9  movzx   eax, ax
0x18005accc  or      eax, 80010000h
0x18005acd1  mov     [rsp+98h+Reply], eax
0x18005acd5  lea     rcx, WPP_RECORDER_INITIALIZED
0x18005acdc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005ace3  jz      short loc_18005AD18
0x18005ace5  mov     r9d, 2Ah ; '*'; int
0x18005aceb  mov     dword ptr [rsp+98h+var_68], eax; char
0x18005acef  mov     rax, [rsp+98h+arg_10]
0x18005acf7  mov     qword ptr [rsp+98h+var_70], rax; __int64
0x18005acfc  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005ad03  mov     [rsp+98h+MessageGuid], rax; MessageGuid
0x18005ad08  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ad0f  mov     rcx, [rcx+28h]; int
0x18005ad13  call    WPP_RECORDER_SF_Sd
0x18005ad18  lea     r14, WPP_RECORDER_INITIALIZED
0x18005ad1f  lea     rsi, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005ad26  mov     rbx, [rsp+98h+arg_0]
0x18005ad2e  jmp     loc_18005ADD4
0x18005ad33  mov     [rsp+98h+var_48], 0
0x18005ad3c  lea     rdx, [rsp+98h+lpMem]
0x18005ad41  mov     rcx, r12
0x18005ad44  call    DafGetProviderAepIdFromAepId
0x18005ad49  mov     [rsp+98h+Reply], eax
0x18005ad4d  test    eax, eax
0x18005ad4f  jns     short loc_18005AD62
0x18005ad51  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ad58  jz      short loc_18005ADD4
0x18005ad5a  mov     r9d, 2Bh ; '+'
0x18005ad60  jmp     short loc_18005ADB6
0x18005ad62  mov     rcx, [rbx+60h]
0x18005ad66  mov     rax, [rcx]
0x18005ad69  lea     r8, [rsp+98h+var_48]
0x18005ad6e  lea     rdx, _GUID_0c512544_e485_46b6_b339_7a301e1e412d
0x18005ad75  mov     rax, [rax]
0x18005ad78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad7d  mov     [rsp+98h+Reply], eax
0x18005ad81  test    eax, eax
0x18005ad83  js      short loc_18005ADD4
0x18005ad85  mov     rcx, [rbx+58h]
0x18005ad89  mov     rax, [rcx]
0x18005ad8c  mov     r8, [rsp+98h+var_48]
0x18005ad91  mov     rdx, [rsp+98h+lpMem]
0x18005ad96  mov     rax, [rax+20h]
0x18005ad9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad9f  mov     [rsp+98h+Reply], eax
0x18005ada3  test    eax, eax
0x18005ada5  jns     short loc_18005ADD4
0x18005ada7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005adae  jz      short loc_18005ADD4
0x18005adb0  mov     r9d, 2Ch ; ','; int
0x18005adb6  mov     dword ptr [rsp+98h+var_68], eax; char
0x18005adba  mov     qword ptr [rsp+98h+var_70], r12; int
0x18005adbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005adc6  mov     [rsp+98h+MessageGuid], rsi; MessageGuid
0x18005adcb  mov     rcx, [rcx+28h]; int
0x18005adcf  call    WPP_RECORDER_SF_Sd
0x18005add4  cmp     [rsp+98h+lpMem], 0
0x18005adda  jz      short loc_18005ADF2
0x18005addc  call    cs:__imp_GetProcessHeap
0x18005ade2  mov     r8, [rsp+98h+lpMem]; lpMem
0x18005ade7  xor     edx, edx; dwFlags
0x18005ade9  mov     rcx, rax; hHeap
0x18005adec  call    cs:__imp_HeapFree
0x18005adf2  mov     eax, [rsp+98h+Reply]
0x18005adf6  test    eax, eax
0x18005adf8  jns     short loc_18005AE09
0x18005adfa  mov     r9, rbx; void *
0x18005adfd  mov     r8d, eax; int
0x18005ae00  xor     edx, edx; unsigned __int8 *
0x18005ae02  xor     ecx, ecx; unsigned int
0x18005ae04  call    ?OnAepExportCompleteStub@@YAJKPEBEJPEAX@Z; OnAepExportCompleteStub(ulong,uchar const *,long,void *)
0x18005ae09  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005ae10  jz      short loc_18005AE3A
0x18005ae12  mov     r9d, 2Dh ; '-'; int
0x18005ae18  mov     eax, [rsp+98h+Reply]
0x18005ae1c  mov     dword ptr [rsp+98h+var_60], eax; char
0x18005ae20  mov     qword ptr [rsp+98h+var_68], rbx; char
0x18005ae25  mov     [rsp+98h+MessageGuid], rsi; MessageGuid
0x18005ae2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ae31  mov     rcx, [rcx+28h]; int
0x18005ae35  call    WPP_RECORDER_SF_sqd
0x18005ae3a  mov     eax, [rsp+98h+Reply]
0x18005ae3e  add     rsp, 68h
0x18005ae42  pop     r15
0x18005ae44  pop     r14
0x18005ae46  pop     r13
0x18005ae48  pop     r12
0x18005ae4a  pop     rsi
0x18005ae4b  pop     rbx
0x18005ae4c  retn
```
