# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000a54c`
- end: `0x18000a61e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180007508`
- `0x180007d88`
- `0x180009714`
- `0x18000991c`
- `0x18000e928`

## callees

- `0x1800073c8`
- `0x18000a54c`
- `0x18000ac08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a5e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a5ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a609`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a58d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a58d`

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
0x18000a54c  push    rbx
0x18000a54e  push    rbp
0x18000a54f  push    rsi
0x18000a550  push    rdi
0x18000a551  push    r14
0x18000a553  push    r15
0x18000a555  sub     rsp, 28h
0x18000a559  mov     rdi, rcx
0x18000a55c  mov     rbx, rdx
0x18000a55f  mov     rcx, [rcx+10h]
0x18000a563  mov     rax, [rdi+8]
0x18000a567  sub     rax, [rdi]
0x18000a56a  sub     rcx, [rdi]
0x18000a56d  add     rax, rdx
0x18000a570  cmp     rax, rcx
0x18000a573  jb      loc_18000A60F
0x18000a579  lea     rax, [rcx+rcx]
0x18000a57d  cmp     rdx, rax
0x18000a580  cmovb   rbx, rax
0x18000a584  cmp     rcx, rbx
0x18000a587  jnb     loc_18000A60F
0x18000a58d  call    cs:__imp_GetLastError
0x18000a593  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000a597  xor     ecx, ecx; dwFlags
0x18000a599  mov     esi, eax
0x18000a59b  lea     r14, [rbx+40h]
0x18000a59f  mov     rdx, r14; dwBytes
0x18000a5a2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a5a7  mov     rbx, rax
0x18000a5aa  test    rax, rax
0x18000a5ad  jnz     short loc_18000A5BB
0x18000a5af  mov     ecx, esi; dwErrCode
0x18000a5b1  call    cs:__imp_SetLastError
0x18000a5b7  xor     al, al
0x18000a5b9  jmp     short loc_18000A611
0x18000a5bb  mov     r15, [rdi+8]
0x18000a5bf  mov     rdx, r14; DestinationSize
0x18000a5c2  sub     r15, [rdi]
0x18000a5c5  mov     rcx, rbx; Destination
0x18000a5c8  mov     r8, [rdi]; Source
0x18000a5cb  mov     r9, r15; SourceSize
0x18000a5ce  call    memcpy_s
0x18000a5d3  mov     rbp, [rdi+18h]
0x18000a5d7  mov     [rdi+18h], rbx
0x18000a5db  test    rbp, rbp
0x18000a5de  jz      short loc_18000A5F4
0x18000a5e0  call    cs:__imp_GetProcessHeap
0x18000a5e6  mov     r8, rbp; lpMem
0x18000a5e9  xor     edx, edx; dwFlags
0x18000a5eb  mov     rcx, rax; hHeap
0x18000a5ee  call    cs:__imp_HeapFree
0x18000a5f4  lea     rax, [r15+rbx]
0x18000a5f8  mov     [rdi], rbx
0x18000a5fb  mov     [rdi+8], rax
0x18000a5ff  mov     ecx, esi; dwErrCode
0x18000a601  lea     rax, [r14+rbx]
0x18000a605  mov     [rdi+10h], rax
0x18000a609  call    cs:__imp_SetLastError
0x18000a60f  mov     al, 1
0x18000a611  add     rsp, 28h
0x18000a615  pop     r15
0x18000a617  pop     r14
0x18000a619  pop     rdi
0x18000a61a  pop     rsi
0x18000a61b  pop     rbp
0x18000a61c  pop     rbx
0x18000a61d  retn
```
