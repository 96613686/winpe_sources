# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008fa0`
- end: `0x180009063`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800084b4`
- `0x1800096e0`

## callees

- `0x180008fa0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008fd9`
- `KERNEL32!HeapFree` at `0x18000903d`
- `KERNEL32!HeapFree` at `0x180008fd9`
- `KERNEL32!HeapFree` at `0x18000903d`
- `KERNEL32!HeapAlloc` at `0x180009004`
- `KERNEL32!HeapAlloc` at `0x180009004`
- `KERNEL32!GetProcessHeap` at `0x180008fcb`
- `KERNEL32!GetProcessHeap` at `0x180008ff5`
- `KERNEL32!GetProcessHeap` at `0x18000902f`
- `KERNEL32!GetProcessHeap` at `0x180008fcb`
- `KERNEL32!GetProcessHeap` at `0x180008ff5`
- `KERNEL32!GetProcessHeap` at `0x18000902f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      this[1] = a2;
      result = 1;
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
0x180008fa0  push    rbx
0x180008fa2  push    rbp
0x180008fa3  push    rsi
0x180008fa4  push    rdi
0x180008fa5  sub     rsp, 28h
0x180008fa9  mov     rbp, rdx
0x180008fac  mov     rdi, rcx
0x180008faf  test    rdx, rdx
0x180008fb2  jnz     short loc_180008FF5
0x180008fb4  mov     rcx, [rcx]
0x180008fb7  test    rcx, rcx
0x180008fba  jz      short loc_180008FEE
0x180008fbc  or      eax, 0FFFFFFFFh
0x180008fbf  lock xadd [rcx], eax
0x180008fc3  cmp     eax, 1
0x180008fc6  jnz     short loc_180008FDF
0x180008fc8  mov     rbx, [rdi]
0x180008fcb  call    cs:__imp_GetProcessHeap
0x180008fd1  mov     r8, rbx; lpMem
0x180008fd4  xor     edx, edx; dwFlags
0x180008fd6  mov     rcx, rax; hHeap
0x180008fd9  call    cs:__imp_HeapFree
0x180008fdf  mov     qword ptr [rdi], 0
0x180008fe6  mov     qword ptr [rdi+8], 0
0x180008fee  mov     eax, 1
0x180008ff3  jmp     short loc_18000905A
0x180008ff5  call    cs:__imp_GetProcessHeap
0x180008ffb  mov     rcx, rax; hHeap
0x180008ffe  lea     r8, [rbp+4]; dwBytes
0x180009002  xor     edx, edx; dwFlags
0x180009004  call    cs:__imp_HeapAlloc
0x18000900a  mov     rsi, rax
0x18000900d  test    rax, rax
0x180009010  jz      short loc_18000905A
0x180009012  mov     dword ptr [rax], 0
0x180009018  mov     rcx, [rdi]
0x18000901b  test    rcx, rcx
0x18000901e  jz      short loc_18000904B
0x180009020  or      eax, 0FFFFFFFFh
0x180009023  lock xadd [rcx], eax
0x180009027  cmp     eax, 1
0x18000902a  jnz     short loc_180009043
0x18000902c  mov     rbx, [rdi]
0x18000902f  call    cs:__imp_GetProcessHeap
0x180009035  mov     r8, rbx; lpMem
0x180009038  xor     edx, edx; dwFlags
0x18000903a  mov     rcx, rax; hHeap
0x18000903d  call    cs:__imp_HeapFree
0x180009043  mov     qword ptr [rdi+8], 0
0x18000904b  mov     [rdi], rsi
0x18000904e  mov     [rdi+8], rbp
0x180009052  mov     eax, 1
0x180009057  lock add [rsi], eax
0x18000905a  add     rsp, 28h
0x18000905e  pop     rdi
0x18000905f  pop     rsi
0x180009060  pop     rbp
0x180009061  pop     rbx
0x180009062  retn
```
