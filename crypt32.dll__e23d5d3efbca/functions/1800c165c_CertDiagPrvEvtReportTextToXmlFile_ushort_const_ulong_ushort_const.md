# CertDiagPrvEvtReportTextToXmlFile(ushort const *,ulong,ushort const *)

- ea: `0x1800c165c`
- end: `0x1800c17dc`
- name: `?CertDiagPrvEvtReportTextToXmlFile@@YAHPEBGK0@Z`
- size: `384`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800101d0`
- `0x180010af4`
- `0x180010fd0`

## callees

- `0x18005d484`
- `0x1800823c0`
- `0x180082450`
- `0x1800c165c`
- `0x180110f38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c16c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c16c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c16cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c16cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c17bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c17bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c168a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c168a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c16b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c16b8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c16fa`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800c16fa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1752`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1777`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c17a3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1752`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c1777`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c17a3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800c1713`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800c1713`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c17b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c17b2`

## pseudocode

```c
__int64 __fastcall CertDiagPrvEvtReportTextToXmlFile(LPCWSTR lpFileName, int a2, const unsigned __int16 *a3)
{
  void *v6; // rbp
  HANDLE FileW; // rdi
  DWORD LastError; // eax
  unsigned int v9; // ebx
  bool v10; // zf
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  v6 = CertDiagPrvRevertImpersonateToken();
  EnterCriticalSection(&g_CertDiagCriticalSection);
  FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 4u, 0, 0);
  LastError = GetLastError();
  if ( FileW == (HANDLE)-1LL )
  {
    SetLastError(LastError);
    v9 = 0;
  }
  else
  {
    v9 = 1;
    if ( LastError == 183 )
    {
      v10 = SetFilePointer(FileW, -dword_180157A7C, 0, 2u) == -1;
    }
    else
    {
      if ( !(unsigned int)I_CryptIsAppContainerToken(0) )
      {
        GetFileAttributesW(lpFileName);
        SetLowIntegrityFile(lpFileName);
      }
      v10 = !WriteFile(FileW, qword_18013C440, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
    }
    if ( v10
      || !WriteFile(FileW, a3, 2 * a2, &NumberOfBytesWritten, 0)
      || !WriteFile(FileW, L"</CertDiag>", dword_180157A7C, &NumberOfBytesWritten, 0) )
    {
      v9 = 0;
    }
    CloseHandle(FileW);
  }
  LeaveCriticalSection(&g_CertDiagCriticalSection);
  CertDiagPrvRestoreImpersonateToken(v6);
  return v9;
}

```

## disassembly

```asm
0x1800c165c  mov     rax, rsp
0x1800c165f  push    rbx
0x1800c1660  push    rbp
0x1800c1661  push    rsi
0x1800c1662  push    rdi
0x1800c1663  push    r14
0x1800c1665  push    r15
0x1800c1667  sub     rsp, 48h
0x1800c166b  mov     r14, r8
0x1800c166e  mov     dword ptr [rax+20h], 0
0x1800c1675  mov     r15d, edx
0x1800c1678  mov     rsi, rcx
0x1800c167b  call    ?CertDiagPrvRevertImpersonateToken@@YAPEAXXZ; CertDiagPrvRevertImpersonateToken(void)
0x1800c1680  lea     rcx, ?g_CertDiagCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c1687  mov     rbp, rax
0x1800c168a  call    cs:__imp_EnterCriticalSection
0x1800c1690  xor     r9d, r9d; lpSecurityAttributes
0x1800c1693  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800c169c  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800c16a4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800c16a9  mov     rcx, rsi; lpFileName
0x1800c16ac  mov     [rsp+78h+dwCreationDisposition], 4; dwCreationDisposition
0x1800c16b4  lea     r8d, [r9+3]; dwShareMode
0x1800c16b8  call    cs:__imp_CreateFileW
0x1800c16be  mov     rdi, rax
0x1800c16c1  call    cs:__imp_GetLastError
0x1800c16c7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800c16cb  jnz     short loc_1800C16DC
0x1800c16cd  mov     ecx, eax; dwErrCode
0x1800c16cf  call    cs:__imp_SetLastError
0x1800c16d5  xor     ebx, ebx
0x1800c16d7  jmp     loc_1800C17B8
0x1800c16dc  mov     ebx, 1
0x1800c16e1  cmp     eax, 0B7h
0x1800c16e6  jnz     short loc_1800C1705
0x1800c16e8  mov     edx, cs:dword_180157A7C
0x1800c16ee  lea     r9d, [rbx+1]; dwMoveMethod
0x1800c16f2  neg     edx; lDistanceToMove
0x1800c16f4  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800c16f7  mov     rcx, rdi; hFile
0x1800c16fa  call    cs:__imp_SetFilePointer
0x1800c1700  cmp     eax, 0FFFFFFFFh
0x1800c1703  jmp     short loc_1800C175A
0x1800c1705  xor     ecx, ecx
0x1800c1707  call    I_CryptIsAppContainerToken
0x1800c170c  test    eax, eax
0x1800c170e  jnz     short loc_1800C1730
0x1800c1710  mov     rcx, rsi; lpFileName
0x1800c1713  call    cs:__imp_GetFileAttributesW
0x1800c1719  cmp     eax, 0FFFFFFFFh
0x1800c171c  jz      short loc_1800C1726
0x1800c171e  test    al, 10h
0x1800c1720  jz      short loc_1800C1726
0x1800c1722  mov     edx, ebx
0x1800c1724  jmp     short loc_1800C1728
0x1800c1726  xor     edx, edx
0x1800c1728  mov     rcx, rsi; lpFileName
0x1800c172b  call    _SetLowIntegrityFile
0x1800c1730  mov     r8d, cs:nNumberOfBytesToWrite; nNumberOfBytesToWrite
0x1800c1737  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c173f  lea     rdx, qword_18013C440; lpBuffer
0x1800c1746  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x1800c174f  mov     rcx, rdi; hFile
0x1800c1752  call    cs:__imp_WriteFile
0x1800c1758  test    eax, eax
0x1800c175a  jz      short loc_1800C17AD
0x1800c175c  lea     r8d, [r15+r15]; nNumberOfBytesToWrite
0x1800c1760  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x1800c1769  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c1771  mov     rdx, r14; lpBuffer
0x1800c1774  mov     rcx, rdi; hFile
0x1800c1777  call    cs:__imp_WriteFile
0x1800c177d  test    eax, eax
0x1800c177f  jz      short loc_1800C17AD
0x1800c1781  mov     r8d, cs:dword_180157A7C; nNumberOfBytesToWrite
0x1800c1788  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c1790  lea     rdx, aCertdiag; "</CertDiag>"
0x1800c1797  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x1800c17a0  mov     rcx, rdi; hFile
0x1800c17a3  call    cs:__imp_WriteFile
0x1800c17a9  test    eax, eax
0x1800c17ab  jnz     short loc_1800C17AF
0x1800c17ad  xor     ebx, ebx
0x1800c17af  mov     rcx, rdi; hObject
0x1800c17b2  call    cs:__imp_CloseHandle
0x1800c17b8  lea     rcx, ?g_CertDiagCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c17bf  call    cs:__imp_LeaveCriticalSection
0x1800c17c5  mov     rcx, rbp; hObject
0x1800c17c8  call    ?CertDiagPrvRestoreImpersonateToken@@YAXPEAX@Z; CertDiagPrvRestoreImpersonateToken(void *)
0x1800c17cd  mov     eax, ebx
0x1800c17cf  add     rsp, 48h
0x1800c17d3  pop     r15
0x1800c17d5  pop     r14
0x1800c17d7  pop     rdi
0x1800c17d8  pop     rsi
0x1800c17d9  pop     rbp
0x1800c17da  pop     rbx
0x1800c17db  retn
```
