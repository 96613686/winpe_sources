# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400049f4`
- end: `0x140004a70`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400046b8`

## callees

- `0x1400049f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004a19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004a4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004a19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004a4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004a27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004a58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004a27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004a58`

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
0x1400049f4  push    rbx
0x1400049f6  push    rbp
0x1400049f7  push    rsi
0x1400049f8  push    rdi
0x1400049f9  sub     rsp, 28h
0x1400049fd  movzx   eax, word ptr [rcx+20h]
0x140004a01  mov     rsi, rcx
0x140004a04  mov     rdi, [rcx+18h]
0x140004a08  lea     rbp, [rax+rax*4]
0x140004a0c  shl     rbp, 4
0x140004a10  add     rbp, rdi
0x140004a13  jmp     short loc_140004A41
0x140004a15  mov     rbx, [rdi+40h]
0x140004a19  call    cs:__imp_GetProcessHeap
0x140004a1f  mov     r8, rbx; lpMem
0x140004a22  xor     edx, edx; dwFlags
0x140004a24  mov     rcx, rax; hHeap
0x140004a27  call    cs:__imp_HeapFree
0x140004a2d  mov     qword ptr [rdi+40h], 0
0x140004a35  mov     qword ptr [rdi+48h], 0
0x140004a3d  add     rdi, 50h ; 'P'
0x140004a41  cmp     rdi, rbp
0x140004a44  jnz     short loc_140004A15
0x140004a46  mov     rbx, [rsi+18h]
0x140004a4a  call    cs:__imp_GetProcessHeap
0x140004a50  mov     r8, rbx; lpMem
0x140004a53  xor     edx, edx; dwFlags
0x140004a55  mov     rcx, rax; hHeap
0x140004a58  call    cs:__imp_HeapFree
0x140004a5e  xor     eax, eax
0x140004a60  mov     [rsi+20h], eax
0x140004a63  mov     [rsi+18h], rax
0x140004a67  add     rsp, 28h
0x140004a6b  pop     rdi
0x140004a6c  pop     rsi
0x140004a6d  pop     rbp
0x140004a6e  pop     rbx
0x140004a6f  retn
```
