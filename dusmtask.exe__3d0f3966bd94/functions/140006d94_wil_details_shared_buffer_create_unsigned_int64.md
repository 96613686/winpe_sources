# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140006d94`
- end: `0x140006e57`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005cd4`
- `0x140006e60`

## callees

- `0x140006d94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006dbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006de9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006e23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006dbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006de9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006e23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006dcd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006e31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006dcd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006e31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006df8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006df8`

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
0x140006d94  push    rbx
0x140006d96  push    rbp
0x140006d97  push    rsi
0x140006d98  push    rdi
0x140006d99  sub     rsp, 28h
0x140006d9d  mov     rbp, rdx
0x140006da0  mov     rdi, rcx
0x140006da3  test    rdx, rdx
0x140006da6  jnz     short loc_140006DE9
0x140006da8  mov     rcx, [rcx]
0x140006dab  test    rcx, rcx
0x140006dae  jz      short loc_140006DE2
0x140006db0  or      eax, 0FFFFFFFFh
0x140006db3  lock xadd [rcx], eax
0x140006db7  cmp     eax, 1
0x140006dba  jnz     short loc_140006DD3
0x140006dbc  mov     rbx, [rdi]
0x140006dbf  call    cs:__imp_GetProcessHeap
0x140006dc5  mov     r8, rbx; lpMem
0x140006dc8  xor     edx, edx; dwFlags
0x140006dca  mov     rcx, rax; hHeap
0x140006dcd  call    cs:__imp_HeapFree
0x140006dd3  mov     qword ptr [rdi], 0
0x140006dda  mov     qword ptr [rdi+8], 0
0x140006de2  mov     eax, 1
0x140006de7  jmp     short loc_140006E4E
0x140006de9  call    cs:__imp_GetProcessHeap
0x140006def  lea     r8, [rbp+4]; dwBytes
0x140006df3  xor     edx, edx; dwFlags
0x140006df5  mov     rcx, rax; hHeap
0x140006df8  call    cs:__imp_HeapAlloc
0x140006dfe  mov     rsi, rax
0x140006e01  test    rax, rax
0x140006e04  jz      short loc_140006E4E
0x140006e06  mov     dword ptr [rax], 0
0x140006e0c  mov     rcx, [rdi]
0x140006e0f  test    rcx, rcx
0x140006e12  jz      short loc_140006E3F
0x140006e14  or      eax, 0FFFFFFFFh
0x140006e17  lock xadd [rcx], eax
0x140006e1b  cmp     eax, 1
0x140006e1e  jnz     short loc_140006E37
0x140006e20  mov     rbx, [rdi]
0x140006e23  call    cs:__imp_GetProcessHeap
0x140006e29  mov     r8, rbx; lpMem
0x140006e2c  xor     edx, edx; dwFlags
0x140006e2e  mov     rcx, rax; hHeap
0x140006e31  call    cs:__imp_HeapFree
0x140006e37  mov     qword ptr [rdi+8], 0
0x140006e3f  mov     [rdi], rsi
0x140006e42  mov     eax, 1
0x140006e47  mov     [rdi+8], rbp
0x140006e4b  lock add [rsi], eax
0x140006e4e  add     rsp, 28h
0x140006e52  pop     rdi
0x140006e53  pop     rsi
0x140006e54  pop     rbp
0x140006e55  pop     rbx
0x140006e56  retn
```
