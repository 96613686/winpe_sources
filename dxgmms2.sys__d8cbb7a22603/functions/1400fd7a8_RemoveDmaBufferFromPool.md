# RemoveDmaBufferFromPool

- ea: `0x1400fd7a8`
- end: `0x1400fda05`
- name: `RemoveDmaBufferFromPool`
- size: `605`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400ae4ec`
- `0x1400c0ac0`
- `0x1400c0fa0`
- `0x1400fd490`

## callees

- `0x14002e6c0`
- `0x14002fd50`
- `0x14002fe98`
- `0x14003cf34`
- `0x1400b899c`
- `0x1400e79b0`
- `0x1400fd7a8`
- `0x1400fdc1c`
- `0x1400feb90`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fd856`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fd856`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd88a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fd88a`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x1400fd916`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x1400fd916`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400fd7c9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400fd7c9`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400fd7b7`

## pseudocode

```c
void __fastcall RemoveDmaBufferFromPool(__int64 a1, unsigned int *a2)
{
  __int64 v4; // rax
  struct _ERESOURCE *v5; // rcx
  _QWORD *v6; // rcx
  void **v7; // rax
  _QWORD *v8; // r8
  VIDMM_PROCESS_ADAPTER_INFO *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx

  if ( g_IsInternalReleaseOrDbg )
  {
    v4 = WdLogNewEntry5_WdTrace(a1);
    *(_QWORD *)(v4 + 24) = a2;
    *(_QWORD *)(v4 + 32) = a1;
    WdLogGlobalForLineNumber = 945;
  }
  if ( (byte_140087201 & 1) != 0 )
    McTemplateK0pppxxxp_EtwWriteTransfer(
      a2[11],
      (unsigned int)EventRemoveDmaBuffer,
      a2[9],
      *(_QWORD *)(a1 + 24),
      *(_QWORD *)(*(_QWORD *)a1 + 24LL),
      (char)a2,
      a2[9],
      a2[10],
      a2[11],
      *((_QWORD *)a2 + 6));
  if ( *((_BYTE *)a2 + 24) )
    WaitDmaBufferNotBusy(a1, a2, 0, 0);
  v5 = Resource;
  --*(_DWORD *)(a1 + 84);
  ExAcquireResourceSharedLite(v5, 1u);
  v6 = *(_QWORD **)a2;
  if ( *(unsigned int **)(*(_QWORD *)a2 + 8LL) != a2 || (v7 = (void **)*((_QWORD *)a2 + 1), *v7 != a2) )
    __fastfail(3u);
  *v7 = v6;
  v6[1] = v7;
  ExReleaseResourceLite(Resource);
  operator delete(*((void **)a2 + 15));
  operator delete(*((void **)a2 + 14));
  operator delete(*((void **)a2 + 13));
  operator delete(*((void **)a2 + 12));
  if ( *(_DWORD *)(a1 + 40) )
  {
    if ( (*(_DWORD *)(a1 + 36) & 1) != 0 )
      VIDMM_GLOBAL::FreePagingBufferResources(*(VIDMM_GLOBAL **)a1, *((struct VIDMM_ALLOC **)a2 + 7));
    VIDMM_GLOBAL::CloseOneAllocation(
      *(VIDMM_GLOBAL **)a1,
      *((__int64 ***)a2 + 7),
      0,
      0,
      (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1,
      0);
    VIDMM_GLOBAL::DestroyOneAllocation(
      *(VIDMM_GLOBAL **)a1,
      *(struct VIDMM_DEVICE **)(a1 + 8),
      *((struct VIDMM_GLOBAL_ALLOC **)a2 + 6),
      0);
  }
  else
  {
    MmFreeContiguousMemorySpecifyCache(*((PVOID *)a2 + 8), a2[9], (MEMORY_CACHING_TYPE)a2[18]);
  }
  if ( *(_DWORD *)(a1 + 84) == 2
    && *(_DWORD *)(a1 + 44) == *(_DWORD *)(a1 + 48)
    && *(_DWORD *)(a1 + 56) == *(_DWORD *)(a1 + 60)
    && *(_DWORD *)(a1 + 68) == *(_DWORD *)(a1 + 72) )
  {
    *(_DWORD *)(a1 + 36) |= 8u;
  }
  *(_DWORD *)(a1 + 120) -= a2[9];
  v8 = *(_QWORD **)(a1 + 8);
  *(_DWORD *)(a1 + 124) += -24 * a2[10];
  *(_DWORD *)(a1 + 128) += -24 * a2[11];
  if ( v8 )
  {
    v9 = *(VIDMM_PROCESS_ADAPTER_INFO **)(*(_QWORD *)(v8[1] + 32LL)
                                        + 8LL * *(unsigned int *)(*(_QWORD *)(*v8 + 24LL) + 240LL));
    VIDMM_PROCESS_ADAPTER_INFO::AcquireProcessAdapterInfoLock(v9);
    v10 = *((_QWORD *)v9 + 23);
    v11 = a2[9];
    --*(_DWORD *)v10;
    *(_QWORD *)(v10 + 8) -= v11;
    *(_DWORD *)(*((_QWORD *)v9 + 23) + 16LL) += -24 * a2[10];
    *(_DWORD *)(*((_QWORD *)v9 + 23) + 20LL) += -24 * a2[11];
    VIDMM_PROCESS_ADAPTER_INFO::ReleaseProcessAdapterInfoLock(v9);
  }
  _InterlockedAdd64(&qword_140087A38, -(__int64)a2[9]);
  _InterlockedAdd64(&qword_140087A08, -24LL * a2[10]);
  _InterlockedAdd64(&qword_1400879D8, -24LL * a2[11]);
  operator delete(a2);
}

```

## disassembly

```asm
0x1400fd7a8  mov     [rsp+arg_0], rbx
0x1400fd7ad  mov     [rsp+arg_8], rsi
0x1400fd7b2  push    rdi
0x1400fd7b3  sub     rsp, 50h
0x1400fd7b7  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400fd7be  mov     rdi, rdx
0x1400fd7c1  mov     rbx, rcx
0x1400fd7c4  cmp     byte ptr [rax], 0
0x1400fd7c7  jz      short loc_1400FD7E7
0x1400fd7c9  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400fd7d0  nop     dword ptr [rax+rax+00h]
0x1400fd7d5  mov     [rax+18h], rdi
0x1400fd7d9  mov     [rax+20h], rbx
0x1400fd7dd  mov     cs:WdLogGlobalForLineNumber, 3B1h
0x1400fd7e7  test    cs:byte_140087201, 1
0x1400fd7ee  jz      short loc_1400FD833
0x1400fd7f0  mov     r9, [rbx]
0x1400fd7f3  mov     rax, [rdi+30h]
0x1400fd7f7  mov     edx, [rdi+28h]
0x1400fd7fa  mov     ecx, [rdi+2Ch]
0x1400fd7fd  mov     r8d, [rdi+24h]
0x1400fd801  mov     [rsp+58h+var_10], rax
0x1400fd806  mov     rax, [r9+18h]
0x1400fd80a  mov     r9, [rbx+18h]
0x1400fd80e  mov     [rsp+58h+var_18], rcx
0x1400fd813  mov     [rsp+58h+var_20], rdx
0x1400fd818  lea     rdx, EventRemoveDmaBuffer
0x1400fd81f  mov     [rsp+58h+var_28], r8
0x1400fd824  mov     [rsp+58h+var_30], rdi
0x1400fd829  mov     qword ptr [rsp+58h+var_38], rax
0x1400fd82e  call    McTemplateK0pppxxxp_EtwWriteTransfer
0x1400fd833  cmp     byte ptr [rdi+18h], 0
0x1400fd837  jz      short loc_1400FD84A
0x1400fd839  xor     r9d, r9d
0x1400fd83c  xor     r8d, r8d
0x1400fd83f  mov     rdx, rdi
0x1400fd842  mov     rcx, rbx
0x1400fd845  call    WaitDmaBufferNotBusy
0x1400fd84a  mov     rcx, cs:Resource; Resource
0x1400fd851  mov     dl, 1; Wait
0x1400fd853  dec     dword ptr [rbx+54h]
0x1400fd856  call    cs:__imp_ExAcquireResourceSharedLite
0x1400fd85d  nop     dword ptr [rax+rax+00h]
0x1400fd862  mov     rcx, [rdi]
0x1400fd865  cmp     [rcx+8], rdi
0x1400fd869  jnz     loc_1400FD9FE
0x1400fd86f  mov     rax, [rdi+8]
0x1400fd873  cmp     [rax], rdi
0x1400fd876  jnz     loc_1400FD9FE
0x1400fd87c  mov     [rax], rcx
0x1400fd87f  mov     [rcx+8], rax
0x1400fd883  mov     rcx, cs:Resource; Resource
0x1400fd88a  call    cs:__imp_ExReleaseResourceLite
0x1400fd891  nop     dword ptr [rax+rax+00h]
0x1400fd896  mov     rcx, [rdi+78h]; void *
0x1400fd89a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400fd89f  mov     rcx, [rdi+70h]; void *
0x1400fd8a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400fd8a8  mov     rcx, [rdi+68h]; void *
0x1400fd8ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400fd8b1  mov     rcx, [rdi+60h]; void *
0x1400fd8b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400fd8ba  cmp     dword ptr [rbx+28h], 0
0x1400fd8be  jz      short loc_1400FD90B
0x1400fd8c0  mov     eax, [rbx+24h]
0x1400fd8c3  test    al, 1
0x1400fd8c5  jz      short loc_1400FD8D3
0x1400fd8c7  mov     rdx, [rdi+38h]; struct VIDMM_ALLOC *
0x1400fd8cb  mov     rcx, [rbx]; this
0x1400fd8ce  call    ?FreePagingBufferResources@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::FreePagingBufferResources(VIDMM_ALLOC *)
0x1400fd8d3  mov     rdx, [rdi+38h]; struct VIDMM_ALLOC *
0x1400fd8d7  xor     r9d, r9d; bool
0x1400fd8da  mov     rcx, [rbx]; this
0x1400fd8dd  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x1400fd8e0  mov     [rsp+58h+var_30], 0; struct _KEVENT **
0x1400fd8e9  mov     dword ptr [rsp+58h+var_38], 1; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1400fd8f1  call    ?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z; VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)
0x1400fd8f6  mov     r8, [rdi+30h]; struct VIDMM_GLOBAL_ALLOC *
0x1400fd8fa  xor     r9d, r9d; bool
0x1400fd8fd  mov     rdx, [rbx+8]; struct VIDMM_DEVICE *
0x1400fd901  mov     rcx, [rbx]; this
0x1400fd904  call    ?DestroyOneAllocation@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_N@Z; VIDMM_GLOBAL::DestroyOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool)
0x1400fd909  jmp     short loc_1400FD922
0x1400fd90b  mov     edx, [rdi+24h]; NumberOfBytes
0x1400fd90e  mov     r8d, [rdi+48h]; CacheType
0x1400fd912  mov     rcx, [rdi+40h]; BaseAddress
0x1400fd916  call    cs:__imp_MmFreeContiguousMemorySpecifyCache
0x1400fd91d  nop     dword ptr [rax+rax+00h]
0x1400fd922  cmp     dword ptr [rbx+54h], 2
0x1400fd926  jnz     short loc_1400FD944
0x1400fd928  mov     eax, [rbx+30h]
0x1400fd92b  cmp     [rbx+2Ch], eax
0x1400fd92e  jnz     short loc_1400FD944
0x1400fd930  mov     eax, [rbx+3Ch]
0x1400fd933  cmp     [rbx+38h], eax
0x1400fd936  jnz     short loc_1400FD944
0x1400fd938  mov     eax, [rbx+48h]
0x1400fd93b  cmp     [rbx+44h], eax
0x1400fd93e  jnz     short loc_1400FD944
0x1400fd940  or      dword ptr [rbx+24h], 8
0x1400fd944  mov     eax, [rdi+24h]
0x1400fd947  sub     [rbx+78h], eax
0x1400fd94a  imul    eax, [rdi+28h], -18h
0x1400fd94e  mov     r8, [rbx+8]
0x1400fd952  add     [rbx+7Ch], eax
0x1400fd955  imul    eax, [rdi+2Ch], -18h
0x1400fd959  add     [rbx+80h], eax
0x1400fd95f  test    r8, r8
0x1400fd962  jz      short loc_1400FD9B9
0x1400fd964  mov     rax, [r8]
0x1400fd967  mov     rcx, [rax+18h]
0x1400fd96b  mov     rax, [r8+8]
0x1400fd96f  mov     edx, [rcx+0F0h]
0x1400fd975  mov     rcx, [rax+20h]
0x1400fd979  mov     rbx, [rcx+rdx*8]
0x1400fd97d  mov     rcx, rbx; this
0x1400fd980  call    ?AcquireProcessAdapterInfoLock@VIDMM_PROCESS_ADAPTER_INFO@@QEAAXXZ; VIDMM_PROCESS_ADAPTER_INFO::AcquireProcessAdapterInfoLock(void)
0x1400fd985  mov     rax, [rbx+0B8h]
0x1400fd98c  mov     rcx, rbx; this
0x1400fd98f  mov     edx, [rdi+24h]
0x1400fd992  dec     dword ptr [rax]
0x1400fd994  sub     [rax+8], rdx
0x1400fd998  imul    eax, [rdi+28h], -18h
0x1400fd99c  mov     rdx, [rbx+0B8h]
0x1400fd9a3  add     [rdx+10h], eax
0x1400fd9a6  imul    eax, [rdi+2Ch], -18h
0x1400fd9aa  mov     rdx, [rbx+0B8h]
0x1400fd9b1  add     [rdx+14h], eax
0x1400fd9b4  call    ?ReleaseProcessAdapterInfoLock@VIDMM_PROCESS_ADAPTER_INFO@@QEAAXXZ; VIDMM_PROCESS_ADAPTER_INFO::ReleaseProcessAdapterInfoLock(void)
0x1400fd9b9  mov     eax, [rdi+24h]
0x1400fd9bc  neg     rax
0x1400fd9bf  lock add cs:qword_140087A38, rax
0x1400fd9c7  mov     eax, [rdi+28h]
0x1400fd9ca  imul    rcx, rax, -18h
0x1400fd9ce  lock add cs:qword_140087A08, rcx
0x1400fd9d6  mov     eax, [rdi+2Ch]
0x1400fd9d9  imul    rcx, rax, -18h
0x1400fd9dd  lock add cs:qword_1400879D8, rcx
0x1400fd9e5  mov     rcx, rdi; void *
0x1400fd9e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400fd9ed  mov     rbx, [rsp+58h+arg_0]
0x1400fd9f2  mov     rsi, [rsp+58h+arg_8]
0x1400fd9f7  add     rsp, 50h
0x1400fd9fb  pop     rdi
0x1400fd9fc  retn
0x1400fd9fe  mov     ecx, 3
0x1400fda03  int     29h; Win8: RtlFailFast(ecx)
```
