# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800067d8`
- end: `0x18000689b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c10`
- `0x1800068b0`

## callees

- `0x1800067d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000682d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006867`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000682d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006867`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000683c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000683c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006811`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006875`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006811`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006875`

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
0x1800067d8  push    rbx
0x1800067da  push    rbp
0x1800067db  push    rsi
0x1800067dc  push    rdi
0x1800067dd  sub     rsp, 28h
0x1800067e1  mov     rbp, rdx
0x1800067e4  mov     rdi, rcx
0x1800067e7  test    rdx, rdx
0x1800067ea  jnz     short loc_18000682D
0x1800067ec  mov     rcx, [rcx]
0x1800067ef  test    rcx, rcx
0x1800067f2  jz      short loc_180006826
0x1800067f4  or      eax, 0FFFFFFFFh
0x1800067f7  lock xadd [rcx], eax
0x1800067fb  cmp     eax, 1
0x1800067fe  jnz     short loc_180006817
0x180006800  mov     rbx, [rdi]
0x180006803  call    cs:__imp_GetProcessHeap
0x180006809  mov     r8, rbx; lpMem
0x18000680c  xor     edx, edx; dwFlags
0x18000680e  mov     rcx, rax; hHeap
0x180006811  call    cs:__imp_HeapFree
0x180006817  mov     qword ptr [rdi], 0
0x18000681e  mov     qword ptr [rdi+8], 0
0x180006826  mov     eax, 1
0x18000682b  jmp     short loc_180006892
0x18000682d  call    cs:__imp_GetProcessHeap
0x180006833  lea     r8, [rbp+4]; dwBytes
0x180006837  xor     edx, edx; dwFlags
0x180006839  mov     rcx, rax; hHeap
0x18000683c  call    cs:__imp_HeapAlloc
0x180006842  mov     rsi, rax
0x180006845  test    rax, rax
0x180006848  jz      short loc_180006892
0x18000684a  mov     dword ptr [rax], 0
0x180006850  mov     rcx, [rdi]
0x180006853  test    rcx, rcx
0x180006856  jz      short loc_180006883
0x180006858  or      eax, 0FFFFFFFFh
0x18000685b  lock xadd [rcx], eax
0x18000685f  cmp     eax, 1
0x180006862  jnz     short loc_18000687B
0x180006864  mov     rbx, [rdi]
0x180006867  call    cs:__imp_GetProcessHeap
0x18000686d  mov     r8, rbx; lpMem
0x180006870  xor     edx, edx; dwFlags
0x180006872  mov     rcx, rax; hHeap
0x180006875  call    cs:__imp_HeapFree
0x18000687b  mov     qword ptr [rdi+8], 0
0x180006883  mov     [rdi], rsi
0x180006886  mov     eax, 1
0x18000688b  mov     [rdi+8], rbp
0x18000688f  lock add [rsi], eax
0x180006892  add     rsp, 28h
0x180006896  pop     rdi
0x180006897  pop     rsi
0x180006898  pop     rbp
0x180006899  pop     rbx
0x18000689a  retn
```
