# CMap<void *,void *,__int64,__int64>::RemoveAll(void)

- ea: `0x180004808`
- end: `0x18000484a`
- name: `?RemoveAll@?$CMap@PEAXPEAX_J_J@@QEAAXXZ`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000417c`
- `0x1800160b0`

## callees

- `0x180001010`

## import_xrefs

- `msvcrt!free` at `0x180004815`
- `msvcrt!free` at `0x180004815`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMap<void *,void *,__int64,__int64>::RemoveAll(__int64 a1)
{
  free(*(void **)(a1 + 8));
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 20) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  CPlexNew::FreeDataChain(*(CPlexNew **)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
}

```

## disassembly

```asm
0x180004808  push    rbx
0x18000480a  sub     rsp, 20h
0x18000480e  mov     rbx, rcx
0x180004811  mov     rcx, [rcx+8]; Block
0x180004815  call    cs:__imp_free
0x18000481b  nop
0x18000481c  mov     qword ptr [rbx+8], 0
0x180004824  mov     dword ptr [rbx+14h], 0
0x18000482b  mov     qword ptr [rbx+18h], 0
0x180004833  mov     rcx, [rbx+20h]; this
0x180004837  call    ?FreeDataChain@CPlexNew@@QEAAXXZ; CPlexNew::FreeDataChain(void)
0x18000483c  mov     qword ptr [rbx+20h], 0
0x180004844  add     rsp, 20h
0x180004848  pop     rbx
0x180004849  retn
```
