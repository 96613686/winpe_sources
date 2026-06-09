# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800063f4`
- end: `0x1800064b7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004db0`
- `0x180006b00`

## callees

- `0x1800063f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000641f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006449`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006483`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000641f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006449`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006483`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006458`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006458`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000642d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006491`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000642d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006491`

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
0x1800063f4  push    rbx
0x1800063f6  push    rbp
0x1800063f7  push    rsi
0x1800063f8  push    rdi
0x1800063f9  sub     rsp, 28h
0x1800063fd  mov     rbp, rdx
0x180006400  mov     rdi, rcx
0x180006403  test    rdx, rdx
0x180006406  jnz     short loc_180006449
0x180006408  mov     rcx, [rcx]
0x18000640b  test    rcx, rcx
0x18000640e  jz      short loc_180006442
0x180006410  or      eax, 0FFFFFFFFh
0x180006413  lock xadd [rcx], eax
0x180006417  cmp     eax, 1
0x18000641a  jnz     short loc_180006433
0x18000641c  mov     rbx, [rdi]
0x18000641f  call    cs:__imp_GetProcessHeap
0x180006425  mov     r8, rbx; lpMem
0x180006428  xor     edx, edx; dwFlags
0x18000642a  mov     rcx, rax; hHeap
0x18000642d  call    cs:__imp_HeapFree
0x180006433  mov     qword ptr [rdi], 0
0x18000643a  mov     qword ptr [rdi+8], 0
0x180006442  mov     eax, 1
0x180006447  jmp     short loc_1800064AE
0x180006449  call    cs:__imp_GetProcessHeap
0x18000644f  lea     r8, [rbp+4]; dwBytes
0x180006453  xor     edx, edx; dwFlags
0x180006455  mov     rcx, rax; hHeap
0x180006458  call    cs:__imp_HeapAlloc
0x18000645e  mov     rsi, rax
0x180006461  test    rax, rax
0x180006464  jz      short loc_1800064AE
0x180006466  mov     dword ptr [rax], 0
0x18000646c  mov     rcx, [rdi]
0x18000646f  test    rcx, rcx
0x180006472  jz      short loc_18000649F
0x180006474  or      eax, 0FFFFFFFFh
0x180006477  lock xadd [rcx], eax
0x18000647b  cmp     eax, 1
0x18000647e  jnz     short loc_180006497
0x180006480  mov     rbx, [rdi]
0x180006483  call    cs:__imp_GetProcessHeap
0x180006489  mov     r8, rbx; lpMem
0x18000648c  xor     edx, edx; dwFlags
0x18000648e  mov     rcx, rax; hHeap
0x180006491  call    cs:__imp_HeapFree
0x180006497  mov     qword ptr [rdi+8], 0
0x18000649f  mov     [rdi], rsi
0x1800064a2  mov     eax, 1
0x1800064a7  mov     [rdi+8], rbp
0x1800064ab  lock add [rsi], eax
0x1800064ae  add     rsp, 28h
0x1800064b2  pop     rdi
0x1800064b3  pop     rsi
0x1800064b4  pop     rbp
0x1800064b5  pop     rbx
0x1800064b6  retn
```
