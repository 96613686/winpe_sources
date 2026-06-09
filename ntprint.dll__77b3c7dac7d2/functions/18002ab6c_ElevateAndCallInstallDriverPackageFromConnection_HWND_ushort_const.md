# ElevateAndCallInstallDriverPackageFromConnection(HWND__ *,ushort const *)

- ea: `0x18002ab6c`
- end: `0x18002ae24`
- name: `?ElevateAndCallInstallDriverPackageFromConnection@@YAJPEAUHWND__@@PEBG@Z`
- size: `696`
- prototype: `int(HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x18000cc50`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000b200`
- `0x18002a5ac`
- `0x18002ab6c`
- `0x18002b6f0`
- `0x18002c440`
- `0x180035208`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad9e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002ace5`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002ace5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ad7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002adf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002adf1`
- `SHELL32!ShellExecuteExW` at `0x18002aca0`
- `SHELL32!ShellExecuteExW` at `0x18002aca0`

## string_xrefs

- `0x18002abc7`: `PSetupElevatedInstallPrinterDriverFromConnection`
- `0x18002ac14`: `PSetupElevatedInstallDriverPackageFromConnectionW `

## pseudocode

```c
__int64 __fastcall ElevateAndCallInstallDriverPackageFromConnection(HWND a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rsi
  DWORD LastErrorAsFailHR; // ebx
  unsigned __int16 *v6; // rdi
  NCoreLibrary *v7; // rcx
  int v8; // eax
  unsigned int v9; // eax
  const unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // r8
  NCoreLibrary *v12; // rcx
  NCoreLibrary *v13; // rcx
  signed int LastError; // eax
  unsigned int v15; // edi
  DWORD v16; // eax
  DWORD ExitCode; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v20; // [rsp+50h] [rbp-B0h] BYREF
  void *v21; // [rsp+58h] [rbp-A8h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v23[264]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(v23, 0, 0x208u);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v4 = 0;
  v19 = 0;
  ExitCode = 0;
  v21 = 0;
  v20 = 0;
  if ( !a2 )
  {
    LastErrorAsFailHR = -2147024809;
    goto LABEL_22;
  }
  LastErrorAsFailHR = CheckLUAAndInitialize(
                        L"PSetupElevatedInstallDriverPackageFromConnectionW ",
                        0x20Cu,
                        &v21,
                        (void **)&v20,
                        &v19,
                        v23);
  if ( (LastErrorAsFailHR & 0x80000000) != 0
    || (v6 = v20,
        memset_0(v20, 0, 0x20Cu),
        LastErrorAsFailHR = StringCchCopyW(v6, 0x104u, a2),
        (LastErrorAsFailHR & 0x80000000) != 0) )
  {
    v4 = v19;
  }
  else
  {
    v4 = v19;
    pExecInfo.lpFile = v23;
    pExecInfo.cbSize = 112;
    pExecInfo.lpDirectory = &qword_18003C420;
    pExecInfo.lpVerb = L"runas";
    pExecInfo.fMask = 64;
    pExecInfo.hwnd = a1;
    pExecInfo.lpParameters = v19;
    pExecInfo.nShow = 1;
    if ( ShellExecuteExW(&pExecInfo) && pExecInfo.hInstApp > HINSTANCE_ERROR
      || (v8 = NCoreLibrary::GetLastErrorAsFailHR(v7), LastErrorAsFailHR = v8, v8 >= 0) )
    {
      if ( (unsigned int)WaitForNtPrintProcessToExit(pExecInfo.hProcess) )
      {
        LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v12);
        v9 = StatusFromHResult(LastErrorAsFailHR);
        v11 = L"WaitForNtPrintProcessToExit failed";
      }
      else if ( GetExitCodeProcess(pExecInfo.hProcess, &ExitCode) )
      {
        if ( *((int *)v6 + 130) < 0 || (LastErrorAsFailHR = ExitCode) == 0 )
        {
          LastErrorAsFailHR = *((_DWORD *)v6 + 130);
          goto LABEL_22;
        }
        if ( (int)ExitCode > 0 )
          LastErrorAsFailHR = (unsigned __int16)ExitCode | 0x80070000;
        v9 = StatusFromHResult(LastErrorAsFailHR);
        v11 = L"Process exited due to failure";
      }
      else
      {
        LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13);
        v9 = StatusFromHResult(LastErrorAsFailHR);
        v11 = L"GetExitCodeProcess failed";
      }
      v10 = 0;
    }
    else
    {
      v9 = StatusFromHResult((unsigned int)v8);
      v10 = v4;
      v11 = L"ShellExecuteEx failed";
    }
    SplLogPrinterSetupGenericEvent(
      &SETUP_PRINTER_OPERATION_FAILED,
      L"PSetupElevatedInstallPrinterDriverFromConnection",
      v11,
      v10,
      0,
      v9,
      LastErrorAsFailHR);
  }
LABEL_22:
  if ( pExecInfo.hProcess )
  {
    if ( !CloseHandle(pExecInfo.hProcess) )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      v16 = GetLastError();
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"PSetupElevatedInstallPrinterDriverFromConnection",
        L"CloseHandle failed",
        L"CloseHandle(sei.hProcess)",
        0,
        v16,
        v15);
    }
    pExecInfo.hProcess = 0;
  }
  FreeSharedMemory((void **)&v20, &v21);
  if ( v4 )
    LocalFree(v4);
  return LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18002ab6c  mov     [rsp-8+arg_10], rbx
0x18002ab71  mov     [rsp-8+arg_18], rsi
0x18002ab76  push    rbp
0x18002ab77  push    rdi
0x18002ab78  push    r13
0x18002ab7a  push    r14
0x18002ab7c  push    r15
0x18002ab7e  lea     rbp, [rsp-1F0h]
0x18002ab86  sub     rsp, 2F0h
0x18002ab8d  mov     rax, cs:__security_cookie
0x18002ab94  xor     rax, rsp
0x18002ab97  mov     [rbp+210h+var_30], rax
0x18002ab9e  mov     r14, rdx
0x18002aba1  mov     r15, rcx
0x18002aba4  xor     edx, edx; Val
0x18002aba6  lea     rcx, [rbp+210h+var_240]; void *
0x18002abaa  mov     r8d, 208h; Size
0x18002abb0  call    memset_0
0x18002abb5  xor     edx, edx; Val
0x18002abb7  lea     rcx, [rsp+310h+pExecInfo]; void *
0x18002abbc  lea     r8d, [rdx+70h]; Size
0x18002abc0  call    memset_0
0x18002abc5  xor     esi, esi
0x18002abc7  lea     r13, aPsetupelevated_4; "PSetupElevatedInstallPrinterDriverFromC"...
0x18002abce  mov     [rsp+310h+var_2C8], rsi
0x18002abd3  mov     [rsp+310h+ExitCode], esi
0x18002abd7  mov     [rsp+310h+var_2B8], rsi
0x18002abdc  mov     [rsp+310h+var_2C0], rsi
0x18002abe1  test    r14, r14
0x18002abe4  jnz     short loc_18002ABF0
0x18002abe6  mov     ebx, 80070057h
0x18002abeb  jmp     loc_18002AD76
0x18002abf0  lea     rax, [rbp+210h+var_240]
0x18002abf4  mov     edi, 20Ch
0x18002abf9  mov     [rsp+310h+var_2E8], rax; unsigned __int16 *
0x18002abfe  lea     r9, [rsp+310h+var_2C0]; void **
0x18002ac03  lea     rax, [rsp+310h+var_2C8]
0x18002ac08  mov     edx, edi; unsigned __int64
0x18002ac0a  lea     r8, [rsp+310h+var_2B8]; void **
0x18002ac0f  mov     [rsp+310h+var_2F0], rax; unsigned __int16 **
0x18002ac14  lea     rcx, aPsetupelevated_6; "PSetupElevatedInstallDriverPackageFromC"...
0x18002ac1b  call    ?CheckLUAAndInitialize@@YAJPEBG_KPEAPEAX2PEAPEAGQEAG@Z; CheckLUAAndInitialize(ushort const *,unsigned __int64,void * *,void * *,ushort * *,ushort * const)
0x18002ac20  mov     ebx, eax
0x18002ac22  test    eax, eax
0x18002ac24  js      loc_18002AD71
0x18002ac2a  mov     r8d, edi; Size
0x18002ac2d  xor     edx, edx; Val
0x18002ac2f  mov     rdi, [rsp+310h+var_2C0]
0x18002ac34  mov     rcx, rdi; void *
0x18002ac37  call    memset_0
0x18002ac3c  mov     r8, r14; unsigned __int16 *
0x18002ac3f  mov     edx, 104h; unsigned __int64
0x18002ac44  mov     rcx, rdi; unsigned __int16 *
0x18002ac47  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ac4c  mov     ebx, eax
0x18002ac4e  test    eax, eax
0x18002ac50  js      loc_18002AD71
0x18002ac56  mov     rsi, [rsp+310h+var_2C8]
0x18002ac5b  lea     rax, [rbp+210h+var_240]
0x18002ac5f  mov     [rsp+310h+pExecInfo.lpFile], rax
0x18002ac64  lea     rcx, [rsp+310h+pExecInfo]; pExecInfo
0x18002ac69  lea     rax, qword_18003C420
0x18002ac70  mov     [rsp+310h+pExecInfo.cbSize], 70h ; 'p'
0x18002ac78  mov     [rbp+210h+pExecInfo.lpDirectory], rax
0x18002ac7c  lea     rax, aRunas; "runas"
0x18002ac83  mov     [rsp+310h+pExecInfo.lpVerb], rax
0x18002ac88  mov     [rsp+310h+pExecInfo.fMask], 40h ; '@'
0x18002ac90  mov     [rsp+310h+pExecInfo.hwnd], r15
0x18002ac95  mov     [rbp+210h+pExecInfo.lpParameters], rsi
0x18002ac99  mov     [rbp+210h+pExecInfo.nShow], 1
0x18002aca0  call    cs:__imp_ShellExecuteExW
0x18002aca6  test    eax, eax
0x18002aca8  jz      short loc_18002ACB1
0x18002acaa  cmp     [rbp+210h+pExecInfo.hInstApp], 20h ; ' '
0x18002acaf  ja      short loc_18002ACCF
0x18002acb1  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002acb6  mov     ebx, eax
0x18002acb8  test    eax, eax
0x18002acba  jns     short loc_18002ACCF
0x18002acbc  mov     ecx, eax
0x18002acbe  call    StatusFromHResult
0x18002acc3  mov     r9, rsi
0x18002acc6  lea     r8, aShellexecuteex; "ShellExecuteEx failed"
0x18002accd  jmp     short loc_18002AD38
0x18002accf  mov     rcx, [rbp+210h+pExecInfo.hProcess]; void *
0x18002acd3  call    ?WaitForNtPrintProcessToExit@@YAJPEAX@Z; WaitForNtPrintProcessToExit(void *)
0x18002acd8  test    eax, eax
0x18002acda  jnz     short loc_18002AD5A
0x18002acdc  mov     rcx, [rbp+210h+pExecInfo.hProcess]; hProcess
0x18002ace0  lea     rdx, [rsp+310h+ExitCode]; lpExitCode
0x18002ace5  call    cs:__imp_GetExitCodeProcess
0x18002aceb  test    eax, eax
0x18002aced  jz      short loc_18002AD20
0x18002acef  mov     eax, [rdi+208h]
0x18002acf5  test    eax, eax
0x18002acf7  js      short loc_18002AD1C
0x18002acf9  mov     ebx, [rsp+310h+ExitCode]
0x18002acfd  test    ebx, ebx
0x18002acff  jz      short loc_18002AD1C
0x18002ad01  jle     short loc_18002AD0C
0x18002ad03  movzx   ebx, bx
0x18002ad06  or      ebx, 80070000h
0x18002ad0c  mov     ecx, ebx
0x18002ad0e  call    StatusFromHResult
0x18002ad13  lea     r8, aProcessExitedD; "Process exited due to failure"
0x18002ad1a  jmp     short loc_18002AD35
0x18002ad1c  mov     ebx, eax
0x18002ad1e  jmp     short loc_18002AD76
0x18002ad20  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002ad25  mov     ecx, eax
0x18002ad27  mov     ebx, eax
0x18002ad29  call    StatusFromHResult
0x18002ad2e  lea     r8, aGetexitcodepro; "GetExitCodeProcess failed"
0x18002ad35  xor     r9d, r9d; unsigned __int16 *
0x18002ad38  mov     [rsp+310h+var_2E0], ebx; unsigned int
0x18002ad3c  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002ad43  mov     dword ptr [rsp+310h+var_2E8], eax; unsigned int
0x18002ad47  mov     rdx, r13; unsigned __int16 *
0x18002ad4a  mov     [rsp+310h+var_2F0], 0; unsigned __int16 *
0x18002ad53  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002ad58  jmp     short loc_18002AD76
0x18002ad5a  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002ad5f  mov     ecx, eax
0x18002ad61  mov     ebx, eax
0x18002ad63  call    StatusFromHResult
0x18002ad68  lea     r8, aWaitforntprint; "WaitForNtPrintProcessToExit failed"
0x18002ad6f  jmp     short loc_18002AD35
0x18002ad71  mov     rsi, [rsp+310h+var_2C8]
0x18002ad76  mov     rcx, [rbp+210h+pExecInfo.hProcess]; hObject
0x18002ad7a  test    rcx, rcx
0x18002ad7d  jz      short loc_18002ADDA
0x18002ad7f  call    cs:__imp_CloseHandle
0x18002ad85  test    eax, eax
0x18002ad87  jnz     short loc_18002ADD2
0x18002ad89  call    cs:__imp_GetLastError
0x18002ad8f  mov     edi, eax
0x18002ad91  test    eax, eax
0x18002ad93  jle     short loc_18002AD9E
0x18002ad95  movzx   edi, ax
0x18002ad98  or      edi, 80070000h
0x18002ad9e  call    cs:__imp_GetLastError
0x18002ada4  mov     [rsp+310h+var_2E0], edi; unsigned int
0x18002ada8  lea     r9, aClosehandleSei; "CloseHandle(sei.hProcess)"
0x18002adaf  mov     dword ptr [rsp+310h+var_2E8], eax; unsigned int
0x18002adb3  lea     r8, aClosehandleFai; "CloseHandle failed"
0x18002adba  mov     rdx, r13; unsigned __int16 *
0x18002adbd  mov     [rsp+310h+var_2F0], 0; unsigned __int16 *
0x18002adc6  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002adcd  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002add2  mov     [rbp+210h+pExecInfo.hProcess], 0
0x18002adda  lea     rdx, [rsp+310h+var_2B8]; void **
0x18002addf  lea     rcx, [rsp+310h+var_2C0]; void **
0x18002ade4  call    ?FreeSharedMemory@@YAXPEAPEAX0@Z; FreeSharedMemory(void * *,void * *)
0x18002ade9  test    rsi, rsi
0x18002adec  jz      short loc_18002ADF7
0x18002adee  mov     rcx, rsi; hMem
0x18002adf1  call    cs:__imp_LocalFree
0x18002adf7  mov     eax, ebx
0x18002adf9  mov     rcx, [rbp+210h+var_30]
0x18002ae00  xor     rcx, rsp; StackCookie
0x18002ae03  call    __security_check_cookie
0x18002ae08  lea     r11, [rsp+310h+var_20]
0x18002ae10  mov     rbx, [r11+40h]
0x18002ae14  mov     rsi, [r11+48h]
0x18002ae18  mov     rsp, r11
0x18002ae1b  pop     r15
0x18002ae1d  pop     r14
0x18002ae1f  pop     r13
0x18002ae21  pop     rdi
0x18002ae22  pop     rbp
0x18002ae23  retn
```
