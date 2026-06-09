# EAPSession::doAction(IASTL::IASRequest &)

- ea: `0x1800194b8`
- end: `0x180019e35`
- name: `?doAction@EAPSession@@IEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z`
- size: `2429`
- prototype: ``
- caller_count: `4`
- callee_count: `30`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800194b8`
- `0x18001ae80`
- `0x18001b084`
- `0x18001b170`

## callees

- `0x180001c88`
- `0x18000a760`
- `0x18000acf4`
- `0x18000b82c`
- `0x18000c28c`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000c808`
- `0x18000d49c`
- `0x18000d604`
- `0x18000e9d0`
- `0x1800141a4`
- `0x1800187b8`
- `0x180018aac`
- `0x180018b10`
- `0x180018c60`
- `0x180018de4`
- `0x180018f04`
- `0x18001934c`
- `0x1800194b8`
- `0x18001a808`
- `0x18001aa00`
- `0x18001b958`
- `0x18001c018`
- `0x1800254a0`
- `0x180025e38`
- `0x180025e60`
- `0x18002944c`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019a29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c87`

## string_xrefs

- `0x180019733`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x180019821`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x1800199c4`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x180019d84`: `Issuing Access-Challenge.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EAPSession::doAction(__int64 a1, struct IAttributesRaw **a2)
{
  PVOID *v4; // rdx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ebx
  DWORD v11; // eax
  unsigned int v12; // r14d
  unsigned int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // r9d
  int v16; // ebx
  unsigned int v17; // eax
  int v19; // ebx
  int v20; // ebx
  unsigned int v21; // eax
  __int64 v22; // rcx
  void *v23; // rcx
  _BYTE *v24; // rax
  unsigned int v25; // r15d
  int v26; // ebx
  unsigned __int16 v27; // r9
  unsigned int v28; // edi
  bool v29; // al
  void *v30; // rbx
  void *v31; // rcx
  int v32; // ebx
  __int64 *v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rdx
  unsigned int v36; // [rsp+20h] [rbp-E0h]
  unsigned int *v37; // [rsp+28h] [rbp-D8h]
  struct _EAP_ERROR *v38; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v39; // [rsp+48h] [rbp-B8h] BYREF
  struct _EAP_ERROR *v40[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v42; // [rsp+70h] [rbp-90h]
  char Buffer[256]; // [rsp+80h] [rbp-80h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Processing output from EAP: action:%d");
    v36 = *(_DWORD *)(a1 + 344);
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_69033002015f3c629418a4473ed337be_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *(_DWORD *)(a1 + 344);
  if ( !v5 )
  {
LABEL_107:
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u && (*((_BYTE *)v4 + 28) & 4) != 0 )
    {
      WppDbgPrint("Discarding packet.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
    }
    v35 = 5;
    v34 = 1;
LABEL_112:
    IASTL::IASRequest::SetResponse(a2, v35, v34);
    return 0;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    LODWORD(v38) = 0;
    LODWORD(v39) = 0;
    v40[0] = 0;
    v31 = *(void **)(a1 + 192);
    if ( v31 )
      CoTaskMemFree(v31);
    v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _EAP_ERROR **, __int64, LPVOID *, struct _EAP_ERROR **))(**(_QWORD **)(a1 + 352) + 56LL))(
            *(_QWORD *)(a1 + 352),
            *(unsigned int *)(a1 + 348),
            &v38,
            a1 + 192,
            &v39,
            v40);
    if ( v32 < 0 )
    {
      FreeEAPError(v40[0]);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("EapHostAuthenticatorSendPacket returned 0x%x");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_69033002015f3c629418a4473ed337be_Traceguids);
      }
      _com_issue_error(v32);
    }
    v33 = &EAPSession::theInteractiveTimeout;
    if ( (_DWORD)v39 != 2 )
      v33 = &EAPSession::theNormalTimeout;
    IASTL::IASAttribute::store((IASTL::IASAttribute *)v33, a2[1]);
    InjectPacket((struct IASTL::IASRequest *)a2, *(const struct _PPP_EAP_PACKET **)(a1 + 192), 4u);
    IASTL::IASAttribute::store((IASTL::IASAttribute *)(a1 + 168), a2[1]);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Issuing Access-Challenge.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
    }
    v34 = 0;
    v35 = 3;
    goto LABEL_112;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 == 1 )
        {
          if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 4u && (*((_BYTE *)v4 + 28) & 4) != 0 )
          {
            WppDbgPrint("EAP Host  invoked default authenticator.");
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
          }
          v38 = 0;
          FreeEAPAttributes((struct _EAP_ATTRIBUTES *)(a1 + 320));
          v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, struct _EAP_ERROR **, unsigned int))(**(_QWORD **)(a1 + 352) + 64LL))(
                  *(_QWORD *)(a1 + 352),
                  *(unsigned int *)(a1 + 348),
                  a1 + 320,
                  &v38,
                  v36);
          if ( v10 < 0 )
          {
            FreeEAPError(v38);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WppDbgPrint("EapHostAuthenticatorGetAttributes failed with 0x%x");
              WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_69033002015f3c629418a4473ed337be_Traceguids);
            }
            _com_issue_error(v10);
          }
          v11 = AuthenticateUser(*(struct _IASATTRIBUTE **)(a1 + 160), (struct _EAP_ATTRIBUTES *)(a1 + 320));
          *(_DWORD *)(a1 + 340) = v11;
          if ( v11 )
          {
            v13 = IASFormatSysErr(v11, Buffer);
            if ( v13 >= 0x100uLL )
              _report_rangecheckfailure(v14);
            Buffer[v13] = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
              WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"Default authentication", (__int64)Buffer);
            }
            v12 = 2;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WppDbgPrint("Default authentication succeeded.");
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                52,
                WPP_69033002015f3c629418a4473ed337be_Traceguids,
                "NPSSVC");
            }
            v12 = 1;
          }
          FreeEAPAttributes((struct _EAP_ATTRIBUTES *)(a1 + 304));
          EAPTranslator::translate(
            (EAPTranslator *)(a1 + 304),
            (struct _EAP_ATTRIBUTES *)(a1 + 224),
            (const struct IASTL::IASAttributeVector *)v12,
            v15);
          v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64, struct _EAP_ERROR **))(**(_QWORD **)(a1 + 352) + 80LL))(
                  *(_QWORD *)(a1 + 352),
                  *(unsigned int *)(a1 + 348),
                  *(unsigned int *)(a1 + 340),
                  a1 + 304,
                  a1 + 344,
                  &v38);
          if ( v16 < 0 )
          {
            FreeEAPError(v38);
            v17 = IASFormatSysErr(v16, Buffer);
            if ( v17 < 0x100uLL )
            {
              Buffer[v17] = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
                WPP_SF_sss(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  (__int64)"EapHostAuthenticatorSetAuthenticateResult",
                  (__int64)Buffer);
              }
              _com_issue_error(v16);
            }
            _report_rangecheckfailure(v17);
          }
          return EAPSession::doAction(a1, a2);
        }
        goto LABEL_107;
      }
    }
    FreeEAPAttributes((struct _EAP_ATTRIBUTES *)(a1 + 320));
    v38 = 0;
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, struct _EAP_ERROR **, unsigned int))(**(_QWORD **)(a1 + 352)
                                                                                                 + 64LL))(
            *(_QWORD *)(a1 + 352),
            *(unsigned int *)(a1 + 348),
            a1 + 320,
            &v38,
            v36);
    if ( v19 < 0 )
    {
      FreeEAPError(v38);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("EapHostAuthenticatorGetAttributes failed with 0x%x");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_69033002015f3c629418a4473ed337be_Traceguids);
      }
      _com_issue_error(v19);
    }
    if ( *(_DWORD *)(a1 + 344) == 3 )
      return EAPSession::onIndicateTLV(a1, a2);
    else
      return EAPSession::onIndicateIdentity(a1, a2);
  }
  else
  {
    *(_OWORD *)pv = 0;
    v42 = 0;
    v38 = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID *, struct _EAP_ERROR **))(**(_QWORD **)(a1 + 352) + 88LL))(
            *(_QWORD *)(a1 + 352),
            *(unsigned int *)(a1 + 348),
            pv,
            &v38);
    if ( v20 < 0 )
    {
      FreeEAPError(v38);
      v21 = IASFormatSysErr(v20, Buffer);
      if ( v21 < 0x100uLL )
      {
        Buffer[v21] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
          WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"EapHostAuthenticatorGetResult", (__int64)Buffer);
        }
        _com_issue_error(v20);
      }
      _report_rangecheckfailure(v22);
    }
    FreeEAPAttributes((struct _EAP_ATTRIBUTES *)(a1 + 320));
    v23 = pv[1];
    if ( pv[1] )
    {
      *(_OWORD *)(a1 + 320) = *(_OWORD *)pv[1];
      CoTaskMemFree(v23);
      pv[1] = 0;
    }
    v24 = v42;
    *(_QWORD *)(a1 + 296) = v42;
    if ( !v24 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("EapHostAuthenticatorGetResult returned NULL pEapMethodInfo");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
      }
      _com_issue_error(-2147467261);
    }
    v25 = HIDWORD(pv[0]);
    v26 = (int)pv[0];
    if ( *v24 != 25 )
    {
      IASTL::IASRequest::put_RoutingType(a2, 0);
      if ( !v26 )
        v26 = EAPSession::checkUnauthenticatedAccess((EAPSession *)a1, (struct IASTL::IASRequest *)a2, v25);
    }
    LODWORD(v39) = 0;
    UpdateAccountLockoutDB(*(struct _IASATTRIBUTE **)(a1 + 160), v26, (int *)&v39);
    if ( (_DWORD)v39 )
    {
      *(_OWORD *)v40 = 0;
      if ( (int)CEventLogResult::Initialize((CEventLogResult *)v40) >= 0 )
        CEventLogResult::LogResult((CEventLogResult *)v40, (struct IRequest *)*a2, a2[1], v27, v36, v37);
      CEventLogResult::~CEventLogResult((CEventLogResult *)v40);
    }
    InjectEAPAttributes((struct IASTL::IASRequest *)a2, (const struct _EAP_ATTRIBUTES *)(a1 + 320), 2 - (v26 != 0));
    EAPSession::storeNameId((EAPSession *)a1, (struct IASTL::IASRequest *)a2);
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("EAP authentication succeeded.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
      }
      IASTL::IASRequest::SetResponse(a2, 1, 0);
    }
    else
    {
      v28 = *(_DWORD *)(a1 + 220);
      if ( !v28 )
        v28 = IASMapWin32Error(v25, 16);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("EAP authentication failed.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
      }
      v39 = 0;
      v29 = IASTL::IASAttribute::load((IASTL::IASAttribute *)&v39, a2[1], 0x1FA7u);
      v30 = v39;
      if ( v29 )
        v28 = *((_DWORD *)v39 + 6);
      IASTL::IASRequest::SetResponse(a2, 2, v28);
      (*(void (__fastcall **)(struct IAttributesRaw *, _QWORD))(*(_QWORD *)*a2 + 128LL))(*a2, v28);
      if ( v30 )
        IASAttributeRelease(v30);
    }
    return 2;
  }
}

```

## disassembly

```asm
0x1800194b8  mov     [rsp-8+arg_10], rbx
0x1800194bd  push    rbp
0x1800194be  push    rsi
0x1800194bf  push    rdi
0x1800194c0  push    r12
0x1800194c2  push    r13
0x1800194c4  push    r14
0x1800194c6  push    r15
0x1800194c8  lea     rbp, [rsp-90h]
0x1800194d0  sub     rsp, 190h
0x1800194d7  mov     rax, cs:__security_cookie
0x1800194de  xor     rax, rsp
0x1800194e1  mov     [rbp+0C0h+var_40], rax
0x1800194e8  mov     rsi, rdx
0x1800194eb  mov     rdi, rcx
0x1800194ee  lea     r14, WPP_GLOBAL_Control
0x1800194f5  lea     rbx, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x1800194fc  mov     r15d, 4
0x180019502  mov     rdx, cs:WPP_GLOBAL_Control
0x180019509  cmp     rdx, r14
0x18001950c  jz      short loc_180019554
0x18001950e  cmp     [rdx+19h], r15b
0x180019512  jb      short loc_180019554
0x180019514  test    [rdx+1Ch], r15b
0x180019518  jz      short loc_180019554
0x18001951a  mov     edx, [rcx+158h]
0x180019520  lea     rcx, aProcessingOutp; "Processing output from EAP: action:%d"
0x180019527  call    WppDbgPrint
0x18001952c  lea     edx, [r15+26h]
0x180019530  mov     eax, [rdi+158h]
0x180019536  mov     [rsp+1C0h+var_1A0], eax; unsigned int
0x18001953a  mov     r8, rbx
0x18001953d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019544  mov     rcx, [rcx+10h]
0x180019548  call    WPP_SF_sd
0x18001954d  mov     rdx, cs:WPP_GLOBAL_Control
0x180019554  lea     r12, [rdi+158h]
0x18001955b  mov     ecx, [r12]
0x18001955f  xor     r13d, r13d
0x180019562  test    ecx, ecx
0x180019564  jz      loc_180019DBC
0x18001956a  sub     ecx, 1
0x18001956d  jz      loc_180019C69
0x180019573  sub     ecx, 1
0x180019576  jz      loc_18001992F
0x18001957c  sub     ecx, 1
0x18001957f  jz      loc_18001987B
0x180019585  sub     ecx, 1
0x180019588  jz      loc_18001987B
0x18001958e  cmp     ecx, 1
0x180019591  jnz     loc_180019DBC
0x180019597  cmp     rdx, r14
0x18001959a  jz      short loc_1800195D2
0x18001959c  cmp     [rdx+19h], r15b
0x1800195a0  jb      short loc_1800195D2
0x1800195a2  test    [rdx+1Ch], r15b
0x1800195a6  jz      short loc_1800195D2
0x1800195a8  lea     rcx, aEapHostInvoked; "EAP Host  invoked default authenticator"...
0x1800195af  call    WppDbgPrint
0x1800195b4  lea     edx, [r13+32h]
0x1800195b8  lea     r9, aNpssvc; "NPSSVC"
0x1800195bf  mov     r8, rbx
0x1800195c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195c9  mov     rcx, [rcx+10h]
0x1800195cd  call    WPP_SF_s
0x1800195d2  mov     [rsp+1C0h+var_180], r13
0x1800195d7  lea     r14, [rdi+140h]
0x1800195de  mov     rcx, r14; struct _EAP_ATTRIBUTES *
0x1800195e1  call    ?FreeEAPAttributes@@YAXAEAU_EAP_ATTRIBUTES@@@Z; FreeEAPAttributes(_EAP_ATTRIBUTES &)
0x1800195e6  mov     rcx, [rdi+160h]
0x1800195ed  mov     rax, [rcx]
0x1800195f0  lea     r9, [rsp+1C0h+var_180]
0x1800195f5  mov     r8, r14
0x1800195f8  mov     edx, [rdi+15Ch]
0x1800195fe  mov     rax, [rax+40h]
0x180019602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019607  mov     ebx, eax
0x180019609  test    eax, eax
0x18001960b  jns     short loc_18001966C
0x18001960d  mov     rcx, [rsp+1C0h+var_180]; struct _EAP_ERROR *
0x180019612  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x180019617  mov     rcx, cs:WPP_GLOBAL_Control
0x18001961e  lea     rax, WPP_GLOBAL_Control
0x180019625  cmp     rcx, rax
0x180019628  jz      short loc_180019664
0x18001962a  cmp     byte ptr [rcx+19h], 2
0x18001962e  jb      short loc_180019664
0x180019630  test    [rcx+1Ch], r15b
0x180019634  jz      short loc_180019664
0x180019636  mov     edx, ebx
0x180019638  lea     rcx, aEaphostauthent; "EapHostAuthenticatorGetAttributes faile"...
0x18001963f  call    WppDbgPrint
0x180019644  mov     edx, 33h ; '3'
0x180019649  mov     [rsp+1C0h+var_1A0], ebx
0x18001964d  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x180019654  mov     rcx, cs:WPP_GLOBAL_Control
0x18001965b  mov     rcx, [rcx+10h]
0x18001965f  call    WPP_SF_sd
0x180019664  mov     ecx, ebx; int
0x180019666  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001966c  mov     rdx, r14; struct _EAP_ATTRIBUTES *
0x18001966f  mov     rcx, [rdi+0A0h]; struct _IASATTRIBUTE *
0x180019676  call    ?AuthenticateUser@@YAKAEAU_IASATTRIBUTE@@AEAU_EAP_ATTRIBUTES@@@Z; AuthenticateUser(_IASATTRIBUTE &,_EAP_ATTRIBUTES &)
0x18001967b  mov     [rdi+154h], eax
0x180019681  mov     r15d, 100h
0x180019687  test    eax, eax
0x180019689  jnz     short loc_1800196E4
0x18001968b  mov     rax, cs:WPP_GLOBAL_Control
0x180019692  lea     rcx, WPP_GLOBAL_Control
0x180019699  cmp     rax, rcx
0x18001969c  jz      short loc_1800196D9
0x18001969e  cmp     byte ptr [rax+19h], 4
0x1800196a2  jb      short loc_1800196D9
0x1800196a4  test    byte ptr [rax+1Ch], 4
0x1800196a8  jz      short loc_1800196D9
0x1800196aa  lea     rcx, aDefaultAuthent; "Default authentication succeeded."
0x1800196b1  call    WppDbgPrint
0x1800196b6  mov     edx, 34h ; '4'
0x1800196bb  lea     r9, aNpssvc; "NPSSVC"
0x1800196c2  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x1800196c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196d0  mov     rcx, [rcx+10h]
0x1800196d4  call    WPP_SF_s
0x1800196d9  mov     r14d, 1
0x1800196df  jmp     loc_18001976F
0x1800196e4  lea     rdx, [rbp+0C0h+Buffer]; Buffer
0x1800196e8  mov     ecx, eax; dwMessageId
0x1800196ea  call    IASFormatSysErr
0x1800196ef  mov     eax, eax
0x1800196f1  cmp     rax, r15
0x1800196f4  jnb     loc_180019875
0x1800196fa  mov     [rbp+rax+0C0h+Buffer], r13b
0x1800196ff  mov     rax, cs:WPP_GLOBAL_Control
0x180019706  lea     rcx, WPP_GLOBAL_Control
0x18001970d  cmp     rax, rcx
0x180019710  jz      short loc_180019769
0x180019712  cmp     byte ptr [rax+19h], 2
0x180019716  jb      short loc_180019769
0x180019718  test    byte ptr [rax+1Ch], 4
0x18001971c  jz      short loc_180019769
0x18001971e  lea     r9, [rbp+0C0h+Buffer]
0x180019722  lea     rbx, aDefaultAuthent_0; "Default authentication"
0x180019729  mov     r8, rbx
0x18001972c  lea     rdx, aNpssvc; "NPSSVC"
0x180019733  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001973a  call    WppDbgPrint
0x18001973f  mov     edx, 35h ; '5'
0x180019744  lea     rax, [rbp+0C0h+Buffer]
0x180019748  mov     [rsp+1C0h+var_198], rax; __int64
0x18001974d  mov     qword ptr [rsp+1C0h+var_1A0], rbx; __int64
0x180019752  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x180019759  mov     rcx, cs:WPP_GLOBAL_Control
0x180019760  mov     rcx, [rcx+10h]; LoggerHandle
0x180019764  call    WPP_SF_sss
0x180019769  mov     r14d, 2
0x18001976f  lea     rbx, [rdi+130h]
0x180019776  mov     rcx, rbx; struct _EAP_ATTRIBUTES *
0x180019779  call    ?FreeEAPAttributes@@YAXAEAU_EAP_ATTRIBUTES@@@Z; FreeEAPAttributes(_EAP_ATTRIBUTES &)
0x18001977e  lea     rdx, [rdi+0E0h]; struct _EAP_ATTRIBUTES *
0x180019785  mov     r8d, r14d; struct IASTL::IASAttributeVector *
0x180019788  mov     rcx, rbx; this
0x18001978b  call    ?translate@EAPTranslator@@YAXAEAU_EAP_ATTRIBUTES@@AEBVIASAttributeVector@IASTL@@K@Z; EAPTranslator::translate(_EAP_ATTRIBUTES &,IASTL::IASAttributeVector const &,ulong)
0x180019790  mov     rcx, [rdi+160h]
0x180019797  mov     rax, [rcx]
0x18001979a  lea     rdx, [rsp+1C0h+var_180]
0x18001979f  mov     [rsp+1C0h+var_198], rdx; unsigned int *
0x1800197a4  mov     qword ptr [rsp+1C0h+var_1A0], r12
0x1800197a9  mov     r9, rbx
0x1800197ac  mov     r8d, [rdi+154h]
0x1800197b3  mov     edx, [rdi+15Ch]
0x1800197b9  mov     rax, [rax+50h]
0x1800197bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197c2  mov     ebx, eax
0x1800197c4  test    eax, eax
0x1800197c6  jns     loc_180019865
0x1800197cc  mov     rcx, [rsp+1C0h+var_180]; struct _EAP_ERROR *
0x1800197d1  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x1800197d6  lea     rdx, [rbp+0C0h+Buffer]; Buffer
0x1800197da  mov     ecx, ebx; dwMessageId
0x1800197dc  call    IASFormatSysErr
0x1800197e1  mov     ecx, eax
0x1800197e3  cmp     rcx, r15
0x1800197e6  jnb     short loc_18001985F
0x1800197e8  mov     [rbp+rcx+0C0h+Buffer], r13b
0x1800197ed  mov     rax, cs:WPP_GLOBAL_Control
0x1800197f4  lea     rcx, WPP_GLOBAL_Control
0x1800197fb  cmp     rax, rcx
0x1800197fe  jz      short loc_180019857
0x180019800  cmp     byte ptr [rax+19h], 2
0x180019804  jb      short loc_180019857
0x180019806  test    byte ptr [rax+1Ch], 4
0x18001980a  jz      short loc_180019857
0x18001980c  lea     r9, [rbp+0C0h+Buffer]
0x180019810  lea     rdi, aEaphostauthent_2; "EapHostAuthenticatorSetAuthenticateResu"...
0x180019817  mov     r8, rdi
0x18001981a  lea     rdx, aNpssvc; "NPSSVC"
0x180019821  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180019828  call    WppDbgPrint
0x18001982d  mov     edx, 36h ; '6'
0x180019832  lea     rax, [rbp+0C0h+Buffer]
0x180019836  mov     [rsp+1C0h+var_198], rax; __int64
0x18001983b  mov     qword ptr [rsp+1C0h+var_1A0], rdi; __int64
0x180019840  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x180019847  mov     rcx, cs:WPP_GLOBAL_Control
0x18001984e  mov     rcx, [rcx+10h]; LoggerHandle
0x180019852  call    WPP_SF_sss
0x180019857  mov     ecx, ebx; int
0x180019859  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001985f  call    __report_rangecheckfailure
0x180019865  mov     rdx, rsi
0x180019868  mov     rcx, rdi
0x18001986b  call    ?doAction@EAPSession@@IEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z; EAPSession::doAction(IASTL::IASRequest &)
0x180019870  jmp     loc_180019E0B
0x180019875  call    __report_rangecheckfailure
0x18001987b  lea     rbx, [rdi+140h]
0x180019882  mov     rcx, rbx; struct _EAP_ATTRIBUTES *
0x180019885  call    ?FreeEAPAttributes@@YAXAEAU_EAP_ATTRIBUTES@@@Z; FreeEAPAttributes(_EAP_ATTRIBUTES &)
0x18001988a  mov     [rsp+1C0h+var_180], r13
0x18001988f  mov     rcx, [rdi+160h]
0x180019896  mov     rax, [rcx]
0x180019899  lea     r9, [rsp+1C0h+var_180]
0x18001989e  mov     r8, rbx
0x1800198a1  mov     edx, [rdi+15Ch]
0x1800198a7  mov     rax, [rax+40h]
0x1800198ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198b0  mov     ebx, eax
0x1800198b2  test    eax, eax
0x1800198b4  jns     short loc_18001990E
0x1800198b6  mov     rcx, [rsp+1C0h+var_180]; struct _EAP_ERROR *
0x1800198bb  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x1800198c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198c7  cmp     rcx, r14
0x1800198ca  jz      short loc_180019906
0x1800198cc  cmp     byte ptr [rcx+19h], 2
0x1800198d0  jb      short loc_180019906
0x1800198d2  test    [rcx+1Ch], r15b
0x1800198d6  jz      short loc_180019906
0x1800198d8  mov     edx, ebx
0x1800198da  lea     rcx, aEaphostauthent; "EapHostAuthenticatorGetAttributes faile"...
0x1800198e1  call    WppDbgPrint
0x1800198e6  mov     edx, 31h ; '1'
0x1800198eb  mov     [rsp+1C0h+var_1A0], ebx
0x1800198ef  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x1800198f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198fd  mov     rcx, [rcx+10h]
0x180019901  call    WPP_SF_sd
0x180019906  mov     ecx, ebx; int
0x180019908  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001990e  mov     rdx, rsi
0x180019911  mov     rcx, rdi
0x180019914  cmp     dword ptr [r12], 3
0x180019919  jnz     short loc_180019925
0x18001991b  call    ?onIndicateTLV@EAPSession@@IEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z; EAPSession::onIndicateTLV(IASTL::IASRequest &)
0x180019920  jmp     loc_180019E0B
0x180019925  call    ?onIndicateIdentity@EAPSession@@IEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z; EAPSession::onIndicateIdentity(IASTL::IASRequest &)
0x18001992a  jmp     loc_180019E0B
0x18001992f  xorps   xmm0, xmm0
0x180019932  xor     eax, eax
0x180019934  movups  xmmword ptr [rsp+1C0h+pv], xmm0
0x180019939  mov     [rsp+1C0h+var_150], rax
0x18001993e  mov     [rsp+1C0h+var_180], r13
0x180019943  mov     rcx, [rdi+160h]
0x18001994a  mov     rax, [rcx]
0x18001994d  lea     r9, [rsp+1C0h+var_180]
0x180019952  lea     r8, [rsp+1C0h+pv]
0x180019957  mov     edx, [rdi+15Ch]
0x18001995d  mov     rax, [rax+58h]
0x180019961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019966  mov     ebx, eax
0x180019968  test    eax, eax
0x18001996a  jns     loc_180019A08
0x180019970  mov     rcx, [rsp+1C0h+var_180]; struct _EAP_ERROR *
0x180019975  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x18001997a  lea     rdx, [rbp+0C0h+Buffer]; Buffer
0x18001997e  mov     ecx, ebx; dwMessageId
0x180019980  call    IASFormatSysErr
0x180019985  mov     eax, eax
0x180019987  mov     r15d, 100h
0x18001998d  cmp     rax, r15
0x180019990  jnb     short loc_180019A02
0x180019992  mov     [rbp+rax+0C0h+Buffer], r13b
0x180019997  mov     rax, cs:WPP_GLOBAL_Control
0x18001999e  cmp     rax, r14
0x1800199a1  jz      short loc_1800199FA
0x1800199a3  cmp     byte ptr [rax+19h], 2
0x1800199a7  jb      short loc_1800199FA
0x1800199a9  test    byte ptr [rax+1Ch], 4
0x1800199ad  jz      short loc_1800199FA
0x1800199af  lea     r9, [rbp+0C0h+Buffer]
0x1800199b3  lea     rdi, aEaphostauthent_4; "EapHostAuthenticatorGetResult"
0x1800199ba  mov     r8, rdi
0x1800199bd  lea     rdx, aNpssvc; "NPSSVC"
0x1800199c4  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x1800199cb  call    WppDbgPrint
0x1800199d0  mov     edx, 2Bh ; '+'
0x1800199d5  lea     rax, [rbp+0C0h+Buffer]
0x1800199d9  mov     [rsp+1C0h+var_198], rax; __int64
0x1800199de  mov     qword ptr [rsp+1C0h+var_1A0], rdi; __int64
0x1800199e3  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x1800199ea  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
