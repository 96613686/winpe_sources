# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180009834`
- end: `0x180009899`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b120`

## callees

- `0x180009834`
- `0x180009908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009872`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009872`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000985e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000985e`

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
0x180009834  push    rbx
0x180009836  push    rbp
0x180009837  push    rsi
0x180009838  push    rdi
0x180009839  sub     rsp, 28h
0x18000983d  lea     rbp, [rcx+50h]
0x180009841  mov     rdi, rcx
0x180009844  cmp     rcx, rbp
0x180009847  jz      short loc_18000988F
0x180009849  mov     rsi, [rdi]
0x18000984c  jmp     short loc_18000987E
0x18000984e  mov     rbx, rsi
0x180009851  mov     rsi, [rsi+8]
0x180009855  lea     rcx, [rbx+10h]; this
0x180009859  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000985e  call    cs:__imp_GetProcessHeap
0x180009865  nop     dword ptr [rax+rax+00h]
0x18000986a  mov     r8, rbx; lpMem
0x18000986d  xor     edx, edx; dwFlags
0x18000986f  mov     rcx, rax; hHeap
0x180009872  call    cs:__imp_HeapFree
0x180009879  nop     dword ptr [rax+rax+00h]
0x18000987e  test    rsi, rsi
0x180009881  jnz     short loc_18000984E
0x180009883  mov     [rdi], rsi
0x180009886  add     rdi, 8
0x18000988a  cmp     rdi, rbp
0x18000988d  jnz     short loc_180009849
0x18000988f  add     rsp, 28h
0x180009893  pop     rdi
0x180009894  pop     rsi
0x180009895  pop     rbp
0x180009896  pop     rbx
0x180009897  retn
```
