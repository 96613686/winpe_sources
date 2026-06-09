# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140005490`
- end: `0x14000551d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004fd0`
- `0x140008a40`
- `0x140009550`
- `0x140013338`

## callees

- `0x140005490`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400054b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400054d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400054fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400054b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400054d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400054fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400054c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400054e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000550c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400054c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400054e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000550c`

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
0x140005490  mov     [rsp+arg_0], rbx
0x140005495  push    rdi
0x140005496  sub     rsp, 20h
0x14000549a  mov     rdi, [rcx+0B0h]
0x1400054a1  mov     rbx, rcx
0x1400054a4  mov     qword ptr [rcx+0B0h], 0
0x1400054af  test    rdi, rdi
0x1400054b2  jz      short loc_1400054C8
0x1400054b4  call    cs:__imp_GetProcessHeap
0x1400054ba  mov     r8, rdi; lpMem
0x1400054bd  xor     edx, edx; dwFlags
0x1400054bf  mov     rcx, rax; hHeap
0x1400054c2  call    cs:__imp_HeapFree
0x1400054c8  mov     rdi, [rbx+70h]
0x1400054cc  mov     qword ptr [rbx+70h], 0
0x1400054d4  test    rdi, rdi
0x1400054d7  jz      short loc_1400054ED
0x1400054d9  call    cs:__imp_GetProcessHeap
0x1400054df  mov     r8, rdi; lpMem
0x1400054e2  xor     edx, edx; dwFlags
0x1400054e4  mov     rcx, rax; hHeap
0x1400054e7  call    cs:__imp_HeapFree
0x1400054ed  mov     rdi, [rbx+30h]
0x1400054f1  mov     qword ptr [rbx+30h], 0
0x1400054f9  test    rdi, rdi
0x1400054fc  jz      short loc_140005512
0x1400054fe  call    cs:__imp_GetProcessHeap
0x140005504  mov     r8, rdi; lpMem
0x140005507  xor     edx, edx; dwFlags
0x140005509  mov     rcx, rax; hHeap
0x14000550c  call    cs:__imp_HeapFree
0x140005512  mov     rbx, [rsp+28h+arg_0]
0x140005517  add     rsp, 20h
0x14000551b  pop     rdi
0x14000551c  retn
```
