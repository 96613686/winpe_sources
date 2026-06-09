# WSTrustTokenRequest::BuildSecurityHeader2005(CSecureString const &,CSecureString const &)

- ea: `0x140017238`
- end: `0x140017339`
- name: `?BuildSecurityHeader2005@WSTrustTokenRequest@@CA?AVCSecureString@@AEBV2@0@Z`
- size: `257`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001749c`

## callees

- `0x14000579c`
- `0x140008644`
- `0x140013278`
- `0x140017238`
- `0x140030010`

## string_xrefs

- `0x140017300`: `<wsse:Security><wsse:UsernameToken wsu:Id='user'><wsse:Username>%s</wsse:Username><wsse:Password>%s</wsse:Password></wsse:UsernameToken></wsse:Security>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall WSTrustTokenRequest::BuildSecurityHeader2005(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  int v7; // [rsp+20h] [rbp-18h]
  _QWORD v8[2]; // [rsp+28h] [rbp-10h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  *a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v7 = 1;
  if ( *(_DWORD *)(*a2 - 16LL) && *(_DWORD *)(*a3 - 16LL) )
  {
    v8[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    StringUtility::EscapeXML(a2, v8);
    StringUtility::EscapeXML(a3, &v9);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a1,
      L"<wsse:Security><wsse:UsernameToken wsu:Id='user'><wsse:Username>%s</wsse:Username><wsse:Password>%s</wsse:Password"
       "></wsse:UsernameToken></wsse:Security>",
      v8[0],
      v9,
      v7);
    CSecureString::~CSecureString((CSecureString *)&v9);
    CSecureString::~CSecureString((CSecureString *)v8);
  }
  return a1;
}

```

## disassembly

```asm
0x140017238  mov     rax, rsp
0x14001723b  mov     [rax+10h], rbx
0x14001723f  mov     [rax+18h], rsi
0x140017243  mov     [rax+8], rcx
0x140017247  push    rdi
0x140017248  sub     rsp, 30h
0x14001724c  mov     rdi, r8
0x14001724f  mov     rsi, rdx
0x140017252  mov     rbx, rcx
0x140017255  mov     dword ptr [rax-18h], 0
0x14001725c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017263  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001726a  mov     rax, [rax+18h]
0x14001726e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017273  add     rax, 18h
0x140017277  mov     [rbx], rax
0x14001727a  mov     [rsp+38h+var_18], 1
0x140017282  mov     rax, [rsi]
0x140017285  cmp     dword ptr [rax-10h], 0
0x140017289  jz      loc_140017325
0x14001728f  mov     rax, [rdi]
0x140017292  cmp     dword ptr [rax-10h], 0
0x140017296  jz      loc_140017325
0x14001729c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400172a3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400172aa  mov     rax, [rax+18h]
0x1400172ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400172b3  add     rax, 18h
0x1400172b7  mov     [rsp+38h+var_10], rax
0x1400172bc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400172c3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400172ca  mov     rax, [rax+18h]
0x1400172ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400172d3  add     rax, 18h
0x1400172d7  mov     [rsp+38h+arg_18], rax
0x1400172dc  lea     rdx, [rsp+38h+var_10]
0x1400172e1  mov     rcx, rsi
0x1400172e4  call    ?EscapeXML@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; StringUtility::EscapeXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400172e9  lea     rdx, [rsp+38h+arg_18]
0x1400172ee  mov     rcx, rdi
0x1400172f1  call    ?EscapeXML@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z; StringUtility::EscapeXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1400172f6  mov     r9, [rsp+38h+arg_18]
0x1400172fb  mov     r8, [rsp+38h+var_10]
0x140017300  lea     rdx, aWsseSecurityWs; "<wsse:Security><wsse:UsernameToken wsu:"...
0x140017307  mov     rcx, rbx
0x14001730a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14001730f  nop
0x140017310  lea     rcx, [rsp+38h+arg_18]; this
0x140017315  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x14001731a  nop
0x14001731b  lea     rcx, [rsp+38h+var_10]; this
0x140017320  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140017325  mov     rax, rbx
0x140017328  mov     rbx, [rsp+38h+arg_8]
0x14001732d  mov     rsi, [rsp+38h+arg_10]
0x140017332  add     rsp, 30h
0x140017336  pop     rdi
0x140017337  retn
```
