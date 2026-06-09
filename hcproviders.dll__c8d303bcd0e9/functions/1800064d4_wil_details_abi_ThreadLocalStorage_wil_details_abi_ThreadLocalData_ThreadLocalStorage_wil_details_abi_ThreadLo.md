# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800064d4`
- end: `0x180006539`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006440`

## callees

- `0x1800064d4`
- `0x180006860`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006512`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006512`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::Clear((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x1800064d4  push    rbx
0x1800064d6  push    rbp
0x1800064d7  push    rsi
0x1800064d8  push    rdi
0x1800064d9  sub     rsp, 28h
0x1800064dd  lea     rbp, [rcx+50h]
0x1800064e1  mov     rdi, rcx
0x1800064e4  cmp     rcx, rbp
0x1800064e7  jz      short loc_18000652F
0x1800064e9  mov     rsi, [rdi]
0x1800064ec  jmp     short loc_18000651E
0x1800064ee  mov     rbx, rsi
0x1800064f1  mov     rsi, [rsi+8]
0x1800064f5  lea     rcx, [rbx+10h]; this
0x1800064f9  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x1800064fe  call    cs:__imp_GetProcessHeap
0x180006505  nop     dword ptr [rax+rax+00h]
0x18000650a  mov     r8, rbx; lpMem
0x18000650d  xor     edx, edx; dwFlags
0x18000650f  mov     rcx, rax; hHeap
0x180006512  call    cs:__imp_HeapFree
0x180006519  nop     dword ptr [rax+rax+00h]
0x18000651e  test    rsi, rsi
0x180006521  jnz     short loc_1800064EE
0x180006523  mov     [rdi], rsi
0x180006526  add     rdi, 8
0x18000652a  cmp     rdi, rbp
0x18000652d  jnz     short loc_1800064E9
0x18000652f  add     rsp, 28h
0x180006533  pop     rdi
0x180006534  pop     rsi
0x180006535  pop     rbp
0x180006536  pop     rbx
0x180006537  retn
```
