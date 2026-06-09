# FwhcFreeMem

- ea: `0x18000bcc4`
- end: `0x18000bd06`
- name: `FwhcFreeMem`
- size: `66`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009978`
- `0x18000b548`
- `0x18000bf3c`
- `0x18000c154`

## callees

- `0x18000bcc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bcde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bcde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bcec`

## pseudocode

```c
__int64 __fastcall FwhcFreeMem(void **a1)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax

  if ( a1 )
  {
    v2 = *a1;
    if ( *a1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
      *a1 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000bcc4  mov     [rsp+arg_0], rbx
0x18000bcc9  push    rdi
0x18000bcca  sub     rsp, 20h
0x18000bcce  mov     rbx, rcx
0x18000bcd1  test    rcx, rcx
0x18000bcd4  jz      short loc_18000BCF9
0x18000bcd6  mov     rdi, [rcx]
0x18000bcd9  test    rdi, rdi
0x18000bcdc  jz      short loc_18000BCF9
0x18000bcde  call    cs:__imp_GetProcessHeap
0x18000bce4  mov     r8, rdi; lpMem
0x18000bce7  xor     edx, edx; dwFlags
0x18000bce9  mov     rcx, rax; hHeap
0x18000bcec  call    cs:__imp_HeapFree
0x18000bcf2  mov     qword ptr [rbx], 0
0x18000bcf9  mov     rbx, [rsp+28h+arg_0]
0x18000bcfe  xor     eax, eax
0x18000bd00  add     rsp, 20h
0x18000bd04  pop     rdi
0x18000bd05  retn
```
