# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140008f74`
- end: `0x140009037`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400079f4`
- `0x140009230`

## callees

- `0x140008f74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009011`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009011`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008fd8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008fd8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008f9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009003`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008f9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009003`

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
0x140008f74  push    rbx
0x140008f76  push    rbp
0x140008f77  push    rsi
0x140008f78  push    rdi
0x140008f79  sub     rsp, 28h
0x140008f7d  mov     rbp, rdx
0x140008f80  mov     rdi, rcx
0x140008f83  test    rdx, rdx
0x140008f86  jnz     short loc_140008FC9
0x140008f88  mov     rcx, [rcx]
0x140008f8b  test    rcx, rcx
0x140008f8e  jz      short loc_140008FC2
0x140008f90  or      eax, 0FFFFFFFFh
0x140008f93  lock xadd [rcx], eax
0x140008f97  cmp     eax, 1
0x140008f9a  jnz     short loc_140008FB3
0x140008f9c  mov     rbx, [rdi]
0x140008f9f  call    cs:__imp_GetProcessHeap
0x140008fa5  mov     r8, rbx; lpMem
0x140008fa8  xor     edx, edx; dwFlags
0x140008faa  mov     rcx, rax; hHeap
0x140008fad  call    cs:__imp_HeapFree
0x140008fb3  mov     qword ptr [rdi], 0
0x140008fba  mov     qword ptr [rdi+8], 0
0x140008fc2  mov     eax, 1
0x140008fc7  jmp     short loc_14000902E
0x140008fc9  call    cs:__imp_GetProcessHeap
0x140008fcf  lea     r8, [rbp+4]; dwBytes
0x140008fd3  xor     edx, edx; dwFlags
0x140008fd5  mov     rcx, rax; hHeap
0x140008fd8  call    cs:__imp_HeapAlloc
0x140008fde  mov     rsi, rax
0x140008fe1  test    rax, rax
0x140008fe4  jz      short loc_14000902E
0x140008fe6  mov     dword ptr [rax], 0
0x140008fec  mov     rcx, [rdi]
0x140008fef  test    rcx, rcx
0x140008ff2  jz      short loc_14000901F
0x140008ff4  or      eax, 0FFFFFFFFh
0x140008ff7  lock xadd [rcx], eax
0x140008ffb  cmp     eax, 1
0x140008ffe  jnz     short loc_140009017
0x140009000  mov     rbx, [rdi]
0x140009003  call    cs:__imp_GetProcessHeap
0x140009009  mov     r8, rbx; lpMem
0x14000900c  xor     edx, edx; dwFlags
0x14000900e  mov     rcx, rax; hHeap
0x140009011  call    cs:__imp_HeapFree
0x140009017  mov     qword ptr [rdi+8], 0
0x14000901f  mov     [rdi], rsi
0x140009022  mov     eax, 1
0x140009027  mov     [rdi+8], rbp
0x14000902b  lock add [rsi], eax
0x14000902e  add     rsp, 28h
0x140009032  pop     rdi
0x140009033  pop     rsi
0x140009034  pop     rbp
0x140009035  pop     rbx
0x140009036  retn
```
