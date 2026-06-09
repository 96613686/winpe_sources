# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007924`
- end: `0x1800079e7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006d00`
- `0x1800079f0`

## callees

- `0x180007924`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000795d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000795d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000794f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007979`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000794f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007979`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007988`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007988`

## pseudocode

```c
__int64 __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    result = (__int64)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = (volatile signed __int32 *)result;
    if ( result )
    {
      *(_DWORD *)result = 0;
      if ( *this )
      {
        if ( _InterlockedExchangeAdd(*this, 0xFFFFFFFF) == 1 )
        {
          v10 = *this;
          v11 = GetProcessHeap();
          HeapFree(v11, 0, (LPVOID)v10);
        }
        this[1] = 0;
      }
      *this = v9;
      result = 1;
      this[1] = a2;
      _InterlockedAdd(v9, 1u);
    }
  }
  else
  {
    v4 = *this;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
      {
        v5 = *this;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, (LPVOID)v5);
      }
      *this = 0;
      this[1] = 0;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180007924  push    rbx
0x180007926  push    rbp
0x180007927  push    rsi
0x180007928  push    rdi
0x180007929  sub     rsp, 28h
0x18000792d  mov     rbp, rdx
0x180007930  mov     rdi, rcx
0x180007933  test    rdx, rdx
0x180007936  jnz     short loc_180007979
0x180007938  mov     rcx, [rcx]
0x18000793b  test    rcx, rcx
0x18000793e  jz      short loc_180007972
0x180007940  or      eax, 0FFFFFFFFh
0x180007943  lock xadd [rcx], eax
0x180007947  cmp     eax, 1
0x18000794a  jnz     short loc_180007963
0x18000794c  mov     rbx, [rdi]
0x18000794f  call    cs:__imp_GetProcessHeap
0x180007955  mov     r8, rbx; lpMem
0x180007958  xor     edx, edx; dwFlags
0x18000795a  mov     rcx, rax; hHeap
0x18000795d  call    cs:__imp_HeapFree
0x180007963  mov     qword ptr [rdi], 0
0x18000796a  mov     qword ptr [rdi+8], 0
0x180007972  mov     eax, 1
0x180007977  jmp     short loc_1800079DE
0x180007979  call    cs:__imp_GetProcessHeap
0x18000797f  lea     r8, [rbp+4]; dwBytes
0x180007983  xor     edx, edx; dwFlags
0x180007985  mov     rcx, rax; hHeap
0x180007988  call    cs:__imp_HeapAlloc
0x18000798e  mov     rsi, rax
0x180007991  test    rax, rax
0x180007994  jz      short loc_1800079DE
0x180007996  mov     dword ptr [rax], 0
0x18000799c  mov     rcx, [rdi]
0x18000799f  test    rcx, rcx
0x1800079a2  jz      short loc_1800079CF
0x1800079a4  or      eax, 0FFFFFFFFh
0x1800079a7  lock xadd [rcx], eax
0x1800079ab  cmp     eax, 1
0x1800079ae  jnz     short loc_1800079C7
0x1800079b0  mov     rbx, [rdi]
0x1800079b3  call    cs:__imp_GetProcessHeap
0x1800079b9  mov     r8, rbx; lpMem
0x1800079bc  xor     edx, edx; dwFlags
0x1800079be  mov     rcx, rax; hHeap
0x1800079c1  call    cs:__imp_HeapFree
0x1800079c7  mov     qword ptr [rdi+8], 0
0x1800079cf  mov     [rdi], rsi
0x1800079d2  mov     eax, 1
0x1800079d7  mov     [rdi+8], rbp
0x1800079db  lock add [rsi], eax
0x1800079de  add     rsp, 28h
0x1800079e2  pop     rdi
0x1800079e3  pop     rsi
0x1800079e4  pop     rbp
0x1800079e5  pop     rbx
0x1800079e6  retn
```
