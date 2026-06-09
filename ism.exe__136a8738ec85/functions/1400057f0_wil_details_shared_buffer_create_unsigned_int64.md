# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400057f0`
- end: `0x1400058b3`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004c24`
- `0x1400058c0`

## callees

- `0x1400057f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005854`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005854`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005829`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000588d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005829`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000588d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000581b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005845`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000587f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000581b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005845`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000587f`

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
0x1400057f0  push    rbx
0x1400057f2  push    rbp
0x1400057f3  push    rsi
0x1400057f4  push    rdi
0x1400057f5  sub     rsp, 28h
0x1400057f9  mov     rbp, rdx
0x1400057fc  mov     rdi, rcx
0x1400057ff  test    rdx, rdx
0x140005802  jnz     short loc_140005845
0x140005804  mov     rcx, [rcx]
0x140005807  test    rcx, rcx
0x14000580a  jz      short loc_14000583E
0x14000580c  or      eax, 0FFFFFFFFh
0x14000580f  lock xadd [rcx], eax
0x140005813  cmp     eax, 1
0x140005816  jnz     short loc_14000582F
0x140005818  mov     rbx, [rdi]
0x14000581b  call    cs:__imp_GetProcessHeap
0x140005821  mov     r8, rbx; lpMem
0x140005824  xor     edx, edx; dwFlags
0x140005826  mov     rcx, rax; hHeap
0x140005829  call    cs:__imp_HeapFree
0x14000582f  mov     qword ptr [rdi], 0
0x140005836  mov     qword ptr [rdi+8], 0
0x14000583e  mov     eax, 1
0x140005843  jmp     short loc_1400058AA
0x140005845  call    cs:__imp_GetProcessHeap
0x14000584b  lea     r8, [rbp+4]; dwBytes
0x14000584f  xor     edx, edx; dwFlags
0x140005851  mov     rcx, rax; hHeap
0x140005854  call    cs:__imp_HeapAlloc
0x14000585a  mov     rsi, rax
0x14000585d  test    rax, rax
0x140005860  jz      short loc_1400058AA
0x140005862  mov     dword ptr [rax], 0
0x140005868  mov     rcx, [rdi]
0x14000586b  test    rcx, rcx
0x14000586e  jz      short loc_14000589B
0x140005870  or      eax, 0FFFFFFFFh
0x140005873  lock xadd [rcx], eax
0x140005877  cmp     eax, 1
0x14000587a  jnz     short loc_140005893
0x14000587c  mov     rbx, [rdi]
0x14000587f  call    cs:__imp_GetProcessHeap
0x140005885  mov     r8, rbx; lpMem
0x140005888  xor     edx, edx; dwFlags
0x14000588a  mov     rcx, rax; hHeap
0x14000588d  call    cs:__imp_HeapFree
0x140005893  mov     qword ptr [rdi+8], 0
0x14000589b  mov     [rdi], rsi
0x14000589e  mov     eax, 1
0x1400058a3  mov     [rdi+8], rbp
0x1400058a7  lock add [rsi], eax
0x1400058aa  add     rsp, 28h
0x1400058ae  pop     rdi
0x1400058af  pop     rsi
0x1400058b0  pop     rbp
0x1400058b1  pop     rbx
0x1400058b2  retn
```
