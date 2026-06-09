# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180015d60`
- end: `0x180015e32`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eacc`
- `0x18000ec70`
- `0x18000f528`
- `0x1800135a0`
- `0x1800137a8`

## callees

- `0x18000e6ac`
- `0x180015d60`
- `0x1800196f0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180015df4`
- `KERNEL32!GetProcessHeap` at `0x180015df4`
- `KERNEL32!GetLastError` at `0x180015da1`
- `KERNEL32!GetLastError` at `0x180015da1`
- `KERNEL32!SetLastError` at `0x180015dc5`
- `KERNEL32!SetLastError` at `0x180015e1d`
- `KERNEL32!SetLastError` at `0x180015dc5`
- `KERNEL32!SetLastError` at `0x180015e1d`
- `KERNEL32!HeapFree` at `0x180015e02`
- `KERNEL32!HeapFree` at `0x180015e02`

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
0x180015d60  push    rbx
0x180015d62  push    rbp
0x180015d63  push    rsi
0x180015d64  push    rdi
0x180015d65  push    r14
0x180015d67  push    r15
0x180015d69  sub     rsp, 28h
0x180015d6d  mov     rdi, rcx
0x180015d70  mov     rbx, rdx
0x180015d73  mov     rcx, [rcx+10h]
0x180015d77  mov     rax, [rdi+8]
0x180015d7b  sub     rax, [rdi]
0x180015d7e  sub     rcx, [rdi]
0x180015d81  add     rax, rdx
0x180015d84  cmp     rax, rcx
0x180015d87  jb      loc_180015E23
0x180015d8d  lea     rax, [rcx+rcx]
0x180015d91  cmp     rdx, rax
0x180015d94  cmovb   rbx, rax
0x180015d98  cmp     rcx, rbx
0x180015d9b  jnb     loc_180015E23
0x180015da1  call    cs:__imp_GetLastError
0x180015da7  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180015dab  xor     ecx, ecx; dwFlags
0x180015dad  mov     esi, eax
0x180015daf  lea     r14, [rbx+40h]
0x180015db3  mov     rdx, r14; dwBytes
0x180015db6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015dbb  mov     rbx, rax
0x180015dbe  test    rax, rax
0x180015dc1  jnz     short loc_180015DCF
0x180015dc3  mov     ecx, esi; dwErrCode
0x180015dc5  call    cs:__imp_SetLastError
0x180015dcb  xor     al, al
0x180015dcd  jmp     short loc_180015E25
0x180015dcf  mov     r15, [rdi+8]
0x180015dd3  mov     rdx, r14; DestinationSize
0x180015dd6  sub     r15, [rdi]
0x180015dd9  mov     rcx, rbx; Destination
0x180015ddc  mov     r8, [rdi]; Source
0x180015ddf  mov     r9, r15; SourceSize
0x180015de2  call    memcpy_s
0x180015de7  mov     rbp, [rdi+18h]
0x180015deb  mov     [rdi+18h], rbx
0x180015def  test    rbp, rbp
0x180015df2  jz      short loc_180015E08
0x180015df4  call    cs:__imp_GetProcessHeap
0x180015dfa  mov     r8, rbp; lpMem
0x180015dfd  xor     edx, edx; dwFlags
0x180015dff  mov     rcx, rax; hHeap
0x180015e02  call    cs:__imp_HeapFree
0x180015e08  lea     rax, [r15+rbx]
0x180015e0c  mov     [rdi], rbx
0x180015e0f  mov     [rdi+8], rax
0x180015e13  mov     ecx, esi; dwErrCode
0x180015e15  lea     rax, [r14+rbx]
0x180015e19  mov     [rdi+10h], rax
0x180015e1d  call    cs:__imp_SetLastError
0x180015e23  mov     al, 1
0x180015e25  add     rsp, 28h
0x180015e29  pop     r15
0x180015e2b  pop     r14
0x180015e2d  pop     rdi
0x180015e2e  pop     rsi
0x180015e2f  pop     rbp
0x180015e30  pop     rbx
0x180015e31  retn
```
