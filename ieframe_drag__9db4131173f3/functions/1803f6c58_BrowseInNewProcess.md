# BrowseInNewProcess

- ea: `0x1803f6c58`
- end: `0x1803f71e3`
- name: `BrowseInNewProcess`
- size: `1419`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800632a8`
- `0x1801ef744`
- `0x180281f28`

## callees

- `0x18002320c`
- `0x1803f6c58`
- `0x1803f7e48`
- `0x1803f8430`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1803f6d2d`
- `KERNEL32!GetCurrentProcessId` at `0x1803f6d2d`
- `USER32!LockSetForegroundWindow` at `0x1803f6da6`
- `USER32!LockSetForegroundWindow` at `0x1803f6faf`
- `USER32!LockSetForegroundWindow` at `0x1803f7084`
- `USER32!LockSetForegroundWindow` at `0x1803f6da6`
- `USER32!LockSetForegroundWindow` at `0x1803f6faf`
- `USER32!LockSetForegroundWindow` at `0x1803f7084`
- `USER32!AllowSetForegroundWindow` at `0x1803f6ec2`
- `USER32!AllowSetForegroundWindow` at `0x1803f70d9`
- `USER32!AllowSetForegroundWindow` at `0x1803f6ec2`
- `USER32!AllowSetForegroundWindow` at `0x1803f70d9`
- `SHELL32!ShellExecuteExW` at `0x1803f6cc7`
- `SHELL32!ShellExecuteExW` at `0x1803f6cc7`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803f6dbb`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803f6e87`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803f6fc4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803f709e`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803f6dbb`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803f6e87`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803f6fc4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1803f709e`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1803f6d4f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1803f6d4f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803f6d58`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803f6f4e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803f7161`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803f6d58`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803f6f4e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1803f7161`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1803f6d3a`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x1803f6d3a`

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
0x1803f6c58  mov     [rsp-8+arg_8], rbx
0x1803f6c5d  mov     [rsp-8+arg_10], rsi
0x1803f6c62  push    rbp
0x1803f6c63  push    rdi
0x1803f6c64  push    r14
0x1803f6c66  lea     rbp, [rsp-2080h]
0x1803f6c6e  mov     eax, 2180h
0x1803f6c73  call    _alloca_probe
0x1803f6c78  sub     rsp, rax
0x1803f6c7b  mov     rax, cs:__security_cookie
0x1803f6c82  xor     rax, rsp
0x1803f6c85  mov     [rbp+2090h+var_20], rax
0x1803f6c8c  mov     rsi, r8
0x1803f6c8f  mov     r14, rcx
0x1803f6c92  test    dl, 1
0x1803f6c95  jz      short loc_1803F6CD6
0x1803f6c97  mov     ebx, 70h ; 'p'
0x1803f6c9c  lea     rcx, [rsp+2190h+pExecInfo]; void *
0x1803f6ca1  mov     r8d, ebx; Size
0x1803f6ca4  xor     edx, edx; Val
0x1803f6ca6  call    memset_0
0x1803f6cab  lea     rcx, [rsp+2190h+pExecInfo]; pExecInfo
0x1803f6cb0  mov     [rsp+2190h+pExecInfo.cbSize], ebx
0x1803f6cb4  mov     [rsp+2190h+pExecInfo.fMask], 4
0x1803f6cbc  mov     [rbp+2090h+pExecInfo.nShow], 0Ah
0x1803f6cc3  mov     [rbp+2090h+pExecInfo.lpIDList], r14
0x1803f6cc7  call    cs:__imp_ShellExecuteExW
0x1803f6ccd  xor     edi, edi
0x1803f6ccf  mov     ebx, edi
0x1803f6cd1  jmp     loc_1803F71BA
0x1803f6cd6  mov     ebx, 80004005h
0x1803f6cdb  test    dl, 2
0x1803f6cde  jz      loc_1803F71BA
0x1803f6ce4  xor     edi, edi
0x1803f6ce6  lea     r9, [rbp+2090h+FileName]; int
0x1803f6cea  mov     [rsp+2190h+var_2168], rdi; __int64
0x1803f6cef  xor     r8d, r8d; int
0x1803f6cf2  mov     edx, 8000h; int
0x1803f6cf7  mov     [rsp+2190h+cchBuf], 824h; cchBuf
0x1803f6cff  call    IEGetNameAndFlagsEx
0x1803f6d04  mov     ebx, eax
0x1803f6d06  test    eax, eax
0x1803f6d08  js      loc_1803F71BA
0x1803f6d0e  xorps   xmm0, xmm0
0x1803f6d11  mov     qword ptr [rsp+2190h+pExecInfo.cbSize], rdi
0x1803f6d16  movups  xmmword ptr [rbp+2090h+pExecInfo.lpDirectory], xmm0
0x1803f6d1a  mov     [rsp+2190h+pExecInfo.hwnd], rdi
0x1803f6d1f  movups  xmmword ptr [rbp+2090h+pExecInfo+34h], xmm0
0x1803f6d23  mov     [rsp+2190h+pExecInfo.lpVerb], rdi
0x1803f6d28  movups  xmmword ptr [rsp+2190h+pExecInfo.lpFile], xmm0
0x1803f6d2d  call    cs:__imp_GetCurrentProcessId
0x1803f6d33  lea     ecx, [rdi+1]
0x1803f6d36  mov     dword ptr [rsp+2190h+pExecInfo.lpFile], eax
0x1803f6d3a  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x1803f6d40  mov     ecx, 20000011h
0x1803f6d45  mov     dword ptr [rbp+2090h+pExecInfo.lpParameters], edi
0x1803f6d48  and     eax, 7Fh
0x1803f6d4b  mov     dword ptr [rsp+2190h+pExecInfo.lpFile+4], eax
0x1803f6d4f  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1803f6d55  mov     dword ptr [rbp+2090h+pExecInfo.lpDirectory], eax
0x1803f6d58  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1803f6d5e  movups  xmm0, xmmword ptr [rax]
0x1803f6d61  movdqu  xmmword ptr [rbp+2090h+pExecInfo+34h], xmm0
0x1803f6d66  cmp     [rsi+3], dil
0x1803f6d6a  jz      loc_1803F6FA0
0x1803f6d70  lea     rcx, [rbp+2090h+FileName]
0x1803f6d74  call    PathIsInternetShortcutFile
0x1803f6d79  test    eax, eax
0x1803f6d7b  jz      loc_1803F6FA0
0x1803f6d81  lea     rdx, [rbp+2090h+var_1070]
0x1803f6d88  lea     rcx, [rbp+2090h+FileName]; lpFileName
0x1803f6d8c  call    TargetUrlFromInternetShortcutFile
0x1803f6d91  test    eax, eax
0x1803f6d93  js      loc_1803F6FA0
0x1803f6d99  cmp     [rsi+1], dil
0x1803f6d9d  jz      loc_1803F6E78
0x1803f6da3  lea     ecx, [rdi+1]; uLockCode
0x1803f6da6  call    cs:__imp_LockSetForegroundWindow
0x1803f6dac  lea     rcx, [rsp+2190h+var_2160]
0x1803f6db1  mov     qword ptr [rsp+2190h+dwProcessId], rdi
0x1803f6db6  mov     [rsp+2190h+var_2160], rdi
0x1803f6dbb  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1803f6dc1  mov     ebx, eax
0x1803f6dc3  test    eax, eax
0x1803f6dc5  js      loc_1803F707F
0x1803f6dcb  mov     rcx, [rsp+2190h+var_2160]
0x1803f6dd0  lea     r9, [rsp+2190h+var_2158]
0x1803f6dd5  mov     [rsp+2190h+var_2158], rdi
0x1803f6dda  lea     r8, IID_IUnknown
0x1803f6de1  lea     rdx, CLSID_CShdocvwBroker
0x1803f6de8  mov     rax, [rcx]
0x1803f6deb  mov     rax, [rax+30h]
0x1803f6def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6df4  mov     ebx, eax
0x1803f6df6  test    eax, eax
0x1803f6df8  js      short loc_1803F6E29
0x1803f6dfa  mov     rcx, [rsp+2190h+var_2158]
0x1803f6dff  lea     r8, [rsp+2190h+dwProcessId]
0x1803f6e04  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1803f6e0b  mov     rax, [rcx]
0x1803f6e0e  mov     rax, [rax]
0x1803f6e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6e16  mov     rcx, [rsp+2190h+var_2158]
0x1803f6e1b  mov     ebx, eax
0x1803f6e1d  mov     rax, [rcx]
0x1803f6e20  mov     rax, [rax+10h]
0x1803f6e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6e29  mov     rcx, [rsp+2190h+var_2160]
0x1803f6e2e  mov     rax, [rcx]
0x1803f6e31  mov     rax, [rax+10h]
0x1803f6e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6e3a  test    ebx, ebx
0x1803f6e3c  js      loc_1803F707F
0x1803f6e42  mov     rcx, qword ptr [rsp+2190h+dwProcessId]
0x1803f6e47  lea     rdx, [rsp+2190h+pExecInfo]
0x1803f6e4c  mov     qword ptr [rsp+2190h+cchBuf], rdx
0x1803f6e51  lea     r8, [rbp+2090h+var_1070]
0x1803f6e58  mov     r9d, 1000h
0x1803f6e5e  lea     rdx, [rbp+2090h+FileName]
0x1803f6e62  mov     rax, [rcx]
0x1803f6e65  mov     rax, [rax+20h]
0x1803f6e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6e6e  mov     rcx, qword ptr [rsp+2190h+dwProcessId]
0x1803f6e73  jmp     loc_1803F7071
0x1803f6e78  lea     rcx, [rsp+2190h+var_2158]
0x1803f6e7d  mov     [rsp+2190h+var_2160], rdi
0x1803f6e82  mov     [rsp+2190h+var_2158], rdi
0x1803f6e87  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1803f6e8d  mov     ebx, eax
0x1803f6e8f  test    eax, eax
0x1803f6e91  js      loc_1803F71BA
0x1803f6e97  mov     rcx, [rsp+2190h+var_2158]
0x1803f6e9c  lea     r9, [rsp+2190h+dwProcessId]
0x1803f6ea1  mov     [rsp+2190h+dwProcessId], edi
0x1803f6ea5  xor     r8d, r8d
0x1803f6ea8  xor     edx, edx
0x1803f6eaa  mov     rax, [rcx]
0x1803f6ead  mov     rax, [rax+18h]
0x1803f6eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6eb6  or      ecx, 0FFFFFFFFh
0x1803f6eb9  cmp     [rsp+2190h+dwProcessId], edi
0x1803f6ebd  cmovnz  ecx, [rsp+2190h+dwProcessId]; dwProcessId
0x1803f6ec2  call    cs:__imp_AllowSetForegroundWindow
0x1803f6ec8  mov     rcx, [rsp+2190h+var_2158]
0x1803f6ecd  lea     r9, [rsp+2190h+var_2140]
0x1803f6ed2  mov     qword ptr [rsp+2190h+var_2140], rdi
0x1803f6ed7  lea     r8, IID_IUnknown
0x1803f6ede  lea     rdx, CLSID_CShdocvwBroker
0x1803f6ee5  mov     rax, [rcx]
0x1803f6ee8  mov     rax, [rax+30h]
0x1803f6eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6ef1  mov     ebx, eax
0x1803f6ef3  test    eax, eax
0x1803f6ef5  js      short loc_1803F6F26
0x1803f6ef7  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x1803f6efc  lea     r8, [rsp+2190h+var_2160]
0x1803f6f01  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1803f6f08  mov     rax, [rcx]
0x1803f6f0b  mov     rax, [rax]
0x1803f6f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6f13  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x1803f6f18  mov     ebx, eax
0x1803f6f1a  mov     rax, [rcx]
0x1803f6f1d  mov     rax, [rax+10h]
0x1803f6f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6f26  mov     rcx, [rsp+2190h+var_2158]
0x1803f6f2b  mov     rax, [rcx]
0x1803f6f2e  mov     rax, [rax+10h]
0x1803f6f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6f37  test    ebx, ebx
0x1803f6f39  js      loc_1803F71BA
0x1803f6f3f  mov     rax, [rsp+2190h+var_2160]
0x1803f6f44  mov     rcx, [rax]
0x1803f6f47  mov     rbx, [rcx+4E8h]
0x1803f6f4e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1803f6f54  mov     rcx, [rsp+2190h+var_2160]
0x1803f6f59  lea     rdx, [rsp+2190h+var_2140]
0x1803f6f5e  movups  xmm0, xmmword ptr [rax]
0x1803f6f61  mov     rax, rbx
0x1803f6f64  movdqu  [rsp+2190h+var_2140], xmm0
0x1803f6f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6f6f  mov     rcx, [rsp+2190h+var_2160]
0x1803f6f74  lea     rdx, [rsp+2190h+pExecInfo]
0x1803f6f79  mov     qword ptr [rsp+2190h+cchBuf], rdx
0x1803f6f7e  lea     r8, [rbp+2090h+var_1070]
0x1803f6f85  mov     r9d, 800h
0x1803f6f8b  lea     rdx, [rbp+2090h+FileName]
0x1803f6f8f  mov     rax, [rcx]
0x1803f6f92  mov     rax, [rax+20h]
0x1803f6f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6f9b  jmp     loc_1803F71A7
0x1803f6fa0  cmp     [rsi+1], dil
0x1803f6fa4  jz      loc_1803F708F
0x1803f6faa  mov     ecx, 1; uLockCode
0x1803f6faf  call    cs:__imp_LockSetForegroundWindow
0x1803f6fb5  lea     rcx, [rsp+2190h+var_2158]
0x1803f6fba  mov     [rsp+2190h+var_2160], rdi
0x1803f6fbf  mov     [rsp+2190h+var_2158], rdi
0x1803f6fc4  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1803f6fca  mov     ebx, eax
0x1803f6fcc  test    eax, eax
0x1803f6fce  js      loc_1803F707F
0x1803f6fd4  mov     rcx, [rsp+2190h+var_2158]
0x1803f6fd9  lea     r9, [rsp+2190h+var_2140]
0x1803f6fde  mov     qword ptr [rsp+2190h+var_2140], rdi
0x1803f6fe3  lea     r8, IID_IUnknown
0x1803f6fea  lea     rdx, CLSID_CShdocvwBroker
0x1803f6ff1  mov     rax, [rcx]
0x1803f6ff4  mov     rax, [rax+30h]
0x1803f6ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f6ffd  mov     ebx, eax
0x1803f6fff  test    eax, eax
0x1803f7001  js      short loc_1803F7032
0x1803f7003  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x1803f7008  lea     r8, [rsp+2190h+var_2160]
0x1803f700d  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1803f7014  mov     rax, [rcx]
0x1803f7017  mov     rax, [rax]
0x1803f701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f701f  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x1803f7024  mov     ebx, eax
0x1803f7026  mov     rax, [rcx]
0x1803f7029  mov     rax, [rax+10h]
0x1803f702d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f7032  mov     rcx, [rsp+2190h+var_2158]
0x1803f7037  mov     rax, [rcx]
0x1803f703a  mov     rax, [rax+10h]
0x1803f703e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f7043  test    ebx, ebx
0x1803f7045  js      short loc_1803F707F
0x1803f7047  mov     rcx, [rsp+2190h+var_2160]
0x1803f704c  lea     r9, [rsp+2190h+pExecInfo]
0x1803f7051  mov     r8d, 1000h
0x1803f7057  mov     qword ptr [rsp+2190h+cchBuf], rdi
0x1803f705c  lea     rdx, [rbp+2090h+FileName]
0x1803f7060  mov     rax, [rcx]
0x1803f7063  mov     rax, [rax+18h]
0x1803f7067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f706c  mov     rcx, [rsp+2190h+var_2160]
0x1803f7071  mov     ebx, eax
0x1803f7073  mov     rax, [rcx]
0x1803f7076  mov     rax, [rax+10h]
0x1803f707a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f707f  mov     ecx, 2; uLockCode
0x1803f7084  call    cs:__imp_LockSetForegroundWindow
0x1803f708a  jmp     loc_1803F71BA
0x1803f708f  lea     rcx, [rsp+2190h+var_2158]
0x1803f7094  mov     [rsp+2190h+var_2160], rdi
0x1803f7099  mov     [rsp+2190h+var_2158], rdi
0x1803f709e  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1803f70a4  mov     ebx, eax
0x1803f70a6  test    eax, eax
0x1803f70a8  js      loc_1803F71BA
0x1803f70ae  mov     rcx, [rsp+2190h+var_2158]
0x1803f70b3  lea     r9, [rsp+2190h+dwProcessId]
0x1803f70b8  mov     [rsp+2190h+dwProcessId], edi
0x1803f70bc  xor     r8d, r8d
0x1803f70bf  xor     edx, edx
0x1803f70c1  mov     rax, [rcx]
0x1803f70c4  mov     rax, [rax+18h]
0x1803f70c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f70cd  or      ecx, 0FFFFFFFFh
0x1803f70d0  cmp     [rsp+2190h+dwProcessId], edi
0x1803f70d4  cmovnz  ecx, [rsp+2190h+dwProcessId]; dwProcessId
0x1803f70d9  call    cs:__imp_AllowSetForegroundWindow
0x1803f70df  mov     rcx, [rsp+2190h+var_2158]
0x1803f70e4  lea     r9, [rsp+2190h+var_2140]
0x1803f70e9  mov     qword ptr [rsp+2190h+var_2140], rdi
0x1803f70ee  lea     r8, IID_IUnknown
0x1803f70f5  lea     rdx, CLSID_CShdocvwBroker
0x1803f70fc  mov     rax, [rcx]
0x1803f70ff  mov     rax, [rax+30h]
0x1803f7103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f7108  mov     ebx, eax
0x1803f710a  test    eax, eax
0x1803f710c  js      short loc_1803F713D
0x1803f710e  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x1803f7113  lea     r8, [rsp+2190h+var_2160]
0x1803f7118  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1803f711f  mov     rax, [rcx]
0x1803f7122  mov     rax, [rax]
0x1803f7125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f712a  mov     rcx, qword ptr [rsp+2190h+var_2140]
0x1803f712f  mov     ebx, eax
0x1803f7131  mov     rax, [rcx]
0x1803f7134  mov     rax, [rax+10h]
0x1803f7138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f713d  mov     rcx, [rsp+2190h+var_2158]
0x1803f7142  mov     rax, [rcx]
0x1803f7145  mov     rax, [rax+10h]
0x1803f7149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803f714e  test    ebx, ebx
0x1803f7150  js      short loc_1803F71BA
0x1803f7152  mov     rax, [rsp+2190h+var_2160]
0x1803f7157  mov     rcx, [rax]
0x1803f715a  mov     rbx, [rcx+4E8h]
0x1803f7161  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1803f7167  mov     rcx, [rsp+2190h+var_2160]
0x1803f716c  lea     rdx, [rsp+2190h+var_2140]
0x1803f7171  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
