# FreeCallParams

- ea: `0x140003068`
- end: `0x140003088`
- name: `FreeCallParams`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140010fd4`
- `0x140013ad0`

## callees

- `0x140003068`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003076`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003076`

## pseudocode

```c
void __fastcall FreeCallParams(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0x6D704353u);
}

```

## disassembly

```asm
0x140003068  sub     rsp, 28h
0x14000306c  test    rcx, rcx
0x14000306f  jz      short loc_140003082
0x140003071  mov     edx, 6D704353h; Tag
0x140003076  call    cs:__imp_ExFreePoolWithTag
0x14000307d  nop     dword ptr [rax+rax+00h]
0x140003082  add     rsp, 28h
0x140003086  retn
```
