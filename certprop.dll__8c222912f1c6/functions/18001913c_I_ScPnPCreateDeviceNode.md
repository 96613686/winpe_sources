# I_ScPnPCreateDeviceNode

- ea: `0x18001913c`
- end: `0x18001979e`
- name: `I_ScPnPCreateDeviceNode`
- size: `1634`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180006a40`

## callees

- `0x180004600`
- `0x18000db90`
- `0x180016090`
- `0x180016a66`
- `0x180018b58`
- `0x180018bb4`
- `0x180018d78`
- `0x18001913c`
- `0x180019ed8`
- `0x18001add8`
- `0x180021c00`
- `0x180021c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196ab`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019699`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019699`
- `WinSCard!SCardConnectW` at `0x180019376`
- `WinSCard!SCardConnectW` at `0x180019376`
- `WinSCard!SCardReconnect` at `0x1800193c7`
- `WinSCard!SCardReconnect` at `0x1800193c7`
- `WinSCard!SCardDisconnect` at `0x1800193f0`
- `WinSCard!SCardDisconnect` at `0x1800193f0`
- `WinSCard!SCardGetDeviceTypeIdW` at `0x1800195f9`
- `WinSCard!SCardGetDeviceTypeIdW` at `0x1800195f9`
- `WinSCard!SCardReleaseContext` at `0x180019400`
- `WinSCard!SCardReleaseContext` at `0x180019724`
- `WinSCard!SCardReleaseContext` at `0x180019400`
- `WinSCard!SCardReleaseContext` at `0x180019724`
- `WinSCard!SCardEstablishContext` at `0x180019342`
- `WinSCard!SCardEstablishContext` at `0x18001959f`
- `WinSCard!SCardEstablishContext` at `0x180019342`
- `WinSCard!SCardEstablishContext` at `0x18001959f`

## pseudocode

```c
__int64 __fastcall I_ScPnPCreateDeviceNode(STRSAFE_LPCWSTR pszSrc, __int64 a2, unsigned int a3)
{
  const wchar_t *v6; // r12
  const wchar_t *v7; // r14
  __int64 v8; // rcx
  STRSAFE_LPSTR v9; // rcx
  int v10; // r8d
  int v11; // r9d
  STRSAFE_LPSTR v12; // rcx
  int v13; // edx
  const char *v14; // rax
  __int64 v15; // rcx
  int DeviceId; // ebx
  __int64 v17; // rax
  __int64 v18; // rcx
  STRSAFE_LPSTR v19; // rcx
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rcx
  char v26; // al
  void *v27; // rcx
  __int64 v28; // rcx
  DWORD LastError; // eax
  int v30; // r9d
  SCARDCONTEXT v31; // rcx
  unsigned int DeviceTypeIdW; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwActiveProtocol; // [rsp+44h] [rbp-BCh] BYREF
  int v35; // [rsp+48h] [rbp-B8h] BYREF
  SCARDHANDLE hCard; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  SCARDCONTEXT phContext; // [rsp+70h] [rbp-90h] BYREF
  SCARDCONTEXT hContext; // [rsp+78h] [rbp-88h] BYREF
  wchar_t InBuffer[128]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v43[128]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t pszDest[128]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t v45[96]; // [rsp+380h] [rbp+280h] BYREF
  __int16 v46; // [rsp+440h] [rbp+340h]
  bool v47; // [rsp+442h] [rbp+342h]
  char v48; // [rsp+443h] [rbp+343h]
  STRSAFE_LPCWSTR v49; // [rsp+450h] [rbp+350h]
  int v50; // [rsp+458h] [rbp+358h]
  int v51; // [rsp+45Ch] [rbp+35Ch]
  unsigned int *v52; // [rsp+460h] [rbp+360h]
  __int64 v53; // [rsp+468h] [rbp+368h]

  DeviceTypeIdW = 0;
  memset_0(InBuffer, 0, 0x3C4u);
  BytesReturned = 0;
  v6 = 0;
  v38 = 0;
  v7 = 0;
  v39 = 0;
  hContext = 0;
  v35 = 0;
  WppTraceIndent(v8, 0);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  if ( !pszSrc )
  {
    WppTraceIndent(v9, 2);
    DeviceTypeIdW = -2146435068;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v13 = 11;
      v14 = "NULL != pScPnPDeviceListNode";
LABEL_10:
      WPP_SF_ss(*((_QWORD *)v12 + 2), v13, v10, v11, (__int64)v14);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  if ( a3 <= 0x24 )
  {
    v47 = g_fScPnPNotification == 0;
    DeviceTypeIdW = StringCchCopyW(pszDest, 0x80u, g_wszDeviceNodeDescription);
    if ( DeviceTypeIdW )
    {
      WppTraceIndent(v15, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent,
          DeviceTypeIdW);
      }
      goto LABEL_77;
    }
    phContext = 0;
    hCard = 0;
    pdwActiveProtocol = 0;
    if ( a2 && a3 - 2 <= 0x22 )
    {
      DeviceId = SCardEstablishContext(0, 0, 0, &phContext);
      if ( !DeviceId )
      {
        DeviceId = SCardConnectW(phContext, pszSrc, 2u, 3u, &hCard, &pdwActiveProtocol);
        if ( !DeviceId )
        {
          do
          {
            DeviceId = CidUtilGetDeviceId(hCard, a2, a3, &v38, (wchar_t **)&v39, pdwActiveProtocol);
            if ( DeviceId != -2146434968 )
              break;
            DeviceId = SCardReconnect(hCard, 2u, 3u, 0, 0);
          }
          while ( !DeviceId );
          v6 = v38;
          v7 = (const wchar_t *)v39;
        }
      }
    }
    else
    {
      DeviceId = 87;
    }
    if ( hCard )
      SCardDisconnect(hCard, 0);
    if ( phContext )
      SCardReleaseContext(phContext);
    DeviceTypeIdW = DeviceId;
    if ( DeviceId )
    {
      v49 = pszSrc;
      v17 = -1;
      do
        ++v17;
      while ( pszSrc[v17] );
      v51 = 0;
      v50 = 2 * v17 + 2;
      v53 = 4;
      v52 = &DeviceTypeIdW;
      I_ScPnPEvtLogWrite(&EVENT_DEVICEID_FAILED);
      goto LABEL_73;
    }
    DeviceTypeIdW = StringCchCopyW(InBuffer, 0x80u, v6);
    if ( DeviceTypeIdW )
    {
      WppTraceIndent(v18, 2);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_73;
      }
      v20 = 14;
    }
    else if ( v7 && (DeviceTypeIdW = StringCchCopyW(v43, 0x80u, v7)) != 0 )
    {
      WppTraceIndent(v21, 2);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_73;
      }
      v20 = 15;
    }
    else
    {
      DeviceTypeIdW = StringCchCopyW(v45, 0x60u, pszSrc);
      if ( DeviceTypeIdW )
      {
        WppTraceIndent(v22, 2);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_73;
        }
        v20 = 16;
      }
      else
      {
        DeviceTypeIdW = SCardEstablishContext(0, 0, 0, &hContext);
        if ( DeviceTypeIdW )
        {
          WppTraceIndent(v23, 2);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[28] & 1) == 0
            || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
          {
            goto LABEL_73;
          }
          v20 = 17;
        }
        else
        {
          DeviceTypeIdW = SCardGetDeviceTypeIdW(hContext, pszSrc, &v35, v24);
          if ( !DeviceTypeIdW )
          {
            if ( v35 == 128 )
            {
              v26 = 1;
              v46 = 0;
            }
            else
            {
              v26 = 0;
              v46 = 257;
            }
            v27 = (void *)*((_QWORD *)pszSrc + 24);
            v48 = v26;
            if ( DeviceIoControl(v27, 0x310FA0u, InBuffer, 0x3C4u, 0, 0, &BytesReturned, 0) )
            {
              *((_DWORD *)pszSrc + 50) = 1;
            }
            else
            {
              WppTraceIndent(v28, 2);
              LastError = GetLastError();
              DeviceTypeIdW = LastError;
              if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control[28] & 1) != 0
                && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  19,
                  (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
                  v30,
                  LastError);
              }
            }
            goto LABEL_73;
          }
          WppTraceIndent(v25, 2);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[28] & 1) == 0
            || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
          {
LABEL_73:
            if ( v6 )
              CidUtilFreeMemory(v6);
            if ( v7 )
              CidUtilFreeMemory(v7);
            goto LABEL_77;
          }
          v20 = 18;
        }
      }
    }
    WPP_SF_sD(
      *((_QWORD *)v19 + 2),
      v20,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      DeviceTypeIdW);
    goto LABEL_73;
  }
  WppTraceIndent(v9, 2);
  DeviceTypeIdW = -2146435068;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    v13 = 12;
    v14 = "MAX_ATR_LEN >= cbAtr";
    goto LABEL_10;
  }
LABEL_77:
  v31 = hContext;
  if ( hContext )
    SCardReleaseContext(hContext);
  WppTraceIndent(v31, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      DeviceTypeIdW);
  }
  return DeviceTypeIdW;
}

```

## disassembly

```asm
0x18001913c  mov     [rsp-8+arg_18], rbx
0x180019141  push    rbp
0x180019142  push    rsi
0x180019143  push    rdi
0x180019144  push    r12
0x180019146  push    r13
0x180019148  push    r14
0x18001914a  push    r15
0x18001914c  lea     rbp, [rsp-380h]
0x180019154  sub     rsp, 480h
0x18001915b  mov     rax, cs:__security_cookie
0x180019162  xor     rax, rsp
0x180019165  mov     [rbp+3B0h+var_40], rax
0x18001916c  mov     esi, r8d
0x18001916f  mov     r15, rdx
0x180019172  mov     rdi, rcx
0x180019175  xor     r13d, r13d
0x180019178  xor     edx, edx; Val
0x18001917a  mov     [rsp+4B0h+var_470], r13d
0x18001917f  mov     r8d, 3C4h; Size
0x180019185  lea     rcx, [rbp+3B0h+InBuffer]; void *
0x180019189  call    memset_0
0x18001918e  xor     edx, edx
0x180019190  mov     [rsp+4B0h+BytesReturned], r13d
0x180019195  mov     r12d, r13d
0x180019198  mov     [rsp+4B0h+var_450], r13
0x18001919d  mov     r14d, r13d
0x1800191a0  mov     [rsp+4B0h+var_448], r13
0x1800191a5  mov     [rsp+4B0h+hContext], r13
0x1800191aa  mov     [rsp+4B0h+var_468], r13d
0x1800191af  call    WppTraceIndent
0x1800191b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191bb  lea     rbx, WPP_GLOBAL_Control
0x1800191c2  cmp     rcx, rbx
0x1800191c5  jz      short loc_1800191EE
0x1800191c7  test    byte ptr [rcx+1Ch], 2
0x1800191cb  jz      short loc_1800191EE
0x1800191cd  cmp     byte ptr [rcx+19h], 5
0x1800191d1  jb      short loc_1800191EE
0x1800191d3  mov     r9, cs:WPP_pszIndent
0x1800191da  lea     edx, [r13+0Ah]
0x1800191de  mov     rcx, [rcx+10h]
0x1800191e2  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x1800191e9  call    WPP_SF_s
0x1800191ee  test    rdi, rdi
0x1800191f1  jnz     short loc_180019244
0x1800191f3  lea     edx, [rdi+2]
0x1800191f6  call    WppTraceIndent
0x1800191fb  mov     [rsp+4B0h+var_470], 80100004h
0x180019203  mov     rcx, cs:WPP_GLOBAL_Control
0x18001920a  cmp     rcx, rbx
0x18001920d  jz      loc_18001971A
0x180019213  test    byte ptr [rcx+1Ch], 1
0x180019217  jz      loc_18001971A
0x18001921d  cmp     byte ptr [rcx+19h], 2
0x180019221  jb      loc_18001971A
0x180019227  lea     edx, [rdi+0Bh]
0x18001922a  lea     rax, aNullPscpnpdevi; "NULL != pScPnPDeviceListNode"
0x180019231  mov     rcx, [rcx+10h]
0x180019235  mov     [rsp+4B0h+phCard], rax
0x18001923a  call    WPP_SF_ss
0x18001923f  jmp     loc_18001971A
0x180019244  cmp     esi, 24h ; '$'
0x180019247  jbe     short loc_18001928D
0x180019249  mov     edx, 2
0x18001924e  call    WppTraceIndent
0x180019253  mov     [rsp+4B0h+var_470], 80100004h
0x18001925b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019262  cmp     rcx, rbx
0x180019265  jz      loc_18001971A
0x18001926b  test    byte ptr [rcx+1Ch], 1
0x18001926f  jz      loc_18001971A
0x180019275  cmp     byte ptr [rcx+19h], 2
0x180019279  jb      loc_18001971A
0x18001927f  mov     edx, 0Ch
0x180019284  lea     rax, aMaxAtrLenCbatr; "MAX_ATR_LEN >= cbAtr"
0x18001928b  jmp     short loc_180019231
0x18001928d  cmp     cs:g_fScPnPNotification, r13b
0x180019294  lea     rcx, [rbp+3B0h+pszDest]; pszDest
0x18001929b  mov     r8, cs:g_wszDeviceNodeDescription; pszSrc
0x1800192a2  mov     edx, 80h; cchDest
0x1800192a7  setz    [rbp+3B0h+var_6E]
0x1800192ae  call    StringCchCopyW
0x1800192b3  mov     [rsp+4B0h+var_470], eax
0x1800192b7  test    eax, eax
0x1800192b9  jz      short loc_180019312
0x1800192bb  mov     edx, 2
0x1800192c0  call    WppTraceIndent
0x1800192c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192cc  cmp     rcx, rbx
0x1800192cf  jz      loc_18001971A
0x1800192d5  test    byte ptr [rcx+1Ch], 1
0x1800192d9  jz      loc_18001971A
0x1800192df  cmp     byte ptr [rcx+19h], 2
0x1800192e3  jb      loc_18001971A
0x1800192e9  mov     eax, [rsp+4B0h+var_470]
0x1800192ed  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x1800192f4  mov     r9, cs:WPP_pszIndent
0x1800192fb  mov     edx, 0Dh
0x180019300  mov     rcx, [rcx+10h]
0x180019304  mov     dword ptr [rsp+4B0h+phCard], eax
0x180019308  call    WPP_SF_sD
0x18001930d  jmp     loc_18001971A
0x180019312  mov     [rsp+4B0h+phContext], r13
0x180019317  mov     [rsp+4B0h+hCard], r13
0x18001931c  mov     [rsp+4B0h+var_46C], r13d
0x180019321  test    r15, r15
0x180019324  jz      loc_1800193DF
0x18001932a  lea     eax, [rsi-2]
0x18001932d  cmp     eax, 22h ; '"'
0x180019330  ja      loc_1800193DF
0x180019336  lea     r9, [rsp+4B0h+phContext]; phContext
0x18001933b  xor     r8d, r8d; pvReserved2
0x18001933e  xor     edx, edx; pvReserved1
0x180019340  xor     ecx, ecx; dwScope
0x180019342  call    cs:__imp_SCardEstablishContext
0x180019348  mov     ebx, eax
0x18001934a  test    eax, eax
0x18001934c  jnz     loc_1800193E4
0x180019352  mov     rcx, [rsp+4B0h+phContext]; hContext
0x180019357  lea     rax, [rsp+4B0h+var_46C]
0x18001935c  mov     [rsp+4B0h+pdwActiveProtocol], rax; pdwActiveProtocol
0x180019361  lea     r9d, [rbx+3]; dwPreferredProtocols
0x180019365  lea     rax, [rsp+4B0h+hCard]
0x18001936a  mov     rdx, rdi; szReader
0x18001936d  lea     r8d, [rbx+2]; dwShareMode
0x180019371  mov     [rsp+4B0h+phCard], rax; phCard
0x180019376  call    cs:__imp_SCardConnectW
0x18001937c  mov     ebx, eax
0x18001937e  test    eax, eax
0x180019380  jnz     short loc_1800193E4
0x180019382  mov     eax, [rsp+4B0h+var_46C]
0x180019386  lea     r9, [rsp+4B0h+var_450]
0x18001938b  mov     rcx, [rsp+4B0h+hCard]; hCard
0x180019390  mov     r8d, esi
0x180019393  mov     dword ptr [rsp+4B0h+pdwActiveProtocol], eax; int
0x180019397  mov     rdx, r15
0x18001939a  lea     rax, [rsp+4B0h+var_448]
0x18001939f  mov     [rsp+4B0h+phCard], rax; __int64
0x1800193a4  call    CidUtilGetDeviceId
0x1800193a9  mov     ebx, eax
0x1800193ab  cmp     eax, 80100068h
0x1800193b0  jnz     short loc_1800193D3
0x1800193b2  mov     rcx, [rsp+4B0h+hCard]; hCard
0x1800193b7  xor     r9d, r9d; dwInitialization
0x1800193ba  mov     [rsp+4B0h+phCard], r13; pdwActiveProtocol
0x1800193bf  lea     edx, [r9+2]; dwShareMode
0x1800193c3  lea     r8d, [r9+3]; dwPreferredProtocols
0x1800193c7  call    cs:__imp_SCardReconnect
0x1800193cd  mov     ebx, eax
0x1800193cf  test    eax, eax
0x1800193d1  jz      short loc_180019382
0x1800193d3  mov     r12, [rsp+4B0h+var_450]
0x1800193d8  mov     r14, [rsp+4B0h+var_448]
0x1800193dd  jmp     short loc_1800193E4
0x1800193df  mov     ebx, 57h ; 'W'
0x1800193e4  mov     rcx, [rsp+4B0h+hCard]; hCard
0x1800193e9  test    rcx, rcx
0x1800193ec  jz      short loc_1800193F6
0x1800193ee  xor     edx, edx; dwDisposition
0x1800193f0  call    cs:__imp_SCardDisconnect
0x1800193f6  mov     rcx, [rsp+4B0h+phContext]; hContext
0x1800193fb  test    rcx, rcx
0x1800193fe  jz      short loc_180019406
0x180019400  call    cs:__imp_SCardReleaseContext
0x180019406  mov     [rsp+4B0h+var_470], ebx
0x18001940a  test    ebx, ebx
0x18001940c  jz      short loc_180019466
0x18001940e  mov     [rbp+3B0h+var_60], rdi
0x180019415  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019419  inc     rax
0x18001941c  cmp     [rdi+rax*2], r13w
0x180019421  jnz     short loc_180019419
0x180019423  lea     eax, ds:2[rax*2]
0x18001942a  mov     [rbp+3B0h+var_54], r13d
0x180019431  mov     [rbp+3B0h+var_58], eax
0x180019437  lea     r8, [rbp+3B0h+var_60]
0x18001943e  lea     rax, [rsp+4B0h+var_470]
0x180019443  mov     [rbp+3B0h+var_48], 4
0x18001944e  lea     rcx, EVENT_DEVICEID_FAILED; EventDescriptor
0x180019455  mov     [rbp+3B0h+var_50], rax
0x18001945c  call    I_ScPnPEvtLogWrite
0x180019461  jmp     loc_1800196F9
0x180019466  mov     ebx, 80h
0x18001946b  lea     rcx, [rbp+3B0h+InBuffer]; pszDest
0x18001946f  mov     edx, ebx; cchDest
0x180019471  mov     r8, r12; pszSrc
0x180019474  call    StringCchCopyW
0x180019479  mov     [rsp+4B0h+var_470], eax
0x18001947d  test    eax, eax
0x18001947f  jz      short loc_1800194DD
0x180019481  lea     edx, [rbx-7Eh]
0x180019484  call    WppTraceIndent
0x180019489  mov     rcx, cs:WPP_GLOBAL_Control
0x180019490  lea     rbx, WPP_GLOBAL_Control
0x180019497  cmp     rcx, rbx
0x18001949a  jz      loc_180019700
0x1800194a0  test    byte ptr [rcx+1Ch], 1
0x1800194a4  jz      loc_180019700
0x1800194aa  cmp     byte ptr [rcx+19h], 2
0x1800194ae  jb      loc_180019700
0x1800194b4  mov     edx, 0Eh
0x1800194b9  mov     eax, [rsp+4B0h+var_470]
0x1800194bd  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x1800194c4  mov     r9, cs:WPP_pszIndent
0x1800194cb  mov     rcx, [rcx+10h]
0x1800194cf  mov     dword ptr [rsp+4B0h+phCard], eax
0x1800194d3  call    WPP_SF_sD
0x1800194d8  jmp     loc_180019700
0x1800194dd  test    r14, r14
0x1800194e0  jz      short loc_180019538
0x1800194e2  mov     r8, r14; pszSrc
0x1800194e5  lea     rcx, [rbp+3B0h+var_330]; pszDest
0x1800194ec  mov     rdx, rbx; cchDest
0x1800194ef  call    StringCchCopyW
0x1800194f4  mov     [rsp+4B0h+var_470], eax
0x1800194f8  test    eax, eax
0x1800194fa  jz      short loc_180019538
0x1800194fc  mov     edx, 2
0x180019501  call    WppTraceIndent
0x180019506  mov     rcx, cs:WPP_GLOBAL_Control
0x18001950d  lea     rbx, WPP_GLOBAL_Control
0x180019514  cmp     rcx, rbx
0x180019517  jz      loc_180019700
0x18001951d  test    byte ptr [rcx+1Ch], 1
0x180019521  jz      loc_180019700
0x180019527  cmp     byte ptr [rcx+19h], 2
0x18001952b  jb      loc_180019700
0x180019531  mov     edx, 0Fh
0x180019536  jmp     short loc_1800194B9
0x180019538  mov     r8, rdi; pszSrc
0x18001953b  lea     rcx, [rbp+3B0h+var_130]; pszDest
0x180019542  mov     edx, 60h ; '`'; cchDest
0x180019547  call    StringCchCopyW
0x18001954c  mov     [rsp+4B0h+var_470], eax
0x180019550  test    eax, eax
0x180019552  jz      short loc_180019593
0x180019554  mov     edx, 2
0x180019559  call    WppTraceIndent
0x18001955e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019565  lea     rbx, WPP_GLOBAL_Control
0x18001956c  cmp     rcx, rbx
0x18001956f  jz      loc_180019700
0x180019575  test    byte ptr [rcx+1Ch], 1
0x180019579  jz      loc_180019700
0x18001957f  cmp     byte ptr [rcx+19h], 2
0x180019583  jb      loc_180019700
0x180019589  mov     edx, 10h
0x18001958e  jmp     loc_1800194B9
0x180019593  lea     r9, [rsp+4B0h+hContext]; phContext
0x180019598  xor     r8d, r8d; pvReserved2
0x18001959b  xor     edx, edx; pvReserved1
0x18001959d  xor     ecx, ecx; dwScope
0x18001959f  call    cs:__imp_SCardEstablishContext
0x1800195a5  mov     [rsp+4B0h+var_470], eax
0x1800195a9  test    eax, eax
0x1800195ab  jz      short loc_1800195EC
0x1800195ad  mov     edx, 2
0x1800195b2  call    WppTraceIndent
0x1800195b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195be  lea     rbx, WPP_GLOBAL_Control
0x1800195c5  cmp     rcx, rbx
0x1800195c8  jz      loc_180019700
0x1800195ce  test    byte ptr [rcx+1Ch], 1
0x1800195d2  jz      loc_180019700
0x1800195d8  cmp     byte ptr [rcx+19h], 2
0x1800195dc  jb      loc_180019700
0x1800195e2  mov     edx, 11h
0x1800195e7  jmp     loc_1800194B9
0x1800195ec  mov     rcx, [rsp+4B0h+hContext]
0x1800195f1  lea     r8, [rsp+4B0h+var_468]
0x1800195f6  mov     rdx, rdi
0x1800195f9  call    cs:__imp_SCardGetDeviceTypeIdW
0x1800195ff  mov     [rsp+4B0h+var_470], eax
0x180019603  test    eax, eax
0x180019605  jz      short loc_180019646
0x180019607  mov     edx, 2
0x18001960c  call    WppTraceIndent
0x180019611  mov     rcx, cs:WPP_GLOBAL_Control
0x180019618  lea     rbx, WPP_GLOBAL_Control
0x18001961f  cmp     rcx, rbx
0x180019622  jz      loc_180019700
0x180019628  test    byte ptr [rcx+1Ch], 1
0x18001962c  jz      loc_180019700
0x180019632  cmp     byte ptr [rcx+19h], 2
0x180019636  jb      loc_180019700
0x18001963c  mov     edx, 12h
0x180019641  jmp     loc_1800194B9
0x180019646  cmp     [rsp+4B0h+var_468], ebx
0x18001964a  jnz     short loc_180019658
0x18001964c  mov     al, 1
0x18001964e  mov     [rbp+3B0h+var_70], r13w
0x180019656  jmp     short loc_180019664
0x180019658  mov     al, r13b
0x18001965b  mov     [rbp+3B0h+var_70], 101h
0x180019664  mov     rcx, [rdi+0C0h]; hDevice
0x18001966b  lea     r8, [rbp+3B0h+InBuffer]; lpInBuffer
0x18001966f  mov     [rsp+4B0h+lpOverlapped], r13; lpOverlapped
0x180019674  mov     r9d, 3C4h; nInBufferSize
0x18001967a  mov     [rbp+3B0h+var_6D], al
  ... truncated ...
```
