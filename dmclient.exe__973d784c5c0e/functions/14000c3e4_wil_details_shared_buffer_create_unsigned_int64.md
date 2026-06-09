# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000c3e4`
- end: `0x14000c4cc`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b194`
- `0x14000c800`

## callees

- `0x14000c3e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c45a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000c45a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c40f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c48b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c40f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c48b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c49f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c49f`

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
0x14000c3e4  push    rbx
0x14000c3e6  push    rbp
0x14000c3e7  push    rsi
0x14000c3e8  push    rdi
0x14000c3e9  sub     rsp, 28h
0x14000c3ed  mov     rbp, rdx
0x14000c3f0  mov     rdi, rcx
0x14000c3f3  test    rdx, rdx
0x14000c3f6  jnz     short loc_14000C445
0x14000c3f8  mov     rcx, [rcx]
0x14000c3fb  test    rcx, rcx
0x14000c3fe  jz      short loc_14000C43E
0x14000c400  or      eax, 0FFFFFFFFh
0x14000c403  lock xadd [rcx], eax
0x14000c407  cmp     eax, 1
0x14000c40a  jnz     short loc_14000C42F
0x14000c40c  mov     rbx, [rdi]
0x14000c40f  call    cs:__imp_GetProcessHeap
0x14000c416  nop     dword ptr [rax+rax+00h]
0x14000c41b  mov     r8, rbx; lpMem
0x14000c41e  xor     edx, edx; dwFlags
0x14000c420  mov     rcx, rax; hHeap
0x14000c423  call    cs:__imp_HeapFree
0x14000c42a  nop     dword ptr [rax+rax+00h]
0x14000c42f  mov     qword ptr [rdi], 0
0x14000c436  mov     qword ptr [rdi+8], 0
0x14000c43e  mov     eax, 1
0x14000c443  jmp     short loc_14000C4C2
0x14000c445  call    cs:__imp_GetProcessHeap
0x14000c44c  nop     dword ptr [rax+rax+00h]
0x14000c451  lea     r8, [rbp+4]; dwBytes
0x14000c455  xor     edx, edx; dwFlags
0x14000c457  mov     rcx, rax; hHeap
0x14000c45a  call    cs:__imp_HeapAlloc
0x14000c461  nop     dword ptr [rax+rax+00h]
0x14000c466  mov     rsi, rax
0x14000c469  test    rax, rax
0x14000c46c  jz      short loc_14000C4C2
0x14000c46e  mov     dword ptr [rax], 0
0x14000c474  mov     rcx, [rdi]
0x14000c477  test    rcx, rcx
0x14000c47a  jz      short loc_14000C4B3
0x14000c47c  or      eax, 0FFFFFFFFh
0x14000c47f  lock xadd [rcx], eax
0x14000c483  cmp     eax, 1
0x14000c486  jnz     short loc_14000C4AB
0x14000c488  mov     rbx, [rdi]
0x14000c48b  call    cs:__imp_GetProcessHeap
0x14000c492  nop     dword ptr [rax+rax+00h]
0x14000c497  mov     r8, rbx; lpMem
0x14000c49a  xor     edx, edx; dwFlags
0x14000c49c  mov     rcx, rax; hHeap
0x14000c49f  call    cs:__imp_HeapFree
0x14000c4a6  nop     dword ptr [rax+rax+00h]
0x14000c4ab  mov     qword ptr [rdi+8], 0
0x14000c4b3  mov     [rdi], rsi
0x14000c4b6  mov     eax, 1
0x14000c4bb  mov     [rdi+8], rbp
0x14000c4bf  lock add [rsi], eax
0x14000c4c2  add     rsp, 28h
0x14000c4c6  pop     rdi
0x14000c4c7  pop     rsi
0x14000c4c8  pop     rbp
0x14000c4c9  pop     rbx
0x14000c4ca  retn
```
