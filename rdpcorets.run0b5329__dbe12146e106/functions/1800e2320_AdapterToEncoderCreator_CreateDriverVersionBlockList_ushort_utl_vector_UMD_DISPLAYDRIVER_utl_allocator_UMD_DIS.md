# AdapterToEncoderCreator::CreateDriverVersionBlockList(ushort *,utl::vector<UMD_DISPLAYDRIVER,utl::allocator<UMD_DISPLAYDRIVER>> &)

- ea: `0x1800e2320`
- end: `0x1800e2e46`
- name: `?CreateDriverVersionBlockList@AdapterToEncoderCreator@@CAJPEAGAEAV?$vector@UUMD_DISPLAYDRIVER@@V?$allocator@UUMD_DISPLAYDRIVER@@@utl@@@utl@@@Z`
- size: `2854`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800e3c50`

## callees

- `0x1800015f0`
- `0x180003ee0`
- `0x180009628`
- `0x180010960`
- `0x18002e600`
- `0x18003394c`
- `0x180033958`
- `0x180033da0`
- `0x18003417c`
- `0x180034940`
- `0x18003494c`
- `0x180034970`
- `0x180034a70`
- `0x1800598d0`
- `0x1800e1bd0`
- `0x1800e2320`
- `0x18014c328`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2377`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2441`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2377`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e2441`

## string_xrefs

- `0x1800e24e0`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e2755`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e2cea`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e2d84`: `onecoreuap\termsrv\rdp\win\codecs\common\adaptertoencodercreator.cpp`
- `0x1800e2447`: `tempDriverBlockVersions`
- `0x1800e24b1`: `wszDriverVersions copy failed`
- `0x1800e24cc`: `CreateDriverVersionBlockList`
- `0x1800e2745`: `CreateDriverVersionBlockList`
- `0x1800e2cda`: `CreateDriverVersionBlockList`
- `0x1800e2d74`: `CreateDriverVersionBlockList`
- `0x1800e2c24`: `CreateDriverVersionBlockList - driverBlockList`

## pseudocode

```c
__int64 __fastcall AdapterToEncoderCreator::CreateDriverVersionBlockList(wchar_t *Source, const char *a2)
{
  int ActivityIdPrefix; // eax
  __int64 v5; // rdi
  __int64 v6; // r13
  __int64 v7; // rax
  unsigned __int64 v8; // rdi
  wchar_t *v9; // rax
  wchar_t *v10; // r14
  int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // r14
  __int64 v16; // rdi
  wchar_t *v17; // rax
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // rax
  __int64 v23; // rdi
  void *v24; // rax
  __int64 v25; // rbx
  char *p_i; // r15
  char *v27; // rsi
  size_t v28; // r14
  unsigned __int64 v29; // r14
  wchar_t *v30; // rbx
  wchar_t *v31; // rdx
  int v32; // ecx
  int v33; // r8d
  const wchar_t *v34; // r9
  const char *v35; // rax
  char *v36; // rdx
  __int64 v37; // rcx
  wchar_t v38; // ax
  int v39; // eax
  int v40; // ecx
  __int64 v41; // rcx
  wchar_t v42; // ax
  __int64 v43; // rcx
  wchar_t v44; // ax
  __int64 v45; // rcx
  wchar_t v46; // ax
  __int64 v47; // rax
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  int v51; // ecx
  int v52; // r8d
  int v53; // r9d
  char *v54; // rdx
  _OWORD *v55; // rax
  _OWORD *v56; // rcx
  _BYTE *v57; // r12
  unsigned __int64 v58; // rcx
  unsigned __int64 v59; // rax
  __int64 v60; // r15
  char *v61; // rax
  char *v62; // rdi
  char *v63; // rsi
  char *v64; // rbx
  char *v65; // r15
  char *v66; // r12
  __int64 v67; // [rsp+20h] [rbp-E0h]
  __int64 v68; // [rsp+28h] [rbp-D8h]
  __int64 v69; // [rsp+30h] [rbp-D0h]
  int v70; // [rsp+50h] [rbp-B0h] BYREF
  int v71; // [rsp+54h] [rbp-ACh] BYREF
  const char *v72; // [rsp+58h] [rbp-A8h] BYREF
  const char *v73; // [rsp+60h] [rbp-A0h] BYREF
  const char *v74; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v75; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *String; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *i; // [rsp+80h] [rbp-80h] BYREF
  const char *v78; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *Context[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v80; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Buffer[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v82; // [rsp+C0h] [rbp-40h]
  __int128 v83; // [rsp+D0h] [rbp-30h]
  __int128 v84; // [rsp+E0h] [rbp-20h]
  __int128 v85; // [rsp+F0h] [rbp-10h]
  __int128 v86; // [rsp+100h] [rbp+0h]
  __int128 v87; // [rsp+110h] [rbp+10h]
  __int128 v88; // [rsp+120h] [rbp+20h]
  __int128 v89; // [rsp+130h] [rbp+30h]
  __int128 v90; // [rsp+140h] [rbp+40h]
  __int128 v91; // [rsp+150h] [rbp+50h]
  __int128 v92; // [rsp+160h] [rbp+60h]
  __int128 v93; // [rsp+170h] [rbp+70h]

  v74 = a2;
  Context[0] = 0;
  if ( !Source )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(0);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_604b36dd83cf35ab199212a9476a51f1_Traceguids,
        ActivityIdPrefix,
        (__int64)"wszDriverBlockVersions");
    }
    operator delete(0);
    return 2147500035LL;
  }
  LODWORD(v5) = 0;
  v6 = -1;
  *((_QWORD *)a2 + 1) = *(_QWORD *)a2;
  v7 = -1;
  v71 = 0;
  String = 0;
  do
    ++v7;
  while ( Source[v7] );
  if ( !(_DWORD)v7 )
    goto LABEL_90;
  v8 = (unsigned int)(v7 + 1);
  v9 = (wchar_t *)operator new[](saturated_mul(v8, 2u));
  String = v9;
  v10 = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_604b36dd83cf35ab199212a9476a51f1_Traceguids,
        v11,
        (__int64)"tempDriverBlockVersions",
        -2147024882);
    }
    operator delete(0);
    return 2147942414LL;
  }
  if ( wcscpy_s(v9, v8, Source) )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v71 = 186;
      v75 = (wchar_t *)"wszDriverVersions copy failed";
      v70 = -2147467259;
      String = (wchar_t *)"CreateDriverVersionBlockList";
      v74 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
      v73 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)&byte_1801AA56F,
        v13,
        v14,
        (__int64)&v73,
        (__int64)&v70,
        (__int64)&v74,
        (__int64)&v71,
        (__int64)&String,
        (__int64)&v75);
    }
    operator delete(v10);
    return 2147500037LL;
  }
  v15 = -1;
  v16 = -1;
  v17 = o_wcstok_s_0(String, L";", Context);
  for ( i = v17; v17; i = v17 )
  {
    v20 = -1;
    if ( v15 == v16 )
    {
      v21 = (v16 - v6) >> 3;
      v22 = 7 * (v21 >> 2) + 8;
      if ( v22 > 0xFFFFFFFFFFFFFFFLL )
        v22 = 0xFFFFFFFFFFFFFFFLL;
      if ( v21 >= v22
        || (v23 = 8 * v22,
            v24 = operator new(8 * v22, (const struct std::nothrow_t *)&std::nothrow),
            (v25 = (__int64)v24) == 0)
        || v24 == (void *)-1LL )
      {
        LODWORD(v5) = -2147467259;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v71 = 195;
          v73 = "driverVersionStrings.push_back failed";
          v70 = -2147467259;
          v75 = (wchar_t *)"CreateDriverVersionBlockList";
          v74 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
          v72 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v20,
            (unsigned int)byte_1801AA3F9,
            v18,
            v19,
            (__int64)&v72,
            (__int64)&v70,
            (__int64)&v74,
            (__int64)&v71,
            (__int64)&v75,
            (__int64)&v73);
        }
        goto LABEL_90;
      }
      p_i = (char *)&i;
      v27 = (char *)&i - v6;
      v16 = (__int64)v24 + v23;
      v28 = 8 * ((v15 - v6) >> 3);
      memcpy_0(v24, (const void *)v6, v28);
      if ( v6 != -1 )
        operator delete((void *)v6);
      if ( (unsigned __int64)v27 < v28 )
        p_i = &v27[v25];
      v6 = v25;
      *(_QWORD *)(v28 + v25) = *(_QWORD *)p_i;
      v15 = v25 + v28 + 8;
    }
    else
    {
      *(_QWORD *)v15 = v17;
      v15 += 8;
    }
    v17 = o_wcstok_s_0(0, L";", Context);
  }
  v5 = 0;
  v29 = (v15 - v6) >> 3;
  v70 = 0;
  if ( !v29 )
    goto LABEL_90;
  while ( 1 )
  {
    v75 = 0;
    memset_0(&v80, 0, 0xE0u);
    v30 = *(wchar_t **)(v6 + 8 * v5);
    v31 = o_wcstok_s_0(v30, L":", &v75);
    if ( !v31 )
    {
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        v72 = (const char *)v30;
        v35 = "Vendor string is NULL in driver version string";
        v36 = &byte_1801AA3B7;
LABEL_83:
        v73 = v35;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v32,
          (_DWORD)v36,
          v33,
          (_DWORD)v34,
          (__int64)&v73,
          (__int64)&v72);
      }
      goto LABEL_84;
    }
    v33 = (int)v75;
    if ( v75 )
      break;
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v72 = "Driver version string buffer is NULL";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v32,
        (unsigned int)byte_1801AA483,
        0,
        (_DWORD)v34,
        (__int64)&v72);
    }
LABEL_84:
    v5 = (unsigned int)(v5 + 1);
    v70 = v5;
    if ( (unsigned int)v5 >= v29 )
    {
      LODWORD(v5) = v71;
      goto LABEL_90;
    }
  }
  v37 = 0;
  do
  {
    v38 = v31[v37++];
    if ( v38 != aIntel[v37 - 1] )
    {
      v41 = 0;
      while ( 1 )
      {
        v42 = v31[v41++];
        if ( v42 != aNvidia[v41 - 1] )
          break;
        if ( v41 == 7 )
        {
          v39 = 3;
          v40 = 4318;
          goto LABEL_64;
        }
      }
      v43 = 0;
      while ( 1 )
      {
        v44 = v31[v43++];
        if ( v44 != SubStr[v43 - 1] )
          break;
        if ( v43 == 4 )
        {
          v39 = 2;
          v40 = 4098;
          goto LABEL_64;
        }
      }
      v45 = 0;
      v34 = L"QCOM";
      while ( 1 )
      {
        v46 = v31[v45++];
        if ( v46 != aQcom[v45 - 1] )
          break;
        if ( v45 == 5 )
        {
          v39 = 4;
          v40 = 1297040209;
          goto LABEL_64;
        }
      }
      v47 = 0;
      while ( 1 )
      {
        v32 = v31[v47];
        if ( (_WORD)v32 != aMicrosoft[v47] )
          break;
        v32 = v31[v47 + 1];
        if ( (_WORD)v32 != aMicrosoft[v47 + 1] )
          break;
        v47 += 2;
        if ( v47 == 10 )
        {
          v39 = 5;
          v40 = 5140;
          goto LABEL_64;
        }
      }
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        v72 = (const char *)v31;
        v35 = "Vendor is unknown";
        v36 = (char *)&unk_1801AA450;
        goto LABEL_83;
      }
      goto LABEL_84;
    }
  }
  while ( v37 != 6 );
  v39 = 1;
  v40 = 32902;
LABEL_64:
  LODWORD(v80) = v40;
  DWORD2(v93) = v39;
  if ( UMD_DISPLAYDRIVER::ConvertDriverVersionStringToLI((UMD_DISPLAYDRIVER *)&v80, v75) < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v72 = "Invalid driver version - failed to convert from string to large int";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v48,
        (unsigned int)byte_1801AA2F9,
        v49,
        v50,
        (__int64)&v72);
    }
    goto LABEL_84;
  }
  LODWORD(v69) = WORD4(v80);
  LODWORD(v68) = HIWORD(DWORD2(v80));
  LODWORD(v67) = WORD6(v80);
  if ( swprintf_s(Buffer, 0x64u, L"%d.%d.%d.%d", HIWORD(v80), v67, v68, v69) == -1 )
  {
    LODWORD(v5) = -2147467259;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v71 = 278;
      v78 = "swprintf_s for driver.m_wszDriverVersion failed";
      v70 = -2147467259;
      v72 = "CreateDriverVersionBlockList";
      v73 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
      v74 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v51,
        (unsigned int)word_1801AA2A2,
        v52,
        v53,
        (__int64)&v74,
        (__int64)&v70,
        (__int64)&v73,
        (__int64)&v71,
        (__int64)&v72,
        (__int64)&v78);
    }
  }
  else
  {
    v54 = (char *)v74;
    v55 = (_OWORD *)*((_QWORD *)v74 + 1);
    v56 = (_OWORD *)*((_QWORD *)v74 + 2);
    if ( v55 != v56 )
    {
      *v55 = v80;
      v55[1] = *(_OWORD *)Buffer;
      v55[2] = v82;
      v55[3] = v83;
      v55[4] = v84;
      v55[5] = v85;
      v55[6] = v86;
      v55[7] = v87;
      v55[8] = v88;
      v55[9] = v89;
      v55[10] = v90;
      v55[11] = v91;
      v55[12] = v92;
      v55[13] = v93;
LABEL_79:
      *((_QWORD *)v54 + 1) += 224LL;
      if ( (unsigned int)dword_1801B76C8 > 5 )
      {
        v72 = (const char *)Buffer;
        v70 = v80;
        v73 = "CreateDriverVersionBlockList - driverBlockList";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v56,
          (unsigned int)&dword_1801AA324,
          v52,
          v53,
          (__int64)&v73,
          (__int64)&v70,
          (__int64)&v72);
      }
      goto LABEL_84;
    }
    v57 = *(_BYTE **)v74;
    v58 = 0x6DB6DB6DB6DB6DB7LL * (((__int64)v56 - *(_QWORD *)v74) >> 5);
    v59 = 7 * (v58 >> 2) + 8;
    if ( v59 > 0x92492492492492LL )
      v59 = 0x92492492492492LL;
    if ( v58 < v59 )
    {
      v60 = 224 * v59;
      v61 = (char *)operator new(224 * v59, (const struct std::nothrow_t *)&std::nothrow);
      v62 = v61;
      LODWORD(v58) = (_DWORD)v61 - 1;
      if ( (unsigned __int64)(v61 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v63 = (char *)((char *)&v80 - v57);
        v64 = (char *)&v80;
        v65 = &v61[v60];
        memcpy_0(v61, *(const void **)v74, 32 * ((__int64)(*((_QWORD *)v74 + 1) - *(_QWORD *)v74) >> 5));
        v54 = (char *)v74;
        v56 = *(_OWORD **)v74;
        v66 = &v62[32 * ((__int64)(*((_QWORD *)v74 + 1) - *(_QWORD *)v74) >> 5)];
        if ( *(_QWORD *)v74 != -1 )
        {
          *((_QWORD *)v74 + 1) = v56;
          operator delete(v56);
          v54 = (char *)v74;
        }
        *(_QWORD *)v54 = v62;
        *((_QWORD *)v54 + 1) = v66;
        *((_QWORD *)v54 + 2) = v65;
        if ( (unsigned __int64)v63 < v66 - v62 )
          v64 = &v62[(_QWORD)v63];
        LODWORD(v5) = v70;
        *(_OWORD *)v66 = *(_OWORD *)v64;
        *((_OWORD *)v66 + 1) = *((_OWORD *)v64 + 1);
        *((_OWORD *)v66 + 2) = *((_OWORD *)v64 + 2);
        *((_OWORD *)v66 + 3) = *((_OWORD *)v64 + 3);
        *((_OWORD *)v66 + 4) = *((_OWORD *)v64 + 4);
        *((_OWORD *)v66 + 5) = *((_OWORD *)v64 + 5);
        *((_OWORD *)v66 + 6) = *((_OWORD *)v64 + 6);
        *((_OWORD *)v66 + 7) = *((_OWORD *)v64 + 7);
        *((_OWORD *)v66 + 8) = *((_OWORD *)v64 + 8);
        *((_OWORD *)v66 + 9) = *((_OWORD *)v64 + 9);
        *((_OWORD *)v66 + 10) = *((_OWORD *)v64 + 10);
        *((_OWORD *)v66 + 11) = *((_OWORD *)v64 + 11);
        *((_OWORD *)v66 + 12) = *((_OWORD *)v64 + 12);
        *((_OWORD *)v66 + 13) = *((_OWORD *)v64 + 13);
        goto LABEL_79;
      }
    }
    LODWORD(v5) = -2147467259;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v71 = 283;
      v72 = "driverBlockList.push_back failed";
      v70 = -2147467259;
      v73 = "CreateDriverVersionBlockList";
      v74 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\common\\adaptertoencodercreator.cpp";
      v78 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v58,
        (unsigned int)&unk_1801AA360,
        v52,
        v53,
        (__int64)&v78,
        (__int64)&v70,
        (__int64)&v74,
        (__int64)&v71,
        (__int64)&v73,
        (__int64)&v72);
    }
  }
LABEL_90:
  operator delete(String);
  if ( v6 != -1 )
    operator delete((void *)v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e2320  push    rbp
0x1800e2322  push    rbx
0x1800e2323  lea     rbp, [rsp-0B8h]
0x1800e232b  sub     rsp, 1B8h
0x1800e2332  mov     rax, cs:__security_cookie
0x1800e2339  xor     rax, rsp
0x1800e233c  mov     [rbp+0C0h+var_40], rax
0x1800e2343  mov     [rsp+1C0h+var_158], rdx
0x1800e2348  mov     rbx, rcx
0x1800e234b  mov     [rbp+0C0h+Context], 0
0x1800e2353  test    rcx, rcx
0x1800e2356  jnz     short loc_1800E23B9
0x1800e2358  mov     rax, cs:WPP_GLOBAL_Control
0x1800e235f  lea     rdx, WPP_GLOBAL_Control
0x1800e2366  cmp     rax, rdx
0x1800e2369  jz      short loc_1800E23A8
0x1800e236b  test    byte ptr [rax+1Ch], 8
0x1800e236f  jz      short loc_1800E23A8
0x1800e2371  cmp     byte ptr [rax+19h], 2
0x1800e2375  jb      short loc_1800E23A8
0x1800e2377  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e237d  lea     rcx, aWszdriverblock; "wszDriverBlockVersions"
0x1800e2384  mov     edx, 0Ch
0x1800e2389  mov     [rsp+1C0h+var_1A0], rcx
0x1800e238e  lea     r8, WPP_604b36dd83cf35ab199212a9476a51f1_Traceguids
0x1800e2395  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e239c  mov     r9d, eax
0x1800e239f  mov     rcx, [rcx+10h]
0x1800e23a3  call    WPP_SF_Ds
0x1800e23a8  xor     ecx, ecx; Block
0x1800e23aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e23af  mov     eax, 80004003h
0x1800e23b4  jmp     loc_1800E2E2D
0x1800e23b9  mov     rax, [rdx]
0x1800e23bc  mov     [rsp+1C0h+var_10], rdi
0x1800e23c4  xor     edi, edi
0x1800e23c6  mov     [rsp+1C0h+var_20], r13
0x1800e23ce  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800e23d5  mov     [rdx+8], rax
0x1800e23d9  mov     rax, r13
0x1800e23dc  mov     [rsp+1C0h+var_16C], edi
0x1800e23e0  mov     [rsp+1C0h+String], rdi
0x1800e23e5  inc     rax
0x1800e23e8  cmp     [rcx+rax*2], di
0x1800e23ec  jnz     short loc_1800E23E5
0x1800e23ee  mov     [rsp+1C0h+var_28], r14
0x1800e23f6  test    eax, eax
0x1800e23f8  jz      loc_1800E2DF4
0x1800e23fe  lea     edi, [rax+1]
0x1800e2401  mov     eax, 2
0x1800e2406  mul     rdi
0x1800e2409  cmovb   rax, r13
0x1800e240d  mov     rcx, rax; unsigned __int64
0x1800e2410  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800e2415  mov     [rsp+1C0h+String], rax
0x1800e241a  mov     r14, rax
0x1800e241d  test    rax, rax
0x1800e2420  jnz     short loc_1800E248C
0x1800e2422  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2429  lea     rdx, WPP_GLOBAL_Control
0x1800e2430  cmp     rcx, rdx
0x1800e2433  jz      short loc_1800E247A
0x1800e2435  test    byte ptr [rcx+1Ch], 8
0x1800e2439  jz      short loc_1800E247A
0x1800e243b  cmp     byte ptr [rcx+19h], 2
0x1800e243f  jb      short loc_1800E247A
0x1800e2441  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e2447  lea     rcx, aTempdriverbloc; "tempDriverBlockVersions"
0x1800e244e  mov     dword ptr [rsp+1C0h+var_198], 8007000Eh
0x1800e2456  mov     [rsp+1C0h+var_1A0], rcx
0x1800e245b  lea     r8, WPP_604b36dd83cf35ab199212a9476a51f1_Traceguids
0x1800e2462  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e2469  mov     edx, 0Dh
0x1800e246e  mov     r9d, eax
0x1800e2471  mov     rcx, [rcx+10h]
0x1800e2475  call    WPP_SF_DsD
0x1800e247a  mov     rcx, r14; Block
0x1800e247d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e2482  mov     eax, 8007000Eh
0x1800e2487  jmp     loc_1800E2E15
0x1800e248c  mov     r8, rbx; Source
0x1800e248f  mov     rdx, rdi; SizeInWords
0x1800e2492  mov     rcx, r14; Destination
0x1800e2495  call    wcscpy_s
0x1800e249a  test    eax, eax
0x1800e249c  jz      loc_1800E254B
0x1800e24a2  mov     eax, cs:dword_1801B76C8
0x1800e24a8  cmp     eax, 2
0x1800e24ab  jbe     loc_1800E2539
0x1800e24b1  lea     rax, aWszdriverversi; "wszDriverVersions copy failed"
0x1800e24b8  mov     [rsp+1C0h+var_16C], 0BAh
0x1800e24c0  mov     [rsp+1C0h+var_150], rax
0x1800e24c5  lea     rdx, byte_1801AA56F
0x1800e24cc  lea     rax, aCreatedriverve; "CreateDriverVersionBlockList"
0x1800e24d3  mov     [rsp+1C0h+var_170], 80004005h
0x1800e24db  mov     [rsp+1C0h+String], rax
0x1800e24e0  lea     rax, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e24e7  mov     [rsp+1C0h+var_158], rax
0x1800e24ec  lea     rax, aErrorCondition; "Error condition failed"
0x1800e24f3  mov     [rsp+1C0h+var_160], rax
0x1800e24f8  lea     rax, [rsp+1C0h+var_150]
0x1800e24fd  mov     [rsp+1C0h+var_178], rax
0x1800e2502  lea     rax, [rsp+1C0h+String]
0x1800e2507  mov     [rsp+1C0h+var_180], rax
0x1800e250c  lea     rax, [rsp+1C0h+var_16C]
0x1800e2511  mov     [rsp+1C0h+var_188], rax
0x1800e2516  lea     rax, [rsp+1C0h+var_158]
0x1800e251b  mov     [rsp+1C0h+var_190], rax
0x1800e2520  lea     rax, [rsp+1C0h+var_170]
0x1800e2525  mov     [rsp+1C0h+var_198], rax
0x1800e252a  lea     rax, [rsp+1C0h+var_160]
0x1800e252f  mov     [rsp+1C0h+var_1A0], rax
0x1800e2534  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800e2539  mov     rcx, r14; Block
0x1800e253c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e2541  mov     eax, 80004005h
0x1800e2546  jmp     loc_1800E2E15
0x1800e254b  mov     rcx, [rsp+1C0h+String]; String
0x1800e2550  lea     r8, [rbp+0C0h+Context]; Context
0x1800e2554  mov     [rsp+1C0h+arg_10], rsi
0x1800e255c  lea     rdx, asc_1801812A0; ";"
0x1800e2563  mov     [rsp+1C0h+var_18], r12
0x1800e256b  mov     r14, r13
0x1800e256e  mov     [rsp+1C0h+var_30], r15
0x1800e2576  mov     rdi, r13
0x1800e2579  call    _o_wcstok_s_0
0x1800e257e  mov     [rbp+0C0h+var_140], rax
0x1800e2582  test    rax, rax
0x1800e2585  jz      loc_1800E2685
0x1800e258b  mov     r12, 0FFFFFFFFFFFFFFFh
0x1800e2595  mov     rcx, 1FFFFFFFFFFFFFFFh
0x1800e259f  cmp     r14, rdi
0x1800e25a2  jz      short loc_1800E25B0
0x1800e25a4  mov     [r14], rax
0x1800e25a7  add     r14, 8
0x1800e25ab  jmp     loc_1800E2666
0x1800e25b0  sub     rdi, r13
0x1800e25b3  sar     rdi, 3
0x1800e25b7  mov     rax, rdi
0x1800e25ba  shr     rax, 2
0x1800e25be  imul    rax, 7
0x1800e25c2  add     rax, 8
0x1800e25c6  cmp     rax, r12
0x1800e25c9  cmova   rax, r12
0x1800e25cd  cmp     rdi, rax
0x1800e25d0  jnb     loc_1800E2716
0x1800e25d6  cmp     rax, rcx
0x1800e25d9  ja      loc_1800E2716
0x1800e25df  lea     rdi, ds:0[rax*8]
0x1800e25e7  mov     rcx, rdi; unsigned __int64
0x1800e25ea  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e25f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800e25f6  mov     rbx, rax
0x1800e25f9  test    rax, rax
0x1800e25fc  jz      loc_1800E2716
0x1800e2602  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e2606  jz      loc_1800E2716
0x1800e260c  sub     r14, r13
0x1800e260f  lea     rsi, [rbp+0C0h+var_140]
0x1800e2613  sar     r14, 3
0x1800e2617  lea     r15, [rbp+0C0h+var_140]
0x1800e261b  mov     rdx, r13; Src
0x1800e261e  mov     rcx, rax; void *
0x1800e2621  sub     rsi, r13
0x1800e2624  add     rdi, rax
0x1800e2627  lea     r14, ds:0[r14*8]
0x1800e262f  mov     r8, r14; Size
0x1800e2632  call    memcpy_0
0x1800e2637  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800e263b  jz      short loc_1800E264C
0x1800e263d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800e2644  mov     rcx, r13; Block
0x1800e2647  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e264c  cmp     rsi, r14
0x1800e264f  jnb     short loc_1800E2655
0x1800e2651  lea     r15, [rsi+rbx]
0x1800e2655  mov     rax, [r15]
0x1800e2658  mov     r13, rbx
0x1800e265b  mov     [r14+rbx], rax
0x1800e265f  add     r14, 8
0x1800e2663  add     r14, rbx
0x1800e2666  lea     r8, [rbp+0C0h+Context]; Context
0x1800e266a  xor     ecx, ecx; String
0x1800e266c  lea     rdx, asc_1801812A0; ";"
0x1800e2673  call    _o_wcstok_s_0
0x1800e2678  mov     [rbp+0C0h+var_140], rax
0x1800e267c  test    rax, rax
0x1800e267f  jnz     loc_1800E2595
0x1800e2685  sub     r14, r13
0x1800e2688  xor     edi, edi
0x1800e268a  sar     r14, 3
0x1800e268e  mov     [rsp+1C0h+var_170], edi
0x1800e2692  test    r14, r14
0x1800e2695  jz      loc_1800E2DDC
0x1800e269b  lea     r15, aIntel; "Intel"
0x1800e26a2  lea     r12, aNvidia; "NVIDIA"
0x1800e26a9  lea     rsi, aMicrosoft; "Microsoft"
0x1800e26b0  xor     edx, edx; Val
0x1800e26b2  mov     [rsp+1C0h+var_150], 0
0x1800e26bb  mov     r8d, 0E0h; Size
0x1800e26c1  lea     rcx, [rbp+0C0h+var_120]; void *
0x1800e26c5  call    memset_0
0x1800e26ca  mov     rbx, [r13+rdi*8+0]
0x1800e26cf  lea     r8, [rsp+1C0h+var_150]; Context
0x1800e26d4  mov     rcx, rbx; String
0x1800e26d7  lea     rdx, asc_180181344; ":"
0x1800e26de  call    _o_wcstok_s_0
0x1800e26e3  mov     rdx, rax
0x1800e26e6  test    rax, rax
0x1800e26e9  jnz     loc_1800E27B3
0x1800e26ef  mov     eax, cs:dword_1801B76C8
0x1800e26f5  cmp     eax, 3
0x1800e26f8  jbe     loc_1800E2C91
0x1800e26fe  mov     [rsp+1C0h+var_168], rbx
0x1800e2703  lea     rax, aVendorStringIs; "Vendor string is NULL in driver version"...
0x1800e270a  lea     rdx, byte_1801AA3B7
0x1800e2711  jmp     loc_1800E2C73
0x1800e2716  mov     eax, cs:dword_1801B76C8
0x1800e271c  mov     edi, 80004005h
0x1800e2721  cmp     eax, 2
0x1800e2724  jbe     loc_1800E2DDC
0x1800e272a  lea     rax, aDriverversions; "driverVersionStrings.push_back failed"
0x1800e2731  mov     [rsp+1C0h+var_16C], 0C3h
0x1800e2739  mov     [rsp+1C0h+var_160], rax
0x1800e273e  lea     rdx, byte_1801AA3F9
0x1800e2745  lea     rax, aCreatedriverve; "CreateDriverVersionBlockList"
0x1800e274c  mov     [rsp+1C0h+var_170], edi
0x1800e2750  mov     [rsp+1C0h+var_150], rax
0x1800e2755  lea     rax, aOnecoreuapTerm_3; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800e275c  mov     [rsp+1C0h+var_158], rax
0x1800e2761  lea     rax, aErrorCondition; "Error condition failed"
0x1800e2768  mov     [rsp+1C0h+var_168], rax
0x1800e276d  lea     rax, [rsp+1C0h+var_160]
0x1800e2772  mov     [rsp+1C0h+var_178], rax
0x1800e2777  lea     rax, [rsp+1C0h+var_150]
0x1800e277c  mov     [rsp+1C0h+var_180], rax
0x1800e2781  lea     rax, [rsp+1C0h+var_16C]
0x1800e2786  mov     [rsp+1C0h+var_188], rax
0x1800e278b  lea     rax, [rsp+1C0h+var_158]
0x1800e2790  mov     [rsp+1C0h+var_190], rax
0x1800e2795  lea     rax, [rsp+1C0h+var_170]
0x1800e279a  mov     [rsp+1C0h+var_198], rax
0x1800e279f  lea     rax, [rsp+1C0h+var_168]
0x1800e27a4  mov     [rsp+1C0h+var_1A0], rax
0x1800e27a9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800e27ae  jmp     loc_1800E2DDC
0x1800e27b3  mov     r8, [rsp+1C0h+var_150]
0x1800e27b8  test    r8, r8
0x1800e27bb  jnz     short loc_1800E27F3
0x1800e27bd  mov     eax, cs:dword_1801B76C8
0x1800e27c3  cmp     eax, 3
0x1800e27c6  jbe     loc_1800E2C91
0x1800e27cc  lea     rax, aDriverVersionS; "Driver version string buffer is NULL"
0x1800e27d3  mov     [rsp+1C0h+var_168], rax
0x1800e27d8  lea     rdx, byte_1801AA483
0x1800e27df  lea     rax, [rsp+1C0h+var_168]
0x1800e27e4  mov     [rsp+1C0h+var_1A0], rax
0x1800e27e9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800e27ee  jmp     loc_1800E2C91
0x1800e27f3  xor     ecx, ecx
0x1800e27f5  nop     word ptr [rax+rax+00000000h]
0x1800e2800  movzx   eax, word ptr [rdx+rcx*2]
0x1800e2804  inc     rcx
0x1800e2807  cmp     ax, [r15+rcx*2-2]
0x1800e280d  jnz     short loc_1800E2824
0x1800e280f  cmp     rcx, 6
0x1800e2813  jnz     short loc_1800E2800
0x1800e2815  mov     eax, 1
0x1800e281a  mov     ecx, 8086h
0x1800e281f  jmp     loc_1800E28F2
0x1800e2824  xor     ecx, ecx
0x1800e2826  nop     word ptr [rax+rax+00000000h]
0x1800e2830  movzx   eax, word ptr [rdx+rcx*2]
0x1800e2834  inc     rcx
0x1800e2837  cmp     ax, [r12+rcx*2-2]
0x1800e283d  jnz     short loc_1800E2854
0x1800e283f  cmp     rcx, 7
0x1800e2843  jnz     short loc_1800E2830
0x1800e2845  mov     eax, 3
0x1800e284a  mov     ecx, 10DEh
0x1800e284f  jmp     loc_1800E28F2
0x1800e2854  xor     ecx, ecx
0x1800e2856  lea     r9, aAmd; "AMD"
0x1800e285d  nop     dword ptr [rax]
0x1800e2860  movzx   eax, word ptr [rdx+rcx*2]
0x1800e2864  inc     rcx
0x1800e2867  cmp     ax, [r9+rcx*2-2]
0x1800e286d  jnz     short loc_1800E2881
0x1800e286f  cmp     rcx, 4
0x1800e2873  jnz     short loc_1800E2860
0x1800e2875  mov     eax, 2
0x1800e287a  mov     ecx, 1002h
0x1800e287f  jmp     short loc_1800E28F2
0x1800e2881  xor     ecx, ecx
0x1800e2883  lea     r9, aQcom; "QCOM"
0x1800e288a  nop     word ptr [rax+rax+00h]
0x1800e2890  movzx   eax, word ptr [rdx+rcx*2]
0x1800e2894  inc     rcx
0x1800e2897  cmp     ax, [r9+rcx*2-2]
0x1800e289d  jnz     short loc_1800E28B1
  ... truncated ...
```
