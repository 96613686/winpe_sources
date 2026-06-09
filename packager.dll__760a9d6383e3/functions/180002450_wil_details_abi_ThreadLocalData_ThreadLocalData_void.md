# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002450`
- end: `0x1800024cc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002384`

## callees

- `0x180002450`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800024b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002483`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800024b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002475`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800024a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002475`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800024a6`

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
0x180002450  push    rbx
0x180002452  push    rbp
0x180002453  push    rsi
0x180002454  push    rdi
0x180002455  sub     rsp, 28h
0x180002459  movzx   eax, word ptr [rcx+20h]
0x18000245d  mov     rsi, rcx
0x180002460  mov     rdi, [rcx+18h]
0x180002464  lea     rbp, [rax+rax*4]
0x180002468  shl     rbp, 4
0x18000246c  add     rbp, rdi
0x18000246f  jmp     short loc_18000249D
0x180002471  mov     rbx, [rdi+40h]
0x180002475  call    cs:__imp_GetProcessHeap
0x18000247b  mov     r8, rbx; lpMem
0x18000247e  xor     edx, edx; dwFlags
0x180002480  mov     rcx, rax; hHeap
0x180002483  call    cs:__imp_HeapFree
0x180002489  mov     qword ptr [rdi+40h], 0
0x180002491  mov     qword ptr [rdi+48h], 0
0x180002499  add     rdi, 50h ; 'P'
0x18000249d  cmp     rdi, rbp
0x1800024a0  jnz     short loc_180002471
0x1800024a2  mov     rbx, [rsi+18h]
0x1800024a6  call    cs:__imp_GetProcessHeap
0x1800024ac  mov     r8, rbx; lpMem
0x1800024af  xor     edx, edx; dwFlags
0x1800024b1  mov     rcx, rax; hHeap
0x1800024b4  call    cs:__imp_HeapFree
0x1800024ba  xor     eax, eax
0x1800024bc  mov     [rsi+20h], eax
0x1800024bf  mov     [rsi+18h], rax
0x1800024c3  add     rsp, 28h
0x1800024c7  pop     rdi
0x1800024c8  pop     rsi
0x1800024c9  pop     rbp
0x1800024ca  pop     rbx
0x1800024cb  retn
```
