# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800060b8`
- end: `0x18000617b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005540`
- `0x180006190`

## callees

- `0x1800060b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000610d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000610d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006147`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000611c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000611c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006155`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006155`

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
0x1800060b8  push    rbx
0x1800060ba  push    rbp
0x1800060bb  push    rsi
0x1800060bc  push    rdi
0x1800060bd  sub     rsp, 28h
0x1800060c1  mov     rbp, rdx
0x1800060c4  mov     rdi, rcx
0x1800060c7  test    rdx, rdx
0x1800060ca  jnz     short loc_18000610D
0x1800060cc  mov     rcx, [rcx]
0x1800060cf  test    rcx, rcx
0x1800060d2  jz      short loc_180006106
0x1800060d4  or      eax, 0FFFFFFFFh
0x1800060d7  lock xadd [rcx], eax
0x1800060db  cmp     eax, 1
0x1800060de  jnz     short loc_1800060F7
0x1800060e0  mov     rbx, [rdi]
0x1800060e3  call    cs:__imp_GetProcessHeap
0x1800060e9  mov     r8, rbx; lpMem
0x1800060ec  xor     edx, edx; dwFlags
0x1800060ee  mov     rcx, rax; hHeap
0x1800060f1  call    cs:__imp_HeapFree
0x1800060f7  mov     qword ptr [rdi], 0
0x1800060fe  mov     qword ptr [rdi+8], 0
0x180006106  mov     eax, 1
0x18000610b  jmp     short loc_180006172
0x18000610d  call    cs:__imp_GetProcessHeap
0x180006113  lea     r8, [rbp+4]; dwBytes
0x180006117  xor     edx, edx; dwFlags
0x180006119  mov     rcx, rax; hHeap
0x18000611c  call    cs:__imp_HeapAlloc
0x180006122  mov     rsi, rax
0x180006125  test    rax, rax
0x180006128  jz      short loc_180006172
0x18000612a  mov     dword ptr [rax], 0
0x180006130  mov     rcx, [rdi]
0x180006133  test    rcx, rcx
0x180006136  jz      short loc_180006163
0x180006138  or      eax, 0FFFFFFFFh
0x18000613b  lock xadd [rcx], eax
0x18000613f  cmp     eax, 1
0x180006142  jnz     short loc_18000615B
0x180006144  mov     rbx, [rdi]
0x180006147  call    cs:__imp_GetProcessHeap
0x18000614d  mov     r8, rbx; lpMem
0x180006150  xor     edx, edx; dwFlags
0x180006152  mov     rcx, rax; hHeap
0x180006155  call    cs:__imp_HeapFree
0x18000615b  mov     qword ptr [rdi+8], 0
0x180006163  mov     [rdi], rsi
0x180006166  mov     eax, 1
0x18000616b  mov     [rdi+8], rbp
0x18000616f  lock add [rsi], eax
0x180006172  add     rsp, 28h
0x180006176  pop     rdi
0x180006177  pop     rsi
0x180006178  pop     rbp
0x180006179  pop     rbx
0x18000617a  retn
```
