# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x140016bbc`
- end: `0x140016c8f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140014a8c`
- `0x140015034`
- `0x1400165cc`

## callees

- `0x14000a74c`
- `0x140016bbc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140016c3e`
- `msvcrt!memcpy_s` at `0x140016c3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016c51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016c51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016c5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016bfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016c21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016c7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016c21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140016c7a`

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
0x140016bbc  push    rbx
0x140016bbe  push    rbp
0x140016bbf  push    rsi
0x140016bc0  push    rdi
0x140016bc1  push    r14
0x140016bc3  push    r15
0x140016bc5  sub     rsp, 28h
0x140016bc9  mov     rdi, rcx
0x140016bcc  mov     rbx, rdx
0x140016bcf  mov     rcx, [rcx+10h]
0x140016bd3  mov     rax, [rdi+8]
0x140016bd7  sub     rax, [rdi]
0x140016bda  sub     rcx, [rdi]
0x140016bdd  add     rax, rdx
0x140016be0  cmp     rax, rcx
0x140016be3  jb      loc_140016C80
0x140016be9  lea     rax, [rcx+rcx]
0x140016bed  cmp     rdx, rax
0x140016bf0  cmovb   rbx, rax
0x140016bf4  cmp     rcx, rbx
0x140016bf7  jnb     loc_140016C80
0x140016bfd  call    cs:__imp_GetLastError
0x140016c03  and     rbx, 0FFFFFFFFFFFFFFC0h
0x140016c07  xor     ecx, ecx; dwFlags
0x140016c09  mov     esi, eax
0x140016c0b  lea     r14, [rbx+40h]
0x140016c0f  mov     rdx, r14; dwBytes
0x140016c12  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140016c17  mov     rbx, rax
0x140016c1a  test    rax, rax
0x140016c1d  jnz     short loc_140016C2B
0x140016c1f  mov     ecx, esi; dwErrCode
0x140016c21  call    cs:__imp_SetLastError
0x140016c27  xor     al, al
0x140016c29  jmp     short loc_140016C82
0x140016c2b  mov     r15, [rdi+8]
0x140016c2f  mov     rdx, r14; DestinationSize
0x140016c32  sub     r15, [rdi]
0x140016c35  mov     rcx, rbx; Destination
0x140016c38  mov     r8, [rdi]; Source
0x140016c3b  mov     r9, r15; SourceSize
0x140016c3e  call    cs:__imp_memcpy_s
0x140016c44  mov     rbp, [rdi+18h]
0x140016c48  mov     [rdi+18h], rbx
0x140016c4c  test    rbp, rbp
0x140016c4f  jz      short loc_140016C65
0x140016c51  call    cs:__imp_GetProcessHeap
0x140016c57  mov     r8, rbp; lpMem
0x140016c5a  xor     edx, edx; dwFlags
0x140016c5c  mov     rcx, rax; hHeap
0x140016c5f  call    cs:__imp_HeapFree
0x140016c65  lea     rax, [r15+rbx]
0x140016c69  mov     [rdi], rbx
0x140016c6c  mov     [rdi+8], rax
0x140016c70  mov     ecx, esi; dwErrCode
0x140016c72  lea     rax, [r14+rbx]
0x140016c76  mov     [rdi+10h], rax
0x140016c7a  call    cs:__imp_SetLastError
0x140016c80  mov     al, 1
0x140016c82  add     rsp, 28h
0x140016c86  pop     r15
0x140016c88  pop     r14
0x140016c8a  pop     rdi
0x140016c8b  pop     rsi
0x140016c8c  pop     rbp
0x140016c8d  pop     rbx
0x140016c8e  retn
```
