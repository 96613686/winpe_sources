# CMSMQRuleSet::Delete(wchar_t *)

- ea: `0x18000aa80`
- end: `0x18000ae92`
- name: `?Delete@CMSMQRuleSet@@UEAAJPEA_W@Z`
- size: `1042`
- prototype: `__int64 __fastcall(HKEY *this, wchar_t *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002ec8`
- `0x1800041ec`
- `0x180004608`
- `0x180004a78`
- `0x180004d20`
- `0x180004d88`
- `0x18000544c`
- `0x18000a2d8`
- `0x18000aa80`
- `0x18000bd0c`
- `0x18000c62c`
- `0x18000d1a0`
- `0x180014d30`
- `0x180016b50`
- `0x180017028`
- `0x18001e380`

## pseudocode

```c
__int64 __fastcall CMSMQRuleSet::Delete(HKEY *this, wchar_t *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // eax
  __int64 result; // rax
  _bstr_t *v7; // rax
  CMSMQRuleSet *v8; // rcx
  unsigned int v9; // eax
  HKEY v10; // rbx
  CMSMQRuleSet *v11; // rcx
  unsigned int v12; // eax
  CRuntimeRuleInfo *v13; // r14
  CMSMQRuleSet *v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edx
  CMSMQRuleSet *v17; // rcx
  unsigned int v18; // eax
  __int16 v19; // [rsp+60h] [rbp-68h] BYREF
  HKEY v20; // [rsp+68h] [rbp-60h] BYREF
  char v21[8]; // [rsp+70h] [rbp-58h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 72) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v7 = _bstr_t::_bstr_t((_bstr_t *)&v20, a2);
      if ( (unsigned __int8)CRuntimeRuleInfo::IsValidRuleID(v7) )
      {
        std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
          (__int64)v21,
          (__int64)a2);
        std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::find(
          this + 148,
          &v20,
          v21);
        v10 = v20;
        if ( v20 == this[149] )
        {
          v11 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
          ((void (__stdcall *)(CMSMQRuleSet *, int))CMSMQRuleSet::SetComClassError)(v11, -1072820734);
          v19 = 200;
          LODWORD(v20) = -1072820734;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v12 = mqwcslen(L"trigobjs/ruleset");
            CMSMQTrace::MSMQTraceEvent(
              (__int64)g_pMSMQErrorLoggingTrace,
              1,
              1,
              2LL * (v12 + 1),
              L"trigobjs/ruleset",
              2,
              &v19,
              4,
              &v20,
              0,
              0);
          }
          std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
            (__int64)v21,
            1,
            0);
          result = 3222146562LL;
        }
        else
        {
          v13 = (CRuntimeRuleInfo *)*((_QWORD *)v20 + 8);
          if ( CRuntimeRuleInfo::Delete(v13, this[10]) )
          {
            CMSMQTriggerNotification::NotifyRuleDeleted((CMSMQTriggerNotification *)(this + 8), a2);
            std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::erase(
              this + 148,
              &v20,
              v10);
            if ( v13 )
              CRuntimeRuleInfo::`scalar deleting destructor'(v13, v16);
            std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
              (__int64)v21,
              1,
              0);
            result = 0;
          }
          else
          {
            ((void (__stdcall *)(CMSMQRuleSet *, int))CMSMQRuleSet::SetComClassError)(v14, -1072820714);
            v19 = 220;
            LODWORD(v20) = -1072820714;
            if ( g_pMSMQErrorLoggingTrace )
            {
              v15 = mqwcslen(L"trigobjs/ruleset");
              CMSMQTrace::MSMQTraceEvent(
                (__int64)g_pMSMQErrorLoggingTrace,
                1,
                1,
                2LL * (v15 + 1),
                L"trigobjs/ruleset",
                2,
                &v19,
                4,
                &v20,
                0,
                0);
            }
            std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
              (__int64)v21,
              1,
              0);
            result = 3222146582LL;
          }
        }
      }
      else
      {
        v8 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
        ((void (__stdcall *)(CMSMQRuleSet *, int))CMSMQRuleSet::SetComClassError)(v8, -1072820713);
        v19 = 190;
        LODWORD(v20) = -1072820713;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v9 = mqwcslen(L"trigobjs/ruleset");
          CMSMQTrace::MSMQTraceEvent(
            (__int64)g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v9 + 1),
            L"trigobjs/ruleset",
            2,
            &v19,
            4,
            &v20,
            0,
            0);
        }
        result = 3222146583LL;
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v17 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids);
        ((void (__stdcall *)(CMSMQRuleSet *, int))CMSMQRuleSet::SetComClassError)(v17, -1072820730);
        v19 = 230;
        LODWORD(v20) = -1072820730;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v18 = mqwcslen(L"trigobjs/ruleset");
          CMSMQTrace::MSMQTraceEvent(
            (__int64)g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v18 + 1),
            L"trigobjs/ruleset",
            2,
            &v19,
            4,
            &v20,
            0,
            0);
        }
        result = 3222146566LL;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000AE5F);
      }
    }
  }
  else
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
      WPP_SF_(v4[2], 30, &WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids);
    ((void (__stdcall *)(CMSMQRuleSet *, int))CMSMQRuleSet::SetComClassError)((CMSMQRuleSet *)v4, -1072820727);
    v19 = 180;
    LODWORD(v20) = -1072820727;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v5 = mqwcslen(L"trigobjs/ruleset");
      CMSMQTrace::MSMQTraceEvent(
        (__int64)g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v5 + 1),
        L"trigobjs/ruleset",
        2,
        &v19,
        4,
        &v20,
        0,
        0);
    }
    return 3222146569LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000aa80  mov     [rsp+arg_10], rbx
0x18000aa85  mov     [rsp+arg_18], rsi
0x18000aa8a  push    rdi
0x18000aa8b  push    r12
0x18000aa8d  push    r13
0x18000aa8f  push    r14
0x18000aa91  push    r15
0x18000aa93  sub     rsp, 0A0h
0x18000aa9a  mov     rax, cs:__security_cookie
0x18000aaa1  xor     rax, rsp
0x18000aaa4  mov     [rsp+0C8h+var_30], rax
0x18000aaac  mov     rsi, rdx
0x18000aaaf  mov     rdi, rcx
0x18000aab2  lea     r14, WPP_GLOBAL_Control
0x18000aab9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aac0  mov     r15d, 4
0x18000aac6  cmp     rcx, r14
0x18000aac9  jz      short loc_18000AAEF
0x18000aacb  test    [rcx+1Ch], r15b
0x18000aacf  jz      short loc_18000AAEF
0x18000aad1  lea     edx, [r15+19h]
0x18000aad5  mov     r9, rsi
0x18000aad8  lea     r8, WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids
0x18000aadf  mov     rcx, [rcx+10h]; LoggerHandle
0x18000aae3  call    WPP_SF_S
0x18000aae8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaef  xor     r13d, r13d
0x18000aaf2  cmp     [rdi+48h], r13b
0x18000aaf6  jnz     loc_18000ABA0
0x18000aafc  cmp     rcx, r14
0x18000aaff  jz      short loc_18000AB1B
0x18000ab01  test    byte ptr [rcx+1Ch], 1
0x18000ab05  jz      short loc_18000AB1B
0x18000ab07  lea     edx, [r13+1Eh]
0x18000ab0b  lea     r8, WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids
0x18000ab12  mov     rcx, [rcx+10h]
0x18000ab16  call    WPP_SF_
0x18000ab1b  mov     edi, 0C00E0E09h
0x18000ab20  mov     edx, edi; int
0x18000ab22  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000ab27  mov     eax, 0B4h
0x18000ab2c  mov     [rsp+0C8h+var_68], ax
0x18000ab31  mov     dword ptr [rsp+0C8h+var_60], edi
0x18000ab35  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000ab3c  jz      short loc_18000AB99
0x18000ab3e  lea     rbx, aTrigobjsRulese; "trigobjs/ruleset"
0x18000ab45  mov     rcx, rbx; wchar_t *
0x18000ab48  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000ab4d  lea     r9d, [rax+1]
0x18000ab51  add     r9, r9
0x18000ab54  mov     [rsp+0C8h+var_78], r13
0x18000ab59  mov     [rsp+0C8h+var_80], r13
0x18000ab5e  lea     rax, [rsp+0C8h+var_60]
0x18000ab63  mov     [rsp+0C8h+var_88], rax
0x18000ab68  mov     [rsp+0C8h+var_90], r15
0x18000ab6d  lea     rcx, [rsp+0C8h+var_68]
0x18000ab72  mov     [rsp+0C8h+var_98], rcx
0x18000ab77  mov     [rsp+0C8h+var_A0], 2
0x18000ab80  mov     [rsp+0C8h+var_A8], rbx
0x18000ab85  mov     edx, 1
0x18000ab8a  mov     r8d, edx
0x18000ab8d  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000ab94  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000ab99  mov     eax, edi
0x18000ab9b  jmp     loc_18000AE64
0x18000aba0  mov     rdx, rsi; wchar_t *
0x18000aba3  lea     rcx, [rsp+0C8h+var_60]; this
0x18000aba8  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000abad  mov     rcx, rax
0x18000abb0  call    ?IsValidRuleID@CRuntimeRuleInfo@@SA_NV_bstr_t@@@Z; CRuntimeRuleInfo::IsValidRuleID(_bstr_t)
0x18000abb5  test    al, al
0x18000abb7  jnz     loc_18000AC6C
0x18000abbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abc4  cmp     rcx, r14
0x18000abc7  jz      short loc_18000ABE7
0x18000abc9  test    byte ptr [rcx+1Ch], 1
0x18000abcd  jz      short loc_18000ABE7
0x18000abcf  mov     edx, 1Fh
0x18000abd4  mov     r9, rsi
0x18000abd7  lea     r8, WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids
0x18000abde  mov     rcx, [rcx+10h]; LoggerHandle
0x18000abe2  call    WPP_SF_S
0x18000abe7  mov     edi, 0C00E0E17h
0x18000abec  mov     edx, edi; int
0x18000abee  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000abf3  mov     eax, 0BEh
0x18000abf8  mov     [rsp+0C8h+var_68], ax
0x18000abfd  mov     dword ptr [rsp+0C8h+var_60], edi
0x18000ac01  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000ac08  jz      short loc_18000AC65
0x18000ac0a  lea     rbx, aTrigobjsRulese; "trigobjs/ruleset"
0x18000ac11  mov     rcx, rbx; wchar_t *
0x18000ac14  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000ac19  lea     r9d, [rax+1]
0x18000ac1d  add     r9, r9
0x18000ac20  mov     [rsp+0C8h+var_78], r13
0x18000ac25  mov     [rsp+0C8h+var_80], r13
0x18000ac2a  lea     rax, [rsp+0C8h+var_60]
0x18000ac2f  mov     [rsp+0C8h+var_88], rax
0x18000ac34  mov     [rsp+0C8h+var_90], r15
0x18000ac39  lea     rcx, [rsp+0C8h+var_68]
0x18000ac3e  mov     [rsp+0C8h+var_98], rcx
0x18000ac43  mov     [rsp+0C8h+var_A0], 2
0x18000ac4c  mov     [rsp+0C8h+var_A8], rbx
0x18000ac51  mov     edx, 1
0x18000ac56  mov     r8d, edx
0x18000ac59  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000ac60  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000ac65  mov     eax, edi
0x18000ac67  jmp     loc_18000AE64
0x18000ac6c  mov     rdx, rsi
0x18000ac6f  lea     rcx, [rsp+0C8h+var_58]
0x18000ac74  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x18000ac79  nop
0x18000ac7a  lea     r12, [rdi+4A0h]
0x18000ac81  lea     r8, [rsp+0C8h+var_58]
0x18000ac86  lea     rdx, [rsp+0C8h+var_60]
0x18000ac8b  mov     rcx, r12
0x18000ac8e  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAVCRuntimeRuleInfo@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAVCRuntimeRuleInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::find(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const &)
0x18000ac93  mov     rbx, [rsp+0C8h+var_60]
0x18000ac98  cmp     rbx, [rdi+4A8h]
0x18000ac9f  jnz     loc_18000AD76
0x18000aca5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acac  cmp     rcx, r14
0x18000acaf  jz      short loc_18000ACE0
0x18000acb1  test    byte ptr [rcx+1Ch], 1
0x18000acb5  jz      short loc_18000ACE0
0x18000acb7  lea     r9, [rsp+0C8h+var_50]
0x18000acbc  cmp     [rsp+0C8h+var_38], 8
0x18000acc5  cmovnb  r9, [rsp+0C8h+var_50]
0x18000accb  mov     edx, 20h ; ' '
0x18000acd0  lea     r8, WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids
0x18000acd7  mov     rcx, [rcx+10h]; LoggerHandle
0x18000acdb  call    WPP_SF_S
0x18000ace0  mov     edi, 0C00E0E02h
0x18000ace5  mov     edx, edi; int
0x18000ace7  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000acec  mov     eax, 0C8h
0x18000acf1  mov     [rsp+0C8h+var_68], ax
0x18000acf6  mov     dword ptr [rsp+0C8h+var_60], edi
0x18000acfa  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000ad01  jz      short loc_18000AD5F
0x18000ad03  lea     rbx, aTrigobjsRulese; "trigobjs/ruleset"
0x18000ad0a  mov     rcx, rbx; wchar_t *
0x18000ad0d  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000ad12  lea     r9d, [rax+1]
0x18000ad16  add     r9, r9
0x18000ad19  mov     [rsp+0C8h+var_78], r13
0x18000ad1e  mov     [rsp+0C8h+var_80], r13
0x18000ad23  lea     rax, [rsp+0C8h+var_60]
0x18000ad28  mov     [rsp+0C8h+var_88], rax
0x18000ad2d  mov     [rsp+0C8h+var_90], r15
0x18000ad32  lea     rax, [rsp+0C8h+var_68]
0x18000ad37  mov     [rsp+0C8h+var_98], rax
0x18000ad3c  mov     [rsp+0C8h+var_A0], 2
0x18000ad45  mov     [rsp+0C8h+var_A8], rbx
0x18000ad4a  mov     edx, 1
0x18000ad4f  mov     r8d, edx
0x18000ad52  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000ad59  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000ad5e  nop
0x18000ad5f  xor     r8d, r8d
0x18000ad62  mov     dl, 1
0x18000ad64  lea     rcx, [rsp+0C8h+var_58]
0x18000ad69  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000ad6e  nop
0x18000ad6f  mov     eax, edi
0x18000ad71  jmp     loc_18000AE64
0x18000ad76  mov     r14, [rbx+40h]
0x18000ad7a  mov     rdx, [rdi+50h]; HKEY
0x18000ad7e  mov     rcx, r14; this
0x18000ad81  call    ?Delete@CRuntimeRuleInfo@@QEAA_NPEAUHKEY__@@@Z; CRuntimeRuleInfo::Delete(HKEY__ *)
0x18000ad86  test    al, al
0x18000ad88  jnz     loc_18000AE21
0x18000ad8e  mov     edi, 0C00E0E16h
0x18000ad93  mov     edx, edi; int
0x18000ad95  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18000ad9a  mov     eax, 0DCh
0x18000ad9f  mov     [rsp+0C8h+var_68], ax
0x18000ada4  mov     dword ptr [rsp+0C8h+var_60], edi
0x18000ada8  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r13; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000adaf  jz      short loc_18000AE0D
0x18000adb1  lea     rbx, aTrigobjsRulese; "trigobjs/ruleset"
0x18000adb8  mov     rcx, rbx; wchar_t *
0x18000adbb  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000adc0  lea     r9d, [rax+1]
0x18000adc4  add     r9, r9
0x18000adc7  mov     [rsp+0C8h+var_78], r13
0x18000adcc  mov     [rsp+0C8h+var_80], r13
0x18000add1  lea     rax, [rsp+0C8h+var_60]
0x18000add6  mov     [rsp+0C8h+var_88], rax
0x18000addb  mov     [rsp+0C8h+var_90], r15
0x18000ade0  lea     rax, [rsp+0C8h+var_68]
0x18000ade5  mov     [rsp+0C8h+var_98], rax
0x18000adea  mov     [rsp+0C8h+var_A0], 2
0x18000adf3  mov     [rsp+0C8h+var_A8], rbx
0x18000adf8  mov     edx, 1
0x18000adfd  mov     r8d, edx
0x18000ae00  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000ae07  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000ae0c  nop
0x18000ae0d  xor     r8d, r8d
0x18000ae10  mov     dl, 1
0x18000ae12  lea     rcx, [rsp+0C8h+var_58]
0x18000ae17  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000ae1c  nop
0x18000ae1d  mov     eax, edi
0x18000ae1f  jmp     short loc_18000AE64
0x18000ae21  lea     rcx, [rdi+40h]; this
0x18000ae25  mov     rdx, rsi; wchar_t *
0x18000ae28  call    ?NotifyRuleDeleted@CMSMQTriggerNotification@@IEAAJPEA_W@Z; CMSMQTriggerNotification::NotifyRuleDeleted(wchar_t *)
0x18000ae2d  mov     r8, rbx
0x18000ae30  lea     rdx, [rsp+0C8h+var_60]
0x18000ae35  mov     rcx, r12
0x18000ae38  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAVCRuntimeRuleInfo@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAVCRuntimeRuleInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@V312@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::erase(std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::iterator)
0x18000ae3d  test    r14, r14
0x18000ae40  jz      short loc_18000AE4B
0x18000ae42  mov     rcx, r14; this
0x18000ae45  call    ??_GCRuntimeRuleInfo@@QEAAPEAXI@Z; CRuntimeRuleInfo::`scalar deleting destructor'(uint)
0x18000ae4a  nop
0x18000ae4b  xor     r8d, r8d
0x18000ae4e  mov     dl, 1
0x18000ae50  lea     rcx, [rsp+0C8h+var_58]
0x18000ae55  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000ae5a  nop
0x18000ae5b  xor     eax, eax
0x18000ae5d  jmp     short loc_18000AE64
0x18000ae5f  mov     eax, 0C00E0E06h
0x18000ae64  mov     rcx, [rsp+0C8h+var_30]
0x18000ae6c  xor     rcx, rsp; StackCookie
0x18000ae6f  call    __security_check_cookie
0x18000ae74  lea     r11, [rsp+0C8h+var_28]
0x18000ae7c  mov     rbx, [r11+40h]
0x18000ae80  mov     rsi, [r11+48h]
0x18000ae84  mov     rsp, r11
0x18000ae87  pop     r15
0x18000ae89  pop     r14
0x18000ae8b  pop     r13
0x18000ae8d  pop     r12
0x18000ae8f  pop     rdi
0x18000ae90  retn
```
