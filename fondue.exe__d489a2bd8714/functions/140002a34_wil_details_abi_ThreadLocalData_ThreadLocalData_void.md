# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140002a34`
- end: `0x140002ab0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002968`

## callees

- `0x140002a34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002a67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002a98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002a67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002a98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002a59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002a8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002a59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002a8a`

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
0x140002a34  push    rbx
0x140002a36  push    rbp
0x140002a37  push    rsi
0x140002a38  push    rdi
0x140002a39  sub     rsp, 28h
0x140002a3d  movzx   eax, word ptr [rcx+20h]
0x140002a41  mov     rsi, rcx
0x140002a44  mov     rdi, [rcx+18h]
0x140002a48  lea     rbp, [rax+rax*4]
0x140002a4c  shl     rbp, 4
0x140002a50  add     rbp, rdi
0x140002a53  jmp     short loc_140002A81
0x140002a55  mov     rbx, [rdi+40h]
0x140002a59  call    cs:__imp_GetProcessHeap
0x140002a5f  mov     r8, rbx; lpMem
0x140002a62  xor     edx, edx; dwFlags
0x140002a64  mov     rcx, rax; hHeap
0x140002a67  call    cs:__imp_HeapFree
0x140002a6d  mov     qword ptr [rdi+40h], 0
0x140002a75  mov     qword ptr [rdi+48h], 0
0x140002a7d  add     rdi, 50h ; 'P'
0x140002a81  cmp     rdi, rbp
0x140002a84  jnz     short loc_140002A55
0x140002a86  mov     rbx, [rsi+18h]
0x140002a8a  call    cs:__imp_GetProcessHeap
0x140002a90  mov     r8, rbx; lpMem
0x140002a93  xor     edx, edx; dwFlags
0x140002a95  mov     rcx, rax; hHeap
0x140002a98  call    cs:__imp_HeapFree
0x140002a9e  xor     eax, eax
0x140002aa0  mov     [rsi+20h], eax
0x140002aa3  mov     [rsi+18h], rax
0x140002aa7  add     rsp, 28h
0x140002aab  pop     rdi
0x140002aac  pop     rsi
0x140002aad  pop     rbp
0x140002aae  pop     rbx
0x140002aaf  retn
```
