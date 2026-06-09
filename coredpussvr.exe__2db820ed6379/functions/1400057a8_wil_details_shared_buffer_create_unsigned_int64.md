# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1400057a8`
- end: `0x140005890`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004acc`
- `0x1400058a0`

## callees

- `0x1400057a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400057e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005863`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400057e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005863`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000581e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000581e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400057d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005809`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000584f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400057d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005809`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000584f`

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
0x1400057a8  push    rbx
0x1400057aa  push    rbp
0x1400057ab  push    rsi
0x1400057ac  push    rdi
0x1400057ad  sub     rsp, 28h
0x1400057b1  mov     rbp, rdx
0x1400057b4  mov     rdi, rcx
0x1400057b7  test    rdx, rdx
0x1400057ba  jnz     short loc_140005809
0x1400057bc  mov     rcx, [rcx]
0x1400057bf  test    rcx, rcx
0x1400057c2  jz      short loc_140005802
0x1400057c4  or      eax, 0FFFFFFFFh
0x1400057c7  lock xadd [rcx], eax
0x1400057cb  cmp     eax, 1
0x1400057ce  jnz     short loc_1400057F3
0x1400057d0  mov     rbx, [rdi]
0x1400057d3  call    cs:__imp_GetProcessHeap
0x1400057da  nop     dword ptr [rax+rax+00h]
0x1400057df  mov     r8, rbx; lpMem
0x1400057e2  xor     edx, edx; dwFlags
0x1400057e4  mov     rcx, rax; hHeap
0x1400057e7  call    cs:__imp_HeapFree
0x1400057ee  nop     dword ptr [rax+rax+00h]
0x1400057f3  mov     qword ptr [rdi], 0
0x1400057fa  mov     qword ptr [rdi+8], 0
0x140005802  mov     eax, 1
0x140005807  jmp     short loc_140005886
0x140005809  call    cs:__imp_GetProcessHeap
0x140005810  nop     dword ptr [rax+rax+00h]
0x140005815  lea     r8, [rbp+4]; dwBytes
0x140005819  xor     edx, edx; dwFlags
0x14000581b  mov     rcx, rax; hHeap
0x14000581e  call    cs:__imp_HeapAlloc
0x140005825  nop     dword ptr [rax+rax+00h]
0x14000582a  mov     rsi, rax
0x14000582d  test    rax, rax
0x140005830  jz      short loc_140005886
0x140005832  mov     dword ptr [rax], 0
0x140005838  mov     rcx, [rdi]
0x14000583b  test    rcx, rcx
0x14000583e  jz      short loc_140005877
0x140005840  or      eax, 0FFFFFFFFh
0x140005843  lock xadd [rcx], eax
0x140005847  cmp     eax, 1
0x14000584a  jnz     short loc_14000586F
0x14000584c  mov     rbx, [rdi]
0x14000584f  call    cs:__imp_GetProcessHeap
0x140005856  nop     dword ptr [rax+rax+00h]
0x14000585b  mov     r8, rbx; lpMem
0x14000585e  xor     edx, edx; dwFlags
0x140005860  mov     rcx, rax; hHeap
0x140005863  call    cs:__imp_HeapFree
0x14000586a  nop     dword ptr [rax+rax+00h]
0x14000586f  mov     qword ptr [rdi+8], 0
0x140005877  mov     [rdi], rsi
0x14000587a  mov     eax, 1
0x14000587f  mov     [rdi+8], rbp
0x140005883  lock add [rsi], eax
0x140005886  add     rsp, 28h
0x14000588a  pop     rdi
0x14000588b  pop     rsi
0x14000588c  pop     rbp
0x14000588d  pop     rbx
0x14000588e  retn
```
