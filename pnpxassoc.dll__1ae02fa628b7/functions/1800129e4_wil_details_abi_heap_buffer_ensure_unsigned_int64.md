# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1800129e4`
- end: `0x180012ab7`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800111a8`
- `0x180011748`
- `0x1800123f4`

## callees

- `0x1800048e8`
- `0x1800129e4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012a66`
- `msvcrt!memcpy_s` at `0x180012a66`
- `KERNEL32!HeapFree` at `0x180012a87`
- `KERNEL32!HeapFree` at `0x180012a87`
- `KERNEL32!SetLastError` at `0x180012a49`
- `KERNEL32!SetLastError` at `0x180012aa2`
- `KERNEL32!SetLastError` at `0x180012a49`
- `KERNEL32!SetLastError` at `0x180012aa2`
- `KERNEL32!GetLastError` at `0x180012a25`
- `KERNEL32!GetLastError` at `0x180012a25`
- `KERNEL32!GetProcessHeap` at `0x180012a79`
- `KERNEL32!GetProcessHeap` at `0x180012a79`

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
0x1800129e4  push    rbx
0x1800129e6  push    rbp
0x1800129e7  push    rsi
0x1800129e8  push    rdi
0x1800129e9  push    r14
0x1800129eb  push    r15
0x1800129ed  sub     rsp, 28h
0x1800129f1  mov     rdi, rcx
0x1800129f4  mov     rbx, rdx
0x1800129f7  mov     rcx, [rcx+10h]
0x1800129fb  mov     rax, [rdi+8]
0x1800129ff  sub     rax, [rdi]
0x180012a02  sub     rcx, [rdi]
0x180012a05  add     rax, rdx
0x180012a08  cmp     rax, rcx
0x180012a0b  jb      loc_180012AA8
0x180012a11  lea     rax, [rcx+rcx]
0x180012a15  cmp     rdx, rax
0x180012a18  cmovb   rbx, rax
0x180012a1c  cmp     rcx, rbx
0x180012a1f  jnb     loc_180012AA8
0x180012a25  call    cs:__imp_GetLastError
0x180012a2b  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180012a2f  xor     ecx, ecx; dwFlags
0x180012a31  mov     esi, eax
0x180012a33  lea     r14, [rbx+40h]
0x180012a37  mov     rdx, r14; dwBytes
0x180012a3a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180012a3f  mov     rbx, rax
0x180012a42  test    rax, rax
0x180012a45  jnz     short loc_180012A53
0x180012a47  mov     ecx, esi; dwErrCode
0x180012a49  call    cs:__imp_SetLastError
0x180012a4f  xor     al, al
0x180012a51  jmp     short loc_180012AAA
0x180012a53  mov     r15, [rdi+8]
0x180012a57  mov     rdx, r14; DestinationSize
0x180012a5a  sub     r15, [rdi]
0x180012a5d  mov     rcx, rbx; Destination
0x180012a60  mov     r8, [rdi]; Source
0x180012a63  mov     r9, r15; SourceSize
0x180012a66  call    cs:__imp_memcpy_s
0x180012a6c  mov     rbp, [rdi+18h]
0x180012a70  mov     [rdi+18h], rbx
0x180012a74  test    rbp, rbp
0x180012a77  jz      short loc_180012A8D
0x180012a79  call    cs:__imp_GetProcessHeap
0x180012a7f  mov     r8, rbp; lpMem
0x180012a82  xor     edx, edx; dwFlags
0x180012a84  mov     rcx, rax; hHeap
0x180012a87  call    cs:__imp_HeapFree
0x180012a8d  lea     rax, [r15+rbx]
0x180012a91  mov     [rdi], rbx
0x180012a94  mov     [rdi+8], rax
0x180012a98  mov     ecx, esi; dwErrCode
0x180012a9a  lea     rax, [r14+rbx]
0x180012a9e  mov     [rdi+10h], rax
0x180012aa2  call    cs:__imp_SetLastError
0x180012aa8  mov     al, 1
0x180012aaa  add     rsp, 28h
0x180012aae  pop     r15
0x180012ab0  pop     r14
0x180012ab2  pop     rdi
0x180012ab3  pop     rsi
0x180012ab4  pop     rbp
0x180012ab5  pop     rbx
0x180012ab6  retn
```
