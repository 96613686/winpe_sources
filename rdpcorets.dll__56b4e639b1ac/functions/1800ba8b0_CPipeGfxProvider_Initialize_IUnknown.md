# CPipeGfxProvider::Initialize(IUnknown *)

- ea: `0x1800ba8b0`
- end: `0x1800badbd`
- name: `?Initialize@CPipeGfxProvider@@UEAAJPEAUIUnknown@@@Z`
- size: `1293`
- prototype: `__int64 __fastcall(CPipeGfxProvider *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800bd8ac`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x18000bef4`
- `0x18000ee00`
- `0x1800ba8b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ba9b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ba9b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba9cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba9cd`
- `RDPSERVERBASE!?GetGfxPipeSettingBOOL@@YAJPEAGHPEAH@Z` at `0x1800bad6a`
- `RDPSERVERBASE!?GetGfxPipeSettingBOOL@@YAJPEAGHPEAH@Z` at `0x1800bad6a`
- `RDPSERVERBASE!?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z` at `0x1800baa6b`
- `RDPSERVERBASE!?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z` at `0x1800baac9`
- `RDPSERVERBASE!?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z` at `0x1800bab27`
- `RDPSERVERBASE!?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z` at `0x1800bab82`
- `RDPSERVERBASE!?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z` at `0x1800baa6b`
- `RDPSERVERBASE!?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z` at `0x1800baac9`
- `RDPSERVERBASE!?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z` at `0x1800bab27`
- `RDPSERVERBASE!?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z` at `0x1800bab82`

## string_xrefs

- `0x1800baa18`: `Failed to create the CPI event.`

## pseudocode

```c
__int64 __fastcall CPipeGfxProvider::Initialize(CPipeGfxProvider *this, struct IUnknown *a2)
{
  _QWORD *v4; // rsi
  int v5; // eax
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v42; // [rsp+50h] [rbp+7h] BYREF
  int v43; // [rsp+54h] [rbp+Bh] BYREF
  unsigned int v44; // [rsp+58h] [rbp+Fh] BYREF
  const char *v45; // [rsp+60h] [rbp+17h] BYREF
  const char *v46; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v47; // [rsp+70h] [rbp+27h] BYREF
  _QWORD v48[5]; // [rsp+78h] [rbp+2Fh] BYREF
  unsigned int v49; // [rsp+B0h] [rbp+67h] BYREF
  unsigned int v50; // [rsp+B8h] [rbp+6Fh] BYREF
  unsigned int v51; // [rsp+C0h] [rbp+77h] BYREF
  unsigned int v52; // [rsp+C8h] [rbp+7Fh] BYREF

  v50 = 0;
  v51 = 0;
  v52 = 0;
  v49 = 1;
  v42 = 0;
  CTSCriticalSection::Initialize((CPipeGfxProvider *)((char *)this + 9696));
  v4 = (_QWORD *)((char *)this + 9728);
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IRDPENCPlatformContext,
         (char *)this + 9728);
  v8 = v5;
  if ( v5 >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 1408) = EventW;
    if ( EventW )
    {
      if ( (int)GetGfxPipeSettingUINT(L"DownsampleMinDesktopScaling", *((_DWORD *)this + 3843), &v50) >= 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v44 = v50;
          v48[0] = "Using MinDownSamplDesktopScale";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v14,
            (unsigned int)byte_1801A6363,
            v15,
            v16,
            (__int64)v48,
            (__int64)&v44);
        }
        *((_DWORD *)this + 3843) = v50;
      }
      if ( (int)GetGfxPipeSettingUINT(L"DownsampleMaxDesktopScaling", *((_DWORD *)this + 3844), &v51) >= 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v44 = v51;
          v48[0] = "Using MaxDownSamplDesktopScale";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v17,
            (unsigned int)&dword_1801A63A4,
            v18,
            v19,
            (__int64)v48,
            (__int64)&v44);
        }
        *((_DWORD *)this + 3844) = v51;
      }
      if ( (int)GetGfxPipeSettingUINT(L"DownsampleInterpolationMode", *((_DWORD *)this + 3846), &v52) >= 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v44 = v52;
          v48[0] = "Using DownsampleInterpolationMode (0=NN,1=Lin,2=Cubic,3=Fant)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&word_1801A62F6,
            v21,
            v22,
            (__int64)v48,
            (__int64)&v44);
        }
        *((_DWORD *)this + 3846) = v52;
      }
      if ( (int)GetGfxPipeSettingUINT(L"DownsampleHardwareMode", v49, &v49) >= 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v44 = v49;
          v48[0] = "Using DownsampleHardwareMode (0=Off, 1=On)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)&byte_1801A632F,
            v24,
            v25,
            (__int64)v48,
            (__int64)&v44);
        }
        *((_DWORD *)this + 3842) = v49 != 0;
      }
      if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(*(_QWORD *)*v4 + 40LL))(
             *v4,
             L"EnableScreenCaptureProtection",
             &v42) >= 0 )
      {
        *((_DWORD *)this + 3850) = v42 != 0;
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v44 = *((_DWORD *)this + 3850);
          v48[0] = "ScreenCaptureProtectionMode (0=Off, 1=On)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)byte_1801A62B3,
            v27,
            v28,
            (__int64)v48,
            (__int64)&v44);
        }
      }
      if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, char *))(*(_QWORD *)*v4 + 32LL))(
             *v4,
             L"EnableWatermarking",
             (char *)this + 15404) >= 0
        && (unsigned int)dword_1801B76C8 > 4 )
      {
        v44 = *((_DWORD *)this + 3851);
        v48[0] = "WatermarkingMode (0=Off, 1=On)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v29,
          (unsigned int)&dword_1801A624C,
          v30,
          v31,
          (__int64)v48,
          (__int64)&v44);
      }
      if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, char *))(*(_QWORD *)*v4 + 32LL))(
             *v4,
             L"EnableWddmIdd",
             (char *)this + 15388) >= 0
        && (unsigned int)dword_1801B76C8 > 4 )
      {
        v44 = *((_DWORD *)this + 3847);
        v48[0] = "WDDM IDD mode (0=Off, 1=On)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v32,
          (unsigned int)&dword_1801A6284,
          v33,
          v34,
          (__int64)v48,
          (__int64)&v44);
      }
      if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, char *))(*(_QWORD *)*v4 + 32LL))(
             *v4,
             L"WVD::UseXVPColorConversion",
             (char *)this + 15408) >= 0
        && (unsigned int)dword_1801B76C8 > 4 )
      {
        v44 = *((_DWORD *)this + 3852);
        v48[0] = "XVP Color Conversion (0=Off, 1=On)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v35,
          (unsigned int)word_1801A61F2,
          v36,
          v37,
          (__int64)v48,
          (__int64)&v44);
      }
      GetGfxPipeSettingBOOL(L"RemoteAppDownsampling", 1, (int *)this + 3841);
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v44 = *((_DWORD *)this + 3841);
        v48[0] = "Using RemoteAppDownsampling (0=Off, 1=On)";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v38,
          (unsigned int)byte_1801A621D,
          v39,
          v40,
          (__int64)v48,
          (__int64)&v44);
      }
      v8 = 0;
      *((_DWORD *)this + 7) |= 2u;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v44 = 152;
        v48[0] = "Initialize";
        v43 = v8;
        v47 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
        v46 = "Failed to create the CPI event.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)byte_1801A63E5,
          v12,
          v13,
          (__int64)&v46,
          (__int64)&v43,
          (__int64)&v47,
          (__int64)&v44,
          (__int64)v48);
      }
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v43 = 147;
    v45 = "Failed to QI for platform context";
    v44 = v5;
    v46 = "Initialize";
    v47 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
    v48[0] = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)byte_1801A6455,
      v6,
      v7,
      (__int64)v48,
      (__int64)&v44,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)&v46,
      (__int64)&v45);
  }
  return v8;
}

```

## disassembly

```asm
0x1800ba8b0  push    rbp
0x1800ba8b2  push    rbx
0x1800ba8b3  push    rsi
0x1800ba8b4  push    rdi
0x1800ba8b5  lea     rbp, [rsp-3Fh]
0x1800ba8ba  sub     rsp, 88h
0x1800ba8c1  mov     rdi, rcx
0x1800ba8c4  mov     [rbp+57h+arg_8], 0
0x1800ba8cb  add     rcx, 25E0h; this
0x1800ba8d2  mov     [rbp+57h+arg_10], 0
0x1800ba8d9  mov     rbx, rdx
0x1800ba8dc  mov     [rbp+57h+arg_18], 0
0x1800ba8e3  mov     [rbp+57h+arg_0], 1
0x1800ba8ea  mov     [rbp+57h+var_50], 0
0x1800ba8f1  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800ba8f6  mov     rax, [rbx]
0x1800ba8f9  lea     rsi, [rdi+2600h]
0x1800ba900  mov     r8, rsi
0x1800ba903  lea     rdx, IID_IRDPENCPlatformContext
0x1800ba90a  mov     rcx, rbx
0x1800ba90d  mov     rax, [rax]
0x1800ba910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba915  mov     ebx, eax
0x1800ba917  test    eax, eax
0x1800ba919  jns     loc_1800BA9AB
0x1800ba91f  mov     ecx, cs:dword_1801B76C8
0x1800ba925  cmp     ecx, 2
0x1800ba928  jbe     loc_1800BADAF
0x1800ba92e  lea     rax, aFailedToQiForP_0; "Failed to QI for platform context"
0x1800ba935  mov     [rbp+57h+var_4C], 93h
0x1800ba93c  mov     [rbp+57h+var_40], rax
0x1800ba940  lea     rdx, byte_1801A6455
0x1800ba947  lea     rax, aInitialize; "Initialize"
0x1800ba94e  mov     [rbp+57h+var_48], ebx
0x1800ba951  mov     [rbp+57h+var_38], rax
0x1800ba955  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800ba95c  mov     [rbp+57h+var_30], rax
0x1800ba960  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800ba967  mov     [rbp+57h+var_28], rax
0x1800ba96b  lea     rax, [rbp+57h+var_40]
0x1800ba96f  mov     [rsp+0A0h+var_58], rax
0x1800ba974  lea     rax, [rbp+57h+var_38]
0x1800ba978  mov     [rsp+0A0h+var_60], rax
0x1800ba97d  lea     rax, [rbp+57h+var_4C]
0x1800ba981  mov     [rsp+0A0h+var_68], rax
0x1800ba986  lea     rax, [rbp+57h+var_30]
0x1800ba98a  mov     [rsp+0A0h+var_70], rax
0x1800ba98f  lea     rax, [rbp+57h+var_48]
0x1800ba993  mov     [rsp+0A0h+var_78], rax
0x1800ba998  lea     rax, [rbp+57h+var_28]
0x1800ba99c  mov     [rsp+0A0h+var_80], rax
0x1800ba9a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800ba9a6  jmp     loc_1800BADAF
0x1800ba9ab  xor     r9d, r9d; lpName
0x1800ba9ae  xor     r8d, r8d; bInitialState
0x1800ba9b1  xor     ecx, ecx; lpEventAttributes
0x1800ba9b3  lea     edx, [r9+1]; bManualReset
0x1800ba9b7  call    cs:__imp_CreateEventW
0x1800ba9bd  mov     [rdi+2C00h], rax
0x1800ba9c4  test    rax, rax
0x1800ba9c7  jnz     loc_1800BAA5A
0x1800ba9cd  call    cs:__imp_GetLastError
0x1800ba9d3  mov     ebx, eax
0x1800ba9d5  test    eax, eax
0x1800ba9d7  jle     short loc_1800BA9E2
0x1800ba9d9  movzx   ebx, ax
0x1800ba9dc  or      ebx, 80070000h
0x1800ba9e2  mov     eax, cs:dword_1801B76C8
0x1800ba9e8  cmp     eax, 2
0x1800ba9eb  jbe     loc_1800BADAF
0x1800ba9f1  lea     rax, aInitialize; "Initialize"
0x1800ba9f8  mov     [rbp+57h+var_48], 98h
0x1800ba9ff  mov     [rbp+57h+var_28], rax
0x1800baa03  lea     rdx, byte_1801A63E5
0x1800baa0a  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800baa11  mov     [rbp+57h+var_4C], ebx
0x1800baa14  mov     [rbp+57h+var_30], rax
0x1800baa18  lea     rax, aFailedToCreate_48; "Failed to create the CPI event."
0x1800baa1f  mov     [rbp+57h+var_38], rax
0x1800baa23  lea     rax, [rbp+57h+var_28]
0x1800baa27  mov     [rsp+0A0h+var_60], rax
0x1800baa2c  lea     rax, [rbp+57h+var_48]
0x1800baa30  mov     [rsp+0A0h+var_68], rax
0x1800baa35  lea     rax, [rbp+57h+var_30]
0x1800baa39  mov     [rsp+0A0h+var_70], rax
0x1800baa3e  lea     rax, [rbp+57h+var_4C]
0x1800baa42  mov     [rsp+0A0h+var_78], rax
0x1800baa47  lea     rax, [rbp+57h+var_38]
0x1800baa4b  mov     [rsp+0A0h+var_80], rax
0x1800baa50  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800baa55  jmp     loc_1800BADAF
0x1800baa5a  mov     edx, [rdi+3C0Ch]
0x1800baa60  lea     r8, [rbp+57h+arg_8]
0x1800baa64  lea     rcx, aDownsamplemind; "DownsampleMinDesktopScaling"
0x1800baa6b  call    cs:__imp_?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z; GetGfxPipeSettingUINT(ushort *,uint,uint *)
0x1800baa71  test    eax, eax
0x1800baa73  js      short loc_1800BAAB8
0x1800baa75  mov     eax, cs:dword_1801B76C8
0x1800baa7b  cmp     eax, 4
0x1800baa7e  jbe     short loc_1800BAAAF
0x1800baa80  mov     eax, [rbp+57h+arg_8]
0x1800baa83  lea     rdx, byte_1801A6363
0x1800baa8a  mov     [rbp+57h+var_48], eax
0x1800baa8d  lea     rax, aUsingMindownsa; "Using MinDownSamplDesktopScale"
0x1800baa94  mov     [rbp+57h+var_28], rax
0x1800baa98  lea     rax, [rbp+57h+var_48]
0x1800baa9c  mov     [rsp+0A0h+var_78], rax
0x1800baaa1  lea     rax, [rbp+57h+var_28]
0x1800baaa5  mov     [rsp+0A0h+var_80], rax
0x1800baaaa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800baaaf  mov     eax, [rbp+57h+arg_8]
0x1800baab2  mov     [rdi+3C0Ch], eax
0x1800baab8  mov     edx, [rdi+3C10h]
0x1800baabe  lea     r8, [rbp+57h+arg_10]
0x1800baac2  lea     rcx, aDownsamplemaxd; "DownsampleMaxDesktopScaling"
0x1800baac9  call    cs:__imp_?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z; GetGfxPipeSettingUINT(ushort *,uint,uint *)
0x1800baacf  test    eax, eax
0x1800baad1  js      short loc_1800BAB16
0x1800baad3  mov     eax, cs:dword_1801B76C8
0x1800baad9  cmp     eax, 4
0x1800baadc  jbe     short loc_1800BAB0D
0x1800baade  mov     eax, [rbp+57h+arg_10]
0x1800baae1  lea     rdx, dword_1801A63A4
0x1800baae8  mov     [rbp+57h+var_48], eax
0x1800baaeb  lea     rax, aUsingMaxdownsa; "Using MaxDownSamplDesktopScale"
0x1800baaf2  mov     [rbp+57h+var_28], rax
0x1800baaf6  lea     rax, [rbp+57h+var_48]
0x1800baafa  mov     [rsp+0A0h+var_78], rax
0x1800baaff  lea     rax, [rbp+57h+var_28]
0x1800bab03  mov     [rsp+0A0h+var_80], rax
0x1800bab08  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800bab0d  mov     eax, [rbp+57h+arg_10]
0x1800bab10  mov     [rdi+3C10h], eax
0x1800bab16  mov     edx, [rdi+3C18h]
0x1800bab1c  lea     r8, [rbp+57h+arg_18]
0x1800bab20  lea     rcx, aDownsampleinte; "DownsampleInterpolationMode"
0x1800bab27  call    cs:__imp_?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z; GetGfxPipeSettingUINT(ushort *,uint,uint *)
0x1800bab2d  test    eax, eax
0x1800bab2f  js      short loc_1800BAB74
0x1800bab31  mov     eax, cs:dword_1801B76C8
0x1800bab37  cmp     eax, 4
0x1800bab3a  jbe     short loc_1800BAB6B
0x1800bab3c  mov     eax, [rbp+57h+arg_18]
0x1800bab3f  lea     rdx, word_1801A62F6
0x1800bab46  mov     [rbp+57h+var_48], eax
0x1800bab49  lea     rax, aUsingDownsampl_0; "Using DownsampleInterpolationMode (0=NN"...
0x1800bab50  mov     [rbp+57h+var_28], rax
0x1800bab54  lea     rax, [rbp+57h+var_48]
0x1800bab58  mov     [rsp+0A0h+var_78], rax
0x1800bab5d  lea     rax, [rbp+57h+var_28]
0x1800bab61  mov     [rsp+0A0h+var_80], rax
0x1800bab66  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800bab6b  mov     eax, [rbp+57h+arg_18]
0x1800bab6e  mov     [rdi+3C18h], eax
0x1800bab74  mov     edx, [rbp+57h+arg_0]
0x1800bab77  lea     r8, [rbp+57h+arg_0]
0x1800bab7b  lea     rcx, aDownsamplehard; "DownsampleHardwareMode"
0x1800bab82  call    cs:__imp_?GetGfxPipeSettingUINT@@YAJPEAGIPEAI@Z; GetGfxPipeSettingUINT(ushort *,uint,uint *)
0x1800bab88  test    eax, eax
0x1800bab8a  js      short loc_1800BABD4
0x1800bab8c  mov     eax, cs:dword_1801B76C8
0x1800bab92  cmp     eax, 4
0x1800bab95  jbe     short loc_1800BABC6
0x1800bab97  mov     eax, [rbp+57h+arg_0]
0x1800bab9a  lea     rdx, byte_1801A632F
0x1800baba1  mov     [rbp+57h+var_48], eax
0x1800baba4  lea     rax, aUsingDownsampl; "Using DownsampleHardwareMode (0=Off, 1="...
0x1800babab  mov     [rbp+57h+var_28], rax
0x1800babaf  lea     rax, [rbp+57h+var_48]
0x1800babb3  mov     [rsp+0A0h+var_78], rax
0x1800babb8  lea     rax, [rbp+57h+var_28]
0x1800babbc  mov     [rsp+0A0h+var_80], rax
0x1800babc1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800babc6  xor     eax, eax
0x1800babc8  cmp     [rbp+57h+arg_0], eax
0x1800babcb  setnz   al
0x1800babce  mov     [rdi+3C08h], eax
0x1800babd4  mov     rcx, [rsi]
0x1800babd7  lea     r8, [rbp+57h+var_50]
0x1800babdb  lea     rdx, aEnablescreenca; "EnableScreenCaptureProtection"
0x1800babe2  mov     rax, [rcx]
0x1800babe5  mov     rax, [rax+28h]
0x1800babe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800babee  test    eax, eax
0x1800babf0  js      short loc_1800BAC3D
0x1800babf2  xor     eax, eax
0x1800babf4  cmp     [rbp+57h+var_50], eax
0x1800babf7  setnbe  al
0x1800babfa  mov     [rdi+3C28h], eax
0x1800bac00  mov     eax, cs:dword_1801B76C8
0x1800bac06  cmp     eax, 4
0x1800bac09  jbe     short loc_1800BAC3D
0x1800bac0b  mov     eax, [rdi+3C28h]
0x1800bac11  lea     rdx, byte_1801A62B3
0x1800bac18  mov     [rbp+57h+var_48], eax
0x1800bac1b  lea     rax, aScreencapturep; "ScreenCaptureProtectionMode (0=Off, 1=O"...
0x1800bac22  mov     [rbp+57h+var_28], rax
0x1800bac26  lea     rax, [rbp+57h+var_48]
0x1800bac2a  mov     [rsp+0A0h+var_78], rax
0x1800bac2f  lea     rax, [rbp+57h+var_28]
0x1800bac33  mov     [rsp+0A0h+var_80], rax
0x1800bac38  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800bac3d  mov     rcx, [rsi]
0x1800bac40  lea     rbx, [rdi+3C2Ch]
0x1800bac47  mov     r8, rbx
0x1800bac4a  lea     rdx, aEnablewatermar; "EnableWatermarking"
0x1800bac51  mov     rax, [rcx]
0x1800bac54  mov     rax, [rax+20h]
0x1800bac58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac5d  test    eax, eax
0x1800bac5f  js      short loc_1800BAC9A
0x1800bac61  mov     eax, cs:dword_1801B76C8
0x1800bac67  cmp     eax, 4
0x1800bac6a  jbe     short loc_1800BAC9A
0x1800bac6c  mov     eax, [rbx]
0x1800bac6e  lea     rdx, dword_1801A624C
0x1800bac75  mov     [rbp+57h+var_48], eax
0x1800bac78  lea     rax, aWatermarkingmo; "WatermarkingMode (0=Off, 1=On)"
0x1800bac7f  mov     [rbp+57h+var_28], rax
0x1800bac83  lea     rax, [rbp+57h+var_48]
0x1800bac87  mov     [rsp+0A0h+var_78], rax
0x1800bac8c  lea     rax, [rbp+57h+var_28]
0x1800bac90  mov     [rsp+0A0h+var_80], rax
0x1800bac95  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800bac9a  mov     rcx, [rsi]
0x1800bac9d  lea     rbx, [rdi+3C1Ch]
0x1800baca4  mov     r8, rbx
0x1800baca7  lea     rdx, aEnablewddmidd; "EnableWddmIdd"
0x1800bacae  mov     rax, [rcx]
0x1800bacb1  mov     rax, [rax+20h]
0x1800bacb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bacba  test    eax, eax
0x1800bacbc  js      short loc_1800BACF7
0x1800bacbe  mov     eax, cs:dword_1801B76C8
0x1800bacc4  cmp     eax, 4
0x1800bacc7  jbe     short loc_1800BACF7
0x1800bacc9  mov     eax, [rbx]
0x1800baccb  lea     rdx, dword_1801A6284
0x1800bacd2  mov     [rbp+57h+var_48], eax
0x1800bacd5  lea     rax, aWddmIddMode0Of; "WDDM IDD mode (0=Off, 1=On)"
0x1800bacdc  mov     [rbp+57h+var_28], rax
0x1800bace0  lea     rax, [rbp+57h+var_48]
0x1800bace4  mov     [rsp+0A0h+var_78], rax
0x1800bace9  lea     rax, [rbp+57h+var_28]
0x1800baced  mov     [rsp+0A0h+var_80], rax
0x1800bacf2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800bacf7  mov     rcx, [rsi]
0x1800bacfa  lea     rbx, [rdi+3C30h]
0x1800bad01  mov     r8, rbx
0x1800bad04  lea     rdx, aWvdUsexvpcolor; "WVD::UseXVPColorConversion"
0x1800bad0b  mov     rax, [rcx]
0x1800bad0e  mov     rax, [rax+20h]
0x1800bad12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad17  test    eax, eax
0x1800bad19  js      short loc_1800BAD54
0x1800bad1b  mov     eax, cs:dword_1801B76C8
0x1800bad21  cmp     eax, 4
0x1800bad24  jbe     short loc_1800BAD54
0x1800bad26  mov     eax, [rbx]
0x1800bad28  lea     rdx, word_1801A61F2
0x1800bad2f  mov     [rbp+57h+var_48], eax
0x1800bad32  lea     rax, aXvpColorConver; "XVP Color Conversion (0=Off, 1=On)"
0x1800bad39  mov     [rbp+57h+var_28], rax
0x1800bad3d  lea     rax, [rbp+57h+var_48]
0x1800bad41  mov     [rsp+0A0h+var_78], rax
0x1800bad46  lea     rax, [rbp+57h+var_28]
0x1800bad4a  mov     [rsp+0A0h+var_80], rax
0x1800bad4f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800bad54  lea     rbx, [rdi+3C04h]
0x1800bad5b  mov     edx, 1
0x1800bad60  mov     r8, rbx
0x1800bad63  lea     rcx, aRemoteappdowns; "RemoteAppDownsampling"
0x1800bad6a  call    cs:__imp_?GetGfxPipeSettingBOOL@@YAJPEAGHPEAH@Z; GetGfxPipeSettingBOOL(ushort *,int,int *)
0x1800bad70  mov     eax, cs:dword_1801B76C8
0x1800bad76  cmp     eax, 4
0x1800bad79  jbe     short loc_1800BADA9
0x1800bad7b  mov     eax, [rbx]
0x1800bad7d  lea     rdx, byte_1801A621D
0x1800bad84  mov     [rbp+57h+var_48], eax
0x1800bad87  lea     rax, aUsingRemoteapp; "Using RemoteAppDownsampling (0=Off, 1=O"...
0x1800bad8e  mov     [rbp+57h+var_28], rax
0x1800bad92  lea     rax, [rbp+57h+var_48]
0x1800bad96  mov     [rsp+0A0h+var_78], rax
0x1800bad9b  lea     rax, [rbp+57h+var_28]
0x1800bad9f  mov     [rsp+0A0h+var_80], rax
0x1800bada4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800bada9  xor     ebx, ebx
0x1800badab  or      dword ptr [rdi+1Ch], 2
0x1800badaf  mov     eax, ebx
0x1800badb1  add     rsp, 88h
0x1800badb8  pop     rdi
0x1800badb9  pop     rsi
0x1800badba  pop     rbx
0x1800badbb  pop     rbp
0x1800badbc  retn
```
