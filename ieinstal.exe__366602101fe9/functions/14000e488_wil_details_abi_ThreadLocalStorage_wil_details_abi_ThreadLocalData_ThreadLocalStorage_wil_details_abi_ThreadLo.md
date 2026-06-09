# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x14000e488`
- end: `0x14000e4ed`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fc1c`

## callees

- `0x14000e488`
- `0x14000e55c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000e4b2`
- `KERNEL32!GetProcessHeap` at `0x14000e4b2`
- `KERNEL32!HeapFree` at `0x14000e4c6`
- `KERNEL32!HeapFree` at `0x14000e4c6`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x14000e488  push    rbx
0x14000e48a  push    rbp
0x14000e48b  push    rsi
0x14000e48c  push    rdi
0x14000e48d  sub     rsp, 28h
0x14000e491  lea     rbp, [rcx+50h]
0x14000e495  mov     rdi, rcx
0x14000e498  cmp     rcx, rbp
0x14000e49b  jz      short loc_14000E4E3
0x14000e49d  mov     rsi, [rdi]
0x14000e4a0  jmp     short loc_14000E4D2
0x14000e4a2  mov     rbx, rsi
0x14000e4a5  mov     rsi, [rsi+8]
0x14000e4a9  lea     rcx, [rbx+10h]; this
0x14000e4ad  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x14000e4b2  call    cs:__imp_GetProcessHeap
0x14000e4b9  nop     dword ptr [rax+rax+00h]
0x14000e4be  mov     r8, rbx; lpMem
0x14000e4c1  xor     edx, edx; dwFlags
0x14000e4c3  mov     rcx, rax; hHeap
0x14000e4c6  call    cs:__imp_HeapFree
0x14000e4cd  nop     dword ptr [rax+rax+00h]
0x14000e4d2  test    rsi, rsi
0x14000e4d5  jnz     short loc_14000E4A2
0x14000e4d7  mov     [rdi], rsi
0x14000e4da  add     rdi, 8
0x14000e4de  cmp     rdi, rbp
0x14000e4e1  jnz     short loc_14000E49D
0x14000e4e3  add     rsp, 28h
0x14000e4e7  pop     rdi
0x14000e4e8  pop     rsi
0x14000e4e9  pop     rbp
0x14000e4ea  pop     rbx
0x14000e4eb  retn
```
