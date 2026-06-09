# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18001bf80`
- end: `0x18001bffc`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024834`

## callees

- `0x18001bf80`
- `0x18001c468`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bfb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bfb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bfc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bfc9`

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
0x18001bf80  mov     [rsp+arg_0], rbx
0x18001bf85  mov     [rsp+arg_8], rbp
0x18001bf8a  mov     [rsp+arg_10], rsi
0x18001bf8f  push    rdi
0x18001bf90  sub     rsp, 20h
0x18001bf94  lea     rbp, [rcx+50h]
0x18001bf98  mov     rdi, rcx
0x18001bf9b  cmp     rcx, rbp
0x18001bf9e  jz      short loc_18001BFE6
0x18001bfa0  mov     rsi, [rdi]
0x18001bfa3  jmp     short loc_18001BFD5
0x18001bfa5  mov     rbx, rsi
0x18001bfa8  mov     rsi, [rsi+8]
0x18001bfac  lea     rcx, [rbx+10h]; this
0x18001bfb0  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18001bfb5  call    cs:__imp_GetProcessHeap
0x18001bfbc  nop     dword ptr [rax+rax+00h]
0x18001bfc1  mov     r8, rbx; lpMem
0x18001bfc4  xor     edx, edx; dwFlags
0x18001bfc6  mov     rcx, rax; hHeap
0x18001bfc9  call    cs:__imp_HeapFree
0x18001bfd0  nop     dword ptr [rax+rax+00h]
0x18001bfd5  test    rsi, rsi
0x18001bfd8  jnz     short loc_18001BFA5
0x18001bfda  mov     [rdi], rsi
0x18001bfdd  add     rdi, 8
0x18001bfe1  cmp     rdi, rbp
0x18001bfe4  jnz     short loc_18001BFA0
0x18001bfe6  mov     rbx, [rsp+28h+arg_0]
0x18001bfeb  mov     rbp, [rsp+28h+arg_8]
0x18001bff0  mov     rsi, [rsp+28h+arg_10]
0x18001bff5  add     rsp, 20h
0x18001bff9  pop     rdi
0x18001bffa  retn
```
