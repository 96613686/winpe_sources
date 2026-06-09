# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140002f64`
- end: `0x140002ff9`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d8c`

## callees

- `0x140002f64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002fda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002fda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002fc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002fc6`

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
0x140002f64  push    rbx
0x140002f66  push    rbp
0x140002f67  push    rsi
0x140002f68  push    rdi
0x140002f69  sub     rsp, 28h
0x140002f6d  movzx   eax, word ptr [rcx+20h]
0x140002f71  mov     rsi, rcx
0x140002f74  mov     rdi, [rcx+18h]
0x140002f78  lea     rbp, [rax+rax*4]
0x140002f7c  shl     rbp, 4
0x140002f80  add     rbp, rdi
0x140002f83  jmp     short loc_140002FBD
0x140002f85  mov     rbx, [rdi+40h]
0x140002f89  call    cs:__imp_GetProcessHeap
0x140002f90  nop     dword ptr [rax+rax+00h]
0x140002f95  mov     r8, rbx; lpMem
0x140002f98  xor     edx, edx; dwFlags
0x140002f9a  mov     rcx, rax; hHeap
0x140002f9d  call    cs:__imp_HeapFree
0x140002fa4  nop     dword ptr [rax+rax+00h]
0x140002fa9  mov     qword ptr [rdi+40h], 0
0x140002fb1  mov     qword ptr [rdi+48h], 0
0x140002fb9  add     rdi, 50h ; 'P'
0x140002fbd  cmp     rdi, rbp
0x140002fc0  jnz     short loc_140002F85
0x140002fc2  mov     rbx, [rsi+18h]
0x140002fc6  call    cs:__imp_GetProcessHeap
0x140002fcd  nop     dword ptr [rax+rax+00h]
0x140002fd2  mov     r8, rbx; lpMem
0x140002fd5  xor     edx, edx; dwFlags
0x140002fd7  mov     rcx, rax; hHeap
0x140002fda  call    cs:__imp_HeapFree
0x140002fe1  nop     dword ptr [rax+rax+00h]
0x140002fe6  xor     eax, eax
0x140002fe8  mov     [rsi+20h], eax
0x140002feb  mov     [rsi+18h], rax
0x140002fef  add     rsp, 28h
0x140002ff3  pop     rdi
0x140002ff4  pop     rsi
0x140002ff5  pop     rbp
0x140002ff6  pop     rbx
0x140002ff7  retn
```
