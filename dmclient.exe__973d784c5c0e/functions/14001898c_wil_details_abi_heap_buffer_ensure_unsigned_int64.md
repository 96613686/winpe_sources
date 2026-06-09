# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x14001898c`
- end: `0x140018a84`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140016d68`
- `0x140017338`
- `0x14001816c`

## callees

- `0x14000a98c`
- `0x14001898c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140018a1a`
- `msvcrt!memcpy_s` at `0x140018a1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140018a33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140018a33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140018a47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140018a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400189cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400189cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400189f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018a68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400189f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018a68`

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
0x14001898c  push    rbx
0x14001898e  push    rbp
0x14001898f  push    rsi
0x140018990  push    rdi
0x140018991  push    r14
0x140018993  push    r15
0x140018995  sub     rsp, 28h
0x140018999  mov     rdi, rcx
0x14001899c  mov     rbx, rdx
0x14001899f  mov     rcx, [rcx+10h]
0x1400189a3  mov     rax, [rdi+8]
0x1400189a7  sub     rax, [rdi]
0x1400189aa  sub     rcx, [rdi]
0x1400189ad  add     rax, rdx
0x1400189b0  cmp     rax, rcx
0x1400189b3  jb      loc_140018A74
0x1400189b9  lea     rax, [rcx+rcx]
0x1400189bd  cmp     rdx, rax
0x1400189c0  cmovb   rbx, rax
0x1400189c4  cmp     rcx, rbx
0x1400189c7  jnb     loc_140018A74
0x1400189cd  call    cs:__imp_GetLastError
0x1400189d4  nop     dword ptr [rax+rax+00h]
0x1400189d9  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1400189dd  xor     ecx, ecx; dwFlags
0x1400189df  mov     esi, eax
0x1400189e1  lea     r14, [rbx+40h]
0x1400189e5  mov     rdx, r14; dwBytes
0x1400189e8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400189ed  mov     rbx, rax
0x1400189f0  test    rax, rax
0x1400189f3  jnz     short loc_140018A07
0x1400189f5  mov     ecx, esi; dwErrCode
0x1400189f7  call    cs:__imp_SetLastError
0x1400189fe  nop     dword ptr [rax+rax+00h]
0x140018a03  xor     al, al
0x140018a05  jmp     short loc_140018A76
0x140018a07  mov     r15, [rdi+8]
0x140018a0b  mov     rdx, r14; DestinationSize
0x140018a0e  sub     r15, [rdi]
0x140018a11  mov     rcx, rbx; Destination
0x140018a14  mov     r8, [rdi]; Source
0x140018a17  mov     r9, r15; SourceSize
0x140018a1a  call    cs:__imp_memcpy_s
0x140018a21  nop     dword ptr [rax+rax+00h]
0x140018a26  mov     rbp, [rdi+18h]
0x140018a2a  mov     [rdi+18h], rbx
0x140018a2e  test    rbp, rbp
0x140018a31  jz      short loc_140018A53
0x140018a33  call    cs:__imp_GetProcessHeap
0x140018a3a  nop     dword ptr [rax+rax+00h]
0x140018a3f  mov     r8, rbp; lpMem
0x140018a42  xor     edx, edx; dwFlags
0x140018a44  mov     rcx, rax; hHeap
0x140018a47  call    cs:__imp_HeapFree
0x140018a4e  nop     dword ptr [rax+rax+00h]
0x140018a53  lea     rax, [r15+rbx]
0x140018a57  mov     [rdi], rbx
0x140018a5a  mov     [rdi+8], rax
0x140018a5e  mov     ecx, esi; dwErrCode
0x140018a60  lea     rax, [r14+rbx]
0x140018a64  mov     [rdi+10h], rax
0x140018a68  call    cs:__imp_SetLastError
0x140018a6f  nop     dword ptr [rax+rax+00h]
0x140018a74  mov     al, 1
0x140018a76  add     rsp, 28h
0x140018a7a  pop     r15
0x140018a7c  pop     r14
0x140018a7e  pop     rdi
0x140018a7f  pop     rsi
0x140018a80  pop     rbp
0x140018a81  pop     rbx
0x140018a82  retn
```
