# FreeContextHandle(void *)

- ea: `0x180017fa0`
- end: `0x180017fc0`
- name: `?FreeContextHandle@@YAXPEAX@Z`
- size: `32`
- prototype: `void __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `msvcrt!free` at `0x180017fb3`
- `msvcrt!free` at `0x180017fb3`
- `Secur32!DeleteSecurityContext` at `0x180017fa9`
- `Secur32!DeleteSecurityContext` at `0x180017fa9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FreeContextHandle(struct _SecHandle *Block)
{
  DeleteSecurityContext(Block);
  free(Block);
}

```

## disassembly

```asm
0x180017fa0  push    rbx
0x180017fa2  sub     rsp, 20h
0x180017fa6  mov     rbx, rcx
0x180017fa9  call    cs:__imp_DeleteSecurityContext
0x180017faf  nop
0x180017fb0  mov     rcx, rbx; Block
0x180017fb3  call    cs:__imp_free
0x180017fb9  nop
0x180017fba  add     rsp, 20h
0x180017fbe  pop     rbx
0x180017fbf  retn
```
