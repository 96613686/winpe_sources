# CMSMQPropertyBag::Write(wchar_t *,tagVARIANT)

- ea: `0x180003640`
- end: `0x180003913`
- name: `?Write@CMSMQPropertyBag@@UEAAJPEA_WUtagVARIANT@@@Z`
- size: `723`
- prototype: `int(CMSMQPropertyBag *__hidden this, wchar_t *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002e90`
- `0x180002ec8`
- `0x180003640`
- `0x1800041ec`
- `0x180004b80`
- `0x180004d20`
- `0x180004dfc`
- `0x180014ae8`
- `0x180014d30`
- `0x18001e380`

## import_xrefs

- `msvcrt!free` at `0x1800037aa`
- `msvcrt!free` at `0x1800037aa`
- `OLEAUT32!__imp_SysStringLen` at `0x180003673`
- `OLEAUT32!__imp_SysStringLen` at `0x180003673`
- `OLEAUT32!__imp_VariantInit` at `0x18000371c`
- `OLEAUT32!__imp_VariantInit` at `0x18000371c`
- `OLEAUT32!__imp_VariantCopy` at `0x180003728`
- `OLEAUT32!__imp_VariantCopy` at `0x180003728`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CMSMQPropertyBag::Write(CMSMQPropertyBag *this, wchar_t *a2, struct tagVARIANT *a3)
{
  int v6; // eax
  VARIANTARG *v8; // rbx
  HRESULT v9; // r14d
  CMSMQTrace *v10; // rax
  int v11; // eax
  int v12; // eax
  __int16 v13; // [rsp+60h] [rbp-A8h] BYREF
  int v14; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t *v15; // [rsp+70h] [rbp-98h]
  _BYTE v16[16]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v17[40]; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG *v18; // [rsp+B0h] [rbp-58h]
  _BYTE v19[40]; // [rsp+B8h] [rbp-50h] BYREF

  v15 = a2;
  if ( SysStringLen(a2) )
  {
    v8 = (VARIANTARG *)MmAllocate(0x18u);
    VariantInit(v8);
    v9 = VariantCopy(v8, a3);
    if ( v9 < 0 )
    {
      free(v8);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9);
      v13 = 40;
      v14 = v9;
      v10 = g_pMSMQErrorLoggingTrace;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v11 = mqwcslen(L"trigobjs/cpropbag");
        CMSMQTrace::MSMQTraceEvent(
          (__int64)g_pMSMQErrorLoggingTrace,
          1,
          1u,
          2LL * (unsigned int)(v11 + 1),
          L"trigobjs/cpropbag",
          2,
          &v13,
          4,
          &v14,
          0,
          0);
        v10 = g_pMSMQErrorLoggingTrace;
      }
      v13 = 10;
      v14 = -2147467259;
      if ( v10 )
      {
        v12 = mqwcslen(L"trigobjs/cpropbag");
        CMSMQTrace::MSMQTraceEvent(
          (__int64)g_pMSMQErrorLoggingTrace,
          1,
          1u,
          2LL * (unsigned int)(v12 + 1),
          L"trigobjs/cpropbag",
          2,
          &v13,
          4,
          &v14,
          0,
          0);
      }
      return 2147500037LL;
    }
    else
    {
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
        (__int64)v19,
        (__int64)a2);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
        v17,
        v19);
      v18 = v8;
      std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,tagVARIANT *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,tagVARIANT *>>,0>>::insert(
        (char *)this + 24,
        v16,
        v17);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
        (__int64)v17,
        1,
        0);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
        (__int64)v19,
        1,
        0);
      return 0;
    }
  }
  else
  {
    v13 = 5;
    v14 = -1072820735;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v6 = mqwcslen(L"trigobjs/cpropbag");
      CMSMQTrace::MSMQTraceEvent(
        (__int64)g_pMSMQErrorLoggingTrace,
        1,
        1u,
        2LL * (unsigned int)(v6 + 1),
        L"trigobjs/cpropbag",
        2,
        &v13,
        4,
        &v14,
        0,
        0);
    }
    return 3222146561LL;
  }
}

```

## disassembly

```asm
0x180003640  mov     [rsp+arg_18], rbx
0x180003645  push    rsi
0x180003646  push    rdi
0x180003647  push    r14
0x180003649  sub     rsp, 0F0h
0x180003650  mov     rax, cs:__security_cookie
0x180003657  xor     rax, rsp
0x18000365a  mov     [rsp+108h+var_28], rax
0x180003662  mov     r14, r8
0x180003665  mov     rsi, rdx
0x180003668  mov     rdi, rcx
0x18000366b  mov     [rsp+108h+var_98], rdx
0x180003670  mov     rcx, rdx; pbstr
0x180003673  call    cs:__imp_SysStringLen
0x180003679  test    eax, eax
0x18000367b  jnz     loc_18000370C
0x180003681  mov     eax, 5
0x180003686  mov     [rsp+108h+var_A8], ax
0x18000368b  mov     edi, 0C00E0E01h
0x180003690  mov     [rsp+108h+var_A0], edi
0x180003694  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000369c  jz      short loc_180003705
0x18000369e  lea     rbx, aTrigobjsCpropb; "trigobjs/cpropbag"
0x1800036a5  mov     rcx, rbx; wchar_t *
0x1800036a8  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800036ad  lea     r9d, [rax+1]
0x1800036b1  add     r9, r9
0x1800036b4  mov     [rsp+108h+var_B8], 0
0x1800036bd  mov     [rsp+108h+var_C0], 0
0x1800036c6  lea     rax, [rsp+108h+var_A0]
0x1800036cb  mov     [rsp+108h+var_C8], rax
0x1800036d0  mov     [rsp+108h+var_D0], 4
0x1800036d9  lea     rcx, [rsp+108h+var_A8]
0x1800036de  mov     [rsp+108h+var_D8], rcx
0x1800036e3  mov     [rsp+108h+var_E0], 2
0x1800036ec  mov     qword ptr [rsp+108h+var_E8], rbx
0x1800036f1  mov     edx, 1
0x1800036f6  mov     r8d, edx
0x1800036f9  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180003700  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180003705  mov     eax, edi
0x180003707  jmp     loc_1800038EE
0x18000370c  mov     ecx, 18h; unsigned __int64
0x180003711  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180003716  mov     rbx, rax
0x180003719  mov     rcx, rax; pvarg
0x18000371c  call    cs:__imp_VariantInit
0x180003722  mov     rdx, r14; pvargSrc
0x180003725  mov     rcx, rbx; pvargDest
0x180003728  call    cs:__imp_VariantCopy
0x18000372e  mov     r14d, eax
0x180003731  test    eax, eax
0x180003733  js      short loc_1800037A7
0x180003735  mov     rdx, rsi
0x180003738  lea     rcx, [rsp+108h+var_50]
0x180003740  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x180003745  nop
0x180003746  lea     rdx, [rsp+108h+var_50]
0x18000374e  lea     rcx, [rsp+108h+var_80]
0x180003756  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@AEBV01@@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const &)
0x18000375b  mov     [rsp+108h+var_58], rbx
0x180003763  lea     r8, [rsp+108h+var_80]
0x18000376b  lea     rdx, [rsp+108h+var_90]
0x180003770  lea     rcx, [rdi+18h]
0x180003774  call    ?insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAUtagVARIANT@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAUtagVARIANT@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAUtagVARIANT@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAUtagVARIANT@@@std@@@2@$0A@@std@@@std@@_N@2@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAUtagVARIANT@@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,tagVARIANT *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,tagVARIANT *>>,0>>::insert(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,tagVARIANT *> const &)
0x180003779  nop
0x18000377a  xor     r8d, r8d
0x18000377d  mov     dl, 1
0x18000377f  lea     rcx, [rsp+108h+var_80]
0x180003787  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000378c  nop
0x18000378d  xor     r8d, r8d
0x180003790  mov     dl, 1
0x180003792  lea     rcx, [rsp+108h+var_50]
0x18000379a  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000379f  nop
0x1800037a0  xor     eax, eax
0x1800037a2  jmp     loc_1800038EE
0x1800037a7  mov     rcx, rbx; Block
0x1800037aa  call    cs:__imp_free
0x1800037b0  nop
0x1800037b1  lea     rax, WPP_GLOBAL_Control
0x1800037b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037bf  mov     edi, 0Ah
0x1800037c4  cmp     rcx, rax
0x1800037c7  jz      short loc_1800037E9
0x1800037c9  test    byte ptr [rcx+1Ch], 1
0x1800037cd  jz      short loc_1800037E9
0x1800037cf  mov     edx, edi
0x1800037d1  mov     dword ptr [rsp+108h+var_E8], r14d; char
0x1800037d6  mov     r9, rsi
0x1800037d9  lea     r8, WPP_493bdb46c745333eb5150e300391ccba_Traceguids
0x1800037e0  mov     rcx, [rcx+10h]; LoggerHandle
0x1800037e4  call    WPP_SF_SD
0x1800037e9  mov     eax, 28h ; '('
0x1800037ee  mov     [rsp+108h+var_A8], ax
0x1800037f3  mov     [rsp+108h+var_A0], r14d
0x1800037f8  mov     rax, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800037ff  lea     rbx, aTrigobjsCpropb; "trigobjs/cpropbag"
0x180003806  test    rax, rax
0x180003809  jz      short loc_180003872
0x18000380b  mov     rcx, rbx; wchar_t *
0x18000380e  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180003813  lea     r9d, [rax+1]
0x180003817  add     r9, r9
0x18000381a  mov     [rsp+108h+var_B8], 0
0x180003823  mov     [rsp+108h+var_C0], 0
0x18000382c  lea     rax, [rsp+108h+var_A0]
0x180003831  mov     [rsp+108h+var_C8], rax
0x180003836  mov     [rsp+108h+var_D0], 4
0x18000383f  lea     rax, [rsp+108h+var_A8]
0x180003844  mov     [rsp+108h+var_D8], rax
0x180003849  mov     [rsp+108h+var_E0], 2
0x180003852  mov     qword ptr [rsp+108h+var_E8], rbx
0x180003857  mov     edx, 1
0x18000385c  mov     r8d, edx
0x18000385f  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180003866  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000386b  mov     rax, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180003872  mov     [rsp+108h+var_A8], di
0x180003877  mov     edi, 80004005h
0x18000387c  mov     [rsp+108h+var_A0], edi
0x180003880  test    rax, rax
0x180003883  jz      short loc_1800038E5
0x180003885  mov     rcx, rbx; wchar_t *
0x180003888  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000388d  lea     r9d, [rax+1]
0x180003891  add     r9, r9
0x180003894  mov     [rsp+108h+var_B8], 0
0x18000389d  mov     [rsp+108h+var_C0], 0
0x1800038a6  lea     rax, [rsp+108h+var_A0]
0x1800038ab  mov     [rsp+108h+var_C8], rax
0x1800038b0  mov     [rsp+108h+var_D0], 4
0x1800038b9  lea     rcx, [rsp+108h+var_A8]
0x1800038be  mov     [rsp+108h+var_D8], rcx
0x1800038c3  mov     [rsp+108h+var_E0], 2
0x1800038cc  mov     qword ptr [rsp+108h+var_E8], rbx
0x1800038d1  mov     edx, 1
0x1800038d6  mov     r8d, edx
0x1800038d9  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800038e0  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800038e5  mov     eax, edi
0x1800038e7  jmp     short loc_1800038EE
0x1800038e9  mov     eax, 0C00E0E06h
0x1800038ee  mov     rcx, [rsp+108h+var_28]
0x1800038f6  xor     rcx, rsp; StackCookie
0x1800038f9  call    __security_check_cookie
0x1800038fe  mov     rbx, [rsp+108h+arg_18]
0x180003906  add     rsp, 0F0h
0x18000390d  pop     r14
0x18000390f  pop     rdi
0x180003910  pop     rsi
0x180003911  retn
```
