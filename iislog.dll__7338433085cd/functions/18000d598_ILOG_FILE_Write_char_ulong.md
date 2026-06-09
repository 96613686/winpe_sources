# ILOG_FILE::Write(char *,ulong)

- ea: `0x18000d598`
- end: `0x18000d699`
- name: `?Write@ILOG_FILE@@QEAAHPEADK@Z`
- size: `257`
- prototype: `__int64 __fastcall(ILOG_FILE *__hidden this, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003374`
- `0x180006730`
- `0x180007250`

## callees

- `0x18000d0e0`
- `0x18000d13c`
- `0x18000d1e8`
- `0x18000d598`
- `0x18000ec56`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000d5c5`
- `KERNEL32!SetLastError` at `0x18000d62b`
- `KERNEL32!SetLastError` at `0x18000d635`
- `KERNEL32!SetLastError` at `0x18000d667`
- `KERNEL32!SetLastError` at `0x18000d5c5`
- `KERNEL32!SetLastError` at `0x18000d62b`
- `KERNEL32!SetLastError` at `0x18000d635`
- `KERNEL32!SetLastError` at `0x18000d667`
- `KERNEL32!GetLastError` at `0x18000d623`
- `KERNEL32!GetLastError` at `0x18000d623`

## pseudocode

```c
__int64 __fastcall ILOG_FILE::Write(ILOG_FILE *this, char *Src, size_t Size)
{
  unsigned int v3; // esi
  char *v4; // r14
  __int64 v6; // rcx
  unsigned __int64 v7; // rbx
  __int64 v8; // rbx
  DWORD LastError; // eax
  __int64 v11; // [rsp+58h] [rbp+20h]

  v3 = Size;
  v4 = Src;
  if ( *((_QWORD *)this + 1) )
  {
    v6 = *((_QWORD *)this + 5);
    v11 = v6;
    v7 = *((_QWORD *)this + 7);
    if ( v6 + (unsigned __int64)(unsigned int)Size <= v7 )
      goto LABEL_6;
    v8 = v7 - v6;
    memcpy_0((void *)(*((_QWORD *)this + 3) + *((unsigned int *)this + 8)), Src, (unsigned int)v8);
    v3 -= v8;
    v4 += (unsigned int)v8;
    *((_DWORD *)this + 8) += v8;
    *((_QWORD *)this + 5) += v8;
    *((_QWORD *)this + 7) += *((unsigned int *)this + 5);
    ILOG_FILE::DestroyMapping(this);
    if ( (unsigned int)ILOG_FILE::CreateMapping(this) )
    {
LABEL_6:
      memcpy_0((void *)(*((_QWORD *)this + 3) + *((unsigned int *)this + 8)), v4, v3);
      *((_DWORD *)this + 8) += v3;
      *((_QWORD *)this + 5) += v3;
      return 1;
    }
    LastError = GetLastError();
    SetLastError(LastError);
    *((_QWORD *)this + 5) = v11;
    ILOG_FILE::CloseFile(this);
  }
  else
  {
    SetLastError(0x57u);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d598  mov     [rsp+arg_8], rbx
0x18000d59d  mov     [rsp+arg_10], rsi
0x18000d5a2  mov     [rsp+arg_0], rcx
0x18000d5a7  push    rdi
0x18000d5a8  push    r14
0x18000d5aa  push    r15
0x18000d5ac  sub     rsp, 20h
0x18000d5b0  mov     esi, r8d
0x18000d5b3  mov     r14, rdx
0x18000d5b6  mov     rdi, rcx
0x18000d5b9  cmp     qword ptr [rcx+8], 0
0x18000d5be  jnz     short loc_18000D5D0
0x18000d5c0  mov     ecx, 57h ; 'W'; dwErrCode
0x18000d5c5  call    cs:__imp_SetLastError
0x18000d5cb  jmp     loc_18000D683
0x18000d5d0  mov     rcx, [rcx+28h]
0x18000d5d4  mov     [rsp+38h+arg_18], rcx
0x18000d5d9  mov     rbx, [rdi+38h]
0x18000d5dd  lea     rax, [rcx+rsi]
0x18000d5e1  cmp     rax, rbx
0x18000d5e4  jbe     short loc_18000D642
0x18000d5e6  sub     rbx, rcx
0x18000d5e9  mov     r15d, ebx
0x18000d5ec  mov     ecx, [rdi+20h]
0x18000d5ef  add     rcx, [rdi+18h]; void *
0x18000d5f3  mov     r8d, ebx; Size
0x18000d5f6  call    memcpy_0
0x18000d5fb  nop
0x18000d5fc  sub     esi, ebx
0x18000d5fe  add     r14, r15
0x18000d601  add     [rdi+20h], ebx
0x18000d604  add     [rdi+28h], rbx
0x18000d608  mov     eax, [rdi+14h]
0x18000d60b  add     [rdi+38h], rax
0x18000d60f  mov     rcx, rdi; this
0x18000d612  call    ?DestroyMapping@ILOG_FILE@@AEAAXXZ; ILOG_FILE::DestroyMapping(void)
0x18000d617  mov     rcx, rdi; this
0x18000d61a  call    ?CreateMapping@ILOG_FILE@@AEAAHXZ; ILOG_FILE::CreateMapping(void)
0x18000d61f  test    eax, eax
0x18000d621  jnz     short loc_18000D642
0x18000d623  call    cs:__imp_GetLastError
0x18000d629  mov     ecx, eax; dwErrCode
0x18000d62b  call    cs:__imp_SetLastError
0x18000d631  jmp     short loc_18000D672
0x18000d633  mov     ecx, eax; dwErrCode
0x18000d635  call    cs:__imp_SetLastError
0x18000d63b  mov     rdi, [rsp+38h+arg_0]
0x18000d640  jmp     short loc_18000D672
0x18000d642  mov     ebx, esi
0x18000d644  mov     ecx, [rdi+20h]
0x18000d647  add     rcx, [rdi+18h]; void *
0x18000d64b  mov     r8d, esi; Size
0x18000d64e  mov     rdx, r14; Src
0x18000d651  call    memcpy_0
0x18000d656  nop
0x18000d657  add     [rdi+20h], esi
0x18000d65a  add     [rdi+28h], rbx
0x18000d65e  mov     eax, 1
0x18000d663  jmp     short loc_18000D685
0x18000d665  mov     ecx, eax; dwErrCode
0x18000d667  call    cs:__imp_SetLastError
0x18000d66d  mov     rdi, [rsp+38h+arg_0]
0x18000d672  mov     rax, [rsp+38h+arg_18]
0x18000d677  mov     [rdi+28h], rax
0x18000d67b  mov     rcx, rdi; this
0x18000d67e  call    ?CloseFile@ILOG_FILE@@QEAAHXZ; ILOG_FILE::CloseFile(void)
0x18000d683  xor     eax, eax
0x18000d685  mov     rbx, [rsp+38h+arg_8]
0x18000d68a  mov     rsi, [rsp+38h+arg_10]
0x18000d68f  add     rsp, 20h
0x18000d693  pop     r15
0x18000d695  pop     r14
0x18000d697  pop     rdi
0x18000d698  retn
0x18000f066  push    rbp
0x18000f068  sub     rsp, 20h
0x18000f06c  mov     rbp, rdx
0x18000f06f  mov     rax, [rcx]
0x18000f072  cmp     dword ptr [rax], 0C0000006h
0x18000f078  jz      short loc_18000F086
0x18000f07a  cmp     dword ptr [rax], 0C000007Fh
0x18000f080  jz      short loc_18000F086
0x18000f082  xor     eax, eax
0x18000f084  jmp     short loc_18000F08B
0x18000f086  mov     eax, 1
0x18000f08b  add     rsp, 20h
0x18000f08f  pop     rbp
0x18000f090  retn
0x18000f092  push    rbp
0x18000f094  sub     rsp, 20h
0x18000f098  mov     rbp, rdx
0x18000f09b  mov     rax, [rcx]
0x18000f09e  cmp     dword ptr [rax], 0C0000006h
0x18000f0a4  jz      short loc_18000F0B2
0x18000f0a6  cmp     dword ptr [rax], 0C000007Fh
0x18000f0ac  jz      short loc_18000F0B2
0x18000f0ae  xor     eax, eax
0x18000f0b0  jmp     short loc_18000F0B7
0x18000f0b2  mov     eax, 1
0x18000f0b7  add     rsp, 20h
0x18000f0bb  pop     rbp
0x18000f0bc  retn
```
