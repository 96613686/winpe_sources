# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140004ae0`
- end: `0x140004b75`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000476c`

## callees

- `0x140004ae0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004b05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004b42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004b05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004b42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004b19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004b56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004b19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004b56`

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
0x140004ae0  push    rbx
0x140004ae2  push    rbp
0x140004ae3  push    rsi
0x140004ae4  push    rdi
0x140004ae5  sub     rsp, 28h
0x140004ae9  movzx   eax, word ptr [rcx+20h]
0x140004aed  mov     rsi, rcx
0x140004af0  mov     rdi, [rcx+18h]
0x140004af4  lea     rbp, [rax+rax*4]
0x140004af8  shl     rbp, 4
0x140004afc  add     rbp, rdi
0x140004aff  jmp     short loc_140004B39
0x140004b01  mov     rbx, [rdi+40h]
0x140004b05  call    cs:__imp_GetProcessHeap
0x140004b0c  nop     dword ptr [rax+rax+00h]
0x140004b11  mov     r8, rbx; lpMem
0x140004b14  xor     edx, edx; dwFlags
0x140004b16  mov     rcx, rax; hHeap
0x140004b19  call    cs:__imp_HeapFree
0x140004b20  nop     dword ptr [rax+rax+00h]
0x140004b25  mov     qword ptr [rdi+40h], 0
0x140004b2d  mov     qword ptr [rdi+48h], 0
0x140004b35  add     rdi, 50h ; 'P'
0x140004b39  cmp     rdi, rbp
0x140004b3c  jnz     short loc_140004B01
0x140004b3e  mov     rbx, [rsi+18h]
0x140004b42  call    cs:__imp_GetProcessHeap
0x140004b49  nop     dword ptr [rax+rax+00h]
0x140004b4e  mov     r8, rbx; lpMem
0x140004b51  xor     edx, edx; dwFlags
0x140004b53  mov     rcx, rax; hHeap
0x140004b56  call    cs:__imp_HeapFree
0x140004b5d  nop     dword ptr [rax+rax+00h]
0x140004b62  xor     eax, eax
0x140004b64  mov     [rsi+20h], eax
0x140004b67  mov     [rsi+18h], rax
0x140004b6b  add     rsp, 28h
0x140004b6f  pop     rdi
0x140004b70  pop     rsi
0x140004b71  pop     rbp
0x140004b72  pop     rbx
0x140004b73  retn
```
