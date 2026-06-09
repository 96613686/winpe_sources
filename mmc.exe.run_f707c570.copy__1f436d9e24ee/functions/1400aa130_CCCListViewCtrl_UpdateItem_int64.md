# CCCListViewCtrl::UpdateItem(__int64)

- ea: `0x1400aa130`
- end: `0x1400aa2d6`
- name: `?UpdateItem@CCCListViewCtrl@@UEAAJ_J@Z`
- size: `422`
- prototype: `__int64 __fastcall(CCCListViewCtrl *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1400205f0`
- `0x1400a59ac`
- `0x1400a7344`
- `0x1400aa130`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `USER32!UpdateWindow` at `0x1400aa250`
- `USER32!UpdateWindow` at `0x1400aa250`
- `USER32!InvalidateRect` at `0x1400aa210`
- `USER32!InvalidateRect` at `0x1400aa210`
- `MFC42u!__imp_?GetItemRect@CListCtrl@@QEBAHHPEAUtagRECT@@I@Z` at `0x1400aa1fc`
- `MFC42u!__imp_?GetItemRect@CListCtrl@@QEBAHHPEAUtagRECT@@I@Z` at `0x1400aa1fc`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400aa19d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400aa238`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400aa27e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400aa2b2`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400aa19d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400aa238`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400aa27e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400aa2b2`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400aa1a7`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400aa242`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400aa288`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400aa1a7`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400aa242`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400aa288`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400aa15a`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400aa15a`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400aa2a6`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400aa2a6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400aa29d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400aa29d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400aa193`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400aa22e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400aa274`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400aa193`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400aa22e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400aa274`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400aa16b`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400aa16b`

## string_xrefs

- `0x1400aa160`: `CCCListViewCtrl::UpdateItem`

## pseudocode

```c
__int64 __fastcall CCCListViewCtrl::UpdateItem(CCCListViewCtrl *this, __int64 a2)
{
  __int64 ItemIndexFromHRESULTITEM; // rax
  unsigned int v4; // ebx
  HWND *v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rax
  mmcerror::SC *v8; // rcx
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v12[24]; // [rsp+28h] [rbp-48h] BYREF
  _BYTE v13[24]; // [rsp+40h] [rbp-30h] BYREF
  RECT Rect; // [rsp+58h] [rbp-18h] BYREF

  *(_QWORD *)&Rect.left = a2;
  mmcerror::SC::SC((mmcerror::SC *)v12, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v12, L"CCCListViewCtrl::UpdateItem");
  v11 = -1;
  ItemIndexFromHRESULTITEM = CCCListViewCtrl::ScGetItemIndexFromHRESULTITEM(this, v13, &Rect, &v11);
  mmcerror::SC::operator=(v12, ItemIndexFromHRESULTITEM);
  mmcerror::SC::~SC((mmcerror::SC *)v13);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v12) )
    goto LABEL_8;
  v4 = v11;
  if ( v11 < 0 || v11 >= *((_DWORD *)this + 54) )
  {
    v8 = (mmcerror::SC *)mmcerror::SC::operator=(v12, 2147942487LL);
    goto LABEL_10;
  }
  v5 = (HWND *)*((_QWORD *)this + 16);
  if ( (*(unsigned int (__fastcall **)(CCCListViewCtrl *))(*(_QWORD *)this + 328LL))(this) )
  {
    Rect = 0;
    CListCtrl::GetItemRect((CListCtrl *)v5, v4, &Rect, 0);
    InvalidateRect(v5[8], &Rect, 1);
LABEL_7:
    UpdateWindow(v5[8]);
    v7 = CEventSource<CListViewObserver,CVoid,CVoid,CVoid,CVoid>::ScFireEvent<CListViewObserver,int>(
           (char *)this + 8,
           v13,
            CAMCViewObserver::`vcall'{48,{flat}},
           v4);
    mmcerror::SC::operator=(v12, v7);
    mmcerror::SC::~SC((mmcerror::SC *)v13);
    mmcerror::SC::operator bool(v12);
    goto LABEL_8;
  }
  v6 = CCCListViewCtrl::ScRedrawItem(this, v13, v4);
  mmcerror::SC::operator=(v12, v6);
  mmcerror::SC::~SC((mmcerror::SC *)v13);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v12) )
    goto LABEL_7;
LABEL_8:
  v8 = (mmcerror::SC *)v12;
LABEL_10:
  v9 = mmcerror::SC::ToHr(v8);
  mmcerror::SC::~SC((mmcerror::SC *)v12);
  return v9;
}

```

## disassembly

```asm
0x1400aa130  mov     [rsp-18h+arg_10], rbx
0x1400aa135  push    rbp
0x1400aa136  push    rsi
0x1400aa137  push    rdi
0x1400aa138  mov     rbp, rsp
0x1400aa13b  sub     rsp, 70h
0x1400aa13f  mov     rax, cs:__security_cookie
0x1400aa146  xor     rax, rsp
0x1400aa149  mov     [rbp+var_8], rax
0x1400aa14d  mov     rdi, rcx
0x1400aa150  mov     qword ptr [rbp+Rect.left], rdx
0x1400aa154  xor     edx, edx
0x1400aa156  lea     rcx, [rbp+var_48]
0x1400aa15a  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400aa160  lea     rdx, aCcclistviewctr_28; "CCCListViewCtrl::UpdateItem"
0x1400aa167  lea     rcx, [rbp+var_48]
0x1400aa16b  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400aa171  lea     r9, [rbp+var_50]
0x1400aa175  mov     [rbp+var_50], 0FFFFFFFFh
0x1400aa17c  lea     r8, [rbp+Rect]
0x1400aa180  mov     rcx, rdi
0x1400aa183  lea     rdx, [rbp+var_30]
0x1400aa187  call    ?ScGetItemIndexFromHRESULTITEM@CCCListViewCtrl@@QEAA?AVSC@mmcerror@@AEB_JAEAH@Z; CCCListViewCtrl::ScGetItemIndexFromHRESULTITEM(__int64 const &,int &)
0x1400aa18c  mov     rdx, rax
0x1400aa18f  lea     rcx, [rbp+var_48]
0x1400aa193  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400aa199  lea     rcx, [rbp+var_30]
0x1400aa19d  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400aa1a3  lea     rcx, [rbp+var_48]
0x1400aa1a7  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400aa1ad  test    al, al
0x1400aa1af  jnz     loc_1400AA28E
0x1400aa1b5  mov     ebx, [rbp+var_50]
0x1400aa1b8  test    ebx, ebx
0x1400aa1ba  js      loc_1400AA294
0x1400aa1c0  cmp     ebx, [rdi+0D8h]
0x1400aa1c6  jge     loc_1400AA294
0x1400aa1cc  mov     rax, [rdi]
0x1400aa1cf  mov     rcx, rdi
0x1400aa1d2  mov     rsi, [rdi+80h]
0x1400aa1d9  mov     rax, [rax+148h]
0x1400aa1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aa1e5  test    eax, eax
0x1400aa1e7  jz      short loc_1400AA218
0x1400aa1e9  xorps   xmm0, xmm0
0x1400aa1ec  lea     r8, [rbp+Rect]
0x1400aa1f0  xor     r9d, r9d
0x1400aa1f3  mov     edx, ebx
0x1400aa1f5  mov     rcx, rsi
0x1400aa1f8  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1400aa1fc  call    cs:__imp_?GetItemRect@CListCtrl@@QEBAHHPEAUtagRECT@@I@Z; CListCtrl::GetItemRect(int,tagRECT *,uint)
0x1400aa202  mov     rcx, [rsi+40h]; hWnd
0x1400aa206  lea     rdx, [rbp+Rect]; lpRect
0x1400aa20a  mov     r8d, 1; bErase
0x1400aa210  call    cs:__imp_InvalidateRect
0x1400aa216  jmp     short loc_1400AA24C
0x1400aa218  mov     r8d, ebx
0x1400aa21b  lea     rdx, [rbp+var_30]
0x1400aa21f  mov     rcx, rdi
0x1400aa222  call    ?ScRedrawItem@CCCListViewCtrl@@AEAA?AVSC@mmcerror@@H@Z; CCCListViewCtrl::ScRedrawItem(int)
0x1400aa227  mov     rdx, rax
0x1400aa22a  lea     rcx, [rbp+var_48]
0x1400aa22e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400aa234  lea     rcx, [rbp+var_30]
0x1400aa238  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400aa23e  lea     rcx, [rbp+var_48]
0x1400aa242  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400aa248  test    al, al
0x1400aa24a  jnz     short loc_1400AA28E
0x1400aa24c  mov     rcx, [rsi+40h]; hWnd
0x1400aa250  call    cs:__imp_UpdateWindow
0x1400aa256  lea     rcx, [rdi+8]
0x1400aa25a  mov     r9d, ebx
0x1400aa25d  lea     r8, ??_9CAMCViewObserver@@$BDA@AA; [thunk]: CAMCViewObserver::`vcall'{48,{flat}}
0x1400aa264  lea     rdx, [rbp+var_30]
0x1400aa268  call    ??$ScFireEvent@VCListViewObserver@@H@?$CEventSource@VCListViewObserver@@VCVoid@@V2@V2@V2@@@QEAA?AVSC@mmcerror@@P8CListViewObserver@@EAA?AV12@H@ZH@Z; CEventSource<CListViewObserver,CVoid,CVoid,CVoid,CVoid>::ScFireEvent<CListViewObserver,int>(mmcerror::SC (CListViewObserver::*)(int),int)
0x1400aa26d  mov     rdx, rax
0x1400aa270  lea     rcx, [rbp+var_48]
0x1400aa274  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400aa27a  lea     rcx, [rbp+var_30]
0x1400aa27e  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400aa284  lea     rcx, [rbp+var_48]
0x1400aa288  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400aa28e  lea     rcx, [rbp+var_48]
0x1400aa292  jmp     short loc_1400AA2A6
0x1400aa294  mov     edx, 80070057h
0x1400aa299  lea     rcx, [rbp+var_48]
0x1400aa29d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400aa2a3  mov     rcx, rax
0x1400aa2a6  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400aa2ac  lea     rcx, [rbp+var_48]
0x1400aa2b0  mov     ebx, eax
0x1400aa2b2  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400aa2b8  mov     eax, ebx
0x1400aa2ba  mov     rcx, [rbp+var_8]
0x1400aa2be  xor     rcx, rsp; StackCookie
0x1400aa2c1  call    __security_check_cookie
0x1400aa2c6  mov     rbx, [rsp+70h+arg_10]
0x1400aa2ce  add     rsp, 70h
0x1400aa2d2  pop     rdi
0x1400aa2d3  pop     rsi
0x1400aa2d4  pop     rbp
0x1400aa2d5  retn
```
