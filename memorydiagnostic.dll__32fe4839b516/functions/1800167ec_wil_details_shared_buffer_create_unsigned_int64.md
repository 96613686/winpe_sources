# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800167ec`
- end: `0x1800168df`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `243`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001199c`
- `0x180019e40`

## callees

- `0x1800167ec`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180016822`
- `KERNEL32!GetProcessHeap` at `0x180016852`
- `KERNEL32!GetProcessHeap` at `0x180016895`
- `KERNEL32!GetProcessHeap` at `0x180016822`
- `KERNEL32!GetProcessHeap` at `0x180016852`
- `KERNEL32!GetProcessHeap` at `0x180016895`
- `KERNEL32!HeapAlloc` at `0x180016867`
- `KERNEL32!HeapAlloc` at `0x180016867`
- `KERNEL32!HeapFree` at `0x180016836`
- `KERNEL32!HeapFree` at `0x1800168a9`
- `KERNEL32!HeapFree` at `0x180016836`
- `KERNEL32!HeapFree` at `0x1800168a9`

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
0x1800167ec  mov     [rsp+arg_0], rbx
0x1800167f1  mov     [rsp+arg_8], rbp
0x1800167f6  mov     [rsp+arg_10], rsi
0x1800167fb  push    rdi
0x1800167fc  sub     rsp, 20h
0x180016800  mov     rbp, rdx
0x180016803  mov     rdi, rcx
0x180016806  test    rdx, rdx
0x180016809  jnz     short loc_180016852
0x18001680b  mov     rcx, [rcx]
0x18001680e  test    rcx, rcx
0x180016811  jz      short loc_18001684B
0x180016813  or      eax, 0FFFFFFFFh
0x180016816  lock xadd [rcx], eax
0x18001681a  cmp     eax, 1
0x18001681d  jnz     short loc_180016842
0x18001681f  mov     rbx, [rdi]
0x180016822  call    cs:__imp_GetProcessHeap
0x180016829  nop     dword ptr [rax+rax+00h]
0x18001682e  mov     r8, rbx; lpMem
0x180016831  xor     edx, edx; dwFlags
0x180016833  mov     rcx, rax; hHeap
0x180016836  call    cs:__imp_HeapFree
0x18001683d  nop     dword ptr [rax+rax+00h]
0x180016842  and     qword ptr [rdi], 0
0x180016846  and     qword ptr [rdi+8], 0
0x18001684b  mov     eax, 1
0x180016850  jmp     short loc_1800168C9
0x180016852  call    cs:__imp_GetProcessHeap
0x180016859  nop     dword ptr [rax+rax+00h]
0x18001685e  lea     r8, [rbp+4]; dwBytes
0x180016862  xor     edx, edx; dwFlags
0x180016864  mov     rcx, rax; hHeap
0x180016867  call    cs:__imp_HeapAlloc
0x18001686e  nop     dword ptr [rax+rax+00h]
0x180016873  mov     rsi, rax
0x180016876  test    rax, rax
0x180016879  jz      short loc_1800168C9
0x18001687b  and     dword ptr [rax], 0
0x18001687e  mov     rcx, [rdi]
0x180016881  test    rcx, rcx
0x180016884  jz      short loc_1800168BA
0x180016886  or      eax, 0FFFFFFFFh
0x180016889  lock xadd [rcx], eax
0x18001688d  cmp     eax, 1
0x180016890  jnz     short loc_1800168B5
0x180016892  mov     rbx, [rdi]
0x180016895  call    cs:__imp_GetProcessHeap
0x18001689c  nop     dword ptr [rax+rax+00h]
0x1800168a1  mov     r8, rbx; lpMem
0x1800168a4  xor     edx, edx; dwFlags
0x1800168a6  mov     rcx, rax; hHeap
0x1800168a9  call    cs:__imp_HeapFree
0x1800168b0  nop     dword ptr [rax+rax+00h]
0x1800168b5  and     qword ptr [rdi+8], 0
0x1800168ba  mov     [rdi], rsi
0x1800168bd  mov     eax, 1
0x1800168c2  mov     [rdi+8], rbp
0x1800168c6  lock add [rsi], eax
0x1800168c9  mov     rbx, [rsp+28h+arg_0]
0x1800168ce  mov     rbp, [rsp+28h+arg_8]
0x1800168d3  mov     rsi, [rsp+28h+arg_10]
0x1800168d8  add     rsp, 20h
0x1800168dc  pop     rdi
0x1800168dd  retn
```
