# MIDL_user_free

- ea: `0x180007d80`
- end: `0x180007dab`
- name: `MIDL_user_free`
- size: `43`
- prototype: `void __stdcall(void *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001970`
- `0x1800030f0`
- `0x180004230`
- `0x180004ed0`
- `0x180005380`
- `0x180009880`

## callees

- `0x18000a7ce`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007da4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180007d89`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180007d89`

## pseudocode

```c
void __stdcall MIDL_user_free(void *a1)
{
  SIZE_T v2; // rax

  v2 = LocalSize(a1);
  memset_0(a1, 0, v2);
  LocalFree(a1);
}

```

## disassembly

```asm
0x180007d80  push    rbx
0x180007d82  sub     rsp, 20h
0x180007d86  mov     rbx, rcx
0x180007d89  call    cs:__imp_LocalSize
0x180007d8f  xor     edx, edx; Val
0x180007d91  mov     rcx, rbx; void *
0x180007d94  mov     r8, rax; Size
0x180007d97  call    memset_0
0x180007d9c  mov     rcx, rbx
0x180007d9f  add     rsp, 20h
0x180007da3  pop     rbx
0x180007da4  jmp     cs:__imp_LocalFree
```
