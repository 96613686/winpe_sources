# CimSetup::Cleanup(void)

- ea: `0x180182144`
- end: `0x18018244f`
- name: `?Cleanup@CimSetup@@QEAAXXZ`
- size: `779`
- prototype: `void __fastcall(CimSetup *__hidden this)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x180182120`
- `0x1801bf324`
- `0x1801c490c`
- `0x1801c7944`
- `0x1801da358`

## callees

- `0x180013250`
- `0x1800261e0`
- `0x180049ec0`
- `0x180098538`
- `0x180099548`
- `0x1800ad504`
- `0x1800eb920`
- `0x1800f6fd4`
- `0x180182144`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801821a9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180182387`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801821a9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180182387`

## string_xrefs

- `0x180182192`: `BfRemoveMappingEx`
- `0x1801822f7`: `Unable to remove the bind mapping for Packages`
- `0x18018229e`: `Unable to remove the bind mapping for WinSxS`
- `0x180182245`: `Unable to format source packages path`
- `0x1801821e8`: `Unable to format source store path`
- `0x180182380`: `CimDismountImage`
- `0x180182344`: `Failed to get proc address for BfRemoveMappingEx`
- `0x18018232d`: `Bind Filter removed`
- `0x180182412`: `Cim was not mounted`
- `0x180182401`: `Failed to get proc address for CimDismountImage`
- `0x1801823ea`: `Cim is dismounted`
- `0x1801823b4`: `Unable to dismount the cim volume`

## pseudocode

```c
void __fastcall CimSetup::Cleanup(CimSetup *this)
{
  HMODULE v2; // rcx
  FARPROC ProcAddress; // rsi
  int v4; // eax
  int v5; // edx
  int v6; // eax
  int v7; // edx
  int v8; // eax
  int v9; // edx
  int v10; // eax
  int v11; // edx
  FARPROC v12; // rax
  int v13; // eax
  int v14; // edx
  int *v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF
  int v18; // [rsp+48h] [rbp-20h] BYREF

  if ( *((_BYTE *)this + 17) )
  {
    LogAdapter::TraceAtLevel<>(1, "Cleaning up Bind Filter");
    v2 = (HMODULE)*((_QWORD *)this + 1);
    v17 = 0;
    v16 = 0;
    ProcAddress = GetProcAddress(v2, "BfRemoveMappingEx");
    if ( ProcAddress )
    {
      v4 = SczAllocFormatted(&v17, L"%s\\winsxs", *((_QWORD *)this + 5));
      if ( v4 < 0 )
      {
        v18 = v4;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Unable to format source store path");
          v15 = &v18;
          LOBYTE(v5) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v5,
            3,
            (unsigned int)": {}",
            (__int64)&v15);
        }
      }
      v6 = SczAllocFormatted(&v16, L"%s\\Servicing\\Packages", *((_QWORD *)this + 5));
      if ( v6 < 0 )
      {
        v18 = v6;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Unable to format source packages path");
          v15 = &v18;
          LOBYTE(v7) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v7,
            3,
            (unsigned int)": {}",
            (__int64)&v15);
        }
      }
      v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(0, 0, v17);
      if ( v8 < 0 )
      {
        v18 = v8;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Unable to remove the bind mapping for WinSxS");
          v15 = &v18;
          LOBYTE(v9) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v9,
            3,
            (unsigned int)": {}",
            (__int64)&v15);
        }
      }
      v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(0, 0, v16);
      if ( v10 < 0 )
      {
        v18 = v10;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Unable to remove the bind mapping for Packages");
          v15 = &v18;
          LOBYTE(v11) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v11,
            3,
            (unsigned int)": {}",
            (__int64)&v15);
        }
      }
      LogAdapter::TraceAtLevel<>(1, "Bind Filter removed");
      *((_BYTE *)this + 17) = 0;
    }
    else
    {
      LogAdapter::TraceAtLevelLastError<>(3, "Failed to get proc address for BfRemoveMappingEx");
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v16);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v17);
  }
  else
  {
    LogAdapter::TraceAtLevel<>(1, "Bind Filter was not added");
  }
  if ( *((_BYTE *)this + 16) )
  {
    v12 = GetProcAddress(*(HMODULE *)this, "CimDismountImage");
    if ( !v12 )
    {
      LogAdapter::TraceAtLevelLastError<>(3, "Failed to get proc address for CimDismountImage");
      return;
    }
    v13 = ((__int64 (__fastcall *)(char *))v12)((char *)this + 20);
    if ( v13 < 0 )
    {
      v18 = v13;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Unable to dismount the cim volume");
        v15 = &v18;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v14,
          3,
          (unsigned int)": {}",
          (__int64)&v15);
      }
    }
    LogAdapter::TraceAtLevel<>(1, "Cim is dismounted");
    *((_BYTE *)this + 16) = 0;
  }
  else
  {
    LogAdapter::TraceAtLevel<>(1, "Cim was not mounted");
  }
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(this);
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close((char *)this + 8);
}

```

## disassembly

```asm
0x180182144  push    rbp
0x180182146  push    rbx
0x180182147  push    rsi
0x180182148  push    r12
0x18018214a  push    r13
0x18018214c  push    r14
0x18018214e  mov     rbp, rsp
0x180182151  sub     rsp, 68h
0x180182155  mov     rax, cs:__security_cookie
0x18018215c  xor     rax, rsp
0x18018215f  mov     [rbp+var_18], rax
0x180182163  cmp     byte ptr [rcx+11h], 0
0x180182167  lea     r13, asc_1802EE7AC; ": {}"
0x18018216e  mov     r12d, 3
0x180182174  mov     rbx, rcx
0x180182177  lea     ecx, [r12-2]
0x18018217c  jz      loc_180182367
0x180182182  lea     rdx, aCleaningUpBind; "Cleaning up Bind Filter"
0x180182189  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18018218e  mov     rcx, [rbx+8]; hModule
0x180182192  lea     rdx, aBfremovemappin; "BfRemoveMappingEx"
0x180182199  mov     [rbp+var_28], 0
0x1801821a1  mov     [rbp+var_30], 0
0x1801821a9  call    cs:__imp_GetProcAddress
0x1801821b0  nop     dword ptr [rax+rax+00h]
0x1801821b5  mov     rsi, rax
0x1801821b8  test    rax, rax
0x1801821bb  jz      loc_180182344
0x1801821c1  mov     r8, [rbx+28h]
0x1801821c5  lea     rdx, aSWinsxs; "%s\\winsxs"
0x1801821cc  lea     rcx, [rbp+var_28]
0x1801821d0  call    SczAllocFormatted
0x1801821d5  test    eax, eax
0x1801821d7  jns     short loc_18018221E
0x1801821d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801821e0  mov     [rbp+var_20], eax
0x1801821e3  test    rcx, rcx
0x1801821e6  jz      short loc_18018221E
0x1801821e8  lea     r9, aUnableToFormat_0; "Unable to format source store path"
0x1801821ef  mov     r8d, r12d
0x1801821f2  xor     edx, edx
0x1801821f4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801821f9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182200  lea     rax, [rbp+var_20]
0x180182204  mov     [rbp+var_38], rax
0x180182208  mov     r9, r13
0x18018220b  lea     rax, [rbp+var_38]
0x18018220f  mov     r8d, r12d
0x180182212  mov     dl, 1
0x180182214  mov     [rsp+68h+var_48], rax
0x180182219  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018221e  mov     r8, [rbx+28h]
0x180182222  lea     rdx, aSServicingPack; "%s\\Servicing\\Packages"
0x180182229  lea     rcx, [rbp+var_30]
0x18018222d  call    SczAllocFormatted
0x180182232  test    eax, eax
0x180182234  jns     short loc_18018227B
0x180182236  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018223d  mov     [rbp+var_20], eax
0x180182240  test    rcx, rcx
0x180182243  jz      short loc_18018227B
0x180182245  lea     r9, aUnableToFormat; "Unable to format source packages path"
0x18018224c  mov     r8d, r12d
0x18018224f  xor     edx, edx
0x180182251  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182256  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018225d  lea     rax, [rbp+var_20]
0x180182261  mov     [rbp+var_38], rax
0x180182265  mov     r9, r13
0x180182268  lea     rax, [rbp+var_38]
0x18018226c  mov     r8d, r12d
0x18018226f  mov     dl, 1
0x180182271  mov     [rsp+68h+var_48], rax
0x180182276  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018227b  mov     r8, [rbp+var_28]
0x18018227f  xor     edx, edx
0x180182281  xor     ecx, ecx
0x180182283  mov     rax, rsi
0x180182286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018228b  test    eax, eax
0x18018228d  jns     short loc_1801822D4
0x18018228f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180182296  mov     [rbp+var_20], eax
0x180182299  test    rcx, rcx
0x18018229c  jz      short loc_1801822D4
0x18018229e  lea     r9, aUnableToRemove_5; "Unable to remove the bind mapping for W"...
0x1801822a5  mov     r8d, r12d
0x1801822a8  xor     edx, edx
0x1801822aa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801822af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801822b6  lea     rax, [rbp+var_20]
0x1801822ba  mov     [rbp+var_38], rax
0x1801822be  mov     r9, r13
0x1801822c1  lea     rax, [rbp+var_38]
0x1801822c5  mov     r8d, r12d
0x1801822c8  mov     dl, 1
0x1801822ca  mov     [rsp+68h+var_48], rax
0x1801822cf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801822d4  mov     r8, [rbp+var_30]
0x1801822d8  xor     edx, edx
0x1801822da  xor     ecx, ecx
0x1801822dc  mov     rax, rsi
0x1801822df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801822e4  test    eax, eax
0x1801822e6  jns     short loc_18018232D
0x1801822e8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801822ef  mov     [rbp+var_20], eax
0x1801822f2  test    rcx, rcx
0x1801822f5  jz      short loc_18018232D
0x1801822f7  lea     r9, aUnableToRemove_8; "Unable to remove the bind mapping for P"...
0x1801822fe  mov     r8d, r12d
0x180182301  xor     edx, edx
0x180182303  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180182308  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018230f  lea     rax, [rbp+var_20]
0x180182313  mov     [rbp+var_38], rax
0x180182317  mov     r9, r13
0x18018231a  lea     rax, [rbp+var_38]
0x18018231e  mov     r8d, r12d
0x180182321  mov     dl, 1
0x180182323  mov     [rsp+68h+var_48], rax
0x180182328  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018232d  lea     rdx, aBindFilterRemo; "Bind Filter removed"
0x180182334  mov     ecx, 1
0x180182339  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18018233e  mov     byte ptr [rbx+11h], 0
0x180182342  jmp     short loc_180182353
0x180182344  lea     rdx, aFailedToGetPro_15; "Failed to get proc address for BfRemove"...
0x18018234b  mov     ecx, r12d
0x18018234e  call    ??$TraceAtLevelLastError@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevelLastError<>(LogAdapter::LogLevel,char const * const)
0x180182353  lea     rcx, [rbp+var_30]
0x180182357  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18018235c  lea     rcx, [rbp+var_28]
0x180182360  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180182365  jmp     short loc_180182373
0x180182367  lea     rdx, aBindFilterWasN; "Bind Filter was not added"
0x18018236e  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180182373  cmp     byte ptr [rbx+10h], 0
0x180182377  jz      loc_180182412
0x18018237d  mov     rcx, [rbx]; hModule
0x180182380  lea     rdx, aCimdismountima; "CimDismountImage"
0x180182387  call    cs:__imp_GetProcAddress
0x18018238e  nop     dword ptr [rax+rax+00h]
0x180182393  test    rax, rax
0x180182396  jz      short loc_180182401
0x180182398  lea     rcx, [rbx+14h]
0x18018239c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801823a1  test    eax, eax
0x1801823a3  jns     short loc_1801823EA
0x1801823a5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801823ac  mov     [rbp+var_20], eax
0x1801823af  test    rcx, rcx
0x1801823b2  jz      short loc_1801823EA
0x1801823b4  lea     r9, aUnableToDismou; "Unable to dismount the cim volume"
0x1801823bb  mov     r8d, r12d
0x1801823be  xor     edx, edx
0x1801823c0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801823c5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801823cc  lea     rax, [rbp+var_20]
0x1801823d0  mov     [rbp+var_38], rax
0x1801823d4  mov     r9, r13
0x1801823d7  lea     rax, [rbp+var_38]
0x1801823db  mov     r8d, r12d
0x1801823de  mov     dl, 1
0x1801823e0  mov     [rsp+68h+var_48], rax
0x1801823e5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801823ea  lea     rdx, aCimIsDismounte; "Cim is dismounted"
0x1801823f1  mov     ecx, 1
0x1801823f6  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1801823fb  mov     byte ptr [rbx+10h], 0
0x1801823ff  jmp     short loc_180182423
0x180182401  lea     rdx, aFailedToGetPro_2; "Failed to get proc address for CimDismo"...
0x180182408  mov     ecx, r12d
0x18018240b  call    ??$TraceAtLevelLastError@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevelLastError<>(LogAdapter::LogLevel,char const * const)
0x180182410  jmp     short loc_180182434
0x180182412  lea     rdx, aCimWasNotMount; "Cim was not mounted"
0x180182419  mov     ecx, 1
0x18018241e  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180182423  mov     rcx, rbx
0x180182426  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18018242b  lea     rcx, [rbx+8]
0x18018242f  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180182434  mov     rcx, [rbp+var_18]
0x180182438  xor     rcx, rsp; StackCookie
0x18018243b  call    __security_check_cookie
0x180182440  add     rsp, 68h
0x180182444  pop     r14
0x180182446  pop     r13
0x180182448  pop     r12
0x18018244a  pop     rsi
0x18018244b  pop     rbx
0x18018244c  pop     rbp
0x18018244d  retn
```
