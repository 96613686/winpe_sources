# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000a474`
- end: `0x18000a537`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008fa8`
- `0x18000a8a0`

## callees

- `0x18000a474`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a4d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a4d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a49f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a4c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a503`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a49f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a4c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a503`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a4ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a4ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a511`

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
0x18000a474  push    rbx
0x18000a476  push    rbp
0x18000a477  push    rsi
0x18000a478  push    rdi
0x18000a479  sub     rsp, 28h
0x18000a47d  mov     rbp, rdx
0x18000a480  mov     rdi, rcx
0x18000a483  test    rdx, rdx
0x18000a486  jnz     short loc_18000A4C9
0x18000a488  mov     rcx, [rcx]
0x18000a48b  test    rcx, rcx
0x18000a48e  jz      short loc_18000A4C2
0x18000a490  or      eax, 0FFFFFFFFh
0x18000a493  lock xadd [rcx], eax
0x18000a497  cmp     eax, 1
0x18000a49a  jnz     short loc_18000A4B3
0x18000a49c  mov     rbx, [rdi]
0x18000a49f  call    cs:__imp_GetProcessHeap
0x18000a4a5  mov     r8, rbx; lpMem
0x18000a4a8  xor     edx, edx; dwFlags
0x18000a4aa  mov     rcx, rax; hHeap
0x18000a4ad  call    cs:__imp_HeapFree
0x18000a4b3  mov     qword ptr [rdi], 0
0x18000a4ba  mov     qword ptr [rdi+8], 0
0x18000a4c2  mov     eax, 1
0x18000a4c7  jmp     short loc_18000A52E
0x18000a4c9  call    cs:__imp_GetProcessHeap
0x18000a4cf  lea     r8, [rbp+4]; dwBytes
0x18000a4d3  xor     edx, edx; dwFlags
0x18000a4d5  mov     rcx, rax; hHeap
0x18000a4d8  call    cs:__imp_HeapAlloc
0x18000a4de  mov     rsi, rax
0x18000a4e1  test    rax, rax
0x18000a4e4  jz      short loc_18000A52E
0x18000a4e6  mov     dword ptr [rax], 0
0x18000a4ec  mov     rcx, [rdi]
0x18000a4ef  test    rcx, rcx
0x18000a4f2  jz      short loc_18000A51F
0x18000a4f4  or      eax, 0FFFFFFFFh
0x18000a4f7  lock xadd [rcx], eax
0x18000a4fb  cmp     eax, 1
0x18000a4fe  jnz     short loc_18000A517
0x18000a500  mov     rbx, [rdi]
0x18000a503  call    cs:__imp_GetProcessHeap
0x18000a509  mov     r8, rbx; lpMem
0x18000a50c  xor     edx, edx; dwFlags
0x18000a50e  mov     rcx, rax; hHeap
0x18000a511  call    cs:__imp_HeapFree
0x18000a517  mov     qword ptr [rdi+8], 0
0x18000a51f  mov     [rdi], rsi
0x18000a522  mov     eax, 1
0x18000a527  mov     [rdi+8], rbp
0x18000a52b  lock add [rsi], eax
0x18000a52e  add     rsp, 28h
0x18000a532  pop     rdi
0x18000a533  pop     rsi
0x18000a534  pop     rbp
0x18000a535  pop     rbx
0x18000a536  retn
```
