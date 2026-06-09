# RdpWinRadcHttpRequest::PerformRequest(void)

- ea: `0x18032f09c`
- end: `0x18032fbe5`
- name: `?PerformRequest@RdpWinRadcHttpRequest@@AEAAJXZ`
- size: `2889`
- prototype: `__int64 __fastcall(RdpWinRadcHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18032dc30`

## callees

- `0x18002a334`
- `0x18002a374`
- `0x180039c98`
- `0x1800e9b1c`
- `0x180102ee8`
- `0x180130604`
- `0x18032c818`
- `0x18032d494`
- `0x18032e2e0`
- `0x18032f09c`
- `0x1803304a0`
- `0x180330fd4`
- `0x18033154c`
- `0x18033173c`
- `0x180331d80`
- `0x180331f0c`
- `0x18068c010`

## import_xrefs

- `msvcrt!wcscspn` at `0x18032f93f`
- `msvcrt!wcscspn` at `0x18032f93f`
- `KERNEL32!GetLastError` at `0x18032f227`
- `KERNEL32!GetLastError` at `0x18032f30c`
- `KERNEL32!GetLastError` at `0x18032f3c7`
- `KERNEL32!GetLastError` at `0x18032f227`
- `KERNEL32!GetLastError` at `0x18032f30c`
- `KERNEL32!GetLastError` at `0x18032f3c7`
- `KERNEL32!CompareStringEx` at `0x18032f989`
- `KERNEL32!CompareStringEx` at `0x18032f9c9`
- `KERNEL32!CompareStringEx` at `0x18032f989`
- `KERNEL32!CompareStringEx` at `0x18032f9c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f20d`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f21c`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f63e`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f6ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f7d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18032fbb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18032fbc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18032fbca`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f20d`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f21c`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f63e`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f6ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18032f7d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18032fbb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18032fbc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18032fbca`
- `WINHTTP!WinHttpReceiveResponse` at `0x18032f302`
- `WINHTTP!WinHttpReceiveResponse` at `0x18032f302`
- `WINHTTP!WinHttpSendRequest` at `0x18032f1fc`
- `WINHTTP!WinHttpSendRequest` at `0x18032f1fc`
- `WINHTTP!WinHttpQueryHeaders` at `0x18032f3bd`
- `WINHTTP!WinHttpQueryHeaders` at `0x18032f3bd`

## string_xrefs

- `0x18032f74b`: `SetClaimsTokenIfExists failed`
- `0x18032f13a`: `Content-Type: application/json; charset=utf-16\n`
- `0x18032f14c`: `Content-Type: application/xml\n`
- `0x18032f143`: `Content-Type: application/json\n`
- `0x18032fa63`: `ReadResponseBody failed`

## pseudocode

```c
__int64 __fastcall RdpWinRadcHttpRequest::PerformRequest(
        RdpWinRadcHttpRequest *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // r12d
  int v6; // ecx
  wchar_t *v7; // rdi
  unsigned __int16 *v8; // rsi
  int v9; // ecx
  __int64 v10; // rcx
  unsigned int v11; // r14d
  int ActivityIdPrefix; // eax
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rcx
  DWORD v15; // ebx
  const WCHAR **v16; // rax
  OLECHAR *v17; // rbx
  const WCHAR *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  int LastError; // ebx
  __int64 v26; // r8
  __int64 v27; // r9
  HKEY v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rdx
  bool v31; // sf
  __int64 v32; // rbx
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rbx
  unsigned int v39; // eax
  int v40; // eax
  bool ShouldEndEarly; // al
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  int v50; // ebx
  __int64 v51; // r14
  unsigned int v52; // eax
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
  int v58; // ebx
  __int64 v59; // r14
  unsigned int v60; // eax
  __int64 v61; // r8
  HKEY v62; // rax
  __int64 v63; // rbx
  unsigned int v64; // eax
  unsigned int v65; // eax
  OLECHAR *v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // r9
  int v71; // eax
  int v72; // edx
  const char *v73; // rcx
  __int64 v74; // rbx
  unsigned int v75; // eax
  __int64 v76; // r8
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 v89; // rbx
  unsigned int v90; // eax
  __int64 v91; // rbx
  unsigned int v92; // eax
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 v97; // rbx
  unsigned int v98; // eax
  unsigned int v99; // eax
  size_t v100; // rax
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // r8
  __int64 v104; // r9
  int v105; // ebx
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // r8
  __int64 v109; // r9
  __int64 v110; // rbx
  int v111; // r8d
  int v112; // r9d
  const wchar_t *v113; // rax
  int v114; // eax
  __int64 v115; // rbx
  unsigned int v116; // eax
  __int64 v117; // r8
  int v118; // eax
  int v119; // eax
  DWORD dwTotalLength[2]; // [rsp+28h] [rbp-58h]
  DWORD dwTotalLengtha[2]; // [rsp+28h] [rbp-58h]
  DWORD dwBufferLength; // [rsp+50h] [rbp-30h] BYREF
  wchar_t *String; // [rsp+58h] [rbp-28h] BYREF
  BSTR v125; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v126; // [rsp+68h] [rbp-18h] BYREF
  LPVOID lpOptional; // [rsp+70h] [rbp-10h]
  BSTR v128; // [rsp+78h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+40h] BYREF
  DWORD dwOptionalLength; // [rsp+C8h] [rbp+48h]
  BSTR v131; // [rsp+D0h] [rbp+50h] BYREF
  DWORD v132; // [rsp+D8h] [rbp+58h]

  v4 = 0;
  dwBufferLength = 4;
  LODWORD(bstrString) = 0;
  v6 = *((_DWORD *)this + 55);
  v7 = 0;
  String = 0;
  v8 = 0;
  v125 = 0;
  v126 = 0;
  if ( v6 )
  {
    v9 = v6 - 1;
    if ( v9 )
    {
      v10 = (unsigned int)(v9 - 1);
      if ( (_DWORD)v10 )
      {
        if ( (_DWORD)v10 != 1 )
        {
          v11 = -2147418113;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(v10, a2, a3, a4);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              96,
              (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              ActivityIdPrefix,
              (__int64)"Unknown request body content type",
              -2147418113);
          }
          goto LABEL_161;
        }
        v13 = L"Content-Type: application/json; charset=utf-16\r\n";
      }
      else
      {
        v13 = L"Content-Type: application/json\r\n";
      }
    }
    else
    {
      v13 = L"Content-Type: application/xml\r\n";
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v125, v13);
  }
  if ( RdpWinRadcHttpRequest::ShouldEndEarly(this) )
  {
    v11 = 1;
    goto LABEL_161;
  }
  v14 = *((_QWORD *)this + 26);
  v15 = *((_DWORD *)this + 54);
  v132 = v15;
  if ( v14 )
  {
    lpOptional = (LPVOID)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
    dwOptionalLength = v15;
  }
  else
  {
    lpOptional = 0;
    dwOptionalLength = 0;
  }
  v11 = 1;
  if ( *((_QWORD *)this + 26) )
  {
    v16 = (const WCHAR **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v128, (const struct ATL::CComBSTR *)&v125);
    v17 = bstrString;
    v4 = 1;
    LODWORD(v131) = 0;
    v18 = *v16;
  }
  else
  {
    v17 = 0;
    LODWORD(v131) = 2;
    v18 = 0;
  }
  dwOptionalLength = WinHttpSendRequest(
                       *((HINTERNET *)this + 5),
                       v18,
                       0,
                       lpOptional,
                       dwOptionalLength,
                       v132,
                       (DWORD_PTR)this);
  if ( (_DWORD)v131 )
    SysFreeString(v17);
  if ( v4 )
    SysFreeString(v128);
  if ( !dwOptionalLength )
  {
    LastError = GetLastError();
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpX_GetActivityIdPrefix(v24, v23, v26, v27);
      v30 = 97;
LABEL_30:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
        v29,
        LastError);
      v28 = WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v32 = *((_QWORD *)this + 2);
    v33 = RdpX_GetActivityIdPrefix(v20, v19, v21, v22);
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v33, v32);
  }
  if ( !RdpWinRadcHttpRequest::ShouldEndEarly(this) )
  {
    if ( !WinHttpReceiveResponse(*((HINTERNET *)this + 5), 0) )
    {
      LastError = GetLastError();
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpX_GetActivityIdPrefix(v24, v23, v26, v27);
        v30 = 99;
        goto LABEL_30;
      }
LABEL_31:
      v31 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v31 = LastError < 0;
      }
      if ( !v31 )
      {
        v11 = -2147467259;
        goto LABEL_161;
      }
      goto LABEL_144;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v38 = *((_QWORD *)this + 2);
      v39 = RdpX_GetActivityIdPrefix(v35, v34, v36, v37);
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v39, v38);
    }
    if ( !RdpWinRadcHttpRequest::ShouldEndEarly(this) )
    {
      if ( !WinHttpQueryHeaders(*((HINTERNET *)this + 5), 0x20000013u, 0, &bstrString, &dwBufferLength, 0) )
      {
        LastError = GetLastError();
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = RdpX_GetActivityIdPrefix(v24, v23, v26, v27);
          v30 = 101;
          goto LABEL_30;
        }
        goto LABEL_31;
      }
      LastError = RdpWinRadcHttpRequest::GetHttpHeaderFromResponse((HINTERNET *)this, 1u, &String);
      if ( LastError < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v40 = RdpX_GetActivityIdPrefix(v24, v23, v26, v27);
          dwTotalLength[0] = LastError;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
            v40,
            (__int64)"GetHttpHeaderFromResponse(WINHTTP_QUERY_CONTENT_TYPE) failed",
            *(_QWORD *)dwTotalLength);
          v7 = String;
LABEL_143:
          v28 = WPP_GLOBAL_Control;
          goto LABEL_144;
        }
        v7 = String;
LABEL_144:
        v11 = LastError;
        if ( LastError == -2147012881 || LastError == -2147012864 )
        {
          if ( v28 != (HKEY)&WPP_GLOBAL_Control && ((_DWORD)v28[7] & 0x10000) != 0 && *((_BYTE *)v28 + 25) >= 4u )
          {
            v115 = *((_QWORD *)this + 2);
            v116 = RdpX_GetActivityIdPrefix(v24, v23, v26, v27);
            WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, v117, v116, v115, v11);
          }
          v11 = -2147220731;
        }
        goto LABEL_161;
      }
      ShouldEndEarly = RdpWinRadcHttpRequest::ShouldEndEarly(this);
      v7 = String;
      if ( ShouldEndEarly )
        goto LABEL_161;
      v45 = (unsigned int)bstrString;
      dwOptionalLength = (unsigned int)bstrString;
      if ( (_DWORD)bstrString != 200 )
      {
        if ( (_DWORD)bstrString == 304 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 25) + 32LL))(
            *((_QWORD *)this + 25),
            *((_QWORD *)this + 2),
            304,
            0);
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v97 = *((_QWORD *)this + 2);
            v98 = RdpX_GetActivityIdPrefix(v94, v93, v95, v96);
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v98,
              v97);
          }
        }
        else
        {
          if ( (_DWORD)bstrString != 401 )
          {
            if ( (_DWORD)bstrString == 404 || (_DWORD)bstrString == 502 || (_DWORD)bstrString == 504 )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, wchar_t *))(**((_QWORD **)this + 25) + 32LL))(
                *((_QWORD *)this + 25),
                *((_QWORD *)this + 2),
                (unsigned int)bstrString,
                String);
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                v58 = (int)bstrString;
                v59 = *((_QWORD *)this + 2);
                v60 = RdpX_GetActivityIdPrefix(v55, v54, v56, v57);
                WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, v61, v60, v59, v58);
              }
              v11 = -2147220734;
            }
            else
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, wchar_t *))(**((_QWORD **)this + 25) + 32LL))(
                *((_QWORD *)this + 25),
                *((_QWORD *)this + 2),
                (unsigned int)bstrString,
                String);
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                v50 = (int)bstrString;
                v51 = *((_QWORD *)this + 2);
                v52 = RdpX_GetActivityIdPrefix(v47, v46, v48, v49);
                WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, v53, v52, v51, v50);
              }
              v11 = -2147220733;
            }
            goto LABEL_161;
          }
          v131 = 0;
          v62 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v63 = *((_QWORD *)this + 2);
            v64 = RdpX_GetActivityIdPrefix(v42, (unsigned int)bstrString, v43, v44);
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v64,
              v63);
            v62 = WPP_GLOBAL_Control;
          }
          if ( !*((_BYTE *)this + 184) )
          {
            if ( v62 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v62[7] & 8) != 0 && *((_BYTE *)v62 + 25) >= 2u )
            {
              v65 = RdpX_GetActivityIdPrefix(v42, v45, v43, v44);
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                110,
                &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
                v65,
                -2147467263);
            }
            v66 = 0;
            v11 = -2147467263;
            goto LABEL_88;
          }
          LastError = RdpWinRadcHttpRequest::TryFindClaimsAuthChallenge(this, &v131, v43, v44);
          if ( LastError < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_95;
            }
            v71 = RdpX_GetActivityIdPrefix(v68, v67, v69, v70);
            v72 = 111;
            v73 = "TryFindClaimsAuthChallenge failed";
LABEL_94:
            dwTotalLength[0] = LastError;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v72,
              (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v71,
              (__int64)v73,
              *(_QWORD *)dwTotalLength);
LABEL_95:
            SysFreeString(v131);
            goto LABEL_143;
          }
          if ( LastError )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v74 = *((_QWORD *)this + 2);
              v75 = RdpX_GetActivityIdPrefix(v68, v67, v69, v70);
              WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v76, v75, v74, -2147220968);
            }
            v11 = -2147220968;
            goto LABEL_102;
          }
          LastError = RdpWinRadcHttpRequest::SetClaimsTokenIfExists(this);
          if ( LastError < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_95;
            }
            v71 = RdpX_GetActivityIdPrefix(v78, v77, v79, v80);
            v72 = 113;
            v73 = "SetClaimsTokenIfExists failed";
            goto LABEL_94;
          }
          if ( RdpWinRadcHttpRequest::ShouldEndEarly(this) )
          {
LABEL_102:
            v66 = v131;
LABEL_88:
            SysFreeString(v66);
            goto LABEL_161;
          }
          if ( LastError != 1 )
          {
            v11 = -2147220731;
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v91 = *((_QWORD *)this + 2);
              v92 = RdpX_GetActivityIdPrefix(v82, v81, v83, v84);
              WPP_SF_Dq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                115,
                &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
                v92,
                v91);
            }
            goto LABEL_102;
          }
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, BSTR))(**((_QWORD **)this + 25) + 32LL))(
            *((_QWORD *)this + 25),
            *((_QWORD *)this + 2),
            dwOptionalLength,
            v131);
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v89 = *((_QWORD *)this + 2);
            v90 = RdpX_GetActivityIdPrefix(v86, v85, v87, v88);
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              114,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v90,
              v89);
          }
          SysFreeString(v131);
        }
LABEL_115:
        v11 = 0;
        goto LABEL_161;
      }
      LastError = RdpWinRadcHttpRequest::GetETagFromHttpResponse(this, &v126);
      if ( LastError == -2147012746 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v99 = RdpX_GetActivityIdPrefix(v24, v23, v26, v27);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v99);
        }
      }
      else if ( LastError < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v118 = RdpX_GetActivityIdPrefix(v24, v23, v26, v27);
          dwTotalLength[0] = LastError;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
            v118,
            (__int64)"GetHttpHeaderFromResponse(WINHTTP_QUERY_CONTENT_TYPE) failed",
            *(_QWORD *)dwTotalLength);
          v28 = WPP_GLOBAL_Control;
        }
        v8 = v126;
        goto LABEL_144;
      }
      v8 = v126;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, wchar_t *, unsigned __int16 *))(**((_QWORD **)this + 25) + 24LL))(
        *((_QWORD *)this + 25),
        *((_QWORD *)this + 2),
        dwOptionalLength,
        v7,
        v126);
      v100 = wcscspn(v7, L";");
      v105 = v100;
      if ( v100 <= 0x7FFFFFFF )
      {
        if ( CompareStringEx(&sourceString, 1u, v7, v100, L"application/x-msts-webfeed-login", -1, 0, 0, 0) != 2 )
          LOBYTE(v11) = CompareStringEx(
                          &sourceString,
                          1u,
                          v7,
                          v105,
                          L"application/x-msts-webfeed-discovery-login",
                          -1,
                          0,
                          0,
                          0) == 2;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v110 = *((_QWORD *)this + 2);
          v112 = RdpX_GetActivityIdPrefix(v107, v106, v108, v109);
          v113 = L"is";
          if ( !(_BYTE)v11 )
            v113 = (const wchar_t *)L"is not";
          WPP_SF_DIS(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, v111, v112, v110, (__int64)v113);
        }
        LastError = RdpWinRadcHttpRequest::ReadResponseBody(this, v11);
        if ( LastError < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v114 = RdpX_GetActivityIdPrefix(v24, v23, v26, v27);
            dwTotalLengtha[0] = LastError;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              108,
              (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v114,
              (__int64)"ReadResponseBody failed",
              *(_QWORD *)dwTotalLengtha);
            goto LABEL_143;
          }
          goto LABEL_144;
        }
        goto LABEL_115;
      }
      v11 = -2147024362;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v119 = RdpX_GetActivityIdPrefix(v102, v101, v103, v104);
        dwTotalLength[0] = -2147024362;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
          v119,
          (__int64)"SizeTToInt failed",
          *(_QWORD *)dwTotalLength);
      }
    }
  }
LABEL_161:
  SysFreeString(v8);
  SysFreeString(v125);
  SysFreeString(v7);
  return v11;
}

```

## disassembly

```asm
0x18032f09c  push    rbp
0x18032f09e  push    rbx
0x18032f09f  push    rsi
0x18032f0a0  push    rdi
0x18032f0a1  push    r12
0x18032f0a3  push    r14
0x18032f0a5  push    r15
0x18032f0a7  mov     rbp, rsp
0x18032f0aa  sub     rsp, 80h
0x18032f0b1  xor     r12d, r12d
0x18032f0b4  mov     [rbp+dwBufferLength], 4
0x18032f0bb  mov     r15, rcx
0x18032f0be  mov     dword ptr [rbp+bstrString], r12d
0x18032f0c2  mov     ecx, [rcx+0DCh]
0x18032f0c8  mov     edi, r12d
0x18032f0cb  mov     [rbp+String], r12
0x18032f0cf  mov     esi, r12d
0x18032f0d2  mov     [rbp+var_20], r12
0x18032f0d6  mov     [rbp+var_18], r12
0x18032f0da  test    ecx, ecx
0x18032f0dc  jz      short loc_18032F15C
0x18032f0de  sub     ecx, 1
0x18032f0e1  jz      short loc_18032F14C
0x18032f0e3  sub     ecx, 1
0x18032f0e6  jz      short loc_18032F143
0x18032f0e8  cmp     ecx, 1
0x18032f0eb  jz      short loc_18032F13A
0x18032f0ed  mov     r14d, 8000FFFFh
0x18032f0f3  mov     rax, cs:WPP_GLOBAL_Control
0x18032f0fa  lea     r12, WPP_GLOBAL_Control
0x18032f101  cmp     rax, r12
0x18032f104  jz      loc_18032FBB4
0x18032f10a  test    byte ptr [rax+1Ch], 8
0x18032f10e  jz      loc_18032FBB4
0x18032f114  cmp     byte ptr [rax+19h], 2
0x18032f118  jb      loc_18032FBB4
0x18032f11e  call    RdpX_GetActivityIdPrefix
0x18032f123  lea     edx, [rsi+60h]
0x18032f126  mov     [rsp+80h+dwTotalLength], 8000FFFFh
0x18032f12e  lea     rcx, aUnknownRequest; "Unknown request body content type"
0x18032f135  jmp     loc_18032FB95
0x18032f13a  lea     rdx, aContentTypeApp; "Content-Type: application/json; charset"...
0x18032f141  jmp     short loc_18032F153
0x18032f143  lea     rdx, aContentTypeApp_2; "Content-Type: application/json\r\n"
0x18032f14a  jmp     short loc_18032F153
0x18032f14c  lea     rdx, aContentTypeApp_0; "Content-Type: application/xml\r\n"
0x18032f153  lea     rcx, [rbp+var_20]; this
0x18032f157  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18032f15c  mov     rcx, r15; this
0x18032f15f  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x18032f164  test    al, al
0x18032f166  jz      short loc_18032F173
0x18032f168  mov     r14d, 1
0x18032f16e  jmp     loc_18032FBB4
0x18032f173  mov     rcx, [r15+0D0h]
0x18032f17a  mov     ebx, [r15+0D8h]
0x18032f181  mov     [rbp+arg_18], ebx
0x18032f184  test    rcx, rcx
0x18032f187  jz      short loc_18032F19E
0x18032f189  mov     rax, [rcx]
0x18032f18c  mov     rax, [rax+20h]
0x18032f190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032f195  mov     [rbp+lpOptional], rax
0x18032f199  mov     [rbp+arg_8], ebx
0x18032f19c  jmp     short loc_18032F1A6
0x18032f19e  mov     [rbp+lpOptional], r12
0x18032f1a2  mov     [rbp+arg_8], r12d
0x18032f1a6  mov     r14d, 1
0x18032f1ac  cmp     [r15+0D0h], r12
0x18032f1b3  jz      short loc_18032F1D1
0x18032f1b5  lea     rdx, [rbp+var_20]; struct ATL::CComBSTR *
0x18032f1b9  lea     rcx, [rbp+var_8]; this
0x18032f1bd  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x18032f1c2  mov     rbx, [rbp+bstrString]
0x18032f1c6  mov     r12d, r14d
0x18032f1c9  mov     dword ptr [rbp+arg_10], esi
0x18032f1cc  mov     rdx, [rax]
0x18032f1cf  jmp     short loc_18032F1DE
0x18032f1d1  mov     rbx, r12
0x18032f1d4  mov     dword ptr [rbp+arg_10], 2
0x18032f1db  mov     rdx, r12; lpszHeaders
0x18032f1de  mov     eax, [rbp+arg_18]
0x18032f1e1  xor     r8d, r8d; dwHeadersLength
0x18032f1e4  mov     r9, [rbp+lpOptional]; lpOptional
0x18032f1e8  mov     rcx, [r15+28h]; hRequest
0x18032f1ec  mov     [rsp+80h+dwContext], r15; dwContext
0x18032f1f1  mov     [rsp+80h+dwTotalLength], eax; dwTotalLength
0x18032f1f5  mov     eax, [rbp+arg_8]
0x18032f1f8  mov     [rsp+80h+dwOptionalLength], eax; dwOptionalLength
0x18032f1fc  call    cs:__imp_WinHttpSendRequest
0x18032f202  mov     [rbp+arg_8], eax
0x18032f205  cmp     dword ptr [rbp+arg_10], esi
0x18032f208  jz      short loc_18032F213
0x18032f20a  mov     rcx, rbx; bstrString
0x18032f20d  call    cs:__imp_SysFreeString
0x18032f213  test    r12d, r12d
0x18032f216  jz      short loc_18032F222
0x18032f218  mov     rcx, [rbp+var_8]; bstrString
0x18032f21c  call    cs:__imp_SysFreeString
0x18032f222  cmp     [rbp+arg_8], esi
0x18032f225  jnz     short loc_18032F29D
0x18032f227  call    cs:__imp_GetLastError
0x18032f22d  mov     ebx, eax
0x18032f22f  mov     rax, cs:WPP_GLOBAL_Control
0x18032f236  lea     r12, WPP_GLOBAL_Control
0x18032f23d  cmp     rax, r12
0x18032f240  jz      short loc_18032F27D
0x18032f242  test    byte ptr [rax+1Ch], 8
0x18032f246  jz      short loc_18032F27D
0x18032f248  cmp     byte ptr [rax+19h], 2
0x18032f24c  jb      short loc_18032F27D
0x18032f24e  call    RdpX_GetActivityIdPrefix
0x18032f253  mov     edx, 61h ; 'a'
0x18032f258  mov     rcx, cs:WPP_GLOBAL_Control
0x18032f25f  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18032f266  mov     r9d, eax
0x18032f269  mov     [rsp+80h+dwOptionalLength], ebx
0x18032f26d  mov     rcx, [rcx+10h]
0x18032f271  call    WPP_SF_Dd
0x18032f276  mov     rax, cs:WPP_GLOBAL_Control
0x18032f27d  test    ebx, ebx
0x18032f27f  jle     short loc_18032F28C
0x18032f281  movzx   ebx, bx
0x18032f284  or      ebx, 80070000h
0x18032f28a  test    ebx, ebx
0x18032f28c  js      loc_18032FA99
0x18032f292  mov     r14d, 80004005h
0x18032f298  jmp     loc_18032FBB4
0x18032f29d  mov     rax, cs:WPP_GLOBAL_Control
0x18032f2a4  lea     r12, WPP_GLOBAL_Control
0x18032f2ab  cmp     rax, r12
0x18032f2ae  jz      short loc_18032F2EC
0x18032f2b0  test    dword ptr [rax+1Ch], 10000h
0x18032f2b7  jz      short loc_18032F2EC
0x18032f2b9  cmp     byte ptr [rax+19h], 4
0x18032f2bd  jb      short loc_18032F2EC
0x18032f2bf  mov     rbx, [r15+10h]
0x18032f2c3  call    RdpX_GetActivityIdPrefix
0x18032f2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18032f2cf  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18032f2d6  mov     edx, 62h ; 'b'
0x18032f2db  mov     qword ptr [rsp+80h+dwOptionalLength], rbx
0x18032f2e0  mov     r9d, eax
0x18032f2e3  mov     rcx, [rcx+10h]
0x18032f2e7  call    WPP_SF_Dq
0x18032f2ec  mov     rcx, r15; this
0x18032f2ef  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x18032f2f4  test    al, al
0x18032f2f6  jnz     loc_18032FBB4
0x18032f2fc  mov     rcx, [r15+28h]; hRequest
0x18032f300  xor     edx, edx; lpReserved
0x18032f302  call    cs:__imp_WinHttpReceiveResponse
0x18032f308  test    eax, eax
0x18032f30a  jnz     short loc_18032F347
0x18032f30c  call    cs:__imp_GetLastError
0x18032f312  mov     ebx, eax
0x18032f314  mov     rax, cs:WPP_GLOBAL_Control
0x18032f31b  cmp     rax, r12
0x18032f31e  jz      loc_18032F27D
0x18032f324  test    byte ptr [rax+1Ch], 8
0x18032f328  jz      loc_18032F27D
0x18032f32e  cmp     byte ptr [rax+19h], 2
0x18032f332  jb      loc_18032F27D
0x18032f338  call    RdpX_GetActivityIdPrefix
0x18032f33d  mov     edx, 63h ; 'c'
0x18032f342  jmp     loc_18032F258
0x18032f347  mov     rax, cs:WPP_GLOBAL_Control
0x18032f34e  cmp     rax, r12
0x18032f351  jz      short loc_18032F38F
0x18032f353  test    dword ptr [rax+1Ch], 10000h
0x18032f35a  jz      short loc_18032F38F
0x18032f35c  cmp     byte ptr [rax+19h], 4
0x18032f360  jb      short loc_18032F38F
0x18032f362  mov     rbx, [r15+10h]
0x18032f366  call    RdpX_GetActivityIdPrefix
0x18032f36b  mov     rcx, cs:WPP_GLOBAL_Control
0x18032f372  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18032f379  mov     edx, 64h ; 'd'
0x18032f37e  mov     qword ptr [rsp+80h+dwOptionalLength], rbx
0x18032f383  mov     r9d, eax
0x18032f386  mov     rcx, [rcx+10h]
0x18032f38a  call    WPP_SF_Dq
0x18032f38f  mov     rcx, r15; this
0x18032f392  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x18032f397  test    al, al
0x18032f399  jnz     loc_18032FBB4
0x18032f39f  mov     rcx, [r15+28h]; hRequest
0x18032f3a3  lea     rax, [rbp+dwBufferLength]
0x18032f3a7  mov     qword ptr [rsp+80h+dwTotalLength], rsi; lpdwIndex
0x18032f3ac  lea     r9, [rbp+bstrString]; lpBuffer
0x18032f3b0  xor     r8d, r8d; pwszName
0x18032f3b3  mov     qword ptr [rsp+80h+dwOptionalLength], rax; lpdwBufferLength
0x18032f3b8  mov     edx, 20000013h; dwInfoLevel
0x18032f3bd  call    cs:__imp_WinHttpQueryHeaders
0x18032f3c3  test    eax, eax
0x18032f3c5  jnz     short loc_18032F402
0x18032f3c7  call    cs:__imp_GetLastError
0x18032f3cd  mov     ebx, eax
0x18032f3cf  mov     rax, cs:WPP_GLOBAL_Control
0x18032f3d6  cmp     rax, r12
0x18032f3d9  jz      loc_18032F27D
0x18032f3df  test    byte ptr [rax+1Ch], 8
0x18032f3e3  jz      loc_18032F27D
0x18032f3e9  cmp     byte ptr [rax+19h], 2
0x18032f3ed  jb      loc_18032F27D
0x18032f3f3  call    RdpX_GetActivityIdPrefix
0x18032f3f8  mov     edx, 65h ; 'e'
0x18032f3fd  jmp     loc_18032F258
0x18032f402  lea     r8, [rbp+String]; unsigned __int16 **
0x18032f406  mov     edx, r14d; unsigned int
0x18032f409  mov     rcx, r15; this
0x18032f40c  call    ?GetHttpHeaderFromResponse@RdpWinRadcHttpRequest@@AEAAJKPEAPEAG@Z; RdpWinRadcHttpRequest::GetHttpHeaderFromResponse(ulong,ushort * *)
0x18032f411  mov     ebx, eax
0x18032f413  test    eax, eax
0x18032f415  jns     short loc_18032F475
0x18032f417  mov     rax, cs:WPP_GLOBAL_Control
0x18032f41e  cmp     rax, r12
0x18032f421  jz      short loc_18032F46C
0x18032f423  test    byte ptr [rax+1Ch], 8
0x18032f427  jz      short loc_18032F46C
0x18032f429  cmp     byte ptr [rax+19h], 2
0x18032f42d  jb      short loc_18032F46C
0x18032f42f  call    RdpX_GetActivityIdPrefix
0x18032f434  lea     rcx, aGethttpheaderf; "GetHttpHeaderFromResponse(WINHTTP_QUERY"...
0x18032f43b  mov     [rsp+80h+dwTotalLength], ebx
0x18032f43f  mov     qword ptr [rsp+80h+dwOptionalLength], rcx
0x18032f444  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18032f44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18032f452  mov     edx, 66h ; 'f'
0x18032f457  mov     r9d, eax
0x18032f45a  mov     rcx, [rcx+10h]
0x18032f45e  call    WPP_SF_DsD
0x18032f463  mov     rdi, [rbp+String]
0x18032f467  jmp     loc_18032FA92
0x18032f46c  mov     rdi, [rbp+String]
0x18032f470  jmp     loc_18032FA99
0x18032f475  mov     rcx, r15; this
0x18032f478  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x18032f47d  mov     rdi, [rbp+String]
0x18032f481  test    al, al
0x18032f483  jnz     loc_18032FBB4
0x18032f489  mov     edx, dword ptr [rbp+bstrString]
0x18032f48c  mov     eax, edx
0x18032f48e  mov     [rbp+arg_8], edx
0x18032f491  sub     eax, 0C8h
0x18032f496  jz      loc_18032F8B6
0x18032f49c  sub     eax, 68h ; 'h'
0x18032f49f  jz      loc_18032F840
0x18032f4a5  sub     eax, 61h ; 'a'
0x18032f4a8  jz      loc_18032F59D
0x18032f4ae  sub     eax, 3
0x18032f4b1  jz      short loc_18032F52D
0x18032f4b3  sub     eax, 62h ; 'b'
0x18032f4b6  jz      short loc_18032F52D
0x18032f4b8  cmp     eax, 2
0x18032f4bb  jz      short loc_18032F52D
0x18032f4bd  mov     rcx, [r15+0C8h]
0x18032f4c4  mov     r8d, edx
0x18032f4c7  mov     rdx, [r15+10h]
0x18032f4cb  mov     r9, rdi
0x18032f4ce  mov     rax, [rcx]
0x18032f4d1  mov     rax, [rax+20h]
0x18032f4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032f4da  mov     rax, cs:WPP_GLOBAL_Control
0x18032f4e1  cmp     rax, r12
0x18032f4e4  jz      short loc_18032F522
0x18032f4e6  test    dword ptr [rax+1Ch], 10000h
0x18032f4ed  jz      short loc_18032F522
0x18032f4ef  cmp     byte ptr [rax+19h], 3
0x18032f4f3  jb      short loc_18032F522
0x18032f4f5  mov     ebx, dword ptr [rbp+bstrString]
0x18032f4f8  mov     r14, [r15+10h]
0x18032f4fc  call    RdpX_GetActivityIdPrefix
0x18032f501  mov     rcx, cs:WPP_GLOBAL_Control
0x18032f508  mov     edx, 76h ; 'v'
0x18032f50d  mov     [rsp+80h+dwTotalLength], ebx
0x18032f511  mov     r9d, eax
0x18032f514  mov     qword ptr [rsp+80h+dwOptionalLength], r14
0x18032f519  mov     rcx, [rcx+10h]
0x18032f51d  call    WPP_SF_DID
0x18032f522  mov     r14d, 80040303h
0x18032f528  jmp     loc_18032FBB4
0x18032f52d  mov     rcx, [r15+0C8h]
0x18032f534  mov     r8d, edx
0x18032f537  mov     rdx, [r15+10h]
0x18032f53b  mov     r9, rdi
0x18032f53e  mov     rax, [rcx]
0x18032f541  mov     rax, [rax+20h]
0x18032f545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032f54a  mov     rax, cs:WPP_GLOBAL_Control
0x18032f551  cmp     rax, r12
0x18032f554  jz      short loc_18032F592
0x18032f556  test    dword ptr [rax+1Ch], 10000h
0x18032f55d  jz      short loc_18032F592
0x18032f55f  cmp     byte ptr [rax+19h], 3
0x18032f563  jb      short loc_18032F592
0x18032f565  mov     ebx, dword ptr [rbp+bstrString]
0x18032f568  mov     r14, [r15+10h]
0x18032f56c  call    RdpX_GetActivityIdPrefix
0x18032f571  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
