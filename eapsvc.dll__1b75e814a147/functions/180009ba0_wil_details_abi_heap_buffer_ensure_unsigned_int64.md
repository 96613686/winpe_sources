# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180009ba0`
- end: `0x180009c72`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180006980`
- `0x180007208`
- `0x180008dc0`
- `0x180008fc8`
- `0x18000b6ec`

## callees

- `0x180006840`
- `0x180009ba0`
- `0x180009fe8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009be1`

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
0x180009ba0  push    rbx
0x180009ba2  push    rbp
0x180009ba3  push    rsi
0x180009ba4  push    rdi
0x180009ba5  push    r14
0x180009ba7  push    r15
0x180009ba9  sub     rsp, 28h
0x180009bad  mov     rdi, rcx
0x180009bb0  mov     rbx, rdx
0x180009bb3  mov     rcx, [rcx+10h]
0x180009bb7  mov     rax, [rdi+8]
0x180009bbb  sub     rax, [rdi]
0x180009bbe  sub     rcx, [rdi]
0x180009bc1  add     rax, rdx
0x180009bc4  cmp     rax, rcx
0x180009bc7  jb      loc_180009C63
0x180009bcd  lea     rax, [rcx+rcx]
0x180009bd1  cmp     rdx, rax
0x180009bd4  cmovb   rbx, rax
0x180009bd8  cmp     rcx, rbx
0x180009bdb  jnb     loc_180009C63
0x180009be1  call    cs:__imp_GetLastError
0x180009be7  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180009beb  xor     ecx, ecx; dwFlags
0x180009bed  mov     esi, eax
0x180009bef  lea     r14, [rbx+40h]
0x180009bf3  mov     rdx, r14; dwBytes
0x180009bf6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009bfb  mov     rbx, rax
0x180009bfe  test    rax, rax
0x180009c01  jnz     short loc_180009C0F
0x180009c03  mov     ecx, esi; dwErrCode
0x180009c05  call    cs:__imp_SetLastError
0x180009c0b  xor     al, al
0x180009c0d  jmp     short loc_180009C65
0x180009c0f  mov     r15, [rdi+8]
0x180009c13  mov     rdx, r14; DestinationSize
0x180009c16  sub     r15, [rdi]
0x180009c19  mov     rcx, rbx; Destination
0x180009c1c  mov     r8, [rdi]; Source
0x180009c1f  mov     r9, r15; SourceSize
0x180009c22  call    memcpy_s
0x180009c27  mov     rbp, [rdi+18h]
0x180009c2b  mov     [rdi+18h], rbx
0x180009c2f  test    rbp, rbp
0x180009c32  jz      short loc_180009C48
0x180009c34  call    cs:__imp_GetProcessHeap
0x180009c3a  mov     r8, rbp; lpMem
0x180009c3d  xor     edx, edx; dwFlags
0x180009c3f  mov     rcx, rax; hHeap
0x180009c42  call    cs:__imp_HeapFree
0x180009c48  lea     rax, [r15+rbx]
0x180009c4c  mov     [rdi], rbx
0x180009c4f  mov     [rdi+8], rax
0x180009c53  mov     ecx, esi; dwErrCode
0x180009c55  lea     rax, [r14+rbx]
0x180009c59  mov     [rdi+10h], rax
0x180009c5d  call    cs:__imp_SetLastError
0x180009c63  mov     al, 1
0x180009c65  add     rsp, 28h
0x180009c69  pop     r15
0x180009c6b  pop     r14
0x180009c6d  pop     rdi
0x180009c6e  pop     rsi
0x180009c6f  pop     rbp
0x180009c70  pop     rbx
0x180009c71  retn
```
