# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800030c8`
- end: `0x180003144`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ffc`

## callees

- `0x1800030c8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800030fb`
- `KERNEL32!HeapFree` at `0x18000312c`
- `KERNEL32!HeapFree` at `0x1800030fb`
- `KERNEL32!HeapFree` at `0x18000312c`
- `KERNEL32!GetProcessHeap` at `0x1800030ed`
- `KERNEL32!GetProcessHeap` at `0x18000311e`
- `KERNEL32!GetProcessHeap` at `0x1800030ed`
- `KERNEL32!GetProcessHeap` at `0x18000311e`

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
0x1800030c8  push    rbx
0x1800030ca  push    rbp
0x1800030cb  push    rsi
0x1800030cc  push    rdi
0x1800030cd  sub     rsp, 28h
0x1800030d1  movzx   eax, word ptr [rcx+20h]
0x1800030d5  mov     rsi, rcx
0x1800030d8  mov     rdi, [rcx+18h]
0x1800030dc  lea     rbp, [rax+rax*4]
0x1800030e0  shl     rbp, 4
0x1800030e4  add     rbp, rdi
0x1800030e7  jmp     short loc_180003115
0x1800030e9  mov     rbx, [rdi+40h]
0x1800030ed  call    cs:__imp_GetProcessHeap
0x1800030f3  mov     r8, rbx; lpMem
0x1800030f6  xor     edx, edx; dwFlags
0x1800030f8  mov     rcx, rax; hHeap
0x1800030fb  call    cs:__imp_HeapFree
0x180003101  mov     qword ptr [rdi+40h], 0
0x180003109  mov     qword ptr [rdi+48h], 0
0x180003111  add     rdi, 50h ; 'P'
0x180003115  cmp     rdi, rbp
0x180003118  jnz     short loc_1800030E9
0x18000311a  mov     rbx, [rsi+18h]
0x18000311e  call    cs:__imp_GetProcessHeap
0x180003124  mov     r8, rbx; lpMem
0x180003127  xor     edx, edx; dwFlags
0x180003129  mov     rcx, rax; hHeap
0x18000312c  call    cs:__imp_HeapFree
0x180003132  xor     eax, eax
0x180003134  mov     [rsi+20h], eax
0x180003137  mov     [rsi+18h], rax
0x18000313b  add     rsp, 28h
0x18000313f  pop     rdi
0x180003140  pop     rsi
0x180003141  pop     rbp
0x180003142  pop     rbx
0x180003143  retn
```
