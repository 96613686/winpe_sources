# ValidateLog

- ea: `0x18000d9b0`
- end: `0x18000dacb`
- name: `ValidateLog`
- size: `283`
- prototype: `BOOL __stdcall(LPCWSTR pszLogFileName, LPSECURITY_ATTRIBUTES psaLogFile, PCLFS_INFORMATION pinfoBuffer, PULONG pcbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009fe0`
- `0x18000b940`
- `0x18000d9b0`
- `0x180014dce`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dab0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dab0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001560a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001560a`

## pseudocode

```c
BOOL __stdcall ValidateLog(
        LPCWSTR pszLogFileName,
        LPSECURITY_ATTRIBUTES psaLogFile,
        PCLFS_INFORMATION pinfoBuffer,
        PULONG pcbBuffer)
{
  BOOL v6; // edi
  DWORD LastError; // ebx
  char *LogFile; // rsi

  v6 = 0;
  if ( pszLogFileName && ((LastError = 0, !pinfoBuffer) || pcbBuffer && *pcbBuffer >= 0x78) )
  {
    LogFile = (char *)CreateLogFile(pszLogFileName, 0xC0010000, 7u, psaLogFile, 3u, 0);
    if ( (unsigned __int64)(LogFile - 1) > 0xFFFFFFFFFFFFFFFDuLL
      || pinfoBuffer && (memset_0(pinfoBuffer, 0, *pcbBuffer), !GetLogFileInformation(LogFile, pinfoBuffer, pcbBuffer)) )
    {
      LastError = GetLastError();
    }
    if ( (unsigned __int64)(LogFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(LogFile);
    SetLastError(LastError);
    LOBYTE(v6) = LastError == 0;
    return v6;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000d9b0  push    rbx
0x18000d9b2  push    rsi
0x18000d9b3  push    rdi
0x18000d9b4  push    r14
0x18000d9b6  push    r15
0x18000d9b8  sub     rsp, 40h
0x18000d9bc  mov     r14, r9
0x18000d9bf  mov     r15, r8
0x18000d9c2  xor     edi, edi
0x18000d9c4  test    rcx, rcx
0x18000d9c7  jz      loc_18000DAAB
0x18000d9cd  mov     ebx, edi
0x18000d9cf  mov     [rsp+68h+var_38], ebx
0x18000d9d3  mov     [rsp+68h+var_30], rdi
0x18000d9d8  test    r8, r8
0x18000d9db  jz      short loc_18000D9F0
0x18000d9dd  test    r9, r9
0x18000d9e0  jz      loc_18000DAAB
0x18000d9e6  cmp     dword ptr [r9], 78h ; 'x'
0x18000d9ea  jb      loc_18000DAAB
0x18000d9f0  mov     [rsp+68h+fFlagsAndAttributes], edi; fFlagsAndAttributes
0x18000d9f4  mov     [rsp+68h+fCreateDisposition], 3; fCreateDisposition
0x18000d9fc  mov     r9, rdx; psaLogFile
0x18000d9ff  mov     edx, 0C0010000h; fDesiredAccess
0x18000da04  mov     r8d, 7; dwShareMode
0x18000da0a  call    CreateLogFile
0x18000da0f  mov     rsi, rax
0x18000da12  mov     [rsp+68h+var_30], rax
0x18000da17  dec     rax
0x18000da1a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000da1e  ja      short loc_18000DA68
0x18000da20  test    r15, r15
0x18000da23  jz      short loc_18000DA7A
0x18000da25  mov     r8d, [r14]; Size
0x18000da28  xor     edx, edx; Val
0x18000da2a  mov     rcx, r15; void *
0x18000da2d  call    memset_0
0x18000da32  nop
0x18000da33  mov     r8, r14; cbBuffer
0x18000da36  mov     rdx, r15; pinfoBuffer
0x18000da39  mov     rcx, rsi; hLog
0x18000da3c  call    GetLogFileInformation
0x18000da41  test    eax, eax
0x18000da43  jnz     short loc_18000DA7A
0x18000da45  jmp     short loc_18000DA68
0x18000da47  mov     ebx, eax
0x18000da49  mov     [rsp+68h+var_38], eax
0x18000da4d  mov     eax, 6F8h
0x18000da52  cmp     ebx, 0C0000005h
0x18000da58  cmovz   ebx, eax
0x18000da5b  mov     [rsp+68h+var_38], ebx
0x18000da5f  xor     edi, edi
0x18000da61  mov     rsi, [rsp+68h+var_30]
0x18000da66  jmp     short loc_18000DA7A
0x18000da68  call    cs:__imp_GetLastError
0x18000da6f  nop     dword ptr [rax+rax+00h]
0x18000da74  mov     [rsp+68h+var_38], eax
0x18000da78  mov     ebx, eax
0x18000da7a  lea     rcx, [rsi-1]
0x18000da7e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000da82  ja      short loc_18000DA93
0x18000da84  mov     rcx, rsi; hObject
0x18000da87  call    cs:__imp_CloseHandle
0x18000da8e  nop     dword ptr [rax+rax+00h]
0x18000da93  mov     ecx, ebx; dwErrCode
0x18000da95  call    cs:__imp_SetLastError
0x18000da9c  nop     dword ptr [rax+rax+00h]
0x18000daa1  test    ebx, ebx
0x18000daa3  setz    dil
0x18000daa7  mov     eax, edi
0x18000daa9  jmp     short loc_18000DABE
0x18000daab  mov     ecx, 57h ; 'W'; dwErrCode
0x18000dab0  call    cs:__imp_SetLastError
0x18000dab7  nop     dword ptr [rax+rax+00h]
0x18000dabc  xor     eax, eax
0x18000dabe  add     rsp, 40h
0x18000dac2  pop     r15
0x18000dac4  pop     r14
0x18000dac6  pop     rdi
0x18000dac7  pop     rsi
0x18000dac8  pop     rbx
0x18000dac9  retn
0x1800155f3  push    rbp
0x1800155f5  sub     rsp, 30h
0x1800155f9  mov     rbp, rdx
0x1800155fc  mov     rcx, [rbp+38h]; hObject
0x180015600  lea     rax, [rcx-1]
0x180015604  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015608  ja      short loc_18001561E
0x18001560a  call    cs:__imp_CloseHandle
0x180015611  nop     dword ptr [rax+rax+00h]
0x180015616  mov     qword ptr [rbp+38h], 0FFFFFFFFFFFFFFFFh
0x18001561e  mov     ecx, [rbp+30h]
0x180015621  add     rsp, 30h
0x180015625  pop     rbp
0x180015626  jmp     cs:__imp_SetLastError
```
