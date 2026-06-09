# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800038ac`
- end: `0x180003928`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000357c`

## callees

- `0x1800038ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003902`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003910`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003910`

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
0x1800038ac  push    rbx
0x1800038ae  push    rbp
0x1800038af  push    rsi
0x1800038b0  push    rdi
0x1800038b1  sub     rsp, 28h
0x1800038b5  movzx   eax, word ptr [rcx+20h]
0x1800038b9  mov     rsi, rcx
0x1800038bc  mov     rdi, [rcx+18h]
0x1800038c0  lea     rbp, [rax+rax*4]
0x1800038c4  shl     rbp, 4
0x1800038c8  add     rbp, rdi
0x1800038cb  jmp     short loc_1800038F9
0x1800038cd  mov     rbx, [rdi+40h]
0x1800038d1  call    cs:__imp_GetProcessHeap
0x1800038d7  mov     r8, rbx; lpMem
0x1800038da  xor     edx, edx; dwFlags
0x1800038dc  mov     rcx, rax; hHeap
0x1800038df  call    cs:__imp_HeapFree
0x1800038e5  mov     qword ptr [rdi+40h], 0
0x1800038ed  mov     qword ptr [rdi+48h], 0
0x1800038f5  add     rdi, 50h ; 'P'
0x1800038f9  cmp     rdi, rbp
0x1800038fc  jnz     short loc_1800038CD
0x1800038fe  mov     rbx, [rsi+18h]
0x180003902  call    cs:__imp_GetProcessHeap
0x180003908  mov     r8, rbx; lpMem
0x18000390b  xor     edx, edx; dwFlags
0x18000390d  mov     rcx, rax; hHeap
0x180003910  call    cs:__imp_HeapFree
0x180003916  xor     eax, eax
0x180003918  mov     [rsi+20h], eax
0x18000391b  mov     [rsi+18h], rax
0x18000391f  add     rsp, 28h
0x180003923  pop     rdi
0x180003924  pop     rsi
0x180003925  pop     rbp
0x180003926  pop     rbx
0x180003927  retn
```
