# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800038e0`
- end: `0x1800039c8`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ff4`
- `0x180003ce0`

## callees

- `0x1800038e0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000391f`
- `KERNEL32!HeapFree` at `0x18000399b`
- `KERNEL32!HeapFree` at `0x18000391f`
- `KERNEL32!HeapFree` at `0x18000399b`
- `KERNEL32!HeapAlloc` at `0x180003956`
- `KERNEL32!HeapAlloc` at `0x180003956`
- `KERNEL32!GetProcessHeap` at `0x18000390b`
- `KERNEL32!GetProcessHeap` at `0x180003941`
- `KERNEL32!GetProcessHeap` at `0x180003987`
- `KERNEL32!GetProcessHeap` at `0x18000390b`
- `KERNEL32!GetProcessHeap` at `0x180003941`
- `KERNEL32!GetProcessHeap` at `0x180003987`

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
0x1800038e0  push    rbx
0x1800038e2  push    rbp
0x1800038e3  push    rsi
0x1800038e4  push    rdi
0x1800038e5  sub     rsp, 28h
0x1800038e9  mov     rbp, rdx
0x1800038ec  mov     rdi, rcx
0x1800038ef  test    rdx, rdx
0x1800038f2  jnz     short loc_180003941
0x1800038f4  mov     rcx, [rcx]
0x1800038f7  test    rcx, rcx
0x1800038fa  jz      short loc_18000393A
0x1800038fc  or      eax, 0FFFFFFFFh
0x1800038ff  lock xadd [rcx], eax
0x180003903  cmp     eax, 1
0x180003906  jnz     short loc_18000392B
0x180003908  mov     rbx, [rdi]
0x18000390b  call    cs:__imp_GetProcessHeap
0x180003912  nop     dword ptr [rax+rax+00h]
0x180003917  mov     r8, rbx; lpMem
0x18000391a  xor     edx, edx; dwFlags
0x18000391c  mov     rcx, rax; hHeap
0x18000391f  call    cs:__imp_HeapFree
0x180003926  nop     dword ptr [rax+rax+00h]
0x18000392b  mov     qword ptr [rdi], 0
0x180003932  mov     qword ptr [rdi+8], 0
0x18000393a  mov     eax, 1
0x18000393f  jmp     short loc_1800039BE
0x180003941  call    cs:__imp_GetProcessHeap
0x180003948  nop     dword ptr [rax+rax+00h]
0x18000394d  lea     r8, [rbp+4]; dwBytes
0x180003951  xor     edx, edx; dwFlags
0x180003953  mov     rcx, rax; hHeap
0x180003956  call    cs:__imp_HeapAlloc
0x18000395d  nop     dword ptr [rax+rax+00h]
0x180003962  mov     rsi, rax
0x180003965  test    rax, rax
0x180003968  jz      short loc_1800039BE
0x18000396a  mov     dword ptr [rax], 0
0x180003970  mov     rcx, [rdi]
0x180003973  test    rcx, rcx
0x180003976  jz      short loc_1800039AF
0x180003978  or      eax, 0FFFFFFFFh
0x18000397b  lock xadd [rcx], eax
0x18000397f  cmp     eax, 1
0x180003982  jnz     short loc_1800039A7
0x180003984  mov     rbx, [rdi]
0x180003987  call    cs:__imp_GetProcessHeap
0x18000398e  nop     dword ptr [rax+rax+00h]
0x180003993  mov     r8, rbx; lpMem
0x180003996  xor     edx, edx; dwFlags
0x180003998  mov     rcx, rax; hHeap
0x18000399b  call    cs:__imp_HeapFree
0x1800039a2  nop     dword ptr [rax+rax+00h]
0x1800039a7  mov     qword ptr [rdi+8], 0
0x1800039af  mov     [rdi], rsi
0x1800039b2  mov     eax, 1
0x1800039b7  mov     [rdi+8], rbp
0x1800039bb  lock add [rsi], eax
0x1800039be  add     rsp, 28h
0x1800039c2  pop     rdi
0x1800039c3  pop     rsi
0x1800039c4  pop     rbp
0x1800039c5  pop     rbx
0x1800039c6  retn
```
