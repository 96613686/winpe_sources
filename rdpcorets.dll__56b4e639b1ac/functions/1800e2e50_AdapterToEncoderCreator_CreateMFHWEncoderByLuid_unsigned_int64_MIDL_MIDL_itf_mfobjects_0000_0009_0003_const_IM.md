# AdapterToEncoderCreator::CreateMFHWEncoderByLuid(unsigned __int64,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,ushort * &)

- ea: `0x1800e2e50`
- end: `0x1800e3382`
- name: `?CreateMFHWEncoderByLuid@AdapterToEncoderCreator@@QEAAJ_KPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAPEAUIMFTransform@@AEAPEAG@Z`
- size: `1330`
- prototype: `__int64 __usercall@<rax>(AdapterToEncoderCreator *__hidden this@<rcx>, unsigned __int64@<rdx>, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *@<r8>, struct IMFTransform **@<r9>, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180086b74`
- `0x180094be0`

## callees

- `0x1800015f0`
- `0x180033da0`
- `0x1800348e0`
- `0x180034970`
- `0x1800598d0`
- `0x1800da1b0`
- `0x1800e2e50`
- `0x1800e3ff0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800e3377`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800e3377`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2ee2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2f41`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2f79`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2ee2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2f41`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2f79`

## string_xrefs

- `0x1800e30ae`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e31b9`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e3291`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e309f`: `CreateMFHWEncoderByLuid`
- `0x1800e31aa`: `CreateMFHWEncoderByLuid`
- `0x1800e325c`: `CreateMFHWEncoderByLuid`

## pseudocode

```c
__int64 __fastcall AdapterToEncoderCreator::CreateMFHWEncoderByLuid(
        CMFApi **this,
        const char *a2,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a3,
        struct IMFTransform **a4,
        unsigned __int16 **a5)
{
  unsigned int v5; // edi
  int ActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  int HWEncoderByLuid; // ebx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 (__fastcall ***v20)(_QWORD, GUID *, struct IDXGIAdapter4 **); // rcx
  struct IDXGIAdapter4 *v21; // rcx
  int v23; // [rsp+58h] [rbp-B0h] BYREF
  int v24; // [rsp+5Ch] [rbp-ACh] BYREF
  const char *v25; // [rsp+60h] [rbp-A8h] BYREF
  struct IDXGIAdapter4 *v26; // [rsp+68h] [rbp-A0h] BYREF
  const char *v27; // [rsp+70h] [rbp-98h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, struct IDXGIAdapter4 **); // [rsp+78h] [rbp-90h] BYREF
  const char *Destination; // [rsp+80h] [rbp-88h] BYREF
  const char *v30; // [rsp+88h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v32[256]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v33; // [rsp+1A8h] [rbp+A0h]
  char Source[24]; // [rsp+1D0h] [rbp+C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1E8h] [rbp+E0h] BYREF
  char *v36; // [rsp+1F8h] [rbp+F0h]
  int v37; // [rsp+200h] [rbp+F8h]
  int v38; // [rsp+204h] [rbp+FCh]
  const char *v39; // [rsp+208h] [rbp+100h]
  __int64 v40; // [rsp+210h] [rbp+108h]
  int *v41; // [rsp+218h] [rbp+110h]
  __int64 v42; // [rsp+220h] [rbp+118h]
  const char *v43; // [rsp+228h] [rbp+120h]
  __int64 v44; // [rsp+230h] [rbp+128h]
  int *v45; // [rsp+238h] [rbp+130h]
  __int64 v46; // [rsp+240h] [rbp+138h]
  const char *v47; // [rsp+248h] [rbp+140h]
  __int64 v48; // [rsp+250h] [rbp+148h]
  const char *v49; // [rsp+258h] [rbp+150h]
  __int64 v50; // [rsp+260h] [rbp+158h]
  const char **v51; // [rsp+268h] [rbp+160h]
  __int64 v52; // [rsp+270h] [rbp+168h]

  v5 = 0;
  v26 = 0;
  v28 = 0;
  memset_0(v32, 0, 0x140u);
  Destination = 0;
  if ( !*this )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v11 = 14;
    v12 = "m_spMFApi";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_604b36dd83cf35ab199212a9476a51f1_Traceguids,
      ActivityIdPrefix,
      (__int64)v12);
LABEL_7:
    HWEncoderByLuid = -2147467261;
    goto LABEL_29;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v11 = 15;
    v12 = "pOutputType";
    goto LABEL_6;
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    v11 = 16;
    v12 = "ppTransform";
    goto LABEL_6;
  }
  HWEncoderByLuid = -2147467259;
  while ( (*(unsigned int (__fastcall **)(CMFApi *, _QWORD, _QWORD))(*(_QWORD *)this[1] + 96LL))(this[1], v5, &v28) != -2005270526 )
  {
    HWEncoderByLuid = (**v28)(v28, &GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e, &v26);
    if ( HWEncoderByLuid < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v24 = 323;
        v27 = "Failed to QI DXGI Adapter.";
        v23 = HWEncoderByLuid;
        *(_QWORD *)&EventDescriptor.Id = "CreateMFHWEncoderByLuid";
        v30 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
        v25 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v14,
          (unsigned int)&byte_1801AA197,
          v15,
          v16,
          (__int64)&v25,
          (__int64)&v23,
          (__int64)&v30,
          (__int64)&v24,
          (__int64)&EventDescriptor,
          (__int64)&v27);
      }
      goto LABEL_29;
    }
    HWEncoderByLuid = ((__int64 (__fastcall *)(struct IDXGIAdapter4 *, _BYTE *))v26->lpVtbl->GetDesc3)(v26, v32);
    if ( HWEncoderByLuid < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v23 = 326;
        v25 = "Failed to get description from DXGI adapter.";
        v24 = HWEncoderByLuid;
        v30 = "CreateMFHWEncoderByLuid";
        *(_QWORD *)&EventDescriptor.Id = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
        v27 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v17,
          (unsigned int)byte_1801AA24B,
          v18,
          v19,
          (__int64)&v27,
          (__int64)&v24,
          (__int64)&EventDescriptor,
          (__int64)&v23,
          (__int64)&v30,
          (__int64)&v25);
      }
      goto LABEL_29;
    }
    ++v5;
    memcpy_s_0(&Destination, 8u, Source, 8u);
    if ( a2 != Destination
      || (unsigned int)AdapterToEncoderCreator::IsDriverVersionBlocked(
                         (AdapterToEncoderCreator *)this,
                         v26,
                         (unsigned __int64)Destination,
                         v33) )
    {
      HWEncoderByLuid = -2147024463;
    }
    else
    {
      HWEncoderByLuid = CMFApi::CreateHWEncoderByLuid(*this, (unsigned __int64)Destination, a3, a4, a5);
      if ( HWEncoderByLuid >= 0 )
        goto LABEL_29;
    }
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v27 = a2;
    v51 = &v27;
    v24 = 346;
    v49 = "Adapter not found or supported";
    v23 = HWEncoderByLuid;
    v47 = "CreateMFHWEncoderByLuid";
    v52 = 8;
    v45 = &v24;
    v50 = 31;
    v43 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
    v48 = 24;
    v41 = &v23;
    v39 = "Error HResult failed";
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_1801B76D0;
    v46 = 4;
    v44 = 69;
    v42 = 4;
    v40 = 21;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_1801B76D0;
    v36 = byte_1801AA1F9;
    UserData.Reserved = 2;
    v37 = 81;
    v38 = 1;
    LODWORD(v25) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 9u, &UserData);
  }
LABEL_29:
  v20 = v28;
  if ( v28 )
  {
    v28 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IDXGIAdapter4 **)))(*v20)[2])(v20);
  }
  v21 = v26;
  if ( v26 )
  {
    v26 = 0;
    ((void (__fastcall *)(struct IDXGIAdapter4 *))v21->lpVtbl->Release)(v21);
  }
  return (unsigned int)HWEncoderByLuid;
}

```

## disassembly

```asm
0x1800e2e50  mov     r11, rsp
0x1800e2e53  push    rbp
0x1800e2e54  push    rbx
0x1800e2e55  push    rdi
0x1800e2e56  lea     rbp, [r11-1B8h]
0x1800e2e5d  sub     rsp, 2A0h
0x1800e2e64  mov     rax, cs:__security_cookie
0x1800e2e6b  xor     rax, rsp
0x1800e2e6e  mov     [rbp+1B0h+var_40], rax
0x1800e2e75  mov     [r11+10h], rsi
0x1800e2e79  xor     edi, edi
0x1800e2e7b  mov     [r11-20h], r12
0x1800e2e7f  mov     rsi, rcx
0x1800e2e82  mov     [r11-28h], r13
0x1800e2e86  lea     rcx, [rbp+1B0h+var_210]; void *
0x1800e2e8a  mov     r13, [rbp+1B0h+arg_20]
0x1800e2e91  mov     r12, rdx
0x1800e2e94  mov     [r11-30h], r14
0x1800e2e98  xor     edx, edx; Val
0x1800e2e9a  mov     r14, r8
0x1800e2e9d  mov     [r11-38h], r15
0x1800e2ea1  mov     r8d, 140h; Size
0x1800e2ea7  mov     [rsp+2B0h+var_250], rdi
0x1800e2eac  mov     r15, r9
0x1800e2eaf  mov     [rsp+2B0h+var_240], rdi
0x1800e2eb4  call    memset_0
0x1800e2eb9  mov     [rsp+2B0h+Destination], rdi
0x1800e2ebe  cmp     [rsi], rdi
0x1800e2ec1  jnz     short loc_1800E2F1D
0x1800e2ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2eca  lea     rax, WPP_GLOBAL_Control
0x1800e2ed1  cmp     rcx, rax
0x1800e2ed4  jz      short loc_1800E2F13
0x1800e2ed6  test    byte ptr [rcx+1Ch], 8
0x1800e2eda  jz      short loc_1800E2F13
0x1800e2edc  cmp     byte ptr [rcx+19h], 2
0x1800e2ee0  jb      short loc_1800E2F13
0x1800e2ee2  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e2ee8  mov     edx, 0Eh
0x1800e2eed  lea     rcx, aMSpmfapi; "m_spMFApi"
0x1800e2ef4  mov     qword ptr [rsp+2B0h+UserDataCount], rcx
0x1800e2ef9  lea     r8, WPP_604b36dd83cf35ab199212a9476a51f1_Traceguids
0x1800e2f00  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2f07  mov     r9d, eax
0x1800e2f0a  mov     rcx, [rcx+10h]
0x1800e2f0e  call    WPP_SF_Ds
0x1800e2f13  mov     ebx, 80004003h
0x1800e2f18  jmp     loc_1800E3106
0x1800e2f1d  test    r14, r14
0x1800e2f20  jnz     short loc_1800E2F55
0x1800e2f22  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2f29  lea     rax, WPP_GLOBAL_Control
0x1800e2f30  cmp     rcx, rax
0x1800e2f33  jz      short loc_1800E2F13
0x1800e2f35  test    byte ptr [rcx+1Ch], 8
0x1800e2f39  jz      short loc_1800E2F13
0x1800e2f3b  cmp     byte ptr [rcx+19h], 2
0x1800e2f3f  jb      short loc_1800E2F13
0x1800e2f41  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e2f47  mov     edx, 0Fh
0x1800e2f4c  lea     rcx, aPoutputtype; "pOutputType"
0x1800e2f53  jmp     short loc_1800E2EF4
0x1800e2f55  test    r15, r15
0x1800e2f58  jnz     short loc_1800E2F90
0x1800e2f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2f61  lea     rax, WPP_GLOBAL_Control
0x1800e2f68  cmp     rcx, rax
0x1800e2f6b  jz      short loc_1800E2F13
0x1800e2f6d  test    byte ptr [rcx+1Ch], 8
0x1800e2f71  jz      short loc_1800E2F13
0x1800e2f73  cmp     byte ptr [rcx+19h], 2
0x1800e2f77  jb      short loc_1800E2F13
0x1800e2f79  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e2f7f  mov     edx, 10h
0x1800e2f84  lea     rcx, aPptransform; "ppTransform"
0x1800e2f8b  jmp     loc_1800E2EF4
0x1800e2f90  mov     ebx, 80004005h
0x1800e2f95  nop     word ptr [rax+rax+00000000h]
0x1800e2fa0  mov     rcx, [rsi+8]
0x1800e2fa4  lea     r8, [rsp+2B0h+var_240]
0x1800e2fa9  mov     edx, edi
0x1800e2fab  mov     rax, [rcx]
0x1800e2fae  mov     rax, [rax+60h]
0x1800e2fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2fb7  cmp     eax, 887A0002h
0x1800e2fbc  jz      loc_1800E320F
0x1800e2fc2  mov     rcx, [rsp+2B0h+var_240]
0x1800e2fc7  lea     r8, [rsp+2B0h+var_250]
0x1800e2fcc  lea     rdx, _GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e
0x1800e2fd3  mov     rax, [rcx]
0x1800e2fd6  mov     rax, [rax]
0x1800e2fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2fde  mov     ebx, eax
0x1800e2fe0  test    eax, eax
0x1800e2fe2  js      loc_1800E3180
0x1800e2fe8  mov     rcx, [rsp+2B0h+var_250]
0x1800e2fed  lea     rdx, [rbp+1B0h+var_210]
0x1800e2ff1  mov     rax, [rcx]
0x1800e2ff4  mov     rax, [rax+90h]
0x1800e2ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3000  mov     ebx, eax
0x1800e3002  test    eax, eax
0x1800e3004  js      short loc_1800E3075
0x1800e3006  mov     r9d, 8; SourceSize
0x1800e300c  lea     r8, [rbp+1B0h+Source]; Source
0x1800e3013  mov     edx, r9d; DestinationSize
0x1800e3016  lea     rcx, [rsp+2B0h+Destination]; Destination
0x1800e301b  inc     edi
0x1800e301d  call    memcpy_s_0
0x1800e3022  mov     r8, [rsp+2B0h+Destination]; unsigned __int64
0x1800e3027  cmp     r12, r8
0x1800e302a  jnz     short loc_1800E306B
0x1800e302c  mov     r9d, [rbp+1B0h+var_110]; unsigned int
0x1800e3033  mov     rcx, rsi; this
0x1800e3036  mov     rdx, [rsp+2B0h+var_250]; struct IDXGIAdapter4 *
0x1800e303b  call    ?IsDriverVersionBlocked@AdapterToEncoderCreator@@QEAAHPEAUIDXGIAdapter4@@_KI@Z; AdapterToEncoderCreator::IsDriverVersionBlocked(IDXGIAdapter4 *,unsigned __int64,uint)
0x1800e3040  test    eax, eax
0x1800e3042  jnz     short loc_1800E306B
0x1800e3044  mov     rdx, [rsp+2B0h+Destination]; unsigned __int64
0x1800e3049  mov     r9, r15; struct IMFTransform **
0x1800e304c  mov     rcx, [rsi]; this
0x1800e304f  mov     r8, r14; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x1800e3052  mov     qword ptr [rsp+2B0h+UserDataCount], r13; unsigned __int16 **
0x1800e3057  call    ?CreateHWEncoderByLuid@CMFApi@@QEAAJ_KPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAPEAUIMFTransform@@AEAPEAG@Z; CMFApi::CreateHWEncoderByLuid(unsigned __int64,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,ushort * &)
0x1800e305c  mov     ebx, eax
0x1800e305e  test    eax, eax
0x1800e3060  js      loc_1800E2FA0
0x1800e3066  jmp     loc_1800E3104
0x1800e306b  mov     ebx, 800701B1h
0x1800e3070  jmp     loc_1800E2FA0
0x1800e3075  mov     eax, cs:dword_1801B76C8
0x1800e307b  cmp     eax, 2
0x1800e307e  jbe     loc_1800E3104
0x1800e3084  lea     rax, aFailedToGetDes; "Failed to get description from DXGI ada"...
0x1800e308b  mov     dword ptr [rsp+2B0h+var_260], 146h
0x1800e3093  mov     [rsp+2B0h+var_258], rax
0x1800e3098  lea     rdx, byte_1801AA24B
0x1800e309f  lea     rax, aCreatemfhwenco; "CreateMFHWEncoderByLuid"
0x1800e30a6  mov     dword ptr [rsp+2B0h+var_260+4], ebx
0x1800e30aa  mov     [rbp+1B0h+var_230], rax
0x1800e30ae  lea     rax, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e30b5  mov     qword ptr [rbp+1B0h+EventDescriptor.Id], rax
0x1800e30b9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e30c0  mov     [rsp+2B0h+var_248], rax
0x1800e30c5  lea     rax, [rsp+2B0h+var_258]
0x1800e30ca  mov     qword ptr [rsp+2B0h+var_268], rax
0x1800e30cf  lea     rax, [rbp+1B0h+var_230]
0x1800e30d3  mov     [rsp+2B0h+var_270], rax
0x1800e30d8  lea     rax, [rsp+2B0h+var_260]
0x1800e30dd  mov     [rsp+2B0h+var_278], rax
0x1800e30e2  lea     rax, [rbp+1B0h+EventDescriptor]
0x1800e30e6  mov     [rsp+2B0h+var_280], rax
0x1800e30eb  lea     rax, [rsp+2B0h+var_260+4]
0x1800e30f0  mov     [rsp+2B0h+UserData], rax
0x1800e30f5  lea     rax, [rsp+2B0h+var_248]
0x1800e30fa  mov     qword ptr [rsp+2B0h+UserDataCount], rax
0x1800e30ff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800e3104  xor     edi, edi
0x1800e3106  mov     rcx, [rsp+2B0h+var_240]
0x1800e310b  mov     r15, [rsp+2B0h+var_30]
0x1800e3113  mov     r14, [rsp+2B0h+var_28]
0x1800e311b  mov     r13, [rsp+2B0h+var_20]
0x1800e3123  mov     r12, [rsp+298h]
0x1800e312b  mov     rsi, [rsp+2B0h+arg_8]
0x1800e3133  test    rcx, rcx
0x1800e3136  jz      short loc_1800E3149
0x1800e3138  mov     [rsp+2B0h+var_240], rdi
0x1800e313d  mov     rax, [rcx]
0x1800e3140  mov     rax, [rax+10h]
0x1800e3144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3149  mov     rcx, [rsp+2B0h+var_250]
0x1800e314e  test    rcx, rcx
0x1800e3151  jz      short loc_1800E3164
0x1800e3153  mov     [rsp+2B0h+var_250], rdi
0x1800e3158  mov     rax, [rcx]
0x1800e315b  mov     rax, [rax+10h]
0x1800e315f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3164  mov     eax, ebx
0x1800e3166  mov     rcx, [rbp+1B0h+var_40]
0x1800e316d  xor     rcx, rsp; StackCookie
0x1800e3170  call    __security_check_cookie
0x1800e3175  add     rsp, 2A0h
0x1800e317c  pop     rdi
0x1800e317d  pop     rbx
0x1800e317e  pop     rbp
0x1800e317f  retn
0x1800e3180  mov     eax, cs:dword_1801B76C8
0x1800e3186  cmp     eax, 2
0x1800e3189  jbe     loc_1800E3104
0x1800e318f  lea     rax, aFailedToQiDxgi; "Failed to QI DXGI Adapter."
0x1800e3196  mov     dword ptr [rsp+2B0h+var_260+4], 143h
0x1800e319e  mov     [rsp+2B0h+var_248], rax
0x1800e31a3  lea     rdx, byte_1801AA197
0x1800e31aa  lea     rax, aCreatemfhwenco; "CreateMFHWEncoderByLuid"
0x1800e31b1  mov     dword ptr [rsp+2B0h+var_260], ebx
0x1800e31b5  mov     qword ptr [rbp+1B0h+EventDescriptor.Id], rax
0x1800e31b9  lea     rax, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e31c0  mov     [rbp+1B0h+var_230], rax
0x1800e31c4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e31cb  mov     [rsp+2B0h+var_258], rax
0x1800e31d0  lea     rax, [rsp+2B0h+var_248]
0x1800e31d5  mov     qword ptr [rsp+2B0h+var_268], rax
0x1800e31da  lea     rax, [rbp+1B0h+EventDescriptor]
0x1800e31de  mov     [rsp+2B0h+var_270], rax
0x1800e31e3  lea     rax, [rsp+2B0h+var_260+4]
0x1800e31e8  mov     [rsp+2B0h+var_278], rax
0x1800e31ed  lea     rax, [rbp+1B0h+var_230]
0x1800e31f1  mov     [rsp+2B0h+var_280], rax
0x1800e31f6  lea     rax, [rsp+2B0h+var_260]
0x1800e31fb  mov     [rsp+2B0h+UserData], rax
0x1800e3200  lea     rax, [rsp+2B0h+var_258]
0x1800e3205  mov     qword ptr [rsp+2B0h+UserDataCount], rax
0x1800e320a  jmp     loc_1800E30FF
0x1800e320f  test    ebx, ebx
0x1800e3211  jns     loc_1800E3104
0x1800e3217  mov     eax, cs:dword_1801B76C8
0x1800e321d  cmp     eax, 2
0x1800e3220  jbe     loc_1800E3104
0x1800e3226  mov     [rsp+2B0h+var_248], r12
0x1800e322b  lea     rax, [rsp+2B0h+var_248]
0x1800e3230  mov     [rbp+1B0h+var_50], rax
0x1800e3237  lea     rcx, _TraceLoggingMetadata
0x1800e323e  mov     dword ptr [rsp+2B0h+var_260+4], 15Ah
0x1800e3246  lea     rax, aAdapterNotFoun_0; "Adapter not found or supported"
0x1800e324d  mov     [rbp+1B0h+var_60], rax
0x1800e3254  lea     rdx, [rbp+1B0h+EventDescriptor]; EventDescriptor
0x1800e3258  mov     dword ptr [rsp+2B0h+var_260], ebx
0x1800e325c  lea     rax, aCreatemfhwenco; "CreateMFHWEncoderByLuid"
0x1800e3263  mov     [rbp+1B0h+var_70], rax
0x1800e326a  xor     edi, edi
0x1800e326c  mov     [rbp+1B0h+var_48], 8
0x1800e3277  lea     rax, [rsp+2B0h+var_260+4]
0x1800e327c  mov     [rbp+1B0h+var_80], rax
0x1800e3283  xor     r9d, r9d; RelatedActivityId
0x1800e3286  mov     [rbp+1B0h+var_58], 1Fh
0x1800e3291  lea     rax, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e3298  mov     [rbp+1B0h+var_90], rax
0x1800e329f  xor     r8d, r8d; ActivityId
0x1800e32a2  mov     [rbp+1B0h+var_68], 18h
0x1800e32ad  lea     rax, [rsp+2B0h+var_260]
0x1800e32b2  mov     [rbp+1B0h+var_A0], rax
0x1800e32b9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800e32c0  mov     [rbp+1B0h+var_B0], rax
0x1800e32c7  movzx   eax, cs:word_1801AA1EF
0x1800e32ce  mov     dword ptr [rbp+1B0h+EventDescriptor.Level], eax
0x1800e32d1  mov     rax, cs:off_1801B76D0
0x1800e32d8  mov     [rbp+1B0h+var_D0.Ptr], rax
0x1800e32df  mov     [rbp+1B0h+var_78], 4
0x1800e32ea  mov     [rbp+1B0h+var_88], 45h ; 'E'
0x1800e32f5  mov     [rbp+1B0h+var_98], 4
0x1800e3300  mov     [rbp+1B0h+var_A8], 15h
0x1800e330b  mov     dword ptr [rbp+1B0h+EventDescriptor.Id], 0B000000h
0x1800e3312  mov     [rbp+1B0h+EventDescriptor.Keyword], rdi
0x1800e3316  movzx   eax, word ptr [rax]
0x1800e3319  mov     [rbp+1B0h+var_D0.Size], eax
0x1800e331f  lea     rax, byte_1801AA1F9
0x1800e3326  mov     [rbp+1B0h+var_C0], rax
0x1800e332d  lea     rax, _TraceLoggingMetadataEnd
0x1800e3334  sub     eax, ecx
0x1800e3336  mov     dword ptr [rbp+1B0h+var_D0.0Ch], 2
0x1800e3340  mov     [rbp+1B0h+var_B8], 51h ; 'Q'
0x1800e334a  mov     [rbp+1B0h+var_B4], 1
0x1800e3354  mov     dword ptr [rsp+2B0h+var_258], eax
0x1800e3358  mov     eax, dword ptr [rsp+2B0h+var_258]
0x1800e335c  mov     rcx, cs:qword_1801B76E8; RegHandle
0x1800e3363  lea     rax, [rbp+1B0h+var_D0]
0x1800e336a  mov     [rsp+2B0h+UserData], rax; UserData
0x1800e336f  mov     [rsp+2B0h+UserDataCount], 9; UserDataCount
0x1800e3377  call    cs:__imp_EventWriteTransfer
0x1800e337d  jmp     loc_1800E3106
```
