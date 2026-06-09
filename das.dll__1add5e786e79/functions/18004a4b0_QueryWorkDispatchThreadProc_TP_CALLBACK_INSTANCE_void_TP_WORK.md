# QueryWorkDispatchThreadProc(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18004a4b0`
- end: `0x18004a56e`
- name: `?QueryWorkDispatchThreadProc@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `190`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180014594`
- `0x180015458`
- `0x1800272ec`
- `0x18002f4e0`
- `0x18003c79c`
- `0x180044c70`
- `0x18004a4b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a553`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a553`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a561`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a561`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004a4d0`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18004a4d0`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004a4dd`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004a4dd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004a4fb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18004a4fb`

## pseudocode

```c
void __fastcall QueryWorkDispatchThreadProc(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  PSLIST_ENTRY v4; // rax
  PSLIST_ENTRY v5; // rbx
  HANDLE ProcessHeap; // rax

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
  {
    CallbackMayRunLong(Instance);
    v4 = InterlockedPopEntrySList(g_QueryWorkItemList);
    v5 = v4;
    if ( v4 )
    {
      EventActivityIdControl(2u, (LPGUID)(*((_QWORD *)&v4[1].Next + 1) + 416LL));
      switch ( LODWORD(v5[1].Next) )
      {
        case 1:
          CQueryContext::InitiateQuery(*((PSRWLOCK *)&v5[1].Next + 1));
          break;
        case 2:
          CQueryContext::QueryAepStore(*((CQueryContext **)&v5[1].Next + 1));
          break;
        case 3:
          CQueryContext::OnQueryStateUpdateWork(
            LODWORD(v5[2].Next),
            HIDWORD(v5[2].Next),
            LODWORD(v5[3].Next),
            *((_QWORD *)&v5[2].Next + 1));
          break;
      }
      CQueryContext::Release(*((CQueryContext **)&v5[1].Next + 1));
      memset_0(v5, 0, 0x40u);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
  }
}

```

## disassembly

```asm
0x18004a4b0  push    rbx
0x18004a4b2  sub     rsp, 20h
0x18004a4b6  mov     rbx, rcx
0x18004a4b9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x18004a4c0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x18004a4c5  test    al, al
0x18004a4c7  jnz     loc_18004A568
0x18004a4cd  mov     rcx, rbx; pci
0x18004a4d0  call    cs:__imp_CallbackMayRunLong
0x18004a4d6  mov     rcx, cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18004a4dd  call    cs:__imp_InterlockedPopEntrySList
0x18004a4e3  mov     rbx, rax
0x18004a4e6  test    rax, rax
0x18004a4e9  jz      short loc_18004A568
0x18004a4eb  mov     rdx, [rax+18h]
0x18004a4ef  add     rdx, 1A0h; ActivityId
0x18004a4f6  mov     ecx, 2; ControlCode
0x18004a4fb  call    cs:__imp_EventActivityIdControl
0x18004a501  mov     eax, [rbx+10h]
0x18004a504  sub     eax, 1
0x18004a507  jz      short loc_18004A533
0x18004a509  sub     eax, 1
0x18004a50c  jz      short loc_18004A528
0x18004a50e  cmp     eax, 1
0x18004a511  jnz     short loc_18004A53C
0x18004a513  mov     r9, [rbx+28h]
0x18004a517  mov     r8d, [rbx+30h]
0x18004a51b  mov     edx, [rbx+24h]
0x18004a51e  mov     ecx, [rbx+20h]
0x18004a521  call    ?OnQueryStateUpdateWork@CQueryContext@@SAXW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@KPEAX@Z; CQueryContext::OnQueryStateUpdateWork(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,ulong,void *)
0x18004a526  jmp     short loc_18004A53C
0x18004a528  mov     rcx, [rbx+18h]; this
0x18004a52c  call    ?QueryAepStore@CQueryContext@@QEAAXXZ; CQueryContext::QueryAepStore(void)
0x18004a531  jmp     short loc_18004A53C
0x18004a533  mov     rcx, [rbx+18h]; SRWLock
0x18004a537  call    ?InitiateQuery@CQueryContext@@QEAAXXZ; CQueryContext::InitiateQuery(void)
0x18004a53c  mov     rcx, [rbx+18h]; this
0x18004a540  call    ?Release@CQueryContext@@QEAAKXZ; CQueryContext::Release(void)
0x18004a545  xor     edx, edx; Val
0x18004a547  lea     r8d, [rdx+40h]; Size
0x18004a54b  mov     rcx, rbx; void *
0x18004a54e  call    memset_0
0x18004a553  call    cs:__imp_GetProcessHeap
0x18004a559  mov     rcx, rax; hHeap
0x18004a55c  mov     r8, rbx; lpMem
0x18004a55f  xor     edx, edx; dwFlags
0x18004a561  call    cs:__imp_HeapFree
0x18004a567  nop
0x18004a568  add     rsp, 20h
0x18004a56c  pop     rbx
0x18004a56d  retn
```
