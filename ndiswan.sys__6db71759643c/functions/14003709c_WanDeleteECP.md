# WanDeleteECP

- ea: `0x14003709c`
- end: `0x1400370df`
- name: `WanDeleteECP`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140007024`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400370a7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400370ba`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400370cd`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400370a7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400370ba`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400370cd`

## pseudocode

```c
void WanDeleteECP()
{
  ExDeleteNPagedLookasideList(&EncryptCtxList);
  ExDeleteNPagedLookasideList(&CachedKeyList);
  ExDeleteNPagedLookasideList(&CachedKeyListLong);
}

```

## disassembly

```asm
0x14003709c  sub     rsp, 28h
0x1400370a0  lea     rcx, EncryptCtxList; Lookaside
0x1400370a7  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400370ae  nop     dword ptr [rax+rax+00h]
0x1400370b3  lea     rcx, CachedKeyList; Lookaside
0x1400370ba  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400370c1  nop     dword ptr [rax+rax+00h]
0x1400370c6  lea     rcx, CachedKeyListLong; Lookaside
0x1400370cd  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400370d4  nop     dword ptr [rax+rax+00h]
0x1400370d9  add     rsp, 28h
0x1400370dd  retn
```
