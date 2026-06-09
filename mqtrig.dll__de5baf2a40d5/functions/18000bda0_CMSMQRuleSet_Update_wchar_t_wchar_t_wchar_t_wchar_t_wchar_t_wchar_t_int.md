# CMSMQRuleSet::Update(wchar_t *,wchar_t *,wchar_t *,wchar_t *,wchar_t *,wchar_t *,int)

- ea: `0x18000bda0`
- end: `0x18000c334`
- name: `?Update@CMSMQRuleSet@@UEAAJPEA_W00000H@Z`
- size: `1428`
- prototype: `__int64 __fastcall(CMSMQRuleSet *this, wchar_t *, wchar_t *, wchar_t *, wchar_t *, wchar_t *, wchar_t *, int)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002ec8`
- `0x1800041ec`
- `0x180004a78`
- `0x180004d20`
- `0x180004d88`
- `0x18000544c`
- `0x180005740`
- `0x18000bd0c`
- `0x18000bda0`
- `0x18000c62c`
- `0x18000d250`
- `0x180014d30`
- `0x180016f70`
- `0x180016fb8`
- `0x180016ff0`
- `0x180017028`
- `0x1800173dc`
- `0x18001e380`

## pseudocode

```c
__int64 __fastcall CMSMQRuleSet::Update(
        CMSMQRuleSet *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4,
        wchar_t *a5,
        wchar_t *a6,
        wchar_t *a7,
        int a8)
{
  PVOID *v12; // rcx
  unsigned int v13; // esi
  __int16 v14; // ax
  unsigned int v15; // eax
  _bstr_t *v17; // rax
  CMSMQRuleSet *v18; // rcx
  _bstr_t *v19; // rax
  CMSMQRuleSet *v20; // rcx
  _bstr_t *v21; // rax
  CMSMQRuleSet *v22; // rcx
  _bstr_t *v23; // rax
  CMSMQRuleSet *v24; // rcx
  _bstr_t *v25; // rax
  CMSMQRuleSet *v26; // rcx
  CMSMQRuleSet *v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // eax
  CRuntimeRuleInfo *v30; // rdi
  CMSMQRuleSet *v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int16 v35; // [rsp+60h] [rbp-88h] BYREF
  __int64 v36; // [rsp+68h] [rbp-80h] BYREF
  wchar_t *v37; // [rsp+70h] [rbp-78h]
  _BYTE v38[40]; // [rsp+78h] [rbp-70h] BYREF

  v37 = a4;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)this + 72) )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_(v12[2], 43, &WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids);
    v13 = -1072820727;
    CMSMQRuleSet::SetComClassError((CMSMQRuleSet *)v12, -1072820727);
    v14 = 320;
LABEL_9:
    v35 = v14;
    LODWORD(v36) = v13;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v15 = mqwcslen(L"trigobjs/ruleset");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v15 + 1),
        L"trigobjs/ruleset",
        2,
        &v35,
        4,
        &v36,
        0,
        0);
    }
    return v13;
  }
  v17 = _bstr_t::_bstr_t((_bstr_t *)&v36, a2);
  if ( !(unsigned __int8)CRuntimeRuleInfo::IsValidRuleID(v17) )
  {
    v18 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v13 = -1072820713;
    CMSMQRuleSet::SetComClassError(v18, -1072820713);
    v14 = 330;
    goto LABEL_9;
  }
  v19 = _bstr_t::_bstr_t((_bstr_t *)&v36, a3);
  if ( !(unsigned __int8)CRuntimeRuleInfo::IsValidRuleID(v19) )
  {
    v20 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v13 = -1072820712;
    CMSMQRuleSet::SetComClassError(v20, -1072820712);
    v14 = 340;
    goto LABEL_9;
  }
  v21 = _bstr_t::_bstr_t((_bstr_t *)&v36, a5);
  if ( !(unsigned __int8)CRuntimeRuleInfo::IsValidRuleCondition(v21) )
  {
    v22 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v13 = -1072820711;
    CMSMQRuleSet::SetComClassError(v22, -1072820711);
    v14 = 350;
    goto LABEL_9;
  }
  v23 = _bstr_t::_bstr_t((_bstr_t *)&v36, a6);
  if ( !(unsigned __int8)CRuntimeRuleInfo::IsValidRuleAction(v23) )
  {
    v24 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v13 = -1072820710;
    CMSMQRuleSet::SetComClassError(v24, -1072820710);
    v14 = 360;
    goto LABEL_9;
  }
  v25 = _bstr_t::_bstr_t((_bstr_t *)&v36, a4);
  if ( !(unsigned __int8)CRuntimeRuleInfo::IsValidRuleDescription(v25) )
  {
    v26 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v13 = -1072820709;
    CMSMQRuleSet::SetComClassError(v26, -1072820709);
    v14 = 370;
    goto LABEL_9;
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
    v38,
    a2);
  std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::find(
    (char *)this + 1184,
    &v36,
    v38);
  if ( v36 == *((_QWORD *)this + 149) )
  {
    v27 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    CMSMQRuleSet::SetComClassError(v27, -1072820734);
    v35 = 380;
    LODWORD(v36) = -1072820734;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v29 = mqwcslen(L"trigobjs/ruleset");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v29 + 1),
        L"trigobjs/ruleset",
        2,
        &v35,
        4,
        &v36,
        0,
        0);
    }
    LOBYTE(v28) = 1;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v38, v28, 0);
    return 3222146562LL;
  }
  else
  {
    v30 = *(CRuntimeRuleInfo **)(v36 + 64);
    if ( a3 )
      _bstr_t::operator=((char *)v30 + 8, a3);
    if ( a5 )
      _bstr_t::operator=((char *)v30 + 40, a5);
    if ( a6 )
      _bstr_t::operator=((char *)v30 + 32, a6);
    _bstr_t::operator=((char *)v30 + 24, L"MSMQTriggerObjects.MSMQRuleHandler");
    if ( v37 )
      _bstr_t::operator=((char *)v30 + 16, v37);
    *((_BYTE *)v30 + 1072) = a8 != 0;
    if ( CRuntimeRuleInfo::Update(v30, *((HKEY *)this + 10)) )
    {
      CMSMQTriggerNotification::NotifyRuleUpdated((CMSMQRuleSet *)((char *)this + 64), a2, a3);
      LOBYTE(v34) = 1;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v38, v34, 0);
      return 0;
    }
    else
    {
      v31 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
      CMSMQRuleSet::SetComClassError(v31, -1072820723);
      v35 = 390;
      LODWORD(v36) = -1072820723;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v33 = mqwcslen(L"trigobjs/ruleset");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v33 + 1),
          L"trigobjs/ruleset",
          2,
          &v35,
          4,
          &v36,
          0,
          0);
      }
      LOBYTE(v32) = 1;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(v38, v32, 0);
      return 3222146573LL;
    }
  }
}

```

## disassembly

```asm
0x18000bda0  push    rbx
0x18000bda2  push    rsi
0x18000bda3  push    rdi
0x18000bda4  push    r12
0x18000bda6  push    r13
0x18000bda8  push    r14
0x18000bdaa  push    r15
0x18000bdac  sub     rsp, 0B0h
0x18000bdb3  mov     rax, cs:__security_cookie
0x18000bdba  xor     rax, rsp
0x18000bdbd  mov     [rsp+0E8h+var_48], rax
0x18000bdc5  mov     rdi, r9
0x18000bdc8  mov     [rsp+0E8h+var_78], r9
0x18000bdcd  mov     r15, r8
0x18000bdd0  mov     rsi, rdx
0x18000bdd3  mov     r14, rcx
0x18000bdd6  mov     r12, [rsp+0E8h+arg_20]
0x18000bdde  mov     r13, [rsp+0E8h+arg_28]
0x18000bde6  lea     rax, WPP_GLOBAL_Control
0x18000bded  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdf4  lea     rbx, WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids
0x18000bdfb  cmp     rcx, rax
0x18000bdfe  jz      short loc_18000BE28
0x18000be00  test    byte ptr [rcx+1Ch], 4
0x18000be04  jz      short loc_18000BE28
0x18000be06  mov     edx, 2Ah ; '*'
0x18000be0b  mov     r9, rsi
0x18000be0e  mov     r8, rbx
0x18000be11  mov     rcx, [rcx+10h]; LoggerHandle
0x18000be15  call    WPP_SF_S
0x18000be1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be21  lea     rax, WPP_GLOBAL_Control
0x18000be28  cmp     byte ptr [r14+48h], 0
0x18000be2d  jnz     loc_18000BED8
0x18000be33  cmp     rcx, rax
0x18000be36  jz      short loc_18000BE4F
0x18000be38  test    byte ptr [rcx+1Ch], 1
0x18000be3c  jz      short loc_18000BE4F
0x18000be3e  mov     edx, 2Bh ; '+'
0x18000be43  mov     r8, rbx
0x18000be46  mov     rcx, [rcx+10h]
0x18000be4a  call    WPP_SF_
0x18000be4f  mov     esi, 0C00E0E09h
0x18000be54  mov     edx, esi; int
0x18000be56  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000be5b  mov     eax, 140h
0x18000be60  mov     [rsp+0E8h+var_88], ax
0x18000be65  mov     dword ptr [rsp+0E8h+var_80], esi
0x18000be69  xor     edi, edi
0x18000be6b  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rdi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000be72  jz      short loc_18000BED1
0x18000be74  lea     rbx, aTrigobjsRulese; "trigobjs/ruleset"
0x18000be7b  mov     rcx, rbx; wchar_t *
0x18000be7e  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000be83  lea     r9d, [rax+1]
0x18000be87  add     r9, r9
0x18000be8a  mov     [rsp+0E8h+var_98], rdi
0x18000be8f  mov     [rsp+0E8h+var_A0], rdi
0x18000be94  lea     rax, [rsp+0E8h+var_80]
0x18000be99  mov     [rsp+0E8h+var_A8], rax
0x18000be9e  mov     [rsp+0E8h+var_B0], 4
0x18000bea7  lea     rcx, [rsp+0E8h+var_88]
0x18000beac  mov     [rsp+0E8h+var_B8], rcx
0x18000beb1  mov     [rsp+0E8h+var_C0], 2
0x18000beba  mov     [rsp+0E8h+var_C8], rbx
0x18000bebf  lea     edx, [rdi+1]
0x18000bec2  mov     r8d, edx
0x18000bec5  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000becc  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000bed1  mov     eax, esi
0x18000bed3  jmp     loc_18000C310
0x18000bed8  mov     rdx, rsi; wchar_t *
0x18000bedb  lea     rcx, [rsp+0E8h+var_80]; this
0x18000bee0  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000bee5  mov     rcx, rax
0x18000bee8  call    ?IsValidRuleID@CRuntimeRuleInfo@@SA_NV_bstr_t@@@Z; CRuntimeRuleInfo::IsValidRuleID(_bstr_t)
0x18000beed  test    al, al
0x18000beef  jnz     short loc_18000BF34
0x18000bef1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bef8  lea     rax, WPP_GLOBAL_Control
0x18000beff  cmp     rcx, rax
0x18000bf02  jz      short loc_18000BF1E
0x18000bf04  test    byte ptr [rcx+1Ch], 1
0x18000bf08  jz      short loc_18000BF1E
0x18000bf0a  mov     edx, 2Ch ; ','
0x18000bf0f  mov     r9, rsi
0x18000bf12  mov     r8, rbx
0x18000bf15  mov     rcx, [rcx+10h]; LoggerHandle
0x18000bf19  call    WPP_SF_S
0x18000bf1e  mov     esi, 0C00E0E17h
0x18000bf23  mov     edx, esi; int
0x18000bf25  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000bf2a  mov     eax, 14Ah
0x18000bf2f  jmp     loc_18000BE60
0x18000bf34  mov     rdx, r15; wchar_t *
0x18000bf37  lea     rcx, [rsp+0E8h+var_80]; this
0x18000bf3c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000bf41  mov     rcx, rax
0x18000bf44  call    ?IsValidRuleID@CRuntimeRuleInfo@@SA_NV_bstr_t@@@Z; CRuntimeRuleInfo::IsValidRuleID(_bstr_t)
0x18000bf49  test    al, al
0x18000bf4b  jnz     short loc_18000BF90
0x18000bf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf54  lea     rax, WPP_GLOBAL_Control
0x18000bf5b  cmp     rcx, rax
0x18000bf5e  jz      short loc_18000BF7A
0x18000bf60  test    byte ptr [rcx+1Ch], 1
0x18000bf64  jz      short loc_18000BF7A
0x18000bf66  mov     edx, 2Dh ; '-'
0x18000bf6b  mov     r9, r15
0x18000bf6e  mov     r8, rbx
0x18000bf71  mov     rcx, [rcx+10h]; LoggerHandle
0x18000bf75  call    WPP_SF_S
0x18000bf7a  mov     esi, 0C00E0E18h
0x18000bf7f  mov     edx, esi; int
0x18000bf81  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000bf86  mov     eax, 154h
0x18000bf8b  jmp     loc_18000BE60
0x18000bf90  mov     rdx, r12; wchar_t *
0x18000bf93  lea     rcx, [rsp+0E8h+var_80]; this
0x18000bf98  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000bf9d  mov     rcx, rax
0x18000bfa0  call    ?IsValidRuleCondition@CRuntimeRuleInfo@@SA_NV_bstr_t@@@Z; CRuntimeRuleInfo::IsValidRuleCondition(_bstr_t)
0x18000bfa5  test    al, al
0x18000bfa7  jnz     short loc_18000BFEC
0x18000bfa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfb0  lea     rax, WPP_GLOBAL_Control
0x18000bfb7  cmp     rcx, rax
0x18000bfba  jz      short loc_18000BFD6
0x18000bfbc  test    byte ptr [rcx+1Ch], 1
0x18000bfc0  jz      short loc_18000BFD6
0x18000bfc2  mov     edx, 2Eh ; '.'
0x18000bfc7  mov     r9, r12
0x18000bfca  mov     r8, rbx
0x18000bfcd  mov     rcx, [rcx+10h]; LoggerHandle
0x18000bfd1  call    WPP_SF_S
0x18000bfd6  mov     esi, 0C00E0E19h
0x18000bfdb  mov     edx, esi; int
0x18000bfdd  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000bfe2  mov     eax, 15Eh
0x18000bfe7  jmp     loc_18000BE60
0x18000bfec  mov     rdx, r13; wchar_t *
0x18000bfef  lea     rcx, [rsp+0E8h+var_80]; this
0x18000bff4  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000bff9  mov     rcx, rax
0x18000bffc  call    ?IsValidRuleAction@CRuntimeRuleInfo@@SA_NV_bstr_t@@@Z; CRuntimeRuleInfo::IsValidRuleAction(_bstr_t)
0x18000c001  test    al, al
0x18000c003  jnz     short loc_18000C048
0x18000c005  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c00c  lea     rax, WPP_GLOBAL_Control
0x18000c013  cmp     rcx, rax
0x18000c016  jz      short loc_18000C032
0x18000c018  test    byte ptr [rcx+1Ch], 1
0x18000c01c  jz      short loc_18000C032
0x18000c01e  mov     edx, 2Fh ; '/'
0x18000c023  mov     r9, r13
0x18000c026  mov     r8, rbx
0x18000c029  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c02d  call    WPP_SF_S
0x18000c032  mov     esi, 0C00E0E1Ah
0x18000c037  mov     edx, esi; int
0x18000c039  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000c03e  mov     eax, 168h
0x18000c043  jmp     loc_18000BE60
0x18000c048  mov     rdx, rdi; wchar_t *
0x18000c04b  lea     rcx, [rsp+0E8h+var_80]; this
0x18000c050  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000c055  mov     rcx, rax
0x18000c058  call    ?IsValidRuleDescription@CRuntimeRuleInfo@@SA_NV_bstr_t@@@Z; CRuntimeRuleInfo::IsValidRuleDescription(_bstr_t)
0x18000c05d  test    al, al
0x18000c05f  jnz     short loc_18000C0A4
0x18000c061  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c068  lea     rax, WPP_GLOBAL_Control
0x18000c06f  cmp     rcx, rax
0x18000c072  jz      short loc_18000C08E
0x18000c074  test    byte ptr [rcx+1Ch], 1
0x18000c078  jz      short loc_18000C08E
0x18000c07a  mov     edx, 30h ; '0'
0x18000c07f  mov     r9, rdi
0x18000c082  mov     r8, rbx
0x18000c085  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c089  call    WPP_SF_S
0x18000c08e  mov     esi, 0C00E0E1Bh
0x18000c093  mov     edx, esi; int
0x18000c095  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000c09a  mov     eax, 172h
0x18000c09f  jmp     loc_18000BE60
0x18000c0a4  mov     rdx, rsi
0x18000c0a7  lea     rcx, [rsp+0E8h+var_70]
0x18000c0ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x18000c0b1  nop
0x18000c0b2  lea     rcx, [r14+4A0h]
0x18000c0b9  lea     r8, [rsp+0E8h+var_70]
0x18000c0be  lea     rdx, [rsp+0E8h+var_80]
0x18000c0c3  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAVCRuntimeRuleInfo@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAVCRuntimeRuleInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::find(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const &)
0x18000c0c8  mov     rax, [rsp+0E8h+var_80]
0x18000c0cd  cmp     rax, [r14+4A8h]
0x18000c0d4  jnz     loc_18000C1A1
0x18000c0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0e1  lea     rax, WPP_GLOBAL_Control
0x18000c0e8  cmp     rcx, rax
0x18000c0eb  jz      short loc_18000C107
0x18000c0ed  test    byte ptr [rcx+1Ch], 1
0x18000c0f1  jz      short loc_18000C107
0x18000c0f3  mov     edx, 31h ; '1'
0x18000c0f8  mov     r9, rsi
0x18000c0fb  mov     r8, rbx
0x18000c0fe  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c102  call    WPP_SF_S
0x18000c107  mov     esi, 0C00E0E02h
0x18000c10c  mov     edx, esi; int
0x18000c10e  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000c113  mov     eax, 17Ch
0x18000c118  mov     [rsp+0E8h+var_88], ax
0x18000c11d  mov     dword ptr [rsp+0E8h+var_80], esi
0x18000c121  xor     edi, edi
0x18000c123  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rdi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000c12a  jz      short loc_18000C18A
0x18000c12c  lea     rbx, aTrigobjsRulese; "trigobjs/ruleset"
0x18000c133  mov     rcx, rbx; wchar_t *
0x18000c136  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000c13b  lea     r9d, [rax+1]
0x18000c13f  add     r9, r9
0x18000c142  mov     [rsp+0E8h+var_98], rdi
0x18000c147  mov     [rsp+0E8h+var_A0], rdi
0x18000c14c  lea     rax, [rsp+0E8h+var_80]
0x18000c151  mov     [rsp+0E8h+var_A8], rax
0x18000c156  mov     [rsp+0E8h+var_B0], 4
0x18000c15f  lea     rax, [rsp+0E8h+var_88]
0x18000c164  mov     [rsp+0E8h+var_B8], rax
0x18000c169  mov     [rsp+0E8h+var_C0], 2
0x18000c172  mov     [rsp+0E8h+var_C8], rbx
0x18000c177  lea     edx, [rdi+1]
0x18000c17a  mov     r8d, edx
0x18000c17d  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000c184  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000c189  nop
0x18000c18a  xor     r8d, r8d
0x18000c18d  mov     dl, 1
0x18000c18f  lea     rcx, [rsp+0E8h+var_70]
0x18000c194  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000c199  nop
0x18000c19a  mov     eax, esi
0x18000c19c  jmp     loc_18000C310
0x18000c1a1  mov     rdi, [rax+40h]
0x18000c1a5  test    r15, r15
0x18000c1a8  jz      short loc_18000C1B6
0x18000c1aa  lea     rcx, [rdi+8]
0x18000c1ae  mov     rdx, r15
0x18000c1b1  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18000c1b6  test    r12, r12
0x18000c1b9  jz      short loc_18000C1C7
0x18000c1bb  lea     rcx, [rdi+28h]
0x18000c1bf  mov     rdx, r12
0x18000c1c2  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18000c1c7  xor     r12d, r12d
0x18000c1ca  test    r13, r13
0x18000c1cd  jz      short loc_18000C1DB
0x18000c1cf  lea     rcx, [rdi+20h]
0x18000c1d3  mov     rdx, r13
0x18000c1d6  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18000c1db  lea     rcx, [rdi+18h]
0x18000c1df  lea     rdx, aMsmqtriggerobj; "MSMQTriggerObjects.MSMQRuleHandler"
0x18000c1e6  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18000c1eb  mov     rdx, [rsp+0E8h+var_78]
0x18000c1f0  test    rdx, rdx
0x18000c1f3  jz      short loc_18000C1FE
0x18000c1f5  lea     rcx, [rdi+10h]
0x18000c1f9  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x18000c1fe  cmp     [rsp+0E8h+arg_38], r12d
0x18000c206  setnz   al
0x18000c209  mov     [rdi+430h], al
0x18000c20f  mov     rdx, [r14+50h]; HKEY
0x18000c213  mov     rcx, rdi; this
0x18000c216  call    ?Update@CRuntimeRuleInfo@@QEAA_NPEAUHKEY__@@@Z; CRuntimeRuleInfo::Update(HKEY__ *)
0x18000c21b  test    al, al
0x18000c21d  jnz     loc_18000C2E7
0x18000c223  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c22a  lea     rax, WPP_GLOBAL_Control
0x18000c231  cmp     rcx, rax
0x18000c234  jz      short loc_18000C250
0x18000c236  test    byte ptr [rcx+1Ch], 1
0x18000c23a  jz      short loc_18000C250
0x18000c23c  mov     edx, 32h ; '2'
0x18000c241  mov     r9, rsi
0x18000c244  mov     r8, rbx
0x18000c247  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c24b  call    WPP_SF_S
0x18000c250  mov     edi, 0C00E0E0Dh
0x18000c255  mov     edx, edi; int
0x18000c257  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000c25c  mov     eax, 186h
0x18000c261  mov     [rsp+0E8h+var_88], ax
0x18000c266  mov     dword ptr [rsp+0E8h+var_80], edi
0x18000c26a  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r12; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000c271  jz      short loc_18000C2D3
0x18000c273  lea     rbx, aTrigobjsRulese; "trigobjs/ruleset"
0x18000c27a  mov     rcx, rbx; wchar_t *
0x18000c27d  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000c282  lea     r9d, [rax+1]
0x18000c286  add     r9, r9
  ... truncated ...
```
