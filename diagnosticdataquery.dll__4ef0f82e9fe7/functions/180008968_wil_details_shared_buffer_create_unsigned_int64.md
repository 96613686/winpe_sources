# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008968`
- end: `0x180008a2b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007db0`
- `0x180008a40`

## callees

- `0x180008968`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008993`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008993`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800089cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800089cc`

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
0x180008968  push    rbx
0x18000896a  push    rbp
0x18000896b  push    rsi
0x18000896c  push    rdi
0x18000896d  sub     rsp, 28h
0x180008971  mov     rbp, rdx
0x180008974  mov     rdi, rcx
0x180008977  test    rdx, rdx
0x18000897a  jnz     short loc_1800089BD
0x18000897c  mov     rcx, [rcx]
0x18000897f  test    rcx, rcx
0x180008982  jz      short loc_1800089B6
0x180008984  or      eax, 0FFFFFFFFh
0x180008987  lock xadd [rcx], eax
0x18000898b  cmp     eax, 1
0x18000898e  jnz     short loc_1800089A7
0x180008990  mov     rbx, [rdi]
0x180008993  call    cs:__imp_GetProcessHeap
0x180008999  mov     r8, rbx; lpMem
0x18000899c  xor     edx, edx; dwFlags
0x18000899e  mov     rcx, rax; hHeap
0x1800089a1  call    cs:__imp_HeapFree
0x1800089a7  mov     qword ptr [rdi], 0
0x1800089ae  mov     qword ptr [rdi+8], 0
0x1800089b6  mov     eax, 1
0x1800089bb  jmp     short loc_180008A22
0x1800089bd  call    cs:__imp_GetProcessHeap
0x1800089c3  lea     r8, [rbp+4]; dwBytes
0x1800089c7  xor     edx, edx; dwFlags
0x1800089c9  mov     rcx, rax; hHeap
0x1800089cc  call    cs:__imp_HeapAlloc
0x1800089d2  mov     rsi, rax
0x1800089d5  test    rax, rax
0x1800089d8  jz      short loc_180008A22
0x1800089da  mov     dword ptr [rax], 0
0x1800089e0  mov     rcx, [rdi]
0x1800089e3  test    rcx, rcx
0x1800089e6  jz      short loc_180008A13
0x1800089e8  or      eax, 0FFFFFFFFh
0x1800089eb  lock xadd [rcx], eax
0x1800089ef  cmp     eax, 1
0x1800089f2  jnz     short loc_180008A0B
0x1800089f4  mov     rbx, [rdi]
0x1800089f7  call    cs:__imp_GetProcessHeap
0x1800089fd  mov     r8, rbx; lpMem
0x180008a00  xor     edx, edx; dwFlags
0x180008a02  mov     rcx, rax; hHeap
0x180008a05  call    cs:__imp_HeapFree
0x180008a0b  mov     qword ptr [rdi+8], 0
0x180008a13  mov     [rdi], rsi
0x180008a16  mov     eax, 1
0x180008a1b  mov     [rdi+8], rbp
0x180008a1f  lock add [rsi], eax
0x180008a22  add     rsp, 28h
0x180008a26  pop     rdi
0x180008a27  pop     rsi
0x180008a28  pop     rbp
0x180008a29  pop     rbx
0x180008a2a  retn
```
