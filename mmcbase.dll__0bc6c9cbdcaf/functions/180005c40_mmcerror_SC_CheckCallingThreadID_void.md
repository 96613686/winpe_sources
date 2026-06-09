# mmcerror::SC::CheckCallingThreadID(void)

- ea: `0x180005c40`
- end: `0x180005c71`
- name: `?CheckCallingThreadID@SC@mmcerror@@QEAAXXZ`
- size: `49`
- prototype: `void __fastcall(mmcerror::SC *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005c40`
- `0x180006aa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c49`

## string_xrefs

- `0x180005c60`: `, method called from wrong thread`

## pseudocode

```c
void __fastcall mmcerror::SC::CheckCallingThreadID(mmcerror::SC *this)
{
  if ( mmcerror::SC::s_dwMainThreadID != GetCurrentThreadId() )
    TraceSnapinError(L", method called from wrong thread", this);
}

```

## disassembly

```asm
0x180005c40  push    rbx
0x180005c42  sub     rsp, 20h
0x180005c46  mov     rbx, rcx
0x180005c49  call    cs:__imp_GetCurrentThreadId
0x180005c4f  cmp     cs:?s_dwMainThreadID@SC@mmcerror@@0KA, eax; ulong mmcerror::SC::s_dwMainThreadID
0x180005c55  jnz     short loc_180005C5D
0x180005c57  add     rsp, 20h
0x180005c5b  pop     rbx
0x180005c5c  retn
0x180005c5d  mov     rdx, rbx; struct mmcerror::SC *
0x180005c60  lea     rcx, aMethodCalledFr; ", method called from wrong thread"
0x180005c67  add     rsp, 20h
0x180005c6b  pop     rbx
0x180005c6c  jmp     ?TraceSnapinError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceSnapinError(ushort const *,mmcerror::SC const &)
```
