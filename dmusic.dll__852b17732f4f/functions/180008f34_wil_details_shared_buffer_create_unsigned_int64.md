# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008f34`
- end: `0x180008ff7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a98`
- `0x1800090f0`

## callees

- `0x180008f34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008f98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fc3`

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
0x180008f34  push    rbx
0x180008f36  push    rbp
0x180008f37  push    rsi
0x180008f38  push    rdi
0x180008f39  sub     rsp, 28h
0x180008f3d  mov     rbp, rdx
0x180008f40  mov     rdi, rcx
0x180008f43  test    rdx, rdx
0x180008f46  jnz     short loc_180008F89
0x180008f48  mov     rcx, [rcx]
0x180008f4b  test    rcx, rcx
0x180008f4e  jz      short loc_180008F82
0x180008f50  or      eax, 0FFFFFFFFh
0x180008f53  lock xadd [rcx], eax
0x180008f57  cmp     eax, 1
0x180008f5a  jnz     short loc_180008F73
0x180008f5c  mov     rbx, [rdi]
0x180008f5f  call    cs:__imp_GetProcessHeap
0x180008f65  mov     r8, rbx; lpMem
0x180008f68  xor     edx, edx; dwFlags
0x180008f6a  mov     rcx, rax; hHeap
0x180008f6d  call    cs:__imp_HeapFree
0x180008f73  mov     qword ptr [rdi], 0
0x180008f7a  mov     qword ptr [rdi+8], 0
0x180008f82  mov     eax, 1
0x180008f87  jmp     short loc_180008FEE
0x180008f89  call    cs:__imp_GetProcessHeap
0x180008f8f  lea     r8, [rbp+4]; dwBytes
0x180008f93  xor     edx, edx; dwFlags
0x180008f95  mov     rcx, rax; hHeap
0x180008f98  call    cs:__imp_HeapAlloc
0x180008f9e  mov     rsi, rax
0x180008fa1  test    rax, rax
0x180008fa4  jz      short loc_180008FEE
0x180008fa6  mov     dword ptr [rax], 0
0x180008fac  mov     rcx, [rdi]
0x180008faf  test    rcx, rcx
0x180008fb2  jz      short loc_180008FDF
0x180008fb4  or      eax, 0FFFFFFFFh
0x180008fb7  lock xadd [rcx], eax
0x180008fbb  cmp     eax, 1
0x180008fbe  jnz     short loc_180008FD7
0x180008fc0  mov     rbx, [rdi]
0x180008fc3  call    cs:__imp_GetProcessHeap
0x180008fc9  mov     r8, rbx; lpMem
0x180008fcc  xor     edx, edx; dwFlags
0x180008fce  mov     rcx, rax; hHeap
0x180008fd1  call    cs:__imp_HeapFree
0x180008fd7  mov     qword ptr [rdi+8], 0
0x180008fdf  mov     [rdi], rsi
0x180008fe2  mov     eax, 1
0x180008fe7  mov     [rdi+8], rbp
0x180008feb  lock add [rsi], eax
0x180008fee  add     rsp, 28h
0x180008ff2  pop     rdi
0x180008ff3  pop     rsi
0x180008ff4  pop     rbp
0x180008ff5  pop     rbx
0x180008ff6  retn
```
