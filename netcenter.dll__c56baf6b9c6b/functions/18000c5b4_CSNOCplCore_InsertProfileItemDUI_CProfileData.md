# CSNOCplCore::InsertProfileItemDUI(CProfileData *)

- ea: `0x18000c5b4`
- end: `0x18000c7e0`
- name: `?InsertProfileItemDUI@CSNOCplCore@@AEAAJPEAVCProfileData@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct CProfileData *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000a010`
- `0x18000f550`
- `0x18000f9ec`

## callees

- `0x180006b70`
- `0x1800094e0`
- `0x18000ba40`
- `0x18000c36c`
- `0x18000c5b4`
- `0x18000c7e8`
- `0x180011464`
- `0x180014274`
- `0x180014448`
- `0x18001bec0`

## import_xrefs

- `DUI70!StrToID` at `0x18000c67e`
- `DUI70!StrToID` at `0x18000c6fb`
- `DUI70!StrToID` at `0x18000c67e`
- `DUI70!StrToID` at `0x18000c6fb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c68a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c707`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c68a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000c707`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000c76d`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18000c76d`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c792`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000c792`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000c79d`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000c79d`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::InsertProfileItemDUI(CSNOCplCore *this, struct _GUID *a2, int a3)
{
  unsigned int Data1; // ecx
  _QWORD *v7; // rcx
  int v8; // edx
  const char *v9; // rax
  DirectUI::Element *v10; // rbx
  int inserted; // ebp
  unsigned __int16 v12; // ax
  CSNOCplCore *v13; // rcx
  DirectUI::Element *Descendent; // r15
  CSNOCplCore *v15; // rcx
  struct DirectUI::Element *v16; // rbx
  unsigned __int16 v17; // ax
  struct DirectUI::Element *v18; // rax
  CSNOCplCore *v19; // rcx
  struct DirectUI::Element *v20; // [rsp+68h] [rbp+10h] BYREF
  struct DirectUI::DUIXmlParser *v21; // [rsp+70h] [rbp+18h] BYREF

  if ( !a2 )
    return 2147500035LL;
  Data1 = a2[3].Data1;
  if ( (Data1 & 0x28) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_15;
    v8 = 113;
    v9 = "INTERNET_CONN";
  }
  else if ( (Data1 & 0x14) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_15;
    v8 = 114;
    v9 = "LOCAL_CONN";
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_15;
    v8 = 115;
    v9 = "NO_CONN";
  }
  WPP_SF_Ss(v7[2], v8, a3, *(_QWORD *)&a2[1].Data1, (__int64)v9);
LABEL_15:
  v10 = (DirectUI::Element *)*((_QWORD *)this + 40);
  inserted = -2147418113;
  v12 = StrToID(L"profilearea");
  Descendent = DirectUI::Element::FindDescendent(v10, v12);
  if ( Descendent )
  {
    v21 = 0;
    v20 = 0;
    inserted = CSNOCplCore::CreateXMLParser(v13, 0x70u, &v21, &v20);
    if ( inserted >= 0 )
    {
      v16 = v20;
      CSNOCplCore::SetGUIDAsAtomtID(v15, v20, a2);
      inserted = CSNOCplCore::InsertProfileNameDUI(this, v16, (struct CProfileData *)a2);
      if ( inserted < 0 )
      {
        DirectUI::Element::Destroy(v16, 0);
      }
      else
      {
        v17 = StrToID(L"connlist");
        v18 = DirectUI::Element::FindDescendent(v16, v17);
        if ( v18 )
        {
          if ( (int)CSNOCplCore::InsertConnectionListDUI(this, v18, (struct CProfileData *)a2) < 0 )
            CSNOCplCore::HideElement(v19, v16, L"ConnectionsContainer", 1, 1);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
        }
        DirectUI::Element::Add(Descendent, v16);
        DUI_WalkIUnknownElements(
          v16,
          (void (*)(struct IUnknown *, __int64))DUI_SetSiteOnUnknown,
          *((_QWORD *)this + 43));
        inserted = 0;
      }
      DirectUI::DUIXmlParser::Destroy(v21);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      117,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)inserted);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18000c5b4  mov     [rsp+arg_0], rbx
0x18000c5b9  push    rbp
0x18000c5ba  push    rsi
0x18000c5bb  push    rdi
0x18000c5bc  push    r14
0x18000c5be  push    r15
0x18000c5c0  sub     rsp, 30h
0x18000c5c4  mov     rsi, rdx
0x18000c5c7  mov     r14, rcx
0x18000c5ca  test    rdx, rdx
0x18000c5cd  jnz     short loc_18000C5D9
0x18000c5cf  mov     eax, 80004003h
0x18000c5d4  jmp     loc_18000C7CF
0x18000c5d9  mov     ecx, [rdx+30h]
0x18000c5dc  test    cl, 28h
0x18000c5df  jz      short loc_18000C608
0x18000c5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5e8  lea     rdi, WPP_GLOBAL_Control
0x18000c5ef  cmp     rcx, rdi
0x18000c5f2  jz      short loc_18000C66B
0x18000c5f4  test    byte ptr [rcx+1Ch], 4
0x18000c5f8  jz      short loc_18000C66B
0x18000c5fa  mov     edx, 71h ; 'q'
0x18000c5ff  lea     rax, aInternetConn; "INTERNET_CONN"
0x18000c606  jmp     short loc_18000C659
0x18000c608  test    cl, 14h
0x18000c60b  jz      short loc_18000C634
0x18000c60d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c614  lea     rdi, WPP_GLOBAL_Control
0x18000c61b  cmp     rcx, rdi
0x18000c61e  jz      short loc_18000C66B
0x18000c620  test    byte ptr [rcx+1Ch], 4
0x18000c624  jz      short loc_18000C66B
0x18000c626  mov     edx, 72h ; 'r'
0x18000c62b  lea     rax, aLocalConn; "LOCAL_CONN"
0x18000c632  jmp     short loc_18000C659
0x18000c634  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c63b  lea     rdi, WPP_GLOBAL_Control
0x18000c642  cmp     rcx, rdi
0x18000c645  jz      short loc_18000C66B
0x18000c647  test    byte ptr [rcx+1Ch], 4
0x18000c64b  jz      short loc_18000C66B
0x18000c64d  mov     edx, 73h ; 's'
0x18000c652  lea     rax, aNoConn; "NO_CONN"
0x18000c659  mov     r9, [rsi+10h]
0x18000c65d  mov     rcx, [rcx+10h]
0x18000c661  mov     qword ptr [rsp+58h+var_38], rax
0x18000c666  call    WPP_SF_Ss
0x18000c66b  mov     rbx, [r14+140h]
0x18000c672  lea     rcx, aProfilearea; "profilearea"
0x18000c679  mov     ebp, 8000FFFFh
0x18000c67e  call    cs:__imp_StrToID
0x18000c684  movzx   edx, ax
0x18000c687  mov     rcx, rbx
0x18000c68a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c690  mov     r15, rax
0x18000c693  test    rax, rax
0x18000c696  jz      loc_18000C7A3
0x18000c69c  lea     r9, [rsp+58h+arg_8]; struct DirectUI::Element **
0x18000c6a1  mov     [rsp+58h+arg_10], 0
0x18000c6aa  lea     r8, [rsp+58h+arg_10]; struct DirectUI::DUIXmlParser **
0x18000c6af  mov     [rsp+58h+arg_8], 0
0x18000c6b8  mov     edx, 70h ; 'p'; unsigned int
0x18000c6bd  call    ?CreateXMLParser@CSNOCplCore@@AEAAJIPEAPEAVDUIXmlParser@DirectUI@@PEAPEAVElement@3@@Z; CSNOCplCore::CreateXMLParser(uint,DirectUI::DUIXmlParser * *,DirectUI::Element * *)
0x18000c6c2  mov     ebp, eax
0x18000c6c4  test    eax, eax
0x18000c6c6  js      loc_18000C7A3
0x18000c6cc  mov     rbx, [rsp+58h+arg_8]
0x18000c6d1  mov     r8, rsi; struct _GUID *
0x18000c6d4  mov     rdx, rbx; struct DirectUI::Element *
0x18000c6d7  call    ?SetGUIDAsAtomtID@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@@Z; CSNOCplCore::SetGUIDAsAtomtID(DirectUI::Element *,_GUID const &)
0x18000c6dc  mov     r8, rsi; struct CProfileData *
0x18000c6df  mov     rdx, rbx; struct DirectUI::Element *
0x18000c6e2  mov     rcx, r14; this
0x18000c6e5  call    ?InsertProfileNameDUI@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEAVCProfileData@@@Z; CSNOCplCore::InsertProfileNameDUI(DirectUI::Element *,CProfileData *)
0x18000c6ea  mov     ebp, eax
0x18000c6ec  test    eax, eax
0x18000c6ee  js      loc_18000C78D
0x18000c6f4  lea     rcx, aConnlist; "connlist"
0x18000c6fb  call    cs:__imp_StrToID
0x18000c701  movzx   edx, ax
0x18000c704  mov     rcx, rbx
0x18000c707  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000c70d  test    rax, rax
0x18000c710  jz      short loc_18000C740
0x18000c712  mov     r8, rsi; struct CProfileData *
0x18000c715  mov     rdx, rax; struct DirectUI::Element *
0x18000c718  mov     rcx, r14; this
0x18000c71b  call    ?InsertConnectionListDUI@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEAVCProfileData@@@Z; CSNOCplCore::InsertConnectionListDUI(DirectUI::Element *,CProfileData *)
0x18000c720  test    eax, eax
0x18000c722  jns     short loc_18000C767
0x18000c724  mov     r9d, 1; int
0x18000c72a  lea     r8, aConnectionscon; "ConnectionsContainer"
0x18000c731  mov     rdx, rbx; struct DirectUI::Element *
0x18000c734  mov     [rsp+58h+var_38], r9d; int
0x18000c739  call    ?HideElement@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEBGHH@Z; CSNOCplCore::HideElement(DirectUI::Element *,ushort const *,int,int)
0x18000c73e  jmp     short loc_18000C767
0x18000c740  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c747  cmp     rcx, rdi
0x18000c74a  jz      short loc_18000C767
0x18000c74c  test    byte ptr [rcx+1Ch], 2
0x18000c750  jz      short loc_18000C767
0x18000c752  mov     rcx, [rcx+10h]
0x18000c756  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000c75d  mov     edx, 74h ; 't'
0x18000c762  call    WPP_SF_
0x18000c767  mov     rdx, rbx
0x18000c76a  mov     rcx, r15
0x18000c76d  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000c773  mov     r8, [r14+158h]; __int64
0x18000c77a  lea     rdx, ?DUI_SetSiteOnUnknown@@YAXPEAUIUnknown@@_J@Z; void (*)(struct IUnknown *, __int64)
0x18000c781  mov     rcx, rbx; struct DirectUI::Element *
0x18000c784  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x18000c789  xor     ebp, ebp
0x18000c78b  jmp     short loc_18000C798
0x18000c78d  xor     edx, edx
0x18000c78f  mov     rcx, rbx
0x18000c792  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000c798  mov     rcx, [rsp+58h+arg_10]
0x18000c79d  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18000c7a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7aa  cmp     rcx, rdi
0x18000c7ad  jz      short loc_18000C7CD
0x18000c7af  test    byte ptr [rcx+1Ch], 8
0x18000c7b3  jz      short loc_18000C7CD
0x18000c7b5  mov     rcx, [rcx+10h]
0x18000c7b9  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000c7c0  mov     edx, 75h ; 'u'
0x18000c7c5  mov     r9d, ebp
0x18000c7c8  call    WPP_SF_d
0x18000c7cd  mov     eax, ebp
0x18000c7cf  mov     rbx, [rsp+58h+arg_0]
0x18000c7d4  add     rsp, 30h
0x18000c7d8  pop     r15
0x18000c7da  pop     r14
0x18000c7dc  pop     rdi
0x18000c7dd  pop     rsi
0x18000c7de  pop     rbp
0x18000c7df  retn
```
