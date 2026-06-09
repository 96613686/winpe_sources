# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007404`
- end: `0x1800074c7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800067c4`
- `0x1800074d0`

## callees

- `0x180007404`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000743d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800074a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000743d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800074a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007468`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007468`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000742f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007493`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000742f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007459`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007493`

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
0x180007404  push    rbx
0x180007406  push    rbp
0x180007407  push    rsi
0x180007408  push    rdi
0x180007409  sub     rsp, 28h
0x18000740d  mov     rbp, rdx
0x180007410  mov     rdi, rcx
0x180007413  test    rdx, rdx
0x180007416  jnz     short loc_180007459
0x180007418  mov     rcx, [rcx]
0x18000741b  test    rcx, rcx
0x18000741e  jz      short loc_180007452
0x180007420  or      eax, 0FFFFFFFFh
0x180007423  lock xadd [rcx], eax
0x180007427  cmp     eax, 1
0x18000742a  jnz     short loc_180007443
0x18000742c  mov     rbx, [rdi]
0x18000742f  call    cs:__imp_GetProcessHeap
0x180007435  mov     r8, rbx; lpMem
0x180007438  xor     edx, edx; dwFlags
0x18000743a  mov     rcx, rax; hHeap
0x18000743d  call    cs:__imp_HeapFree
0x180007443  mov     qword ptr [rdi], 0
0x18000744a  mov     qword ptr [rdi+8], 0
0x180007452  mov     eax, 1
0x180007457  jmp     short loc_1800074BE
0x180007459  call    cs:__imp_GetProcessHeap
0x18000745f  lea     r8, [rbp+4]; dwBytes
0x180007463  xor     edx, edx; dwFlags
0x180007465  mov     rcx, rax; hHeap
0x180007468  call    cs:__imp_HeapAlloc
0x18000746e  mov     rsi, rax
0x180007471  test    rax, rax
0x180007474  jz      short loc_1800074BE
0x180007476  mov     dword ptr [rax], 0
0x18000747c  mov     rcx, [rdi]
0x18000747f  test    rcx, rcx
0x180007482  jz      short loc_1800074AF
0x180007484  or      eax, 0FFFFFFFFh
0x180007487  lock xadd [rcx], eax
0x18000748b  cmp     eax, 1
0x18000748e  jnz     short loc_1800074A7
0x180007490  mov     rbx, [rdi]
0x180007493  call    cs:__imp_GetProcessHeap
0x180007499  mov     r8, rbx; lpMem
0x18000749c  xor     edx, edx; dwFlags
0x18000749e  mov     rcx, rax; hHeap
0x1800074a1  call    cs:__imp_HeapFree
0x1800074a7  mov     qword ptr [rdi+8], 0
0x1800074af  mov     [rdi], rsi
0x1800074b2  mov     eax, 1
0x1800074b7  mov     [rdi+8], rbp
0x1800074bb  lock add [rsi], eax
0x1800074be  add     rsp, 28h
0x1800074c2  pop     rdi
0x1800074c3  pop     rsi
0x1800074c4  pop     rbp
0x1800074c5  pop     rbx
0x1800074c6  retn
```
