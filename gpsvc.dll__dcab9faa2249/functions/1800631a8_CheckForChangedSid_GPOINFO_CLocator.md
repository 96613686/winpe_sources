# CheckForChangedSid(_GPOINFO *,CLocator *)

- ea: `0x1800631a8`
- end: `0x1800639fd`
- name: `?CheckForChangedSid@@YAHPEAU_GPOINFO@@PEAVCLocator@@@Z`
- size: `2133`
- prototype: `__int64 __fastcall(struct _GPOINFO *, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005ce5c`

## callees

- `0x180003770`
- `0x18000a504`
- `0x1800246a8`
- `0x18002f6e0`
- `0x180030bcc`
- `0x1800631a8`
- `0x1800672b0`
- `0x180067d58`
- `0x180073984`
- `0x180075ec0`
- `0x18007d320`
- `0x18009d1f8`
- `0x18009d280`
- `0x18009d4a8`
- `0x18009db40`
- `0x1800a4e40`
- `0x1800b2850`
- `0x1800b397c`
- `0x1800b7494`
- `0x1800b74e0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800632ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800639ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800632ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800639ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800633e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800635ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800633e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800635ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006367d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800636c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800636d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006367d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800636c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800636d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800639bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800639bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800638c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800634e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800638c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063343`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180063343`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006347d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800638b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006347d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800638b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006328c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006328c`

## string_xrefs

- `0x180063251`: `CheckForChangedSid: GetSidString failed.`
- `0x180063274`: `CheckForChangedSid: GetSidString failed.`
- `0x180063379`: `CheckForChangedSid: Failed to open registry key with %d.`
- `0x18006339f`: `CheckForChangedSid: Failed to open registry key with %d.`
- `0x180063405`: `CheckForChangedSid: WriteSidMapping failed.`
- `0x180063433`: `CheckForChangedSid: WriteSidMapping failed.`
- `0x18006349f`: `CheckForChangedSid: RegCreateKey failed.`
- `0x1800634cd`: `CheckForChangedSid: RegCreateKey failed.`
- `0x1800638e1`: `CheckForChangedSid: RegCreateKey failed.`
- `0x180063904`: `CheckForChangedSid: RegCreateKey failed.`
- `0x180063531`: `CheckForChangedSid: MigrateMembershipData failed.`
- `0x18006355f`: `CheckForChangedSid: MigrateMembershipData failed.`
- `0x1800635ae`: `CheckForChangedSid: MigrateGPOData failed.`
- `0x1800635d1`: `CheckForChangedSid: MigrateGPOData failed.`
- `0x180063615`: `CheckForChangedSid: MigrateStatusData failed.`
- `0x18006363b`: `CheckForChangedSid: MigrateStatusData failed.`
- `0x18006377a`: `CheckForChangedSid: couldn't allocate memory.`
- `0x18006379d`: `CheckForChangedSid: couldn't allocate memory.`
- `0x1800637e6`: `CheckForChangedSid: couldn't get WMI locator.`
- `0x180063809`: `CheckForChangedSid: couldn't get WMI locator.`
- `0x18006384c`: `CheckForChangedSid: SetOldString failed.`
- `0x18006386f`: `CheckForChangedSid: SetOldString failed.`

## pseudocode

```c
__int64 __fastcall CheckForChangedSid(struct _GPOINFO *a1, LPVOID *ppv)
{
  int v4; // esi
  DWORD LastError; // ebx
  unsigned int v6; // r12d
  unsigned __int16 *SidString; // rax
  DWORD v8; // ebx
  int v9; // edi
  DWORD v10; // esi
  int v11; // edi
  unsigned int GPSourceFileId; // eax
  int *v13; // r8
  DWORD v14; // ecx
  int v16; // eax
  unsigned int v17; // eax
  const unsigned __int16 *v18; // rdx
  DWORD v19; // edi
  const unsigned __int16 *OldSidString; // rax
  const unsigned __int16 *v21; // r8
  unsigned __int16 *v22; // rdi
  const unsigned __int16 *v23; // r8
  void (*v24)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v25; // rdx
  __int64 v26; // rsi
  __int64 v27; // rax
  HLOCAL v28; // r14
  __int64 v29; // rax
  __int64 v30; // rdi
  HLOCAL v31; // rsi
  HLOCAL v32; // rax
  HLOCAL v33; // rdi
  struct IWbemLocator *WbemLocator; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  __int64 samDesired; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v39; // [rsp+68h] [rbp-98h]
  __int64 v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+78h] [rbp-88h]
  unsigned __int64 v42; // [rsp+80h] [rbp-80h]
  LPVOID *ppva; // [rsp+88h] [rbp-78h]
  void *v44; // [rsp+90h] [rbp-70h] BYREF
  void *v45; // [rsp+98h] [rbp-68h] BYREF
  void *v46; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v47[96]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[400]; // [rsp+110h] [rbp+10h] BYREF

  ppva = ppv;
  v4 = 0;
  hKey = 0;
  dwDisposition = 0;
  LastError = GetLastError();
  *((_DWORD *)a1 + 34) = 0;
  v6 = 1;
  if ( (*(_BYTE *)a1 & 1) == 0 )
  {
    SidString = (unsigned __int16 *)*((_QWORD *)a1 + 9);
    if ( !SidString )
    {
      SidString = GetSidString(*((void **)a1 + 1));
      *((_QWORD *)a1 + 9) = SidString;
      if ( !SidString )
      {
        v8 = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"CheckForChangedSid: GetSidString failed.");
          }
          else if ( g_lpDebugMsgContextInstance )
          {
            if ( g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"CheckForChangedSid: GetSidString failed.");
          }
        }
        v9 = *((_DWORD *)a1 + 64);
        v10 = GetTickCount() - v9;
        v11 = *((_DWORD *)a1 + 70);
        GPSourceFileId = GetGPSourceFileId(L"ds\\grouppolicy\\client\\gpsvc\\engine\\gpstate.cpp");
        LODWORD(samDesired) = v10;
        LODWORD(phkResult) = v11;
        CGPAdminEventInitFailure::CGPAdminEventInitFailure(
          (CGPAdminEventInitFailure *)v47,
          (__int64)&gpEvent_INTERNAL_SYSTEM_ERROR,
          GPSourceFileId,
          1918,
          (__int64)phkResult,
          samDesired,
          v8);
        CGPPolicyEventReporting::Report(*((CGPPolicyEventReporting **)a1 + 34), (struct CGPEventInfo *)v47, v13);
        CGPAdminEventInitFailure::~CGPAdminEventInitFailure((CGPAdminEventInitFailure *)v47);
        v14 = v8;
        goto LABEL_11;
      }
    }
    if ( (*(_BYTE *)a1 & 4) != 0 )
    {
      v16 = StringCchPrintfW(
              SubKey,
              0x190u,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws",
              SidString);
      if ( v16 < 0 )
      {
        v14 = (unsigned __int16)v16;
LABEL_11:
        SetLastError(v14);
        return 0;
      }
      v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      v19 = v17;
      if ( !v17 )
      {
LABEL_39:
        RegCloseKey(hKey);
        goto LABEL_108;
      }
      if ( v17 != 2 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"CheckForChangedSid: Failed to open registry key with %d.", v17);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"CheckForChangedSid: Failed to open registry key with %d.", v17);
          }
        }
        v14 = v19;
        goto LABEL_11;
      }
      OldSidString = GetOldSidString(*((HANDLE *)a1 + 1), v18);
      v22 = (unsigned __int16 *)OldSidString;
      v39 = (unsigned __int16 *)OldSidString;
      if ( !OldSidString )
      {
        if ( !(unsigned int)SetOldSidString(*((HANDLE *)a1 + 1), *((BYTE **)a1 + 9), v21) )
        {
          LastError = GetLastError();
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CheckForChangedSid: WriteSidMapping failed.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"CheckForChangedSid: WriteSidMapping failed.");
            }
          }
LABEL_107:
          v6 = v4;
          goto LABEL_108;
        }
        if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition) )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CheckForChangedSid: RegCreateKey failed.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"CheckForChangedSid: RegCreateKey failed.");
            }
          }
          goto LABEL_108;
        }
        goto LABEL_39;
      }
      DeletePolicyState(OldSidString);
      if ( (unsigned int)MigrateMembershipData(*((const unsigned __int16 **)a1 + 9), v22) )
      {
        if ( !(unsigned int)MigrateGPOData(a1, *((const unsigned __int16 **)a1 + 9), v22) )
        {
          LastError = GetLastError();
          if ( !*(_DWORD *)&g_dwDebugLevel )
            goto LABEL_88;
          v24 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"CheckForChangedSid: MigrateGPOData failed.");
            goto LABEL_88;
          }
          v25 = L"CheckForChangedSid: MigrateGPOData failed.";
          goto LABEL_44;
        }
        if ( (unsigned int)MigrateStatusData(a1, *((const unsigned __int16 **)a1 + 9), v22) )
        {
          if ( CLocator::GetWbemLocator(ppv) )
          {
            v26 = -1;
            v27 = -1;
            do
              ++v27;
            while ( v22[v27] );
            v42 = v27 + 31;
            v28 = LocalAlloc(0x40u, 2 * (v27 + 31));
            v46 = v28;
            v29 = -1;
            do
              ++v29;
            while ( v22[v29] );
            v40 = v29 + 1;
            do
              ++v26;
            while ( *(_WORD *)(*((_QWORD *)a1 + 9) + 2 * v26) );
            v30 = v26 + 1;
            v41 = v26 + 1;
            v31 = LocalAlloc(0x40u, 2 * (v29 + 1));
            v45 = v31;
            v32 = LocalAlloc(0x40u, 2 * v30);
            v33 = v32;
            v44 = v32;
            if ( v28 && v31 && v32 )
            {
              ConvertSidToWMIName(v39, v40, v31);
              ConvertSidToWMIName(*((_QWORD *)a1 + 9), v41, v33);
              StringCchPrintfW((unsigned __int16 *)v28, v42, L"\\\\.\\Root\\Rsop\\User\\%s", v31);
              WbemLocator = CLocator::GetWbemLocator(ppva);
              CreateAndCopyNameSpace(WbemLocator, 5, 0, 0);
            }
            else if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"CheckForChangedSid: couldn't allocate memory.");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"CheckForChangedSid: couldn't allocate memory.");
              }
            }
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v44);
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v45);
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v46);
            v22 = v39;
          }
          else if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CheckForChangedSid: couldn't get WMI locator.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"CheckForChangedSid: couldn't get WMI locator.");
            }
          }
          v4 = 1;
          goto LABEL_88;
        }
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v24 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"CheckForChangedSid: MigrateStatusData failed.");
            goto LABEL_88;
          }
          v25 = L"CheckForChangedSid: MigrateStatusData failed.";
LABEL_44:
          v24(2u, v25);
        }
      }
      else
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v24 = g_lpDebugMsg;
          if ( !g_lpDebugMsg )
          {
            if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              RedirectDebugMsg(2u, L"CheckForChangedSid: MigrateMembershipData failed.");
            goto LABEL_88;
          }
          v25 = L"CheckForChangedSid: MigrateMembershipData failed.";
          goto LABEL_44;
        }
      }
LABEL_88:
      if ( v4 )
      {
        if ( !(unsigned int)SetOldSidString(*((HANDLE *)a1 + 1), *((BYTE **)a1 + 9), v23) && *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"CheckForChangedSid: SetOldString failed.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"CheckForChangedSid: SetOldString failed.");
          }
        }
        if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition) )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CheckForChangedSid: RegCreateKey failed.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"CheckForChangedSid: RegCreateKey failed.");
            }
          }
        }
        else
        {
          RegCloseKey(hKey);
        }
        StringCchPrintfW(SubKey, 0x190u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws", v22);
        GPRegDelnode(HKEY_LOCAL_MACHINE, SubKey);
        StringCchPrintfW(SubKey, 0x190u, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\%ws", v22);
        GPRegDelnode(HKEY_LOCAL_MACHINE, SubKey);
        *((_DWORD *)a1 + 34) = 1;
      }
      else
      {
        StringCchPrintfW(
          SubKey,
          0x190u,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\%ws",
          *((_QWORD *)a1 + 9));
        GPRegDelnode(HKEY_LOCAL_MACHINE, SubKey);
        StringCchPrintfW(
          SubKey,
          0x190u,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\%ws",
          *((_QWORD *)a1 + 9));
        GPRegDelnode(HKEY_LOCAL_MACHINE, SubKey);
      }
      LocalFree(v22);
      goto LABEL_107;
    }
  }
LABEL_108:
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x1800631a8  mov     [rsp-8+arg_10], rbx
0x1800631ad  push    rbp
0x1800631ae  push    rsi
0x1800631af  push    rdi
0x1800631b0  push    r12
0x1800631b2  push    r13
0x1800631b4  push    r14
0x1800631b6  push    r15
0x1800631b8  lea     rbp, [rsp-340h]
0x1800631c0  sub     rsp, 440h
0x1800631c7  mov     rax, cs:__security_cookie
0x1800631ce  xor     rax, rsp
0x1800631d1  mov     [rbp+370h+var_40], rax
0x1800631d8  mov     r14, rdx
0x1800631db  mov     [rbp+370h+ppv], rdx
0x1800631df  mov     r13, rcx
0x1800631e2  xor     esi, esi
0x1800631e4  mov     [rsp+470h+hKey], rsi
0x1800631e9  mov     [rsp+470h+dwDisposition], esi
0x1800631ed  call    cs:__imp_GetLastError
0x1800631f3  mov     ebx, eax
0x1800631f5  mov     [rsp+470h+var_420], eax
0x1800631f9  mov     [r13+88h], esi
0x180063200  lea     r12d, [rsi+1]
0x180063204  test    [r13+0], r12b
0x180063208  jnz     loc_1800639C8
0x18006320e  mov     rax, [r13+48h]
0x180063212  test    rax, rax
0x180063215  jnz     loc_1800632F9
0x18006321b  mov     rcx, [r13+8]; void *
0x18006321f  call    ?GetSidString@@YAPEAGPEAX@Z; GetSidString(void *)
0x180063224  mov     [r13+48h], rax
0x180063228  test    rax, rax
0x18006322b  jnz     loc_1800632F9
0x180063231  call    cs:__imp_GetLastError
0x180063237  mov     ebx, eax
0x180063239  mov     [rsp+470h+var_420], eax
0x18006323d  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180063243  jz      short loc_180063285
0x180063245  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006324c  test    rax, rax
0x18006324f  jz      short loc_180063262
0x180063251  lea     rdx, aCheckforchange_2; "CheckForChangedSid: GetSidString failed"...
0x180063258  lea     ecx, [rsi+2]
0x18006325b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063260  jmp     short loc_180063285
0x180063262  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180063269  jz      short loc_180063285
0x18006326b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180063272  jz      short loc_180063285
0x180063274  lea     rdx, aCheckforchange_2; "CheckForChangedSid: GetSidString failed"...
0x18006327b  mov     ecx, 2; unsigned int
0x180063280  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180063285  mov     edi, [r13+100h]
0x18006328c  call    cs:__imp_GetTickCount
0x180063292  mov     esi, eax
0x180063294  sub     esi, edi
0x180063296  mov     edi, [r13+118h]
0x18006329d  lea     rcx, aDsGrouppolicyC_8; "ds\\grouppolicy\\client\\gpsvc\\engine"...
0x1800632a4  call    ?GetGPSourceFileId@@YAKPEBG@Z; GetGPSourceFileId(ushort const *)
0x1800632a9  mov     dword ptr [rsp+470h+lpSecurityAttributes], ebx
0x1800632ad  mov     [rsp+470h+samDesired], esi
0x1800632b1  mov     dword ptr [rsp+470h+phkResult], edi
0x1800632b5  mov     r9d, 77Eh
0x1800632bb  mov     r8d, eax
0x1800632be  lea     rdx, gpEvent_INTERNAL_SYSTEM_ERROR
0x1800632c5  lea     rcx, [rbp+370h+var_3C0]
0x1800632c9  call    ??0CGPAdminEventInitFailure@@QEAA@PEBU_EVENT_DESCRIPTOR@@KKW4ProcessingModeEnum@@KKPEBG@Z; CGPAdminEventInitFailure::CGPAdminEventInitFailure(_EVENT_DESCRIPTOR const *,ulong,ulong,ProcessingModeEnum,ulong,ulong,ushort const *)
0x1800632ce  nop
0x1800632cf  lea     rdx, [rbp+370h+var_3C0]; struct CGPEventInfo *
0x1800632d3  mov     rcx, [r13+110h]; this
0x1800632da  call    ?Report@CGPPolicyEventReporting@@QEAAKPEAVCGPEventInfo@@PEAH@Z; CGPPolicyEventReporting::Report(CGPEventInfo *,int *)
0x1800632df  nop
0x1800632e0  lea     rcx, [rbp+370h+var_3C0]; this
0x1800632e4  call    ??1CGPAdminEventInitFailure@@UEAA@XZ; CGPAdminEventInitFailure::~CGPAdminEventInitFailure(void)
0x1800632e9  nop
0x1800632ea  mov     ecx, ebx; dwErrCode
0x1800632ec  call    cs:__imp_SetLastError
0x1800632f2  xor     eax, eax
0x1800632f4  jmp     loc_1800639D3
0x1800632f9  test    byte ptr [r13+0], 4
0x1800632fe  jz      loc_1800639C8
0x180063304  mov     r9, rax
0x180063307  lea     r8, aSoftwareMicros_27; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006330e  mov     edx, 190h; unsigned __int64
0x180063313  lea     rcx, [rbp+370h+SubKey]; unsigned __int16 *
0x180063317  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006331c  test    eax, eax
0x18006331e  jns     short loc_180063325
0x180063320  movzx   ecx, ax
0x180063323  jmp     short loc_1800632EC
0x180063325  lea     rax, [rsp+470h+hKey]
0x18006332a  mov     [rsp+470h+phkResult], rax; phkResult
0x18006332f  mov     r9d, 20019h; samDesired
0x180063335  xor     r8d, r8d; ulOptions
0x180063338  lea     rdx, [rbp+370h+SubKey]; lpSubKey
0x18006333c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180063343  call    cs:__imp_RegOpenKeyExW
0x180063349  mov     edi, eax
0x18006334b  test    eax, eax
0x18006334d  jz      loc_1800634E1
0x180063353  mov     r15d, 2
0x180063359  cmp     eax, r15d
0x18006335c  jz      short loc_1800633B6
0x18006335e  mov     [rsp+470h+var_420], eax
0x180063362  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180063368  jz      short loc_1800633AF
0x18006336a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180063371  test    rax, rax
0x180063374  jz      short loc_18006338A
0x180063376  mov     r8d, edi
0x180063379  lea     rdx, aCheckforchange_3; "CheckForChangedSid: Failed to open regi"...
0x180063380  mov     ecx, r15d
0x180063383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063388  jmp     short loc_1800633AF
0x18006338a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180063391  jz      short loc_1800633AF
0x180063393  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006339a  jz      short loc_1800633AF
0x18006339c  mov     r8d, edi
0x18006339f  lea     rdx, aCheckforchange_3; "CheckForChangedSid: Failed to open regi"...
0x1800633a6  mov     ecx, r15d; unsigned int
0x1800633a9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800633ae  nop
0x1800633af  mov     ecx, edi
0x1800633b1  jmp     loc_1800632EC
0x1800633b6  mov     rcx, [r13+8]; hToken
0x1800633ba  call    ?GetOldSidString@@YAPEAGPEAXPEBG@Z; GetOldSidString(void *,ushort const *)
0x1800633bf  mov     rdi, rax
0x1800633c2  mov     [rsp+470h+var_408], rax
0x1800633c7  test    rax, rax
0x1800633ca  jnz     loc_1800634F1
0x1800633d0  mov     rdx, [r13+48h]; lpData
0x1800633d4  mov     rcx, [r13+8]; hToken
0x1800633d8  call    ?SetOldSidString@@YAHPEAXPEBG1@Z; SetOldSidString(void *,ushort const *,ushort const *)
0x1800633dd  test    eax, eax
0x1800633df  jnz     short loc_180063447
0x1800633e1  call    cs:__imp_GetLastError
0x1800633e7  mov     ebx, eax
0x1800633e9  mov     [rsp+470h+var_420], eax
0x1800633ed  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800633f3  jz      loc_1800639C5
0x1800633f9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180063400  test    rax, rax
0x180063403  jz      short loc_180063419
0x180063405  lea     rdx, aCheckforchange_5; "CheckForChangedSid: WriteSidMapping fai"...
0x18006340c  mov     ecx, r15d
0x18006340f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063414  jmp     loc_1800639C5
0x180063419  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180063420  jz      loc_1800639C5
0x180063426  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006342d  jz      loc_1800639C5
0x180063433  lea     rdx, aCheckforchange_5; "CheckForChangedSid: WriteSidMapping fai"...
0x18006343a  mov     ecx, r15d; unsigned int
0x18006343d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180063442  jmp     loc_1800639C5
0x180063447  lea     rax, [rsp+470h+dwDisposition]
0x18006344c  mov     [rsp+470h+lpdwDisposition], rax; lpdwDisposition
0x180063451  lea     rax, [rsp+470h+hKey]
0x180063456  mov     [rsp+470h+var_438], rax; phkResult
0x18006345b  mov     [rsp+470h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180063460  mov     [rsp+470h+samDesired], 20006h; samDesired
0x180063468  mov     dword ptr [rsp+470h+phkResult], esi; dwOptions
0x18006346c  xor     r9d, r9d; lpClass
0x18006346f  xor     r8d, r8d; Reserved
0x180063472  lea     rdx, [rbp+370h+SubKey]; lpSubKey
0x180063476  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006347d  call    cs:__imp_RegCreateKeyExW
0x180063483  test    eax, eax
0x180063485  jz      short loc_1800634E1
0x180063487  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18006348d  jz      loc_1800639C8
0x180063493  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006349a  test    rax, rax
0x18006349d  jz      short loc_1800634B3
0x18006349f  lea     rdx, aCheckforchange; "CheckForChangedSid: RegCreateKey failed"...
0x1800634a6  mov     ecx, r15d
0x1800634a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800634ae  jmp     loc_1800639C8
0x1800634b3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800634ba  jz      loc_1800639C8
0x1800634c0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800634c7  jz      loc_1800639C8
0x1800634cd  lea     rdx, aCheckforchange; "CheckForChangedSid: RegCreateKey failed"...
0x1800634d4  mov     ecx, r15d; unsigned int
0x1800634d7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800634dc  jmp     loc_1800639C8
0x1800634e1  mov     rcx, [rsp+470h+hKey]; hKey
0x1800634e6  call    cs:__imp_RegCloseKey
0x1800634ec  jmp     loc_1800639C8
0x1800634f1  mov     rcx, rdi; unsigned __int16 *
0x1800634f4  call    ?DeletePolicyState@@YAKPEBG@Z; DeletePolicyState(ushort const *)
0x1800634f9  mov     rdx, rdi; unsigned __int16 *
0x1800634fc  mov     rcx, [r13+48h]; unsigned __int16 *
0x180063500  call    ?MigrateMembershipData@@YAHPEBG0@Z; MigrateMembershipData(ushort const *,ushort const *)
0x180063505  test    eax, eax
0x180063507  jnz     short loc_180063573
0x180063509  call    cs:__imp_GetLastError
0x18006350f  mov     ebx, eax
0x180063511  mov     [rsp+470h+var_420], eax
0x180063515  xor     r14d, r14d
0x180063518  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006351f  jz      loc_18006381B
0x180063525  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006352c  test    rax, rax
0x18006352f  jz      short loc_180063545
0x180063531  lea     rdx, aCheckforchange_8; "CheckForChangedSid: MigrateMembershipDa"...
0x180063538  mov     ecx, r15d
0x18006353b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063540  jmp     loc_18006381B
0x180063545  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18006354c  jz      loc_18006381B
0x180063552  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180063559  jz      loc_18006381B
0x18006355f  lea     rdx, aCheckforchange_8; "CheckForChangedSid: MigrateMembershipDa"...
0x180063566  mov     ecx, r15d; unsigned int
0x180063569  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006356e  jmp     loc_18006381B
0x180063573  mov     r8, rdi; unsigned __int16 *
0x180063576  mov     rdx, [r13+48h]; unsigned __int16 *
0x18006357a  mov     rcx, r13; struct _GPOINFO *
0x18006357d  call    ?MigrateGPOData@@YAHPEAU_GPOINFO@@PEBG1@Z; MigrateGPOData(_GPOINFO *,ushort const *,ushort const *)
0x180063582  test    eax, eax
0x180063584  jnz     short loc_1800635DA
0x180063586  call    cs:__imp_GetLastError
0x18006358c  mov     ebx, eax
0x18006358e  mov     [rsp+470h+var_420], eax
0x180063592  xor     r14d, r14d
0x180063595  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18006359c  jz      loc_18006381B
0x1800635a2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800635a9  test    rax, rax
0x1800635ac  jz      short loc_1800635B7
0x1800635ae  lea     rdx, aCheckforchange_4; "CheckForChangedSid: MigrateGPOData fail"...
0x1800635b5  jmp     short loc_180063538
0x1800635b7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800635be  jz      loc_18006381B
0x1800635c4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800635cb  jz      loc_18006381B
0x1800635d1  lea     rdx, aCheckforchange_4; "CheckForChangedSid: MigrateGPOData fail"...
0x1800635d8  jmp     short loc_180063566
0x1800635da  mov     r8, rdi; unsigned __int16 *
0x1800635dd  mov     rdx, [r13+48h]; unsigned __int16 *
0x1800635e1  mov     rcx, r13; struct _GPOINFO *
0x1800635e4  call    ?MigrateStatusData@@YAHPEAU_GPOINFO@@PEBG1@Z; MigrateStatusData(_GPOINFO *,ushort const *,ushort const *)
0x1800635e9  test    eax, eax
0x1800635eb  jnz     short loc_180063647
0x1800635ed  call    cs:__imp_GetLastError
0x1800635f3  mov     ebx, eax
0x1800635f5  mov     [rsp+470h+var_420], eax
0x1800635f9  xor     r14d, r14d
0x1800635fc  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180063603  jz      loc_18006381B
0x180063609  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180063610  test    rax, rax
0x180063613  jz      short loc_180063621
0x180063615  lea     rdx, aCheckforchange_7; "CheckForChangedSid: MigrateStatusData f"...
0x18006361c  jmp     loc_180063538
0x180063621  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180063628  jz      loc_18006381B
0x18006362e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180063635  jz      loc_18006381B
0x18006363b  lea     rdx, aCheckforchange_7; "CheckForChangedSid: MigrateStatusData f"...
0x180063642  jmp     loc_180063566
0x180063647  mov     rcx, r14; ppv
0x18006364a  call    ?GetWbemLocator@CLocator@@QEAAPEAUIWbemLocator@@XZ; CLocator::GetWbemLocator(void)
0x18006364f  xor     r14d, r14d
0x180063652  test    rax, rax
0x180063655  jz      loc_1800637D1
0x18006365b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006365f  mov     rax, rsi
0x180063662  inc     rax
0x180063665  cmp     [rdi+rax*2], r14w
0x18006366a  jnz     short loc_180063662
0x18006366c  add     rax, 1Fh
0x180063670  mov     [rbp+370h+var_3F0], rax
0x180063674  lea     rdx, [rax+rax]; uBytes
0x180063678  mov     ecx, 40h ; '@'; uFlags
0x18006367d  call    cs:__imp_LocalAlloc
0x180063683  mov     r14, rax
0x180063686  mov     [rbp+370h+var_3D0], rax
0x18006368a  mov     rax, rsi
0x18006368d  xor     edx, edx
0x18006368f  inc     rax
0x180063692  cmp     [rdi+rax*2], dx
0x180063696  jnz     short loc_18006368F
0x180063698  lea     rcx, [rax+1]
0x18006369c  mov     [rsp+470h+var_400], rcx
0x1800636a1  mov     rax, [r13+48h]
0x1800636a5  inc     rsi
0x1800636a8  cmp     [rax+rsi*2], dx
0x1800636ac  jnz     short loc_1800636A5
0x1800636ae  lea     rdi, [rsi+1]
0x1800636b2  mov     [rsp+470h+var_3F8], rdi
0x1800636b7  lea     rdx, [rcx+rcx]; uBytes
0x1800636bb  mov     ecx, 40h ; '@'; uFlags
0x1800636c0  call    cs:__imp_LocalAlloc
0x1800636c6  mov     rsi, rax
0x1800636c9  mov     [rbp+370h+var_3D8], rax
  ... truncated ...
```
