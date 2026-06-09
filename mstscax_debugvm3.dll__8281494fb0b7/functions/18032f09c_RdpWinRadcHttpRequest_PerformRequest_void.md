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
- `0x18032f14c`: `Content-Type: application/xml\n`
- `0x18032f143`: `Content-Type: application/json\n`
- `0x18032f13a`: `Content-Type: application/json; charset=utf-16\n`
- `0x18032fa63`: `ReadResponseBody failed`

## pseudocode

```c
__int64 __fastcall RdpWinRadcHttpRequest::PerformRequest(RdpWinRadcHttpRequest *this, __int64 a2, __int64 a3)
{
  int v3; // r12d
  int v5; // ecx
  wchar_t *v6; // rdi
  unsigned __int16 *v7; // rsi
  int v8; // ecx
  __int64 v9; // rcx
  unsigned int v10; // r14d
  int ActivityIdPrefix; // eax
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rcx
  DWORD v14; // ebx
  const WCHAR **v15; // rax
  OLECHAR *v16; // rbx
  const WCHAR *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  signed int LastError; // ebx
  __int64 v24; // r8
  HKEY v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rdx
  bool v28; // sf
  __int64 v29; // rbx
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rbx
  unsigned int v35; // eax
  int v36; // eax
  bool ShouldEndEarly; // al
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  int v44; // ebx
  __int64 v45; // r14
  unsigned int v46; // eax
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  int v51; // ebx
  __int64 v52; // r14
  unsigned int v53; // eax
  __int64 v54; // r8
  HKEY v55; // rax
  __int64 v56; // rbx
  unsigned int v57; // eax
  unsigned int v58; // eax
  OLECHAR *v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  int v63; // eax
  int v64; // edx
  const char *v65; // rcx
  __int64 v66; // rbx
  unsigned int v67; // eax
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // rbx
  unsigned int v79; // eax
  __int64 v80; // rbx
  unsigned int v81; // eax
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rbx
  unsigned int v86; // eax
  unsigned int v87; // eax
  size_t v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  int v92; // ebx
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // r8
  __int64 v96; // rbx
  int v97; // r8d
  int v98; // r9d
  const wchar_t *v99; // rax
  int v100; // eax
  __int64 v101; // rbx
  unsigned int v102; // eax
  __int64 v103; // r8
  int v104; // eax
  int v105; // eax
  DWORD dwTotalLength[2]; // [rsp+28h] [rbp-58h]
  DWORD dwTotalLengtha[2]; // [rsp+28h] [rbp-58h]
  DWORD dwBufferLength; // [rsp+50h] [rbp-30h] BYREF
  wchar_t *String; // [rsp+58h] [rbp-28h] BYREF
  BSTR v111; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v112; // [rsp+68h] [rbp-18h] BYREF
  LPVOID lpOptional; // [rsp+70h] [rbp-10h]
  BSTR v114; // [rsp+78h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+40h] BYREF
  DWORD dwOptionalLength; // [rsp+C8h] [rbp+48h]
  BSTR v117; // [rsp+D0h] [rbp+50h] BYREF
  DWORD v118; // [rsp+D8h] [rbp+58h]

  v3 = 0;
  dwBufferLength = 4;
  LODWORD(bstrString) = 0;
  v5 = *((_DWORD *)this + 55);
  v6 = 0;
  String = 0;
  v7 = 0;
  v111 = 0;
  v112 = 0;
  if ( v5 )
  {
    v8 = v5 - 1;
    if ( v8 )
    {
      v9 = (unsigned int)(v8 - 1);
      if ( (_DWORD)v9 )
      {
        if ( (_DWORD)v9 != 1 )
        {
          v10 = -2147418113;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(v9, a2, a3);
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
        v12 = L"Content-Type: application/json; charset=utf-16\r\n";
      }
      else
      {
        v12 = L"Content-Type: application/json\r\n";
      }
    }
    else
    {
      v12 = L"Content-Type: application/xml\r\n";
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v111, v12);
  }
  if ( RdpWinRadcHttpRequest::ShouldEndEarly(this) )
  {
    v10 = 1;
    goto LABEL_161;
  }
  v13 = *((_QWORD *)this + 26);
  v14 = *((_DWORD *)this + 54);
  v118 = v14;
  if ( v13 )
  {
    lpOptional = (LPVOID)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
    dwOptionalLength = v14;
  }
  else
  {
    lpOptional = 0;
    dwOptionalLength = 0;
  }
  v10 = 1;
  if ( *((_QWORD *)this + 26) )
  {
    v15 = (const WCHAR **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v114, (const struct ATL::CComBSTR *)&v111);
    v16 = bstrString;
    v3 = 1;
    LODWORD(v117) = 0;
    v17 = *v15;
  }
  else
  {
    v16 = 0;
    LODWORD(v117) = 2;
    v17 = 0;
  }
  dwOptionalLength = WinHttpSendRequest(
                       *((HINTERNET *)this + 5),
                       v17,
                       0,
                       lpOptional,
                       dwOptionalLength,
                       v118,
                       (DWORD_PTR)this);
  if ( (_DWORD)v117 )
    SysFreeString(v16);
  if ( v3 )
    SysFreeString(v114);
  if ( !dwOptionalLength )
  {
    LastError = GetLastError();
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = RdpX_GetActivityIdPrefix(v22, v21, v24);
      v27 = 97;
LABEL_30:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
        v26,
        LastError);
      v25 = WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v29 = *((_QWORD *)this + 2);
    v30 = RdpX_GetActivityIdPrefix(v19, v18, v20);
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v30, v29);
  }
  if ( !RdpWinRadcHttpRequest::ShouldEndEarly(this) )
  {
    if ( !WinHttpReceiveResponse(*((HINTERNET *)this + 5), 0) )
    {
      LastError = GetLastError();
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = RdpX_GetActivityIdPrefix(v22, v21, v24);
        v27 = 99;
        goto LABEL_30;
      }
LABEL_31:
      v28 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v28 = LastError < 0;
      }
      if ( !v28 )
      {
        v10 = -2147467259;
        goto LABEL_161;
      }
      goto LABEL_144;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v34 = *((_QWORD *)this + 2);
      v35 = RdpX_GetActivityIdPrefix(v32, v31, v33);
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v35, v34);
    }
    if ( !RdpWinRadcHttpRequest::ShouldEndEarly(this) )
    {
      if ( !WinHttpQueryHeaders(*((HINTERNET *)this + 5), 0x20000013u, 0, &bstrString, &dwBufferLength, 0) )
      {
        LastError = GetLastError();
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = RdpX_GetActivityIdPrefix(v22, v21, v24);
          v27 = 101;
          goto LABEL_30;
        }
        goto LABEL_31;
      }
      LastError = RdpWinRadcHttpRequest::GetHttpHeaderFromResponse(this, 1u, &String);
      if ( LastError < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v36 = RdpX_GetActivityIdPrefix(v22, v21, v24);
          dwTotalLength[0] = LastError;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
            v36,
            (__int64)"GetHttpHeaderFromResponse(WINHTTP_QUERY_CONTENT_TYPE) failed",
            *(_QWORD *)dwTotalLength);
          v6 = String;
LABEL_143:
          v25 = WPP_GLOBAL_Control;
          goto LABEL_144;
        }
        v6 = String;
LABEL_144:
        v10 = LastError;
        if ( LastError == -2147012881 || LastError == -2147012864 )
        {
          if ( v25 != (HKEY)&WPP_GLOBAL_Control && ((_DWORD)v25[7] & 0x10000) != 0 && *((_BYTE *)v25 + 25) >= 4u )
          {
            v101 = *((_QWORD *)this + 2);
            v102 = RdpX_GetActivityIdPrefix(v22, v21, v24);
            WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, v103, v102, v101, v10);
          }
          v10 = -2147220731;
        }
        goto LABEL_161;
      }
      ShouldEndEarly = RdpWinRadcHttpRequest::ShouldEndEarly(this);
      v6 = String;
      if ( ShouldEndEarly )
        goto LABEL_161;
      v40 = (unsigned int)bstrString;
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
            v85 = *((_QWORD *)this + 2);
            v86 = RdpX_GetActivityIdPrefix(v83, v82, v84);
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v86,
              v85);
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
                v51 = (int)bstrString;
                v52 = *((_QWORD *)this + 2);
                v53 = RdpX_GetActivityIdPrefix(v49, v48, v50);
                WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, v54, v53, v52, v51);
              }
              v10 = -2147220734;
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
                v44 = (int)bstrString;
                v45 = *((_QWORD *)this + 2);
                v46 = RdpX_GetActivityIdPrefix(v42, v41, v43);
                WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, v47, v46, v45, v44);
              }
              v10 = -2147220733;
            }
            goto LABEL_161;
          }
          v117 = 0;
          v55 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v56 = *((_QWORD *)this + 2);
            v57 = RdpX_GetActivityIdPrefix(v38, (unsigned int)bstrString, v39);
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v57,
              v56);
            v55 = WPP_GLOBAL_Control;
          }
          if ( !*((_BYTE *)this + 184) )
          {
            if ( v55 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v55[7] & 8) != 0 && *((_BYTE *)v55 + 25) >= 2u )
            {
              v58 = RdpX_GetActivityIdPrefix(v38, v40, v39);
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                110,
                &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
                v58,
                -2147467263);
            }
            v59 = 0;
            v10 = -2147467263;
            goto LABEL_88;
          }
          LastError = RdpWinRadcHttpRequest::TryFindClaimsAuthChallenge(this, &v117);
          if ( LastError < 0 )
          {
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_95;
            }
            v63 = RdpX_GetActivityIdPrefix(v61, v60, v62);
            v64 = 111;
            v65 = "TryFindClaimsAuthChallenge failed";
LABEL_94:
            dwTotalLength[0] = LastError;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v64,
              (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v63,
              (__int64)v65,
              *(_QWORD *)dwTotalLength);
LABEL_95:
            SysFreeString(v117);
            goto LABEL_143;
          }
          if ( LastError )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v66 = *((_QWORD *)this + 2);
              v67 = RdpX_GetActivityIdPrefix(v61, v60, v62);
              WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v68, v67, v66, -2147220968);
            }
            v10 = -2147220968;
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
            v63 = RdpX_GetActivityIdPrefix(v70, v69, v71);
            v64 = 113;
            v65 = "SetClaimsTokenIfExists failed";
            goto LABEL_94;
          }
          if ( RdpWinRadcHttpRequest::ShouldEndEarly(this) )
          {
LABEL_102:
            v59 = v117;
LABEL_88:
            SysFreeString(v59);
            goto LABEL_161;
          }
          if ( LastError != 1 )
          {
            v10 = -2147220731;
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v80 = *((_QWORD *)this + 2);
              v81 = RdpX_GetActivityIdPrefix(v73, v72, v74);
              WPP_SF_Dq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                115,
                &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
                v81,
                v80);
            }
            goto LABEL_102;
          }
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, BSTR))(**((_QWORD **)this + 25) + 32LL))(
            *((_QWORD *)this + 25),
            *((_QWORD *)this + 2),
            dwOptionalLength,
            v117);
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v78 = *((_QWORD *)this + 2);
            v79 = RdpX_GetActivityIdPrefix(v76, v75, v77);
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              114,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v79,
              v78);
          }
          SysFreeString(v117);
        }
LABEL_115:
        v10 = 0;
        goto LABEL_161;
      }
      LastError = RdpWinRadcHttpRequest::GetETagFromHttpResponse(this, &v112);
      if ( LastError == -2147012746 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v87 = RdpX_GetActivityIdPrefix(v22, v21, v24);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v87);
        }
      }
      else if ( LastError < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v104 = RdpX_GetActivityIdPrefix(v22, v21, v24);
          dwTotalLength[0] = LastError;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
            v104,
            (__int64)"GetHttpHeaderFromResponse(WINHTTP_QUERY_CONTENT_TYPE) failed",
            *(_QWORD *)dwTotalLength);
          v25 = WPP_GLOBAL_Control;
        }
        v7 = v112;
        goto LABEL_144;
      }
      v7 = v112;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, wchar_t *, unsigned __int16 *))(**((_QWORD **)this + 25) + 24LL))(
        *((_QWORD *)this + 25),
        *((_QWORD *)this + 2),
        dwOptionalLength,
        v6,
        v112);
      v88 = wcscspn(v6, L";");
      v92 = v88;
      if ( v88 <= 0x7FFFFFFF )
      {
        if ( CompareStringEx(&sourceString, 1u, v6, v88, L"application/x-msts-webfeed-login", -1, 0, 0, 0) != 2 )
          LOBYTE(v10) = CompareStringEx(
                          &sourceString,
                          1u,
                          v6,
                          v92,
                          L"application/x-msts-webfeed-discovery-login",
                          -1,
                          0,
                          0,
                          0) == 2;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v96 = *((_QWORD *)this + 2);
          v98 = RdpX_GetActivityIdPrefix(v94, v93, v95);
          v99 = L"is";
          if ( !(_BYTE)v10 )
            v99 = (const wchar_t *)L"is not";
          WPP_SF_DIS(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, v97, v98, v96, (__int64)v99);
        }
        LastError = RdpWinRadcHttpRequest::ReadResponseBody(this, v10);
        if ( LastError < 0 )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v100 = RdpX_GetActivityIdPrefix(v22, v21, v24);
            dwTotalLengtha[0] = LastError;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              108,
              (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v100,
              (__int64)"ReadResponseBody failed",
              *(_QWORD *)dwTotalLengtha);
            goto LABEL_143;
          }
          goto LABEL_144;
        }
        goto LABEL_115;
      }
      v10 = -2147024362;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v105 = RdpX_GetActivityIdPrefix(v90, v89, v91);
        dwTotalLength[0] = -2147024362;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
          v105,
          (__int64)"SizeTToInt failed",
          *(_QWORD *)dwTotalLength);
      }
    }
  }
LABEL_161:
  SysFreeString(v7);
  SysFreeString(v111);
  SysFreeString(v6);
  return v10;
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
