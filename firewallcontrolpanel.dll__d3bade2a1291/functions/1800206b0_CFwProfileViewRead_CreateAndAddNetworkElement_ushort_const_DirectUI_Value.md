# CFwProfileViewRead::CreateAndAddNetworkElement(ushort const *,DirectUI::Value *)

- ea: `0x1800206b0`
- end: `0x18002085f`
- name: `?CreateAndAddNetworkElement@CFwProfileViewRead@@AEAAJPEBGPEAVValue@DirectUI@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(CFwProfileViewRead *__hidden this, const unsigned __int16 *, struct DirectUI::Value *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020598`
- `0x1800212e4`

## callees

- `0x18000994c`
- `0x1800206b0`

## import_xrefs

- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180020828`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180020828`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800207ed`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800207fd`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800207fd`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180020777`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180020777`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180020726`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180020726`
- `DUI70!StrToID` at `0x1800206f1`
- `DUI70!StrToID` at `0x1800207aa`
- `DUI70!StrToID` at `0x1800207d1`
- `DUI70!StrToID` at `0x1800206f1`
- `DUI70!StrToID` at `0x1800207aa`
- `DUI70!StrToID` at `0x1800207d1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800206fd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800207b8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800207df`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800206fd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800207b8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800207df`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180020836`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180020836`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180020844`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180020844`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800207c4`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800207c4`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020820`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020820`

## pseudocode

```c
__int64 __fastcall CFwProfileViewRead::CreateAndAddNetworkElement(
        CFwProfileViewRead *this,
        const unsigned __int16 *a2,
        struct DirectUI::Value *a3)
{
  int v6; // edi
  DirectUI::Element *v7; // rbx
  int v8; // r14d
  unsigned __int16 v9; // ax
  struct DirectUI::Element *Descendent; // rbx
  CFwCplLua *v11; // rcx
  __int64 v12; // rdx
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rax
  unsigned __int16 v15; // ax
  DirectUI::Element *v16; // rcx
  DirectUI::Element *Parent; // rbx
  struct DirectUI::Element *v19; // [rsp+58h] [rbp+10h] BYREF

  v19 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v7 = (DirectUI::Element *)*((_QWORD *)this + 4);
  v8 = 0;
  v9 = StrToID(L"networks");
  Descendent = DirectUI::Element::FindDescendent(v7, v9);
  v6 = DirectUI::DUIXmlParser::CreateElement(
         *((DirectUI::DUIXmlParser **)this + 7),
         L"networkitem",
         0,
         Descendent,
         0,
         &v19);
  if ( v6 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 24;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids, (unsigned int)v6);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  v6 = DirectUI::Element::Add(Descendent, v19);
  if ( v6 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 25;
      goto LABEL_7;
    }
LABEL_14:
    if ( v19 && !v8 )
      DirectUI::Element::Destroy(v19, 1);
    return (unsigned int)v6;
  }
  v13 = StrToID(L"networkname");
  v14 = DirectUI::Element::FindDescendent(v19, v13);
  DirectUI::Element::SetContentString(v14, a2);
  v15 = StrToID(L"networkIcon");
  v16 = DirectUI::Element::FindDescendent(v19, v15);
  if ( !a3 )
  {
    Parent = DirectUI::Element::GetParent(v16);
    DirectUI::Element::SetVisible(Parent, 0);
    DirectUI::Element::SetLayoutPos(Parent, -3);
    return (unsigned int)v6;
  }
  v6 = DirectUI::Element::SetValue(
         v16,
         (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
         1,
         a3);
  v8 = 1;
  if ( v6 < 0 )
    goto LABEL_14;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800206b0  mov     [rsp+arg_0], rbx
0x1800206b5  mov     [rsp+arg_10], rbp
0x1800206ba  push    rsi
0x1800206bb  push    rdi
0x1800206bc  push    r14
0x1800206be  sub     rsp, 30h
0x1800206c2  mov     [rsp+48h+arg_8], 0
0x1800206cb  mov     rbp, r8
0x1800206ce  mov     rsi, rdx
0x1800206d1  mov     rdi, rcx
0x1800206d4  test    rdx, rdx
0x1800206d7  jnz     short loc_1800206E3
0x1800206d9  mov     edi, 80070057h
0x1800206de  jmp     loc_18002084A
0x1800206e3  mov     rbx, [rcx+20h]
0x1800206e7  xor     r14d, r14d
0x1800206ea  lea     rcx, aNetworks; "networks"
0x1800206f1  call    cs:__imp_StrToID
0x1800206f7  movzx   edx, ax
0x1800206fa  mov     rcx, rbx
0x1800206fd  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180020703  mov     rcx, [rdi+38h]
0x180020707  lea     rdx, aNetworkitem; "networkitem"
0x18002070e  mov     rbx, rax
0x180020711  xor     r8d, r8d
0x180020714  lea     rax, [rsp+48h+arg_8]
0x180020719  mov     r9, rbx
0x18002071c  mov     [rsp+48h+var_20], rax
0x180020721  mov     [rsp+48h+var_28], r14
0x180020726  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18002072c  mov     edi, eax
0x18002072e  test    eax, eax
0x180020730  jns     short loc_18002076F
0x180020732  mov     rcx, cs:WPP_GLOBAL_Control
0x180020739  lea     rax, WPP_GLOBAL_Control
0x180020740  cmp     rcx, rax
0x180020743  jz      loc_18002080F
0x180020749  test    byte ptr [rcx+1Ch], 1
0x18002074d  jz      loc_18002080F
0x180020753  lea     edx, [r14+18h]
0x180020757  mov     rcx, [rcx+10h]
0x18002075b  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020762  mov     r9d, edi
0x180020765  call    WPP_SF_d
0x18002076a  jmp     loc_18002080F
0x18002076f  mov     rdx, [rsp+48h+arg_8]
0x180020774  mov     rcx, rbx
0x180020777  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18002077d  mov     edi, eax
0x18002077f  test    eax, eax
0x180020781  jns     short loc_1800207A3
0x180020783  mov     rcx, cs:WPP_GLOBAL_Control
0x18002078a  lea     rax, WPP_GLOBAL_Control
0x180020791  cmp     rcx, rax
0x180020794  jz      short loc_18002080F
0x180020796  test    byte ptr [rcx+1Ch], 1
0x18002079a  jz      short loc_18002080F
0x18002079c  mov     edx, 19h
0x1800207a1  jmp     short loc_180020757
0x1800207a3  lea     rcx, aNetworkname; "networkname"
0x1800207aa  call    cs:__imp_StrToID
0x1800207b0  mov     rcx, [rsp+48h+arg_8]
0x1800207b5  movzx   edx, ax
0x1800207b8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800207be  mov     rcx, rax
0x1800207c1  mov     rdx, rsi
0x1800207c4  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800207ca  lea     rcx, aNetworkicon; "networkIcon"
0x1800207d1  call    cs:__imp_StrToID
0x1800207d7  mov     rcx, [rsp+48h+arg_8]
0x1800207dc  movzx   edx, ax
0x1800207df  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800207e5  mov     rcx, rax
0x1800207e8  test    rbp, rbp
0x1800207eb  jz      short loc_180020828
0x1800207ed  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800207f4  mov     r9, rbp
0x1800207f7  mov     r8d, 1
0x1800207fd  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180020803  mov     edi, eax
0x180020805  mov     r14d, 1
0x18002080b  test    eax, eax
0x18002080d  jns     short loc_18002084A
0x18002080f  mov     rcx, [rsp+48h+arg_8]
0x180020814  test    rcx, rcx
0x180020817  jz      short loc_18002084A
0x180020819  test    r14d, r14d
0x18002081c  jnz     short loc_18002084A
0x18002081e  mov     dl, 1
0x180020820  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180020826  jmp     short loc_18002084A
0x180020828  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x18002082e  mov     rcx, rax
0x180020831  xor     edx, edx
0x180020833  mov     rbx, rax
0x180020836  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18002083c  mov     edx, 0FFFFFFFDh
0x180020841  mov     rcx, rbx
0x180020844  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18002084a  mov     rbx, [rsp+48h+arg_0]
0x18002084f  mov     eax, edi
0x180020851  mov     rbp, [rsp+48h+arg_10]
0x180020856  add     rsp, 30h
0x18002085a  pop     r14
0x18002085c  pop     rdi
0x18002085d  pop     rsi
0x18002085e  retn
```
