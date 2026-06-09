# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1800078bc`
- end: `0x18000798e`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005500`
- `0x180005b30`
- `0x180006ea8`

## callees

- `0x1800053f8`
- `0x1800078bc`
- `0x180007de8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000795e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000795e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007950`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007921`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007979`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007921`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007979`

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
0x1800078bc  push    rbx
0x1800078be  push    rbp
0x1800078bf  push    rsi
0x1800078c0  push    rdi
0x1800078c1  push    r14
0x1800078c3  push    r15
0x1800078c5  sub     rsp, 28h
0x1800078c9  mov     rdi, rcx
0x1800078cc  mov     rbx, rdx
0x1800078cf  mov     rcx, [rcx+10h]
0x1800078d3  mov     rax, [rdi+8]
0x1800078d7  sub     rax, [rdi]
0x1800078da  sub     rcx, [rdi]
0x1800078dd  add     rax, rdx
0x1800078e0  cmp     rax, rcx
0x1800078e3  jb      loc_18000797F
0x1800078e9  lea     rax, [rcx+rcx]
0x1800078ed  cmp     rdx, rax
0x1800078f0  cmovb   rbx, rax
0x1800078f4  cmp     rcx, rbx
0x1800078f7  jnb     loc_18000797F
0x1800078fd  call    cs:__imp_GetLastError
0x180007903  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180007907  xor     ecx, ecx; dwFlags
0x180007909  mov     esi, eax
0x18000790b  lea     r14, [rbx+40h]
0x18000790f  mov     rdx, r14; dwBytes
0x180007912  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007917  mov     rbx, rax
0x18000791a  test    rax, rax
0x18000791d  jnz     short loc_18000792B
0x18000791f  mov     ecx, esi; dwErrCode
0x180007921  call    cs:__imp_SetLastError
0x180007927  xor     al, al
0x180007929  jmp     short loc_180007981
0x18000792b  mov     r15, [rdi+8]
0x18000792f  mov     rdx, r14; DestinationSize
0x180007932  sub     r15, [rdi]
0x180007935  mov     rcx, rbx; Destination
0x180007938  mov     r8, [rdi]; Source
0x18000793b  mov     r9, r15; SourceSize
0x18000793e  call    memcpy_s
0x180007943  mov     rbp, [rdi+18h]
0x180007947  mov     [rdi+18h], rbx
0x18000794b  test    rbp, rbp
0x18000794e  jz      short loc_180007964
0x180007950  call    cs:__imp_GetProcessHeap
0x180007956  mov     r8, rbp; lpMem
0x180007959  xor     edx, edx; dwFlags
0x18000795b  mov     rcx, rax; hHeap
0x18000795e  call    cs:__imp_HeapFree
0x180007964  lea     rax, [r15+rbx]
0x180007968  mov     [rdi], rbx
0x18000796b  mov     [rdi+8], rax
0x18000796f  mov     ecx, esi; dwErrCode
0x180007971  lea     rax, [r14+rbx]
0x180007975  mov     [rdi+10h], rax
0x180007979  call    cs:__imp_SetLastError
0x18000797f  mov     al, 1
0x180007981  add     rsp, 28h
0x180007985  pop     r15
0x180007987  pop     r14
0x180007989  pop     rdi
0x18000798a  pop     rsi
0x18000798b  pop     rbp
0x18000798c  pop     rbx
0x18000798d  retn
```
