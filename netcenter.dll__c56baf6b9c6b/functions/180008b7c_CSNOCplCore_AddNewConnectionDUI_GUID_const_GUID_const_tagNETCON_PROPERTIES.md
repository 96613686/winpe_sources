# CSNOCplCore::AddNewConnectionDUI(_GUID const &,_GUID const &,tagNETCON_PROPERTIES *)

- ea: `0x180008b7c`
- end: `0x180008d4a`
- name: `?AddNewConnectionDUI@CSNOCplCore@@AEAAJAEBU_GUID@@0PEAUtagNETCON_PROPERTIES@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, GUID *rguid, const struct _GUID *, struct tagNETCON_PROPERTIES *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009c1c`
- `0x180012b6c`

## callees

- `0x180002270`
- `0x180008b7c`
- `0x180008fc4`
- `0x1800094e0`
- `0x18001113c`
- `0x180011464`
- `0x180012a84`
- `0x180014274`
- `0x1800155ec`
- `0x180017dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008bbd`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008bbd`
- `DUI70!StrToID` at `0x180008bcf`
- `DUI70!StrToID` at `0x180008bf4`
- `DUI70!StrToID` at `0x180008c59`
- `DUI70!StrToID` at `0x180008bcf`
- `DUI70!StrToID` at `0x180008bf4`
- `DUI70!StrToID` at `0x180008c59`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180008bdb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180008c00`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180008c65`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180008bdb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180008c00`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180008c65`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180008cdd`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180008cdd`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180008cf1`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180008cf1`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::AddNewConnectionDUI(
        CSNOCplCore *this,
        GUID *rguid,
        const struct _GUID *a3,
        struct tagNETCON_PROPERTIES *a4)
{
  int v7; // edi
  DirectUI::Element *v8; // rbx
  unsigned __int16 v9; // ax
  DirectUI::Element *Descendent; // rbx
  unsigned __int16 v11; // ax
  CSNOCplCore *v12; // rcx
  DirectUI::Element *v13; // r14
  CSNOCplCore *v14; // rcx
  DirectUI::Element *v15; // rbx
  unsigned __int16 v16; // ax
  struct DirectUI::Element *v17; // rax
  CSNOCplCore *v18; // rcx
  const unsigned __int16 *v19; // rdx
  CSNOCplCore *v20; // rcx
  const struct _GUID *v21; // r8
  __int64 v22; // rcx
  struct DirectUI::Element *v24; // [rsp+30h] [rbp-A8h] BYREF
  struct DirectUI::DUIXmlParser *v25; // [rsp+38h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-98h] BYREF

  v7 = -2147418113;
  StringFromGUID2(rguid, sz, 39);
  v8 = (DirectUI::Element *)*((_QWORD *)this + 40);
  v9 = StrToID(sz);
  Descendent = DirectUI::Element::FindDescendent(v8, v9);
  if ( Descendent )
  {
    v11 = StrToID(L"connlist");
    v13 = DirectUI::Element::FindDescendent(Descendent, v11);
    if ( v13 )
    {
      v25 = 0;
      v24 = 0;
      v7 = CSNOCplCore::CreateXMLParser(v12, 0x72u, &v25, &v24);
      if ( v7 >= 0 )
      {
        v15 = v24;
        CSNOCplCore::SetGUIDAsAtomtID(v14, v24, &a4->guidId);
        v16 = StrToID(L"connname");
        v17 = DirectUI::Element::FindDescendent(v15, v16);
        if ( v17 )
        {
          v7 = CSNOCplCore::SetContentAndAccName(v18, v17, a4->pszwName, 0xC1u);
          if ( v7 >= 0 )
          {
            v7 = CSNOCplCore::ChangeHiddenChildIdGUIDGUID(v20, v19, &a4->guidId, a3, v15);
            if ( v7 >= 0 )
            {
              CWlanHelper::GetSignalStrength((char *)this + 184, (char *)this + 216);
              v22 = *((_QWORD *)this + 26);
              if ( v22 )
                CWwanHelper::GetSignalStrength(v22, (char *)this + 232);
              CSNOCplCore::UpdateConnectionIcon(this, v15, v21, a4);
              v7 = DirectUI::Element::Add(v13, v15);
            }
          }
        }
        else
        {
          v7 = -2147418113;
        }
        DirectUI::DUIXmlParser::Destroy(v25);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      145,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008b7c  push    rbx
0x180008b7e  push    rbp
0x180008b7f  push    rsi
0x180008b80  push    rdi
0x180008b81  push    r14
0x180008b83  push    r15
0x180008b85  sub     rsp, 0A8h
0x180008b8c  mov     rax, cs:__security_cookie
0x180008b93  xor     rax, rsp
0x180008b96  mov     [rsp+0D8h+var_48], rax
0x180008b9e  mov     rax, rdx
0x180008ba1  mov     r15, r8
0x180008ba4  mov     rsi, rcx
0x180008ba7  lea     rdx, [rsp+0D8h+sz]; lpsz
0x180008bac  mov     rcx, rax; rguid
0x180008baf  mov     r8d, 27h ; '''; cchMax
0x180008bb5  mov     rbp, r9
0x180008bb8  mov     edi, 8000FFFFh
0x180008bbd  call    cs:__imp_StringFromGUID2
0x180008bc3  mov     rbx, [rsi+140h]
0x180008bca  lea     rcx, [rsp+0D8h+sz]
0x180008bcf  call    cs:__imp_StrToID
0x180008bd5  movzx   edx, ax
0x180008bd8  mov     rcx, rbx
0x180008bdb  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180008be1  mov     rbx, rax
0x180008be4  test    rax, rax
0x180008be7  jz      loc_180008CF7
0x180008bed  lea     rcx, aConnlist; "connlist"
0x180008bf4  call    cs:__imp_StrToID
0x180008bfa  movzx   edx, ax
0x180008bfd  mov     rcx, rbx
0x180008c00  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180008c06  mov     r14, rax
0x180008c09  test    rax, rax
0x180008c0c  jz      loc_180008CF7
0x180008c12  lea     r9, [rsp+0D8h+var_A8]; struct DirectUI::Element **
0x180008c17  mov     [rsp+0D8h+var_A0], 0
0x180008c20  lea     r8, [rsp+0D8h+var_A0]; struct DirectUI::DUIXmlParser **
0x180008c25  mov     [rsp+0D8h+var_A8], 0
0x180008c2e  mov     edx, 72h ; 'r'; unsigned int
0x180008c33  call    ?CreateXMLParser@CSNOCplCore@@AEAAJIPEAPEAVDUIXmlParser@DirectUI@@PEAPEAVElement@3@@Z; CSNOCplCore::CreateXMLParser(uint,DirectUI::DUIXmlParser * *,DirectUI::Element * *)
0x180008c38  mov     edi, eax
0x180008c3a  test    eax, eax
0x180008c3c  js      loc_180008CF7
0x180008c42  mov     rbx, [rsp+0D8h+var_A8]
0x180008c47  mov     r8, rbp; struct _GUID *
0x180008c4a  mov     rdx, rbx; struct DirectUI::Element *
0x180008c4d  call    ?SetGUIDAsAtomtID@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@@Z; CSNOCplCore::SetGUIDAsAtomtID(DirectUI::Element *,_GUID const &)
0x180008c52  lea     rcx, aConnname; "connname"
0x180008c59  call    cs:__imp_StrToID
0x180008c5f  movzx   edx, ax
0x180008c62  mov     rcx, rbx
0x180008c65  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180008c6b  test    rax, rax
0x180008c6e  jz      short loc_180008CE7
0x180008c70  mov     r8, [rbp+10h]; unsigned __int16 *
0x180008c74  mov     r9d, 0C1h; unsigned int
0x180008c7a  mov     rdx, rax; struct DirectUI::Element *
0x180008c7d  call    ?SetContentAndAccName@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEBGI@Z; CSNOCplCore::SetContentAndAccName(DirectUI::Element *,ushort const *,uint)
0x180008c82  mov     edi, eax
0x180008c84  test    eax, eax
0x180008c86  js      short loc_180008CEC
0x180008c88  mov     r9, r15; struct _GUID *
0x180008c8b  mov     [rsp+0D8h+var_B8], rbx; struct DirectUI::Element *
0x180008c90  mov     r8, rbp; struct _GUID *
0x180008c93  call    ?ChangeHiddenChildIdGUIDGUID@CSNOCplCore@@AEAAJPEBGAEBU_GUID@@1PEAVElement@DirectUI@@@Z; CSNOCplCore::ChangeHiddenChildIdGUIDGUID(ushort const *,_GUID const &,_GUID const &,DirectUI::Element *)
0x180008c98  mov     edi, eax
0x180008c9a  test    eax, eax
0x180008c9c  js      short loc_180008CEC
0x180008c9e  lea     rdx, [rsi+0D8h]
0x180008ca5  lea     rcx, [rsi+0B8h]
0x180008cac  call    ?GetSignalStrength@CWlanHelper@@QEAAJPEAV?$list@PEAUtagSIGNALSTRENGTHDATA@@V?$allocator@PEAUtagSIGNALSTRENGTHDATA@@@std@@@std@@@Z; CWlanHelper::GetSignalStrength(std::list<tagSIGNALSTRENGTHDATA *> *)
0x180008cb1  mov     rcx, [rsi+0D0h]
0x180008cb8  test    rcx, rcx
0x180008cbb  jz      short loc_180008CC9
0x180008cbd  lea     rdx, [rsi+0E8h]
0x180008cc4  call    ?GetSignalStrength@CWwanHelper@@QEAAJPEAV?$list@PEAUtagSIGNALSTRENGTHDATA@@V?$allocator@PEAUtagSIGNALSTRENGTHDATA@@@std@@@std@@@Z; CWwanHelper::GetSignalStrength(std::list<tagSIGNALSTRENGTHDATA *> *)
0x180008cc9  mov     r9, rbp; struct tagNETCON_PROPERTIES *
0x180008ccc  mov     rdx, rbx; struct DirectUI::Element *
0x180008ccf  mov     rcx, rsi; this
0x180008cd2  call    ?UpdateConnectionIcon@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z; CSNOCplCore::UpdateConnectionIcon(DirectUI::Element *,_GUID const &,tagNETCON_PROPERTIES *)
0x180008cd7  mov     rdx, rbx
0x180008cda  mov     rcx, r14
0x180008cdd  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180008ce3  mov     edi, eax
0x180008ce5  jmp     short loc_180008CEC
0x180008ce7  mov     edi, 8000FFFFh
0x180008cec  mov     rcx, [rsp+0D8h+var_A0]
0x180008cf1  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180008cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cfe  lea     rax, WPP_GLOBAL_Control
0x180008d05  cmp     rcx, rax
0x180008d08  jz      short loc_180008D28
0x180008d0a  test    byte ptr [rcx+1Ch], 8
0x180008d0e  jz      short loc_180008D28
0x180008d10  mov     rcx, [rcx+10h]
0x180008d14  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180008d1b  mov     edx, 91h
0x180008d20  mov     r9d, edi
0x180008d23  call    WPP_SF_d
0x180008d28  mov     eax, edi
0x180008d2a  mov     rcx, [rsp+0D8h+var_48]
0x180008d32  xor     rcx, rsp; StackCookie
0x180008d35  call    __security_check_cookie
0x180008d3a  add     rsp, 0A8h
0x180008d41  pop     r15
0x180008d43  pop     r14
0x180008d45  pop     rdi
0x180008d46  pop     rsi
0x180008d47  pop     rbp
0x180008d48  pop     rbx
0x180008d49  retn
```
