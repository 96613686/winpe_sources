# StartMTSTOCOM(_WLX_NOTIFICATION_INFO *)

- ea: `0x1800170a0`
- end: `0x1800175cf`
- name: `?StartMTSTOCOM@@YAXPEAU_WLX_NOTIFICATION_INFO@@@Z`
- size: `1327`
- prototype: `void __fastcall(struct _WLX_NOTIFICATION_INFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005944`
- `0x18000717c`
- `0x180007a7c`
- `0x180015594`
- `0x180016f2c`
- `0x180016ffc`
- `0x1800170a0`
- `0x180017688`
- `0x18005583a`
- `0x180055880`
- `0x180055940`
- `0x180057010`

## import_xrefs

- `msvcrt!_ltow` at `0x180017389`
- `msvcrt!_ltow` at `0x1800174b7`
- `msvcrt!_ltow` at `0x180017389`
- `msvcrt!_ltow` at `0x1800174b7`
- `msvcrt!_waccess` at `0x1800172b8`
- `msvcrt!_waccess` at `0x1800172b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001732a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001732a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800173b4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800173b4`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18001721b`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x18001721b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017244`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017244`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001733a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800171d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001733a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800173be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017428`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800171c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800171c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017529`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001753c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001754f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017529`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001753c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001754f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001741e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001741e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001748e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001748e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800174f2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800174f2`
- `ADVAPI32!RegDeleteKeyW` at `0x180017461`
- `ADVAPI32!RegDeleteKeyW` at `0x180017461`

## string_xrefs

- `0x180017166`: `com\complus\src\comcat\catsrvut\mig.cpp`
- `0x180017593`: `com\complus\src\comcat\catsrvut\mig.cpp`
- `0x18001728a`: `%s\mtstocom.exe`
- `0x18001731c`: `MTSTOCOM_EVENT`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall StartMTSTOCOM(struct _WLX_NOTIFICATION_INFO *a1)
{
  int v2; // r14d
  signed int v3; // eax
  signed int v4; // ebx
  const WCHAR *v5; // rax
  __int64 v6; // rax
  signed int v7; // eax
  HINSTANCE v8; // rax
  signed int v9; // eax
  signed int LastError; // eax
  LSTATUS v11; // eax
  int Value; // [rsp+50h] [rbp-1578h] BYREF
  HANDLE Handles[2]; // [rsp+58h] [rbp-1570h] BYREF
  signed int v14; // [rsp+68h] [rbp-1560h] BYREF
  __int16 v15; // [rsp+6Ch] [rbp-155Ch]
  int v16; // [rsp+70h] [rbp-1558h]
  __int128 v17; // [rsp+78h] [rbp-1550h]
  __int64 v18; // [rsp+88h] [rbp-1540h]
  int v19; // [rsp+90h] [rbp-1538h]
  int v20; // [rsp+94h] [rbp-1534h]
  va_list Arguments[2]; // [rsp+98h] [rbp-1530h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A8h] [rbp-1520h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-1508h] BYREF
  wchar_t v24[12]; // [rsp+130h] [rbp-1498h] BYREF
  wchar_t v25[12]; // [rsp+148h] [rbp-1480h] BYREF
  WCHAR Buffer[264]; // [rsp+160h] [rbp-1468h] BYREF
  wchar_t FileName[264]; // [rsp+370h] [rbp-1258h] BYREF
  WCHAR Source[1032]; // [rsp+580h] [rbp-1048h] BYREF
  WCHAR v29[1032]; // [rsp+D90h] [rbp-838h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  v2 = 0;
  Value = 0;
  *(_OWORD *)Arguments = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)Handles = 0;
  v14 = 0;
  v15 = 34;
  v16 = 1073742598;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 1;
  CError::WriteToLog((CError *)&v14, L"com\\complus\\src\\comcat\\catsrvut\\mig.cpp", 0xAAu, 0);
  if ( !(unsigned int)IsUpgradingPDC() && (unsigned int)WaitForNetworkAvailability() )
  {
    Arguments[0] = (va_list)v25;
    Arguments[1] = (va_list)v24;
    Handles[1] = 0;
    Handles[0] = 0;
    if ( GetSystemDirectoryW(Buffer, 0x104u) )
    {
      v5 = &Buffer[(int)safe_lstrlenW(Buffer)];
      do
      {
        v5 = CharPrevW(Buffer, v5);
        if ( *v5 != 32 && *v5 != 92 )
          goto LABEL_12;
      }
      while ( v5 != Buffer );
      if ( *v5 != 32 && *v5 != 92 )
      {
LABEL_12:
        *CharNextW(v5) = 0;
        goto LABEL_14;
      }
      Buffer[0] = 0;
LABEL_14:
      v6 = -1;
      do
        ++v6;
      while ( Buffer[v6] );
      if ( (unsigned __int64)(v6 + 13) < 0x104 )
      {
        v4 = StringCchPrintfW(FileName, 0x105u, L"%s\\mtstocom.exe", Buffer);
        if ( v4 >= 0 )
        {
          if ( _waccess(FileName, 0) )
          {
            v4 = -2147024894;
          }
          else
          {
            memset_0(&StartupInfo, 0, sizeof(StartupInfo));
            StartupInfo.cb = 104;
            memset(&StartupInfo.lpReserved, 0, 24);
            StartupInfo.dwFlags = 129;
            *(_DWORD *)&StartupInfo.wShowWindow = 6;
            StartupInfo.lpReserved2 = 0;
            Handles[0] = CreateEventW(0, 0, 0, L"MTSTOCOM_EVENT");
            if ( Handles[0] )
            {
              if ( GetLastError() == 183 )
              {
                v4 = -2147024713;
              }
              else
              {
                if ( (unsigned int)GetNumPackages((unsigned int *)&Value) )
                  v24[0] = 0;
                else
                  _ltow(Value, v24, 10);
                v8 = COMResModuleInstance();
                if ( LoadStringW(v8, 0x6Fu, Source, 1024) )
                {
                  if ( CreateProcessW(FileName, FileName, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
                    goto LABEL_36;
                  LastError = GetLastError();
                  v4 = LastError;
                  if ( LastError > 0 )
                    v4 = (unsigned __int16)LastError | 0x80070000;
                  if ( v4 >= 0 )
                  {
LABEL_36:
                    Handles[1] = ProcessInformation.hProcess;
                    v11 = RegDeleteKeyW(
                            HKEY_LOCAL_MACHINE,
                            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\Notify\\CATSRVUT");
                    v4 = v11;
                    if ( v11 > 0 )
                      v4 = (unsigned __int16)v11 | 0x80070000;
                    if ( v4 >= 0 )
                    {
                      while ( !WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
                      {
                        if ( a1 && a1->Size >= 0x20 && a1->pStatusCallback )
                        {
                          _ltow(v2, v25, 10);
                          FormatMessageW(0x2400u, Source, 0, 0, v29, 0x400u, Arguments);
                          ((void (__fastcall *)(_QWORD, WCHAR *))a1->pStatusCallback)(0, v29);
                        }
                        ++v2;
                      }
                    }
                  }
                }
                else
                {
                  v9 = GetLastError();
                  v4 = v9;
                  if ( v9 > 0 )
                    v4 = (unsigned __int16)v9 | 0x80070000;
                }
              }
            }
            else
            {
              v7 = GetLastError();
              v4 = v7;
              if ( v7 > 0 )
                v4 = (unsigned __int16)v7 | 0x80070000;
            }
          }
        }
      }
      else
      {
        v4 = -2147418113;
      }
    }
    else
    {
      v3 = GetLastError();
      v4 = v3;
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
    }
    if ( Handles[0] )
      CloseHandle(Handles[0]);
    if ( ProcessInformation.hProcess )
      CloseHandle(ProcessInformation.hProcess);
    if ( ProcessInformation.hThread )
      CloseHandle(ProcessInformation.hThread);
    v14 = v4;
    v15 = 34;
    v16 = 1073742599;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 1;
    CError::WriteToLog((CError *)&v14, L"com\\complus\\src\\comcat\\catsrvut\\mig.cpp", 0x146u, 0);
  }
}

```

## disassembly

```asm
0x1800170a0  mov     [rsp+arg_8], rbx
0x1800170a5  mov     [rsp+arg_10], rsi
0x1800170aa  push    rdi
0x1800170ab  push    r14
0x1800170ad  push    r15
0x1800170af  mov     eax, 15B0h
0x1800170b4  call    _alloca_probe
0x1800170b9  sub     rsp, rax
0x1800170bc  mov     rax, cs:__security_cookie
0x1800170c3  xor     rax, rsp
0x1800170c6  mov     [rsp+15C8h+var_28], rax
0x1800170ce  mov     rsi, rcx
0x1800170d1  xor     edx, edx; Val
0x1800170d3  mov     r8d, 20Ah; Size
0x1800170d9  lea     rcx, [rsp+15C8h+Buffer]; void *
0x1800170e1  call    memset_0
0x1800170e6  xor     edi, edi
0x1800170e8  mov     r14d, edi
0x1800170eb  mov     [rsp+15C8h+Value], edi
0x1800170ef  xorps   xmm0, xmm0
0x1800170f2  movups  xmmword ptr [rsp+15C8h+Arguments], xmm0
0x1800170fa  xor     edx, edx; Val
0x1800170fc  lea     r8d, [rdi+68h]; Size
0x180017100  lea     rcx, [rsp+15C8h+StartupInfo]; void *
0x180017108  call    memset_0
0x18001710d  xorps   xmm0, xmm0
0x180017110  xor     eax, eax
0x180017112  movups  xmmword ptr [rsp+15C8h+ProcessInformation.hProcess], xmm0
0x18001711a  mov     qword ptr [rsp+15C8h+ProcessInformation.dwProcessId], rax
0x180017122  movups  xmmword ptr [rsp+15C8h+Handles], xmm0
0x180017127  mov     [rsp+15C8h+var_1560], edi
0x18001712b  lea     r15d, [rdi+22h]
0x18001712f  mov     [rsp+15C8h+var_155C], r15w
0x180017135  mov     [rsp+15C8h+var_1558], 40000306h
0x18001713d  movdqu  [rsp+15C8h+var_1550], xmm0
0x180017143  mov     [rsp+15C8h+var_1540], rdi
0x18001714b  mov     [rsp+15C8h+var_1538], edi
0x180017152  mov     [rsp+15C8h+var_1534], 1
0x18001715d  xor     r9d, r9d; unsigned __int16 *
0x180017160  mov     r8d, 0AAh; unsigned int
0x180017166  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrvut\\mi"...
0x18001716d  lea     rcx, [rsp+15C8h+var_1560]; this
0x180017172  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180017177  call    ?IsUpgradingPDC@@YAHXZ; IsUpgradingPDC(void)
0x18001717c  test    eax, eax
0x18001717e  jnz     loc_1800175A5
0x180017184  call    ?WaitForNetworkAvailability@@YAHXZ; WaitForNetworkAvailability(void)
0x180017189  test    eax, eax
0x18001718b  jz      loc_1800175A5
0x180017191  lea     rax, [rsp+15C8h+var_1480]
0x180017199  mov     [rsp+15C8h+Arguments], rax
0x1800171a1  lea     rax, [rsp+15C8h+var_1498]
0x1800171a9  mov     [rsp+15C8h+Arguments+8], rax
0x1800171b1  mov     [rsp+15C8h+Handles+8], rdi
0x1800171b6  mov     [rsp+15C8h+Handles], rdi
0x1800171bb  mov     edx, 104h; uSize
0x1800171c0  lea     rcx, [rsp+15C8h+Buffer]; lpBuffer
0x1800171c8  call    cs:__imp_GetSystemDirectoryW
0x1800171ce  test    eax, eax
0x1800171d0  jnz     short loc_1800171EC
0x1800171d2  call    cs:__imp_GetLastError
0x1800171d8  mov     ebx, eax
0x1800171da  test    eax, eax
0x1800171dc  jle     short loc_1800171E7
0x1800171de  movzx   ebx, ax
0x1800171e1  or      ebx, 80070000h
0x1800171e7  jmp     loc_18001751F
0x1800171ec  lea     rbx, [rsp+15C8h+Buffer]
0x1800171f4  lea     rcx, [rsp+15C8h+Buffer]; unsigned __int16 *
0x1800171fc  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180017201  movsxd  rcx, eax
0x180017204  lea     rax, [rsp+15C8h+Buffer]
0x18001720c  lea     rax, [rax+rcx*2]
0x180017210  mov     rdx, rax; lpszCurrent
0x180017213  lea     rcx, [rsp+15C8h+Buffer]; lpszStart
0x18001721b  call    cs:__imp_CharPrevW
0x180017221  mov     ecx, 20h ; ' '
0x180017226  cmp     [rax], cx
0x180017229  jz      short loc_180017231
0x18001722b  cmp     word ptr [rax], 5Ch ; '\'
0x18001722f  jnz     short loc_180017241
0x180017231  cmp     rax, rbx
0x180017234  jnz     short loc_180017210
0x180017236  cmp     [rax], cx
0x180017239  jz      short loc_18001724F
0x18001723b  cmp     word ptr [rax], 5Ch ; '\'
0x18001723f  jz      short loc_18001724F
0x180017241  mov     rcx, rax; lpsz
0x180017244  call    cs:__imp_CharNextW
0x18001724a  mov     [rax], di
0x18001724d  jmp     short loc_180017257
0x18001724f  mov     [rsp+15C8h+Buffer], di
0x180017257  lea     rcx, [rsp+15C8h+Buffer]
0x18001725f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017263  inc     rax
0x180017266  cmp     [rcx+rax*2], di
0x18001726a  jnz     short loc_180017263
0x18001726c  add     rax, 0Dh
0x180017270  cmp     rax, 104h
0x180017276  jb      short loc_180017282
0x180017278  mov     ebx, 8000FFFFh
0x18001727d  jmp     loc_18001751F
0x180017282  lea     r9, [rsp+15C8h+Buffer]
0x18001728a  lea     r8, aSMtstocomExe; "%s\\mtstocom.exe"
0x180017291  mov     edx, 105h; unsigned __int64
0x180017296  lea     rcx, [rsp+15C8h+FileName]; unsigned __int16 *
0x18001729e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800172a3  mov     ebx, eax
0x1800172a5  test    eax, eax
0x1800172a7  jns     short loc_1800172AE
0x1800172a9  jmp     loc_18001751F
0x1800172ae  xor     edx, edx; AccessMode
0x1800172b0  lea     rcx, [rsp+15C8h+FileName]; FileName
0x1800172b8  call    cs:__imp__waccess
0x1800172be  test    eax, eax
0x1800172c0  jz      short loc_1800172CC
0x1800172c2  mov     ebx, 80070002h
0x1800172c7  jmp     loc_18001751F
0x1800172cc  xor     edx, edx; Val
0x1800172ce  lea     r8d, [rdx+68h]; Size
0x1800172d2  lea     rcx, [rsp+15C8h+StartupInfo]; void *
0x1800172da  call    memset_0
0x1800172df  mov     [rsp+15C8h+StartupInfo.cb], 68h ; 'h'
0x1800172ea  mov     [rsp+15C8h+StartupInfo.lpReserved], rdi
0x1800172f2  xorps   xmm0, xmm0
0x1800172f5  movdqa  xmmword ptr [rsp+15C8h+StartupInfo.lpDesktop], xmm0
0x1800172fe  mov     [rsp+15C8h+StartupInfo.dwFlags], 81h
0x180017309  mov     dword ptr [rsp+15C8h+StartupInfo.wShowWindow], 6
0x180017314  mov     [rsp+15C8h+StartupInfo.lpReserved2], rdi
0x18001731c  lea     r9, Name; "MTSTOCOM_EVENT"
0x180017323  xor     r8d, r8d; bInitialState
0x180017326  xor     edx, edx; bManualReset
0x180017328  xor     ecx, ecx; lpEventAttributes
0x18001732a  call    cs:__imp_CreateEventW
0x180017330  mov     [rsp+15C8h+Handles], rax
0x180017335  test    rax, rax
0x180017338  jnz     short loc_180017354
0x18001733a  call    cs:__imp_GetLastError
0x180017340  mov     ebx, eax
0x180017342  test    eax, eax
0x180017344  jle     short loc_18001734F
0x180017346  movzx   ebx, ax
0x180017349  or      ebx, 80070000h
0x18001734f  jmp     loc_18001751F
0x180017354  call    cs:__imp_GetLastError
0x18001735a  cmp     eax, 0B7h
0x18001735f  jnz     short loc_18001736B
0x180017361  mov     ebx, 800700B7h
0x180017366  jmp     loc_18001751F
0x18001736b  lea     rcx, [rsp+15C8h+Value]; unsigned int *
0x180017370  call    ?GetNumPackages@@YAJPEAK@Z; GetNumPackages(ulong *)
0x180017375  test    eax, eax
0x180017377  jnz     short loc_180017391
0x180017379  lea     r8d, [rax+0Ah]; Radix
0x18001737d  lea     rdx, [rsp+15C8h+var_1498]; Buffer
0x180017385  mov     ecx, [rsp+15C8h+Value]; Value
0x180017389  call    cs:__imp__ltow
0x18001738f  jmp     short loc_180017399
0x180017391  mov     [rsp+15C8h+var_1498], di
0x180017399  call    ?COMResModuleInstance@@YAPEAUHINSTANCE__@@XZ; COMResModuleInstance(void)
0x18001739e  mov     r9d, 400h; cchBufferMax
0x1800173a4  lea     r8, [rsp+15C8h+Source]; lpBuffer
0x1800173ac  mov     edx, 6Fh ; 'o'; uID
0x1800173b1  mov     rcx, rax; hInstance
0x1800173b4  call    cs:__imp_LoadStringW
0x1800173ba  test    eax, eax
0x1800173bc  jnz     short loc_1800173D8
0x1800173be  call    cs:__imp_GetLastError
0x1800173c4  mov     ebx, eax
0x1800173c6  test    eax, eax
0x1800173c8  jle     short loc_1800173D3
0x1800173ca  movzx   ebx, ax
0x1800173cd  or      ebx, 80070000h
0x1800173d3  jmp     loc_18001751F
0x1800173d8  lea     rax, [rsp+15C8h+ProcessInformation]
0x1800173e0  mov     [rsp+15C8h+lpProcessInformation], rax; lpProcessInformation
0x1800173e5  lea     rax, [rsp+15C8h+StartupInfo]
0x1800173ed  mov     [rsp+15C8h+lpStartupInfo], rax; lpStartupInfo
0x1800173f2  mov     [rsp+15C8h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x1800173f7  mov     [rsp+15C8h+lpEnvironment], rdi; lpEnvironment
0x1800173fc  mov     [rsp+15C8h+dwCreationFlags], 8; dwCreationFlags
0x180017404  mov     [rsp+15C8h+bInheritHandles], edi; bInheritHandles
0x180017408  xor     r9d, r9d; lpThreadAttributes
0x18001740b  xor     r8d, r8d; lpProcessAttributes
0x18001740e  lea     rdx, [rsp+15C8h+FileName]; lpCommandLine
0x180017416  lea     rcx, [rsp+15C8h+FileName]; lpApplicationName
0x18001741e  call    cs:__imp_CreateProcessW
0x180017424  test    eax, eax
0x180017426  jnz     short loc_180017446
0x180017428  call    cs:__imp_GetLastError
0x18001742e  mov     ebx, eax
0x180017430  test    eax, eax
0x180017432  jle     short loc_18001743D
0x180017434  movzx   ebx, ax
0x180017437  or      ebx, 80070000h
0x18001743d  test    ebx, ebx
0x18001743f  jns     short loc_180017446
0x180017441  jmp     loc_18001751F
0x180017446  mov     rax, [rsp+15C8h+ProcessInformation.hProcess]
0x18001744e  mov     [rsp+15C8h+Handles+8], rax
0x180017453  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001745a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017461  call    cs:__imp_RegDeleteKeyW
0x180017467  mov     ebx, eax
0x180017469  test    eax, eax
0x18001746b  jle     short loc_180017476
0x18001746d  movzx   ebx, ax
0x180017470  or      ebx, 80070000h
0x180017476  test    ebx, ebx
0x180017478  js      loc_180017513
0x18001747e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180017482  xor     r8d, r8d; bWaitAll
0x180017485  lea     rdx, [rsp+15C8h+Handles]; lpHandles
0x18001748a  lea     ecx, [r8+2]; nCount
0x18001748e  call    cs:__imp_WaitForMultipleObjects
0x180017494  test    eax, eax
0x180017496  jnz     short loc_180017513
0x180017498  test    rsi, rsi
0x18001749b  jz      short loc_18001750B
0x18001749d  cmp     dword ptr [rsi], 20h ; ' '
0x1800174a0  jb      short loc_18001750B
0x1800174a2  cmp     [rsi+30h], rdi
0x1800174a6  jz      short loc_18001750B
0x1800174a8  lea     r8d, [rax+0Ah]; Radix
0x1800174ac  lea     rdx, [rsp+15C8h+var_1480]; Buffer
0x1800174b4  mov     ecx, r14d; Value
0x1800174b7  call    cs:__imp__ltow
0x1800174bd  lea     rax, [rsp+15C8h+Arguments]
0x1800174c5  mov     [rsp+15C8h+lpEnvironment], rax; Arguments
0x1800174ca  mov     [rsp+15C8h+dwCreationFlags], 400h; nSize
0x1800174d2  lea     rax, [rsp+15C8h+var_838]
0x1800174da  mov     qword ptr [rsp+15C8h+bInheritHandles], rax; lpBuffer
0x1800174df  xor     r9d, r9d; dwLanguageId
0x1800174e2  xor     r8d, r8d; dwMessageId
0x1800174e5  lea     rdx, [rsp+15C8h+Source]; lpSource
0x1800174ed  mov     ecx, 2400h; dwFlags
0x1800174f2  call    cs:__imp_FormatMessageW
0x1800174f8  lea     rdx, [rsp+15C8h+var_838]
0x180017500  xor     ecx, ecx
0x180017502  mov     rax, [rsi+30h]
0x180017506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001750b  inc     r14d
0x18001750e  jmp     loc_18001747E
0x180017513  jmp     short loc_18001751F
0x180017515  xor     edi, edi
0x180017517  lea     r15d, [rdi+22h]
0x18001751b  mov     ebx, [rsp+15C8h+Value]
0x18001751f  mov     rcx, [rsp+15C8h+Handles]; hObject
0x180017524  test    rcx, rcx
0x180017527  jz      short loc_18001752F
0x180017529  call    cs:__imp_CloseHandle
0x18001752f  mov     rcx, [rsp+15C8h+ProcessInformation.hProcess]; hObject
0x180017537  test    rcx, rcx
0x18001753a  jz      short loc_180017542
0x18001753c  call    cs:__imp_CloseHandle
0x180017542  mov     rcx, [rsp+15C8h+ProcessInformation.hThread]; hObject
0x18001754a  test    rcx, rcx
0x18001754d  jz      short loc_180017555
0x18001754f  call    cs:__imp_CloseHandle
0x180017555  mov     [rsp+15C8h+var_1560], ebx
0x180017559  mov     [rsp+15C8h+var_155C], r15w
0x18001755f  mov     [rsp+15C8h+var_1558], 40000307h
0x180017567  xorps   xmm0, xmm0
0x18001756a  movdqu  [rsp+15C8h+var_1550], xmm0
0x180017570  mov     [rsp+15C8h+var_1540], rdi
0x180017578  mov     [rsp+15C8h+var_1538], edi
0x18001757f  mov     [rsp+15C8h+var_1534], 1
0x18001758a  xor     r9d, r9d; unsigned __int16 *
0x18001758d  mov     r8d, 146h; unsigned int
0x180017593  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrvut\\mi"...
0x18001759a  lea     rcx, [rsp+15C8h+var_1560]; this
0x18001759f  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x1800175a4  nop
0x1800175a5  mov     rcx, [rsp+15C8h+var_28]
0x1800175ad  xor     rcx, rsp; StackCookie
0x1800175b0  call    __security_check_cookie
0x1800175b5  lea     r11, [rsp+15C8h+var_18]
0x1800175bd  mov     rbx, [r11+28h]
0x1800175c1  mov     rsi, [r11+30h]
0x1800175c5  mov     rsp, r11
0x1800175c8  pop     r15
0x1800175ca  pop     r14
0x1800175cc  pop     rdi
0x1800175cd  retn
```
