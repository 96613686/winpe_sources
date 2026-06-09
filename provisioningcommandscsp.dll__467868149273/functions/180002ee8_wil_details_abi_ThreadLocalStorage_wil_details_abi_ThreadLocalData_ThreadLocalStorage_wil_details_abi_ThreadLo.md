# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180002ee8`
- end: `0x180002f4d`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b14`

## callees

- `0x180002ee8`
- `0x1800030bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f12`

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
0x180002ee8  push    rbx
0x180002eea  push    rbp
0x180002eeb  push    rsi
0x180002eec  push    rdi
0x180002eed  sub     rsp, 28h
0x180002ef1  lea     rbp, [rcx+50h]
0x180002ef5  mov     rdi, rcx
0x180002ef8  cmp     rcx, rbp
0x180002efb  jz      short loc_180002F43
0x180002efd  mov     rsi, [rdi]
0x180002f00  jmp     short loc_180002F32
0x180002f02  mov     rbx, rsi
0x180002f05  mov     rsi, [rsi+8]
0x180002f09  lea     rcx, [rbx+10h]; this
0x180002f0d  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180002f12  call    cs:__imp_GetProcessHeap
0x180002f19  nop     dword ptr [rax+rax+00h]
0x180002f1e  mov     r8, rbx; lpMem
0x180002f21  xor     edx, edx; dwFlags
0x180002f23  mov     rcx, rax; hHeap
0x180002f26  call    cs:__imp_HeapFree
0x180002f2d  nop     dword ptr [rax+rax+00h]
0x180002f32  test    rsi, rsi
0x180002f35  jnz     short loc_180002F02
0x180002f37  mov     [rdi], rsi
0x180002f3a  add     rdi, 8
0x180002f3e  cmp     rdi, rbp
0x180002f41  jnz     short loc_180002EFD
0x180002f43  add     rsp, 28h
0x180002f47  pop     rdi
0x180002f48  pop     rsi
0x180002f49  pop     rbp
0x180002f4a  pop     rbx
0x180002f4b  retn
```
