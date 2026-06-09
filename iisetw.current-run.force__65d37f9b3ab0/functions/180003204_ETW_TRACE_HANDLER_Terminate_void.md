# ETW_TRACE_HANDLER::Terminate(void)

- ea: `0x180003204`
- end: `0x1800032cc`
- name: `?Terminate@ETW_TRACE_HANDLER@@SAXXZ`
- size: `200`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180002c20`
- `0x1800031e0`

## callees

- `0x180001048`
- `0x180003204`
- `0x180004010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003263`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003263`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003296`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180003296`
- `iisutil!?UnRegister@CEtwTracer@@QEAAKXZ` at `0x180003227`
- `iisutil!?UnRegister@CEtwTracer@@QEAAKXZ` at `0x180003227`
- `iisutil!??1CEtwTracer@@QEAA@XZ` at `0x180003236`
- `iisutil!??1CEtwTracer@@QEAA@XZ` at `0x180003236`

## pseudocode

```c
void ETW_TRACE_HANDLER::Terminate(void)
{
  void **v0; // rbx
  void **v1; // rdi
  void **v2; // rbx
  REGHANDLE v3; // rcx
  void **v4; // rdi

  v0 = (void **)ETW_TRACE_HANDLER::sm_EtwProviderListHead;
  while ( v0 != &ETW_TRACE_HANDLER::sm_EtwProviderListHead )
  {
    v1 = v0;
    v0 = (void **)*v0;
    CEtwTracer::UnRegister((CEtwTracer *)(v1 + 2));
    if ( v1 )
    {
      CEtwTracer::~CEtwTracer((CEtwTracer *)(v1 + 2));
      operator delete(v1);
    }
  }
  v2 = (void **)ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead;
  while ( v2 != &ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead )
  {
    v3 = (REGHANDLE)v2[8];
    v4 = v2;
    v2 = (void **)*v2;
    EventUnregister(v3);
    if ( v4 )
    {
      v4[2] = &CCustomEtwTracerV2::`vftable';
      operator delete(v4);
    }
  }
  if ( ETW_TRACE_HANDLER::sm_pHttpTracingTable )
  {
    CLKRHashTable::Clear((struct HTTP_TRACING_TABLE *)((char *)ETW_TRACE_HANDLER::sm_pHttpTracingTable + 8));
    if ( ETW_TRACE_HANDLER::sm_pHttpTracingTable )
      (**(void (__fastcall ***)(struct HTTP_TRACING_TABLE *, __int64))ETW_TRACE_HANDLER::sm_pHttpTracingTable)(
        ETW_TRACE_HANDLER::sm_pHttpTracingTable,
        1);
    ETW_TRACE_HANDLER::sm_pHttpTracingTable = 0;
  }
}

```

## disassembly

```asm
0x180003204  push    rbx
0x180003206  push    rbp
0x180003207  push    rsi
0x180003208  push    rdi
0x180003209  sub     rsp, 28h
0x18000320d  mov     rbx, cs:?sm_EtwProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwProviderListHead
0x180003214  lea     rbp, ?sm_EtwProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwProviderListHead
0x18000321b  jmp     short loc_180003244
0x18000321d  mov     rdi, rbx
0x180003220  mov     rbx, [rbx]
0x180003223  lea     rcx, [rdi+10h]
0x180003227  call    cs:__imp_?UnRegister@CEtwTracer@@QEAAKXZ; CEtwTracer::UnRegister(void)
0x18000322d  test    rdi, rdi
0x180003230  jz      short loc_180003244
0x180003232  lea     rcx, [rdi+10h]
0x180003236  call    cs:__imp_??1CEtwTracer@@QEAA@XZ; CEtwTracer::~CEtwTracer(void)
0x18000323c  mov     rcx, rdi; Block
0x18000323f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003244  cmp     rbx, rbp
0x180003247  jnz     short loc_18000321D
0x180003249  mov     rbx, cs:?sm_EtwV2ProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead
0x180003250  lea     rsi, ?sm_EtwV2ProviderListHead@ETW_TRACE_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY ETW_TRACE_HANDLER::sm_EtwV2ProviderListHead
0x180003257  jmp     short loc_180003281
0x180003259  mov     rcx, [rbx+40h]; RegHandle
0x18000325d  mov     rdi, rbx
0x180003260  mov     rbx, [rbx]
0x180003263  call    cs:__imp_EventUnregister
0x180003269  test    rdi, rdi
0x18000326c  jz      short loc_180003281
0x18000326e  lea     rax, ??_7CCustomEtwTracerV2@@6B@; const CCustomEtwTracerV2::`vftable'
0x180003275  mov     rcx, rdi; Block
0x180003278  mov     [rdi+10h], rax
0x18000327c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003281  cmp     rbx, rsi
0x180003284  jnz     short loc_180003259
0x180003286  mov     rcx, cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x18000328d  test    rcx, rcx
0x180003290  jz      short loc_1800032C3
0x180003292  add     rcx, 8
0x180003296  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18000329c  mov     rcx, cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x1800032a3  test    rcx, rcx
0x1800032a6  jz      short loc_1800032B8
0x1800032a8  mov     rax, [rcx]
0x1800032ab  mov     edx, 1
0x1800032b0  mov     rax, [rax]
0x1800032b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b8  mov     cs:?sm_pHttpTracingTable@ETW_TRACE_HANDLER@@0PEAVHTTP_TRACING_TABLE@@EA, 0; HTTP_TRACING_TABLE * ETW_TRACE_HANDLER::sm_pHttpTracingTable
0x1800032c3  add     rsp, 28h
0x1800032c7  pop     rdi
0x1800032c8  pop     rsi
0x1800032c9  pop     rbp
0x1800032ca  pop     rbx
0x1800032cb  retn
```
