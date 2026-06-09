# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180004830`
- end: `0x180004895`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006664`

## callees

- `0x180004830`
- `0x180004a64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000486e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000486e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000485a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000485a`

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
0x180004830  push    rbx
0x180004832  push    rbp
0x180004833  push    rsi
0x180004834  push    rdi
0x180004835  sub     rsp, 28h
0x180004839  lea     rbp, [rcx+50h]
0x18000483d  mov     rdi, rcx
0x180004840  cmp     rcx, rbp
0x180004843  jz      short loc_18000488B
0x180004845  mov     rsi, [rdi]
0x180004848  jmp     short loc_18000487A
0x18000484a  mov     rbx, rsi
0x18000484d  mov     rsi, [rsi+8]
0x180004851  lea     rcx, [rbx+10h]; this
0x180004855  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000485a  call    cs:__imp_GetProcessHeap
0x180004861  nop     dword ptr [rax+rax+00h]
0x180004866  mov     r8, rbx; lpMem
0x180004869  xor     edx, edx; dwFlags
0x18000486b  mov     rcx, rax; hHeap
0x18000486e  call    cs:__imp_HeapFree
0x180004875  nop     dword ptr [rax+rax+00h]
0x18000487a  test    rsi, rsi
0x18000487d  jnz     short loc_18000484A
0x18000487f  mov     [rdi], rsi
0x180004882  add     rdi, 8
0x180004886  cmp     rdi, rbp
0x180004889  jnz     short loc_180004845
0x18000488b  add     rsp, 28h
0x18000488f  pop     rdi
0x180004890  pop     rsi
0x180004891  pop     rbp
0x180004892  pop     rbx
0x180004893  retn
```
