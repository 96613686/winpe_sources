# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007600`
- end: `0x1800076c3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f80`
- `0x1800076d0`

## callees

- `0x180007600`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007664`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007664`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000762b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000768f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000762b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000768f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007639`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000769d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007639`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000769d`

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
0x180007600  push    rbx
0x180007602  push    rbp
0x180007603  push    rsi
0x180007604  push    rdi
0x180007605  sub     rsp, 28h
0x180007609  mov     rbp, rdx
0x18000760c  mov     rdi, rcx
0x18000760f  test    rdx, rdx
0x180007612  jnz     short loc_180007655
0x180007614  mov     rcx, [rcx]
0x180007617  test    rcx, rcx
0x18000761a  jz      short loc_18000764E
0x18000761c  or      eax, 0FFFFFFFFh
0x18000761f  lock xadd [rcx], eax
0x180007623  cmp     eax, 1
0x180007626  jnz     short loc_18000763F
0x180007628  mov     rbx, [rdi]
0x18000762b  call    cs:__imp_GetProcessHeap
0x180007631  mov     r8, rbx; lpMem
0x180007634  xor     edx, edx; dwFlags
0x180007636  mov     rcx, rax; hHeap
0x180007639  call    cs:__imp_HeapFree
0x18000763f  mov     qword ptr [rdi], 0
0x180007646  mov     qword ptr [rdi+8], 0
0x18000764e  mov     eax, 1
0x180007653  jmp     short loc_1800076BA
0x180007655  call    cs:__imp_GetProcessHeap
0x18000765b  lea     r8, [rbp+4]; dwBytes
0x18000765f  xor     edx, edx; dwFlags
0x180007661  mov     rcx, rax; hHeap
0x180007664  call    cs:__imp_HeapAlloc
0x18000766a  mov     rsi, rax
0x18000766d  test    rax, rax
0x180007670  jz      short loc_1800076BA
0x180007672  mov     dword ptr [rax], 0
0x180007678  mov     rcx, [rdi]
0x18000767b  test    rcx, rcx
0x18000767e  jz      short loc_1800076AB
0x180007680  or      eax, 0FFFFFFFFh
0x180007683  lock xadd [rcx], eax
0x180007687  cmp     eax, 1
0x18000768a  jnz     short loc_1800076A3
0x18000768c  mov     rbx, [rdi]
0x18000768f  call    cs:__imp_GetProcessHeap
0x180007695  mov     r8, rbx; lpMem
0x180007698  xor     edx, edx; dwFlags
0x18000769a  mov     rcx, rax; hHeap
0x18000769d  call    cs:__imp_HeapFree
0x1800076a3  mov     qword ptr [rdi+8], 0
0x1800076ab  mov     [rdi], rsi
0x1800076ae  mov     eax, 1
0x1800076b3  mov     [rdi+8], rbp
0x1800076b7  lock add [rsi], eax
0x1800076ba  add     rsp, 28h
0x1800076be  pop     rdi
0x1800076bf  pop     rsi
0x1800076c0  pop     rbp
0x1800076c1  pop     rbx
0x1800076c2  retn
```
