# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000cf54`
- end: `0x18000d017`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bdc8`
- `0x18000d100`

## callees

- `0x18000cf54`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000cf8d`
- `KERNEL32!HeapFree` at `0x18000cff1`
- `KERNEL32!HeapFree` at `0x18000cf8d`
- `KERNEL32!HeapFree` at `0x18000cff1`
- `KERNEL32!HeapAlloc` at `0x18000cfb8`
- `KERNEL32!HeapAlloc` at `0x18000cfb8`
- `KERNEL32!GetProcessHeap` at `0x18000cf7f`
- `KERNEL32!GetProcessHeap` at `0x18000cfa9`
- `KERNEL32!GetProcessHeap` at `0x18000cfe3`
- `KERNEL32!GetProcessHeap` at `0x18000cf7f`
- `KERNEL32!GetProcessHeap` at `0x18000cfa9`
- `KERNEL32!GetProcessHeap` at `0x18000cfe3`

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
0x18000cf54  push    rbx
0x18000cf56  push    rbp
0x18000cf57  push    rsi
0x18000cf58  push    rdi
0x18000cf59  sub     rsp, 28h
0x18000cf5d  mov     rbp, rdx
0x18000cf60  mov     rdi, rcx
0x18000cf63  test    rdx, rdx
0x18000cf66  jnz     short loc_18000CFA9
0x18000cf68  mov     rcx, [rcx]
0x18000cf6b  test    rcx, rcx
0x18000cf6e  jz      short loc_18000CFA2
0x18000cf70  or      eax, 0FFFFFFFFh
0x18000cf73  lock xadd [rcx], eax
0x18000cf77  cmp     eax, 1
0x18000cf7a  jnz     short loc_18000CF93
0x18000cf7c  mov     rbx, [rdi]
0x18000cf7f  call    cs:__imp_GetProcessHeap
0x18000cf85  mov     r8, rbx; lpMem
0x18000cf88  xor     edx, edx; dwFlags
0x18000cf8a  mov     rcx, rax; hHeap
0x18000cf8d  call    cs:__imp_HeapFree
0x18000cf93  mov     qword ptr [rdi], 0
0x18000cf9a  mov     qword ptr [rdi+8], 0
0x18000cfa2  mov     eax, 1
0x18000cfa7  jmp     short loc_18000D00E
0x18000cfa9  call    cs:__imp_GetProcessHeap
0x18000cfaf  lea     r8, [rbp+4]; dwBytes
0x18000cfb3  xor     edx, edx; dwFlags
0x18000cfb5  mov     rcx, rax; hHeap
0x18000cfb8  call    cs:__imp_HeapAlloc
0x18000cfbe  mov     rsi, rax
0x18000cfc1  test    rax, rax
0x18000cfc4  jz      short loc_18000D00E
0x18000cfc6  mov     dword ptr [rax], 0
0x18000cfcc  mov     rcx, [rdi]
0x18000cfcf  test    rcx, rcx
0x18000cfd2  jz      short loc_18000CFFF
0x18000cfd4  or      eax, 0FFFFFFFFh
0x18000cfd7  lock xadd [rcx], eax
0x18000cfdb  cmp     eax, 1
0x18000cfde  jnz     short loc_18000CFF7
0x18000cfe0  mov     rbx, [rdi]
0x18000cfe3  call    cs:__imp_GetProcessHeap
0x18000cfe9  mov     r8, rbx; lpMem
0x18000cfec  xor     edx, edx; dwFlags
0x18000cfee  mov     rcx, rax; hHeap
0x18000cff1  call    cs:__imp_HeapFree
0x18000cff7  mov     qword ptr [rdi+8], 0
0x18000cfff  mov     [rdi], rsi
0x18000d002  mov     eax, 1
0x18000d007  mov     [rdi+8], rbp
0x18000d00b  lock add [rsi], eax
0x18000d00e  add     rsp, 28h
0x18000d012  pop     rdi
0x18000d013  pop     rsi
0x18000d014  pop     rbp
0x18000d015  pop     rbx
0x18000d016  retn
```
