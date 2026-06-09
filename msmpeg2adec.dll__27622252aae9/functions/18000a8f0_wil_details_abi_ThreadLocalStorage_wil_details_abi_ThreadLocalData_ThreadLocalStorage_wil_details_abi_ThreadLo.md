# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000a8f0`
- end: `0x18000a97c`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800134a0`

## callees

- `0x18000a8f0`
- `0x18000adc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a944`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a930`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a930`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rdi
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
0x18000a8f0  mov     [rsp+arg_18], rbp
0x18000a8f5  push    rsi
0x18000a8f6  sub     rsp, 20h
0x18000a8fa  lea     rbp, [rcx+50h]
0x18000a8fe  mov     rsi, rcx
0x18000a901  cmp     rcx, rbp
0x18000a904  jz      short loc_18000A970
0x18000a906  mov     [rsp+28h+arg_0], rbx
0x18000a90b  mov     [rsp+28h+arg_8], rdi
0x18000a910  mov     [rsp+28h+arg_10], r14
0x18000a915  xor     r14d, r14d
0x18000a918  mov     rbx, [rsi]
0x18000a91b  test    rbx, rbx
0x18000a91e  jz      short loc_18000A955
0x18000a920  mov     rdi, rbx
0x18000a923  mov     rbx, [rbx+8]
0x18000a927  lea     rcx, [rdi+10h]; this
0x18000a92b  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000a930  call    cs:__imp_GetProcessHeap
0x18000a937  nop     dword ptr [rax+rax+00h]
0x18000a93c  mov     r8, rdi; lpMem
0x18000a93f  xor     edx, edx; dwFlags
0x18000a941  mov     rcx, rax; hHeap
0x18000a944  call    cs:__imp_HeapFree
0x18000a94b  nop     dword ptr [rax+rax+00h]
0x18000a950  test    rbx, rbx
0x18000a953  jnz     short loc_18000A920
0x18000a955  mov     [rsi], r14
0x18000a958  add     rsi, 8
0x18000a95c  cmp     rsi, rbp
0x18000a95f  jnz     short loc_18000A918
0x18000a961  mov     r14, [rsp+28h+arg_10]
0x18000a966  mov     rdi, [rsp+28h+arg_8]
0x18000a96b  mov     rbx, [rsp+28h+arg_0]
0x18000a970  mov     rbp, [rsp+28h+arg_18]
0x18000a975  add     rsp, 20h
0x18000a979  pop     rsi
0x18000a97a  retn
```
