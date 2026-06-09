# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003c40`
- end: `0x140003cbc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039fc`

## callees

- `0x140003c40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003ca4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003ca4`

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
0x140003c40  push    rbx
0x140003c42  push    rbp
0x140003c43  push    rsi
0x140003c44  push    rdi
0x140003c45  sub     rsp, 28h
0x140003c49  movzx   eax, word ptr [rcx+20h]
0x140003c4d  mov     rsi, rcx
0x140003c50  mov     rdi, [rcx+18h]
0x140003c54  lea     rbp, [rax+rax*4]
0x140003c58  shl     rbp, 4
0x140003c5c  add     rbp, rdi
0x140003c5f  jmp     short loc_140003C8D
0x140003c61  mov     rbx, [rdi+40h]
0x140003c65  call    cs:__imp_GetProcessHeap
0x140003c6b  mov     r8, rbx; lpMem
0x140003c6e  xor     edx, edx; dwFlags
0x140003c70  mov     rcx, rax; hHeap
0x140003c73  call    cs:__imp_HeapFree
0x140003c79  mov     qword ptr [rdi+40h], 0
0x140003c81  mov     qword ptr [rdi+48h], 0
0x140003c89  add     rdi, 50h ; 'P'
0x140003c8d  cmp     rdi, rbp
0x140003c90  jnz     short loc_140003C61
0x140003c92  mov     rbx, [rsi+18h]
0x140003c96  call    cs:__imp_GetProcessHeap
0x140003c9c  mov     r8, rbx; lpMem
0x140003c9f  xor     edx, edx; dwFlags
0x140003ca1  mov     rcx, rax; hHeap
0x140003ca4  call    cs:__imp_HeapFree
0x140003caa  xor     eax, eax
0x140003cac  mov     [rsi+20h], eax
0x140003caf  mov     [rsi+18h], rax
0x140003cb3  add     rsp, 28h
0x140003cb7  pop     rdi
0x140003cb8  pop     rsi
0x140003cb9  pop     rbp
0x140003cba  pop     rbx
0x140003cbb  retn
```
