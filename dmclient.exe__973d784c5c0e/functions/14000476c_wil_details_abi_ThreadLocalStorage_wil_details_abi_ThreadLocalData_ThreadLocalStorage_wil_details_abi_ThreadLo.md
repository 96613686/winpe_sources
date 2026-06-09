# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x14000476c`
- end: `0x1400047d1`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ae34`

## callees

- `0x14000476c`
- `0x140004ae0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004796`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004796`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400047aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400047aa`

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
0x14000476c  push    rbx
0x14000476e  push    rbp
0x14000476f  push    rsi
0x140004770  push    rdi
0x140004771  sub     rsp, 28h
0x140004775  lea     rbp, [rcx+50h]
0x140004779  mov     rdi, rcx
0x14000477c  cmp     rcx, rbp
0x14000477f  jz      short loc_1400047C7
0x140004781  mov     rsi, [rdi]
0x140004784  jmp     short loc_1400047B6
0x140004786  mov     rbx, rsi
0x140004789  mov     rsi, [rsi+8]
0x14000478d  lea     rcx, [rbx+10h]; this
0x140004791  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x140004796  call    cs:__imp_GetProcessHeap
0x14000479d  nop     dword ptr [rax+rax+00h]
0x1400047a2  mov     r8, rbx; lpMem
0x1400047a5  xor     edx, edx; dwFlags
0x1400047a7  mov     rcx, rax; hHeap
0x1400047aa  call    cs:__imp_HeapFree
0x1400047b1  nop     dword ptr [rax+rax+00h]
0x1400047b6  test    rsi, rsi
0x1400047b9  jnz     short loc_140004786
0x1400047bb  mov     [rdi], rsi
0x1400047be  add     rdi, 8
0x1400047c2  cmp     rdi, rbp
0x1400047c5  jnz     short loc_140004781
0x1400047c7  add     rsp, 28h
0x1400047cb  pop     rdi
0x1400047cc  pop     rsi
0x1400047cd  pop     rbp
0x1400047ce  pop     rbx
0x1400047cf  retn
```
