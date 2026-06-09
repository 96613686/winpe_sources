# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000cf80`
- end: `0x14000d043`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ad28`
- `0x14000d240`

## callees

- `0x14000cf80`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000cfab`
- `KERNEL32!GetProcessHeap` at `0x14000cfd5`
- `KERNEL32!GetProcessHeap` at `0x14000d00f`
- `KERNEL32!GetProcessHeap` at `0x14000cfab`
- `KERNEL32!GetProcessHeap` at `0x14000cfd5`
- `KERNEL32!GetProcessHeap` at `0x14000d00f`
- `KERNEL32!HeapAlloc` at `0x14000cfe4`
- `KERNEL32!HeapAlloc` at `0x14000cfe4`
- `KERNEL32!HeapFree` at `0x14000cfb9`
- `KERNEL32!HeapFree` at `0x14000d01d`
- `KERNEL32!HeapFree` at `0x14000cfb9`
- `KERNEL32!HeapFree` at `0x14000d01d`

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
0x14000cf80  push    rbx
0x14000cf82  push    rbp
0x14000cf83  push    rsi
0x14000cf84  push    rdi
0x14000cf85  sub     rsp, 28h
0x14000cf89  mov     rbp, rdx
0x14000cf8c  mov     rdi, rcx
0x14000cf8f  test    rdx, rdx
0x14000cf92  jnz     short loc_14000CFD5
0x14000cf94  mov     rcx, [rcx]
0x14000cf97  test    rcx, rcx
0x14000cf9a  jz      short loc_14000CFCE
0x14000cf9c  or      eax, 0FFFFFFFFh
0x14000cf9f  lock xadd [rcx], eax
0x14000cfa3  cmp     eax, 1
0x14000cfa6  jnz     short loc_14000CFBF
0x14000cfa8  mov     rbx, [rdi]
0x14000cfab  call    cs:__imp_GetProcessHeap
0x14000cfb1  mov     r8, rbx; lpMem
0x14000cfb4  xor     edx, edx; dwFlags
0x14000cfb6  mov     rcx, rax; hHeap
0x14000cfb9  call    cs:__imp_HeapFree
0x14000cfbf  mov     qword ptr [rdi], 0
0x14000cfc6  mov     qword ptr [rdi+8], 0
0x14000cfce  mov     eax, 1
0x14000cfd3  jmp     short loc_14000D03A
0x14000cfd5  call    cs:__imp_GetProcessHeap
0x14000cfdb  lea     r8, [rbp+4]; dwBytes
0x14000cfdf  xor     edx, edx; dwFlags
0x14000cfe1  mov     rcx, rax; hHeap
0x14000cfe4  call    cs:__imp_HeapAlloc
0x14000cfea  mov     rsi, rax
0x14000cfed  test    rax, rax
0x14000cff0  jz      short loc_14000D03A
0x14000cff2  mov     dword ptr [rax], 0
0x14000cff8  mov     rcx, [rdi]
0x14000cffb  test    rcx, rcx
0x14000cffe  jz      short loc_14000D02B
0x14000d000  or      eax, 0FFFFFFFFh
0x14000d003  lock xadd [rcx], eax
0x14000d007  cmp     eax, 1
0x14000d00a  jnz     short loc_14000D023
0x14000d00c  mov     rbx, [rdi]
0x14000d00f  call    cs:__imp_GetProcessHeap
0x14000d015  mov     r8, rbx; lpMem
0x14000d018  xor     edx, edx; dwFlags
0x14000d01a  mov     rcx, rax; hHeap
0x14000d01d  call    cs:__imp_HeapFree
0x14000d023  mov     qword ptr [rdi+8], 0
0x14000d02b  mov     [rdi], rsi
0x14000d02e  mov     eax, 1
0x14000d033  mov     [rdi+8], rbp
0x14000d037  lock add [rsi], eax
0x14000d03a  add     rsp, 28h
0x14000d03e  pop     rdi
0x14000d03f  pop     rsi
0x14000d040  pop     rbp
0x14000d041  pop     rbx
0x14000d042  retn
```
