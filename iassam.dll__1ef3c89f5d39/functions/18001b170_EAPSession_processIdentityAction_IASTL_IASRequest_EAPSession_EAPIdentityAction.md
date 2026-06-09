# EAPSession::processIdentityAction(IASTL::IASRequest &,EAPSession::EAPIdentityAction)

- ea: `0x18001b170`
- end: `0x18001b5b3`
- name: `?processIdentityAction@EAPSession@@QEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@W4EAPIdentityAction@1@@Z`
- size: `1091`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180017900`

## callees

- `0x180001c88`
- `0x18000a760`
- `0x18000acf4`
- `0x18000ba5c`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000c808`
- `0x18000d49c`
- `0x18000d5d8`
- `0x18000d604`
- `0x180016ce4`
- `0x180018b10`
- `0x1800194b8`
- `0x180019eac`
- `0x18001b170`
- `0x18001be30`
- `0x1800254a0`
- `0x18002b4a0`
- `0x18002e010`

## string_xrefs

- `0x18001b45c`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`
- `0x18001b44b`: `EapHostAuthenticatorUpdateInnerMethodParams`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EAPSession::processIdentityAction(__int64 a1, IASTL::IASRequest *a2, int a3)
{
  const struct _IASATTRIBUTE *v6; // r8
  void *v7; // rbx
  int v8; // r15d
  unsigned int v9; // eax
  int v10; // ebx
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v12; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v13; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v15; // [rsp+58h] [rbp-A8h] BYREF
  struct _EAP_ERROR *v16; // [rsp+60h] [rbp-A0h] BYREF
  struct _EAP_ERROR *v17; // [rsp+68h] [rbp-98h] BYREF
  __int128 v18; // [rsp+70h] [rbp-90h] BYREF
  __int128 v19; // [rsp+80h] [rbp-80h] BYREF
  __int128 v20; // [rsp+90h] [rbp-70h] BYREF
  char Buffer[256]; // [rsp+A0h] [rbp-60h] BYREF

  if ( a3 != 1 )
  {
    if ( a3 == 2 || a3 == 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("SoH Payload TLVs should not exist in the requests.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
      }
      EAPError::Throw(3);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("EAP identity action %d should never be hit");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_69033002015f3c629418a4473ed337be_Traceguids);
    }
LABEL_35:
    v13 = 8113;
    IASTL::IASRequest::RemoveAttributesByType(a2, 1u, &v13);
    v17 = 0;
    v20 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64, struct _EAP_ERROR **))(**(_QWORD **)(a1 + 352)
                                                                                               + 72LL))(
            *(_QWORD *)(a1 + 352),
            *(unsigned int *)(a1 + 348),
            &v20,
            a1 + 344,
            &v17);
    if ( v10 < 0 )
    {
      FreeEAPError(v17);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("pEapHost->EapHostAuthenticatorSetAttributes(EmptyAttribute) failed with 0x%x");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_69033002015f3c629418a4473ed337be_Traceguids);
      }
      _com_issue_error(v10);
    }
    return EAPSession::doAction(a1, (struct IAttributesRaw **)a2);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Successfully validate PEAP inner identity");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
  }
  if ( (unsigned __int8)IASTL::IASAttribute::load(a1 + 160, *((_QWORD *)a2 + 1), 4129, 5) )
  {
    v16 = 0;
    v15 = 0;
    pv = 0;
    v19 = 0;
    v18 = 0;
    v11 = 0;
    EAPSession::getAccountInfo(
      (EAPSession *)a1,
      a2,
      (const unsigned __int16 **)&v15,
      (struct IASTL::IASAttribute *)&pv,
      &v11);
    v7 = pv;
    if ( pv )
    {
      LODWORD(v19) = 1;
      v18 = 0;
      EAPTranslator::translate((EAPTranslator *)&v18, (struct _EAP_ATTRIBUTE *)pv, v6);
      *((_QWORD *)&v19 + 1) = &v18;
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int16 *, __int128 *, struct _EAP_ERROR **))(**(_QWORD **)(a1 + 352) + 32LL))(
           *(_QWORD *)(a1 + 352),
           *(unsigned int *)(a1 + 348),
           v11,
           v15,
           &v19,
           &v16);
    if ( v8 < 0 )
    {
      FreeEAPError(v16);
      v9 = IASFormatSysErr(v8, Buffer);
      if ( v9 < 0x100uLL )
      {
        Buffer[v9] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
          WPP_SF_sss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (__int64)"EapHostAuthenticatorUpdateInnerMethodParams",
            (__int64)Buffer);
        }
        _com_issue_error(v8);
      }
      _report_rangecheckfailure(v9);
    }
    v12 = 8113;
    IASTL::IASRequest::RemoveAttributesByType(a2, 1u, &v12);
    if ( v7 )
      IASAttributeRelease(v7);
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("SAM account name not found.");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
  }
  IASTL::IASRequest::SetResponse(a2, 5, 3);
  return 1;
}

```

## disassembly

```asm
0x18001b170  mov     [rsp-8+arg_18], rbx
0x18001b175  push    rbp
0x18001b176  push    rsi
0x18001b177  push    rdi
0x18001b178  push    r14
0x18001b17a  push    r15
0x18001b17c  lea     rbp, [rsp-0B0h]
0x18001b184  sub     rsp, 1B0h
0x18001b18b  mov     rax, cs:__security_cookie
0x18001b192  xor     rax, rsp
0x18001b195  mov     [rbp+0D0h+var_30], rax
0x18001b19c  mov     ebx, r8d
0x18001b19f  mov     rsi, rdx
0x18001b1a2  mov     r14, rcx
0x18001b1a5  mov     ecx, r8d
0x18001b1a8  mov     r15d, 1
0x18001b1ae  sub     ecx, r15d
0x18001b1b1  jz      loc_18001B27D
0x18001b1b7  sub     ecx, r15d
0x18001b1ba  jz      short loc_18001B224
0x18001b1bc  sub     ecx, r15d
0x18001b1bf  jz      short loc_18001B1C6
0x18001b1c1  cmp     ecx, r15d
0x18001b1c4  jz      short loc_18001B224
0x18001b1c6  lea     rdi, WPP_GLOBAL_Control
0x18001b1cd  mov     rax, cs:WPP_GLOBAL_Control
0x18001b1d4  cmp     rax, rdi
0x18001b1d7  jz      loc_18001B4CD
0x18001b1dd  cmp     byte ptr [rax+19h], 2
0x18001b1e1  jb      loc_18001B4CD
0x18001b1e7  test    byte ptr [rax+1Ch], 4
0x18001b1eb  jz      loc_18001B4CD
0x18001b1f1  mov     edx, ebx
0x18001b1f3  lea     rcx, aEapIdentityAct; "EAP identity action %d should never be "...
0x18001b1fa  call    WppDbgPrint
0x18001b1ff  mov     edx, 1Ch
0x18001b204  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x18001b208  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001b20f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b216  mov     rcx, [rcx+10h]
0x18001b21a  call    WPP_SF_sd
0x18001b21f  jmp     loc_18001B4CD
0x18001b224  lea     rdi, WPP_GLOBAL_Control
0x18001b22b  mov     rax, cs:WPP_GLOBAL_Control
0x18001b232  cmp     rax, rdi
0x18001b235  jz      short loc_18001B272
0x18001b237  cmp     byte ptr [rax+19h], 2
0x18001b23b  jb      short loc_18001B272
0x18001b23d  test    byte ptr [rax+1Ch], 4
0x18001b241  jz      short loc_18001B272
0x18001b243  lea     rcx, aSohPayloadTlvs; "SoH Payload TLVs should not exist in th"...
0x18001b24a  call    WppDbgPrint
0x18001b24f  mov     edx, 1Bh
0x18001b254  lea     r9, aNpssvc; "NPSSVC"
0x18001b25b  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001b262  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b269  mov     rcx, [rcx+10h]
0x18001b26d  call    WPP_SF_s
0x18001b272  mov     ecx, 3; int
0x18001b277  call    ?Throw@EAPError@@SAXJ@Z; EAPError::Throw(long)
0x18001b27d  lea     rdi, WPP_GLOBAL_Control
0x18001b284  mov     rax, cs:WPP_GLOBAL_Control
0x18001b28b  cmp     rax, rdi
0x18001b28e  jz      short loc_18001B2CB
0x18001b290  cmp     byte ptr [rax+19h], 4
0x18001b294  jb      short loc_18001B2CB
0x18001b296  test    byte ptr [rax+1Ch], 4
0x18001b29a  jz      short loc_18001B2CB
0x18001b29c  lea     rcx, aSuccessfullyVa_0; "Successfully validate PEAP inner identi"...
0x18001b2a3  call    WppDbgPrint
0x18001b2a8  mov     edx, 18h
0x18001b2ad  lea     r9, aNpssvc; "NPSSVC"
0x18001b2b4  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001b2bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2c2  mov     rcx, [rcx+10h]
0x18001b2c6  call    WPP_SF_s
0x18001b2cb  lea     rcx, [r14+0A0h]
0x18001b2d2  mov     ebx, 5
0x18001b2d7  mov     r9d, ebx
0x18001b2da  mov     r8d, 1021h
0x18001b2e0  mov     rdx, [rsi+8]
0x18001b2e4  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong,IASTYPEENUM)
0x18001b2e9  test    al, al
0x18001b2eb  jnz     short loc_18001B34A
0x18001b2ed  mov     rax, cs:WPP_GLOBAL_Control
0x18001b2f4  cmp     rax, rdi
0x18001b2f7  jz      short loc_18001B332
0x18001b2f9  cmp     byte ptr [rax+19h], 2
0x18001b2fd  jb      short loc_18001B332
0x18001b2ff  test    byte ptr [rax+1Ch], 4
0x18001b303  jz      short loc_18001B332
0x18001b305  lea     rcx, aSamAccountName_0; "SAM account name not found."
0x18001b30c  call    WppDbgPrint
0x18001b311  lea     edx, [rbx+14h]
0x18001b314  lea     r9, aNpssvc; "NPSSVC"
0x18001b31b  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001b322  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b329  mov     rcx, [rcx+10h]
0x18001b32d  call    WPP_SF_s
0x18001b332  mov     r8d, 3
0x18001b338  mov     edx, ebx
0x18001b33a  mov     rcx, rsi
0x18001b33d  call    ?SetResponse@IASRequest@IASTL@@QEAAXW4_IASRESPONSE@@K@Z; IASTL::IASRequest::SetResponse(_IASRESPONSE,ulong)
0x18001b342  mov     eax, r15d
0x18001b345  jmp     loc_18001B58D
0x18001b34a  mov     [rsp+1D0h+var_170], 0
0x18001b353  mov     [rsp+1D0h+var_178], 0
0x18001b35c  mov     [rsp+1D0h+pv], 0
0x18001b365  xorps   xmm0, xmm0
0x18001b368  movups  [rbp+0D0h+var_150], xmm0
0x18001b36c  xorps   xmm1, xmm1
0x18001b36f  movups  [rsp+1D0h+var_160], xmm1
0x18001b374  mov     [rsp+1D0h+var_190], 0
0x18001b37c  lea     rax, [rsp+1D0h+var_190]
0x18001b381  mov     [rsp+1D0h+var_1B0], rax; unsigned int *
0x18001b386  lea     r9, [rsp+1D0h+pv]; struct IASTL::IASAttribute *
0x18001b38b  lea     r8, [rsp+1D0h+var_178]; unsigned __int16 **
0x18001b390  mov     rdx, rsi; struct IASTL::IASRequest *
0x18001b393  mov     rcx, r14; this
0x18001b396  call    ?getAccountInfo@EAPSession@@IEAAXAEAVIASRequest@IASTL@@AEAPEBGAEAVIASAttribute@3@AEAK@Z; EAPSession::getAccountInfo(IASTL::IASRequest &,ushort const * &,IASTL::IASAttribute &,ulong &)
0x18001b39b  mov     rbx, [rsp+1D0h+pv]
0x18001b3a0  test    rbx, rbx
0x18001b3a3  jz      short loc_18001B3C7
0x18001b3a5  mov     dword ptr [rbp+0D0h+var_150], r15d
0x18001b3a9  xorps   xmm0, xmm0
0x18001b3ac  movups  [rsp+1D0h+var_160], xmm0
0x18001b3b1  mov     rdx, rbx; struct _EAP_ATTRIBUTE *
0x18001b3b4  lea     rcx, [rsp+1D0h+var_160]; this
0x18001b3b9  call    ?translate@EAPTranslator@@YAHAEAU_EAP_ATTRIBUTE@@AEBU_IASATTRIBUTE@@@Z; EAPTranslator::translate(_EAP_ATTRIBUTE &,_IASATTRIBUTE const &)
0x18001b3be  lea     rax, [rsp+1D0h+var_160]
0x18001b3c3  mov     qword ptr [rbp+0D0h+var_150+8], rax
0x18001b3c7  mov     rcx, [r14+160h]
0x18001b3ce  mov     rax, [rcx]
0x18001b3d1  lea     rdx, [rsp+1D0h+var_170]
0x18001b3d6  mov     [rsp+1D0h+var_1A8], rdx
0x18001b3db  lea     rdx, [rbp+0D0h+var_150]
0x18001b3df  mov     [rsp+1D0h+var_1B0], rdx
0x18001b3e4  mov     r9, [rsp+1D0h+var_178]
0x18001b3e9  mov     r8d, [rsp+1D0h+var_190]
0x18001b3ee  mov     edx, [r14+15Ch]
0x18001b3f5  mov     rax, [rax+20h]
0x18001b3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3fe  mov     r15d, eax
0x18001b401  test    eax, eax
0x18001b403  jns     loc_18001B4A1
0x18001b409  mov     rcx, [rsp+1D0h+var_170]; struct _EAP_ERROR *
0x18001b40e  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x18001b413  lea     rdx, [rbp+0D0h+Buffer]; Buffer
0x18001b417  mov     ecx, r15d; dwMessageId
0x18001b41a  call    IASFormatSysErr
0x18001b41f  mov     ecx, eax
0x18001b421  cmp     rcx, 100h
0x18001b428  jnb     short loc_18001B49B
0x18001b42a  mov     [rbp+rcx+0D0h+Buffer], 0
0x18001b42f  mov     rax, cs:WPP_GLOBAL_Control
0x18001b436  cmp     rax, rdi
0x18001b439  jz      short loc_18001B492
0x18001b43b  cmp     byte ptr [rax+19h], 2
0x18001b43f  jb      short loc_18001B492
0x18001b441  test    byte ptr [rax+1Ch], 4
0x18001b445  jz      short loc_18001B492
0x18001b447  lea     r9, [rbp+0D0h+Buffer]
0x18001b44b  lea     rbx, aEaphostauthent_7; "EapHostAuthenticatorUpdateInnerMethodPa"...
0x18001b452  mov     r8, rbx
0x18001b455  lea     rdx, aNpssvc; "NPSSVC"
0x18001b45c  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001b463  call    WppDbgPrint
0x18001b468  mov     edx, 1Ah
0x18001b46d  lea     rax, [rbp+0D0h+Buffer]
0x18001b471  mov     [rsp+1D0h+var_1A8], rax; __int64
0x18001b476  mov     [rsp+1D0h+var_1B0], rbx; __int64
0x18001b47b  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001b482  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b489  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b48d  call    WPP_SF_sss
0x18001b492  mov     ecx, r15d; int
0x18001b495  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001b49b  call    __report_rangecheckfailure
0x18001b4a1  mov     [rsp+1D0h+var_18C], 1FB1h
0x18001b4a9  lea     r8, [rsp+1D0h+var_18C]; unsigned int *
0x18001b4ae  mov     r15d, 1
0x18001b4b4  mov     edx, r15d; unsigned int
0x18001b4b7  mov     rcx, rsi; this
0x18001b4ba  call    ?RemoveAttributesByType@IASRequest@IASTL@@QEAAXKPEAK@Z; IASTL::IASRequest::RemoveAttributesByType(ulong,ulong *)
0x18001b4bf  nop
0x18001b4c0  test    rbx, rbx
0x18001b4c3  jz      short loc_18001B4CD
0x18001b4c5  mov     rcx, rbx; pv
0x18001b4c8  call    IASAttributeRelease
0x18001b4cd  mov     [rsp+1D0h+var_188], 1FB1h
0x18001b4d5  lea     r8, [rsp+1D0h+var_188]; unsigned int *
0x18001b4da  mov     edx, r15d; unsigned int
0x18001b4dd  mov     rcx, rsi; this
0x18001b4e0  call    ?RemoveAttributesByType@IASRequest@IASTL@@QEAAXKPEAK@Z; IASTL::IASRequest::RemoveAttributesByType(ulong,ulong *)
0x18001b4e5  mov     [rsp+1D0h+var_168], 0
0x18001b4ee  xorps   xmm0, xmm0
0x18001b4f1  movups  [rbp+0D0h+var_140], xmm0
0x18001b4f5  mov     rcx, [r14+160h]
0x18001b4fc  mov     rax, [rcx]
0x18001b4ff  lea     r9, [r14+158h]
0x18001b506  lea     rdx, [rsp+1D0h+var_168]
0x18001b50b  mov     [rsp+1D0h+var_1B0], rdx
0x18001b510  lea     r8, [rbp+0D0h+var_140]
0x18001b514  mov     edx, [r14+15Ch]
0x18001b51b  mov     rax, [rax+48h]
0x18001b51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b524  mov     ebx, eax
0x18001b526  test    eax, eax
0x18001b528  jns     short loc_18001B582
0x18001b52a  mov     rcx, [rsp+1D0h+var_168]; struct _EAP_ERROR *
0x18001b52f  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x18001b534  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b53b  cmp     rcx, rdi
0x18001b53e  jz      short loc_18001B57A
0x18001b540  cmp     byte ptr [rcx+19h], 2
0x18001b544  jb      short loc_18001B57A
0x18001b546  test    byte ptr [rcx+1Ch], 4
0x18001b54a  jz      short loc_18001B57A
0x18001b54c  mov     edx, ebx
0x18001b54e  lea     rcx, aPeaphostEaphos_0; "pEapHost->EapHostAuthenticatorSetAttrib"...
0x18001b555  call    WppDbgPrint
0x18001b55a  mov     edx, 1Dh
0x18001b55f  mov     dword ptr [rsp+1D0h+var_1B0], ebx
0x18001b563  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001b56a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b571  mov     rcx, [rcx+10h]
0x18001b575  call    WPP_SF_sd
0x18001b57a  mov     ecx, ebx; int
0x18001b57c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001b582  mov     rdx, rsi
0x18001b585  mov     rcx, r14
0x18001b588  call    ?doAction@EAPSession@@IEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z; EAPSession::doAction(IASTL::IASRequest &)
0x18001b58d  mov     rcx, [rbp+0D0h+var_30]
0x18001b594  xor     rcx, rsp; StackCookie
0x18001b597  call    __security_check_cookie
0x18001b59c  mov     rbx, [rsp+1D0h+arg_18]
0x18001b5a4  add     rsp, 1B0h
0x18001b5ab  pop     r15
0x18001b5ad  pop     r14
0x18001b5af  pop     rdi
0x18001b5b0  pop     rsi
0x18001b5b1  pop     rbp
0x18001b5b2  retn
```
