# RdpWinRadcHttpRequest::PrepareRequest(void)

- ea: `0x18032fbec`
- end: `0x1803302f5`
- name: `?PrepareRequest@RdpWinRadcHttpRequest@@AEAAJXZ`
- size: `1801`
- prototype: `__int64 __fastcall(RdpWinRadcHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18032dc30`

## callees

- `0x18002a374`
- `0x180039c98`
- `0x1800e9b1c`
- `0x1801a0450`
- `0x18032c818`
- `0x18032c840`
- `0x18032e11c`
- `0x18032e4f0`
- `0x18032fbec`
- `0x180330a48`
- `0x180330dcc`
- `0x180330fd4`
- `0x180331344`
- `0x180331f0c`
- `0x180332280`
- `0x180688fc0`
- `0x180689080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18032fd2d`
- `KERNEL32!GetLastError` at `0x18032fdb7`
- `KERNEL32!GetLastError` at `0x1803300b3`
- `KERNEL32!GetLastError` at `0x180330285`
- `KERNEL32!GetLastError` at `0x18032fd2d`
- `KERNEL32!GetLastError` at `0x18032fdb7`
- `KERNEL32!GetLastError` at `0x1803300b3`
- `KERNEL32!GetLastError` at `0x180330285`
- `OLEAUT32!__imp_SysFreeString` at `0x1803302c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1803302d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1803302c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1803302d2`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18032fdab`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18032fdab`
- `WINHTTP!WinHttpOpenRequest` at `0x1803300a4`
- `WINHTTP!WinHttpOpenRequest` at `0x1803300a4`
- `WINHTTP!WinHttpConnect` at `0x18032fd1e`
- `WINHTTP!WinHttpConnect` at `0x18032fd1e`
- `WINHTTP!WinHttpSetOption` at `0x18033027b`
- `WINHTTP!WinHttpSetOption` at `0x18033027b`

## string_xrefs

- `0x18032fc30`: `application/xml`
- `0x18032fc8c`: `application/x-msts-radc-discovery+xml`
- `0x18032fcdc`: `StringCchCopyN(hostname) failed`
- `0x18032fe39`: `GetProxyConfig failed`
- `0x18032fefe`: `bstrUrlPath.Append(empty string) failed`
- `0x18032fc81`: `application/x-msts-radc+xml;radc_schema_version=2.0`
- `0x180330172`: `SetClaimsTokenIfExists failed`
- `0x18032fea6`: `bstrUrlPath.Append failed`
- `0x18033001d`: `RadcCombineUrl failed`

## pseudocode

```c
__int64 __fastcall RdpWinRadcHttpRequest::PrepareRequest(RdpWinRadcHttpRequest *this)
{
  unsigned __int64 v1; // r9
  const unsigned __int16 *v2; // r8
  __int64 v4; // rdx
  __int64 v5; // rcx
  signed int LastError; // ebx
  __int64 v7; // r8
  int ActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  void *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  const unsigned __int16 *v23; // rdx
  int v24; // r8d
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  const unsigned __int16 *v31; // rdx
  int v32; // r8d
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  unsigned int v36; // r9d
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rbx
  int v44; // eax
  int v45; // r8d
  HINTERNET v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // rdx
  int v63; // ebx
  __int64 v64; // r8
  int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-D8h]
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v72; // [rsp+48h] [rbp-B8h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v74; // [rsp+60h] [rbp-A0h]
  LPCWSTR v75[7]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pwszObjectName[2088]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pswzServerName[2088]; // [rsp+10F0h] [rbp+FF0h] BYREF

  v1 = *((unsigned int *)this + 24);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 11);
  v74 = 0;
  v72 = 0;
  v75[0] = L"application/xml";
  bstrString = 0;
  v75[1] = L"Image/*";
  v75[6] = 0;
  v75[2] = L"Application/*";
  v75[3] = L"text/*";
  v75[4] = L"application/x-msts-radc+xml;radc_schema_version=2.0";
  v75[5] = L"application/x-msts-radc-discovery+xml";
  Buffer = 0;
  LastError = StringCchCopyNW(pswzServerName, 0x824u, v2, v1);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v5, v4, v7);
      v9 = 54;
      v10 = "StringCchCopyN(hostname) failed";
LABEL_6:
      LODWORD(ppwszAcceptTypes) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
        ActivityIdPrefix,
        (__int64)v10,
        ppwszAcceptTypes);
      goto LABEL_97;
    }
    goto LABEL_97;
  }
  v11 = WinHttpConnect(*((HINTERNET *)this + 3), pswzServerName, *((_WORD *)this + 50), 0);
  *((_QWORD *)this + 4) = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v15 = RdpX_GetActivityIdPrefix(v13, v12, v14);
    v16 = 55;
    goto LABEL_12;
  }
  if ( WinHttpSetStatusCallback(v11, RdpWinRadcHttpRequest::WinHttpCallbackFn, 0x4000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v15 = RdpX_GetActivityIdPrefix(v18, v17, v19);
    v16 = 56;
    goto LABEL_12;
  }
  LastError = RdpWinRadcHttpRequest::GetProxyConfig(this, *((void **)this + 3), (struct _WINHTTP_PROXY_INFO *)&Buffer);
  if ( LastError >= 0 )
  {
    v23 = (const unsigned __int16 *)*((_QWORD *)this + 17);
    if ( v23 && (v24 = *((_DWORD *)this + 36)) != 0 )
    {
      LastError = ATL::CComBSTR::Append((ATL::CComBSTR *)&v72, v23, v24);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v26, v25, v27);
          v9 = 59;
          v10 = "bstrUrlPath.Append failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
    }
    else
    {
      LastError = ATL::CComBSTR::Append((ATL::CComBSTR *)&v72, &sourceString);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v29, v28, v30);
          v9 = 58;
          v10 = "bstrUrlPath.Append(empty string) failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
    }
    v31 = (const unsigned __int16 *)*((_QWORD *)this + 19);
    if ( v31 && (v32 = *((_DWORD *)this + 40)) != 0 )
    {
      LastError = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, v31, v32);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v34, v33, v35);
          v9 = 61;
          v10 = "bstrUrlExtraInfo.Append failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
    }
    else
    {
      LastError = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, &sourceString);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v38, v37, v39);
          v9 = 60;
          v10 = "bstrUrlExtraInfo.Append(empty string) failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
    }
    LastError = RadcCombineUrl(v72, bstrString, pwszObjectName, v36);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(v41, v40, v42);
        v9 = 62;
        v10 = "RadcCombineUrl failed";
        goto LABEL_6;
      }
      goto LABEL_97;
    }
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v43 = *((_QWORD *)this + 2);
      v44 = RdpX_GetActivityIdPrefix(v41, v40, v42);
      WPP_SF_DIS(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, v45, v44, v43, (__int64)pwszObjectName);
    }
    v46 = WinHttpOpenRequest(*((HINTERNET *)this + 4), *((LPCWSTR *)this + 6), pwszObjectName, 0, 0, v75, 0x800100u);
    *((_QWORD *)this + 5) = v46;
    if ( v46 )
    {
      LastError = RdpWinRadcHttpRequest::SetAuthCookieIfExists(this);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v51, v50, v52);
          v9 = 65;
          v10 = "SetAuthCookieIfExists failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
      LastError = RdpWinRadcHttpRequest::SetClaimsTokenIfExists(this);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v54, v53, v55);
          v9 = 66;
          v10 = "SetClaimsTokenIfExists failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
      LastError = RdpWinRadcHttpRequest::SetActivityIdIfExists(this);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v57, v56, v58);
          v9 = 67;
          v10 = "SetActivityIdIfExists failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
      LastError = RdpWinRadcHttpRequest::SetIfNoneMatchHeaderIfExists(this);
      if ( LastError < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(v60, v59, v61);
          v9 = 68;
          v10 = "SetIfNoneMatchHeaderIfExists failed";
          goto LABEL_6;
        }
        goto LABEL_97;
      }
      v63 = RdpWinRadcHttpRequest::GetAndSetClientVersionHeaders(this);
      if ( v63 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v65 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v62, v64);
        LODWORD(ppwszAcceptTypes) = v63;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
          v65,
          (__int64)"GetAndSetClientVersionHeaders failed",
          ppwszAcceptTypes);
      }
      if ( WinHttpSetOption(*((HINTERNET *)this + 5), 0x26u, &Buffer, 0x18u) )
      {
        LastError = 0;
        goto LABEL_97;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_13:
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        goto LABEL_97;
      }
      v15 = RdpX_GetActivityIdPrefix(v67, v66, v68);
      v16 = 70;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_13;
      }
      v15 = RdpX_GetActivityIdPrefix(v48, v47, v49);
      v16 = 64;
    }
LABEL_12:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
      v15,
      LastError);
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(v21, v20, v22);
    v9 = 57;
    v10 = "GetProxyConfig failed";
    goto LABEL_6;
  }
LABEL_97:
  SysFreeString(bstrString);
  SysFreeString(v72);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18032fbec  push    rbp
0x18032fbee  push    rbx
0x18032fbef  push    rsi
0x18032fbf0  push    rdi
0x18032fbf1  lea     rbp, [rsp-2058h]
0x18032fbf9  mov     eax, 2158h
0x18032fbfe  call    _alloca_probe
0x18032fc03  sub     rsp, rax
0x18032fc06  mov     rax, cs:__security_cookie
0x18032fc0d  xor     rax, rsp
0x18032fc10  mov     [rbp+2070h+var_30], rax
0x18032fc17  mov     r9d, [rcx+60h]; unsigned __int64
0x18032fc1b  xor     eax, eax
0x18032fc1d  mov     r8, [rcx+58h]; unsigned __int16 *
0x18032fc21  mov     rsi, rcx
0x18032fc24  mov     [rsp+2170h+var_2110], rax
0x18032fc29  lea     rcx, [rbp+2070h+pswzServerName]; unsigned __int16 *
0x18032fc30  lea     rax, aApplicationXml; "application/xml"
0x18032fc37  mov     [rsp+2170h+var_2128], 0
0x18032fc40  mov     [rsp+2170h+var_2108], rax
0x18032fc45  xorps   xmm0, xmm0
0x18032fc48  lea     rax, aImage; "Image/*"
0x18032fc4f  mov     [rsp+2170h+bstrString], 0
0x18032fc58  mov     [rsp+2170h+var_2100], rax
0x18032fc5d  mov     edx, 824h; unsigned __int64
0x18032fc62  lea     rax, aApplication_0; "Application/*"
0x18032fc69  mov     [rbp+2070h+var_20D8], 0
0x18032fc71  mov     [rsp+2170h+var_20F8], rax
0x18032fc76  lea     rax, aText; "text/*"
0x18032fc7d  mov     [rbp+2070h+var_20F0], rax
0x18032fc81  lea     rax, aApplicationXMs; "application/x-msts-radc+xml;radc_schema"...
0x18032fc88  mov     [rbp+2070h+var_20E8], rax
0x18032fc8c  lea     rax, aApplicationXMs_0; "application/x-msts-radc-discovery+xml"
0x18032fc93  mov     [rbp+2070h+var_20E0], rax
0x18032fc97  movups  [rsp+2170h+Buffer], xmm0
0x18032fc9c  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18032fca1  mov     ebx, eax
0x18032fca3  test    eax, eax
0x18032fca5  jns     short loc_18032FD0B
0x18032fca7  mov     rax, cs:WPP_GLOBAL_Control
0x18032fcae  lea     rdi, WPP_GLOBAL_Control
0x18032fcb5  cmp     rax, rdi
0x18032fcb8  jz      loc_1803302C2
0x18032fcbe  test    byte ptr [rax+1Ch], 8
0x18032fcc2  jz      loc_1803302C2
0x18032fcc8  cmp     byte ptr [rax+19h], 2
0x18032fccc  jb      loc_1803302C2
0x18032fcd2  call    RdpX_GetActivityIdPrefix
0x18032fcd7  mov     edx, 36h ; '6'
0x18032fcdc  lea     rcx, aStringcchcopyn_3; "StringCchCopyN(hostname) failed"
0x18032fce3  mov     dword ptr [rsp+2170h+ppwszAcceptTypes], ebx
0x18032fce7  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18032fcee  mov     [rsp+2170h+pwszReferrer], rcx
0x18032fcf3  mov     r9d, eax
0x18032fcf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18032fcfd  mov     rcx, [rcx+10h]
0x18032fd01  call    WPP_SF_DsD
0x18032fd06  jmp     loc_1803302C2
0x18032fd0b  movzx   r8d, word ptr [rsi+64h]; nServerPort
0x18032fd10  lea     rdx, [rbp+2070h+pswzServerName]; pswzServerName
0x18032fd17  mov     rcx, [rsi+18h]; hSession
0x18032fd1b  xor     r9d, r9d; dwReserved
0x18032fd1e  call    cs:__imp_WinHttpConnect
0x18032fd24  mov     [rsi+20h], rax
0x18032fd28  test    rax, rax
0x18032fd2b  jnz     short loc_18032FD98
0x18032fd2d  call    cs:__imp_GetLastError
0x18032fd33  mov     ebx, eax
0x18032fd35  mov     rax, cs:WPP_GLOBAL_Control
0x18032fd3c  lea     rdi, WPP_GLOBAL_Control
0x18032fd43  cmp     rax, rdi
0x18032fd46  jz      short loc_18032FD7C
0x18032fd48  test    byte ptr [rax+1Ch], 8
0x18032fd4c  jz      short loc_18032FD7C
0x18032fd4e  cmp     byte ptr [rax+19h], 2
0x18032fd52  jb      short loc_18032FD7C
0x18032fd54  call    RdpX_GetActivityIdPrefix
0x18032fd59  mov     edx, 37h ; '7'
0x18032fd5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18032fd65  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18032fd6c  mov     r9d, eax
0x18032fd6f  mov     dword ptr [rsp+2170h+pwszReferrer], ebx
0x18032fd73  mov     rcx, [rcx+10h]
0x18032fd77  call    WPP_SF_Dd
0x18032fd7c  test    ebx, ebx
0x18032fd7e  jle     short loc_18032FD89
0x18032fd80  movzx   ebx, bx
0x18032fd83  or      ebx, 80070000h
0x18032fd89  test    ebx, ebx
0x18032fd8b  mov     eax, 80004005h
0x18032fd90  cmovns  ebx, eax
0x18032fd93  jmp     loc_1803302C2
0x18032fd98  xor     r9d, r9d; dwReserved
0x18032fd9b  lea     rdx, ?WinHttpCallbackFn@RdpWinRadcHttpRequest@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x18032fda2  mov     r8d, 4000h; dwNotificationFlags
0x18032fda8  mov     rcx, rax; hInternet
0x18032fdab  call    cs:__imp_WinHttpSetStatusCallback
0x18032fdb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18032fdb5  jnz     short loc_18032FDED
0x18032fdb7  call    cs:__imp_GetLastError
0x18032fdbd  mov     ebx, eax
0x18032fdbf  mov     rax, cs:WPP_GLOBAL_Control
0x18032fdc6  lea     rdi, WPP_GLOBAL_Control
0x18032fdcd  cmp     rax, rdi
0x18032fdd0  jz      short loc_18032FD7C
0x18032fdd2  test    byte ptr [rax+1Ch], 8
0x18032fdd6  jz      short loc_18032FD7C
0x18032fdd8  cmp     byte ptr [rax+19h], 2
0x18032fddc  jb      short loc_18032FD7C
0x18032fdde  call    RdpX_GetActivityIdPrefix
0x18032fde3  mov     edx, 38h ; '8'
0x18032fde8  jmp     loc_18032FD5E
0x18032fded  mov     rdx, [rsi+18h]; void *
0x18032fdf1  lea     r8, [rsp+2170h+Buffer]; struct _WINHTTP_PROXY_INFO *
0x18032fdf6  mov     rcx, rsi; this
0x18032fdf9  call    ?GetProxyConfig@RdpWinRadcHttpRequest@@AEAAJPEAXPEAU_WINHTTP_PROXY_INFO@@@Z; RdpWinRadcHttpRequest::GetProxyConfig(void *,_WINHTTP_PROXY_INFO *)
0x18032fdfe  mov     ebx, eax
0x18032fe00  test    eax, eax
0x18032fe02  jns     short loc_18032FE45
0x18032fe04  mov     rax, cs:WPP_GLOBAL_Control
0x18032fe0b  lea     rdi, WPP_GLOBAL_Control
0x18032fe12  cmp     rax, rdi
0x18032fe15  jz      loc_1803302C2
0x18032fe1b  test    byte ptr [rax+1Ch], 8
0x18032fe1f  jz      loc_1803302C2
0x18032fe25  cmp     byte ptr [rax+19h], 2
0x18032fe29  jb      loc_1803302C2
0x18032fe2f  call    RdpX_GetActivityIdPrefix
0x18032fe34  mov     edx, 39h ; '9'
0x18032fe39  lea     rcx, aGetproxyconfig; "GetProxyConfig failed"
0x18032fe40  jmp     loc_18032FCE3
0x18032fe45  mov     rdx, [rsi+88h]; unsigned __int16 *
0x18032fe4c  test    rdx, rdx
0x18032fe4f  jz      short loc_18032FEB2
0x18032fe51  mov     r8d, [rsi+90h]; int
0x18032fe58  test    r8d, r8d
0x18032fe5b  jz      short loc_18032FEB2
0x18032fe5d  lea     rcx, [rsp+2170h+var_2128]; this
0x18032fe62  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18032fe67  mov     ebx, eax
0x18032fe69  test    eax, eax
0x18032fe6b  jns     loc_18032FF0A
0x18032fe71  mov     rax, cs:WPP_GLOBAL_Control
0x18032fe78  lea     rdi, WPP_GLOBAL_Control
0x18032fe7f  cmp     rax, rdi
0x18032fe82  jz      loc_1803302C2
0x18032fe88  test    byte ptr [rax+1Ch], 8
0x18032fe8c  jz      loc_1803302C2
0x18032fe92  cmp     byte ptr [rax+19h], 2
0x18032fe96  jb      loc_1803302C2
0x18032fe9c  call    RdpX_GetActivityIdPrefix
0x18032fea1  mov     edx, 3Bh ; ';'
0x18032fea6  lea     rcx, aBstrurlpathApp; "bstrUrlPath.Append failed"
0x18032fead  jmp     loc_18032FCE3
0x18032feb2  lea     rdx, sourceString; unsigned __int16 *
0x18032feb9  lea     rcx, [rsp+2170h+var_2128]; this
0x18032febe  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18032fec3  mov     ebx, eax
0x18032fec5  test    eax, eax
0x18032fec7  jns     short loc_18032FF0A
0x18032fec9  mov     rax, cs:WPP_GLOBAL_Control
0x18032fed0  lea     rdi, WPP_GLOBAL_Control
0x18032fed7  cmp     rax, rdi
0x18032feda  jz      loc_1803302C2
0x18032fee0  test    byte ptr [rax+1Ch], 8
0x18032fee4  jz      loc_1803302C2
0x18032feea  cmp     byte ptr [rax+19h], 2
0x18032feee  jb      loc_1803302C2
0x18032fef4  call    RdpX_GetActivityIdPrefix
0x18032fef9  mov     edx, 3Ah ; ':'
0x18032fefe  lea     rcx, aBstrurlpathApp_0; "bstrUrlPath.Append(empty string) failed"
0x18032ff05  jmp     loc_18032FCE3
0x18032ff0a  mov     rdx, [rsi+98h]; unsigned __int16 *
0x18032ff11  test    rdx, rdx
0x18032ff14  jz      short loc_18032FF77
0x18032ff16  mov     r8d, [rsi+0A0h]; int
0x18032ff1d  test    r8d, r8d
0x18032ff20  jz      short loc_18032FF77
0x18032ff22  lea     rcx, [rsp+2170h+bstrString]; this
0x18032ff27  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18032ff2c  mov     ebx, eax
0x18032ff2e  test    eax, eax
0x18032ff30  jns     loc_18032FFCF
0x18032ff36  mov     rax, cs:WPP_GLOBAL_Control
0x18032ff3d  lea     rdi, WPP_GLOBAL_Control
0x18032ff44  cmp     rax, rdi
0x18032ff47  jz      loc_1803302C2
0x18032ff4d  test    byte ptr [rax+1Ch], 8
0x18032ff51  jz      loc_1803302C2
0x18032ff57  cmp     byte ptr [rax+19h], 2
0x18032ff5b  jb      loc_1803302C2
0x18032ff61  call    RdpX_GetActivityIdPrefix
0x18032ff66  mov     edx, 3Dh ; '='
0x18032ff6b  lea     rcx, aBstrurlextrain; "bstrUrlExtraInfo.Append failed"
0x18032ff72  jmp     loc_18032FCE3
0x18032ff77  lea     rdx, sourceString; unsigned __int16 *
0x18032ff7e  lea     rcx, [rsp+2170h+bstrString]; this
0x18032ff83  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18032ff88  mov     ebx, eax
0x18032ff8a  test    eax, eax
0x18032ff8c  jns     short loc_18032FFCF
0x18032ff8e  mov     rax, cs:WPP_GLOBAL_Control
0x18032ff95  lea     rdi, WPP_GLOBAL_Control
0x18032ff9c  cmp     rax, rdi
0x18032ff9f  jz      loc_1803302C2
0x18032ffa5  test    byte ptr [rax+1Ch], 8
0x18032ffa9  jz      loc_1803302C2
0x18032ffaf  cmp     byte ptr [rax+19h], 2
0x18032ffb3  jb      loc_1803302C2
0x18032ffb9  call    RdpX_GetActivityIdPrefix
0x18032ffbe  mov     edx, 3Ch ; '<'
0x18032ffc3  lea     rcx, aBstrurlextrain_0; "bstrUrlExtraInfo.Append(empty string) f"...
0x18032ffca  jmp     loc_18032FCE3
0x18032ffcf  mov     rdx, [rsp+2170h+bstrString]; unsigned __int16 *
0x18032ffd4  lea     r8, [rbp+2070h+pwszObjectName]; unsigned __int16 *
0x18032ffd8  mov     rcx, [rsp+2170h+var_2128]; unsigned __int16 *
0x18032ffdd  call    ?RadcCombineUrl@@YAJPEBG0PEAGK@Z; RadcCombineUrl(ushort const *,ushort const *,ushort *,ulong)
0x18032ffe2  mov     ebx, eax
0x18032ffe4  test    eax, eax
0x18032ffe6  jns     short loc_180330029
0x18032ffe8  mov     rax, cs:WPP_GLOBAL_Control
0x18032ffef  lea     rdi, WPP_GLOBAL_Control
0x18032fff6  cmp     rax, rdi
0x18032fff9  jz      loc_1803302C2
0x18032ffff  test    byte ptr [rax+1Ch], 8
0x180330003  jz      loc_1803302C2
0x180330009  cmp     byte ptr [rax+19h], 2
0x18033000d  jb      loc_1803302C2
0x180330013  call    RdpX_GetActivityIdPrefix
0x180330018  mov     edx, 3Eh ; '>'
0x18033001d  lea     rcx, aRadccombineurl; "RadcCombineUrl failed"
0x180330024  jmp     loc_18032FCE3
0x180330029  mov     rax, cs:WPP_GLOBAL_Control
0x180330030  lea     rdi, WPP_GLOBAL_Control
0x180330037  cmp     rax, rdi
0x18033003a  jz      short loc_18033007A
0x18033003c  test    dword ptr [rax+1Ch], 10000h
0x180330043  jz      short loc_18033007A
0x180330045  cmp     byte ptr [rax+19h], 5
0x180330049  jb      short loc_18033007A
0x18033004b  mov     rbx, [rsi+10h]
0x18033004f  call    RdpX_GetActivityIdPrefix
0x180330054  lea     rcx, [rbp+2070h+pwszObjectName]
0x180330058  mov     edx, 3Fh ; '?'
0x18033005d  mov     [rsp+2170h+ppwszAcceptTypes], rcx
0x180330062  mov     r9d, eax
0x180330065  mov     rcx, cs:WPP_GLOBAL_Control
0x18033006c  mov     [rsp+2170h+pwszReferrer], rbx
0x180330071  mov     rcx, [rcx+10h]
0x180330075  call    WPP_SF_DIS
0x18033007a  mov     rdx, [rsi+30h]; pwszVerb
0x18033007e  lea     rax, [rsp+2170h+var_2108]
0x180330083  mov     rcx, [rsi+20h]; hConnect
0x180330087  lea     r8, [rbp+2070h+pwszObjectName]; pwszObjectName
0x18033008b  mov     [rsp+2170h+dwFlags], 800100h; dwFlags
0x180330093  xor     r9d, r9d; pwszVersion
0x180330096  mov     [rsp+2170h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x18033009b  mov     [rsp+2170h+pwszReferrer], 0; pwszReferrer
0x1803300a4  call    cs:__imp_WinHttpOpenRequest
0x1803300aa  mov     [rsi+28h], rax
0x1803300ae  test    rax, rax
0x1803300b1  jnz     short loc_1803300EE
0x1803300b3  call    cs:__imp_GetLastError
0x1803300b9  mov     ebx, eax
0x1803300bb  mov     rax, cs:WPP_GLOBAL_Control
0x1803300c2  cmp     rax, rdi
0x1803300c5  jz      loc_18032FD7C
0x1803300cb  test    byte ptr [rax+1Ch], 8
0x1803300cf  jz      loc_18032FD7C
0x1803300d5  cmp     byte ptr [rax+19h], 2
0x1803300d9  jb      loc_18032FD7C
0x1803300df  call    RdpX_GetActivityIdPrefix
0x1803300e4  mov     edx, 40h ; '@'
0x1803300e9  jmp     loc_18032FD5E
0x1803300ee  mov     rcx, rsi; this
0x1803300f1  call    ?SetAuthCookieIfExists@RdpWinRadcHttpRequest@@AEAAJXZ; RdpWinRadcHttpRequest::SetAuthCookieIfExists(void)
0x1803300f6  mov     ebx, eax
0x1803300f8  test    eax, eax
0x1803300fa  jns     short loc_180330136
0x1803300fc  mov     rax, cs:WPP_GLOBAL_Control
0x180330103  cmp     rax, rdi
0x180330106  jz      loc_1803302C2
0x18033010c  test    byte ptr [rax+1Ch], 8
0x180330110  jz      loc_1803302C2
0x180330116  cmp     byte ptr [rax+19h], 2
0x18033011a  jb      loc_1803302C2
0x180330120  call    RdpX_GetActivityIdPrefix
0x180330125  mov     edx, 41h ; 'A'
0x18033012a  lea     rcx, aSetauthcookiei; "SetAuthCookieIfExists failed"
0x180330131  jmp     loc_18032FCE3
0x180330136  mov     rcx, rsi; this
0x180330139  call    ?SetClaimsTokenIfExists@RdpWinRadcHttpRequest@@AEAAJXZ; RdpWinRadcHttpRequest::SetClaimsTokenIfExists(void)
0x18033013e  mov     ebx, eax
0x180330140  test    eax, eax
0x180330142  jns     short loc_18033017E
0x180330144  mov     rax, cs:WPP_GLOBAL_Control
0x18033014b  cmp     rax, rdi
0x18033014e  jz      loc_1803302C2
0x180330154  test    byte ptr [rax+1Ch], 8
0x180330158  jz      loc_1803302C2
  ... truncated ...
```
