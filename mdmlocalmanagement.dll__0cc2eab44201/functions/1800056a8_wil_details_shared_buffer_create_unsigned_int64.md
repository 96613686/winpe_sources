# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800056a8`
- end: `0x180005790`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049ac`
- `0x1800057a0`

## callees

- `0x1800056a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005709`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000574f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005709`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000574f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000571e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000571e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005763`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005763`

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
0x1800056a8  push    rbx
0x1800056aa  push    rbp
0x1800056ab  push    rsi
0x1800056ac  push    rdi
0x1800056ad  sub     rsp, 28h
0x1800056b1  mov     rbp, rdx
0x1800056b4  mov     rdi, rcx
0x1800056b7  test    rdx, rdx
0x1800056ba  jnz     short loc_180005709
0x1800056bc  mov     rcx, [rcx]
0x1800056bf  test    rcx, rcx
0x1800056c2  jz      short loc_180005702
0x1800056c4  or      eax, 0FFFFFFFFh
0x1800056c7  lock xadd [rcx], eax
0x1800056cb  cmp     eax, 1
0x1800056ce  jnz     short loc_1800056F3
0x1800056d0  mov     rbx, [rdi]
0x1800056d3  call    cs:__imp_GetProcessHeap
0x1800056da  nop     dword ptr [rax+rax+00h]
0x1800056df  mov     r8, rbx; lpMem
0x1800056e2  xor     edx, edx; dwFlags
0x1800056e4  mov     rcx, rax; hHeap
0x1800056e7  call    cs:__imp_HeapFree
0x1800056ee  nop     dword ptr [rax+rax+00h]
0x1800056f3  mov     qword ptr [rdi], 0
0x1800056fa  mov     qword ptr [rdi+8], 0
0x180005702  mov     eax, 1
0x180005707  jmp     short loc_180005786
0x180005709  call    cs:__imp_GetProcessHeap
0x180005710  nop     dword ptr [rax+rax+00h]
0x180005715  lea     r8, [rbp+4]; dwBytes
0x180005719  xor     edx, edx; dwFlags
0x18000571b  mov     rcx, rax; hHeap
0x18000571e  call    cs:__imp_HeapAlloc
0x180005725  nop     dword ptr [rax+rax+00h]
0x18000572a  mov     rsi, rax
0x18000572d  test    rax, rax
0x180005730  jz      short loc_180005786
0x180005732  mov     dword ptr [rax], 0
0x180005738  mov     rcx, [rdi]
0x18000573b  test    rcx, rcx
0x18000573e  jz      short loc_180005777
0x180005740  or      eax, 0FFFFFFFFh
0x180005743  lock xadd [rcx], eax
0x180005747  cmp     eax, 1
0x18000574a  jnz     short loc_18000576F
0x18000574c  mov     rbx, [rdi]
0x18000574f  call    cs:__imp_GetProcessHeap
0x180005756  nop     dword ptr [rax+rax+00h]
0x18000575b  mov     r8, rbx; lpMem
0x18000575e  xor     edx, edx; dwFlags
0x180005760  mov     rcx, rax; hHeap
0x180005763  call    cs:__imp_HeapFree
0x18000576a  nop     dword ptr [rax+rax+00h]
0x18000576f  mov     qword ptr [rdi+8], 0
0x180005777  mov     [rdi], rsi
0x18000577a  mov     eax, 1
0x18000577f  mov     [rdi+8], rbp
0x180005783  lock add [rsi], eax
0x180005786  add     rsp, 28h
0x18000578a  pop     rdi
0x18000578b  pop     rsi
0x18000578c  pop     rbp
0x18000578d  pop     rbx
0x18000578e  retn
```
