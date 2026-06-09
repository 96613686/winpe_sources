# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005ba4`
- end: `0x180005c67`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e30`
- `0x180005e40`

## callees

- `0x180005ba4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bdd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bdd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c08`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c08`

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
0x180005ba4  push    rbx
0x180005ba6  push    rbp
0x180005ba7  push    rsi
0x180005ba8  push    rdi
0x180005ba9  sub     rsp, 28h
0x180005bad  mov     rbp, rdx
0x180005bb0  mov     rdi, rcx
0x180005bb3  test    rdx, rdx
0x180005bb6  jnz     short loc_180005BF9
0x180005bb8  mov     rcx, [rcx]
0x180005bbb  test    rcx, rcx
0x180005bbe  jz      short loc_180005BF2
0x180005bc0  or      eax, 0FFFFFFFFh
0x180005bc3  lock xadd [rcx], eax
0x180005bc7  cmp     eax, 1
0x180005bca  jnz     short loc_180005BE3
0x180005bcc  mov     rbx, [rdi]
0x180005bcf  call    cs:__imp_GetProcessHeap
0x180005bd5  mov     r8, rbx; lpMem
0x180005bd8  xor     edx, edx; dwFlags
0x180005bda  mov     rcx, rax; hHeap
0x180005bdd  call    cs:__imp_HeapFree
0x180005be3  mov     qword ptr [rdi], 0
0x180005bea  mov     qword ptr [rdi+8], 0
0x180005bf2  mov     eax, 1
0x180005bf7  jmp     short loc_180005C5E
0x180005bf9  call    cs:__imp_GetProcessHeap
0x180005bff  lea     r8, [rbp+4]; dwBytes
0x180005c03  xor     edx, edx; dwFlags
0x180005c05  mov     rcx, rax; hHeap
0x180005c08  call    cs:__imp_HeapAlloc
0x180005c0e  mov     rsi, rax
0x180005c11  test    rax, rax
0x180005c14  jz      short loc_180005C5E
0x180005c16  mov     dword ptr [rax], 0
0x180005c1c  mov     rcx, [rdi]
0x180005c1f  test    rcx, rcx
0x180005c22  jz      short loc_180005C4F
0x180005c24  or      eax, 0FFFFFFFFh
0x180005c27  lock xadd [rcx], eax
0x180005c2b  cmp     eax, 1
0x180005c2e  jnz     short loc_180005C47
0x180005c30  mov     rbx, [rdi]
0x180005c33  call    cs:__imp_GetProcessHeap
0x180005c39  mov     r8, rbx; lpMem
0x180005c3c  xor     edx, edx; dwFlags
0x180005c3e  mov     rcx, rax; hHeap
0x180005c41  call    cs:__imp_HeapFree
0x180005c47  mov     qword ptr [rdi+8], 0
0x180005c4f  mov     [rdi], rsi
0x180005c52  mov     eax, 1
0x180005c57  mov     [rdi+8], rbp
0x180005c5b  lock add [rsi], eax
0x180005c5e  add     rsp, 28h
0x180005c62  pop     rdi
0x180005c63  pop     rsi
0x180005c64  pop     rbp
0x180005c65  pop     rbx
0x180005c66  retn
```
