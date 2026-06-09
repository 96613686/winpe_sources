# WriteStringToStorage(ushort const *,ushort const *,ulong)

- ea: `0x18006b8a8`
- end: `0x18006bad2`
- name: `?WriteStringToStorage@@YAJPEBG0K@Z`
- size: `554`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18006bae0`
- `0x18006c2c0`

## callees

- `0x180011bcc`
- `0x180029414`
- `0x180029560`
- `0x18002ec0c`
- `0x180069ca4`
- `0x18006b8a8`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18006b913`
- `MSDART!MpHeapAlloc` at `0x18006b913`
- `KERNEL32!SetEndOfFile` at `0x18006ba3a`
- `KERNEL32!SetEndOfFile` at `0x18006ba3a`
- `KERNEL32!WriteFile` at `0x18006ba12`
- `KERNEL32!WriteFile` at `0x18006ba12`
- `KERNEL32!GetFileType` at `0x18006b9c7`
- `KERNEL32!GetFileType` at `0x18006b9c7`
- `KERNEL32!CreateFileW` at `0x18006b996`
- `KERNEL32!CreateFileW` at `0x18006b996`
- `KERNEL32!GetLastError` at `0x18006b9a9`
- `KERNEL32!GetLastError` at `0x18006ba1c`
- `KERNEL32!GetLastError` at `0x18006b9a9`
- `KERNEL32!GetLastError` at `0x18006ba1c`
- `KERNEL32!SetLastError` at `0x18006b96a`
- `KERNEL32!SetLastError` at `0x18006b96a`
- `KERNEL32!CloseHandle` at `0x18006b9d5`
- `KERNEL32!CloseHandle` at `0x18006ba71`
- `KERNEL32!CloseHandle` at `0x18006b9d5`
- `KERNEL32!CloseHandle` at `0x18006ba71`

## string_xrefs

- `0x18006ba9d`: `<WriteStringToStorage|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteStringToStorage(LPCWSTR lpFileName, const unsigned __int16 *a2, DWORD a3)
{
  const WCHAR *v4; // r12
  __int64 v5; // rax
  int v6; // r13d
  unsigned __int64 v7; // r15
  __int64 v8; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  int v11; // r15d
  HANDLE FileW; // rax
  void *v13; // rsi
  ulong pExceptionObject; // [rsp+40h] [rbp-58h] BYREF
  ulong LastError; // [rsp+44h] [rbp-54h] BYREF
  int v17; // [rsp+48h] [rbp-50h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-4Ch] BYREF
  ulong v19; // [rsp+50h] [rbp-48h] BYREF
  ulong v20; // [rsp+54h] [rbp-44h] BYREF
  __int64 v21; // [rsp+58h] [rbp-40h]
  int v24; // [rsp+B8h] [rbp+20h]

  v4 = lpFileName;
  if ( !lpFileName )
    return 2147942487LL;
  v21 = -1;
  if ( !a2 )
    return 2147942487LL;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 66;
  v7 = (unsigned int)(v5 + 67);
  v8 = 2 * v7;
  if ( !is_mul_ok(v7, 2u) )
    v8 = -1;
  v9 = (unsigned __int16 *)MpHeapAlloc(g_hHeapHandle, 19922944, v8);
  try
  {
    v10 = v9;
    if ( !v9 )
    {
      pExceptionObject = 14;
      throw &pExceptionObject;
    }
    v11 = StringCchPrintfW(v9, v7, L"%ls%ls\r\n", &wszMDLVersion1Header, a2);
    *v10 = -257;
    SetLastError(0);
    FileW = CreateFileW(v4, 0x40000000u, 0, 0, a3, 0x80u, 0);
    v13 = FileW;
    v21 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      throw &LastError;
    }
    if ( GetFileType(FileW) != 1 )
    {
      CloseHandle(v13);
      v21 = -1;
      v17 = 5;
      throw (long *)&v17;
    }
    NumberOfBytesWritten = 0;
    if ( !WriteFile(v13, v10, 2 * v6, &NumberOfBytesWritten, 0) )
    {
      v19 = GetLastError();
      throw &v19;
    }
    SetEndOfFile(v13);
    operator delete(v10);
  }
  catch ( ulong v20 )
  {
    v24 = MapERRtoHRESULT(v20);
LABEL_17:
    v13 = (void *)v21;
    v4 = lpFileName;
    v11 = v24;
    if ( v21 == -1 )
      goto LABEL_19;
  }
  catch ( ... )
  {
    v24 = -2147418113;
    if ( (bidGblFlags & 2) != 0 && off_1800C8AA0[0] )
      bidTraceA(off_1800C8468[0], 1720320, off_1800C8AA0[0], 0);
    goto LABEL_17;
  }
  CloseHandle(v13);
LABEL_19:
  if ( v11 >= 0 && *((_BYTE *)_UdlCacheMap + 60) )
    TCMHashTableLocked<unsigned short const *,CUdlCacheValue *>::DeleteRecord(_UdlCacheMap, v4);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8468[0], 1729545, L"<WriteStringToStorage|Trace|HR> ", (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18006b8a8  mov     [rsp+arg_10], r8d
0x18006b8ad  mov     [rsp+arg_0], rcx
0x18006b8b2  push    rbx
0x18006b8b3  push    rsi
0x18006b8b4  push    rdi
0x18006b8b5  push    r12
0x18006b8b7  push    r13
0x18006b8b9  push    r14
0x18006b8bb  push    r15
0x18006b8bd  sub     rsp, 60h
0x18006b8c1  mov     rsi, rdx
0x18006b8c4  mov     r12, rcx
0x18006b8c7  xor     edi, edi
0x18006b8c9  test    rcx, rcx
0x18006b8cc  jz      loc_18006BABD
0x18006b8d2  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006b8d6  mov     [rsp+98h+var_40], r14
0x18006b8db  test    rdx, rdx
0x18006b8de  jz      loc_18006BABD
0x18006b8e4  mov     rax, r14
0x18006b8e7  inc     rax
0x18006b8ea  cmp     [rdx+rax*2], di
0x18006b8ee  jnz     short loc_18006B8E7
0x18006b8f0  lea     r13d, [rax+42h]
0x18006b8f4  lea     r15d, [r13+1]
0x18006b8f8  mov     eax, 2
0x18006b8fd  mul     r15
0x18006b900  cmovb   rax, r14
0x18006b904  mov     r8, rax
0x18006b907  mov     edx, 1300000h
0x18006b90c  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18006b913  call    cs:__imp_MpHeapAlloc
0x18006b919  mov     rbx, rax
0x18006b91c  mov     [rsp+98h+arg_18], rax
0x18006b924  test    rax, rax
0x18006b927  jnz     short loc_18006B942
0x18006b929  mov     [rsp+98h+pExceptionObject], 0Eh
0x18006b931  lea     rdx, _TI1K; pThrowInfo
0x18006b938  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18006b93d  call    _CxxThrowException_0
0x18006b942  mov     qword ptr [rsp+98h+dwCreationDisposition], rsi
0x18006b947  lea     r9, ?wszMDLVersion1Header@@3PAGA; ushort near * wszMDLVersion1Header
0x18006b94e  lea     r8, aLsLs; "%ls%ls\r\n"
0x18006b955  mov     rdx, r15; unsigned __int64
0x18006b958  mov     rcx, rbx; unsigned __int16 *
0x18006b95b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006b960  mov     r15d, eax
0x18006b963  mov     word ptr [rbx], 0FEFFh
0x18006b968  xor     ecx, ecx; dwErrCode
0x18006b96a  call    cs:__imp_SetLastError
0x18006b970  mov     [rsp+98h+hTemplateFile], rdi; hTemplateFile
0x18006b975  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006b97d  mov     eax, [rsp+98h+arg_10]
0x18006b984  mov     [rsp+98h+dwCreationDisposition], eax; dwCreationDisposition
0x18006b988  xor     r9d, r9d; lpSecurityAttributes
0x18006b98b  xor     r8d, r8d; dwShareMode
0x18006b98e  mov     edx, 40000000h; dwDesiredAccess
0x18006b993  mov     rcx, r12; lpFileName
0x18006b996  call    cs:__imp_CreateFileW
0x18006b99c  mov     rsi, rax
0x18006b99f  mov     [rsp+98h+var_40], rax
0x18006b9a4  cmp     rax, r14
0x18006b9a7  jnz     short loc_18006B9C4
0x18006b9a9  call    cs:__imp_GetLastError
0x18006b9af  mov     [rsp+98h+var_54], eax
0x18006b9b3  lea     rdx, _TI1K; pThrowInfo
0x18006b9ba  lea     rcx, [rsp+98h+var_54]; pExceptionObject
0x18006b9bf  call    _CxxThrowException_0
0x18006b9c4  mov     rcx, rsi; hFile
0x18006b9c7  call    cs:__imp_GetFileType
0x18006b9cd  mov     rcx, rsi; hFile
0x18006b9d0  cmp     eax, 1
0x18006b9d3  jz      short loc_18006B9F9
0x18006b9d5  call    cs:__imp_CloseHandle
0x18006b9db  mov     [rsp+98h+var_40], r14
0x18006b9e0  mov     [rsp+98h+var_50], 5
0x18006b9e8  lea     rdx, _TI1J; pThrowInfo
0x18006b9ef  lea     rcx, [rsp+98h+var_50]; pExceptionObject
0x18006b9f4  call    _CxxThrowException_0
0x18006b9f9  mov     [rsp+98h+NumberOfBytesWritten], edi
0x18006b9fd  lea     r8d, ds:0[r13*2]; nNumberOfBytesToWrite
0x18006ba05  mov     qword ptr [rsp+98h+dwCreationDisposition], rdi; lpOverlapped
0x18006ba0a  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006ba0f  mov     rdx, rbx; lpBuffer
0x18006ba12  call    cs:__imp_WriteFile
0x18006ba18  test    eax, eax
0x18006ba1a  jnz     short loc_18006BA37
0x18006ba1c  call    cs:__imp_GetLastError
0x18006ba22  mov     [rsp+98h+var_48], eax
0x18006ba26  lea     rdx, _TI1K; pThrowInfo
0x18006ba2d  lea     rcx, [rsp+98h+var_48]; pExceptionObject
0x18006ba32  call    _CxxThrowException_0
0x18006ba37  mov     rcx, rsi; hFile
0x18006ba3a  call    cs:__imp_SetEndOfFile
0x18006ba40  nop
0x18006ba41  mov     rcx, rbx; void *
0x18006ba44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006ba49  nop
0x18006ba4a  jmp     short loc_18006BA6E
0x18006ba4c  jmp     short $+2
0x18006ba4e  mov     rsi, [rsp+98h+var_40]
0x18006ba53  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006ba57  xor     edi, edi
0x18006ba59  mov     r12, [rsp+98h+arg_0]
0x18006ba61  mov     r15d, dword ptr [rsp+98h+arg_18]
0x18006ba69  cmp     rsi, r14
0x18006ba6c  jz      short loc_18006BA77
0x18006ba6e  mov     rcx, rsi; hObject
0x18006ba71  call    cs:__imp_CloseHandle
0x18006ba77  test    r15d, r15d
0x18006ba7a  js      short loc_18006BA91
0x18006ba7c  mov     rcx, cs:?_UdlCacheMap@@3PEAVCUdlCacheMap@@EA; CUdlCacheMap * _UdlCacheMap
0x18006ba83  cmp     [rcx+3Ch], dil
0x18006ba87  jz      short loc_18006BA91
0x18006ba89  mov     rdx, r12
0x18006ba8c  call    ?DeleteRecord@?$TCMHashTableLocked@PEBGPEAVCUdlCacheValue@@@@QEAAXPEBG@Z; TCMHashTableLocked<ushort const *,CUdlCacheValue *>::DeleteRecord(ushort const *)
0x18006ba91  test    byte ptr cs:_bidGblFlags, 2
0x18006ba98  jz      short loc_18006BAB8
0x18006ba9a  mov     r9d, r15d
0x18006ba9d  lea     r8, aWritestringtos; "<WriteStringToStorage|Trace|HR> "
0x18006baa4  mov     edx, 1A6409h
0x18006baa9  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006bab0  call    _bidTraceHR
0x18006bab5  mov     r15d, eax
0x18006bab8  mov     eax, r15d
0x18006babb  jmp     short loc_18006BAC2
0x18006babd  mov     eax, 80070057h
0x18006bac2  add     rsp, 60h
0x18006bac6  pop     r15
0x18006bac8  pop     r14
0x18006baca  pop     r13
0x18006bacc  pop     r12
0x18006bace  pop     rdi
0x18006bacf  pop     rsi
0x18006bad0  pop     rbx
0x18006bad1  retn
```
