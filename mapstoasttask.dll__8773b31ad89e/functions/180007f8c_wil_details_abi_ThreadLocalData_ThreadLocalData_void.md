# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180007f8c`
- end: `0x180008008`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ec0`

## callees

- `0x180007f8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fe2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fe2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ff0`

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
0x180007f8c  push    rbx
0x180007f8e  push    rbp
0x180007f8f  push    rsi
0x180007f90  push    rdi
0x180007f91  sub     rsp, 28h
0x180007f95  movzx   eax, word ptr [rcx+20h]
0x180007f99  mov     rsi, rcx
0x180007f9c  mov     rdi, [rcx+18h]
0x180007fa0  lea     rbp, [rax+rax*4]
0x180007fa4  shl     rbp, 4
0x180007fa8  add     rbp, rdi
0x180007fab  jmp     short loc_180007FD9
0x180007fad  mov     rbx, [rdi+40h]
0x180007fb1  call    cs:__imp_GetProcessHeap
0x180007fb7  mov     r8, rbx; lpMem
0x180007fba  xor     edx, edx; dwFlags
0x180007fbc  mov     rcx, rax; hHeap
0x180007fbf  call    cs:__imp_HeapFree
0x180007fc5  mov     qword ptr [rdi+40h], 0
0x180007fcd  mov     qword ptr [rdi+48h], 0
0x180007fd5  add     rdi, 50h ; 'P'
0x180007fd9  cmp     rdi, rbp
0x180007fdc  jnz     short loc_180007FAD
0x180007fde  mov     rbx, [rsi+18h]
0x180007fe2  call    cs:__imp_GetProcessHeap
0x180007fe8  mov     r8, rbx; lpMem
0x180007feb  xor     edx, edx; dwFlags
0x180007fed  mov     rcx, rax; hHeap
0x180007ff0  call    cs:__imp_HeapFree
0x180007ff6  xor     eax, eax
0x180007ff8  mov     [rsi+20h], eax
0x180007ffb  mov     [rsi+18h], rax
0x180007fff  add     rsp, 28h
0x180008003  pop     rdi
0x180008004  pop     rsi
0x180008005  pop     rbp
0x180008006  pop     rbx
0x180008007  retn
```
