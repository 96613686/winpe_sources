# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x140017744`
- end: `0x140017817`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001552c`
- `0x140015b40`
- `0x140016d78`

## callees

- `0x140015488`
- `0x140017744`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400177e7`
- `KERNEL32!HeapFree` at `0x1400177e7`
- `KERNEL32!GetProcessHeap` at `0x1400177d9`
- `KERNEL32!GetProcessHeap` at `0x1400177d9`
- `KERNEL32!GetLastError` at `0x140017785`
- `KERNEL32!GetLastError` at `0x140017785`
- `KERNEL32!SetLastError` at `0x1400177a9`
- `KERNEL32!SetLastError` at `0x140017802`
- `KERNEL32!SetLastError` at `0x1400177a9`
- `KERNEL32!SetLastError` at `0x140017802`
- `msvcrt!memcpy_s` at `0x1400177c6`
- `msvcrt!memcpy_s` at `0x1400177c6`

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
0x140017744  push    rbx
0x140017746  push    rbp
0x140017747  push    rsi
0x140017748  push    rdi
0x140017749  push    r14
0x14001774b  push    r15
0x14001774d  sub     rsp, 28h
0x140017751  mov     rdi, rcx
0x140017754  mov     rbx, rdx
0x140017757  mov     rcx, [rcx+10h]
0x14001775b  mov     rax, [rdi+8]
0x14001775f  sub     rax, [rdi]
0x140017762  sub     rcx, [rdi]
0x140017765  add     rax, rdx
0x140017768  cmp     rax, rcx
0x14001776b  jb      loc_140017808
0x140017771  lea     rax, [rcx+rcx]
0x140017775  cmp     rdx, rax
0x140017778  cmovb   rbx, rax
0x14001777c  cmp     rcx, rbx
0x14001777f  jnb     loc_140017808
0x140017785  call    cs:__imp_GetLastError
0x14001778b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14001778f  xor     ecx, ecx; dwFlags
0x140017791  mov     esi, eax
0x140017793  lea     r14, [rbx+40h]
0x140017797  mov     rdx, r14; dwBytes
0x14001779a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001779f  mov     rbx, rax
0x1400177a2  test    rax, rax
0x1400177a5  jnz     short loc_1400177B3
0x1400177a7  mov     ecx, esi; dwErrCode
0x1400177a9  call    cs:__imp_SetLastError
0x1400177af  xor     al, al
0x1400177b1  jmp     short loc_14001780A
0x1400177b3  mov     r15, [rdi+8]
0x1400177b7  mov     rdx, r14; DestinationSize
0x1400177ba  sub     r15, [rdi]
0x1400177bd  mov     rcx, rbx; Destination
0x1400177c0  mov     r8, [rdi]; Source
0x1400177c3  mov     r9, r15; SourceSize
0x1400177c6  call    cs:__imp_memcpy_s
0x1400177cc  mov     rbp, [rdi+18h]
0x1400177d0  mov     [rdi+18h], rbx
0x1400177d4  test    rbp, rbp
0x1400177d7  jz      short loc_1400177ED
0x1400177d9  call    cs:__imp_GetProcessHeap
0x1400177df  mov     r8, rbp; lpMem
0x1400177e2  xor     edx, edx; dwFlags
0x1400177e4  mov     rcx, rax; hHeap
0x1400177e7  call    cs:__imp_HeapFree
0x1400177ed  lea     rax, [r15+rbx]
0x1400177f1  mov     [rdi], rbx
0x1400177f4  mov     [rdi+8], rax
0x1400177f8  mov     ecx, esi; dwErrCode
0x1400177fa  lea     rax, [r14+rbx]
0x1400177fe  mov     [rdi+10h], rax
0x140017802  call    cs:__imp_SetLastError
0x140017808  mov     al, 1
0x14001780a  add     rsp, 28h
0x14001780e  pop     r15
0x140017810  pop     r14
0x140017812  pop     rdi
0x140017813  pop     rsi
0x140017814  pop     rbp
0x140017815  pop     rbx
0x140017816  retn
```
