# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800078e0`
- end: `0x1800079a3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b80`
- `0x1800079b0`

## callees

- `0x1800078e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007919`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000797d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007919`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000797d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007944`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000790b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007935`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000796f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000790b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007935`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000796f`

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
0x1800078e0  push    rbx
0x1800078e2  push    rbp
0x1800078e3  push    rsi
0x1800078e4  push    rdi
0x1800078e5  sub     rsp, 28h
0x1800078e9  mov     rbp, rdx
0x1800078ec  mov     rdi, rcx
0x1800078ef  test    rdx, rdx
0x1800078f2  jnz     short loc_180007935
0x1800078f4  mov     rcx, [rcx]
0x1800078f7  test    rcx, rcx
0x1800078fa  jz      short loc_18000792E
0x1800078fc  or      eax, 0FFFFFFFFh
0x1800078ff  lock xadd [rcx], eax
0x180007903  cmp     eax, 1
0x180007906  jnz     short loc_18000791F
0x180007908  mov     rbx, [rdi]
0x18000790b  call    cs:__imp_GetProcessHeap
0x180007911  mov     r8, rbx; lpMem
0x180007914  xor     edx, edx; dwFlags
0x180007916  mov     rcx, rax; hHeap
0x180007919  call    cs:__imp_HeapFree
0x18000791f  mov     qword ptr [rdi], 0
0x180007926  mov     qword ptr [rdi+8], 0
0x18000792e  mov     eax, 1
0x180007933  jmp     short loc_18000799A
0x180007935  call    cs:__imp_GetProcessHeap
0x18000793b  lea     r8, [rbp+4]; dwBytes
0x18000793f  xor     edx, edx; dwFlags
0x180007941  mov     rcx, rax; hHeap
0x180007944  call    cs:__imp_HeapAlloc
0x18000794a  mov     rsi, rax
0x18000794d  test    rax, rax
0x180007950  jz      short loc_18000799A
0x180007952  mov     dword ptr [rax], 0
0x180007958  mov     rcx, [rdi]
0x18000795b  test    rcx, rcx
0x18000795e  jz      short loc_18000798B
0x180007960  or      eax, 0FFFFFFFFh
0x180007963  lock xadd [rcx], eax
0x180007967  cmp     eax, 1
0x18000796a  jnz     short loc_180007983
0x18000796c  mov     rbx, [rdi]
0x18000796f  call    cs:__imp_GetProcessHeap
0x180007975  mov     r8, rbx; lpMem
0x180007978  xor     edx, edx; dwFlags
0x18000797a  mov     rcx, rax; hHeap
0x18000797d  call    cs:__imp_HeapFree
0x180007983  mov     qword ptr [rdi+8], 0
0x18000798b  mov     [rdi], rsi
0x18000798e  mov     eax, 1
0x180007993  mov     [rdi+8], rbp
0x180007997  lock add [rsi], eax
0x18000799a  add     rsp, 28h
0x18000799e  pop     rdi
0x18000799f  pop     rsi
0x1800079a0  pop     rbp
0x1800079a1  pop     rbx
0x1800079a2  retn
```
