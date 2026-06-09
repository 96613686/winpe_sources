# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000cacc`
- end: `0x18000cb9f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a89c`
- `0x18000aeb0`
- `0x18000c0e8`

## callees

- `0x18000a7f8`
- `0x18000cacc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000cb4e`
- `msvcrt!memcpy_s` at `0x18000cb4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cb61`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  char *v8; // rax
  char *v9; // rbx
  rsize_t v11; // r15
  void *v12; // rbp
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v3 = 2 * v4;
    if ( v4 < v3 )
    {
      LastError = GetLastError();
      v6 = (v3 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v8 = (char *)wil::details::ProcessHeapAlloc(0, v6, v7);
      v9 = v8;
      if ( !v8 )
      {
        SetLastError(LastError);
        return 0;
      }
      v11 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v8, v6, *(const void *const *)this, v11);
      v12 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v9;
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      *(_QWORD *)this = v9;
      *((_QWORD *)this + 1) = &v9[v11];
      *((_QWORD *)this + 2) = &v9[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000cacc  push    rbx
0x18000cace  push    rbp
0x18000cacf  push    rsi
0x18000cad0  push    rdi
0x18000cad1  push    r14
0x18000cad3  push    r15
0x18000cad5  sub     rsp, 28h
0x18000cad9  mov     rdi, rcx
0x18000cadc  mov     rbx, rdx
0x18000cadf  mov     rcx, [rcx+10h]
0x18000cae3  mov     rax, [rdi+8]
0x18000cae7  sub     rax, [rdi]
0x18000caea  sub     rcx, [rdi]
0x18000caed  add     rax, rdx
0x18000caf0  cmp     rax, rcx
0x18000caf3  jb      loc_18000CB90
0x18000caf9  lea     rax, [rcx+rcx]
0x18000cafd  cmp     rdx, rax
0x18000cb00  cmovb   rbx, rax
0x18000cb04  cmp     rcx, rbx
0x18000cb07  jnb     loc_18000CB90
0x18000cb0d  call    cs:__imp_GetLastError
0x18000cb13  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000cb17  xor     ecx, ecx; dwFlags
0x18000cb19  mov     esi, eax
0x18000cb1b  lea     r14, [rbx+40h]
0x18000cb1f  mov     rdx, r14; dwBytes
0x18000cb22  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000cb27  mov     rbx, rax
0x18000cb2a  test    rax, rax
0x18000cb2d  jnz     short loc_18000CB3B
0x18000cb2f  mov     ecx, esi; dwErrCode
0x18000cb31  call    cs:__imp_SetLastError
0x18000cb37  xor     al, al
0x18000cb39  jmp     short loc_18000CB92
0x18000cb3b  mov     r15, [rdi+8]
0x18000cb3f  mov     rdx, r14; DestinationSize
0x18000cb42  sub     r15, [rdi]
0x18000cb45  mov     rcx, rbx; Destination
0x18000cb48  mov     r8, [rdi]; Source
0x18000cb4b  mov     r9, r15; SourceSize
0x18000cb4e  call    cs:__imp_memcpy_s
0x18000cb54  mov     rbp, [rdi+18h]
0x18000cb58  mov     [rdi+18h], rbx
0x18000cb5c  test    rbp, rbp
0x18000cb5f  jz      short loc_18000CB75
0x18000cb61  call    cs:__imp_GetProcessHeap
0x18000cb67  mov     r8, rbp; lpMem
0x18000cb6a  xor     edx, edx; dwFlags
0x18000cb6c  mov     rcx, rax; hHeap
0x18000cb6f  call    cs:__imp_HeapFree
0x18000cb75  lea     rax, [r15+rbx]
0x18000cb79  mov     [rdi], rbx
0x18000cb7c  mov     [rdi+8], rax
0x18000cb80  mov     ecx, esi; dwErrCode
0x18000cb82  lea     rax, [r14+rbx]
0x18000cb86  mov     [rdi+10h], rax
0x18000cb8a  call    cs:__imp_SetLastError
0x18000cb90  mov     al, 1
0x18000cb92  add     rsp, 28h
0x18000cb96  pop     r15
0x18000cb98  pop     r14
0x18000cb9a  pop     rdi
0x18000cb9b  pop     rsi
0x18000cb9c  pop     rbp
0x18000cb9d  pop     rbx
0x18000cb9e  retn
```
