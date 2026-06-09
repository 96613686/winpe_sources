# CTSSession::OnLogonCompleted(void)

- ea: `0x18006afe0`
- end: `0x18006b46c`
- name: `?OnLogonCompleted@CTSSession@@UEAAJXZ`
- size: `1164`
- prototype: `__int64 __fastcall(CTSSession *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001b80`
- `0x1800074c0`
- `0x180008f64`
- `0x180009a68`
- `0x180009b2c`
- `0x180014ff0`
- `0x1800186a0`
- `0x180024884`
- `0x180025070`
- `0x180025600`
- `0x180025890`
- `0x18002d31c`
- `0x18004b460`
- `0x18006afe0`
- `0x18006df40`
- `0x18006f140`
- `0x18006f3a4`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006b2fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006b2fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b06f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b097`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b06f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006b097`
- `USER32!LoadStringW` at `0x18006b370`
- `USER32!LoadStringW` at `0x18006b3c4`
- `USER32!LoadStringW` at `0x18006b370`
- `USER32!LoadStringW` at `0x18006b3c4`

## string_xrefs

- `0x18006b0ce`: `unable to write LastRemoteLogonTime to registry`
- `0x18006b037`: `pNewTerminal->LoggedOnCompleted`
- `0x18006b0be`: `OnLogonCompleted`
- `0x18006b138`: `ptrTerminal->OnLogonCompleted took this long`
- `0x18006b17c`: `CTSSession::OnLogonCompleted`
- `0x18006b175`: `Terminal->OnLogonCompleted failed: 0x%x in %s`
- `0x18006b219`: `EventDispatch->OnLogonCompleted failed: 0x%x`
- `0x18006b2f1`: `lsm.dll`
- `0x18006b327`: `Failed loading module in OnLogonCompleted`
- `0x18006b39d`: `Failed loading title in OnLogonCompleted`
- `0x18006b3ed`: `Failed loading message in OnLogonCompleted`

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
        LODWORD(v5) = dword_1800DA020;
        if ( (unsigned int)dword_1800DA020 > 3 )
        {
          phModule = (HMODULE)"OnLogonCompleted";
          v28 = v9;
          *(_QWORD *)v30 = "unable to write LastRemoteLogonTime to registry";
          *(_QWORD *)&v32.Id = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            dword_1800DA020,
            (unsigned int)&word_1800C406E,
            v7,
            v8,
            (__int64)&v32,
            (__int64)v30,
            (__int64)&v28,
            (__int64)&phModule);
        }
      }
    }
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      *(_QWORD *)&v32.Id = v6 - TickCount64;
      v28 = *((_DWORD *)this + 436);
      phModule = (HMODULE)"ptrTerminal->OnLogonCompleted took this long";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v5,
        (unsigned int)&word_1800C4016,
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
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        *(_QWORD *)&v32.Id = "DWM previously crashed for this user";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v15,
          (unsigned int)&dword_1800C3FFC,
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
          if ( (unsigned int)dword_1800DA020 > 2 )
          {
            v22 = "Failed loading message in OnLogonCompleted";
            v23 = &byte_1800C3F9F;
            goto LABEL_31;
          }
        }
        else
        {
          v24 = GetLastError();
          InstanceOfSessionManagerInternal = v24;
          if ( v24 > 0 )
            InstanceOfSessionManagerInternal = (unsigned __int16)v24 | 0x80070000;
          if ( (unsigned int)dword_1800DA020 > 2 )
          {
            v22 = "Failed loading title in OnLogonCompleted";
            v23 = (char *)&word_1800C3FBE;
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
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          v22 = "Failed loading module in OnLogonCompleted";
          v23 = byte_1800C3FDD;
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
0x18006afe0  push    rbp
0x18006afe2  push    rbx
0x18006afe3  push    rsi
0x18006afe4  push    rdi
0x18006afe5  push    r14
0x18006afe7  push    r15
0x18006afe9  lea     rbp, [rsp-618h]
0x18006aff1  sub     rsp, 718h
0x18006aff8  mov     rax, cs:__security_cookie
0x18006afff  xor     rax, rsp
0x18006b002  mov     [rbp+640h+var_40], rax
0x18006b009  mov     r14, rcx
0x18006b00c  mov     [rsp+740h+var_6E8], 0
0x18006b015  cmp     qword ptr [rcx+718h], 0
0x18006b01d  jz      loc_18006B268
0x18006b023  movups  xmm0, cs:EVENT_TERMINAL_LOGON_TOOLONG
0x18006b02a  movdqu  xmmword ptr [rsp+740h+var_6E0.Id], xmm0
0x18006b030  lea     rdx, [rcx+0C88h]; struct _GUID *
0x18006b037  lea     rax, aPnewterminalLo_1; "pNewTerminal->LoggedOnCompleted"
0x18006b03e  mov     [rsp+740h+var_718], rax; char *
0x18006b043  lea     rax, [rsp+740h+var_6E0]
0x18006b048  mov     [rsp+740h+var_720], rax; struct _EVENT_DESCRIPTOR
0x18006b04d  mov     r9, rcx; struct ITSSession *
0x18006b050  mov     r8d, [rcx+6D0h]; int
0x18006b057  lea     rcx, [rbp+640h+Parameter]; Parameter
0x18006b05b  call    ??0CTSTerminalOpsMonitor@@QEAA@PEAU_GUID@@JPEAUITSSession@@U_EVENT_DESCRIPTOR@@PEBDK@Z; CTSTerminalOpsMonitor::CTSTerminalOpsMonitor(_GUID *,long,ITSSession *,_EVENT_DESCRIPTOR,char const *,ulong)
0x18006b060  nop
0x18006b061  mov     rcx, [r14+718h]; struct ITerminal *
0x18006b068  call    ?IsLocalGlassTerminal@CGlassTerminal@@SAHPEAUITerminal@@@Z; CGlassTerminal::IsLocalGlassTerminal(ITerminal *)
0x18006b06d  mov     edi, eax
0x18006b06f  call    cs:__imp_GetTickCount64
0x18006b075  mov     r15, rax
0x18006b078  mov     r8, [r14+718h]
0x18006b07f  mov     rcx, [r8]
0x18006b082  mov     rax, [rcx+48h]
0x18006b086  mov     rdx, [r14+1728h]
0x18006b08d  mov     rcx, r8
0x18006b090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b095  mov     esi, eax
0x18006b097  call    cs:__imp_GetTickCount64
0x18006b09d  mov     rbx, rax
0x18006b0a0  test    esi, esi
0x18006b0a2  js      short loc_18006B11A
0x18006b0a4  test    edi, edi
0x18006b0a6  jnz     short loc_18006B11A
0x18006b0a8  call    ?WriteLastRemoteLogonTime@CTSSession@@AEAAJXZ; CTSSession::WriteLastRemoteLogonTime(void)
0x18006b0ad  mov     esi, eax
0x18006b0af  test    eax, eax
0x18006b0b1  jns     short loc_18006B11A
0x18006b0b3  mov     ecx, cs:dword_1800DA020
0x18006b0b9  cmp     ecx, 3
0x18006b0bc  jbe     short loc_18006B11A
0x18006b0be  lea     rax, aOnlogoncomplet; "OnLogonCompleted"
0x18006b0c5  mov     [rsp+740h+phModule], rax
0x18006b0ca  mov     [rsp+740h+var_700], esi
0x18006b0ce  lea     rax, aUnableToWriteL; "unable to write LastRemoteLogonTime to "...
0x18006b0d5  mov     qword ptr [rsp+740h+var_6F0], rax
0x18006b0da  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18006b0e1  mov     qword ptr [rsp+740h+var_6E0.Id], rax
0x18006b0e6  lea     rax, [rsp+740h+phModule]
0x18006b0eb  mov     qword ptr [rsp+740h+var_708], rax
0x18006b0f0  lea     rax, [rsp+740h+var_700]
0x18006b0f5  mov     qword ptr [rsp+740h+var_710], rax
0x18006b0fa  lea     rax, [rsp+740h+var_6F0]
0x18006b0ff  mov     [rsp+740h+var_718], rax
0x18006b104  lea     rax, [rsp+740h+var_6E0]
0x18006b109  mov     [rsp+740h+var_720], rax
0x18006b10e  lea     rdx, word_1800C406E
0x18006b115  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18006b11a  mov     eax, cs:dword_1800DA020
0x18006b120  cmp     eax, 4
0x18006b123  jbe     short loc_18006B16E
0x18006b125  sub     rbx, r15
0x18006b128  mov     qword ptr [rsp+740h+var_6E0.Id], rbx
0x18006b12d  mov     eax, [r14+6D0h]
0x18006b134  mov     [rsp+740h+var_700], eax
0x18006b138  lea     rax, aPtrterminalOnl; "ptrTerminal->OnLogonCompleted took this"...
0x18006b13f  mov     [rsp+740h+phModule], rax
0x18006b144  lea     rax, [rsp+740h+var_6E0]
0x18006b149  mov     qword ptr [rsp+740h+var_710], rax
0x18006b14e  lea     rax, [rsp+740h+var_700]
0x18006b153  mov     [rsp+740h+var_718], rax
0x18006b158  lea     rax, [rsp+740h+phModule]
0x18006b15d  mov     [rsp+740h+var_720], rax
0x18006b162  lea     rdx, word_1800C4016
0x18006b169  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18006b16e  test    esi, esi
0x18006b170  jns     short loc_18006B19C
0x18006b172  mov     r8d, esi
0x18006b175  lea     rdx, aTerminalOnlogo; "Terminal->OnLogonCompleted failed: 0x%x"...
0x18006b17c  lea     r9, aCtssessionOnlo_0; "CTSSession::OnLogonCompleted"
0x18006b183  mov     ecx, 8; int
0x18006b188  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b18d  nop
0x18006b18e  lea     rcx, [rbp+640h+Parameter]; this
0x18006b192  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006b197  jmp     loc_18006B441
0x18006b19c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif> `wil::Feature<__WilFeatureTraits_Feature_LogonCompletedNotif>::GetImpl(void)'::`2'::impl
0x18006b1a3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LogonCompletedNotif@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogonCompletedNotif>::__private_IsEnabled(void)
0x18006b1a8  test    al, al
0x18006b1aa  jz      loc_18006B25F
0x18006b1b0  xorps   xmm0, xmm0
0x18006b1b3  xor     eax, eax
0x18006b1b5  movups  xmmword ptr [rsp+740h+var_6E0.Id], xmm0
0x18006b1ba  movups  [rsp+740h+var_6D0], xmm0
0x18006b1bf  movups  [rbp+640h+var_6C0], xmm0
0x18006b1c3  mov     [rbp+640h+var_6B0], rax
0x18006b1c7  lea     rdx, [rsp+740h+var_6E0]; struct __PTSSessInfo *
0x18006b1cc  mov     rcx, r14; this
0x18006b1cf  call    ?InitializeNotifyInfo@CTSSession@@AEAAJPEAU__PTSSessInfo@@@Z; CTSSession::InitializeNotifyInfo(__PTSSessInfo *)
0x18006b1d4  mov     esi, eax
0x18006b1d6  test    eax, eax
0x18006b1d8  jns     short loc_18006B1E6
0x18006b1da  mov     r8d, eax
0x18006b1dd  lea     rdx, aInitializenoti_0; "InitializeNotifyInfo failed: 0x%x in %s"
0x18006b1e4  jmp     short loc_18006B17C
0x18006b1e6  mov     r8d, [r14+0CB8h]
0x18006b1ed  mov     rcx, [r14+720h]
0x18006b1f4  add     rcx, 728h
0x18006b1fb  mov     rax, [rcx]
0x18006b1fe  mov     r9d, r8d
0x18006b201  lea     rdx, [rsp+740h+var_6E0]
0x18006b206  mov     rax, [rax+0C0h]
0x18006b20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b212  test    eax, eax
0x18006b214  jns     short loc_18006B22A
0x18006b216  mov     r8d, eax
0x18006b219  lea     rdx, aEventdispatchO_0; "EventDispatch->OnLogonCompleted failed:"...
0x18006b220  mov     ecx, 8; int
0x18006b225  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006b22a  mov     rcx, qword ptr [rsp+740h+var_6E0.Id]
0x18006b22f  test    rcx, rcx
0x18006b232  jz      short loc_18006B249
0x18006b234  mov     rax, [rcx]
0x18006b237  mov     rax, [rax+10h]
0x18006b23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b240  mov     qword ptr [rsp+740h+var_6E0.Id], 0
0x18006b249  mov     rcx, qword ptr [rbp+640h+var_6C0]
0x18006b24d  test    rcx, rcx
0x18006b250  jz      short loc_18006B25F
0x18006b252  mov     rax, [rcx]
0x18006b255  mov     rax, [rax+10h]
0x18006b259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b25e  nop
0x18006b25f  lea     rcx, [rbp+640h+Parameter]; this
0x18006b263  call    ??1CTSTerminalOpsMonitor@@UEAA@XZ; CTSTerminalOpsMonitor::~CTSTerminalOpsMonitor(void)
0x18006b268  lea     rcx, [rsp+740h+var_6E8]; struct ISessionManagerInternal **
0x18006b26d  call    ?GetInstanceOfSessionManagerInternal@ISessionManagerInternal@@SAJPEAPEAV1@@Z; ISessionManagerInternal::GetInstanceOfSessionManagerInternal(ISessionManagerInternal * *)
0x18006b272  mov     esi, eax
0x18006b274  test    eax, eax
0x18006b276  js      loc_18006B441
0x18006b27c  mov     rdi, [rsp+740h+var_6E8]
0x18006b281  mov     rax, [rdi]
0x18006b284  mov     rbx, [rax+0E0h]
0x18006b28b  lea     rdx, [r14+1738h]
0x18006b292  lea     rcx, [rsp+740h+var_6E0]
0x18006b297  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b29c  mov     rdx, rax
0x18006b29f  mov     rcx, rdi
0x18006b2a2  mov     rax, rbx
0x18006b2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2aa  test    eax, eax
0x18006b2ac  jnz     loc_18006B441
0x18006b2b2  mov     eax, cs:dword_1800DA020
0x18006b2b8  mov     ebx, 2
0x18006b2bd  cmp     eax, ebx
0x18006b2bf  jbe     short loc_18006B2E3
0x18006b2c1  lea     rax, aDwmPreviouslyC; "DWM previously crashed for this user"
0x18006b2c8  mov     qword ptr [rsp+740h+var_6E0.Id], rax
0x18006b2cd  lea     rax, [rsp+740h+var_6E0]
0x18006b2d2  mov     [rsp+740h+var_720], rax
0x18006b2d7  lea     rdx, dword_1800C3FFC
0x18006b2de  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006b2e3  mov     [rsp+740h+phModule], 0
0x18006b2ec  lea     r8, [rsp+740h+phModule]; phModule
0x18006b2f1  lea     rdx, aLsmDll_0; "lsm.dll"
0x18006b2f8  mov     ecx, ebx; dwFlags
0x18006b2fa  call    cs:__imp_GetModuleHandleExW
0x18006b300  test    eax, eax
0x18006b302  jnz     short loc_18006B35C
0x18006b304  call    cs:__imp_GetLastError
0x18006b30a  mov     esi, eax
0x18006b30c  test    eax, eax
0x18006b30e  jle     short loc_18006B319
0x18006b310  movzx   esi, ax
0x18006b313  or      esi, 80070000h
0x18006b319  mov     eax, cs:dword_1800DA020
0x18006b31f  cmp     eax, ebx
0x18006b321  jbe     loc_18006B441
0x18006b327  lea     rax, aFailedLoadingM_1; "Failed loading module in OnLogonComplet"...
0x18006b32e  lea     rdx, byte_1800C3FDD
0x18006b335  mov     qword ptr [rsp+740h+var_6E0.Id], rax
0x18006b33a  lea     rax, [rsp+740h+var_700]
0x18006b33f  mov     [rsp+740h+var_718], rax
0x18006b344  lea     rax, [rsp+740h+var_6E0]
0x18006b349  mov     [rsp+740h+var_720], rax
0x18006b34e  mov     [rsp+740h+var_700], esi
0x18006b352  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006b357  jmp     loc_18006B441
0x18006b35c  mov     r9d, 100h; cchBufferMax
0x18006b362  lea     r8, [rbp+640h+Buffer]; lpBuffer
0x18006b366  mov     edx, 3EBh; uID
0x18006b36b  mov     rcx, [rsp+740h+phModule]; hInstance
0x18006b370  call    cs:__imp_LoadStringW
0x18006b376  test    eax, eax
0x18006b378  jnz     short loc_18006B3AD
0x18006b37a  call    cs:__imp_GetLastError
0x18006b380  mov     esi, eax
0x18006b382  test    eax, eax
0x18006b384  jle     short loc_18006B38F
0x18006b386  movzx   esi, ax
0x18006b389  or      esi, 80070000h
0x18006b38f  mov     eax, cs:dword_1800DA020
0x18006b395  cmp     eax, ebx
0x18006b397  jbe     loc_18006B441
0x18006b39d  lea     rax, aFailedLoadingT; "Failed loading title in OnLogonComplete"...
0x18006b3a4  lea     rdx, word_1800C3FBE
0x18006b3ab  jmp     short loc_18006B335
0x18006b3ad  mov     r9d, 200h; cchBufferMax
0x18006b3b3  lea     r8, [rbp+640h+var_440]; lpBuffer
0x18006b3ba  mov     edx, 3ECh; uID
0x18006b3bf  mov     rcx, [rsp+740h+phModule]; hInstance
0x18006b3c4  call    cs:__imp_LoadStringW
0x18006b3ca  test    eax, eax
0x18006b3cc  jnz     short loc_18006B400
0x18006b3ce  call    cs:__imp_GetLastError
0x18006b3d4  mov     esi, eax
0x18006b3d6  test    eax, eax
0x18006b3d8  jle     short loc_18006B3E3
0x18006b3da  movzx   esi, ax
0x18006b3dd  or      esi, 80070000h
0x18006b3e3  mov     eax, cs:dword_1800DA020
0x18006b3e9  cmp     eax, ebx
0x18006b3eb  jbe     short loc_18006B441
0x18006b3ed  lea     rax, aFailedLoadingM_0; "Failed loading message in OnLogonComple"...
0x18006b3f4  lea     rdx, byte_1800C3F9F
0x18006b3fb  jmp     loc_18006B335
0x18006b400  mov     [rsp+740h+var_6F0], 0
0x18006b408  mov     eax, 1
0x18006b40d  mov     [rsp+740h+var_708], eax; int
0x18006b411  mov     [rsp+740h+var_710], eax; int
0x18006b415  lea     rax, [rsp+740h+var_6F0]
0x18006b41a  mov     [rsp+740h+var_718], rax; unsigned int *
0x18006b41f  mov     dword ptr [rsp+740h+var_720], 7530h; unsigned int
0x18006b427  mov     r9d, 10h; unsigned int
0x18006b42d  lea     r8, [rbp+640h+var_440]; unsigned __int16 *
0x18006b434  lea     rdx, [rbp+640h+Buffer]; unsigned __int16 *
0x18006b438  mov     rcx, r14; this
0x18006b43b  call    ?ShowMessageBox@CTSSession@@UEAAJPEBG0KKPEAKHH@Z; CTSSession::ShowMessageBox(ushort const *,ushort const *,ulong,ulong,ulong *,int,int)
0x18006b440  nop
0x18006b441  lea     rcx, [rsp+740h+var_6E8]
0x18006b446  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18006b44b  mov     eax, esi
0x18006b44d  mov     rcx, [rbp+640h+var_40]
0x18006b454  xor     rcx, rsp; StackCookie
0x18006b457  call    __security_check_cookie
0x18006b45c  add     rsp, 718h
0x18006b463  pop     r15
0x18006b465  pop     r14
0x18006b467  pop     rdi
0x18006b468  pop     rsi
0x18006b469  pop     rbx
0x18006b46a  pop     rbp
0x18006b46b  retn
```
