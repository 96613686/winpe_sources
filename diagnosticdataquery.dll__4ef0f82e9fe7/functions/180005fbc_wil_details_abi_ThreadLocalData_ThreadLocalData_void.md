# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180005fbc`
- end: `0x180006038`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e04`

## callees

- `0x180005fbc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006012`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006020`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006020`

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
0x180005fbc  push    rbx
0x180005fbe  push    rbp
0x180005fbf  push    rsi
0x180005fc0  push    rdi
0x180005fc1  sub     rsp, 28h
0x180005fc5  movzx   eax, word ptr [rcx+20h]
0x180005fc9  mov     rsi, rcx
0x180005fcc  mov     rdi, [rcx+18h]
0x180005fd0  lea     rbp, [rax+rax*4]
0x180005fd4  shl     rbp, 4
0x180005fd8  add     rbp, rdi
0x180005fdb  jmp     short loc_180006009
0x180005fdd  mov     rbx, [rdi+40h]
0x180005fe1  call    cs:__imp_GetProcessHeap
0x180005fe7  mov     r8, rbx; lpMem
0x180005fea  xor     edx, edx; dwFlags
0x180005fec  mov     rcx, rax; hHeap
0x180005fef  call    cs:__imp_HeapFree
0x180005ff5  mov     qword ptr [rdi+40h], 0
0x180005ffd  mov     qword ptr [rdi+48h], 0
0x180006005  add     rdi, 50h ; 'P'
0x180006009  cmp     rdi, rbp
0x18000600c  jnz     short loc_180005FDD
0x18000600e  mov     rbx, [rsi+18h]
0x180006012  call    cs:__imp_GetProcessHeap
0x180006018  mov     r8, rbx; lpMem
0x18000601b  xor     edx, edx; dwFlags
0x18000601d  mov     rcx, rax; hHeap
0x180006020  call    cs:__imp_HeapFree
0x180006026  xor     eax, eax
0x180006028  mov     [rsi+20h], eax
0x18000602b  mov     [rsi+18h], rax
0x18000602f  add     rsp, 28h
0x180006033  pop     rdi
0x180006034  pop     rsi
0x180006035  pop     rbp
0x180006036  pop     rbx
0x180006037  retn
```
