# InitializeQueryServices(void)

- ea: `0x18004a280`
- end: `0x18004a3de`
- name: `?InitializeQueryServices@@YAJXZ`
- size: `350`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180042f44`

## callees

- `0x180044c70`
- `0x18004a280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004a2c2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004a2c2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004a293`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004a2a0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004a293`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004a2a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a3cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a3cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a2ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a388`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a2ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a396`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a396`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a2fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a2fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a357`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004a3b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004a3b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004a345`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004a345`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18004a333`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18004a333`

## pseudocode

```c
__int64 InitializeQueryServices(void)
{
  signed int v0; // ebx
  HANDLE ProcessHeap; // rax
  signed int LastError; // eax
  PSLIST_HEADER v4; // rdi
  HANDLE v5; // rax

  v0 = 0;
  InitializeSRWLock(&g_srwQueryServicesStopping);
  InitializeSRWLock(&g_srwResourceRegistred);
  qword_1800A45A0 = (__int64)&lpMem;
  lpMem = &lpMem;
  InitializeCriticalSection(&ActiveQueriesList);
  g_bQueryServicesStopping = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
  {
    g_QueryWorkItemList = 0;
    g_QueryThreadpoolWork = 0;
    ProcessHeap = GetProcessHeap();
    g_QueryWorkItemList = (PSLIST_HEADER)HeapAlloc(ProcessHeap, 0, 0x10u);
  }
  g_bRmResourceRegistred = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
  {
    if ( !g_QueryWorkItemList )
      return 2147942414LL;
    InitializeSListHead(g_QueryWorkItemList);
    g_QueryThreadpoolWork = CreateThreadpoolWork(QueryWorkDispatchThreadProc, 0, 0);
    if ( !g_QueryThreadpoolWork )
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl)
    && v0 < 0 )
  {
    v4 = g_QueryWorkItemList;
    if ( g_QueryWorkItemList )
    {
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v4);
      g_QueryWorkItemList = 0;
    }
    if ( g_QueryThreadpoolWork )
    {
      CloseThreadpoolWork(g_QueryThreadpoolWork);
      g_QueryThreadpoolWork = 0;
    }
    DeleteCriticalSection(&ActiveQueriesList);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18004a280  mov     [rsp+arg_0], rbx
0x18004a285  push    rdi
0x18004a286  sub     rsp, 20h
0x18004a28a  xor     ebx, ebx
0x18004a28c  lea     rcx, ?g_srwQueryServicesStopping@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004a293  call    cs:__imp_InitializeSRWLock
0x18004a299  lea     rcx, ?g_srwResourceRegistred@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004a2a0  call    cs:__imp_InitializeSRWLock
0x18004a2a6  lea     rax, lpMem
0x18004a2ad  mov     cs:qword_1800A45A0, rax
0x18004a2b4  mov     cs:lpMem, rax
0x18004a2bb  lea     rcx, ?ActiveQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004a2c2  call    cs:__imp_InitializeCriticalSection
0x18004a2c8  mov     cs:?g_bQueryServicesStopping@@3HA, ebx; int g_bQueryServicesStopping
0x18004a2ce  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x18004a2d5  mov     rcx, rdi
0x18004a2d8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x18004a2dd  test    al, al
0x18004a2df  jnz     short loc_18004A30B
0x18004a2e1  mov     cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA, rbx; _SLIST_HEADER * g_QueryWorkItemList
0x18004a2e8  mov     cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA, rbx; _TP_WORK * g_QueryThreadpoolWork
0x18004a2ef  call    cs:__imp_GetProcessHeap
0x18004a2f5  mov     rcx, rax; hHeap
0x18004a2f8  xor     edx, edx; dwFlags
0x18004a2fa  lea     r8d, [rbx+10h]; dwBytes
0x18004a2fe  call    cs:__imp_HeapAlloc
0x18004a304  mov     cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA, rax; _SLIST_HEADER * g_QueryWorkItemList
0x18004a30b  mov     cs:?g_bRmResourceRegistred@@3JA, ebx; long g_bRmResourceRegistred
0x18004a311  mov     rcx, rdi
0x18004a314  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x18004a319  test    al, al
0x18004a31b  jnz     short loc_18004A36C
0x18004a31d  mov     rcx, cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18004a324  test    rcx, rcx
0x18004a327  jnz     short loc_18004A333
0x18004a329  mov     eax, 8007000Eh
0x18004a32e  jmp     loc_18004A3D3
0x18004a333  call    cs:__imp_InitializeSListHead
0x18004a339  xor     r8d, r8d; pcbe
0x18004a33c  xor     edx, edx; pv
0x18004a33e  lea     rcx, ?QueryWorkDispatchThreadProc@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18004a345  call    cs:__imp_CreateThreadpoolWork
0x18004a34b  mov     cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * g_QueryThreadpoolWork
0x18004a352  test    rax, rax
0x18004a355  jnz     short loc_18004A36C
0x18004a357  call    cs:__imp_GetLastError
0x18004a35d  mov     ebx, eax
0x18004a35f  test    eax, eax
0x18004a361  jle     short loc_18004A36C
0x18004a363  movzx   ebx, ax
0x18004a366  or      ebx, 80070000h
0x18004a36c  mov     rcx, rdi
0x18004a36f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x18004a374  test    al, al
0x18004a376  jnz     short loc_18004A3D1
0x18004a378  test    ebx, ebx
0x18004a37a  jns     short loc_18004A3D1
0x18004a37c  mov     rdi, cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * g_QueryWorkItemList
0x18004a383  test    rdi, rdi
0x18004a386  jz      short loc_18004A3A7
0x18004a388  call    cs:__imp_GetProcessHeap
0x18004a38e  mov     r8, rdi; lpMem
0x18004a391  xor     edx, edx; dwFlags
0x18004a393  mov     rcx, rax; hHeap
0x18004a396  call    cs:__imp_HeapFree
0x18004a39c  mov     cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA, 0; _SLIST_HEADER * g_QueryWorkItemList
0x18004a3a7  mov     rcx, cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA; pwk
0x18004a3ae  test    rcx, rcx
0x18004a3b1  jz      short loc_18004A3C4
0x18004a3b3  call    cs:__imp_CloseThreadpoolWork
0x18004a3b9  mov     cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * g_QueryThreadpoolWork
0x18004a3c4  lea     rcx, ?ActiveQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004a3cb  call    cs:__imp_DeleteCriticalSection
0x18004a3d1  mov     eax, ebx
0x18004a3d3  mov     rbx, [rsp+28h+arg_0]
0x18004a3d8  add     rsp, 20h
0x18004a3dc  pop     rdi
0x18004a3dd  retn
```
