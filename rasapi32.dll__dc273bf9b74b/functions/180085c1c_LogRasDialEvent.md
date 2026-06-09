# LogRasDialEvent

- ea: `0x180085c1c`
- end: `0x180086656`
- name: `LogRasDialEvent`
- size: `2618`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036f2c`
- `0x18003b8d0`
- `0x180075e60`
- `0x180084d10`
- `0x180087230`

## callees

- `0x1800203dc`
- `0x1800307e0`
- `0x18004e580`
- `0x18004e984`
- `0x18007e3a8`
- `0x18007f140`
- `0x180083620`
- `0x180085c1c`
- `0x1800c131c`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800dee10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800865de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800865de`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180085dc6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180085dc6`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180085e8a`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180086102`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18008636c`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x1800865aa`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180085e8a`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180086102`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18008636c`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x1800865aa`
- `rasman!RasIsTrustedCustomDll` at `0x180086433`
- `rasman!RasIsTrustedCustomDll` at `0x180086433`

## pseudocode

```c
HRESULT __fastcall LogRasDialEvent(unsigned int a1, const GUID *a2, __int64 a3)
{
  _QWORD *v6; // rbx
  HRESULT result; // eax
  __int64 v8; // rdx
  DWORD v9; // r9d
  DWORD v10; // r9d
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rbx
  DWORD LastError; // eax
  const wchar_t *v15; // r8
  bool v16; // zf
  const wchar_t *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rbx
  DWORD v20; // eax
  WORD wNumStrings; // [rsp+28h] [rbp-D8h]
  LPCWSTR Strings[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpStrings[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h]
  __int128 v26; // [rsp+90h] [rbp-70h]
  OLECHAR sz[128]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t pszDest[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t v29[1024]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v30[2048]; // [rsp+BB0h] [rbp+AB0h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, a1);
    v6 = WPP_GLOBAL_Control;
  }
  memset_0(pszDest, 0, 0x202u);
  result = (unsigned int)memset_0(sz, 0, sizeof(sz));
  if ( !hRasClientEventLog )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    {
      v8 = 219;
      return WPP_SF_(v6[2], v8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    }
    return result;
  }
  if ( !::pszDest && dword_1800FE004 != 1312 )
    GetWkstaUserInfo();
  if ( g_dwTraceId != -1 )
    TracePrintfW1("GetLogonUser=%s", &::pszDest);
  if ( !word_1800FE7F8 && dword_1800FE004 != 1312 )
    GetWkstaUserInfo();
  if ( g_dwTraceId != -1 )
    TracePrintfW1("GetLogonDomain=%s", &word_1800FE7F8);
  result = StringCchPrintfW(pszDest, 0x101u, L"%s\\%s", &word_1800FE7F8, &::pszDest);
  if ( pszDest[0] == 92 )
    result = StringCchCopyW(pszDest, 0x101u, L"SYSTEM");
  if ( a2 )
    result = StringFromGUID2(a2, sz, 128);
  switch ( a1 )
  {
    case 1u:
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      *(_OWORD *)lpStrings = 0;
      v25 = 0;
      v26 = 0;
      memset_0(v29, 0, 0x202u);
      result = (unsigned int)memset_0(v30, 0, sizeof(v30));
      LODWORD(Strings[0]) = 0;
      if ( *(_DWORD *)(a3 + 4872) || *(_DWORD *)(a3 + 4868) )
        goto LABEL_116;
      ConstructEventMessage(1, v30, 1024, a3);
      RasIsTrustedCustomDll(0, *(_QWORD *)(*(_QWORD *)(a3 + 1584) + 448LL), Strings);
      if ( LODWORD(Strings[0]) )
      {
        v15 = L"Connection Manager";
      }
      else
      {
        switch ( *(_DWORD *)(*(_QWORD *)(a3 + 1584) + 24LL) )
        {
          case 1:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            }
            v15 = L"Dial-up";
            break;
          case 2:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            }
            v15 = L"VPN";
            break;
          case 5:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            }
            v15 = L"Broadband";
            break;
          default:
LABEL_111:
            v16 = *(_DWORD *)(a3 + 1528) == 0;
            lpStrings[0] = sz;
            lpStrings[1] = pszDest;
            *(_QWORD *)&v25 = v29;
            v17 = L"all-user";
            if ( !v16 )
              v17 = L"per-user";
            *((_QWORD *)&v25 + 1) = v17;
            v18 = *(_QWORD *)(*(_QWORD *)(a3 + 1584) + 8LL);
            *((_QWORD *)&v26 + 1) = v30;
            *(_QWORD *)&v26 = v18;
            result = ReportEventW(hRasClientEventLog, 4u, 0, 0x4EFDu, 0, 6u, 0, lpStrings, 0);
            goto LABEL_114;
        }
      }
      StringCchCopyW(v29, 0x101u, v15);
      goto LABEL_111;
    case 2u:
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      *(_OWORD *)Strings = 0;
      v23 = 0;
      result = (unsigned int)memset_0(v29, 0, sizeof(v29));
      if ( !*(_DWORD *)(a3 + 4868) )
      {
        ConstructEventMessage(2, v29, 1024, a3);
        v10 = 20222;
        Strings[0] = sz;
        Strings[1] = pszDest;
        *(_QWORD *)&v23 = *(_QWORD *)(*(_QWORD *)(a3 + 1584) + 8LL);
LABEL_82:
        *((_QWORD *)&v23 + 1) = v29;
LABEL_83:
        result = ReportEventW(hRasClientEventLog, 4u, 0, v10, 0, 4u, 0, Strings, 0);
        goto LABEL_114;
      }
      goto LABEL_116;
    case 3u:
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      *(_QWORD *)&v23 = 0;
      *(_OWORD *)Strings = 0;
      result = (unsigned int)memset_0(v29, 0, sizeof(v29));
      if ( *(_DWORD *)(a3 + 4868) )
        goto LABEL_116;
      ConstructEventMessage(3, v29, 1024, a3);
      Strings[0] = sz;
      v9 = 20223;
      Strings[1] = pszDest;
      *(_QWORD *)&v23 = v29;
      wNumStrings = 3;
LABEL_37:
      result = ReportEventW(hRasClientEventLog, 4u, 0, v9, 0, wNumStrings, 0, Strings, 0);
      goto LABEL_114;
    case 4u:
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      if ( *(_DWORD *)(a3 + 4868) )
        goto LABEL_116;
      Strings[0] = sz;
      v9 = 20224;
      Strings[1] = pszDest;
      wNumStrings = 2;
      goto LABEL_37;
  }
  if ( a1 != 5 )
  {
    if ( a1 != 6 )
    {
      if ( a1 != 7 )
      {
        if ( a1 != 8 )
        {
LABEL_115:
          v6 = WPP_GLOBAL_Control;
          goto LABEL_116;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        }
        Strings[0] = (LPCWSTR)(a3 + 304);
        v9 = 20291;
        wNumStrings = 1;
        goto LABEL_37;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      }
      v23 = 0;
      memset_0(v29, 0, 0x100u);
      StringCchPrintfW(v29, 0x80u, L"%d", 631);
      *(_QWORD *)&v23 = a3;
      Strings[0] = sz;
      v10 = 20226;
      Strings[1] = pszDest;
      goto LABEL_82;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    }
    *(_OWORD *)Strings = 0;
    v23 = 0;
    memset_0(v29, 0, 0x100u);
    v11 = 0;
    if ( !*(_DWORD *)(a3 + 4868) )
      v11 = *(unsigned int *)(a3 + 344);
    StringCchPrintfW(v29, 0x80u, L"%d", v11);
    Strings[0] = sz;
    Strings[1] = pszDest;
    v12 = *(_QWORD *)(*(_QWORD *)(a3 + 1584) + 8LL);
    *((_QWORD *)&v23 + 1) = v29;
    *(_QWORD *)&v23 = v12;
    result = ReportEventW(hRasClientEventLog, 1u, 0, 0x4F03u, 0, 4u, 0, Strings, 0);
LABEL_114:
    if ( result )
    {
LABEL_120:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_121;
    }
    goto LABEL_115;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  *(_OWORD *)Strings = 0;
  v23 = 0;
  result = (unsigned int)memset_0(v29, 0, sizeof(v29));
  if ( !*(_DWORD *)(a3 + 4868) )
  {
    ConstructEventMessage(5, v29, 1024, a3);
    Strings[0] = sz;
    Strings[1] = pszDest;
    *(_QWORD *)&v23 = *(_QWORD *)(*(_QWORD *)(a3 + 1584) + 8LL);
    *((_QWORD *)&v23 + 1) = v29;
    if ( *(_DWORD *)(a3 + 384) == 1
      && (*(_BYTE *)(a3 + 536) & 3) == 3
      && !ReportEventW(hRasClientEventLog, 4u, 0, 0x4F39u, 0, 1u, 0, Strings, 0)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_Dd(v13, 228, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, 20281, LastError);
    }
    v10 = 20225;
    goto LABEL_83;
  }
LABEL_116:
  if ( v6 == &WPP_GLOBAL_Control )
    return result;
  if ( (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    v19 = v6[2];
    v20 = GetLastError();
    result = WPP_SF_Dd(v19, 232, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, a1, v20);
    goto LABEL_120;
  }
LABEL_121:
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x800) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v8 = 233;
    return WPP_SF_(v6[2], v8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180085c1c  mov     [rsp-8+arg_18], rbx
0x180085c21  push    rbp
0x180085c22  push    rsi
0x180085c23  push    rdi
0x180085c24  push    r12
0x180085c26  push    r13
0x180085c28  push    r14
0x180085c2a  push    r15
0x180085c2c  lea     rbp, [rsp-12C0h]
0x180085c34  mov     eax, 13C0h
0x180085c39  call    _alloca_probe
0x180085c3e  sub     rsp, rax
0x180085c41  mov     rax, cs:__security_cookie
0x180085c48  xor     rax, rsp
0x180085c4b  mov     [rbp+12F0h+var_40], rax
0x180085c52  mov     rdi, r8
0x180085c55  mov     rsi, rdx
0x180085c58  mov     r14d, ecx
0x180085c5b  mov     rbx, cs:WPP_GLOBAL_Control
0x180085c62  lea     r13, WPP_GLOBAL_Control
0x180085c69  mov     r12d, 800h
0x180085c6f  cmp     rbx, r13
0x180085c72  jz      short loc_180085C9F
0x180085c74  test    [rbx+1Ch], r12d
0x180085c78  jz      short loc_180085C9F
0x180085c7a  cmp     byte ptr [rbx+19h], 6
0x180085c7e  jb      short loc_180085C9F
0x180085c80  mov     r9d, ecx
0x180085c83  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180085c8a  mov     rcx, [rbx+10h]
0x180085c8e  mov     edx, 0DAh
0x180085c93  call    WPP_SF_d
0x180085c98  mov     rbx, cs:WPP_GLOBAL_Control
0x180085c9f  xor     edx, edx; Val
0x180085ca1  lea     rcx, [rbp+12F0h+pszDest]; void *
0x180085ca8  mov     r8d, 202h; Size
0x180085cae  call    memset_0
0x180085cb3  xor     edx, edx; Val
0x180085cb5  lea     rcx, [rbp+12F0h+sz]; void *
0x180085cb9  mov     r8d, 100h; Size
0x180085cbf  call    memset_0
0x180085cc4  xor     r15d, r15d
0x180085cc7  cmp     cs:hRasClientEventLog, r15
0x180085cce  jnz     short loc_180085CFB
0x180085cd0  cmp     rbx, r13
0x180085cd3  jz      loc_18008662C
0x180085cd9  test    [rbx+1Ch], r12d
0x180085cdd  jz      loc_18008662C
0x180085ce3  lea     edi, [r15+6]
0x180085ce7  cmp     [rbx+19h], dil
0x180085ceb  jb      loc_18008662C
0x180085cf1  mov     edx, 0DBh
0x180085cf6  jmp     loc_18008661C
0x180085cfb  cmp     cs:pszDest, r15w
0x180085d03  mov     ebx, 520h
0x180085d08  jnz     short loc_180085D17
0x180085d0a  cmp     cs:dword_1800FE004, ebx
0x180085d10  jz      short loc_180085D17
0x180085d12  call    GetWkstaUserInfo
0x180085d17  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180085d1e  jz      short loc_180085D33
0x180085d20  lea     rdx, pszDest; lpWideCharStr
0x180085d27  lea     rcx, aGetlogonuserS; "GetLogonUser=%s"
0x180085d2e  call    TracePrintfW1
0x180085d33  cmp     cs:word_1800FE7F8, r15w
0x180085d3b  jnz     short loc_180085D4A
0x180085d3d  cmp     cs:dword_1800FE004, ebx
0x180085d43  jz      short loc_180085D4A
0x180085d45  call    GetWkstaUserInfo
0x180085d4a  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x180085d51  jz      short loc_180085D66
0x180085d53  lea     rdx, word_1800FE7F8; lpWideCharStr
0x180085d5a  lea     rcx, aGetlogondomain; "GetLogonDomain=%s"
0x180085d61  call    TracePrintfW1
0x180085d66  lea     rax, pszDest
0x180085d6d  mov     ebx, 101h
0x180085d72  mov     edx, ebx; cchDest
0x180085d74  mov     [rsp+13F0h+lpUserSid], rax
0x180085d79  lea     r9, word_1800FE7F8
0x180085d80  lea     r8, aSS_2; "%s\\%s"
0x180085d87  lea     rcx, [rbp+12F0h+pszDest]; pszDest
0x180085d8e  call    StringCchPrintfW
0x180085d93  cmp     [rbp+12F0h+pszDest], 5Ch ; '\'
0x180085d9b  jnz     short loc_180085DB2
0x180085d9d  lea     r8, aSystem; "SYSTEM"
0x180085da4  mov     edx, ebx; cchDest
0x180085da6  lea     rcx, [rbp+12F0h+pszDest]; pszDest
0x180085dad  call    StringCchCopyW
0x180085db2  mov     ebx, 80h
0x180085db7  test    rsi, rsi
0x180085dba  jz      short loc_180085DCC
0x180085dbc  mov     r8d, ebx; cchMax
0x180085dbf  lea     rdx, [rbp+12F0h+sz]; lpsz
0x180085dc3  mov     rcx, rsi; rguid
0x180085dc6  call    cs:__imp_StringFromGUID2
0x180085dcc  mov     ecx, r14d
0x180085dcf  mov     esi, 2
0x180085dd4  sub     ecx, 1
0x180085dd7  jz      loc_18008637C
0x180085ddd  sub     ecx, 1
0x180085de0  jz      loc_180086290
0x180085de6  sub     ecx, 1
0x180085de9  jz      loc_1800861CE
0x180085def  sub     ecx, 1
0x180085df2  jz      loc_180086154
0x180085df8  sub     ecx, 1
0x180085dfb  jz      loc_180086003
0x180085e01  sub     ecx, 1
0x180085e04  jz      loc_180085F30
0x180085e0a  sub     ecx, 1
0x180085e0d  jz      loc_180085E9A
0x180085e13  cmp     ecx, 1
0x180085e16  jnz     loc_1800865B6
0x180085e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180085e23  cmp     rcx, r13
0x180085e26  jz      short loc_180085E49
0x180085e28  test    [rcx+1Ch], r12d
0x180085e2c  jz      short loc_180085E49
0x180085e2e  cmp     byte ptr [rcx+19h], 5
0x180085e32  jb      short loc_180085E49
0x180085e34  mov     rcx, [rcx+10h]
0x180085e38  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180085e3f  mov     edx, 0E7h
0x180085e44  call    WPP_SF_
0x180085e49  mov     [rsp+13F0h+lpRawData], r15; lpRawData
0x180085e4e  lea     rax, [rdi+130h]
0x180085e55  mov     [rsp+13F0h+Strings], rax
0x180085e5a  mov     r9d, 4F43h; dwEventID
0x180085e60  lea     rax, [rsp+13F0h+Strings]
0x180085e65  mov     [rsp+13F0h+lpStrings], rax; lpStrings
0x180085e6a  mov     [rsp+13F0h+dwDataSize], r15d; dwDataSize
0x180085e6f  mov     [rsp+13F0h+wNumStrings], 1; wNumStrings
0x180085e76  mov     edx, 4; wType
0x180085e7b  mov     rcx, cs:hRasClientEventLog; hEventLog
0x180085e82  xor     r8d, r8d; wCategory
0x180085e85  mov     [rsp+13F0h+lpUserSid], r15; lpUserSid
0x180085e8a  call    cs:__imp_ReportEventW
0x180085e90  mov     edi, 6
0x180085e95  jmp     loc_1800865B0
0x180085e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180085ea1  cmp     rcx, r13
0x180085ea4  jz      short loc_180085EC7
0x180085ea6  test    [rcx+1Ch], r12d
0x180085eaa  jz      short loc_180085EC7
0x180085eac  cmp     byte ptr [rcx+19h], 5
0x180085eb0  jb      short loc_180085EC7
0x180085eb2  mov     rcx, [rcx+10h]
0x180085eb6  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180085ebd  mov     edx, 0E6h
0x180085ec2  call    WPP_SF_
0x180085ec7  xorps   xmm0, xmm0
0x180085eca  lea     rcx, [rbp+12F0h+var_1040]; void *
0x180085ed1  xor     edx, edx; Val
0x180085ed3  mov     r8d, 100h; Size
0x180085ed9  movups  xmmword ptr [rsp+13F0h+Strings], xmm0
0x180085ede  movups  [rsp+13F0h+var_1390], xmm0
0x180085ee3  call    memset_0
0x180085ee8  mov     r9d, 277h
0x180085eee  lea     r8, aD; "%d"
0x180085ef5  mov     rdx, rbx; cchDest
0x180085ef8  lea     rcx, [rbp+12F0h+var_1040]; pszDest
0x180085eff  call    StringCchPrintfW
0x180085f04  lea     rax, [rbp+12F0h+sz]
0x180085f08  mov     qword ptr [rsp+13F0h+var_1390], rdi
0x180085f0d  mov     [rsp+13F0h+Strings], rax
0x180085f12  mov     r9d, 4F02h
0x180085f18  lea     rax, [rbp+12F0h+pszDest]
0x180085f1f  mov     [rsp+13F0h+Strings+8], rax
0x180085f24  lea     rax, [rbp+12F0h+var_1040]
0x180085f2b  jmp     loc_180086338
0x180085f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180085f37  cmp     rcx, r13
0x180085f3a  jz      short loc_180085F5D
0x180085f3c  test    [rcx+1Ch], r12d
0x180085f40  jz      short loc_180085F5D
0x180085f42  cmp     byte ptr [rcx+19h], 5
0x180085f46  jb      short loc_180085F5D
0x180085f48  mov     rcx, [rcx+10h]
0x180085f4c  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180085f53  mov     edx, 0E5h
0x180085f58  call    WPP_SF_
0x180085f5d  xorps   xmm0, xmm0
0x180085f60  lea     rcx, [rbp+12F0h+var_1040]; void *
0x180085f67  xor     edx, edx; Val
0x180085f69  mov     r8d, 100h; Size
0x180085f6f  movups  xmmword ptr [rsp+13F0h+Strings], xmm0
0x180085f74  movups  [rsp+13F0h+var_1390], xmm0
0x180085f79  call    memset_0
0x180085f7e  mov     r9d, r15d
0x180085f81  cmp     [rdi+1304h], r15d
0x180085f88  jnz     short loc_180085F91
0x180085f8a  mov     r9d, [rdi+158h]
0x180085f91  lea     r8, aD; "%d"
0x180085f98  mov     rdx, rbx; cchDest
0x180085f9b  lea     rcx, [rbp+12F0h+var_1040]; pszDest
0x180085fa2  call    StringCchPrintfW
0x180085fa7  mov     [rsp+13F0h+lpRawData], r15
0x180085fac  lea     rax, [rbp+12F0h+sz]
0x180085fb0  mov     [rsp+13F0h+Strings], rax
0x180085fb5  mov     edx, 1
0x180085fba  lea     rax, [rbp+12F0h+pszDest]
0x180085fc1  mov     r9d, 4F03h
0x180085fc7  mov     [rsp+13F0h+Strings+8], rax
0x180085fcc  mov     rax, [rdi+630h]
0x180085fd3  mov     rcx, [rax+8]
0x180085fd7  lea     rax, [rbp+12F0h+var_1040]
0x180085fde  mov     qword ptr [rsp+13F0h+var_1390+8], rax
0x180085fe3  lea     rax, [rsp+13F0h+Strings]
0x180085fe8  mov     [rsp+13F0h+lpStrings], rax
0x180085fed  mov     [rsp+13F0h+dwDataSize], r15d
0x180085ff2  mov     [rsp+13F0h+wNumStrings], 4
0x180085ff9  mov     qword ptr [rsp+13F0h+var_1390], rcx
0x180085ffe  jmp     loc_180085E7B
0x180086003  mov     rbx, cs:WPP_GLOBAL_Control
0x18008600a  cmp     rbx, r13
0x18008600d  jz      short loc_180086037
0x18008600f  test    [rbx+1Ch], r12d
0x180086013  jz      short loc_180086037
0x180086015  cmp     byte ptr [rbx+19h], 5
0x180086019  jb      short loc_180086037
0x18008601b  mov     rcx, [rbx+10h]
0x18008601f  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180086026  mov     edx, 0E3h
0x18008602b  call    WPP_SF_
0x180086030  mov     rbx, cs:WPP_GLOBAL_Control
0x180086037  xorps   xmm0, xmm0
0x18008603a  lea     rcx, [rbp+12F0h+var_1040]; void *
0x180086041  mov     r8, r12; Size
0x180086044  xor     edx, edx; Val
0x180086046  movups  xmmword ptr [rsp+13F0h+Strings], xmm0
0x18008604b  movups  [rsp+13F0h+var_1390], xmm0
0x180086050  call    memset_0
0x180086055  cmp     [rdi+1304h], r15d
0x18008605c  jnz     loc_1800865C4
0x180086062  mov     r9, rdi
0x180086065  lea     rdx, [rbp+12F0h+var_1040]
0x18008606c  mov     r8d, 400h
0x180086072  mov     ecx, 5
0x180086077  call    ConstructEventMessage
0x18008607c  lea     rax, [rbp+12F0h+sz]
0x180086080  mov     esi, 4
0x180086085  mov     [rsp+13F0h+Strings], rax
0x18008608a  lea     rax, [rbp+12F0h+pszDest]
0x180086091  mov     [rsp+13F0h+Strings+8], rax
0x180086096  mov     rax, [rdi+630h]
0x18008609d  mov     rcx, [rax+8]
0x1800860a1  lea     rax, [rbp+12F0h+var_1040]
0x1800860a8  mov     qword ptr [rsp+13F0h+var_1390], rcx
0x1800860ad  lea     ecx, [rsi-3]
0x1800860b0  mov     qword ptr [rsp+13F0h+var_1390+8], rax
0x1800860b5  cmp     [rdi+180h], ecx
0x1800860bb  jnz     loc_180086149
0x1800860c1  mov     eax, [rdi+218h]
0x1800860c7  lea     ebx, [rsi-1]
0x1800860ca  and     eax, ebx
0x1800860cc  cmp     al, bl
0x1800860ce  jnz     short loc_180086149
0x1800860d0  mov     [rsp+13F0h+lpRawData], r15; lpRawData
0x1800860d5  lea     rax, [rsp+13F0h+Strings]
0x1800860da  mov     [rsp+13F0h+lpStrings], rax; lpStrings
0x1800860df  mov     edi, 4F39h
0x1800860e4  mov     [rsp+13F0h+dwDataSize], r15d; dwDataSize
0x1800860e9  xor     r8d, r8d; wCategory
0x1800860ec  mov     [rsp+13F0h+wNumStrings], cx; wNumStrings
0x1800860f1  mov     edx, esi; wType
0x1800860f3  mov     rcx, cs:hRasClientEventLog; hEventLog
0x1800860fa  mov     r9d, edi; dwEventID
0x1800860fd  mov     [rsp+13F0h+lpUserSid], r15; lpUserSid
0x180086102  call    cs:__imp_ReportEventW
0x180086108  test    eax, eax
0x18008610a  jnz     short loc_180086149
0x18008610c  mov     rbx, cs:WPP_GLOBAL_Control
0x180086113  cmp     rbx, r13
0x180086116  jz      short loc_180086149
0x180086118  test    [rbx+1Ch], r12d
0x18008611c  jz      short loc_180086149
0x18008611e  cmp     byte ptr [rbx+19h], 2
0x180086122  jb      short loc_180086149
0x180086124  mov     rbx, [rbx+10h]
0x180086128  call    cs:__imp_GetLastError
0x18008612e  mov     edx, 0E4h
0x180086133  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008613a  mov     r9d, edi
0x18008613d  mov     dword ptr [rsp+13F0h+lpUserSid], eax
0x180086141  mov     rcx, rbx
0x180086144  call    WPP_SF_Dd
0x180086149  mov     r9d, 4F01h
0x18008614f  jmp     loc_180086342
0x180086154  mov     rbx, cs:WPP_GLOBAL_Control
0x18008615b  cmp     rbx, r13
0x18008615e  jz      short loc_180086188
0x180086160  test    [rbx+1Ch], r12d
0x180086164  jz      short loc_180086188
0x180086166  cmp     byte ptr [rbx+19h], 5
0x18008616a  jb      short loc_180086188
0x18008616c  mov     rcx, [rbx+10h]
0x180086170  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180086177  mov     edx, 0E2h
0x18008617c  call    WPP_SF_
0x180086181  mov     rbx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
