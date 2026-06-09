# ElevateAndCallInstallDownloadedLegacyDriver(HWND__ *,unsigned __int64,_DRIVER_INFO_6W *)

- ea: `0x18002a83c`
- end: `0x18002ab66`
- name: `?ElevateAndCallInstallDownloadedLegacyDriver@@YAJPEAUHWND__@@_KPEAU_DRIVER_INFO_6W@@@Z`
- size: `810`
- prototype: `__int64 __fastcall(HWND, unsigned __int64, struct _DRIVER_INFO_6W *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002f364`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x180026498`
- `0x18002a5ac`
- `0x18002a83c`
- `0x18002b6f0`
- `0x18002c440`
- `0x180035208`
- `0x180036664`
- `0x180039044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aada`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002aa25`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002aa25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aabb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aabb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab31`
- `SHELL32!ShellExecuteExW` at `0x18002a9e0`
- `SHELL32!ShellExecuteExW` at `0x18002a9e0`

## string_xrefs

- `0x18002a8d6`: `PSetupElevatedInstallDownloadedLegacyDriverW `

## pseudocode

```c
__int64 __fastcall ElevateAndCallInstallDownloadedLegacyDriver(HWND a1, __int64 a2, struct _DRIVER_INFO_6W *a3)
{
  unsigned __int16 *v6; // rsi
  unsigned __int64 v7; // rsi
  unsigned int v8; // ebx
  char *v9; // r14
  __int64 i; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  NCoreLibrary *v13; // rcx
  int LastErrorAsFailHR; // eax
  unsigned int v15; // eax
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // r8
  NCoreLibrary *v18; // rcx
  NCoreLibrary *v19; // rcx
  signed int LastError; // eax
  unsigned int v21; // edi
  DWORD v22; // eax
  NCoreLibrary::TString *v23; // rcx
  DWORD ExitCode; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  void *v27; // [rsp+50h] [rbp-B0h] BYREF
  void *v28; // [rsp+58h] [rbp-A8h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v30[264]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(v30, 0, 0x208u);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v6 = 0;
  hMem = 0;
  ExitCode = 0;
  v28 = 0;
  v27 = 0;
  if ( !a3 )
  {
    v8 = -2147024809;
    goto LABEL_24;
  }
  v7 = (unsigned int)(2 * a2 + 152);
  v8 = CheckLUAAndInitialize(
         L"PSetupElevatedInstallDownloadedLegacyDriverW ",
         v7,
         &v28,
         &v27,
         (unsigned __int16 **)&hMem,
         v30);
  if ( (v8 & 0x80000000) != 0 )
  {
    v6 = (unsigned __int16 *)hMem;
    goto LABEL_24;
  }
  v9 = (char *)v27;
  memset_0(v27, 0, (unsigned int)v7);
  *(_QWORD *)v9 = v7;
  *((_OWORD *)v9 + 1) = *(_OWORD *)&a3->cVersion;
  *((_OWORD *)v9 + 2) = *(_OWORD *)&a3->pEnvironment;
  *((_OWORD *)v9 + 3) = *(_OWORD *)&a3->pDataFile;
  *((_OWORD *)v9 + 4) = *(_OWORD *)&a3->pHelpFile;
  *((_OWORD *)v9 + 5) = *(_OWORD *)&a3->pMonitorName;
  *((_OWORD *)v9 + 6) = *(_OWORD *)&a3->pszzPreviousNames;
  *((_OWORD *)v9 + 7) = *(_OWORD *)&a3->dwlDriverVersion;
  *((_OWORD *)v9 + 8) = *(_OWORD *)&a3->pszOEMUrl;
  *((_QWORD *)v9 + 18) = a3->pszProvider;
  memcpy_0(v9 + 152, &a3[1], 2 * a2);
  for ( i = 0; i != 14; ++i )
  {
    v11 = *(unsigned int *)&DriverInfo6Strings[4 * i];
    v12 = *(_QWORD *)((char *)&a3->cVersion + v11);
    if ( v12 )
      *(_QWORD *)&v9[v11 + 16] = v12 - (_QWORD)a3;
  }
  v6 = (unsigned __int16 *)hMem;
  pExecInfo.lpFile = v30;
  pExecInfo.cbSize = 112;
  pExecInfo.lpDirectory = &qword_18003C420;
  pExecInfo.lpVerb = L"runas";
  pExecInfo.fMask = 64;
  pExecInfo.hwnd = a1;
  pExecInfo.lpParameters = (LPCWSTR)hMem;
  pExecInfo.nShow = 1;
  if ( !ShellExecuteExW(&pExecInfo) || pExecInfo.hInstApp <= HINSTANCE_ERROR )
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13);
    v8 = LastErrorAsFailHR;
    if ( LastErrorAsFailHR < 0 )
    {
      v15 = StatusFromHResult((unsigned int)LastErrorAsFailHR);
      v16 = v6;
      v17 = L"ShellExecuteEx failed";
LABEL_20:
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"ElevateAndCallDownloadLegacyDriver",
        v17,
        v16,
        0,
        v15,
        v8);
      goto LABEL_24;
    }
  }
  if ( (unsigned int)WaitForNtPrintProcessToExit(pExecInfo.hProcess) )
  {
    v8 = NCoreLibrary::GetLastErrorAsFailHR(v18);
    v15 = StatusFromHResult(v8);
    v17 = L"WaitForNtPrintProcessToExit failed";
    goto LABEL_19;
  }
  if ( !GetExitCodeProcess(pExecInfo.hProcess, &ExitCode) )
  {
    v8 = NCoreLibrary::GetLastErrorAsFailHR(v19);
    v15 = StatusFromHResult(v8);
    v17 = L"GetExitCodeProcess failed";
LABEL_19:
    v16 = 0;
    goto LABEL_20;
  }
  if ( *((int *)v9 + 2) >= 0 && (v8 = ExitCode) != 0 )
  {
    if ( (int)ExitCode > 0 )
      v8 = (unsigned __int16)ExitCode | 0x80070000;
  }
  else
  {
    v8 = *((_DWORD *)v9 + 2);
  }
LABEL_24:
  if ( pExecInfo.hProcess )
  {
    if ( !CloseHandle(pExecInfo.hProcess) )
    {
      LastError = GetLastError();
      v21 = LastError;
      if ( LastError > 0 )
        v21 = (unsigned __int16)LastError | 0x80070000;
      v22 = GetLastError();
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"ElevateAndCallDownloadLegacyDriver",
        L"CloseHandle failed",
        L"CloseHandle(sei.hProcess)",
        0,
        v22,
        v21);
    }
    pExecInfo.hProcess = 0;
  }
  FreeSharedMemory(&v27, &v28);
  if ( v6 )
    LocalFree(v6);
  NCoreLibrary::TString::vFree(v23, &NCoreLibrary::TString::gszNullState);
  return v8;
}

```

## disassembly

```asm
0x18002a83c  push    rbp
0x18002a83e  push    rbx
0x18002a83f  push    rsi
0x18002a840  push    rdi
0x18002a841  push    r12
0x18002a843  push    r14
0x18002a845  push    r15
0x18002a847  lea     rbp, [rsp-1F0h]
0x18002a84f  sub     rsp, 2F0h
0x18002a856  mov     rax, cs:__security_cookie
0x18002a85d  xor     rax, rsp
0x18002a860  mov     [rbp+220h+var_40], rax
0x18002a867  mov     rdi, r8
0x18002a86a  mov     r15, rdx
0x18002a86d  mov     r12, rcx
0x18002a870  xor     edx, edx; Val
0x18002a872  mov     r8d, 208h; Size
0x18002a878  lea     rcx, [rbp+220h+var_250]; void *
0x18002a87c  call    memset_0
0x18002a881  xor     edx, edx; Val
0x18002a883  lea     rcx, [rsp+320h+pExecInfo]; void *
0x18002a888  lea     r8d, [rdx+70h]; Size
0x18002a88c  call    memset_0
0x18002a891  xor     esi, esi
0x18002a893  mov     [rsp+320h+hMem], rsi
0x18002a898  mov     [rsp+320h+ExitCode], esi
0x18002a89c  mov     [rsp+320h+var_2C8], rsi
0x18002a8a1  mov     [rsp+320h+var_2D0], rsi
0x18002a8a6  test    rdi, rdi
0x18002a8a9  jz      loc_18002AAAD
0x18002a8af  lea     rax, [rbp+220h+var_250]
0x18002a8b3  mov     [rsp+320h+var_2F8], rax; unsigned __int16 *
0x18002a8b8  lea     esi, ds:98h[r15*2]
0x18002a8c0  lea     rax, [rsp+320h+hMem]
0x18002a8c5  mov     edx, esi; unsigned __int64
0x18002a8c7  lea     r9, [rsp+320h+var_2D0]; void **
0x18002a8cc  mov     [rsp+320h+var_300], rax; unsigned __int16 **
0x18002a8d1  lea     r8, [rsp+320h+var_2C8]; void **
0x18002a8d6  lea     rcx, aPsetupelevated_5; "PSetupElevatedInstallDownloadedLegacyDr"...
0x18002a8dd  call    ?CheckLUAAndInitialize@@YAJPEBG_KPEAPEAX2PEAPEAGQEAG@Z; CheckLUAAndInitialize(ushort const *,unsigned __int64,void * *,void * *,ushort * *,ushort * const)
0x18002a8e2  mov     ebx, eax
0x18002a8e4  test    eax, eax
0x18002a8e6  js      loc_18002AAA6
0x18002a8ec  mov     r14, [rsp+320h+var_2D0]
0x18002a8f1  mov     r8d, esi; Size
0x18002a8f4  mov     rcx, r14; void *
0x18002a8f7  xor     edx, edx; Val
0x18002a8f9  call    memset_0
0x18002a8fe  mov     [r14], rsi
0x18002a901  lea     r8, [r15+r15]; Size
0x18002a905  movups  xmm0, xmmword ptr [rdi]
0x18002a908  lea     rdx, [rdi+88h]; Src
0x18002a90f  lea     rcx, [r14+98h]; void *
0x18002a916  movups  xmmword ptr [r14+10h], xmm0
0x18002a91b  movups  xmm1, xmmword ptr [rdi+10h]
0x18002a91f  movups  xmmword ptr [r14+20h], xmm1
0x18002a924  movups  xmm0, xmmword ptr [rdi+20h]
0x18002a928  movups  xmmword ptr [r14+30h], xmm0
0x18002a92d  movups  xmm1, xmmword ptr [rdi+30h]
0x18002a931  movups  xmmword ptr [r14+40h], xmm1
0x18002a936  movups  xmm0, xmmword ptr [rdi+40h]
0x18002a93a  movups  xmmword ptr [r14+50h], xmm0
0x18002a93f  movups  xmm1, xmmword ptr [rdi+50h]
0x18002a943  movups  xmmword ptr [r14+60h], xmm1
0x18002a948  movups  xmm0, xmmword ptr [rdi+60h]
0x18002a94c  movups  xmmword ptr [r14+70h], xmm0
0x18002a951  movups  xmm1, xmmword ptr [rdi+70h]
0x18002a955  movups  xmmword ptr [r14+80h], xmm1
0x18002a95d  mov     rax, [rdi+80h]
0x18002a964  mov     [r14+90h], rax
0x18002a96b  call    memcpy_0
0x18002a970  xor     ecx, ecx
0x18002a972  lea     rax, DriverInfo6Strings; "\b"
0x18002a979  mov     edx, [rax+rcx*8]
0x18002a97c  mov     rax, [rdx+rdi]
0x18002a980  test    rax, rax
0x18002a983  jz      short loc_18002A98D
0x18002a985  sub     rax, rdi
0x18002a988  mov     [rdx+r14+10h], rax
0x18002a98d  inc     rcx
0x18002a990  cmp     rcx, 0Eh
0x18002a994  jnz     short loc_18002A972
0x18002a996  mov     rsi, [rsp+320h+hMem]
0x18002a99b  lea     rax, [rbp+220h+var_250]
0x18002a99f  mov     [rsp+320h+pExecInfo.lpFile], rax
0x18002a9a4  lea     rcx, [rsp+320h+pExecInfo]; pExecInfo
0x18002a9a9  lea     rax, qword_18003C420
0x18002a9b0  mov     [rsp+320h+pExecInfo.cbSize], 70h ; 'p'
0x18002a9b8  mov     [rbp+220h+pExecInfo.lpDirectory], rax
0x18002a9bc  lea     rax, aRunas; "runas"
0x18002a9c3  mov     [rsp+320h+pExecInfo.lpVerb], rax
0x18002a9c8  mov     [rsp+320h+pExecInfo.fMask], 40h ; '@'
0x18002a9d0  mov     [rsp+320h+pExecInfo.hwnd], r12
0x18002a9d5  mov     [rbp+220h+pExecInfo.lpParameters], rsi
0x18002a9d9  mov     [rbp+220h+pExecInfo.nShow], 1
0x18002a9e0  call    cs:__imp_ShellExecuteExW
0x18002a9e6  test    eax, eax
0x18002a9e8  jz      short loc_18002A9F1
0x18002a9ea  cmp     [rbp+220h+pExecInfo.hInstApp], 20h ; ' '
0x18002a9ef  ja      short loc_18002AA0F
0x18002a9f1  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002a9f6  mov     ebx, eax
0x18002a9f8  test    eax, eax
0x18002a9fa  jns     short loc_18002AA0F
0x18002a9fc  mov     ecx, eax
0x18002a9fe  call    StatusFromHResult
0x18002aa03  mov     r9, rsi
0x18002aa06  lea     r8, aShellexecuteex; "ShellExecuteEx failed"
0x18002aa0d  jmp     short loc_18002AA69
0x18002aa0f  mov     rcx, [rbp+220h+pExecInfo.hProcess]; void *
0x18002aa13  call    ?WaitForNtPrintProcessToExit@@YAJPEAX@Z; WaitForNtPrintProcessToExit(void *)
0x18002aa18  test    eax, eax
0x18002aa1a  jnz     short loc_18002AA8F
0x18002aa1c  mov     rcx, [rbp+220h+pExecInfo.hProcess]; hProcess
0x18002aa20  lea     rdx, [rsp+320h+ExitCode]; lpExitCode
0x18002aa25  call    cs:__imp_GetExitCodeProcess
0x18002aa2b  test    eax, eax
0x18002aa2d  jz      short loc_18002AA51
0x18002aa2f  cmp     dword ptr [r14+8], 0
0x18002aa34  jl      short loc_18002AA4B
0x18002aa36  mov     ebx, [rsp+320h+ExitCode]
0x18002aa3a  test    ebx, ebx
0x18002aa3c  jz      short loc_18002AA4B
0x18002aa3e  jle     short loc_18002AAB2
0x18002aa40  movzx   ebx, bx
0x18002aa43  or      ebx, 80070000h
0x18002aa49  jmp     short loc_18002AAB2
0x18002aa4b  mov     ebx, [r14+8]
0x18002aa4f  jmp     short loc_18002AAB2
0x18002aa51  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002aa56  mov     ecx, eax
0x18002aa58  mov     ebx, eax
0x18002aa5a  call    StatusFromHResult
0x18002aa5f  lea     r8, aGetexitcodepro; "GetExitCodeProcess failed"
0x18002aa66  xor     r9d, r9d; unsigned __int16 *
0x18002aa69  mov     [rsp+320h+var_2F0], ebx; unsigned int
0x18002aa6d  lea     rdx, aElevateandcall_0; "ElevateAndCallDownloadLegacyDriver"
0x18002aa74  mov     dword ptr [rsp+320h+var_2F8], eax; unsigned int
0x18002aa78  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002aa7f  mov     [rsp+320h+var_300], 0; unsigned __int16 *
0x18002aa88  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002aa8d  jmp     short loc_18002AAB2
0x18002aa8f  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002aa94  mov     ecx, eax
0x18002aa96  mov     ebx, eax
0x18002aa98  call    StatusFromHResult
0x18002aa9d  lea     r8, aWaitforntprint; "WaitForNtPrintProcessToExit failed"
0x18002aaa4  jmp     short loc_18002AA66
0x18002aaa6  mov     rsi, [rsp+320h+hMem]
0x18002aaab  jmp     short loc_18002AAB2
0x18002aaad  mov     ebx, 80070057h
0x18002aab2  mov     rcx, [rbp+220h+pExecInfo.hProcess]; hObject
0x18002aab6  test    rcx, rcx
0x18002aab9  jz      short loc_18002AB1A
0x18002aabb  call    cs:__imp_CloseHandle
0x18002aac1  test    eax, eax
0x18002aac3  jnz     short loc_18002AB12
0x18002aac5  call    cs:__imp_GetLastError
0x18002aacb  mov     edi, eax
0x18002aacd  test    eax, eax
0x18002aacf  jle     short loc_18002AADA
0x18002aad1  movzx   edi, ax
0x18002aad4  or      edi, 80070000h
0x18002aada  call    cs:__imp_GetLastError
0x18002aae0  mov     [rsp+320h+var_2F0], edi; unsigned int
0x18002aae4  lea     r9, aClosehandleSei; "CloseHandle(sei.hProcess)"
0x18002aaeb  mov     dword ptr [rsp+320h+var_2F8], eax; unsigned int
0x18002aaef  lea     r8, aClosehandleFai; "CloseHandle failed"
0x18002aaf6  lea     rdx, aElevateandcall_0; "ElevateAndCallDownloadLegacyDriver"
0x18002aafd  mov     [rsp+320h+var_300], 0; unsigned __int16 *
0x18002ab06  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002ab0d  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002ab12  mov     [rbp+220h+pExecInfo.hProcess], 0
0x18002ab1a  lea     rdx, [rsp+320h+var_2C8]; void **
0x18002ab1f  lea     rcx, [rsp+320h+var_2D0]; void **
0x18002ab24  call    ?FreeSharedMemory@@YAXPEAPEAX0@Z; FreeSharedMemory(void * *,void * *)
0x18002ab29  test    rsi, rsi
0x18002ab2c  jz      short loc_18002AB37
0x18002ab2e  mov     rcx, rsi; hMem
0x18002ab31  call    cs:__imp_LocalFree
0x18002ab37  lea     rdx, ?gszNullState@TString@NCoreLibrary@@0PAGA; void *
0x18002ab3e  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x18002ab43  mov     eax, ebx
0x18002ab45  mov     rcx, [rbp+220h+var_40]
0x18002ab4c  xor     rcx, rsp; StackCookie
0x18002ab4f  call    __security_check_cookie
0x18002ab54  add     rsp, 2F0h
0x18002ab5b  pop     r15
0x18002ab5d  pop     r14
0x18002ab5f  pop     r12
0x18002ab61  pop     rdi
0x18002ab62  pop     rsi
0x18002ab63  pop     rbx
0x18002ab64  pop     rbp
0x18002ab65  retn
```
