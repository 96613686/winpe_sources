# CMSMQPropertyBag::Read(wchar_t *,tagVARIANT *)

- ea: `0x180003460`
- end: `0x180003632`
- name: `?Read@CMSMQPropertyBag@@UEAAJPEA_WPEAUtagVARIANT@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(CMSMQPropertyBag *this, wchar_t *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002ec8`
- `0x180003460`
- `0x1800041ec`
- `0x180004a78`
- `0x180004d20`
- `0x180014d30`
- `0x18001e380`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180003498`
- `OLEAUT32!__imp_SysStringLen` at `0x180003498`
- `OLEAUT32!__imp_VariantInit` at `0x180003534`
- `OLEAUT32!__imp_VariantInit` at `0x180003534`
- `OLEAUT32!__imp_VariantCopy` at `0x180003582`
- `OLEAUT32!__imp_VariantCopy` at `0x180003582`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMSMQPropertyBag::Read(CMSMQPropertyBag *this, wchar_t *a2, struct tagVARIANT *a3)
{
  __int16 v6; // ax
  int v7; // eax
  __int64 v9; // r14
  HRESULT v10; // ebx
  int v11; // eax
  __int16 v12; // [rsp+60h] [rbp-9h] BYREF
  int v13; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v14[40]; // [rsp+70h] [rbp+7h] BYREF

  if ( a3 )
  {
    if ( !SysStringLen(a2) )
    {
      v6 = 26;
      goto LABEL_5;
    }
    VariantInit(a3);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
      (__int64)v14,
      (__int64)a2);
    v9 = *(_QWORD *)std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::find(
                      (char *)this + 24,
                      &v13,
                      v14);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
      (__int64)v14,
      1,
      0);
    if ( v9 == *((_QWORD *)this + 4) || !*((_QWORD *)this + 5) )
    {
      a3->vt = 10;
      v10 = -2147467259;
    }
    else
    {
      v10 = VariantCopy(a3, *(const VARIANTARG **)(v9 + 64));
      if ( v10 >= 0 )
        return (unsigned int)v10;
    }
    v12 = 30;
    v13 = v10;
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
        &v12,
        4,
        &v13,
        0,
        0);
    }
    return (unsigned int)v10;
  }
  v6 = 25;
LABEL_5:
  v13 = -1072820735;
  v12 = v6;
  if ( g_pMSMQErrorLoggingTrace )
  {
    v7 = mqwcslen(L"trigobjs/cpropbag");
    CMSMQTrace::MSMQTraceEvent(
      (__int64)g_pMSMQErrorLoggingTrace,
      1,
      1u,
      2LL * (unsigned int)(v7 + 1),
      L"trigobjs/cpropbag",
      2,
      &v12,
      4,
      &v13,
      0,
      0);
  }
  return 3222146561LL;
}

```

## disassembly

```asm
0x180003460  push    rbp
0x180003462  push    rbx
0x180003463  push    rsi
0x180003464  push    rdi
0x180003465  push    r14
0x180003467  lea     rbp, [rsp-37h]
0x18000346c  sub     rsp, 0A0h
0x180003473  mov     rax, cs:__security_cookie
0x18000347a  xor     rax, rsp
0x18000347d  mov     [rbp+57h+var_28], rax
0x180003481  mov     rbx, r8
0x180003484  mov     rdi, rdx
0x180003487  mov     rsi, rcx
0x18000348a  test    r8, r8
0x18000348d  jnz     short loc_180003495
0x18000348f  lea     eax, [r8+19h]
0x180003493  jmp     short loc_1800034AB
0x180003495  mov     rcx, rdi; pbstr
0x180003498  call    cs:__imp_SysStringLen
0x18000349e  test    eax, eax
0x1800034a0  jnz     loc_180003531
0x1800034a6  mov     eax, 1Ah
0x1800034ab  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800034b3  mov     [rbp+57h+var_58], 0C00E0E01h
0x1800034ba  mov     [rbp+57h+var_60], ax
0x1800034be  jz      short loc_180003527
0x1800034c0  lea     rsi, aTrigobjsCpropb; "trigobjs/cpropbag"
0x1800034c7  mov     rcx, rsi; wchar_t *
0x1800034ca  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800034cf  mov     edi, 1
0x1800034d4  mov     [rsp+0C0h+var_70], 0
0x1800034dd  lea     r9d, [rdi+rax]
0x1800034e1  mov     [rsp+0C0h+var_78], 0
0x1800034ea  lea     rax, [rbp+57h+var_58]
0x1800034ee  mov     [rsp+0C0h+var_80], rax
0x1800034f3  mov     [rsp+0C0h+var_88], 4
0x1800034fc  lea     rax, [rbp+57h+var_60]
0x180003500  mov     [rsp+0C0h+var_90], rax
0x180003505  mov     [rsp+0C0h+var_98], 2
0x18000350e  mov     [rsp+0C0h+var_A0], rsi
0x180003513  add     r9, r9
0x180003516  mov     r8d, edi
0x180003519  mov     edx, edi
0x18000351b  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180003522  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180003527  mov     eax, 0C00E0E01h
0x18000352c  jmp     loc_180003618
0x180003531  mov     rcx, rbx; pvarg
0x180003534  call    cs:__imp_VariantInit
0x18000353a  mov     rdx, rdi
0x18000353d  lea     rcx, [rbp+57h+var_50]
0x180003541  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x180003546  lea     rcx, [rsi+18h]
0x18000354a  lea     r8, [rbp+57h+var_50]
0x18000354e  lea     rdx, [rbp+57h+var_58]
0x180003552  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAVCRuntimeRuleInfo@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@PEAVCRuntimeRuleInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@2@@Z; std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>,CRuntimeRuleInfo *,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const,CRuntimeRuleInfo *>>,0>>::find(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const &)
0x180003557  mov     r14, [rax]
0x18000355a  xor     r8d, r8d
0x18000355d  lea     edi, [r8+1]
0x180003561  mov     dl, dil
0x180003564  lea     rcx, [rbp+57h+var_50]
0x180003568  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x18000356d  nop
0x18000356e  cmp     r14, [rsi+20h]
0x180003572  jz      short loc_180003594
0x180003574  cmp     qword ptr [rsi+28h], 0
0x180003579  jz      short loc_180003594
0x18000357b  mov     rdx, [r14+40h]; pvargSrc
0x18000357f  mov     rcx, rbx; pvargDest
0x180003582  call    cs:__imp_VariantCopy
0x180003588  mov     ebx, eax
0x18000358a  test    eax, eax
0x18000358c  jns     loc_180003616
0x180003592  jmp     short loc_18000359E
0x180003594  mov     word ptr [rbx], 0Ah
0x180003599  mov     ebx, 80004005h
0x18000359e  mov     eax, 1Eh
0x1800035a3  mov     [rbp+57h+var_60], ax
0x1800035a7  mov     [rbp+57h+var_58], ebx
0x1800035aa  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800035b2  jz      short loc_180003616
0x1800035b4  lea     rsi, aTrigobjsCpropb; "trigobjs/cpropbag"
0x1800035bb  mov     rcx, rsi; wchar_t *
0x1800035be  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800035c3  lea     r9d, [rdi+rax]
0x1800035c7  add     r9, r9
0x1800035ca  mov     [rsp+0C0h+var_70], 0
0x1800035d3  mov     [rsp+0C0h+var_78], 0
0x1800035dc  lea     rax, [rbp+57h+var_58]
0x1800035e0  mov     [rsp+0C0h+var_80], rax
0x1800035e5  mov     [rsp+0C0h+var_88], 4
0x1800035ee  lea     rax, [rbp+57h+var_60]
0x1800035f2  mov     [rsp+0C0h+var_90], rax
0x1800035f7  mov     [rsp+0C0h+var_98], 2
0x180003600  mov     [rsp+0C0h+var_A0], rsi
0x180003605  mov     r8d, edi
0x180003608  mov     edx, edi
0x18000360a  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180003611  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180003616  mov     eax, ebx
0x180003618  mov     rcx, [rbp+57h+var_28]
0x18000361c  xor     rcx, rsp; StackCookie
0x18000361f  call    __security_check_cookie
0x180003624  add     rsp, 0A0h
0x18000362b  pop     r14
0x18000362d  pop     rdi
0x18000362e  pop     rsi
0x18000362f  pop     rbx
0x180003630  pop     rbp
0x180003631  retn
```
