# CheckExecutableImage(ushort const *,_FINDEXE_CALLBACK *,ulong)

- ea: `0x18000de4c`
- end: `0x18000dfa4`
- name: `?CheckExecutableImage@@YAPEAXPEBGPEAU_FINDEXE_CALLBACK@@K@Z`
- size: `344`
- prototype: `void *__fastcall(const unsigned __int16 *, struct _FINDEXE_CALLBACK *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1801a8ed0`
- `0x1801a93a0`

## callees

- `0x18000de4c`
- `0x18000dfac`
- `0x18000e1a8`
- `0x180021374`
- `0x1801af304`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dec8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000de71`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000df90`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000de71`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000df90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df14`

## pseudocode

```c
__int64 __fastcall CheckExecutableImage(const unsigned __int16 *a1, struct _FINDEXE_CALLBACK *a2, char a3)
{
  struct _PROCESS_ENTRY *v3; // rdi
  __int64 v7; // rax
  DWORD v8; // r8d
  HANDLE FileW; // rax
  __int64 v10; // rsi
  int v11; // eax
  DWORD LastError; // eax
  const unsigned __int16 *v13; // rax

  v3 = 0;
  if ( (dword_1802AF9CC & 0x200) != 0 )
    uMode = SetErrorMode(1u);
  v7 = *((_QWORD *)a2 + 1);
  if ( v7 && *(_DWORD *)v7 == 4888 )
    v3 = *(struct _PROCESS_ENTRY **)(v7 + 8);
  v8 = 3;
  if ( dword_1802AF874 == 2 )
    v8 = 7;
  FileW = CreateFileW(a1, 0x80000000, v8, 0, 3u, 0, 0);
  v10 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( (unsigned int)spew() )
    {
      LastError = GetLastError();
      v13 = errortext(LastError);
      _pwprint(v3, L"%s - %s\n", a1, v13);
    }
  }
  else
  {
    if ( *(_QWORD *)a2 && !FindExeCallback(a2, FileW, a1) )
    {
      v11 = spew();
      if ( (a3 & 0x40) == 0 )
      {
        if ( v11 )
          _pwprint(v3, L"%s - mismatched timestamp\n", a1);
        CloseHandle((HANDLE)v10);
        v10 = -1;
        goto LABEL_21;
      }
      if ( v11 )
        _pwprint(v3, L"%s - mismatched timestamp OK\n", a1);
    }
    if ( (unsigned int)spew() )
      _pwprint(v3, L"%s - OK\n", a1);
  }
LABEL_21:
  if ( (dword_1802AF9CC & 0x200) != 0 )
    SetErrorMode(uMode);
  return v10;
}

```

## disassembly

```asm
0x18000de4c  push    rbx
0x18000de4e  push    rbp
0x18000de4f  push    rsi
0x18000de50  push    rdi
0x18000de51  push    r14
0x18000de53  sub     rsp, 40h
0x18000de57  xor     edi, edi
0x18000de59  mov     r14d, r8d
0x18000de5c  test    cs:dword_1802AF9CC, 200h
0x18000de66  mov     rbp, rdx
0x18000de69  mov     rbx, rcx
0x18000de6c  jz      short loc_18000DE7D
0x18000de6e  lea     ecx, [rdi+1]; uMode
0x18000de71  call    cs:__imp_SetErrorMode
0x18000de77  mov     cs:uMode, eax
0x18000de7d  mov     rax, [rbp+8]
0x18000de81  test    rax, rax
0x18000de84  jz      short loc_18000DE92
0x18000de86  cmp     dword ptr [rax], 1318h
0x18000de8c  jnz     short loc_18000DE92
0x18000de8e  mov     rdi, [rax+8]
0x18000de92  cmp     cs:dword_1802AF874, 2
0x18000de99  mov     ecx, 3
0x18000de9e  mov     r8d, ecx
0x18000dea1  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000deaa  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000deb2  mov     edx, 80000000h; dwDesiredAccess
0x18000deb7  mov     [rsp+68h+dwCreationDisposition], ecx; dwCreationDisposition
0x18000debb  lea     eax, [rcx+4]
0x18000debe  mov     rcx, rbx; lpFileName
0x18000dec1  cmovz   r8d, eax; dwShareMode
0x18000dec5  xor     r9d, r9d; lpSecurityAttributes
0x18000dec8  call    cs:__imp_CreateFileW
0x18000dece  mov     rsi, rax
0x18000ded1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ded5  jz      short loc_18000DF53
0x18000ded7  cmp     qword ptr [rbp+0], 0
0x18000dedc  jz      short loc_18000DF36
0x18000dede  mov     r8, rbx; unsigned __int16 *
0x18000dee1  mov     rdx, rax; void *
0x18000dee4  mov     rcx, rbp; struct _FINDEXE_CALLBACK *
0x18000dee7  call    ?FindExeCallback@@YAHPEAU_FINDEXE_CALLBACK@@PEAXPEBG@Z; FindExeCallback(_FINDEXE_CALLBACK *,void *,ushort const *)
0x18000deec  test    eax, eax
0x18000deee  jnz     short loc_18000DF36
0x18000def0  call    ?spew@@YAHXZ; spew(void)
0x18000def5  test    r14b, 40h
0x18000def9  jnz     short loc_18000DF20
0x18000defb  test    eax, eax
0x18000defd  jz      short loc_18000DF11
0x18000deff  mov     r8, rbx
0x18000df02  lea     rdx, aSMismatchedTim_0; "%s - mismatched timestamp\n"
0x18000df09  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18000df0c  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000df11  mov     rcx, rsi; hObject
0x18000df14  call    cs:__imp_CloseHandle
0x18000df1a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000df1e  jmp     short loc_18000DF7E
0x18000df20  test    eax, eax
0x18000df22  jz      short loc_18000DF36
0x18000df24  mov     r8, rbx
0x18000df27  lea     rdx, aSMismatchedTim; "%s - mismatched timestamp OK\n"
0x18000df2e  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18000df31  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000df36  call    ?spew@@YAHXZ; spew(void)
0x18000df3b  test    eax, eax
0x18000df3d  jz      short loc_18000DF7E
0x18000df3f  mov     r8, rbx
0x18000df42  lea     rdx, aSOk_0; "%s - OK\n"
0x18000df49  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18000df4c  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000df51  jmp     short loc_18000DF7E
0x18000df53  call    ?spew@@YAHXZ; spew(void)
0x18000df58  test    eax, eax
0x18000df5a  jz      short loc_18000DF7E
0x18000df5c  call    cs:__imp_GetLastError
0x18000df62  mov     ecx, eax; unsigned int
0x18000df64  call    ?errortext@@YAPEBGK@Z; errortext(ulong)
0x18000df69  mov     r9, rax
0x18000df6c  lea     rdx, aSS_1; "%s - %s\n"
0x18000df73  mov     r8, rbx
0x18000df76  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x18000df79  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000df7e  test    cs:dword_1802AF9CC, 200h
0x18000df88  jz      short loc_18000DF96
0x18000df8a  mov     ecx, cs:uMode; uMode
0x18000df90  call    cs:__imp_SetErrorMode
0x18000df96  mov     rax, rsi
0x18000df99  add     rsp, 40h
0x18000df9d  pop     r14
0x18000df9f  pop     rdi
0x18000dfa0  pop     rsi
0x18000dfa1  pop     rbp
0x18000dfa2  pop     rbx
0x18000dfa3  retn
```
