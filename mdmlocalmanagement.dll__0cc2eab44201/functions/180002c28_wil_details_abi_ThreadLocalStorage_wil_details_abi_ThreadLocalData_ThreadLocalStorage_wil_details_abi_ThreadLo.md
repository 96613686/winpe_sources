# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180002c28`
- end: `0x180002c8d`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046c4`

## callees

- `0x180002c28`
- `0x180002e2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c66`

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
0x180002c28  push    rbx
0x180002c2a  push    rbp
0x180002c2b  push    rsi
0x180002c2c  push    rdi
0x180002c2d  sub     rsp, 28h
0x180002c31  lea     rbp, [rcx+50h]
0x180002c35  mov     rdi, rcx
0x180002c38  cmp     rcx, rbp
0x180002c3b  jz      short loc_180002C83
0x180002c3d  mov     rsi, [rdi]
0x180002c40  jmp     short loc_180002C72
0x180002c42  mov     rbx, rsi
0x180002c45  mov     rsi, [rsi+8]
0x180002c49  lea     rcx, [rbx+10h]; this
0x180002c4d  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180002c52  call    cs:__imp_GetProcessHeap
0x180002c59  nop     dword ptr [rax+rax+00h]
0x180002c5e  mov     r8, rbx; lpMem
0x180002c61  xor     edx, edx; dwFlags
0x180002c63  mov     rcx, rax; hHeap
0x180002c66  call    cs:__imp_HeapFree
0x180002c6d  nop     dword ptr [rax+rax+00h]
0x180002c72  test    rsi, rsi
0x180002c75  jnz     short loc_180002C42
0x180002c77  mov     [rdi], rsi
0x180002c7a  add     rdi, 8
0x180002c7e  cmp     rdi, rbp
0x180002c81  jnz     short loc_180002C3D
0x180002c83  add     rsp, 28h
0x180002c87  pop     rdi
0x180002c88  pop     rsi
0x180002c89  pop     rbp
0x180002c8a  pop     rbx
0x180002c8b  retn
```
