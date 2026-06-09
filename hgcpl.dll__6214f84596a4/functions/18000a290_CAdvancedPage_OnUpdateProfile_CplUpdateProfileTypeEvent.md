# CAdvancedPage::_OnUpdateProfile(CplUpdateProfileTypeEvent *)

- ea: `0x18000a290`
- end: `0x18000a444`
- name: `?_OnUpdateProfile@CAdvancedPage@@AEAAXPEAUCplUpdateProfileTypeEvent@@@Z`
- size: `436`
- prototype: `void __fastcall(CAdvancedPage *__hidden this, struct CplUpdateProfileTypeEvent *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008250`

## callees

- `0x18000766c`
- `0x18000a290`
- `0x18000a4e0`
- `0x18000fbcc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3bb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a2b6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a30b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a330`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a366`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a3f0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a2b6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a30b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a330`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a366`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000a3f0`
- `DUI70!StrToID` at `0x18000a2aa`
- `DUI70!StrToID` at `0x18000a2ff`
- `DUI70!StrToID` at `0x18000a324`
- `DUI70!StrToID` at `0x18000a35a`
- `DUI70!StrToID` at `0x18000a3e4`
- `DUI70!StrToID` at `0x18000a2aa`
- `DUI70!StrToID` at `0x18000a2ff`
- `DUI70!StrToID` at `0x18000a324`
- `DUI70!StrToID` at `0x18000a35a`
- `DUI70!StrToID` at `0x18000a3e4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000a3c6`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000a3c6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000a2c9`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000a2c9`
- `DUI70!?SetExpanded@Expandable@DirectUI@@QEAAJ_N@Z` at `0x18000a343`
- `DUI70!?SetExpanded@Expandable@DirectUI@@QEAAJ_N@Z` at `0x18000a343`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18000a385`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18000a385`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000a3b2`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18000a3b2`
- `DUI70!?SetYScrollable@BaseScrollViewer@DirectUI@@QEAAJ_N@Z` at `0x18000a400`
- `DUI70!?SetYScrollable@BaseScrollViewer@DirectUI@@QEAAJ_N@Z` at `0x18000a400`
- `DUI70!?_PostEvent@Element@DirectUI@@AEAAXPEAUEvent@2@H@Z` at `0x18000a435`
- `DUI70!?_PostEvent@Element@DirectUI@@AEAAXPEAUEvent@2@H@Z` at `0x18000a435`

## pseudocode

```c
void __fastcall CAdvancedPage::_OnUpdateProfile(CAdvancedPage *this, struct CplUpdateProfileTypeEvent *a2)
{
  DirectUI::Element *v2; // rbx
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v7; // rbx
  __int64 v8; // r8
  unsigned int i; // ecx
  unsigned __int16 v10; // ax
  DirectUI::Element *v11; // rdi
  unsigned __int16 v12; // ax
  DirectUI::Expandable *v13; // rax
  struct DirectUI::Expando *v14; // rbx
  unsigned __int16 v15; // ax
  DirectUI::Element *v16; // rax
  CAdvancedPage *v17; // rcx
  DirectUI::Element *v18; // rsi
  const unsigned __int16 *ContentString; // rax
  const unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rdi
  DirectUI::Element *v22; // rbx
  unsigned __int16 v23; // ax
  DirectUI::BaseScrollViewer *v24; // rax
  unsigned __int64 v25; // rdx
  struct DirectUI::Event *v26; // rax
  struct DirectUI::Value *v27; // [rsp+50h] [rbp+8h] BYREF

  v2 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v5 = StrToID(L"AdvPageContents");
  Descendent = DirectUI::Element::FindDescendent(v2, v5);
  if ( Descendent )
    DirectUI::Element::SetLayoutPos(Descendent, 4);
  v7 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v8 = 0;
  for ( i = 0; i < 4; ++i )
  {
    if ( HIDWORD(qword_18001C220[2 * i]) == *((_DWORD *)a2 + 8) )
    {
      v8 = qword_18001C220[2 * i + 1];
      break;
    }
  }
  v10 = StrToID(v8);
  v11 = DirectUI::Element::FindDescendent(v7, v10);
  if ( v11 )
  {
    v12 = StrToID(L"Expando");
    v13 = DirectUI::Element::FindDescendent(v11, v12);
    v14 = v13;
    if ( v13 )
      DirectUI::Expandable::SetExpanded(v13, 1);
    if ( *((_DWORD *)a2 + 8) )
    {
      v15 = StrToID(L"ExpandoButtonText");
      v16 = DirectUI::Element::FindDescendent(v11, v15);
      v18 = v16;
      if ( v16 )
      {
        v27 = 0;
        ContentString = DirectUI::Element::GetContentString(v16, &v27);
        if ( ContentString )
        {
          v20 = (const unsigned __int16 *)ShellConstructMessageStringW(g_hinst, 89, ContentString);
          v21 = (unsigned __int16 *)v20;
          if ( v20 )
          {
            DirectUI::Element::SetContentString(v18, v20);
            LocalFree(v21);
          }
        }
        DirectUI::Value::Release(v27);
      }
      if ( v14 )
        CAdvancedPage::_SetExpandoAccNameFromHeaderText(v17, v14);
    }
  }
  v22 = (DirectUI::Element *)*((_QWORD *)this + 2);
  v23 = StrToID(L"AdvScrollViewer");
  v24 = DirectUI::Element::FindDescendent(v22, v23);
  if ( v24 )
    DirectUI::BaseScrollViewer::SetYScrollable(v24, 0);
  v26 = (struct DirectUI::Event *)DirectUI::HAllocAndZero((DirectUI *)0x20, v25);
  if ( v26 )
  {
    *((_QWORD *)v26 + 1) = 0;
    *((_QWORD *)v26 + 1) = CAdvancedPage::ProfileUpdateComplete;
    DirectUI::Element::_PostEvent(*((DirectUI::Element **)this + 2), v26, 33784);
  }
}

```

## disassembly

```asm
0x18000a290  push    rbx
0x18000a292  push    rbp
0x18000a293  push    rsi
0x18000a294  push    rdi
0x18000a295  sub     rsp, 28h
0x18000a299  mov     rbx, [rcx+10h]
0x18000a29d  mov     rbp, rcx
0x18000a2a0  lea     rcx, aAdvpagecontent; "AdvPageContents"
0x18000a2a7  mov     rsi, rdx
0x18000a2aa  call    cs:__imp_StrToID
0x18000a2b0  movzx   edx, ax
0x18000a2b3  mov     rcx, rbx
0x18000a2b6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a2bc  test    rax, rax
0x18000a2bf  jz      short loc_18000A2CF
0x18000a2c1  mov     edx, 4
0x18000a2c6  mov     rcx, rax
0x18000a2c9  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18000a2cf  mov     rbx, [rbp+10h]
0x18000a2d3  lea     r9, qword_18001C220
0x18000a2da  xor     r8d, r8d
0x18000a2dd  xor     ecx, ecx
0x18000a2df  cmp     ecx, 4
0x18000a2e2  jnb     short loc_18000A2FC
0x18000a2e4  mov     eax, [rsi+20h]
0x18000a2e7  mov     edx, ecx
0x18000a2e9  add     rdx, rdx
0x18000a2ec  cmp     [r9+rdx*8+4], eax
0x18000a2f1  jz      short loc_18000A2F7
0x18000a2f3  inc     ecx
0x18000a2f5  jmp     short loc_18000A2DF
0x18000a2f7  mov     r8, [r9+rdx*8+8]
0x18000a2fc  mov     rcx, r8
0x18000a2ff  call    cs:__imp_StrToID
0x18000a305  movzx   edx, ax
0x18000a308  mov     rcx, rbx
0x18000a30b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a311  mov     rdi, rax
0x18000a314  test    rax, rax
0x18000a317  jz      loc_18000A3D9
0x18000a31d  lea     rcx, aExpando; "Expando"
0x18000a324  call    cs:__imp_StrToID
0x18000a32a  movzx   edx, ax
0x18000a32d  mov     rcx, rdi
0x18000a330  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a336  mov     rbx, rax
0x18000a339  test    rax, rax
0x18000a33c  jz      short loc_18000A349
0x18000a33e  mov     dl, 1
0x18000a340  mov     rcx, rax
0x18000a343  call    cs:__imp_?SetExpanded@Expandable@DirectUI@@QEAAJ_N@Z; DirectUI::Expandable::SetExpanded(bool)
0x18000a349  cmp     dword ptr [rsi+20h], 0
0x18000a34d  jz      loc_18000A3D9
0x18000a353  lea     rcx, aExpandobuttont; "ExpandoButtonText"
0x18000a35a  call    cs:__imp_StrToID
0x18000a360  movzx   edx, ax
0x18000a363  mov     rcx, rdi
0x18000a366  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a36c  mov     rsi, rax
0x18000a36f  test    rax, rax
0x18000a372  jz      short loc_18000A3CC
0x18000a374  lea     rdx, [rsp+48h+arg_0]
0x18000a379  mov     [rsp+48h+arg_0], 0
0x18000a382  mov     rcx, rax
0x18000a385  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x18000a38b  test    rax, rax
0x18000a38e  jz      short loc_18000A3C1
0x18000a390  mov     rcx, cs:g_hinst
0x18000a397  mov     r8, rax
0x18000a39a  mov     edx, 59h ; 'Y'
0x18000a39f  call    ShellConstructMessageStringW
0x18000a3a4  mov     rdi, rax
0x18000a3a7  test    rax, rax
0x18000a3aa  jz      short loc_18000A3C1
0x18000a3ac  mov     rdx, rax
0x18000a3af  mov     rcx, rsi
0x18000a3b2  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18000a3b8  mov     rcx, rdi; hMem
0x18000a3bb  call    cs:__imp_LocalFree
0x18000a3c1  mov     rcx, [rsp+48h+arg_0]
0x18000a3c6  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000a3cc  test    rbx, rbx
0x18000a3cf  jz      short loc_18000A3D9
0x18000a3d1  mov     rdx, rbx; struct DirectUI::Expando *
0x18000a3d4  call    ?_SetExpandoAccNameFromHeaderText@CAdvancedPage@@AEAAXPEAVExpando@DirectUI@@@Z; CAdvancedPage::_SetExpandoAccNameFromHeaderText(DirectUI::Expando *)
0x18000a3d9  mov     rbx, [rbp+10h]
0x18000a3dd  lea     rcx, aAdvscrollviewe; "AdvScrollViewer"
0x18000a3e4  call    cs:__imp_StrToID
0x18000a3ea  movzx   edx, ax
0x18000a3ed  mov     rcx, rbx
0x18000a3f0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000a3f6  test    rax, rax
0x18000a3f9  jz      short loc_18000A406
0x18000a3fb  xor     edx, edx
0x18000a3fd  mov     rcx, rax
0x18000a400  call    cs:__imp_?SetYScrollable@BaseScrollViewer@DirectUI@@QEAAJ_N@Z; DirectUI::BaseScrollViewer::SetYScrollable(bool)
0x18000a406  mov     ecx, 20h ; ' '; this
0x18000a40b  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000a410  test    rax, rax
0x18000a413  jz      short loc_18000A43B
0x18000a415  mov     qword ptr [rax+8], 0
0x18000a41d  mov     r8d, 83F8h
0x18000a423  mov     rcx, cs:?ProfileUpdateComplete@CAdvancedPage@@0VUID@@A; UID CAdvancedPage::ProfileUpdateComplete
0x18000a42a  mov     rdx, rax
0x18000a42d  mov     [rax+8], rcx
0x18000a431  mov     rcx, [rbp+10h]
0x18000a435  call    cs:__imp_?_PostEvent@Element@DirectUI@@AEAAXPEAUEvent@2@H@Z; DirectUI::Element::_PostEvent(DirectUI::Event *,int)
0x18000a43b  add     rsp, 28h
0x18000a43f  pop     rdi
0x18000a440  pop     rsi
0x18000a441  pop     rbp
0x18000a442  pop     rbx
0x18000a443  retn
```
