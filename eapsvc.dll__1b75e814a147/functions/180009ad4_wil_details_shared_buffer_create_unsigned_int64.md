# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009ad4`
- end: `0x180009b97`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008688`
- `0x180009c80`

## callees

- `0x180009ad4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b63`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b38`

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
0x180009ad4  push    rbx
0x180009ad6  push    rbp
0x180009ad7  push    rsi
0x180009ad8  push    rdi
0x180009ad9  sub     rsp, 28h
0x180009add  mov     rbp, rdx
0x180009ae0  mov     rdi, rcx
0x180009ae3  test    rdx, rdx
0x180009ae6  jnz     short loc_180009B29
0x180009ae8  mov     rcx, [rcx]
0x180009aeb  test    rcx, rcx
0x180009aee  jz      short loc_180009B22
0x180009af0  or      eax, 0FFFFFFFFh
0x180009af3  lock xadd [rcx], eax
0x180009af7  cmp     eax, 1
0x180009afa  jnz     short loc_180009B13
0x180009afc  mov     rbx, [rdi]
0x180009aff  call    cs:__imp_GetProcessHeap
0x180009b05  mov     r8, rbx; lpMem
0x180009b08  xor     edx, edx; dwFlags
0x180009b0a  mov     rcx, rax; hHeap
0x180009b0d  call    cs:__imp_HeapFree
0x180009b13  mov     qword ptr [rdi], 0
0x180009b1a  mov     qword ptr [rdi+8], 0
0x180009b22  mov     eax, 1
0x180009b27  jmp     short loc_180009B8E
0x180009b29  call    cs:__imp_GetProcessHeap
0x180009b2f  lea     r8, [rbp+4]; dwBytes
0x180009b33  xor     edx, edx; dwFlags
0x180009b35  mov     rcx, rax; hHeap
0x180009b38  call    cs:__imp_HeapAlloc
0x180009b3e  mov     rsi, rax
0x180009b41  test    rax, rax
0x180009b44  jz      short loc_180009B8E
0x180009b46  mov     dword ptr [rax], 0
0x180009b4c  mov     rcx, [rdi]
0x180009b4f  test    rcx, rcx
0x180009b52  jz      short loc_180009B7F
0x180009b54  or      eax, 0FFFFFFFFh
0x180009b57  lock xadd [rcx], eax
0x180009b5b  cmp     eax, 1
0x180009b5e  jnz     short loc_180009B77
0x180009b60  mov     rbx, [rdi]
0x180009b63  call    cs:__imp_GetProcessHeap
0x180009b69  mov     r8, rbx; lpMem
0x180009b6c  xor     edx, edx; dwFlags
0x180009b6e  mov     rcx, rax; hHeap
0x180009b71  call    cs:__imp_HeapFree
0x180009b77  mov     qword ptr [rdi+8], 0
0x180009b7f  mov     [rdi], rsi
0x180009b82  mov     eax, 1
0x180009b87  mov     [rdi+8], rbp
0x180009b8b  lock add [rsi], eax
0x180009b8e  add     rsp, 28h
0x180009b92  pop     rdi
0x180009b93  pop     rsi
0x180009b94  pop     rbp
0x180009b95  pop     rbx
0x180009b96  retn
```
