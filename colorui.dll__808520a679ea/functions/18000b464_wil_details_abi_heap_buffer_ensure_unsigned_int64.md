# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000b464`
- end: `0x18000b537`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007818`
- `0x180008014`
- `0x18000a080`
- `0x18000a250`
- `0x180015790`

## callees

- `0x1800075e4`
- `0x18000b464`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b4e6`
- `msvcrt!memcpy_s` at `0x18000b4e6`
- `KERNEL32!GetLastError` at `0x18000b4a5`
- `KERNEL32!GetLastError` at `0x18000b4a5`
- `KERNEL32!GetProcessHeap` at `0x18000b4f9`
- `KERNEL32!GetProcessHeap` at `0x18000b4f9`
- `KERNEL32!HeapFree` at `0x18000b507`
- `KERNEL32!HeapFree` at `0x18000b507`
- `KERNEL32!SetLastError` at `0x18000b4c9`
- `KERNEL32!SetLastError` at `0x18000b522`
- `KERNEL32!SetLastError` at `0x18000b4c9`
- `KERNEL32!SetLastError` at `0x18000b522`

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
0x18000b464  push    rbx
0x18000b466  push    rbp
0x18000b467  push    rsi
0x18000b468  push    rdi
0x18000b469  push    r14
0x18000b46b  push    r15
0x18000b46d  sub     rsp, 28h
0x18000b471  mov     rdi, rcx
0x18000b474  mov     rbx, rdx
0x18000b477  mov     rcx, [rcx+10h]
0x18000b47b  mov     rax, [rdi+8]
0x18000b47f  sub     rax, [rdi]
0x18000b482  sub     rcx, [rdi]
0x18000b485  add     rax, rdx
0x18000b488  cmp     rax, rcx
0x18000b48b  jb      loc_18000B528
0x18000b491  lea     rax, [rcx+rcx]
0x18000b495  cmp     rdx, rax
0x18000b498  cmovb   rbx, rax
0x18000b49c  cmp     rcx, rbx
0x18000b49f  jnb     loc_18000B528
0x18000b4a5  call    cs:__imp_GetLastError
0x18000b4ab  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000b4af  xor     ecx, ecx; dwFlags
0x18000b4b1  mov     esi, eax
0x18000b4b3  lea     r14, [rbx+40h]
0x18000b4b7  mov     rdx, r14; dwBytes
0x18000b4ba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b4bf  mov     rbx, rax
0x18000b4c2  test    rax, rax
0x18000b4c5  jnz     short loc_18000B4D3
0x18000b4c7  mov     ecx, esi; dwErrCode
0x18000b4c9  call    cs:__imp_SetLastError
0x18000b4cf  xor     al, al
0x18000b4d1  jmp     short loc_18000B52A
0x18000b4d3  mov     r15, [rdi+8]
0x18000b4d7  mov     rdx, r14; DestinationSize
0x18000b4da  sub     r15, [rdi]
0x18000b4dd  mov     rcx, rbx; Destination
0x18000b4e0  mov     r8, [rdi]; Source
0x18000b4e3  mov     r9, r15; SourceSize
0x18000b4e6  call    cs:__imp_memcpy_s
0x18000b4ec  mov     rbp, [rdi+18h]
0x18000b4f0  mov     [rdi+18h], rbx
0x18000b4f4  test    rbp, rbp
0x18000b4f7  jz      short loc_18000B50D
0x18000b4f9  call    cs:__imp_GetProcessHeap
0x18000b4ff  mov     r8, rbp; lpMem
0x18000b502  xor     edx, edx; dwFlags
0x18000b504  mov     rcx, rax; hHeap
0x18000b507  call    cs:__imp_HeapFree
0x18000b50d  lea     rax, [r15+rbx]
0x18000b511  mov     [rdi], rbx
0x18000b514  mov     [rdi+8], rax
0x18000b518  mov     ecx, esi; dwErrCode
0x18000b51a  lea     rax, [r14+rbx]
0x18000b51e  mov     [rdi+10h], rax
0x18000b522  call    cs:__imp_SetLastError
0x18000b528  mov     al, 1
0x18000b52a  add     rsp, 28h
0x18000b52e  pop     r15
0x18000b530  pop     r14
0x18000b532  pop     rdi
0x18000b533  pop     rsi
0x18000b534  pop     rbp
0x18000b535  pop     rbx
0x18000b536  retn
```
