# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003f50`
- end: `0x180003fcc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ac4`

## callees

- `0x180003f50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fb4`

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
0x180003f50  push    rbx
0x180003f52  push    rbp
0x180003f53  push    rsi
0x180003f54  push    rdi
0x180003f55  sub     rsp, 28h
0x180003f59  movzx   eax, word ptr [rcx+20h]
0x180003f5d  mov     rsi, rcx
0x180003f60  mov     rdi, [rcx+18h]
0x180003f64  lea     rbp, [rax+rax*4]
0x180003f68  shl     rbp, 4
0x180003f6c  add     rbp, rdi
0x180003f6f  jmp     short loc_180003F9D
0x180003f71  mov     rbx, [rdi+40h]
0x180003f75  call    cs:__imp_GetProcessHeap
0x180003f7b  mov     r8, rbx; lpMem
0x180003f7e  xor     edx, edx; dwFlags
0x180003f80  mov     rcx, rax; hHeap
0x180003f83  call    cs:__imp_HeapFree
0x180003f89  mov     qword ptr [rdi+40h], 0
0x180003f91  mov     qword ptr [rdi+48h], 0
0x180003f99  add     rdi, 50h ; 'P'
0x180003f9d  cmp     rdi, rbp
0x180003fa0  jnz     short loc_180003F71
0x180003fa2  mov     rbx, [rsi+18h]
0x180003fa6  call    cs:__imp_GetProcessHeap
0x180003fac  mov     r8, rbx; lpMem
0x180003faf  xor     edx, edx; dwFlags
0x180003fb1  mov     rcx, rax; hHeap
0x180003fb4  call    cs:__imp_HeapFree
0x180003fba  xor     eax, eax
0x180003fbc  mov     [rsi+20h], eax
0x180003fbf  mov     [rsi+18h], rax
0x180003fc3  add     rsp, 28h
0x180003fc7  pop     rdi
0x180003fc8  pop     rsi
0x180003fc9  pop     rbp
0x180003fca  pop     rbx
0x180003fcb  retn
```
