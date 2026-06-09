# CMFApi::CreateHWEncoderByLuid(unsigned __int64,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,ushort * &)

- ea: `0x1800da1b0`
- end: `0x1800da74c`
- name: `?CreateHWEncoderByLuid@CMFApi@@QEAAJ_KPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAPEAUIMFTransform@@AEAPEAG@Z`
- size: `1436`
- prototype: `int(CMFApi *__hidden this, unsigned __int64, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, struct IMFTransform **, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800908f0`
- `0x1800e2e50`
- `0x1800e3390`
- `0x1800e3850`

## callees

- `0x1800015f0`
- `0x180009628`
- `0x180032f60`
- `0x180033da0`
- `0x1800da1b0`
- `0x1800db510`
- `0x1800dc8e0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da38a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da4c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da38a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da4c4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800da322`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800da741`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800da322`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800da741`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800da51f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800da51f`

## string_xrefs

- `0x1800da26e`: `onecoreuap\termsrv\rdp\win\codecs\common\cmfapi.cpp`
- `0x1800da41f`: `onecoreuap\termsrv\rdp\win\codecs\common\cmfapi.cpp`
- `0x1800da243`: `CreateHWEncoderByLuid`
- `0x1800da40c`: `CreateHWEncoderByLuid`

## pseudocode

```c
__int64 __fastcall CMFApi::CreateHWEncoderByLuid(
        CMFApi *this,
        unsigned __int64 a2,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a3,
        struct IMFTransform **a4,
        unsigned __int16 **a5)
{
  unsigned __int64 v7; // r15
  int v8; // esi
  unsigned int i; // ebx
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v14; // ebx
  __int64 v15; // r14
  unsigned int ActivityIdPrefix; // eax
  int v17; // ecx
  int v18; // r9d
  const wchar_t *v19; // rax
  const wchar_t *v20; // rcx
  bool v21; // zf
  const char *v22; // r13
  __int64 v23; // rax
  unsigned int v24; // eax
  unsigned int v25; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v27; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD EventDescriptor[3]; // [rsp+70h] [rbp-98h] BYREF
  const char *v30; // [rsp+88h] [rbp-80h] BYREF
  __int64 v31; // [rsp+90h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR v32; // [rsp+98h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A8h] [rbp-60h] BYREF
  __int16 *v34; // [rsp+B8h] [rbp-50h]
  int v35; // [rsp+C0h] [rbp-48h]
  int v36; // [rsp+C4h] [rbp-44h]
  const char *v37; // [rsp+C8h] [rbp-40h]
  __int64 v38; // [rsp+D0h] [rbp-38h]
  __int64 *v39; // [rsp+D8h] [rbp-30h]
  __int64 v40; // [rsp+E0h] [rbp-28h]
  const char *v41; // [rsp+E8h] [rbp-20h]
  __int64 v42; // [rsp+F0h] [rbp-18h]
  const char **v43; // [rsp+F8h] [rbp-10h]
  __int64 v44; // [rsp+100h] [rbp-8h]
  const char *v45; // [rsp+108h] [rbp+0h]
  __int64 v46; // [rsp+110h] [rbp+8h]
  const char *v47; // [rsp+118h] [rbp+10h]
  __int64 v48; // [rsp+120h] [rbp+18h]
  _QWORD *v49; // [rsp+128h] [rbp+20h]
  __int64 v50; // [rsp+130h] [rbp+28h]

  v7 = a2;
  EventDescriptor[0] = 0;
  pv = 0;
  v25 = 0;
  if ( !*((_QWORD *)this + 16) )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v30) = 432;
      v47 = "MFT Enum2 not supported in the host device";
      LODWORD(v27) = -2147024809;
      v45 = "CreateHWEncoderByLuid";
      v48 = 43;
      v43 = &v30;
      v46 = 22;
      v41 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\cmfapi.cpp";
      v44 = 4;
      v39 = &v27;
      v37 = "Error condition failed";
      UserData.Ptr = (ULONGLONG)off_1801B76D0;
      v42 = 52;
      v40 = 4;
      v38 = 23;
      EventDescriptor[1] = 0x20B000000LL;
      EventDescriptor[2] = 0;
      UserData.Size = *(unsigned __int16 *)off_1801B76D0;
      v34 = (__int16 *)&byte_1801A9CCF;
      UserData.Reserved = 2;
      v35 = 75;
      v36 = 1;
      v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1801B76E8, (PCEVENT_DESCRIPTOR)&EventDescriptor[1], 0, 0, 8u, &UserData);
    }
    goto LABEL_4;
  }
  if ( !a2 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v26 = 434;
      v30 = "No LUID provided";
      LODWORD(v27) = -2147024809;
      *(_QWORD *)&v32.Id = "CreateHWEncoderByLuid";
      v31 = (__int64)"onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\cmfapi.cpp";
      EventDescriptor[1] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)byte_1801A9B19,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&EventDescriptor[1],
        (__int64)&v27,
        (__int64)&v31,
        (__int64)&v26,
        (__int64)&v32,
        (__int64)&v30);
    }
    goto LABEL_4;
  }
  *(GUID *)&EventDescriptor[1] = MFT_CATEGORY_VIDEO_ENCODER;
  if ( (int)CMFApi::FindEncodersByLuid(
              this,
              (struct _GUID *)&EventDescriptor[1],
              a2,
              (const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *)a4,
              a3,
              (struct IMFActivate ***)&pv,
              &v25) < 0
    || (v14 = 0, !v25) )
  {
LABEL_4:
    v8 = -2147024463;
    goto LABEL_5;
  }
  while ( 1 )
  {
    CoTaskMemFree(*a5);
    *a5 = 0;
    v15 = 8LL * v14;
    v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD *))(**(_QWORD **)((char *)pv + v15) + 264LL))(
           *(_QWORD *)((char *)pv + v15),
           &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
           EventDescriptor);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        &WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids,
        ActivityIdPrefix,
        v8);
    }
    if ( v8 >= 0 )
      break;
    if ( ++v14 >= v25 )
      goto LABEL_4;
  }
  if ( (int)MFGetAttributeString(*(_QWORD *)((char *)pv + v15), &MFT_FRIENDLY_NAME_Attribute, a5) < 0
    && (unsigned int)dword_1801B76C8 > 3 )
  {
    EventDescriptor[1] = "MFGetAttributeString of MFT_FRIENDLY_NAME_Attribute failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v17,
      (unsigned int)&word_1801A9AEE,
      (_DWORD)a3,
      v18,
      (__int64)&EventDescriptor[1]);
  }
  *a4 = (struct IMFTransform *)EventDescriptor[0];
  EventDescriptor[0] = 0;
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    a2 = 0x470000000000LL;
    if ( (qword_1801B76D8 & 0x470000000000LL) != 0 && (qword_1801B76E0 & 0x470000000000LL) == qword_1801B76E0 )
    {
      v19 = *a5;
      v20 = L"Unknown";
      v21 = *a5 == 0;
      EventDescriptor[1] = v7;
      v31 = 0x1000000;
      if ( !v21 )
        v20 = v19;
      v50 = 8;
      v22 = (char *)this + 160;
      v49 = &EventDescriptor[1];
      if ( v20 )
      {
        v23 = -1;
        do
          v21 = v20[++v23] == 0;
        while ( !v21 );
        v24 = 2 * v23 + 2;
      }
      else
      {
        v20 = &WindowName;
        v24 = 2;
      }
      v48 = v24;
      v47 = (const char *)v20;
      v43 = (const char **)"MFAPI";
      v32.Keyword = 0x470000000000LL;
      v41 = "Stack";
      v39 = &v31;
      v45 = v22;
      v37 = "Checkpoint";
      *(_DWORD *)&v32.Level = 11268;
      UserData.Ptr = (ULONGLONG)off_1801B76D0;
      v46 = 16;
      v44 = 6;
      v42 = 6;
      v40 = 8;
      v38 = 11;
      *(_DWORD *)&v32.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_1801B76D0;
      v34 = word_1801A9BD2;
      UserData.Reserved = 2;
      v35 = 155;
      v36 = 1;
      v26 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1801B76E8, &v32, 0, 0, 9u, &UserData);
    }
  }
LABEL_5:
  if ( v25 )
  {
    for ( i = 0; i < v25; ++i )
    {
      v10 = 8LL * i;
      v11 = *(_QWORD *)((char *)pv + v10);
      if ( v11 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int64, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *))(*(_QWORD *)v11 + 16LL))(
          v11,
          a2,
          a3);
        *(_QWORD *)((char *)pv + v10) = 0;
      }
    }
    CoTaskMemFree(pv);
    pv = 0;
  }
  v12 = EventDescriptor[0];
  if ( EventDescriptor[0] )
  {
    EventDescriptor[0] = 0;
    (*(void (__fastcall **)(__int64, unsigned __int64, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *))(*(_QWORD *)v12 + 16LL))(
      v12,
      a2,
      a3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800da1b0  mov     r11, rsp
0x1800da1b3  push    rbp
0x1800da1b4  push    rsi
0x1800da1b5  push    r14
0x1800da1b7  lea     rbp, [r11-78h]
0x1800da1bb  sub     rsp, 160h
0x1800da1c2  mov     rax, cs:__security_cookie
0x1800da1c9  xor     rax, rsp
0x1800da1cc  mov     [rbp+70h+var_40], rax
0x1800da1d0  mov     [r11+8], rbx
0x1800da1d4  xor     r14d, r14d
0x1800da1d7  mov     [r11-20h], rdi
0x1800da1db  mov     rdi, [rbp+70h+arg_20]
0x1800da1e2  mov     [r11-28h], r12
0x1800da1e6  mov     r12, r9
0x1800da1e9  mov     [r11-30h], r13
0x1800da1ed  mov     r13, rcx
0x1800da1f0  mov     [r11-38h], r15
0x1800da1f4  mov     r15, rdx
0x1800da1f7  mov     qword ptr [rsp+170h+EventDescriptor], r14
0x1800da1fc  mov     [rsp+170h+pv], r14
0x1800da201  mov     [rsp+170h+var_120], r14d
0x1800da206  cmp     [rcx+80h], r14
0x1800da20d  jnz     loc_1800DA3DA
0x1800da213  mov     eax, cs:dword_1801B76C8
0x1800da219  cmp     eax, 2
0x1800da21c  jbe     loc_1800DA328
0x1800da222  mov     dword ptr [rbp+70h+var_F0], 1B0h
0x1800da229  lea     rax, aMftEnum2NotSup; "MFT Enum2 not supported in the host dev"...
0x1800da230  mov     [rbp+70h+var_60], rax
0x1800da234  lea     rcx, _TraceLoggingMetadata
0x1800da23b  mov     dword ptr [rsp+170h+var_118], 80070057h
0x1800da243  lea     rax, aCreatehwencode_2; "CreateHWEncoderByLuid"
0x1800da24a  mov     [rbp+70h+var_70], rax
0x1800da24e  lea     rdx, [rsp+170h+EventDescriptor+8]; EventDescriptor
0x1800da253  mov     [rbp+70h+var_58], 2Bh ; '+'
0x1800da25b  lea     rax, [rbp+70h+var_F0]
0x1800da25f  mov     [rbp+70h+var_80], rax
0x1800da263  xor     r9d, r9d; RelatedActivityId
0x1800da266  mov     [rbp+70h+var_68], 16h
0x1800da26e  lea     rax, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800da275  mov     [rbp+70h+var_90], rax
0x1800da279  xor     r8d, r8d; ActivityId
0x1800da27c  mov     [rbp+70h+var_78], 4
0x1800da284  lea     rax, [rsp+170h+var_118]
0x1800da289  mov     [rbp+70h+var_A0], rax
0x1800da28d  lea     rax, aErrorCondition; "Error condition failed"
0x1800da294  mov     [rbp+70h+var_B0], rax
0x1800da298  movzx   eax, cs:word_1801A9CC5
0x1800da29f  mov     dword ptr [rsp+170h+EventDescriptor+0Ch], eax
0x1800da2a3  mov     rax, cs:off_1801B76D0
0x1800da2aa  mov     [rbp+70h+var_D0.Ptr], rax
0x1800da2ae  mov     [rbp+70h+var_88], 34h ; '4'
0x1800da2b6  mov     [rbp+70h+var_98], 4
0x1800da2be  mov     [rbp+70h+var_A8], 17h
0x1800da2c6  mov     dword ptr [rsp+170h+EventDescriptor+8], 0B000000h
0x1800da2ce  mov     qword ptr [rsp+170h+EventDescriptor+10h], r14
0x1800da2d3  movzx   eax, word ptr [rax]
0x1800da2d6  mov     [rbp+70h+var_D0.Size], eax
0x1800da2d9  lea     rax, byte_1801A9CCF
0x1800da2e0  mov     [rbp+70h+var_C0], rax
0x1800da2e4  lea     rax, _TraceLoggingMetadataEnd
0x1800da2eb  sub     eax, ecx
0x1800da2ed  mov     dword ptr [rbp+70h+var_D0.0Ch], 2
0x1800da2f4  mov     [rbp+70h+var_B8], 4Bh ; 'K'
0x1800da2fb  mov     [rbp+70h+var_B4], 1
0x1800da302  mov     [rsp+170h+var_11C], eax
0x1800da306  mov     eax, [rsp+170h+var_11C]
0x1800da30a  mov     rcx, cs:qword_1801B76E8; RegHandle
0x1800da311  lea     rax, [rbp+70h+var_D0]
0x1800da315  mov     [rsp+170h+UserData], rax; UserData
0x1800da31a  mov     [rsp+170h+UserDataCount], 8; UserDataCount
0x1800da322  call    cs:__imp_EventWriteTransfer
0x1800da328  mov     esi, 800701B1h
0x1800da32d  mov     eax, [rsp+170h+var_120]
0x1800da331  mov     r15, [rsp+170h+var_30]
0x1800da339  mov     r13, [rsp+170h+var_28]
0x1800da341  mov     r12, [rsp+170h+var_20]
0x1800da349  test    eax, eax
0x1800da34b  jz      short loc_1800DA395
0x1800da34d  mov     ebx, r14d
0x1800da350  mov     eax, ebx
0x1800da352  lea     rdi, ds:0[rax*8]
0x1800da35a  mov     rax, [rsp+170h+pv]
0x1800da35f  mov     rcx, [rdi+rax]
0x1800da363  test    rcx, rcx
0x1800da366  jz      short loc_1800DA37D
0x1800da368  mov     rax, [rcx]
0x1800da36b  mov     rax, [rax+10h]
0x1800da36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da374  mov     rax, [rsp+170h+pv]
0x1800da379  mov     [rdi+rax], r14
0x1800da37d  inc     ebx
0x1800da37f  cmp     ebx, [rsp+170h+var_120]
0x1800da383  jb      short loc_1800DA350
0x1800da385  mov     rcx, [rsp+170h+pv]; pv
0x1800da38a  call    cs:__imp_CoTaskMemFree
0x1800da390  mov     [rsp+170h+pv], r14
0x1800da395  mov     rcx, qword ptr [rsp+170h+EventDescriptor]
0x1800da39a  mov     rdi, [rsp+158h]
0x1800da3a2  mov     rbx, [rsp+170h+arg_0]
0x1800da3aa  test    rcx, rcx
0x1800da3ad  jz      short loc_1800DA3C0
0x1800da3af  mov     qword ptr [rsp+170h+EventDescriptor], r14
0x1800da3b4  mov     rax, [rcx]
0x1800da3b7  mov     rax, [rax+10h]
0x1800da3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da3c0  mov     eax, esi
0x1800da3c2  mov     rcx, [rbp+70h+var_40]
0x1800da3c6  xor     rcx, rsp; StackCookie
0x1800da3c9  call    __security_check_cookie
0x1800da3ce  add     rsp, 160h
0x1800da3d5  pop     r14
0x1800da3d7  pop     rsi
0x1800da3d8  pop     rbp
0x1800da3d9  retn
0x1800da3da  test    r15, r15
0x1800da3dd  jnz     loc_1800DA479
0x1800da3e3  mov     eax, cs:dword_1801B76C8
0x1800da3e9  cmp     eax, 2
0x1800da3ec  jbe     loc_1800DA328
0x1800da3f2  lea     rax, aNoLuidProvided; "No LUID provided"
0x1800da3f9  mov     [rsp+170h+var_11C], 1B2h
0x1800da401  mov     [rbp+70h+var_F0], rax
0x1800da405  lea     rdx, byte_1801A9B19
0x1800da40c  lea     rax, aCreatehwencode_2; "CreateHWEncoderByLuid"
0x1800da413  mov     dword ptr [rsp+170h+var_118], 80070057h
0x1800da41b  mov     qword ptr [rbp+70h+var_E0.Id], rax
0x1800da41f  lea     rax, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800da426  mov     [rbp+70h+var_E8], rax
0x1800da42a  lea     rax, aErrorCondition; "Error condition failed"
0x1800da431  mov     qword ptr [rsp+170h+EventDescriptor+8], rax
0x1800da436  lea     rax, [rbp+70h+var_F0]
0x1800da43a  mov     qword ptr [rsp+170h+var_128], rax
0x1800da43f  lea     rax, [rbp+70h+var_E0]
0x1800da443  mov     [rsp+170h+var_130], rax
0x1800da448  lea     rax, [rsp+170h+var_11C]
0x1800da44d  mov     [rsp+170h+var_138], rax
0x1800da452  lea     rax, [rbp+70h+var_E8]
0x1800da456  mov     [rsp+170h+var_140], rax
0x1800da45b  lea     rax, [rsp+170h+var_118]
0x1800da460  mov     [rsp+170h+UserData], rax
0x1800da465  lea     rax, [rsp+170h+EventDescriptor+8]
0x1800da46a  mov     qword ptr [rsp+170h+UserDataCount], rax
0x1800da46f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800da474  jmp     loc_1800DA328
0x1800da479  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1800da480  lea     rax, [rsp+170h+var_120]
0x1800da485  mov     [rsp+170h+var_140], rax; unsigned int *
0x1800da48a  lea     rdx, [rsp+170h+EventDescriptor+8]; struct _GUID *
0x1800da48f  lea     rax, [rsp+170h+pv]
0x1800da494  movaps  xmmword ptr [rsp+170h+EventDescriptor+8], xmm0
0x1800da499  mov     [rsp+170h+UserData], rax; struct IMFActivate ***
0x1800da49e  mov     qword ptr [rsp+170h+UserDataCount], r8; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x1800da4a3  mov     r8, r15; unsigned __int64
0x1800da4a6  call    ?FindEncodersByLuid@CMFApi@@QEAAJU_GUID@@_KPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@2PEAPEAPEAUIMFActivate@@PEAI@Z; CMFApi::FindEncodersByLuid(_GUID,unsigned __int64,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)
0x1800da4ab  test    eax, eax
0x1800da4ad  js      loc_1800DA328
0x1800da4b3  mov     ebx, r14d
0x1800da4b6  cmp     [rsp+170h+var_120], r14d
0x1800da4bb  jbe     loc_1800DA328
0x1800da4c1  mov     rcx, [rdi]; pv
0x1800da4c4  call    cs:__imp_CoTaskMemFree
0x1800da4ca  mov     [rdi], r14
0x1800da4cd  lea     r8, [rsp+170h+EventDescriptor]
0x1800da4d2  mov     eax, ebx
0x1800da4d4  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x1800da4db  lea     r14, ds:0[rax*8]
0x1800da4e3  mov     rax, [rsp+170h+pv]
0x1800da4e8  mov     rcx, [r14+rax]
0x1800da4ec  mov     rax, [rcx]
0x1800da4ef  mov     rax, [rax+108h]
0x1800da4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da4fb  mov     esi, eax
0x1800da4fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da504  lea     rax, WPP_GLOBAL_Control
0x1800da50b  cmp     rcx, rax
0x1800da50e  jz      short loc_1800DA548
0x1800da510  test    dword ptr [rcx+1Ch], 100h
0x1800da517  jz      short loc_1800DA548
0x1800da519  cmp     byte ptr [rcx+19h], 5
0x1800da51d  jb      short loc_1800DA548
0x1800da51f  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800da525  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da52c  lea     r8, WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids
0x1800da533  mov     edx, 1Ah
0x1800da538  mov     [rsp+170h+UserDataCount], esi
0x1800da53c  mov     r9d, eax
0x1800da53f  mov     rcx, [rcx+10h]
0x1800da543  call    WPP_SF_Dd
0x1800da548  test    esi, esi
0x1800da54a  jns     short loc_1800DA563
0x1800da54c  inc     ebx
0x1800da54e  mov     r14d, 0
0x1800da554  cmp     ebx, [rsp+170h+var_120]
0x1800da558  jb      loc_1800DA4C1
0x1800da55e  jmp     loc_1800DA328
0x1800da563  mov     rcx, [rsp+170h+pv]
0x1800da568  lea     rdx, MFT_FRIENDLY_NAME_Attribute
0x1800da56f  mov     r8, rdi
0x1800da572  mov     rcx, [r14+rcx]
0x1800da576  call    MFGetAttributeString
0x1800da57b  test    eax, eax
0x1800da57d  jns     short loc_1800DA5AC
0x1800da57f  mov     eax, cs:dword_1801B76C8
0x1800da585  cmp     eax, 3
0x1800da588  jbe     short loc_1800DA5AC
0x1800da58a  lea     rax, aMfgetattribute_0; "MFGetAttributeString of MFT_FRIENDLY_NA"...
0x1800da591  mov     qword ptr [rsp+170h+EventDescriptor+8], rax
0x1800da596  lea     rdx, word_1801A9AEE
0x1800da59d  lea     rax, [rsp+170h+EventDescriptor+8]
0x1800da5a2  mov     qword ptr [rsp+170h+UserDataCount], rax
0x1800da5a7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800da5ac  mov     rax, qword ptr [rsp+170h+EventDescriptor]
0x1800da5b1  xor     r14d, r14d
0x1800da5b4  mov     [r12], rax
0x1800da5b8  mov     eax, cs:dword_1801B76C8
0x1800da5be  mov     qword ptr [rsp+170h+EventDescriptor], r14
0x1800da5c3  cmp     eax, 4
0x1800da5c6  jbe     loc_1800DA32D
0x1800da5cc  mov     rcx, cs:qword_1801B76E0
0x1800da5d3  mov     rdx, 470000000000h
0x1800da5dd  mov     rax, cs:qword_1801B76D8
0x1800da5e4  test    rdx, rax
0x1800da5e7  jz      loc_1800DA32D
0x1800da5ed  mov     rax, rcx
0x1800da5f0  and     rax, rdx
0x1800da5f3  cmp     rax, rcx
0x1800da5f6  jnz     loc_1800DA32D
0x1800da5fc  mov     rax, [rdi]
0x1800da5ff  lea     rcx, aUnknown_0; "Unknown"
0x1800da606  test    rax, rax
0x1800da609  mov     qword ptr [rsp+170h+EventDescriptor+8], r15
0x1800da60e  mov     [rbp+70h+var_E8], 1000000h
0x1800da616  cmovnz  rcx, rax
0x1800da61a  mov     [rbp+70h+var_48], 8
0x1800da622  add     r13, 0A0h
0x1800da629  lea     rax, [rsp+170h+EventDescriptor+8]
0x1800da62e  mov     [rbp+70h+var_50], rax
0x1800da632  test    rcx, rcx
0x1800da635  jz      short loc_1800DA655
0x1800da637  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800da63e  xchg    ax, ax
0x1800da640  cmp     [rcx+rax*2+2], r14w
0x1800da646  lea     rax, [rax+1]
0x1800da64a  jnz     short loc_1800DA640
0x1800da64c  lea     eax, ds:2[rax*2]
0x1800da653  jmp     short loc_1800DA661
0x1800da655  lea     rcx, WindowName
0x1800da65c  mov     eax, 2
0x1800da661  mov     dword ptr [rbp+70h+var_58], eax
0x1800da664  xor     r9d, r9d; RelatedActivityId
0x1800da667  mov     [rbp+70h+var_60], rcx
0x1800da66b  lea     rax, aMfapi; "MFAPI"
0x1800da672  mov     [rbp+70h+var_80], rax
0x1800da676  lea     rcx, _TraceLoggingMetadata
0x1800da67d  mov     [rbp+70h+var_E0.Keyword], rdx
0x1800da681  lea     rax, aStack; "Stack"
0x1800da688  mov     [rbp+70h+var_90], rax
0x1800da68c  lea     rdx, [rbp+70h+var_E0]; EventDescriptor
0x1800da690  mov     dword ptr [rbp+70h+var_58+4], r14d
0x1800da694  lea     rax, [rbp+70h+var_E8]
0x1800da698  mov     [rbp+70h+var_A0], rax
0x1800da69c  xor     r8d, r8d; ActivityId
0x1800da69f  lea     rax, aCheckpoint; "Checkpoint"
0x1800da6a6  mov     [rbp+70h+var_70], r13
0x1800da6aa  mov     [rbp+70h+var_B0], rax
0x1800da6ae  movzx   eax, cs:word_1801A9BC8
0x1800da6b5  mov     dword ptr [rbp+70h+var_E0.Level], eax
0x1800da6b8  mov     rax, cs:off_1801B76D0
0x1800da6bf  mov     [rbp+70h+var_D0.Ptr], rax
0x1800da6c3  mov     [rbp+70h+var_68], 10h
0x1800da6cb  mov     [rbp+70h+var_78], 6
0x1800da6d3  mov     [rbp+70h+var_88], 6
0x1800da6db  mov     [rbp+70h+var_98], 8
0x1800da6e3  mov     [rbp+70h+var_A8], 0Bh
0x1800da6eb  mov     dword ptr [rbp+70h+var_E0.Id], 0B000000h
0x1800da6f2  movzx   eax, word ptr [rax]
0x1800da6f5  mov     [rbp+70h+var_D0.Size], eax
0x1800da6f8  lea     rax, word_1801A9BD2
0x1800da6ff  mov     [rbp+70h+var_C0], rax
0x1800da703  lea     rax, _TraceLoggingMetadataEnd
0x1800da70a  sub     eax, ecx
0x1800da70c  mov     dword ptr [rbp+70h+var_D0.0Ch], 2
0x1800da713  mov     [rbp+70h+var_B8], 9Bh
0x1800da71a  mov     [rbp+70h+var_B4], 1
0x1800da721  mov     [rsp+170h+var_11C], eax
0x1800da725  mov     eax, [rsp+170h+var_11C]
0x1800da729  mov     rcx, cs:qword_1801B76E8; RegHandle
0x1800da730  lea     rax, [rbp+70h+var_D0]
0x1800da734  mov     [rsp+170h+UserData], rax; UserData
0x1800da739  mov     [rsp+170h+UserDataCount], 9; UserDataCount
0x1800da741  call    cs:__imp_EventWriteTransfer
0x1800da747  jmp     loc_1800DA32D
```
