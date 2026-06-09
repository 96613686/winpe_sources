# _DualEngineBrowseInNewProcess(_ITEMIDLIST_ABSOLUTE const *,ulong,tagTABWINDOWDATA *)

- ea: `0x180184270`
- end: `0x1801847f1`
- name: `?_DualEngineBrowseInNewProcess@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAUtagTABWINDOWDATA@@@Z`
- size: `1409`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST_ABSOLUTE *, unsigned int, struct tagTABWINDOWDATA *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800632a8`

## callees

- `0x18002320c`
- `0x1800be898`
- `0x180104e3c`
- `0x180184270`
- `0x1803f7e48`
- `0x1803f8430`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18018430e`
- `KERNEL32!GetCurrentProcessId` at `0x18018430e`
- `USER32!LockSetForegroundWindow` at `0x1801843af`
- `USER32!LockSetForegroundWindow` at `0x1801845c4`
- `USER32!LockSetForegroundWindow` at `0x18018469d`
- `USER32!LockSetForegroundWindow` at `0x1801843af`
- `USER32!LockSetForegroundWindow` at `0x1801845c4`
- `USER32!LockSetForegroundWindow` at `0x18018469d`
- `USER32!AllowSetForegroundWindow` at `0x1801844d4`
- `USER32!AllowSetForegroundWindow` at `0x1801846f2`
- `USER32!AllowSetForegroundWindow` at `0x1801844d4`
- `USER32!AllowSetForegroundWindow` at `0x1801846f2`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801843c4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180184499`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801845d9`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801846b7`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801843c4`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180184499`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801845d9`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801846b7`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180184332`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180184332`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801842a1`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801842a1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18018433b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18018455d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180184777`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18018433b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18018455d`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180184777`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18018431e`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18018431e`

## pseudocode

```c
__int64 __fastcall _DualEngineBrowseInNewProcess(
        const struct _ITEMIDLIST_ABSOLUTE *a1,
        __int64 a2,
        struct tagTABWINDOWDATA *a3)
{
  int v4; // ebx
  const char *v5; // r9
  int v6; // ebx
  int OpenerCookie; // eax
  bool v8; // zf
  int v9; // eax
  struct IEUserBroker *v10; // rcx
  DWORD v11; // ecx
  void (__fastcall *v12)(struct IEUserBroker *, __int128 *); // rbx
  int v13; // eax
  DWORD v14; // ecx
  void (__fastcall *v15)(struct IEUserBroker *, __int128 *); // rbx
  struct IEUserBroker *v17; // [rsp+40h] [rbp-C0h] BYREF
  struct IEUserBroker *v18; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwProcessId[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v21[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v22; // [rsp+88h] [rbp-78h]
  _DWORD v23[10]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v24[4]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR FileName[2088]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v26[4176]; // [rsp+1150h] [rbp+1050h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+21D8h] [rbp+20D8h]

  v4 = (int)a1;
  if ( !IsDualEngineProcess() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x49A,
      (unsigned int)"inetcore\\ieframe\\shdocvw\\hlframe.cpp",
      v5);
  v6 = IEGetNameAndFlagsEx(v4, 0x8000, 0, (int)FileName, 0x824u, 0);
  if ( v6 >= 0 )
  {
    memset(v21, 0, sizeof(v21));
    memset(v23, 0, 28);
    v22 = 0;
    LODWORD(v22) = GetCurrentProcessId();
    *(_QWORD *)((char *)&v22 + 4) = IsoGetIntegrity(1) & 0x7F;
    v23[0] = IEConfiguration_GetDWORD(536870929);
    *(_OWORD *)&v23[3] = *(_OWORD *)GlobalThreadState();
    memset(v24, 0, 60);
    OpenerCookie = DualEngine::GetOpenerCookie();
    v8 = *((_BYTE *)a3 + 1) == 0;
    LODWORD(v24[0]) = OpenerCookie;
    DWORD2(v24[0]) = !v8;
    if ( *((_BYTE *)a3 + 3)
      && (unsigned int)PathIsInternetShortcutFile(FileName)
      && (int)TargetUrlFromInternetShortcutFile(FileName) >= 0 )
    {
      if ( *((_BYTE *)a3 + 1) )
      {
        LockSetForegroundWindow(1u);
        *(_QWORD *)dwProcessId = 0;
        v17 = 0;
        v6 = CoCreateUserBroker(&v17);
        if ( v6 < 0 )
          goto LABEL_27;
        v18 = 0;
        v6 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, struct IEUserBroker **))(*(_QWORD *)v17 + 48LL))(
               v17,
               &CLSID_CShdocvwBroker,
               &IID_IUnknown,
               &v18);
        if ( v6 >= 0 )
        {
          v6 = (**(__int64 (__fastcall ***)(struct IEUserBroker *, GUID *, DWORD *))v18)(
                 v18,
                 &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                 dwProcessId);
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v18 + 16LL))(v18);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v17 + 16LL))(v17);
        if ( v6 < 0 )
          goto LABEL_27;
        v9 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, _BYTE *, __int64, _QWORD *, _OWORD *))(**(_QWORD **)dwProcessId
                                                                                              + 40LL))(
               *(_QWORD *)dwProcessId,
               FileName,
               v26,
               4096,
               v21,
               v24);
        v10 = *(struct IEUserBroker **)dwProcessId;
LABEL_26:
        v6 = v9;
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_27:
        LockSetForegroundWindow(2u);
        return (unsigned int)v6;
      }
      v17 = 0;
      v18 = 0;
      v6 = CoCreateUserBroker(&v18);
      if ( v6 >= 0 )
      {
        dwProcessId[0] = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v18 + 24LL))(
          v18,
          0,
          0,
          dwProcessId);
        v11 = -1;
        if ( dwProcessId[0] )
          v11 = dwProcessId[0];
        AllowSetForegroundWindow(v11);
        *(_QWORD *)&v20 = 0;
        v6 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v18 + 48LL))(
               v18,
               &CLSID_CShdocvwBroker,
               &IID_IUnknown,
               &v20);
        if ( v6 >= 0 )
        {
          v6 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IEUserBroker **))v20)(
                 v20,
                 &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                 &v17);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 16LL))(v20);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v6 >= 0 )
        {
          v12 = *(void (__fastcall **)(struct IEUserBroker *, __int128 *))(*(_QWORD *)v17 + 56LL);
          v20 = *(_OWORD *)GlobalThreadState();
          v12(v17, &v20);
          v13 = (*(__int64 (__fastcall **)(struct IEUserBroker *, WCHAR *, _BYTE *, __int64, _QWORD *, _OWORD *))(*(_QWORD *)v17 + 40LL))(
                  v17,
                  FileName,
                  v26,
                  2048,
                  v21,
                  v24);
LABEL_35:
          v6 = v13;
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
    }
    else
    {
      if ( *((_BYTE *)a3 + 1) )
      {
        LockSetForegroundWindow(1u);
        v17 = 0;
        v18 = 0;
        v6 = CoCreateUserBroker(&v18);
        if ( v6 < 0 )
          goto LABEL_27;
        *(_QWORD *)&v20 = 0;
        v6 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v18 + 48LL))(
               v18,
               &CLSID_CShdocvwBroker,
               &IID_IUnknown,
               &v20);
        if ( v6 >= 0 )
        {
          v6 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IEUserBroker **))v20)(
                 v20,
                 &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                 &v17);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 16LL))(v20);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v6 < 0 )
          goto LABEL_27;
        v9 = (*(__int64 (__fastcall **)(struct IEUserBroker *, WCHAR *, __int64, _QWORD *, _OWORD *))(*(_QWORD *)v17 + 32LL))(
               v17,
               FileName,
               4096,
               v21,
               v24);
        v10 = v17;
        goto LABEL_26;
      }
      v17 = 0;
      v18 = 0;
      v6 = CoCreateUserBroker(&v18);
      if ( v6 >= 0 )
      {
        dwProcessId[0] = 0;
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD, _QWORD, DWORD *))(*(_QWORD *)v18 + 24LL))(
          v18,
          0,
          0,
          dwProcessId);
        v14 = -1;
        if ( dwProcessId[0] )
          v14 = dwProcessId[0];
        AllowSetForegroundWindow(v14);
        *(_QWORD *)&v20 = 0;
        v6 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int128 *))(*(_QWORD *)v18 + 48LL))(
               v18,
               &CLSID_CShdocvwBroker,
               &IID_IUnknown,
               &v20);
        if ( v6 >= 0 )
        {
          v6 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IEUserBroker **))v20)(
                 v20,
                 &GUID_14272506_7d5c_46df_9233_0e98de2e5f14,
                 &v17);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 16LL))(v20);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v6 >= 0 )
        {
          v15 = *(void (__fastcall **)(struct IEUserBroker *, __int128 *))(*(_QWORD *)v17 + 56LL);
          v20 = *(_OWORD *)GlobalThreadState();
          v15(v17, &v20);
          v13 = (*(__int64 (__fastcall **)(struct IEUserBroker *, WCHAR *, __int64, _QWORD *, _OWORD *))(*(_QWORD *)v17 + 32LL))(
                  v17,
                  FileName,
                  2048,
                  v21,
                  v24);
          goto LABEL_35;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180184270  push    rbp
0x180184272  push    rbx
0x180184273  push    rsi
0x180184274  push    rdi
0x180184275  lea     rbp, [rsp-20B8h]
0x18018427d  mov     eax, 21B8h
0x180184282  call    _alloca_probe
0x180184287  sub     rsp, rax
0x18018428a  mov     rax, cs:__security_cookie
0x180184291  xor     rax, rsp
0x180184294  mov     [rbp+20D0h+var_30], rax
0x18018429b  mov     rdi, r8
0x18018429e  mov     rbx, rcx
0x1801842a1  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801842a7  xor     esi, esi
0x1801842a9  test    al, al
0x1801842ab  jnz     short loc_1801842C6
0x1801842ad  mov     rcx, [rbp+20D8h]; this
0x1801842b4  lea     r8, aInetcoreIefram_35; "inetcore\\ieframe\\shdocvw\\hlframe.cpp"
0x1801842bb  mov     edx, 49Ah; void *
0x1801842c0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1801842c6  mov     [rsp+21D0h+var_21A8], rsi; __int64
0x1801842cb  lea     r9, [rbp+20D0h+FileName]; int
0x1801842cf  xor     r8d, r8d; int
0x1801842d2  mov     [rsp+21D0h+cchBuf], 824h; cchBuf
0x1801842da  mov     edx, 8000h; int
0x1801842df  mov     rcx, rbx; int
0x1801842e2  call    IEGetNameAndFlagsEx
0x1801842e7  mov     ebx, eax
0x1801842e9  test    eax, eax
0x1801842eb  js      loc_1801847D4
0x1801842f1  xorps   xmm0, xmm0
0x1801842f4  mov     [rsp+21D0h+var_2160], rsi
0x1801842f9  movups  xmmword ptr [rbp+20D0h+var_2138], xmm0
0x1801842fd  mov     [rsp+21D0h+var_2158], rsi
0x180184302  movups  xmmword ptr [rbp+20D0h+var_2138+0Ch], xmm0
0x180184306  mov     [rbp+20D0h+var_2150], rsi
0x18018430a  movups  [rbp+20D0h+var_2148], xmm0
0x18018430e  call    cs:__imp_GetCurrentProcessId
0x180184314  mov     ebx, 1
0x180184319  mov     dword ptr [rbp+20D0h+var_2148], eax
0x18018431c  mov     ecx, ebx
0x18018431e  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180184324  mov     ecx, 20000011h
0x180184329  mov     dword ptr [rbp+20D0h+var_2148+8], esi
0x18018432c  and     eax, 7Fh
0x18018432f  mov     dword ptr [rbp+20D0h+var_2148+4], eax
0x180184332  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180184338  mov     [rbp+20D0h+var_2138], eax
0x18018433b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180184341  xorps   xmm1, xmm1
0x180184344  movups  xmm0, xmmword ptr [rax]
0x180184347  movups  xmmword ptr [rbp+20D0h+var_20F0], xmm1
0x18018434b  movdqu  xmmword ptr [rbp+20D0h+var_2138+0Ch], xmm0
0x180184350  movups  [rbp+20D0h+var_2110], xmm1
0x180184354  movups  [rbp+20D0h+var_2100], xmm1
0x180184358  movups  xmmword ptr [rbp+20D0h+var_20F0+0Ch], xmm1
0x18018435c  call    DualEngine__GetOpenerCookie
0x180184361  cmp     [rdi+1], sil
0x180184365  mov     dword ptr [rbp+20D0h+var_2110], eax
0x180184368  mov     eax, esi
0x18018436a  setnz   al
0x18018436d  mov     dword ptr [rbp+20D0h+var_2110+8], eax
0x180184370  cmp     [rdi+3], sil
0x180184374  jz      loc_1801845B8
0x18018437a  lea     rcx, [rbp+20D0h+FileName]
0x18018437e  call    PathIsInternetShortcutFile
0x180184383  test    eax, eax
0x180184385  jz      loc_1801845B8
0x18018438b  lea     rdx, [rbp+20D0h+var_1080]
0x180184392  lea     rcx, [rbp+20D0h+FileName]; lpFileName
0x180184396  call    TargetUrlFromInternetShortcutFile
0x18018439b  test    eax, eax
0x18018439d  js      loc_1801845B8
0x1801843a3  cmp     [rdi+1], sil
0x1801843a7  jz      loc_18018448A
0x1801843ad  mov     ecx, ebx; uLockCode
0x1801843af  call    cs:__imp_LockSetForegroundWindow
0x1801843b5  lea     rcx, [rsp+21D0h+var_2190]
0x1801843ba  mov     qword ptr [rsp+21D0h+dwProcessId], rsi
0x1801843bf  mov     [rsp+21D0h+var_2190], rsi
0x1801843c4  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801843ca  mov     ebx, eax
0x1801843cc  test    eax, eax
0x1801843ce  js      loc_180184698
0x1801843d4  mov     rcx, [rsp+21D0h+var_2190]
0x1801843d9  lea     r9, [rsp+21D0h+var_2188]
0x1801843de  mov     [rsp+21D0h+var_2188], rsi
0x1801843e3  lea     r8, IID_IUnknown
0x1801843ea  lea     rdx, CLSID_CShdocvwBroker
0x1801843f1  mov     rax, [rcx]
0x1801843f4  mov     rax, [rax+30h]
0x1801843f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801843fd  mov     ebx, eax
0x1801843ff  test    eax, eax
0x180184401  js      short loc_180184432
0x180184403  mov     rcx, [rsp+21D0h+var_2188]
0x180184408  lea     r8, [rsp+21D0h+dwProcessId]
0x18018440d  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180184414  mov     rax, [rcx]
0x180184417  mov     rax, [rax]
0x18018441a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018441f  mov     rcx, [rsp+21D0h+var_2188]
0x180184424  mov     ebx, eax
0x180184426  mov     rax, [rcx]
0x180184429  mov     rax, [rax+10h]
0x18018442d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184432  mov     rcx, [rsp+21D0h+var_2190]
0x180184437  mov     rax, [rcx]
0x18018443a  mov     rax, [rax+10h]
0x18018443e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184443  test    ebx, ebx
0x180184445  js      loc_180184698
0x18018444b  mov     rcx, qword ptr [rsp+21D0h+dwProcessId]
0x180184450  lea     rdx, [rbp+20D0h+var_2110]
0x180184454  mov     [rsp+21D0h+var_21A8], rdx
0x180184459  lea     r8, [rbp+20D0h+var_1080]
0x180184460  lea     rdx, [rsp+21D0h+var_2160]
0x180184465  mov     r9d, 1000h
0x18018446b  mov     qword ptr [rsp+21D0h+cchBuf], rdx
0x180184470  lea     rdx, [rbp+20D0h+FileName]
0x180184474  mov     rax, [rcx]
0x180184477  mov     rax, [rax+28h]
0x18018447b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184480  mov     rcx, qword ptr [rsp+21D0h+dwProcessId]
0x180184485  jmp     loc_18018468A
0x18018448a  lea     rcx, [rsp+21D0h+var_2188]
0x18018448f  mov     [rsp+21D0h+var_2190], rsi
0x180184494  mov     [rsp+21D0h+var_2188], rsi
0x180184499  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18018449f  mov     ebx, eax
0x1801844a1  test    eax, eax
0x1801844a3  js      loc_1801847D4
0x1801844a9  mov     rcx, [rsp+21D0h+var_2188]
0x1801844ae  lea     r9, [rsp+21D0h+dwProcessId]
0x1801844b3  mov     [rsp+21D0h+dwProcessId], esi
0x1801844b7  xor     r8d, r8d
0x1801844ba  xor     edx, edx
0x1801844bc  mov     rax, [rcx]
0x1801844bf  mov     rax, [rax+18h]
0x1801844c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801844c8  mov     eax, [rsp+21D0h+dwProcessId]
0x1801844cc  or      ecx, 0FFFFFFFFh
0x1801844cf  test    eax, eax
0x1801844d1  cmovnz  ecx, eax; dwProcessId
0x1801844d4  call    cs:__imp_AllowSetForegroundWindow
0x1801844da  mov     rcx, [rsp+21D0h+var_2188]
0x1801844df  lea     r9, [rsp+21D0h+var_2170]
0x1801844e4  mov     qword ptr [rsp+21D0h+var_2170], rsi
0x1801844e9  lea     r8, IID_IUnknown
0x1801844f0  lea     rdx, CLSID_CShdocvwBroker
0x1801844f7  mov     rax, [rcx]
0x1801844fa  mov     rax, [rax+30h]
0x1801844fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184503  mov     ebx, eax
0x180184505  test    eax, eax
0x180184507  js      short loc_180184538
0x180184509  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x18018450e  lea     r8, [rsp+21D0h+var_2190]
0x180184513  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x18018451a  mov     rax, [rcx]
0x18018451d  mov     rax, [rax]
0x180184520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184525  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x18018452a  mov     ebx, eax
0x18018452c  mov     rax, [rcx]
0x18018452f  mov     rax, [rax+10h]
0x180184533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184538  mov     rcx, [rsp+21D0h+var_2188]
0x18018453d  mov     rax, [rcx]
0x180184540  mov     rax, [rax+10h]
0x180184544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184549  test    ebx, ebx
0x18018454b  js      loc_1801847D4
0x180184551  mov     rax, [rsp+21D0h+var_2190]
0x180184556  mov     rcx, [rax]
0x180184559  mov     rbx, [rcx+38h]
0x18018455d  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180184563  mov     rcx, [rsp+21D0h+var_2190]
0x180184568  lea     rdx, [rsp+21D0h+var_2170]
0x18018456d  movups  xmm0, xmmword ptr [rax]
0x180184570  mov     rax, rbx
0x180184573  movdqu  [rsp+21D0h+var_2170], xmm0
0x180184579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018457e  mov     rcx, [rsp+21D0h+var_2190]
0x180184583  lea     rdx, [rbp+20D0h+var_2110]
0x180184587  mov     [rsp+21D0h+var_21A8], rdx
0x18018458c  lea     r8, [rbp+20D0h+var_1080]
0x180184593  lea     rdx, [rsp+21D0h+var_2160]
0x180184598  mov     r9d, 800h
0x18018459e  mov     qword ptr [rsp+21D0h+cchBuf], rdx
0x1801845a3  lea     rdx, [rbp+20D0h+FileName]
0x1801845a7  mov     rax, [rcx]
0x1801845aa  mov     rax, [rax+28h]
0x1801845ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801845b3  jmp     loc_1801847C1
0x1801845b8  cmp     [rdi+1], sil
0x1801845bc  jz      loc_1801846A8
0x1801845c2  mov     ecx, ebx; uLockCode
0x1801845c4  call    cs:__imp_LockSetForegroundWindow
0x1801845ca  lea     rcx, [rsp+21D0h+var_2188]
0x1801845cf  mov     [rsp+21D0h+var_2190], rsi
0x1801845d4  mov     [rsp+21D0h+var_2188], rsi
0x1801845d9  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801845df  mov     ebx, eax
0x1801845e1  test    eax, eax
0x1801845e3  js      loc_180184698
0x1801845e9  mov     rcx, [rsp+21D0h+var_2188]
0x1801845ee  lea     r9, [rsp+21D0h+var_2170]
0x1801845f3  mov     qword ptr [rsp+21D0h+var_2170], rsi
0x1801845f8  lea     r8, IID_IUnknown
0x1801845ff  lea     rdx, CLSID_CShdocvwBroker
0x180184606  mov     rax, [rcx]
0x180184609  mov     rax, [rax+30h]
0x18018460d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184612  mov     ebx, eax
0x180184614  test    eax, eax
0x180184616  js      short loc_180184647
0x180184618  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x18018461d  lea     r8, [rsp+21D0h+var_2190]
0x180184622  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180184629  mov     rax, [rcx]
0x18018462c  mov     rax, [rax]
0x18018462f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184634  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x180184639  mov     ebx, eax
0x18018463b  mov     rax, [rcx]
0x18018463e  mov     rax, [rax+10h]
0x180184642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184647  mov     rcx, [rsp+21D0h+var_2188]
0x18018464c  mov     rax, [rcx]
0x18018464f  mov     rax, [rax+10h]
0x180184653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184658  test    ebx, ebx
0x18018465a  js      short loc_180184698
0x18018465c  mov     rcx, [rsp+21D0h+var_2190]
0x180184661  lea     rdx, [rbp+20D0h+var_2110]
0x180184665  mov     qword ptr [rsp+21D0h+cchBuf], rdx
0x18018466a  lea     r9, [rsp+21D0h+var_2160]
0x18018466f  mov     r8d, 1000h
0x180184675  lea     rdx, [rbp+20D0h+FileName]
0x180184679  mov     rax, [rcx]
0x18018467c  mov     rax, [rax+20h]
0x180184680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184685  mov     rcx, [rsp+21D0h+var_2190]
0x18018468a  mov     ebx, eax
0x18018468c  mov     rax, [rcx]
0x18018468f  mov     rax, [rax+10h]
0x180184693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184698  mov     ecx, 2; uLockCode
0x18018469d  call    cs:__imp_LockSetForegroundWindow
0x1801846a3  jmp     loc_1801847D4
0x1801846a8  lea     rcx, [rsp+21D0h+var_2188]
0x1801846ad  mov     [rsp+21D0h+var_2190], rsi
0x1801846b2  mov     [rsp+21D0h+var_2188], rsi
0x1801846b7  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801846bd  mov     ebx, eax
0x1801846bf  test    eax, eax
0x1801846c1  js      loc_1801847D4
0x1801846c7  mov     rcx, [rsp+21D0h+var_2188]
0x1801846cc  lea     r9, [rsp+21D0h+dwProcessId]
0x1801846d1  mov     [rsp+21D0h+dwProcessId], esi
0x1801846d5  xor     r8d, r8d
0x1801846d8  xor     edx, edx
0x1801846da  mov     rax, [rcx]
0x1801846dd  mov     rax, [rax+18h]
0x1801846e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801846e6  mov     eax, [rsp+21D0h+dwProcessId]
0x1801846ea  or      ecx, 0FFFFFFFFh
0x1801846ed  test    eax, eax
0x1801846ef  cmovnz  ecx, eax; dwProcessId
0x1801846f2  call    cs:__imp_AllowSetForegroundWindow
0x1801846f8  mov     rcx, [rsp+21D0h+var_2188]
0x1801846fd  lea     r9, [rsp+21D0h+var_2170]
0x180184702  mov     qword ptr [rsp+21D0h+var_2170], rsi
0x180184707  lea     r8, IID_IUnknown
0x18018470e  lea     rdx, CLSID_CShdocvwBroker
0x180184715  mov     rax, [rcx]
0x180184718  mov     rax, [rax+30h]
0x18018471c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184721  mov     ebx, eax
0x180184723  test    eax, eax
0x180184725  js      short loc_180184756
0x180184727  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x18018472c  lea     r8, [rsp+21D0h+var_2190]
0x180184731  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180184738  mov     rax, [rcx]
0x18018473b  mov     rax, [rax]
0x18018473e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184743  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x180184748  mov     ebx, eax
0x18018474a  mov     rax, [rcx]
0x18018474d  mov     rax, [rax+10h]
0x180184751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184756  mov     rcx, [rsp+21D0h+var_2188]
0x18018475b  mov     rax, [rcx]
0x18018475e  mov     rax, [rax+10h]
0x180184762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184767  test    ebx, ebx
0x180184769  js      short loc_1801847D4
  ... truncated ...
```
