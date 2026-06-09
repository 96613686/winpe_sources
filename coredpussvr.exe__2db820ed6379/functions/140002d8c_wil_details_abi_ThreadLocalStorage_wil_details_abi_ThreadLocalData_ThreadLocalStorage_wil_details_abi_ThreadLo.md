# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140002d8c`
- end: `0x140002df1`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400047e4`

## callees

- `0x140002d8c`
- `0x140002f64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002dca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002dca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002db6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002db6`

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
0x140002d8c  push    rbx
0x140002d8e  push    rbp
0x140002d8f  push    rsi
0x140002d90  push    rdi
0x140002d91  sub     rsp, 28h
0x140002d95  lea     rbp, [rcx+50h]
0x140002d99  mov     rdi, rcx
0x140002d9c  cmp     rcx, rbp
0x140002d9f  jz      short loc_140002DE7
0x140002da1  mov     rsi, [rdi]
0x140002da4  jmp     short loc_140002DD6
0x140002da6  mov     rbx, rsi
0x140002da9  mov     rsi, [rsi+8]
0x140002dad  lea     rcx, [rbx+10h]; this
0x140002db1  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x140002db6  call    cs:__imp_GetProcessHeap
0x140002dbd  nop     dword ptr [rax+rax+00h]
0x140002dc2  mov     r8, rbx; lpMem
0x140002dc5  xor     edx, edx; dwFlags
0x140002dc7  mov     rcx, rax; hHeap
0x140002dca  call    cs:__imp_HeapFree
0x140002dd1  nop     dword ptr [rax+rax+00h]
0x140002dd6  test    rsi, rsi
0x140002dd9  jnz     short loc_140002DA6
0x140002ddb  mov     [rdi], rsi
0x140002dde  add     rdi, 8
0x140002de2  cmp     rdi, rbp
0x140002de5  jnz     short loc_140002DA1
0x140002de7  add     rsp, 28h
0x140002deb  pop     rdi
0x140002dec  pop     rsi
0x140002ded  pop     rbp
0x140002dee  pop     rbx
0x140002def  retn
```
