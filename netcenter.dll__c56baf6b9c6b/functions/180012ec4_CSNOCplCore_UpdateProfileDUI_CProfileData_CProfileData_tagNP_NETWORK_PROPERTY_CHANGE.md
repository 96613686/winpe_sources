# CSNOCplCore::UpdateProfileDUI(CProfileData *,CProfileData *,tagNP_NETWORK_PROPERTY_CHANGE)

- ea: `0x180012ec4`
- end: `0x180013054`
- name: `?UpdateProfileDUI@CSNOCplCore@@AEAAJPEAVCProfileData@@0W4tagNP_NETWORK_PROPERTY_CHANGE@@@Z`
- size: `400`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18000ef50`
- `0x18000f9ec`

## callees

- `0x180002270`
- `0x1800117f4`
- `0x180011950`
- `0x180011a50`
- `0x180012580`
- `0x180012ec4`
- `0x180014274`
- `0x1800142b4`

## import_xrefs

- `DUI70!StrToID` at `0x180012f0a`
- `DUI70!StrToID` at `0x180012f3c`
- `DUI70!StrToID` at `0x180012f0a`
- `DUI70!StrToID` at `0x180012f3c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012f16`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012f48`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012f16`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012f48`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012f74`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012f74`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012f81`
- `DUI70!?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012f81`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012f5d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180012f5d`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::UpdateProfileDUI(
        CSNOCplCore *a1,
        struct _GUID *a2,
        const unsigned __int16 **a3,
        char a4)
{
  DirectUI::Element *v7; // rbx
  unsigned __int16 v8; // ax
  CSNOCplCore *v9; // rcx
  struct DirectUI::Element *Descendent; // rbp
  __int64 v11; // r8
  unsigned __int16 v12; // ax
  DirectUI::Element *v13; // rax
  DirectUI::Element *v14; // rsi
  int v15; // ebx
  CSNOCplCore *v16; // rcx
  PVOID *v17; // rcx
  __int64 v18; // rdx
  unsigned __int16 v20[40]; // [rsp+20h] [rbp-98h] BYREF

  StringFromGUID2(a2, v20, (unsigned int)a3);
  v7 = (DirectUI::Element *)*((_QWORD *)a1 + 40);
  v8 = StrToID(v20);
  Descendent = DirectUI::Element::FindDescendent(v7, v8);
  if ( !Descendent )
  {
    v15 = -2147418113;
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)v15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_18;
    v18 = 124;
    goto LABEL_16;
  }
  if ( (a4 & 4) == 0 )
  {
LABEL_6:
    v15 = CSNOCplCore::ShowNetworkCategory(v9, Descendent, (struct CProfileData *)a3);
    if ( v15 >= 0 )
    {
      if ( (a4 & 0x20) == 0
        || (v15 = CSNOCplCore::ShowProfileConnectivity(v16, Descendent, (struct CProfileData *)a3), v15 >= 0) )
      {
        v15 = CSNOCplCore::ShowHomeGroup(a1, Descendent, (struct CProfileData *)a3);
      }
    }
    goto LABEL_17;
  }
  v12 = StrToID(L"profilename");
  v13 = DirectUI::Element::FindDescendent(Descendent, v12);
  v14 = v13;
  if ( v13 )
  {
    v15 = DirectUI::Element::SetContentString(v13, a3[2]);
    if ( v15 >= 0 )
    {
      DirectUI::Element::SetAccValue(v14, a3[2]);
      DirectUI::Element::SetAccDesc(v14, a3[2]);
      goto LABEL_6;
    }
LABEL_17:
    v17 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v15 = -2147418113;
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v18 = 123;
LABEL_16:
    WPP_SF_S(v17[2], v18, v11, v20);
    goto LABEL_17;
  }
LABEL_18:
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
    WPP_SF_d(v17[2], 125, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, (unsigned int)v15);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180012ec4  push    rbx
0x180012ec6  push    rbp
0x180012ec7  push    rsi
0x180012ec8  push    rdi
0x180012ec9  push    r12
0x180012ecb  push    r14
0x180012ecd  push    r15
0x180012ecf  sub     rsp, 80h
0x180012ed6  mov     rax, cs:__security_cookie
0x180012edd  xor     rax, rsp
0x180012ee0  mov     [rsp+0B8h+var_48], rax
0x180012ee5  mov     rax, rdx
0x180012ee8  mov     r15, rcx
0x180012eeb  mov     rcx, rax; struct _GUID *
0x180012eee  lea     rdx, [rsp+0B8h+var_98]; unsigned __int16 *
0x180012ef3  mov     r14d, r9d
0x180012ef6  mov     rdi, r8
0x180012ef9  call    ?StringFromGUID2@@YAXAEAU_GUID@@PEAGK@Z; StringFromGUID2(_GUID &,ushort *,ulong)
0x180012efe  mov     rbx, [r15+140h]
0x180012f05  lea     rcx, [rsp+0B8h+var_98]
0x180012f0a  call    cs:__imp_StrToID
0x180012f10  movzx   edx, ax
0x180012f13  mov     rcx, rbx
0x180012f16  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012f1c  lea     r12, WPP_GLOBAL_Control
0x180012f23  mov     rbp, rax
0x180012f26  test    rax, rax
0x180012f29  jz      loc_180012FDF
0x180012f2f  test    r14b, 4
0x180012f33  jz      short loc_180012F87
0x180012f35  lea     rcx, aProfilename; "profilename"
0x180012f3c  call    cs:__imp_StrToID
0x180012f42  movzx   edx, ax
0x180012f45  mov     rcx, rbp
0x180012f48  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012f4e  mov     rsi, rax
0x180012f51  test    rax, rax
0x180012f54  jz      short loc_180012FC1
0x180012f56  mov     rdx, [rdi+10h]
0x180012f5a  mov     rcx, rax
0x180012f5d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180012f63  mov     ebx, eax
0x180012f65  test    eax, eax
0x180012f67  js      loc_180013009
0x180012f6d  mov     rdx, [rdi+10h]
0x180012f71  mov     rcx, rsi
0x180012f74  call    cs:__imp_?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccValue(ushort const *)
0x180012f7a  mov     rdx, [rdi+10h]
0x180012f7e  mov     rcx, rsi
0x180012f81  call    cs:__imp_?SetAccDesc@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccDesc(ushort const *)
0x180012f87  mov     r8, rdi; struct CProfileData *
0x180012f8a  mov     rdx, rbp; struct DirectUI::Element *
0x180012f8d  call    ?ShowNetworkCategory@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEAVCProfileData@@@Z; CSNOCplCore::ShowNetworkCategory(DirectUI::Element *,CProfileData *)
0x180012f92  mov     ebx, eax
0x180012f94  test    eax, eax
0x180012f96  js      short loc_180013009
0x180012f98  test    r14b, 20h
0x180012f9c  jz      short loc_180012FAF
0x180012f9e  mov     r8, rdi; struct CProfileData *
0x180012fa1  mov     rdx, rbp; struct DirectUI::Element *
0x180012fa4  call    ?ShowProfileConnectivity@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEAVCProfileData@@@Z; CSNOCplCore::ShowProfileConnectivity(DirectUI::Element *,CProfileData *)
0x180012fa9  mov     ebx, eax
0x180012fab  test    eax, eax
0x180012fad  js      short loc_180013009
0x180012faf  mov     r8, rdi; struct CProfileData *
0x180012fb2  mov     rdx, rbp; struct DirectUI::Element *
0x180012fb5  mov     rcx, r15; this
0x180012fb8  call    ?ShowHomeGroup@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEAVCProfileData@@@Z; CSNOCplCore::ShowHomeGroup(DirectUI::Element *,CProfileData *)
0x180012fbd  mov     ebx, eax
0x180012fbf  jmp     short loc_180013009
0x180012fc1  mov     ebx, 8000FFFFh
0x180012fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fcd  cmp     rcx, r12
0x180012fd0  jz      short loc_180013033
0x180012fd2  test    byte ptr [rcx+1Ch], 2
0x180012fd6  jz      short loc_180013010
0x180012fd8  mov     edx, 7Bh ; '{'
0x180012fdd  jmp     short loc_180012FFB
0x180012fdf  mov     ebx, 8000FFFFh
0x180012fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012feb  cmp     rcx, r12
0x180012fee  jz      short loc_180013033
0x180012ff0  test    byte ptr [rcx+1Ch], 2
0x180012ff4  jz      short loc_180013010
0x180012ff6  mov     edx, 7Ch ; '|'
0x180012ffb  mov     rcx, [rcx+10h]
0x180012fff  lea     r9, [rsp+0B8h+var_98]
0x180013004  call    WPP_SF_S
0x180013009  mov     rcx, cs:WPP_GLOBAL_Control
0x180013010  cmp     rcx, r12
0x180013013  jz      short loc_180013033
0x180013015  test    byte ptr [rcx+1Ch], 8
0x180013019  jz      short loc_180013033
0x18001301b  mov     rcx, [rcx+10h]
0x18001301f  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180013026  mov     edx, 7Dh ; '}'
0x18001302b  mov     r9d, ebx
0x18001302e  call    WPP_SF_d
0x180013033  mov     eax, ebx
0x180013035  mov     rcx, [rsp+0B8h+var_48]
0x18001303a  xor     rcx, rsp; StackCookie
0x18001303d  call    __security_check_cookie
0x180013042  add     rsp, 80h
0x180013049  pop     r15
0x18001304b  pop     r14
0x18001304d  pop     r12
0x18001304f  pop     rdi
0x180013050  pop     rsi
0x180013051  pop     rbp
0x180013052  pop     rbx
0x180013053  retn
```
