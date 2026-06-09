# DestroyQueryServices(void)

- ea: `0x18004a114`
- end: `0x18004a277`
- name: `?DestroyQueryServices@@YAJXZ`
- size: `355`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180049410`

## callees

- `0x180015458`
- `0x180044c70`
- `0x18004a114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a1fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a1fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a1e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a1e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a1cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a1cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a24a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a24a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a257`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a257`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a1a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a22a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a1a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a22a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a180`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a1b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a238`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a180`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a1b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004a238`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004a156`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004a156`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004a149`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004a149`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004a18d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004a18d`

## pseudocode

```c
__int64 DestroyQueryServices(void)
{
  HANDLE ProcessHeap; // rax
  PSLIST_ENTRY v1; // rax
  PSLIST_ENTRY v2; // rbx
  PSLIST_HEADER v3; // rbx
  HANDLE v4; // rax
  LPVOID *v5; // rdi
  LPVOID *v6; // rcx
  LPVOID **v7; // rax
  LPVOID *v8; // rbx
  HANDLE v9; // rax

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
  {
    if ( g_QueryThreadpoolWork )
    {
      WaitForThreadpoolWorkCallbacks(g_QueryThreadpoolWork, 1);
      CloseThreadpoolWork(g_QueryThreadpoolWork);
      g_QueryThreadpoolWork = 0;
    }
    while ( 1 )
    {
      v1 = InterlockedPopEntrySList(g_QueryWorkItemList);
      v2 = v1;
      if ( !v1 )
        break;
      CQueryContext::Release(*((CQueryContext **)&v1[1].Next + 1));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    v3 = g_QueryWorkItemList;
    if ( g_QueryWorkItemList )
    {
      v4 = GetProcessHeap();
      HeapFree(v4, 0, v3);
      g_QueryWorkItemList = 0;
    }
  }
  EnterCriticalSection(&ActiveQueriesList);
  v5 = (LPVOID *)lpMem;
  while ( v5 != &lpMem )
  {
    AcquireSRWLockExclusive((PSRWLOCK)v5[2]);
    *((_DWORD *)v5[2] + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v5[2]);
    CQueryContext::Release((CQueryContext *)v5[2]);
    v6 = (LPVOID *)*v5;
    if ( *((LPVOID **)*v5 + 1) != v5 || (v7 = (LPVOID **)v5[1], *v7 != v5) )
      __fastfail(3u);
    v8 = v5;
    v5 = (LPVOID *)*v5;
    *v7 = v6;
    v6[1] = v7;
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  LeaveCriticalSection(&ActiveQueriesList);
  DeleteCriticalSection(&ActiveQueriesList);
  return 0;
}

```

## disassembly

```asm
0x18004a114  mov     [rsp+arg_0], rbx
0x18004a119  mov     [rsp+arg_8], rdi
0x18004a11e  push    r14
0x18004a120  sub     rsp, 20h
0x18004a124  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x18004a12b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x18004a130  test    al, al
0x18004a132  jnz     loc_18004A1C6
0x18004a138  mov     rcx, cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA; pwk
0x18004a13f  test    rcx, rcx
0x18004a142  jz      short loc_18004A186
0x18004a144  mov     edx, 1; fCancelPendingCallbacks
0x18004a149  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18004a14f  mov     rcx, cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA; pwk
0x18004a156  call    cs:__imp_CloseThreadpoolWork
0x18004a15c  mov     cs:?g_QueryThreadpoolWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * g_QueryThreadpoolWork
0x18004a167  jmp     short loc_18004A186
0x18004a169  mov     rcx, [rbx+18h]; this
0x18004a16d  call    ?Release@CQueryContext@@QEAAKXZ; CQueryContext::Release(void)
0x18004a172  call    cs:__imp_GetProcessHeap
0x18004a178  mov     rcx, rax; hHeap
0x18004a17b  mov     r8, rbx; lpMem
0x18004a17e  xor     edx, edx; dwFlags
0x18004a180  call    cs:__imp_HeapFree
0x18004a186  mov     rcx, cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18004a18d  call    cs:__imp_InterlockedPopEntrySList
0x18004a193  test    rax, rax
0x18004a196  mov     rbx, rax
0x18004a199  jnz     short loc_18004A169
0x18004a19b  mov     rbx, cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * g_QueryWorkItemList
0x18004a1a2  test    rbx, rbx
0x18004a1a5  jz      short loc_18004A1C6
0x18004a1a7  call    cs:__imp_GetProcessHeap
0x18004a1ad  mov     r8, rbx; lpMem
0x18004a1b0  xor     edx, edx; dwFlags
0x18004a1b2  mov     rcx, rax; hHeap
0x18004a1b5  call    cs:__imp_HeapFree
0x18004a1bb  mov     cs:?g_QueryWorkItemList@@3PEAT_SLIST_HEADER@@EA, 0; _SLIST_HEADER * g_QueryWorkItemList
0x18004a1c6  lea     rcx, ?ActiveQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004a1cd  call    cs:__imp_EnterCriticalSection
0x18004a1d3  mov     rdi, cs:lpMem
0x18004a1da  lea     r14, lpMem
0x18004a1e1  jmp     short loc_18004A23E
0x18004a1e3  mov     rcx, [rdi+10h]; SRWLock
0x18004a1e7  call    cs:__imp_AcquireSRWLockExclusive
0x18004a1ed  mov     rax, [rdi+10h]
0x18004a1f1  mov     dword ptr [rax+8], 0
0x18004a1f8  mov     rcx, [rdi+10h]; SRWLock
0x18004a1fc  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a202  mov     rcx, [rdi+10h]; this
0x18004a206  call    ?Release@CQueryContext@@QEAAKXZ; CQueryContext::Release(void)
0x18004a20b  mov     rcx, [rdi]
0x18004a20e  cmp     [rcx+8], rdi
0x18004a212  jnz     short loc_18004A270
0x18004a214  mov     rax, [rdi+8]
0x18004a218  cmp     [rax], rdi
0x18004a21b  jnz     short loc_18004A270
0x18004a21d  mov     rbx, rdi
0x18004a220  mov     rdi, rcx
0x18004a223  mov     [rax], rcx
0x18004a226  mov     [rcx+8], rax
0x18004a22a  call    cs:__imp_GetProcessHeap
0x18004a230  mov     rcx, rax; hHeap
0x18004a233  mov     r8, rbx; lpMem
0x18004a236  xor     edx, edx; dwFlags
0x18004a238  call    cs:__imp_HeapFree
0x18004a23e  cmp     rdi, r14
0x18004a241  jnz     short loc_18004A1E3
0x18004a243  lea     rcx, ?ActiveQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004a24a  call    cs:__imp_LeaveCriticalSection
0x18004a250  lea     rcx, ?ActiveQueriesList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004a257  call    cs:__imp_DeleteCriticalSection
0x18004a25d  xor     eax, eax
0x18004a25f  mov     rbx, [rsp+28h+arg_0]
0x18004a264  mov     rdi, [rsp+28h+arg_8]
0x18004a269  add     rsp, 20h
0x18004a26d  pop     r14
0x18004a26f  retn
0x18004a270  mov     ecx, 3
0x18004a275  int     29h; Win8: RtlFailFast(ecx)
```
