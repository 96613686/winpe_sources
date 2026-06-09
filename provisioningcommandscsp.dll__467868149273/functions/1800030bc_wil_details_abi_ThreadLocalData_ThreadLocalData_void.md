# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800030bc`
- end: `0x180003151`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ee8`

## callees

- `0x1800030bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003132`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800030f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003132`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000311e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800030e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000311e`

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
0x1800030bc  push    rbx
0x1800030be  push    rbp
0x1800030bf  push    rsi
0x1800030c0  push    rdi
0x1800030c1  sub     rsp, 28h
0x1800030c5  movzx   eax, word ptr [rcx+20h]
0x1800030c9  mov     rsi, rcx
0x1800030cc  mov     rdi, [rcx+18h]
0x1800030d0  lea     rbp, [rax+rax*4]
0x1800030d4  shl     rbp, 4
0x1800030d8  add     rbp, rdi
0x1800030db  jmp     short loc_180003115
0x1800030dd  mov     rbx, [rdi+40h]
0x1800030e1  call    cs:__imp_GetProcessHeap
0x1800030e8  nop     dword ptr [rax+rax+00h]
0x1800030ed  mov     r8, rbx; lpMem
0x1800030f0  xor     edx, edx; dwFlags
0x1800030f2  mov     rcx, rax; hHeap
0x1800030f5  call    cs:__imp_HeapFree
0x1800030fc  nop     dword ptr [rax+rax+00h]
0x180003101  mov     qword ptr [rdi+40h], 0
0x180003109  mov     qword ptr [rdi+48h], 0
0x180003111  add     rdi, 50h ; 'P'
0x180003115  cmp     rdi, rbp
0x180003118  jnz     short loc_1800030DD
0x18000311a  mov     rbx, [rsi+18h]
0x18000311e  call    cs:__imp_GetProcessHeap
0x180003125  nop     dword ptr [rax+rax+00h]
0x18000312a  mov     r8, rbx; lpMem
0x18000312d  xor     edx, edx; dwFlags
0x18000312f  mov     rcx, rax; hHeap
0x180003132  call    cs:__imp_HeapFree
0x180003139  nop     dword ptr [rax+rax+00h]
0x18000313e  xor     eax, eax
0x180003140  mov     [rsi+20h], eax
0x180003143  mov     [rsi+18h], rax
0x180003147  add     rsp, 28h
0x18000314b  pop     rdi
0x18000314c  pop     rsi
0x18000314d  pop     rbp
0x18000314e  pop     rbx
0x18000314f  retn
```
