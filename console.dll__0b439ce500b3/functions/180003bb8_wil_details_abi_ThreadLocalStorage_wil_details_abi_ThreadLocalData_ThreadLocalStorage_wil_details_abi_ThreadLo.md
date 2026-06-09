# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003bb8`
- end: `0x180003c1d`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b24`

## callees

- `0x180003bb8`
- `0x180003f3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003bf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003bf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003be2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003be2`

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
0x180003bb8  push    rbx
0x180003bba  push    rbp
0x180003bbb  push    rsi
0x180003bbc  push    rdi
0x180003bbd  sub     rsp, 28h
0x180003bc1  lea     rbp, [rcx+50h]
0x180003bc5  mov     rdi, rcx
0x180003bc8  cmp     rcx, rbp
0x180003bcb  jz      short loc_180003C13
0x180003bcd  mov     rsi, [rdi]
0x180003bd0  jmp     short loc_180003C02
0x180003bd2  mov     rbx, rsi
0x180003bd5  mov     rsi, [rsi+8]
0x180003bd9  lea     rcx, [rbx+10h]; this
0x180003bdd  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x180003be2  call    cs:__imp_GetProcessHeap
0x180003be9  nop     dword ptr [rax+rax+00h]
0x180003bee  mov     r8, rbx; lpMem
0x180003bf1  xor     edx, edx; dwFlags
0x180003bf3  mov     rcx, rax; hHeap
0x180003bf6  call    cs:__imp_HeapFree
0x180003bfd  nop     dword ptr [rax+rax+00h]
0x180003c02  test    rsi, rsi
0x180003c05  jnz     short loc_180003BD2
0x180003c07  mov     [rdi], rsi
0x180003c0a  add     rdi, 8
0x180003c0e  cmp     rdi, rbp
0x180003c11  jnz     short loc_180003BCD
0x180003c13  add     rsp, 28h
0x180003c17  pop     rdi
0x180003c18  pop     rsi
0x180003c19  pop     rbp
0x180003c1a  pop     rbx
0x180003c1b  retn
```
