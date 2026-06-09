# CTSSession::OnLogonCompleted(void)

- ea: `0x18006ee30`
- end: `0x18006f2f0`
- name: `?OnLogonCompleted@CTSSession@@UEAAJXZ`
- size: `1216`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b90`
- `0x1800077a0`
- `0x18000c684`
- `0x18000c6b0`
- `0x18000f320`
- `0x1800115a8`
- `0x1800120d0`
- `0x1800266bc`
- `0x18002701c`
- `0x180027610`
- `0x18002772c`
- `0x18002f26c`
- `0x18004e850`
- `0x18006ee30`
- `0x180071e80`
- `0x180073110`
- `0x180073390`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006f156`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006f156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f1e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f24b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f1e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f24b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006eebf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006eeed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006eebf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006eeed`
- `USER32!LoadStringW` at `0x18006f1d8`
- `USER32!LoadStringW` at `0x18006f23b`
- `USER32!LoadStringW` at `0x18006f1d8`
- `USER32!LoadStringW` at `0x18006f23b`

## string_xrefs

- `0x18006ef2a`: `unable to write LastRemoteLogonTime to registry`
- `0x18006ee87`: `pNewTerminal->LoggedOnCompleted`
- `0x18006ef1a`: `OnLogonCompleted`
- `0x18006ef94`: `ptrTerminal->OnLogonCompleted took this long`
- `0x18006efd8`: `CTSSession::OnLogonCompleted`
- `0x18006efd1`: `Terminal->OnLogonCompleted failed: 0x%x in %s`
- `0x18006f075`: `EventDispatch->OnLogonCompleted failed: 0x%x`
- `0x18006f14d`: `lsm.dll`
- `0x18006f18f`: `Failed loading module in OnLogonCompleted`
- `0x18006f211`: `Failed loading title in OnLogonCompleted`
- `0x18006f270`: `Failed loading message in OnLogonCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTSSession::OnLogonCompleted(CTSSession *this)
{
  int IsLocalGlassTerminal; // edi
  ULONGLONG TickCount64; // r15
  signed int InstanceOfSessionManagerInternal; // esi
  CTSSession *v5; // rcx
  ULONGLONG v6; // rbx
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  int v10; // eax
  int v11; // eax
  struct ISessionManagerInternal *v12; // rdi
  unsigned int (__fastcall *v13)(struct ISessionManagerInternal *, __int64); // rbx
  __int64 v14; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  signed int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  const char *v22; // rax
  char *v23; // rdx
  signed int v24; // eax
  signed int LastError; // eax
  unsigned int v27; // [rsp+30h] [rbp-D0h]
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct ISessionManagerInternal *v31; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DESCRIPTOR v32; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  _BYTE Parameter[96]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[256]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR v38[512]; // [rsp+300h] [rbp+200h] BYREF

  v31 = 0;
  if ( *((_QWORD *)this + 227) )
  {
    v32 = (struct _EVENT_DESCRIPTOR)EVENT_TERMINAL_LOGON_TOOLONG;
    CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(
      Parameter,
      (struct _GUID *)((char *)this + 3208),
      *((_DWORD *)this + 436),
      this,
      &v32,
      "pNewTerminal->LoggedOnCompleted",
      v27);
    IsLocalGlassTerminal = CGlassTerminal::IsLocalGlassTerminal(*((struct ITerminal **)this + 227));
    TickCount64 = GetTickCount64();
    InstanceOfSessionManagerInternal = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 227) + 72LL))(
                                         *((_QWORD *)this + 227),
                                         *((_QWORD *)this + 741));
    v6 = GetTickCount64();
    if ( InstanceOfSessionManagerInternal >= 0 && !IsLocalGlassTerminal )
    {
      v9 = CTSSession::WriteLastRemoteLogonTime(v5);
      InstanceOfSessionManagerInternal = v9;
      if ( v9 < 0 )
      {
        LODWORD(v5) = dword_1800DF020;
        if ( (unsigned int)dword_1800DF020 > 3 )
        {
          phModule = (HMODULE)"OnLogonCompleted";
          v28 = v9;
          *(_QWORD *)v30 = "unable to write LastRemoteLogonTime to registry";
          *(_QWORD *)&v32.Id = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            dword_1800DF020,
            (unsigned int)&word_1800C91F6,
            v7,
            v8,
            (__int64)&v32,
            (__int64)v30,
            (__int64)&v28,
            (__int64)&phModule);
        }
      }
    }
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      *(_QWORD *)&v32.Id = v6 - TickCount64;
      v28 = *((_DWORD *)this + 436);
      phModule = (HMODULE)"ptrTerminal->OnLogonCompleted took this long";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v5,
        (unsigned int)&word_1800C919E,
        v7,
        v8,
        (__int64)&phModule,
        (__int64)&v28,
        (__int64)&v32);
    }
    if ( InstanceOfSessionManagerInternal < 0 )
    {
      _DbgPrintMessage(
        8,
        "Terminal->OnLogonCompleted failed: 0x%x in %s",
        (unsigned int)InstanceOfSessionManagerInternal,
        "CTSSession::OnLogonCompleted");
LABEL_11:
      CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
      goto LABEL_43;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LogonCompletedNotif>::GetImpl'::`2'::impl) )
    {
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v10 = CTSSession::InitializeNotifyInfo(this, (struct __PTSSessInfo *)&v32);
      InstanceOfSessionManagerInternal = v10;
      if ( v10 < 0 )
      {
        _DbgPrintMessage(
          8,
          "InitializeNotifyInfo failed: 0x%x in %s",
          (unsigned int)v10,
          "CTSSession::OnLogonCompleted");
        goto LABEL_11;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, struct _EVENT_DESCRIPTOR *, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 228) + 1832LL)
                                                                                           + 192LL))(
              *((_QWORD *)this + 228) + 1832LL,
              &v32,
              *((unsigned int *)this + 814),
              *((unsigned int *)this + 814));
      if ( v11 < 0 )
        _DbgPrintMessage(8, "EventDispatch->OnLogonCompleted failed: 0x%x", v11);
      if ( *(_QWORD *)&v32.Id )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v32.Id + 16LL))(*(_QWORD *)&v32.Id);
        *(_QWORD *)&v32.Id = 0;
      }
      if ( (_QWORD)v34 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v34 + 16LL))(v34);
    }
    CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor((CTSTerminalOpsMonitor *)Parameter);
  }
  InstanceOfSessionManagerInternal = ISessionManagerInternal::GetInstanceOfSessionManagerInternal(&v31);
  if ( InstanceOfSessionManagerInternal >= 0 )
  {
    v12 = v31;
    v13 = *(unsigned int (__fastcall **)(struct ISessionManagerInternal *, __int64))(*(_QWORD *)v31 + 224LL);
    v14 = std::wstring::wstring(&v32, (char *)this + 5944);
    if ( !v13(v12, v14) )
    {
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        *(_QWORD *)&v32.Id = "DWM previously crashed for this user";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v15,
          (unsigned int)&dword_1800C9184,
          v16,
          v17,
          (__int64)&v32);
      }
      phModule = 0;
      if ( GetModuleHandleExW(2u, L"lsm.dll", &phModule) )
      {
        if ( LoadStringW(phModule, 0x3EBu, Buffer, 256) )
        {
          if ( LoadStringW(phModule, 0x3ECu, v38, 512) )
          {
            v30[0] = 0;
            CTSSession::ShowMessageBox(this, Buffer, v38, 0x10u, 0x7530u, v30, 1, 1);
            goto LABEL_43;
          }
          LastError = GetLastError();
          InstanceOfSessionManagerInternal = LastError;
          if ( LastError > 0 )
            InstanceOfSessionManagerInternal = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)dword_1800DF020 > 2 )
          {
            v22 = "Failed loading message in OnLogonCompleted";
            v23 = &byte_1800C9127;
            goto LABEL_31;
          }
        }
        else
        {
          v24 = GetLastError();
          InstanceOfSessionManagerInternal = v24;
          if ( v24 > 0 )
            InstanceOfSessionManagerInternal = (unsigned __int16)v24 | 0x80070000;
          if ( (unsigned int)dword_1800DF020 > 2 )
          {
            v22 = "Failed loading title in OnLogonCompleted";
            v23 = (char *)&word_1800C9146;
            goto LABEL_31;
          }
        }
      }
      else
      {
        v18 = GetLastError();
        InstanceOfSessionManagerInternal = v18;
        if ( v18 > 0 )
          InstanceOfSessionManagerInternal = (unsigned __int16)v18 | 0x80070000;
        if ( (unsigned int)dword_1800DF020 > 2 )
        {
          v22 = "Failed loading module in OnLogonCompleted";
          v23 = byte_1800C9165;
LABEL_31:
          *(_QWORD *)&v32.Id = v22;
          v28 = InstanceOfSessionManagerInternal;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v19,
            (_DWORD)v23,
            v20,
            v21,
            (__int64)&v32,
            (__int64)&v28);
        }
      }
    }
  }
LABEL_43:
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v31);
  return (unsigned int)InstanceOfSessionManagerInternal;
}

```

## disassembly

```asm
0x18006ee30  push    rbp
0x18006ee32  push    rbx
0x18006ee33  push    rsi
0x18006ee34  push    rdi
0x18006ee35  push    r14
0x18006ee37  push    r15
0x18006ee39  lea     rbp, [rsp-618h]
0x18006ee41  sub     rsp, 718h
0x18006ee48  mov     rax, cs:__security_cookie
0x18006ee4f  xor     rax, rsp
0x18006ee52  mov     [rbp+640h+var_40], rax
0x18006ee59  mov     r14, rcx
0x18006ee5c  mov     [rsp+740h+var_6E8], 0
0x18006ee65  cmp     qword ptr [rcx+718h], 0
0x18006ee6d  jz      loc_18006F0C4
0x18006ee73  movups  xmm0, cs:EVENT_TERMINAL_LOGON_TOOLONG
0x18006ee7a  movdqu  xmmword ptr [rsp+740h+var_6E0.Id], xmm0
0x18006ee80  lea     rdx, [rcx+0C88h]; struct _GUID *
0x18006ee87  lea     rax, aPnewterminalLo_1; "pNewTerminal->LoggedOnCompleted"
0x18006ee8e  mov     [rsp+740h+var_718], rax; char *
0x18006ee93  lea     rax, [rsp+740h+var_6E0]
0x18006ee98  mov     [rsp+740h+var_720], rax; struct _EVENT_DESCRIPTOR
0x18006ee9d  mov     r9, rcx; struct ITSSession *
0x18006eea0  mov     r8d, [rcx+6D0h]; int
0x18006eea7  lea     rcx, [rbp+640h+Parameter]; Parameter
0x18006eeab  call    ??0CTSTerminalOpsMonitor@@QEAA@PEAU_GUID@@JPEAUITSSession@@U_EVENT_DESCRIPTOR@@PEBDK@Z; CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(_GUID *,long,ITSSession *,_EVENT_DESCRIPTOR,char const *,ulong)
0x18006eeb0  nop
0x18006eeb1  mov     rcx, [r14+718h]; struct ITerminal *
0x18006eeb8  call    ?IsLocalGlassTerminal@CGlassTerminal@@SAHPEAUITerminal@@@Z; CGlassTerminal::IsLocalGlassTerminal(ITerminal *)
0x18006eebd  mov     edi, eax
0x18006eebf  call    cs:__imp_GetTickCount64
0x18006eec6  nop     dword ptr [rax+rax+00h]
0x18006eecb  mov     r15, rax
0x18006eece  mov     r8, [r14+718h]
0x18006eed5  mov     rcx, [r8]
0x18006eed8  mov     rax, [rcx+48h]
0x18006eedc  mov     rdx, [r14+1728h]
0x18006eee3  mov     rcx, r8
0x18006eee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eeeb  mov     esi, eax
0x18006eeed  call    cs:__imp_GetTickCount64
0x18006eef4  nop     dword ptr [rax+rax+00h]
0x18006eef9  mov     rbx, rax
0x18006eefc  test    esi, esi
0x18006eefe  js      short loc_18006EF76
0x18006ef00  test    edi, edi
0x18006ef02  jnz     short loc_18006EF76
0x18006ef04  call    ?WriteLastRemoteLogonTime@CTSSession@@AEAAJXZ; CTSSession::WriteLastRemoteLogonTime(void)
0x18006ef09  mov     esi, eax
0x18006ef0b  test    eax, eax
0x18006ef0d  jns     short loc_18006EF76
0x18006ef0f  mov     ecx, cs:dword_1800DF020
0x18006ef15  cmp     ecx, 3
0x18006ef18  jbe     short loc_18006EF76
0x18006ef1a  lea     rax, aOnlogoncomplet; "OnLogonCompleted"
0x18006ef21  mov     [rsp+740h+phModule], rax
0x18006ef26  mov     [rsp+740h+var_700], esi
0x18006ef2a  lea     rax, aUnableToWriteL; "unable to write LastRemoteLogonTime to "...
0x18006ef31  mov     qword ptr [rsp+740h+var_6F0], rax
0x18006ef36  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18006ef3d  mov     qword ptr [rsp+740h+var_6E0.Id], rax
0x18006ef42  lea     rax, [rsp+740h+phModule]
0x18006ef47  mov     qword ptr [rsp+740h+var_708], rax
0x18006ef4c  lea     rax, [rsp+740h+var_700]
0x18006ef51  mov     qword ptr [rsp+740h+var_710], rax
0x18006ef56  lea     rax, [rsp+740h+var_6F0]
0x18006ef5b  mov     [rsp+740h+var_718], rax
0x18006ef60  lea     rax, [rsp+740h+var_6E0]
0x18006ef65  mov     [rsp+740h+var_720], rax
0x18006ef6a  lea     rdx, word_1800C91F6
0x18006ef71  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006ef76  mov     eax, cs:dword_1800DF020
0x18006ef7c  cmp     eax, 4
0x18006ef7f  jbe     short loc_18006EFCA
0x18006ef81  sub     rbx, r15
0x18006ef84  mov     qword ptr [rsp+740h+var_6E0.Id], rbx
0x18006ef89  mov     eax, [r14+6D0h]
0x18006ef90  mov     [rsp+740h+var_700], eax
0x18006ef94  lea     rax, aPtrterminalOnl; "ptrTerminal->OnLogonCompleted took this"...
0x18006ef9b  mov     [rsp+740h+phModule], rax
0x18006efa0  lea     rax, [rsp+740h+var_6E0]
0x18006efa5  mov     qword ptr [rsp+740h+var_710], rax
0x18006efaa  lea     rax, [rsp+740h+var_700]
0x18006efaf  mov     [rsp+740h+var_718], rax
0x18006efb4  lea     rax, [rsp+740h+phModule]
0x18006efb9  mov     [rsp+740h+var_720], rax
0x18006efbe  lea     rdx, word_1800C919E
0x18006efc5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18006efca  test    esi, esi
0x18006efcc  jns     short loc_18006EFF8
0x18006efce  mov     r8d, esi
0x18006efd1  lea     rdx, aTerminalOnlogo; "Terminal->OnLogonCompleted failed: 0x%x"...
0x18006efd8  lea     r9, aCtssessionOnlo_0; "CTSSession::OnLogonCompleted"
0x18006efdf  mov     ecx, 8; int
0x18006efe4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006efe9  nop
0x18006efea  lea     rcx, [rbp+640h+Parameter]; this
0x18006efee  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006eff3  jmp     loc_18006F2C4
0x18006eff8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif> `wil::Feature<__WilFeatureTraits_Feature_LogonCompletedNotif>::GetImpl(void)'::`2'::impl
0x18006efff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif>::__private_IsEnabled(void)
0x18006f004  test    al, al
0x18006f006  jz      loc_18006F0BB
0x18006f00c  xorps   xmm0, xmm0
0x18006f00f  xor     eax, eax
0x18006f011  movups  xmmword ptr [rsp+740h+var_6E0.Id], xmm0
0x18006f016  movups  [rsp+740h+var_6D0], xmm0
0x18006f01b  movups  [rbp+640h+var_6C0], xmm0
0x18006f01f  mov     [rbp+640h+var_6B0], rax
0x18006f023  lea     rdx, [rsp+740h+var_6E0]; struct __PTSSessInfo *
0x18006f028  mov     rcx, r14; this
0x18006f02b  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18006f030  mov     esi, eax
0x18006f032  test    eax, eax
0x18006f034  jns     short loc_18006F042
0x18006f036  mov     r8d, eax
0x18006f039  lea     rdx, aInitializenoti_0; "InitializeNotifyInfo failed: 0x%x in %s"
0x18006f040  jmp     short loc_18006EFD8
0x18006f042  mov     r8d, [r14+0CB8h]
0x18006f049  mov     rcx, [r14+720h]
0x18006f050  add     rcx, 728h
0x18006f057  mov     rax, [rcx]
0x18006f05a  mov     r9d, r8d
0x18006f05d  lea     rdx, [rsp+740h+var_6E0]
0x18006f062  mov     rax, [rax+0C0h]
0x18006f069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f06e  test    eax, eax
0x18006f070  jns     short loc_18006F086
0x18006f072  mov     r8d, eax
0x18006f075  lea     rdx, aEventdispatchO_0; "EventDispatch->OnLogonCompleted failed:"...
0x18006f07c  mov     ecx, 8; int
0x18006f081  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006f086  mov     rcx, qword ptr [rsp+740h+var_6E0.Id]
0x18006f08b  test    rcx, rcx
0x18006f08e  jz      short loc_18006F0A5
0x18006f090  mov     rax, [rcx]
0x18006f093  mov     rax, [rax+10h]
0x18006f097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f09c  mov     qword ptr [rsp+740h+var_6E0.Id], 0
0x18006f0a5  mov     rcx, qword ptr [rbp+640h+var_6C0]
0x18006f0a9  test    rcx, rcx
0x18006f0ac  jz      short loc_18006F0BB
0x18006f0ae  mov     rax, [rcx]
0x18006f0b1  mov     rax, [rax+10h]
0x18006f0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f0ba  nop
0x18006f0bb  lea     rcx, [rbp+640h+Parameter]; this
0x18006f0bf  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006f0c4  lea     rcx, [rsp+740h+var_6E8]; struct ISessionManagerInternal **
0x18006f0c9  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18006f0ce  mov     esi, eax
0x18006f0d0  test    eax, eax
0x18006f0d2  js      loc_18006F2C4
0x18006f0d8  mov     rdi, [rsp+740h+var_6E8]
0x18006f0dd  mov     rax, [rdi]
0x18006f0e0  mov     rbx, [rax+0E0h]
0x18006f0e7  lea     rdx, [r14+1738h]
0x18006f0ee  lea     rcx, [rsp+740h+var_6E0]
0x18006f0f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006f0f8  mov     rdx, rax
0x18006f0fb  mov     rcx, rdi
0x18006f0fe  mov     rax, rbx
0x18006f101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f106  test    eax, eax
0x18006f108  jnz     loc_18006F2C4
0x18006f10e  mov     eax, cs:dword_1800DF020
0x18006f114  mov     ebx, 2
0x18006f119  cmp     eax, ebx
0x18006f11b  jbe     short loc_18006F13F
0x18006f11d  lea     rax, aDwmPreviouslyC; "DWM previously crashed for this user"
0x18006f124  mov     qword ptr [rsp+740h+var_6E0.Id], rax
0x18006f129  lea     rax, [rsp+740h+var_6E0]
0x18006f12e  mov     [rsp+740h+var_720], rax
0x18006f133  lea     rdx, dword_1800C9184
0x18006f13a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006f13f  mov     [rsp+740h+phModule], 0
0x18006f148  lea     r8, [rsp+740h+phModule]; phModule
0x18006f14d  lea     rdx, aLsmDll_0; "lsm.dll"
0x18006f154  mov     ecx, ebx; dwFlags
0x18006f156  call    cs:__imp_GetModuleHandleExW
0x18006f15d  nop     dword ptr [rax+rax+00h]
0x18006f162  test    eax, eax
0x18006f164  jnz     short loc_18006F1C4
0x18006f166  call    cs:__imp_GetLastError
0x18006f16d  nop     dword ptr [rax+rax+00h]
0x18006f172  mov     esi, eax
0x18006f174  test    eax, eax
0x18006f176  jle     short loc_18006F181
0x18006f178  movzx   esi, ax
0x18006f17b  or      esi, 80070000h
0x18006f181  mov     eax, cs:dword_1800DF020
0x18006f187  cmp     eax, ebx
0x18006f189  jbe     loc_18006F2C4
0x18006f18f  lea     rax, aFailedLoadingM_1; "Failed loading module in OnLogonComplet"...
0x18006f196  lea     rdx, byte_1800C9165
0x18006f19d  mov     qword ptr [rsp+740h+var_6E0.Id], rax
0x18006f1a2  lea     rax, [rsp+740h+var_700]
0x18006f1a7  mov     [rsp+740h+var_718], rax
0x18006f1ac  lea     rax, [rsp+740h+var_6E0]
0x18006f1b1  mov     [rsp+740h+var_720], rax
0x18006f1b6  mov     [rsp+740h+var_700], esi
0x18006f1ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006f1bf  jmp     loc_18006F2C4
0x18006f1c4  mov     r9d, 100h; cchBufferMax
0x18006f1ca  lea     r8, [rbp+640h+Buffer]; lpBuffer
0x18006f1ce  mov     edx, 3EBh; uID
0x18006f1d3  mov     rcx, [rsp+740h+phModule]; hInstance
0x18006f1d8  call    cs:__imp_LoadStringW
0x18006f1df  nop     dword ptr [rax+rax+00h]
0x18006f1e4  test    eax, eax
0x18006f1e6  jnz     short loc_18006F224
0x18006f1e8  call    cs:__imp_GetLastError
0x18006f1ef  nop     dword ptr [rax+rax+00h]
0x18006f1f4  mov     esi, eax
0x18006f1f6  test    eax, eax
0x18006f1f8  jle     short loc_18006F203
0x18006f1fa  movzx   esi, ax
0x18006f1fd  or      esi, 80070000h
0x18006f203  mov     eax, cs:dword_1800DF020
0x18006f209  cmp     eax, ebx
0x18006f20b  jbe     loc_18006F2C4
0x18006f211  lea     rax, aFailedLoadingT; "Failed loading title in OnLogonComplete"...
0x18006f218  lea     rdx, word_1800C9146
0x18006f21f  jmp     loc_18006F19D
0x18006f224  mov     r9d, 200h; cchBufferMax
0x18006f22a  lea     r8, [rbp+640h+var_440]; lpBuffer
0x18006f231  mov     edx, 3ECh; uID
0x18006f236  mov     rcx, [rsp+740h+phModule]; hInstance
0x18006f23b  call    cs:__imp_LoadStringW
0x18006f242  nop     dword ptr [rax+rax+00h]
0x18006f247  test    eax, eax
0x18006f249  jnz     short loc_18006F283
0x18006f24b  call    cs:__imp_GetLastError
0x18006f252  nop     dword ptr [rax+rax+00h]
0x18006f257  mov     esi, eax
0x18006f259  test    eax, eax
0x18006f25b  jle     short loc_18006F266
0x18006f25d  movzx   esi, ax
0x18006f260  or      esi, 80070000h
0x18006f266  mov     eax, cs:dword_1800DF020
0x18006f26c  cmp     eax, ebx
0x18006f26e  jbe     short loc_18006F2C4
0x18006f270  lea     rax, aFailedLoadingM_0; "Failed loading message in OnLogonComple"...
0x18006f277  lea     rdx, byte_1800C9127
0x18006f27e  jmp     loc_18006F19D
0x18006f283  mov     [rsp+740h+var_6F0], 0
0x18006f28b  mov     eax, 1
0x18006f290  mov     [rsp+740h+var_708], eax; int
0x18006f294  mov     [rsp+740h+var_710], eax; int
0x18006f298  lea     rax, [rsp+740h+var_6F0]
0x18006f29d  mov     [rsp+740h+var_718], rax; unsigned int *
0x18006f2a2  mov     dword ptr [rsp+740h+var_720], 7530h; unsigned int
0x18006f2aa  mov     r9d, 10h; unsigned int
0x18006f2b0  lea     r8, [rbp+640h+var_440]; unsigned __int16 *
0x18006f2b7  lea     rdx, [rbp+640h+Buffer]; unsigned __int16 *
0x18006f2bb  mov     rcx, r14; this
0x18006f2be  call    ?ShowMessageBox@CTSSession@@UEAAJPEBG0KKPEAKHH@Z; CTSSession::ShowMessageBox(ushort const *,ushort const *,ulong,ulong,ulong *,int,int)
0x18006f2c3  nop
0x18006f2c4  lea     rcx, [rsp+740h+var_6E8]
0x18006f2c9  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006f2ce  mov     eax, esi
0x18006f2d0  mov     rcx, [rbp+640h+var_40]
0x18006f2d7  xor     rcx, rsp; StackCookie
0x18006f2da  call    __security_check_cookie
0x18006f2df  add     rsp, 718h
0x18006f2e6  pop     r15
0x18006f2e8  pop     r14
0x18006f2ea  pop     rdi
0x18006f2eb  pop     rsi
0x18006f2ec  pop     rbx
0x18006f2ed  pop     rbp
0x18006f2ee  retn
```
