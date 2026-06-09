# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000a270`
- end: `0x18000a342`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800069f8`
- `0x180007238`
- `0x180009138`
- `0x180009340`
- `0x18000bcf0`

## callees

- `0x1800068b8`
- `0x18000a270`
- `0x18000a8b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a304`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a304`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a312`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a312`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a2d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a32d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a2d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a32d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2b1`

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
0x18000a270  push    rbx
0x18000a272  push    rbp
0x18000a273  push    rsi
0x18000a274  push    rdi
0x18000a275  push    r14
0x18000a277  push    r15
0x18000a279  sub     rsp, 28h
0x18000a27d  mov     rdi, rcx
0x18000a280  mov     rbx, rdx
0x18000a283  mov     rcx, [rcx+10h]
0x18000a287  mov     rax, [rdi+8]
0x18000a28b  sub     rax, [rdi]
0x18000a28e  sub     rcx, [rdi]
0x18000a291  add     rax, rdx
0x18000a294  cmp     rax, rcx
0x18000a297  jb      loc_18000A333
0x18000a29d  lea     rax, [rcx+rcx]
0x18000a2a1  cmp     rdx, rax
0x18000a2a4  cmovb   rbx, rax
0x18000a2a8  cmp     rcx, rbx
0x18000a2ab  jnb     loc_18000A333
0x18000a2b1  call    cs:__imp_GetLastError
0x18000a2b7  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000a2bb  xor     ecx, ecx; dwFlags
0x18000a2bd  mov     esi, eax
0x18000a2bf  lea     r14, [rbx+40h]
0x18000a2c3  mov     rdx, r14; dwBytes
0x18000a2c6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a2cb  mov     rbx, rax
0x18000a2ce  test    rax, rax
0x18000a2d1  jnz     short loc_18000A2DF
0x18000a2d3  mov     ecx, esi; dwErrCode
0x18000a2d5  call    cs:__imp_SetLastError
0x18000a2db  xor     al, al
0x18000a2dd  jmp     short loc_18000A335
0x18000a2df  mov     r15, [rdi+8]
0x18000a2e3  mov     rdx, r14; DestinationSize
0x18000a2e6  sub     r15, [rdi]
0x18000a2e9  mov     rcx, rbx; Destination
0x18000a2ec  mov     r8, [rdi]; Source
0x18000a2ef  mov     r9, r15; SourceSize
0x18000a2f2  call    memcpy_s
0x18000a2f7  mov     rbp, [rdi+18h]
0x18000a2fb  mov     [rdi+18h], rbx
0x18000a2ff  test    rbp, rbp
0x18000a302  jz      short loc_18000A318
0x18000a304  call    cs:__imp_GetProcessHeap
0x18000a30a  mov     r8, rbp; lpMem
0x18000a30d  xor     edx, edx; dwFlags
0x18000a30f  mov     rcx, rax; hHeap
0x18000a312  call    cs:__imp_HeapFree
0x18000a318  lea     rax, [r15+rbx]
0x18000a31c  mov     [rdi], rbx
0x18000a31f  mov     [rdi+8], rax
0x18000a323  mov     ecx, esi; dwErrCode
0x18000a325  lea     rax, [r14+rbx]
0x18000a329  mov     [rdi+10h], rax
0x18000a32d  call    cs:__imp_SetLastError
0x18000a333  mov     al, 1
0x18000a335  add     rsp, 28h
0x18000a339  pop     r15
0x18000a33b  pop     r14
0x18000a33d  pop     rdi
0x18000a33e  pop     rsi
0x18000a33f  pop     rbp
0x18000a340  pop     rbx
0x18000a341  retn
```
