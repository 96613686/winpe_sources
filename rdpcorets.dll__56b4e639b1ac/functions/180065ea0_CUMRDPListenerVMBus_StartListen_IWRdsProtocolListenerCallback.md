# CUMRDPListenerVMBus::StartListen(IWRdsProtocolListenerCallback *)

- ea: `0x180065ea0`
- end: `0x18006643b`
- name: `?StartListen@CUMRDPListenerVMBus@@UEAAJPEAUIWRdsProtocolListenerCallback@@@Z`
- size: `1435`
- prototype: `__int64 __fastcall(HMODULE *this, struct IWRdsProtocolListenerCallback *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x180012200`
- `0x180041ff0`
- `0x1800653e0`
- `0x180065ea0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066129`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800661e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006629b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066354`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066129`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800661e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006629b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006613f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800662b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006636a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006613f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800662b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006636a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006606a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006606a`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180065ede`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180065ede`
- `OLEAUT32!__imp_VariantInit` at `0x180065f89`
- `OLEAUT32!__imp_VariantInit` at `0x180065f89`
- `OLEAUT32!__imp_VariantClear` at `0x18006605d`
- `OLEAUT32!__imp_VariantClear` at `0x18006605d`

## string_xrefs

- `0x180066063`: `vmbuspipe.dll`
- `0x180066122`: `VmbusPipeClientOpenChannel`
- `0x180066164`: `Failed to get proc address for VmbusPipeClientOpenChannel`
- `0x18006634d`: `VmbusPipeClientReadyForChannelNotification`
- `0x18006638b`: `Failed to get proc address for VmbusPipeClientReadyForChannelNotification`

## pseudocode

```c
__int64 __fastcall CUMRDPListenerVMBus::StartListen(
        HMODULE *this,
        struct IWRdsProtocolListenerCallback *a2,
        __int64 a3)
{
  char *v4; // rcx
  int started; // ebx
  __int64 v7; // r8
  int v8; // r9d
  int v9; // ecx
  char *v10; // rdx
  const char **v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rcx
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  signed int v16; // eax
  FARPROC v17; // rax
  signed int v18; // eax
  FARPROC v19; // rax
  signed int v20; // eax
  FARPROC v21; // rax
  __int64 v22; // rdx
  signed int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  const char **v27; // [rsp+30h] [rbp-29h]
  const char **v28; // [rsp+40h] [rbp-19h]
  const char **v29; // [rsp+48h] [rbp-11h]
  const char *v30; // [rsp+50h] [rbp-9h] BYREF
  const char *v31; // [rsp+58h] [rbp-1h] BYREF
  const char *v32; // [rsp+60h] [rbp+7h] BYREF
  const char *v33; // [rsp+68h] [rbp+Fh] BYREF
  char *v34; // [rsp+70h] [rbp+17h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp+1Fh] BYREF
  int v36; // [rsp+C0h] [rbp+67h] BYREF
  int v37; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v38; // [rsp+D8h] [rbp+7Fh] BYREF

  v38 = 0;
  v4 = (char *)(this + 11);
  memset(&pvarg, 0, sizeof(pvarg));
  v34 = v4;
  if ( *((_DWORD *)v4 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v4, a2, a3);
  started = CUMRDPListenerBase::StartListen((CUMRDPListenerBase *)this, a2);
  if ( started < 0 )
  {
    v9 = dword_1801B76C8;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_41;
    v36 = 300;
    v30 = "Failed to start listener.";
    v10 = byte_18019CC9D;
    v31 = "StartListen";
    v32 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
    v33 = "Error HResult failed";
    v29 = &v30;
    v28 = &v31;
    v27 = &v32;
    v11 = &v33;
    goto LABEL_6;
  }
  VariantInit(&pvarg);
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))this[13];
  pvarg.vt = 11;
  pvarg.iVal = -1;
  started = (**v12)(v12, &IID_IRDPENCPlatformContext, &v38);
  if ( started >= 0 )
  {
    (*(void (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v38 + 56LL))(
      v38,
      L"ExternalSSLEncryption",
      &pvarg);
    VariantClear(&pvarg);
    LibraryW = LoadLibraryW(L"vmbuspipe.dll");
    this[53] = LibraryW;
    if ( LibraryW )
      goto LABEL_16;
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    if ( started >= 0 )
    {
LABEL_16:
      ProcAddress = GetProcAddress(this[53], "VmbusPipeClientOpenChannel");
      this[54] = (HMODULE)ProcAddress;
      if ( ProcAddress )
        goto LABEL_22;
      v16 = GetLastError();
      started = v16;
      if ( v16 > 0 )
        started = (unsigned __int16)v16 | 0x80070000;
      if ( started >= 0 )
      {
LABEL_22:
        v17 = GetProcAddress(this[53], "VmbusPipeClientRegisterChannelNotification");
        this[55] = (HMODULE)v17;
        if ( v17 )
          goto LABEL_28;
        v18 = GetLastError();
        started = v18;
        if ( v18 > 0 )
          started = (unsigned __int16)v18 | 0x80070000;
        if ( started >= 0 )
        {
LABEL_28:
          v19 = GetProcAddress(this[53], "VmbusPipeClientUnregisterChannelNotification");
          this[56] = (HMODULE)v19;
          if ( v19 )
            goto LABEL_34;
          v20 = GetLastError();
          started = v20;
          if ( v20 > 0 )
            started = (unsigned __int16)v20 | 0x80070000;
          if ( started >= 0 )
          {
LABEL_34:
            v21 = GetProcAddress(this[53], "VmbusPipeClientReadyForChannelNotification");
            this[57] = (HMODULE)v21;
            if ( v21 )
              goto LABEL_40;
            v23 = GetLastError();
            started = v23;
            if ( v23 > 0 )
              started = (unsigned __int16)v23 | 0x80070000;
            if ( started >= 0 )
            {
LABEL_40:
              started = CUMRDPListenerVMBus::StartControlChannel((CUMRDPListenerVMBus *)(this - 1), v22, v7, v8);
            }
            else if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              v36 = 350;
              v33 = "Failed to get proc address for VmbusPipeClientReadyForChannelNotification";
              v10 = byte_18019CAA5;
              v32 = "StartListen";
              v31 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
              v30 = "Error HResult failed";
              v29 = &v33;
              v28 = &v32;
              v27 = &v31;
              v11 = &v30;
              goto LABEL_6;
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v36 = 341;
            v33 = "Failed to get proc address for VmbusPipeClientUnregisterChannelNotification";
            v10 = byte_18019CAF9;
            v32 = "StartListen";
            v31 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
            v30 = "Error HResult failed";
            v29 = &v33;
            v28 = &v32;
            v27 = &v31;
            v11 = &v30;
            goto LABEL_6;
          }
        }
        else if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v36 = 332;
          v33 = "Failed to get proc address for VmbusPipeClientRegisterChannelNotification";
          v10 = byte_18019CB4D;
          v32 = "StartListen";
          v31 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
          v30 = "Error HResult failed";
          v29 = &v33;
          v28 = &v32;
          v27 = &v31;
          v11 = &v30;
          goto LABEL_6;
        }
      }
      else if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v36 = 324;
        v33 = "Failed to get proc address for VmbusPipeClientOpenChannel";
        v10 = byte_18019CBA1;
        v32 = "StartListen";
        v31 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
        v30 = "Error HResult failed";
        v29 = &v33;
        v28 = &v32;
        v27 = &v31;
        v11 = &v30;
        goto LABEL_6;
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v36 = 316;
      v33 = "Failed to load vmbus pipe library.";
      v10 = byte_18019CBF5;
      v32 = "StartListen";
      v31 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
      v30 = "Error HResult failed";
      v29 = &v33;
      v28 = &v32;
      v27 = &v31;
      v11 = &v30;
      goto LABEL_6;
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v36 = 307;
    v33 = "Failed to QI for IRDPENCPlatformContext";
    v10 = byte_18019CC49;
    v32 = "StartListen";
    v31 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
    v30 = "Error HResult failed";
    v29 = &v33;
    v28 = &v32;
    v27 = &v31;
    v11 = &v30;
LABEL_6:
    v37 = started;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v9,
      (_DWORD)v10,
      v7,
      v8,
      (__int64)v11,
      (__int64)&v37,
      (__int64)v27,
      (__int64)&v36,
      (__int64)v28,
      (__int64)v29);
  }
LABEL_41:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v34);
  if ( started < 0 )
    (*((void (__fastcall **)(HMODULE *))*this + 5))(this);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v38, v24, v25);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180065ea0  push    rbp
0x180065ea2  push    rbx
0x180065ea3  push    rsi
0x180065ea4  push    rdi
0x180065ea5  push    r14
0x180065ea7  lea     rbp, [rsp-37h]
0x180065eac  sub     rsp, 90h
0x180065eb3  xor     eax, eax
0x180065eb5  mov     [rbp+57h+arg_18], 0
0x180065ebd  mov     rdi, rcx
0x180065ec0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180065ec4  add     rcx, 58h ; 'X'
0x180065ec8  xorps   xmm0, xmm0
0x180065ecb  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180065ecf  mov     rbx, rdx
0x180065ed2  mov     [rbp+57h+var_40], rcx
0x180065ed6  cmp     [rcx+8], eax
0x180065ed9  jz      short loc_180065EE4
0x180065edb  mov     rcx, [rcx]
0x180065ede  call    cs:__imp_PAL_System_CritSecEnter
0x180065ee4  mov     rdx, rbx; struct IWRdsProtocolListenerCallback *
0x180065ee7  mov     rcx, rdi; this
0x180065eea  call    ?StartListen@CUMRDPListenerBase@@UEAAJPEAUIWRdsProtocolListenerCallback@@@Z; CUMRDPListenerBase::StartListen(IWRdsProtocolListenerCallback *)
0x180065eef  mov     ebx, eax
0x180065ef1  test    eax, eax
0x180065ef3  jns     loc_180065F85
0x180065ef9  mov     ecx, cs:dword_1801B76C8
0x180065eff  cmp     ecx, 2
0x180065f02  jbe     loc_180066406
0x180065f08  lea     rax, aFailedToStartL_0; "Failed to start listener."
0x180065f0f  mov     [rbp+57h+arg_0], 12Ch
0x180065f16  mov     [rbp+57h+var_60], rax
0x180065f1a  lea     rdx, byte_18019CC9D
0x180065f21  lea     rax, aStartlisten; "StartListen"
0x180065f28  mov     [rbp+57h+var_58], rax
0x180065f2c  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180065f33  mov     [rbp+57h+var_50], rax
0x180065f37  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180065f3e  mov     [rbp+57h+var_48], rax
0x180065f42  lea     rax, [rbp+57h+var_60]
0x180065f46  mov     [rsp+0B0h+var_68], rax
0x180065f4b  lea     rax, [rbp+57h+var_58]
0x180065f4f  mov     [rsp+0B0h+var_70], rax
0x180065f54  lea     rax, [rbp+57h+arg_0]
0x180065f58  mov     [rsp+0B0h+var_78], rax
0x180065f5d  lea     rax, [rbp+57h+var_50]
0x180065f61  mov     [rsp+0B0h+var_80], rax
0x180065f66  lea     rax, [rbp+57h+arg_10]
0x180065f6a  mov     [rsp+0B0h+var_88], rax
0x180065f6f  lea     rax, [rbp+57h+var_48]
0x180065f73  mov     [rbp+57h+arg_10], ebx
0x180065f76  mov     [rsp+0B0h+var_90], rax
0x180065f7b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180065f80  jmp     loc_180066406
0x180065f85  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180065f89  call    cs:__imp_VariantInit
0x180065f8f  mov     rcx, [rdi+68h]
0x180065f93  lea     r8, [rbp+57h+arg_18]
0x180065f97  mov     eax, 0Bh
0x180065f9c  lea     rdx, IID_IRDPENCPlatformContext
0x180065fa3  mov     word ptr [rbp+57h+pvarg], ax
0x180065fa7  or      eax, 0FFFFFFFFh
0x180065faa  mov     word ptr [rbp+57h+pvarg+8], ax
0x180065fae  mov     rax, [rcx]
0x180065fb1  mov     rax, [rax]
0x180065fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fb9  mov     ebx, eax
0x180065fbb  test    eax, eax
0x180065fbd  jns     short loc_18006603E
0x180065fbf  mov     eax, cs:dword_1801B76C8
0x180065fc5  cmp     eax, 2
0x180065fc8  jbe     loc_180066406
0x180065fce  lea     rax, aFailedToQiForI; "Failed to QI for IRDPENCPlatformContext"
0x180065fd5  mov     [rbp+57h+arg_0], 133h
0x180065fdc  mov     [rbp+57h+var_48], rax
0x180065fe0  lea     rdx, byte_18019CC49
0x180065fe7  lea     rax, aStartlisten; "StartListen"
0x180065fee  mov     [rbp+57h+var_50], rax
0x180065ff2  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180065ff9  mov     [rbp+57h+var_58], rax
0x180065ffd  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180066004  mov     [rbp+57h+var_60], rax
0x180066008  lea     rax, [rbp+57h+var_48]
0x18006600c  mov     [rsp+0B0h+var_68], rax
0x180066011  lea     rax, [rbp+57h+var_50]
0x180066015  mov     [rsp+0B0h+var_70], rax
0x18006601a  lea     rax, [rbp+57h+arg_0]
0x18006601e  mov     [rsp+0B0h+var_78], rax
0x180066023  lea     rax, [rbp+57h+var_58]
0x180066027  mov     [rsp+0B0h+var_80], rax
0x18006602c  lea     rax, [rbp+57h+arg_10]
0x180066030  mov     [rsp+0B0h+var_88], rax
0x180066035  lea     rax, [rbp+57h+var_60]
0x180066039  jmp     loc_180065F73
0x18006603e  mov     rcx, [rbp+57h+arg_18]
0x180066042  lea     r8, [rbp+57h+pvarg]
0x180066046  lea     rdx, aExternalsslenc; "ExternalSSLEncryption"
0x18006604d  mov     rax, [rcx]
0x180066050  mov     rax, [rax+38h]
0x180066054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066059  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006605d  call    cs:__imp_VariantClear
0x180066063  lea     rcx, aVmbuspipeDll; "vmbuspipe.dll"
0x18006606a  call    cs:__imp_LoadLibraryW
0x180066070  mov     [rdi+1A8h], rax
0x180066077  mov     r14d, 80070000h
0x18006607d  test    rax, rax
0x180066080  jnz     loc_18006611B
0x180066086  call    cs:__imp_GetLastError
0x18006608c  mov     ebx, eax
0x18006608e  test    eax, eax
0x180066090  jle     short loc_180066098
0x180066092  movzx   ebx, ax
0x180066095  or      ebx, r14d
0x180066098  test    ebx, ebx
0x18006609a  jns     short loc_18006611B
0x18006609c  mov     eax, cs:dword_1801B76C8
0x1800660a2  cmp     eax, 2
0x1800660a5  jbe     loc_180066406
0x1800660ab  lea     rax, aFailedToLoadVm; "Failed to load vmbus pipe library."
0x1800660b2  mov     [rbp+57h+arg_0], 13Ch
0x1800660b9  mov     [rbp+57h+var_48], rax
0x1800660bd  lea     rdx, byte_18019CBF5
0x1800660c4  lea     rax, aStartlisten; "StartListen"
0x1800660cb  mov     [rbp+57h+var_50], rax
0x1800660cf  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800660d6  mov     [rbp+57h+var_58], rax
0x1800660da  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800660e1  mov     [rbp+57h+var_60], rax
0x1800660e5  lea     rax, [rbp+57h+var_48]
0x1800660e9  mov     [rsp+0B0h+var_68], rax
0x1800660ee  lea     rax, [rbp+57h+var_50]
0x1800660f2  mov     [rsp+0B0h+var_70], rax
0x1800660f7  lea     rax, [rbp+57h+arg_0]
0x1800660fb  mov     [rsp+0B0h+var_78], rax
0x180066100  lea     rax, [rbp+57h+var_58]
0x180066104  mov     [rsp+0B0h+var_80], rax
0x180066109  lea     rax, [rbp+57h+arg_10]
0x18006610d  mov     [rsp+0B0h+var_88], rax
0x180066112  lea     rax, [rbp+57h+var_60]
0x180066116  jmp     loc_180065F73
0x18006611b  mov     rcx, [rdi+1A8h]; hModule
0x180066122  lea     rdx, aVmbuspipeclien_2; "VmbusPipeClientOpenChannel"
0x180066129  call    cs:__imp_GetProcAddress
0x18006612f  mov     [rdi+1B0h], rax
0x180066136  test    rax, rax
0x180066139  jnz     loc_1800661D4
0x18006613f  call    cs:__imp_GetLastError
0x180066145  mov     ebx, eax
0x180066147  test    eax, eax
0x180066149  jle     short loc_180066151
0x18006614b  movzx   ebx, ax
0x18006614e  or      ebx, r14d
0x180066151  test    ebx, ebx
0x180066153  jns     short loc_1800661D4
0x180066155  mov     eax, cs:dword_1801B76C8
0x18006615b  cmp     eax, 2
0x18006615e  jbe     loc_180066406
0x180066164  lea     rax, aFailedToGetPro_7; "Failed to get proc address for VmbusPip"...
0x18006616b  mov     [rbp+57h+arg_0], 144h
0x180066172  mov     [rbp+57h+var_48], rax
0x180066176  lea     rdx, byte_18019CBA1
0x18006617d  lea     rax, aStartlisten; "StartListen"
0x180066184  mov     [rbp+57h+var_50], rax
0x180066188  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18006618f  mov     [rbp+57h+var_58], rax
0x180066193  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18006619a  mov     [rbp+57h+var_60], rax
0x18006619e  lea     rax, [rbp+57h+var_48]
0x1800661a2  mov     [rsp+0B0h+var_68], rax
0x1800661a7  lea     rax, [rbp+57h+var_50]
0x1800661ab  mov     [rsp+0B0h+var_70], rax
0x1800661b0  lea     rax, [rbp+57h+arg_0]
0x1800661b4  mov     [rsp+0B0h+var_78], rax
0x1800661b9  lea     rax, [rbp+57h+var_58]
0x1800661bd  mov     [rsp+0B0h+var_80], rax
0x1800661c2  lea     rax, [rbp+57h+arg_10]
0x1800661c6  mov     [rsp+0B0h+var_88], rax
0x1800661cb  lea     rax, [rbp+57h+var_60]
0x1800661cf  jmp     loc_180065F73
0x1800661d4  mov     rcx, [rdi+1A8h]; hModule
0x1800661db  lea     rdx, aVmbuspipeclien; "VmbusPipeClientRegisterChannelNotificat"...
0x1800661e2  call    cs:__imp_GetProcAddress
0x1800661e8  mov     [rdi+1B8h], rax
0x1800661ef  test    rax, rax
0x1800661f2  jnz     loc_18006628D
0x1800661f8  call    cs:__imp_GetLastError
0x1800661fe  mov     ebx, eax
0x180066200  test    eax, eax
0x180066202  jle     short loc_18006620A
0x180066204  movzx   ebx, ax
0x180066207  or      ebx, r14d
0x18006620a  test    ebx, ebx
0x18006620c  jns     short loc_18006628D
0x18006620e  mov     eax, cs:dword_1801B76C8
0x180066214  cmp     eax, 2
0x180066217  jbe     loc_180066406
0x18006621d  lea     rax, aFailedToGetPro_4; "Failed to get proc address for VmbusPip"...
0x180066224  mov     [rbp+57h+arg_0], 14Ch
0x18006622b  mov     [rbp+57h+var_48], rax
0x18006622f  lea     rdx, byte_18019CB4D
0x180066236  lea     rax, aStartlisten; "StartListen"
0x18006623d  mov     [rbp+57h+var_50], rax
0x180066241  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180066248  mov     [rbp+57h+var_58], rax
0x18006624c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180066253  mov     [rbp+57h+var_60], rax
0x180066257  lea     rax, [rbp+57h+var_48]
0x18006625b  mov     [rsp+0B0h+var_68], rax
0x180066260  lea     rax, [rbp+57h+var_50]
0x180066264  mov     [rsp+0B0h+var_70], rax
0x180066269  lea     rax, [rbp+57h+arg_0]
0x18006626d  mov     [rsp+0B0h+var_78], rax
0x180066272  lea     rax, [rbp+57h+var_58]
0x180066276  mov     [rsp+0B0h+var_80], rax
0x18006627b  lea     rax, [rbp+57h+arg_10]
0x18006627f  mov     [rsp+0B0h+var_88], rax
0x180066284  lea     rax, [rbp+57h+var_60]
0x180066288  jmp     loc_180065F73
0x18006628d  mov     rcx, [rdi+1A8h]; hModule
0x180066294  lea     rdx, aVmbuspipeclien_0; "VmbusPipeClientUnregisterChannelNotific"...
0x18006629b  call    cs:__imp_GetProcAddress
0x1800662a1  mov     [rdi+1C0h], rax
0x1800662a8  test    rax, rax
0x1800662ab  jnz     loc_180066346
0x1800662b1  call    cs:__imp_GetLastError
0x1800662b7  mov     ebx, eax
0x1800662b9  test    eax, eax
0x1800662bb  jle     short loc_1800662C3
0x1800662bd  movzx   ebx, ax
0x1800662c0  or      ebx, r14d
0x1800662c3  test    ebx, ebx
0x1800662c5  jns     short loc_180066346
0x1800662c7  mov     eax, cs:dword_1801B76C8
0x1800662cd  cmp     eax, 2
0x1800662d0  jbe     loc_180066406
0x1800662d6  lea     rax, aFailedToGetPro_3; "Failed to get proc address for VmbusPip"...
0x1800662dd  mov     [rbp+57h+arg_0], 155h
0x1800662e4  mov     [rbp+57h+var_48], rax
0x1800662e8  lea     rdx, byte_18019CAF9
0x1800662ef  lea     rax, aStartlisten; "StartListen"
0x1800662f6  mov     [rbp+57h+var_50], rax
0x1800662fa  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180066301  mov     [rbp+57h+var_58], rax
0x180066305  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18006630c  mov     [rbp+57h+var_60], rax
0x180066310  lea     rax, [rbp+57h+var_48]
0x180066314  mov     [rsp+0B0h+var_68], rax
0x180066319  lea     rax, [rbp+57h+var_50]
0x18006631d  mov     [rsp+0B0h+var_70], rax
0x180066322  lea     rax, [rbp+57h+arg_0]
0x180066326  mov     [rsp+0B0h+var_78], rax
0x18006632b  lea     rax, [rbp+57h+var_58]
0x18006632f  mov     [rsp+0B0h+var_80], rax
0x180066334  lea     rax, [rbp+57h+arg_10]
0x180066338  mov     [rsp+0B0h+var_88], rax
0x18006633d  lea     rax, [rbp+57h+var_60]
0x180066341  jmp     loc_180065F73
0x180066346  mov     rcx, [rdi+1A8h]; hModule
0x18006634d  lea     rdx, aVmbuspipeclien_1; "VmbusPipeClientReadyForChannelNotificat"...
0x180066354  call    cs:__imp_GetProcAddress
0x18006635a  mov     [rdi+1C8h], rax
0x180066361  test    rax, rax
0x180066364  jnz     loc_1800663FB
0x18006636a  call    cs:__imp_GetLastError
0x180066370  mov     ebx, eax
0x180066372  test    eax, eax
0x180066374  jle     short loc_18006637C
0x180066376  movzx   ebx, ax
0x180066379  or      ebx, r14d
0x18006637c  test    ebx, ebx
0x18006637e  jns     short loc_1800663FB
0x180066380  mov     eax, cs:dword_1801B76C8
0x180066386  cmp     eax, 2
0x180066389  jbe     short loc_180066406
0x18006638b  lea     rax, aFailedToGetPro; "Failed to get proc address for VmbusPip"...
0x180066392  mov     [rbp+57h+arg_0], 15Eh
0x180066399  mov     [rbp+57h+var_48], rax
0x18006639d  lea     rdx, byte_18019CAA5
0x1800663a4  lea     rax, aStartlisten; "StartListen"
0x1800663ab  mov     [rbp+57h+var_50], rax
0x1800663af  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800663b6  mov     [rbp+57h+var_58], rax
0x1800663ba  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800663c1  mov     [rbp+57h+var_60], rax
0x1800663c5  lea     rax, [rbp+57h+var_48]
0x1800663c9  mov     [rsp+0B0h+var_68], rax
0x1800663ce  lea     rax, [rbp+57h+var_50]
0x1800663d2  mov     [rsp+0B0h+var_70], rax
0x1800663d7  lea     rax, [rbp+57h+arg_0]
0x1800663db  mov     [rsp+0B0h+var_78], rax
0x1800663e0  lea     rax, [rbp+57h+var_58]
0x1800663e4  mov     [rsp+0B0h+var_80], rax
0x1800663e9  lea     rax, [rbp+57h+arg_10]
0x1800663ed  mov     [rsp+0B0h+var_88], rax
0x1800663f2  lea     rax, [rbp+57h+var_60]
0x1800663f6  jmp     loc_180065F73
0x1800663fb  lea     rcx, [rdi-8]; this
0x1800663ff  call    ?StartControlChannel@CUMRDPListenerVMBus@@AEAAJXZ; CUMRDPListenerVMBus::StartControlChannel(void)
0x180066404  mov     ebx, eax
  ... truncated ...
```
