# _DualEngineBrowseInNewProcess(_ITEMIDLIST_ABSOLUTE const *,ulong,tagTABWINDOWDATA *)

- ea: `0x180196f40`
- end: `0x180197522`
- name: `?_DualEngineBrowseInNewProcess@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAUtagTABWINDOWDATA@@@Z`
- size: `1506`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST_ABSOLUTE *, unsigned int, struct tagTABWINDOWDATA *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180067c94`

## callees

- `0x180024bc4`
- `0x1800c562c`
- `0x180110868`
- `0x180196f40`
- `0x18042e5a8`
- `0x18042ebf4`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180196fe4`
- `KERNEL32!GetCurrentProcessId` at `0x180196fe4`
- `USER32!LockSetForegroundWindow` at `0x18019709d`
- `USER32!LockSetForegroundWindow` at `0x1801972d0`
- `USER32!LockSetForegroundWindow` at `0x1801973b5`
- `USER32!LockSetForegroundWindow` at `0x18019709d`
- `USER32!LockSetForegroundWindow` at `0x1801972d0`
- `USER32!LockSetForegroundWindow` at `0x1801973b5`
- `USER32!AllowSetForegroundWindow` at `0x1801971d4`
- `USER32!AllowSetForegroundWindow` at `0x180197416`
- `USER32!AllowSetForegroundWindow` at `0x1801971d4`
- `USER32!AllowSetForegroundWindow` at `0x180197416`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801970b8`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180197193`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801972eb`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801973d5`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801970b8`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180197193`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801972eb`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1801973d5`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180197014`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180197014`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180196f71`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180196f71`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180197023`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180197263`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801974a1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180197023`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180197263`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801974a1`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180196ffa`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x180196ffa`

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
0x180196f40  push    rbp
0x180196f42  push    rbx
0x180196f43  push    rsi
0x180196f44  push    rdi
0x180196f45  lea     rbp, [rsp-20B8h]
0x180196f4d  mov     eax, 21B8h
0x180196f52  call    _alloca_probe
0x180196f57  sub     rsp, rax
0x180196f5a  mov     rax, cs:__security_cookie
0x180196f61  xor     rax, rsp
0x180196f64  mov     [rbp+20D0h+var_30], rax
0x180196f6b  mov     rdi, r8
0x180196f6e  mov     rbx, rcx
0x180196f71  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180196f78  nop     dword ptr [rax+rax+00h]
0x180196f7d  xor     esi, esi
0x180196f7f  test    al, al
0x180196f81  jnz     short loc_180196F9C
0x180196f83  mov     rcx, [rbp+20D8h]; this
0x180196f8a  lea     r8, aInetcoreIefram_35; "inetcore\\ieframe\\shdocvw\\hlframe.cpp"
0x180196f91  mov     edx, 49Ah; void *
0x180196f96  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180196f9c  mov     [rsp+21D0h+var_21A8], rsi; __int64
0x180196fa1  lea     r9, [rbp+20D0h+FileName]; int
0x180196fa5  xor     r8d, r8d; int
0x180196fa8  mov     [rsp+21D0h+cchBuf], 824h; cchBuf
0x180196fb0  mov     edx, 8000h; int
0x180196fb5  mov     rcx, rbx; int
0x180196fb8  call    IEGetNameAndFlagsEx
0x180196fbd  mov     ebx, eax
0x180196fbf  test    eax, eax
0x180196fc1  js      loc_180197504
0x180196fc7  xorps   xmm0, xmm0
0x180196fca  mov     [rsp+21D0h+var_2160], rsi
0x180196fcf  movups  xmmword ptr [rbp+20D0h+var_2138], xmm0
0x180196fd3  mov     [rsp+21D0h+var_2158], rsi
0x180196fd8  movups  xmmword ptr [rbp+20D0h+var_2138+0Ch], xmm0
0x180196fdc  mov     [rbp+20D0h+var_2150], rsi
0x180196fe0  movups  [rbp+20D0h+var_2148], xmm0
0x180196fe4  call    cs:__imp_GetCurrentProcessId
0x180196feb  nop     dword ptr [rax+rax+00h]
0x180196ff0  mov     ebx, 1
0x180196ff5  mov     dword ptr [rbp+20D0h+var_2148], eax
0x180196ff8  mov     ecx, ebx
0x180196ffa  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180197001  nop     dword ptr [rax+rax+00h]
0x180197006  mov     ecx, 20000011h
0x18019700b  mov     dword ptr [rbp+20D0h+var_2148+8], esi
0x18019700e  and     eax, 7Fh
0x180197011  mov     dword ptr [rbp+20D0h+var_2148+4], eax
0x180197014  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18019701b  nop     dword ptr [rax+rax+00h]
0x180197020  mov     [rbp+20D0h+var_2138], eax
0x180197023  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18019702a  nop     dword ptr [rax+rax+00h]
0x18019702f  xorps   xmm1, xmm1
0x180197032  movups  xmm0, xmmword ptr [rax]
0x180197035  movups  xmmword ptr [rbp+20D0h+var_20F0], xmm1
0x180197039  movdqu  xmmword ptr [rbp+20D0h+var_2138+0Ch], xmm0
0x18019703e  movups  [rbp+20D0h+var_2110], xmm1
0x180197042  movups  [rbp+20D0h+var_2100], xmm1
0x180197046  movups  xmmword ptr [rbp+20D0h+var_20F0+0Ch], xmm1
0x18019704a  call    DualEngine__GetOpenerCookie
0x18019704f  cmp     [rdi+1], sil
0x180197053  mov     dword ptr [rbp+20D0h+var_2110], eax
0x180197056  mov     eax, esi
0x180197058  setnz   al
0x18019705b  mov     dword ptr [rbp+20D0h+var_2110+8], eax
0x18019705e  cmp     [rdi+3], sil
0x180197062  jz      loc_1801972C4
0x180197068  lea     rcx, [rbp+20D0h+FileName]
0x18019706c  call    PathIsInternetShortcutFile
0x180197071  test    eax, eax
0x180197073  jz      loc_1801972C4
0x180197079  lea     rdx, [rbp+20D0h+var_1080]
0x180197080  lea     rcx, [rbp+20D0h+FileName]; lpFileName
0x180197084  call    TargetUrlFromInternetShortcutFile
0x180197089  test    eax, eax
0x18019708b  js      loc_1801972C4
0x180197091  cmp     [rdi+1], sil
0x180197095  jz      loc_180197184
0x18019709b  mov     ecx, ebx; uLockCode
0x18019709d  call    cs:__imp_LockSetForegroundWindow
0x1801970a4  nop     dword ptr [rax+rax+00h]
0x1801970a9  lea     rcx, [rsp+21D0h+var_2190]
0x1801970ae  mov     qword ptr [rsp+21D0h+dwProcessId], rsi
0x1801970b3  mov     [rsp+21D0h+var_2190], rsi
0x1801970b8  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801970bf  nop     dword ptr [rax+rax+00h]
0x1801970c4  mov     ebx, eax
0x1801970c6  test    eax, eax
0x1801970c8  js      loc_1801973B0
0x1801970ce  mov     rcx, [rsp+21D0h+var_2190]
0x1801970d3  lea     r9, [rsp+21D0h+var_2188]
0x1801970d8  mov     [rsp+21D0h+var_2188], rsi
0x1801970dd  lea     r8, IID_IUnknown
0x1801970e4  lea     rdx, CLSID_CShdocvwBroker
0x1801970eb  mov     rax, [rcx]
0x1801970ee  mov     rax, [rax+30h]
0x1801970f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801970f7  mov     ebx, eax
0x1801970f9  test    eax, eax
0x1801970fb  js      short loc_18019712C
0x1801970fd  mov     rcx, [rsp+21D0h+var_2188]
0x180197102  lea     r8, [rsp+21D0h+dwProcessId]
0x180197107  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x18019710e  mov     rax, [rcx]
0x180197111  mov     rax, [rax]
0x180197114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197119  mov     rcx, [rsp+21D0h+var_2188]
0x18019711e  mov     ebx, eax
0x180197120  mov     rax, [rcx]
0x180197123  mov     rax, [rax+10h]
0x180197127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019712c  mov     rcx, [rsp+21D0h+var_2190]
0x180197131  mov     rax, [rcx]
0x180197134  mov     rax, [rax+10h]
0x180197138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019713d  test    ebx, ebx
0x18019713f  js      loc_1801973B0
0x180197145  mov     rcx, qword ptr [rsp+21D0h+dwProcessId]
0x18019714a  lea     rdx, [rbp+20D0h+var_2110]
0x18019714e  mov     [rsp+21D0h+var_21A8], rdx
0x180197153  lea     r8, [rbp+20D0h+var_1080]
0x18019715a  lea     rdx, [rsp+21D0h+var_2160]
0x18019715f  mov     r9d, 1000h
0x180197165  mov     qword ptr [rsp+21D0h+cchBuf], rdx
0x18019716a  lea     rdx, [rbp+20D0h+FileName]
0x18019716e  mov     rax, [rcx]
0x180197171  mov     rax, [rax+28h]
0x180197175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019717a  mov     rcx, qword ptr [rsp+21D0h+dwProcessId]
0x18019717f  jmp     loc_1801973A2
0x180197184  lea     rcx, [rsp+21D0h+var_2188]
0x180197189  mov     [rsp+21D0h+var_2190], rsi
0x18019718e  mov     [rsp+21D0h+var_2188], rsi
0x180197193  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18019719a  nop     dword ptr [rax+rax+00h]
0x18019719f  mov     ebx, eax
0x1801971a1  test    eax, eax
0x1801971a3  js      loc_180197504
0x1801971a9  mov     rcx, [rsp+21D0h+var_2188]
0x1801971ae  lea     r9, [rsp+21D0h+dwProcessId]
0x1801971b3  mov     [rsp+21D0h+dwProcessId], esi
0x1801971b7  xor     r8d, r8d
0x1801971ba  xor     edx, edx
0x1801971bc  mov     rax, [rcx]
0x1801971bf  mov     rax, [rax+18h]
0x1801971c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801971c8  mov     eax, [rsp+21D0h+dwProcessId]
0x1801971cc  or      ecx, 0FFFFFFFFh
0x1801971cf  test    eax, eax
0x1801971d1  cmovnz  ecx, eax; dwProcessId
0x1801971d4  call    cs:__imp_AllowSetForegroundWindow
0x1801971db  nop     dword ptr [rax+rax+00h]
0x1801971e0  mov     rcx, [rsp+21D0h+var_2188]
0x1801971e5  lea     r9, [rsp+21D0h+var_2170]
0x1801971ea  mov     qword ptr [rsp+21D0h+var_2170], rsi
0x1801971ef  lea     r8, IID_IUnknown
0x1801971f6  lea     rdx, CLSID_CShdocvwBroker
0x1801971fd  mov     rax, [rcx]
0x180197200  mov     rax, [rax+30h]
0x180197204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197209  mov     ebx, eax
0x18019720b  test    eax, eax
0x18019720d  js      short loc_18019723E
0x18019720f  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x180197214  lea     r8, [rsp+21D0h+var_2190]
0x180197219  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180197220  mov     rax, [rcx]
0x180197223  mov     rax, [rax]
0x180197226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019722b  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x180197230  mov     ebx, eax
0x180197232  mov     rax, [rcx]
0x180197235  mov     rax, [rax+10h]
0x180197239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019723e  mov     rcx, [rsp+21D0h+var_2188]
0x180197243  mov     rax, [rcx]
0x180197246  mov     rax, [rax+10h]
0x18019724a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019724f  test    ebx, ebx
0x180197251  js      loc_180197504
0x180197257  mov     rax, [rsp+21D0h+var_2190]
0x18019725c  mov     rcx, [rax]
0x18019725f  mov     rbx, [rcx+38h]
0x180197263  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18019726a  nop     dword ptr [rax+rax+00h]
0x18019726f  mov     rcx, [rsp+21D0h+var_2190]
0x180197274  lea     rdx, [rsp+21D0h+var_2170]
0x180197279  movups  xmm0, xmmword ptr [rax]
0x18019727c  mov     rax, rbx
0x18019727f  movdqu  [rsp+21D0h+var_2170], xmm0
0x180197285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019728a  mov     rcx, [rsp+21D0h+var_2190]
0x18019728f  lea     rdx, [rbp+20D0h+var_2110]
0x180197293  mov     [rsp+21D0h+var_21A8], rdx
0x180197298  lea     r8, [rbp+20D0h+var_1080]
0x18019729f  lea     rdx, [rsp+21D0h+var_2160]
0x1801972a4  mov     r9d, 800h
0x1801972aa  mov     qword ptr [rsp+21D0h+cchBuf], rdx
0x1801972af  lea     rdx, [rbp+20D0h+FileName]
0x1801972b3  mov     rax, [rcx]
0x1801972b6  mov     rax, [rax+28h]
0x1801972ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801972bf  jmp     loc_1801974F1
0x1801972c4  cmp     [rdi+1], sil
0x1801972c8  jz      loc_1801973C6
0x1801972ce  mov     ecx, ebx; uLockCode
0x1801972d0  call    cs:__imp_LockSetForegroundWindow
0x1801972d7  nop     dword ptr [rax+rax+00h]
0x1801972dc  lea     rcx, [rsp+21D0h+var_2188]
0x1801972e1  mov     [rsp+21D0h+var_2190], rsi
0x1801972e6  mov     [rsp+21D0h+var_2188], rsi
0x1801972eb  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801972f2  nop     dword ptr [rax+rax+00h]
0x1801972f7  mov     ebx, eax
0x1801972f9  test    eax, eax
0x1801972fb  js      loc_1801973B0
0x180197301  mov     rcx, [rsp+21D0h+var_2188]
0x180197306  lea     r9, [rsp+21D0h+var_2170]
0x18019730b  mov     qword ptr [rsp+21D0h+var_2170], rsi
0x180197310  lea     r8, IID_IUnknown
0x180197317  lea     rdx, CLSID_CShdocvwBroker
0x18019731e  mov     rax, [rcx]
0x180197321  mov     rax, [rax+30h]
0x180197325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019732a  mov     ebx, eax
0x18019732c  test    eax, eax
0x18019732e  js      short loc_18019735F
0x180197330  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x180197335  lea     r8, [rsp+21D0h+var_2190]
0x18019733a  lea     rdx, _GUID_14272506_7d5c_46df_9233_0e98de2e5f14
0x180197341  mov     rax, [rcx]
0x180197344  mov     rax, [rax]
0x180197347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019734c  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x180197351  mov     ebx, eax
0x180197353  mov     rax, [rcx]
0x180197356  mov     rax, [rax+10h]
0x18019735a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019735f  mov     rcx, [rsp+21D0h+var_2188]
0x180197364  mov     rax, [rcx]
0x180197367  mov     rax, [rax+10h]
0x18019736b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180197370  test    ebx, ebx
0x180197372  js      short loc_1801973B0
0x180197374  mov     rcx, [rsp+21D0h+var_2190]
0x180197379  lea     rdx, [rbp+20D0h+var_2110]
0x18019737d  mov     qword ptr [rsp+21D0h+cchBuf], rdx
0x180197382  lea     r9, [rsp+21D0h+var_2160]
0x180197387  mov     r8d, 1000h
0x18019738d  lea     rdx, [rbp+20D0h+FileName]
0x180197391  mov     rax, [rcx]
0x180197394  mov     rax, [rax+20h]
0x180197398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019739d  mov     rcx, [rsp+21D0h+var_2190]
0x1801973a2  mov     ebx, eax
0x1801973a4  mov     rax, [rcx]
0x1801973a7  mov     rax, [rax+10h]
0x1801973ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801973b0  mov     ecx, 2; uLockCode
0x1801973b5  call    cs:__imp_LockSetForegroundWindow
0x1801973bc  nop     dword ptr [rax+rax+00h]
0x1801973c1  jmp     loc_180197504
0x1801973c6  lea     rcx, [rsp+21D0h+var_2188]
0x1801973cb  mov     [rsp+21D0h+var_2190], rsi
0x1801973d0  mov     [rsp+21D0h+var_2188], rsi
0x1801973d5  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1801973dc  nop     dword ptr [rax+rax+00h]
0x1801973e1  mov     ebx, eax
0x1801973e3  test    eax, eax
0x1801973e5  js      loc_180197504
0x1801973eb  mov     rcx, [rsp+21D0h+var_2188]
0x1801973f0  lea     r9, [rsp+21D0h+dwProcessId]
0x1801973f5  mov     [rsp+21D0h+dwProcessId], esi
0x1801973f9  xor     r8d, r8d
0x1801973fc  xor     edx, edx
0x1801973fe  mov     rax, [rcx]
0x180197401  mov     rax, [rax+18h]
0x180197405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019740a  mov     eax, [rsp+21D0h+dwProcessId]
0x18019740e  or      ecx, 0FFFFFFFFh
0x180197411  test    eax, eax
0x180197413  cmovnz  ecx, eax; dwProcessId
0x180197416  call    cs:__imp_AllowSetForegroundWindow
0x18019741d  nop     dword ptr [rax+rax+00h]
0x180197422  mov     rcx, [rsp+21D0h+var_2188]
0x180197427  lea     r9, [rsp+21D0h+var_2170]
0x18019742c  mov     qword ptr [rsp+21D0h+var_2170], rsi
0x180197431  lea     r8, IID_IUnknown
0x180197438  lea     rdx, CLSID_CShdocvwBroker
0x18019743f  mov     rax, [rcx]
0x180197442  mov     rax, [rax+30h]
0x180197446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019744b  mov     ebx, eax
0x18019744d  test    eax, eax
0x18019744f  js      short loc_180197480
0x180197451  mov     rcx, qword ptr [rsp+21D0h+var_2170]
0x180197456  lea     r8, [rsp+21D0h+var_2190]
  ... truncated ...
```
