# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002e2c`
- end: `0x180002ec1`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c28`

## callees

- `0x180002e2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ea2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ea2`

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
0x180002e2c  push    rbx
0x180002e2e  push    rbp
0x180002e2f  push    rsi
0x180002e30  push    rdi
0x180002e31  sub     rsp, 28h
0x180002e35  movzx   eax, word ptr [rcx+20h]
0x180002e39  mov     rsi, rcx
0x180002e3c  mov     rdi, [rcx+18h]
0x180002e40  lea     rbp, [rax+rax*4]
0x180002e44  shl     rbp, 4
0x180002e48  add     rbp, rdi
0x180002e4b  jmp     short loc_180002E85
0x180002e4d  mov     rbx, [rdi+40h]
0x180002e51  call    cs:__imp_GetProcessHeap
0x180002e58  nop     dword ptr [rax+rax+00h]
0x180002e5d  mov     r8, rbx; lpMem
0x180002e60  xor     edx, edx; dwFlags
0x180002e62  mov     rcx, rax; hHeap
0x180002e65  call    cs:__imp_HeapFree
0x180002e6c  nop     dword ptr [rax+rax+00h]
0x180002e71  mov     qword ptr [rdi+40h], 0
0x180002e79  mov     qword ptr [rdi+48h], 0
0x180002e81  add     rdi, 50h ; 'P'
0x180002e85  cmp     rdi, rbp
0x180002e88  jnz     short loc_180002E4D
0x180002e8a  mov     rbx, [rsi+18h]
0x180002e8e  call    cs:__imp_GetProcessHeap
0x180002e95  nop     dword ptr [rax+rax+00h]
0x180002e9a  mov     r8, rbx; lpMem
0x180002e9d  xor     edx, edx; dwFlags
0x180002e9f  mov     rcx, rax; hHeap
0x180002ea2  call    cs:__imp_HeapFree
0x180002ea9  nop     dword ptr [rax+rax+00h]
0x180002eae  xor     eax, eax
0x180002eb0  mov     [rsi+20h], eax
0x180002eb3  mov     [rsi+18h], rax
0x180002eb7  add     rsp, 28h
0x180002ebb  pop     rdi
0x180002ebc  pop     rsi
0x180002ebd  pop     rbp
0x180002ebe  pop     rbx
0x180002ebf  retn
```
