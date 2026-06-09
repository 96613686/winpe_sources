# BrowseInNewProcess

- ea: `0x18042d290`
- end: `0x18042d87c`
- name: `BrowseInNewProcess`
- size: `1516`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180067c94`
- `0x180209260`
- `0x1802a3b40`

## callees

- `0x180024bc4`
- `0x18042d290`
- `0x18042e5a8`
- `0x18042ebf4`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18042d36b`
- `KERNEL32!GetCurrentProcessId` at `0x18042d36b`
- `USER32!LockSetForegroundWindow` at `0x18042d3fc`
- `USER32!LockSetForegroundWindow` at `0x18042d623`
- `USER32!LockSetForegroundWindow` at `0x18042d704`
- `USER32!LockSetForegroundWindow` at `0x18042d3fc`
- `USER32!LockSetForegroundWindow` at `0x18042d623`
- `USER32!LockSetForegroundWindow` at `0x18042d704`
- `USER32!AllowSetForegroundWindow` at `0x18042d52a`
- `USER32!AllowSetForegroundWindow` at `0x18042d765`
- `USER32!AllowSetForegroundWindow` at `0x18042d52a`
- `USER32!AllowSetForegroundWindow` at `0x18042d765`
- `SHELL32!ShellExecuteExW` at `0x18042d2ff`
- `SHELL32!ShellExecuteExW` at `0x18042d2ff`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18042d417`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18042d4e9`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18042d63e`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18042d724`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18042d417`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18042d4e9`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18042d63e`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18042d724`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18042d399`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18042d399`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18042d3a8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18042d5bc`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18042d7f3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18042d3a8`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18042d5bc`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18042d7f3`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18042d37e`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18042d37e`

## pseudocode

```c
__int64 __fastcall BrowseInNewProcess(void *a1, char a2, __int64 a3)
{
  int v5; // ebx
  int v6; // eax
  struct IEUserBroker *v7; // rcx
  DWORD v8; // ecx
  void (__fastcall *v9)(struct IEUserBroker *, __int128 *); // rbx
  int v10; // eax
  DWORD v11; // ecx
  void (__fastcall *v12)(struct IEUserBroker *, __int128 *); // rbx
  struct IEUserBroker *v14; // [rsp+30h] [rbp-D0h] BYREF
  struct IEUserBroker *v15; // [rsp+38h] [rbp-C8h] BYREF
  DWORD dwProcessId[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[2088]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v20[4176]; // [rsp+1120h] [rbp+1020h] BYREF

  if ( (a2 & 1) != 0 )
  {
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.cbSize = 112;
    pExecInfo.fMask = 4;
    pExecInfo.nShow = 10;
    pExecInfo.lpIDList = a1;
    ShellExecuteExW(&pExecInfo);
    return 0;
  }
  v5 = -2147467259;
  if ( (a2 & 2) != 0 )
  {
    v5 = IEGetNameAndFlagsEx((int)a1, 0x8000, 0, (int)FileName, 0x824u, 0);
    if ( v5 >= 0 )
    {
      memset(&pExecInfo, 0, 68);
      LODWORD(pExecInfo.lpFile) = GetCurrentProcessId();
      LODWORD(pExecInfo.lpParameters) = 0;
      HIDWORD(pExecInfo.lpFile) = IsoGetIntegrity(1) & 0x7F;
      LODWORD(pExecInfo.lpDirectory) = IEConfiguration_GetDWORD(536870929);
      *(_OWORD *)(&pExecInfo.nShow + 1) = *(_OWORD *)GlobalThreadState();
      if ( *(_BYTE *)(a3 + 3)
        && (unsigned int)PathIsInternetShortcutFile(FileName)
        && (int)TargetUrlFromInternetShortcutFile(FileName) >= 0 )
      {
        if ( *(_BYTE *)(a3 + 1) )
        {
          LockSetForegroundWindow(1u);
          *(_QWORD *)dwProcessId = 0;
          v14 = 0;
          v5 = CoCreateUserBroker(&v14);
          if ( v5 < 0 )
            goto LABEL_28;
          v15 = 0;
          v5 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, struct IEUserBroker **))(*(_QWORD *)v14 + 48LL))(
                 v14,
                 &CLSID_CShdocvwBroker,
                 &IID_IUnknown,
                 &v15);
          if ( v5 >= 0 )
          {
            v5 = (**(__int64 (__fastcall ***)(struct IEUserBroker *, GUID *, DWORD *))v15)(
                   v15,
                   &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                   dwProcessId);
            (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
          }
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v14 + 16LL))(v14);
          if ( v5 < 0 )
            goto LABEL_28;
          v6 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, _BYTE *, __int64, SHELLEXECUTEINFOW *))(**(_QWORD **)dwProcessId
                                                                                                 + 32LL))(
                 *(_QWORD *)dwProcessId,
                 FileName,
                 v20,
                 4096,
                 &pExecInfo);
          v7 = *(struct IEUserBroker **)dwProcessId;
LABEL_27:
          v5 = v6;
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_28:
          LockSetForegroundWindow(2u);
          return (unsigned int)v5;
        }
        v14 = 0;
        v15 = 0;
        v5 = CoCreateUserBroker(&v15);
        if ( v5 >= 0 )
        {
          dwProcessId[0] = 0;
          (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v15 + 24LL))(
            v15,
            0,
            0,
            dwProcessId);
          v8 = -1;
          if ( dwProcessId[0] )
            v8 = dwProcessId[0];
          AllowSetForegroundWindow(v8);
          *(_QWORD *)&v17 = 0;
          v5 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v15 + 48LL))(
                 v15,
                 &CLSID_CShdocvwBroker,
                 &IID_IUnknown,
                 &v17);
          if ( v5 >= 0 )
          {
            v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IEUserBroker **))v17)(
                   v17,
                   &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                   &v14);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 16LL))(v17);
          }
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v5 >= 0 )
          {
            v9 = *(void (__fastcall **)(struct IEUserBroker *, __int128 *))(*(_QWORD *)v14 + 1256LL);
            v17 = *(_OWORD *)GlobalThreadState();
            v9(v14, &v17);
            v10 = (*(__int64 (__fastcall **)(struct IEUserBroker *, WCHAR *, _BYTE *, __int64, SHELLEXECUTEINFOW *))(*(_QWORD *)v14 + 32LL))(
                    v14,
                    FileName,
                    v20,
                    2048,
                    &pExecInfo);
LABEL_36:
            v5 = v10;
            (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
      }
      else
      {
        if ( *(_BYTE *)(a3 + 1) )
        {
          LockSetForegroundWindow(1u);
          v14 = 0;
          v15 = 0;
          v5 = CoCreateUserBroker(&v15);
          if ( v5 < 0 )
            goto LABEL_28;
          *(_QWORD *)&v17 = 0;
          v5 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v15 + 48LL))(
                 v15,
                 &CLSID_CShdocvwBroker,
                 &IID_IUnknown,
                 &v17);
          if ( v5 >= 0 )
          {
            v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IEUserBroker **))v17)(
                   v17,
                   &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                   &v14);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 16LL))(v17);
          }
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v5 < 0 )
            goto LABEL_28;
          v6 = (*(__int64 (__fastcall **)(struct IEUserBroker *, WCHAR *, __int64, SHELLEXECUTEINFOW *, _QWORD))(*(_QWORD *)v14 + 24LL))(
                 v14,
                 FileName,
                 4096,
                 &pExecInfo,
                 0);
          v7 = v14;
          goto LABEL_27;
        }
        v14 = 0;
        v15 = 0;
        v5 = CoCreateUserBroker(&v15);
        if ( v5 >= 0 )
        {
          dwProcessId[0] = 0;
          (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v15 + 24LL))(
            v15,
            0,
            0,
            dwProcessId);
          v11 = -1;
          if ( dwProcessId[0] )
            v11 = dwProcessId[0];
          AllowSetForegroundWindow(v11);
          *(_QWORD *)&v17 = 0;
          v5 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v15 + 48LL))(
                 v15,
                 &CLSID_CShdocvwBroker,
                 &IID_IUnknown,
                 &v17);
          if ( v5 >= 0 )
          {
            v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IEUserBroker **))v17)(
                   v17,
                   &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                   &v14);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 16LL))(v17);
          }
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v5 >= 0 )
          {
            v12 = *(void (__fastcall **)(struct IEUserBroker *, __int128 *))(*(_QWORD *)v14 + 1256LL);
            v17 = *(_OWORD *)GlobalThreadState();
            v12(v14, &v17);
            v10 = (*(__int64 (__fastcall **)(struct IEUserBroker *, WCHAR *, __int64, SHELLEXECUTEINFOW *, _QWORD))(*(_QWORD *)v14 + 24LL))(
                    v14,
                    FileName,
                    2048,
                    &pExecInfo,
                    0);
            goto LABEL_36;
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18042d290  mov     [rsp-8+arg_8], rbx
0x18042d295  mov     [rsp-8+arg_10], rsi
0x18042d29a  push    rbp
0x18042d29b  push    rdi
0x18042d29c  push    r14
0x18042d29e  lea     rbp, [rsp-2080h]
0x18042d2a6  mov     eax, 2180h
0x18042d2ab  call    _alloca_probe
0x18042d2b0  sub     rsp, rax
0x18042d2b3  mov     rax, cs:__security_cookie
0x18042d2ba  xor     rax, rsp
0x18042d2bd  mov     [rbp+2090h+var_20], rax
0x18042d2c4  mov     rsi, r8
0x18042d2c7  mov     r14, rcx
0x18042d2ca  test    dl, 1
0x18042d2cd  jz      short loc_18042D314
0x18042d2cf  mov     ebx, 70h ; 'p'
0x18042d2d4  lea     rcx, [rsp+2190h+pExecInfo]; void *
0x18042d2d9  mov     r8d, ebx; Size
0x18042d2dc  xor     edx, edx; Val
0x18042d2de  call    memset_0
0x18042d2e3  lea     rcx, [rsp+2190h+pExecInfo]; pExecInfo
0x18042d2e8  mov     [rsp+2190h+pExecInfo.cbSize], ebx
0x18042d2ec  mov     [rsp+2190h+pExecInfo.fMask], 4
0x18042d2f4  mov     [rbp+2090h+pExecInfo.nShow], 0Ah
0x18042d2fb  mov     [rbp+2090h+pExecInfo.lpIDList], r14
0x18042d2ff  call    cs:__imp_ShellExecuteExW
0x18042d306  nop     dword ptr [rax+rax+00h]
0x18042d30b  xor     edi, edi
0x18042d30d  mov     ebx, edi
0x18042d30f  jmp     loc_18042D852
0x18042d314  mov     ebx, 80004005h
0x18042d319  test    dl, 2
0x18042d31c  jz      loc_18042D852
0x18042d322  xor     edi, edi
0x18042d324  lea     r9, [rbp+2090h+FileName]; int
0x18042d328  mov     [rsp+2190h+var_2168], rdi; __int64
0x18042d32d  xor     r8d, r8d; int
0x18042d330  mov     edx, 8000h; int
0x18042d335  mov     [rsp+2190h+cchBuf], 824h; cchBuf
0x18042d33d  call    IEGetNameAndFlagsEx
0x18042d342  mov     ebx, eax
0x18042d344  test    eax, eax
0x18042d346  js      loc_18042D852
0x18042d34c  xorps   xmm0, xmm0
0x18042d34f  mov     qword ptr [rsp+2190h+pExecInfo.cbSize], rdi
0x18042d354  movups  xmmword ptr [rbp+2090h+pExecInfo.lpDirectory], xmm0
0x18042d358  mov     [rsp+2190h+pExecInfo.hwnd], rdi
0x18042d35d  movups  xmmword ptr [rbp+2090h+pExecInfo+34h], xmm0
0x18042d361  mov     [rsp+2190h+pExecInfo.lpVerb], rdi
0x18042d366  movups  xmmword ptr [rsp+2190h+pExecInfo.lpFile], xmm0
0x18042d36b  call    cs:__imp_GetCurrentProcessId
0x18042d372  nop     dword ptr [rax+rax+00h]
0x18042d377  lea     ecx, [rdi+1]
0x18042d37a  mov     dword ptr [rsp+2190h+pExecInfo.lpFile], eax
0x18042d37e  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18042d385  nop     dword ptr [rax+rax+00h]
0x18042d38a  mov     ecx, 20000011h
0x18042d38f  mov     dword ptr [rbp+2090h+pExecInfo.lpParameters], edi
0x18042d392  and     eax, 7Fh
0x18042d395  mov     dword ptr [rsp+2190h+pExecInfo.lpFile+4], eax
0x18042d399  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18042d3a0  nop     dword ptr [rax+rax+00h]
0x18042d3a5  mov     dword ptr [rbp+2090h+pExecInfo.lpDirectory], eax
0x18042d3a8  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18042d3af  nop     dword ptr [rax+rax+00h]
0x18042d3b4  movups  xmm0, xmmword ptr [rax]
0x18042d3b7  movdqu  xmmword ptr [rbp+2090h+pExecInfo+34h], xmm0
0x18042d3bc  cmp     [rsi+3], dil
0x18042d3c0  jz      loc_18042D614
0x18042d3c6  lea     rcx, [rbp+2090h+FileName]
0x18042d3ca  call    PathIsInternetShortcutFile
0x18042d3cf  test    eax, eax
0x18042d3d1  jz      loc_18042D614
0x18042d3d7  lea     rdx, [rbp+2090h+var_1070]
0x18042d3de  lea     rcx, [rbp+2090h+FileName]; lpFileName
0x18042d3e2  call    TargetUrlFromInternetShortcutFile
0x18042d3e7  test    eax, eax
0x18042d3e9  js      loc_18042D614
0x18042d3ef  cmp     [rsi+1], dil
0x18042d3f3  jz      loc_18042D4DA
0x18042d3f9  lea     ecx, [rdi+1]; uLockCode
0x18042d3fc  call    cs:__imp_LockSetForegroundWindow
0x18042d403  nop     dword ptr [rax+rax+00h]
0x18042d408  lea     rcx, [rsp+2190h+var_2160]
0x18042d40d  mov     qword ptr [rsp+2190h+dwProcessId], rdi
0x18042d412  mov     [rsp+2190h+var_2160], rdi
0x18042d417  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18042d41e  nop     dword ptr [rax+rax+00h]
0x18042d423  mov     ebx, eax
0x18042d425  test    eax, eax
0x18042d427  js      loc_18042D6FF
0x18042d42d  mov     rcx, [rsp+2190h+var_2160]
0x18042d432  lea     r9, [rsp+2190h+var_2158]
0x18042d437  mov     [rsp+2190h+var_2158], rdi
0x18042d43c  lea     r8, IID_IUnknown
0x18042d443  lea     rdx, CLSID_CShdocvwBroker
0x18042d44a  mov     rax, [rcx]
0x18042d44d  mov     rax, [rax+30h]
0x18042d451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d456  mov     ebx, eax
0x18042d458  test    eax, eax
0x18042d45a  js      short loc_18042D48B
0x18042d45c  mov     rcx, [rsp+2190h+var_2158]
0x18042d461  lea     r8, [rsp+2190h+dwProcessId]
0x18042d466  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18042d46d  mov     rax, [rcx]
0x18042d470  mov     rax, [rax]
0x18042d473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d478  mov     rcx, [rsp+2190h+var_2158]
0x18042d47d  mov     ebx, eax
0x18042d47f  mov     rax, [rcx]
0x18042d482  mov     rax, [rax+10h]
0x18042d486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d48b  mov     rcx, [rsp+2190h+var_2160]
0x18042d490  mov     rax, [rcx]
0x18042d493  mov     rax, [rax+10h]
0x18042d497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d49c  test    ebx, ebx
0x18042d49e  js      loc_18042D6FF
0x18042d4a4  mov     rcx, qword ptr [rsp+2190h+dwProcessId]
0x18042d4a9  lea     rdx, [rsp+2190h+pExecInfo]
0x18042d4ae  mov     qword ptr [rsp+2190h+cchBuf], rdx
0x18042d4b3  lea     r8, [rbp+2090h+var_1070]
0x18042d4ba  mov     r9d, 1000h
0x18042d4c0  lea     rdx, [rbp+2090h+FileName]
0x18042d4c4  mov     rax, [rcx]
0x18042d4c7  mov     rax, [rax+20h]
0x18042d4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d4d0  mov     rcx, qword ptr [rsp+2190h+dwProcessId]
0x18042d4d5  jmp     loc_18042D6F1
0x18042d4da  lea     rcx, [rsp+2190h+var_2158]
0x18042d4df  mov     [rsp+2190h+var_2160], rdi
0x18042d4e4  mov     [rsp+2190h+var_2158], rdi
0x18042d4e9  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18042d4f0  nop     dword ptr [rax+rax+00h]
0x18042d4f5  mov     ebx, eax
0x18042d4f7  test    eax, eax
0x18042d4f9  js      loc_18042D852
0x18042d4ff  mov     rcx, [rsp+2190h+var_2158]
0x18042d504  lea     r9, [rsp+2190h+dwProcessId]
0x18042d509  mov     [rsp+2190h+dwProcessId], edi
0x18042d50d  xor     r8d, r8d
0x18042d510  xor     edx, edx
0x18042d512  mov     rax, [rcx]
0x18042d515  mov     rax, [rax+18h]
0x18042d519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d51e  or      ecx, 0FFFFFFFFh
0x18042d521  cmp     [rsp+2190h+dwProcessId], edi
0x18042d525  cmovnz  ecx, [rsp+2190h+dwProcessId]; dwProcessId
0x18042d52a  call    cs:__imp_AllowSetForegroundWindow
0x18042d531  nop     dword ptr [rax+rax+00h]
0x18042d536  mov     rcx, [rsp+2190h+var_2158]
0x18042d53b  lea     r9, [rsp+2190h+var_2140]
0x18042d540  mov     qword ptr [rsp+2190h+var_2140], rdi
0x18042d545  lea     r8, IID_IUnknown
0x18042d54c  lea     rdx, CLSID_CShdocvwBroker
0x18042d553  mov     rax, [rcx]
0x18042d556  mov     rax, [rax+30h]
0x18042d55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d55f  mov     ebx, eax
0x18042d561  test    eax, eax
0x18042d563  js      short loc_18042D594
0x18042d565  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x18042d56a  lea     r8, [rsp+2190h+var_2160]
0x18042d56f  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18042d576  mov     rax, [rcx]
0x18042d579  mov     rax, [rax]
0x18042d57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d581  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x18042d586  mov     ebx, eax
0x18042d588  mov     rax, [rcx]
0x18042d58b  mov     rax, [rax+10h]
0x18042d58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d594  mov     rcx, [rsp+2190h+var_2158]
0x18042d599  mov     rax, [rcx]
0x18042d59c  mov     rax, [rax+10h]
0x18042d5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d5a5  test    ebx, ebx
0x18042d5a7  js      loc_18042D852
0x18042d5ad  mov     rax, [rsp+2190h+var_2160]
0x18042d5b2  mov     rcx, [rax]
0x18042d5b5  mov     rbx, [rcx+4E8h]
0x18042d5bc  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18042d5c3  nop     dword ptr [rax+rax+00h]
0x18042d5c8  mov     rcx, [rsp+2190h+var_2160]
0x18042d5cd  lea     rdx, [rsp+2190h+var_2140]
0x18042d5d2  movups  xmm0, xmmword ptr [rax]
0x18042d5d5  mov     rax, rbx
0x18042d5d8  movdqu  [rsp+2190h+var_2140], xmm0
0x18042d5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d5e3  mov     rcx, [rsp+2190h+var_2160]
0x18042d5e8  lea     rdx, [rsp+2190h+pExecInfo]
0x18042d5ed  mov     qword ptr [rsp+2190h+cchBuf], rdx
0x18042d5f2  lea     r8, [rbp+2090h+var_1070]
0x18042d5f9  mov     r9d, 800h
0x18042d5ff  lea     rdx, [rbp+2090h+FileName]
0x18042d603  mov     rax, [rcx]
0x18042d606  mov     rax, [rax+20h]
0x18042d60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d60f  jmp     loc_18042D83F
0x18042d614  cmp     [rsi+1], dil
0x18042d618  jz      loc_18042D715
0x18042d61e  mov     ecx, 1; uLockCode
0x18042d623  call    cs:__imp_LockSetForegroundWindow
0x18042d62a  nop     dword ptr [rax+rax+00h]
0x18042d62f  lea     rcx, [rsp+2190h+var_2158]
0x18042d634  mov     [rsp+2190h+var_2160], rdi
0x18042d639  mov     [rsp+2190h+var_2158], rdi
0x18042d63e  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18042d645  nop     dword ptr [rax+rax+00h]
0x18042d64a  mov     ebx, eax
0x18042d64c  test    eax, eax
0x18042d64e  js      loc_18042D6FF
0x18042d654  mov     rcx, [rsp+2190h+var_2158]
0x18042d659  lea     r9, [rsp+2190h+var_2140]
0x18042d65e  mov     qword ptr [rsp+2190h+var_2140], rdi
0x18042d663  lea     r8, IID_IUnknown
0x18042d66a  lea     rdx, CLSID_CShdocvwBroker
0x18042d671  mov     rax, [rcx]
0x18042d674  mov     rax, [rax+30h]
0x18042d678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d67d  mov     ebx, eax
0x18042d67f  test    eax, eax
0x18042d681  js      short loc_18042D6B2
0x18042d683  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x18042d688  lea     r8, [rsp+2190h+var_2160]
0x18042d68d  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18042d694  mov     rax, [rcx]
0x18042d697  mov     rax, [rax]
0x18042d69a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d69f  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x18042d6a4  mov     ebx, eax
0x18042d6a6  mov     rax, [rcx]
0x18042d6a9  mov     rax, [rax+10h]
0x18042d6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d6b2  mov     rcx, [rsp+2190h+var_2158]
0x18042d6b7  mov     rax, [rcx]
0x18042d6ba  mov     rax, [rax+10h]
0x18042d6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d6c3  test    ebx, ebx
0x18042d6c5  js      short loc_18042D6FF
0x18042d6c7  mov     rcx, [rsp+2190h+var_2160]
0x18042d6cc  lea     r9, [rsp+2190h+pExecInfo]
0x18042d6d1  mov     r8d, 1000h
0x18042d6d7  mov     qword ptr [rsp+2190h+cchBuf], rdi
0x18042d6dc  lea     rdx, [rbp+2090h+FileName]
0x18042d6e0  mov     rax, [rcx]
0x18042d6e3  mov     rax, [rax+18h]
0x18042d6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d6ec  mov     rcx, [rsp+2190h+var_2160]
0x18042d6f1  mov     ebx, eax
0x18042d6f3  mov     rax, [rcx]
0x18042d6f6  mov     rax, [rax+10h]
0x18042d6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d6ff  mov     ecx, 2; uLockCode
0x18042d704  call    cs:__imp_LockSetForegroundWindow
0x18042d70b  nop     dword ptr [rax+rax+00h]
0x18042d710  jmp     loc_18042D852
0x18042d715  lea     rcx, [rsp+2190h+var_2158]
0x18042d71a  mov     [rsp+2190h+var_2160], rdi
0x18042d71f  mov     [rsp+2190h+var_2158], rdi
0x18042d724  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18042d72b  nop     dword ptr [rax+rax+00h]
0x18042d730  mov     ebx, eax
0x18042d732  test    eax, eax
0x18042d734  js      loc_18042D852
0x18042d73a  mov     rcx, [rsp+2190h+var_2158]
0x18042d73f  lea     r9, [rsp+2190h+dwProcessId]
0x18042d744  mov     [rsp+2190h+dwProcessId], edi
0x18042d748  xor     r8d, r8d
0x18042d74b  xor     edx, edx
0x18042d74d  mov     rax, [rcx]
0x18042d750  mov     rax, [rax+18h]
0x18042d754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d759  or      ecx, 0FFFFFFFFh
0x18042d75c  cmp     [rsp+2190h+dwProcessId], edi
0x18042d760  cmovnz  ecx, [rsp+2190h+dwProcessId]; dwProcessId
0x18042d765  call    cs:__imp_AllowSetForegroundWindow
0x18042d76c  nop     dword ptr [rax+rax+00h]
0x18042d771  mov     rcx, [rsp+2190h+var_2158]
0x18042d776  lea     r9, [rsp+2190h+var_2140]
0x18042d77b  mov     qword ptr [rsp+2190h+var_2140], rdi
0x18042d780  lea     r8, IID_IUnknown
0x18042d787  lea     rdx, CLSID_CShdocvwBroker
0x18042d78e  mov     rax, [rcx]
0x18042d791  mov     rax, [rax+30h]
0x18042d795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d79a  mov     ebx, eax
0x18042d79c  test    eax, eax
0x18042d79e  js      short loc_18042D7CF
0x18042d7a0  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x18042d7a5  lea     r8, [rsp+2190h+var_2160]
0x18042d7aa  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18042d7b1  mov     rax, [rcx]
0x18042d7b4  mov     rax, [rax]
0x18042d7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18042d7bc  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x18042d7c1  mov     ebx, eax
0x18042d7c3  mov     rax, [rcx]
  ... truncated ...
```
