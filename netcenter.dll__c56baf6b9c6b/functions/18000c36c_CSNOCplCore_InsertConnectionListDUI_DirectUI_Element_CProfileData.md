# CSNOCplCore::InsertConnectionListDUI(DirectUI::Element *,CProfileData *)

- ea: `0x18000c36c`
- end: `0x18000c5ac`
- name: `?InsertConnectionListDUI@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEAVCProfileData@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct DirectUI::Element *, struct CProfileData *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x18000c5b4`

## callees

- `0x180007618`
- `0x180008fc4`
- `0x1800094e0`
- `0x18000c36c`
- `0x18001113c`
- `0x180011464`
- `0x180012a84`
- `0x180014274`
- `0x1800142b4`
- `0x18001e460`
- `0x18001e670`
- `0x18001fde8`

## import_xrefs

- `DUI70!StrToID` at `0x18000c479`
- `DUI70!StrToID` at `0x18000c479`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c485`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c485`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000c4d2`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000c4d2`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c50b`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c50b`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000c4e9`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000c4e9`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::InsertConnectionListDUI(
        CSNOCplCore *this,
        struct DirectUI::Element *a2,
        struct CProfileData *a3)
{
  _QWORD *v3; // r14
  int ConnectionList; // esi
  __int64 v8; // r8
  PVOID *v9; // rcx
  _QWORD *v10; // rbx
  struct tagNETCON_PROPERTIES *v11; // rdi
  CSNOCplCore *v12; // rcx
  DirectUI::Element *v13; // rbp
  unsigned __int16 v14; // ax
  struct DirectUI::Element *Descendent; // rax
  CSNOCplCore *v16; // rcx
  const unsigned __int16 *v17; // rdx
  CSNOCplCore *v18; // rcx
  const struct _GUID *v19; // r8
  _QWORD *v20; // rdi
  _QWORD *v21; // r15
  _QWORD *v22; // rax
  __int64 v23; // rbp
  _QWORD *v24; // rbx
  int v26; // [rsp+20h] [rbp-58h]
  int v27; // [rsp+28h] [rbp-50h]
  struct DirectUI::Element *v28; // [rsp+90h] [rbp+18h] BYREF
  struct DirectUI::DUIXmlParser *v29; // [rsp+98h] [rbp+20h] BYREF

  v3 = (_QWORD *)((char *)a3 + 80);
  ClearNetConnPropList((char *)a3 + 80);
  ConnectionList = CProfileMgr::GetConnectionList(this, v26, v27, (__int64)v3);
  if ( ConnectionList >= 0 && v3[1] )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, v8, *((_QWORD *)a3 + 2));
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = (_QWORD *)*v3;
    while ( 1 )
    {
      v10 = (_QWORD *)*v10;
      if ( v10 == (_QWORD *)*v3 )
        break;
      v11 = (struct tagNETCON_PROPERTIES *)v10[2];
      v29 = 0;
      v28 = 0;
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
        WPP_SF_S(v9[2], 104, v8, v11->pszwName);
      ConnectionList = CSNOCplCore::CreateXMLParser((CSNOCplCore *)v9, 0x72u, &v29, &v28);
      if ( ConnectionList >= 0 )
      {
        v13 = v28;
        CSNOCplCore::SetGUIDAsAtomtID(v12, v28, &v11->guidId);
        v14 = StrToID(L"connname");
        Descendent = DirectUI::Element::FindDescendent(v13, v14);
        if ( Descendent )
        {
          ConnectionList = CSNOCplCore::SetContentAndAccName(v16, Descendent, v11->pszwName, 0xC1u);
          if ( ConnectionList >= 0 )
          {
            ConnectionList = CSNOCplCore::ChangeHiddenChildIdGUIDGUID(
                               v18,
                               v17,
                               &v11->guidId,
                               (const struct _GUID *)a3,
                               v13);
            if ( ConnectionList >= 0 )
            {
              CSNOCplCore::UpdateConnectionIcon(this, v13, v19, v11);
              ConnectionList = DirectUI::Element::Add(a2, v13);
            }
          }
        }
        else
        {
          ConnectionList = -2147418113;
        }
        DirectUI::DUIXmlParser::Destroy(v29);
        if ( ConnectionList < 0 )
        {
          DirectUI::Element::Destroy(v13, 0);
          v20 = (_QWORD *)*v3;
          v21 = v10;
          do
          {
            FreeNetConnProp((struct tagNETCON_PROPERTIES *)v10[2]);
            v10[2] = 0;
            v10 = (_QWORD *)*v10;
          }
          while ( v10 != v20 );
          if ( v21 != v20 )
          {
            v22 = (_QWORD *)v21[1];
            v23 = 0;
            *v22 = v20;
            v20[1] = v22;
            do
            {
              v24 = (_QWORD *)*v21;
              std::_Deallocate<16>(v21, 24);
              ++v23;
              v21 = v24;
            }
            while ( v24 != v20 );
            v3[1] -= v23;
          }
          goto LABEL_25;
        }
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
LABEL_25:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_d(v9[2], 105, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, (unsigned int)ConnectionList);
  return (unsigned int)ConnectionList;
}

```

## disassembly

```asm
0x18000c36c  mov     [rsp+arg_0], rbx
0x18000c371  push    rbp
0x18000c372  push    rsi
0x18000c373  push    rdi
0x18000c374  push    r12
0x18000c376  push    r13
0x18000c378  push    r14
0x18000c37a  push    r15
0x18000c37c  sub     rsp, 40h
0x18000c380  lea     r14, [r8+50h]
0x18000c384  mov     r12, rcx
0x18000c387  mov     rcx, r14
0x18000c38a  mov     r15, r8
0x18000c38d  mov     r13, rdx
0x18000c390  call    ?ClearNetConnPropList@@YAXPEAV?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@@Z; ClearNetConnPropList(std::list<tagNETCON_PROPERTIES *> *)
0x18000c395  mov     rdx, r15
0x18000c398  mov     [rsp+78h+var_48], r14; __int64
0x18000c39d  mov     rcx, r12; this
0x18000c3a0  call    ?GetConnectionList@CProfileMgr@@QEAAJPEAU_GUID@@PEAUHINSTANCE__@@IIIPEAV?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@@Z; CProfileMgr::GetConnectionList(_GUID *,HINSTANCE__ *,uint,uint,uint,std::list<tagNETCON_PROPERTIES *> *)
0x18000c3a5  mov     esi, eax
0x18000c3a7  lea     rax, WPP_GLOBAL_Control
0x18000c3ae  test    esi, esi
0x18000c3b0  js      loc_18000C561
0x18000c3b6  cmp     qword ptr [r14+8], 0
0x18000c3bb  jz      loc_18000C561
0x18000c3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3c8  cmp     rcx, rax
0x18000c3cb  jz      short loc_18000C3F3
0x18000c3cd  test    byte ptr [rcx+1Ch], 8
0x18000c3d1  jz      short loc_18000C3F3
0x18000c3d3  mov     r9, [r15+10h]
0x18000c3d7  mov     edx, 67h ; 'g'
0x18000c3dc  mov     rcx, [rcx+10h]
0x18000c3e0  call    WPP_SF_S
0x18000c3e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3ec  lea     rax, WPP_GLOBAL_Control
0x18000c3f3  mov     rbx, [r14]
0x18000c3f6  mov     rbx, [rbx]
0x18000c3f9  cmp     rbx, [r14]
0x18000c3fc  jz      loc_18000C568
0x18000c402  mov     rdi, [rbx+10h]
0x18000c406  mov     [rsp+78h+arg_18], 0
0x18000c412  mov     [rsp+78h+arg_10], 0
0x18000c41e  cmp     rcx, rax
0x18000c421  jz      short loc_18000C43B
0x18000c423  test    byte ptr [rcx+1Ch], 8
0x18000c427  jz      short loc_18000C43B
0x18000c429  mov     r9, [rdi+10h]
0x18000c42d  mov     edx, 68h ; 'h'
0x18000c432  mov     rcx, [rcx+10h]
0x18000c436  call    WPP_SF_S
0x18000c43b  lea     r9, [rsp+78h+arg_10]; struct DirectUI::Element **
0x18000c443  mov     edx, 72h ; 'r'; unsigned int
0x18000c448  lea     r8, [rsp+78h+arg_18]; struct DirectUI::DUIXmlParser **
0x18000c450  call    ?CreateXMLParser@CSNOCplCore@@AEAAJIPEAPEAVDUIXmlParser@DirectUI@@PEAPEAVElement@3@@Z; CSNOCplCore::CreateXMLParser(uint,DirectUI::DUIXmlParser * *,DirectUI::Element * *)
0x18000c455  mov     esi, eax
0x18000c457  test    eax, eax
0x18000c459  js      loc_18000C4F3
0x18000c45f  mov     rbp, [rsp+78h+arg_10]
0x18000c467  mov     r8, rdi; struct _GUID *
0x18000c46a  mov     rdx, rbp; struct DirectUI::Element *
0x18000c46d  call    ?SetGUIDAsAtomtID@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@@Z; CSNOCplCore::SetGUIDAsAtomtID(DirectUI::Element *,_GUID const &)
0x18000c472  lea     rcx, aConnname; "connname"
0x18000c479  call    cs:__imp_StrToID
0x18000c47f  movzx   edx, ax
0x18000c482  mov     rcx, rbp
0x18000c485  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c48b  test    rax, rax
0x18000c48e  jz      short loc_18000C4DC
0x18000c490  mov     r8, [rdi+10h]; unsigned __int16 *
0x18000c494  mov     r9d, 0C1h; unsigned int
0x18000c49a  mov     rdx, rax; struct DirectUI::Element *
0x18000c49d  call    ?SetContentAndAccName@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEBGI@Z; CSNOCplCore::SetContentAndAccName(DirectUI::Element *,ushort const *,uint)
0x18000c4a2  mov     esi, eax
0x18000c4a4  test    eax, eax
0x18000c4a6  js      short loc_18000C4E1
0x18000c4a8  mov     r9, r15; struct _GUID *
0x18000c4ab  mov     [rsp+78h+var_58], rbp; struct DirectUI::Element *
0x18000c4b0  mov     r8, rdi; struct _GUID *
0x18000c4b3  call    ?ChangeHiddenChildIdGUIDGUID@CSNOCplCore@@AEAAJPEBGAEBU_GUID@@1PEAVElement@DirectUI@@@Z; CSNOCplCore::ChangeHiddenChildIdGUIDGUID(ushort const *,_GUID const &,_GUID const &,DirectUI::Element *)
0x18000c4b8  mov     esi, eax
0x18000c4ba  test    eax, eax
0x18000c4bc  js      short loc_18000C4E1
0x18000c4be  mov     r9, rdi; struct tagNETCON_PROPERTIES *
0x18000c4c1  mov     rdx, rbp; struct DirectUI::Element *
0x18000c4c4  mov     rcx, r12; this
0x18000c4c7  call    ?UpdateConnectionIcon@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z; CSNOCplCore::UpdateConnectionIcon(DirectUI::Element *,_GUID const &,tagNETCON_PROPERTIES *)
0x18000c4cc  mov     rdx, rbp
0x18000c4cf  mov     rcx, r13
0x18000c4d2  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000c4d8  mov     esi, eax
0x18000c4da  jmp     short loc_18000C4E1
0x18000c4dc  mov     esi, 8000FFFFh
0x18000c4e1  mov     rcx, [rsp+78h+arg_18]
0x18000c4e9  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18000c4ef  test    esi, esi
0x18000c4f1  js      short loc_18000C506
0x18000c4f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4fa  lea     rax, WPP_GLOBAL_Control
0x18000c501  jmp     loc_18000C3F6
0x18000c506  xor     edx, edx
0x18000c508  mov     rcx, rbp
0x18000c50b  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000c511  mov     rdi, [r14]
0x18000c514  mov     r15, rbx
0x18000c517  mov     rcx, [rbx+10h]; pv
0x18000c51b  call    ?FreeNetConnProp@@YAXPEAUtagNETCON_PROPERTIES@@@Z; FreeNetConnProp(tagNETCON_PROPERTIES *)
0x18000c520  mov     qword ptr [rbx+10h], 0
0x18000c528  mov     rbx, [rbx]
0x18000c52b  cmp     rbx, rdi
0x18000c52e  jnz     short loc_18000C517
0x18000c530  cmp     r15, rdi
0x18000c533  jz      short loc_18000C561
0x18000c535  mov     rax, [r15+8]
0x18000c539  xor     ebp, ebp
0x18000c53b  mov     [rax], rdi
0x18000c53e  mov     [rdi+8], rax
0x18000c542  mov     rbx, [r15]
0x18000c545  mov     edx, 18h
0x18000c54a  mov     rcx, r15
0x18000c54d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c552  inc     rbp
0x18000c555  mov     r15, rbx
0x18000c558  cmp     rbx, rdi
0x18000c55b  jnz     short loc_18000C542
0x18000c55d  sub     [r14+8], rbp
0x18000c561  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c568  lea     rax, WPP_GLOBAL_Control
0x18000c56f  cmp     rcx, rax
0x18000c572  jz      short loc_18000C592
0x18000c574  test    byte ptr [rcx+1Ch], 8
0x18000c578  jz      short loc_18000C592
0x18000c57a  mov     rcx, [rcx+10h]
0x18000c57e  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000c585  mov     edx, 69h ; 'i'
0x18000c58a  mov     r9d, esi
0x18000c58d  call    WPP_SF_d
0x18000c592  mov     rbx, [rsp+78h+arg_0]
0x18000c59a  mov     eax, esi
0x18000c59c  add     rsp, 40h
0x18000c5a0  pop     r15
0x18000c5a2  pop     r14
0x18000c5a4  pop     r13
0x18000c5a6  pop     r12
0x18000c5a8  pop     rdi
0x18000c5a9  pop     rsi
0x18000c5aa  pop     rbp
0x18000c5ab  retn
```
