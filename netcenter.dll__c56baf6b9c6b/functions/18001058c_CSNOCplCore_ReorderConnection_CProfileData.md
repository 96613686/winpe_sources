# CSNOCplCore::ReorderConnection(CProfileData *)

- ea: `0x18001058c`
- end: `0x1800107f3`
- name: `?ReorderConnection@CSNOCplCore@@AEAAJPEAVCProfileData@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct CProfileData *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800104ac`
- `0x1800107fc`

## callees

- `0x180002270`
- `0x18000400c`
- `0x180007828`
- `0x180007b60`
- `0x1800086c8`
- `0x18000a2e0`
- `0x18001058c`
- `0x18001113c`
- `0x180012580`
- `0x180013ce8`
- `0x180014274`

## import_xrefs

- `DUI70!StrToID` at `0x180010622`
- `DUI70!StrToID` at `0x18001066b`
- `DUI70!StrToID` at `0x1800106e8`
- `DUI70!StrToID` at `0x180010622`
- `DUI70!StrToID` at `0x18001066b`
- `DUI70!StrToID` at `0x1800106e8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001062e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010677`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800106f4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001062e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180010677`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800106f4`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800106a7`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800106a7`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800106d1`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800106d1`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800105e6`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800105e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSNOCplCore::ReorderConnection(CSNOCplCore *this, struct CProfileData *a2)
{
  int v4; // edi
  unsigned __int64 v5; // rdx
  void *v6; // rax
  __int64 **v7; // rsi
  DirectUI::Element *v8; // rbx
  unsigned __int16 v9; // dx
  unsigned int v10; // r8d
  DirectUI::Element *Descendent; // r15
  _QWORD *v12; // rbx
  struct _GUID *v13; // r13
  unsigned __int16 v14; // ax
  struct DirectUI::Element *v15; // rdi
  __int64 *v16; // rbx
  DirectUI::Element *v17; // rdi
  unsigned __int16 v18; // ax
  struct DirectUI::Element *v19; // rax
  CSNOCplCore *v20; // rcx
  __int64 **v21; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  DirectUI::Element *v24; // [rsp+20h] [rbp-A8h] BYREF
  unsigned int v25; // [rsp+28h] [rbp-A0h] BYREF
  void *v26; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int16 v27[40]; // [rsp+40h] [rbp-88h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = 0;
  if ( *((_QWORD *)a2 + 11) )
  {
    v24 = (DirectUI::Element *)*((_QWORD *)this + 40);
    v25 = 0;
    DirectUI::Element::StartDefer(v24, &v25);
    v6 = DirectUI::HAllocAndZero((DirectUI *)0x10, v5);
    v26 = v6;
    if ( v6 )
    {
      try
      {
        v7 = (__int64 **)std::map<unsigned short *,void *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,void *>>>::map<unsigned short *,void *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,void *>>>(v6);
      }
      catch ( ... )
      {
        goto LABEL_32;
      }
    }
    else
    {
      v7 = 0;
    }
    if ( v7 )
    {
      v8 = (DirectUI::Element *)*((_QWORD *)a2 + 12);
      v9 = StrToID(L"connlist");
      Descendent = DirectUI::Element::FindDescendent(v8, v9);
      if ( Descendent )
      {
        v4 = 0;
        if ( *((_QWORD *)a2 + 11) )
        {
          v12 = (_QWORD *)**((_QWORD **)a2 + 10);
          while ( v12 != *((_QWORD **)a2 + 10) )
          {
            v13 = (struct _GUID *)v12[2];
            StringFromGUID2(v13, v27, v10);
            v14 = StrToID(v27);
            v15 = DirectUI::Element::FindDescendent(Descendent, v14);
            if ( !v15 )
              goto LABEL_30;
            *(_QWORD *)(*(_QWORD *)std::map<unsigned short *,unsigned short *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,unsigned short *>>>::_Try_emplace<unsigned short * const &,>(
                                     v7,
                                     &v26,
                                     &v13[1])
                      + 40LL) = v15;
            v4 = DirectUI::Element::Remove(Descendent, v15);
            v12 = (_QWORD *)*v12;
            if ( v4 < 0 )
              goto LABEL_31;
          }
        }
        v16 = (__int64 *)**v7;
        do
        {
          if ( v16 == *v7 )
            break;
          v4 = DirectUI::Element::Add(Descendent, (struct DirectUI::Element *)v16[5]);
          if ( v4 >= 0 )
          {
            v17 = (DirectUI::Element *)v16[5];
            v18 = StrToID(L"connname");
            v19 = DirectUI::Element::FindDescendent(v17, v18);
            if ( v19 )
              v4 = CSNOCplCore::SetContentAndAccName(v20, v19, (const unsigned __int16 *)v16[4], 0xC1u);
            else
              v4 = -2147418113;
          }
          v21 = (__int64 **)v16[2];
          if ( *((_BYTE *)v21 + 25) )
          {
            for ( i = (__int64 *)v16[1]; !*((_BYTE *)i + 25) && v16 == (__int64 *)i[2]; i = (__int64 *)i[1] )
              v16 = i;
            v16 = i;
          }
          else
          {
            v16 = (__int64 *)v16[2];
            for ( j = *v21; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v16 = j;
          }
        }
        while ( v4 >= 0 );
      }
      else
      {
LABEL_30:
        v4 = -2147418113;
      }
LABEL_31:
      DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v24);
      std::_Tree<std::_Tmap_traits<unsigned short *,void *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,void *>>,0>>::clear(v7);
      std::map<unsigned short *,void *,CStringKey_Less,std::allocator<std::pair<unsigned short * const,void *>>>::`scalar deleting destructor'(v7);
    }
    else
    {
LABEL_32:
      v4 = -2147024882;
    }
    DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v24);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001058c  mov     [rsp+arg_10], rbx
0x180010591  push    rsi
0x180010592  push    rdi
0x180010593  push    r13
0x180010595  push    r14
0x180010597  push    r15
0x180010599  sub     rsp, 0A0h
0x1800105a0  mov     rax, cs:__security_cookie
0x1800105a7  xor     rax, rsp
0x1800105aa  mov     [rsp+0C8h+var_38], rax
0x1800105b2  mov     r14, rdx
0x1800105b5  test    rdx, rdx
0x1800105b8  jnz     short loc_1800105C4
0x1800105ba  mov     eax, 80004003h
0x1800105bf  jmp     loc_1800107CB
0x1800105c4  xor     edi, edi
0x1800105c6  cmp     qword ptr [rdx+58h], 1
0x1800105cb  jb      loc_180010798
0x1800105d1  mov     rcx, [rcx+140h]
0x1800105d8  mov     [rsp+0C8h+var_A8], rcx
0x1800105dd  mov     [rsp+0C8h+var_A0], edi
0x1800105e1  lea     rdx, [rsp+0C8h+var_A0]
0x1800105e6  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1800105ec  nop
0x1800105ed  lea     ecx, [rdi+10h]; this
0x1800105f0  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800105f5  mov     [rsp+0C8h+var_98], rax
0x1800105fa  test    rax, rax
0x1800105fd  jz      short loc_18001060C
0x1800105ff  mov     rcx, rax
0x180010602  call    ??0?$map@PEAGPEAXVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAX@std@@@std@@@std@@QEAA@XZ; std::map<ushort *,void *,CStringKey_Less,std::allocator<std::pair<ushort * const,void *>>>::map<ushort *,void *,CStringKey_Less,std::allocator<std::pair<ushort * const,void *>>>(void)
0x180010607  mov     rsi, rax
0x18001060a  jmp     short loc_18001060E
0x18001060c  xor     esi, esi
0x18001060e  test    rsi, rsi
0x180010611  jz      loc_180010788
0x180010617  mov     rbx, [r14+60h]
0x18001061b  lea     rcx, aConnlist; "connlist"
0x180010622  call    cs:__imp_StrToID
0x180010628  movzx   edx, ax
0x18001062b  mov     rcx, rbx
0x18001062e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180010634  mov     r15, rax
0x180010637  test    rax, rax
0x18001063a  jz      loc_180010767
0x180010640  xor     edi, edi
0x180010642  cmp     [r14+58h], rdi
0x180010646  jz      short loc_1800106BB
0x180010648  mov     rbx, [r14+50h]
0x18001064c  mov     rbx, [rbx]
0x18001064f  cmp     rbx, [r14+50h]
0x180010653  jz      short loc_1800106BB
0x180010655  mov     r13, [rbx+10h]
0x180010659  lea     rdx, [rsp+0C8h+var_88]; unsigned __int16 *
0x18001065e  mov     rcx, r13; struct _GUID *
0x180010661  call    ?StringFromGUID2@@YAXAEAU_GUID@@PEAGK@Z; StringFromGUID2(_GUID &,ushort *,ulong)
0x180010666  lea     rcx, [rsp+0C8h+var_88]
0x18001066b  call    cs:__imp_StrToID
0x180010671  movzx   edx, ax
0x180010674  mov     rcx, r15
0x180010677  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001067d  mov     rdi, rax
0x180010680  test    rax, rax
0x180010683  jz      loc_180010767
0x180010689  lea     r8, [r13+10h]
0x18001068d  lea     rdx, [rsp+0C8h+var_98]
0x180010692  mov     rcx, rsi
0x180010695  call    ??$_Try_emplace@AEBQEAG$$V@?$map@PEAGPEAGVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAG@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAGPEAG@std@@PEAX@std@@_N@1@AEBQEAG@Z; std::map<ushort *,ushort *,CStringKey_Less,std::allocator<std::pair<ushort * const,ushort *>>>::_Try_emplace<ushort * const &,>(ushort * const &)
0x18001069a  mov     rcx, [rax]
0x18001069d  mov     [rcx+28h], rdi
0x1800106a1  mov     rdx, rdi
0x1800106a4  mov     rcx, r15
0x1800106a7  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x1800106ad  mov     edi, eax
0x1800106af  mov     rbx, [rbx]
0x1800106b2  test    eax, eax
0x1800106b4  jns     short loc_18001064F
0x1800106b6  jmp     loc_18001076C
0x1800106bb  mov     rbx, [rsi]
0x1800106be  mov     rbx, [rbx]
0x1800106c1  cmp     rbx, [rsi]
0x1800106c4  jz      loc_18001076C
0x1800106ca  mov     rdx, [rbx+28h]
0x1800106ce  mov     rcx, r15
0x1800106d1  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x1800106d7  mov     edi, eax
0x1800106d9  test    eax, eax
0x1800106db  js      short loc_18001071A
0x1800106dd  mov     rdi, [rbx+28h]
0x1800106e1  lea     rcx, aConnname; "connname"
0x1800106e8  call    cs:__imp_StrToID
0x1800106ee  movzx   edx, ax
0x1800106f1  mov     rcx, rdi
0x1800106f4  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800106fa  test    rax, rax
0x1800106fd  jz      short loc_180010715
0x1800106ff  mov     r9d, 0C1h; unsigned int
0x180010705  mov     r8, [rbx+20h]; unsigned __int16 *
0x180010709  mov     rdx, rax; struct DirectUI::Element *
0x18001070c  call    ?SetContentAndAccName@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEBGI@Z; CSNOCplCore::SetContentAndAccName(DirectUI::Element *,ushort const *,uint)
0x180010711  mov     edi, eax
0x180010713  jmp     short loc_18001071A
0x180010715  mov     edi, 8000FFFFh
0x18001071a  mov     rcx, [rbx+10h]
0x18001071e  cmp     byte ptr [rcx+19h], 0
0x180010722  jz      short loc_180010742
0x180010724  mov     rax, [rbx+8]
0x180010728  jmp     short loc_180010737
0x18001072a  cmp     rbx, [rax+10h]
0x18001072e  jnz     short loc_18001073D
0x180010730  mov     rbx, rax
0x180010733  mov     rax, [rax+8]
0x180010737  cmp     byte ptr [rax+19h], 0
0x18001073b  jz      short loc_18001072A
0x18001073d  mov     rbx, rax
0x180010740  jmp     short loc_18001075D
0x180010742  mov     rbx, rcx
0x180010745  mov     rcx, [rcx]
0x180010748  cmp     byte ptr [rcx+19h], 0
0x18001074c  jnz     short loc_18001075D
0x18001074e  mov     rbx, rcx
0x180010751  mov     rax, [rcx]
0x180010754  mov     rcx, rax
0x180010757  cmp     byte ptr [rax+19h], 0
0x18001075b  jz      short loc_18001074E
0x18001075d  test    edi, edi
0x18001075f  jns     loc_1800106C1
0x180010765  jmp     short loc_18001076C
0x180010767  mov     edi, 8000FFFFh
0x18001076c  lea     rcx, [rsp+0C8h+var_A8]; this
0x180010771  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x180010776  mov     rcx, rsi
0x180010779  call    ?clear@?$_Tree@V?$_Tmap_traits@PEAGPEAXVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAX@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort *,void *,CStringKey_Less,std::allocator<std::pair<ushort * const,void *>>,0>>::clear(void)
0x18001077e  mov     rcx, rsi; void *
0x180010781  call    ??_G?$map@PEAGPEAXVCStringKey_Less@@V?$allocator@U?$pair@QEAGPEAX@std@@@std@@@std@@QEAAPEAXI@Z; std::map<ushort *,void *,CStringKey_Less,std::allocator<std::pair<ushort * const,void *>>>::`scalar deleting destructor'(uint)
0x180010786  jmp     short loc_18001078D
0x180010788  mov     edi, 8007000Eh
0x18001078d  lea     rcx, [rsp+0C8h+var_A8]; this
0x180010792  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x180010797  nop
0x180010798  lea     rax, WPP_GLOBAL_Control
0x18001079f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107a6  cmp     rcx, rax
0x1800107a9  jz      short loc_1800107C9
0x1800107ab  test    byte ptr [rcx+1Ch], 8
0x1800107af  jz      short loc_1800107C9
0x1800107b1  mov     edx, 62h ; 'b'
0x1800107b6  mov     r9d, edi
0x1800107b9  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x1800107c0  mov     rcx, [rcx+10h]
0x1800107c4  call    WPP_SF_d
0x1800107c9  mov     eax, edi
0x1800107cb  mov     rcx, [rsp+0C8h+var_38]
0x1800107d3  xor     rcx, rsp; StackCookie
0x1800107d6  call    __security_check_cookie
0x1800107db  mov     rbx, [rsp+0C8h+arg_10]
0x1800107e3  add     rsp, 0A0h
0x1800107ea  pop     r15
0x1800107ec  pop     r14
0x1800107ee  pop     r13
0x1800107f0  pop     rdi
0x1800107f1  pop     rsi
0x1800107f2  retn
```
