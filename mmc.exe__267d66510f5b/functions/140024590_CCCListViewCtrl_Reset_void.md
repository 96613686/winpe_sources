# CCCListViewCtrl::Reset(void)

- ea: `0x140024590`
- end: `0x1400246fc`
- name: `?Reset@CCCListViewCtrl@@UEAAJXZ`
- size: `364`
- prototype: `__int64 __fastcall(CCCListViewCtrl *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140024590`
- `0x140024904`
- `0x1400254d8`
- `0x14003d080`
- `0x14003ee9c`
- `0x1400f3010`

## import_xrefs

- `MFC42u!__imp_?DeleteImageList@CImageList@@QEAAHXZ` at `0x1400245e9`
- `MFC42u!__imp_?DeleteImageList@CImageList@@QEAAHXZ` at `0x1400245f6`
- `MFC42u!__imp_?DeleteImageList@CImageList@@QEAAHXZ` at `0x1400245e9`
- `MFC42u!__imp_?DeleteImageList@CImageList@@QEAAHXZ` at `0x1400245f6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140024619`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140024694`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400246e4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140024619`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140024694`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400246e4`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140024623`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14002469e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140024623`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14002469e`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400245ab`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140024658`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400245ab`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140024658`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400246d8`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1400246d8`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14002460f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14002468a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14002460f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14002468a`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400245bc`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140024669`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400245bc`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140024669`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400246ac`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x1400246ac`

## pseudocode

```c
__int64 __fastcall CCCListViewCtrl::Reset(CCCListViewCtrl *this)
{
  mmcerror::SC *v2; // rax
  __int64 v3; // rdi
  int v4; // edx
  int v5; // edx
  unsigned int v6; // ebx
  _BYTE v8[24]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v9[24]; // [rsp+38h] [rbp-18h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v8, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v8, L"CCCListViewCtrl::Reset");
  (*(void (__fastcall **)(CCCListViewCtrl *, __int64))(*(_QWORD *)this + 96LL))(this, 60102025);
  CMap<CImageIndexMapKey *,CImageIndexMapKey *,int,int &>::RemoveAll((char *)this + 264);
  CImageList::DeleteImageList((CCCListViewCtrl *)((char *)this + 232));
  CImageList::DeleteImageList((CCCListViewCtrl *)((char *)this + 248));
  v2 = CCCListViewCtrl::ScSetImageLists((__int64)this, (mmcerror::SC *)v9);
  mmcerror::SC::operator=(v8, v2);
  mmcerror::SC::~SC((mmcerror::SC *)v9);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v8) )
  {
    while ( (*(int (__fastcall **)(CCCListViewCtrl *, _QWORD))(*(_QWORD *)this + 88LL))(this, 0) >= 0 )
      ;
    v3 = *((_QWORD *)this + 16);
    if ( v3 )
    {
      mmcerror::SC::SC((mmcerror::SC *)v9, 0);
      mmcerror::SC::SetFunctionName((mmcerror::SC *)v9, L"CAMCListView::ScResetColumnStatusData");
      *(_BYTE *)(v3 + 497) = 1;
      std::list<SubclasserData>::clear(v3 + 456);
      mmcerror::SC::operator=(v8, v9);
      mmcerror::SC::~SC((mmcerror::SC *)v9);
    }
    if ( (unsigned __int8)mmcerror::SC::operator bool(v8) )
      mmcerror::SC::TraceAndClear((mmcerror::SC *)v8);
    *((_DWORD *)this + 85) = 0;
    SnapinInterfaceWrapper::Assign((CCCListViewCtrl *)((char *)this + 360), v4);
    SnapinInterfaceWrapper::Assign((CCCListViewCtrl *)((char *)this + 440), v5);
  }
  v6 = mmcerror::SC::ToHr((mmcerror::SC *)v8);
  mmcerror::SC::~SC((mmcerror::SC *)v8);
  return v6;
}

```

## disassembly

```asm
0x140024590  mov     [rsp-8+arg_0], rbx
0x140024595  mov     [rsp-8+arg_8], rdi
0x14002459a  push    rbp
0x14002459b  mov     rbp, rsp
0x14002459e  sub     rsp, 50h
0x1400245a2  mov     rbx, rcx
0x1400245a5  xor     edx, edx
0x1400245a7  lea     rcx, [rbp+var_30]
0x1400245ab  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400245b1  lea     rdx, aCcclistviewctr_52; "CCCListViewCtrl::Reset"
0x1400245b8  lea     rcx, [rbp+var_30]
0x1400245bc  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400245c2  mov     rax, [rbx]
0x1400245c5  mov     edx, 3951589h
0x1400245ca  mov     rcx, rbx
0x1400245cd  mov     rax, [rax+60h]
0x1400245d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400245d6  lea     rcx, [rbx+108h]
0x1400245dd  call    ?RemoveAll@?$CMap@PEAVCImageIndexMapKey@@PEAV1@HAEAH@@QEAAXXZ; CMap<CImageIndexMapKey *,CImageIndexMapKey *,int,int &>::RemoveAll(void)
0x1400245e2  lea     rcx, [rbx+0E8h]
0x1400245e9  call    cs:__imp_?DeleteImageList@CImageList@@QEAAHXZ; CImageList::DeleteImageList(void)
0x1400245ef  lea     rcx, [rbx+0F8h]
0x1400245f6  call    cs:__imp_?DeleteImageList@CImageList@@QEAAHXZ; CImageList::DeleteImageList(void)
0x1400245fc  lea     rdx, [rbp+var_18]
0x140024600  mov     rcx, rbx
0x140024603  call    ?ScSetImageLists@CCCListViewCtrl@@AEAA?AVSC@mmcerror@@XZ; CCCListViewCtrl::ScSetImageLists(void)
0x140024608  mov     rdx, rax
0x14002460b  lea     rcx, [rbp+var_30]
0x14002460f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140024615  lea     rcx, [rbp+var_18]
0x140024619  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14002461f  lea     rcx, [rbp+var_30]
0x140024623  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140024629  test    al, al
0x14002462b  jnz     loc_1400246D4
0x140024631  mov     rax, [rbx]
0x140024634  xor     edx, edx
0x140024636  mov     rcx, rbx
0x140024639  mov     rax, [rax+58h]
0x14002463d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024642  test    eax, eax
0x140024644  jns     short loc_140024631
0x140024646  mov     rdi, [rbx+80h]
0x14002464d  test    rdi, rdi
0x140024650  jz      short loc_14002469A
0x140024652  xor     edx, edx
0x140024654  lea     rcx, [rbp+var_18]
0x140024658  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14002465e  lea     rdx, aCamclistviewSc_1; "CAMCListView::ScResetColumnStatusData"
0x140024665  lea     rcx, [rbp+var_18]
0x140024669  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14002466f  lea     rcx, [rdi+1C8h]
0x140024676  mov     byte ptr [rdi+1F1h], 1
0x14002467d  call    ?clear@?$list@VSubclasserData@@V?$allocator@VSubclasserData@@@std@@@std@@QEAAXXZ; std::list<SubclasserData>::clear(void)
0x140024682  lea     rdx, [rbp+var_18]
0x140024686  lea     rcx, [rbp+var_30]
0x14002468a  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140024690  lea     rcx, [rbp+var_18]
0x140024694  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14002469a  lea     rcx, [rbp+var_30]
0x14002469e  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400246a4  test    al, al
0x1400246a6  jz      short loc_1400246B2
0x1400246a8  lea     rcx, [rbp+var_30]
0x1400246ac  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x1400246b2  lea     rcx, [rbx+168h]; this
0x1400246b9  mov     dword ptr [rbx+154h], 0
0x1400246c3  call    ?Assign@SnapinInterfaceWrapper@@QEAAJH@Z; SnapinInterfaceWrapper::Assign(int)
0x1400246c8  lea     rcx, [rbx+1B8h]; this
0x1400246cf  call    ?Assign@SnapinInterfaceWrapper@@QEAAJH@Z; SnapinInterfaceWrapper::Assign(int)
0x1400246d4  lea     rcx, [rbp+var_30]
0x1400246d8  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x1400246de  lea     rcx, [rbp+var_30]
0x1400246e2  mov     ebx, eax
0x1400246e4  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400246ea  mov     rdi, [rsp+50h+arg_8]
0x1400246ef  mov     eax, ebx
0x1400246f1  mov     rbx, [rsp+50h+arg_0]
0x1400246f6  add     rsp, 50h
0x1400246fa  pop     rbp
0x1400246fb  retn
```
