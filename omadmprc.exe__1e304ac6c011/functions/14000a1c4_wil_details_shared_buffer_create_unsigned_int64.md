# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000a1c4`
- end: `0x14000a2ac`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008730`
- `0x14000a760`

## callees

- `0x14000a1c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a23a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a23a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a1ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a225`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a26b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a1ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a225`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a26b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a27f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a27f`

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
0x14000a1c4  push    rbx
0x14000a1c6  push    rbp
0x14000a1c7  push    rsi
0x14000a1c8  push    rdi
0x14000a1c9  sub     rsp, 28h
0x14000a1cd  mov     rbp, rdx
0x14000a1d0  mov     rdi, rcx
0x14000a1d3  test    rdx, rdx
0x14000a1d6  jnz     short loc_14000A225
0x14000a1d8  mov     rcx, [rcx]
0x14000a1db  test    rcx, rcx
0x14000a1de  jz      short loc_14000A21E
0x14000a1e0  or      eax, 0FFFFFFFFh
0x14000a1e3  lock xadd [rcx], eax
0x14000a1e7  cmp     eax, 1
0x14000a1ea  jnz     short loc_14000A20F
0x14000a1ec  mov     rbx, [rdi]
0x14000a1ef  call    cs:__imp_GetProcessHeap
0x14000a1f6  nop     dword ptr [rax+rax+00h]
0x14000a1fb  mov     r8, rbx; lpMem
0x14000a1fe  xor     edx, edx; dwFlags
0x14000a200  mov     rcx, rax; hHeap
0x14000a203  call    cs:__imp_HeapFree
0x14000a20a  nop     dword ptr [rax+rax+00h]
0x14000a20f  mov     qword ptr [rdi], 0
0x14000a216  mov     qword ptr [rdi+8], 0
0x14000a21e  mov     eax, 1
0x14000a223  jmp     short loc_14000A2A2
0x14000a225  call    cs:__imp_GetProcessHeap
0x14000a22c  nop     dword ptr [rax+rax+00h]
0x14000a231  lea     r8, [rbp+4]; dwBytes
0x14000a235  xor     edx, edx; dwFlags
0x14000a237  mov     rcx, rax; hHeap
0x14000a23a  call    cs:__imp_HeapAlloc
0x14000a241  nop     dword ptr [rax+rax+00h]
0x14000a246  mov     rsi, rax
0x14000a249  test    rax, rax
0x14000a24c  jz      short loc_14000A2A2
0x14000a24e  mov     dword ptr [rax], 0
0x14000a254  mov     rcx, [rdi]
0x14000a257  test    rcx, rcx
0x14000a25a  jz      short loc_14000A293
0x14000a25c  or      eax, 0FFFFFFFFh
0x14000a25f  lock xadd [rcx], eax
0x14000a263  cmp     eax, 1
0x14000a266  jnz     short loc_14000A28B
0x14000a268  mov     rbx, [rdi]
0x14000a26b  call    cs:__imp_GetProcessHeap
0x14000a272  nop     dword ptr [rax+rax+00h]
0x14000a277  mov     r8, rbx; lpMem
0x14000a27a  xor     edx, edx; dwFlags
0x14000a27c  mov     rcx, rax; hHeap
0x14000a27f  call    cs:__imp_HeapFree
0x14000a286  nop     dword ptr [rax+rax+00h]
0x14000a28b  mov     qword ptr [rdi+8], 0
0x14000a293  mov     [rdi], rsi
0x14000a296  mov     eax, 1
0x14000a29b  mov     [rdi+8], rbp
0x14000a29f  lock add [rsi], eax
0x14000a2a2  add     rsp, 28h
0x14000a2a6  pop     rdi
0x14000a2a7  pop     rsi
0x14000a2a8  pop     rbp
0x14000a2a9  pop     rbx
0x14000a2aa  retn
```
