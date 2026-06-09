# CMFApi::CreateHWEncoderByPreferredVendor(PreferredHwVendor,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *,ushort * &)

- ea: `0x1800da760`
- end: `0x1800db03c`
- name: `?CreateHWEncoderByPreferredVendor@CMFApi@@QEAAJW4PreferredHwVendor@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAPEAUIMFTransform@@AEAPEAG@Z`
- size: `2268`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800908f0`

## callees

- `0x1800015f0`
- `0x180009628`
- `0x180032f60`
- `0x180033da0`
- `0x1800b4db0`
- `0x1800da760`
- `0x1800dc8e0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da9fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dab7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800daf88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dafea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da9fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dab7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800daf88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dafea`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800da8de`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800da8de`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800daa58`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dab4c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800daf4a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800daa58`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800dab4c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800daf4a`

## string_xrefs

- `0x1800da82f`: `onecoreuap\termsrv\rdp\win\codecs\common\cmfapi.cpp`
- `0x1800da969`: `onecoreuap\termsrv\rdp\win\codecs\common\cmfapi.cpp`
- `0x1800da804`: `CreateHWEncoderByPreferredVendor`
- `0x1800da955`: `CreateHWEncoderByPreferredVendor`
- `0x1800daed1`: `GetGUID for CLSID failed`
- `0x1800dac9a`: `VEN_QCOM`

## pseudocode

```c
__int64 __fastcall CMFApi::CreateHWEncoderByPreferredVendor(__int64 a1, int a2, __int64 a3, __int64 a4, LPVOID *a5)
{
  LPVOID *v5; // rdi
  unsigned int v6; // r12d
  __int64 v8; // rbx
  int v9; // r14d
  __int64 (__fastcall *v10)(GUID *, __int64, _QWORD, __int64, LPVOID *, unsigned int *); // rax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // esi
  unsigned int v15; // r13d
  void *v16; // rcx
  __int64 v17; // rdi
  unsigned int ActivityIdPrefix; // eax
  void *v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int16 v22; // ax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rdi
  __int64 v32; // rcx
  int v33; // r15d
  LPVOID *v34; // r14
  __int64 v35; // rbx
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  unsigned int v45; // eax
  unsigned int i; // edi
  __int64 v47; // rsi
  __int64 v48; // rcx
  unsigned int v50; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID *v52; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v53; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v54[2]; // [rsp+70h] [rbp-90h] BYREF
  GUID v55; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  const char *v57; // [rsp+98h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A0h] [rbp-60h] BYREF
  GUID v59; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  void *v61; // [rsp+D0h] [rbp-30h]
  int v62; // [rsp+D8h] [rbp-28h]
  int v63; // [rsp+DCh] [rbp-24h]
  const char *v64; // [rsp+E0h] [rbp-20h]
  __int64 v65; // [rsp+E8h] [rbp-18h]
  LPVOID **v66; // [rsp+F0h] [rbp-10h]
  __int64 v67; // [rsp+F8h] [rbp-8h]
  const char *v68; // [rsp+100h] [rbp+0h]
  __int64 v69; // [rsp+108h] [rbp+8h]
  _QWORD *v70; // [rsp+110h] [rbp+10h]
  __int64 v71; // [rsp+118h] [rbp+18h]
  const char *v72; // [rsp+120h] [rbp+20h]
  __int64 v73; // [rsp+128h] [rbp+28h]
  const char *v74; // [rsp+130h] [rbp+30h]
  __int64 v75; // [rsp+138h] [rbp+38h]

  v5 = a5;
  v6 = 0;
  *(_QWORD *)&EventDescriptor.Id = a4;
  v8 = 0;
  v57 = (const char *)a1;
  v52 = a5;
  pv = 0;
  v53 = 0;
  v50 = 0;
  v59 = GUID_00000000_0000_0000_0000_000000000000;
  if ( a3 )
  {
    v10 = *(__int64 (__fastcall **)(GUID *, __int64, _QWORD, __int64, LPVOID *, unsigned int *))(a1 + 120);
    v55 = MFT_CATEGORY_VIDEO_ENCODER;
    v11 = v10(&v55, 87, 0, a3, &v53, &v50);
    if ( v11 >= 0 )
    {
      v14 = 0;
      v15 = 0;
      LODWORD(v54[0]) = 0;
      v9 = -2147024463;
      if ( v50 )
      {
        while ( 1 )
        {
          v16 = *v5;
          v51 = 0;
          CoTaskMemFree(v16);
          *v5 = 0;
          v17 = 8LL * v6;
          v9 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**(_QWORD **)((char *)v53 + v17) + 264LL))(
                 *(_QWORD *)((char *)v53 + v17),
                 &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
                 &v51);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              &WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids,
              ActivityIdPrefix,
              v9);
          }
          if ( v9 >= 0 )
          {
            v9 = MFGetAttributeString(*(_QWORD *)((char *)v53 + v17), MFT_ENUM_HARDWARE_VENDOR_ID_Attribute, &pv);
            if ( v9 >= 0 )
            {
              v19 = pv;
              switch ( a2 )
              {
                case 1:
                  v20 = -1;
                  do
                  {
                    if ( *((_WORD *)pv + v20 + 1) != aVen8086[v20 + 1] )
                      break;
                    v20 += 2;
                    if ( v20 == 9 )
                      goto LABEL_24;
                  }
                  while ( *((_WORD *)pv + v20) == aVen8086[v20] );
                  break;
                case 2:
                  v21 = 0;
                  while ( 1 )
                  {
                    v22 = *((_WORD *)pv + v21++);
                    if ( v22 != SubStr[v21 - 1] )
                      break;
                    if ( v21 == 4 )
                      goto LABEL_24;
                  }
                  v24 = -1;
                  do
                  {
                    if ( *((_WORD *)pv + v24 + 1) != aVen1002[v24 + 1] )
                      break;
                    v24 += 2;
                    if ( v24 == 9 )
                      goto LABEL_24;
                  }
                  while ( *((_WORD *)pv + v24) == aVen1002[v24] );
                  break;
                case 3:
                  v25 = -1;
                  do
                  {
                    if ( *((_WORD *)pv + v25 + 1) != aVenNvda[v25 + 1] )
                      break;
                    v25 += 2;
                    if ( v25 == 9 )
                      goto LABEL_24;
                  }
                  while ( *((_WORD *)pv + v25) == aVenNvda[v25] );
                  v26 = -1;
                  do
                  {
                    if ( *((_WORD *)pv + v26 + 1) != aVen10de[v26 + 1] )
                      break;
                    v26 += 2;
                    if ( v26 == 9 )
                      goto LABEL_24;
                  }
                  while ( *((_WORD *)pv + v26) == aVen10de[v26] );
                  break;
                case 4:
                  v27 = -1;
                  do
                  {
                    if ( *((_WORD *)pv + v27 + 1) != aVenQcom[v27 + 1] )
                      break;
                    v27 += 2;
                    if ( v27 == 9 )
                      goto LABEL_24;
                  }
                  while ( *((_WORD *)pv + v27) == aVenQcom[v27] );
                  v28 = -1;
                  do
                  {
                    if ( *((_WORD *)pv + v28 + 1) != aVen4d4f4351[v28 + 1] )
                      break;
                    v28 += 2;
                    if ( v28 == 13 )
                      goto LABEL_24;
                  }
                  while ( *((_WORD *)pv + v28) == aVen4d4f4351[v28] );
                  break;
                case 5:
                  v29 = -1;
                  while ( *((_WORD *)pv + v29 + 1) == aVen1414[v29 + 1] )
                  {
                    v29 += 2;
                    if ( v29 == 9 )
                    {
LABEL_24:
                      ++v14;
                      goto LABEL_25;
                    }
                    if ( *((_WORD *)pv + v29) != aVen1414[v29] )
                      goto LABEL_25;
                  }
                  break;
              }
LABEL_25:
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v23 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
                WPP_SF_DdS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  (unsigned int)&WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids,
                  v23,
                  a2,
                  (__int64)v19);
              }
              CoTaskMemFree(v19);
              if ( v14 == 1 )
              {
                if ( v51 != v8 )
                {
                  if ( v8 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
                  v8 = v51;
                  if ( v51 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
                }
                v15 = v6;
              }
              else if ( v14 > 1 )
              {
                v32 = v51;
                v9 = -2147467259;
                if ( v51 )
                {
                  v51 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                  v5 = v52;
                  v33 = 0;
                }
                else
                {
                  v5 = v52;
                  v33 = v54[0];
                }
                goto LABEL_88;
              }
            }
          }
          v30 = v51;
          v31 = v8;
          if ( v51 )
          {
            v51 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          if ( ++v6 >= v50 )
            break;
          v5 = v52;
        }
        if ( v14 == 1 )
        {
          v34 = v52;
          v35 = 8LL * v15;
          if ( (int)MFGetAttributeString(*(_QWORD *)((char *)v53 + v35), &MFT_FRIENDLY_NAME_Attribute, v52) < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 > 3 )
            {
              *(_QWORD *)&v55.Data1 = "MFGetAttributeString of MFT_FRIENDLY_NAME_Attribute failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v36,
                (unsigned int)byte_1801A9C99,
                v37,
                v38,
                (__int64)&v55);
            }
            if ( (*(int (__fastcall **)(_QWORD, const GUID *, GUID *))(**(_QWORD **)((char *)v53 + v35) + 80LL))(
                   *(_QWORD *)((char *)v53 + v35),
                   &MFT_TRANSFORM_CLSID_Attribute,
                   &v59) < 0 )
            {
              if ( (unsigned int)dword_1801B76C8 > 3 )
              {
                *(_QWORD *)&v55.Data1 = "GetGUID for CLSID failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  v39,
                  (unsigned int)byte_1801A9D1B,
                  v40,
                  v41,
                  (__int64)&v55);
              }
            }
            else
            {
              v55 = v59;
              if ( (*((int (__fastcall **)(GUID *, LPVOID *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v57 + 17))(
                     &v55,
                     v34,
                     0,
                     0,
                     0,
                     0,
                     0) < 0
                && (unsigned int)dword_1801B76C8 > 3 )
              {
                *(_QWORD *)&v55.Data1 = "_pfnMFTGetInfo failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  v42,
                  (unsigned int)&word_1801A9C6E,
                  v43,
                  v44,
                  (__int64)&v55);
              }
            }
          }
          v8 = 0;
          v33 = 1;
          v9 = 0;
          **(_QWORD **)&EventDescriptor.Id = v31;
          v5 = v52;
        }
        else
        {
          v5 = v52;
          v33 = v54[0];
        }
      }
      else
      {
        v33 = 0;
      }
LABEL_88:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v45 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control);
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids, v45, v14);
      }
      if ( v33 )
      {
        if ( v9 >= 0 )
          goto LABEL_96;
        goto LABEL_95;
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v52) = v11;
      pv = "_pfnMFTEnumEx failed";
      LODWORD(v51) = 298;
      v54[0] = "CreateHWEncoderByPreferredVendor";
      v57 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\cmfapi.cpp";
      *(_QWORD *)&v55.Data1 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)&word_1801A9D46,
        v12,
        v13,
        (__int64)&v55,
        (__int64)&v52,
        (__int64)&v57,
        (__int64)&v51,
        (__int64)v54,
        (__int64)&pv);
      v9 = -2147024463;
      goto LABEL_95;
    }
LABEL_93:
    v9 = -2147024463;
    goto LABEL_95;
  }
  if ( (unsigned int)dword_1801B76C8 <= 2 )
    goto LABEL_93;
  LODWORD(v54[0]) = 295;
  v74 = "pOutputType - NULL pointer";
  LODWORD(v52) = -2147467261;
  v72 = "CreateHWEncoderByPreferredVendor";
  v75 = 27;
  v70 = v54;
  v73 = 33;
  v68 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\cmfapi.cpp";
  v66 = &v52;
  v64 = "Error condition failed";
  *(_DWORD *)&EventDescriptor.Level = 2;
  UserData.Ptr = (ULONGLONG)off_1801B76D0;
  v71 = 4;
  v69 = 52;
  v67 = 4;
  v65 = 23;
  *(_DWORD *)&EventDescriptor.Id = 184549376;
  EventDescriptor.Keyword = 0;
  UserData.Size = *(unsigned __int16 *)off_1801B76D0;
  v61 = &unk_1801A9DA8;
  v63 = 1;
  UserData.Reserved = 2;
  v62 = 75;
  LODWORD(v51) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 8u, &UserData);
  v9 = -2147024463;
LABEL_95:
  CoTaskMemFree(*v5);
  *v5 = 0;
LABEL_96:
  if ( v50 )
  {
    for ( i = 0; i < v50; ++i )
    {
      v47 = 8LL * i;
      v48 = *(_QWORD *)((char *)v53 + v47);
      if ( v48 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        *(_QWORD *)((char *)v53 + v47) = 0;
      }
    }
    CoTaskMemFree(v53);
    v53 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800da760  mov     r11, rsp
0x1800da763  push    rbp
0x1800da764  push    rbx
0x1800da765  push    r14
0x1800da767  lea     rbp, [rsp-70h]
0x1800da76c  sub     rsp, 170h
0x1800da773  mov     rax, cs:__security_cookie
0x1800da77a  xor     rax, rsp
0x1800da77d  mov     [rbp+80h+var_40], rax
0x1800da781  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800da788  mov     [r11+10h], rsi
0x1800da78c  mov     rax, rcx
0x1800da78f  mov     [r11-20h], rdi
0x1800da793  mov     rdi, [rbp+80h+arg_20]
0x1800da79a  mov     [r11-28h], r12
0x1800da79e  xor     r12d, r12d
0x1800da7a1  mov     [r11-38h], r15
0x1800da7a5  mov     r15d, edx
0x1800da7a8  mov     qword ptr [rbp+80h+EventDescriptor.Id], r9
0x1800da7ac  mov     ebx, r12d
0x1800da7af  mov     [rbp+80h+var_E8], rcx
0x1800da7b3  mov     [rsp+180h+var_120], rdi
0x1800da7b8  mov     [rbp+80h+pv], r12
0x1800da7bc  mov     [rsp+180h+var_118], r12
0x1800da7c1  mov     [rsp+180h+var_130], r12d
0x1800da7c6  movaps  [rbp+80h+var_D0], xmm0
0x1800da7ca  test    r8, r8
0x1800da7cd  jnz     loc_1800DA8EF
0x1800da7d3  mov     eax, cs:dword_1801B76C8
0x1800da7d9  cmp     eax, 2
0x1800da7dc  jbe     loc_1800DAF78
0x1800da7e2  mov     dword ptr [rsp+180h+var_110], 127h
0x1800da7ea  lea     rax, aPoutputtypeNul; "pOutputType - NULL pointer"
0x1800da7f1  mov     [rbp+80h+var_50], rax
0x1800da7f5  lea     rcx, _TraceLoggingMetadata
0x1800da7fc  mov     dword ptr [rsp+180h+var_120], 80004003h
0x1800da804  lea     rax, aCreatehwencode_3; "CreateHWEncoderByPreferredVendor"
0x1800da80b  mov     [rbp+80h+var_60], rax
0x1800da80f  lea     rdx, [rbp+80h+EventDescriptor]; EventDescriptor
0x1800da813  mov     [rbp+80h+var_48], 1Bh
0x1800da81b  lea     rax, [rsp+180h+var_110]
0x1800da820  mov     [rbp+80h+var_70], rax
0x1800da824  xor     r9d, r9d; RelatedActivityId
0x1800da827  mov     [rbp+80h+var_58], 21h ; '!'
0x1800da82f  lea     rax, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800da836  mov     [rbp+80h+var_80], rax
0x1800da83a  lea     rax, [rsp+180h+var_120]
0x1800da83f  mov     [rbp+80h+var_90], rax
0x1800da843  lea     rax, aErrorCondition; "Error condition failed"
0x1800da84a  mov     [rbp+80h+var_A0], rax
0x1800da84e  movzx   eax, cs:word_1801A9D9E
0x1800da855  mov     dword ptr [rbp+80h+EventDescriptor.Level], eax
0x1800da858  mov     rax, cs:off_1801B76D0
0x1800da85f  mov     [rbp+80h+var_C0.Ptr], rax
0x1800da863  mov     [rbp+80h+var_68], 4
0x1800da86b  mov     [rbp+80h+var_78], 34h ; '4'
0x1800da873  mov     [rbp+80h+var_88], 4
0x1800da87b  mov     [rbp+80h+var_98], 17h
0x1800da883  mov     dword ptr [rbp+80h+EventDescriptor.Id], 0B000000h
0x1800da88a  mov     [rbp+80h+EventDescriptor.Keyword], r12
0x1800da88e  movzx   eax, word ptr [rax]
0x1800da891  mov     [rbp+80h+var_C0.Size], eax
0x1800da894  lea     rax, unk_1801A9DA8
0x1800da89b  mov     [rbp+80h+var_B0], rax
0x1800da89f  mov     eax, 1
0x1800da8a4  mov     [rbp+80h+var_A4], eax
0x1800da8a7  lea     rax, _TraceLoggingMetadataEnd
0x1800da8ae  sub     eax, ecx
0x1800da8b0  mov     dword ptr [rbp+80h+var_C0.0Ch], 2
0x1800da8b7  mov     [rbp+80h+var_A8], 4Bh ; 'K'
0x1800da8be  mov     dword ptr [rsp+180h+var_128], eax
0x1800da8c2  mov     eax, dword ptr [rsp+180h+var_128]
0x1800da8c6  mov     rcx, cs:qword_1801B76E8; RegHandle
0x1800da8cd  lea     rax, [rbp+80h+var_C0]
0x1800da8d1  mov     [rsp+180h+UserData], rax; UserData
0x1800da8d6  mov     [rsp+180h+UserDataCount], 8; UserDataCount
0x1800da8de  call    cs:__imp_EventWriteTransfer
0x1800da8e4  mov     r14d, 800701B1h
0x1800da8ea  jmp     loc_1800DAF85
0x1800da8ef  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1800da8f6  mov     rax, [rax+78h]
0x1800da8fa  lea     rcx, [rsp+180h+var_130]
0x1800da8ff  mov     [rsp+180h+UserData], rcx
0x1800da904  mov     r9, r8
0x1800da907  lea     rcx, [rsp+180h+var_118]
0x1800da90c  movaps  [rbp+80h+var_100], xmm0
0x1800da910  mov     qword ptr [rsp+180h+UserDataCount], rcx
0x1800da915  xor     r8d, r8d
0x1800da918  lea     rcx, [rbp+80h+var_100]
0x1800da91c  mov     edx, 57h ; 'W'
0x1800da921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da926  mov     edx, eax
0x1800da928  test    eax, eax
0x1800da92a  jns     loc_1800DA9C8
0x1800da930  mov     ecx, cs:dword_1801B76C8
0x1800da936  cmp     ecx, 2
0x1800da939  jbe     loc_1800DAF78
0x1800da93f  lea     rax, aPfnmftenumexFa; "_pfnMFTEnumEx failed"
0x1800da946  mov     dword ptr [rsp+180h+var_120], edx
0x1800da94a  mov     [rbp+80h+pv], rax
0x1800da94e  lea     rdx, word_1801A9D46
0x1800da955  lea     rax, aCreatehwencode_3; "CreateHWEncoderByPreferredVendor"
0x1800da95c  mov     dword ptr [rsp+180h+var_128], 12Ah
0x1800da964  mov     [rsp+180h+var_110], rax
0x1800da969  lea     rax, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800da970  mov     [rbp+80h+var_E8], rax
0x1800da974  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800da97b  mov     qword ptr [rbp+80h+var_100], rax
0x1800da97f  lea     rax, [rbp+80h+pv]
0x1800da983  mov     [rsp+180h+var_138], rax
0x1800da988  lea     rax, [rsp+180h+var_110]
0x1800da98d  mov     [rsp+180h+var_140], rax
0x1800da992  lea     rax, [rsp+180h+var_128]
0x1800da997  mov     [rsp+180h+var_148], rax
0x1800da99c  lea     rax, [rbp+80h+var_E8]
0x1800da9a0  mov     [rsp+180h+var_150], rax
0x1800da9a5  lea     rax, [rsp+180h+var_120]
0x1800da9aa  mov     [rsp+180h+UserData], rax
0x1800da9af  lea     rax, [rbp+80h+var_100]
0x1800da9b3  mov     qword ptr [rsp+180h+UserDataCount], rax
0x1800da9b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800da9bd  mov     r14d, 800701B1h
0x1800da9c3  jmp     loc_1800DAF85
0x1800da9c8  mov     esi, r12d
0x1800da9cb  mov     [rsp+180h+var_28], r13
0x1800da9d3  mov     r13d, r12d
0x1800da9d6  mov     dword ptr [rsp+180h+var_110], r12d
0x1800da9db  mov     r14d, 800701B1h
0x1800da9e1  cmp     [rsp+180h+var_130], ebx
0x1800da9e5  jbe     loc_1800DAF1D
0x1800da9eb  nop     dword ptr [rax+rax+00h]
0x1800da9f0  mov     rcx, [rdi]; pv
0x1800da9f3  xor     r14d, r14d
0x1800da9f6  mov     [rsp+180h+var_128], r14
0x1800da9fb  call    cs:__imp_CoTaskMemFree
0x1800daa01  mov     [rdi], r14
0x1800daa04  lea     r8, [rsp+180h+var_128]
0x1800daa09  mov     eax, r12d
0x1800daa0c  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x1800daa13  lea     rdi, ds:0[rax*8]
0x1800daa1b  mov     rax, [rsp+180h+var_118]
0x1800daa20  mov     rcx, [rdi+rax]
0x1800daa24  mov     rax, [rcx]
0x1800daa27  mov     rax, [rax+108h]
0x1800daa2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daa33  mov     r14d, eax
0x1800daa36  mov     rax, cs:WPP_GLOBAL_Control
0x1800daa3d  lea     rcx, WPP_GLOBAL_Control
0x1800daa44  cmp     rax, rcx
0x1800daa47  jz      short loc_1800DAA82
0x1800daa49  test    dword ptr [rax+1Ch], 100h
0x1800daa50  jz      short loc_1800DAA82
0x1800daa52  cmp     byte ptr [rax+19h], 5
0x1800daa56  jb      short loc_1800DAA82
0x1800daa58  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800daa5e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daa65  lea     r8, WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids
0x1800daa6c  mov     edx, 17h
0x1800daa71  mov     [rsp+180h+UserDataCount], r14d
0x1800daa76  mov     r9d, eax
0x1800daa79  mov     rcx, [rcx+10h]
0x1800daa7d  call    WPP_SF_Dd
0x1800daa82  test    r14d, r14d
0x1800daa85  js      loc_1800DAD5F
0x1800daa8b  mov     rcx, [rsp+180h+var_118]
0x1800daa90  lea     r8, [rbp+80h+pv]
0x1800daa94  lea     rdx, MFT_ENUM_HARDWARE_VENDOR_ID_Attribute
0x1800daa9b  mov     rcx, [rdi+rcx]
0x1800daa9f  call    MFGetAttributeString
0x1800daaa4  mov     r14d, eax
0x1800daaa7  test    eax, eax
0x1800daaa9  js      loc_1800DAD5F
0x1800daaaf  mov     rdi, [rbp+80h+pv]
0x1800daab3  cmp     r15d, 1
0x1800daab7  jnz     short loc_1800DAAF2
0x1800daab9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800daac0  lea     rdx, aVen8086; "VEN_8086"
0x1800daac7  nop     word ptr [rax+rax+00000000h]
0x1800daad0  movzx   eax, word ptr [rdi+rcx*2+2]
0x1800daad5  cmp     ax, [rdx+rcx*2+2]
0x1800daada  jnz     short loc_1800DAB2A
0x1800daadc  add     rcx, 2
0x1800daae0  cmp     rcx, 9
0x1800daae4  jz      short loc_1800DAB28
0x1800daae6  movzx   eax, word ptr [rdi+rcx*2]
0x1800daaea  cmp     ax, [rdx+rcx*2]
0x1800daaee  jz      short loc_1800DAAD0
0x1800daaf0  jmp     short loc_1800DAB2A
0x1800daaf2  cmp     r15d, 2
0x1800daaf6  jnz     loc_1800DAC0D
0x1800daafc  xor     ecx, ecx
0x1800daafe  lea     rdx, aAmd; "AMD"
0x1800dab05  nop     word ptr [rax+rax+00000000h]
0x1800dab10  movzx   eax, word ptr [rdi+rcx*2]
0x1800dab14  inc     rcx
0x1800dab17  cmp     ax, [rdx+rcx*2-2]
0x1800dab1c  jnz     loc_1800DABC9
0x1800dab22  cmp     rcx, 4
0x1800dab26  jnz     short loc_1800DAB10
0x1800dab28  inc     esi
0x1800dab2a  mov     rax, cs:WPP_GLOBAL_Control
0x1800dab31  lea     rcx, WPP_GLOBAL_Control
0x1800dab38  cmp     rax, rcx
0x1800dab3b  jz      short loc_1800DAB7B
0x1800dab3d  test    dword ptr [rax+1Ch], 100h
0x1800dab44  jz      short loc_1800DAB7B
0x1800dab46  cmp     byte ptr [rax+19h], 4
0x1800dab4a  jb      short loc_1800DAB7B
0x1800dab4c  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800dab52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dab59  lea     r8, WPP_db3a594a455a3ed0b19703917d125bc2_Traceguids
0x1800dab60  mov     edx, 18h
0x1800dab65  mov     [rsp+180h+UserData], rdi
0x1800dab6a  mov     r9d, eax
0x1800dab6d  mov     [rsp+180h+UserDataCount], r15d
0x1800dab72  mov     rcx, [rcx+10h]
0x1800dab76  call    WPP_SF_DdS
0x1800dab7b  mov     rcx, rdi; pv
0x1800dab7e  call    cs:__imp_CoTaskMemFree
0x1800dab84  cmp     esi, 1
0x1800dab87  jnz     loc_1800DAD5D
0x1800dab8d  cmp     [rsp+180h+var_128], rbx
0x1800dab92  jz      short loc_1800DABC1
0x1800dab94  test    rbx, rbx
0x1800dab97  jz      short loc_1800DABA8
0x1800dab99  mov     rax, [rbx]
0x1800dab9c  mov     rcx, rbx
0x1800dab9f  mov     rax, [rax+10h]
0x1800daba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daba8  mov     rbx, [rsp+180h+var_128]
0x1800dabad  test    rbx, rbx
0x1800dabb0  jz      short loc_1800DABC1
0x1800dabb2  mov     rax, [rbx]
0x1800dabb5  mov     rcx, rbx
0x1800dabb8  mov     rax, [rax+8]
0x1800dabbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dabc1  mov     r13d, r12d
0x1800dabc4  jmp     loc_1800DAD5F
0x1800dabc9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dabd0  lea     rdx, aVen1002; "VEN_1002"
0x1800dabd7  nop     word ptr [rax+rax+00000000h]
0x1800dabe0  movzx   eax, word ptr [rdi+rcx*2+2]
0x1800dabe5  cmp     ax, [rdx+rcx*2+2]
0x1800dabea  jnz     loc_1800DAB2A
0x1800dabf0  add     rcx, 2
0x1800dabf4  cmp     rcx, 9
0x1800dabf8  jz      loc_1800DAB28
0x1800dabfe  movzx   eax, word ptr [rdi+rcx*2]
0x1800dac02  cmp     ax, [rdx+rcx*2]
0x1800dac06  jz      short loc_1800DABE0
0x1800dac08  jmp     loc_1800DAB2A
0x1800dac0d  cmp     r15d, 3
0x1800dac11  jnz     short loc_1800DAC8D
0x1800dac13  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dac1a  lea     rdx, aVenNvda; "VEN_NVDA"
0x1800dac21  movzx   eax, word ptr [rdi+rcx*2+2]
0x1800dac26  cmp     ax, [rdx+rcx*2+2]
0x1800dac2b  jnz     short loc_1800DAC45
0x1800dac2d  add     rcx, 2
0x1800dac31  cmp     rcx, 9
0x1800dac35  jz      loc_1800DAB28
0x1800dac3b  movzx   eax, word ptr [rdi+rcx*2]
0x1800dac3f  cmp     ax, [rdx+rcx*2]
0x1800dac43  jz      short loc_1800DAC21
0x1800dac45  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dac4c  lea     rdx, aVen10de; "VEN_10DE"
0x1800dac53  nop     dword ptr [rax+00h]
0x1800dac57  nop     word ptr [rax+rax+00000000h]
0x1800dac60  movzx   eax, word ptr [rdi+rcx*2+2]
0x1800dac65  cmp     ax, [rdx+rcx*2+2]
0x1800dac6a  jnz     loc_1800DAB2A
0x1800dac70  add     rcx, 2
0x1800dac74  cmp     rcx, 9
0x1800dac78  jz      loc_1800DAB28
0x1800dac7e  movzx   eax, word ptr [rdi+rcx*2]
0x1800dac82  cmp     ax, [rdx+rcx*2]
0x1800dac86  jz      short loc_1800DAC60
0x1800dac88  jmp     loc_1800DAB2A
0x1800dac8d  cmp     r15d, 4
0x1800dac91  jnz     short loc_1800DAD0D
0x1800dac93  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dac9a  lea     rdx, aVenQcom; "VEN_QCOM"
0x1800daca1  movzx   eax, word ptr [rdi+rcx*2+2]
0x1800daca6  cmp     ax, [rdx+rcx*2+2]
0x1800dacab  jnz     short loc_1800DACC5
0x1800dacad  add     rcx, 2
0x1800dacb1  cmp     rcx, 9
0x1800dacb5  jz      loc_1800DAB28
0x1800dacbb  movzx   eax, word ptr [rdi+rcx*2]
0x1800dacbf  cmp     ax, [rdx+rcx*2]
0x1800dacc3  jz      short loc_1800DACA1
0x1800dacc5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800daccc  lea     rdx, aVen4d4f4351; "VEN_4D4F4351"
0x1800dacd3  nop     dword ptr [rax+00h]
0x1800dacd7  nop     word ptr [rax+rax+00000000h]
0x1800dace0  movzx   eax, word ptr [rdi+rcx*2+2]
0x1800dace5  cmp     ax, [rdx+rcx*2+2]
0x1800dacea  jnz     loc_1800DAB2A
0x1800dacf0  add     rcx, 2
0x1800dacf4  cmp     rcx, 0Dh
  ... truncated ...
```
