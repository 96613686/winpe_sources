# Common::GlobalHeap::Free(void *)

- ea: `0x18000be3c`
- end: `0x18000be5c`
- name: `?Free@GlobalHeap@Common@@SAXPEAX@Z`
- size: `32`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `47`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004510`
- `0x180008190`
- `0x18000bcc8`
- `0x18000bd38`
- `0x18000c6d8`
- `0x18000c914`
- `0x18000c9b0`
- `0x18000cfcc`
- `0x18000d0d0`
- `0x18000f590`
- `0x18000f740`
- `0x180010024`
- `0x180010190`
- `0x1800101e0`
- `0x180011a40`
- `0x1800133c0`
- `0x180013910`
- `0x1800144ac`
- `0x18001480c`
- `0x18001577c`
- `0x180015934`
- `0x180015998`
- `0x180015a64`
- `0x180015ff4`
- `0x18001601c`
- `0x180016044`
- `0x18001606c`
- `0x180016094`
- `0x1800160bc`
- `0x1800163ec`
- `0x1800165c0`
- `0x18001686c`
- `0x180016cd0`
- `0x180016d68`
- `0x180016dec`
- `0x180017140`
- `0x180017318`
- `0x180017518`
- `0x180017ae0`
- `0x180017b5c`
- `0x180017ba8`
- `0x18001890c`
- `0x180018aac`
- `0x180018b90`
- `0x180018ffc`
- `0x18001a330`
- `0x18001adf0`

## callees

- `0x18000be3c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000be51`
- `ntdll!RtlFreeHeap` at `0x18000be51`

## pseudocode

```c
void __fastcall Common::GlobalHeap::Free(PVOID P)
{
  if ( P )
    RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P);
}

```

## disassembly

```asm
0x18000be3c  sub     rsp, 28h
0x18000be40  test    rcx, rcx
0x18000be43  jz      short loc_18000BE57
0x18000be45  mov     r8, rcx; P
0x18000be48  xor     edx, edx; Flags
0x18000be4a  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18000be51  call    cs:__imp_RtlFreeHeap
0x18000be57  add     rsp, 28h
0x18000be5b  retn
```
