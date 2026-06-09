# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009a14`
- end: `0x180009ad7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008630`
- `0x180009ae0`

## callees

- `0x180009a14`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180009a4d`
- `KERNEL32!HeapFree` at `0x180009ab1`
- `KERNEL32!HeapFree` at `0x180009a4d`
- `KERNEL32!HeapFree` at `0x180009ab1`
- `KERNEL32!HeapAlloc` at `0x180009a78`
- `KERNEL32!HeapAlloc` at `0x180009a78`
- `KERNEL32!GetProcessHeap` at `0x180009a3f`
- `KERNEL32!GetProcessHeap` at `0x180009a69`
- `KERNEL32!GetProcessHeap` at `0x180009aa3`
- `KERNEL32!GetProcessHeap` at `0x180009a3f`
- `KERNEL32!GetProcessHeap` at `0x180009a69`
- `KERNEL32!GetProcessHeap` at `0x180009aa3`

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
0x180009a14  push    rbx
0x180009a16  push    rbp
0x180009a17  push    rsi
0x180009a18  push    rdi
0x180009a19  sub     rsp, 28h
0x180009a1d  mov     rbp, rdx
0x180009a20  mov     rdi, rcx
0x180009a23  test    rdx, rdx
0x180009a26  jnz     short loc_180009A69
0x180009a28  mov     rcx, [rcx]
0x180009a2b  test    rcx, rcx
0x180009a2e  jz      short loc_180009A62
0x180009a30  or      eax, 0FFFFFFFFh
0x180009a33  lock xadd [rcx], eax
0x180009a37  cmp     eax, 1
0x180009a3a  jnz     short loc_180009A53
0x180009a3c  mov     rbx, [rdi]
0x180009a3f  call    cs:__imp_GetProcessHeap
0x180009a45  mov     r8, rbx; lpMem
0x180009a48  xor     edx, edx; dwFlags
0x180009a4a  mov     rcx, rax; hHeap
0x180009a4d  call    cs:__imp_HeapFree
0x180009a53  mov     qword ptr [rdi], 0
0x180009a5a  mov     qword ptr [rdi+8], 0
0x180009a62  mov     eax, 1
0x180009a67  jmp     short loc_180009ACE
0x180009a69  call    cs:__imp_GetProcessHeap
0x180009a6f  lea     r8, [rbp+4]; dwBytes
0x180009a73  xor     edx, edx; dwFlags
0x180009a75  mov     rcx, rax; hHeap
0x180009a78  call    cs:__imp_HeapAlloc
0x180009a7e  mov     rsi, rax
0x180009a81  test    rax, rax
0x180009a84  jz      short loc_180009ACE
0x180009a86  mov     dword ptr [rax], 0
0x180009a8c  mov     rcx, [rdi]
0x180009a8f  test    rcx, rcx
0x180009a92  jz      short loc_180009ABF
0x180009a94  or      eax, 0FFFFFFFFh
0x180009a97  lock xadd [rcx], eax
0x180009a9b  cmp     eax, 1
0x180009a9e  jnz     short loc_180009AB7
0x180009aa0  mov     rbx, [rdi]
0x180009aa3  call    cs:__imp_GetProcessHeap
0x180009aa9  mov     r8, rbx; lpMem
0x180009aac  xor     edx, edx; dwFlags
0x180009aae  mov     rcx, rax; hHeap
0x180009ab1  call    cs:__imp_HeapFree
0x180009ab7  mov     qword ptr [rdi+8], 0
0x180009abf  mov     [rdi], rsi
0x180009ac2  mov     eax, 1
0x180009ac7  mov     [rdi+8], rbp
0x180009acb  lock add [rsi], eax
0x180009ace  add     rsp, 28h
0x180009ad2  pop     rdi
0x180009ad3  pop     rsi
0x180009ad4  pop     rbp
0x180009ad5  pop     rbx
0x180009ad6  retn
```
