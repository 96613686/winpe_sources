# VIDMM_GLOBAL::DeInitGlobals(void)

- ea: `0x1400b7068`
- end: `0x1400b721c`
- name: `?DeInitGlobals@VIDMM_GLOBAL@@SAXXZ`
- size: `436`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400be79c`

## callees

- `0x14002e47c`
- `0x14002e6c0`
- `0x140047bd0`
- `0x140059030`
- `0x1400b7068`
- `0x1400c9c8c`
- `0x1400e3ed8`

## import_xrefs

- `ntoskrnl!PcwUnregister` at `0x1400b7083`
- `ntoskrnl!PcwUnregister` at `0x1400b709f`
- `ntoskrnl!PcwUnregister` at `0x1400b70bb`
- `ntoskrnl!PcwUnregister` at `0x1400b70d7`
- `ntoskrnl!PcwUnregister` at `0x1400b7083`
- `ntoskrnl!PcwUnregister` at `0x1400b709f`
- `ntoskrnl!PcwUnregister` at `0x1400b70bb`
- `ntoskrnl!PcwUnregister` at `0x1400b70d7`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400b71e5`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400b71e5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400b7113`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400b7113`

## pseudocode

```c
void VIDMM_GLOBAL::DeInitGlobals(void)
{
  unsigned int v0; // edx
  _QWORD *v1; // rcx
  unsigned __int16 v2; // bx
  __int64 v3; // rdi
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  bool v5; // cf

  if ( byte_1400879AB )
    PcwUnregister(GpuPerformanceCounterSetProcessMemory);
  if ( byte_1400879AA )
    PcwUnregister(GpuPerformanceCounterSetAdapterMemory);
  if ( byte_1400879A9 )
    PcwUnregister(GpuPerformanceCounterSetLocalAdapterMemory);
  if ( byte_1400879A8 )
    PcwUnregister(GpuPerformanceCounterSetNonLocalAdapterMemory);
  operator delete(VIDMM_PROCESS::_pDxProcessPerAdapterCount);
  if ( VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage )
    VIDMM_PROCESS_FENCE_STORAGE::`scalar deleting destructor'(VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage, v0);
  VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage = 0;
  if ( Resource )
  {
    ExDeleteResourceLite(Resource);
    operator delete(Resource);
    Resource = 0;
  }
  v1 = g_ppSystemHeapPerNumaNode;
  if ( g_ppSystemHeapPerNumaNode )
  {
    v2 = 0;
    if ( g_ppSystemHeapPerNumaNodeArraySize )
    {
      do
      {
        v3 = v2;
        v4 = (void (__fastcall ***)(_QWORD, __int64))v1[v2];
        if ( v4 )
          (**v4)(v4, 1);
        v1 = g_ppSystemHeapPerNumaNode;
        v5 = ++v2 < g_ppSystemHeapPerNumaNodeArraySize;
        *((_QWORD *)g_ppSystemHeapPerNumaNode + v3) = 0;
      }
      while ( v5 );
    }
    operator delete(v1);
    g_ppSystemHeapPerNumaNode = 0;
  }
  if ( g_pExistingSysMemHeap )
  {
    (**(void (__fastcall ***)(struct VIDMM_EXISTINGSYSMEM_HEAP *, __int64))g_pExistingSysMemHeap)(
      g_pExistingSysMemHeap,
      1);
    g_pExistingSysMemHeap = 0;
  }
  if ( VIDMM_GLOBAL::_RotationHistory )
  {
    operator delete(VIDMM_GLOBAL::_RotationHistory);
    *(_OWORD *)&VIDMM_GLOBAL::_RotationHistory = 0;
  }
  TlgUnregisterAggregateProvider();
  McGenEventUnregister_EtwUnregister(&DxgkControlGuid_Context);
  DxgkControlGuid_Context = 0;
  ExDeleteLookasideListEx(&g_VaRangeLookasideList);
  if ( g_Feature_ResourcePoolManagement )
  {
    if ( g_pSystemResourcePool )
    {
      VidMmDereferenceResourcePool(g_pSystemResourcePool);
      g_pSystemResourcePool = 0;
    }
  }
}

```

## disassembly

```asm
0x1400b7068  push    rbx
0x1400b706a  push    rbp
0x1400b706b  push    rsi
0x1400b706c  push    rdi
0x1400b706d  sub     rsp, 28h
0x1400b7071  xor     esi, esi
0x1400b7073  cmp     cs:byte_1400879AB, sil
0x1400b707a  jz      short loc_1400B708F
0x1400b707c  mov     rcx, cs:GpuPerformanceCounterSetProcessMemory; Registration
0x1400b7083  call    cs:__imp_PcwUnregister
0x1400b708a  nop     dword ptr [rax+rax+00h]
0x1400b708f  cmp     cs:byte_1400879AA, sil
0x1400b7096  jz      short loc_1400B70AB
0x1400b7098  mov     rcx, cs:GpuPerformanceCounterSetAdapterMemory; Registration
0x1400b709f  call    cs:__imp_PcwUnregister
0x1400b70a6  nop     dword ptr [rax+rax+00h]
0x1400b70ab  cmp     cs:byte_1400879A9, sil
0x1400b70b2  jz      short loc_1400B70C7
0x1400b70b4  mov     rcx, cs:GpuPerformanceCounterSetLocalAdapterMemory; Registration
0x1400b70bb  call    cs:__imp_PcwUnregister
0x1400b70c2  nop     dword ptr [rax+rax+00h]
0x1400b70c7  cmp     cs:byte_1400879A8, sil
0x1400b70ce  jz      short loc_1400B70E3
0x1400b70d0  mov     rcx, cs:GpuPerformanceCounterSetNonLocalAdapterMemory; Registration
0x1400b70d7  call    cs:__imp_PcwUnregister
0x1400b70de  nop     dword ptr [rax+rax+00h]
0x1400b70e3  mov     rcx, cs:?_pDxProcessPerAdapterCount@VIDMM_PROCESS@@2PEAJEA; void *
0x1400b70ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b70ef  mov     rcx, cs:?_GlobalFenceStorage@VIDMM_PROCESS_FENCE_STORAGE@@0PEAV1@EA; this
0x1400b70f6  test    rcx, rcx
0x1400b70f9  jz      short loc_1400B7100
0x1400b70fb  call    ??_GVIDMM_PROCESS_FENCE_STORAGE@@AEAAPEAXI@Z; VIDMM_PROCESS_FENCE_STORAGE::`scalar deleting destructor'(uint)
0x1400b7100  mov     rcx, cs:Resource; Resource
0x1400b7107  mov     cs:?_GlobalFenceStorage@VIDMM_PROCESS_FENCE_STORAGE@@0PEAV1@EA, rsi; VIDMM_PROCESS_FENCE_STORAGE * VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage
0x1400b710e  test    rcx, rcx
0x1400b7111  jz      short loc_1400B7132
0x1400b7113  call    cs:__imp_ExDeleteResourceLite
0x1400b711a  nop     dword ptr [rax+rax+00h]
0x1400b711f  mov     rcx, cs:Resource; void *
0x1400b7126  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b712b  mov     cs:Resource, rsi
0x1400b7132  mov     rcx, cs:?g_ppSystemHeapPerNumaNode@@3PEAPEAVVIDMM_SYSTEM_HEAP@@EA; VIDMM_SYSTEM_HEAP * * g_ppSystemHeapPerNumaNode
0x1400b7139  mov     ebp, 1
0x1400b713e  test    rcx, rcx
0x1400b7141  jz      short loc_1400B718B
0x1400b7143  mov     ebx, esi
0x1400b7145  cmp     cs:?g_ppSystemHeapPerNumaNodeArraySize@@3KA, ebx; ulong g_ppSystemHeapPerNumaNodeArraySize
0x1400b714b  jz      short loc_1400B717F
0x1400b714d  movzx   edi, bx
0x1400b7150  mov     rcx, [rcx+rdi*8]
0x1400b7154  test    rcx, rcx
0x1400b7157  jz      short loc_1400B7166
0x1400b7159  mov     rax, [rcx]
0x1400b715c  mov     edx, ebp
0x1400b715e  mov     rax, [rax]
0x1400b7161  call    _guard_dispatch_icall
0x1400b7166  mov     rcx, cs:?g_ppSystemHeapPerNumaNode@@3PEAPEAVVIDMM_SYSTEM_HEAP@@EA; void *
0x1400b716d  add     bx, bp
0x1400b7170  movzx   eax, bx
0x1400b7173  cmp     eax, cs:?g_ppSystemHeapPerNumaNodeArraySize@@3KA; ulong g_ppSystemHeapPerNumaNodeArraySize
0x1400b7179  mov     [rcx+rdi*8], rsi
0x1400b717d  jb      short loc_1400B714D
0x1400b717f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b7184  mov     cs:?g_ppSystemHeapPerNumaNode@@3PEAPEAVVIDMM_SYSTEM_HEAP@@EA, rsi; VIDMM_SYSTEM_HEAP * * g_ppSystemHeapPerNumaNode
0x1400b718b  mov     rcx, cs:?g_pExistingSysMemHeap@@3PEAVVIDMM_EXISTINGSYSMEM_HEAP@@EA; VIDMM_EXISTINGSYSMEM_HEAP * g_pExistingSysMemHeap
0x1400b7192  test    rcx, rcx
0x1400b7195  jz      short loc_1400B71AB
0x1400b7197  mov     rax, [rcx]
0x1400b719a  mov     edx, ebp
0x1400b719c  mov     rax, [rax]
0x1400b719f  call    _guard_dispatch_icall
0x1400b71a4  mov     cs:?g_pExistingSysMemHeap@@3PEAVVIDMM_EXISTINGSYSMEM_HEAP@@EA, rsi; VIDMM_EXISTINGSYSMEM_HEAP * g_pExistingSysMemHeap
0x1400b71ab  mov     rcx, qword ptr cs:?_RotationHistory@VIDMM_GLOBAL@@2U_VIDMM_ROTATION_HISTORY@@A; void *
0x1400b71b2  test    rcx, rcx
0x1400b71b5  jz      short loc_1400B71C6
0x1400b71b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b71bc  xorps   xmm0, xmm0
0x1400b71bf  movups  cs:?_RotationHistory@VIDMM_GLOBAL@@2U_VIDMM_ROTATION_HISTORY@@A, xmm0; _VIDMM_ROTATION_HISTORY VIDMM_GLOBAL::_RotationHistory
0x1400b71c6  call    TlgUnregisterAggregateProvider
0x1400b71cb  lea     rcx, DxgkControlGuid_Context
0x1400b71d2  call    McGenEventUnregister_EtwUnregister
0x1400b71d7  mov     cs:DxgkControlGuid_Context, rsi
0x1400b71de  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1400b71e5  call    cs:__imp_ExDeleteLookasideListEx
0x1400b71ec  nop     dword ptr [rax+rax+00h]
0x1400b71f1  cmp     cs:?g_Feature_ResourcePoolManagement@@3_NA, sil; bool g_Feature_ResourcePoolManagement
0x1400b71f8  jz      short loc_1400B7212
0x1400b71fa  mov     rcx, cs:?g_pSystemResourcePool@@3PEAUVIDMM_RESOURCE_POOL@@EA; this
0x1400b7201  test    rcx, rcx
0x1400b7204  jz      short loc_1400B7212
0x1400b7206  call    ?VidMmDereferenceResourcePool@@YAXPEBUVIDMM_RESOURCE_POOL@@@Z; VidMmDereferenceResourcePool(VIDMM_RESOURCE_POOL const *)
0x1400b720b  mov     cs:?g_pSystemResourcePool@@3PEAUVIDMM_RESOURCE_POOL@@EA, rsi; VIDMM_RESOURCE_POOL * g_pSystemResourcePool
0x1400b7212  add     rsp, 28h
0x1400b7216  pop     rdi
0x1400b7217  pop     rsi
0x1400b7218  pop     rbp
0x1400b7219  pop     rbx
0x1400b721a  retn
```
