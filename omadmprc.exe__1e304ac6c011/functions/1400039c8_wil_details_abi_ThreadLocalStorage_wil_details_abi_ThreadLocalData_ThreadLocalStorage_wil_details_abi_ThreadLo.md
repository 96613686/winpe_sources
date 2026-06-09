# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1400039c8`
- end: `0x140003a2d`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007dc4`

## callees

- `0x1400039c8`
- `0x14000402c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a06`

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
0x1400039c8  push    rbx
0x1400039ca  push    rbp
0x1400039cb  push    rsi
0x1400039cc  push    rdi
0x1400039cd  sub     rsp, 28h
0x1400039d1  lea     rbp, [rcx+50h]
0x1400039d5  mov     rdi, rcx
0x1400039d8  cmp     rcx, rbp
0x1400039db  jz      short loc_140003A23
0x1400039dd  mov     rsi, [rdi]
0x1400039e0  jmp     short loc_140003A12
0x1400039e2  mov     rbx, rsi
0x1400039e5  mov     rsi, [rsi+8]
0x1400039e9  lea     rcx, [rbx+10h]; this
0x1400039ed  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x1400039f2  call    cs:__imp_GetProcessHeap
0x1400039f9  nop     dword ptr [rax+rax+00h]
0x1400039fe  mov     r8, rbx; lpMem
0x140003a01  xor     edx, edx; dwFlags
0x140003a03  mov     rcx, rax; hHeap
0x140003a06  call    cs:__imp_HeapFree
0x140003a0d  nop     dword ptr [rax+rax+00h]
0x140003a12  test    rsi, rsi
0x140003a15  jnz     short loc_1400039E2
0x140003a17  mov     [rdi], rsi
0x140003a1a  add     rdi, 8
0x140003a1e  cmp     rdi, rbp
0x140003a21  jnz     short loc_1400039DD
0x140003a23  add     rsp, 28h
0x140003a27  pop     rdi
0x140003a28  pop     rsi
0x140003a29  pop     rbp
0x140003a2a  pop     rbx
0x140003a2b  retn
```
