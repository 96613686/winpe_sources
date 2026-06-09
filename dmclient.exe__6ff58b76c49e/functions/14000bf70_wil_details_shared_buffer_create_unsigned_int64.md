# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000bf70`
- end: `0x14000c033`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ae84`
- `0x14000c360`

## callees

- `0x14000bf70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bfd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000bfd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bf9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bfc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bfff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bf9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bfc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bfff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bfa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c00d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bfa9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c00d`

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
0x14000bf70  push    rbx
0x14000bf72  push    rbp
0x14000bf73  push    rsi
0x14000bf74  push    rdi
0x14000bf75  sub     rsp, 28h
0x14000bf79  mov     rbp, rdx
0x14000bf7c  mov     rdi, rcx
0x14000bf7f  test    rdx, rdx
0x14000bf82  jnz     short loc_14000BFC5
0x14000bf84  mov     rcx, [rcx]
0x14000bf87  test    rcx, rcx
0x14000bf8a  jz      short loc_14000BFBE
0x14000bf8c  or      eax, 0FFFFFFFFh
0x14000bf8f  lock xadd [rcx], eax
0x14000bf93  cmp     eax, 1
0x14000bf96  jnz     short loc_14000BFAF
0x14000bf98  mov     rbx, [rdi]
0x14000bf9b  call    cs:__imp_GetProcessHeap
0x14000bfa1  mov     r8, rbx; lpMem
0x14000bfa4  xor     edx, edx; dwFlags
0x14000bfa6  mov     rcx, rax; hHeap
0x14000bfa9  call    cs:__imp_HeapFree
0x14000bfaf  mov     qword ptr [rdi], 0
0x14000bfb6  mov     qword ptr [rdi+8], 0
0x14000bfbe  mov     eax, 1
0x14000bfc3  jmp     short loc_14000C02A
0x14000bfc5  call    cs:__imp_GetProcessHeap
0x14000bfcb  lea     r8, [rbp+4]; dwBytes
0x14000bfcf  xor     edx, edx; dwFlags
0x14000bfd1  mov     rcx, rax; hHeap
0x14000bfd4  call    cs:__imp_HeapAlloc
0x14000bfda  mov     rsi, rax
0x14000bfdd  test    rax, rax
0x14000bfe0  jz      short loc_14000C02A
0x14000bfe2  mov     dword ptr [rax], 0
0x14000bfe8  mov     rcx, [rdi]
0x14000bfeb  test    rcx, rcx
0x14000bfee  jz      short loc_14000C01B
0x14000bff0  or      eax, 0FFFFFFFFh
0x14000bff3  lock xadd [rcx], eax
0x14000bff7  cmp     eax, 1
0x14000bffa  jnz     short loc_14000C013
0x14000bffc  mov     rbx, [rdi]
0x14000bfff  call    cs:__imp_GetProcessHeap
0x14000c005  mov     r8, rbx; lpMem
0x14000c008  xor     edx, edx; dwFlags
0x14000c00a  mov     rcx, rax; hHeap
0x14000c00d  call    cs:__imp_HeapFree
0x14000c013  mov     qword ptr [rdi+8], 0
0x14000c01b  mov     [rdi], rsi
0x14000c01e  mov     eax, 1
0x14000c023  mov     [rdi+8], rbp
0x14000c027  lock add [rsi], eax
0x14000c02a  add     rsp, 28h
0x14000c02e  pop     rdi
0x14000c02f  pop     rsi
0x14000c030  pop     rbp
0x14000c031  pop     rbx
0x14000c032  retn
```
