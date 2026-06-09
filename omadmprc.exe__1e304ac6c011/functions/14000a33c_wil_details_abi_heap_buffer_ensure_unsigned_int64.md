# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14000a33c`
- end: `0x14000a434`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140006b24`
- `0x140006c9c`
- `0x140007548`
- `0x140008f34`
- `0x14000922c`

## callees

- `0x1400067f8`
- `0x14000a33c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000a3ca`
- `msvcrt!memcpy_s` at `0x14000a3ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a3e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a3e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a3f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a37d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a37d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a3a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a418`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a3a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a418`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
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
      v7 = (char *)wil::details::ProcessHeapAlloc(0, v6);
      v8 = v7;
      if ( !v7 )
      {
        SetLastError(LastError);
        return 0;
      }
      v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v7, v6, *(const void *const *)this, v10);
      v11 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v8;
      if ( v11 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
      *(_QWORD *)this = v8;
      *((_QWORD *)this + 1) = &v8[v10];
      *((_QWORD *)this + 2) = &v8[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000a33c  push    rbx
0x14000a33e  push    rbp
0x14000a33f  push    rsi
0x14000a340  push    rdi
0x14000a341  push    r14
0x14000a343  push    r15
0x14000a345  sub     rsp, 28h
0x14000a349  mov     rdi, rcx
0x14000a34c  mov     rbx, rdx
0x14000a34f  mov     rcx, [rcx+10h]
0x14000a353  mov     rax, [rdi+8]
0x14000a357  sub     rax, [rdi]
0x14000a35a  sub     rcx, [rdi]
0x14000a35d  add     rax, rdx
0x14000a360  cmp     rax, rcx
0x14000a363  jb      loc_14000A424
0x14000a369  lea     rax, [rcx+rcx]
0x14000a36d  cmp     rdx, rax
0x14000a370  cmovb   rbx, rax
0x14000a374  cmp     rcx, rbx
0x14000a377  jnb     loc_14000A424
0x14000a37d  call    cs:__imp_GetLastError
0x14000a384  nop     dword ptr [rax+rax+00h]
0x14000a389  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000a38d  xor     ecx, ecx; dwFlags
0x14000a38f  mov     esi, eax
0x14000a391  lea     r14, [rbx+40h]
0x14000a395  mov     rdx, r14; dwBytes
0x14000a398  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000a39d  mov     rbx, rax
0x14000a3a0  test    rax, rax
0x14000a3a3  jnz     short loc_14000A3B7
0x14000a3a5  mov     ecx, esi; dwErrCode
0x14000a3a7  call    cs:__imp_SetLastError
0x14000a3ae  nop     dword ptr [rax+rax+00h]
0x14000a3b3  xor     al, al
0x14000a3b5  jmp     short loc_14000A426
0x14000a3b7  mov     r15, [rdi+8]
0x14000a3bb  mov     rdx, r14; DestinationSize
0x14000a3be  sub     r15, [rdi]
0x14000a3c1  mov     rcx, rbx; Destination
0x14000a3c4  mov     r8, [rdi]; Source
0x14000a3c7  mov     r9, r15; SourceSize
0x14000a3ca  call    cs:__imp_memcpy_s
0x14000a3d1  nop     dword ptr [rax+rax+00h]
0x14000a3d6  mov     rbp, [rdi+18h]
0x14000a3da  mov     [rdi+18h], rbx
0x14000a3de  test    rbp, rbp
0x14000a3e1  jz      short loc_14000A403
0x14000a3e3  call    cs:__imp_GetProcessHeap
0x14000a3ea  nop     dword ptr [rax+rax+00h]
0x14000a3ef  mov     r8, rbp; lpMem
0x14000a3f2  xor     edx, edx; dwFlags
0x14000a3f4  mov     rcx, rax; hHeap
0x14000a3f7  call    cs:__imp_HeapFree
0x14000a3fe  nop     dword ptr [rax+rax+00h]
0x14000a403  lea     rax, [r15+rbx]
0x14000a407  mov     [rdi], rbx
0x14000a40a  mov     [rdi+8], rax
0x14000a40e  mov     ecx, esi; dwErrCode
0x14000a410  lea     rax, [r14+rbx]
0x14000a414  mov     [rdi+10h], rax
0x14000a418  call    cs:__imp_SetLastError
0x14000a41f  nop     dword ptr [rax+rax+00h]
0x14000a424  mov     al, 1
0x14000a426  add     rsp, 28h
0x14000a42a  pop     r15
0x14000a42c  pop     r14
0x14000a42e  pop     rdi
0x14000a42f  pop     rsi
0x14000a430  pop     rbp
0x14000a431  pop     rbx
0x14000a432  retn
```
