# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1400040c8`
- end: `0x14000417a`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `178`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003bcc`
- `0x1400074a4`
- `0x140007f30`
- `0x1400158ec`

## callees

- `0x1400040c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400040ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000411d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000414e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400040ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000411d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000414e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004131`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004162`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004131`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004162`

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
0x1400040c8  mov     [rsp+arg_0], rbx
0x1400040cd  push    rdi
0x1400040ce  sub     rsp, 20h
0x1400040d2  mov     rdi, [rcx+0B0h]
0x1400040d9  mov     rbx, rcx
0x1400040dc  mov     qword ptr [rcx+0B0h], 0
0x1400040e7  test    rdi, rdi
0x1400040ea  jz      short loc_14000410C
0x1400040ec  call    cs:__imp_GetProcessHeap
0x1400040f3  nop     dword ptr [rax+rax+00h]
0x1400040f8  mov     r8, rdi; lpMem
0x1400040fb  xor     edx, edx; dwFlags
0x1400040fd  mov     rcx, rax; hHeap
0x140004100  call    cs:__imp_HeapFree
0x140004107  nop     dword ptr [rax+rax+00h]
0x14000410c  mov     rdi, [rbx+70h]
0x140004110  mov     qword ptr [rbx+70h], 0
0x140004118  test    rdi, rdi
0x14000411b  jz      short loc_14000413D
0x14000411d  call    cs:__imp_GetProcessHeap
0x140004124  nop     dword ptr [rax+rax+00h]
0x140004129  mov     r8, rdi; lpMem
0x14000412c  xor     edx, edx; dwFlags
0x14000412e  mov     rcx, rax; hHeap
0x140004131  call    cs:__imp_HeapFree
0x140004138  nop     dword ptr [rax+rax+00h]
0x14000413d  mov     rdi, [rbx+30h]
0x140004141  mov     qword ptr [rbx+30h], 0
0x140004149  test    rdi, rdi
0x14000414c  jz      short loc_14000416E
0x14000414e  call    cs:__imp_GetProcessHeap
0x140004155  nop     dword ptr [rax+rax+00h]
0x14000415a  mov     r8, rdi; lpMem
0x14000415d  xor     edx, edx; dwFlags
0x14000415f  mov     rcx, rax; hHeap
0x140004162  call    cs:__imp_HeapFree
0x140004169  nop     dword ptr [rax+rax+00h]
0x14000416e  mov     rbx, [rsp+28h+arg_0]
0x140004173  add     rsp, 20h
0x140004177  pop     rdi
0x140004178  retn
```
