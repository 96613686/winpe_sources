# MemAlloc(unsigned __int64)

- ea: `0x180007d38`
- end: `0x180007d79`
- name: `?MemAlloc@@YAPEAX_K@Z`
- size: `65`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x18000331c`
- `0x180003ff4`
- `0x180004120`
- `0x180004240`
- `0x180007fe4`
- `0x18000831c`
- `0x180009224`
- `0x18000949c`
- `0x1800099f0`
- `0x18000a1b4`
- `0x18000a5dc`
- `0x18000a8bc`
- `0x18000ab50`
- `0x18000af5c`
- `0x18000b584`
- `0x18000da34`
- `0x18001084c`
- `0x180010a00`
- `0x180010f54`

## callees

- `0x180007d38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007d72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d4d`

## pseudocode

```c
HANDLE __fastcall MemAlloc(SIZE_T a1)
{
  HANDLE result; // rax

  result = g_hLocalHeap;
  if ( g_hLocalHeap )
    return HeapAlloc(result, 0, a1);
  result = GetProcessHeap();
  g_hLocalHeap = result;
  if ( result )
    return HeapAlloc(result, 0, a1);
  return result;
}

```

## disassembly

```asm
0x180007d38  push    rbx
0x180007d3a  sub     rsp, 20h
0x180007d3e  mov     rbx, rcx
0x180007d41  mov     rax, cs:?g_hLocalHeap@@3PEAXEA; void * g_hLocalHeap
0x180007d48  test    rax, rax
0x180007d4b  jnz     short loc_180007D65
0x180007d4d  call    cs:__imp_GetProcessHeap
0x180007d53  mov     cs:?g_hLocalHeap@@3PEAXEA, rax; void * g_hLocalHeap
0x180007d5a  test    rax, rax
0x180007d5d  jnz     short loc_180007D65
0x180007d5f  add     rsp, 20h
0x180007d63  pop     rbx
0x180007d64  retn
0x180007d65  mov     r8, rbx
0x180007d68  xor     edx, edx
0x180007d6a  mov     rcx, rax
0x180007d6d  add     rsp, 20h
0x180007d71  pop     rbx
0x180007d72  jmp     cs:__imp_HeapAlloc
```
