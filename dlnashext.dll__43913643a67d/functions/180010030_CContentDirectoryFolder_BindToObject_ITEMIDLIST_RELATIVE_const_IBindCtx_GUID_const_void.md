# CContentDirectoryFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180010030`
- end: `0x1800103d2`
- name: `?BindToObject@CContentDirectoryFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `930`
- prototype: `int(CContentDirectoryFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011204`
- `0x1800157c0`
- `0x180016af0`

## callees

- `0x180001710`
- `0x18000a030`
- `0x180010030`
- `0x180011930`
- `0x180014a00`
- `0x180014e48`
- `0x180017ef0`
- `0x180019298`
- `0x180019b84`
- `0x180019ca4`
- `0x180035010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHBindToFolderIDListParent` at `0x180010339`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToFolderIDListParent` at `0x180010339`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CContentDirectoryFolder::BindToObject(
        unsigned __int64 this,
        const ITEMIDLIST *a2,
        struct IBindCtx *a3,
        struct _GUID *a4,
        void **a5)
{
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  HRESULT Folder; // edi
  void *v14; // rsi
  PVOID *v15; // r10
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  void *ppv; // [rsp+40h] [rbp-30h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v23[12]; // [rsp+50h] [rbp-20h] BYREF
  int v24; // [rsp+5Ch] [rbp-14h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qq_guid_q(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, (_DWORD)a3, (_DWORD)a2, (_DWORD)a3, (__int64)a4);
  }
  *a5 = 0;
  if ( !(unsigned int)ILIsChild((const struct _ITEMIDLIST_RELATIVE *)a2) )
  {
    ppv = 0;
    ppidlLast = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&ppv);
    Folder = SHBindToFolderIDListParent(
               (IShellFolder *)(this & -(__int64)(this != 16)),
               a2,
               &GUID_000214e6_0000_0000_c000_000000000046,
               &ppv,
               &ppidlLast);
    if ( Folder >= 0 )
      Folder = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, struct IBindCtx *, struct _GUID *, void **))(*(_QWORD *)ppv + 40LL))(
                 ppv,
                 ppidlLast,
                 a3,
                 a4,
                 a5);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&ppv);
    goto LABEL_51;
  }
  v9 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_000214e6_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_000214e6_0000_0000_c000_000000000046.Data1 )
    v9 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_000214e6_0000_0000_c000_000000000046.Data4;
  if ( !v9 )
    goto LABEL_44;
  v10 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data1 )
    v10 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data4;
  if ( !v10 )
    goto LABEL_44;
  v11 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_72dbece7_d912_4a8f_841c_a521b7447463.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_72dbece7_d912_4a8f_841c_a521b7447463.Data1 )
    v11 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_72dbece7_d912_4a8f_841c_a521b7447463.Data4;
  if ( !v11 )
  {
LABEL_44:
    Folder = CContentDirectoryFolder::_CreateFolder(
               (CContentDirectoryFolder *)(this - 16),
               (const struct _ITEMID_CHILD *)a2,
               a4,
               a5);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)Folder;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_52;
    v16 = 18;
    goto LABEL_30;
  }
  v12 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data1 )
    v12 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data4;
  if ( v12 )
  {
    v17 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_0000000c_0000_0000_c000_000000000046.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_0000000c_0000_0000_c000_000000000046.Data1 )
      v17 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_0000000c_0000_0000_c000_000000000046.Data4;
    if ( v17 )
    {
      v18 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1 )
        v18 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4;
      if ( v18 )
      {
        Folder = -2147467262;
        v19 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_cc254827_4b3d_438f_9232_10c76bc7e038.Data1;
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_cc254827_4b3d_438f_9232_10c76bc7e038.Data1 )
          v19 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_cc254827_4b3d_438f_9232_10c76bc7e038.Data4;
        if ( v19 )
          goto LABEL_51;
      }
    }
    Folder = CContentDirectoryFolder::_GetStreamFromItem(
               (CContentDirectoryFolder *)(this - 16),
               (const struct _ITEMID_CHILD *)a2,
               a4,
               a5);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)Folder;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_52;
    v16 = 20;
LABEL_30:
    WPP_SF_(v15[2], v16, &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids);
LABEL_51:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_52;
  }
  if ( a3
    && (*(_DWORD *)v23 = 16,
        *(_QWORD *)&v23[4] = 0,
        v24 = 0,
        ((int (__fastcall *)(struct IBindCtx *, _BYTE *))a3->lpVtbl->GetBindOptions)(a3, v23) >= 0)
    && (v23[8] & 3) != 0 )
  {
    Folder = -2147287035;
  }
  else
  {
    ppv = 0;
    ppidlLast = a2;
    *(_QWORD *)v23 = this - 16;
    Folder = Microsoft::WRL::Details::MakeAndInitialize<CDLNAShextPropertyStore,CDLNAShextPropertyStore,CContentDirectoryFolder *,_ITEMID_CHILD const __unaligned *>(
               &ppv,
               v23,
               &ppidlLast);
    v14 = ppv;
    if ( Folder >= 0 )
      Folder = (**(__int64 (__fastcall ***)(void *, struct _GUID *, void **))ppv)(ppv, a4, a5);
    if ( v14 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
LABEL_52:
      if ( v15 != &WPP_GLOBAL_Control
        && (*((_BYTE *)v15 + 28) & 2) != 0
        && *((unsigned __int8 *)v15 + 25) >= ((Folder >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(v15[2], 21, &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids, (unsigned int)Folder);
      }
      return (unsigned int)Folder;
    }
    v16 = 19;
    goto LABEL_30;
  }
  return (unsigned int)Folder;
}

```

## disassembly

```asm
0x180010030  push    rbp
0x180010032  push    rbx
0x180010033  push    rsi
0x180010034  push    rdi
0x180010035  push    r13
0x180010037  push    r14
0x180010039  push    r15
0x18001003b  mov     rbp, rsp
0x18001003e  sub     rsp, 70h
0x180010042  mov     rax, cs:__security_cookie
0x180010049  xor     rax, rsp
0x18001004c  mov     [rbp+var_10], rax
0x180010050  mov     rbx, r9
0x180010053  mov     rsi, r8
0x180010056  mov     r14, rdx
0x180010059  mov     r13, rcx
0x18001005c  mov     r15, [rbp+arg_20]
0x180010060  lea     rax, WPP_GLOBAL_Control
0x180010067  mov     rcx, cs:WPP_GLOBAL_Control
0x18001006e  cmp     rcx, rax
0x180010071  jz      short loc_18001009A
0x180010073  test    byte ptr [rcx+1Ch], 2
0x180010077  jz      short loc_18001009A
0x180010079  cmp     byte ptr [rcx+19h], 5
0x18001007d  jb      short loc_18001009A
0x18001007f  mov     [rsp+70h+var_40], r15
0x180010084  mov     [rsp+70h+var_48], rbx
0x180010089  mov     [rsp+70h+ppidlLast], r8
0x18001008e  mov     r9, rdx
0x180010091  mov     rcx, [rcx+10h]
0x180010095  call    WPP_SF_qq_guid_q
0x18001009a  mov     qword ptr [r15], 0
0x1800100a1  mov     rcx, r14; struct _ITEMIDLIST_RELATIVE *
0x1800100a4  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x1800100a9  test    eax, eax
0x1800100ab  jz      loc_1800102FC
0x1800100b1  mov     rax, [rbx]
0x1800100b4  sub     rax, qword ptr cs:_GUID_000214e6_0000_0000_c000_000000000046.Data1
0x1800100bb  jnz     short loc_1800100C8
0x1800100bd  mov     rax, [rbx+8]
0x1800100c1  sub     rax, qword ptr cs:_GUID_000214e6_0000_0000_c000_000000000046.Data4
0x1800100c8  test    rax, rax
0x1800100cb  jz      loc_1800102B1
0x1800100d1  mov     rax, [rbx]
0x1800100d4  sub     rax, qword ptr cs:_GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data1
0x1800100db  jnz     short loc_1800100E8
0x1800100dd  mov     rax, [rbx+8]
0x1800100e1  sub     rax, qword ptr cs:_GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data4
0x1800100e8  test    rax, rax
0x1800100eb  jz      loc_1800102B1
0x1800100f1  mov     rax, [rbx]
0x1800100f4  sub     rax, qword ptr cs:_GUID_72dbece7_d912_4a8f_841c_a521b7447463.Data1
0x1800100fb  jnz     short loc_180010108
0x1800100fd  mov     rax, [rbx+8]
0x180010101  sub     rax, qword ptr cs:_GUID_72dbece7_d912_4a8f_841c_a521b7447463.Data4
0x180010108  test    rax, rax
0x18001010b  jz      loc_1800102B1
0x180010111  mov     rax, [rbx]
0x180010114  sub     rax, qword ptr cs:_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data1
0x18001011b  jnz     short loc_180010128
0x18001011d  mov     rax, [rbx+8]
0x180010121  sub     rax, qword ptr cs:_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99.Data4
0x180010128  test    rax, rax
0x18001012b  jnz     loc_180010209
0x180010131  test    rsi, rsi
0x180010134  jz      short loc_180010168
0x180010136  mov     dword ptr [rbp+var_20], 10h
0x18001013d  mov     qword ptr [rbp+var_20+4], rax
0x180010141  mov     [rbp+var_14], eax
0x180010144  mov     rax, [rsi]
0x180010147  lea     rdx, [rbp+var_20]
0x18001014b  mov     rcx, rsi
0x18001014e  mov     rax, [rax+38h]
0x180010152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010157  test    eax, eax
0x180010159  js      short loc_180010168
0x18001015b  test    [rbp+var_20+8], 3
0x18001015f  jz      short loc_180010168
0x180010161  mov     edi, 80030005h
0x180010166  jmp     short loc_1800101C2
0x180010168  mov     [rbp+ppv], 0
0x180010170  mov     [rbp+var_28], r14
0x180010174  lea     rax, [r13-10h]
0x180010178  mov     qword ptr [rbp+var_20], rax
0x18001017c  lea     r8, [rbp+var_28]
0x180010180  lea     rdx, [rbp+var_20]
0x180010184  lea     rcx, [rbp+ppv]
0x180010188  call    ??$MakeAndInitialize@VCDLNAShextPropertyStore@@V1@PEAVCContentDirectoryFolder@@PEFBU_ITEMID_CHILD@@@Details@WRL@Microsoft@@YAJPEAPEAVCDLNAShextPropertyStore@@$$QEAPEAVCContentDirectoryFolder@@$$QEAPEFBU_ITEMID_CHILD@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CDLNAShextPropertyStore,CDLNAShextPropertyStore,CContentDirectoryFolder *,_ITEMID_CHILD const *>(CDLNAShextPropertyStore * *,CContentDirectoryFolder * &&,_ITEMID_CHILD const * &&)
0x18001018d  mov     edi, eax
0x18001018f  mov     rsi, [rbp+ppv]
0x180010193  test    eax, eax
0x180010195  js      short loc_1800101AD
0x180010197  mov     rax, [rsi]
0x18001019a  mov     r8, r15
0x18001019d  mov     rdx, rbx
0x1800101a0  mov     rcx, rsi
0x1800101a3  mov     rax, [rax]
0x1800101a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101ab  mov     edi, eax
0x1800101ad  test    rsi, rsi
0x1800101b0  jz      short loc_1800101C2
0x1800101b2  mov     rax, [rsi]
0x1800101b5  mov     rcx, rsi
0x1800101b8  mov     rax, [rax+10h]
0x1800101bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c1  nop
0x1800101c2  mov     r10, cs:WPP_GLOBAL_Control
0x1800101c9  lea     rbx, WPP_GLOBAL_Control
0x1800101d0  cmp     r10, rbx
0x1800101d3  jz      loc_1800103B5
0x1800101d9  test    byte ptr [r10+1Ch], 40h
0x1800101de  jz      loc_18001037D
0x1800101e4  cmp     byte ptr [r10+19h], 4
0x1800101e9  jb      loc_18001037D
0x1800101ef  mov     edx, 13h
0x1800101f4  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x1800101fb  mov     rcx, [r10+10h]
0x1800101ff  call    WPP_SF_
0x180010204  jmp     loc_180010376
0x180010209  mov     rax, [rbx]
0x18001020c  sub     rax, qword ptr cs:_GUID_0000000c_0000_0000_c000_000000000046.Data1
0x180010213  jnz     short loc_180010220
0x180010215  mov     rax, [rbx+8]
0x180010219  sub     rax, qword ptr cs:_GUID_0000000c_0000_0000_c000_000000000046.Data4
0x180010220  test    rax, rax
0x180010223  jz      short loc_180010266
0x180010225  mov     rax, [rbx]
0x180010228  sub     rax, qword ptr cs:_GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1
0x18001022f  jnz     short loc_18001023C
0x180010231  mov     rax, [rbx+8]
0x180010235  sub     rax, qword ptr cs:_GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4
0x18001023c  test    rax, rax
0x18001023f  jz      short loc_180010266
0x180010241  mov     edi, 80004002h
0x180010246  mov     rax, [rbx]
0x180010249  sub     rax, qword ptr cs:_GUID_cc254827_4b3d_438f_9232_10c76bc7e038.Data1
0x180010250  jnz     short loc_18001025D
0x180010252  mov     rax, [rbx+8]
0x180010256  sub     rax, qword ptr cs:_GUID_cc254827_4b3d_438f_9232_10c76bc7e038.Data4
0x18001025d  test    rax, rax
0x180010260  jnz     loc_18001036F
0x180010266  lea     rcx, [r13-10h]; this
0x18001026a  mov     r9, r15; void **
0x18001026d  mov     r8, rbx; riid
0x180010270  mov     rdx, r14; struct _ITEMID_CHILD *
0x180010273  call    ?_GetStreamFromItem@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CContentDirectoryFolder::_GetStreamFromItem(_ITEMID_CHILD const *,_GUID const &,void * *)
0x180010278  mov     edi, eax
0x18001027a  mov     r10, cs:WPP_GLOBAL_Control
0x180010281  lea     rbx, WPP_GLOBAL_Control
0x180010288  cmp     r10, rbx
0x18001028b  jz      loc_1800103B5
0x180010291  test    byte ptr [r10+1Ch], 40h
0x180010296  jz      loc_18001037D
0x18001029c  cmp     byte ptr [r10+19h], 4
0x1800102a1  jb      loc_18001037D
0x1800102a7  mov     edx, 14h
0x1800102ac  jmp     loc_1800101F4
0x1800102b1  lea     rcx, [r13-10h]; this
0x1800102b5  mov     r9, r15; void **
0x1800102b8  mov     r8, rbx; struct _GUID *
0x1800102bb  mov     rdx, r14; struct _ITEMID_CHILD *
0x1800102be  call    ?_CreateFolder@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CContentDirectoryFolder::_CreateFolder(_ITEMID_CHILD const *,_GUID const &,void * *)
0x1800102c3  mov     edi, eax
0x1800102c5  mov     r10, cs:WPP_GLOBAL_Control
0x1800102cc  lea     rbx, WPP_GLOBAL_Control
0x1800102d3  cmp     r10, rbx
0x1800102d6  jz      loc_1800103B5
0x1800102dc  test    byte ptr [r10+1Ch], 40h
0x1800102e1  jz      loc_18001037D
0x1800102e7  cmp     byte ptr [r10+19h], 4
0x1800102ec  jb      loc_18001037D
0x1800102f2  mov     edx, 12h
0x1800102f7  jmp     loc_1800101F4
0x1800102fc  mov     [rbp+ppv], 0
0x180010304  mov     [rbp+var_28], 0
0x18001030c  lea     rcx, [rbp+ppv]
0x180010310  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010315  lea     rax, [r13-10h]
0x180010319  neg     rax
0x18001031c  sbb     rcx, rcx
0x18001031f  and     rcx, r13; psfRoot
0x180010322  lea     rax, [rbp+var_28]
0x180010326  mov     [rsp+70h+ppidlLast], rax; ppidlLast
0x18001032b  lea     r9, [rbp+ppv]; ppv
0x18001032f  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180010336  mov     rdx, r14; pidl
0x180010339  call    cs:__imp_SHBindToFolderIDListParent
0x18001033f  mov     edi, eax
0x180010341  test    eax, eax
0x180010343  js      short loc_180010366
0x180010345  mov     rcx, [rbp+ppv]
0x180010349  mov     rax, [rcx]
0x18001034c  mov     [rsp+70h+ppidlLast], r15
0x180010351  mov     r9, rbx
0x180010354  mov     r8, rsi
0x180010357  mov     rdx, [rbp+var_28]
0x18001035b  mov     rax, [rax+28h]
0x18001035f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010364  mov     edi, eax
0x180010366  lea     rcx, [rbp+ppv]
0x18001036a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001036f  lea     rbx, WPP_GLOBAL_Control
0x180010376  mov     r10, cs:WPP_GLOBAL_Control
0x18001037d  cmp     r10, rbx
0x180010380  jz      short loc_1800103B5
0x180010382  test    byte ptr [r10+1Ch], 2
0x180010387  jz      short loc_1800103B5
0x180010389  mov     ecx, edi
0x18001038b  sar     ecx, 1Fh
0x18001038e  and     ecx, 0FFFFFFFDh
0x180010391  add     ecx, 5
0x180010394  movzx   eax, byte ptr [r10+19h]
0x180010399  cmp     eax, ecx
0x18001039b  jb      short loc_1800103B5
0x18001039d  mov     edx, 15h
0x1800103a2  mov     r9d, edi
0x1800103a5  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x1800103ac  mov     rcx, [r10+10h]
0x1800103b0  call    WPP_SF_d
0x1800103b5  mov     eax, edi
0x1800103b7  mov     rcx, [rbp+var_10]
0x1800103bb  xor     rcx, rsp; StackCookie
0x1800103be  call    __security_check_cookie
0x1800103c3  add     rsp, 70h
0x1800103c7  pop     r15
0x1800103c9  pop     r14
0x1800103cb  pop     r13
0x1800103cd  pop     rdi
0x1800103ce  pop     rsi
0x1800103cf  pop     rbx
0x1800103d0  pop     rbp
0x1800103d1  retn
```
