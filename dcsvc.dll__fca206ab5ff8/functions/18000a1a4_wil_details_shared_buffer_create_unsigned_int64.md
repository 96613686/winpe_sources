# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000a1a4`
- end: `0x18000a267`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800088f4`
- `0x18000a350`

## callees

- `0x18000a1a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a233`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a1f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a233`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a208`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a208`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a241`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a1dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a241`

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
0x18000a1a4  push    rbx
0x18000a1a6  push    rbp
0x18000a1a7  push    rsi
0x18000a1a8  push    rdi
0x18000a1a9  sub     rsp, 28h
0x18000a1ad  mov     rbp, rdx
0x18000a1b0  mov     rdi, rcx
0x18000a1b3  test    rdx, rdx
0x18000a1b6  jnz     short loc_18000A1F9
0x18000a1b8  mov     rcx, [rcx]
0x18000a1bb  test    rcx, rcx
0x18000a1be  jz      short loc_18000A1F2
0x18000a1c0  or      eax, 0FFFFFFFFh
0x18000a1c3  lock xadd [rcx], eax
0x18000a1c7  cmp     eax, 1
0x18000a1ca  jnz     short loc_18000A1E3
0x18000a1cc  mov     rbx, [rdi]
0x18000a1cf  call    cs:__imp_GetProcessHeap
0x18000a1d5  mov     r8, rbx; lpMem
0x18000a1d8  xor     edx, edx; dwFlags
0x18000a1da  mov     rcx, rax; hHeap
0x18000a1dd  call    cs:__imp_HeapFree
0x18000a1e3  mov     qword ptr [rdi], 0
0x18000a1ea  mov     qword ptr [rdi+8], 0
0x18000a1f2  mov     eax, 1
0x18000a1f7  jmp     short loc_18000A25E
0x18000a1f9  call    cs:__imp_GetProcessHeap
0x18000a1ff  lea     r8, [rbp+4]; dwBytes
0x18000a203  xor     edx, edx; dwFlags
0x18000a205  mov     rcx, rax; hHeap
0x18000a208  call    cs:__imp_HeapAlloc
0x18000a20e  mov     rsi, rax
0x18000a211  test    rax, rax
0x18000a214  jz      short loc_18000A25E
0x18000a216  mov     dword ptr [rax], 0
0x18000a21c  mov     rcx, [rdi]
0x18000a21f  test    rcx, rcx
0x18000a222  jz      short loc_18000A24F
0x18000a224  or      eax, 0FFFFFFFFh
0x18000a227  lock xadd [rcx], eax
0x18000a22b  cmp     eax, 1
0x18000a22e  jnz     short loc_18000A247
0x18000a230  mov     rbx, [rdi]
0x18000a233  call    cs:__imp_GetProcessHeap
0x18000a239  mov     r8, rbx; lpMem
0x18000a23c  xor     edx, edx; dwFlags
0x18000a23e  mov     rcx, rax; hHeap
0x18000a241  call    cs:__imp_HeapFree
0x18000a247  mov     qword ptr [rdi+8], 0
0x18000a24f  mov     [rdi], rsi
0x18000a252  mov     eax, 1
0x18000a257  mov     [rdi+8], rbp
0x18000a25b  lock add [rsi], eax
0x18000a25e  add     rsp, 28h
0x18000a262  pop     rdi
0x18000a263  pop     rsi
0x18000a264  pop     rbp
0x18000a265  pop     rbx
0x18000a266  retn
```
