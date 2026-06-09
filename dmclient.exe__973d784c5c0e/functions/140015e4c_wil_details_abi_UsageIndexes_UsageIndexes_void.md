# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140015e4c`
- end: `0x140015efe`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `178`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140015b54`
- `0x140017294`
- `0x140017c4c`
- `0x140019be0`

## callees

- `0x140015e4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015e70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ea1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ed2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015e70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ea1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ed2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015e84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015ee6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015e84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140015ee6`

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
0x140015e4c  mov     [rsp+arg_0], rbx
0x140015e51  push    rdi
0x140015e52  sub     rsp, 20h
0x140015e56  mov     rdi, [rcx+0B0h]
0x140015e5d  mov     rbx, rcx
0x140015e60  mov     qword ptr [rcx+0B0h], 0
0x140015e6b  test    rdi, rdi
0x140015e6e  jz      short loc_140015E90
0x140015e70  call    cs:__imp_GetProcessHeap
0x140015e77  nop     dword ptr [rax+rax+00h]
0x140015e7c  mov     r8, rdi; lpMem
0x140015e7f  xor     edx, edx; dwFlags
0x140015e81  mov     rcx, rax; hHeap
0x140015e84  call    cs:__imp_HeapFree
0x140015e8b  nop     dword ptr [rax+rax+00h]
0x140015e90  mov     rdi, [rbx+70h]
0x140015e94  mov     qword ptr [rbx+70h], 0
0x140015e9c  test    rdi, rdi
0x140015e9f  jz      short loc_140015EC1
0x140015ea1  call    cs:__imp_GetProcessHeap
0x140015ea8  nop     dword ptr [rax+rax+00h]
0x140015ead  mov     r8, rdi; lpMem
0x140015eb0  xor     edx, edx; dwFlags
0x140015eb2  mov     rcx, rax; hHeap
0x140015eb5  call    cs:__imp_HeapFree
0x140015ebc  nop     dword ptr [rax+rax+00h]
0x140015ec1  mov     rdi, [rbx+30h]
0x140015ec5  mov     qword ptr [rbx+30h], 0
0x140015ecd  test    rdi, rdi
0x140015ed0  jz      short loc_140015EF2
0x140015ed2  call    cs:__imp_GetProcessHeap
0x140015ed9  nop     dword ptr [rax+rax+00h]
0x140015ede  mov     r8, rdi; lpMem
0x140015ee1  xor     edx, edx; dwFlags
0x140015ee3  mov     rcx, rax; hHeap
0x140015ee6  call    cs:__imp_HeapFree
0x140015eed  nop     dword ptr [rax+rax+00h]
0x140015ef2  mov     rbx, [rsp+28h+arg_0]
0x140015ef7  add     rsp, 20h
0x140015efb  pop     rdi
0x140015efc  retn
```
