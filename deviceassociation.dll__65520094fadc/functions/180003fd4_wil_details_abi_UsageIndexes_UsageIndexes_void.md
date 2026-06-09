# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180003fd4`
- end: `0x180004061`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c84`
- `0x18000681c`
- `0x1800072d0`

## callees

- `0x180003fd4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ff8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000401d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004042`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ff8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000401d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004042`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004006`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000402b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004050`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004006`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000402b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004050`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  v4 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
}

```

## disassembly

```asm
0x180003fd4  mov     [rsp+arg_0], rbx
0x180003fd9  push    rdi
0x180003fda  sub     rsp, 20h
0x180003fde  mov     rdi, [rcx+0B0h]
0x180003fe5  mov     rbx, rcx
0x180003fe8  mov     qword ptr [rcx+0B0h], 0
0x180003ff3  test    rdi, rdi
0x180003ff6  jz      short loc_18000400C
0x180003ff8  call    cs:__imp_GetProcessHeap
0x180003ffe  mov     r8, rdi; lpMem
0x180004001  xor     edx, edx; dwFlags
0x180004003  mov     rcx, rax; hHeap
0x180004006  call    cs:__imp_HeapFree
0x18000400c  mov     rdi, [rbx+70h]
0x180004010  mov     qword ptr [rbx+70h], 0
0x180004018  test    rdi, rdi
0x18000401b  jz      short loc_180004031
0x18000401d  call    cs:__imp_GetProcessHeap
0x180004023  mov     r8, rdi; lpMem
0x180004026  xor     edx, edx; dwFlags
0x180004028  mov     rcx, rax; hHeap
0x18000402b  call    cs:__imp_HeapFree
0x180004031  mov     rdi, [rbx+30h]
0x180004035  mov     qword ptr [rbx+30h], 0
0x18000403d  test    rdi, rdi
0x180004040  jz      short loc_180004056
0x180004042  call    cs:__imp_GetProcessHeap
0x180004048  mov     r8, rdi; lpMem
0x18000404b  xor     edx, edx; dwFlags
0x18000404d  mov     rcx, rax; hHeap
0x180004050  call    cs:__imp_HeapFree
0x180004056  mov     rbx, [rsp+28h+arg_0]
0x18000405b  add     rsp, 20h
0x18000405f  pop     rdi
0x180004060  retn
```
