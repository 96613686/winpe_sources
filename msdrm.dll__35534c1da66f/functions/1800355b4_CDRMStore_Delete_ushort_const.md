# CDRMStore::Delete(ushort const *)

- ea: `0x1800355b4`
- end: `0x1800356f0`
- name: `?Delete@CDRMStore@@QEAAJPEBG@Z`
- size: `316`
- prototype: `int(CDRMStore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001dd08`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x180017210`
- `0x180034bb0`
- `0x1800355b4`
- `0x1800370d8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003569f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003569f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180035684`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800356ac`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180035684`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800356ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003568e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003568e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDRMStore::Delete(CDRMStore *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned __int64 v7; // rbp
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  signed int v10; // ebx
  signed int LastError; // eax
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 1) )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = *((_QWORD *)this + 2);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    v7 = v6 + v4 + 1;
    v8 = (unsigned __int16 *)operator new(saturated_mul(v7, 2u));
    v9 = v8;
    if ( v8 )
    {
      v10 = StringCchCopyW(v8, v7, *((const unsigned __int16 **)this + 2));
      if ( v10 >= 0 )
      {
        v10 = StringCchCatW(v9, v7, a2);
        if ( v10 >= 0 )
        {
          v13 = 0;
          if ( CDRMCLock::Lock((CDRMCLock *)&v13, v9) >= 0
            && !DeleteFileW(v9)
            && GetLastError() == 5
            && (!SetFileAttributesW(v9, 0x80u) || !DeleteFileW(v9)) )
          {
            LastError = GetLastError();
            v10 = LastError;
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
          }
          CDRMCLock::~CDRMCLock((CDRMCLock *)&v13);
        }
      }
    }
    else
    {
      v10 = -2147024882;
    }
  }
  else
  {
    v10 = 0;
    v9 = 0;
  }
  operator delete(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800355b4  push    rsi
0x1800355b6  push    rdi
0x1800355b7  push    r14
0x1800355b9  sub     rsp, 30h
0x1800355bd  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800355c6  mov     [rsp+48h+arg_8], rbx
0x1800355cb  mov     [rsp+48h+arg_10], rbp
0x1800355d0  mov     rsi, rdx
0x1800355d3  mov     rbx, rcx
0x1800355d6  xor     r14d, r14d
0x1800355d9  cmp     [rcx+4], r14d
0x1800355dd  jz      loc_1800356CD
0x1800355e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800355e7  mov     rax, r8
0x1800355ea  inc     rax
0x1800355ed  cmp     [rdx+rax*2], r14w
0x1800355f2  jnz     short loc_1800355EA
0x1800355f4  mov     rdx, [rcx+10h]
0x1800355f8  mov     rcx, r8
0x1800355fb  inc     rcx
0x1800355fe  cmp     [rdx+rcx*2], r14w
0x180035603  jnz     short loc_1800355FB
0x180035605  lea     rbp, [rax+1]
0x180035609  add     rbp, rcx
0x18003560c  mov     eax, 2
0x180035611  mul     rbp
0x180035614  cmovb   rax, r8
0x180035618  mov     rcx, rax; Size
0x18003561b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035620  mov     rdi, rax
0x180035623  test    rax, rax
0x180035626  jnz     short loc_180035632
0x180035628  mov     ebx, 8007000Eh
0x18003562d  jmp     loc_1800356D3
0x180035632  mov     r8, [rbx+10h]; unsigned __int16 *
0x180035636  mov     rdx, rbp; unsigned __int64
0x180035639  mov     rcx, rdi; unsigned __int16 *
0x18003563c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035641  mov     ebx, eax
0x180035643  test    eax, eax
0x180035645  js      loc_1800356D3
0x18003564b  mov     r8, rsi; unsigned __int16 *
0x18003564e  mov     rdx, rbp; unsigned __int64
0x180035651  mov     rcx, rdi; unsigned __int16 *
0x180035654  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035659  mov     ebx, eax
0x18003565b  test    eax, eax
0x18003565d  js      short loc_1800356D3
0x18003565f  mov     [rsp+48h+arg_0], r14
0x180035664  mov     rdx, rdi; unsigned __int16 *
0x180035667  lea     rcx, [rsp+48h+arg_0]; this
0x18003566c  call    ?Lock@CDRMCLock@@QEAAJPEAG@Z; CDRMCLock::Lock(ushort *)
0x180035671  test    eax, eax
0x180035673  jns     short loc_180035681
0x180035675  lea     rcx, [rsp+48h+arg_0]; this
0x18003567a  call    ??1CDRMCLock@@QEAA@XZ; CDRMCLock::~CDRMCLock(void)
0x18003567f  jmp     short loc_1800356D3
0x180035681  mov     rcx, rdi; lpFileName
0x180035684  call    cs:__imp_DeleteFileW
0x18003568a  test    eax, eax
0x18003568c  jnz     short loc_180035675
0x18003568e  call    cs:__imp_GetLastError
0x180035694  cmp     eax, 5
0x180035697  jnz     short loc_180035675
0x180035699  lea     edx, [rax+7Bh]; dwFileAttributes
0x18003569c  mov     rcx, rdi; lpFileName
0x18003569f  call    cs:__imp_SetFileAttributesW
0x1800356a5  test    eax, eax
0x1800356a7  jz      short loc_1800356B6
0x1800356a9  mov     rcx, rdi; lpFileName
0x1800356ac  call    cs:__imp_DeleteFileW
0x1800356b2  test    eax, eax
0x1800356b4  jnz     short loc_180035675
0x1800356b6  call    cs:__imp_GetLastError
0x1800356bc  mov     ebx, eax
0x1800356be  test    eax, eax
0x1800356c0  jle     short loc_180035675
0x1800356c2  movzx   ebx, ax
0x1800356c5  or      ebx, 80070000h
0x1800356cb  jmp     short loc_180035675
0x1800356cd  mov     ebx, r14d
0x1800356d0  mov     rdi, r14
0x1800356d3  mov     rcx, rdi; Block
0x1800356d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800356db  mov     eax, ebx
0x1800356dd  mov     rbx, [rsp+48h+arg_8]
0x1800356e2  mov     rbp, [rsp+48h+arg_10]
0x1800356e7  add     rsp, 30h
0x1800356eb  pop     r14
0x1800356ed  pop     rdi
0x1800356ee  pop     rsi
0x1800356ef  retn
```
