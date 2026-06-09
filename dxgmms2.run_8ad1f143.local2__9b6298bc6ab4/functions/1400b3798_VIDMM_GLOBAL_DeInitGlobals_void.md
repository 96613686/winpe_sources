# VIDMM_GLOBAL::DeInitGlobals(void)

- ea: `0x1400b3798`
- end: `0x1400b3953`
- name: `?DeInitGlobals@VIDMM_GLOBAL@@SAXXZ`
- size: `443`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400bacfc`

## callees

- `0x140030894`
- `0x140030ae0`
- `0x140047598`
- `0x1400479f8`
- `0x140058760`
- `0x1400b3798`
- `0x1400dba78`

## import_xrefs

- `ntoskrnl!PcwUnregister` at `0x1400b37b7`
- `ntoskrnl!PcwUnregister` at `0x1400b37d3`
- `ntoskrnl!PcwUnregister` at `0x1400b37ef`
- `ntoskrnl!PcwUnregister` at `0x1400b380b`
- `ntoskrnl!PcwUnregister` at `0x1400b37b7`
- `ntoskrnl!PcwUnregister` at `0x1400b37d3`
- `ntoskrnl!PcwUnregister` at `0x1400b37ef`
- `ntoskrnl!PcwUnregister` at `0x1400b380b`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400b3931`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400b3931`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400b384b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400b384b`

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

  if ( byte_1400869A2 )
    PcwUnregister(GpuPerformanceCounterSetProcessMemory);
  if ( byte_1400869A1 )
    PcwUnregister(GpuPerformanceCounterSetAdapterMemory);
  if ( byte_1400869A0 )
    PcwUnregister(GpuPerformanceCounterSetLocalAdapterMemory);
  if ( byte_140086298 )
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
  VIDMM_GLOBAL::DestroyDedicatedPartition();
}

```

## disassembly

```asm
0x1400b3798  mov     [rsp+arg_0], rbx
0x1400b379d  mov     [rsp+arg_8], rbp
0x1400b37a2  push    rdi
0x1400b37a3  sub     rsp, 20h
0x1400b37a7  cmp     cs:byte_1400869A2, 0
0x1400b37ae  jz      short loc_1400B37C3
0x1400b37b0  mov     rcx, cs:GpuPerformanceCounterSetProcessMemory; Registration
0x1400b37b7  call    cs:__imp_PcwUnregister
0x1400b37be  nop     dword ptr [rax+rax+00h]
0x1400b37c3  cmp     cs:byte_1400869A1, 0
0x1400b37ca  jz      short loc_1400B37DF
0x1400b37cc  mov     rcx, cs:GpuPerformanceCounterSetAdapterMemory; Registration
0x1400b37d3  call    cs:__imp_PcwUnregister
0x1400b37da  nop     dword ptr [rax+rax+00h]
0x1400b37df  cmp     cs:byte_1400869A0, 0
0x1400b37e6  jz      short loc_1400B37FB
0x1400b37e8  mov     rcx, cs:GpuPerformanceCounterSetLocalAdapterMemory; Registration
0x1400b37ef  call    cs:__imp_PcwUnregister
0x1400b37f6  nop     dword ptr [rax+rax+00h]
0x1400b37fb  cmp     cs:byte_140086298, 0
0x1400b3802  jz      short loc_1400B3817
0x1400b3804  mov     rcx, cs:GpuPerformanceCounterSetNonLocalAdapterMemory; Registration
0x1400b380b  call    cs:__imp_PcwUnregister
0x1400b3812  nop     dword ptr [rax+rax+00h]
0x1400b3817  mov     rcx, cs:?_pDxProcessPerAdapterCount@VIDMM_PROCESS@@2PEAJEA; void *
0x1400b381e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b3823  mov     rcx, cs:?_GlobalFenceStorage@VIDMM_PROCESS_FENCE_STORAGE@@0PEAV1@EA; this
0x1400b382a  test    rcx, rcx
0x1400b382d  jz      short loc_1400B3834
0x1400b382f  call    ??_GVIDMM_PROCESS_FENCE_STORAGE@@AEAAPEAXI@Z; VIDMM_PROCESS_FENCE_STORAGE::`scalar deleting destructor'(uint)
0x1400b3834  mov     rcx, cs:Resource; Resource
0x1400b383b  mov     cs:?_GlobalFenceStorage@VIDMM_PROCESS_FENCE_STORAGE@@0PEAV1@EA, 0; VIDMM_PROCESS_FENCE_STORAGE * VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage
0x1400b3846  test    rcx, rcx
0x1400b3849  jz      short loc_1400B386E
0x1400b384b  call    cs:__imp_ExDeleteResourceLite
0x1400b3852  nop     dword ptr [rax+rax+00h]
0x1400b3857  mov     rcx, cs:Resource; void *
0x1400b385e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b3863  mov     cs:Resource, 0
0x1400b386e  mov     rcx, cs:?g_ppSystemHeapPerNumaNode@@3PEAPEAVVIDMM_SYSTEM_HEAP@@EA; VIDMM_SYSTEM_HEAP * * g_ppSystemHeapPerNumaNode
0x1400b3875  mov     ebp, 1
0x1400b387a  test    rcx, rcx
0x1400b387d  jz      short loc_1400B38CF
0x1400b387f  xor     ebx, ebx
0x1400b3881  cmp     cs:?g_ppSystemHeapPerNumaNodeArraySize@@3KA, ebx; ulong g_ppSystemHeapPerNumaNodeArraySize
0x1400b3887  jz      short loc_1400B38BF
0x1400b3889  movzx   edi, bx
0x1400b388c  mov     rcx, [rcx+rdi*8]
0x1400b3890  test    rcx, rcx
0x1400b3893  jz      short loc_1400B38A2
0x1400b3895  mov     rax, [rcx]
0x1400b3898  mov     edx, ebp
0x1400b389a  mov     rax, [rax]
0x1400b389d  call    _guard_dispatch_icall
0x1400b38a2  mov     rcx, cs:?g_ppSystemHeapPerNumaNode@@3PEAPEAVVIDMM_SYSTEM_HEAP@@EA; void *
0x1400b38a9  add     bx, bp
0x1400b38ac  movzx   eax, bx
0x1400b38af  cmp     eax, cs:?g_ppSystemHeapPerNumaNodeArraySize@@3KA; ulong g_ppSystemHeapPerNumaNodeArraySize
0x1400b38b5  mov     qword ptr [rcx+rdi*8], 0
0x1400b38bd  jb      short loc_1400B3889
0x1400b38bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b38c4  mov     cs:?g_ppSystemHeapPerNumaNode@@3PEAPEAVVIDMM_SYSTEM_HEAP@@EA, 0; VIDMM_SYSTEM_HEAP * * g_ppSystemHeapPerNumaNode
0x1400b38cf  mov     rcx, cs:?g_pExistingSysMemHeap@@3PEAVVIDMM_EXISTINGSYSMEM_HEAP@@EA; VIDMM_EXISTINGSYSMEM_HEAP * g_pExistingSysMemHeap
0x1400b38d6  test    rcx, rcx
0x1400b38d9  jz      short loc_1400B38F3
0x1400b38db  mov     rax, [rcx]
0x1400b38de  mov     edx, ebp
0x1400b38e0  mov     rax, [rax]
0x1400b38e3  call    _guard_dispatch_icall
0x1400b38e8  mov     cs:?g_pExistingSysMemHeap@@3PEAVVIDMM_EXISTINGSYSMEM_HEAP@@EA, 0; VIDMM_EXISTINGSYSMEM_HEAP * g_pExistingSysMemHeap
0x1400b38f3  mov     rcx, qword ptr cs:?_RotationHistory@VIDMM_GLOBAL@@2U_VIDMM_ROTATION_HISTORY@@A; void *
0x1400b38fa  test    rcx, rcx
0x1400b38fd  jz      short loc_1400B390E
0x1400b38ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b3904  xorps   xmm0, xmm0
0x1400b3907  movups  cs:?_RotationHistory@VIDMM_GLOBAL@@2U_VIDMM_ROTATION_HISTORY@@A, xmm0; _VIDMM_ROTATION_HISTORY VIDMM_GLOBAL::_RotationHistory
0x1400b390e  call    TlgUnregisterAggregateProvider
0x1400b3913  lea     rcx, DxgkControlGuid_Context
0x1400b391a  call    McGenEventUnregister_EtwUnregister
0x1400b391f  mov     cs:DxgkControlGuid_Context, 0
0x1400b392a  lea     rcx, ?g_VaRangeLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1400b3931  call    cs:__imp_ExDeleteLookasideListEx
0x1400b3938  nop     dword ptr [rax+rax+00h]
0x1400b393d  call    ?DestroyDedicatedPartition@VIDMM_GLOBAL@@SAXXZ; VIDMM_GLOBAL::DestroyDedicatedPartition(void)
0x1400b3942  mov     rbx, [rsp+28h+arg_0]
0x1400b3947  mov     rbp, [rsp+28h+arg_8]
0x1400b394c  add     rsp, 20h
0x1400b3950  pop     rdi
0x1400b3951  retn
```
