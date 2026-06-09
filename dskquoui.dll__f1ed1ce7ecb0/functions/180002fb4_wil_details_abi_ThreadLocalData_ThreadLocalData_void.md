# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002fb4`
- end: `0x180003030`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dfc`

## callees

- `0x180002fb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000300a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000300a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003018`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003018`

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
0x180002fb4  push    rbx
0x180002fb6  push    rbp
0x180002fb7  push    rsi
0x180002fb8  push    rdi
0x180002fb9  sub     rsp, 28h
0x180002fbd  movzx   eax, word ptr [rcx+20h]
0x180002fc1  mov     rsi, rcx
0x180002fc4  mov     rdi, [rcx+18h]
0x180002fc8  lea     rbp, [rax+rax*4]
0x180002fcc  shl     rbp, 4
0x180002fd0  add     rbp, rdi
0x180002fd3  jmp     short loc_180003001
0x180002fd5  mov     rbx, [rdi+40h]
0x180002fd9  call    cs:__imp_GetProcessHeap
0x180002fdf  mov     r8, rbx; lpMem
0x180002fe2  xor     edx, edx; dwFlags
0x180002fe4  mov     rcx, rax; hHeap
0x180002fe7  call    cs:__imp_HeapFree
0x180002fed  mov     qword ptr [rdi+40h], 0
0x180002ff5  mov     qword ptr [rdi+48h], 0
0x180002ffd  add     rdi, 50h ; 'P'
0x180003001  cmp     rdi, rbp
0x180003004  jnz     short loc_180002FD5
0x180003006  mov     rbx, [rsi+18h]
0x18000300a  call    cs:__imp_GetProcessHeap
0x180003010  mov     r8, rbx; lpMem
0x180003013  xor     edx, edx; dwFlags
0x180003015  mov     rcx, rax; hHeap
0x180003018  call    cs:__imp_HeapFree
0x18000301e  xor     eax, eax
0x180003020  mov     [rsi+20h], eax
0x180003023  mov     [rsi+18h], rax
0x180003027  add     rsp, 28h
0x18000302b  pop     rdi
0x18000302c  pop     rsi
0x18000302d  pop     rbp
0x18000302e  pop     rbx
0x18000302f  retn
```
