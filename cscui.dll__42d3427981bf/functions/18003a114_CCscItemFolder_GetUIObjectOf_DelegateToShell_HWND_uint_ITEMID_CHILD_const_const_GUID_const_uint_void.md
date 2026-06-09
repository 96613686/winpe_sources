# CCscItemFolder::_GetUIObjectOf_DelegateToShell(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x18003a114`
- end: `0x18003a2da`
- name: `?_GetUIObjectOf_DelegateToShell@CCscItemFolder@@AEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `454`
- prototype: `__int64 __usercall@<rax>(CCscItemFolder *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, const struct _ITEMID_CHILD *const *@<r9>, const struct _GUID *, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008db0`
- `0x18003a2e0`

## callees

- `0x18001101c`
- `0x180013dfc`
- `0x180032e80`
- `0x18003833c`
- `0x180038934`
- `0x180039088`
- `0x18003a114`
- `0x18003a3e0`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18003a286`
- `SHELL32!__imp_ILFree` at `0x18003a286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a261`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a261`

## pseudocode

```c
__int64 __fastcall CCscItemFolder::_GetUIObjectOf_DelegateToShell(
        CCscItemFolder *this,
        HWND a2,
        unsigned int a3,
        const struct _ITEMID_CHILD *const *a4,
        const struct _GUID *a5,
        unsigned int *a6,
        struct _ITEMID_CHILD **a7)
{
  struct _ITEMID_CHILD **v7; // r15
  int v12; // ebx
  unsigned __int16 *v13; // rax
  __int64 v14; // rcx
  const struct _ITEMID_CHILD *v15; // rdx
  const struct _GUID *v16; // rsi
  void *v17; // rcx
  unsigned int v18; // eax
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-20h] BYREF
  struct _ITEMID_CHILD *v21; // [rsp+48h] [rbp-18h] BYREF
  const struct _GUID *v22; // [rsp+50h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-8h]
  void *v24; // [rsp+A8h] [rbp+48h] BYREF

  v7 = a7;
  v12 = -2147024809;
  *a7 = 0;
  v13 = CItemIDFactory<tagCSCITEMDATA,86514056>::_IsValid(*(unsigned __int16 **)a4);
  v15 = (const struct _ITEMID_CHILD *)(v14
                                     & -(__int64)(((unsigned __int64)(v13 + 7)
                                                 & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64)) != 0));
  if ( v15 )
  {
    v24 = 0;
    pidl = 0;
    v21 = 0;
    v12 = CCscItemFolder::_BindToShellItemParent(
            this,
            v15,
            &GUID_000214e6_0000_0000_c000_000000000046,
            &v24,
            (struct _ITEMIDLIST_ABSOLUTE **)&pidl,
            &v21);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids,
          (unsigned int)v12);
      }
    }
    else
    {
      a7 = 0;
      v12 = CCscItemFolder::_CreateFsIDs(this, a3, a4, &a7);
      if ( v12 >= 0 )
      {
        v16 = a5;
        v12 = (*(__int64 (__fastcall **)(void *, HWND, _QWORD, struct _ITEMID_CHILD **, const struct _GUID *, unsigned int *, struct _ITEMID_CHILD **))(*(_QWORD *)v24 + 80LL))(
                v24,
                a2,
                a3,
                a7,
                a5,
                a6,
                v7);
        if ( v12 < 0 )
        {
          v17 = 0;
          v22 = v16;
          pv = 0;
          if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v18 = (unsigned int)CStringIID::Text((CStringIID *)&v22);
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              (unsigned int)WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids,
              v18,
              v12);
            v17 = pv;
          }
          CoTaskMemFree(v17);
        }
        CscDestroyItemIDArray(a3, a7);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
      ILFree(pidl);
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003a114  mov     [rsp-28h+arg_0], rbx
0x18003a119  mov     [rsp-28h+arg_8], rsi
0x18003a11e  push    rbp
0x18003a11f  push    rdi
0x18003a120  push    r12
0x18003a122  push    r14
0x18003a124  push    r15
0x18003a126  mov     rbp, rsp
0x18003a129  sub     rsp, 60h
0x18003a12d  mov     r15, [rbp+arg_30]
0x18003a131  mov     rsi, rcx
0x18003a134  mov     r14, r9
0x18003a137  mov     edi, r8d
0x18003a13a  mov     r12, rdx
0x18003a13d  mov     ebx, 80070057h
0x18003a142  mov     qword ptr [r15], 0
0x18003a149  mov     rcx, [r9]
0x18003a14c  call    ?_IsValid@?$CItemIDFactory@UtagCSCITEMDATA@@$0FCIBJII@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<tagCSCITEMDATA,86514056>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x18003a151  lea     r9, [rax+0Eh]
0x18003a155  neg     rax
0x18003a158  sbb     rdx, rdx
0x18003a15b  and     rdx, r9
0x18003a15e  neg     rdx
0x18003a161  sbb     rdx, rdx
0x18003a164  and     rdx, rcx; struct _ITEMID_CHILD *
0x18003a167  jz      loc_18003A2BF
0x18003a16d  lea     rax, [rbp+var_18]
0x18003a171  mov     [rbp+arg_18], 0
0x18003a179  mov     [rsp+60h+var_38], rax; struct _ITEMID_CHILD **
0x18003a17e  lea     r9, [rbp+arg_18]; void **
0x18003a182  lea     rax, [rbp+pidl]
0x18003a186  mov     [rbp+pidl], 0
0x18003a18e  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; struct _GUID *
0x18003a195  mov     [rsp+60h+var_40], rax; struct _ITEMIDLIST_ABSOLUTE **
0x18003a19a  mov     rcx, rsi; this
0x18003a19d  mov     [rbp+var_18], 0
0x18003a1a5  call    ?_BindToShellItemParent@CCscItemFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAXPEAPEAU_ITEMIDLIST_ABSOLUTE@@PEAPEFBU2@@Z; CCscItemFolder::_BindToShellItemParent(_ITEMID_CHILD const *,_GUID const &,void * *,_ITEMIDLIST_ABSOLUTE * *,_ITEMID_CHILD const * *)
0x18003a1aa  mov     ebx, eax
0x18003a1ac  test    eax, eax
0x18003a1ae  js      loc_18003A28E
0x18003a1b4  lea     r9, [rbp+arg_30]; struct _ITEMID_CHILD ***
0x18003a1b8  mov     [rbp+arg_30], 0
0x18003a1c0  mov     r8, r14; struct _ITEMID_CHILD **
0x18003a1c3  mov     edx, edi; unsigned int
0x18003a1c5  mov     rcx, rsi; this
0x18003a1c8  call    ?_CreateFsIDs@CCscItemFolder@@AEAAJIPEBQEFBU_ITEMID_CHILD@@PEAPEAPEAU2@@Z; CCscItemFolder::_CreateFsIDs(uint,_ITEMID_CHILD const * const *,_ITEMID_CHILD * * *)
0x18003a1cd  mov     ebx, eax
0x18003a1cf  test    eax, eax
0x18003a1d1  js      loc_18003A272
0x18003a1d7  mov     rcx, [rbp+arg_18]
0x18003a1db  mov     r8d, edi
0x18003a1de  mov     rdx, [rbp+arg_28]
0x18003a1e2  mov     rsi, [rbp+arg_20]
0x18003a1e6  mov     r9, [rbp+arg_30]
0x18003a1ea  mov     rax, [rcx]
0x18003a1ed  mov     [rsp+60h+var_30], r15
0x18003a1f2  mov     [rsp+60h+var_38], rdx
0x18003a1f7  mov     rdx, r12
0x18003a1fa  mov     [rsp+60h+var_40], rsi
0x18003a1ff  mov     rax, [rax+50h]
0x18003a203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a208  mov     ebx, eax
0x18003a20a  test    eax, eax
0x18003a20c  jns     short loc_18003A267
0x18003a20e  xor     ecx, ecx
0x18003a210  mov     [rbp+var_10], rsi
0x18003a214  mov     [rbp+pv], rcx
0x18003a218  mov     rdx, cs:WPP_GLOBAL_Control
0x18003a21f  lea     rax, WPP_GLOBAL_Control
0x18003a226  cmp     rdx, rax
0x18003a229  jz      short loc_18003A261
0x18003a22b  test    byte ptr [rdx+1Ch], 2
0x18003a22f  jz      short loc_18003A261
0x18003a231  lea     rcx, [rbp+var_10]; this
0x18003a235  call    ?Text@CStringIID@@QEAAPEBGXZ; CStringIID::Text(void)
0x18003a23a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a241  lea     r8, WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids
0x18003a248  mov     edx, 31h ; '1'
0x18003a24d  mov     dword ptr [rsp+60h+var_40], ebx
0x18003a251  mov     r9, rax
0x18003a254  mov     rcx, [rcx+10h]
0x18003a258  call    WPP_SF_Sd
0x18003a25d  mov     rcx, [rbp+pv]; pv
0x18003a261  call    cs:__imp_CoTaskMemFree
0x18003a267  mov     rdx, [rbp+arg_30]; struct _ITEMID_CHILD **
0x18003a26b  mov     ecx, edi; unsigned int
0x18003a26d  call    ?CscDestroyItemIDArray@@YAXIPEAPEAU_ITEMID_CHILD@@@Z; CscDestroyItemIDArray(uint,_ITEMID_CHILD * *)
0x18003a272  mov     rcx, [rbp+arg_18]
0x18003a276  mov     rax, [rcx]
0x18003a279  mov     rax, [rax+10h]
0x18003a27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a282  mov     rcx, [rbp+pidl]; pidl
0x18003a286  call    cs:__imp_ILFree
0x18003a28c  jmp     short loc_18003A2BF
0x18003a28e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a295  lea     rax, WPP_GLOBAL_Control
0x18003a29c  cmp     rcx, rax
0x18003a29f  jz      short loc_18003A2BF
0x18003a2a1  test    byte ptr [rcx+1Ch], 2
0x18003a2a5  jz      short loc_18003A2BF
0x18003a2a7  mov     rcx, [rcx+10h]
0x18003a2ab  lea     r8, WPP_5fe987ea1b1f3d929bb98d819c20dc91_Traceguids
0x18003a2b2  mov     edx, 32h ; '2'
0x18003a2b7  mov     r9d, ebx
0x18003a2ba  call    WPP_SF_d
0x18003a2bf  lea     r11, [rsp+60h+var_s0]
0x18003a2c4  mov     eax, ebx
0x18003a2c6  mov     rbx, [r11+30h]
0x18003a2ca  mov     rsi, [r11+38h]
0x18003a2ce  mov     rsp, r11
0x18003a2d1  pop     r15
0x18003a2d3  pop     r14
0x18003a2d5  pop     r12
0x18003a2d7  pop     rdi
0x18003a2d8  pop     rbp
0x18003a2d9  retn
```
