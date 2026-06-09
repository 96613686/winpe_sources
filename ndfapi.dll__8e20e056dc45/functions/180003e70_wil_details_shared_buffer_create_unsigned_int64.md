# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180003e70`
- end: `0x180003f33`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003714`
- `0x180003f40`

## callees

- `0x180003e70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003ea9`
- `KERNEL32!HeapFree` at `0x180003f0d`
- `KERNEL32!HeapFree` at `0x180003ea9`
- `KERNEL32!HeapFree` at `0x180003f0d`
- `KERNEL32!HeapAlloc` at `0x180003ed4`
- `KERNEL32!HeapAlloc` at `0x180003ed4`
- `KERNEL32!GetProcessHeap` at `0x180003e9b`
- `KERNEL32!GetProcessHeap` at `0x180003ec5`
- `KERNEL32!GetProcessHeap` at `0x180003eff`
- `KERNEL32!GetProcessHeap` at `0x180003e9b`
- `KERNEL32!GetProcessHeap` at `0x180003ec5`
- `KERNEL32!GetProcessHeap` at `0x180003eff`

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
0x180003e70  push    rbx
0x180003e72  push    rbp
0x180003e73  push    rsi
0x180003e74  push    rdi
0x180003e75  sub     rsp, 28h
0x180003e79  mov     rbp, rdx
0x180003e7c  mov     rdi, rcx
0x180003e7f  test    rdx, rdx
0x180003e82  jnz     short loc_180003EC5
0x180003e84  mov     rcx, [rcx]
0x180003e87  test    rcx, rcx
0x180003e8a  jz      short loc_180003EBE
0x180003e8c  or      eax, 0FFFFFFFFh
0x180003e8f  lock xadd [rcx], eax
0x180003e93  cmp     eax, 1
0x180003e96  jnz     short loc_180003EAF
0x180003e98  mov     rbx, [rdi]
0x180003e9b  call    cs:__imp_GetProcessHeap
0x180003ea1  mov     r8, rbx; lpMem
0x180003ea4  xor     edx, edx; dwFlags
0x180003ea6  mov     rcx, rax; hHeap
0x180003ea9  call    cs:__imp_HeapFree
0x180003eaf  mov     qword ptr [rdi], 0
0x180003eb6  mov     qword ptr [rdi+8], 0
0x180003ebe  mov     eax, 1
0x180003ec3  jmp     short loc_180003F2A
0x180003ec5  call    cs:__imp_GetProcessHeap
0x180003ecb  lea     r8, [rbp+4]; dwBytes
0x180003ecf  xor     edx, edx; dwFlags
0x180003ed1  mov     rcx, rax; hHeap
0x180003ed4  call    cs:__imp_HeapAlloc
0x180003eda  mov     rsi, rax
0x180003edd  test    rax, rax
0x180003ee0  jz      short loc_180003F2A
0x180003ee2  mov     dword ptr [rax], 0
0x180003ee8  mov     rcx, [rdi]
0x180003eeb  test    rcx, rcx
0x180003eee  jz      short loc_180003F1B
0x180003ef0  or      eax, 0FFFFFFFFh
0x180003ef3  lock xadd [rcx], eax
0x180003ef7  cmp     eax, 1
0x180003efa  jnz     short loc_180003F13
0x180003efc  mov     rbx, [rdi]
0x180003eff  call    cs:__imp_GetProcessHeap
0x180003f05  mov     r8, rbx; lpMem
0x180003f08  xor     edx, edx; dwFlags
0x180003f0a  mov     rcx, rax; hHeap
0x180003f0d  call    cs:__imp_HeapFree
0x180003f13  mov     qword ptr [rdi+8], 0
0x180003f1b  mov     [rdi], rsi
0x180003f1e  mov     eax, 1
0x180003f23  mov     [rdi+8], rbp
0x180003f27  lock add [rsi], eax
0x180003f2a  add     rsp, 28h
0x180003f2e  pop     rdi
0x180003f2f  pop     rsi
0x180003f30  pop     rbp
0x180003f31  pop     rbx
0x180003f32  retn
```
