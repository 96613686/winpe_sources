# FILTER_POOL_ITEM::~FILTER_POOL_ITEM(void)

- ea: `0x180007190`
- end: `0x1800071b4`
- name: `??1FILTER_POOL_ITEM@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(FILTER_POOL_ITEM *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f60`
- `0x180007160`

## callees

- `0x180007190`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071a2`

## pseudocode

```c
void __fastcall FILTER_POOL_ITEM::~FILTER_POOL_ITEM(FILTER_POOL_ITEM *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    LocalFree(v2);
  *(_DWORD *)this = 1716539212;
}

```

## disassembly

```asm
0x180007190  push    rbx
0x180007192  sub     rsp, 20h
0x180007196  mov     rbx, rcx
0x180007199  mov     rcx, [rcx+18h]; hMem
0x18000719d  test    rcx, rcx
0x1800071a0  jz      short loc_1800071A8
0x1800071a2  call    cs:__imp_LocalFree
0x1800071a8  mov     dword ptr [rbx], 66504F4Ch
0x1800071ae  add     rsp, 20h
0x1800071b2  pop     rbx
0x1800071b3  retn
```
