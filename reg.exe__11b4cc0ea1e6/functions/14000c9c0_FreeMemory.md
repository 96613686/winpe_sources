# FreeMemory

- ea: `0x14000c9c0`
- end: `0x14000ca47`
- name: `FreeMemory`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e90`
- `0x140001fec`
- `0x140002070`
- `0x1400024a4`
- `0x14000329c`
- `0x140003a58`
- `0x1400055f8`
- `0x140005940`
- `0x140005e84`
- `0x14000612c`
- `0x140006394`
- `0x140007170`
- `0x140007834`
- `0x140007be0`
- `0x140008320`
- `0x140008b4c`
- `0x140008f10`
- `0x14000a3f8`
- `0x14000caa8`
- `0x14000d7a8`
- `0x14000d8b4`
- `0x14000e634`
- `0x14000e7a4`
- `0x14000e928`
- `0x14000e994`
- `0x14000ebc8`

## callees

- `0x140001cc6`
- `0x14000c9c0`
- `0x14000ca50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c9d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c9d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c9df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c9df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c9f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c9f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ca2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ca2f`

## pseudocode

```c
BOOL __fastcall FreeMemory(void **a1)
{
  DWORD v2; // ecx
  BOOL result; // eax
  HANDLE ProcessHeap; // rdi
  int BufferSize; // eax

  if ( !a1 )
  {
    if ( GetLastError() )
      return 0;
    v2 = 87;
LABEL_4:
    SetLastError(v2);
    return 0;
  }
  if ( !*a1 )
    return 1;
  ProcessHeap = GetProcessHeap();
  if ( !ProcessHeap )
    return 0;
  BufferSize = GetBufferSize(*a1);
  if ( BufferSize == -1 )
  {
    v2 = -2147467261;
    goto LABEL_4;
  }
  memset_0(*a1, 0, BufferSize);
  result = HeapFree(ProcessHeap, 0, *a1);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x14000c9c0  mov     [rsp+arg_0], rbx
0x14000c9c5  push    rdi
0x14000c9c6  sub     rsp, 20h
0x14000c9ca  mov     rbx, rcx
0x14000c9cd  test    rcx, rcx
0x14000c9d0  jnz     short loc_14000C9E7
0x14000c9d2  call    cs:__imp_GetLastError
0x14000c9d8  test    eax, eax
0x14000c9da  jnz     short loc_14000CA02
0x14000c9dc  lea     ecx, [rbx+57h]; dwErrCode
0x14000c9df  call    cs:__imp_SetLastError
0x14000c9e5  jmp     short loc_14000CA02
0x14000c9e7  cmp     qword ptr [rcx], 0
0x14000c9eb  jnz     short loc_14000C9F4
0x14000c9ed  mov     eax, 1
0x14000c9f2  jmp     short loc_14000CA3C
0x14000c9f4  call    cs:__imp_GetProcessHeap
0x14000c9fa  mov     rdi, rax
0x14000c9fd  test    rax, rax
0x14000ca00  jnz     short loc_14000CA06
0x14000ca02  xor     eax, eax
0x14000ca04  jmp     short loc_14000CA3C
0x14000ca06  mov     rcx, [rbx]
0x14000ca09  call    GetBufferSize
0x14000ca0e  cmp     eax, 0FFFFFFFFh
0x14000ca11  jnz     short loc_14000CA1A
0x14000ca13  mov     ecx, 80004003h
0x14000ca18  jmp     short loc_14000C9DF
0x14000ca1a  mov     rcx, [rbx]; void *
0x14000ca1d  xor     edx, edx; Val
0x14000ca1f  movsxd  r8, eax; Size
0x14000ca22  call    memset_0
0x14000ca27  mov     r8, [rbx]; lpMem
0x14000ca2a  xor     edx, edx; dwFlags
0x14000ca2c  mov     rcx, rdi; hHeap
0x14000ca2f  call    cs:__imp_HeapFree
0x14000ca35  mov     qword ptr [rbx], 0
0x14000ca3c  mov     rbx, [rsp+28h+arg_0]
0x14000ca41  add     rsp, 20h
0x14000ca45  pop     rdi
0x14000ca46  retn
```
