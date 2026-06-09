# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000626c`
- end: `0x180006354`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d34`
- `0x180006360`

## callees

- `0x18000626c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006327`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006297`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006297`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006313`

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
0x18000626c  push    rbx
0x18000626e  push    rbp
0x18000626f  push    rsi
0x180006270  push    rdi
0x180006271  sub     rsp, 28h
0x180006275  mov     rbp, rdx
0x180006278  mov     rdi, rcx
0x18000627b  test    rdx, rdx
0x18000627e  jnz     short loc_1800062CD
0x180006280  mov     rcx, [rcx]
0x180006283  test    rcx, rcx
0x180006286  jz      short loc_1800062C6
0x180006288  or      eax, 0FFFFFFFFh
0x18000628b  lock xadd [rcx], eax
0x18000628f  cmp     eax, 1
0x180006292  jnz     short loc_1800062B7
0x180006294  mov     rbx, [rdi]
0x180006297  call    cs:__imp_GetProcessHeap
0x18000629e  nop     dword ptr [rax+rax+00h]
0x1800062a3  mov     r8, rbx; lpMem
0x1800062a6  xor     edx, edx; dwFlags
0x1800062a8  mov     rcx, rax; hHeap
0x1800062ab  call    cs:__imp_HeapFree
0x1800062b2  nop     dword ptr [rax+rax+00h]
0x1800062b7  mov     qword ptr [rdi], 0
0x1800062be  mov     qword ptr [rdi+8], 0
0x1800062c6  mov     eax, 1
0x1800062cb  jmp     short loc_18000634A
0x1800062cd  call    cs:__imp_GetProcessHeap
0x1800062d4  nop     dword ptr [rax+rax+00h]
0x1800062d9  lea     r8, [rbp+4]; dwBytes
0x1800062dd  xor     edx, edx; dwFlags
0x1800062df  mov     rcx, rax; hHeap
0x1800062e2  call    cs:__imp_HeapAlloc
0x1800062e9  nop     dword ptr [rax+rax+00h]
0x1800062ee  mov     rsi, rax
0x1800062f1  test    rax, rax
0x1800062f4  jz      short loc_18000634A
0x1800062f6  mov     dword ptr [rax], 0
0x1800062fc  mov     rcx, [rdi]
0x1800062ff  test    rcx, rcx
0x180006302  jz      short loc_18000633B
0x180006304  or      eax, 0FFFFFFFFh
0x180006307  lock xadd [rcx], eax
0x18000630b  cmp     eax, 1
0x18000630e  jnz     short loc_180006333
0x180006310  mov     rbx, [rdi]
0x180006313  call    cs:__imp_GetProcessHeap
0x18000631a  nop     dword ptr [rax+rax+00h]
0x18000631f  mov     r8, rbx; lpMem
0x180006322  xor     edx, edx; dwFlags
0x180006324  mov     rcx, rax; hHeap
0x180006327  call    cs:__imp_HeapFree
0x18000632e  nop     dword ptr [rax+rax+00h]
0x180006333  mov     qword ptr [rdi+8], 0
0x18000633b  mov     [rdi], rsi
0x18000633e  mov     eax, 1
0x180006343  mov     [rdi+8], rbp
0x180006347  lock add [rsi], eax
0x18000634a  add     rsp, 28h
0x18000634e  pop     rdi
0x18000634f  pop     rsi
0x180006350  pop     rbp
0x180006351  pop     rbx
0x180006352  retn
```
