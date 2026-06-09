# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180015b70`
- end: `0x180015c33`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180010f70`
- `0x180018fa0`

## callees

- `0x180015b70`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180015b9b`
- `KERNEL32!GetProcessHeap` at `0x180015bc5`
- `KERNEL32!GetProcessHeap` at `0x180015bff`
- `KERNEL32!GetProcessHeap` at `0x180015b9b`
- `KERNEL32!GetProcessHeap` at `0x180015bc5`
- `KERNEL32!GetProcessHeap` at `0x180015bff`
- `KERNEL32!HeapAlloc` at `0x180015bd4`
- `KERNEL32!HeapAlloc` at `0x180015bd4`
- `KERNEL32!HeapFree` at `0x180015ba9`
- `KERNEL32!HeapFree` at `0x180015c0d`
- `KERNEL32!HeapFree` at `0x180015ba9`
- `KERNEL32!HeapFree` at `0x180015c0d`

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
0x180015b70  push    rbx
0x180015b72  push    rbp
0x180015b73  push    rsi
0x180015b74  push    rdi
0x180015b75  sub     rsp, 28h
0x180015b79  mov     rbp, rdx
0x180015b7c  mov     rdi, rcx
0x180015b7f  test    rdx, rdx
0x180015b82  jnz     short loc_180015BC5
0x180015b84  mov     rcx, [rcx]
0x180015b87  test    rcx, rcx
0x180015b8a  jz      short loc_180015BBE
0x180015b8c  or      eax, 0FFFFFFFFh
0x180015b8f  lock xadd [rcx], eax
0x180015b93  cmp     eax, 1
0x180015b96  jnz     short loc_180015BAF
0x180015b98  mov     rbx, [rdi]
0x180015b9b  call    cs:__imp_GetProcessHeap
0x180015ba1  mov     r8, rbx; lpMem
0x180015ba4  xor     edx, edx; dwFlags
0x180015ba6  mov     rcx, rax; hHeap
0x180015ba9  call    cs:__imp_HeapFree
0x180015baf  mov     qword ptr [rdi], 0
0x180015bb6  mov     qword ptr [rdi+8], 0
0x180015bbe  mov     eax, 1
0x180015bc3  jmp     short loc_180015C2A
0x180015bc5  call    cs:__imp_GetProcessHeap
0x180015bcb  lea     r8, [rbp+4]; dwBytes
0x180015bcf  xor     edx, edx; dwFlags
0x180015bd1  mov     rcx, rax; hHeap
0x180015bd4  call    cs:__imp_HeapAlloc
0x180015bda  mov     rsi, rax
0x180015bdd  test    rax, rax
0x180015be0  jz      short loc_180015C2A
0x180015be2  mov     dword ptr [rax], 0
0x180015be8  mov     rcx, [rdi]
0x180015beb  test    rcx, rcx
0x180015bee  jz      short loc_180015C1B
0x180015bf0  or      eax, 0FFFFFFFFh
0x180015bf3  lock xadd [rcx], eax
0x180015bf7  cmp     eax, 1
0x180015bfa  jnz     short loc_180015C13
0x180015bfc  mov     rbx, [rdi]
0x180015bff  call    cs:__imp_GetProcessHeap
0x180015c05  mov     r8, rbx; lpMem
0x180015c08  xor     edx, edx; dwFlags
0x180015c0a  mov     rcx, rax; hHeap
0x180015c0d  call    cs:__imp_HeapFree
0x180015c13  mov     qword ptr [rdi+8], 0
0x180015c1b  mov     [rdi], rsi
0x180015c1e  mov     eax, 1
0x180015c23  mov     [rdi+8], rbp
0x180015c27  lock add [rsi], eax
0x180015c2a  add     rsp, 28h
0x180015c2e  pop     rdi
0x180015c2f  pop     rsi
0x180015c30  pop     rbp
0x180015c31  pop     rbx
0x180015c32  retn
```
