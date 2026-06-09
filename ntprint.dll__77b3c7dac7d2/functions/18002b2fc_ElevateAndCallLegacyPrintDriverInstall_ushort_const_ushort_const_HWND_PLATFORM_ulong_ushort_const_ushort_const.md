# ElevateAndCallLegacyPrintDriverInstall(ushort const *,ushort const *,HWND__ *,PLATFORM,ulong,ushort const *,ushort const *,ulong,ulong,ulong *)

- ea: `0x18002b2fc`
- end: `0x18002b6e9`
- name: `?ElevateAndCallLegacyPrintDriverInstall@@YAKPEBG0PEAUHWND__@@W4PLATFORM@@K00KKPEAK@Z`
- size: `1005`
- prototype: `unsigned int __high(const unsigned __int16 *, const unsigned __int16 *, HWND, enum PLATFORM, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b7ec`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000b200`
- `0x18002a30c`
- `0x18002a5ac`
- `0x18002b2fc`
- `0x18002b6f0`
- `0x18002c440`
- `0x180035208`
- `0x180036470`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b639`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002b578`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002b578`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b61a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b61a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b693`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b6b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b693`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b6b2`
- `SHELL32!ShellExecuteExW` at `0x18002b52d`
- `SHELL32!ShellExecuteExW` at `0x18002b52d`

## string_xrefs

- `0x18002b5d3`: `ElevateAndCallLegacyPrintDriverInstall`
- `0x18002b655`: `ElevateAndCallLegacyPrintDriverInstall`
- `0x18002b3db`: `PSetupElevatedLegacyPrintDriverInstallW `

## pseudocode

```c
__int64 __fastcall ElevateAndCallLegacyPrintDriverInstall(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        HWND a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        int a9,
        _DWORD *a10)
{
  signed int v14; // ebx
  void *v15; // rdi
  unsigned __int16 *v16; // r11
  int v17; // esi
  int v18; // esi
  unsigned __int16 v19; // ax
  NCoreLibrary *v20; // rcx
  int LastErrorAsFailHR; // eax
  unsigned int v22; // eax
  const unsigned __int16 *v23; // r9
  const unsigned __int16 *v24; // r8
  NCoreLibrary *v25; // rcx
  NCoreLibrary *v26; // rcx
  signed int LastError; // eax
  unsigned int v28; // edi
  DWORD v29; // eax
  HLOCAL v30; // rdi
  DWORD ExitCode; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v33; // [rsp+48h] [rbp-B8h] BYREF
  void *v34; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  void *v36; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v37; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v38; // [rsp+70h] [rbp-90h]
  _DWORD *v39; // [rsp+78h] [rbp-88h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v41[264]; // [rsp+F0h] [rbp-10h] BYREF

  v38 = a7;
  v37 = a1;
  v39 = a10;
  memset_0(v41, 0, 0x208u);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v33 = 0;
  ExitCode = 0;
  v36 = 0;
  v34 = 0;
  hMem = 0;
  if ( !a1 || !a2 || (a8 & 8) != 0 )
    goto LABEL_35;
  v14 = CheckLUAAndInitialize(
          L"PSetupElevatedLegacyPrintDriverInstallW ",
          0x658u,
          &v36,
          &v34,
          (unsigned __int16 **)&v33,
          v41);
  if ( v14 < 0 )
    goto LABEL_36;
  v15 = v34;
  memset_0(v34, 0, 0x658u);
  v14 = StringCchCopyW((unsigned __int16 *)v15 + 545, 0x104u, v37);
  if ( v14 < 0 )
    goto LABEL_36;
  v14 = StringCchCopyW((unsigned __int16 *)v15 + 12, 0xFFu, a2);
  if ( v14 < 0 )
    goto LABEL_36;
  if ( a6 )
  {
    v14 = StringCchCopyW((unsigned __int16 *)v15 + 527, 0x12u, a6);
    if ( v14 < 0 )
      goto LABEL_36;
  }
  if ( v38 )
  {
    v14 = StringCchCopyW((unsigned __int16 *)v15 + 267, 0x104u, v38);
    if ( v14 < 0 )
      goto LABEL_36;
  }
  *(_QWORD *)v15 = a3;
  *((_DWORD *)v15 + 2) = a4;
  *((_DWORD *)v15 + 3) = a5;
  *((_DWORD *)v15 + 4) = a8;
  *((_DWORD *)v15 + 5) = a9;
  v17 = a4 - 1;
  if ( v17 )
  {
    v18 = v17 - 4;
    if ( v18 )
    {
      if ( v18 == 2 )
      {
        v19 = 9;
        goto LABEL_17;
      }
LABEL_35:
      v14 = -2147024809;
      goto LABEL_36;
    }
    v19 = 6;
  }
  else
  {
    v19 = 0;
  }
LABEL_17:
  v14 = CheckForNetworkPathAndCopyToLocalDriveIfRequired(v19, a3, v16, (unsigned __int16 **)&hMem);
  if ( v14 < 0 )
    goto LABEL_36;
  pExecInfo.cbSize = 112;
  pExecInfo.lpFile = v41;
  pExecInfo.lpParameters = (LPCWSTR)v33;
  pExecInfo.lpDirectory = &qword_18003C420;
  pExecInfo.lpVerb = L"runas";
  pExecInfo.fMask = 64;
  pExecInfo.hwnd = a3;
  pExecInfo.nShow = 1;
  if ( !ShellExecuteExW(&pExecInfo) || pExecInfo.hInstApp <= HINSTANCE_ERROR )
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v20);
    v14 = LastErrorAsFailHR;
    if ( LastErrorAsFailHR < 0 )
    {
      v22 = StatusFromHResult((unsigned int)LastErrorAsFailHR);
      v23 = (const unsigned __int16 *)v33;
      v24 = L"ShellExecuteEx failed";
LABEL_33:
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"ElevateAndCallLegacyPrintDriverInstall",
        v24,
        v23,
        0,
        v22,
        v14);
      goto LABEL_36;
    }
  }
  if ( (unsigned int)WaitForNtPrintProcessToExit(pExecInfo.hProcess) )
  {
    v14 = NCoreLibrary::GetLastErrorAsFailHR(v25);
    v22 = StatusFromHResult((unsigned int)v14);
    v24 = L"WaitForNtPrintProcessToExit failed";
    goto LABEL_32;
  }
  if ( !GetExitCodeProcess(pExecInfo.hProcess, &ExitCode) )
  {
    v14 = NCoreLibrary::GetLastErrorAsFailHR(v26);
    v22 = StatusFromHResult((unsigned int)v14);
    v24 = L"GetExitCodeProcess failed";
LABEL_32:
    v23 = 0;
    goto LABEL_33;
  }
  if ( *((int *)v15 + 404) >= 0 && (v14 = ExitCode) != 0 )
  {
    if ( (int)ExitCode > 0 )
      v14 = (unsigned __int16)ExitCode | 0x80070000;
  }
  else
  {
    v14 = *((_DWORD *)v15 + 404);
  }
  if ( v39 )
    *v39 = *((_DWORD *)v15 + 403);
LABEL_36:
  if ( pExecInfo.hProcess )
  {
    if ( !CloseHandle(pExecInfo.hProcess) )
    {
      LastError = GetLastError();
      v28 = LastError;
      if ( LastError > 0 )
        v28 = (unsigned __int16)LastError | 0x80070000;
      v29 = GetLastError();
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"ElevateAndCallLegacyPrintDriverInstall",
        L"CloseHandle failed",
        L"CloseHandle(sei.hProcess)",
        0,
        v29,
        v28);
    }
    pExecInfo.hProcess = 0;
  }
  v30 = hMem;
  if ( hMem )
  {
    RecursivelyDeleteDirectory((const WCHAR *)hMem, 5);
    LocalFree(v30);
  }
  FreeSharedMemory(&v34, &v36);
  if ( v33 )
    LocalFree(v33);
  return StatusFromHResult((unsigned int)v14);
}

```

## disassembly

```asm
0x18002b2fc  mov     [rsp-8+arg_18], rbx
0x18002b301  push    rbp
0x18002b302  push    rsi
0x18002b303  push    rdi
0x18002b304  push    r12
0x18002b306  push    r13
0x18002b308  push    r14
0x18002b30a  push    r15
0x18002b30c  lea     rbp, [rsp-210h]
0x18002b314  sub     rsp, 310h
0x18002b31b  mov     rax, cs:__security_cookie
0x18002b322  xor     rax, rsp
0x18002b325  mov     [rbp+240h+var_40], rax
0x18002b32c  mov     rax, [rbp+240h+arg_30]
0x18002b333  mov     r12, r8
0x18002b336  mov     r13, [rbp+240h+arg_28]
0x18002b33d  mov     r15, rdx
0x18002b340  mov     [rsp+340h+var_2D0], rax
0x18002b345  mov     rbx, rcx
0x18002b348  mov     rax, [rbp+240h+arg_48]
0x18002b34f  xor     edx, edx; Val
0x18002b351  mov     [rsp+340h+var_2D8], rcx
0x18002b356  mov     r8d, 208h; Size
0x18002b35c  lea     rcx, [rbp+240h+var_250]; void *
0x18002b360  mov     [rsp+340h+var_2C8], rax
0x18002b365  mov     esi, r9d
0x18002b368  call    memset_0
0x18002b36d  xor     edx, edx; Val
0x18002b36f  lea     rcx, [rbp+240h+pExecInfo]; void *
0x18002b373  lea     r8d, [rdx+70h]; Size
0x18002b377  call    memset_0
0x18002b37c  xor     edi, edi
0x18002b37e  mov     [rsp+340h+var_2F8], rdi
0x18002b383  mov     [rsp+340h+ExitCode], edi
0x18002b387  mov     [rsp+340h+var_2E0], rdi
0x18002b38c  mov     [rsp+340h+var_2F0], rdi
0x18002b391  mov     [rsp+340h+hMem], rdi
0x18002b396  test    rbx, rbx
0x18002b399  jz      loc_18002B60C
0x18002b39f  test    r15, r15
0x18002b3a2  jz      loc_18002B60C
0x18002b3a8  mov     r14d, [rbp+240h+arg_38]
0x18002b3af  test    r14b, 8
0x18002b3b3  jnz     loc_18002B60C
0x18002b3b9  lea     rax, [rbp+240h+var_250]
0x18002b3bd  mov     edx, 658h; unsigned __int64
0x18002b3c2  mov     [rsp+340h+var_318], rax; unsigned __int16 *
0x18002b3c7  lea     r9, [rsp+340h+var_2F0]; void **
0x18002b3cc  lea     rax, [rsp+340h+var_2F8]
0x18002b3d1  lea     r8, [rsp+340h+var_2E0]; void **
0x18002b3d6  mov     [rsp+340h+var_320], rax; unsigned __int16 **
0x18002b3db  lea     rcx, aPsetupelevated_8; "PSetupElevatedLegacyPrintDriverInstallW"...
0x18002b3e2  call    ?CheckLUAAndInitialize@@YAJPEBG_KPEAPEAX2PEAPEAGQEAG@Z; CheckLUAAndInitialize(ushort const *,unsigned __int64,void * *,void * *,ushort * *,ushort * const)
0x18002b3e7  mov     ebx, eax
0x18002b3e9  test    eax, eax
0x18002b3eb  js      loc_18002B611
0x18002b3f1  mov     rdi, [rsp+340h+var_2F0]
0x18002b3f6  xor     edx, edx; Val
0x18002b3f8  mov     rcx, rdi; void *
0x18002b3fb  mov     r8d, 658h; Size
0x18002b401  call    memset_0
0x18002b406  mov     r8, [rsp+340h+var_2D8]; unsigned __int16 *
0x18002b40b  lea     r11, [rdi+442h]
0x18002b412  mov     rcx, r11; unsigned __int16 *
0x18002b415  mov     edx, 104h; unsigned __int64
0x18002b41a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b41f  mov     ebx, eax
0x18002b421  test    eax, eax
0x18002b423  js      loc_18002B611
0x18002b429  lea     rcx, [rdi+18h]; unsigned __int16 *
0x18002b42d  mov     r8, r15; unsigned __int16 *
0x18002b430  mov     edx, 0FFh; unsigned __int64
0x18002b435  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b43a  mov     ebx, eax
0x18002b43c  test    eax, eax
0x18002b43e  js      loc_18002B611
0x18002b444  test    r13, r13
0x18002b447  jz      short loc_18002B467
0x18002b449  lea     rcx, [rdi+41Eh]; unsigned __int16 *
0x18002b450  mov     r8, r13; unsigned __int16 *
0x18002b453  mov     edx, 12h; unsigned __int64
0x18002b458  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b45d  mov     ebx, eax
0x18002b45f  test    eax, eax
0x18002b461  js      loc_18002B611
0x18002b467  mov     rax, [rsp+340h+var_2D0]
0x18002b46c  test    rax, rax
0x18002b46f  jz      short loc_18002B48F
0x18002b471  lea     rcx, [rdi+216h]; unsigned __int16 *
0x18002b478  mov     r8, rax; unsigned __int16 *
0x18002b47b  mov     edx, 104h; unsigned __int64
0x18002b480  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b485  mov     ebx, eax
0x18002b487  test    eax, eax
0x18002b489  js      loc_18002B611
0x18002b48f  mov     eax, [rbp+240h+arg_20]
0x18002b495  mov     [rdi], r12
0x18002b498  mov     [rdi+8], esi
0x18002b49b  mov     [rdi+0Ch], eax
0x18002b49e  mov     eax, [rbp+240h+arg_40]
0x18002b4a4  mov     [rdi+10h], r14d
0x18002b4a8  mov     [rdi+14h], eax
0x18002b4ab  sub     esi, 1
0x18002b4ae  jz      short loc_18002B4CA
0x18002b4b0  sub     esi, 4
0x18002b4b3  jz      short loc_18002B4C3
0x18002b4b5  cmp     esi, 2
0x18002b4b8  jnz     loc_18002B60C
0x18002b4be  lea     eax, [rsi+7]
0x18002b4c1  jmp     short loc_18002B4CC
0x18002b4c3  mov     eax, 6
0x18002b4c8  jmp     short loc_18002B4CC
0x18002b4ca  xor     eax, eax
0x18002b4cc  lea     r9, [rsp+340h+hMem]; unsigned __int16 **
0x18002b4d1  mov     r8, r11; unsigned __int16 *
0x18002b4d4  mov     rdx, r12; HWND
0x18002b4d7  movzx   ecx, ax; unsigned __int16
0x18002b4da  call    ?CheckForNetworkPathAndCopyToLocalDriveIfRequired@@YAJGPEAUHWND__@@QEAGPEAPEAG@Z; CheckForNetworkPathAndCopyToLocalDriveIfRequired(ushort,HWND__ *,ushort * const,ushort * *)
0x18002b4df  mov     ebx, eax
0x18002b4e1  test    eax, eax
0x18002b4e3  js      loc_18002B611
0x18002b4e9  lea     rax, [rbp+240h+var_250]
0x18002b4ed  mov     [rbp+240h+pExecInfo.cbSize], 70h ; 'p'
0x18002b4f4  mov     [rbp+240h+pExecInfo.lpFile], rax
0x18002b4f8  lea     rcx, [rbp+240h+pExecInfo]; pExecInfo
0x18002b4fc  mov     rax, [rsp+340h+var_2F8]
0x18002b501  mov     [rbp+240h+pExecInfo.lpParameters], rax
0x18002b505  lea     rax, qword_18003C420
0x18002b50c  mov     [rbp+240h+pExecInfo.lpDirectory], rax
0x18002b510  lea     rax, aRunas; "runas"
0x18002b517  mov     [rbp+240h+pExecInfo.lpVerb], rax
0x18002b51b  mov     [rbp+240h+pExecInfo.fMask], 40h ; '@'
0x18002b522  mov     [rbp+240h+pExecInfo.hwnd], r12
0x18002b526  mov     [rbp+240h+pExecInfo.nShow], 1
0x18002b52d  call    cs:__imp_ShellExecuteExW
0x18002b533  test    eax, eax
0x18002b535  jz      short loc_18002B53E
0x18002b537  cmp     [rbp+240h+pExecInfo.hInstApp], 20h ; ' '
0x18002b53c  ja      short loc_18002B55E
0x18002b53e  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002b543  mov     ebx, eax
0x18002b545  test    eax, eax
0x18002b547  jns     short loc_18002B55E
0x18002b549  mov     ecx, eax
0x18002b54b  call    StatusFromHResult
0x18002b550  mov     r9, [rsp+340h+var_2F8]
0x18002b555  lea     r8, aShellexecuteex; "ShellExecuteEx failed"
0x18002b55c  jmp     short loc_18002B5CF
0x18002b55e  mov     rcx, [rbp+240h+pExecInfo.hProcess]; void *
0x18002b562  call    ?WaitForNtPrintProcessToExit@@YAJPEAX@Z; WaitForNtPrintProcessToExit(void *)
0x18002b567  test    eax, eax
0x18002b569  jnz     loc_18002B5F5
0x18002b56f  mov     rcx, [rbp+240h+pExecInfo.hProcess]; hProcess
0x18002b573  lea     rdx, [rsp+340h+ExitCode]; lpExitCode
0x18002b578  call    cs:__imp_GetExitCodeProcess
0x18002b57e  test    eax, eax
0x18002b580  jz      short loc_18002B5B7
0x18002b582  mov     eax, [rdi+650h]
0x18002b588  test    eax, eax
0x18002b58a  js      short loc_18002B5A1
0x18002b58c  mov     ebx, [rsp+340h+ExitCode]
0x18002b590  test    ebx, ebx
0x18002b592  jz      short loc_18002B5A1
0x18002b594  jle     short loc_18002B5A3
0x18002b596  movzx   ebx, bx
0x18002b599  or      ebx, 80070000h
0x18002b59f  jmp     short loc_18002B5A3
0x18002b5a1  mov     ebx, eax
0x18002b5a3  mov     rcx, [rsp+340h+var_2C8]
0x18002b5a8  test    rcx, rcx
0x18002b5ab  jz      short loc_18002B611
0x18002b5ad  mov     eax, [rdi+64Ch]
0x18002b5b3  mov     [rcx], eax
0x18002b5b5  jmp     short loc_18002B611
0x18002b5b7  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002b5bc  mov     ecx, eax
0x18002b5be  mov     ebx, eax
0x18002b5c0  call    StatusFromHResult
0x18002b5c5  lea     r8, aGetexitcodepro; "GetExitCodeProcess failed"
0x18002b5cc  xor     r9d, r9d; unsigned __int16 *
0x18002b5cf  mov     [rsp+340h+var_310], ebx; unsigned int
0x18002b5d3  lea     rdx, aElevateandcall; "ElevateAndCallLegacyPrintDriverInstall"
0x18002b5da  mov     dword ptr [rsp+340h+var_318], eax; unsigned int
0x18002b5de  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002b5e5  mov     [rsp+340h+var_320], 0; unsigned __int16 *
0x18002b5ee  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002b5f3  jmp     short loc_18002B611
0x18002b5f5  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002b5fa  mov     ecx, eax
0x18002b5fc  mov     ebx, eax
0x18002b5fe  call    StatusFromHResult
0x18002b603  lea     r8, aWaitforntprint; "WaitForNtPrintProcessToExit failed"
0x18002b60a  jmp     short loc_18002B5CC
0x18002b60c  mov     ebx, 80070057h
0x18002b611  mov     rcx, [rbp+240h+pExecInfo.hProcess]; hObject
0x18002b615  test    rcx, rcx
0x18002b618  jz      short loc_18002B679
0x18002b61a  call    cs:__imp_CloseHandle
0x18002b620  test    eax, eax
0x18002b622  jnz     short loc_18002B671
0x18002b624  call    cs:__imp_GetLastError
0x18002b62a  mov     edi, eax
0x18002b62c  test    eax, eax
0x18002b62e  jle     short loc_18002B639
0x18002b630  movzx   edi, ax
0x18002b633  or      edi, 80070000h
0x18002b639  call    cs:__imp_GetLastError
0x18002b63f  mov     [rsp+340h+var_310], edi; unsigned int
0x18002b643  lea     r9, aClosehandleSei; "CloseHandle(sei.hProcess)"
0x18002b64a  mov     dword ptr [rsp+340h+var_318], eax; unsigned int
0x18002b64e  lea     r8, aClosehandleFai; "CloseHandle failed"
0x18002b655  lea     rdx, aElevateandcall; "ElevateAndCallLegacyPrintDriverInstall"
0x18002b65c  mov     [rsp+340h+var_320], 0; unsigned __int16 *
0x18002b665  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002b66c  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002b671  mov     [rbp+240h+pExecInfo.hProcess], 0
0x18002b679  mov     rdi, [rsp+340h+hMem]
0x18002b67e  test    rdi, rdi
0x18002b681  jz      short loc_18002B699
0x18002b683  mov     edx, 5
0x18002b688  mov     rcx, rdi
0x18002b68b  call    RecursivelyDeleteDirectory
0x18002b690  mov     rcx, rdi; hMem
0x18002b693  call    cs:__imp_LocalFree
0x18002b699  lea     rdx, [rsp+340h+var_2E0]; void **
0x18002b69e  lea     rcx, [rsp+340h+var_2F0]; void **
0x18002b6a3  call    ?FreeSharedMemory@@YAXPEAPEAX0@Z; FreeSharedMemory(void * *,void * *)
0x18002b6a8  mov     rcx, [rsp+340h+var_2F8]; hMem
0x18002b6ad  test    rcx, rcx
0x18002b6b0  jz      short loc_18002B6B8
0x18002b6b2  call    cs:__imp_LocalFree
0x18002b6b8  mov     ecx, ebx
0x18002b6ba  call    StatusFromHResult
0x18002b6bf  mov     rcx, [rbp+240h+var_40]
0x18002b6c6  xor     rcx, rsp; StackCookie
0x18002b6c9  call    __security_check_cookie
0x18002b6ce  mov     rbx, [rsp+340h+arg_18]
0x18002b6d6  add     rsp, 310h
0x18002b6dd  pop     r15
0x18002b6df  pop     r14
0x18002b6e1  pop     r13
0x18002b6e3  pop     r12
0x18002b6e5  pop     rdi
0x18002b6e6  pop     rsi
0x18002b6e7  pop     rbp
0x18002b6e8  retn
```
