# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800034d4`
- end: `0x180003550`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e58`

## callees

- `0x1800034d4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800034f9`
- `KERNEL32!GetProcessHeap` at `0x18000352a`
- `KERNEL32!GetProcessHeap` at `0x1800034f9`
- `KERNEL32!GetProcessHeap` at `0x18000352a`
- `KERNEL32!HeapFree` at `0x180003507`
- `KERNEL32!HeapFree` at `0x180003538`
- `KERNEL32!HeapFree` at `0x180003507`
- `KERNEL32!HeapFree` at `0x180003538`

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
0x1800034d4  push    rbx
0x1800034d6  push    rbp
0x1800034d7  push    rsi
0x1800034d8  push    rdi
0x1800034d9  sub     rsp, 28h
0x1800034dd  movzx   eax, word ptr [rcx+20h]
0x1800034e1  mov     rsi, rcx
0x1800034e4  mov     rdi, [rcx+18h]
0x1800034e8  lea     rbp, [rax+rax*4]
0x1800034ec  shl     rbp, 4
0x1800034f0  add     rbp, rdi
0x1800034f3  jmp     short loc_180003521
0x1800034f5  mov     rbx, [rdi+40h]
0x1800034f9  call    cs:__imp_GetProcessHeap
0x1800034ff  mov     r8, rbx; lpMem
0x180003502  xor     edx, edx; dwFlags
0x180003504  mov     rcx, rax; hHeap
0x180003507  call    cs:__imp_HeapFree
0x18000350d  mov     qword ptr [rdi+40h], 0
0x180003515  mov     qword ptr [rdi+48h], 0
0x18000351d  add     rdi, 50h ; 'P'
0x180003521  cmp     rdi, rbp
0x180003524  jnz     short loc_1800034F5
0x180003526  mov     rbx, [rsi+18h]
0x18000352a  call    cs:__imp_GetProcessHeap
0x180003530  mov     r8, rbx; lpMem
0x180003533  xor     edx, edx; dwFlags
0x180003535  mov     rcx, rax; hHeap
0x180003538  call    cs:__imp_HeapFree
0x18000353e  xor     eax, eax
0x180003540  mov     [rsi+20h], eax
0x180003543  mov     [rsi+18h], rax
0x180003547  add     rsp, 28h
0x18000354b  pop     rdi
0x18000354c  pop     rsi
0x18000354d  pop     rbp
0x18000354e  pop     rbx
0x18000354f  retn
```
