# InitDebugSupport

- ea: `0x180037470`
- end: `0x1800377fb`
- name: `InitDebugSupport`
- size: `907`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800310b0`
- `0x180035f70`
- `0x180036340`
- `0x180058f20`
- `0x18005ce5c`
- `0x180071890`
- `0x1800971c0`

## callees

- `0x18002c690`
- `0x180037470`
- `0x180075ec0`
- `0x18007d320`
- `0x18008728c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037793`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037574`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800375db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037574`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800375db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800374f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037534`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003759b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800374f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037534`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003759b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037569`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800375d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037569`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800375d0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800376eb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800376eb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180037693`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800376cc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003771b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180037693`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800376cc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003771b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180037740`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180037740`

## pseudocode

```c
void __fastcall InitDebugSupport(int a1)
{
  LSTATUS v2; // eax
  const WCHAR *v3; // rdx
  __int64 v4; // rcx
  unsigned __int16 near **v5; // rdx
  __int64 v6; // r8
  WCHAR *v7; // rax
  int v8; // ebx
  WCHAR *v9; // rcx
  bool v10; // zf
  const unsigned __int16 *v11; // r8
  struct _SECURITY_ATTRIBUTES *v12; // rdx
  void (*v13)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v15; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-98h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR NewFileName[264]; // [rsp+490h] [rbp+390h] BYREF

  hKey = 0;
  v20 = 0;
  Type = 0;
  g_lpDebugMsg = _DebugMsg;
  cbData = 0;
  *(_DWORD *)&g_dwDebugLevel = 0;
  g_DebugCallerId = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Diagnostics",
         0,
         0x20019u,
         &hKey);
  if ( !v2 )
  {
    v3 = L"GpSvcDebugLevel";
LABEL_6:
    cbData = 4;
    RegQueryValueExW(hKey, v3, 0, &Type, &g_dwDebugLevel, &cbData);
    RegCloseKey(hKey);
    goto LABEL_7;
  }
  if ( v2 == 2
    && !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          0,
          0x20019u,
          &hKey) )
  {
    v3 = L"UserenvDebugLevel";
    goto LABEL_6;
  }
LABEL_7:
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    RegQueryValueExW(hKey, L"GpSvcDebugLevel", 0, &Type, &g_dwDebugLevel, &cbData);
    RegCloseKey(hKey);
  }
  if ( !*(_DWORD *)&g_dwDebugLevel )
  {
LABEL_33:
    if ( dword_180128038 && (qword_180128048 & 1) != 0 && (qword_180128050 & 1) == qword_180128050 )
      *(_DWORD *)&g_dwDebugLevel |= 0x100000u;
    return;
  }
  v4 = 2147483646;
  v5 = &szLogDirectory;
  v6 = 260;
  v7 = &g_szLogDirectory;
  do
  {
    if ( !v4 )
      break;
    if ( !*(_WORD *)v5 )
      break;
    *v7 = *(_WORD *)v5;
    v5 = (unsigned __int16 near **)((char *)v5 + 2);
    ++v7;
    --v4;
    --v6;
  }
  while ( v6 );
  v8 = g_DebugCallerId;
  v9 = v7 - 1;
  v10 = v6 == 0;
  v11 = (const unsigned __int16 *)&szLogFileName;
  if ( !v10 )
    v9 = v7;
  if ( g_DebugCallerId )
    v11 = szGPMCLogFileName;
  *v9 = 0;
  StringCchCopyW(&g_szLogFileName, 0x104u, v11);
  if ( !v8 )
    StringCchCopyW(&g_szBackupLogFileName, 0x104u, szBackupLogFileName);
  if ( ExpandEnvironmentStringsW(&g_szLogDirectory, Dst, 0x104u) - 1 <= 0x103 )
  {
    CreateNestedDirectoryEx(Dst, v12);
    if ( a1 )
    {
      if ( ExpandEnvironmentStringsW(&g_szLogFileName, FileName, 0x104u) - 1 > 0x103
        || !GetFileAttributesExW(FileName, GetFileExInfoStandard, FileInformation)
        || v20 < 0x4B000
        || ExpandEnvironmentStringsW(&g_szBackupLogFileName, NewFileName, 0x104u) - 1 > 0x103 )
      {
        return;
      }
      if ( !MoveFileExW(FileName, NewFileName, 1u) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v13 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            LastError = GetLastError();
            v13(4u, L"Moving log file to backup failed with 0x%x", LastError);
          }
          else if ( g_lpDebugMsgContextInstance )
          {
            if ( g_lpDebugMsgContext )
            {
              v15 = GetLastError();
              RedirectDebugMsg(4u, L"Moving log file to backup failed with 0x%x", v15);
            }
          }
        }
        return;
      }
    }
    goto LABEL_33;
  }
}

```

## disassembly

```asm
0x180037470  push    rbp
0x180037472  push    rbx
0x180037473  push    rsi
0x180037474  push    rdi
0x180037475  lea     rbp, [rsp-5B8h]
0x18003747d  sub     rsp, 6B8h
0x180037484  mov     rax, cs:__security_cookie
0x18003748b  xor     rax, rsp
0x18003748e  mov     [rbp+5D0h+var_30], rax
0x180037495  xor     esi, esi
0x180037497  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003749e  xor     eax, eax
0x1800374a0  mov     [rsp+6D0h+hKey], rsi
0x1800374a5  mov     [rsp+6D0h+var_668], eax
0x1800374a9  xorps   xmm0, xmm0
0x1800374ac  lea     rax, ?_DebugMsg@@YAXIPEBGZZ; _DebugMsg(uint,ushort const *,...)
0x1800374b3  mov     [rsp+6D0h+Type], esi
0x1800374b7  mov     cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA, rax; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800374be  mov     edi, ecx
0x1800374c0  lea     rax, [rsp+6D0h+hKey]
0x1800374c5  mov     [rsp+6D0h+cbData], esi
0x1800374c9  mov     r9d, 20019h; samDesired
0x1800374cf  mov     [rsp+6D0h+phkResult], rax; phkResult
0x1800374d4  xor     r8d, r8d; ulOptions
0x1800374d7  mov     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800374dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800374e4  mov     cs:?g_DebugCallerId@@3W4_DebugLoggerInvoker@@A, esi; _DebugLoggerInvoker g_DebugCallerId
0x1800374ea  movups  [rsp+6D0h+FileInformation], xmm0
0x1800374ef  movups  [rsp+6D0h+var_678], xmm0
0x1800374f4  call    cs:__imp_RegOpenKeyExW
0x1800374fa  lea     rbx, ?g_dwDebugLevel@@3KA; ulong g_dwDebugLevel
0x180037501  test    eax, eax
0x180037503  jnz     short loc_18003750E
0x180037505  lea     rdx, aGpsvcdebugleve; "GpSvcDebugLevel"
0x18003750c  jmp     short loc_180037545
0x18003750e  cmp     eax, 2
0x180037511  jnz     short loc_18003757A
0x180037513  lea     rax, [rsp+6D0h+hKey]
0x180037518  mov     r9d, 20019h; samDesired
0x18003751e  xor     r8d, r8d; ulOptions
0x180037521  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180037526  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003752d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037534  call    cs:__imp_RegOpenKeyExW
0x18003753a  test    eax, eax
0x18003753c  jnz     short loc_18003757A
0x18003753e  lea     rdx, aUserenvdebugle_0; "UserenvDebugLevel"
0x180037545  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18003754a  lea     rax, [rsp+6D0h+cbData]
0x18003754f  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x180037554  lea     r9, [rsp+6D0h+Type]; lpType
0x180037559  xor     r8d, r8d; lpReserved
0x18003755c  mov     [rsp+6D0h+phkResult], rbx; lpData
0x180037561  mov     [rsp+6D0h+cbData], 4
0x180037569  call    cs:__imp_RegQueryValueExW
0x18003756f  mov     rcx, [rsp+6D0h+hKey]; hKey
0x180037574  call    cs:__imp_RegCloseKey
0x18003757a  lea     rax, [rsp+6D0h+hKey]
0x18003757f  mov     r9d, 20019h; samDesired
0x180037585  xor     r8d, r8d; ulOptions
0x180037588  mov     [rsp+6D0h+phkResult], rax; phkResult
0x18003758d  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180037594  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003759b  call    cs:__imp_RegOpenKeyExW
0x1800375a1  test    eax, eax
0x1800375a3  jnz     short loc_1800375E1
0x1800375a5  mov     rcx, [rsp+6D0h+hKey]; hKey
0x1800375aa  lea     rax, [rsp+6D0h+cbData]
0x1800375af  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x1800375b4  lea     r9, [rsp+6D0h+Type]; lpType
0x1800375b9  xor     r8d, r8d; lpReserved
0x1800375bc  mov     [rsp+6D0h+phkResult], rbx; lpData
0x1800375c1  lea     rdx, aGpsvcdebugleve; "GpSvcDebugLevel"
0x1800375c8  mov     [rsp+6D0h+cbData], 4
0x1800375d0  call    cs:__imp_RegQueryValueExW
0x1800375d6  mov     rcx, [rsp+6D0h+hKey]; hKey
0x1800375db  call    cs:__imp_RegCloseKey
0x1800375e1  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800375e7  jz      loc_1800377AF
0x1800375ed  mov     ecx, 7FFFFFFEh
0x1800375f2  lea     rdx, ?szLogDirectory@@3PAGA; "%SystemRoot%\\Debug\\UserMode"
0x1800375f9  mov     r8d, 104h
0x1800375ff  lea     rax, ?g_szLogDirectory@@3PAGA; ushort near * g_szLogDirectory
0x180037606  test    rcx, rcx
0x180037609  jz      short loc_18003762A
0x18003760b  movzx   r9d, word ptr [rdx]
0x18003760f  test    r9w, r9w
0x180037613  jz      short loc_18003762A
0x180037615  mov     [rax], r9w
0x180037619  add     rdx, 2
0x18003761d  add     rax, 2
0x180037621  dec     rcx
0x180037624  sub     r8, 1
0x180037628  jnz     short loc_180037606
0x18003762a  mov     ebx, cs:?g_DebugCallerId@@3W4_DebugLoggerInvoker@@A; _DebugLoggerInvoker g_DebugCallerId
0x180037630  lea     rcx, [rax-2]
0x180037634  test    r8, r8
0x180037637  mov     edx, 104h; unsigned __int64
0x18003763c  lea     r8, ?szLogFileName@@3PAGA; "%SystemRoot%\\Debug\\UserMode\\gpsvc.lo"...
0x180037643  cmovnz  rcx, rax
0x180037647  lea     rax, ?szGPMCLogFileName@@3PAGA; "%SystemRoot%\\Debug\\UserMode\\gpmc.log"
0x18003764e  test    ebx, ebx
0x180037650  cmovnz  r8, rax; unsigned __int16 *
0x180037654  mov     [rcx], si
0x180037657  lea     rcx, ?g_szLogFileName@@3PAGA; unsigned __int16 *
0x18003765e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037663  test    ebx, ebx
0x180037665  jnz     short loc_18003767F
0x180037667  lea     r8, ?szBackupLogFileName@@3PAGA; "%SystemRoot%\\Debug\\UserMode\\gpsvc.ba"...
0x18003766e  mov     edx, 104h; unsigned __int64
0x180037673  lea     rcx, ?g_szBackupLogFileName@@3PAGA; unsigned __int16 *
0x18003767a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003767f  mov     r8d, 104h; nSize
0x180037685  lea     rdx, [rbp+5D0h+Dst]; lpDst
0x18003768c  lea     rcx, ?g_szLogDirectory@@3PAGA; lpSrc
0x180037693  call    cs:__imp_ExpandEnvironmentStringsW
0x180037699  dec     eax
0x18003769b  cmp     eax, 103h
0x1800376a0  ja      loc_1800377E0
0x1800376a6  lea     rcx, [rbp+5D0h+Dst]; unsigned __int16 *
0x1800376ad  call    ?CreateNestedDirectoryEx@@YAIPEBGPEAU_SECURITY_ATTRIBUTES@@H@Z; CreateNestedDirectoryEx(ushort const *,_SECURITY_ATTRIBUTES *,int)
0x1800376b2  test    edi, edi
0x1800376b4  jz      loc_1800377AF
0x1800376ba  mov     r8d, 104h; nSize
0x1800376c0  lea     rdx, [rsp+6D0h+FileName]; lpDst
0x1800376c5  lea     rcx, ?g_szLogFileName@@3PAGA; lpSrc
0x1800376cc  call    cs:__imp_ExpandEnvironmentStringsW
0x1800376d2  dec     eax
0x1800376d4  cmp     eax, 103h
0x1800376d9  ja      loc_1800377E0
0x1800376df  lea     r8, [rsp+6D0h+FileInformation]; lpFileInformation
0x1800376e4  xor     edx, edx; fInfoLevelId
0x1800376e6  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x1800376eb  call    cs:__imp_GetFileAttributesExW
0x1800376f1  test    eax, eax
0x1800376f3  jz      loc_1800377E0
0x1800376f9  cmp     [rsp+6D0h+var_668], 4B000h
0x180037701  jb      loc_1800377E0
0x180037707  mov     r8d, 104h; nSize
0x18003770d  lea     rdx, [rbp+5D0h+NewFileName]; lpDst
0x180037714  lea     rcx, ?g_szBackupLogFileName@@3PAGA; lpSrc
0x18003771b  call    cs:__imp_ExpandEnvironmentStringsW
0x180037721  dec     eax
0x180037723  cmp     eax, 103h
0x180037728  ja      loc_1800377E0
0x18003772e  mov     r8d, 1; dwFlags
0x180037734  lea     rdx, [rbp+5D0h+NewFileName]; lpNewFileName
0x18003773b  lea     rcx, [rsp+6D0h+FileName]; lpExistingFileName
0x180037740  call    cs:__imp_MoveFileExW
0x180037746  test    eax, eax
0x180037748  jnz     short loc_1800377AF
0x18003774a  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180037750  jz      loc_1800377E0
0x180037756  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003775d  test    rbx, rbx
0x180037760  jz      short loc_180037781
0x180037762  call    cs:__imp_GetLastError
0x180037768  lea     rdx, aMovingLogFileT; "Moving log file to backup failed with 0"...
0x18003776f  mov     ecx, 4
0x180037774  mov     r8d, eax
0x180037777  mov     rax, rbx
0x18003777a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003777f  jmp     short loc_1800377E0
0x180037781  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180037788  jz      short loc_1800377E0
0x18003778a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180037791  jz      short loc_1800377E0
0x180037793  call    cs:__imp_GetLastError
0x180037799  lea     rdx, aMovingLogFileT; "Moving log file to backup failed with 0"...
0x1800377a0  mov     ecx, 4; unsigned int
0x1800377a5  mov     r8d, eax
0x1800377a8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800377ad  jmp     short loc_1800377E0
0x1800377af  mov     eax, cs:dword_180128038
0x1800377b5  test    eax, eax
0x1800377b7  jz      short loc_1800377E0
0x1800377b9  mov     rcx, cs:qword_180128050
0x1800377c0  mov     rax, cs:qword_180128048
0x1800377c7  test    al, 1
0x1800377c9  jz      short loc_1800377E0
0x1800377cb  mov     rax, rcx
0x1800377ce  and     eax, 1
0x1800377d1  cmp     rax, rcx
0x1800377d4  jnz     short loc_1800377E0
0x1800377d6  or      cs:?g_dwDebugLevel@@3KA, 100000h; ulong g_dwDebugLevel
0x1800377e0  mov     rcx, [rbp+5D0h+var_30]
0x1800377e7  xor     rcx, rsp; StackCookie
0x1800377ea  call    __security_check_cookie
0x1800377ef  add     rsp, 6B8h
0x1800377f6  pop     rdi
0x1800377f7  pop     rsi
0x1800377f8  pop     rbx
0x1800377f9  pop     rbp
0x1800377fa  retn
```
