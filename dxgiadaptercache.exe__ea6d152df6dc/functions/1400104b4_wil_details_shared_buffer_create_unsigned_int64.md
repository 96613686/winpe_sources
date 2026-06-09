# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400104b4`
- end: `0x140010577`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cd28`
- `0x140010c10`

## callees

- `0x1400104b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400104df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010509`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010543`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400104df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010509`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010543`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010518`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010518`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400104ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400104ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010551`

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
0x1400104b4  push    rbx
0x1400104b6  push    rbp
0x1400104b7  push    rsi
0x1400104b8  push    rdi
0x1400104b9  sub     rsp, 28h
0x1400104bd  mov     rbp, rdx
0x1400104c0  mov     rdi, rcx
0x1400104c3  test    rdx, rdx
0x1400104c6  jnz     short loc_140010509
0x1400104c8  mov     rcx, [rcx]
0x1400104cb  test    rcx, rcx
0x1400104ce  jz      short loc_140010502
0x1400104d0  or      eax, 0FFFFFFFFh
0x1400104d3  lock xadd [rcx], eax
0x1400104d7  cmp     eax, 1
0x1400104da  jnz     short loc_1400104F3
0x1400104dc  mov     rbx, [rdi]
0x1400104df  call    cs:__imp_GetProcessHeap
0x1400104e5  mov     r8, rbx; lpMem
0x1400104e8  xor     edx, edx; dwFlags
0x1400104ea  mov     rcx, rax; hHeap
0x1400104ed  call    cs:__imp_HeapFree
0x1400104f3  mov     qword ptr [rdi], 0
0x1400104fa  mov     qword ptr [rdi+8], 0
0x140010502  mov     eax, 1
0x140010507  jmp     short loc_14001056E
0x140010509  call    cs:__imp_GetProcessHeap
0x14001050f  lea     r8, [rbp+4]; dwBytes
0x140010513  xor     edx, edx; dwFlags
0x140010515  mov     rcx, rax; hHeap
0x140010518  call    cs:__imp_HeapAlloc
0x14001051e  mov     rsi, rax
0x140010521  test    rax, rax
0x140010524  jz      short loc_14001056E
0x140010526  mov     dword ptr [rax], 0
0x14001052c  mov     rcx, [rdi]
0x14001052f  test    rcx, rcx
0x140010532  jz      short loc_14001055F
0x140010534  or      eax, 0FFFFFFFFh
0x140010537  lock xadd [rcx], eax
0x14001053b  cmp     eax, 1
0x14001053e  jnz     short loc_140010557
0x140010540  mov     rbx, [rdi]
0x140010543  call    cs:__imp_GetProcessHeap
0x140010549  mov     r8, rbx; lpMem
0x14001054c  xor     edx, edx; dwFlags
0x14001054e  mov     rcx, rax; hHeap
0x140010551  call    cs:__imp_HeapFree
0x140010557  mov     qword ptr [rdi+8], 0
0x14001055f  mov     [rdi], rsi
0x140010562  mov     eax, 1
0x140010567  mov     [rdi+8], rbp
0x14001056b  lock add [rsi], eax
0x14001056e  add     rsp, 28h
0x140010572  pop     rdi
0x140010573  pop     rsi
0x140010574  pop     rbp
0x140010575  pop     rbx
0x140010576  retn
```
