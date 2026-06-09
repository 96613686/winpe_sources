# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800035f0`
- end: `0x180003685`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000326c`

## callees

- `0x1800035f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003652`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003652`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003629`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003666`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003629`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003666`

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
0x1800035f0  push    rbx
0x1800035f2  push    rbp
0x1800035f3  push    rsi
0x1800035f4  push    rdi
0x1800035f5  sub     rsp, 28h
0x1800035f9  movzx   eax, word ptr [rcx+20h]
0x1800035fd  mov     rsi, rcx
0x180003600  mov     rdi, [rcx+18h]
0x180003604  lea     rbp, [rax+rax*4]
0x180003608  shl     rbp, 4
0x18000360c  add     rbp, rdi
0x18000360f  jmp     short loc_180003649
0x180003611  mov     rbx, [rdi+40h]
0x180003615  call    cs:__imp_GetProcessHeap
0x18000361c  nop     dword ptr [rax+rax+00h]
0x180003621  mov     r8, rbx; lpMem
0x180003624  xor     edx, edx; dwFlags
0x180003626  mov     rcx, rax; hHeap
0x180003629  call    cs:__imp_HeapFree
0x180003630  nop     dword ptr [rax+rax+00h]
0x180003635  mov     qword ptr [rdi+40h], 0
0x18000363d  mov     qword ptr [rdi+48h], 0
0x180003645  add     rdi, 50h ; 'P'
0x180003649  cmp     rdi, rbp
0x18000364c  jnz     short loc_180003611
0x18000364e  mov     rbx, [rsi+18h]
0x180003652  call    cs:__imp_GetProcessHeap
0x180003659  nop     dword ptr [rax+rax+00h]
0x18000365e  mov     r8, rbx; lpMem
0x180003661  xor     edx, edx; dwFlags
0x180003663  mov     rcx, rax; hHeap
0x180003666  call    cs:__imp_HeapFree
0x18000366d  nop     dword ptr [rax+rax+00h]
0x180003672  xor     eax, eax
0x180003674  mov     [rsi+20h], eax
0x180003677  mov     [rsi+18h], rax
0x18000367b  add     rsp, 28h
0x18000367f  pop     rdi
0x180003680  pop     rsi
0x180003681  pop     rbp
0x180003682  pop     rbx
0x180003683  retn
```
