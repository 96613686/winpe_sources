# ElevateAndCallInstallPrinterDriverFromTheWeb(HWND__ *,ushort *,ushort *,ushort *,ushort *,_OSVERSIONINFOW *)

- ea: `0x18002ae2c`
- end: `0x18002b2f4`
- name: `?ElevateAndCallInstallPrinterDriverFromTheWeb@@YAKPEAUHWND__@@PEAG111PEAU_OSVERSIONINFOW@@@Z`
- size: `1224`
- prototype: `unsigned int(HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct _OSVERSIONINFOW *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x1800113c0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000b200`
- `0x180026498`
- `0x18002a5ac`
- `0x18002ae2c`
- `0x18002b6f0`
- `0x18002c440`
- `0x180035208`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b269`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002b1b4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18002b1b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b24a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b24a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b2b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b2b8`
- `SHELL32!ShellExecuteExW` at `0x18002b16f`
- `SHELL32!ShellExecuteExW` at `0x18002b16f`

## string_xrefs

- `0x18002b1fd`: `ElevateAndCallInstallPrinterDriverFromTheWeb`
- `0x18002b285`: `ElevateAndCallInstallPrinterDriverFromTheWeb`
- `0x18002af45`: `PSetupElevatedInstallPrinterDriverFromTheWebW `

## pseudocode

```c
__int64 __fastcall ElevateAndCallInstallPrinterDriverFromTheWeb(
        HWND a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v9; // rsi
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // ecx
  __int64 v15; // rax
  unsigned __int64 v16; // rdi
  int v17; // ebx
  size_t v18; // r8
  char *v19; // rdi
  __int64 v20; // rax
  unsigned __int64 v21; // r14
  __int64 v22; // r11
  __int64 v23; // rax
  unsigned __int16 *v24; // r11
  __int64 v25; // rax
  unsigned __int64 v26; // r14
  __int64 v27; // r11
  unsigned __int16 *v28; // r8
  __int64 v29; // rax
  unsigned __int16 *v30; // r11
  __int64 v31; // rax
  unsigned __int64 v32; // r14
  __int64 v33; // r11
  unsigned __int16 *v34; // r11
  __int64 v35; // r11
  __int64 v36; // rdx
  _OWORD *v37; // rcx
  struct _OSVERSIONINFOW *v38; // rax
  __int64 v39; // r8
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  DWORD dwPlatformId; // eax
  _OWORD *v49; // rcx
  _OWORD *v50; // rax
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  int v59; // eax
  NCoreLibrary *v60; // rcx
  int LastErrorAsFailHR; // eax
  unsigned int v62; // eax
  const unsigned __int16 *v63; // r9
  const unsigned __int16 *v64; // r8
  NCoreLibrary *v65; // rcx
  NCoreLibrary *v66; // rcx
  signed int LastError; // eax
  unsigned int v68; // edi
  DWORD v69; // eax
  NCoreLibrary::TString *v70; // rcx
  DWORD ExitCode; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  void *v74; // [rsp+50h] [rbp-B0h] BYREF
  void *v75; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v76; // [rsp+60h] [rbp-A0h]
  HWND v77; // [rsp+68h] [rbp-98h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v79[288]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v80[264]; // [rsp+200h] [rbp+100h] BYREF

  v77 = a1;
  v76 = a4;
  memset_0(v80, 0, 0x208u);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  hMem = 0;
  v9 = 0;
  ExitCode = 0;
  v75 = 0;
  v74 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v17 = -2147024809;
    goto LABEL_52;
  }
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v13 = -1;
  do
    ++v13;
  while ( a4[v13] );
  v14 = 2 * (v13 + v11 + v12) + 334;
  if ( a5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a5[v15] );
    v16 = v14 + 2 * ((_DWORD)v15 + 1);
  }
  else
  {
    v16 = v14;
  }
  v17 = CheckLUAAndInitialize(
          L"PSetupElevatedInstallPrinterDriverFromTheWebW ",
          v16,
          &v75,
          &v74,
          (unsigned __int16 **)&hMem,
          v80);
  if ( v17 < 0 )
    goto LABEL_50;
  v18 = v16;
  v19 = (char *)v74;
  memset_0(v74, 0, v18);
  *((_QWORD *)v19 + 38) = a1;
  v20 = -1;
  do
    ++v20;
  while ( a2[v20] );
  v21 = (unsigned int)(v20 + 1);
  v17 = StringCchCopyW((unsigned __int16 *)v19 + 164, v21, a2);
  if ( v17 >= 0 )
  {
    v23 = v22;
    v24 = (unsigned __int16 *)(v22 + 2 * v21);
    *(_QWORD *)v19 = v23 - (_QWORD)v19;
    v25 = -1;
    do
      ++v25;
    while ( a3[v25] );
    v26 = (unsigned int)(v25 + 1);
    v17 = StringCchCopyW(v24, v26, a3);
    if ( v17 >= 0 )
    {
      v28 = v76;
      v29 = v27 - (_QWORD)v19;
      v30 = (unsigned __int16 *)(v27 + 2 * v26);
      *((_QWORD *)v19 + 1) = v29;
      v31 = -1;
      do
        ++v31;
      while ( v28[v31] );
      v32 = (unsigned int)(v31 + 1);
      v17 = StringCchCopyW(v30, v32, v28);
      if ( v17 >= 0 )
      {
        *((_QWORD *)v19 + 2) = v33 - (_QWORD)v19;
        if ( a5 )
        {
          v34 = (unsigned __int16 *)(v33 + 2 * v32);
          do
            ++v10;
          while ( a5[v10] );
          v17 = StringCchCopyW(v34, (unsigned int)(v10 + 1), a5);
          if ( v17 >= 0 )
            *((_QWORD *)v19 + 39) = v35 - (_QWORD)v19;
        }
      }
    }
  }
  v36 = 2;
  v37 = v79;
  v38 = &OsVersionInfo;
  v39 = 2;
  do
  {
    v40 = *(_OWORD *)&v38->dwPlatformId;
    *v37 = *(_OWORD *)&v38->dwOSVersionInfoSize;
    v41 = *(_OWORD *)&v38->szCSDVersion[6];
    v37[1] = v40;
    v42 = *(_OWORD *)&v38->szCSDVersion[14];
    v37[2] = v41;
    v43 = *(_OWORD *)&v38->szCSDVersion[22];
    v37[3] = v42;
    v44 = *(_OWORD *)&v38->szCSDVersion[30];
    v37[4] = v43;
    v45 = *(_OWORD *)&v38->szCSDVersion[38];
    v37[5] = v44;
    v46 = *(_OWORD *)&v38->szCSDVersion[46];
    v38 = (struct _OSVERSIONINFOW *)((char *)v38 + 128);
    v37[6] = v45;
    v37[7] = v46;
    v37 += 8;
    --v39;
  }
  while ( v39 );
  v47 = *(_OWORD *)&v38->dwOSVersionInfoSize;
  dwPlatformId = v38->dwPlatformId;
  *v37 = v47;
  *((_DWORD *)v37 + 4) = dwPlatformId;
  v49 = v19 + 24;
  v50 = v79;
  do
  {
    v51 = v50[1];
    *v49 = *v50;
    v52 = v50[2];
    v49[1] = v51;
    v53 = v50[3];
    v49[2] = v52;
    v54 = v50[4];
    v49[3] = v53;
    v55 = v50[5];
    v49[4] = v54;
    v56 = v50[6];
    v49[5] = v55;
    v57 = v50[7];
    v50 += 8;
    v49[6] = v56;
    v49[7] = v57;
    v49 += 8;
    --v36;
  }
  while ( v36 );
  v58 = *v50;
  v59 = *((_DWORD *)v50 + 4);
  *v49 = v58;
  *((_DWORD *)v49 + 4) = v59;
  if ( v17 < 0 )
  {
LABEL_50:
    v9 = (unsigned __int16 *)hMem;
    goto LABEL_52;
  }
  v9 = (unsigned __int16 *)hMem;
  pExecInfo.hwnd = v77;
  pExecInfo.lpFile = v80;
  pExecInfo.lpDirectory = &qword_18003C420;
  pExecInfo.lpVerb = L"runas";
  pExecInfo.cbSize = 112;
  pExecInfo.fMask = 64;
  pExecInfo.lpParameters = (LPCWSTR)hMem;
  pExecInfo.nShow = 1;
  if ( !ShellExecuteExW(&pExecInfo) || pExecInfo.hInstApp <= HINSTANCE_ERROR )
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v60);
    v17 = LastErrorAsFailHR;
    if ( LastErrorAsFailHR < 0 )
    {
      v62 = StatusFromHResult((unsigned int)LastErrorAsFailHR);
      v63 = v9;
      v64 = L"ShellExecuteEx failed";
LABEL_48:
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"ElevateAndCallInstallPrinterDriverFromTheWeb",
        v64,
        v63,
        0,
        v62,
        v17);
      goto LABEL_52;
    }
  }
  if ( (unsigned int)WaitForNtPrintProcessToExit(pExecInfo.hProcess) )
  {
    v17 = NCoreLibrary::GetLastErrorAsFailHR(v65);
    v62 = StatusFromHResult((unsigned int)v17);
    v64 = L"WaitForNtPrintProcessToExit failed";
    goto LABEL_47;
  }
  if ( !GetExitCodeProcess(pExecInfo.hProcess, &ExitCode) )
  {
    v17 = NCoreLibrary::GetLastErrorAsFailHR(v66);
    v62 = StatusFromHResult((unsigned int)v17);
    v64 = L"GetExitCodeProcess failed";
LABEL_47:
    v63 = 0;
    goto LABEL_48;
  }
  if ( *((int *)v19 + 80) >= 0 && (v17 = ExitCode) != 0 )
  {
    if ( (int)ExitCode > 0 )
      v17 = (unsigned __int16)ExitCode | 0x80070000;
  }
  else
  {
    v17 = *((_DWORD *)v19 + 80);
  }
LABEL_52:
  if ( pExecInfo.hProcess )
  {
    if ( !CloseHandle(pExecInfo.hProcess) )
    {
      LastError = GetLastError();
      v68 = LastError;
      if ( LastError > 0 )
        v68 = (unsigned __int16)LastError | 0x80070000;
      v69 = GetLastError();
      SplLogPrinterSetupGenericEvent(
        &SETUP_PRINTER_OPERATION_FAILED,
        L"ElevateAndCallInstallPrinterDriverFromTheWeb",
        L"CloseHandle failed",
        L"CloseHandle(sei.hProcess)",
        0,
        v69,
        v68);
    }
    pExecInfo.hProcess = 0;
  }
  FreeSharedMemory(&v74, &v75);
  if ( v9 )
    LocalFree(v9);
  NCoreLibrary::TString::vFree(v70, &NCoreLibrary::TString::gszNullState);
  return StatusFromHResult((unsigned int)v17);
}

```

## disassembly

```asm
0x18002ae2c  push    rbp
0x18002ae2e  push    rbx
0x18002ae2f  push    rsi
0x18002ae30  push    rdi
0x18002ae31  push    r12
0x18002ae33  push    r13
0x18002ae35  push    r14
0x18002ae37  push    r15
0x18002ae39  lea     rbp, [rsp-328h]
0x18002ae41  sub     rsp, 428h
0x18002ae48  mov     rax, cs:__security_cookie
0x18002ae4f  xor     rax, rsp
0x18002ae52  mov     [rbp+360h+var_50], rax
0x18002ae59  mov     r12, [rbp+360h+arg_20]
0x18002ae60  mov     rbx, r9
0x18002ae63  mov     r15, r8
0x18002ae66  mov     [rsp+460h+var_3F8], rcx
0x18002ae6b  mov     r13, rdx
0x18002ae6e  mov     [rsp+460h+var_400], rbx
0x18002ae73  mov     r14, rcx
0x18002ae76  xor     edx, edx; Val
0x18002ae78  mov     r8d, 208h; Size
0x18002ae7e  lea     rcx, [rbp+360h+var_260]; void *
0x18002ae85  call    memset_0
0x18002ae8a  xor     edx, edx; Val
0x18002ae8c  lea     rcx, [rsp+460h+pExecInfo]; void *
0x18002ae91  lea     r8d, [rdx+70h]; Size
0x18002ae95  call    memset_0
0x18002ae9a  xor     ecx, ecx
0x18002ae9c  mov     [rsp+460h+hMem], rcx
0x18002aea1  mov     esi, ecx
0x18002aea3  mov     [rsp+460h+ExitCode], ecx
0x18002aea7  mov     [rsp+460h+var_408], rcx
0x18002aeac  mov     [rsp+460h+var_410], rcx
0x18002aeb1  test    r13, r13
0x18002aeb4  jz      loc_18002B239
0x18002aeba  test    r15, r15
0x18002aebd  jz      loc_18002B239
0x18002aec3  test    rbx, rbx
0x18002aec6  jz      loc_18002B239
0x18002aecc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002aed0  mov     rdx, rsi
0x18002aed3  inc     rdx
0x18002aed6  cmp     [r13+rdx*2+0], cx
0x18002aedc  jnz     short loc_18002AED3
0x18002aede  mov     rax, rsi
0x18002aee1  inc     rax
0x18002aee4  cmp     [r15+rax*2], cx
0x18002aee9  jnz     short loc_18002AEE1
0x18002aeeb  mov     rcx, rsi
0x18002aeee  xor     r8d, r8d
0x18002aef1  inc     rcx
0x18002aef4  cmp     [rbx+rcx*2], r8w
0x18002aef9  jnz     short loc_18002AEF1
0x18002aefb  add     eax, edx
0x18002aefd  add     eax, ecx
0x18002aeff  lea     ecx, ds:14Eh[rax*2]
0x18002af06  test    r12, r12
0x18002af09  jz      short loc_18002AF20
0x18002af0b  mov     rax, rsi
0x18002af0e  inc     rax
0x18002af11  cmp     [r12+rax*2], r8w
0x18002af16  jnz     short loc_18002AF0E
0x18002af18  lea     edi, [rax+1]
0x18002af1b  lea     edi, [rcx+rdi*2]
0x18002af1e  jmp     short loc_18002AF22
0x18002af20  mov     edi, ecx
0x18002af22  lea     rax, [rbp+360h+var_260]
0x18002af29  mov     rdx, rdi; unsigned __int64
0x18002af2c  mov     [rsp+460h+var_438], rax; unsigned __int16 *
0x18002af31  lea     r9, [rsp+460h+var_410]; void **
0x18002af36  lea     rax, [rsp+460h+hMem]
0x18002af3b  lea     r8, [rsp+460h+var_408]; void **
0x18002af40  mov     [rsp+460h+var_440], rax; unsigned __int16 **
0x18002af45  lea     rcx, aPsetupelevated_7; "PSetupElevatedInstallPrinterDriverFromT"...
0x18002af4c  call    ?CheckLUAAndInitialize@@YAJPEBG_KPEAPEAX2PEAPEAGQEAG@Z; CheckLUAAndInitialize(ushort const *,unsigned __int64,void * *,void * *,ushort * *,ushort * const)
0x18002af51  mov     ebx, eax
0x18002af53  test    eax, eax
0x18002af55  js      loc_18002B232
0x18002af5b  mov     r8, rdi; Size
0x18002af5e  xor     edx, edx; Val
0x18002af60  mov     rdi, [rsp+460h+var_410]
0x18002af65  mov     rcx, rdi; void *
0x18002af68  call    memset_0
0x18002af6d  lea     r11, [rdi+148h]
0x18002af74  mov     [rdi+130h], r14
0x18002af7b  mov     rax, rsi
0x18002af7e  xor     ecx, ecx
0x18002af80  inc     rax
0x18002af83  cmp     [r13+rax*2+0], cx
0x18002af89  jnz     short loc_18002AF80
0x18002af8b  inc     eax
0x18002af8d  mov     r8, r13; unsigned __int16 *
0x18002af90  mov     edx, eax; unsigned __int64
0x18002af92  mov     rcx, r11; unsigned __int16 *
0x18002af95  mov     r14d, eax
0x18002af98  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002af9d  xor     r13d, r13d
0x18002afa0  mov     ebx, eax
0x18002afa2  test    eax, eax
0x18002afa4  js      loc_18002B04C
0x18002afaa  mov     rax, r11
0x18002afad  lea     r11, [r11+r14*2]
0x18002afb1  sub     rax, rdi
0x18002afb4  mov     [rdi], rax
0x18002afb7  mov     rax, rsi
0x18002afba  inc     rax
0x18002afbd  cmp     [r15+rax*2], r13w
0x18002afc2  jnz     short loc_18002AFBA
0x18002afc4  inc     eax
0x18002afc6  mov     r8, r15; unsigned __int16 *
0x18002afc9  mov     edx, eax; unsigned __int64
0x18002afcb  mov     rcx, r11; unsigned __int16 *
0x18002afce  mov     r14d, eax
0x18002afd1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002afd6  mov     ebx, eax
0x18002afd8  test    eax, eax
0x18002afda  js      short loc_18002B04C
0x18002afdc  mov     r8, [rsp+460h+var_400]; unsigned __int16 *
0x18002afe1  mov     rax, r11
0x18002afe4  sub     rax, rdi
0x18002afe7  lea     r11, [r11+r14*2]
0x18002afeb  mov     [rdi+8], rax
0x18002afef  mov     rax, rsi
0x18002aff2  inc     rax
0x18002aff5  cmp     [r8+rax*2], r13w
0x18002affa  jnz     short loc_18002AFF2
0x18002affc  inc     eax
0x18002affe  mov     rcx, r11; unsigned __int16 *
0x18002b001  mov     edx, eax; unsigned __int64
0x18002b003  mov     r14d, eax
0x18002b006  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b00b  mov     ebx, eax
0x18002b00d  test    eax, eax
0x18002b00f  js      short loc_18002B04C
0x18002b011  mov     rax, r11
0x18002b014  sub     rax, rdi
0x18002b017  mov     [rdi+10h], rax
0x18002b01b  test    r12, r12
0x18002b01e  jz      short loc_18002B04C
0x18002b020  lea     r11, [r11+r14*2]
0x18002b024  inc     rsi
0x18002b027  cmp     [r12+rsi*2], r13w
0x18002b02c  jnz     short loc_18002B024
0x18002b02e  lea     edx, [rsi+1]; unsigned __int64
0x18002b031  mov     r8, r12; unsigned __int16 *
0x18002b034  mov     rcx, r11; unsigned __int16 *
0x18002b037  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b03c  mov     ebx, eax
0x18002b03e  test    eax, eax
0x18002b040  js      short loc_18002B04C
0x18002b042  sub     r11, rdi
0x18002b045  mov     [rdi+138h], r11
0x18002b04c  mov     edx, 2
0x18002b051  lea     rcx, [rbp+360h+var_380]
0x18002b055  lea     rax, OsVersionInfo
0x18002b05c  mov     r8d, edx
0x18002b05f  lea     r9d, [rdx+7Eh]
0x18002b063  movups  xmm0, xmmword ptr [rax]
0x18002b066  movups  xmm1, xmmword ptr [rax+10h]
0x18002b06a  movups  xmmword ptr [rcx], xmm0
0x18002b06d  movups  xmm0, xmmword ptr [rax+20h]
0x18002b071  movups  xmmword ptr [rcx+10h], xmm1
0x18002b075  movups  xmm1, xmmword ptr [rax+30h]
0x18002b079  movups  xmmword ptr [rcx+20h], xmm0
0x18002b07d  movups  xmm0, xmmword ptr [rax+40h]
0x18002b081  movups  xmmword ptr [rcx+30h], xmm1
0x18002b085  movups  xmm1, xmmword ptr [rax+50h]
0x18002b089  movups  xmmword ptr [rcx+40h], xmm0
0x18002b08d  movups  xmm0, xmmword ptr [rax+60h]
0x18002b091  movups  xmmword ptr [rcx+50h], xmm1
0x18002b095  movups  xmm1, xmmword ptr [rax+70h]
0x18002b099  add     rax, r9
0x18002b09c  movups  xmmword ptr [rcx+60h], xmm0
0x18002b0a0  movups  xmmword ptr [rcx+70h], xmm1
0x18002b0a4  add     rcx, r9
0x18002b0a7  sub     r8, 1
0x18002b0ab  jnz     short loc_18002B063
0x18002b0ad  movups  xmm0, xmmword ptr [rax]
0x18002b0b0  mov     eax, [rax+10h]
0x18002b0b3  movups  xmmword ptr [rcx], xmm0
0x18002b0b6  mov     [rcx+10h], eax
0x18002b0b9  lea     rcx, [rdi+18h]
0x18002b0bd  lea     rax, [rbp+360h+var_380]
0x18002b0c1  movups  xmm0, xmmword ptr [rax]
0x18002b0c4  movups  xmm1, xmmword ptr [rax+10h]
0x18002b0c8  movups  xmmword ptr [rcx], xmm0
0x18002b0cb  movups  xmm0, xmmword ptr [rax+20h]
0x18002b0cf  movups  xmmword ptr [rcx+10h], xmm1
0x18002b0d3  movups  xmm1, xmmword ptr [rax+30h]
0x18002b0d7  movups  xmmword ptr [rcx+20h], xmm0
0x18002b0db  movups  xmm0, xmmword ptr [rax+40h]
0x18002b0df  movups  xmmword ptr [rcx+30h], xmm1
0x18002b0e3  movups  xmm1, xmmword ptr [rax+50h]
0x18002b0e7  movups  xmmword ptr [rcx+40h], xmm0
0x18002b0eb  movups  xmm0, xmmword ptr [rax+60h]
0x18002b0ef  movups  xmmword ptr [rcx+50h], xmm1
0x18002b0f3  movups  xmm1, xmmword ptr [rax+70h]
0x18002b0f7  add     rax, r9
0x18002b0fa  movups  xmmword ptr [rcx+60h], xmm0
0x18002b0fe  movups  xmmword ptr [rcx+70h], xmm1
0x18002b102  add     rcx, r9
0x18002b105  sub     rdx, 1
0x18002b109  jnz     short loc_18002B0C1
0x18002b10b  movups  xmm0, xmmword ptr [rax]
0x18002b10e  mov     eax, [rax+10h]
0x18002b111  movups  xmmword ptr [rcx], xmm0
0x18002b114  mov     [rcx+10h], eax
0x18002b117  test    ebx, ebx
0x18002b119  js      loc_18002B232
0x18002b11f  mov     rax, [rsp+460h+var_3F8]
0x18002b124  lea     rcx, [rsp+460h+pExecInfo]; pExecInfo
0x18002b129  mov     rsi, [rsp+460h+hMem]
0x18002b12e  mov     [rsp+460h+pExecInfo.hwnd], rax
0x18002b133  lea     rax, [rbp+360h+var_260]
0x18002b13a  mov     [rbp+360h+pExecInfo.lpFile], rax
0x18002b13e  lea     rax, qword_18003C420
0x18002b145  mov     [rbp+360h+pExecInfo.lpDirectory], rax
0x18002b149  lea     rax, aRunas; "runas"
0x18002b150  mov     [rbp+360h+pExecInfo.lpVerb], rax
0x18002b154  mov     [rsp+460h+pExecInfo.cbSize], 70h ; 'p'
0x18002b15c  mov     [rsp+460h+pExecInfo.fMask], 40h ; '@'
0x18002b164  mov     [rbp+360h+pExecInfo.lpParameters], rsi
0x18002b168  mov     [rbp+360h+pExecInfo.nShow], 1
0x18002b16f  call    cs:__imp_ShellExecuteExW
0x18002b175  test    eax, eax
0x18002b177  jz      short loc_18002B180
0x18002b179  cmp     [rbp+360h+pExecInfo.hInstApp], 20h ; ' '
0x18002b17e  ja      short loc_18002B19E
0x18002b180  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002b185  mov     ebx, eax
0x18002b187  test    eax, eax
0x18002b189  jns     short loc_18002B19E
0x18002b18b  mov     ecx, eax
0x18002b18d  call    StatusFromHResult
0x18002b192  mov     r9, rsi
0x18002b195  lea     r8, aShellexecuteex; "ShellExecuteEx failed"
0x18002b19c  jmp     short loc_18002B1F9
0x18002b19e  mov     rcx, [rbp+360h+pExecInfo.hProcess]; void *
0x18002b1a2  call    ?WaitForNtPrintProcessToExit@@YAJPEAX@Z; WaitForNtPrintProcessToExit(void *)
0x18002b1a7  test    eax, eax
0x18002b1a9  jnz     short loc_18002B21B
0x18002b1ab  mov     rcx, [rbp+360h+pExecInfo.hProcess]; hProcess
0x18002b1af  lea     rdx, [rsp+460h+ExitCode]; lpExitCode
0x18002b1b4  call    cs:__imp_GetExitCodeProcess
0x18002b1ba  test    eax, eax
0x18002b1bc  jz      short loc_18002B1E1
0x18002b1be  mov     eax, [rdi+140h]
0x18002b1c4  test    eax, eax
0x18002b1c6  js      short loc_18002B1DD
0x18002b1c8  mov     ebx, [rsp+460h+ExitCode]
0x18002b1cc  test    ebx, ebx
0x18002b1ce  jz      short loc_18002B1DD
0x18002b1d0  jle     short loc_18002B23E
0x18002b1d2  movzx   ebx, bx
0x18002b1d5  or      ebx, 80070000h
0x18002b1db  jmp     short loc_18002B23E
0x18002b1dd  mov     ebx, eax
0x18002b1df  jmp     short loc_18002B23E
0x18002b1e1  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002b1e6  mov     ecx, eax
0x18002b1e8  mov     ebx, eax
0x18002b1ea  call    StatusFromHResult
0x18002b1ef  lea     r8, aGetexitcodepro; "GetExitCodeProcess failed"
0x18002b1f6  xor     r9d, r9d; unsigned __int16 *
0x18002b1f9  mov     [rsp+460h+var_430], ebx; unsigned int
0x18002b1fd  lea     rdx, aElevateandcall_1; "ElevateAndCallInstallPrinterDriverFromT"...
0x18002b204  mov     dword ptr [rsp+460h+var_438], eax; unsigned int
0x18002b208  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x18002b20f  mov     [rsp+460h+var_440], r13; unsigned __int16 *
0x18002b214  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x18002b219  jmp     short loc_18002B23E
0x18002b21b  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002b220  mov     ecx, eax
0x18002b222  mov     ebx, eax
0x18002b224  call    StatusFromHResult
0x18002b229  lea     r8, aWaitforntprint; "WaitForNtPrintProcessToExit failed"
0x18002b230  jmp     short loc_18002B1F6
0x18002b232  mov     rsi, [rsp+460h+hMem]
0x18002b237  jmp     short loc_18002B23E
0x18002b239  mov     ebx, 80070057h
0x18002b23e  mov     rcx, [rbp+360h+pExecInfo.hProcess]; hObject
0x18002b242  xor     r14d, r14d
0x18002b245  test    rcx, rcx
0x18002b248  jz      short loc_18002B2A1
0x18002b24a  call    cs:__imp_CloseHandle
0x18002b250  test    eax, eax
0x18002b252  jnz     short loc_18002B29D
0x18002b254  call    cs:__imp_GetLastError
0x18002b25a  mov     edi, eax
0x18002b25c  test    eax, eax
0x18002b25e  jle     short loc_18002B269
0x18002b260  movzx   edi, ax
0x18002b263  or      edi, 80070000h
0x18002b269  call    cs:__imp_GetLastError
0x18002b26f  mov     [rsp+460h+var_430], edi; unsigned int
0x18002b273  lea     r9, aClosehandleSei; "CloseHandle(sei.hProcess)"
0x18002b27a  mov     dword ptr [rsp+460h+var_438], eax; unsigned int
0x18002b27e  lea     r8, aClosehandleFai; "CloseHandle failed"
0x18002b285  lea     rdx, aElevateandcall_1; "ElevateAndCallInstallPrinterDriverFromT"...
  ... truncated ...
```
