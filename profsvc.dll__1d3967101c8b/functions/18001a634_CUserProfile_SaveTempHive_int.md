# CUserProfile::SaveTempHive(int *)

- ea: `0x18001a634`
- end: `0x18001a8a1`
- name: `?SaveTempHive@CUserProfile@@IEAAJPEAH@Z`
- size: `621`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009320`

## callees

- `0x180010f30`
- `0x1800111a0`
- `0x180018bcc`
- `0x18001a634`
- `0x18001a8a8`
- `0x18002d2d8`
- `0x18002e648`
- `0x180030558`
- `0x180040e94`
- `0x180047cbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a67e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a67e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a882`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18001a722`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18001a722`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x18001a739`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x18001a739`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a7be`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a806`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a806`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a718`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a7c8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a718`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a7c8`

## string_xrefs

- `0x18001a695`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001a6f5`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001a7d2`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x18001a814`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::SaveTempHive(CUserProfile *this, int *a2)
{
  const WCHAR *v4; // rdx
  char v5; // si
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // r8
  int v10; // eax
  LSTATUS v11; // ebx
  void *v12; // rdx
  DWORD v13; // edx
  const wchar_t **v14; // rax
  __int64 v15; // rcx
  const wchar_t *v16; // r8
  const WCHAR *v17; // rcx
  const char *v18; // r9
  void *v19; // rdx
  __int64 v20; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  LPCWSTR lpFileName[3]; // [rsp+30h] [rbp-50h] BYREF
  int v23; // [rsp+48h] [rbp-38h] BYREF
  __int64 v24; // [rsp+50h] [rbp-30h]
  __int64 v25; // [rsp+58h] [rbp-28h]
  int v26; // [rsp+60h] [rbp-20h]
  __int128 v27; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HKEY hKey; // [rsp+B0h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp+38h] BYREF

  LODWORD(hKey) = 0;
  *a2 = 0;
  v4 = (const WCHAR *)*((_QWORD *)this + 6);
  hKey = 0;
  v5 = 0;
  v6 = RegOpenKeyExW(HKEY_USERS, v4, 0, 0xF003Fu, &hKey);
  if ( v6 != 2 )
  {
    if ( v6 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x9EC,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
             (const char *)v6,
             phkResult);
LABEL_4:
      if ( hKey )
        RegCloseKey(hKey);
      return v7;
    }
    v9 = *((_QWORD *)this + 19);
    memset(lpFileName, 0, sizeof(lpFileName));
    v10 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            lpFileName,
            L"%s\\%s",
            v9,
            L"ntuser.tmp");
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F0,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v10,
        phkResult);
LABEL_9:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
      goto LABEL_4;
    }
    DeleteFileW(lpFileName[0]);
    RegFlushKey(hKey);
    v11 = RegSaveKeyExW(hKey, lpFileName[0], 0, 1u);
    if ( v11 )
    {
      v12 = (void *)*((_QWORD *)this + 3);
      v23 = 0;
      v27 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      if ( CThreadContext::ImpersonateUser((CThreadContext *)&v23, v12) >= 0 )
      {
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
        {
          if ( v11 > 0 )
            v13 = (unsigned __int16)v11 | 0x80070000;
          else
            v13 = v11;
          v14 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v13);
          v16 = L"???";
          if ( *v14 )
            v16 = *v14;
          McTemplateU0z_EtwEventWriteTransfer(v15, EVENT_FAILED_HIVE_UNLOAD, v16);
          v5 = 1;
        }
        if ( (v5 & 1) != 0 )
          LocalFree(hMem);
      }
      DeleteFileW(lpFileName[0]);
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xA03,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
             (const char *)(unsigned int)v11,
             phkResult);
      CThreadContext::~CThreadContext((CThreadContext *)&v23);
      goto LABEL_9;
    }
    v17 = lpFileName[0];
    *a2 = 1;
    if ( !SetFileAttributesW(v17, 0x22u) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xA0A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        v18);
    v19 = (void *)*((_QWORD *)this + 3);
    v23 = 0;
    v27 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    if ( CThreadContext::ImpersonateUser((CThreadContext *)&v23, v19) >= 0
      && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 2) != 0 )
    {
      McTemplateU0z_EtwEventWriteTransfer(v20, EVENT_HIVE_SAVED, *((_QWORD *)this + 6));
    }
    CThreadContext::~CThreadContext((CThreadContext *)&v23);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001a634  mov     [rsp-28h+arg_10], rbx
0x18001a639  push    rbp
0x18001a63a  push    rsi
0x18001a63b  push    rdi
0x18001a63c  push    r12
0x18001a63e  push    r15
0x18001a640  mov     rbp, rsp
0x18001a643  sub     rsp, 80h
0x18001a64a  xor     r12d, r12d
0x18001a64d  lea     rax, [rbp+hKey]
0x18001a651  mov     dword ptr [rbp+hKey], r12d
0x18001a655  mov     r15, rdx
0x18001a658  mov     [rdx], r12d
0x18001a65b  mov     rdi, rcx
0x18001a65e  mov     rdx, [rcx+30h]; lpSubKey
0x18001a662  mov     r9d, 0F003Fh; samDesired
0x18001a668  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001a66f  mov     [rbp+hKey], r12
0x18001a673  xor     r8d, r8d; ulOptions
0x18001a676  mov     qword ptr [rsp+80h+phkResult], rax; unsigned int
0x18001a67b  mov     esi, r12d
0x18001a67e  call    cs:__imp_RegOpenKeyExW
0x18001a684  cmp     eax, 2
0x18001a687  jz      loc_18001A879
0x18001a68d  test    eax, eax
0x18001a68f  jz      short loc_18001A6C1
0x18001a691  mov     rcx, [rbp+28h]; this
0x18001a695  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a69c  mov     r9d, eax; char *
0x18001a69f  mov     edx, 9ECh; void *
0x18001a6a4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001a6a9  mov     ebx, eax
0x18001a6ab  mov     rcx, [rbp+hKey]; hKey
0x18001a6af  test    rcx, rcx
0x18001a6b2  jz      short loc_18001A6BA
0x18001a6b4  call    cs:__imp_RegCloseKey
0x18001a6ba  mov     eax, ebx
0x18001a6bc  jmp     loc_18001A88A
0x18001a6c1  mov     r8, [rdi+98h]
0x18001a6c8  lea     r9, ?c_szNTUserTmp@@3QBGB; "ntuser.tmp"
0x18001a6cf  lea     rdx, aSS_0; "%s\\%s"
0x18001a6d6  mov     [rbp+lpFileName], r12
0x18001a6da  lea     rcx, [rbp+lpFileName]
0x18001a6de  mov     [rbp+var_48], r12
0x18001a6e2  mov     [rbp+var_40], r12
0x18001a6e6  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001a6eb  mov     ebx, eax
0x18001a6ed  test    eax, eax
0x18001a6ef  jns     short loc_18001A714
0x18001a6f1  mov     rcx, [rbp+28h]; this
0x18001a6f5  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a6fc  mov     r9d, eax; char *
0x18001a6ff  mov     edx, 9F0h; void *
0x18001a704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a709  lea     rcx, [rbp+lpFileName]
0x18001a70d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a712  jmp     short loc_18001A6AB
0x18001a714  mov     rcx, [rbp+lpFileName]; lpFileName
0x18001a718  call    cs:__imp_DeleteFileW
0x18001a71e  mov     rcx, [rbp+hKey]; hKey
0x18001a722  call    cs:__imp_RegFlushKey
0x18001a728  mov     rdx, [rbp+lpFileName]; lpFile
0x18001a72c  mov     r9d, 1; Flags
0x18001a732  mov     rcx, [rbp+hKey]; hKey
0x18001a736  xor     r8d, r8d; lpSecurityAttributes
0x18001a739  call    cs:__imp_RegSaveKeyExW
0x18001a73f  mov     ebx, eax
0x18001a741  test    eax, eax
0x18001a743  jz      loc_18001A7F6
0x18001a749  mov     rdx, [rdi+18h]; void *
0x18001a74d  lea     rcx, [rbp+var_38]; this
0x18001a751  xorps   xmm0, xmm0
0x18001a754  mov     [rbp+var_38], r12d
0x18001a758  movdqu  [rbp+var_18], xmm0
0x18001a75d  mov     [rbp+var_30], r12
0x18001a761  mov     [rbp+var_28], r12
0x18001a765  mov     [rbp+var_20], r12d
0x18001a769  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18001a76e  test    eax, eax
0x18001a770  js      short loc_18001A7C4
0x18001a772  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x18001a779  jz      short loc_18001A7B4
0x18001a77b  test    ebx, ebx
0x18001a77d  jg      short loc_18001A783
0x18001a77f  mov     edx, ebx
0x18001a781  jmp     short loc_18001A78C
0x18001a783  movzx   edx, bx
0x18001a786  or      edx, 80070000h; dwMessageId
0x18001a78c  lea     rcx, [rbp+hMem]; lpBuffer
0x18001a790  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18001a795  lea     r8, asc_180060EA8; "???"
0x18001a79c  lea     rdx, EVENT_FAILED_HIVE_UNLOAD
0x18001a7a3  cmp     [rax], r12
0x18001a7a6  cmovnz  r8, [rax]
0x18001a7aa  call    McTemplateU0z_EtwEventWriteTransfer
0x18001a7af  mov     esi, 1
0x18001a7b4  test    sil, 1
0x18001a7b8  jz      short loc_18001A7C4
0x18001a7ba  mov     rcx, [rbp+hMem]; hMem
0x18001a7be  call    cs:__imp_LocalFree
0x18001a7c4  mov     rcx, [rbp+lpFileName]; lpFileName
0x18001a7c8  call    cs:__imp_DeleteFileW
0x18001a7ce  mov     rcx, [rbp+28h]; this
0x18001a7d2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a7d9  mov     r9d, ebx; char *
0x18001a7dc  mov     edx, 0A03h; void *
0x18001a7e1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001a7e6  lea     rcx, [rbp+var_38]; this
0x18001a7ea  mov     ebx, eax
0x18001a7ec  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001a7f1  jmp     loc_18001A709
0x18001a7f6  mov     rcx, [rbp+lpFileName]; lpFileName
0x18001a7fa  mov     edx, 22h ; '"'; dwFileAttributes
0x18001a7ff  mov     dword ptr [r15], 1
0x18001a806  call    cs:__imp_SetFileAttributesW
0x18001a80c  test    eax, eax
0x18001a80e  jnz     short loc_18001A825
0x18001a810  mov     rcx, [rbp+28h]; this
0x18001a814  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001a81b  mov     edx, 0A0Ah; void *
0x18001a820  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001a825  mov     rdx, [rdi+18h]; void *
0x18001a829  lea     rcx, [rbp+var_38]; this
0x18001a82d  xorps   xmm0, xmm0
0x18001a830  mov     [rbp+var_38], r12d
0x18001a834  movdqu  [rbp+var_18], xmm0
0x18001a839  mov     [rbp+var_30], r12
0x18001a83d  mov     [rbp+var_28], r12
0x18001a841  mov     [rbp+var_20], r12d
0x18001a845  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x18001a84a  test    eax, eax
0x18001a84c  js      short loc_18001A867
0x18001a84e  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 2
0x18001a855  jz      short loc_18001A867
0x18001a857  mov     r8, [rdi+30h]
0x18001a85b  lea     rdx, EVENT_HIVE_SAVED
0x18001a862  call    McTemplateU0z_EtwEventWriteTransfer
0x18001a867  lea     rcx, [rbp+var_38]; this
0x18001a86b  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001a870  lea     rcx, [rbp+lpFileName]
0x18001a874  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a879  mov     rcx, [rbp+hKey]; hKey
0x18001a87d  test    rcx, rcx
0x18001a880  jz      short loc_18001A888
0x18001a882  call    cs:__imp_RegCloseKey
0x18001a888  xor     eax, eax
0x18001a88a  mov     rbx, [rsp+80h+arg_10]
0x18001a892  add     rsp, 80h
0x18001a899  pop     r15
0x18001a89b  pop     r12
0x18001a89d  pop     rdi
0x18001a89e  pop     rsi
0x18001a89f  pop     rbp
0x18001a8a0  retn
```
