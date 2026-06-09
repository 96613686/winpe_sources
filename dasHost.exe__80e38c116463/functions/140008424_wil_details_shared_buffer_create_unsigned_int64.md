# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x140008424`
- end: `0x1400084e7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400070f8`
- `0x1400085e0`

## callees

- `0x140008424`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008488`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008488`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000845d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400084c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000845d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400084c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000844f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008479`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400084b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000844f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008479`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400084b3`

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
0x140008424  push    rbx
0x140008426  push    rbp
0x140008427  push    rsi
0x140008428  push    rdi
0x140008429  sub     rsp, 28h
0x14000842d  mov     rbp, rdx
0x140008430  mov     rdi, rcx
0x140008433  test    rdx, rdx
0x140008436  jnz     short loc_140008479
0x140008438  mov     rcx, [rcx]
0x14000843b  test    rcx, rcx
0x14000843e  jz      short loc_140008472
0x140008440  or      eax, 0FFFFFFFFh
0x140008443  lock xadd [rcx], eax
0x140008447  cmp     eax, 1
0x14000844a  jnz     short loc_140008463
0x14000844c  mov     rbx, [rdi]
0x14000844f  call    cs:__imp_GetProcessHeap
0x140008455  mov     r8, rbx; lpMem
0x140008458  xor     edx, edx; dwFlags
0x14000845a  mov     rcx, rax; hHeap
0x14000845d  call    cs:__imp_HeapFree
0x140008463  mov     qword ptr [rdi], 0
0x14000846a  mov     qword ptr [rdi+8], 0
0x140008472  mov     eax, 1
0x140008477  jmp     short loc_1400084DE
0x140008479  call    cs:__imp_GetProcessHeap
0x14000847f  lea     r8, [rbp+4]; dwBytes
0x140008483  xor     edx, edx; dwFlags
0x140008485  mov     rcx, rax; hHeap
0x140008488  call    cs:__imp_HeapAlloc
0x14000848e  mov     rsi, rax
0x140008491  test    rax, rax
0x140008494  jz      short loc_1400084DE
0x140008496  mov     dword ptr [rax], 0
0x14000849c  mov     rcx, [rdi]
0x14000849f  test    rcx, rcx
0x1400084a2  jz      short loc_1400084CF
0x1400084a4  or      eax, 0FFFFFFFFh
0x1400084a7  lock xadd [rcx], eax
0x1400084ab  cmp     eax, 1
0x1400084ae  jnz     short loc_1400084C7
0x1400084b0  mov     rbx, [rdi]
0x1400084b3  call    cs:__imp_GetProcessHeap
0x1400084b9  mov     r8, rbx; lpMem
0x1400084bc  xor     edx, edx; dwFlags
0x1400084be  mov     rcx, rax; hHeap
0x1400084c1  call    cs:__imp_HeapFree
0x1400084c7  mov     qword ptr [rdi+8], 0
0x1400084cf  mov     [rdi], rsi
0x1400084d2  mov     eax, 1
0x1400084d7  mov     [rdi+8], rbp
0x1400084db  lock add [rsi], eax
0x1400084de  add     rsp, 28h
0x1400084e2  pop     rdi
0x1400084e3  pop     rsi
0x1400084e4  pop     rbp
0x1400084e5  pop     rbx
0x1400084e6  retn
```
