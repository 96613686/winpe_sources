# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003ca0`
- end: `0x180003d1c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ae8`

## callees

- `0x180003ca0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d04`

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
0x180003ca0  push    rbx
0x180003ca2  push    rbp
0x180003ca3  push    rsi
0x180003ca4  push    rdi
0x180003ca5  sub     rsp, 28h
0x180003ca9  movzx   eax, word ptr [rcx+20h]
0x180003cad  mov     rsi, rcx
0x180003cb0  mov     rdi, [rcx+18h]
0x180003cb4  lea     rbp, [rax+rax*4]
0x180003cb8  shl     rbp, 4
0x180003cbc  add     rbp, rdi
0x180003cbf  jmp     short loc_180003CED
0x180003cc1  mov     rbx, [rdi+40h]
0x180003cc5  call    cs:__imp_GetProcessHeap
0x180003ccb  mov     r8, rbx; lpMem
0x180003cce  xor     edx, edx; dwFlags
0x180003cd0  mov     rcx, rax; hHeap
0x180003cd3  call    cs:__imp_HeapFree
0x180003cd9  mov     qword ptr [rdi+40h], 0
0x180003ce1  mov     qword ptr [rdi+48h], 0
0x180003ce9  add     rdi, 50h ; 'P'
0x180003ced  cmp     rdi, rbp
0x180003cf0  jnz     short loc_180003CC1
0x180003cf2  mov     rbx, [rsi+18h]
0x180003cf6  call    cs:__imp_GetProcessHeap
0x180003cfc  mov     r8, rbx; lpMem
0x180003cff  xor     edx, edx; dwFlags
0x180003d01  mov     rcx, rax; hHeap
0x180003d04  call    cs:__imp_HeapFree
0x180003d0a  xor     eax, eax
0x180003d0c  mov     [rsi+20h], eax
0x180003d0f  mov     [rsi+18h], rax
0x180003d13  add     rsp, 28h
0x180003d17  pop     rdi
0x180003d18  pop     rsi
0x180003d19  pop     rbp
0x180003d1a  pop     rbx
0x180003d1b  retn
```
