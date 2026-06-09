# SecFileMonShutdown

- ea: `0x14003c830`
- end: `0x14003c86e`
- name: `SecFileMonShutdown`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002a5e8`

## callees

- `0x140009b80`
- `0x14003c830`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003c840`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003c840`

## pseudocode

```c
void SecFileMonShutdown()
{
  if ( SecFileMonDataPrivate )
  {
    ExDeletePagedLookasideList(SecFileMonDataPrivate);
    SecFreePool(SecFileMonDataPrivate, 0x6D466353u);
    SecFileMonDataPrivate = 0;
  }
}

```

## disassembly

```asm
0x14003c830  sub     rsp, 28h
0x14003c834  mov     rcx, cs:SecFileMonDataPrivate; Lookaside
0x14003c83b  test    rcx, rcx
0x14003c83e  jz      short loc_14003C868
0x14003c840  call    cs:__imp_ExDeletePagedLookasideList
0x14003c847  nop     dword ptr [rax+rax+00h]
0x14003c84c  mov     rcx, cs:SecFileMonDataPrivate; P
0x14003c853  mov     edx, 6D466353h; Tag
0x14003c858  call    SecFreePool
0x14003c85d  mov     cs:SecFileMonDataPrivate, 0
0x14003c868  add     rsp, 28h
0x14003c86c  retn
```
