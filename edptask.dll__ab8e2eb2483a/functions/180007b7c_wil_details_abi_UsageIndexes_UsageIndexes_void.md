# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180007b7c`
- end: `0x180007c09`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077fc`
- `0x18000f7e0`
- `0x180010190`
- `0x180013c11`

## callees

- `0x180007b7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bf8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007bea`

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
0x180007b7c  mov     [rsp+arg_0], rbx
0x180007b81  push    rdi
0x180007b82  sub     rsp, 20h
0x180007b86  mov     rdi, [rcx+0B0h]
0x180007b8d  mov     rbx, rcx
0x180007b90  mov     qword ptr [rcx+0B0h], 0
0x180007b9b  test    rdi, rdi
0x180007b9e  jz      short loc_180007BB4
0x180007ba0  call    cs:__imp_GetProcessHeap
0x180007ba6  mov     r8, rdi; lpMem
0x180007ba9  xor     edx, edx; dwFlags
0x180007bab  mov     rcx, rax; hHeap
0x180007bae  call    cs:__imp_HeapFree
0x180007bb4  mov     rdi, [rbx+70h]
0x180007bb8  mov     qword ptr [rbx+70h], 0
0x180007bc0  test    rdi, rdi
0x180007bc3  jz      short loc_180007BD9
0x180007bc5  call    cs:__imp_GetProcessHeap
0x180007bcb  mov     r8, rdi; lpMem
0x180007bce  xor     edx, edx; dwFlags
0x180007bd0  mov     rcx, rax; hHeap
0x180007bd3  call    cs:__imp_HeapFree
0x180007bd9  mov     rdi, [rbx+30h]
0x180007bdd  mov     qword ptr [rbx+30h], 0
0x180007be5  test    rdi, rdi
0x180007be8  jz      short loc_180007BFE
0x180007bea  call    cs:__imp_GetProcessHeap
0x180007bf0  mov     r8, rdi; lpMem
0x180007bf3  xor     edx, edx; dwFlags
0x180007bf5  mov     rcx, rax; hHeap
0x180007bf8  call    cs:__imp_HeapFree
0x180007bfe  mov     rbx, [rsp+28h+arg_0]
0x180007c03  add     rsp, 20h
0x180007c07  pop     rdi
0x180007c08  retn
```
