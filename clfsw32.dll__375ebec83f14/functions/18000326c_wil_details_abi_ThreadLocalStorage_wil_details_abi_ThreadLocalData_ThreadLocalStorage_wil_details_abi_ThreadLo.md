# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000326c`
- end: `0x1800032d1`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006924`

## callees

- `0x18000326c`
- `0x1800035f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003296`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003296`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032aa`

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
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 16));
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
0x18000326c  push    rbx
0x18000326e  push    rbp
0x18000326f  push    rsi
0x180003270  push    rdi
0x180003271  sub     rsp, 28h
0x180003275  lea     rbp, [rcx+50h]
0x180003279  mov     rdi, rcx
0x18000327c  cmp     rcx, rbp
0x18000327f  jz      short loc_1800032C7
0x180003281  mov     rsi, [rdi]
0x180003284  jmp     short loc_1800032B6
0x180003286  mov     rbx, rsi
0x180003289  mov     rsi, [rsi+8]
0x18000328d  lea     rcx, [rbx+10h]; this
0x180003291  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180003296  call    cs:__imp_GetProcessHeap
0x18000329d  nop     dword ptr [rax+rax+00h]
0x1800032a2  mov     r8, rbx; lpMem
0x1800032a5  xor     edx, edx; dwFlags
0x1800032a7  mov     rcx, rax; hHeap
0x1800032aa  call    cs:__imp_HeapFree
0x1800032b1  nop     dword ptr [rax+rax+00h]
0x1800032b6  test    rsi, rsi
0x1800032b9  jnz     short loc_180003286
0x1800032bb  mov     [rdi], rsi
0x1800032be  add     rdi, 8
0x1800032c2  cmp     rdi, rbp
0x1800032c5  jnz     short loc_180003281
0x1800032c7  add     rsp, 28h
0x1800032cb  pop     rdi
0x1800032cc  pop     rsi
0x1800032cd  pop     rbp
0x1800032ce  pop     rbx
0x1800032cf  retn
```
