# CUserProfile::SaveTempHive(int *)

- ea: `0x180013144`
- end: `0x1800133cb`
- name: `?SaveTempHive@CUserProfile@@IEAAJPEAH@Z`
- size: `647`
- prototype: `__int64 __fastcall(CUserProfile *__hidden this, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800066cc`

## callees

- `0x18000d030`
- `0x18000e1a0`
- `0x180013144`
- `0x180013770`
- `0x18001378c`
- `0x18001c358`
- `0x18002df68`
- `0x180030ad0`
- `0x180031060`
- `0x180042880`
- `0x180049e10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001318e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001318e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180013230`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180013230`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x18001324d`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x18001324d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800132d8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001332c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001332c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180013220`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800132e8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180013220`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800132e8`

## string_xrefs

- `0x1800131ab`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800131fa`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x1800132f8`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`
- `0x180013340`: `onecore\ds\security\gina\profile\profsvc\profile.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfile::SaveTempHive(CUserProfile *this, int *a2)
{
  const WCHAR *v4; // rdx
  char v5; // si
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r8
  int v9; // eax
  LSTATUS v10; // ebx
  void *v11; // rdx
  DWORD v12; // edx
  const wchar_t **v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // r8
  const WCHAR *v16; // rcx
  const char *v17; // r9
  void *v18; // rdx
  __int64 v19; // rcx
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
  if ( v6 == 2 )
    goto LABEL_25;
  if ( !v6 )
  {
    v8 = *((_QWORD *)this + 19);
    memset(lpFileName, 0, sizeof(lpFileName));
    v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
           lpFileName,
           L"%s\\%s",
           v8,
           L"ntuser.tmp");
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F0,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        (const char *)(unsigned int)v9,
        phkResult);
LABEL_6:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
      goto LABEL_26;
    }
    DeleteFileW(lpFileName[0]);
    RegFlushKey(hKey);
    v10 = RegSaveKeyExW(hKey, lpFileName[0], 0, 1u);
    if ( v10 )
    {
      v11 = (void *)*((_QWORD *)this + 3);
      v23 = 0;
      v27 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      if ( CThreadContext::ImpersonateUser((CThreadContext *)&v23, v11) >= 0 )
      {
        if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 1) != 0 )
        {
          if ( v10 > 0 )
            v12 = (unsigned __int16)v10 | 0x80070000;
          else
            v12 = v10;
          v13 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v12);
          v15 = L"???";
          if ( *v13 )
            v15 = *v13;
          McTemplateU0z_EtwEventWriteTransfer(v14, EVENT_FAILED_HIVE_UNLOAD, v15);
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
             (const char *)(unsigned int)v10,
             phkResult);
      CThreadContext::~CThreadContext((CThreadContext *)&v23);
      goto LABEL_6;
    }
    v16 = lpFileName[0];
    *a2 = 1;
    if ( !SetFileAttributesW(v16, 0x22u) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0xA0A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
        v17);
    v18 = (void *)*((_QWORD *)this + 3);
    v23 = 0;
    v27 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    if ( CThreadContext::ImpersonateUser((CThreadContext *)&v23, v18) >= 0
      && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 2) != 0 )
    {
      McTemplateU0z_EtwEventWriteTransfer(v19, EVENT_HIVE_SAVED, *((_QWORD *)this + 6));
    }
    CThreadContext::~CThreadContext((CThreadContext *)&v23);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
LABEL_25:
    v7 = 0;
    goto LABEL_26;
  }
  v7 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x9EC,
         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profile.cpp",
         (const char *)v6,
         phkResult);
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v7;
}

```

## disassembly

```asm
0x180013144  mov     [rsp-28h+arg_10], rbx
0x180013149  push    rbp
0x18001314a  push    rsi
0x18001314b  push    rdi
0x18001314c  push    r12
0x18001314e  push    r15
0x180013150  mov     rbp, rsp
0x180013153  sub     rsp, 80h
0x18001315a  xor     r12d, r12d
0x18001315d  lea     rax, [rbp+hKey]
0x180013161  mov     dword ptr [rbp+hKey], r12d
0x180013165  mov     r15, rdx
0x180013168  mov     [rdx], r12d
0x18001316b  mov     rdi, rcx
0x18001316e  mov     rdx, [rcx+30h]; lpSubKey
0x180013172  mov     r9d, 0F003Fh; samDesired
0x180013178  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001317f  mov     [rbp+hKey], r12
0x180013183  xor     r8d, r8d; ulOptions
0x180013186  mov     qword ptr [rsp+80h+phkResult], rax; unsigned int
0x18001318b  mov     esi, r12d
0x18001318e  call    cs:__imp_RegOpenKeyExW
0x180013195  nop     dword ptr [rax+rax+00h]
0x18001319a  cmp     eax, 2
0x18001319d  jz      loc_1800133A5
0x1800131a3  test    eax, eax
0x1800131a5  jz      short loc_1800131C6
0x1800131a7  mov     rcx, [rbp+28h]; this
0x1800131ab  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800131b2  mov     r9d, eax; char *
0x1800131b5  mov     edx, 9ECh; void *
0x1800131ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800131bf  mov     ebx, eax
0x1800131c1  jmp     loc_1800133A8
0x1800131c6  mov     r8, [rdi+98h]
0x1800131cd  lea     r9, ?c_szNTUserTmp@@3QBGB; "ntuser.tmp"
0x1800131d4  lea     rdx, aSS_0; "%s\\%s"
0x1800131db  mov     [rbp+lpFileName], r12
0x1800131df  lea     rcx, [rbp+lpFileName]
0x1800131e3  mov     [rbp+var_48], r12
0x1800131e7  mov     [rbp+var_40], r12
0x1800131eb  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800131f0  mov     ebx, eax
0x1800131f2  test    eax, eax
0x1800131f4  jns     short loc_18001321C
0x1800131f6  mov     rcx, [rbp+28h]; this
0x1800131fa  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013201  mov     r9d, eax; char *
0x180013204  mov     edx, 9F0h; void *
0x180013209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001320e  lea     rcx, [rbp+lpFileName]
0x180013212  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013217  jmp     loc_1800133A8
0x18001321c  mov     rcx, [rbp+lpFileName]; lpFileName
0x180013220  call    cs:__imp_DeleteFileW
0x180013227  nop     dword ptr [rax+rax+00h]
0x18001322c  mov     rcx, [rbp+hKey]; hKey
0x180013230  call    cs:__imp_RegFlushKey
0x180013237  nop     dword ptr [rax+rax+00h]
0x18001323c  mov     rdx, [rbp+lpFileName]; lpFile
0x180013240  mov     r9d, 1; Flags
0x180013246  mov     rcx, [rbp+hKey]; hKey
0x18001324a  xor     r8d, r8d; lpSecurityAttributes
0x18001324d  call    cs:__imp_RegSaveKeyExW
0x180013254  nop     dword ptr [rax+rax+00h]
0x180013259  mov     ebx, eax
0x18001325b  test    eax, eax
0x18001325d  jz      loc_18001331C
0x180013263  mov     rdx, [rdi+18h]; void *
0x180013267  lea     rcx, [rbp+var_38]; this
0x18001326b  xorps   xmm0, xmm0
0x18001326e  mov     [rbp+var_38], r12d
0x180013272  movdqu  [rbp+var_18], xmm0
0x180013277  mov     [rbp+var_30], r12
0x18001327b  mov     [rbp+var_28], r12
0x18001327f  mov     [rbp+var_20], r12d
0x180013283  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180013288  test    eax, eax
0x18001328a  js      short loc_1800132E4
0x18001328c  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 1
0x180013293  jz      short loc_1800132CE
0x180013295  test    ebx, ebx
0x180013297  jg      short loc_18001329D
0x180013299  mov     edx, ebx
0x18001329b  jmp     short loc_1800132A6
0x18001329d  movzx   edx, bx
0x1800132a0  or      edx, 80070000h; dwMessageId
0x1800132a6  lea     rcx, [rbp+hMem]; lpBuffer
0x1800132aa  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x1800132af  lea     r8, asc_180063710; "???"
0x1800132b6  lea     rdx, EVENT_FAILED_HIVE_UNLOAD
0x1800132bd  cmp     [rax], r12
0x1800132c0  cmovnz  r8, [rax]
0x1800132c4  call    McTemplateU0z_EtwEventWriteTransfer
0x1800132c9  mov     esi, 1
0x1800132ce  test    sil, 1
0x1800132d2  jz      short loc_1800132E4
0x1800132d4  mov     rcx, [rbp+hMem]; hMem
0x1800132d8  call    cs:__imp_LocalFree
0x1800132df  nop     dword ptr [rax+rax+00h]
0x1800132e4  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800132e8  call    cs:__imp_DeleteFileW
0x1800132ef  nop     dword ptr [rax+rax+00h]
0x1800132f4  mov     rcx, [rbp+28h]; this
0x1800132f8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800132ff  mov     r9d, ebx; char *
0x180013302  mov     edx, 0A03h; void *
0x180013307  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001330c  lea     rcx, [rbp+var_38]; this
0x180013310  mov     ebx, eax
0x180013312  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180013317  jmp     loc_18001320E
0x18001331c  mov     rcx, [rbp+lpFileName]; lpFileName
0x180013320  mov     edx, 22h ; '"'; dwFileAttributes
0x180013325  mov     dword ptr [r15], 1
0x18001332c  call    cs:__imp_SetFileAttributesW
0x180013333  nop     dword ptr [rax+rax+00h]
0x180013338  test    eax, eax
0x18001333a  jnz     short loc_180013351
0x18001333c  mov     rcx, [rbp+28h]; this
0x180013340  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\gina\\profile\\p"...
0x180013347  mov     edx, 0A0Ah; void *
0x18001334c  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180013351  mov     rdx, [rdi+18h]; void *
0x180013355  lea     rcx, [rbp+var_38]; this
0x180013359  xorps   xmm0, xmm0
0x18001335c  mov     [rbp+var_38], r12d
0x180013360  movdqu  [rbp+var_18], xmm0
0x180013365  mov     [rbp+var_30], r12
0x180013369  mov     [rbp+var_28], r12
0x18001336d  mov     [rbp+var_20], r12d
0x180013371  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180013376  test    eax, eax
0x180013378  js      short loc_180013393
0x18001337a  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 2
0x180013381  jz      short loc_180013393
0x180013383  mov     r8, [rdi+30h]
0x180013387  lea     rdx, EVENT_HIVE_SAVED
0x18001338e  call    McTemplateU0z_EtwEventWriteTransfer
0x180013393  lea     rcx, [rbp+var_38]; this
0x180013397  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x18001339c  lea     rcx, [rbp+lpFileName]
0x1800133a0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800133a5  mov     ebx, r12d
0x1800133a8  lea     rcx, [rbp+hKey]
0x1800133ac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800133b1  mov     eax, ebx
0x1800133b3  mov     rbx, [rsp+80h+arg_10]
0x1800133bb  add     rsp, 80h
0x1800133c2  pop     r15
0x1800133c4  pop     r12
0x1800133c6  pop     rdi
0x1800133c7  pop     rsi
0x1800133c8  pop     rbp
0x1800133c9  retn
```
