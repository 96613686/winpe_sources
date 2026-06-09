# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800078f4`
- end: `0x1800079dc`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a84`
- `0x1800079f0`

## callees

- `0x1800078f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000796a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000796a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007933`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007933`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000791f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007955`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000799b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000791f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007955`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000799b`

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
0x1800078f4  push    rbx
0x1800078f6  push    rbp
0x1800078f7  push    rsi
0x1800078f8  push    rdi
0x1800078f9  sub     rsp, 28h
0x1800078fd  mov     rbp, rdx
0x180007900  mov     rdi, rcx
0x180007903  test    rdx, rdx
0x180007906  jnz     short loc_180007955
0x180007908  mov     rcx, [rcx]
0x18000790b  test    rcx, rcx
0x18000790e  jz      short loc_18000794E
0x180007910  or      eax, 0FFFFFFFFh
0x180007913  lock xadd [rcx], eax
0x180007917  cmp     eax, 1
0x18000791a  jnz     short loc_18000793F
0x18000791c  mov     rbx, [rdi]
0x18000791f  call    cs:__imp_GetProcessHeap
0x180007926  nop     dword ptr [rax+rax+00h]
0x18000792b  mov     r8, rbx; lpMem
0x18000792e  xor     edx, edx; dwFlags
0x180007930  mov     rcx, rax; hHeap
0x180007933  call    cs:__imp_HeapFree
0x18000793a  nop     dword ptr [rax+rax+00h]
0x18000793f  mov     qword ptr [rdi], 0
0x180007946  mov     qword ptr [rdi+8], 0
0x18000794e  mov     eax, 1
0x180007953  jmp     short loc_1800079D2
0x180007955  call    cs:__imp_GetProcessHeap
0x18000795c  nop     dword ptr [rax+rax+00h]
0x180007961  lea     r8, [rbp+4]; dwBytes
0x180007965  xor     edx, edx; dwFlags
0x180007967  mov     rcx, rax; hHeap
0x18000796a  call    cs:__imp_HeapAlloc
0x180007971  nop     dword ptr [rax+rax+00h]
0x180007976  mov     rsi, rax
0x180007979  test    rax, rax
0x18000797c  jz      short loc_1800079D2
0x18000797e  mov     dword ptr [rax], 0
0x180007984  mov     rcx, [rdi]
0x180007987  test    rcx, rcx
0x18000798a  jz      short loc_1800079C3
0x18000798c  or      eax, 0FFFFFFFFh
0x18000798f  lock xadd [rcx], eax
0x180007993  cmp     eax, 1
0x180007996  jnz     short loc_1800079BB
0x180007998  mov     rbx, [rdi]
0x18000799b  call    cs:__imp_GetProcessHeap
0x1800079a2  nop     dword ptr [rax+rax+00h]
0x1800079a7  mov     r8, rbx; lpMem
0x1800079aa  xor     edx, edx; dwFlags
0x1800079ac  mov     rcx, rax; hHeap
0x1800079af  call    cs:__imp_HeapFree
0x1800079b6  nop     dword ptr [rax+rax+00h]
0x1800079bb  mov     qword ptr [rdi+8], 0
0x1800079c3  mov     [rdi], rsi
0x1800079c6  mov     eax, 1
0x1800079cb  mov     [rdi+8], rbp
0x1800079cf  lock add [rsi], eax
0x1800079d2  add     rsp, 28h
0x1800079d6  pop     rdi
0x1800079d7  pop     rsi
0x1800079d8  pop     rbp
0x1800079d9  pop     rbx
0x1800079da  retn
```
