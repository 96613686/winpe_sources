# CFile::SetStatus(wchar_t const *,CFileStatus const &,ATL::CAtlTransactionManager *)

- ea: `0x180236500`
- end: `0x180236792`
- name: `?SetStatus@CFile@@SAXPEB_WAEBUCFileStatus@@PEAVCAtlTransactionManager@ATL@@@Z`
- size: `658`
- prototype: `void __fastcall(const wchar_t *lpszFileName, const CFileStatus *status, ATL::CAtlTransactionManager *pTM)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180233718`
- `0x180236330`
- `0x180236500`
- `0x1802367c4`
- `0x1802373b0`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180236721`
- `KERNEL32!GetLastError` at `0x180236732`
- `KERNEL32!GetLastError` at `0x180236743`
- `KERNEL32!GetLastError` at `0x180236754`
- `KERNEL32!GetLastError` at `0x180236770`
- `KERNEL32!GetLastError` at `0x180236781`
- `KERNEL32!GetLastError` at `0x180236721`
- `KERNEL32!GetLastError` at `0x180236732`
- `KERNEL32!GetLastError` at `0x180236743`
- `KERNEL32!GetLastError` at `0x180236754`
- `KERNEL32!GetLastError` at `0x180236770`
- `KERNEL32!GetLastError` at `0x180236781`
- `KERNEL32!GetProcAddress` at `0x18023657c`
- `KERNEL32!GetProcAddress` at `0x1802366d4`
- `KERNEL32!GetProcAddress` at `0x18023657c`
- `KERNEL32!GetProcAddress` at `0x1802366d4`
- `KERNEL32!GetModuleHandleW` at `0x180236567`
- `KERNEL32!GetModuleHandleW` at `0x1802366bf`
- `KERNEL32!GetModuleHandleW` at `0x180236567`
- `KERNEL32!GetModuleHandleW` at `0x1802366bf`
- `KERNEL32!CloseHandle` at `0x180236691`
- `KERNEL32!CloseHandle` at `0x18023675f`
- `KERNEL32!CloseHandle` at `0x180236691`
- `KERNEL32!CloseHandle` at `0x18023675f`
- `KERNEL32!CreateFileW` at `0x18023665f`
- `KERNEL32!CreateFileW` at `0x18023665f`
- `KERNEL32!GetFileAttributesW` at `0x180236537`
- `KERNEL32!GetFileAttributesW` at `0x180236537`
- `KERNEL32!SetFileAttributesW` at `0x1802365a6`
- `KERNEL32!SetFileAttributesW` at `0x1802366fe`
- `KERNEL32!SetFileAttributesW` at `0x1802365a6`
- `KERNEL32!SetFileAttributesW` at `0x1802366fe`
- `KERNEL32!SetFileTime` at `0x180236680`
- `KERNEL32!SetFileTime` at `0x180236680`

## string_xrefs

- `0x180236560`: `kernel32.dll`
- `0x1802366b8`: `kernel32.dll`
- `0x180236572`: `SetFileAttributesTransactedW`
- `0x1802366ca`: `SetFileAttributesTransactedW`

## pseudocode

```c
void __fastcall CFile::SetStatus(
        const wchar_t *lpszFileName,
        const CFileStatus *status,
        ATL::CAtlTransactionManager *pTM)
{
  _FILETIME *p_creationTime; // r15
  _FILETIME *p_lastAccessTime; // r12
  DWORD FileAttributesW; // eax
  DWORD v9; // ebp
  DWORD m_attribute; // esi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v13; // eax
  HANDLE FileW; // rax
  void *v15; // rsi
  DWORD v16; // esi
  HMODULE v17; // rax
  FARPROC v18; // rax
  int v19; // eax
  DWORD LastError; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // ebx
  DWORD v24; // eax
  DWORD v25; // eax
  void *v26; // [rsp+38h] [rbp-40h]
  _FILETIME lastWriteTime; // [rsp+40h] [rbp-38h] BYREF
  _FILETIME lastAccessTime; // [rsp+90h] [rbp+18h] BYREF
  _FILETIME creationTime; // [rsp+98h] [rbp+20h] BYREF

  p_creationTime = 0;
  p_lastAccessTime = 0;
  if ( pTM )
    FileAttributesW = ATL::CAtlTransactionManager::GetFileAttributesW(pTM, lpszFileName);
  else
    FileAttributesW = GetFileAttributesW(lpszFileName);
  v9 = FileAttributesW;
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    CFileException::ThrowOsError(LastError, lpszFileName);
    __debugbreak();
  }
  m_attribute = status->m_attribute;
  if ( m_attribute != FileAttributesW && (FileAttributesW & 1) != 0 )
  {
    if ( pTM )
    {
      if ( pTM->m_hTransaction )
      {
        ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
        if ( ModuleHandleW )
        {
          ProcAddress = GetProcAddress(ModuleHandleW, "SetFileAttributesTransactedW");
          if ( ProcAddress )
          {
            v13 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, void *))ProcAddress)(
                    lpszFileName,
                    m_attribute,
                    pTM->m_hTransaction);
            goto LABEL_15;
          }
        }
        goto LABEL_13;
      }
      if ( !pTM->m_bFallback )
      {
LABEL_13:
        v13 = 0;
        goto LABEL_15;
      }
    }
    v13 = SetFileAttributesW(lpszFileName, m_attribute);
LABEL_15:
    if ( !v13 )
    {
      v21 = GetLastError();
      CFileException::ThrowOsError(v21, lpszFileName);
      __debugbreak();
    }
  }
  if ( status->m_mtime.m_time )
  {
    AfxTimeToFileTime(&status->m_mtime, &lastWriteTime);
    if ( status->m_atime.m_time )
    {
      AfxTimeToFileTime(&status->m_atime, &lastAccessTime);
      p_lastAccessTime = &lastAccessTime;
    }
    if ( status->m_ctime.m_time )
    {
      AfxTimeToFileTime(&status->m_ctime, &creationTime);
      p_creationTime = &creationTime;
    }
    if ( pTM )
      FileW = ATL::CAtlTransactionManager::CreateFileW(pTM, lpszFileName, 0xC0000000, 1u, 0, 3u, 0x80u, v26);
    else
      FileW = CreateFileW(lpszFileName, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
    v15 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v22 = GetLastError();
      CFileException::ThrowOsError(v22, lpszFileName);
      __debugbreak();
    }
    if ( !SetFileTime(FileW, p_creationTime, p_lastAccessTime, &lastWriteTime) )
    {
      v23 = GetLastError();
      CloseHandle(v15);
      CFileException::ThrowOsError(v23, lpszFileName);
      __debugbreak();
    }
    if ( !CloseHandle(v15) )
    {
      v24 = GetLastError();
      CFileException::ThrowOsError(v24, lpszFileName);
      __debugbreak();
    }
  }
  v16 = status->m_attribute;
  if ( v16 != v9 && (v9 & 1) == 0 )
  {
    if ( pTM )
    {
      if ( pTM->m_hTransaction )
      {
        v17 = GetModuleHandleW(L"kernel32.dll");
        if ( v17 )
        {
          v18 = GetProcAddress(v17, "SetFileAttributesTransactedW");
          if ( v18 )
          {
            v19 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, void *))v18)(lpszFileName, v16, pTM->m_hTransaction);
            goto LABEL_37;
          }
        }
        goto LABEL_35;
      }
      if ( !pTM->m_bFallback )
      {
LABEL_35:
        v19 = 0;
        goto LABEL_37;
      }
    }
    v19 = SetFileAttributesW(lpszFileName, v16);
LABEL_37:
    if ( !v19 )
    {
      v25 = GetLastError();
      CFileException::ThrowOsError(v25, lpszFileName);
      JUMPOUT(0x180236791LL);
    }
  }
}

```

## disassembly

```asm
0x180236500  mov     [rsp+arg_0], rbx
0x180236505  mov     [rsp+arg_8], rbp
0x18023650a  push    rsi
0x18023650b  push    rdi
0x18023650c  push    r12
0x18023650e  push    r14
0x180236510  push    r15
0x180236512  sub     rsp, 50h
0x180236516  xor     r15d, r15d
0x180236519  xor     r12d, r12d
0x18023651c  mov     rbx, pTM
0x18023651f  mov     r14, status
0x180236522  mov     rdi, lpszFileName
0x180236525  test    pTM, pTM
0x180236528  jz      short loc_180236537
0x18023652a  mov     status, lpszFileName; lpFileName
0x18023652d  mov     lpszFileName, rbx; this
0x180236530  call    ?GetFileAttributesW@CAtlTransactionManager@ATL@@QEAAKPEB_W@Z; ATL::CAtlTransactionManager::GetFileAttributesW(wchar_t const *)
0x180236535  jmp     short loc_18023653D
0x180236537  call    cs:__imp_GetFileAttributesW
0x18023653d  mov     ebp, eax
0x18023653f  cmp     eax, 0FFFFFFFFh
0x180236542  jz      loc_180236721
0x180236548  mov     esi, [r14+20h]
0x18023654c  cmp     esi, eax
0x18023654e  jz      short loc_1802365B4
0x180236550  test    bpl, 1
0x180236554  jz      short loc_1802365B4
0x180236556  test    rbx, rbx
0x180236559  jz      short loc_1802365A1
0x18023655b  cmp     [rbx], r12
0x18023655e  jz      short loc_180236597
0x180236560  lea     lpszFileName, aKernel32Dll_0; "kernel32.dll"
0x180236567  call    cs:__imp_GetModuleHandleW
0x18023656d  test    rax, rax
0x180236570  jz      short loc_18023659D
0x180236572  lea     status, aSetfileattribu; "SetFileAttributesTransactedW"
0x180236579  mov     lpszFileName, rax; hModule
0x18023657c  call    cs:__imp_GetProcAddress
0x180236582  test    rax, rax
0x180236585  jz      short loc_18023659D
0x180236587  mov     pTM, [rbx]
0x18023658a  mov     edx, esi
0x18023658c  mov     lpszFileName, rdi
0x18023658f  call    cs:__guard_dispatch_icall_fptr
0x180236595  jmp     short loc_1802365AC
0x180236597  cmp     [rbx+8], r12d
0x18023659b  jnz     short loc_1802365A1
0x18023659d  xor     eax, eax
0x18023659f  jmp     short loc_1802365AC
0x1802365a1  mov     edx, esi; dwFileAttributes
0x1802365a3  mov     lpszFileName, rdi; lpFileName
0x1802365a6  call    cs:__imp_SetFileAttributesW
0x1802365ac  test    eax, eax
0x1802365ae  jz      loc_180236732
0x1802365b4  lea     lpszFileName, [r14+8]; time
0x1802365b8  cmp     [lpszFileName], r12
0x1802365bb  jz      loc_18023669F
0x1802365c1  lea     status, [rsp+78h+lastWriteTime]; pFileTime
0x1802365c6  call    ?AfxTimeToFileTime@@YAXAEBVCTime@ATL@@PEAU_FILETIME@@@Z; AfxTimeToFileTime(ATL::CTime const &,_FILETIME *)
0x1802365cb  lea     lpszFileName, [r14+10h]; time
0x1802365cf  cmp     [lpszFileName], r12
0x1802365d2  jz      short loc_1802365E9
0x1802365d4  lea     status, [rsp+78h+lastAccessTime]; pFileTime
0x1802365dc  call    ?AfxTimeToFileTime@@YAXAEBVCTime@ATL@@PEAU_FILETIME@@@Z; AfxTimeToFileTime(ATL::CTime const &,_FILETIME *)
0x1802365e1  lea     r12, [rsp+78h+lastAccessTime]
0x1802365e9  cmp     [r14], r15
0x1802365ec  jz      short loc_180236606
0x1802365ee  lea     status, [rsp+78h+creationTime]; pFileTime
0x1802365f6  mov     lpszFileName, r14; time
0x1802365f9  call    ?AfxTimeToFileTime@@YAXAEBVCTime@ATL@@PEAU_FILETIME@@@Z; AfxTimeToFileTime(ATL::CTime const &,_FILETIME *)
0x1802365fe  lea     r15, [rsp+78h+creationTime]
0x180236606  test    rbx, rbx
0x180236609  jz      short loc_18023663A
0x18023660b  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180236613  mov     r9d, 1; dwShareMode
0x180236619  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180236621  mov     r8d, 0C0000000h; dwDesiredAccess
0x180236627  and     qword ptr [rsp+78h+var_58], 0
0x18023662d  mov     status, rdi; lpFileName
0x180236630  mov     lpszFileName, rbx; this
0x180236633  call    ?CreateFileW@CAtlTransactionManager@ATL@@QEAAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; ATL::CAtlTransactionManager::CreateFileW(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180236638  jmp     short loc_180236665
0x18023663a  and     qword ptr [rsp+78h+dwFlagsAndAttributes], 0
0x180236640  xor     r9d, r9d; lpSecurityAttributes
0x180236643  mov     [rsp+78h+dwCreationDisposition], 80h; dwFlagsAndAttributes
0x18023664b  mov     edx, 0C0000000h; dwDesiredAccess
0x180236650  mov     lpszFileName, rdi; lpFileName
0x180236653  mov     [rsp+78h+var_58], 3; dwCreationDisposition
0x18023665b  lea     r8d, [r9+1]; dwShareMode
0x18023665f  call    cs:__imp_CreateFileW
0x180236665  mov     rsi, rax
0x180236668  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18023666c  jz      loc_180236743
0x180236672  lea     r9, [rsp+78h+lastWriteTime]; lpLastWriteTime
0x180236677  mov     pTM, r12; lpLastAccessTime
0x18023667a  mov     status, r15; lpCreationTime
0x18023667d  mov     lpszFileName, rax; hFile
0x180236680  call    cs:__imp_SetFileTime
0x180236686  test    eax, eax
0x180236688  jz      loc_180236754
0x18023668e  mov     lpszFileName, rsi; hObject
0x180236691  call    cs:__imp_CloseHandle
0x180236697  test    eax, eax
0x180236699  jz      loc_180236770
0x18023669f  mov     esi, [r14+20h]
0x1802366a3  cmp     esi, ebp
0x1802366a5  jz      short loc_180236708
0x1802366a7  test    bpl, 1
0x1802366ab  jnz     short loc_180236708
0x1802366ad  test    rbx, rbx
0x1802366b0  jz      short loc_1802366F9
0x1802366b2  cmp     qword ptr [rbx], 0
0x1802366b6  jz      short loc_1802366EF
0x1802366b8  lea     lpszFileName, aKernel32Dll_0; "kernel32.dll"
0x1802366bf  call    cs:__imp_GetModuleHandleW
0x1802366c5  test    rax, rax
0x1802366c8  jz      short loc_1802366F5
0x1802366ca  lea     status, aSetfileattribu; "SetFileAttributesTransactedW"
0x1802366d1  mov     lpszFileName, rax; hModule
0x1802366d4  call    cs:__imp_GetProcAddress
0x1802366da  test    rax, rax
0x1802366dd  jz      short loc_1802366F5
0x1802366df  mov     pTM, [rbx]
0x1802366e2  mov     edx, esi
0x1802366e4  mov     lpszFileName, rdi
0x1802366e7  call    cs:__guard_dispatch_icall_fptr
0x1802366ed  jmp     short loc_180236704
0x1802366ef  cmp     dword ptr [rbx+8], 0
0x1802366f3  jnz     short loc_1802366F9
0x1802366f5  xor     eax, eax
0x1802366f7  jmp     short loc_180236704
0x1802366f9  mov     edx, esi; dwFileAttributes
0x1802366fb  mov     lpszFileName, rdi; lpFileName
0x1802366fe  call    cs:__imp_SetFileAttributesW
0x180236704  test    eax, eax
0x180236706  jz      short loc_180236781
0x180236708  lea     r11, [rsp+78h+var_28]
0x18023670d  mov     rbx, [r11+30h]
0x180236711  mov     rbp, [r11+38h]
0x180236715  mov     rsp, r11
0x180236718  pop     r15
0x18023671a  pop     r14
0x18023671c  pop     r12
0x18023671e  pop     rdi
0x18023671f  pop     rsi
0x180236720  retn
0x180236721  call    cs:__imp_GetLastError
0x180236727  mov     ecx, eax; lOsError
0x180236729  mov     status, rdi; lpszFileName
0x18023672c  call    ?ThrowOsError@CFileException@@SAXJPEB_W@Z; CFileException::ThrowOsError(long,wchar_t const *)
0x180236731  int     3; Trap to Debugger
0x180236732  call    cs:__imp_GetLastError
0x180236738  mov     ecx, eax; lOsError
0x18023673a  mov     status, rdi; lpszFileName
0x18023673d  call    ?ThrowOsError@CFileException@@SAXJPEB_W@Z; CFileException::ThrowOsError(long,wchar_t const *)
0x180236742  int     3; Trap to Debugger
0x180236743  call    cs:__imp_GetLastError
0x180236749  mov     ecx, eax; lOsError
0x18023674b  mov     status, rdi; lpszFileName
0x18023674e  call    ?ThrowOsError@CFileException@@SAXJPEB_W@Z; CFileException::ThrowOsError(long,wchar_t const *)
0x180236753  int     3; Trap to Debugger
0x180236754  call    cs:__imp_GetLastError
0x18023675a  mov     lpszFileName, rsi; hObject
0x18023675d  mov     ebx, eax
0x18023675f  call    cs:__imp_CloseHandle
0x180236765  mov     status, rdi; lpszFileName
0x180236768  mov     ecx, ebx; lOsError
0x18023676a  call    ?ThrowOsError@CFileException@@SAXJPEB_W@Z; CFileException::ThrowOsError(long,wchar_t const *)
0x18023676f  int     3; Trap to Debugger
0x180236770  call    cs:__imp_GetLastError
0x180236776  mov     ecx, eax; lOsError
0x180236778  mov     status, rdi; lpszFileName
0x18023677b  call    ?ThrowOsError@CFileException@@SAXJPEB_W@Z; CFileException::ThrowOsError(long,wchar_t const *)
0x180236780  int     3; Trap to Debugger
0x180236781  call    cs:__imp_GetLastError
0x180236787  mov     ecx, eax; lOsError
0x180236789  mov     status, rdi; lpszFileName
0x18023678c  call    ?ThrowOsError@CFileException@@SAXJPEB_W@Z; CFileException::ThrowOsError(long,wchar_t const *)
```
