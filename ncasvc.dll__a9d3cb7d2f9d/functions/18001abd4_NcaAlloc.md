# NcaAlloc

- ea: `0x18001abd4`
- end: `0x18001ac22`
- name: `NcaAlloc`
- size: `78`
- prototype: `LPVOID __fastcall(SIZE_T)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x180007780`
- `0x18000833c`
- `0x180008560`
- `0x180008db0`
- `0x18000b1e8`
- `0x18000b51c`
- `0x18000b88c`
- `0x18000c1d0`
- `0x18000d0e8`
- `0x18000df10`
- `0x18000eec0`
- `0x18000f654`
- `0x18000f90c`
- `0x1800127ec`
- `0x1800169b0`
- `0x180017708`
- `0x180017c78`
- `0x180019178`
- `0x1800197ac`
- `0x180019b04`
- `0x180019c70`
- `0x18001a0fc`
- `0x18001a38c`
- `0x18001a95c`
- `0x18001ac28`
- `0x18001ac78`
- `0x18001c03c`

## callees

- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001abe5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001abe5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001abfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001abfa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ac16`

## pseudocode

```c
LPVOID __fastcall NcaAlloc(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  if ( a1 )
  {
    ProcessHeap = GetProcessHeap();
    return HeapAlloc(ProcessHeap, 8u, a1);
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18001abd4  push    rbx
0x18001abd6  sub     rsp, 20h
0x18001abda  mov     rbx, rcx
0x18001abdd  test    rcx, rcx
0x18001abe0  jnz     short loc_18001ABFA
0x18001abe2  lea     ecx, [rbx+57h]; dwErrCode
0x18001abe5  call    cs:__imp_SetLastError
0x18001abec  nop     dword ptr [rax+rax+00h]
0x18001abf1  xor     eax, eax
0x18001abf3  add     rsp, 20h
0x18001abf7  pop     rbx
0x18001abf8  retn
0x18001abfa  call    cs:__imp_GetProcessHeap
0x18001ac01  nop     dword ptr [rax+rax+00h]
0x18001ac06  mov     r8, rbx
0x18001ac09  mov     edx, 8
0x18001ac0e  mov     rcx, rax
0x18001ac11  add     rsp, 20h
0x18001ac15  pop     rbx
0x18001ac16  jmp     cs:__imp_HeapAlloc
```
