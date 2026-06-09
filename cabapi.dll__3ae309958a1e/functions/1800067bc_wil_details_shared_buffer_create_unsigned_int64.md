# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800067bc`
- end: `0x18000687f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005870`
- `0x180006890`

## callees

- `0x1800067bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006820`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006820`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006811`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000684b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006811`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000684b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006859`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006859`

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
0x1800067bc  push    rbx
0x1800067be  push    rbp
0x1800067bf  push    rsi
0x1800067c0  push    rdi
0x1800067c1  sub     rsp, 28h
0x1800067c5  mov     rbp, rdx
0x1800067c8  mov     rdi, rcx
0x1800067cb  test    rdx, rdx
0x1800067ce  jnz     short loc_180006811
0x1800067d0  mov     rcx, [rcx]
0x1800067d3  test    rcx, rcx
0x1800067d6  jz      short loc_18000680A
0x1800067d8  or      eax, 0FFFFFFFFh
0x1800067db  lock xadd [rcx], eax
0x1800067df  cmp     eax, 1
0x1800067e2  jnz     short loc_1800067FB
0x1800067e4  mov     rbx, [rdi]
0x1800067e7  call    cs:__imp_GetProcessHeap
0x1800067ed  mov     r8, rbx; lpMem
0x1800067f0  xor     edx, edx; dwFlags
0x1800067f2  mov     rcx, rax; hHeap
0x1800067f5  call    cs:__imp_HeapFree
0x1800067fb  mov     qword ptr [rdi], 0
0x180006802  mov     qword ptr [rdi+8], 0
0x18000680a  mov     eax, 1
0x18000680f  jmp     short loc_180006876
0x180006811  call    cs:__imp_GetProcessHeap
0x180006817  lea     r8, [rbp+4]; dwBytes
0x18000681b  xor     edx, edx; dwFlags
0x18000681d  mov     rcx, rax; hHeap
0x180006820  call    cs:__imp_HeapAlloc
0x180006826  mov     rsi, rax
0x180006829  test    rax, rax
0x18000682c  jz      short loc_180006876
0x18000682e  mov     dword ptr [rax], 0
0x180006834  mov     rcx, [rdi]
0x180006837  test    rcx, rcx
0x18000683a  jz      short loc_180006867
0x18000683c  or      eax, 0FFFFFFFFh
0x18000683f  lock xadd [rcx], eax
0x180006843  cmp     eax, 1
0x180006846  jnz     short loc_18000685F
0x180006848  mov     rbx, [rdi]
0x18000684b  call    cs:__imp_GetProcessHeap
0x180006851  mov     r8, rbx; lpMem
0x180006854  xor     edx, edx; dwFlags
0x180006856  mov     rcx, rax; hHeap
0x180006859  call    cs:__imp_HeapFree
0x18000685f  mov     qword ptr [rdi+8], 0
0x180006867  mov     [rdi], rsi
0x18000686a  mov     eax, 1
0x18000686f  mov     [rdi+8], rbp
0x180006873  lock add [rsi], eax
0x180006876  add     rsp, 28h
0x18000687a  pop     rdi
0x18000687b  pop     rsi
0x18000687c  pop     rbp
0x18000687d  pop     rbx
0x18000687e  retn
```
