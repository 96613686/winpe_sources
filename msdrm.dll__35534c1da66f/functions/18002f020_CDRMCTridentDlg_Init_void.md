# CDRMCTridentDlg::Init(void)

- ea: `0x18002f020`
- end: `0x18002f19a`
- name: `?Init@CDRMCTridentDlg@@QEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(CDRMCTridentDlg *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bcd0`
- `0x18002c0f4`

## callees

- `0x180001244`
- `0x18002f020`
- `0x18002fee4`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f0f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f0f0`
- `ole32!OleSetContainedObject` at `0x18002f11d`
- `ole32!OleSetContainedObject` at `0x18002f11d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDRMCTridentDlg::Init(CDRMCTridentDlg *this)
{
  char *v2; // rax
  CWebBrowser *v3; // rbx
  LPUNKNOWN *v4; // rdi
  _QWORD *v5; // rsi

  v2 = (char *)operator new(0x88u);
  v3 = (CWebBrowser *)v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &CWebBrowser::`vftable'{for `IOleInPlaceSite'};
    *((_QWORD *)v2 + 1) = &CWebBrowser::`vftable'{for `IOleClientSite'};
    *((_QWORD *)v2 + 2) = &CWebBrowser::`vftable'{for `IOleInPlaceFrame'};
    *((_QWORD *)v2 + 3) = &CWebBrowser::`vftable'{for `IServiceProvider'};
    *((_QWORD *)v2 + 4) = &CWebBrowser::`vftable'{for `IDocHostUIHandler'};
    *((_QWORD *)v2 + 5) = &CWebBrowser::`vftable'{for `DWebBrowserEvents2'};
    *((_QWORD *)v2 + 6) = &CWebBrowser::`vftable'{for `IInternetSecurityManager'};
    *((_QWORD *)v2 + 7) = 0;
    *((_QWORD *)v2 + 8) = 0;
    v4 = (LPUNKNOWN *)(v2 + 72);
    *((_QWORD *)v2 + 9) = 0;
    v5 = v2 + 80;
    *((_QWORD *)v2 + 10) = 0;
    *((_QWORD *)v2 + 11) = 0;
    *((_QWORD *)v2 + 12) = 0;
    *((_QWORD *)v2 + 13) = 0;
    *((_QWORD *)v2 + 14) = 0;
    *((_QWORD *)v2 + 15) = 0;
    *((_QWORD *)v2 + 16) = 0;
    if ( CoCreateInstance(&CLSID_WebBrowser, 0, 1u, &IID_IWebBrowser2, (LPVOID *)v2 + 10) < 0
      || (**(int (__fastcall ***)(_QWORD, GUID *, __int64))*v5)(*v5, &IID_IOleObject, (__int64)v3 + 72) < 0
      || (OleSetContainedObject(*v4, 1),
          ((int (__fastcall *)(LPUNKNOWN, __int64))(*v4)->lpVtbl[1].QueryInterface)(*v4, (__int64)v3 + 8) < 0)
      || (int)CWebBrowser::ConnectToConnectionPoint(v3, 1) < 0 )
    {
      if ( *v5 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
        *v5 = 0;
      }
      if ( *v4 )
      {
        ((void (__fastcall *)(LPUNKNOWN))(*v4)->lpVtbl->Release)(*v4);
        *v4 = 0;
      }
    }
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)this + 8) = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18002f020  push    rbx
0x18002f022  push    rbp
0x18002f023  push    rsi
0x18002f024  push    rdi
0x18002f025  push    r14
0x18002f027  push    r15
0x18002f029  sub     rsp, 48h
0x18002f02d  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x18002f036  mov     rbp, rcx
0x18002f039  mov     ecx, 88h; Size
0x18002f03e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f043  mov     rbx, rax
0x18002f046  mov     [rsp+78h+arg_0], rax
0x18002f04e  xor     r15d, r15d
0x18002f051  test    rax, rax
0x18002f054  jz      loc_18002F17A
0x18002f05a  lea     rax, ??_7CWebBrowser@@6BIOleInPlaceSite@@@; const CWebBrowser::`vftable'{for `IOleInPlaceSite'}
0x18002f061  mov     [rbx], rax
0x18002f064  lea     rax, ??_7CWebBrowser@@6BIOleClientSite@@@; const CWebBrowser::`vftable'{for `IOleClientSite'}
0x18002f06b  mov     [rbx+8], rax
0x18002f06f  lea     rax, ??_7CWebBrowser@@6BIOleInPlaceFrame@@@; const CWebBrowser::`vftable'{for `IOleInPlaceFrame'}
0x18002f076  mov     [rbx+10h], rax
0x18002f07a  lea     rax, ??_7CWebBrowser@@6BIServiceProvider@@@; const CWebBrowser::`vftable'{for `IServiceProvider'}
0x18002f081  mov     [rbx+18h], rax
0x18002f085  lea     rax, ??_7CWebBrowser@@6BIDocHostUIHandler@@@; const CWebBrowser::`vftable'{for `IDocHostUIHandler'}
0x18002f08c  mov     [rbx+20h], rax
0x18002f090  lea     rax, ??_7CWebBrowser@@6BDWebBrowserEvents2@@@; const CWebBrowser::`vftable'{for `DWebBrowserEvents2'}
0x18002f097  mov     [rbx+28h], rax
0x18002f09b  lea     rax, ??_7CWebBrowser@@6BIInternetSecurityManager@@@; const CWebBrowser::`vftable'{for `IInternetSecurityManager'}
0x18002f0a2  mov     [rbx+30h], rax
0x18002f0a6  mov     [rbx+38h], r15
0x18002f0aa  mov     [rbx+40h], r15
0x18002f0ae  lea     rdi, [rbx+48h]
0x18002f0b2  mov     [rdi], r15
0x18002f0b5  lea     rsi, [rbx+50h]
0x18002f0b9  mov     [rsi], r15
0x18002f0bc  mov     [rbx+58h], r15
0x18002f0c0  mov     [rbx+60h], r15
0x18002f0c4  mov     [rbx+68h], r15
0x18002f0c8  mov     [rbx+70h], r15
0x18002f0cc  mov     [rbx+78h], r15
0x18002f0d0  mov     [rbx+80h], r15
0x18002f0d7  mov     [rsp+78h+ppv], rsi; ppv
0x18002f0dc  lea     r9, IID_IWebBrowser2; riid
0x18002f0e3  xor     edx, edx; pUnkOuter
0x18002f0e5  lea     r8d, [r15+1]; dwClsContext
0x18002f0e9  lea     rcx, CLSID_WebBrowser; rclsid
0x18002f0f0  call    cs:__imp_CoCreateInstance
0x18002f0f6  test    eax, eax
0x18002f0f8  js      short loc_18002F14A
0x18002f0fa  mov     rcx, [rsi]
0x18002f0fd  mov     rax, [rcx]
0x18002f100  mov     r8, rdi
0x18002f103  lea     rdx, IID_IOleObject
0x18002f10a  mov     rax, [rax]
0x18002f10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f112  test    eax, eax
0x18002f114  js      short loc_18002F14A
0x18002f116  lea     edx, [r15+1]; fContained
0x18002f11a  mov     rcx, [rdi]; pUnknown
0x18002f11d  call    cs:__imp_OleSetContainedObject
0x18002f123  mov     rcx, [rdi]
0x18002f126  mov     rax, [rcx]
0x18002f129  lea     rdx, [rbx+8]
0x18002f12d  mov     rax, [rax+18h]
0x18002f131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f136  test    eax, eax
0x18002f138  js      short loc_18002F14A
0x18002f13a  lea     edx, [r15+1]; int
0x18002f13e  mov     rcx, rbx; this
0x18002f141  call    ?ConnectToConnectionPoint@CWebBrowser@@AEAAJH@Z; CWebBrowser::ConnectToConnectionPoint(int)
0x18002f146  test    eax, eax
0x18002f148  jns     short loc_18002F17D
0x18002f14a  mov     rcx, [rsi]
0x18002f14d  test    rcx, rcx
0x18002f150  jz      short loc_18002F161
0x18002f152  mov     rax, [rcx]
0x18002f155  mov     rax, [rax+10h]
0x18002f159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f15e  mov     [rsi], r15
0x18002f161  mov     rcx, [rdi]
0x18002f164  test    rcx, rcx
0x18002f167  jz      short loc_18002F17D
0x18002f169  mov     rax, [rcx]
0x18002f16c  mov     rax, [rax+10h]
0x18002f170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f175  mov     [rdi], r15
0x18002f178  jmp     short loc_18002F17D
0x18002f17a  mov     rbx, r15
0x18002f17d  mov     [rbp+40h], rbx
0x18002f181  neg     rbx
0x18002f184  sbb     eax, eax
0x18002f186  not     eax
0x18002f188  and     eax, 8007000Eh
0x18002f18d  add     rsp, 48h
0x18002f191  pop     r15
0x18002f193  pop     r14
0x18002f195  pop     rdi
0x18002f196  pop     rsi
0x18002f197  pop     rbp
0x18002f198  pop     rbx
0x18002f199  retn
```
