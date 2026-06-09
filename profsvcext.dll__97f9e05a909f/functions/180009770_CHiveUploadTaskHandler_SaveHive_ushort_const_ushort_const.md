# CHiveUploadTaskHandler::_SaveHive(ushort const *,ushort const *)

- ea: `0x180009770`
- end: `0x180009a23`
- name: `?_SaveHive@CHiveUploadTaskHandler@@AEAAJPEBG0@Z`
- size: `691`
- prototype: `__int64 __fastcall(CHiveUploadTaskHandler *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180018a3c`

## callees

- `0x180002960`
- `0x1800029b0`
- `0x1800045d0`
- `0x180005558`
- `0x1800055c8`
- `0x180008b1c`
- `0x180009770`
- `0x180009a2c`
- `0x18000f220`
- `0x18000f4b0`
- `0x18000f530`
- `0x18000fca8`
- `0x18001a1e4`
- `0x18001a2c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009826`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800098d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800099bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009826`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800098d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800099bc`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x18000994a`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x18000994a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000985c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000985c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800097a6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800097a6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000979d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000979d`

## string_xrefs

- `0x1800097d0`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x18000987c`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x180009924`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x18000996a`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHiveUploadTaskHandler::_SaveHive(
        CHiveUploadTaskHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  char v5; // di
  BOOL v6; // eax
  DWORD v7; // ebx
  const wchar_t **v8; // rax
  __int64 v9; // rcx
  const wchar_t *v10; // r9
  LSTATUS v11; // eax
  int v12; // r8d
  const wchar_t **v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // r9
  int v16; // eax
  LSTATUS v17; // eax
  CHiveUploadTaskHandler *v18; // rcx
  const wchar_t **v19; // rax
  __int64 v20; // rcx
  const wchar_t *v21; // r9
  CHiveUploadTaskHandler *v22; // rcx
  int phkResult; // [rsp+20h] [rbp-40h]
  int v25; // [rsp+30h] [rbp-30h] BYREF
  __int64 v26; // [rsp+38h] [rbp-28h]
  __int64 v27; // [rsp+40h] [rbp-20h]
  int v28; // [rsp+48h] [rbp-18h]
  __int128 v29; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HLOCAL hMem; // [rsp+80h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  HIDWORD(hMem) = HIDWORD(this);
  v5 = 0;
  LODWORD(hMem) = 0;
  SetFileAttributesW(a3, 0x80u);
  v6 = DeleteFileW(a3);
  v7 = ResultFromWin32Bool(v6);
  if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147024894 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v11 = RegOpenKeyExW(HKEY_USERS, a2, 0, 0x2001Fu, &hKey);
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    if ( (v7 & 0x80000000) == 0 )
    {
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v29 = 0;
      LODWORD(hMem) = 17;
      v16 = CThreadContext::EnablePrivileges((CThreadContext *)&v25, (unsigned int *)&hMem, v12);
      v7 = v16;
      if ( v16 >= 0 )
      {
        v17 = RegSaveKeyExW(hKey, a3, 0, 1u);
        v7 = v17;
        if ( v17 > 0 )
          v7 = (unsigned __int16)v17 | 0x80070000;
        v18 = retaddr;
        if ( (v7 & 0x80000000) == 0 )
        {
          if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 8) != 0 )
            McTemplateU0z_EtwEventWriteTransfer(retaddr, EVENT_SAVE_USER_HIVE_SUCCEEDED, a3);
          CHiveUploadTaskHandler::_SetHiveAttributes(v18, a2, a3);
          CHiveUploadTaskHandler::_SaveLastUploadTime(v22, a2);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x235,
            (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
            (const char *)v7);
          if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x10) != 0 )
          {
            v19 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v7);
            v5 = 1;
            v21 = L"???";
            if ( *v19 )
              v21 = *v19;
            McTemplateU0zz_EtwEventWriteTransfer(v20, EVENT_SAVE_USER_HIVE_FAILED, a3, v21);
          }
          if ( (v5 & 1) != 0 )
            LocalFree(hMem);
        }
        CThreadContext::RevertPrivileges((CThreadContext *)&v25);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x232,
          (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
          (const char *)(unsigned int)v16);
      }
      CThreadContext::~CThreadContext((CThreadContext *)&v25);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22D,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
        (const char *)v7);
      if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x10) != 0 )
      {
        v13 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v7);
        v5 = 2;
        v15 = L"???";
        if ( *v13 )
          v15 = *v13;
        McTemplateU0zz_EtwEventWriteTransfer(v14, EVENT_OPEN_USER_ROOT_KEY_FAILED, a2, v15);
      }
      if ( (v5 & 2) != 0 )
        LocalFree(hMem);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      (const char *)v7,
      phkResult);
    if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x10) != 0 )
    {
      v8 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v7);
      v5 = 4;
      v10 = L"???";
      if ( *v8 )
        v10 = *v8;
      McTemplateU0zz_EtwEventWriteTransfer(v9, EVENT_DELETE_FILE_FAILED, a3, v10);
    }
    if ( (v5 & 4) != 0 )
      LocalFree(hMem);
  }
  return v7;
}

```

## disassembly

```asm
0x180009770  mov     [rsp-18h+arg_8], rbx
0x180009775  mov     [rsp-18h+arg_10], rsi
0x18000977a  mov     [rsp-18h+hMem], rcx
0x18000977f  push    rbp
0x180009780  push    rdi
0x180009781  push    r14
0x180009783  mov     rbp, rsp
0x180009786  sub     rsp, 60h
0x18000978a  mov     rsi, r8
0x18000978d  mov     r14, rdx
0x180009790  xor     edi, edi
0x180009792  mov     dword ptr [rbp+hMem], edi
0x180009795  mov     edx, 80h; dwFileAttributes
0x18000979a  mov     rcx, r8; lpFileName
0x18000979d  call    cs:__imp_SetFileAttributesW
0x1800097a3  mov     rcx, rsi; lpFileName
0x1800097a6  call    cs:__imp_DeleteFileW
0x1800097ac  mov     ecx, eax; int
0x1800097ae  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800097b3  mov     ebx, eax
0x1800097b5  mov     eax, 80000000h
0x1800097ba  lea     ecx, [rbx+rax]
0x1800097bd  test    eax, ecx
0x1800097bf  jnz     short loc_180009831
0x1800097c1  cmp     ebx, 80070002h
0x1800097c7  jz      short loc_180009831
0x1800097c9  mov     rcx, [rbp+18h]; this
0x1800097cd  mov     r9d, ebx; char *
0x1800097d0  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x1800097d7  mov     edx, 249h; void *
0x1800097dc  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800097e1  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 10h
0x1800097e8  jz      short loc_180009818
0x1800097ea  mov     edx, ebx; dwMessageId
0x1800097ec  lea     rcx, [rbp+hMem]; lpBuffer
0x1800097f0  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x1800097f5  mov     edi, 4
0x1800097fa  lea     r9, asc_180022B10; "???"
0x180009801  cmp     qword ptr [rax], 0
0x180009805  cmovnz  r9, [rax]
0x180009809  mov     r8, rsi
0x18000980c  lea     rdx, EVENT_DELETE_FILE_FAILED
0x180009813  call    McTemplateU0zz_EtwEventWriteTransfer
0x180009818  test    dil, 4
0x18000981c  jz      loc_180009A0C
0x180009822  mov     rcx, [rbp+hMem]; hMem
0x180009826  call    cs:__imp_LocalFree
0x18000982c  jmp     loc_180009A0C
0x180009831  mov     [rbp+hKey], rdi
0x180009835  xor     edx, edx
0x180009837  lea     rcx, [rbp+hKey]
0x18000983b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180009840  lea     rax, [rbp+hKey]
0x180009844  mov     qword ptr [rsp+60h+phkResult], rax; int
0x180009849  mov     r9d, 2001Fh; samDesired
0x18000984f  xor     r8d, r8d; ulOptions
0x180009852  mov     rdx, r14; lpSubKey
0x180009855  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000985c  call    cs:__imp_RegOpenKeyExW
0x180009862  mov     ebx, eax
0x180009864  test    eax, eax
0x180009866  jle     short loc_180009871
0x180009868  movzx   ebx, ax
0x18000986b  or      ebx, 80070000h
0x180009871  mov     rcx, [rbp+18h]; this
0x180009875  test    ebx, ebx
0x180009877  jns     short loc_1800098DD
0x180009879  mov     r9d, ebx; char *
0x18000987c  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180009883  mov     edx, 22Dh; void *
0x180009888  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000988d  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 10h
0x180009894  jz      short loc_1800098C4
0x180009896  mov     edx, ebx; dwMessageId
0x180009898  lea     rcx, [rbp+hMem]; lpBuffer
0x18000989c  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x1800098a1  mov     edi, 2
0x1800098a6  lea     r9, asc_180022B10; "???"
0x1800098ad  cmp     qword ptr [rax], 0
0x1800098b1  cmovnz  r9, [rax]
0x1800098b5  mov     r8, r14
0x1800098b8  lea     rdx, EVENT_OPEN_USER_ROOT_KEY_FAILED
0x1800098bf  call    McTemplateU0zz_EtwEventWriteTransfer
0x1800098c4  test    dil, 2
0x1800098c8  jz      loc_180009A03
0x1800098ce  mov     rcx, [rbp+hMem]; hMem
0x1800098d2  call    cs:__imp_LocalFree
0x1800098d8  jmp     loc_180009A03
0x1800098dd  mov     [rbp+var_30], 0
0x1800098e4  mov     [rbp+var_28], 0
0x1800098ec  mov     [rbp+var_20], 0
0x1800098f4  mov     [rbp+var_18], 0
0x1800098fb  xorps   xmm0, xmm0
0x1800098fe  movdqu  [rbp+var_10], xmm0
0x180009903  mov     dword ptr [rbp+hMem], 11h
0x18000990a  lea     rdx, [rbp+hMem]; unsigned int *
0x18000990e  lea     rcx, [rbp+var_30]; this
0x180009912  call    ?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z; CThreadContext::EnablePrivileges(ulong *,ulong)
0x180009917  mov     ebx, eax
0x180009919  mov     rcx, [rbp+18h]; this
0x18000991d  test    eax, eax
0x18000991f  jns     short loc_18000993A
0x180009921  mov     r9d, eax; char *
0x180009924  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18000992b  mov     edx, 232h; void *
0x180009930  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009935  jmp     loc_1800099F9
0x18000993a  mov     r9d, 1; Flags
0x180009940  xor     r8d, r8d; lpSecurityAttributes
0x180009943  mov     rdx, rsi; lpFile
0x180009946  mov     rcx, [rbp+hKey]; hKey
0x18000994a  call    cs:__imp_RegSaveKeyExW
0x180009950  mov     ebx, eax
0x180009952  test    eax, eax
0x180009954  jle     short loc_18000995F
0x180009956  movzx   ebx, ax
0x180009959  or      ebx, 80070000h
0x18000995f  mov     rcx, [rbp+18h]; this
0x180009963  test    ebx, ebx
0x180009965  jns     short loc_1800099C4
0x180009967  mov     r9d, ebx; char *
0x18000996a  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180009971  mov     edx, 235h; void *
0x180009976  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000997b  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 10h
0x180009982  jz      short loc_1800099B2
0x180009984  mov     edx, ebx; dwMessageId
0x180009986  lea     rcx, [rbp+hMem]; lpBuffer
0x18000998a  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x18000998f  mov     edi, 1
0x180009994  lea     r9, asc_180022B10; "???"
0x18000999b  cmp     qword ptr [rax], 0
0x18000999f  cmovnz  r9, [rax]
0x1800099a3  mov     r8, rsi
0x1800099a6  lea     rdx, EVENT_SAVE_USER_HIVE_FAILED
0x1800099ad  call    McTemplateU0zz_EtwEventWriteTransfer
0x1800099b2  test    dil, 1
0x1800099b6  jz      short loc_1800099EF
0x1800099b8  mov     rcx, [rbp+hMem]; hMem
0x1800099bc  call    cs:__imp_LocalFree
0x1800099c2  jmp     short loc_1800099EF
0x1800099c4  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 8
0x1800099cb  jz      short loc_1800099DC
0x1800099cd  mov     r8, rsi
0x1800099d0  lea     rdx, EVENT_SAVE_USER_HIVE_SUCCEEDED
0x1800099d7  call    McTemplateU0z_EtwEventWriteTransfer
0x1800099dc  mov     r8, rsi; unsigned __int16 *
0x1800099df  mov     rdx, r14; unsigned __int16 *
0x1800099e2  call    ?_SetHiveAttributes@CHiveUploadTaskHandler@@AEAAJPEBG0@Z; CHiveUploadTaskHandler::_SetHiveAttributes(ushort const *,ushort const *)
0x1800099e7  mov     rdx, r14; unsigned __int16 *
0x1800099ea  call    ?_SaveLastUploadTime@CHiveUploadTaskHandler@@AEAAJPEBG@Z; CHiveUploadTaskHandler::_SaveLastUploadTime(ushort const *)
0x1800099ef  lea     rcx, [rbp+var_30]; this
0x1800099f3  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x1800099f8  nop
0x1800099f9  lea     rcx, [rbp+var_30]; this
0x1800099fd  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180009a02  nop
0x180009a03  lea     rcx, [rbp+hKey]
0x180009a07  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009a0c  mov     eax, ebx
0x180009a0e  lea     r11, [rsp+60h+var_s0]
0x180009a13  mov     rbx, [r11+28h]
0x180009a17  mov     rsi, [r11+30h]
0x180009a1b  mov     rsp, r11
0x180009a1e  pop     r14
0x180009a20  pop     rdi
0x180009a21  pop     rbp
0x180009a22  retn
```
