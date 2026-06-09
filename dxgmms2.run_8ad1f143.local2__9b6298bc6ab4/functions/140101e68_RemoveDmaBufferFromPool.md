# RemoveDmaBufferFromPool

- ea: `0x140101e68`
- end: `0x1401020c5`
- name: `RemoveDmaBufferFromPool`
- size: `605`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400ad02c`
- `0x1400bd010`
- `0x1400bd4f0`
- `0x140101b50`

## callees

- `0x140030ae0`
- `0x140031f84`
- `0x1400320d8`
- `0x14003e56c`
- `0x1400b4ff4`
- `0x1400df550`
- `0x1400e84b4`
- `0x140101e68`
- `0x140102390`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140101f16`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140101f16`
- `ntoskrnl!ExReleaseResourceLite` at `0x140101f4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140101f4a`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x140101fd6`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x140101fd6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140101e89`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140101e89`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x140101e77`

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
    v4 = WdLogNewEntry5_WdTrace(a1, a2);
    *(_QWORD *)(v4 + 24) = a2;
    *(_QWORD *)(v4 + 32) = a1;
    WdLogGlobalForLineNumber = 944;
  }
  if ( (byte_140086201 & 1) != 0 )
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
  _InterlockedAdd64(&qword_140086A48, -(__int64)a2[9]);
  _InterlockedAdd64(&qword_140086A18, -24LL * a2[10]);
  _InterlockedAdd64(&qword_1400869E8, -24LL * a2[11]);
  operator delete(a2);
}

```

## disassembly

```asm
0x140101e68  mov     [rsp+arg_0], rbx
0x140101e6d  mov     [rsp+arg_8], rsi
0x140101e72  push    rdi
0x140101e73  sub     rsp, 50h
0x140101e77  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x140101e7e  mov     rdi, rdx
0x140101e81  mov     rbx, rcx
0x140101e84  cmp     byte ptr [rax], 0
0x140101e87  jz      short loc_140101EA7
0x140101e89  call    cs:__imp_WdLogNewEntry5_WdTrace
0x140101e90  nop     dword ptr [rax+rax+00h]
0x140101e95  mov     [rax+18h], rdi
0x140101e99  mov     [rax+20h], rbx
0x140101e9d  mov     cs:WdLogGlobalForLineNumber, 3B0h
0x140101ea7  test    cs:byte_140086201, 1
0x140101eae  jz      short loc_140101EF3
0x140101eb0  mov     r9, [rbx]
0x140101eb3  mov     rax, [rdi+30h]
0x140101eb7  mov     edx, [rdi+28h]
0x140101eba  mov     ecx, [rdi+2Ch]
0x140101ebd  mov     r8d, [rdi+24h]
0x140101ec1  mov     [rsp+58h+var_10], rax
0x140101ec6  mov     rax, [r9+18h]
0x140101eca  mov     r9, [rbx+18h]
0x140101ece  mov     [rsp+58h+var_18], rcx
0x140101ed3  mov     [rsp+58h+var_20], rdx
0x140101ed8  lea     rdx, EventRemoveDmaBuffer
0x140101edf  mov     [rsp+58h+var_28], r8
0x140101ee4  mov     [rsp+58h+var_30], rdi
0x140101ee9  mov     qword ptr [rsp+58h+var_38], rax
0x140101eee  call    McTemplateK0pppxxxp_EtwWriteTransfer
0x140101ef3  cmp     byte ptr [rdi+18h], 0
0x140101ef7  jz      short loc_140101F0A
0x140101ef9  xor     r9d, r9d
0x140101efc  xor     r8d, r8d
0x140101eff  mov     rdx, rdi
0x140101f02  mov     rcx, rbx
0x140101f05  call    WaitDmaBufferNotBusy
0x140101f0a  mov     rcx, cs:Resource; Resource
0x140101f11  mov     dl, 1; Wait
0x140101f13  dec     dword ptr [rbx+54h]
0x140101f16  call    cs:__imp_ExAcquireResourceSharedLite
0x140101f1d  nop     dword ptr [rax+rax+00h]
0x140101f22  mov     rcx, [rdi]
0x140101f25  cmp     [rcx+8], rdi
0x140101f29  jnz     loc_1401020BE
0x140101f2f  mov     rax, [rdi+8]
0x140101f33  cmp     [rax], rdi
0x140101f36  jnz     loc_1401020BE
0x140101f3c  mov     [rax], rcx
0x140101f3f  mov     [rcx+8], rax
0x140101f43  mov     rcx, cs:Resource; Resource
0x140101f4a  call    cs:__imp_ExReleaseResourceLite
0x140101f51  nop     dword ptr [rax+rax+00h]
0x140101f56  mov     rcx, [rdi+78h]; void *
0x140101f5a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140101f5f  mov     rcx, [rdi+70h]; void *
0x140101f63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140101f68  mov     rcx, [rdi+68h]; void *
0x140101f6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140101f71  mov     rcx, [rdi+60h]; void *
0x140101f75  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140101f7a  cmp     dword ptr [rbx+28h], 0
0x140101f7e  jz      short loc_140101FCB
0x140101f80  mov     eax, [rbx+24h]
0x140101f83  test    al, 1
0x140101f85  jz      short loc_140101F93
0x140101f87  mov     rdx, [rdi+38h]; struct VIDMM_ALLOC *
0x140101f8b  mov     rcx, [rbx]; this
0x140101f8e  call    ?FreePagingBufferResources@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::FreePagingBufferResources(VIDMM_ALLOC *)
0x140101f93  mov     rdx, [rdi+38h]; struct VIDMM_ALLOC *
0x140101f97  xor     r9d, r9d; bool
0x140101f9a  mov     rcx, [rbx]; this
0x140101f9d  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x140101fa0  mov     [rsp+58h+var_30], 0; struct _KEVENT **
0x140101fa9  mov     dword ptr [rsp+58h+var_38], 1; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x140101fb1  call    ?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z; VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)
0x140101fb6  mov     r8, [rdi+30h]; struct VIDMM_GLOBAL_ALLOC *
0x140101fba  xor     r9d, r9d; bool
0x140101fbd  mov     rdx, [rbx+8]; struct VIDMM_DEVICE *
0x140101fc1  mov     rcx, [rbx]; this
0x140101fc4  call    ?DestroyOneAllocation@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_N@Z; VIDMM_GLOBAL::DestroyOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool)
0x140101fc9  jmp     short loc_140101FE2
0x140101fcb  mov     edx, [rdi+24h]; NumberOfBytes
0x140101fce  mov     r8d, [rdi+48h]; CacheType
0x140101fd2  mov     rcx, [rdi+40h]; BaseAddress
0x140101fd6  call    cs:__imp_MmFreeContiguousMemorySpecifyCache
0x140101fdd  nop     dword ptr [rax+rax+00h]
0x140101fe2  cmp     dword ptr [rbx+54h], 2
0x140101fe6  jnz     short loc_140102004
0x140101fe8  mov     eax, [rbx+30h]
0x140101feb  cmp     [rbx+2Ch], eax
0x140101fee  jnz     short loc_140102004
0x140101ff0  mov     eax, [rbx+3Ch]
0x140101ff3  cmp     [rbx+38h], eax
0x140101ff6  jnz     short loc_140102004
0x140101ff8  mov     eax, [rbx+48h]
0x140101ffb  cmp     [rbx+44h], eax
0x140101ffe  jnz     short loc_140102004
0x140102000  or      dword ptr [rbx+24h], 8
0x140102004  mov     eax, [rdi+24h]
0x140102007  sub     [rbx+78h], eax
0x14010200a  imul    eax, [rdi+28h], -18h
0x14010200e  mov     r8, [rbx+8]
0x140102012  add     [rbx+7Ch], eax
0x140102015  imul    eax, [rdi+2Ch], -18h
0x140102019  add     [rbx+80h], eax
0x14010201f  test    r8, r8
0x140102022  jz      short loc_140102079
0x140102024  mov     rax, [r8]
0x140102027  mov     rcx, [rax+18h]
0x14010202b  mov     rax, [r8+8]
0x14010202f  mov     edx, [rcx+0F0h]
0x140102035  mov     rcx, [rax+20h]
0x140102039  mov     rbx, [rcx+rdx*8]
0x14010203d  mov     rcx, rbx; this
0x140102040  call    ?AcquireProcessAdapterInfoLock@VIDMM_PROCESS_ADAPTER_INFO@@QEAAXXZ; VIDMM_PROCESS_ADAPTER_INFO::AcquireProcessAdapterInfoLock(void)
0x140102045  mov     rax, [rbx+0B8h]
0x14010204c  mov     rcx, rbx; this
0x14010204f  mov     edx, [rdi+24h]
0x140102052  dec     dword ptr [rax]
0x140102054  sub     [rax+8], rdx
0x140102058  imul    eax, [rdi+28h], -18h
0x14010205c  mov     rdx, [rbx+0B8h]
0x140102063  add     [rdx+10h], eax
0x140102066  imul    eax, [rdi+2Ch], -18h
0x14010206a  mov     rdx, [rbx+0B8h]
0x140102071  add     [rdx+14h], eax
0x140102074  call    ?ReleaseProcessAdapterInfoLock@VIDMM_PROCESS_ADAPTER_INFO@@QEAAXXZ; VIDMM_PROCESS_ADAPTER_INFO::ReleaseProcessAdapterInfoLock(void)
0x140102079  mov     eax, [rdi+24h]
0x14010207c  neg     rax
0x14010207f  lock add cs:qword_140086A48, rax
0x140102087  mov     eax, [rdi+28h]
0x14010208a  imul    rcx, rax, -18h
0x14010208e  lock add cs:qword_140086A18, rcx
0x140102096  mov     eax, [rdi+2Ch]
0x140102099  imul    rcx, rax, -18h
0x14010209d  lock add cs:qword_1400869E8, rcx
0x1401020a5  mov     rcx, rdi; void *
0x1401020a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1401020ad  mov     rbx, [rsp+58h+arg_0]
0x1401020b2  mov     rsi, [rsp+58h+arg_8]
0x1401020b7  add     rsp, 50h
0x1401020bb  pop     rdi
0x1401020bc  retn
0x1401020be  mov     ecx, 3
0x1401020c3  int     29h; Win8: RtlFailFast(ecx)
```
