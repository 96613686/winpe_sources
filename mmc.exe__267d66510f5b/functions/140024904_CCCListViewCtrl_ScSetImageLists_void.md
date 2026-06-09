# CCCListViewCtrl::ScSetImageLists(void)

- ea: `0x140024904`
- end: `0x140024c52`
- name: `?ScSetImageLists@CCCListViewCtrl@@AEAA?AVSC@mmcerror@@XZ`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140024590`
- `0x14009fefc`

## callees

- `0x140024904`
- `0x1400253a4`
- `0x140025400`
- `0x1400576fc`
- `0x1400598b4`
- `0x1400f3010`

## import_xrefs

- `USER32!SendMessageW` at `0x140024980`
- `USER32!SendMessageW` at `0x140024c13`
- `USER32!SendMessageW` at `0x140024c46`
- `USER32!SendMessageW` at `0x140024980`
- `USER32!SendMessageW` at `0x140024c13`
- `USER32!SendMessageW` at `0x140024c46`
- `MFC42u!__imp_?Create@CImageList@@QEAAHHHIHH@Z` at `0x1400249c5`
- `MFC42u!__imp_?Create@CImageList@@QEAAHHHIHH@Z` at `0x1400249f9`
- `MFC42u!__imp_?Create@CImageList@@QEAAHHHIHH@Z` at `0x1400249c5`
- `MFC42u!__imp_?Create@CImageList@@QEAAHHHIHH@Z` at `0x1400249f9`
- `MFC42u!__imp_?DeleteImageList@CImageList@@QEAAHXZ` at `0x140024b83`
- `MFC42u!__imp_?DeleteImageList@CImageList@@QEAAHXZ` at `0x140024b90`
- `MFC42u!__imp_?DeleteImageList@CImageList@@QEAAHXZ` at `0x140024b83`
- `MFC42u!__imp_?DeleteImageList@CImageList@@QEAAHXZ` at `0x140024b90`
- `MFC42u!__imp_?FromHandle@CImageList@@SAPEAV1@PEAU_IMAGELIST@@@Z` at `0x140024989`
- `MFC42u!__imp_?FromHandle@CImageList@@SAPEAV1@PEAU_IMAGELIST@@@Z` at `0x140024c1c`
- `MFC42u!__imp_?FromHandle@CImageList@@SAPEAV1@PEAU_IMAGELIST@@@Z` at `0x140024989`
- `MFC42u!__imp_?FromHandle@CImageList@@SAPEAV1@PEAU_IMAGELIST@@@Z` at `0x140024c1c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140024a8f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140024a8f`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14002492c`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14002492c`
- `mmcbase!LoadStandardOverlays` at `0x140024abf`
- `mmcbase!LoadStandardOverlays` at `0x140024b11`
- `mmcbase!LoadStandardOverlays` at `0x140024abf`
- `mmcbase!LoadStandardOverlays` at `0x140024b11`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140024b99`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140024baf`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140024b99`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x140024baf`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140024ad3`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140024b25`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140024ad3`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x140024b25`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140024ba6`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140024ba6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024a86`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024aca`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024b1c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024bc1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024a86`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024aca`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024b1c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140024bc1`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140024944`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140024944`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
mmcerror::SC *__fastcall CCCListViewCtrl::ScSetImageLists(__int64 a1, mmcerror::SC *a2)
{
  __int64 v4; // r15
  __int64 v5; // r14
  LPARAM v6; // r9
  struct _IMAGELIST *v7; // rax
  LPARAM v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  struct _IMAGELIST *v16; // rax
  struct CAMCHeaderCtrl *HeaderCtrl; // rax
  void **v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h]
  void **v20; // [rsp+50h] [rbp-10h] BYREF
  __int64 v21; // [rsp+58h] [rbp-8h]
  int v22; // [rsp+A0h] [rbp+40h] BYREF
  mmcerror::SC *v23; // [rsp+A8h] [rbp+48h]
  int v24; // [rsp+B0h] [rbp+50h] BYREF
  int v25; // [rsp+B8h] [rbp+58h]

  v23 = a2;
  v25 = 1;
  mmcerror::SC::SC(a2, 0);
  v25 = 1;
  mmcerror::SC::SetFunctionName(a2, L"CCCListViewCtrl::ScSetImageLists");
  v4 = *(_QWORD *)(a1 + 128);
  if ( a1 != -232 && *(_QWORD *)(a1 + 240) )
  {
    v5 = a1 + 248;
    goto LABEL_4;
  }
  if ( CImageList::Create((CImageList *)(a1 + 232), 16, 16, 0x21u, 20, 10) )
  {
    v5 = a1 + 248;
    if ( CImageList::Create((CImageList *)(a1 + 248), 32, 32, 0x21u, 20, 10) )
    {
      v21 = 0;
      v20 = &CBitmap::`vftable';
      v19 = 0;
      v18 = &CBitmap::`vftable';
      if ( !LoadResourceToCBitmap((struct CBitmap *)&v20, 0x9Eu) )
        goto LABEL_21;
      if ( !LoadResourceToCBitmap((struct CBitmap *)&v18, 0x9Fu) )
        goto LABEL_21;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, _DWORD, _DWORD))(*(_QWORD *)a1 + 176LL))(
             a1,
             60102025,
             v21,
             v19,
             0,
             0);
      mmcerror::SC::operator=(a2, v9);
      if ( (unsigned __int8)mmcerror::SC::operator bool(a2) )
        goto LABEL_21;
      v24 = 0;
      v22 = 0;
      v10 = LoadStandardOverlays(*(struct _IMAGELIST **)(a1 + 240), 16, &v24, &v22);
      mmcerror::SC::operator=(a2, v10);
      v11 = mmcerror::SC::ToHr(a2);
      if ( v11 >= 0 )
      {
        v14 = LoadStandardOverlays(*(struct _IMAGELIST **)(a1 + 256), 32, &v24, &v22);
        mmcerror::SC::operator=(a2, v14);
        v11 = mmcerror::SC::ToHr(a2);
        if ( v11 >= 0 )
        {
          v18 = &CBitmap::`vftable';
          CGdiObject::~CGdiObject((CGdiObject *)&v18);
          v20 = &CBitmap::`vftable';
          CGdiObject::~CGdiObject((CGdiObject *)&v20);
          if ( a1 == -232 )
          {
            v6 = 0;
            goto LABEL_5;
          }
LABEL_4:
          v6 = *(_QWORD *)(a1 + 240);
LABEL_5:
          v7 = (struct _IMAGELIST *)SendMessageW(*(HWND *)(v4 + 64), 0x1003u, 1u, v6);
          CImageList::FromHandle(v7);
          if ( v5 )
            v8 = *(_QWORD *)(v5 + 8);
          else
            v8 = 0;
          v16 = (struct _IMAGELIST *)SendMessageW(*(HWND *)(v4 + 64), 0x1003u, 0, v8);
          CImageList::FromHandle(v16);
          HeaderCtrl = CAMCListView::GetHeaderCtrl(*(CAMCListView **)(a1 + 128));
          if ( HeaderCtrl )
            SendMessageW(*((HWND *)HeaderCtrl + 8), 0x1208u, 0, *(_QWORD *)(a1 + 312));
          return a2;
        }
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
          goto LABEL_21;
        v13 = 33;
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
          goto LABEL_21;
        v13 = 32;
      }
      WPP_SF_d(*(_QWORD *)(v12 + 16), v13, WPP_bf2b9f813cf4358b795ac1814230b624_Traceguids, (unsigned int)v11);
LABEL_21:
      v18 = &CBitmap::`vftable';
      CGdiObject::~CGdiObject((CGdiObject *)&v18);
      v20 = &CBitmap::`vftable';
      CGdiObject::~CGdiObject((CGdiObject *)&v20);
    }
  }
  CImageList::DeleteImageList((CImageList *)(a1 + 232));
  CImageList::DeleteImageList((CImageList *)(a1 + 248));
  if ( !mmcerror::SC::IsError(a2) )
  {
    mmcerror::SC::FromLastError(a2);
    if ( !mmcerror::SC::IsError(a2) )
      mmcerror::SC::operator=(a2, 2147500037LL);
  }
  return a2;
}

```

## disassembly

```asm
0x140024904  mov     [rsp-38h+arg_8], rdx
0x140024909  push    rbp
0x14002490a  push    rbx
0x14002490b  push    rsi
0x14002490c  push    rdi
0x14002490d  push    r13
0x14002490f  push    r14
0x140024911  push    r15
0x140024913  mov     rbp, rsp
0x140024916  sub     rsp, 60h
0x14002491a  mov     rbx, rdx
0x14002491d  mov     rdi, rcx
0x140024920  mov     [rbp+arg_18], 1
0x140024927  xor     edx, edx
0x140024929  mov     rcx, rbx
0x14002492c  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140024932  nop
0x140024933  mov     [rbp+arg_18], 1
0x14002493a  lea     rdx, aCcclistviewctr_11; "CCCListViewCtrl::ScSetImageLists"
0x140024941  mov     rcx, rbx
0x140024944  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14002494a  mov     r15, [rdi+80h]
0x140024951  lea     rsi, [rdi+0E8h]
0x140024958  test    rsi, rsi
0x14002495b  jz      short loc_1400249A0
0x14002495d  cmp     qword ptr [rsi+8], 0
0x140024962  jz      short loc_1400249A0
0x140024964  lea     r14, [rdi+0F8h]
0x14002496b  mov     r9, [rsi+8]; lParam
0x14002496f  mov     esi, 1003h
0x140024974  mov     r8d, 1; wParam
0x14002497a  mov     edx, esi; Msg
0x14002497c  mov     rcx, [r15+40h]; hWnd
0x140024980  call    cs:__imp_SendMessageW
0x140024986  mov     rcx, rax
0x140024989  call    cs:__imp_?FromHandle@CImageList@@SAPEAV1@PEAU_IMAGELIST@@@Z; CImageList::FromHandle(_IMAGELIST *)
0x14002498f  test    r14, r14
0x140024992  jnz     loc_140024C06
0x140024998  xor     r9d, r9d
0x14002499b  jmp     loc_140024C0A
0x1400249a0  mov     [rsp+60h+var_38], 0Ah
0x1400249a8  mov     [rsp+60h+var_40], 14h
0x1400249b0  mov     r13d, 21h ; '!'
0x1400249b6  mov     r9d, r13d
0x1400249b9  lea     eax, [r13-11h]
0x1400249bd  mov     r8d, eax
0x1400249c0  mov     edx, eax
0x1400249c2  mov     rcx, rsi
0x1400249c5  call    cs:__imp_?Create@CImageList@@QEAAHHHIHH@Z; CImageList::Create(int,int,uint,int,int)
0x1400249cb  test    eax, eax
0x1400249cd  jz      loc_140024B80
0x1400249d3  lea     r14, [rdi+0F8h]
0x1400249da  mov     [rsp+60h+var_38], 0Ah
0x1400249e2  mov     [rsp+60h+var_40], 14h
0x1400249ea  mov     r9d, r13d
0x1400249ed  lea     eax, [r13-1]
0x1400249f1  mov     r8d, eax
0x1400249f4  mov     edx, eax
0x1400249f6  mov     rcx, r14
0x1400249f9  call    cs:__imp_?Create@CImageList@@QEAAHHHIHH@Z; CImageList::Create(int,int,uint,int,int)
0x1400249ff  test    eax, eax
0x140024a01  jz      loc_140024B80
0x140024a07  mov     [rbp+var_8], 0
0x140024a0f  lea     r13, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x140024a16  mov     [rbp+var_10], r13
0x140024a1a  mov     [rbp+var_18], 0
0x140024a22  mov     [rbp+var_20], r13
0x140024a26  mov     edx, 9Eh; unsigned int
0x140024a2b  lea     rcx, [rbp+var_10]; struct CBitmap *
0x140024a2f  call    ?LoadResourceToCBitmap@@YA_NAEAVCBitmap@@I@Z; LoadResourceToCBitmap(CBitmap &,uint)
0x140024a34  test    al, al
0x140024a36  jz      loc_140024B65
0x140024a3c  mov     edx, 9Fh; unsigned int
0x140024a41  lea     rcx, [rbp+var_20]; struct CBitmap *
0x140024a45  call    ?LoadResourceToCBitmap@@YA_NAEAVCBitmap@@I@Z; LoadResourceToCBitmap(CBitmap &,uint)
0x140024a4a  test    al, al
0x140024a4c  jz      loc_140024B65
0x140024a52  mov     rax, [rdi]
0x140024a55  mov     [rsp+60h+var_38], 0
0x140024a5d  mov     [rsp+60h+var_40], 0
0x140024a65  mov     r9, [rbp+var_18]
0x140024a69  mov     r8, [rbp+var_8]
0x140024a6d  mov     edx, 3951589h
0x140024a72  mov     rcx, rdi
0x140024a75  mov     rax, [rax+0B0h]
0x140024a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024a81  mov     edx, eax
0x140024a83  mov     rcx, rbx
0x140024a86  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140024a8c  mov     rcx, rbx
0x140024a8f  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140024a95  test    al, al
0x140024a97  jnz     loc_140024B65
0x140024a9d  mov     [rbp+arg_10], 0
0x140024aa4  mov     [rbp+arg_0], 0
0x140024aab  lea     r9, [rbp+arg_0]
0x140024aaf  lea     r8, [rbp+arg_10]
0x140024ab3  mov     edx, 10h
0x140024ab8  mov     rcx, [rdi+0F0h]
0x140024abf  call    cs:__imp_?LoadStandardOverlays@@YAJPEAU_IMAGELIST@@HPEAH1@Z; LoadStandardOverlays(_IMAGELIST *,int,int *,int *)
0x140024ac5  mov     edx, eax
0x140024ac7  mov     rcx, rbx
0x140024aca  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140024ad0  mov     rcx, rbx
0x140024ad3  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x140024ad9  test    eax, eax
0x140024adb  jns     short loc_140024AFD
0x140024add  lea     r8, WPP_GLOBAL_Control
0x140024ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x140024aeb  cmp     rcx, r8
0x140024aee  jz      short loc_140024B65
0x140024af0  cmp     byte ptr [rcx+19h], 2
0x140024af4  jb      short loc_140024B65
0x140024af6  mov     edx, 20h ; ' '
0x140024afb  jmp     short loc_140024B51
0x140024afd  lea     r9, [rbp+arg_0]
0x140024b01  lea     r8, [rbp+arg_10]
0x140024b05  mov     edx, 20h ; ' '
0x140024b0a  mov     rcx, [rdi+100h]
0x140024b11  call    cs:__imp_?LoadStandardOverlays@@YAJPEAU_IMAGELIST@@HPEAH1@Z; LoadStandardOverlays(_IMAGELIST *,int,int *,int *)
0x140024b17  mov     edx, eax
0x140024b19  mov     rcx, rbx
0x140024b1c  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140024b22  mov     rcx, rbx
0x140024b25  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x140024b2b  test    eax, eax
0x140024b2d  jns     loc_140024BDA
0x140024b33  lea     r8, WPP_GLOBAL_Control
0x140024b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b41  cmp     rcx, r8
0x140024b44  jz      short loc_140024B65
0x140024b46  cmp     byte ptr [rcx+19h], 2
0x140024b4a  jb      short loc_140024B65
0x140024b4c  mov     edx, 21h ; '!'
0x140024b51  mov     r9d, eax
0x140024b54  lea     r8, WPP_bf2b9f813cf4358b795ac1814230b624_Traceguids
0x140024b5b  mov     rcx, [rcx+10h]
0x140024b5f  call    WPP_SF_d
0x140024b64  nop
0x140024b65  mov     [rbp+var_20], r13
0x140024b69  lea     rcx, [rbp+var_20]; this
0x140024b6d  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140024b72  nop
0x140024b73  mov     [rbp+var_10], r13
0x140024b77  lea     rcx, [rbp+var_10]; this
0x140024b7b  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140024b80  mov     rcx, rsi
0x140024b83  call    cs:__imp_?DeleteImageList@CImageList@@QEAAHXZ; CImageList::DeleteImageList(void)
0x140024b89  lea     rcx, [rdi+0F8h]
0x140024b90  call    cs:__imp_?DeleteImageList@CImageList@@QEAAHXZ; CImageList::DeleteImageList(void)
0x140024b96  mov     rcx, rbx
0x140024b99  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x140024b9f  test    al, al
0x140024ba1  jnz     short loc_140024BC8
0x140024ba3  mov     rcx, rbx
0x140024ba6  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x140024bac  mov     rcx, rbx
0x140024baf  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x140024bb5  test    al, al
0x140024bb7  jnz     short loc_140024BC8
0x140024bb9  mov     edx, 80004005h
0x140024bbe  mov     rcx, rbx
0x140024bc1  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140024bc7  nop
0x140024bc8  mov     rax, rbx
0x140024bcb  add     rsp, 60h
0x140024bcf  pop     r15
0x140024bd1  pop     r14
0x140024bd3  pop     r13
0x140024bd5  pop     rdi
0x140024bd6  pop     rsi
0x140024bd7  pop     rbx
0x140024bd8  pop     rbp
0x140024bd9  retn
0x140024bda  mov     [rbp+var_20], r13
0x140024bde  lea     rcx, [rbp+var_20]; this
0x140024be2  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140024be7  nop
0x140024be8  mov     [rbp+var_10], r13
0x140024bec  lea     rcx, [rbp+var_10]; this
0x140024bf0  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x140024bf5  test    rsi, rsi
0x140024bf8  jnz     loc_14002496B
0x140024bfe  xor     r9d, r9d
0x140024c01  jmp     loc_14002496F
0x140024c06  mov     r9, [r14+8]; lParam
0x140024c0a  xor     r8d, r8d; wParam
0x140024c0d  mov     edx, esi; Msg
0x140024c0f  mov     rcx, [r15+40h]; hWnd
0x140024c13  call    cs:__imp_SendMessageW
0x140024c19  mov     rcx, rax
0x140024c1c  call    cs:__imp_?FromHandle@CImageList@@SAPEAV1@PEAU_IMAGELIST@@@Z; CImageList::FromHandle(_IMAGELIST *)
0x140024c22  mov     rcx, [rdi+80h]; this
0x140024c29  call    ?GetHeaderCtrl@CAMCListView@@QEBAPEAVCAMCHeaderCtrl@@XZ; CAMCListView::GetHeaderCtrl(void)
0x140024c2e  test    rax, rax
0x140024c31  jz      short loc_140024BC8
0x140024c33  mov     r9, [rdi+138h]; lParam
0x140024c3a  xor     r8d, r8d; wParam
0x140024c3d  mov     edx, 1208h; Msg
0x140024c42  mov     rcx, [rax+40h]; hWnd
0x140024c46  call    cs:__imp_SendMessageW
0x140024c4c  jmp     loc_140024BC8
```
