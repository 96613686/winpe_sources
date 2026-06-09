# CHtmlHelpControl::~CHtmlHelpControl(void)

- ea: `0x18002eb98`
- end: `0x18002ee94`
- name: `??1CHtmlHelpControl@@UEAA@XZ`
- size: `764`
- prototype: `void __fastcall(CHtmlHelpControl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002eef0`

## callees

- `0x180001710`
- `0x180006708`
- `0x1800173b8`
- `0x18002eb98`
- `0x18003e634`
- `0x180078010`

## import_xrefs

- `msvcrt!free` at `0x18002ed0c`
- `msvcrt!free` at `0x18002ed55`
- `msvcrt!free` at `0x18002ed67`
- `msvcrt!free` at `0x18002ed79`
- `msvcrt!free` at `0x18002edea`
- `msvcrt!free` at `0x18002edfc`
- `msvcrt!free` at `0x18002ee0e`
- `msvcrt!free` at `0x18002ee20`
- `msvcrt!free` at `0x18002ed0c`
- `msvcrt!free` at `0x18002ed55`
- `msvcrt!free` at `0x18002ed67`
- `msvcrt!free` at `0x18002ed79`
- `msvcrt!free` at `0x18002edea`
- `msvcrt!free` at `0x18002edfc`
- `msvcrt!free` at `0x18002ee0e`
- `msvcrt!free` at `0x18002ee20`
- `USER32!DestroyWindow` at `0x18002ec6c`
- `USER32!DestroyWindow` at `0x18002ec6c`
- `GDI32!DeleteObject` at `0x18002ecfa`
- `GDI32!DeleteObject` at `0x18002edbd`
- `GDI32!DeleteObject` at `0x18002edd8`
- `GDI32!DeleteObject` at `0x18002ecfa`
- `GDI32!DeleteObject` at `0x18002edbd`
- `GDI32!DeleteObject` at `0x18002edd8`

## pseudocode

```c
void __fastcall CHtmlHelpControl::~CHtmlHelpControl(CHtmlHelpControl *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  IWebBrowserAppImpl *v20; // rcx
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  void (__fastcall ***v22)(_QWORD, __int64); // rcx
  void (__fastcall ***v23)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &CHtmlHelpControl::`vftable'{for `CAutomationObject'};
  *((_QWORD *)this + 6) = &CHtmlHelpControl::`vftable'{for `IOleObject'};
  *((_QWORD *)this + 7) = &CInternetControl::`vftable'{for `IOleControl'};
  *((_QWORD *)this + 8) = &CHtmlHelpControl::`vftable'{for `IOleInPlaceObjectWindowless'};
  *((_QWORD *)this + 9) = &CHtmlHelpControl::`vftable'{for `IOleInPlaceActiveObject'};
  *((_QWORD *)this + 10) = &CInternetControl::`vftable'{for `IViewObjectEx'};
  *((_QWORD *)this + 11) = &CHtmlHelpControl::`vftable'{for `IPersistPropertyBag'};
  *((_QWORD *)this + 12) = &CInternetControl::`vftable'{for `IPersistStreamInit'};
  *((_QWORD *)this + 13) = &CHtmlHelpControl::`vftable'{for `IPersistStorage'};
  *((_QWORD *)this + 14) = &CInternetControl::`vftable'{for `IConnectionPointContainer'};
  *((_QWORD *)this + 15) = &CHtmlHelpControl::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 16) = &COleControl::`vftable'{for `IPointerInactive'};
  *((_QWORD *)this + 17) = &CHtmlHelpControl::`vftable'{for `IQuickActivate'};
  *((_QWORD *)this + 43) = &CHtmlHelpControl::`vftable'{for `IHHCtrl'};
  *((_QWORD *)this + 44) = &CHtmlHelpControl::`vftable'{for `ISupportErrorInfo'};
  if ( (unsigned int)IsValidWindow(*((HWND *)this + 56)) )
    DestroyWindow(*((HWND *)this + 56));
  v3 = *((_QWORD *)this + 69);
  if ( v3 )
  {
    v2 = *((_QWORD *)this + 152);
    if ( v2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 192LL))(v3);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 69) + 200LL))(
        *((_QWORD *)this + 69),
        *((_QWORD *)this + 152));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 69) + 16LL))(*((_QWORD *)this + 69));
      *((_QWORD *)this + 152) = 0;
    }
  }
  v4 = (void *)*((_QWORD *)this + 78);
  if ( v4 )
    operator delete[](v4);
  v5 = (void *)*((_QWORD *)this + 152);
  if ( v5 && !*((_DWORD *)this + 300) )
    DeleteObject(v5);
  v6 = (void *)*((_QWORD *)this + 46);
  if ( v6 )
    free(v6);
  v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 76);
  if ( v7 )
    (**v7)(v7, 1);
  v8 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 75);
  if ( v8 )
    (**v8)(v8, 1);
  v9 = (void *)*((_QWORD *)this + 72);
  if ( v9 )
    free(v9);
  v10 = (void *)*((_QWORD *)this + 48);
  if ( v10 )
    free(v10);
  v11 = (void *)*((_QWORD *)this + 49);
  if ( v11 )
    free(v11);
  v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 63);
  if ( v12 )
    (**v12)(v12, 1);
  v13 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 67);
  if ( v13 )
    (**v13)(v13, 1);
  v14 = (void *)*((_QWORD *)this + 52);
  if ( v14 )
    DeleteObject(v14);
  if ( !*((_DWORD *)this + 107) )
  {
    v15 = (void *)*((_QWORD *)this + 54);
    if ( v15 )
      DeleteObject(v15);
  }
  v16 = (void *)*((_QWORD *)this + 58);
  if ( v16 )
    free(v16);
  v17 = (void *)*((_QWORD *)this + 59);
  if ( v17 )
    free(v17);
  v18 = (void *)*((_QWORD *)this + 60);
  if ( v18 )
    free(v18);
  v19 = (void *)*((_QWORD *)this + 61);
  if ( v19 )
    free(v19);
  v20 = (IWebBrowserAppImpl *)*((_QWORD *)this + 62);
  if ( v20 )
    IWebBrowserAppImpl::`scalar deleting destructor'(v20, v2);
  v21 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 64);
  if ( v21 )
    (**v21)(v21, 1);
  v22 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 65);
  if ( v22 )
    (**v22)(v22, 1);
  v23 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 66);
  if ( v23 )
    (**v23)(v23, 1);
  CInternetControl::~CInternetControl(this);
}

```

## disassembly

```asm
0x18002eb98  mov     [rsp+arg_0], rbx
0x18002eb9d  push    rsi
0x18002eb9e  sub     rsp, 20h
0x18002eba2  mov     rbx, rcx
0x18002eba5  lea     rax, ??_7CHtmlHelpControl@@6BCAutomationObject@@@; const CHtmlHelpControl::`vftable'{for `CAutomationObject'}
0x18002ebac  mov     [rcx], rax
0x18002ebaf  lea     rax, ??_7CHtmlHelpControl@@6BIOleObject@@@; const CHtmlHelpControl::`vftable'{for `IOleObject'}
0x18002ebb6  mov     [rcx+30h], rax
0x18002ebba  lea     rax, ??_7CInternetControl@@6BIOleControl@@@; const CInternetControl::`vftable'{for `IOleControl'}
0x18002ebc1  mov     [rcx+38h], rax
0x18002ebc5  lea     rax, ??_7CHtmlHelpControl@@6BIOleInPlaceObjectWindowless@@@; const CHtmlHelpControl::`vftable'{for `IOleInPlaceObjectWindowless'}
0x18002ebcc  mov     [rcx+40h], rax
0x18002ebd0  lea     rax, ??_7CHtmlHelpControl@@6BIOleInPlaceActiveObject@@@; const CHtmlHelpControl::`vftable'{for `IOleInPlaceActiveObject'}
0x18002ebd7  mov     [rcx+48h], rax
0x18002ebdb  lea     rax, ??_7CInternetControl@@6BIViewObjectEx@@@; const CInternetControl::`vftable'{for `IViewObjectEx'}
0x18002ebe2  mov     [rcx+50h], rax
0x18002ebe6  lea     rax, ??_7CHtmlHelpControl@@6BIPersistPropertyBag@@@; const CHtmlHelpControl::`vftable'{for `IPersistPropertyBag'}
0x18002ebed  mov     [rcx+58h], rax
0x18002ebf1  lea     rax, ??_7CInternetControl@@6BIPersistStreamInit@@@; const CInternetControl::`vftable'{for `IPersistStreamInit'}
0x18002ebf8  mov     [rcx+60h], rax
0x18002ebfc  lea     rax, ??_7CHtmlHelpControl@@6BIPersistStorage@@@; const CHtmlHelpControl::`vftable'{for `IPersistStorage'}
0x18002ec03  mov     [rcx+68h], rax
0x18002ec07  lea     rax, ??_7CInternetControl@@6BIConnectionPointContainer@@@; const CInternetControl::`vftable'{for `IConnectionPointContainer'}
0x18002ec0e  mov     [rcx+70h], rax
0x18002ec12  lea     rax, ??_7CHtmlHelpControl@@6BIProvideClassInfo@@@; const CHtmlHelpControl::`vftable'{for `IProvideClassInfo'}
0x18002ec19  mov     [rcx+78h], rax
0x18002ec1d  lea     rax, ??_7COleControl@@6BIPointerInactive@@@; const COleControl::`vftable'{for `IPointerInactive'}
0x18002ec24  mov     [rcx+80h], rax
0x18002ec2b  lea     rax, ??_7CHtmlHelpControl@@6BIQuickActivate@@@; const CHtmlHelpControl::`vftable'{for `IQuickActivate'}
0x18002ec32  mov     [rcx+88h], rax
0x18002ec39  lea     rax, ??_7CHtmlHelpControl@@6BIHHCtrl@@@; const CHtmlHelpControl::`vftable'{for `IHHCtrl'}
0x18002ec40  mov     [rcx+158h], rax
0x18002ec47  lea     rax, ??_7CHtmlHelpControl@@6BISupportErrorInfo@@@; const CHtmlHelpControl::`vftable'{for `ISupportErrorInfo'}
0x18002ec4e  mov     [rcx+160h], rax
0x18002ec55  mov     rcx, [rcx+1C0h]; HWND
0x18002ec5c  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18002ec61  test    eax, eax
0x18002ec63  jz      short loc_18002EC72
0x18002ec65  mov     rcx, [rbx+1C0h]; hWnd
0x18002ec6c  call    cs:__imp_DestroyWindow
0x18002ec72  mov     rcx, [rbx+228h]
0x18002ec79  test    rcx, rcx
0x18002ec7c  jz      short loc_18002ECD4
0x18002ec7e  mov     rdx, [rbx+4C0h]
0x18002ec85  test    rdx, rdx
0x18002ec88  jz      short loc_18002ECD4
0x18002ec8a  mov     rax, [rcx]
0x18002ec8d  mov     rax, [rax+0C0h]
0x18002ec94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec99  mov     rcx, [rbx+228h]
0x18002eca0  mov     rax, [rcx]
0x18002eca3  mov     rdx, [rbx+4C0h]
0x18002ecaa  mov     rax, [rax+0C8h]
0x18002ecb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecb6  mov     rcx, [rbx+228h]
0x18002ecbd  mov     rax, [rcx]
0x18002ecc0  mov     rax, [rax+10h]
0x18002ecc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ecc9  mov     qword ptr [rbx+4C0h], 0
0x18002ecd4  mov     rcx, [rbx+270h]; void *
0x18002ecdb  test    rcx, rcx
0x18002ecde  jz      short loc_18002ECE5
0x18002ece0  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ece5  mov     rcx, [rbx+4C0h]; ho
0x18002ecec  test    rcx, rcx
0x18002ecef  jz      short loc_18002ED00
0x18002ecf1  cmp     dword ptr [rbx+4B0h], 0
0x18002ecf8  jnz     short loc_18002ED00
0x18002ecfa  call    cs:__imp_DeleteObject
0x18002ed00  mov     rcx, [rbx+170h]; Block
0x18002ed07  test    rcx, rcx
0x18002ed0a  jz      short loc_18002ED12
0x18002ed0c  call    cs:__imp_free
0x18002ed12  mov     rcx, [rbx+260h]
0x18002ed19  mov     esi, 1
0x18002ed1e  test    rcx, rcx
0x18002ed21  jz      short loc_18002ED30
0x18002ed23  mov     rax, [rcx]
0x18002ed26  mov     edx, esi
0x18002ed28  mov     rax, [rax]
0x18002ed2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed30  mov     rcx, [rbx+258h]
0x18002ed37  test    rcx, rcx
0x18002ed3a  jz      short loc_18002ED49
0x18002ed3c  mov     rax, [rcx]
0x18002ed3f  mov     edx, esi
0x18002ed41  mov     rax, [rax]
0x18002ed44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed49  mov     rcx, [rbx+240h]; Block
0x18002ed50  test    rcx, rcx
0x18002ed53  jz      short loc_18002ED5B
0x18002ed55  call    cs:__imp_free
0x18002ed5b  mov     rcx, [rbx+180h]; Block
0x18002ed62  test    rcx, rcx
0x18002ed65  jz      short loc_18002ED6D
0x18002ed67  call    cs:__imp_free
0x18002ed6d  mov     rcx, [rbx+188h]; Block
0x18002ed74  test    rcx, rcx
0x18002ed77  jz      short loc_18002ED7F
0x18002ed79  call    cs:__imp_free
0x18002ed7f  mov     rcx, [rbx+1F8h]
0x18002ed86  test    rcx, rcx
0x18002ed89  jz      short loc_18002ED98
0x18002ed8b  mov     rax, [rcx]
0x18002ed8e  mov     edx, esi
0x18002ed90  mov     rax, [rax]
0x18002ed93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed98  mov     rcx, [rbx+218h]
0x18002ed9f  test    rcx, rcx
0x18002eda2  jz      short loc_18002EDB1
0x18002eda4  mov     rax, [rcx]
0x18002eda7  mov     edx, esi
0x18002eda9  mov     rax, [rax]
0x18002edac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edb1  mov     rcx, [rbx+1A0h]; ho
0x18002edb8  test    rcx, rcx
0x18002edbb  jz      short loc_18002EDC3
0x18002edbd  call    cs:__imp_DeleteObject
0x18002edc3  cmp     dword ptr [rbx+1ACh], 0
0x18002edca  jnz     short loc_18002EDDE
0x18002edcc  mov     rcx, [rbx+1B0h]; ho
0x18002edd3  test    rcx, rcx
0x18002edd6  jz      short loc_18002EDDE
0x18002edd8  call    cs:__imp_DeleteObject
0x18002edde  mov     rcx, [rbx+1D0h]; Block
0x18002ede5  test    rcx, rcx
0x18002ede8  jz      short loc_18002EDF0
0x18002edea  call    cs:__imp_free
0x18002edf0  mov     rcx, [rbx+1D8h]; Block
0x18002edf7  test    rcx, rcx
0x18002edfa  jz      short loc_18002EE02
0x18002edfc  call    cs:__imp_free
0x18002ee02  mov     rcx, [rbx+1E0h]; Block
0x18002ee09  test    rcx, rcx
0x18002ee0c  jz      short loc_18002EE14
0x18002ee0e  call    cs:__imp_free
0x18002ee14  mov     rcx, [rbx+1E8h]; Block
0x18002ee1b  test    rcx, rcx
0x18002ee1e  jz      short loc_18002EE26
0x18002ee20  call    cs:__imp_free
0x18002ee26  mov     rcx, [rbx+1F0h]; this
0x18002ee2d  test    rcx, rcx
0x18002ee30  jz      short loc_18002EE37
0x18002ee32  call    ??_GIWebBrowserAppImpl@@QEAAPEAXI@Z; IWebBrowserAppImpl::`scalar deleting destructor'(uint)
0x18002ee37  mov     rcx, [rbx+200h]
0x18002ee3e  test    rcx, rcx
0x18002ee41  jz      short loc_18002EE50
0x18002ee43  mov     rax, [rcx]
0x18002ee46  mov     edx, esi
0x18002ee48  mov     rax, [rax]
0x18002ee4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee50  mov     rcx, [rbx+208h]
0x18002ee57  test    rcx, rcx
0x18002ee5a  jz      short loc_18002EE69
0x18002ee5c  mov     rax, [rcx]
0x18002ee5f  mov     edx, esi
0x18002ee61  mov     rax, [rax]
0x18002ee64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee69  mov     rcx, [rbx+210h]
0x18002ee70  test    rcx, rcx
0x18002ee73  jz      short loc_18002EE82
0x18002ee75  mov     rax, [rcx]
0x18002ee78  mov     edx, esi
0x18002ee7a  mov     rax, [rax]
0x18002ee7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee82  mov     rcx, rbx; this
0x18002ee85  mov     rbx, [rsp+28h+arg_0]
0x18002ee8a  add     rsp, 20h
0x18002ee8e  pop     rsi
0x18002ee8f  jmp     ??1CInternetControl@@UEAA@XZ; CInternetControl::~CInternetControl(void)
```
