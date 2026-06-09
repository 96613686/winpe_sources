# WSTrustTokenRequest::BuildSecurityHeader13(CSecureString const &,CSecureString const &)

- ea: `0x140017104`
- end: `0x140017231`
- name: `?BuildSecurityHeader13@WSTrustTokenRequest@@CA?AVCSecureString@@AEBV2@0@Z`
- size: `301`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017340`

## callees

- `0x14000579c`
- `0x140008644`
- `0x140012cb4`
- `0x140013278`
- `0x140017104`
- `0x140030010`

## string_xrefs

- `0x1400171d8`: `<o:Security s:mustUnderstand='1' xmlns:o='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd'><o:UsernameToken u:Id='uuid-%s'><o:Username>%s</o:Username><o:Password>%s</o:Password></o:UsernameToken></o:Security>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall WSTrustTokenRequest::BuildSecurityHeader13(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v6; // rdx
  __int64 v8; // [rsp+38h] [rbp-18h] BYREF
  __int64 v9; // [rsp+40h] [rbp-10h] BYREF
  __int64 v10; // [rsp+88h] [rbp+38h] BYREF

  *a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( *(_DWORD *)(*a2 - 16LL) )
  {
    if ( *(_DWORD *)(*a3 - 16LL) )
    {
      StringUtility::CreateGuid(&v9);
      v8 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      v10 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      StringUtility::EscapeXML(a2, &v8);
      StringUtility::EscapeXML(a3, &v10);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        a1,
        L"<o:Security s:mustUnderstand='1' xmlns:o='http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-sec"
         "ext-1.0.xsd'><o:UsernameToken u:Id='uuid-%s'><o:Username>%s</o:Username><o:Password>%s</o:Password></o:Username"
         "Token></o:Security>",
        v9,
        v8,
        v10);
      CSecureString::~CSecureString((CSecureString *)&v10);
      CSecureString::~CSecureString((CSecureString *)&v8);
      v6 = (_QWORD *)(v9 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140017104  mov     [rsp-18h+arg_8], rbx
0x140017109  mov     [rsp-18h+arg_0], rcx
0x14001710e  push    rbp
0x14001710f  push    rsi
0x140017110  push    rdi
0x140017111  mov     rbp, rsp
0x140017114  sub     rsp, 50h
0x140017118  mov     rdi, r8
0x14001711b  mov     rsi, rdx
0x14001711e  mov     rbx, rcx
0x140017121  mov     [rbp+var_20], 0
0x140017128  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001712f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017136  mov     rax, [rax+18h]
0x14001713a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001713f  add     rax, 18h
0x140017143  mov     [rbx], rax
0x140017146  mov     [rbp+var_20], 1
0x14001714d  mov     rax, [rsi]
0x140017150  cmp     dword ptr [rax-10h], 0
0x140017154  jz      loc_140017220
0x14001715a  mov     rax, [rdi]
0x14001715d  cmp     dword ptr [rax-10h], 0
0x140017161  jz      loc_140017220
0x140017167  lea     rcx, [rbp+var_10]
0x14001716b  call    ?CreateGuid@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; StringUtility::CreateGuid(void)
0x140017170  nop
0x140017171  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017178  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001717f  mov     rax, [rax+18h]
0x140017183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017188  add     rax, 18h
0x14001718c  mov     [rbp+var_18], rax
0x140017190  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017197  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001719e  mov     rax, [rax+18h]
0x1400171a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400171a7  add     rax, 18h
0x1400171ab  mov     [rbp+arg_18], rax
0x1400171af  lea     rdx, [rbp+var_18]
0x1400171b3  mov     rcx, rsi
0x1400171b6  call    ?EscapeXML@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; StringUtility::EscapeXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400171bb  lea     rdx, [rbp+arg_18]
0x1400171bf  mov     rcx, rdi
0x1400171c2  call    ?EscapeXML@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; StringUtility::EscapeXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400171c7  mov     rax, [rbp+arg_18]
0x1400171cb  mov     [rsp+50h+var_30], rax
0x1400171d0  mov     r9, [rbp+var_18]
0x1400171d4  mov     r8, [rbp+var_10]
0x1400171d8  lea     rdx, aOSecuritySMust; "<o:Security s:mustUnderstand='1' xmlns:"...
0x1400171df  mov     rcx, rbx
0x1400171e2  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1400171e7  nop
0x1400171e8  lea     rcx, [rbp+arg_18]; this
0x1400171ec  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400171f1  nop
0x1400171f2  lea     rcx, [rbp+var_18]; this
0x1400171f6  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400171fb  nop
0x1400171fc  mov     rdx, [rbp+var_10]
0x140017200  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140017204  or      eax, 0FFFFFFFFh
0x140017207  lock xadd [rdx+10h], eax
0x14001720c  sub     eax, 1
0x14001720f  jg      short loc_140017220
0x140017211  mov     rcx, [rdx]
0x140017214  mov     rax, [rcx]
0x140017217  mov     rax, [rax+8]
0x14001721b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017220  mov     rax, rbx
0x140017223  mov     rbx, [rsp+50h+arg_8]
0x140017228  add     rsp, 50h
0x14001722c  pop     rdi
0x14001722d  pop     rsi
0x14001722e  pop     rbp
0x14001722f  retn
```
