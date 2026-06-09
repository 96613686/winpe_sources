# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180006318`
- end: `0x1800063eb`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e58`
- `0x18000fd04`
- `0x1800102a4`
- `0x180010f50`

## callees

- `0x1800051fc`
- `0x180006318`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000639a`
- `msvcrt!memcpy_s` at `0x18000639a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006359`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000637d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000637d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800063d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063bb`

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
0x180006318  push    rbx
0x18000631a  push    rbp
0x18000631b  push    rsi
0x18000631c  push    rdi
0x18000631d  push    r14
0x18000631f  push    r15
0x180006321  sub     rsp, 28h
0x180006325  mov     rdi, rcx
0x180006328  mov     rbx, rdx
0x18000632b  mov     rcx, [rcx+10h]
0x18000632f  mov     rax, [rdi+8]
0x180006333  sub     rax, [rdi]
0x180006336  sub     rcx, [rdi]
0x180006339  add     rax, rdx
0x18000633c  cmp     rax, rcx
0x18000633f  jb      loc_1800063DC
0x180006345  lea     rax, [rcx+rcx]
0x180006349  cmp     rdx, rax
0x18000634c  cmovb   rbx, rax
0x180006350  cmp     rcx, rbx
0x180006353  jnb     loc_1800063DC
0x180006359  call    cs:__imp_GetLastError
0x18000635f  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180006363  xor     ecx, ecx; dwFlags
0x180006365  mov     esi, eax
0x180006367  lea     r14, [rbx+40h]
0x18000636b  mov     rdx, r14; dwBytes
0x18000636e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006373  mov     rbx, rax
0x180006376  test    rax, rax
0x180006379  jnz     short loc_180006387
0x18000637b  mov     ecx, esi; dwErrCode
0x18000637d  call    cs:__imp_SetLastError
0x180006383  xor     al, al
0x180006385  jmp     short loc_1800063DE
0x180006387  mov     r15, [rdi+8]
0x18000638b  mov     rdx, r14; DestinationSize
0x18000638e  sub     r15, [rdi]
0x180006391  mov     rcx, rbx; Destination
0x180006394  mov     r8, [rdi]; Source
0x180006397  mov     r9, r15; SourceSize
0x18000639a  call    cs:__imp_memcpy_s
0x1800063a0  mov     rbp, [rdi+18h]
0x1800063a4  mov     [rdi+18h], rbx
0x1800063a8  test    rbp, rbp
0x1800063ab  jz      short loc_1800063C1
0x1800063ad  call    cs:__imp_GetProcessHeap
0x1800063b3  mov     r8, rbp; lpMem
0x1800063b6  xor     edx, edx; dwFlags
0x1800063b8  mov     rcx, rax; hHeap
0x1800063bb  call    cs:__imp_HeapFree
0x1800063c1  lea     rax, [r15+rbx]
0x1800063c5  mov     [rdi], rbx
0x1800063c8  mov     [rdi+8], rax
0x1800063cc  mov     ecx, esi; dwErrCode
0x1800063ce  lea     rax, [r14+rbx]
0x1800063d2  mov     [rdi+10h], rax
0x1800063d6  call    cs:__imp_SetLastError
0x1800063dc  mov     al, 1
0x1800063de  add     rsp, 28h
0x1800063e2  pop     r15
0x1800063e4  pop     r14
0x1800063e6  pop     rdi
0x1800063e7  pop     rsi
0x1800063e8  pop     rbp
0x1800063e9  pop     rbx
0x1800063ea  retn
```
