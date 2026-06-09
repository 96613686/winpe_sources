# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007f54`
- end: `0x180008017`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006c98`
- `0x180008110`

## callees

- `0x180007f54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ff1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fe3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fe3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007fb8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007fb8`

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
0x180007f54  push    rbx
0x180007f56  push    rbp
0x180007f57  push    rsi
0x180007f58  push    rdi
0x180007f59  sub     rsp, 28h
0x180007f5d  mov     rbp, rdx
0x180007f60  mov     rdi, rcx
0x180007f63  test    rdx, rdx
0x180007f66  jnz     short loc_180007FA9
0x180007f68  mov     rcx, [rcx]
0x180007f6b  test    rcx, rcx
0x180007f6e  jz      short loc_180007FA2
0x180007f70  or      eax, 0FFFFFFFFh
0x180007f73  lock xadd [rcx], eax
0x180007f77  cmp     eax, 1
0x180007f7a  jnz     short loc_180007F93
0x180007f7c  mov     rbx, [rdi]
0x180007f7f  call    cs:__imp_GetProcessHeap
0x180007f85  mov     r8, rbx; lpMem
0x180007f88  xor     edx, edx; dwFlags
0x180007f8a  mov     rcx, rax; hHeap
0x180007f8d  call    cs:__imp_HeapFree
0x180007f93  mov     qword ptr [rdi], 0
0x180007f9a  mov     qword ptr [rdi+8], 0
0x180007fa2  mov     eax, 1
0x180007fa7  jmp     short loc_18000800E
0x180007fa9  call    cs:__imp_GetProcessHeap
0x180007faf  lea     r8, [rbp+4]; dwBytes
0x180007fb3  xor     edx, edx; dwFlags
0x180007fb5  mov     rcx, rax; hHeap
0x180007fb8  call    cs:__imp_HeapAlloc
0x180007fbe  mov     rsi, rax
0x180007fc1  test    rax, rax
0x180007fc4  jz      short loc_18000800E
0x180007fc6  mov     dword ptr [rax], 0
0x180007fcc  mov     rcx, [rdi]
0x180007fcf  test    rcx, rcx
0x180007fd2  jz      short loc_180007FFF
0x180007fd4  or      eax, 0FFFFFFFFh
0x180007fd7  lock xadd [rcx], eax
0x180007fdb  cmp     eax, 1
0x180007fde  jnz     short loc_180007FF7
0x180007fe0  mov     rbx, [rdi]
0x180007fe3  call    cs:__imp_GetProcessHeap
0x180007fe9  mov     r8, rbx; lpMem
0x180007fec  xor     edx, edx; dwFlags
0x180007fee  mov     rcx, rax; hHeap
0x180007ff1  call    cs:__imp_HeapFree
0x180007ff7  mov     qword ptr [rdi+8], 0
0x180007fff  mov     [rdi], rsi
0x180008002  mov     eax, 1
0x180008007  mov     [rdi+8], rbp
0x18000800b  lock add [rsi], eax
0x18000800e  add     rsp, 28h
0x180008012  pop     rdi
0x180008013  pop     rsi
0x180008014  pop     rbp
0x180008015  pop     rbx
0x180008016  retn
```
