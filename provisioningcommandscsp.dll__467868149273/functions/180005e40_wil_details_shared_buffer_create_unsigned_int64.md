# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005e40`
- end: `0x180005f28`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f7c`
- `0x180006100`

## callees

- `0x180005e40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005efb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005e7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005efb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ea1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ee7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ea1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ee7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005eb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005eb6`

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
0x180005e40  push    rbx
0x180005e42  push    rbp
0x180005e43  push    rsi
0x180005e44  push    rdi
0x180005e45  sub     rsp, 28h
0x180005e49  mov     rbp, rdx
0x180005e4c  mov     rdi, rcx
0x180005e4f  test    rdx, rdx
0x180005e52  jnz     short loc_180005EA1
0x180005e54  mov     rcx, [rcx]
0x180005e57  test    rcx, rcx
0x180005e5a  jz      short loc_180005E9A
0x180005e5c  or      eax, 0FFFFFFFFh
0x180005e5f  lock xadd [rcx], eax
0x180005e63  cmp     eax, 1
0x180005e66  jnz     short loc_180005E8B
0x180005e68  mov     rbx, [rdi]
0x180005e6b  call    cs:__imp_GetProcessHeap
0x180005e72  nop     dword ptr [rax+rax+00h]
0x180005e77  mov     r8, rbx; lpMem
0x180005e7a  xor     edx, edx; dwFlags
0x180005e7c  mov     rcx, rax; hHeap
0x180005e7f  call    cs:__imp_HeapFree
0x180005e86  nop     dword ptr [rax+rax+00h]
0x180005e8b  mov     qword ptr [rdi], 0
0x180005e92  mov     qword ptr [rdi+8], 0
0x180005e9a  mov     eax, 1
0x180005e9f  jmp     short loc_180005F1E
0x180005ea1  call    cs:__imp_GetProcessHeap
0x180005ea8  nop     dword ptr [rax+rax+00h]
0x180005ead  lea     r8, [rbp+4]; dwBytes
0x180005eb1  xor     edx, edx; dwFlags
0x180005eb3  mov     rcx, rax; hHeap
0x180005eb6  call    cs:__imp_HeapAlloc
0x180005ebd  nop     dword ptr [rax+rax+00h]
0x180005ec2  mov     rsi, rax
0x180005ec5  test    rax, rax
0x180005ec8  jz      short loc_180005F1E
0x180005eca  mov     dword ptr [rax], 0
0x180005ed0  mov     rcx, [rdi]
0x180005ed3  test    rcx, rcx
0x180005ed6  jz      short loc_180005F0F
0x180005ed8  or      eax, 0FFFFFFFFh
0x180005edb  lock xadd [rcx], eax
0x180005edf  cmp     eax, 1
0x180005ee2  jnz     short loc_180005F07
0x180005ee4  mov     rbx, [rdi]
0x180005ee7  call    cs:__imp_GetProcessHeap
0x180005eee  nop     dword ptr [rax+rax+00h]
0x180005ef3  mov     r8, rbx; lpMem
0x180005ef6  xor     edx, edx; dwFlags
0x180005ef8  mov     rcx, rax; hHeap
0x180005efb  call    cs:__imp_HeapFree
0x180005f02  nop     dword ptr [rax+rax+00h]
0x180005f07  mov     qword ptr [rdi+8], 0
0x180005f0f  mov     [rdi], rsi
0x180005f12  mov     eax, 1
0x180005f17  mov     [rdi+8], rbp
0x180005f1b  lock add [rsi], eax
0x180005f1e  add     rsp, 28h
0x180005f22  pop     rdi
0x180005f23  pop     rsi
0x180005f24  pop     rbp
0x180005f25  pop     rbx
0x180005f26  retn
```
