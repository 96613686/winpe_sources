# CSNOCplCore::ReorderProfile(CProfileData * *)

- ea: `0x1800107fc`
- end: `0x180010b9f`
- name: `?ReorderProfile@CSNOCplCore@@AEAAJPEAPEAVCProfileData@@@Z`
- size: `931`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct CProfileData **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000b384`

## callees

- `0x180002270`
- `0x180008644`
- `0x18000a2e0`
- `0x18001058c`
- `0x1800107fc`
- `0x180012580`
- `0x180014274`
- `0x18001431c`

## import_xrefs

- `DUI70!StrToID` at `0x180010880`
- `DUI70!StrToID` at `0x1800108cc`
- `DUI70!StrToID` at `0x18001093c`
- `DUI70!StrToID` at `0x180010880`
- `DUI70!StrToID` at `0x1800108cc`
- `DUI70!StrToID` at `0x18001093c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001088c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800108d8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010948`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001088c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800108d8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010948`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001095d`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001095d`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180010a30`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180010adb`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180010a30`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180010adb`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18001086b`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18001086b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSNOCplCore::ReorderProfile(CSNOCplCore *this, struct CProfileData **a2)
{
  __int64 v5; // rdi
  DirectUI::Element *v6; // rbx
  unsigned __int16 v7; // ax
  unsigned int v8; // r8d
  DirectUI::Element *Descendent; // r12
  struct CProfileData *v10; // rdi
  unsigned __int16 v11; // ax
  struct DirectUI::Element *v12; // rax
  int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rbx
  unsigned __int16 v16; // ax
  struct DirectUI::Element *v17; // rax
  unsigned int v18; // r15d
  unsigned int v19; // r12d
  __int64 v20; // rax
  __int64 v21; // r13
  DirectUI::Element *v22; // r12
  __int64 v23; // rdi
  __int64 v24; // rax
  __int64 v25; // rdi
  int v26; // eax
  int v27; // r8d
  __int64 i; // [rsp+30h] [rbp-89h] BYREF
  int v29; // [rsp+38h] [rbp-81h]
  int v30; // [rsp+3Ch] [rbp-7Dh]
  DirectUI::Element *v31; // [rsp+40h] [rbp-79h]
  _DWORD v32[4]; // [rsp+48h] [rbp-71h]
  _DWORD v33[4]; // [rsp+58h] [rbp-61h]
  DirectUI::Element *v34; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v35[4]; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int16 v36[40]; // [rsp+80h] [rbp-39h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *(_QWORD *)(*((_QWORD *)this + 19) + 8LL);
  if ( !v5 )
    return 0;
  v34 = (DirectUI::Element *)*((_QWORD *)this + 40);
  v35[0] = 0;
  DirectUI::Element::StartDefer(v34, v35);
  v6 = (DirectUI::Element *)*((_QWORD *)this + 40);
  v7 = StrToID(L"profilearea");
  Descendent = DirectUI::Element::FindDescendent(v6, v7);
  v31 = Descendent;
  if ( !Descendent )
    goto LABEL_49;
  if ( v5 != 1 )
  {
    v13 = 0;
    v14 = ***((_QWORD ***)this + 19);
    for ( i = v14; v14 != **((_QWORD **)this + 19); v14 = i )
    {
      v15 = *(_QWORD *)(v14 + 48);
      StringFromGUID2((struct _GUID *)v15, v36, v8);
      v16 = StrToID(v36);
      v17 = DirectUI::Element::FindDescendent(Descendent, v16);
      *(_QWORD *)(v15 + 96) = v17;
      v13 = v17 ? DirectUI::Element::Remove(Descendent, v17) : -2147418113;
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(&i);
      if ( v13 < 0 )
        break;
    }
    v33[0] = 40;
    v33[1] = 20;
    v33[2] = 1;
    v32[0] = 2;
    v32[1] = 3;
    v32[2] = 1;
    v18 = 0;
    v30 = 0;
    if ( v13 >= 0 )
    {
      do
      {
        if ( v18 >= 3 )
          break;
        v19 = 0;
        v29 = 0;
        do
        {
          if ( v19 >= 3 )
            break;
          v20 = ***((_QWORD ***)this + 19);
          i = v20;
          v21 = (int)v19;
          v22 = v31;
          while ( v20 != **((_QWORD **)this + 19) )
          {
            v23 = *(_QWORD *)(v20 + 48);
            if ( *(_QWORD *)(v23 + 96) && *(_DWORD *)(v23 + 104) == v32[v18] && (*(_DWORD *)(v23 + 48) & v33[v21]) != 0 )
            {
              if ( !*a2 )
                *a2 = (struct CProfileData *)v23;
              v13 = DirectUI::Element::Add(v22, *(struct DirectUI::Element **)(v23 + 96));
              if ( v13 >= 0 )
                v13 = CSNOCplCore::ReorderConnection(this, (struct CProfileData *)v23);
              *(_QWORD *)(v23 + 96) = 0;
            }
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(&i);
            if ( v13 < 0 )
              break;
            v20 = i;
          }
          v19 = ++v29;
        }
        while ( v13 >= 0 );
        v18 = ++v30;
      }
      while ( v13 >= 0 );
      Descendent = v31;
    }
    v24 = ***((_QWORD ***)this + 19);
    i = v24;
    if ( v13 >= 0 )
    {
      while ( v24 != **((_QWORD **)this + 19) )
      {
        v25 = *(_QWORD *)(v24 + 48);
        if ( *(_QWORD *)(v25 + 96) )
        {
          if ( !*a2 )
            *a2 = (struct CProfileData *)v25;
          v26 = DirectUI::Element::Add(Descendent, *(struct DirectUI::Element **)(v25 + 96));
          v13 = v26;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, v27, *(_QWORD *)(v25 + 16), v26);
          if ( v13 >= 0 )
            v13 = CSNOCplCore::ReorderConnection(this, (struct CProfileData *)v25);
          *(_QWORD *)(v25 + 96) = 0;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(&i);
        if ( v13 < 0 )
          break;
        v24 = i;
      }
    }
    goto LABEL_50;
  }
  v10 = *(struct CProfileData **)(***((_QWORD ***)this + 19) + 48LL);
  *a2 = v10;
  StringFromGUID2((struct _GUID *)v10, v36, v8);
  v11 = StrToID(v36);
  v12 = DirectUI::Element::FindDescendent(Descendent, v11);
  *((_QWORD *)v10 + 12) = v12;
  if ( v12 )
  {
    v13 = CSNOCplCore::ReorderConnection(this, v10);
    *((_QWORD *)v10 + 12) = 0;
  }
  else
  {
LABEL_49:
    v13 = -2147418113;
  }
LABEL_50:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)v13);
  DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v34);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800107fc  mov     [rsp-8+arg_10], rbx
0x180010801  push    rbp
0x180010802  push    rsi
0x180010803  push    rdi
0x180010804  push    r12
0x180010806  push    r13
0x180010808  push    r14
0x18001080a  push    r15
0x18001080c  lea     rbp, [rsp-27h]
0x180010811  sub     rsp, 0E0h
0x180010818  mov     rax, cs:__security_cookie
0x18001081f  xor     rax, rsp
0x180010822  mov     [rbp+57h+var_40], rax
0x180010826  mov     r14, rdx
0x180010829  mov     rsi, rcx
0x18001082c  xor     r13d, r13d
0x18001082f  test    rdx, rdx
0x180010832  jnz     short loc_18001083E
0x180010834  mov     eax, 80004003h
0x180010839  jmp     loc_180010B78
0x18001083e  mov     [rdx], r13
0x180010841  mov     rax, [rcx+98h]
0x180010848  mov     rdi, [rax+8]
0x18001084c  test    rdi, rdi
0x18001084f  jnz     short loc_180010858
0x180010851  xor     eax, eax
0x180010853  jmp     loc_180010B78
0x180010858  mov     rcx, [rcx+140h]
0x18001085f  mov     [rbp+57h+var_A8], rcx
0x180010863  mov     [rbp+57h+var_A0], r13d
0x180010867  lea     rdx, [rbp+57h+var_A0]
0x18001086b  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x180010871  nop
0x180010872  mov     rbx, [rsi+140h]
0x180010879  lea     rcx, aProfilearea; "profilearea"
0x180010880  call    cs:__imp_StrToID
0x180010886  movzx   edx, ax
0x180010889  mov     rcx, rbx
0x18001088c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010892  mov     r12, rax
0x180010895  mov     [rbp+57h+var_D0], rax
0x180010899  test    rax, rax
0x18001089c  jz      loc_180010B35
0x1800108a2  cmp     rdi, 1
0x1800108a6  jnz     short loc_180010901
0x1800108a8  mov     rcx, [rsi+98h]
0x1800108af  mov     rdx, [rcx]
0x1800108b2  mov     rcx, [rdx]
0x1800108b5  mov     rdi, [rcx+30h]
0x1800108b9  mov     [r14], rdi
0x1800108bc  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x1800108c0  mov     rcx, rdi; struct _GUID *
0x1800108c3  call    ?StringFromGUID2@@YAXAEAU_GUID@@PEAGK@Z; StringFromGUID2(_GUID &,ushort *,ulong)
0x1800108c8  lea     rcx, [rbp+57h+var_90]
0x1800108cc  call    cs:__imp_StrToID
0x1800108d2  movzx   edx, ax
0x1800108d5  mov     rcx, r12
0x1800108d8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800108de  mov     [rdi+60h], rax
0x1800108e2  test    rax, rax
0x1800108e5  jz      loc_180010B35
0x1800108eb  mov     rdx, rdi; struct CProfileData *
0x1800108ee  mov     rcx, rsi; this
0x1800108f1  call    ?ReorderConnection@CSNOCplCore@@AEAAJPEAVCProfileData@@@Z; CSNOCplCore::ReorderConnection(CProfileData *)
0x1800108f6  mov     ebx, eax
0x1800108f8  mov     [rdi+60h], r13
0x1800108fc  jmp     loc_180010B3A
0x180010901  mov     ebx, r13d
0x180010904  jbe     loc_180010B3A
0x18001090a  mov     rax, [rsi+98h]
0x180010911  mov     rax, [rax]
0x180010914  mov     rax, [rax]
0x180010917  mov     [rsp+110h+var_E0], rax
0x18001091c  mov     rcx, [rsi+98h]
0x180010923  cmp     rax, [rcx]
0x180010926  jz      short loc_180010981
0x180010928  mov     rbx, [rax+30h]
0x18001092c  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180010930  mov     rcx, rbx; struct _GUID *
0x180010933  call    ?StringFromGUID2@@YAXAEAU_GUID@@PEAGK@Z; StringFromGUID2(_GUID &,ushort *,ulong)
0x180010938  lea     rcx, [rbp+57h+var_90]
0x18001093c  call    cs:__imp_StrToID
0x180010942  movzx   edx, ax
0x180010945  mov     rcx, r12
0x180010948  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001094e  mov     [rbx+60h], rax
0x180010952  test    rax, rax
0x180010955  jz      short loc_180010967
0x180010957  mov     rdx, rax
0x18001095a  mov     rcx, r12
0x18001095d  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x180010963  mov     ebx, eax
0x180010965  jmp     short loc_18001096C
0x180010967  mov     ebx, 8000FFFFh
0x18001096c  lea     rcx, [rsp+110h+var_E0]
0x180010971  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(void)
0x180010976  test    ebx, ebx
0x180010978  js      short loc_180010981
0x18001097a  mov     rax, [rsp+110h+var_E0]
0x18001097f  jmp     short loc_18001091C
0x180010981  mov     [rbp+57h+var_B8], 28h ; '('
0x180010988  mov     [rbp+57h+var_B4], 14h
0x18001098f  mov     [rbp+57h+var_B0], 1
0x180010996  mov     [rbp+57h+var_C8], 2
0x18001099d  mov     [rbp+57h+var_C4], 3
0x1800109a4  mov     [rbp+57h+var_C0], 1
0x1800109ab  mov     r15d, r13d
0x1800109ae  mov     [rbp+57h+var_D4], r13d
0x1800109b2  test    ebx, ebx
0x1800109b4  js      loc_180010A95
0x1800109ba  cmp     r15d, 3
0x1800109be  jnb     loc_180010A91
0x1800109c4  mov     r12d, r13d
0x1800109c7  mov     [rsp+110h+var_D8], r13d
0x1800109cc  movsxd  rax, r15d
0x1800109cf  mov     r15, rax
0x1800109d2  cmp     r12d, 3
0x1800109d6  jnb     loc_180010A7E
0x1800109dc  mov     rax, [rsi+98h]
0x1800109e3  mov     rax, [rax]
0x1800109e6  mov     rax, [rax]
0x1800109e9  mov     [rsp+110h+var_E0], rax
0x1800109ee  movsxd  r13, r12d
0x1800109f1  mov     r12, [rbp+57h+var_D0]
0x1800109f5  mov     rcx, [rsi+98h]
0x1800109fc  cmp     rax, [rcx]
0x1800109ff  jz      short loc_180010A66
0x180010a01  mov     rdi, [rax+30h]
0x180010a05  cmp     qword ptr [rdi+60h], 0
0x180010a0a  jz      short loc_180010A51
0x180010a0c  mov     eax, [rbp+r15*4+57h+var_C8]
0x180010a11  cmp     [rdi+68h], eax
0x180010a14  jnz     short loc_180010A51
0x180010a16  mov     eax, [rdi+30h]
0x180010a19  test    [rbp+r13*4+57h+var_B8], eax
0x180010a1e  jz      short loc_180010A51
0x180010a20  cmp     qword ptr [r14], 0
0x180010a24  jnz     short loc_180010A29
0x180010a26  mov     [r14], rdi
0x180010a29  mov     rdx, [rdi+60h]
0x180010a2d  mov     rcx, r12
0x180010a30  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180010a36  mov     ebx, eax
0x180010a38  test    eax, eax
0x180010a3a  js      short loc_180010A49
0x180010a3c  mov     rdx, rdi; struct CProfileData *
0x180010a3f  mov     rcx, rsi; this
0x180010a42  call    ?ReorderConnection@CSNOCplCore@@AEAAJPEAVCProfileData@@@Z; CSNOCplCore::ReorderConnection(CProfileData *)
0x180010a47  mov     ebx, eax
0x180010a49  mov     qword ptr [rdi+60h], 0
0x180010a51  lea     rcx, [rsp+110h+var_E0]
0x180010a56  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(void)
0x180010a5b  test    ebx, ebx
0x180010a5d  js      short loc_180010A66
0x180010a5f  mov     rax, [rsp+110h+var_E0]
0x180010a64  jmp     short loc_1800109F5
0x180010a66  mov     r12d, [rsp+110h+var_D8]
0x180010a6b  inc     r12d
0x180010a6e  mov     [rsp+110h+var_D8], r12d
0x180010a73  xor     r13d, r13d
0x180010a76  test    ebx, ebx
0x180010a78  jns     loc_1800109D2
0x180010a7e  mov     r15d, [rbp+57h+var_D4]
0x180010a82  inc     r15d
0x180010a85  mov     [rbp+57h+var_D4], r15d
0x180010a89  test    ebx, ebx
0x180010a8b  jns     loc_1800109BA
0x180010a91  mov     r12, [rbp+57h+var_D0]
0x180010a95  mov     rax, [rsi+98h]
0x180010a9c  mov     rax, [rax]
0x180010a9f  mov     rax, [rax]
0x180010aa2  mov     [rsp+110h+var_E0], rax
0x180010aa7  test    ebx, ebx
0x180010aa9  js      loc_180010B3A
0x180010aaf  lea     r15, WPP_GLOBAL_Control
0x180010ab6  mov     rcx, [rsi+98h]
0x180010abd  cmp     rax, [rcx]
0x180010ac0  jz      short loc_180010B41
0x180010ac2  mov     rdi, [rax+30h]
0x180010ac6  cmp     [rdi+60h], r13
0x180010aca  jz      short loc_180010B20
0x180010acc  cmp     [r14], r13
0x180010acf  jnz     short loc_180010AD4
0x180010ad1  mov     [r14], rdi
0x180010ad4  mov     rdx, [rdi+60h]
0x180010ad8  mov     rcx, r12
0x180010adb  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180010ae1  mov     ebx, eax
0x180010ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180010aea  cmp     rcx, r15
0x180010aed  jz      short loc_180010B0B
0x180010aef  test    byte ptr [rcx+1Ch], 4
0x180010af3  jz      short loc_180010B0B
0x180010af5  mov     edx, 60h ; '`'
0x180010afa  mov     [rsp+110h+var_F0], eax
0x180010afe  mov     r9, [rdi+10h]
0x180010b02  mov     rcx, [rcx+10h]
0x180010b06  call    WPP_SF_SD
0x180010b0b  test    ebx, ebx
0x180010b0d  js      short loc_180010B1C
0x180010b0f  mov     rdx, rdi; struct CProfileData *
0x180010b12  mov     rcx, rsi; this
0x180010b15  call    ?ReorderConnection@CSNOCplCore@@AEAAJPEAVCProfileData@@@Z; CSNOCplCore::ReorderConnection(CProfileData *)
0x180010b1a  mov     ebx, eax
0x180010b1c  mov     [rdi+60h], r13
0x180010b20  lea     rcx, [rsp+110h+var_E0]
0x180010b25  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>::operator++(void)
0x180010b2a  test    ebx, ebx
0x180010b2c  js      short loc_180010B41
0x180010b2e  mov     rax, [rsp+110h+var_E0]
0x180010b33  jmp     short loc_180010AB6
0x180010b35  mov     ebx, 8000FFFFh
0x180010b3a  lea     r15, WPP_GLOBAL_Control
0x180010b41  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b48  cmp     rcx, r15
0x180010b4b  jz      short loc_180010B6C
0x180010b4d  test    byte ptr [rcx+1Ch], 8
0x180010b51  jz      short loc_180010B6C
0x180010b53  mov     edx, 61h ; 'a'
0x180010b58  mov     r9d, ebx
0x180010b5b  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180010b62  mov     rcx, [rcx+10h]
0x180010b66  call    WPP_SF_d
0x180010b6b  nop
0x180010b6c  lea     rcx, [rbp+57h+var_A8]; this
0x180010b70  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x180010b75  nop
0x180010b76  mov     eax, ebx
0x180010b78  mov     rcx, [rbp+57h+var_40]
0x180010b7c  xor     rcx, rsp; StackCookie
0x180010b7f  call    __security_check_cookie
0x180010b84  mov     rbx, [rsp+110h+arg_10]
0x180010b8c  add     rsp, 0E0h
0x180010b93  pop     r15
0x180010b95  pop     r14
0x180010b97  pop     r13
0x180010b99  pop     r12
0x180010b9b  pop     rdi
0x180010b9c  pop     rsi
0x180010b9d  pop     rbp
0x180010b9e  retn
```
