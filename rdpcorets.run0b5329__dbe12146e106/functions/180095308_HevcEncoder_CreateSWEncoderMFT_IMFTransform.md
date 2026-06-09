# HevcEncoder::CreateSWEncoderMFT(IMFTransform * *)

- ea: `0x180095308`
- end: `0x180095794`
- name: `?CreateSWEncoderMFT@HevcEncoder@@AEAAJPEAPEAUIMFTransform@@@Z`
- size: `1164`
- prototype: `__int64 __fastcall(HevcEncoder *__hidden this, struct IMFTransform **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180097b9c`

## callees

- `0x1800015f0`
- `0x180009628`
- `0x18000ee00`
- `0x180010960`
- `0x18002e600`
- `0x180033da0`
- `0x180034850`
- `0x180095308`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009560e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009572d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095742`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009574c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009560e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009572d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095742`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009574c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800955ec`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800956b4`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800955ec`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800956b4`

## string_xrefs

- `0x18009540e`: `CreateSWEncoderMFT`
- `0x180095366`: `CoCreateInstance CLSID_CMSH265EncoderMFT failed but do not worry yet`
- `0x180095518`: `Microsoft.HEVCVideoExtension_8wekyb3d8bbwe`
- `0x1800956c7`: `Failed to retrieve MF MEDIA EXTENSION ACTIVATABLE_CLASS_ID/PACKAGE_FAMILY_NAME; Cannot create HEVC SW encoder`
- `0x180095662`: `Created MFT SW encoder from HEVC Video extensions`

## pseudocode

```c
__int64 __fastcall HevcEncoder::CreateSWEncoderMFT(HevcEncoder *this, struct IMFTransform **a2, int a3, int a4)
{
  __int64 v6; // rax
  __int64 (__fastcall *v7)(GUID *, __int64, _QWORD, _OWORD *, LPVOID *, unsigned int *); // rax
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  int v11; // ebx
  unsigned int v12; // edi
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // eax
  _QWORD **v23; // rax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int ActivityIdPrefix; // eax
  _QWORD *v28; // rcx
  unsigned int i; // edi
  __int64 v30; // rdx
  __int64 v32; // [rsp+28h] [rbp-81h]
  unsigned int v33; // [rsp+50h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-51h] BYREF
  int v35; // [rsp+60h] [rbp-49h] BYREF
  const char *v36; // [rsp+68h] [rbp-41h] BYREF
  GUID v37; // [rsp+70h] [rbp-39h] BYREF
  wchar_t *String1; // [rsp+80h] [rbp-29h] BYREF
  wchar_t *v39; // [rsp+88h] [rbp-21h] BYREF
  int v40; // [rsp+90h] [rbp-19h] BYREF
  const char *v41; // [rsp+98h] [rbp-11h] BYREF
  const char *v42; // [rsp+A0h] [rbp-9h] BYREF
  const char *v43; // [rsp+A8h] [rbp-1h] BYREF
  _OWORD v44[2]; // [rsp+B0h] [rbp+7h] BYREF

  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 42) = 0;
  String1 = 0;
  v39 = 0;
  pv = 0;
  v33 = 0;
  if ( (unsigned int)dword_1801B76C8 > 5 )
  {
    v36 = "CoCreateInstance CLSID_CMSH265EncoderMFT failed but do not worry yet";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)byte_1801A2769,
      a3,
      a4,
      (__int64)&v36);
  }
  v6 = *((_QWORD *)this + 11);
  v44[0] = MFMediaType_Video;
  v35 = 0;
  v44[1] = MFVideoFormat_HEVC;
  v7 = *(__int64 (__fastcall **)(GUID *, __int64, _QWORD, _OWORD *, LPVOID *, unsigned int *))(v6 + 120);
  v37 = MFT_CATEGORY_VIDEO_ENCODER;
  v8 = v7(&v37, 59, 0, v44, &pv, &v33);
  v11 = v8;
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v40 = 844;
      v42 = "m_spMFApi->_pfnMFTEnumEx failed";
      LODWORD(v36) = v8;
      v43 = "CreateSWEncoderMFT";
      v41 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\hevccodec\\hevcencoder.cpp";
      *(_QWORD *)&v37.Data1 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)&byte_1801A278F,
        v9,
        v10,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v43,
        (__int64)&v42);
    }
    goto LABEL_33;
  }
  v11 = -2147024463;
  v12 = 0;
  if ( !v33 )
    goto LABEL_27;
  while ( 1 )
  {
    if ( (*(int (__fastcall **)(_QWORD, __int64 *, wchar_t **, int *))(**((_QWORD **)pv + v12) + 104LL))(
           *((_QWORD *)pv + v12),
           MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID,
           &String1,
           &v35) >= 0
      && (*(int (__fastcall **)(_QWORD, __int64 *, wchar_t **, int *))(**((_QWORD **)pv + v12) + 104LL))(
           *((_QWORD *)pv + v12),
           MF_MEDIA_EXTENSION_PACKAGE_FAMILY_NAME,
           &v39,
           &v35) >= 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 5 )
      {
        *(_QWORD *)&v37.Data1 = "creating SW encoder from store";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v13,
          (unsigned int)byte_1801A271D,
          v14,
          v15,
          (__int64)&v37);
      }
      if ( !wcsicmp(String1, L"H265Encoder.CH265EncoderTransform")
        && !wcsicmp(v39, L"Microsoft.HEVCVideoExtension_8wekyb3d8bbwe") )
      {
        break;
      }
    }
    if ( ++v12 >= v33 )
      goto LABEL_27;
  }
  if ( (unsigned int)dword_1801B76C8 > 5 )
  {
    *(_QWORD *)&v37.Data1 = "trying to activate transform object";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v16,
      (unsigned int)byte_1801A2743,
      v17,
      v18,
      (__int64)&v37);
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct IMFTransform **))(**((_QWORD **)pv + v12) + 264LL))(
          *((_QWORD *)pv + v12),
          &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
          a2);
  if ( (unsigned int)dword_1801B76C8 > 5 )
  {
    LODWORD(v36) = v11;
    *(_QWORD *)&v37.Data1 = "Activate transform object succeeded ?";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_1801A26B3,
      v20,
      v21,
      (__int64)&v37,
      (__int64)&v36);
  }
  if ( v11 >= 0 )
  {
    CoTaskMemFree(*((LPVOID *)this + 25));
    v23 = (_QWORD **)pv;
    *((_QWORD *)this + 25) = 0;
    if ( (*(int (__fastcall **)(_QWORD *, const GUID *, _QWORD, _QWORD, _QWORD))(*v23[v12] + 96LL))(
           v23[v12],
           &MFT_FRIENDLY_NAME_Attribute,
           0,
           0,
           0) >= 0
      && (unsigned int)dword_1801B76C8 > 5 )
    {
      *(_QWORD *)&v37.Data1 = *((_QWORD *)this + 25);
      v41 = "Created MFT SW encoder from HEVC Video extensions";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v24,
        (unsigned int)byte_1801A26E1,
        v25,
        v26,
        (__int64)&v41,
        (__int64)&v37);
    }
LABEL_27:
    if ( !String1 || !v39 )
    {
      v11 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
        LODWORD(v32) = -2147467259;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)WPP_225ebdff2f7730fc004038fb7f46f5ea_Traceguids,
          ActivityIdPrefix,
          (__int64)"Failed to retrieve MF MEDIA EXTENSION ACTIVATABLE_CLASS_ID/PACKAGE_FAMILY_NAME; Cannot create HEVC SW encoder",
          v32);
      }
    }
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
    LODWORD(v32) = v11;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)WPP_225ebdff2f7730fc004038fb7f46f5ea_Traceguids,
      v22,
      (__int64)"ActivateObject failed",
      v32);
  }
LABEL_33:
  v28 = pv;
  if ( pv )
  {
    for ( i = 0; i < v33; ++i )
    {
      v30 = v28[i];
      if ( v30 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 16LL))(v28[i]);
        *((_QWORD *)pv + i) = 0;
        v28 = pv;
      }
    }
    CoTaskMemFree(v28);
    pv = 0;
  }
  else
  {
    v11 = -2147467259;
  }
  CoTaskMemFree(String1);
  CoTaskMemFree(v39);
  if ( v11 >= 0 )
  {
    *((_DWORD *)this + 40) = 1;
    *((_DWORD *)this + 42) = 1;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180095308  mov     [rsp-8+arg_10], rbx
0x18009530d  mov     [rsp-8+arg_18], rsi
0x180095312  push    rbp
0x180095313  push    rdi
0x180095314  push    r12
0x180095316  push    r14
0x180095318  push    r15
0x18009531a  lea     rbp, [rsp-37h]
0x18009531f  sub     rsp, 0E0h
0x180095326  mov     rax, cs:__security_cookie
0x18009532d  xor     rax, rsp
0x180095330  mov     [rbp+57h+var_30], rax
0x180095334  xor     r12d, r12d
0x180095337  mov     r15, rdx
0x18009533a  mov     [rcx+0A0h], r12d
0x180095341  mov     rsi, rcx
0x180095344  mov     [rcx+0A8h], r12d
0x18009534b  mov     eax, cs:dword_1801B76C8
0x180095351  mov     [rbp+57h+String1], r12
0x180095355  mov     [rbp+57h+var_78], r12
0x180095359  mov     [rbp+57h+pv], r12
0x18009535d  mov     [rbp+57h+var_B0], r12d
0x180095361  cmp     eax, 5
0x180095364  jbe     short loc_180095386
0x180095366  lea     rax, aCocreateinstan_5; "CoCreateInstance CLSID_CMSH265EncoderMF"...
0x18009536d  mov     [rbp+57h+var_98], rax
0x180095371  lea     rdx, byte_1801A2769
0x180095378  lea     rax, [rbp+57h+var_98]
0x18009537c  mov     [rsp+100h+var_E0], rax
0x180095381  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180095386  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x18009538d  mov     rax, [rsi+58h]
0x180095391  lea     rcx, [rbp+57h+var_B0]
0x180095395  movups  xmm1, xmmword ptr cs:MFVideoFormat_HEVC.Data1
0x18009539c  mov     [rsp+100h+var_D8], rcx
0x1800953a1  lea     r9, [rbp+57h+var_50]
0x1800953a5  movdqu  [rbp+57h+var_50], xmm0
0x1800953aa  xor     r8d, r8d
0x1800953ad  lea     rcx, [rbp+57h+pv]
0x1800953b1  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1800953b8  mov     [rbp+57h+var_A0], r12d
0x1800953bc  movdqu  [rbp+57h+var_40], xmm1
0x1800953c1  mov     rax, [rax+78h]
0x1800953c5  lea     edx, [r8+3Bh]
0x1800953c9  mov     [rsp+100h+var_E0], rcx
0x1800953ce  lea     rcx, [rbp+57h+var_90]
0x1800953d2  movdqu  [rbp+57h+var_90], xmm0
0x1800953d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800953dc  mov     ebx, eax
0x1800953de  test    eax, eax
0x1800953e0  jns     loc_180095472
0x1800953e6  mov     ecx, cs:dword_1801B76C8
0x1800953ec  cmp     ecx, 2
0x1800953ef  jbe     loc_1800956ED
0x1800953f5  lea     rax, aMSpmfapiPfnmft_0; "m_spMFApi->_pfnMFTEnumEx failed"
0x1800953fc  mov     [rbp+57h+var_70], 34Ch
0x180095403  mov     [rbp+57h+var_60], rax
0x180095407  lea     rdx, byte_1801A278F
0x18009540e  lea     rax, aCreateswencode; "CreateSWEncoderMFT"
0x180095415  mov     dword ptr [rbp+57h+var_98], ebx
0x180095418  mov     [rbp+57h+var_58], rax
0x18009541c  lea     rax, aOnecoreuapTerm_7; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180095423  mov     [rbp+57h+var_68], rax
0x180095427  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009542e  mov     qword ptr [rbp+57h+var_90], rax
0x180095432  lea     rax, [rbp+57h+var_60]
0x180095436  mov     [rsp+100h+var_B8], rax
0x18009543b  lea     rax, [rbp+57h+var_58]
0x18009543f  mov     [rsp+100h+var_C0], rax
0x180095444  lea     rax, [rbp+57h+var_70]
0x180095448  mov     [rsp+100h+var_C8], rax
0x18009544d  lea     rax, [rbp+57h+var_68]
0x180095451  mov     [rsp+100h+var_D0], rax
0x180095456  lea     rax, [rbp+57h+var_98]
0x18009545a  mov     [rsp+100h+var_D8], rax
0x18009545f  lea     rax, [rbp+57h+var_90]
0x180095463  mov     [rsp+100h+var_E0], rax
0x180095468  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009546d  jmp     loc_1800956ED
0x180095472  mov     ebx, 800701B1h
0x180095477  mov     edi, r12d
0x18009547a  cmp     [rbp+57h+var_B0], r12d
0x18009547e  jbe     loc_180095684
0x180095484  mov     rax, [rbp+57h+pv]
0x180095488  lea     r9, [rbp+57h+var_A0]
0x18009548c  mov     r14d, edi
0x18009548f  lea     r8, [rbp+57h+String1]
0x180095493  lea     rdx, MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID
0x18009549a  mov     rcx, [rax+r14*8]
0x18009549e  mov     rax, [rcx]
0x1800954a1  mov     rax, [rax+68h]
0x1800954a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800954aa  test    eax, eax
0x1800954ac  js      short loc_180095528
0x1800954ae  mov     rax, [rbp+57h+pv]
0x1800954b2  lea     r9, [rbp+57h+var_A0]
0x1800954b6  lea     r8, [rbp+57h+var_78]
0x1800954ba  lea     rdx, MF_MEDIA_EXTENSION_PACKAGE_FAMILY_NAME
0x1800954c1  mov     rcx, [rax+r14*8]
0x1800954c5  mov     rax, [rcx]
0x1800954c8  mov     rax, [rax+68h]
0x1800954cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800954d1  test    eax, eax
0x1800954d3  js      short loc_180095528
0x1800954d5  mov     eax, cs:dword_1801B76C8
0x1800954db  cmp     eax, 5
0x1800954de  jbe     short loc_180095500
0x1800954e0  lea     rax, aCreatingSwEnco; "creating SW encoder from store"
0x1800954e7  mov     qword ptr [rbp+57h+var_90], rax
0x1800954eb  lea     rdx, byte_1801A271D
0x1800954f2  lea     rax, [rbp+57h+var_90]
0x1800954f6  mov     [rsp+100h+var_E0], rax
0x1800954fb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180095500  mov     rcx, [rbp+57h+String1]; String1
0x180095504  lea     rdx, aH265encoderCh2; "H265Encoder.CH265EncoderTransform"
0x18009550b  call    _wcsicmp
0x180095510  test    eax, eax
0x180095512  jnz     short loc_180095528
0x180095514  mov     rcx, [rbp+57h+var_78]; String1
0x180095518  lea     rdx, aMicrosoftHevcv; "Microsoft.HEVCVideoExtension_8wekyb3d8b"...
0x18009551f  call    _wcsicmp
0x180095524  test    eax, eax
0x180095526  jz      short loc_180095538
0x180095528  inc     edi
0x18009552a  cmp     edi, [rbp+57h+var_B0]
0x18009552d  jb      loc_180095484
0x180095533  jmp     loc_180095684
0x180095538  mov     eax, cs:dword_1801B76C8
0x18009553e  cmp     eax, 5
0x180095541  jbe     short loc_180095563
0x180095543  lea     rax, aTryingToActiva; "trying to activate transform object"
0x18009554a  mov     qword ptr [rbp+57h+var_90], rax
0x18009554e  lea     rdx, byte_1801A2743
0x180095555  lea     rax, [rbp+57h+var_90]
0x180095559  mov     [rsp+100h+var_E0], rax
0x18009555e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180095563  mov     rax, [rbp+57h+pv]
0x180095567  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x18009556e  mov     r8, r15
0x180095571  mov     rcx, [rax+r14*8]
0x180095575  mov     rax, [rcx]
0x180095578  mov     rax, [rax+108h]
0x18009557f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095584  mov     ebx, eax
0x180095586  mov     eax, cs:dword_1801B76C8
0x18009558c  cmp     eax, 5
0x18009558f  jbe     short loc_1800955BD
0x180095591  lea     rax, aActivateTransf; "Activate transform object succeeded ?"
0x180095598  mov     dword ptr [rbp+57h+var_98], ebx
0x18009559b  mov     qword ptr [rbp+57h+var_90], rax
0x18009559f  lea     rdx, byte_1801A26B3
0x1800955a6  lea     rax, [rbp+57h+var_98]
0x1800955aa  mov     [rsp+100h+var_D8], rax
0x1800955af  lea     rax, [rbp+57h+var_90]
0x1800955b3  mov     [rsp+100h+var_E0], rax
0x1800955b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800955bd  test    ebx, ebx
0x1800955bf  jns     short loc_180095607
0x1800955c1  mov     rax, cs:WPP_GLOBAL_Control
0x1800955c8  lea     rcx, WPP_GLOBAL_Control
0x1800955cf  cmp     rax, rcx
0x1800955d2  jz      loc_1800956ED
0x1800955d8  test    byte ptr [rax+1Ch], 8
0x1800955dc  jz      loc_1800956ED
0x1800955e2  cmp     byte ptr [rax+19h], 2
0x1800955e6  jb      loc_1800956ED
0x1800955ec  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800955f2  mov     edx, 23h ; '#'
0x1800955f7  mov     dword ptr [rsp+100h+var_D8], ebx
0x1800955fb  lea     rcx, aActivateobject; "ActivateObject failed"
0x180095602  jmp     loc_1800956CE
0x180095607  mov     rcx, [rsi+0C8h]; pv
0x18009560e  call    cs:__imp_CoTaskMemFree
0x180095614  mov     rax, [rbp+57h+pv]
0x180095618  lea     rdx, MFT_FRIENDLY_NAME_Attribute
0x18009561f  mov     [rsi+0C8h], r12
0x180095626  xor     r9d, r9d
0x180095629  xor     r8d, r8d
0x18009562c  mov     [rsp+100h+var_E0], r12
0x180095631  mov     rcx, [rax+r14*8]
0x180095635  mov     rax, [rcx]
0x180095638  mov     rax, [rax+60h]
0x18009563c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095641  test    eax, eax
0x180095643  js      short loc_180095684
0x180095645  mov     eax, cs:dword_1801B76C8
0x18009564b  cmp     eax, 5
0x18009564e  jbe     short loc_180095684
0x180095650  mov     rax, [rsi+0C8h]
0x180095657  lea     rdx, byte_1801A26E1
0x18009565e  mov     qword ptr [rbp+57h+var_90], rax
0x180095662  lea     rax, aCreatedMftSwEn; "Created MFT SW encoder from HEVC Video "...
0x180095669  mov     [rbp+57h+var_68], rax
0x18009566d  lea     rax, [rbp+57h+var_90]
0x180095671  mov     [rsp+100h+var_D8], rax
0x180095676  lea     rax, [rbp+57h+var_68]
0x18009567a  mov     [rsp+100h+var_E0], rax
0x18009567f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180095684  cmp     [rbp+57h+String1], r12
0x180095688  jz      short loc_180095690
0x18009568a  cmp     [rbp+57h+var_78], r12
0x18009568e  jnz     short loc_1800956ED
0x180095690  mov     ebx, 80004005h
0x180095695  mov     rax, cs:WPP_GLOBAL_Control
0x18009569c  lea     rcx, WPP_GLOBAL_Control
0x1800956a3  cmp     rax, rcx
0x1800956a6  jz      short loc_1800956ED
0x1800956a8  test    byte ptr [rax+1Ch], 8
0x1800956ac  jz      short loc_1800956ED
0x1800956ae  cmp     byte ptr [rax+19h], 2
0x1800956b2  jb      short loc_1800956ED
0x1800956b4  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800956ba  mov     edx, 24h ; '$'
0x1800956bf  mov     dword ptr [rsp+100h+var_D8], 80004005h
0x1800956c7  lea     rcx, aFailedToRetrie; "Failed to retrieve MF MEDIA EXTENSION A"...
0x1800956ce  mov     [rsp+100h+var_E0], rcx
0x1800956d3  lea     r8, WPP_225ebdff2f7730fc004038fb7f46f5ea_Traceguids
0x1800956da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800956e1  mov     r9d, eax
0x1800956e4  mov     rcx, [rcx+10h]
0x1800956e8  call    WPP_SF_DsD
0x1800956ed  mov     rcx, [rbp+57h+pv]
0x1800956f1  test    rcx, rcx
0x1800956f4  jz      short loc_180095739
0x1800956f6  mov     edi, r12d
0x1800956f9  cmp     [rbp+57h+var_B0], r12d
0x1800956fd  jbe     short loc_18009572D
0x1800956ff  mov     r14d, edi
0x180095702  mov     rdx, [rcx+r14*8]
0x180095706  test    rdx, rdx
0x180095709  jz      short loc_180095726
0x18009570b  mov     rax, [rdx]
0x18009570e  mov     rcx, rdx
0x180095711  mov     rax, [rax+10h]
0x180095715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009571a  mov     rax, [rbp+57h+pv]
0x18009571e  mov     [rax+r14*8], r12
0x180095722  mov     rcx, [rbp+57h+pv]; pv
0x180095726  inc     edi
0x180095728  cmp     edi, [rbp+57h+var_B0]
0x18009572b  jb      short loc_1800956FF
0x18009572d  call    cs:__imp_CoTaskMemFree
0x180095733  mov     [rbp+57h+pv], r12
0x180095737  jmp     short loc_18009573E
0x180095739  mov     ebx, 80004005h
0x18009573e  mov     rcx, [rbp+57h+String1]; pv
0x180095742  call    cs:__imp_CoTaskMemFree
0x180095748  mov     rcx, [rbp+57h+var_78]; pv
0x18009574c  call    cs:__imp_CoTaskMemFree
0x180095752  test    ebx, ebx
0x180095754  js      short loc_18009576A
0x180095756  mov     dword ptr [rsi+0A0h], 1
0x180095760  mov     dword ptr [rsi+0A8h], 1
0x18009576a  mov     eax, ebx
0x18009576c  mov     rcx, [rbp+57h+var_30]
0x180095770  xor     rcx, rsp; StackCookie
0x180095773  call    __security_check_cookie
0x180095778  lea     r11, [rsp+100h+var_20]
0x180095780  mov     rbx, [r11+40h]
0x180095784  mov     rsi, [r11+48h]
0x180095788  mov     rsp, r11
0x18009578b  pop     r15
0x18009578d  pop     r14
0x18009578f  pop     r12
0x180095791  pop     rdi
0x180095792  pop     rbp
0x180095793  retn
```
