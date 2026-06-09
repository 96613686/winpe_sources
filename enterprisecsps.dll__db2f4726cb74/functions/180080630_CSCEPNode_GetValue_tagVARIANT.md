# CSCEPNode::GetValue(tagVARIANT *)

- ea: `0x180080630`
- end: `0x180080b9f`
- name: `?GetValue@CSCEPNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `1391`
- prototype: `int(CSCEPNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001180`
- `0x180003624`
- `0x180008de0`
- `0x180015888`
- `0x180019fd8`
- `0x180023f1c`
- `0x180025450`
- `0x18003f3a0`
- `0x18003f6f0`
- `0x180080094`
- `0x180080630`
- `0x180081a28`
- `0x180082be8`
- `0x180082e64`
- `0x180082ffc`
- `0x180083068`
- `0x180083600`
- `0x1800d1fa8`
- `0x1800d23bc`
- `0x1800fd680`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008086a`
- `OLEAUT32!__imp_SysAllocString` at `0x180080ac3`
- `OLEAUT32!__imp_SysAllocString` at `0x18008086a`
- `OLEAUT32!__imp_SysAllocString` at `0x180080ac3`
- `OLEAUT32!__imp_VariantInit` at `0x180080744`
- `OLEAUT32!__imp_VariantInit` at `0x180080744`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800809a6`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800809a6`

## string_xrefs

- `0x180080965`: `\Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CSCEPNode::GetValue(CSCEPNode *this, struct tagVARIANT *a2)
{
  CSCEPNode *v3; // rsi
  __int64 Imei; // rax
  int SCEPRegistryKeyPath; // edi
  unsigned __int64 v7; // rdx
  char v8; // r13
  unsigned int v9; // r12d
  int v10; // eax
  int Challenge; // eax
  wil *v12; // rcx
  const OLECHAR *v13; // rcx
  BSTR v14; // rax
  const unsigned __int16 *v15; // rdx
  int DWORD; // eax
  unsigned int IsRemoteDesktopSession; // eax
  int v18; // r8d
  int v19; // r9d
  bool v20; // r12
  DWORD v21; // ecx
  CClientCertScepLogger *Logger; // rax
  const unsigned __int16 *v23; // r8
  bool v24[4]; // [rsp+30h] [rbp-AE8h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-AE4h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-AE0h] BYREF
  __int16 v27; // [rsp+40h] [rbp-AD8h] BYREF
  char v28; // [rsp+42h] [rbp-AD6h]
  __int64 v29; // [rsp+48h] [rbp-AD0h]
  __int64 v30; // [rsp+50h] [rbp-AC8h] BYREF
  CSCEPNode *v31; // [rsp+58h] [rbp-AC0h]
  OLECHAR *psz[2]; // [rsp+60h] [rbp-AB8h] BYREF
  __m128i v33; // [rsp+70h] [rbp-AA8h]
  _QWORD Src[4]; // [rsp+80h] [rbp-A98h] BYREF
  unsigned __int16 *v35[2]; // [rsp+A0h] [rbp-A78h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-A68h]
  _OWORD v37[2]; // [rsp+C0h] [rbp-A58h] BYREF
  unsigned __int16 v38[1280]; // [rsp+E0h] [rbp-A38h] BYREF

  v3 = this;
  v31 = this;
  v30 = 0;
  *(_OWORD *)v35 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v35[0]) = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v26 = 0;
  v37[0] = 0;
  v37[1] = si128;
  LOWORD(v37[0]) = 0;
  if ( (unsigned int)(*((_DWORD *)this + 11) - 27) <= 2 )
  {
    std::wstring::_Tidy_deallocate(v37);
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v27);
    std::wstring::_Tidy_deallocate(v35);
    return 2248146946LL;
  }
  Imei = CellularIdentity::GetImei(*((_QWORD *)this + 2) + 104LL, Src);
  std::wstring::operator=(v35, Imei);
  std::wstring::_Tidy_deallocate(Src);
  v38[0] = 0;
  VariantInit(a2);
  if ( !a2 )
  {
    SCEPRegistryKeyPath = -2147024809;
    goto LABEL_51;
  }
  if ( !*((_DWORD *)v3 + 11) )
  {
    SCEPRegistryKeyPath = -2046820335;
    goto LABEL_51;
  }
  SCEPRegistryKeyPath = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)v3 + 3) + 88LL))(
                          *((_QWORD *)v3 + 3),
                          *((unsigned int *)v3 + 10),
                          &v30);
  if ( SCEPRegistryKeyPath < 0 )
    goto LABEL_51;
  v8 = 1;
  if ( CSCEPNode::m_fIsUser == 1 )
  {
    SCEPRegistryKeyPath = AutoImpersonate::ImpersonateTargetedUser(
                            (AutoImpersonate *)&v27,
                            *((struct CConfigServiceProvider2Impl **)v3 + 2));
    if ( SCEPRegistryKeyPath < 0 )
      goto LABEL_51;
  }
  v9 = 3;
  if ( *((_DWORD *)v3 + 11) != 3 )
  {
    SCEPRegistryKeyPath = CSCEPNode::GetSCEPRegistryKeyPath(
                            v38,
                            v7,
                            1,
                            *((struct IConfigManager2URI **)v3 + 3),
                            *((struct CConfigServiceProvider2Impl **)v3 + 2),
                            0);
    if ( SCEPRegistryKeyPath < 0 )
      goto LABEL_51;
    if ( (unsigned int)(*((_DWORD *)v3 + 11) - 19) > 2 )
    {
LABEL_49:
      SCEPRegistryKeyPath = CCspSimpleRegHelper::GetValueAsVariant(
                              CSCEPNode::m_hCurrentHive,
                              v38,
                              v30,
                              *((unsigned int *)v3 + 12),
                              a2);
LABEL_50:
      if ( SCEPRegistryKeyPath >= 0 )
        goto LABEL_54;
LABEL_51:
      Logger = CClientCertScepLogger::GetLogger();
      v23 = (const unsigned __int16 *)v35;
      if ( si128.m128i_i64[1] > 7uLL )
        v23 = v35[0];
      CClientCertScepLogger::LogSCEPCspGetValue(Logger, SCEPRegistryKeyPath, v23, *((const unsigned __int16 **)v3 + 4));
      goto LABEL_54;
    }
    *(_OWORD *)psz = 0;
    v33 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(psz[0]) = 0;
    SCEPRegistryKeyPath = UtilsReadCertThumbprint(CSCEPNode::m_hCurrentHive, v38, psz);
    if ( SCEPRegistryKeyPath < 0 )
    {
LABEL_25:
      std::wstring::_Tidy_deallocate(psz);
      goto LABEL_51;
    }
    if ( !v33.m128i_i64[0] )
    {
LABEL_48:
      std::wstring::_Tidy_deallocate(psz);
      goto LABEL_49;
    }
    std::wstring::wstring(Src, v38);
    std::wstring::_Append<unsigned short>(Src);
    v15 = (const unsigned __int16 *)Src;
    if ( Src[3] > 7u )
      v15 = (const unsigned __int16 *)Src[0];
    DWORD = OmaDmRegistryGetDWORD(CSCEPNode::m_hCurrentHive, v15, L"KeyProtection", &v26);
    SCEPRegistryKeyPath = DWORD;
    if ( DWORD == -2147024894 )
    {
      v26 = 3;
    }
    else
    {
      if ( DWORD < 0 )
        goto LABEL_32;
      v9 = v26;
    }
    if ( v9 != 4 )
    {
LABEL_40:
      std::wstring::_Tidy_deallocate(Src);
      if ( v8 )
      {
        v24[0] = 0;
        v21 = 98304;
        if ( !CSCEPNode::m_fIsUser )
          v21 = 163840;
        v25 = 0;
        SCEPRegistryKeyPath = UtilsIsCertValid(v21);
        if ( SCEPRegistryKeyPath < 0 )
          goto LABEL_25;
        if ( !v24[0] )
        {
          SCEPRegistryKeyPath = UtilsUpdateRegistryForInvalidCert(CSCEPNode::m_hCurrentHive, v38, v25);
          if ( SCEPRegistryKeyPath < 0 )
            goto LABEL_25;
          if ( *((_DWORD *)v3 + 11) == 19 )
          {
            a2->llVal = (LONGLONG)SysAllocString(&Class);
            a2->vt = 8;
            std::wstring::_Tidy_deallocate(psz);
            goto LABEL_54;
          }
        }
      }
      goto LABEL_48;
    }
    v24[0] = 0;
    IsRemoteDesktopSession = UtilsIsRemoteDesktopSession(v24);
    SCEPRegistryKeyPath = IsRemoteDesktopSession;
    v20 = v24[0];
    if ( (unsigned int)dword_180155C20 > 4 )
    {
      v25 = IsRemoteDesktopSession;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        dword_180155C20,
        (unsigned int)&dword_1801349BC,
        v18,
        v19,
        (__int64)&v25,
        (__int64)v24);
    }
    if ( SCEPRegistryKeyPath >= 0 )
    {
      if ( v20 )
        v8 = 0;
      goto LABEL_40;
    }
LABEL_32:
    std::wstring::_Tidy_deallocate(Src);
    goto LABEL_25;
  }
  if ( (unsigned int)dword_180155C20 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180155C20,
      &byte_1801349FF,
      0);
  v10 = CSCEPNode::GetSCEPRegistryKeyPath(
          v38,
          v7,
          0,
          *((struct IConfigManager2URI **)v3 + 3),
          *((struct CConfigServiceProvider2Impl **)v3 + 2),
          0);
  SCEPRegistryKeyPath = v10;
  if ( v10 < 0 )
    goto LABEL_51;
  try
  {
    *(_OWORD *)psz = 0;
    v33 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(psz[0]) = 0;
    Challenge = UtilsReadChallenge(CSCEPNode::m_hCurrentHive, v38, psz);
  }
  catch ( ... )
  {
    v25 = wil::ResultFromCaughtException(v12);
    SCEPRegistryKeyPath = v25;
    v3 = v31;
    goto LABEL_50;
  }
  SCEPRegistryKeyPath = Challenge;
  if ( Challenge < 0 )
  {
    std::wstring::_Tidy_deallocate(psz);
    goto LABEL_51;
  }
  v13 = (const OLECHAR *)psz;
  if ( v33.m128i_i64[1] > 7uLL )
    v13 = psz[0];
  v14 = SysAllocString(v13);
  a2->llVal = (LONGLONG)v14;
  if ( !v14 )
  {
    SCEPRegistryKeyPath = -2147024882;
    std::wstring::_Tidy_deallocate(psz);
    goto LABEL_51;
  }
  a2->vt = 8;
  std::wstring::_Tidy_deallocate(psz);
LABEL_54:
  std::wstring::_Tidy_deallocate(v37);
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v27);
  std::wstring::_Tidy_deallocate(v35);
  return (unsigned int)SCEPRegistryKeyPath;
}

```

## disassembly

```asm
0x180080630  mov     [rsp+arg_10], rbx
0x180080635  mov     [rsp+arg_18], rsi
0x18008063a  push    rdi
0x18008063b  push    r12
0x18008063d  push    r13
0x18008063f  push    r14
0x180080641  push    r15
0x180080643  sub     rsp, 0AF0h
0x18008064a  mov     rax, cs:__security_cookie
0x180080651  xor     rax, rsp
0x180080654  mov     [rsp+0B18h+var_38], rax
0x18008065c  mov     r14, rdx
0x18008065f  mov     rsi, rcx
0x180080662  mov     [rsp+0B18h+var_AC0], rcx
0x180080667  xor     ebx, ebx
0x180080669  mov     [rsp+0B18h+var_AC8], rbx
0x18008066e  xorps   xmm0, xmm0
0x180080671  movups  xmmword ptr [rsp+0B18h+var_A78], xmm0
0x180080679  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180080681  movdqu  [rsp+0B18h+var_A68], xmm1
0x18008068a  mov     word ptr [rsp+0B18h+var_A78], bx
0x180080692  mov     [rsp+0B18h+var_AD8], bx
0x180080697  mov     [rsp+0B18h+var_AD6], bl
0x18008069b  mov     [rsp+0B18h+var_AD0], rbx
0x1800806a0  mov     [rsp+0B18h+var_AE0], ebx
0x1800806a4  movups  [rsp+0B18h+var_A58], xmm0
0x1800806ac  movdqu  [rsp+0B18h+var_A48], xmm1
0x1800806b5  mov     word ptr [rsp+0B18h+var_A58], bx
0x1800806bd  mov     eax, [rcx+2Ch]
0x1800806c0  add     eax, 0FFFFFFE5h
0x1800806c3  cmp     eax, 2
0x1800806c6  ja      short loc_1800806F8
0x1800806c8  lea     rcx, [rsp+0B18h+var_A58]
0x1800806d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800806d5  nop
0x1800806d6  lea     rcx, [rsp+0B18h+var_AD8]; this
0x1800806db  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800806e0  nop
0x1800806e1  lea     rcx, [rsp+0B18h+var_A78]
0x1800806e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800806ee  mov     eax, 86000002h
0x1800806f3  jmp     loc_180080B71
0x1800806f8  mov     rcx, [rcx+10h]
0x1800806fc  add     rcx, 68h ; 'h'
0x180080700  lea     rdx, [rsp+0B18h+Src]
0x180080708  cmp     cs:?m_fIsCertStore@CSCEPNode@@0HA, ebx; int CSCEPNode::m_fIsCertStore
0x18008070e  jz      short loc_180080717
0x180080710  call    ?GetImei@CellularIdentity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CellularIdentity::GetImei(void)
0x180080715  jmp     short loc_18008071C
0x180080717  call    ?GetImei@CellularIdentity@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CellularIdentity::GetImei(void)
0x18008071c  mov     rdx, rax
0x18008071f  lea     rcx, [rsp+0B18h+var_A78]
0x180080727  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008072c  lea     rcx, [rsp+0B18h+Src]
0x180080734  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080739  mov     [rsp+0B18h+var_A38], bx
0x180080741  mov     rcx, r14; pvarg
0x180080744  call    cs:__imp_VariantInit
0x18008074b  nop     dword ptr [rax+rax+00h]
0x180080750  test    r14, r14
0x180080753  jnz     short loc_18008075F
0x180080755  mov     edi, 80070057h
0x18008075a  jmp     loc_180080B15
0x18008075f  cmp     [rsi+2Ch], ebx
0x180080762  jnz     short loc_18008076E
0x180080764  mov     edi, 86000011h
0x180080769  jmp     loc_180080B15
0x18008076e  mov     rcx, [rsi+18h]
0x180080772  mov     rax, [rcx]
0x180080775  lea     r8, [rsp+0B18h+var_AC8]
0x18008077a  mov     edx, [rsi+28h]
0x18008077d  mov     rax, [rax+58h]
0x180080781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080786  mov     edi, eax
0x180080788  test    eax, eax
0x18008078a  js      loc_180080B15
0x180080790  mov     r13d, 1
0x180080796  cmp     cs:?m_fIsUser@CSCEPNode@@0HA, r13d; int CSCEPNode::m_fIsUser
0x18008079d  jnz     short loc_1800807B7
0x18008079f  mov     rdx, [rsi+10h]; struct CConfigServiceProvider2Impl *
0x1800807a3  lea     rcx, [rsp+0B18h+var_AD8]; this
0x1800807a8  call    ?ImpersonateTargetedUser@AutoImpersonate@@QEAAJPEAVCConfigServiceProvider2Impl@@@Z; AutoImpersonate::ImpersonateTargetedUser(CConfigServiceProvider2Impl *)
0x1800807ad  mov     edi, eax
0x1800807af  test    eax, eax
0x1800807b1  js      loc_180080B15
0x1800807b7  mov     r12d, 3
0x1800807bd  cmp     [rsi+2Ch], r12d
0x1800807c1  jnz     loc_1800808B8
0x1800807c7  mov     eax, cs:dword_180155C20
0x1800807cd  cmp     eax, 4
0x1800807d0  jbe     short loc_1800807E8
0x1800807d2  xor     r8d, r8d
0x1800807d5  lea     rdx, byte_1801349FF
0x1800807dc  lea     rcx, dword_180155C20
0x1800807e3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800807e8  mov     [rsp+0B18h+var_AF0], ebx; int
0x1800807ec  mov     rax, [rsi+10h]
0x1800807f0  mov     [rsp+0B18h+var_AF8], rax; struct CConfigServiceProvider2Impl *
0x1800807f5  mov     r9, [rsi+18h]; struct IConfigManager2URI *
0x1800807f9  xor     r8d, r8d; int
0x1800807fc  lea     rcx, [rsp+0B18h+var_A38]; unsigned __int16 *
0x180080804  call    ?GetSCEPRegistryKeyPath@CSCEPNode@@CAJPEAG_KHPEAUIConfigManager2URI@@PEAVCConfigServiceProvider2Impl@@H@Z; CSCEPNode::GetSCEPRegistryKeyPath(ushort *,unsigned __int64,int,IConfigManager2URI *,CConfigServiceProvider2Impl *,int)
0x180080809  mov     edi, eax
0x18008080b  test    eax, eax
0x18008080d  js      loc_180080B15
0x180080813  xorps   xmm0, xmm0
0x180080816  movups  xmmword ptr [rsp+0B18h+psz], xmm0
0x18008081b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180080823  movdqu  [rsp+0B18h+var_AA8], xmm1
0x180080829  mov     word ptr [rsp+0B18h+psz], bx
0x18008082e  lea     r8, [rsp+0B18h+psz]
0x180080833  lea     rdx, [rsp+0B18h+var_A38]
0x18008083b  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x180080842  call    ?UtilsReadChallenge@@YAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UtilsReadChallenge(HKEY__ *,ushort const *,std::wstring &)
0x180080847  mov     edi, eax
0x180080849  test    eax, eax
0x18008084b  jns     short loc_180080859
0x18008084d  lea     rcx, [rsp+0B18h+psz]
0x180080852  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080857  jmp     short loc_18008088F
0x180080859  lea     rcx, [rsp+0B18h+psz]
0x18008085e  cmp     qword ptr [rsp+0B18h+var_AA8+8], 7
0x180080864  cmova   rcx, [rsp+0B18h+psz]; psz
0x18008086a  call    cs:__imp_SysAllocString
0x180080871  nop     dword ptr [rax+rax+00h]
0x180080876  mov     [r14+8], rax
0x18008087a  test    rax, rax
0x18008087d  jnz     short loc_180080894
0x18008087f  mov     edi, 8007000Eh
0x180080884  lea     rcx, [rsp+0B18h+psz]
0x180080889  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008088e  nop
0x18008088f  jmp     loc_180080B15
0x180080894  mov     word ptr [r14], 8
0x18008089a  lea     rcx, [rsp+0B18h+psz]
0x18008089f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800808a4  nop
0x1800808a5  jmp     loc_180080B43
0x1800808aa  mov     edi, [rsp+0B18h+var_AE4]
0x1800808ae  mov     rsi, [rsp+0B18h+var_AC0]
0x1800808b3  jmp     loc_180080B11
0x1800808b8  mov     [rsp+0B18h+var_AF0], ebx; int
0x1800808bc  mov     rax, [rsi+10h]
0x1800808c0  mov     [rsp+0B18h+var_AF8], rax; struct CConfigServiceProvider2Impl *
0x1800808c5  mov     r9, [rsi+18h]; struct IConfigManager2URI *
0x1800808c9  mov     r8d, r13d; int
0x1800808cc  lea     rcx, [rsp+0B18h+var_A38]; unsigned __int16 *
0x1800808d4  call    ?GetSCEPRegistryKeyPath@CSCEPNode@@CAJPEAG_KHPEAUIConfigManager2URI@@PEAVCConfigServiceProvider2Impl@@H@Z; CSCEPNode::GetSCEPRegistryKeyPath(ushort *,unsigned __int64,int,IConfigManager2URI *,CConfigServiceProvider2Impl *,int)
0x1800808d9  mov     edi, eax
0x1800808db  test    eax, eax
0x1800808dd  js      loc_180080B15
0x1800808e3  mov     eax, [rsi+2Ch]
0x1800808e6  sub     eax, 13h
0x1800808e9  cmp     eax, 2
0x1800808ec  ja      loc_180080AED
0x1800808f2  xorps   xmm0, xmm0
0x1800808f5  movups  xmmword ptr [rsp+0B18h+psz], xmm0
0x1800808fa  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180080902  movdqu  [rsp+0B18h+var_AA8], xmm1
0x180080908  mov     word ptr [rsp+0B18h+psz], bx
0x18008090d  lea     r8, [rsp+0B18h+psz]
0x180080912  lea     rdx, [rsp+0B18h+var_A38]
0x18008091a  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x180080921  call    ?UtilsReadCertThumbprint@@YAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UtilsReadCertThumbprint(HKEY__ *,ushort const *,std::wstring &)
0x180080926  mov     edi, eax
0x180080928  test    eax, eax
0x18008092a  jns     short loc_18008093B
0x18008092c  lea     rcx, [rsp+0B18h+psz]
0x180080931  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080936  jmp     loc_180080B15
0x18008093b  cmp     qword ptr [rsp+0B18h+var_AA8], rbx
0x180080940  jz      loc_180080AE3
0x180080946  lea     rdx, [rsp+0B18h+var_A38]
0x18008094e  lea     rcx, [rsp+0B18h+Src]
0x180080956  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008095b  nop
0x18008095c  mov     r15d, 8
0x180080962  mov     r8d, r15d
0x180080965  lea     rdx, aInstall_0; "\\Install"
0x18008096c  lea     rcx, [rsp+0B18h+Src]; Src
0x180080974  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180080979  lea     rdx, [rsp+0B18h+Src]
0x180080981  cmp     [rsp+0B18h+var_A80], 7
0x18008098a  cmova   rdx, [rsp+0B18h+Src]
0x180080993  lea     r9, [rsp+0B18h+var_AE0]
0x180080998  lea     r8, aKeyprotection_0; "KeyProtection"
0x18008099f  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x1800809a6  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800809ad  nop     dword ptr [rax+rax+00h]
0x1800809b2  mov     edi, eax
0x1800809b4  cmp     eax, 80070002h
0x1800809b9  jnz     short loc_1800809C2
0x1800809bb  mov     [rsp+0B18h+var_AE0], r12d
0x1800809c0  jmp     short loc_1800809DD
0x1800809c2  test    eax, eax
0x1800809c4  jns     short loc_1800809D8
0x1800809c6  lea     rcx, [rsp+0B18h+Src]
0x1800809ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800809d3  jmp     loc_18008092C
0x1800809d8  mov     r12d, [rsp+0B18h+var_AE0]
0x1800809dd  cmp     r12d, 4
0x1800809e1  jnz     short loc_180080A3E
0x1800809e3  mov     [rsp+0B18h+var_AE8], bl
0x1800809e7  lea     rcx, [rsp+0B18h+var_AE8]; bool *
0x1800809ec  call    ?UtilsIsRemoteDesktopSession@@YAJAEA_N@Z; UtilsIsRemoteDesktopSession(bool &)
0x1800809f1  mov     edi, eax
0x1800809f3  mov     ecx, cs:dword_180155C20
0x1800809f9  cmp     ecx, r12d
0x1800809fc  jbe     short loc_180080A2E
0x1800809fe  mov     r12b, [rsp+0B18h+var_AE8]
0x180080a03  mov     [rsp+0B18h+var_AE8], r12b
0x180080a08  mov     [rsp+0B18h+var_AE4], eax
0x180080a0c  lea     rax, [rsp+0B18h+var_AE8]
0x180080a11  mov     qword ptr [rsp+0B18h+var_AF0], rax
0x180080a16  lea     rax, [rsp+0B18h+var_AE4]
0x180080a1b  mov     [rsp+0B18h+var_AF8], rax
0x180080a20  lea     rdx, dword_1801349BC
0x180080a27  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180080a2c  jmp     short loc_180080A33
0x180080a2e  mov     r12b, [rsp+0B18h+var_AE8]
0x180080a33  test    edi, edi
0x180080a35  js      short loc_1800809C6
0x180080a37  test    r12b, r12b
0x180080a3a  cmovnz  r13d, ebx
0x180080a3e  lea     rcx, [rsp+0B18h+Src]
0x180080a46  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080a4b  test    r13b, r13b
0x180080a4e  jz      loc_180080AE3
0x180080a54  mov     [rsp+0B18h+var_AE8], bl
0x180080a58  mov     ecx, 18000h
0x180080a5d  mov     eax, 28000h
0x180080a62  cmp     cs:?m_fIsUser@CSCEPNode@@0HA, ebx; int CSCEPNode::m_fIsUser
0x180080a68  cmovz   ecx, eax; dwFlags
0x180080a6b  mov     [rsp+0B18h+var_AE4], ebx
0x180080a6f  lea     r9, [rsp+0B18h+var_AE4]
0x180080a74  lea     r8, [rsp+0B18h+var_AE8]
0x180080a79  lea     rdx, [rsp+0B18h+psz]
0x180080a7e  call    ?UtilsIsCertValid@@YAJKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAK@Z; UtilsIsCertValid(ulong,std::wstring const &,bool &,ulong &)
0x180080a83  mov     edi, eax
0x180080a85  test    eax, eax
0x180080a87  js      loc_18008092C
0x180080a8d  cmp     [rsp+0B18h+var_AE8], bl
0x180080a91  jnz     short loc_180080AE3
0x180080a93  mov     r8d, [rsp+0B18h+var_AE4]; unsigned int
0x180080a98  lea     rdx, [rsp+0B18h+var_A38]; unsigned __int16 *
0x180080aa0  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x180080aa7  call    ?UtilsUpdateRegistryForInvalidCert@@YAJPEAUHKEY__@@PEBGK@Z; UtilsUpdateRegistryForInvalidCert(HKEY__ *,ushort const *,ulong)
0x180080aac  mov     edi, eax
0x180080aae  test    eax, eax
0x180080ab0  js      loc_18008092C
0x180080ab6  cmp     dword ptr [rsi+2Ch], 13h
0x180080aba  jnz     short loc_180080AE3
0x180080abc  lea     rcx, Class; psz
0x180080ac3  call    cs:__imp_SysAllocString
0x180080aca  nop     dword ptr [rax+rax+00h]
0x180080acf  mov     [r14+8], rax
0x180080ad3  mov     [r14], r15w
0x180080ad7  lea     rcx, [rsp+0B18h+psz]
0x180080adc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080ae1  jmp     short loc_180080B43
0x180080ae3  lea     rcx, [rsp+0B18h+psz]
0x180080ae8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080aed  mov     [rsp+0B18h+var_AF8], r14
0x180080af2  mov     r9d, [rsi+30h]
0x180080af6  mov     r8, [rsp+0B18h+var_AC8]
0x180080afb  lea     rdx, [rsp+0B18h+var_A38]
0x180080b03  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CSCEPNode::m_hCurrentHive
0x180080b0a  call    ?GetValueAsVariant@CCspSimpleRegHelper@@SAJPEAUHKEY__@@PEBG1W4ConfigDataType@@PEAUtagVARIANT@@@Z; CCspSimpleRegHelper::GetValueAsVariant(HKEY__ *,ushort const *,ushort const *,ConfigDataType,tagVARIANT *)
0x180080b0f  mov     edi, eax
0x180080b11  test    edi, edi
0x180080b13  jns     short loc_180080B43
0x180080b15  call    ?GetLogger@CClientCertScepLogger@@SAPEAV1@XZ; CClientCertScepLogger::GetLogger(void)
0x180080b1a  lea     r8, [rsp+0B18h+var_A78]
0x180080b22  cmp     qword ptr [rsp+0B18h+var_A68+8], 7
0x180080b2b  cmova   r8, [rsp+0B18h+var_A78]; unsigned __int16 *
0x180080b34  mov     r9, [rsi+20h]; unsigned __int16 *
0x180080b38  mov     edx, edi; int
0x180080b3a  mov     rcx, rax; this
0x180080b3d  call    ?LogSCEPCspGetValue@CClientCertScepLogger@@QEAAXJPEBG0@Z; CClientCertScepLogger::LogSCEPCspGetValue(long,ushort const *,ushort const *)
0x180080b42  nop
0x180080b43  lea     rcx, [rsp+0B18h+var_A58]
0x180080b4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080b50  nop
0x180080b51  lea     rcx, [rsp+0B18h+var_AD8]; this
0x180080b56  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180080b5b  nop
0x180080b5c  lea     rcx, [rsp+0B18h+var_A78]
0x180080b64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080b69  mov     eax, edi
0x180080b6b  jmp     short loc_180080B71
0x180080b6d  mov     eax, [rsp+0B18h+var_AE4]
0x180080b71  mov     rcx, [rsp+0B18h+var_38]
0x180080b79  xor     rcx, rsp; StackCookie
0x180080b7c  call    __security_check_cookie
0x180080b81  lea     r11, [rsp+0B18h+var_28]
0x180080b89  mov     rbx, [r11+40h]
0x180080b8d  mov     rsi, [r11+48h]
0x180080b91  mov     rsp, r11
0x180080b94  pop     r15
0x180080b96  pop     r14
  ... truncated ...
```
