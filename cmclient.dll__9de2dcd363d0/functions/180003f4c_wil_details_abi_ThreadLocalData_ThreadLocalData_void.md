# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003f4c`
- end: `0x180003fc8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003d24`

## callees

- `0x180003f4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fa2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fb0`

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
0x180003f4c  push    rbx
0x180003f4e  push    rbp
0x180003f4f  push    rsi
0x180003f50  push    rdi
0x180003f51  sub     rsp, 28h
0x180003f55  movzx   eax, word ptr [rcx+20h]
0x180003f59  mov     rsi, rcx
0x180003f5c  mov     rdi, [rcx+18h]
0x180003f60  lea     rbp, [rax+rax*4]
0x180003f64  shl     rbp, 4
0x180003f68  add     rbp, rdi
0x180003f6b  jmp     short loc_180003F99
0x180003f6d  mov     rbx, [rdi+40h]
0x180003f71  call    cs:__imp_GetProcessHeap
0x180003f77  mov     r8, rbx; lpMem
0x180003f7a  xor     edx, edx; dwFlags
0x180003f7c  mov     rcx, rax; hHeap
0x180003f7f  call    cs:__imp_HeapFree
0x180003f85  mov     qword ptr [rdi+40h], 0
0x180003f8d  mov     qword ptr [rdi+48h], 0
0x180003f95  add     rdi, 50h ; 'P'
0x180003f99  cmp     rdi, rbp
0x180003f9c  jnz     short loc_180003F6D
0x180003f9e  mov     rbx, [rsi+18h]
0x180003fa2  call    cs:__imp_GetProcessHeap
0x180003fa8  mov     r8, rbx; lpMem
0x180003fab  xor     edx, edx; dwFlags
0x180003fad  mov     rcx, rax; hHeap
0x180003fb0  call    cs:__imp_HeapFree
0x180003fb6  xor     eax, eax
0x180003fb8  mov     [rsi+20h], eax
0x180003fbb  mov     [rsi+18h], rax
0x180003fbf  add     rsp, 28h
0x180003fc3  pop     rdi
0x180003fc4  pop     rsi
0x180003fc5  pop     rbp
0x180003fc6  pop     rbx
0x180003fc7  retn
```
