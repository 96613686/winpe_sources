# PSetupElevateAndCallDriverStoreAddDriverPackage(HWND__ *,ushort const *,ulong,ushort,ushort *,ulong *)

- ea: `0x18002b960`
- end: `0x18002bce8`
- name: `?PSetupElevateAndCallDriverStoreAddDriverPackage@@YAJPEAUHWND__@@PEBGKGPEAGPEAK@Z`
- size: `904`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned __int16@<r9w>, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000b200`
- `0x18000c368`
- `0x18002a30c`
- `0x18002a5ac`
- `0x18002b6f0`
- `0x18002b960`
- `0x18002c440`
- `0x180035208`
- `0x180036470`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc3f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002bb5e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002bb5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bcb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bcb6`
- `SHELL32!ShellExecuteExW` at `0x18002bb12`
- `SHELL32!ShellExecuteExW` at `0x18002bb12`

## string_xrefs

- `0x18002bbd2`: `PSetupElevateAndCallDriverStoreAddDriverPackage`
- `0x18002bc5b`: `PSetupElevateAndCallDriverStoreAddDriverPackage`
- `0x18002ba55`: `PSetupElevatedDriverStoreAddDriverPackageW `

## pseudocode

```c
__int64 __fastcall PSetupElevateAndCallDriverStoreAddDriverPackage(
        HWND a1,
        const unsigned __int16 *a2,
        char a3,
        unsigned __int16 a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  unsigned __int16 *v10; // rsi
  int v12; // ebx
  unsigned __int16 *v13; // rdi
  int v14; // eax
  NCoreLibrary *v15; // rcx
  int LastErrorAsFailHR; // eax
  unsigned int v17; // eax
  const unsigned __int16 *v18; // r9
  const unsigned __int16 *v19; // r8
  NCoreLibrary *v20; // rcx
  NCoreLibrary *v21; // rcx
  bool v22; // sf
  signed int LastError; // eax
  unsigned int v24; // edi
  DWORD v25; // eax
  HLOCAL v26; // rdi
  DWORD ExitCode; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v28; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v29; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  void *v31; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v32; // [rsp+68h] [rbp-98h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v34[264]; // [rsp+E0h] [rbp-20h] BYREF

  v32 = a5;
  memset_0(v34, 0, 0x208u);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v10 = 0;
  v28 = 0;
  ExitCode = 0;
  v31 = 0;
  v29 = 0;
  hMem = 0;
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
    return 2147943660LL;
  if ( !a2 || !a5 || !a6 || *a6 < 0x104 || (a3 & 1) != 0 )
  {
    v12 = -2147024809;
    goto LABEL_32;
  }
  v12 = CheckLUAAndInitialize(
          L"PSetupElevatedDriverStoreAddDriverPackageW ",
          0x41Cu,
          &v31,
          (void **)&v29,
          (unsigned __int16 **)&v28,
          v34);
  if ( v12 < 0
    || (v13 = v29,
        memset_0(v29, 0, 0x41Cu),
        v13[260] = a4,
        *((_DWORD *)v13 + 261) = *a6,
        v12 = StringCchCopyW(v13, 0x104u, a2),
        v12 < 0) )
  {
    v10 = (unsigned __int16 *)v28;
    goto LABEL_32;
  }
  v14 = CheckForNetworkPathAndCopyToLocalDriveIfRequired(a4, a1, v13, (unsigned __int16 **)&hMem);
  v10 = (unsigned __int16 *)v28;
  v12 = v14;
  if ( v14 >= 0 )
  {
    pExecInfo.cbSize = 112;
    pExecInfo.lpFile = v34;
    pExecInfo.fMask = 64;
    pExecInfo.lpDirectory = &qword_18003C420;
    pExecInfo.lpVerb = L"runas";
    pExecInfo.hwnd = a1;
    pExecInfo.lpParameters = (LPCWSTR)v28;
    pExecInfo.nShow = 1;
    if ( !ShellExecuteExW(&pExecInfo) || pExecInfo.hInstApp <= HINSTANCE_ERROR )
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v15);
      v12 = LastErrorAsFailHR;
      if ( LastErrorAsFailHR < 0 )
      {
        v17 = StatusFromHResult((unsigned int)LastErrorAsFailHR);
        v18 = v10;
        v19 = L"ShellExecuteEx failed";
LABEL_28:
        SplLogPrinterSetupGenericEvent(
          &SETUP_PRINTER_OPERATION_FAILED,
          L"PSetupElevateAndCallDriverStoreAddDriverPackage",
          v19,
          v18,
          0,
          v17,
          v12);
        goto LABEL_32;
      }
    }
    if ( (unsigned int)WaitForNtPrintProcessToExit(pExecInfo.hProcess) )
    {
      v12 = NCoreLibrary::GetLastErrorAsFailHR(v20);
      v17 = StatusFromHResult((unsigned int)v12);
      v19 = L"WaitForNtPrintProcessToExit failed";
    }
    else
    {
      if ( GetExitCodeProcess(pExecInfo.hProcess, &ExitCode) )
      {
        if ( *((int *)v13 + 262) >= 0 && (v12 = ExitCode, v22 = (ExitCode & 0x80000000) != 0, ExitCode) )
        {
          if ( (int)ExitCode <= 0 )
          {
LABEL_23:
            if ( !v22 )
            {
              v12 = StringCchCopyW(v32, 0x104u, v13 + 261);
              if ( v12 >= 0 )
                *a6 = *((_DWORD *)v13 + 261);
            }
            goto LABEL_32;
          }
          v12 = (unsigned __int16)ExitCode | 0x80070000;
        }
        else
        {
          v12 = *((_DWORD *)v13 + 262);
        }
        v22 = v12 < 0;
        goto LABEL_23;
      }
      v12 = NCoreLibrary::GetLastErrorAsFailHR(v21);
      v17 = StatusFromHResult((unsigned int)v12);
      v19 = L"GetExitCodeProcess failed";
    }
    v18 = 0;
    goto LABEL_28;
  }
LABEL_32:
  if ( pExecInfo.hProcess )
  {
    if ( !CloseHandle(pExecInfo.hProcess) )
    {
      LastError = GetLastError();
      v24 = LastError;
      if ( LastError > 0 )
        v24 = (unsigned __int16)LastError | 0x80070000;
      v25 = GetLastError();
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"PSetupElevateAndCallDriverStoreAddDriverPackage",
        L"CloseHandle failed",
        L"CloseHandle(sei.hProcess)",
        0,
        v25,
        v24);
    }
    pExecInfo.hProcess = 0;
  }
  v26 = hMem;
  if ( hMem )
  {
    RecursivelyDeleteDirectory((const WCHAR *)hMem, 5);
    LocalFree(v26);
  }
  FreeSharedMemory((void **)&v29, &v31);
  if ( v10 )
    LocalFree(v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002b960  mov     [rsp-8+arg_10], rbx
0x18002b965  push    rbp
0x18002b966  push    rsi
0x18002b967  push    rdi
0x18002b968  push    r12
0x18002b96a  push    r13
0x18002b96c  push    r14
0x18002b96e  push    r15
0x18002b970  lea     rbp, [rsp-200h]
0x18002b978  sub     rsp, 300h
0x18002b97f  mov     rax, cs:__security_cookie
0x18002b986  xor     rax, rsp
0x18002b989  mov     [rbp+230h+var_40], rax
0x18002b990  mov     rdi, [rbp+230h+arg_20]
0x18002b997  mov     ebx, r8d
0x18002b99a  mov     r14, [rbp+230h+arg_28]
0x18002b9a1  mov     r15, rdx
0x18002b9a4  mov     r12, rcx
0x18002b9a7  mov     [rsp+330h+var_2C8], rdi
0x18002b9ac  xor     edx, edx; Val
0x18002b9ae  lea     rcx, [rbp+230h+var_250]; void *
0x18002b9b2  mov     r8d, 208h; Size
0x18002b9b8  movzx   r13d, r9w
0x18002b9bc  call    memset_0
0x18002b9c1  xor     edx, edx; Val
0x18002b9c3  lea     rcx, [rsp+330h+pExecInfo]; void *
0x18002b9c8  lea     r8d, [rdx+70h]; Size
0x18002b9cc  call    memset_0
0x18002b9d1  xor     eax, eax
0x18002b9d3  mov     esi, eax
0x18002b9d5  mov     [rsp+330h+var_2E8], rax
0x18002b9da  mov     [rsp+330h+ExitCode], eax
0x18002b9de  mov     [rsp+330h+var_2D0], rax
0x18002b9e3  mov     [rsp+330h+var_2E0], rax
0x18002b9e8  mov     [rsp+330h+hMem], rax
0x18002b9ed  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x18002b9f2  test    al, al
0x18002b9f4  jz      short loc_18002BA00
0x18002b9f6  mov     eax, 800704ECh
0x18002b9fb  jmp     loc_18002BCBE
0x18002ba00  test    r15, r15
0x18002ba03  jz      loc_18002BC12
0x18002ba09  test    rdi, rdi
0x18002ba0c  jz      loc_18002BC12
0x18002ba12  test    r14, r14
0x18002ba15  jz      loc_18002BC12
0x18002ba1b  cmp     dword ptr [r14], 104h
0x18002ba22  jb      loc_18002BC12
0x18002ba28  test    bl, 1
0x18002ba2b  jnz     loc_18002BC12
0x18002ba31  lea     rax, [rbp+230h+var_250]
0x18002ba35  mov     edi, 41Ch
0x18002ba3a  mov     [rsp+330h+var_308], rax; unsigned __int16 *
0x18002ba3f  lea     r9, [rsp+330h+var_2E0]; void **
0x18002ba44  lea     rax, [rsp+330h+var_2E8]
0x18002ba49  mov     edx, edi; unsigned __int64
0x18002ba4b  lea     r8, [rsp+330h+var_2D0]; void **
0x18002ba50  mov     [rsp+330h+var_310], rax; unsigned __int16 **
0x18002ba55  lea     rcx, aPsetupelevated_9; "PSetupElevatedDriverStoreAddDriverPacka"...
0x18002ba5c  call    ?CheckLUAAndInitialize@@YAJPEBG_KPEAPEAX2PEAPEAGQEAG@Z; CheckLUAAndInitialize(ushort const *,unsigned __int64,void * *,void * *,ushort * *,ushort * const)
0x18002ba61  mov     ebx, eax
0x18002ba63  test    eax, eax
0x18002ba65  js      loc_18002BC0B
0x18002ba6b  mov     r8d, edi; Size
0x18002ba6e  xor     edx, edx; Val
0x18002ba70  mov     rdi, [rsp+330h+var_2E0]
0x18002ba75  mov     rcx, rdi; void *
0x18002ba78  call    memset_0
0x18002ba7d  mov     [rdi+208h], r13w
0x18002ba85  mov     r8, r15; unsigned __int16 *
0x18002ba88  mov     eax, [r14]
0x18002ba8b  mov     r15d, 104h
0x18002ba91  mov     edx, r15d; unsigned __int64
0x18002ba94  mov     [rdi+414h], eax
0x18002ba9a  mov     rcx, rdi; unsigned __int16 *
0x18002ba9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002baa2  mov     ebx, eax
0x18002baa4  test    eax, eax
0x18002baa6  js      loc_18002BC0B
0x18002baac  lea     r9, [rsp+330h+hMem]; unsigned __int16 **
0x18002bab1  mov     r8, rdi; unsigned __int16 *
0x18002bab4  mov     rdx, r12; HWND
0x18002bab7  movzx   ecx, r13w; unsigned __int16
0x18002babb  call    ?CheckForNetworkPathAndCopyToLocalDriveIfRequired@@YAJGPEAUHWND__@@QEAGPEAPEAG@Z; CheckForNetworkPathAndCopyToLocalDriveIfRequired(ushort,HWND__ *,ushort * const,ushort * *)
0x18002bac0  mov     rsi, [rsp+330h+var_2E8]
0x18002bac5  mov     ebx, eax
0x18002bac7  test    eax, eax
0x18002bac9  js      loc_18002BC17
0x18002bacf  lea     rax, [rbp+230h+var_250]
0x18002bad3  mov     [rsp+330h+pExecInfo.cbSize], 70h ; 'p'
0x18002badb  mov     [rbp+230h+pExecInfo.lpFile], rax
0x18002badf  lea     rcx, [rsp+330h+pExecInfo]; pExecInfo
0x18002bae4  lea     rax, qword_18003C420
0x18002baeb  mov     [rsp+330h+pExecInfo.fMask], 40h ; '@'
0x18002baf3  mov     [rbp+230h+pExecInfo.lpDirectory], rax
0x18002baf7  lea     rax, aRunas; "runas"
0x18002bafe  mov     [rbp+230h+pExecInfo.lpVerb], rax
0x18002bb02  mov     [rsp+330h+pExecInfo.hwnd], r12
0x18002bb07  mov     [rbp+230h+pExecInfo.lpParameters], rsi
0x18002bb0b  mov     [rbp+230h+pExecInfo.nShow], 1
0x18002bb12  call    cs:__imp_ShellExecuteExW
0x18002bb18  test    eax, eax
0x18002bb1a  jz      short loc_18002BB23
0x18002bb1c  cmp     [rbp+230h+pExecInfo.hInstApp], 20h ; ' '
0x18002bb21  ja      short loc_18002BB44
0x18002bb23  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002bb28  mov     ebx, eax
0x18002bb2a  test    eax, eax
0x18002bb2c  jns     short loc_18002BB44
0x18002bb2e  mov     ecx, eax
0x18002bb30  call    StatusFromHResult
0x18002bb35  mov     r9, rsi
0x18002bb38  lea     r8, aShellexecuteex; "ShellExecuteEx failed"
0x18002bb3f  jmp     loc_18002BBCE
0x18002bb44  mov     rcx, [rbp+230h+pExecInfo.hProcess]; void *
0x18002bb48  call    ?WaitForNtPrintProcessToExit@@YAJPEAX@Z; WaitForNtPrintProcessToExit(void *)
0x18002bb4d  test    eax, eax
0x18002bb4f  jnz     loc_18002BBF4
0x18002bb55  mov     rcx, [rbp+230h+pExecInfo.hProcess]; hProcess
0x18002bb59  lea     rdx, [rsp+330h+ExitCode]; lpExitCode
0x18002bb5e  call    cs:__imp_GetExitCodeProcess
0x18002bb64  test    eax, eax
0x18002bb66  jz      short loc_18002BBB6
0x18002bb68  mov     eax, [rdi+418h]
0x18002bb6e  test    eax, eax
0x18002bb70  js      short loc_18002BB87
0x18002bb72  mov     ebx, [rsp+330h+ExitCode]
0x18002bb76  test    ebx, ebx
0x18002bb78  jz      short loc_18002BB87
0x18002bb7a  jle     short loc_18002BB8B
0x18002bb7c  movzx   ebx, bx
0x18002bb7f  or      ebx, 80070000h
0x18002bb85  jmp     short loc_18002BB89
0x18002bb87  mov     ebx, eax
0x18002bb89  test    ebx, ebx
0x18002bb8b  js      loc_18002BC17
0x18002bb91  mov     rcx, [rsp+330h+var_2C8]; unsigned __int16 *
0x18002bb96  lea     r8, [rdi+20Ah]; unsigned __int16 *
0x18002bb9d  mov     rdx, r15; unsigned __int64
0x18002bba0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bba5  mov     ebx, eax
0x18002bba7  test    eax, eax
0x18002bba9  js      short loc_18002BC17
0x18002bbab  mov     eax, [rdi+414h]
0x18002bbb1  mov     [r14], eax
0x18002bbb4  jmp     short loc_18002BC17
0x18002bbb6  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002bbbb  mov     ecx, eax
0x18002bbbd  mov     ebx, eax
0x18002bbbf  call    StatusFromHResult
0x18002bbc4  lea     r8, aGetexitcodepro; "GetExitCodeProcess failed"
0x18002bbcb  xor     r9d, r9d; unsigned __int16 *
0x18002bbce  mov     [rsp+330h+var_300], ebx; unsigned int
0x18002bbd2  lea     rdx, aPsetupelevatea_0; "PSetupElevateAndCallDriverStoreAddDrive"...
0x18002bbd9  mov     dword ptr [rsp+330h+var_308], eax; unsigned int
0x18002bbdd  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002bbe4  mov     [rsp+330h+var_310], 0; unsigned __int16 *
0x18002bbed  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002bbf2  jmp     short loc_18002BC17
0x18002bbf4  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002bbf9  mov     ecx, eax
0x18002bbfb  mov     ebx, eax
0x18002bbfd  call    StatusFromHResult
0x18002bc02  lea     r8, aWaitforntprint; "WaitForNtPrintProcessToExit failed"
0x18002bc09  jmp     short loc_18002BBCB
0x18002bc0b  mov     rsi, [rsp+330h+var_2E8]
0x18002bc10  jmp     short loc_18002BC17
0x18002bc12  mov     ebx, 80070057h
0x18002bc17  mov     rcx, [rbp+230h+pExecInfo.hProcess]; hObject
0x18002bc1b  test    rcx, rcx
0x18002bc1e  jz      short loc_18002BC7F
0x18002bc20  call    cs:__imp_CloseHandle
0x18002bc26  test    eax, eax
0x18002bc28  jnz     short loc_18002BC77
0x18002bc2a  call    cs:__imp_GetLastError
0x18002bc30  mov     edi, eax
0x18002bc32  test    eax, eax
0x18002bc34  jle     short loc_18002BC3F
0x18002bc36  movzx   edi, ax
0x18002bc39  or      edi, 80070000h
0x18002bc3f  call    cs:__imp_GetLastError
0x18002bc45  mov     [rsp+330h+var_300], edi; unsigned int
0x18002bc49  lea     r9, aClosehandleSei; "CloseHandle(sei.hProcess)"
0x18002bc50  mov     dword ptr [rsp+330h+var_308], eax; unsigned int
0x18002bc54  lea     r8, aClosehandleFai; "CloseHandle failed"
0x18002bc5b  lea     rdx, aPsetupelevatea_0; "PSetupElevateAndCallDriverStoreAddDrive"...
0x18002bc62  mov     [rsp+330h+var_310], 0; unsigned __int16 *
0x18002bc6b  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002bc72  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002bc77  mov     [rbp+230h+pExecInfo.hProcess], 0
0x18002bc7f  mov     rdi, [rsp+330h+hMem]
0x18002bc84  test    rdi, rdi
0x18002bc87  jz      short loc_18002BC9F
0x18002bc89  mov     edx, 5
0x18002bc8e  mov     rcx, rdi
0x18002bc91  call    RecursivelyDeleteDirectory
0x18002bc96  mov     rcx, rdi; hMem
0x18002bc99  call    cs:__imp_LocalFree
0x18002bc9f  lea     rdx, [rsp+330h+var_2D0]; void **
0x18002bca4  lea     rcx, [rsp+330h+var_2E0]; void **
0x18002bca9  call    ?FreeSharedMemory@@YAXPEAPEAX0@Z; FreeSharedMemory(void * *,void * *)
0x18002bcae  test    rsi, rsi
0x18002bcb1  jz      short loc_18002BCBC
0x18002bcb3  mov     rcx, rsi; hMem
0x18002bcb6  call    cs:__imp_LocalFree
0x18002bcbc  mov     eax, ebx
0x18002bcbe  mov     rcx, [rbp+230h+var_40]
0x18002bcc5  xor     rcx, rsp; StackCookie
0x18002bcc8  call    __security_check_cookie
0x18002bccd  mov     rbx, [rsp+330h+arg_10]
0x18002bcd5  add     rsp, 300h
0x18002bcdc  pop     r15
0x18002bcde  pop     r14
0x18002bce0  pop     r13
0x18002bce2  pop     r12
0x18002bce4  pop     rdi
0x18002bce5  pop     rsi
0x18002bce6  pop     rbp
0x18002bce7  retn
```
