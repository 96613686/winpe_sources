# EAPSession::begin(IASTL::IASRequest &)

- ea: `0x180018fb0`
- end: `0x180019344`
- name: `?begin@EAPSession@@QEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z`
- size: `916`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017330`
- `0x180017b70`

## callees

- `0x18000acf4`
- `0x18000b2a0`
- `0x18000b2dc`
- `0x18000baa8`
- `0x18000bbf8`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000c808`
- `0x180016ce4`
- `0x180018aac`
- `0x180018b10`
- `0x180018fb0`
- `0x180019eac`
- `0x18001a0c4`
- `0x18001b084`
- `0x18001b5bc`
- `0x18001c018`
- `0x1800254a0`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019000`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019000`

## string_xrefs

- `0x18001902f`: `CoCreateInstance(CLSID_HostAuthenticatorApis) failed with 0x%x`
- `0x1800192bc`: `Succesfully created EAP Host session with session id %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EAPSession::begin(__int64 a1, struct IAttributesRaw **a2)
{
  _QWORD *v4; // r12
  HRESULT Instance; // ebx
  _BYTE *v6; // r8
  unsigned int v7; // edx
  unsigned int v8; // ecx
  _DWORD *v9; // r15
  bool v10; // r8
  void *v11; // rbx
  unsigned int v12; // r9d
  int v13; // esi
  unsigned int v14; // edi
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v17; // [rsp+58h] [rbp-A8h] BYREF
  struct _EAP_ERROR *v18; // [rsp+60h] [rbp-A0h] BYREF
  _EAP_ATTRIBUTES v19; // [rsp+68h] [rbp-98h] BYREF
  int v20; // [rsp+78h] [rbp-88h]
  char v21; // [rsp+7Ch] [rbp-84h]
  _BYTE *v22; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v23; // [rsp+88h] [rbp-78h]
  int v24; // [rsp+90h] [rbp-70h]
  char v25; // [rsp+94h] [rbp-6Ch]
  _BYTE v26[136]; // [rsp+98h] [rbp-68h] BYREF

  v4 = (_QWORD *)(a1 + 352);
  Instance = CoCreateInstance(
               &CLSID_HostAuthenticatorApis,
               0,
               4u,
               &GUID_5a8371a3_0c6d_487b_b3c8_46d785c4c940,
               (LPVOID *)(a1 + 352));
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("CoCreateInstance(CLSID_HostAuthenticatorApis) failed with 0x%x");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_69033002015f3c629418a4473ed337be_Traceguids);
    }
    _com_issue_error(Instance);
  }
  EAPSession::getEAPMethods((EAPSession *)a1, a2);
  if ( !*(_DWORD *)(a1 + 280) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("No authorized EAP types are found.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_69033002015f3c629418a4473ed337be_Traceguids, "NPSSVC");
    }
    EAPError::Throw(22);
  }
  v22 = v26;
  v23 = v26;
  v24 = 8;
  v25 = 0;
  LODWORD(pv) = 12;
  IASTL::IASAttributeVector::load((IASTL::IASAttributeVector *)&v22, a2[1], 1u, (unsigned int *)&pv);
  v6 = v22;
  if ( v22 != v23 )
  {
    v7 = 2048;
    do
    {
      v8 = *(_DWORD *)(*((_QWORD *)v6 + 1) + 24LL);
      if ( v7 <= v8 )
        v8 = v7;
      v7 = v8;
      v6 += 16;
    }
    while ( v6 != v23 );
    if ( v8 >= 0x40 )
    {
      *(_DWORD *)(a1 + 184) = v8 - 4;
      if ( v8 - 4 > 0x800 )
        *(_DWORD *)(a1 + 184) = 2048;
    }
  }
  v19 = 0;
  v20 = 0;
  v21 = 0;
  IASTL::IASAttributeVector::load((IASTL::IASAttributeVector *)&v19, a2[1]);
  v17 = 0;
  pv = 0;
  v9 = (_DWORD *)(a1 + 336);
  EAPSession::getAccountInfo(
    (EAPSession *)a1,
    (struct IASTL::IASRequest *)a2,
    (const unsigned __int16 **)&v17,
    (struct IASTL::IASAttribute *)&pv,
    (unsigned int *)(a1 + 336));
  v11 = pv;
  if ( pv )
    IASTL::IASAttributeVector::push_back((IASTL::IASAttributeVector *)&v19, (struct _IASATTRIBUTE *)pv, v10);
  FreeEAPAttributes((struct _EAP_ATTRIBUTES *)(a1 + 304));
  EAPTranslator::translate((EAPTranslator *)(a1 + 304), &v19, (const struct IASTL::IASAttributeVector *)8, v12);
  if ( !*(_DWORD *)(a1 + 272) )
    *v9 = 1024;
  v18 = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, _DWORD, unsigned __int16 *, __int64, struct _EAP_ERROR **))(*(_QWORD *)*v4 + 24LL))(
          *v4,
          (unsigned int)*v9,
          a1 + 280,
          a1 + 304,
          *(_DWORD *)(a1 + 184),
          v17,
          a1 + 348,
          &v18);
  if ( v13 < 0 )
  {
    FreeEAPError(v18);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("EapHostAuthenticatorBeginSession failed with 0x%x");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_69033002015f3c629418a4473ed337be_Traceguids);
    }
    _com_issue_error(v13);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Succesfully created EAP Host session with session id %d");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_69033002015f3c629418a4473ed337be_Traceguids);
  }
  v14 = EAPSession::processEAPPacket(a1, a2);
  if ( v11 )
    IASAttributeRelease(v11);
  IASTL::IASAttributeVector::~IASAttributeVector((IASTL::IASAttributeVector *)&v19);
  IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>((IASTL::IASAttributeVector *)&v22);
  return v14;
}

```

## disassembly

```asm
0x180018fb0  mov     [rsp-8+arg_10], rbx
0x180018fb5  push    rbp
0x180018fb6  push    rsi
0x180018fb7  push    rdi
0x180018fb8  push    r12
0x180018fba  push    r13
0x180018fbc  push    r14
0x180018fbe  push    r15
0x180018fc0  lea     rbp, [rsp-30h]
0x180018fc5  sub     rsp, 130h
0x180018fcc  mov     rax, cs:__security_cookie
0x180018fd3  xor     rax, rsp
0x180018fd6  mov     [rbp+60h+var_40], rax
0x180018fda  mov     r14, rdx
0x180018fdd  mov     rdi, rcx
0x180018fe0  lea     r12, [rcx+160h]
0x180018fe7  mov     [rsp+160h+ppv], r12; ppv
0x180018fec  lea     r9, _GUID_5a8371a3_0c6d_487b_b3c8_46d785c4c940; riid
0x180018ff3  xor     edx, edx; pUnkOuter
0x180018ff5  lea     r8d, [rdx+4]; dwClsContext
0x180018ff9  lea     rcx, CLSID_HostAuthenticatorApis; rclsid
0x180019000  call    cs:__imp_CoCreateInstance
0x180019006  mov     ebx, eax
0x180019008  xor     esi, esi
0x18001900a  test    eax, eax
0x18001900c  jns     short loc_180019061
0x18001900e  lea     rcx, WPP_GLOBAL_Control
0x180019015  mov     rdx, cs:WPP_GLOBAL_Control
0x18001901c  cmp     rdx, rcx
0x18001901f  jz      short loc_180019059
0x180019021  cmp     byte ptr [rdx+19h], 2
0x180019025  jb      short loc_180019059
0x180019027  test    byte ptr [rdx+1Ch], 4
0x18001902b  jz      short loc_180019059
0x18001902d  mov     edx, eax
0x18001902f  lea     rcx, aCocreateinstan; "CoCreateInstance(CLSID_HostAuthenticato"...
0x180019036  call    WppDbgPrint
0x18001903b  lea     edx, [rsi+13h]
0x18001903e  mov     dword ptr [rsp+160h+ppv], ebx
0x180019042  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x180019049  mov     rcx, cs:WPP_GLOBAL_Control
0x180019050  mov     rcx, [rcx+10h]
0x180019054  call    WPP_SF_sd
0x180019059  mov     ecx, ebx; int
0x18001905b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180019061  mov     rdx, r14; struct IASTL::IASRequest *
0x180019064  mov     rcx, rdi; this
0x180019067  call    ?getEAPMethods@EAPSession@@QEAAXAEAVIASRequest@IASTL@@@Z; EAPSession::getEAPMethods(IASTL::IASRequest &)
0x18001906c  lea     r13, [rdi+118h]
0x180019073  cmp     [r13+0], esi
0x180019077  jnz     short loc_1800190D2
0x180019079  lea     rcx, WPP_GLOBAL_Control
0x180019080  mov     rax, cs:WPP_GLOBAL_Control
0x180019087  cmp     rax, rcx
0x18001908a  jz      short loc_1800190C7
0x18001908c  cmp     byte ptr [rax+19h], 2
0x180019090  jb      short loc_1800190C7
0x180019092  test    byte ptr [rax+1Ch], 4
0x180019096  jz      short loc_1800190C7
0x180019098  lea     rcx, aNoAuthorizedEa; "No authorized EAP types are found."
0x18001909f  call    WppDbgPrint
0x1800190a4  mov     edx, 14h
0x1800190a9  lea     r9, aNpssvc; "NPSSVC"
0x1800190b0  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x1800190b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190be  mov     rcx, [rcx+10h]
0x1800190c2  call    WPP_SF_s
0x1800190c7  mov     ecx, 16h; int
0x1800190cc  call    ?Throw@EAPError@@SAXJ@Z; EAPError::Throw(long)
0x1800190d2  lea     rax, [rbp+60h+var_C8]
0x1800190d6  mov     [rbp+60h+var_E0], rax
0x1800190da  lea     rax, [rbp+60h+var_C8]
0x1800190de  mov     [rbp+60h+var_D8], rax
0x1800190e2  mov     [rbp+60h+var_D0], 8
0x1800190e9  mov     [rbp+60h+var_CC], sil
0x1800190ed  mov     dword ptr [rsp+160h+pv], 0Ch
0x1800190f5  lea     r9, [rsp+160h+pv]; unsigned int *
0x1800190fa  mov     r8d, 1; unsigned int
0x180019100  mov     rdx, [r14+8]; struct IAttributesRaw *
0x180019104  lea     rcx, [rbp+60h+var_E0]; this
0x180019108  call    ?load@IASAttributeVector@IASTL@@QEAAKPEAUIAttributesRaw@@KPEAK@Z; IASTL::IASAttributeVector::load(IAttributesRaw *,ulong,ulong *)
0x18001910d  mov     r8, [rbp+60h+var_E0]
0x180019111  mov     r9, [rbp+60h+var_D8]
0x180019115  cmp     r8, r9
0x180019118  jz      short loc_180019154
0x18001911a  mov     r10d, 800h
0x180019120  mov     edx, r10d
0x180019123  mov     rax, [r8+8]
0x180019127  mov     ecx, [rax+18h]
0x18001912a  cmp     edx, ecx
0x18001912c  cmovbe  ecx, edx
0x18001912f  mov     edx, ecx
0x180019131  add     r8, 10h
0x180019135  cmp     r8, r9
0x180019138  jnz     short loc_180019123
0x18001913a  cmp     ecx, 40h ; '@'
0x18001913d  jb      short loc_180019154
0x18001913f  lea     eax, [rcx-4]
0x180019142  mov     [rdi+0B8h], eax
0x180019148  cmp     eax, r10d
0x18001914b  jbe     short loc_180019154
0x18001914d  mov     [rdi+0B8h], r10d
0x180019154  xorps   xmm0, xmm0
0x180019157  movdqu  xmmword ptr [rsp+160h+var_F8.dwNumberOfAttributes], xmm0
0x18001915d  mov     [rsp+160h+var_E8], esi
0x180019161  mov     [rsp+160h+var_E4], sil
0x180019166  mov     rdx, [r14+8]; struct IAttributesRaw *
0x18001916a  lea     rcx, [rsp+160h+var_F8]; this
0x18001916f  call    ?load@IASAttributeVector@IASTL@@QEAAKPEAUIAttributesRaw@@@Z; IASTL::IASAttributeVector::load(IAttributesRaw *)
0x180019174  mov     [rsp+160h+var_108], rsi
0x180019179  mov     [rsp+160h+pv], rsi
0x18001917e  lea     r15, [rdi+150h]
0x180019185  mov     [rsp+160h+ppv], r15; unsigned int *
0x18001918a  lea     r9, [rsp+160h+pv]; struct IASTL::IASAttribute *
0x18001918f  lea     r8, [rsp+160h+var_108]; unsigned __int16 **
0x180019194  mov     rdx, r14; struct IASTL::IASRequest *
0x180019197  mov     rcx, rdi; this
0x18001919a  call    ?getAccountInfo@EAPSession@@IEAAXAEAVIASRequest@IASTL@@AEAPEBGAEAVIASAttribute@3@AEAK@Z; EAPSession::getAccountInfo(IASTL::IASRequest &,ushort const * &,IASTL::IASAttribute &,ulong &)
0x18001919f  mov     rbx, [rsp+160h+pv]
0x1800191a4  test    rbx, rbx
0x1800191a7  jz      short loc_1800191B6
0x1800191a9  mov     rdx, rbx; struct _IASATTRIBUTE *
0x1800191ac  lea     rcx, [rsp+160h+var_F8]; this
0x1800191b1  call    ?push_back@IASAttributeVector@IASTL@@QEAAXPEAU_IASATTRIBUTE@@_N@Z; IASTL::IASAttributeVector::push_back(_IASATTRIBUTE *,bool)
0x1800191b6  lea     rsi, [rdi+130h]
0x1800191bd  mov     rcx, rsi; struct _EAP_ATTRIBUTES *
0x1800191c0  call    ?FreeEAPAttributes@@YAXAEAU_EAP_ATTRIBUTES@@@Z; FreeEAPAttributes(_EAP_ATTRIBUTES &)
0x1800191c5  mov     r8d, 8; struct IASTL::IASAttributeVector *
0x1800191cb  lea     rdx, [rsp+160h+var_F8]; struct _EAP_ATTRIBUTES *
0x1800191d0  mov     rcx, rsi; this
0x1800191d3  call    ?translate@EAPTranslator@@YAXAEAU_EAP_ATTRIBUTES@@AEBVIASAttributeVector@IASTL@@K@Z; EAPTranslator::translate(_EAP_ATTRIBUTES &,IASTL::IASAttributeVector const &,ulong)
0x1800191d8  cmp     dword ptr [rdi+110h], 0
0x1800191df  jnz     short loc_1800191E8
0x1800191e1  mov     dword ptr [r15], 400h
0x1800191e8  mov     [rsp+160h+var_100], 0
0x1800191f1  mov     rcx, [r12]
0x1800191f5  lea     r12, [rdi+15Ch]
0x1800191fc  mov     rax, [rcx]
0x1800191ff  lea     rdx, [rsp+160h+var_100]
0x180019204  mov     [rsp+160h+var_128], rdx
0x180019209  mov     [rsp+160h+var_130], r12
0x18001920e  mov     rdx, [rsp+160h+var_108]
0x180019213  mov     [rsp+160h+var_138], rdx
0x180019218  mov     edx, [rdi+0B8h]
0x18001921e  mov     dword ptr [rsp+160h+ppv], edx
0x180019222  mov     r9, rsi
0x180019225  mov     r8, r13
0x180019228  mov     edx, [r15]
0x18001922b  mov     rax, [rax+18h]
0x18001922f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019234  mov     esi, eax
0x180019236  test    eax, eax
0x180019238  jns     short loc_180019299
0x18001923a  mov     rcx, [rsp+160h+var_100]; struct _EAP_ERROR *
0x18001923f  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x180019244  lea     rcx, WPP_GLOBAL_Control
0x18001924b  mov     rdx, cs:WPP_GLOBAL_Control
0x180019252  cmp     rdx, rcx
0x180019255  jz      short loc_180019291
0x180019257  cmp     byte ptr [rdx+19h], 2
0x18001925b  jb      short loc_180019291
0x18001925d  test    byte ptr [rdx+1Ch], 4
0x180019261  jz      short loc_180019291
0x180019263  mov     edx, esi
0x180019265  lea     rcx, aEaphostauthent_9; "EapHostAuthenticatorBeginSession failed"...
0x18001926c  call    WppDbgPrint
0x180019271  mov     edx, 15h
0x180019276  mov     dword ptr [rsp+160h+ppv], esi
0x18001927a  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x180019281  mov     rcx, cs:WPP_GLOBAL_Control
0x180019288  mov     rcx, [rcx+10h]
0x18001928c  call    WPP_SF_sd
0x180019291  mov     ecx, esi; int
0x180019293  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180019299  lea     rcx, WPP_GLOBAL_Control
0x1800192a0  mov     rax, cs:WPP_GLOBAL_Control
0x1800192a7  cmp     rax, rcx
0x1800192aa  jz      short loc_1800192EC
0x1800192ac  cmp     byte ptr [rax+19h], 4
0x1800192b0  jb      short loc_1800192EC
0x1800192b2  test    byte ptr [rax+1Ch], 4
0x1800192b6  jz      short loc_1800192EC
0x1800192b8  mov     edx, [r12]
0x1800192bc  lea     rcx, aSuccesfullyCre; "Succesfully created EAP Host session wi"...
0x1800192c3  call    WppDbgPrint
0x1800192c8  mov     edx, 16h
0x1800192cd  mov     eax, [r12]
0x1800192d1  mov     dword ptr [rsp+160h+ppv], eax
0x1800192d5  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x1800192dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192e3  mov     rcx, [rcx+10h]
0x1800192e7  call    WPP_SF_sd
0x1800192ec  mov     rdx, r14
0x1800192ef  mov     rcx, rdi
0x1800192f2  call    ?processEAPPacket@EAPSession@@QEAA?AW4_IASREQUESTSTATUS@@AEAVIASRequest@IASTL@@@Z; EAPSession::processEAPPacket(IASTL::IASRequest &)
0x1800192f7  mov     edi, eax
0x1800192f9  test    rbx, rbx
0x1800192fc  jz      short loc_180019307
0x1800192fe  mov     rcx, rbx; pv
0x180019301  call    IASAttributeRelease
0x180019306  nop
0x180019307  lea     rcx, [rsp+160h+var_F8]; this
0x18001930c  call    ??1IASAttributeVector@IASTL@@QEAA@XZ; IASTL::IASAttributeVector::~IASAttributeVector(void)
0x180019311  nop
0x180019312  lea     rcx, [rbp+60h+var_E0]; this
0x180019316  call    ??1?$IASAttributeVectorWithBuffer@$09@IASTL@@QEAA@XZ; IASTL::IASAttributeVectorWithBuffer<10>::~IASAttributeVectorWithBuffer<10>(void)
0x18001931b  mov     eax, edi
0x18001931d  mov     rcx, [rbp+60h+var_40]
0x180019321  xor     rcx, rsp; StackCookie
0x180019324  call    __security_check_cookie
0x180019329  mov     rbx, [rsp+160h+arg_10]
0x180019331  add     rsp, 130h
0x180019338  pop     r15
0x18001933a  pop     r14
0x18001933c  pop     r13
0x18001933e  pop     r12
0x180019340  pop     rdi
0x180019341  pop     rsi
0x180019342  pop     rbp
0x180019343  retn
```
