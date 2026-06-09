# OSKDuiFrame::Initialize(DirectUI::NativeHWNDHost *,HINSTANCE__ *,int,DirectUI::Element *,ulong *)

- ea: `0x14000f098`
- end: `0x14000f2a3`
- name: `?Initialize@OSKDuiFrame@@QEAAJPEAVNativeHWNDHost@DirectUI@@PEAUHINSTANCE__@@HPEAVElement@3@PEAK@Z`
- size: `523`
- prototype: `__int64 __usercall@<rax>(OSKDuiFrame *__hidden this@<rcx>, struct DirectUI::NativeHWNDHost *@<rdx>, HINSTANCE@<r8>, int@<r9d>, struct DirectUI::Element *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000ecc8`

## callees

- `0x14000f098`
- `0x14000f2ac`
- `0x14000ffdc`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000f1f9`
- `KERNEL32!GetLastError` at `0x14000f1f9`
- `USER32!LoadImageW` at `0x14000f1d1`
- `USER32!LoadImageW` at `0x14000f1d1`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x14000f217`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x14000f217`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x14000f228`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x14000f228`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x14000f159`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x14000f159`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x14000f146`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x14000f146`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14000f19f`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x14000f19f`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x14000f278`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x14000f278`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14000f10c`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x14000f10c`
- `DUI70!?DoubleBuffered@Element@DirectUI@@QEAAX_N@Z` at `0x14000f249`
- `DUI70!?DoubleBuffered@Element@DirectUI@@QEAAX_N@Z` at `0x14000f249`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x14000f23e`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x14000f23e`
- `DUI70!?Register@HWNDElement@DirectUI@@SAJXZ` at `0x14000f0bb`
- `DUI70!?Register@HWNDElement@DirectUI@@SAJXZ` at `0x14000f0bb`
- `DUI70!?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x14000f0f2`
- `DUI70!?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x14000f0f2`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14000f0ce`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14000f0ce`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14000f28a`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x14000f28a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSKDuiFrame::Initialize(
        OSKDuiFrame *this,
        struct DirectUI::NativeHWNDHost *a2,
        HINSTANCE a3,
        __int64 a4,
        struct DirectUI::Element *a5,
        unsigned int *a6)
{
  signed int KeyboardManager; // ebx
  HWND HWND; // rax
  HBITMAP ImageW; // rax
  signed int LastError; // eax
  unsigned int v12; // [rsp+38h] [rbp-8h] BYREF
  struct DirectUI::Layout *v13; // [rsp+50h] [rbp+10h] BYREF
  struct DirectUI::Element *v14; // [rsp+58h] [rbp+18h] BYREF

  *((_QWORD *)this + 32) = a2;
  *((_QWORD *)this + 33) = a3;
  KeyboardManager = DirectUI::HWNDElement::Register();
  if ( KeyboardManager >= 0 )
  {
    HWND = DirectUI::NativeHWNDHost::GetHWND(*((DirectUI::NativeHWNDHost **)this + 32));
    KeyboardManager = DirectUI::HWNDElement::Initialize(this, HWND, 0, 0, 0, a6);
  }
  v12 = 0;
  DirectUI::Element::StartDefer(this, &v12);
  if ( KeyboardManager < 0 )
  {
    v13 = 0;
    v14 = 0;
LABEL_19:
    if ( v13 )
      DirectUI::Layout::Destroy(v13);
    goto LABEL_21;
  }
  KeyboardManager = (*(__int64 (__fastcall **)(OSKDuiFrame *, char *))(*(_QWORD *)this + 440LL))(
                      this,
                      (char *)this + 280);
  v13 = 0;
  if ( KeyboardManager >= 0 )
  {
    KeyboardManager = DirectUI::FillLayout::Create(&v13);
    if ( KeyboardManager >= 0 )
      KeyboardManager = DirectUI::Element::SetLayout(this, v13);
  }
  v14 = 0;
  if ( KeyboardManager < 0 )
    goto LABEL_19;
  v13 = 0;
  KeyboardManager = DirectUI::DUIXmlParser::CreateElement(
                      *((DirectUI::DUIXmlParser **)this + 35),
                      L"main",
                      this,
                      0,
                      0,
                      &v14);
  if ( KeyboardManager < 0 )
    goto LABEL_19;
  ImageW = (HBITMAP)LoadImageW(*((HINSTANCE *)this + 33), (LPCWSTR)0x7D0, 0, 0, 0, 0);
  if ( ImageW )
  {
    KeyboardManager = COSKKeyboardManager::CreateKeyboardManager(
                        *((struct DirectUI::NativeHWNDHost **)this + 32),
                        this,
                        ImageW,
                        (struct COSKKeyboardManager **)this + 34);
  }
  else
  {
    LastError = GetLastError();
    KeyboardManager = LastError;
    if ( LastError > 0 )
      KeyboardManager = (unsigned __int16)LastError | 0x80070000;
  }
  if ( KeyboardManager < 0 )
    goto LABEL_19;
  KeyboardManager = DirectUI::Element::SetVisible(this, 1);
  if ( KeyboardManager < 0 )
    goto LABEL_19;
  KeyboardManager = DirectUI::Element::SetAccessible(this, 1);
  if ( KeyboardManager < 0 )
    goto LABEL_19;
  DirectUI::NativeHWNDHost::Host(*((DirectUI::NativeHWNDHost **)this + 32), this);
  DirectUI::Element::DoubleBuffered(this, 1);
  KeyboardManager = OSKDuiFrame::InitializeTooltipWindow(this);
  if ( KeyboardManager < 0 )
    goto LABEL_19;
LABEL_21:
  if ( v12 )
    DirectUI::Element::EndDefer(this, v12);
  return (unsigned int)KeyboardManager;
}

```

## disassembly

```asm
0x14000f098  mov     [rsp-8+arg_10], rbx
0x14000f09d  mov     [rsp-8+arg_18], rdi
0x14000f0a2  push    rbp
0x14000f0a3  mov     rbp, rsp
0x14000f0a6  sub     rsp, 40h
0x14000f0aa  mov     rdi, rcx
0x14000f0ad  mov     [rcx+100h], rdx
0x14000f0b4  mov     [rcx+108h], r8
0x14000f0bb  call    cs:__imp_?Register@HWNDElement@DirectUI@@SAJXZ; DirectUI::HWNDElement::Register(void)
0x14000f0c1  mov     ebx, eax
0x14000f0c3  test    eax, eax
0x14000f0c5  js      short loc_14000F0FA
0x14000f0c7  mov     rcx, [rdi+100h]
0x14000f0ce  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x14000f0d4  mov     rdx, rax
0x14000f0d7  mov     rax, [rbp+arg_28]
0x14000f0db  mov     qword ptr [rsp+40h+fuLoad], rax
0x14000f0e0  mov     qword ptr [rsp+40h+cy], 0
0x14000f0e9  xor     r9d, r9d
0x14000f0ec  xor     r8d, r8d
0x14000f0ef  mov     rcx, rdi
0x14000f0f2  call    cs:__imp_?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z; DirectUI::HWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)
0x14000f0f8  mov     ebx, eax
0x14000f0fa  mov     [rbp+var_10], rdi
0x14000f0fe  mov     [rbp+var_8], 0
0x14000f105  lea     rdx, [rbp+var_8]
0x14000f109  mov     rcx, rdi
0x14000f10c  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x14000f112  nop
0x14000f113  test    ebx, ebx
0x14000f115  js      loc_14000F25F
0x14000f11b  mov     rax, [rdi]
0x14000f11e  lea     rdx, [rdi+118h]
0x14000f125  mov     rcx, rdi
0x14000f128  mov     rax, [rax+1B8h]
0x14000f12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f134  mov     ebx, eax
0x14000f136  mov     [rbp+arg_0], 0
0x14000f13e  test    eax, eax
0x14000f140  js      short loc_14000F161
0x14000f142  lea     rcx, [rbp+arg_0]
0x14000f146  call    cs:__imp_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z; DirectUI::FillLayout::Create(DirectUI::Layout * *)
0x14000f14c  mov     ebx, eax
0x14000f14e  test    eax, eax
0x14000f150  js      short loc_14000F161
0x14000f152  mov     rdx, [rbp+arg_0]
0x14000f156  mov     rcx, rdi
0x14000f159  call    cs:__imp_?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z; DirectUI::Element::SetLayout(DirectUI::Layout *)
0x14000f15f  mov     ebx, eax
0x14000f161  mov     [rbp+arg_8], 0
0x14000f169  test    ebx, ebx
0x14000f16b  js      loc_14000F26F
0x14000f171  mov     [rbp+arg_0], 0
0x14000f179  lea     rax, [rbp+arg_8]
0x14000f17d  mov     qword ptr [rsp+40h+fuLoad], rax
0x14000f182  mov     qword ptr [rsp+40h+cy], 0
0x14000f18b  xor     r9d, r9d
0x14000f18e  mov     r8, rdi
0x14000f191  lea     rdx, aMain; "main"
0x14000f198  mov     rcx, [rdi+118h]
0x14000f19f  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x14000f1a5  mov     ebx, eax
0x14000f1a7  test    eax, eax
0x14000f1a9  js      loc_14000F26F
0x14000f1af  mov     [rsp+40h+fuLoad], 0; fuLoad
0x14000f1b7  mov     [rsp+40h+cy], 0; cy
0x14000f1bf  xor     r9d, r9d; cx
0x14000f1c2  xor     r8d, r8d; type
0x14000f1c5  mov     edx, 7D0h; name
0x14000f1ca  mov     rcx, [rdi+108h]; hInst
0x14000f1d1  call    cs:__imp_LoadImageW
0x14000f1d7  test    rax, rax
0x14000f1da  jz      short loc_14000F1F9
0x14000f1dc  lea     r9, [rdi+110h]; struct COSKKeyboardManager **
0x14000f1e3  mov     r8, rax; HBITMAP
0x14000f1e6  mov     rdx, rdi; struct DirectUI::Element *
0x14000f1e9  mov     rcx, [rdi+100h]; struct DirectUI::NativeHWNDHost *
0x14000f1f0  call    ?CreateKeyboardManager@COSKKeyboardManager@@SAJPEAVNativeHWNDHost@DirectUI@@PEAVElement@3@PEAUHBITMAP__@@PEAPEAV1@@Z; COSKKeyboardManager::CreateKeyboardManager(DirectUI::NativeHWNDHost *,DirectUI::Element *,HBITMAP__ *,COSKKeyboardManager * *)
0x14000f1f5  mov     ebx, eax
0x14000f1f7  jmp     short loc_14000F20E
0x14000f1f9  call    cs:__imp_GetLastError
0x14000f1ff  mov     ebx, eax
0x14000f201  test    eax, eax
0x14000f203  jle     short loc_14000F20E
0x14000f205  movzx   ebx, ax
0x14000f208  or      ebx, 80070000h
0x14000f20e  test    ebx, ebx
0x14000f210  js      short loc_14000F26F
0x14000f212  mov     dl, 1
0x14000f214  mov     rcx, rdi
0x14000f217  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x14000f21d  mov     ebx, eax
0x14000f21f  test    eax, eax
0x14000f221  js      short loc_14000F26F
0x14000f223  mov     dl, 1
0x14000f225  mov     rcx, rdi
0x14000f228  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x14000f22e  mov     ebx, eax
0x14000f230  test    eax, eax
0x14000f232  js      short loc_14000F26F
0x14000f234  mov     rdx, rdi
0x14000f237  mov     rcx, [rdi+100h]
0x14000f23e  call    cs:__imp_?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z; DirectUI::NativeHWNDHost::Host(DirectUI::Element *)
0x14000f244  mov     dl, 1
0x14000f246  mov     rcx, rdi
0x14000f249  call    cs:__imp_?DoubleBuffered@Element@DirectUI@@QEAAX_N@Z; DirectUI::Element::DoubleBuffered(bool)
0x14000f24f  mov     rcx, rdi; this
0x14000f252  call    ?InitializeTooltipWindow@OSKDuiFrame@@AEAAJXZ; OSKDuiFrame::InitializeTooltipWindow(void)
0x14000f257  mov     ebx, eax
0x14000f259  test    eax, eax
0x14000f25b  jns     short loc_14000F27F
0x14000f25d  jmp     short loc_14000F26F
0x14000f25f  mov     [rbp+arg_0], 0
0x14000f267  mov     [rbp+arg_8], 0
0x14000f26f  mov     rcx, [rbp+arg_0]
0x14000f273  test    rcx, rcx
0x14000f276  jz      short loc_14000F27F
0x14000f278  call    cs:__imp_?Destroy@Layout@DirectUI@@QEAAXXZ; DirectUI::Layout::Destroy(void)
0x14000f27e  nop
0x14000f27f  mov     edx, [rbp+var_8]
0x14000f282  test    edx, edx
0x14000f284  jz      short loc_14000F291
0x14000f286  mov     rcx, [rbp+var_10]
0x14000f28a  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x14000f290  nop
0x14000f291  mov     eax, ebx
0x14000f293  mov     rbx, [rsp+40h+arg_10]
0x14000f298  mov     rdi, [rsp+40h+arg_18]
0x14000f29d  add     rsp, 40h
0x14000f2a1  pop     rbp
0x14000f2a2  retn
```
