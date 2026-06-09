# LoadStringFromDisk(ushort const *,ushort * *)

- ea: `0x18006a844`
- end: `0x18006aa83`
- name: `?LoadStringFromDisk@@YAJPEBGPEAPEAG@Z`
- size: `575`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18006ac14`

## callees

- `0x180029560`
- `0x18002ec0c`
- `0x18006a844`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18006a9de`
- `msvcrt!_wcsnicmp` at `0x18006a9de`
- `MSDART!MpHeapAlloc` at `0x18006a942`
- `MSDART!MpHeapAlloc` at `0x18006a942`
- `KERNEL32!ReadFile` at `0x18006a996`
- `KERNEL32!ReadFile` at `0x18006a996`
- `KERNEL32!GetFileType` at `0x18006a8cb`
- `KERNEL32!GetFileType` at `0x18006a8cb`
- `KERNEL32!GetFileSize` at `0x18006a8f4`
- `KERNEL32!GetFileSize` at `0x18006a8f4`
- `KERNEL32!CreateFileW` at `0x18006a896`
- `KERNEL32!CreateFileW` at `0x18006a896`
- `KERNEL32!GetLastError` at `0x18006a8ad`
- `KERNEL32!GetLastError` at `0x18006a902`
- `KERNEL32!GetLastError` at `0x18006a9a0`
- `KERNEL32!GetLastError` at `0x18006a8ad`
- `KERNEL32!GetLastError` at `0x18006a902`
- `KERNEL32!GetLastError` at `0x18006a9a0`
- `KERNEL32!SetLastError` at `0x18006a86c`
- `KERNEL32!SetLastError` at `0x18006a86c`
- `KERNEL32!CloseHandle` at `0x18006aa40`
- `KERNEL32!CloseHandle` at `0x18006aa40`

## pseudocode

```c
__int64 __fastcall LoadStringFromDisk(LPCWSTR lpFileName, const wchar_t **a2)
{
  unsigned int v4; // esi
  HANDLE FileW; // rax
  void *v6; // rbx
  DWORD FileSize; // r15d
  __int64 v8; // r14
  __int64 v9; // rax
  wchar_t *v10; // rax
  const wchar_t *v11; // rdi
  __int64 result; // rax
  ulong pExceptionObject; // [rsp+40h] [rbp-58h] BYREF
  ulong v14; // [rsp+44h] [rbp-54h] BYREF
  ulong LastError; // [rsp+48h] [rbp-50h] BYREF
  ulong v16; // [rsp+4Ch] [rbp-4Ch] BYREF
  ulong v17; // [rsp+50h] [rbp-48h] BYREF
  ulong v18; // [rsp+54h] [rbp-44h] BYREF
  ulong v19; // [rsp+58h] [rbp-40h] BYREF
  HANDLE v20; // [rsp+60h] [rbp-38h]
  wchar_t *v22; // [rsp+B0h] [rbp+18h]
  int v23; // [rsp+B0h] [rbp+18h]
  DWORD NumberOfBytesRead; // [rsp+B8h] [rbp+20h] BYREF

  v4 = 0;
  SetLastError(0);
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  try
  {
    v6 = FileW;
    v20 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    if ( GetFileType(FileW) != 1 )
    {
      v14 = 5;
      throw &v14;
    }
    FileSize = GetFileSize(v6, 0);
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
      throw &LastError;
    }
    v8 = FileSize >> 1;
    v9 = 2LL * (unsigned int)(v8 + 1);
    if ( !is_mul_ok((unsigned int)(v8 + 1), 2u) )
      v9 = -1;
    v10 = (wchar_t *)MpHeapAlloc(g_hHeapHandle, 19922944, v9);
    v11 = v10;
    v22 = v10;
    if ( !v10 )
    {
      v16 = 8;
      throw &v16;
    }
    NumberOfBytesRead = 0;
    if ( !ReadFile(v6, v10, FileSize, &NumberOfBytesRead, 0) )
    {
      v17 = GetLastError();
      throw &v17;
    }
    v11[v8] = 0;
    if ( !NumberOfBytesRead || (unsigned int)v8 <= 0x40 || _wcsnicmp(v11, &wszMDLVersion1Header, 0x40u) )
    {
      v18 = -2147286789;
      throw &v18;
    }
    if ( v11[(unsigned int)(v8 - 2)] == 13 && v11[(unsigned int)(v8 - 1)] == 10 )
      v11[(unsigned int)(v8 - 2)] = 0;
    *a2 = v11;
  }
  catch ( ulong v19 )
  {
    if ( v22 )
      operator delete(v22);
    *a2 = 0;
    v23 = MapERRtoHRESULT(v19);
    goto LABEL_22;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8AA8[0] )
      bidTraceA(off_1800C8468[0], 1629184, off_1800C8AA8[0], 0);
    if ( v22 )
      operator delete(v22);
    *a2 = 0;
    v23 = -2147418113;
LABEL_22:
    v6 = v20;
    v4 = v23;
    if ( v20 != (HANDLE)-1LL )
      goto LABEL_23;
LABEL_24:
    if ( (bidGblFlags & 2) != 0 )
      v4 = bidTraceHR(off_1800C8468[0], 1642505, L"<LoadStringFromDisk|Trace|HR> ", v4);
    result = v4;
  }
LABEL_23:
  CloseHandle(v6);
  goto LABEL_24;
}

```

## disassembly

```asm
0x18006a844  mov     [rsp+arg_0], rbx
0x18006a849  mov     [rsp+arg_8], rdx
0x18006a84e  push    rsi
0x18006a84f  push    rdi
0x18006a850  push    r12
0x18006a852  push    r14
0x18006a854  push    r15
0x18006a856  sub     rsp, 70h
0x18006a85a  mov     r12, rdx
0x18006a85d  mov     rbx, rcx
0x18006a860  xor     esi, esi
0x18006a862  mov     [rsp+98h+arg_10], rsi
0x18006a86a  xor     ecx, ecx; dwErrCode
0x18006a86c  call    cs:__imp_SetLastError
0x18006a872  mov     [rsp+98h+hTemplateFile], rsi; hTemplateFile
0x18006a877  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006a87f  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18006a887  xor     r9d, r9d; lpSecurityAttributes
0x18006a88a  mov     edx, 80000000h; dwDesiredAccess
0x18006a88f  lea     r8d, [rsi+1]; dwShareMode
0x18006a893  mov     rcx, rbx; lpFileName
0x18006a896  call    cs:__imp_CreateFileW
0x18006a89c  mov     rbx, rax
0x18006a89f  mov     [rsp+98h+var_38], rax
0x18006a8a4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006a8a8  cmp     rax, rdi
0x18006a8ab  jnz     short loc_18006A8C8
0x18006a8ad  call    cs:__imp_GetLastError
0x18006a8b3  mov     [rsp+98h+pExceptionObject], eax
0x18006a8b7  lea     rdx, _TI1K; pThrowInfo
0x18006a8be  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18006a8c3  call    _CxxThrowException_0
0x18006a8c8  mov     rcx, rbx; hFile
0x18006a8cb  call    cs:__imp_GetFileType
0x18006a8d1  cmp     eax, 1
0x18006a8d4  jz      short loc_18006A8EF
0x18006a8d6  mov     [rsp+98h+var_54], 5
0x18006a8de  lea     rdx, _TI1K; pThrowInfo
0x18006a8e5  lea     rcx, [rsp+98h+var_54]; pExceptionObject
0x18006a8ea  call    _CxxThrowException_0
0x18006a8ef  xor     edx, edx; lpFileSizeHigh
0x18006a8f1  mov     rcx, rbx; hFile
0x18006a8f4  call    cs:__imp_GetFileSize
0x18006a8fa  mov     r15d, eax
0x18006a8fd  cmp     eax, 0FFFFFFFFh
0x18006a900  jnz     short loc_18006A91D
0x18006a902  call    cs:__imp_GetLastError
0x18006a908  mov     [rsp+98h+var_50], eax
0x18006a90c  lea     rdx, _TI1K; pThrowInfo
0x18006a913  lea     rcx, [rsp+98h+var_50]; pExceptionObject
0x18006a918  call    _CxxThrowException_0
0x18006a91d  mov     r14d, r15d
0x18006a920  shr     r14d, 1
0x18006a923  lea     ecx, [r14+1]
0x18006a927  mov     eax, 2
0x18006a92c  mul     rcx
0x18006a92f  cmovb   rax, rdi
0x18006a933  mov     r8, rax
0x18006a936  mov     edx, 1300000h
0x18006a93b  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18006a942  call    cs:__imp_MpHeapAlloc
0x18006a948  mov     rdi, rax
0x18006a94b  mov     [rsp+98h+arg_10], rax
0x18006a953  test    rax, rax
0x18006a956  jnz     short loc_18006A971
0x18006a958  mov     [rsp+98h+var_4C], 8
0x18006a960  lea     rdx, _TI1K; pThrowInfo
0x18006a967  lea     rcx, [rsp+98h+var_4C]; pExceptionObject
0x18006a96c  call    _CxxThrowException_0
0x18006a971  mov     [rsp+98h+NumberOfBytesRead], 0
0x18006a97c  mov     qword ptr [rsp+98h+dwCreationDisposition], 0; lpOverlapped
0x18006a985  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006a98d  mov     r8d, r15d; nNumberOfBytesToRead
0x18006a990  mov     rdx, rdi; lpBuffer
0x18006a993  mov     rcx, rbx; hFile
0x18006a996  call    cs:__imp_ReadFile
0x18006a99c  test    eax, eax
0x18006a99e  jnz     short loc_18006A9BB
0x18006a9a0  call    cs:__imp_GetLastError
0x18006a9a6  mov     [rsp+98h+var_48], eax
0x18006a9aa  lea     rdx, _TI1K; pThrowInfo
0x18006a9b1  lea     rcx, [rsp+98h+var_48]; pExceptionObject
0x18006a9b6  call    _CxxThrowException_0
0x18006a9bb  xor     eax, eax
0x18006a9bd  mov     [rdi+r14*2], ax
0x18006a9c2  cmp     [rsp+98h+NumberOfBytesRead], eax
0x18006a9c9  jz      short loc_18006AA0C
0x18006a9cb  lea     r8d, [rax+40h]; MaxCount
0x18006a9cf  cmp     r14d, r8d
0x18006a9d2  jbe     short loc_18006AA0C
0x18006a9d4  lea     rdx, ?wszMDLVersion1Header@@3PAGA; String2
0x18006a9db  mov     rcx, rdi; String1
0x18006a9de  call    cs:__imp__wcsnicmp
0x18006a9e4  test    eax, eax
0x18006a9e6  jnz     short loc_18006AA0C
0x18006a9e8  lea     eax, [r14-2]
0x18006a9ec  mov     edx, eax
0x18006a9ee  cmp     word ptr [rdi+rax*2], 0Dh
0x18006a9f3  jnz     short loc_18006AA06
0x18006a9f5  lea     eax, [r14-1]
0x18006a9f9  cmp     word ptr [rdi+rax*2], 0Ah
0x18006a9fe  jnz     short loc_18006AA06
0x18006aa00  xor     eax, eax
0x18006aa02  mov     [rdi+rdx*2], ax
0x18006aa06  mov     [r12], rdi
0x18006aa0a  jmp     short loc_18006AA3D
0x18006aa0c  mov     [rsp+98h+var_44], 800300FBh
0x18006aa14  lea     rdx, _TI1K; pThrowInfo
0x18006aa1b  lea     rcx, [rsp+98h+var_44]; pExceptionObject
0x18006aa20  call    _CxxThrowException_0
0x18006aa26  jmp     short $+2
0x18006aa28  mov     rbx, [rsp+98h+var_38]
0x18006aa2d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006aa31  mov     esi, dword ptr [rsp+98h+arg_10]
0x18006aa38  cmp     rbx, rdi
0x18006aa3b  jz      short loc_18006AA46
0x18006aa3d  mov     rcx, rbx; hObject
0x18006aa40  call    cs:__imp_CloseHandle
0x18006aa46  test    byte ptr cs:_bidGblFlags, 2
0x18006aa4d  jz      short loc_18006AA6C
0x18006aa4f  mov     r9d, esi
0x18006aa52  lea     r8, aLoadstringfrom; "<LoadStringFromDisk|Trace|HR> "
0x18006aa59  mov     edx, 191009h
0x18006aa5e  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006aa65  call    _bidTraceHR
0x18006aa6a  mov     esi, eax
0x18006aa6c  mov     eax, esi
0x18006aa6e  mov     rbx, [rsp+98h+arg_0]
0x18006aa76  add     rsp, 70h
0x18006aa7a  pop     r15
0x18006aa7c  pop     r14
0x18006aa7e  pop     r12
0x18006aa80  pop     rdi
0x18006aa81  pop     rsi
0x18006aa82  retn
```
