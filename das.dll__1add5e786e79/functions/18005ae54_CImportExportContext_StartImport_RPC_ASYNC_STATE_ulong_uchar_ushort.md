# CImportExportContext::StartImport(_RPC_ASYNC_STATE *,ulong,uchar *,ushort * *)

- ea: `0x18005ae54`
- end: `0x18005b422`
- name: `?StartImport@CImportExportContext@@QEAAJPEAU_RPC_ASYNC_STATE@@KPEAEPEAPEAG@Z`
- size: `1486`
- prototype: `__int64 __usercall@<rax>(CImportExportContext *__hidden this@<rcx>, PRPC_ASYNC_STATE pAsync@<rdx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004b540`

## callees

- `0x180007500`
- `0x180009220`
- `0x180009590`
- `0x1800095bc`
- `0x1800185d0`
- `0x18002394c`
- `0x180023f34`
- `0x1800452a4`
- `0x1800489e4`
- `0x18005a688`
- `0x18005ae54`
- `0x18005b428`
- `0x18005b674`
- `0x18005f4a4`
- `0x18007e9d8`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005aefc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b046`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b359`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005aefc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b046`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b359`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005af4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005afba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b3bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005af4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005afba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b3bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b323`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b323`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b333`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b333`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005af46`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005af46`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005b1d7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005b1d7`

## pseudocode

```c
__int64 __fastcall CImportExportContext::StartImport(
        CImportExportContext *this,
        PRPC_ASYNC_STATE pAsync,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned __int16 **a5)
{
  int v8; // edx
  int v9; // r8d
  int v10; // eax
  void *v11; // rdx
  int v12; // r8d
  int v13; // r9d
  int v14; // eax
  unsigned __int64 v15; // r13
  _QWORD *v16; // rbx
  int ProviderAepIdFromAepId; // eax
  int v18; // r9d
  HANDLE ProcessHeap; // rax
  void *v20; // rdx
  int v21; // r8d
  void ***v22; // rbx
  __int64 v24; // [rsp+28h] [rbp-90h]
  int Reply; // [rsp+50h] [rbp-68h] BYREF
  wil::details *pObject; // [rsp+58h] [rbp-60h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-58h] BYREF
  __int64 v28; // [rsp+68h] [rbp-50h] BYREF
  unsigned __int64 v29; // [rsp+70h] [rbp-48h] BYREF
  void ***v30; // [rsp+78h] [rbp-40h]
  char *v31; // [rsp+80h] [rbp-38h]
  _DWORD *v32; // [rsp+88h] [rbp-30h]

  Reply = 0;
  pObject = 0;
  lpMem = 0;
  v28 = 0;
  v29 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)pAsync,
      a3,
      27,
      &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
      v24,
      (char)this);
  v31 = (char *)this + 232;
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
          28,
          &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
          28);
      RpcAsyncCompleteCall(pAsync, &Reply);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
      (*(void (__fastcall **)(CImportExportContext *))(*(_QWORD *)this + 16LL))(this);
      return (unsigned int)Reply;
    }
    *((_DWORD *)this + 10) = 2;
  }
  *((_QWORD *)this + 4) = pAsync;
  v30 = (void ***)((char *)this + 56);
  *((_QWORD *)this + 7) = a5;
  *((_DWORD *)this + 56) = 0;
  v32 = (_DWORD *)((char *)this + 228);
  *((_DWORD *)this + 57) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v10 = CImportExportContext::SubscribeForNotifications(this);
  Reply = v10;
  if ( v10 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v13 = 29;
LABEL_14:
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)v11,
        v12,
        v13,
        &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
        v10);
    }
  }
  else
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl)
      && _InterlockedExchange((volatile __int32 *)this + 10, 2) != 1 )
    {
      Reply = -2140930020;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)v11,
          v12,
          30,
          &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
          28);
      goto LABEL_47;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    if ( *((_DWORD *)this + 56) )
      v14 = -2147416294;
    else
      v14 = DecodeBlob(a3, a4, &pObject);
    Reply = v14;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    if ( Reply == -2147024809 )
      Reply = -2140930022;
    LOBYTE(v10) = Reply;
    if ( Reply >= 0 )
    {
      if ( *((_DWORD *)pObject + 2) != 2 )
      {
        Reply = -2140930022;
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            (int)v11,
            v12,
            32,
            &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
            *(_QWORD *)pObject,
            26);
        goto LABEL_47;
      }
      Reply = StringCbLengthW(*(const unsigned __int16 **)pObject, 0x600u, &v29);
      if ( Reply >= 0 )
      {
        v15 = v29;
        v16 = (_QWORD *)*((_QWORD *)this + 7);
        *v16 = DAF_user_alloc(v29 + 2);
        if ( **v30 )
        {
          memcpy_0(**v30, *(const void **)pObject, v15 + 2);
          ProviderAepIdFromAepId = CImportExportContext::SetupAsyncOp(this, *(const unsigned __int16 **)pObject);
          Reply = ProviderAepIdFromAepId;
          if ( ProviderAepIdFromAepId >= 0 )
          {
            if ( *((_DWORD *)this + 11) )
            {
              v24 = *(_QWORD *)pObject;
              Ndr64AsyncClientCall(
                (MIDL_STUBLESS_PROXY_INFO *)&stru_180083280,
                0x1Eu,
                0,
                (char *)this + 96,
                (char *)this + 88);
              goto LABEL_47;
            }
            ProviderAepIdFromAepId = DafGetProviderAepIdFromAepId(*(_QWORD *)pObject, &lpMem);
            Reply = ProviderAepIdFromAepId;
            if ( ProviderAepIdFromAepId >= 0 )
            {
              Reply = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 12))(
                        *((_QWORD *)this + 12),
                        &GUID_0c512544_e485_46b6_b339_7a301e1e412d,
                        &v28);
              if ( Reply < 0 )
                goto LABEL_47;
              ProviderAepIdFromAepId = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 11)
                                                                                                  + 24LL))(
                                         *((_QWORD *)this + 11),
                                         **((unsigned int **)pObject + 2),
                                         *(_QWORD *)(*((_QWORD *)pObject + 2) + 8LL),
                                         v28);
              Reply = ProviderAepIdFromAepId;
              if ( ProviderAepIdFromAepId >= 0 || *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                goto LABEL_47;
              v18 = 36;
            }
            else
            {
              if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                goto LABEL_47;
              v18 = 35;
            }
          }
          else
          {
            if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              goto LABEL_47;
            v18 = 33;
          }
          WPP_RECORDER_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            (int)v11,
            v12,
            v18,
            &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
            *(_QWORD *)pObject,
            ProviderAepIdFromAepId);
          goto LABEL_47;
        }
        Reply = -2147024882;
      }
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v13 = 31;
      goto LABEL_14;
    }
  }
LABEL_47:
  if ( pObject )
    wil::details::FreeProcessHeap(pObject, v11);
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( Reply < 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    if ( *v32 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)v20,
          v21,
          37,
          &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
          Reply);
    }
    else
    {
      v22 = v30;
      if ( **v30 )
      {
        wil::details::FreeProcessHeap((wil::details *)**v30, v20);
        **v22 = 0;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    DAS::Dispatcher::Dispatch::OnAepImportComplete(0, 0, Reply, this);
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)v11,
      v12,
      38,
      &WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids,
      v24,
      (char)this,
      Reply);
  return (unsigned int)Reply;
}

```

## disassembly

```asm
0x18005ae54  mov     rax, rsp
0x18005ae57  mov     [rax+10h], rbx
0x18005ae5b  mov     [rax+18h], r8d
0x18005ae5f  mov     [rax+8], rcx
0x18005ae63  push    rsi
0x18005ae64  push    r12
0x18005ae66  push    r13
0x18005ae68  push    r14
0x18005ae6a  push    r15
0x18005ae6c  sub     rsp, 90h
0x18005ae73  mov     r13, r9
0x18005ae76  mov     rbx, rdx
0x18005ae79  mov     rsi, rcx
0x18005ae7c  mov     dword ptr [rax-68h], 0
0x18005ae83  mov     qword ptr [rax-60h], 0
0x18005ae8b  mov     qword ptr [rax-58h], 0
0x18005ae93  mov     qword ptr [rax-50h], 0
0x18005ae9b  mov     qword ptr [rax-48h], 0
0x18005aea3  lea     r14, WPP_RECORDER_INITIALIZED
0x18005aeaa  lea     r15, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005aeb1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005aeb8  jz      short loc_18005AEDA
0x18005aeba  mov     r9d, 1Bh; int
0x18005aec0  mov     qword ptr [rsp+0B8h+var_88], rcx; char
0x18005aec5  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18005aeca  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aed1  mov     rcx, [rcx+28h]; int
0x18005aed5  call    WPP_RECORDER_SF_sq
0x18005aeda  lea     r12, [rsi+0E8h]
0x18005aee1  mov     [rsp+0B8h+var_38], r12
0x18005aee9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005aef0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005aef5  test    al, al
0x18005aef7  jz      short loc_18005AF70
0x18005aef9  mov     rcx, r12; lpCriticalSection
0x18005aefc  call    cs:__imp_EnterCriticalSection
0x18005af02  mov     eax, [rsi+28h]
0x18005af05  cmp     eax, 1
0x18005af08  jz      short loc_18005AF69
0x18005af0a  mov     [rsp+0B8h+Reply], 8064001Ch
0x18005af12  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005af19  jz      short loc_18005AF3E
0x18005af1b  mov     r9d, 1Ch; int
0x18005af21  mov     dword ptr [rsp+0B8h+var_90], 8064001Ch; char
0x18005af29  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18005af2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005af35  mov     rcx, [rcx+28h]; int
0x18005af39  call    WPP_RECORDER_SF_D
0x18005af3e  lea     rdx, [rsp+0B8h+Reply]; Reply
0x18005af43  mov     rcx, rbx; pAsync
0x18005af46  call    cs:__imp_RpcAsyncCompleteCall
0x18005af4c  mov     rcx, r12; lpCriticalSection
0x18005af4f  call    cs:__imp_LeaveCriticalSection
0x18005af55  mov     rax, [rsi]
0x18005af58  mov     rcx, rsi
0x18005af5b  mov     rax, [rax+10h]
0x18005af5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af64  jmp     loc_18005B405
0x18005af69  mov     dword ptr [rsi+28h], 2
0x18005af70  mov     [rsi+20h], rbx
0x18005af74  lea     rbx, [rsi+38h]
0x18005af78  mov     [rsp+0B8h+var_40], rbx
0x18005af7d  mov     rax, [rsp+0B8h+arg_20]
0x18005af85  mov     [rbx], rax
0x18005af88  mov     dword ptr [rsi+0E0h], 0
0x18005af92  lea     rax, [rsi+0E4h]
0x18005af99  mov     [rsp+0B8h+var_30], rax
0x18005afa1  mov     dword ptr [rax], 0
0x18005afa7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005afae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005afb3  test    al, al
0x18005afb5  jz      short loc_18005AFC0
0x18005afb7  mov     rcx, r12; lpCriticalSection
0x18005afba  call    cs:__imp_LeaveCriticalSection
0x18005afc0  mov     rcx, rsi; pv
0x18005afc3  call    ?SubscribeForNotifications@CImportExportContext@@IEAAJXZ; CImportExportContext::SubscribeForNotifications(void)
0x18005afc8  mov     [rsp+0B8h+Reply], eax
0x18005afcc  test    eax, eax
0x18005afce  jz      short loc_18005B001
0x18005afd0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005afd7  jz      loc_18005B30C
0x18005afdd  mov     r9d, 1Dh; int
0x18005afe3  mov     dword ptr [rsp+0B8h+var_90], eax; char
0x18005afe7  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18005afec  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aff3  mov     rcx, [rcx+28h]; int
0x18005aff7  call    WPP_RECORDER_SF_D
0x18005affc  jmp     loc_18005B30C
0x18005b001  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x18005b008  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x18005b00d  test    al, al
0x18005b00f  jnz     short loc_18005B043
0x18005b011  mov     eax, 2
0x18005b016  xchg    eax, [rsi+28h]
0x18005b019  cmp     eax, 1
0x18005b01c  jz      short loc_18005B043
0x18005b01e  mov     [rsp+0B8h+Reply], 8064001Ch
0x18005b026  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b02d  jz      loc_18005B30C
0x18005b033  mov     r9d, 1Eh
0x18005b039  mov     dword ptr [rsp+0B8h+var_90], 8064001Ch
0x18005b041  jmp     short loc_18005AFE7
0x18005b043  mov     rcx, r12; lpCriticalSection
0x18005b046  call    cs:__imp_EnterCriticalSection
0x18005b04c  cmp     dword ptr [rsi+0E0h], 0
0x18005b053  jz      short loc_18005B05C
0x18005b055  mov     eax, 8001071Ah
0x18005b05a  jmp     short loc_18005B070
0x18005b05c  lea     r8, [rsp+0B8h+pObject]; pObject
0x18005b061  mov     rdx, r13; Src
0x18005b064  mov     ecx, dword ptr [rsp+0B8h+Size]; Size
0x18005b06b  call    ?DecodeBlob@@YAJKPEBXPEAPEAU_ENCODE_OBJECT@@@Z; DecodeBlob(ulong,void const *,_ENCODE_OBJECT * *)
0x18005b070  mov     [rsp+0B8h+Reply], eax
0x18005b074  mov     rcx, r12; lpCriticalSection
0x18005b077  call    cs:__imp_LeaveCriticalSection
0x18005b07d  cmp     [rsp+0B8h+Reply], 80070057h
0x18005b085  jnz     short loc_18005B08F
0x18005b087  mov     [rsp+0B8h+Reply], 8064001Ah
0x18005b08f  mov     eax, [rsp+0B8h+Reply]
0x18005b093  test    eax, eax
0x18005b095  jns     short loc_18005B0AF
0x18005b097  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b09e  jz      loc_18005B30C
0x18005b0a4  mov     r9d, 1Fh
0x18005b0aa  jmp     loc_18005AFE3
0x18005b0af  mov     rcx, [rsp+0B8h+pObject]
0x18005b0b4  cmp     dword ptr [rcx+8], 2
0x18005b0b8  jz      short loc_18005B0EA
0x18005b0ba  mov     [rsp+0B8h+Reply], 8064001Ah
0x18005b0c2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b0c9  jz      loc_18005B30C
0x18005b0cf  mov     r9d, 20h ; ' '
0x18005b0d5  mov     dword ptr [rsp+0B8h+var_88], 8064001Ah
0x18005b0dd  mov     rax, [rcx]
0x18005b0e0  mov     qword ptr [rsp+0B8h+var_90], rax
0x18005b0e5  jmp     loc_18005B2F7
0x18005b0ea  lea     r8, [rsp+0B8h+var_48]; unsigned __int64 *
0x18005b0ef  mov     edx, 600h; unsigned __int64
0x18005b0f4  mov     rcx, [rsp+0B8h+pObject]
0x18005b0f9  mov     rcx, [rcx]; unsigned __int16 *
0x18005b0fc  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005b101  mov     [rsp+0B8h+Reply], eax
0x18005b105  test    eax, eax
0x18005b107  js      loc_18005B30C
0x18005b10d  mov     r13, [rsp+0B8h+var_48]
0x18005b112  mov     rbx, [rbx]
0x18005b115  lea     rcx, [r13+2]
0x18005b119  call    DAF_user_alloc
0x18005b11e  mov     [rbx], rax
0x18005b121  mov     rbx, [rsp+0B8h+var_40]
0x18005b126  mov     rax, [rbx]
0x18005b129  cmp     qword ptr [rax], 0
0x18005b12d  jnz     short loc_18005B13C
0x18005b12f  mov     [rsp+0B8h+Reply], 8007000Eh
0x18005b137  jmp     loc_18005B30C
0x18005b13c  lea     r8, [r13+2]; Size
0x18005b140  mov     rdx, [rsp+0B8h+pObject]
0x18005b145  mov     rdx, [rdx]; Src
0x18005b148  mov     rcx, [rax]; void *
0x18005b14b  call    memcpy_0
0x18005b150  mov     rdx, [rsp+0B8h+pObject]
0x18005b155  mov     rdx, [rdx]; unsigned __int16 *
0x18005b158  mov     rcx, rsi; this
0x18005b15b  call    ?SetupAsyncOp@CImportExportContext@@IEAAJPEBG@Z; CImportExportContext::SetupAsyncOp(ushort const *)
0x18005b160  mov     [rsp+0B8h+Reply], eax
0x18005b164  test    eax, eax
0x18005b166  jns     short loc_18005B180
0x18005b168  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b16f  jz      loc_18005B30C
0x18005b175  mov     r9d, 21h ; '!'
0x18005b17b  jmp     loc_18005B2E6
0x18005b180  cmp     dword ptr [rsi+2Ch], 0
0x18005b184  jz      loc_18005B259
0x18005b18a  mov     r8, [rsp+0B8h+pObject]
0x18005b18f  mov     rdx, [r8+10h]
0x18005b193  lea     r10, [rsi+58h]
0x18005b197  lea     rax, [rbx+10h]
0x18005b19b  lea     rcx, [rbx+8]
0x18005b19f  lea     r9, [r10+8]
0x18005b1a3  mov     [rsp+0B8h+var_70], rax
0x18005b1a8  mov     [rsp+0B8h+var_78], rcx
0x18005b1ad  mov     rax, [rdx+8]
0x18005b1b1  mov     qword ptr [rsp+0B8h+var_80], rax
0x18005b1b6  mov     eax, [rdx]
0x18005b1b8  mov     dword ptr [rsp+0B8h+var_88], eax
0x18005b1bc  mov     rax, [r8]
0x18005b1bf  mov     qword ptr [rsp+0B8h+var_90], rax
0x18005b1c4  mov     [rsp+0B8h+MessageGuid], r10
0x18005b1c9  xor     r8d, r8d; pReturnValue
0x18005b1cc  lea     edx, [r8+1Eh]; nProcNum
0x18005b1d0  lea     rcx, stru_180083280; pProxyInfo
0x18005b1d7  call    cs:__imp_Ndr64AsyncClientCall
0x18005b1dd  jmp     loc_18005B30C
0x18005b1e2  cmp     eax, 1
0x18005b1e5  jl      short loc_18005B1EF
0x18005b1e7  movzx   eax, ax
0x18005b1ea  or      eax, 80010000h
0x18005b1ef  mov     [rsp+0B8h+Reply], eax
0x18005b1f3  lea     rcx, WPP_RECORDER_INITIALIZED
0x18005b1fa  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005b201  jz      short loc_18005B236
0x18005b203  mov     r9d, 22h ; '"'; int
0x18005b209  mov     dword ptr [rsp+0B8h+var_88], eax; char
0x18005b20d  mov     rax, [rsp+0B8h+pObject]
0x18005b212  mov     rcx, [rax]
0x18005b215  mov     qword ptr [rsp+0B8h+var_90], rcx; __int64
0x18005b21a  lea     rax, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005b221  mov     [rsp+0B8h+MessageGuid], rax; MessageGuid
0x18005b226  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b22d  mov     rcx, [rcx+28h]; int
0x18005b231  call    WPP_RECORDER_SF_Sd
0x18005b236  lea     r14, WPP_RECORDER_INITIALIZED
0x18005b23d  lea     r15, WPP_a3cdfe3099563ce25636ef842994cf43_Traceguids
0x18005b244  mov     rsi, [rsp+0B8h+arg_0]
0x18005b24c  mov     r12, [rsp+0B8h+var_38]
0x18005b254  jmp     loc_18005B30C
0x18005b259  lea     rdx, [rsp+0B8h+lpMem]
0x18005b25e  mov     rcx, [rsp+0B8h+pObject]
0x18005b263  mov     rcx, [rcx]
0x18005b266  call    DafGetProviderAepIdFromAepId
0x18005b26b  mov     [rsp+0B8h+Reply], eax
0x18005b26f  test    eax, eax
0x18005b271  jns     short loc_18005B288
0x18005b273  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b27a  jz      loc_18005B30C
0x18005b280  mov     r9d, 23h ; '#'
0x18005b286  jmp     short loc_18005B2E6
0x18005b288  mov     rcx, [rsi+60h]
0x18005b28c  mov     rax, [rcx]
0x18005b28f  lea     r8, [rsp+0B8h+var_50]
0x18005b294  lea     rdx, _GUID_0c512544_e485_46b6_b339_7a301e1e412d
0x18005b29b  mov     rax, [rax]
0x18005b29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b2a3  mov     [rsp+0B8h+Reply], eax
0x18005b2a7  test    eax, eax
0x18005b2a9  js      short loc_18005B30C
0x18005b2ab  mov     rcx, [rsi+58h]
0x18005b2af  mov     rax, [rsp+0B8h+pObject]
0x18005b2b4  mov     rdx, [rax+10h]
0x18005b2b8  mov     rax, [rcx]
0x18005b2bb  mov     r9, [rsp+0B8h+var_50]
0x18005b2c0  mov     r8, [rdx+8]
0x18005b2c4  mov     edx, [rdx]
0x18005b2c6  mov     rax, [rax+18h]
0x18005b2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b2cf  mov     [rsp+0B8h+Reply], eax
0x18005b2d3  test    eax, eax
0x18005b2d5  jns     short loc_18005B30C
0x18005b2d7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b2de  jz      short loc_18005B30C
0x18005b2e0  mov     r9d, 24h ; '$'; int
0x18005b2e6  mov     dword ptr [rsp+0B8h+var_88], eax; char
0x18005b2ea  mov     rax, [rsp+0B8h+pObject]
0x18005b2ef  mov     rcx, [rax]
0x18005b2f2  mov     qword ptr [rsp+0B8h+var_90], rcx; int
0x18005b2f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b2fe  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18005b303  mov     rcx, [rcx+28h]; int
0x18005b307  call    WPP_RECORDER_SF_Sd
0x18005b30c  mov     rcx, [rsp+0B8h+pObject]; this
0x18005b311  test    rcx, rcx
0x18005b314  jz      short loc_18005B31B
0x18005b316  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18005b31b  cmp     [rsp+0B8h+lpMem], 0
0x18005b321  jz      short loc_18005B339
0x18005b323  call    cs:__imp_GetProcessHeap
0x18005b329  mov     r8, [rsp+0B8h+lpMem]; lpMem
0x18005b32e  xor     edx, edx; dwFlags
0x18005b330  mov     rcx, rax; hHeap
0x18005b333  call    cs:__imp_HeapFree
0x18005b339  mov     rcx, [rsp+0B8h+var_50]
0x18005b33e  test    rcx, rcx
0x18005b341  jz      short loc_18005B34F
0x18005b343  mov     rax, [rcx]
0x18005b346  mov     rax, [rax+10h]
0x18005b34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b34f  cmp     [rsp+0B8h+Reply], 0
0x18005b354  jge     short loc_18005B3D4
0x18005b356  mov     rcx, r12; lpCriticalSection
0x18005b359  call    cs:__imp_EnterCriticalSection
0x18005b35f  mov     rax, [rsp+0B8h+var_30]
0x18005b367  cmp     dword ptr [rax], 0
0x18005b36a  jz      short loc_18005B39A
0x18005b36c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18005b373  jz      short loc_18005B3BA
0x18005b375  mov     r9d, 25h ; '%'; int
0x18005b37b  mov     eax, [rsp+0B8h+Reply]
0x18005b37f  mov     dword ptr [rsp+0B8h+var_90], eax; char
0x18005b383  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18005b388  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b38f  mov     rcx, [rcx+28h]; int
0x18005b393  call    WPP_RECORDER_SF_D
0x18005b398  jmp     short loc_18005B3BA
0x18005b39a  mov     rbx, [rsp+0B8h+var_40]
0x18005b39f  mov     rax, [rbx]
0x18005b3a2  cmp     qword ptr [rax], 0
0x18005b3a6  jz      short loc_18005B3BA
0x18005b3a8  mov     rcx, [rax]; this
0x18005b3ab  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18005b3b0  mov     rax, [rbx]
  ... truncated ...
```
