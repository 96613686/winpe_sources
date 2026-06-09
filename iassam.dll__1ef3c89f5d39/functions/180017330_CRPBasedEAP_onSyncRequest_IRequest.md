# CRPBasedEAP::onSyncRequest(IRequest *)

- ea: `0x180017330`
- end: `0x1800178f4`
- name: `?onSyncRequest@CRPBasedEAP@@MEAA?AW4_IASREQUESTSTATUS@@PEAUIRequest@@@Z`
- size: `1476`
- prototype: `enum _IASREQUESTSTATUS __high(struct IRequest *)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops`

## callees

- `0x1800033bc`
- `0x18000acf4`
- `0x18000b24c`
- `0x18000b484`
- `0x18000ba5c`
- `0x18000bea8`
- `0x18000c28c`
- `0x18000c4a4`
- `0x18000d55c`
- `0x18000e754`
- `0x180013b34`
- `0x180016b44`
- `0x180016ce4`
- `0x180017074`
- `0x180017258`
- `0x180017330`
- `0x180017c54`
- `0x180018330`
- `0x180018460`
- `0x1800184f4`
- `0x180018fb0`
- `0x18001a738`
- `0x18001ac5c`
- `0x18001b084`
- `0x1800254a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!free` at `0x1800173c5`
- `msvcrt!free` at `0x180017495`
- `msvcrt!free` at `0x18001753f`
- `msvcrt!free` at `0x18001761b`
- `msvcrt!free` at `0x1800177be`
- `msvcrt!free` at `0x180017809`
- `msvcrt!free` at `0x1800178c4`
- `msvcrt!free` at `0x1800173c5`
- `msvcrt!free` at `0x180017495`
- `msvcrt!free` at `0x18001753f`
- `msvcrt!free` at `0x18001761b`
- `msvcrt!free` at `0x1800177be`
- `msvcrt!free` at `0x180017809`
- `msvcrt!free` at `0x1800178c4`

## string_xrefs

- `0x18001756f`: `Successfully created new CRP Based EAP session for user %S.`
- `0x18001764b`: `Successfully created new RAP Based EAP session for user %S.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CRPBasedEAP::onSyncRequest(__int64 a1, struct IRequest *a2)
{
  __int64 v4; // rax
  void *v5; // rax
  struct EAPSession *v6; // rbx
  void *v7; // rsi
  void *v8; // rcx
  int v9; // r9d
  bool v10; // dl
  void *v11; // rax
  void *v12; // rsi
  void *v13; // rcx
  int v14; // r9d
  struct EAPState *EAPState; // rax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  void *v19; // rsi
  void *v20; // rcx
  LPVOID pv; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int8 Src[24]; // [rsp+38h] [rbp-50h] BYREF
  struct IAttributesRaw *v23; // [rsp+50h] [rbp-38h] BYREF
  struct IAttributesRaw *v24; // [rsp+58h] [rbp-30h]
  void *Block; // [rsp+A0h] [rbp+18h] BYREF
  struct EAPSession *v26; // [rsp+A8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Entering CRPBasedEAP stage");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids, "NPSSVC");
  }
  IASTL::IASRequest::IASRequest((IASTL::IASRequest *)&v23, a2);
  CRPBasedEAP::getEAPPacket(&Block, &v23);
  if ( !Block )
  {
    free(0);
    (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v24 + 16LL))(v24);
    return 1;
  }
  v26 = 0;
  if ( (unsigned int)IASTL::IASRequest::get_RoutingType(&v23) )
  {
    EAPState = EAPBase::getEAPState((struct IASTL::IASRequest *)&v23);
    v6 = EAPSessionTable::remove(
           EAPBase::pSessions,
           *(unsigned __int8 *)(*((_QWORD *)EAPState + 1) + 35LL)
         | ((*(unsigned __int8 *)(*((_QWORD *)EAPState + 1) + 34LL)
           | (((*(unsigned __int8 *)(*((_QWORD *)EAPState + 1) + 32LL) << 8)
             | (unsigned int)*(unsigned __int8 *)(*((_QWORD *)EAPState + 1) + 33LL)) << 8)) << 8));
    *(_QWORD *)Src = 0;
    v26 = v6;
    std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(Src);
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Session timed out");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids, "NPSSVC");
      }
      EAPError::Throw(96);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Successfully retrieved session (%d) for user %S.");
      WPP_SF_sdS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        v17,
        v18,
        *((_DWORD *)v6 + 87),
        *(_QWORD *)(*((_QWORD *)v6 + 20) + 32LL));
    }
    v19 = Block;
    Block = 0;
    v20 = (void *)*((_QWORD *)v6 + 26);
    if ( v19 != v20 )
      free(v20);
    *((_QWORD *)v6 + 26) = v19;
    if ( EAPSession::onReceiveEvent(v6, (struct IASTL::IASRequest *)&v23) )
    {
      EAPSessionTable::insert(EAPBase::pSessions, v6);
      v26 = 0;
      std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(&v26);
      free(Block);
      (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v24 + 16LL))(v24);
      return 1;
    }
    EAPSession::injectProfile(v6, (struct IASTL::IASRequest *)&v23);
    if ( !*((_DWORD *)v6 + 68) )
      EAPSession::processEAPPacket(v6, &v23);
  }
  else
  {
    pv = 0;
    if ( !(unsigned __int8)IASTL::IASAttribute::load(&pv, v24, 4129, 5) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("SAM account name not found.");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids, "NPSSVC");
      }
      if ( pv )
        IASAttributeRelease(pv);
      std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(&v26);
      free(Block);
      (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v24 + 16LL))(v24);
      return 1;
    }
    v4 = IASPeekAttribute(v24, 8112, 1);
    if ( v4 && *(_DWORD *)(v4 + 24) )
    {
      v5 = operator new(0x168u);
      *(_QWORD *)Src = v5;
      if ( v5 )
        v6 = (struct EAPSession *)EAPSession::EAPSession(v5, &pv, 0);
      else
        v6 = 0;
      *(_QWORD *)Src = 0;
      v26 = v6;
      std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(Src);
      v7 = Block;
      Block = 0;
      v8 = (void *)*((_QWORD *)v6 + 26);
      if ( v7 != v8 )
        free(v8);
      *((_QWORD *)v6 + 26) = v7;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Successfully created new CRP Based EAP session for user %S.");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)&WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids,
          v9,
          *(_QWORD *)(*((_QWORD *)v6 + 20) + 32LL));
      }
      EAPSession::begin((__int64)v6, &v23);
    }
    else
    {
      v11 = operator new(0x168u);
      *(_QWORD *)Src = v11;
      if ( v11 )
        v6 = (struct EAPSession *)EAPSession::EAPSession(v11, &pv, 2);
      else
        v6 = 0;
      *(_QWORD *)Src = 0;
      v26 = v6;
      std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(Src);
      v12 = Block;
      Block = 0;
      v13 = (void *)*((_QWORD *)v6 + 26);
      if ( v12 != v13 )
        free(v13);
      *((_QWORD *)v6 + 26) = v12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Successfully created new RAP Based EAP session for user %S.");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)&WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids,
          v14,
          *(_QWORD *)(*((_QWORD *)v6 + 20) + 32LL));
      }
    }
    if ( pv )
      IASAttributeRelease(pv);
  }
  IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&pv, v10);
  *((_DWORD *)pv + 2) = 8105;
  *(_QWORD *)Src = v6;
  IASTL::IASAttribute::setOctetString((IASTL::IASAttribute *)&pv, 8u, Src);
  *((_DWORD *)pv + 1) = 4;
  IASTL::IASAttribute::store((IASTL::IASAttribute *)&pv, v24);
  if ( pv )
    IASAttributeRelease(pv);
  v26 = 0;
  std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(&v26);
  free(Block);
  (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v24 + 16LL))(v24);
  return 1;
}

```

## disassembly

```asm
0x180017330  mov     [rsp+arg_8], rdx
0x180017335  push    rbx
0x180017336  push    rsi
0x180017337  push    rdi
0x180017338  push    r14
0x18001733a  push    r15
0x18001733c  sub     rsp, 60h
0x180017340  mov     rbx, rdx
0x180017343  lea     r15, WPP_GLOBAL_Control
0x18001734a  mov     rax, cs:WPP_GLOBAL_Control
0x180017351  mov     edi, 4
0x180017356  cmp     rax, r15
0x180017359  jz      short loc_180017395
0x18001735b  cmp     [rax+19h], dil
0x18001735f  jb      short loc_180017395
0x180017361  test    [rax+1Ch], dil
0x180017365  jz      short loc_180017395
0x180017367  lea     rcx, aEnteringCrpbas; "Entering CRPBasedEAP stage"
0x18001736e  call    WppDbgPrint
0x180017373  lea     edx, [rdi+7]
0x180017376  lea     r9, aNpssvc; "NPSSVC"
0x18001737d  lea     r8, WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids
0x180017384  mov     rcx, cs:WPP_GLOBAL_Control
0x18001738b  mov     rcx, [rcx+10h]
0x18001738f  call    WPP_SF_s
0x180017394  nop
0x180017395  mov     rdx, rbx; struct IRequest *
0x180017398  lea     rcx, [rsp+88h+var_38]; this
0x18001739d  call    ??0IASRequest@IASTL@@QEAA@PEAUIRequest@@@Z; IASTL::IASRequest::IASRequest(IRequest *)
0x1800173a2  nop
0x1800173a3  lea     rdx, [rsp+88h+var_38]
0x1800173a8  lea     rcx, [rsp+88h+Block]
0x1800173b0  call    ?getEAPPacket@CRPBasedEAP@@CA?AV?$auto_ptr@U_PPP_EAP_PACKET@@@std@@AEAVIASRequest@IASTL@@@Z; CRPBasedEAP::getEAPPacket(IASTL::IASRequest &)
0x1800173b5  nop
0x1800173b6  xor     r14d, r14d
0x1800173b9  cmp     [rsp+88h+Block], r14
0x1800173c1  jnz     short loc_1800173E7
0x1800173c3  xor     ecx, ecx; Block
0x1800173c5  call    cs:__imp_free
0x1800173cb  nop
0x1800173cc  mov     rcx, [rsp+88h+var_30]
0x1800173d1  mov     rax, [rcx]
0x1800173d4  mov     rax, [rax+10h]
0x1800173d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173dd  nop
0x1800173de  lea     eax, [r14+1]
0x1800173e2  jmp     loc_1800178E8
0x1800173e7  mov     [rsp+88h+arg_18], r14
0x1800173ef  lea     rcx, [rsp+88h+var_38]
0x1800173f4  call    ?get_RoutingType@IASRequest@IASTL@@QEBA?AW4_IASREQUEST@@XZ; IASTL::IASRequest::get_RoutingType(void)
0x1800173f9  test    eax, eax
0x1800173fb  jnz     loc_18001769C
0x180017401  mov     [rsp+88h+pv], r14
0x180017406  lea     r9d, [rax+5]
0x18001740a  mov     r8d, 1021h
0x180017410  mov     rdx, [rsp+88h+var_30]
0x180017415  lea     rcx, [rsp+88h+pv]
0x18001741a  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong,IASTYPEENUM)
0x18001741f  test    al, al
0x180017421  jnz     loc_1800174B8
0x180017427  mov     rax, cs:WPP_GLOBAL_Control
0x18001742e  cmp     rax, r15
0x180017431  jz      short loc_18001746F
0x180017433  cmp     byte ptr [rax+19h], 2
0x180017437  jb      short loc_18001746F
0x180017439  test    [rax+1Ch], dil
0x18001743d  jz      short loc_18001746F
0x18001743f  lea     rcx, aSamAccountName_0; "SAM account name not found."
0x180017446  call    WppDbgPrint
0x18001744b  mov     edx, 0Ch
0x180017450  lea     r9, aNpssvc; "NPSSVC"
0x180017457  lea     r8, WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids
0x18001745e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017465  mov     rcx, [rcx+10h]
0x180017469  call    WPP_SF_s
0x18001746e  nop
0x18001746f  mov     rcx, [rsp+88h+pv]; pv
0x180017474  test    rcx, rcx
0x180017477  jz      short loc_18001747F
0x180017479  call    IASAttributeRelease
0x18001747e  nop
0x18001747f  lea     rcx, [rsp+88h+arg_18]
0x180017487  call    ??1?$auto_ptr@VEAPSession@@@std@@QEAA@XZ; std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(void)
0x18001748c  nop
0x18001748d  mov     rcx, [rsp+88h+Block]; Block
0x180017495  call    cs:__imp_free
0x18001749b  nop
0x18001749c  mov     rcx, [rsp+88h+var_30]
0x1800174a1  mov     rax, [rcx]
0x1800174a4  mov     rax, [rax+10h]
0x1800174a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ad  nop
0x1800174ae  mov     eax, 1
0x1800174b3  jmp     loc_1800178E8
0x1800174b8  mov     edx, 1FB0h
0x1800174bd  mov     r8d, 1
0x1800174c3  mov     rcx, [rsp+88h+var_30]
0x1800174c8  call    ?IASPeekAttribute@@YAPEAU_IASATTRIBUTE@@PEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASPeekAttribute(IAttributesRaw *,ulong,IASTYPEENUM)
0x1800174cd  test    rax, rax
0x1800174d0  jz      loc_1800175B9
0x1800174d6  cmp     [rax+18h], r14d
0x1800174da  jz      loc_1800175B9
0x1800174e0  mov     ecx, 168h; Size
0x1800174e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800174ea  mov     qword ptr [rsp+88h+Src], rax
0x1800174ef  test    rax, rax
0x1800174f2  jz      short loc_180017509
0x1800174f4  xor     r8d, r8d
0x1800174f7  lea     rdx, [rsp+88h+pv]
0x1800174fc  mov     rcx, rax
0x1800174ff  call    ??0EAPSession@@QEAA@AEBVIASAttribute@IASTL@@W4EAPHandlerType@0@@Z; EAPSession::EAPSession(IASTL::IASAttribute const &,EAPSession::EAPHandlerType)
0x180017504  mov     rbx, rax
0x180017507  jmp     short loc_18001750C
0x180017509  mov     rbx, r14
0x18001750c  mov     qword ptr [rsp+88h+Src], r14
0x180017511  mov     [rsp+88h+arg_18], rbx
0x180017519  lea     rcx, [rsp+88h+Src]
0x18001751e  call    ??1?$auto_ptr@VEAPSession@@@std@@QEAA@XZ; std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(void)
0x180017523  mov     rsi, [rsp+88h+Block]
0x18001752b  mov     [rsp+88h+Block], r14
0x180017533  mov     rcx, [rbx+0D0h]; Block
0x18001753a  cmp     rsi, rcx
0x18001753d  jz      short loc_180017545
0x18001753f  call    cs:__imp_free
0x180017545  mov     [rbx+0D0h], rsi
0x18001754c  mov     rax, cs:WPP_GLOBAL_Control
0x180017553  cmp     rax, r15
0x180017556  jz      short loc_1800175A7
0x180017558  cmp     [rax+19h], dil
0x18001755c  jb      short loc_1800175A7
0x18001755e  test    [rax+1Ch], dil
0x180017562  jz      short loc_1800175A7
0x180017564  mov     rdx, [rbx+0A0h]
0x18001756b  mov     rdx, [rdx+20h]
0x18001756f  lea     rcx, aSuccessfullyCr_0; "Successfully created new CRP Based EAP "...
0x180017576  call    WppDbgPrint
0x18001757b  mov     rax, [rbx+0A0h]
0x180017582  mov     edx, 0Dh
0x180017587  mov     rax, [rax+20h]
0x18001758b  mov     [rsp+88h+var_68], rax
0x180017590  lea     r8, WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids
0x180017597  mov     rcx, cs:WPP_GLOBAL_Control
0x18001759e  mov     rcx, [rcx+10h]
0x1800175a2  call    WPP_SF_sS
0x1800175a7  lea     rdx, [rsp+88h+var_38]
0x1800175ac  mov     rcx, rbx
0x1800175af  call    ?begin@EAPSession@@QEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z; EAPSession::begin(IASTL::IASRequest &)
0x1800175b4  jmp     loc_180017684
0x1800175b9  mov     ecx, 168h; Size
0x1800175be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800175c3  mov     qword ptr [rsp+88h+Src], rax
0x1800175c8  test    rax, rax
0x1800175cb  jz      short loc_1800175E5
0x1800175cd  mov     r8d, 2
0x1800175d3  lea     rdx, [rsp+88h+pv]
0x1800175d8  mov     rcx, rax
0x1800175db  call    ??0EAPSession@@QEAA@AEBVIASAttribute@IASTL@@W4EAPHandlerType@0@@Z; EAPSession::EAPSession(IASTL::IASAttribute const &,EAPSession::EAPHandlerType)
0x1800175e0  mov     rbx, rax
0x1800175e3  jmp     short loc_1800175E8
0x1800175e5  mov     rbx, r14
0x1800175e8  mov     qword ptr [rsp+88h+Src], r14
0x1800175ed  mov     [rsp+88h+arg_18], rbx
0x1800175f5  lea     rcx, [rsp+88h+Src]
0x1800175fa  call    ??1?$auto_ptr@VEAPSession@@@std@@QEAA@XZ; std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(void)
0x1800175ff  mov     rsi, [rsp+88h+Block]
0x180017607  mov     [rsp+88h+Block], r14
0x18001760f  mov     rcx, [rbx+0D0h]; Block
0x180017616  cmp     rsi, rcx
0x180017619  jz      short loc_180017621
0x18001761b  call    cs:__imp_free
0x180017621  mov     [rbx+0D0h], rsi
0x180017628  mov     rax, cs:WPP_GLOBAL_Control
0x18001762f  cmp     rax, r15
0x180017632  jz      short loc_180017684
0x180017634  cmp     [rax+19h], dil
0x180017638  jb      short loc_180017684
0x18001763a  test    [rax+1Ch], dil
0x18001763e  jz      short loc_180017684
0x180017640  mov     rdx, [rbx+0A0h]
0x180017647  mov     rdx, [rdx+20h]
0x18001764b  lea     rcx, aSuccessfullyCr_2; "Successfully created new RAP Based EAP "...
0x180017652  call    WppDbgPrint
0x180017657  mov     rax, [rbx+0A0h]
0x18001765e  mov     edx, 0Eh
0x180017663  mov     rax, [rax+20h]
0x180017667  mov     [rsp+88h+var_68], rax
0x18001766c  lea     r8, WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids
0x180017673  mov     rcx, cs:WPP_GLOBAL_Control
0x18001767a  mov     rcx, [rcx+10h]
0x18001767e  call    WPP_SF_sS
0x180017683  nop
0x180017684  mov     rcx, [rsp+88h+pv]; pv
0x180017689  test    rcx, rcx
0x18001768c  jz      loc_18001784F
0x180017692  call    IASAttributeRelease
0x180017697  jmp     loc_18001784F
0x18001769c  lea     rcx, [rsp+88h+var_38]; struct IASTL::IASRequest *
0x1800176a1  call    ?getEAPState@EAPBase@@KAPEAUEAPState@@AEAVIASRequest@IASTL@@@Z; EAPBase::getEAPState(IASTL::IASRequest &)
0x1800176a6  mov     rcx, [rax+8]
0x1800176aa  movzx   edx, byte ptr [rcx+21h]
0x1800176ae  movzx   eax, byte ptr [rcx+20h]
0x1800176b2  shl     eax, 8
0x1800176b5  or      edx, eax
0x1800176b7  shl     edx, 8
0x1800176ba  movzx   eax, byte ptr [rcx+22h]
0x1800176be  or      edx, eax
0x1800176c0  shl     edx, 8
0x1800176c3  movzx   eax, byte ptr [rcx+23h]
0x1800176c7  or      edx, eax; unsigned int
0x1800176c9  mov     rcx, cs:?pSessions@EAPBase@@1V?$auto_ptr@VEAPSessionTable@@@std@@A; this
0x1800176d0  call    ?remove@EAPSessionTable@@QEAAPEAVEAPSession@@K@Z; EAPSessionTable::remove(ulong)
0x1800176d5  mov     rbx, rax
0x1800176d8  mov     qword ptr [rsp+88h+Src], r14
0x1800176dd  mov     [rsp+88h+arg_18], rax
0x1800176e5  lea     rcx, [rsp+88h+Src]
0x1800176ea  call    ??1?$auto_ptr@VEAPSession@@@std@@QEAA@XZ; std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(void)
0x1800176ef  test    rbx, rbx
0x1800176f2  jnz     short loc_180017743
0x1800176f4  mov     rax, cs:WPP_GLOBAL_Control
0x1800176fb  cmp     rax, r15
0x1800176fe  jz      short loc_180017739
0x180017700  cmp     byte ptr [rax+19h], 2
0x180017704  jb      short loc_180017739
0x180017706  test    [rax+1Ch], dil
0x18001770a  jz      short loc_180017739
0x18001770c  lea     rcx, aSessionTimedOu; "Session timed out"
0x180017713  call    WppDbgPrint
0x180017718  lea     edx, [rbx+0Fh]
0x18001771b  lea     r9, aNpssvc; "NPSSVC"
0x180017722  lea     r8, WPP_b829fb7136a83693b1672dc98cdf59eb_Traceguids
0x180017729  mov     rcx, cs:WPP_GLOBAL_Control
0x180017730  mov     rcx, [rcx+10h]
0x180017734  call    WPP_SF_s
0x180017739  mov     ecx, 60h ; '`'; int
0x18001773e  call    ?Throw@EAPError@@SAXJ@Z; EAPError::Throw(long)
0x180017743  mov     rax, cs:WPP_GLOBAL_Control
0x18001774a  cmp     rax, r15
0x18001774d  jz      short loc_1800177A2
0x18001774f  cmp     [rax+19h], dil
0x180017753  jb      short loc_1800177A2
0x180017755  test    [rax+1Ch], dil
0x180017759  jz      short loc_1800177A2
0x18001775b  mov     r8, [rbx+0A0h]
0x180017762  mov     r8, [r8+20h]
0x180017766  mov     edx, [rbx+15Ch]
0x18001776c  lea     rcx, aSuccessfullyRe_0; "Successfully retrieved session (%d) for"...
0x180017773  call    WppDbgPrint
0x180017778  mov     rax, [rbx+0A0h]
0x18001777f  mov     rcx, [rax+20h]
0x180017783  mov     [rsp+88h+var_60], rcx
0x180017788  mov     eax, [rbx+15Ch]
0x18001778e  mov     dword ptr [rsp+88h+var_68], eax
0x180017792  mov     rcx, cs:WPP_GLOBAL_Control
0x180017799  mov     rcx, [rcx+10h]
0x18001779d  call    WPP_SF_sdS
0x1800177a2  mov     rsi, [rsp+88h+Block]
0x1800177aa  mov     [rsp+88h+Block], r14
0x1800177b2  mov     rcx, [rbx+0D0h]; Block
0x1800177b9  cmp     rsi, rcx
0x1800177bc  jz      short loc_1800177C4
0x1800177be  call    cs:__imp_free
0x1800177c4  mov     [rbx+0D0h], rsi
0x1800177cb  lea     rdx, [rsp+88h+var_38]; struct IASTL::IASRequest *
0x1800177d0  mov     rcx, rbx; this
0x1800177d3  call    ?onReceiveEvent@EAPSession@@QEAA_NAEAVIASRequest@IASTL@@@Z; EAPSession::onReceiveEvent(IASTL::IASRequest &)
0x1800177d8  test    al, al
0x1800177da  jz      short loc_18001782C
0x1800177dc  mov     rdx, rbx; struct EAPSession *
0x1800177df  mov     rcx, cs:?pSessions@EAPBase@@1V?$auto_ptr@VEAPSessionTable@@@std@@A; this
0x1800177e6  call    ?insert@EAPSessionTable@@QEAAXPEAVEAPSession@@@Z; EAPSessionTable::insert(EAPSession *)
0x1800177eb  mov     [rsp+88h+arg_18], r14
0x1800177f3  lea     rcx, [rsp+88h+arg_18]
0x1800177fb  call    ??1?$auto_ptr@VEAPSession@@@std@@QEAA@XZ; std::auto_ptr<EAPSession>::~auto_ptr<EAPSession>(void)
0x180017800  nop
0x180017801  mov     rcx, [rsp+88h+Block]; Block
0x180017809  call    cs:__imp_free
0x18001780f  nop
0x180017810  mov     rcx, [rsp+88h+var_30]
0x180017815  mov     rax, [rcx]
0x180017818  mov     rax, [rax+10h]
0x18001781c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017821  nop
0x180017822  mov     eax, 1
0x180017827  jmp     loc_1800178E8
0x18001782c  lea     rdx, [rsp+88h+var_38]; struct IASTL::IASRequest *
0x180017831  mov     rcx, rbx; this
0x180017834  call    ?injectProfile@EAPSession@@QEAAXAEAVIASRequest@IASTL@@@Z; EAPSession::injectProfile(IASTL::IASRequest &)
0x180017839  cmp     [rbx+110h], r14d
0x180017840  jnz     short loc_18001784F
0x180017842  lea     rdx, [rsp+88h+var_38]
0x180017847  mov     rcx, rbx
0x18001784a  call    ?processEAPPacket@EAPSession@@QEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z; EAPSession::processEAPPacket(IASTL::IASRequest &)
0x18001784f  lea     rcx, [rsp+88h+pv]; this
0x180017854  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x180017859  nop
0x18001785a  mov     rax, [rsp+88h+pv]
0x18001785f  mov     dword ptr [rax+8], 1FA9h
0x180017866  mov     qword ptr [rsp+88h+Src], rbx
0x18001786b  lea     r8, [rsp+88h+Src]; Src
0x180017870  mov     edx, 8; Size
  ... truncated ...
```
