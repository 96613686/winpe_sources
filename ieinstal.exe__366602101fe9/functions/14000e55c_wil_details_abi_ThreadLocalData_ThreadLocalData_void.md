# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x14000e55c`
- end: `0x14000e5f1`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e488`

## callees

- `0x14000e55c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000e581`
- `KERNEL32!GetProcessHeap` at `0x14000e5be`
- `KERNEL32!GetProcessHeap` at `0x14000e581`
- `KERNEL32!GetProcessHeap` at `0x14000e5be`
- `KERNEL32!HeapFree` at `0x14000e595`
- `KERNEL32!HeapFree` at `0x14000e5d2`
- `KERNEL32!HeapFree` at `0x14000e595`
- `KERNEL32!HeapFree` at `0x14000e5d2`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x14000e55c  push    rbx
0x14000e55e  push    rbp
0x14000e55f  push    rsi
0x14000e560  push    rdi
0x14000e561  sub     rsp, 28h
0x14000e565  movzx   eax, word ptr [rcx+20h]
0x14000e569  mov     rsi, rcx
0x14000e56c  mov     rdi, [rcx+18h]
0x14000e570  lea     rbp, [rax+rax*4]
0x14000e574  shl     rbp, 4
0x14000e578  add     rbp, rdi
0x14000e57b  jmp     short loc_14000E5B5
0x14000e57d  mov     rbx, [rdi+40h]
0x14000e581  call    cs:__imp_GetProcessHeap
0x14000e588  nop     dword ptr [rax+rax+00h]
0x14000e58d  mov     r8, rbx; lpMem
0x14000e590  xor     edx, edx; dwFlags
0x14000e592  mov     rcx, rax; hHeap
0x14000e595  call    cs:__imp_HeapFree
0x14000e59c  nop     dword ptr [rax+rax+00h]
0x14000e5a1  mov     qword ptr [rdi+40h], 0
0x14000e5a9  mov     qword ptr [rdi+48h], 0
0x14000e5b1  add     rdi, 50h ; 'P'
0x14000e5b5  cmp     rdi, rbp
0x14000e5b8  jnz     short loc_14000E57D
0x14000e5ba  mov     rbx, [rsi+18h]
0x14000e5be  call    cs:__imp_GetProcessHeap
0x14000e5c5  nop     dword ptr [rax+rax+00h]
0x14000e5ca  mov     r8, rbx; lpMem
0x14000e5cd  xor     edx, edx; dwFlags
0x14000e5cf  mov     rcx, rax; hHeap
0x14000e5d2  call    cs:__imp_HeapFree
0x14000e5d9  nop     dword ptr [rax+rax+00h]
0x14000e5de  xor     eax, eax
0x14000e5e0  mov     [rsi+20h], eax
0x14000e5e3  mov     [rsi+18h], rax
0x14000e5e7  add     rsp, 28h
0x14000e5eb  pop     rdi
0x14000e5ec  pop     rsi
0x14000e5ed  pop     rbp
0x14000e5ee  pop     rbx
0x14000e5ef  retn
```
