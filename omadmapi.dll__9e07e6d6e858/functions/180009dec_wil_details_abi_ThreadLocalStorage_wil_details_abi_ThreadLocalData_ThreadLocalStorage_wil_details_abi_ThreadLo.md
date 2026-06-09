# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180009dec`
- end: `0x180009e51`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011538`

## callees

- `0x180009dec`
- `0x18000a5b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e16`

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
0x180009dec  push    rbx
0x180009dee  push    rbp
0x180009def  push    rsi
0x180009df0  push    rdi
0x180009df1  sub     rsp, 28h
0x180009df5  lea     rbp, [rcx+50h]
0x180009df9  mov     rdi, rcx
0x180009dfc  cmp     rcx, rbp
0x180009dff  jz      short loc_180009E47
0x180009e01  mov     rsi, [rdi]
0x180009e04  jmp     short loc_180009E36
0x180009e06  mov     rbx, rsi
0x180009e09  mov     rsi, [rsi+8]
0x180009e0d  lea     rcx, [rbx+10h]; this
0x180009e11  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180009e16  call    cs:__imp_GetProcessHeap
0x180009e1d  nop     dword ptr [rax+rax+00h]
0x180009e22  mov     r8, rbx; lpMem
0x180009e25  xor     edx, edx; dwFlags
0x180009e27  mov     rcx, rax; hHeap
0x180009e2a  call    cs:__imp_HeapFree
0x180009e31  nop     dword ptr [rax+rax+00h]
0x180009e36  test    rsi, rsi
0x180009e39  jnz     short loc_180009E06
0x180009e3b  mov     [rdi], rsi
0x180009e3e  add     rdi, 8
0x180009e42  cmp     rdi, rbp
0x180009e45  jnz     short loc_180009E01
0x180009e47  add     rsp, 28h
0x180009e4b  pop     rdi
0x180009e4c  pop     rsi
0x180009e4d  pop     rbp
0x180009e4e  pop     rbx
0x180009e4f  retn
```
