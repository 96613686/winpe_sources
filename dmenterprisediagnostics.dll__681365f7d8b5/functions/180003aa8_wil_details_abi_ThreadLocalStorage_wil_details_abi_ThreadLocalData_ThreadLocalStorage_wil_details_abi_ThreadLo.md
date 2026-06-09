# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003aa8`
- end: `0x180003b0d`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039c0`

## callees

- `0x180003aa8`
- `0x1800041c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ae6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ae6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ad2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ad2`

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
      wil::details_abi::ThreadLocalData::Clear((wil::details_abi::ThreadLocalData *)(v4 + 16));
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
0x180003aa8  push    rbx
0x180003aaa  push    rbp
0x180003aab  push    rsi
0x180003aac  push    rdi
0x180003aad  sub     rsp, 28h
0x180003ab1  lea     rbp, [rcx+50h]
0x180003ab5  mov     rdi, rcx
0x180003ab8  cmp     rcx, rbp
0x180003abb  jz      short loc_180003B03
0x180003abd  mov     rsi, [rdi]
0x180003ac0  jmp     short loc_180003AF2
0x180003ac2  mov     rbx, rsi
0x180003ac5  mov     rsi, [rsi+8]
0x180003ac9  lea     rcx, [rbx+10h]; this
0x180003acd  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x180003ad2  call    cs:__imp_GetProcessHeap
0x180003ad9  nop     dword ptr [rax+rax+00h]
0x180003ade  mov     r8, rbx; lpMem
0x180003ae1  xor     edx, edx; dwFlags
0x180003ae3  mov     rcx, rax; hHeap
0x180003ae6  call    cs:__imp_HeapFree
0x180003aed  nop     dword ptr [rax+rax+00h]
0x180003af2  test    rsi, rsi
0x180003af5  jnz     short loc_180003AC2
0x180003af7  mov     [rdi], rsi
0x180003afa  add     rdi, 8
0x180003afe  cmp     rdi, rbp
0x180003b01  jnz     short loc_180003ABD
0x180003b03  add     rsp, 28h
0x180003b07  pop     rdi
0x180003b08  pop     rsi
0x180003b09  pop     rbp
0x180003b0a  pop     rbx
0x180003b0b  retn
```
