# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140007534`
- end: `0x140007583`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004080`

## callees

- `0x140007534`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007555`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007555`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007563`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007563`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x140007534  push    rbx
0x140007536  push    rbp
0x140007537  push    rsi
0x140007538  push    rdi
0x140007539  sub     rsp, 28h
0x14000753d  lea     rbp, [rcx+50h]
0x140007541  mov     rdi, rcx
0x140007544  cmp     rcx, rbp
0x140007547  jz      short loc_14000757A
0x140007549  mov     rsi, [rdi]
0x14000754c  jmp     short loc_140007569
0x14000754e  mov     rbx, rsi
0x140007551  mov     rsi, [rsi+8]
0x140007555  call    cs:__imp_GetProcessHeap
0x14000755b  mov     r8, rbx; lpMem
0x14000755e  xor     edx, edx; dwFlags
0x140007560  mov     rcx, rax; hHeap
0x140007563  call    cs:__imp_HeapFree
0x140007569  test    rsi, rsi
0x14000756c  jnz     short loc_14000754E
0x14000756e  mov     [rdi], rsi
0x140007571  add     rdi, 8
0x140007575  cmp     rdi, rbp
0x140007578  jnz     short loc_140007549
0x14000757a  add     rsp, 28h
0x14000757e  pop     rdi
0x14000757f  pop     rsi
0x140007580  pop     rbp
0x140007581  pop     rbx
0x140007582  retn
```
