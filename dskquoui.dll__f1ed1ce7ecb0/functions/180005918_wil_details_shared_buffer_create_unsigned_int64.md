# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005918`
- end: `0x1800059db`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d30`
- `0x1800059f0`

## callees

- `0x180005918`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000596d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005943`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000596d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000597c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000597c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059b5`

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
0x180005918  push    rbx
0x18000591a  push    rbp
0x18000591b  push    rsi
0x18000591c  push    rdi
0x18000591d  sub     rsp, 28h
0x180005921  mov     rbp, rdx
0x180005924  mov     rdi, rcx
0x180005927  test    rdx, rdx
0x18000592a  jnz     short loc_18000596D
0x18000592c  mov     rcx, [rcx]
0x18000592f  test    rcx, rcx
0x180005932  jz      short loc_180005966
0x180005934  or      eax, 0FFFFFFFFh
0x180005937  lock xadd [rcx], eax
0x18000593b  cmp     eax, 1
0x18000593e  jnz     short loc_180005957
0x180005940  mov     rbx, [rdi]
0x180005943  call    cs:__imp_GetProcessHeap
0x180005949  mov     r8, rbx; lpMem
0x18000594c  xor     edx, edx; dwFlags
0x18000594e  mov     rcx, rax; hHeap
0x180005951  call    cs:__imp_HeapFree
0x180005957  mov     qword ptr [rdi], 0
0x18000595e  mov     qword ptr [rdi+8], 0
0x180005966  mov     eax, 1
0x18000596b  jmp     short loc_1800059D2
0x18000596d  call    cs:__imp_GetProcessHeap
0x180005973  lea     r8, [rbp+4]; dwBytes
0x180005977  xor     edx, edx; dwFlags
0x180005979  mov     rcx, rax; hHeap
0x18000597c  call    cs:__imp_HeapAlloc
0x180005982  mov     rsi, rax
0x180005985  test    rax, rax
0x180005988  jz      short loc_1800059D2
0x18000598a  mov     dword ptr [rax], 0
0x180005990  mov     rcx, [rdi]
0x180005993  test    rcx, rcx
0x180005996  jz      short loc_1800059C3
0x180005998  or      eax, 0FFFFFFFFh
0x18000599b  lock xadd [rcx], eax
0x18000599f  cmp     eax, 1
0x1800059a2  jnz     short loc_1800059BB
0x1800059a4  mov     rbx, [rdi]
0x1800059a7  call    cs:__imp_GetProcessHeap
0x1800059ad  mov     r8, rbx; lpMem
0x1800059b0  xor     edx, edx; dwFlags
0x1800059b2  mov     rcx, rax; hHeap
0x1800059b5  call    cs:__imp_HeapFree
0x1800059bb  mov     qword ptr [rdi+8], 0
0x1800059c3  mov     [rdi], rsi
0x1800059c6  mov     eax, 1
0x1800059cb  mov     [rdi+8], rbp
0x1800059cf  lock add [rsi], eax
0x1800059d2  add     rsp, 28h
0x1800059d6  pop     rdi
0x1800059d7  pop     rsi
0x1800059d8  pop     rbp
0x1800059d9  pop     rbx
0x1800059da  retn
```
