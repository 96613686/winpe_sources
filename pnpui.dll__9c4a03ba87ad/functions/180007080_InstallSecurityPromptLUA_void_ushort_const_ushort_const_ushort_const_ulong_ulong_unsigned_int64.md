# InstallSecurityPromptLUA(void *,ushort const *,ushort const *,ushort const *,ulong,ulong *,unsigned __int64)

- ea: `0x180007080`
- end: `0x180007629`
- name: `?InstallSecurityPromptLUA@@YAKPEAXPEBG11KPEAK_K@Z`
- size: `1449`
- prototype: `__int64 __fastcall(void *, WCHAR *lpString2, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int *, SP_LOG_TOKEN LogToken)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003614`
- `0x180005490`
- `0x180006cb4`
- `0x180007080`
- `0x18000ccde`
- `0x18000cd10`

## import_xrefs

- `msvcrt!malloc` at `0x1800073c4`
- `msvcrt!malloc` at `0x1800073c4`
- `msvcrt!free` at `0x1800075e0`
- `msvcrt!free` at `0x1800075e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007572`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000715f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000715f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800071f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800071f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007504`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007517`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007534`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007504`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007517`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007534`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000724a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800072be`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000724a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800072be`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800074d0`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800074d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180007117`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180007117`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075fe`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800072a3`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800072a3`
- `RPCRT4!UuidCreate` at `0x180007234`
- `RPCRT4!UuidCreate` at `0x180007297`
- `RPCRT4!UuidCreate` at `0x180007234`
- `RPCRT4!UuidCreate` at `0x180007297`
- `USERENV!CreateEnvironmentBlock` at `0x180007221`
- `USERENV!CreateEnvironmentBlock` at `0x180007221`
- `USERENV!DestroyEnvironmentBlock` at `0x1800075f0`
- `USERENV!DestroyEnvironmentBlock` at `0x1800075f0`
- `SETUPAPI!SetupWriteTextLog` at `0x18000718e`
- `SETUPAPI!SetupWriteTextLog` at `0x180007561`
- `SETUPAPI!SetupWriteTextLog` at `0x1800075a2`
- `SETUPAPI!SetupWriteTextLog` at `0x18000718e`
- `SETUPAPI!SetupWriteTextLog` at `0x180007561`
- `SETUPAPI!SetupWriteTextLog` at `0x1800075a2`

## string_xrefs

- `0x18000743a`: `pnpui.dll`
- `0x18000742e`: `InstallSecurityPromptRunDllW`
- `0x180007311`: `rundll32.exe`
- `0x1800073e6`: `rundll32.exe`
- `0x1800074e2`: `Failed to create process to display UI. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall InstallSecurityPromptLUA(
        void *a1,
        WCHAR *lpString2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int *a6,
        SP_LOG_TOKEN LogToken)
{
  HANDLE hProcess; // r12
  UINT SystemDirectoryW; // eax
  unsigned int LastError; // ebx
  __int64 v13; // rsi
  WCHAR *v14; // r14
  unsigned __int64 v15; // rax
  void *UserUIAToken; // rax
  void *v17; // r15
  RPC_STATUS v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // rbx
  DWORD v27; // eax
  const CHAR *v28; // r9
  PDWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID Environment; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hHandle; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v36; // [rsp+80h] [rbp-80h]
  unsigned int *v37; // [rsp+88h] [rbp-78h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  WCHAR *v39; // [rsp+A8h] [rbp-58h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  UUID Uuid; // [rsp+120h] [rbp+20h] BYREF
  OLECHAR sz[40]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR v43[96]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR Name[96]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR Buffer[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR ApplicationName[264]; // [rsp+510h] [rbp+410h] BYREF

  v36 = a3;
  v39 = lpString2;
  v37 = a6;
  Environment = 0;
  hObject = 0;
  Uuid = 0;
  hHandle = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  hProcess = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  v32 = SystemDirectoryW;
  if ( !SystemDirectoryW )
    goto LABEL_2;
  if ( SystemDirectoryW > 0x104 )
  {
    LastError = 13;
    goto LABEL_67;
  }
  if ( !GetTokenInformation(a1, TokenSessionId, (char *)&v32 + 4, 4u, (PDWORD)&v32) )
  {
    LastError = GetLastError();
    LODWORD(ReturnLength) = LastError;
    SetupWriteTextLog(LogToken, 0x100u, 1u, "Failed to determine session. Error = 0x%08X", ReturnLength);
    goto LABEL_67;
  }
  if ( !HIDWORD(v32) )
  {
    LastError = 1459;
    LODWORD(ReturnLength) = 1459;
    SetupWriteTextLog(LogToken, 0x100u, 1u, "Cannot display UI to non-interactive caller. Error = 0x%08X", ReturnLength);
    goto LABEL_67;
  }
  v13 = -1;
  v14 = 0;
  v15 = -1;
  do
    ++v15;
  while ( lpString2[v15] );
  if ( v15 < 8 || CompareStringW(0x7Fu, 1u, L"WinSta0\\", 8, lpString2, 8) != 2 )
  {
    LastError = 1459;
    goto LABEL_61;
  }
  UserUIAToken = GetUserUIAToken(a1);
  v17 = UserUIAToken;
  if ( !UserUIAToken )
  {
LABEL_2:
    LastError = GetLastError();
    goto LABEL_67;
  }
  if ( !CreateEnvironmentBlock(&Environment, UserUIAToken, 0) )
    Environment = 0;
  v18 = UuidCreate(&Uuid);
  if ( v18 )
    goto LABEL_22;
  if ( !StringFromGUID2(&Uuid, sz, 39) )
    goto LABEL_24;
  if ( (int)StringCchPrintfW(Name, 0x59u, L"Global\\%ws", sz) < 0 )
    goto LABEL_45;
  LastError = CreateAdminSecuredEvent(Name, v19, &hObject);
  if ( !LastError )
  {
    v18 = UuidCreate(&Uuid);
    if ( v18 )
    {
LABEL_22:
      LastError = I_RpcMapWin32Status(v18);
      goto LABEL_59;
    }
    if ( !StringFromGUID2(&Uuid, sz, 39) )
    {
LABEL_24:
      LastError = 1359;
      goto LABEL_59;
    }
    if ( (int)StringCchPrintfW(v43, 0x59u, L"Global\\%ws", sz) >= 0 )
    {
      LastError = CreateAdminSecuredEvent(v43, v20, &hHandle);
      if ( LastError )
        goto LABEL_59;
      if ( (int)StringCchPrintfW(ApplicationName, 0x104u, L"%ws\\%ws", Buffer, L"rundll32.exe") >= 0 )
      {
        if ( a4 )
        {
          v21 = -1;
          do
            ++v21;
          while ( a4[v21] );
          v22 = v21 + 1;
        }
        else
        {
          v22 = 1;
        }
        v23 = -1;
        do
          ++v23;
        while ( Buffer[v23] );
        v24 = -1;
        do
          ++v24;
        while ( Name[v24] );
        v25 = -1;
        do
          ++v25;
        while ( v43[v25] );
        do
          ++v13;
        while ( v36[v13] );
        v26 = (unsigned int)(v22 + 67 + v13 + v23 + v24 + v25);
        v14 = (WCHAR *)malloc(2 * v26);
        if ( !v14 )
        {
          LastError = 8;
          goto LABEL_59;
        }
        if ( !a4 )
          a4 = (const unsigned __int16 *)&qword_18000FDD8;
        if ( (int)StringCchPrintfW(
                    v14,
                    v26,
                    L"%ws %ws\\%ws,%ws %d %ws %ws %ws %ws",
                    L"rundll32.exe",
                    Buffer,
                    L"pnpui.dll",
                    L"InstallSecurityPromptRunDllW",
                    a5,
                    Name,
                    v43,
                    v36,
                    a4,
                    v32) >= 0 )
        {
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          memset_0(&StartupInfo, 0, sizeof(StartupInfo));
          StartupInfo.lpDesktop = v39;
          StartupInfo.cb = 104;
          if ( CreateProcessAsUserW(
                 v17,
                 ApplicationName,
                 v14,
                 0,
                 0,
                 0,
                 0x408u,
                 Environment,
                 0,
                 &StartupInfo,
                 &ProcessInformation) )
          {
            CloseHandle(ProcessInformation.hThread);
            hProcess = ProcessInformation.hProcess;
            v27 = WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
            switch ( v27 )
            {
              case 0u:
                LastError = 0;
                if ( WaitForSingleObject(hHandle, 0) )
                {
                  if ( !WaitForSingleObject(hObject, 0) )
                    *v37 = 1;
                }
                else
                {
                  *v37 = 2;
                }
                goto LABEL_59;
              case 0x102u:
                SetupWriteTextLog(
                  LogToken,
                  0x100u,
                  1u,
                  "Failed to retrive code returned by the UI displayed to the user, UI timed out before the user selected an option.");
                LastError = 1460;
                goto LABEL_59;
              case 0xFFFFFFFF:
                v27 = GetLastError();
                LastError = v27;
                v28 = "Failed to retrive code returned by the UI displayed to the user, unable to wait for UI. Error = 0x%08X";
                break;
              default:
                LastError = 13;
                v28 = "Failed to retrive code returned by the UI displayed to the user. Error = 0x%08X";
                break;
            }
          }
          else
          {
            v27 = GetLastError();
            LastError = v27;
            v28 = "Failed to create process to display UI. Error = 0x%08X";
          }
          LODWORD(ReturnLengtha) = v27;
          SetupWriteTextLog(LogToken, 0x100u, 1u, v28, ReturnLengtha);
          goto LABEL_59;
        }
      }
    }
LABEL_45:
    LastError = 13;
  }
LABEL_59:
  CloseHandle(v17);
LABEL_61:
  if ( hObject )
    CloseHandle(hObject);
  if ( hHandle )
    CloseHandle(hHandle);
  if ( v14 )
    free(v14);
LABEL_67:
  if ( Environment )
    DestroyEnvironmentBlock(Environment);
  if ( hProcess )
    CloseHandle(hProcess);
  return LastError;
}

```

## disassembly

```asm
0x180007080  push    rbp
0x180007082  push    rbx
0x180007083  push    rsi
0x180007084  push    rdi
0x180007085  push    r12
0x180007087  push    r13
0x180007089  push    r14
0x18000708b  push    r15
0x18000708d  lea     rbp, [rsp-638h]
0x180007095  sub     rsp, 738h
0x18000709c  mov     rax, cs:__security_cookie
0x1800070a3  xor     rax, rsp
0x1800070a6  mov     [rbp+670h+var_50], rax
0x1800070ad  mov     rax, [rbp+670h+arg_28]
0x1800070b4  xor     r15d, r15d
0x1800070b7  mov     [rbp+670h+var_6F0], r8
0x1800070bb  mov     rdi, rdx
0x1800070be  mov     [rbp+670h+var_6C8], rdx
0x1800070c2  mov     rbx, rcx
0x1800070c5  xorps   xmm0, xmm0
0x1800070c8  mov     [rbp+670h+var_6E8], rax
0x1800070cc  lea     r8d, [r15+68h]; Size
0x1800070d0  mov     [rsp+770h+TokenInformation], r15d
0x1800070d5  xor     edx, edx; Val
0x1800070d7  mov     [rsp+770h+var_710], r15d
0x1800070dc  lea     rcx, [rbp+670h+StartupInfo]; void *
0x1800070e0  mov     [rsp+770h+Environment], r15
0x1800070e5  mov     r13, r9
0x1800070e8  mov     [rsp+770h+hObject], r15
0x1800070ed  movups  xmmword ptr [rbp+670h+Uuid.Data1], xmm0
0x1800070f1  mov     [rsp+770h+hHandle], r15
0x1800070f6  call    memset_0
0x1800070fb  xorps   xmm0, xmm0
0x1800070fe  lea     rcx, [rbp+670h+Buffer]; lpBuffer
0x180007105  xor     eax, eax
0x180007107  mov     edx, 104h; uSize
0x18000710c  movups  xmmword ptr [rbp+670h+ProcessInformation.hProcess], xmm0
0x180007110  mov     qword ptr [rbp+670h+ProcessInformation.dwProcessId], rax
0x180007114  mov     r12d, r15d
0x180007117  call    cs:__imp_GetSystemDirectoryW
0x18000711d  mov     [rsp+770h+var_710], eax
0x180007121  test    eax, eax
0x180007123  jnz     short loc_180007132
0x180007125  call    cs:__imp_GetLastError
0x18000712b  mov     ebx, eax
0x18000712d  jmp     loc_1800075E6
0x180007132  cmp     eax, 104h
0x180007137  jbe     short loc_180007143
0x180007139  mov     ebx, 0Dh
0x18000713e  jmp     loc_1800075E6
0x180007143  mov     r9d, 4; TokenInformationLength
0x180007149  lea     rax, [rsp+770h+var_710]
0x18000714e  lea     r8, [rsp+770h+TokenInformation]; TokenInformation
0x180007153  mov     [rsp+770h+ReturnLength], rax; ReturnLength
0x180007158  mov     rcx, rbx; TokenHandle
0x18000715b  lea     edx, [r9+8]; TokenInformationClass
0x18000715f  call    cs:__imp_GetTokenInformation
0x180007165  test    eax, eax
0x180007167  jnz     short loc_180007199
0x180007169  call    cs:__imp_GetLastError
0x18000716f  mov     ebx, eax
0x180007171  mov     dword ptr [rsp+770h+ReturnLength], eax
0x180007175  lea     r9, MessageStr; "Failed to determine session. Error = 0x"...
0x18000717c  mov     rcx, [rbp+670h+LogToken]; LogToken
0x180007183  mov     edx, 100h; Category
0x180007188  mov     r8d, 1; Flags
0x18000718e  call    cs:__imp_SetupWriteTextLog
0x180007194  jmp     loc_1800075E6
0x180007199  cmp     [rsp+770h+TokenInformation], r15d
0x18000719e  jnz     short loc_1800071B2
0x1800071a0  mov     ebx, 5B3h
0x1800071a5  lea     r9, aCannotDisplayU; "Cannot display UI to non-interactive ca"...
0x1800071ac  mov     dword ptr [rsp+770h+ReturnLength], ebx
0x1800071b0  jmp     short loc_18000717C
0x1800071b2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800071b6  mov     r14, r15
0x1800071b9  mov     rax, rsi
0x1800071bc  inc     rax
0x1800071bf  cmp     [rdi+rax*2], r15w
0x1800071c4  jnz     short loc_1800071BC
0x1800071c6  cmp     rax, 8
0x1800071ca  jb      loc_1800075B3
0x1800071d0  mov     r9d, 8; cchCount1
0x1800071d6  mov     [rsp+770h+cchCount2], 8; cchCount2
0x1800071de  mov     [rsp+770h+ReturnLength], rdi; lpString2
0x1800071e3  lea     r8, String1; "WinSta0\\"
0x1800071ea  lea     edi, [r9-7]
0x1800071ee  mov     edx, edi; dwCmpFlags
0x1800071f0  lea     ecx, [rdi+7Eh]; Locale
0x1800071f3  call    cs:__imp_CompareStringW
0x1800071f9  cmp     eax, 2
0x1800071fc  jnz     loc_1800075B3
0x180007202  mov     rcx, rbx; void *
0x180007205  call    ?GetUserUIAToken@@YAPEAXPEAX@Z; GetUserUIAToken(void *)
0x18000720a  mov     r15, rax
0x18000720d  test    rax, rax
0x180007210  jz      loc_180007125
0x180007216  xor     r8d, r8d; bInherit
0x180007219  lea     rcx, [rsp+770h+Environment]; lpEnvironment
0x18000721e  mov     rdx, rax; hToken
0x180007221  call    cs:__imp_CreateEnvironmentBlock
0x180007227  test    eax, eax
0x180007229  jnz     short loc_180007230
0x18000722b  mov     [rsp+770h+Environment], r12
0x180007230  lea     rcx, [rbp+670h+Uuid]; Uuid
0x180007234  call    cs:__imp_UuidCreate
0x18000723a  test    eax, eax
0x18000723c  jnz     short loc_1800072A1
0x18000723e  lea     r8d, [rax+27h]; cchMax
0x180007242  lea     rdx, [rbp+670h+sz]; lpsz
0x180007246  lea     rcx, [rbp+670h+Uuid]; rguid
0x18000724a  call    cs:__imp_StringFromGUID2
0x180007250  test    eax, eax
0x180007252  jz      short loc_1800072C8
0x180007254  lea     r9, [rbp+670h+sz]
0x180007258  mov     edx, 59h ; 'Y'; unsigned __int64
0x18000725d  lea     r8, aGlobalWs; "Global\\%ws"
0x180007264  lea     rcx, [rbp+670h+Name]; unsigned __int16 *
0x18000726b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007270  test    eax, eax
0x180007272  js      loc_18000745B
0x180007278  lea     r8, [rsp+770h+hObject]; void **
0x18000727d  lea     rcx, [rbp+670h+Name]; lpName
0x180007284  call    ?CreateAdminSecuredEvent@@YAKPEBGKPEAPEAX@Z; CreateAdminSecuredEvent(ushort const *,ulong,void * *)
0x180007289  mov     ebx, eax
0x18000728b  test    eax, eax
0x18000728d  jnz     loc_1800075A8
0x180007293  lea     rcx, [rbp+670h+Uuid]; Uuid
0x180007297  call    cs:__imp_UuidCreate
0x18000729d  test    eax, eax
0x18000729f  jz      short loc_1800072B0
0x1800072a1  mov     ecx, eax; Status
0x1800072a3  call    cs:__imp_I_RpcMapWin32Status
0x1800072a9  mov     ebx, eax
0x1800072ab  jmp     loc_1800075A8
0x1800072b0  mov     r8d, 27h ; '''; cchMax
0x1800072b6  lea     rdx, [rbp+670h+sz]; lpsz
0x1800072ba  lea     rcx, [rbp+670h+Uuid]; rguid
0x1800072be  call    cs:__imp_StringFromGUID2
0x1800072c4  test    eax, eax
0x1800072c6  jnz     short loc_1800072D2
0x1800072c8  mov     ebx, 54Fh
0x1800072cd  jmp     loc_1800075A8
0x1800072d2  lea     r9, [rbp+670h+sz]
0x1800072d6  mov     edx, 59h ; 'Y'; unsigned __int64
0x1800072db  lea     r8, aGlobalWs; "Global\\%ws"
0x1800072e2  lea     rcx, [rbp+670h+var_5F0]; unsigned __int16 *
0x1800072e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800072ee  test    eax, eax
0x1800072f0  js      loc_18000745B
0x1800072f6  lea     r8, [rsp+770h+hHandle]; void **
0x1800072fb  lea     rcx, [rbp+670h+var_5F0]; lpName
0x180007302  call    ?CreateAdminSecuredEvent@@YAKPEBGKPEAPEAX@Z; CreateAdminSecuredEvent(ushort const *,ulong,void * *)
0x180007307  mov     ebx, eax
0x180007309  test    eax, eax
0x18000730b  jnz     loc_1800075A8
0x180007311  lea     rax, aRundll32Exe; "rundll32.exe"
0x180007318  mov     edx, 104h; unsigned __int64
0x18000731d  lea     r9, [rbp+670h+Buffer]
0x180007324  mov     [rsp+770h+ReturnLength], rax
0x180007329  lea     r8, aWsWs; "%ws\\%ws"
0x180007330  lea     rcx, [rbp+670h+ApplicationName]; unsigned __int16 *
0x180007337  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000733c  xor     r10d, r10d
0x18000733f  test    eax, eax
0x180007341  js      loc_18000745B
0x180007347  test    r13, r13
0x18000734a  jz      short loc_180007360
0x18000734c  mov     rax, rsi
0x18000734f  inc     rax
0x180007352  cmp     [r13+rax*2+0], r10w
0x180007358  jnz     short loc_18000734F
0x18000735a  lea     r8, [rax+1]
0x18000735e  jmp     short loc_180007363
0x180007360  mov     r8, rdi
0x180007363  lea     rax, [rbp+670h+Buffer]
0x18000736a  mov     rdx, rsi
0x18000736d  inc     rdx
0x180007370  cmp     [rax+rdx*2], r10w
0x180007375  jnz     short loc_18000736D
0x180007377  lea     rax, [rbp+670h+Name]
0x18000737e  mov     rcx, rsi
0x180007381  inc     rcx
0x180007384  cmp     [rax+rcx*2], r10w
0x180007389  jnz     short loc_180007381
0x18000738b  lea     r9, [rbp+670h+var_5F0]
0x180007392  mov     rax, rsi
0x180007395  inc     rax
0x180007398  cmp     [r9+rax*2], r10w
0x18000739d  jnz     short loc_180007395
0x18000739f  mov     r9, [rbp+670h+var_6F0]
0x1800073a3  inc     rsi
0x1800073a6  cmp     [r9+rsi*2], r10w
0x1800073ab  jnz     short loc_1800073A3
0x1800073ad  lea     rbx, [rcx+rax]
0x1800073b1  add     r8, 43h ; 'C'
0x1800073b5  add     rbx, rdx
0x1800073b8  add     rbx, rsi
0x1800073bb  add     rbx, r8
0x1800073be  mov     ebx, ebx
0x1800073c0  lea     rcx, [rbx+rbx]; Size
0x1800073c4  call    cs:__imp_malloc
0x1800073ca  xor     esi, esi
0x1800073cc  mov     r14, rax
0x1800073cf  test    rax, rax
0x1800073d2  jnz     short loc_1800073DC
0x1800073d4  lea     ebx, [rax+8]
0x1800073d7  jmp     loc_1800075A8
0x1800073dc  lea     rax, qword_18000FDD8
0x1800073e3  test    r13, r13
0x1800073e6  lea     r9, aRundll32Exe; "rundll32.exe"
0x1800073ed  mov     rdx, rbx; unsigned __int64
0x1800073f0  cmovz   r13, rax
0x1800073f4  lea     r8, aWsWsWsWsDWsWsW; "%ws %ws\\%ws,%ws %d %ws %ws %ws %ws"
0x1800073fb  mov     rax, [rbp+670h+var_6F0]
0x1800073ff  mov     rcx, r14; unsigned __int16 *
0x180007402  mov     [rsp+770h+var_718], r13
0x180007407  mov     [rsp+770h+lpProcessInformation], rax
0x18000740c  lea     rax, [rbp+670h+var_5F0]
0x180007413  mov     [rsp+770h+lpStartupInfo], rax
0x180007418  lea     rax, [rbp+670h+Name]
0x18000741f  mov     [rsp+770h+lpCurrentDirectory], rax
0x180007424  mov     eax, [rbp+670h+arg_20]
0x18000742a  mov     dword ptr [rsp+770h+lpEnvironment], eax
0x18000742e  lea     rax, aInstallsecurit_2; "InstallSecurityPromptRunDllW"
0x180007435  mov     qword ptr [rsp+770h+dwCreationFlags], rax
0x18000743a  lea     rax, ModuleName; "pnpui.dll"
0x180007441  mov     qword ptr [rsp+770h+cchCount2], rax
0x180007446  lea     rax, [rbp+670h+Buffer]
0x18000744d  mov     [rsp+770h+ReturnLength], rax
0x180007452  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007457  test    eax, eax
0x180007459  jns     short loc_180007465
0x18000745b  mov     ebx, 0Dh
0x180007460  jmp     loc_1800075A8
0x180007465  xor     eax, eax
0x180007467  lea     rcx, [rbp+670h+StartupInfo]; void *
0x18000746b  xorps   xmm0, xmm0
0x18000746e  mov     qword ptr [rbp+670h+ProcessInformation.dwProcessId], rax
0x180007472  xor     edx, edx; Val
0x180007474  movups  xmmword ptr [rbp+670h+ProcessInformation.hProcess], xmm0
0x180007478  lea     ebx, [rax+68h]
0x18000747b  mov     r8d, ebx; Size
0x18000747e  call    memset_0
0x180007483  mov     rax, [rbp+670h+var_6C8]
0x180007487  lea     rdx, [rbp+670h+ApplicationName]; lpApplicationName
0x18000748e  mov     [rbp+670h+StartupInfo.lpDesktop], rax
0x180007492  xor     r9d, r9d; lpProcessAttributes
0x180007495  lea     rax, [rbp+670h+ProcessInformation]
0x180007499  mov     [rbp+670h+StartupInfo.cb], ebx
0x18000749c  mov     [rsp+770h+lpProcessInformation], rax; lpProcessInformation
0x1800074a1  mov     r8, r14; lpCommandLine
0x1800074a4  lea     rax, [rbp+670h+StartupInfo]
0x1800074a8  mov     rcx, r15; hToken
0x1800074ab  mov     [rsp+770h+lpStartupInfo], rax; lpStartupInfo
0x1800074b0  mov     rax, [rsp+770h+Environment]
0x1800074b5  mov     [rsp+770h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x1800074ba  mov     [rsp+770h+lpEnvironment], rax; lpEnvironment
0x1800074bf  mov     [rsp+770h+dwCreationFlags], 408h; dwCreationFlags
0x1800074c7  mov     [rsp+770h+cchCount2], esi; bInheritHandles
0x1800074cb  mov     [rsp+770h+ReturnLength], rsi; lpThreadAttributes
0x1800074d0  call    cs:__imp_CreateProcessAsUserW
0x1800074d6  test    eax, eax
0x1800074d8  jnz     short loc_1800074EE
0x1800074da  call    cs:__imp_GetLastError
0x1800074e0  mov     ebx, eax
0x1800074e2  lea     r9, aFailedToCreate; "Failed to create process to display UI."...
0x1800074e9  jmp     loc_18000758F
0x1800074ee  mov     rcx, [rbp+670h+ProcessInformation.hThread]; hObject
0x1800074f2  call    cs:__imp_CloseHandle
0x1800074f8  mov     r12, [rbp+670h+ProcessInformation.hProcess]
0x1800074fc  or      ebx, 0FFFFFFFFh
0x1800074ff  mov     edx, ebx; dwMilliseconds
0x180007501  mov     rcx, r12; hHandle
0x180007504  call    cs:__imp_WaitForSingleObject
0x18000750a  test    eax, eax
0x18000750c  jnz     short loc_180007546
0x18000750e  mov     rcx, [rsp+770h+hHandle]; hHandle
0x180007513  xor     edx, edx; dwMilliseconds
0x180007515  mov     ebx, esi
0x180007517  call    cs:__imp_WaitForSingleObject
0x18000751d  test    eax, eax
0x18000751f  jnz     short loc_18000752D
0x180007521  mov     rax, [rbp+670h+var_6E8]
0x180007525  mov     dword ptr [rax], 2
0x18000752b  jmp     short loc_1800075A8
0x18000752d  mov     rcx, [rsp+770h+hObject]; hHandle
0x180007532  xor     edx, edx; dwMilliseconds
0x180007534  call    cs:__imp_WaitForSingleObject
0x18000753a  test    eax, eax
0x18000753c  jnz     short loc_1800075A8
0x18000753e  mov     rax, [rbp+670h+var_6E8]
0x180007542  mov     [rax], edi
0x180007544  jmp     short loc_1800075A8
0x180007546  cmp     eax, 102h
0x18000754b  jnz     short loc_18000756E
0x18000754d  mov     rcx, [rbp+670h+LogToken]; LogToken
0x180007554  lea     r9, aFailedToRetriv_1; "Failed to retrive code returned by the "...
0x18000755b  mov     r8d, edi; Flags
0x18000755e  lea     edx, [rax-2]; Category
  ... truncated ...
```
