# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000d020`
- end: `0x18000d0f3`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a9ac`
- `0x18000afc8`
- `0x18000c554`

## callees

- `0x18000a908`
- `0x18000d020`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d0a2`
- `msvcrt!memcpy_s` at `0x18000d0a2`
- `KERNEL32!SetLastError` at `0x18000d085`
- `KERNEL32!SetLastError` at `0x18000d0de`
- `KERNEL32!SetLastError` at `0x18000d085`
- `KERNEL32!SetLastError` at `0x18000d0de`
- `KERNEL32!HeapFree` at `0x18000d0c3`
- `KERNEL32!HeapFree` at `0x18000d0c3`
- `KERNEL32!GetProcessHeap` at `0x18000d0b5`
- `KERNEL32!GetProcessHeap` at `0x18000d0b5`
- `KERNEL32!GetLastError` at `0x18000d061`
- `KERNEL32!GetLastError` at `0x18000d061`

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
0x18000d020  push    rbx
0x18000d022  push    rbp
0x18000d023  push    rsi
0x18000d024  push    rdi
0x18000d025  push    r14
0x18000d027  push    r15
0x18000d029  sub     rsp, 28h
0x18000d02d  mov     rdi, rcx
0x18000d030  mov     rbx, rdx
0x18000d033  mov     rcx, [rcx+10h]
0x18000d037  mov     rax, [rdi+8]
0x18000d03b  sub     rax, [rdi]
0x18000d03e  sub     rcx, [rdi]
0x18000d041  add     rax, rdx
0x18000d044  cmp     rax, rcx
0x18000d047  jb      loc_18000D0E4
0x18000d04d  lea     rax, [rcx+rcx]
0x18000d051  cmp     rdx, rax
0x18000d054  cmovb   rbx, rax
0x18000d058  cmp     rcx, rbx
0x18000d05b  jnb     loc_18000D0E4
0x18000d061  call    cs:__imp_GetLastError
0x18000d067  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000d06b  xor     ecx, ecx; dwFlags
0x18000d06d  mov     esi, eax
0x18000d06f  lea     r14, [rbx+40h]
0x18000d073  mov     rdx, r14; dwBytes
0x18000d076  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d07b  mov     rbx, rax
0x18000d07e  test    rax, rax
0x18000d081  jnz     short loc_18000D08F
0x18000d083  mov     ecx, esi; dwErrCode
0x18000d085  call    cs:__imp_SetLastError
0x18000d08b  xor     al, al
0x18000d08d  jmp     short loc_18000D0E6
0x18000d08f  mov     r15, [rdi+8]
0x18000d093  mov     rdx, r14; DestinationSize
0x18000d096  sub     r15, [rdi]
0x18000d099  mov     rcx, rbx; Destination
0x18000d09c  mov     r8, [rdi]; Source
0x18000d09f  mov     r9, r15; SourceSize
0x18000d0a2  call    cs:__imp_memcpy_s
0x18000d0a8  mov     rbp, [rdi+18h]
0x18000d0ac  mov     [rdi+18h], rbx
0x18000d0b0  test    rbp, rbp
0x18000d0b3  jz      short loc_18000D0C9
0x18000d0b5  call    cs:__imp_GetProcessHeap
0x18000d0bb  mov     r8, rbp; lpMem
0x18000d0be  xor     edx, edx; dwFlags
0x18000d0c0  mov     rcx, rax; hHeap
0x18000d0c3  call    cs:__imp_HeapFree
0x18000d0c9  lea     rax, [r15+rbx]
0x18000d0cd  mov     [rdi], rbx
0x18000d0d0  mov     [rdi+8], rax
0x18000d0d4  mov     ecx, esi; dwErrCode
0x18000d0d6  lea     rax, [r14+rbx]
0x18000d0da  mov     [rdi+10h], rax
0x18000d0de  call    cs:__imp_SetLastError
0x18000d0e4  mov     al, 1
0x18000d0e6  add     rsp, 28h
0x18000d0ea  pop     r15
0x18000d0ec  pop     r14
0x18000d0ee  pop     rdi
0x18000d0ef  pop     rsi
0x18000d0f0  pop     rbp
0x18000d0f1  pop     rbx
0x18000d0f2  retn
```
