# OpenDbg(_PROCESS_ENTRY *,ushort const *,ushort *,ulong,_FINDDBG_CALLBACK *)

- ea: `0x18000e378`
- end: `0x18000e4b5`
- name: `?OpenDbg@@YAPEAXPEAU_PROCESS_ENTRY@@PEBGPEAGKPEAU_FINDDBG_CALLBACK@@@Z`
- size: `317`
- prototype: `void *__usercall@<rax>(struct _PROCESS_ENTRY *@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, struct _FINDDBG_CALLBACK *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800120f0`
- `0x1800130f4`

## callees

- `0x18000dfac`
- `0x18000e378`
- `0x180012e6c`
- `0x180021374`
- `0x1801a8de0`
- `0x1801af304`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e3d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e460`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e460`

## pseudocode

```c
__int64 __fastcall OpenDbg(
        struct _PROCESS_ENTRY *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        struct _FINDDBG_CALLBACK *a5)
{
  DWORD v7; // r8d
  HANDLE FileW; // rax
  void *v10; // rdi
  DWORD LastError; // eax
  const unsigned __int16 *v12; // rax

  v7 = dword_1802B29B4;
  if ( dword_1802B29B4 == -1 )
  {
    v7 = 3;
    if ( dword_1802AF874 == 2 )
      v7 = 7;
    dword_1802B29B4 = v7;
  }
  if ( !*a2 )
    return -1;
  FileW = CreateFileW(a2, 0x80000000, v7, 0, 3u, 0, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( (unsigned int)spew() )
    {
      LastError = GetLastError();
      v12 = errortext(LastError);
      _pwprint(a1, L"%s - %s\n", a2, v12);
    }
    return -1;
  }
  if ( a5 && *(_QWORD *)a5 && !FindDbgCallback(FileW, a2, a5) )
  {
    if ( (unsigned int)spew() )
      _pwprint(a1, L"%s - mismatched timestamp\n", a2);
    CloseHandle(v10);
    if ( !*a3 )
      wcscpy_s_ex(a3, 0x105u, a2);
    return -1;
  }
  wcscpy_s_ex(a3, 0x105u, a2);
  if ( !a1 && (unsigned int)spew() )
    _pwprint(0, L"%s - OK", a2);
  return (__int64)v10;
}

```

## disassembly

```asm
0x18000e378  push    rbx
0x18000e37a  push    rbp
0x18000e37b  push    rsi
0x18000e37c  push    rdi
0x18000e37d  push    r14
0x18000e37f  sub     rsp, 40h
0x18000e383  mov     rsi, r8
0x18000e386  mov     rbp, rcx
0x18000e389  mov     r8d, cs:dword_1802B29B4
0x18000e390  mov     rbx, rdx
0x18000e393  mov     ecx, 3
0x18000e398  cmp     r8d, 0FFFFFFFFh
0x18000e39c  jnz     short loc_18000E3B6
0x18000e39e  cmp     cs:dword_1802AF874, 2
0x18000e3a5  lea     eax, [rcx+4]
0x18000e3a8  mov     r8d, ecx
0x18000e3ab  cmovz   r8d, eax; dwShareMode
0x18000e3af  mov     cs:dword_1802B29B4, r8d
0x18000e3b6  xor     r14d, r14d
0x18000e3b9  cmp     [rdx], r14w
0x18000e3bd  jz      short loc_18000E412
0x18000e3bf  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x18000e3c4  xor     r9d, r9d; lpSecurityAttributes
0x18000e3c7  mov     [rsp+68h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18000e3cc  mov     edx, 80000000h; dwDesiredAccess
0x18000e3d1  mov     [rsp+68h+dwCreationDisposition], ecx; dwCreationDisposition
0x18000e3d5  mov     rcx, rbx; lpFileName
0x18000e3d8  call    cs:__imp_CreateFileW
0x18000e3de  mov     rdi, rax
0x18000e3e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e3e5  jnz     short loc_18000E421
0x18000e3e7  call    ?spew@@YAHXZ; spew(void)
0x18000e3ec  test    eax, eax
0x18000e3ee  jz      short loc_18000E412
0x18000e3f0  call    cs:__imp_GetLastError
0x18000e3f6  mov     ecx, eax; unsigned int
0x18000e3f8  call    ?errortext@@YAPEBGK@Z; errortext(ulong)
0x18000e3fd  mov     r9, rax
0x18000e400  lea     rdx, aSS_1; "%s - %s\n"
0x18000e407  mov     r8, rbx
0x18000e40a  mov     rcx, rbp; struct _PROCESS_ENTRY *
0x18000e40d  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000e412  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e416  add     rsp, 40h
0x18000e41a  pop     r14
0x18000e41c  pop     rdi
0x18000e41d  pop     rsi
0x18000e41e  pop     rbp
0x18000e41f  pop     rbx
0x18000e420  retn
0x18000e421  mov     r8, [rsp+68h+arg_20]; struct _FINDDBG_CALLBACK *
0x18000e429  test    r8, r8
0x18000e42c  jz      short loc_18000E47E
0x18000e42e  cmp     [r8], r14
0x18000e431  jz      short loc_18000E47E
0x18000e433  mov     rdx, rbx; unsigned __int16 *
0x18000e436  mov     rcx, rdi; void *
0x18000e439  call    ?FindDbgCallback@@YAHPEAXPEBGPEAU_FINDDBG_CALLBACK@@@Z; FindDbgCallback(void *,ushort const *,_FINDDBG_CALLBACK *)
0x18000e43e  test    eax, eax
0x18000e440  jnz     short loc_18000E47E
0x18000e442  call    ?spew@@YAHXZ; spew(void)
0x18000e447  test    eax, eax
0x18000e449  jz      short loc_18000E45D
0x18000e44b  mov     r8, rbx
0x18000e44e  lea     rdx, aSMismatchedTim_0; "%s - mismatched timestamp\n"
0x18000e455  mov     rcx, rbp; struct _PROCESS_ENTRY *
0x18000e458  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000e45d  mov     rcx, rdi; hObject
0x18000e460  call    cs:__imp_CloseHandle
0x18000e466  cmp     [rsi], r14w
0x18000e46a  jnz     short loc_18000E412
0x18000e46c  mov     r8, rbx; unsigned __int16 *
0x18000e46f  mov     edx, 105h; unsigned __int64
0x18000e474  mov     rcx, rsi; unsigned __int16 *
0x18000e477  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000e47c  jmp     short loc_18000E412
0x18000e47e  mov     r8, rbx; unsigned __int16 *
0x18000e481  mov     edx, 105h; unsigned __int64
0x18000e486  mov     rcx, rsi; unsigned __int16 *
0x18000e489  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x18000e48e  test    rbp, rbp
0x18000e491  jnz     short loc_18000E4AD
0x18000e493  call    ?spew@@YAHXZ; spew(void)
0x18000e498  test    eax, eax
0x18000e49a  jz      short loc_18000E4AD
0x18000e49c  mov     r8, rbx
0x18000e49f  lea     rdx, aSOk; "%s - OK"
0x18000e4a6  xor     ecx, ecx; struct _PROCESS_ENTRY *
0x18000e4a8  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000e4ad  mov     rax, rdi
0x18000e4b0  jmp     loc_18000E416
```
