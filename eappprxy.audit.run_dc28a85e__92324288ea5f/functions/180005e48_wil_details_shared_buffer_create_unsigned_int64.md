# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005e48`
- end: `0x180005f30`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d2c`
- `0x180005f40`

## callees

- `0x180005e48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005eef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005eef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ebe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ebe`

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
0x180005e48  push    rbx
0x180005e4a  push    rbp
0x180005e4b  push    rsi
0x180005e4c  push    rdi
0x180005e4d  sub     rsp, 28h
0x180005e51  mov     rbp, rdx
0x180005e54  mov     rdi, rcx
0x180005e57  test    rdx, rdx
0x180005e5a  jnz     short loc_180005EA9
0x180005e5c  mov     rcx, [rcx]
0x180005e5f  test    rcx, rcx
0x180005e62  jz      short loc_180005EA2
0x180005e64  or      eax, 0FFFFFFFFh
0x180005e67  lock xadd [rcx], eax
0x180005e6b  cmp     eax, 1
0x180005e6e  jnz     short loc_180005E93
0x180005e70  mov     rbx, [rdi]
0x180005e73  call    cs:__imp_GetProcessHeap
0x180005e7a  nop     dword ptr [rax+rax+00h]
0x180005e7f  mov     r8, rbx; lpMem
0x180005e82  xor     edx, edx; dwFlags
0x180005e84  mov     rcx, rax; hHeap
0x180005e87  call    cs:__imp_HeapFree
0x180005e8e  nop     dword ptr [rax+rax+00h]
0x180005e93  mov     qword ptr [rdi], 0
0x180005e9a  mov     qword ptr [rdi+8], 0
0x180005ea2  mov     eax, 1
0x180005ea7  jmp     short loc_180005F26
0x180005ea9  call    cs:__imp_GetProcessHeap
0x180005eb0  nop     dword ptr [rax+rax+00h]
0x180005eb5  lea     r8, [rbp+4]; dwBytes
0x180005eb9  xor     edx, edx; dwFlags
0x180005ebb  mov     rcx, rax; hHeap
0x180005ebe  call    cs:__imp_HeapAlloc
0x180005ec5  nop     dword ptr [rax+rax+00h]
0x180005eca  mov     rsi, rax
0x180005ecd  test    rax, rax
0x180005ed0  jz      short loc_180005F26
0x180005ed2  mov     dword ptr [rax], 0
0x180005ed8  mov     rcx, [rdi]
0x180005edb  test    rcx, rcx
0x180005ede  jz      short loc_180005F17
0x180005ee0  or      eax, 0FFFFFFFFh
0x180005ee3  lock xadd [rcx], eax
0x180005ee7  cmp     eax, 1
0x180005eea  jnz     short loc_180005F0F
0x180005eec  mov     rbx, [rdi]
0x180005eef  call    cs:__imp_GetProcessHeap
0x180005ef6  nop     dword ptr [rax+rax+00h]
0x180005efb  mov     r8, rbx; lpMem
0x180005efe  xor     edx, edx; dwFlags
0x180005f00  mov     rcx, rax; hHeap
0x180005f03  call    cs:__imp_HeapFree
0x180005f0a  nop     dword ptr [rax+rax+00h]
0x180005f0f  mov     qword ptr [rdi+8], 0
0x180005f17  mov     [rdi], rsi
0x180005f1a  mov     eax, 1
0x180005f1f  mov     [rdi+8], rbp
0x180005f23  lock add [rsi], eax
0x180005f26  add     rsp, 28h
0x180005f2a  pop     rdi
0x180005f2b  pop     rsi
0x180005f2c  pop     rbp
0x180005f2d  pop     rbx
0x180005f2e  retn
```
