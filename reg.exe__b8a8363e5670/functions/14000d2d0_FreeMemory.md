# FreeMemory

- ea: `0x14000d2d0`
- end: `0x14000d370`
- name: `FreeMemory`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e90`
- `0x140002004`
- `0x140002090`
- `0x14000263c`
- `0x1400033d8`
- `0x140003c24`
- `0x140005910`
- `0x140005c78`
- `0x1400061e4`
- `0x1400064b0`
- `0x14000672c`
- `0x1400075ac`
- `0x140007cbc`
- `0x1400080a4`
- `0x140008838`
- `0x1400090a8`
- `0x140009498`
- `0x14000aa4c`
- `0x14000d3e8`
- `0x14000e268`
- `0x14000e3bc`
- `0x14000f2c4`
- `0x14000f43c`
- `0x14000f5c8`
- `0x14000f638`
- `0x14000f874`

## callees

- `0x140001cc6`
- `0x14000d2d0`
- `0x14000d378`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d2e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d2e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d2f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d310`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d310`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d351`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d351`

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
0x14000d2d0  mov     [rsp+arg_0], rbx
0x14000d2d5  push    rdi
0x14000d2d6  sub     rsp, 20h
0x14000d2da  mov     rbx, rcx
0x14000d2dd  test    rcx, rcx
0x14000d2e0  jnz     short loc_14000D303
0x14000d2e2  call    cs:__imp_GetLastError
0x14000d2e9  nop     dword ptr [rax+rax+00h]
0x14000d2ee  test    eax, eax
0x14000d2f0  jnz     short loc_14000D324
0x14000d2f2  lea     ecx, [rbx+57h]; dwErrCode
0x14000d2f5  call    cs:__imp_SetLastError
0x14000d2fc  nop     dword ptr [rax+rax+00h]
0x14000d301  jmp     short loc_14000D324
0x14000d303  cmp     qword ptr [rcx], 0
0x14000d307  jnz     short loc_14000D310
0x14000d309  mov     eax, 1
0x14000d30e  jmp     short loc_14000D364
0x14000d310  call    cs:__imp_GetProcessHeap
0x14000d317  nop     dword ptr [rax+rax+00h]
0x14000d31c  mov     rdi, rax
0x14000d31f  test    rax, rax
0x14000d322  jnz     short loc_14000D328
0x14000d324  xor     eax, eax
0x14000d326  jmp     short loc_14000D364
0x14000d328  mov     rcx, [rbx]
0x14000d32b  call    GetBufferSize
0x14000d330  cmp     eax, 0FFFFFFFFh
0x14000d333  jnz     short loc_14000D33C
0x14000d335  mov     ecx, 80004003h
0x14000d33a  jmp     short loc_14000D2F5
0x14000d33c  mov     rcx, [rbx]; void *
0x14000d33f  xor     edx, edx; Val
0x14000d341  movsxd  r8, eax; Size
0x14000d344  call    memset_0
0x14000d349  mov     r8, [rbx]; lpMem
0x14000d34c  xor     edx, edx; dwFlags
0x14000d34e  mov     rcx, rdi; hHeap
0x14000d351  call    cs:__imp_HeapFree
0x14000d358  nop     dword ptr [rax+rax+00h]
0x14000d35d  mov     qword ptr [rbx], 0
0x14000d364  mov     rbx, [rsp+28h+arg_0]
0x14000d369  add     rsp, 20h
0x14000d36d  pop     rdi
0x14000d36e  retn
```
