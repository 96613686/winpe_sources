# rc4_safe_shutdown

- ea: `0x18004bb84`
- end: `0x18004bbe8`
- name: `rc4_safe_shutdown`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004a8c0`

## callees

- `0x18004bb84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004bba7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004bba7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bbdc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bbb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bbb9`

## pseudocode

```c
BOOL __fastcall rc4_safe_shutdown(unsigned int *a1)
{
  unsigned int v1; // esi
  __int64 i; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&a1[2 * i + 2] + 8LL));
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18004bb84  mov     [rsp+arg_0], rbx
0x18004bb89  mov     [rsp+arg_8], rsi
0x18004bb8e  push    rdi
0x18004bb8f  sub     rsp, 20h
0x18004bb93  mov     esi, [rcx]
0x18004bb95  xor     ebx, ebx
0x18004bb97  mov     rdi, rcx
0x18004bb9a  test    esi, esi
0x18004bb9c  jz      short loc_18004BBB9
0x18004bb9e  mov     rcx, [rdi+rbx*8+8]
0x18004bba3  add     rcx, 8; lpCriticalSection
0x18004bba7  call    cs:__imp_DeleteCriticalSection
0x18004bbae  nop     dword ptr [rax+rax+00h]
0x18004bbb3  inc     ebx
0x18004bbb5  cmp     ebx, esi
0x18004bbb7  jb      short loc_18004BB9E
0x18004bbb9  call    cs:__imp_GetProcessHeap
0x18004bbc0  nop     dword ptr [rax+rax+00h]
0x18004bbc5  mov     r8, rdi
0x18004bbc8  xor     edx, edx
0x18004bbca  mov     rcx, rax
0x18004bbcd  mov     rbx, [rsp+28h+arg_0]
0x18004bbd2  mov     rsi, [rsp+28h+arg_8]
0x18004bbd7  add     rsp, 20h
0x18004bbdb  pop     rdi
0x18004bbdc  jmp     cs:__imp_HeapFree
```
