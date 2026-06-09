# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004a64`
- end: `0x180004af9`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004830`

## callees

- `0x180004a64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ada`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ada`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ac6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ac6`

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
0x180004a64  push    rbx
0x180004a66  push    rbp
0x180004a67  push    rsi
0x180004a68  push    rdi
0x180004a69  sub     rsp, 28h
0x180004a6d  movzx   eax, word ptr [rcx+20h]
0x180004a71  mov     rsi, rcx
0x180004a74  mov     rdi, [rcx+18h]
0x180004a78  lea     rbp, [rax+rax*4]
0x180004a7c  shl     rbp, 4
0x180004a80  add     rbp, rdi
0x180004a83  jmp     short loc_180004ABD
0x180004a85  mov     rbx, [rdi+40h]
0x180004a89  call    cs:__imp_GetProcessHeap
0x180004a90  nop     dword ptr [rax+rax+00h]
0x180004a95  mov     r8, rbx; lpMem
0x180004a98  xor     edx, edx; dwFlags
0x180004a9a  mov     rcx, rax; hHeap
0x180004a9d  call    cs:__imp_HeapFree
0x180004aa4  nop     dword ptr [rax+rax+00h]
0x180004aa9  mov     qword ptr [rdi+40h], 0
0x180004ab1  mov     qword ptr [rdi+48h], 0
0x180004ab9  add     rdi, 50h ; 'P'
0x180004abd  cmp     rdi, rbp
0x180004ac0  jnz     short loc_180004A85
0x180004ac2  mov     rbx, [rsi+18h]
0x180004ac6  call    cs:__imp_GetProcessHeap
0x180004acd  nop     dword ptr [rax+rax+00h]
0x180004ad2  mov     r8, rbx; lpMem
0x180004ad5  xor     edx, edx; dwFlags
0x180004ad7  mov     rcx, rax; hHeap
0x180004ada  call    cs:__imp_HeapFree
0x180004ae1  nop     dword ptr [rax+rax+00h]
0x180004ae6  xor     eax, eax
0x180004ae8  mov     [rsi+20h], eax
0x180004aeb  mov     [rsi+18h], rax
0x180004aef  add     rsp, 28h
0x180004af3  pop     rdi
0x180004af4  pop     rsi
0x180004af5  pop     rbp
0x180004af6  pop     rbx
0x180004af7  retn
```
