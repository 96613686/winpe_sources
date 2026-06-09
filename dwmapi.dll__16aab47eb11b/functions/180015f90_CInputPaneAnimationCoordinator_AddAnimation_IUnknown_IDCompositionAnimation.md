# CInputPaneAnimationCoordinator::AddAnimation(IUnknown *,IDCompositionAnimation *)

- ea: `0x180015f90`
- end: `0x1800160cd`
- name: `?AddAnimation@CInputPaneAnimationCoordinator@@UEAAJPEAUIUnknown@@PEAUIDCompositionAnimation@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CInputPaneAnimationCoordinator *__hidden this, struct IUnknown *, struct IDCompositionAnimation *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180011410`
- `0x180015a98`
- `0x180015f90`
- `0x18001630c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016096`

## pseudocode

```c
__int64 __fastcall CInputPaneAnimationCoordinator::AddAnimation(
        CInputPaneAnimationCoordinator *this,
        struct IUnknown *a2,
        struct IDCompositionAnimation *a3)
{
  struct IUnknownVtbl *lpVtbl; // rax
  int AnimationClockToken; // esi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v9; // rax
  HRESULT (__stdcall *v10)(IDCompositionAnimation *, const IID *const, void **); // rbx
  __int64 v11; // rax
  __int128 v12; // xmm0
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HANDLE, GUID *, __int64); // rbx
  __int64 v15; // rax
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+38h] [rbp-18h] BYREF
  __int128 v19; // [rsp+40h] [rbp-10h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+38h] BYREF
  __int64 v21; // [rsp+98h] [rbp+48h] BYREF

  lpVtbl = a2->lpVtbl;
  v18 = 0;
  v17 = 0;
  AnimationClockToken = -2147024809;
  QueryInterface = lpVtbl->QueryInterface;
  v9 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>(&v18);
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, __int64))QueryInterface)(
         a2,
         &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0,
         v9) >= 0 )
  {
    v10 = a3->lpVtbl->QueryInterface;
    v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>(&v17);
    if ( ((int (__fastcall *)(struct IDCompositionAnimation *, GUID *, __int64))v10)(
           a3,
           &GUID_cadfc221_2187_4f55_b289_01544817b158,
           v11) >= 0 )
    {
      v12 = *((_OWORD *)this + 1);
      hObject = 0;
      v19 = v12;
      AnimationClockToken = DwmpGetAnimationClockToken(&v19, &hObject);
      if ( AnimationClockToken >= 0 )
      {
        v13 = v18;
        v21 = 0;
        v14 = *(__int64 (__fastcall **)(__int64, HANDLE, GUID *, __int64))(*(_QWORD *)v18 + 232LL);
        v15 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>(&v21);
        AnimationClockToken = v14(v13, hObject, &GUID_64217f82_b1ca_430c_8a88_6cedec74c860, v15);
        if ( AnimationClockToken >= 0 )
          AnimationClockToken = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 72LL))(v17, v21);
        CloseHandle(hObject);
        Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(&v21);
      }
    }
  }
  Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(&v18);
  return (unsigned int)AnimationClockToken;
}

```

## disassembly

```asm
0x180015f90  mov     [rsp-28h+arg_0], rbx
0x180015f95  push    rbp
0x180015f96  push    rsi
0x180015f97  push    rdi
0x180015f98  push    r14
0x180015f9a  push    r15
0x180015f9c  mov     rbp, rsp
0x180015f9f  sub     rsp, 50h
0x180015fa3  mov     rax, [rdx]
0x180015fa6  mov     r15, rcx
0x180015fa9  lea     rcx, [rbp+var_18]
0x180015fad  mov     [rbp+var_18], 0
0x180015fb5  mov     r14, r8
0x180015fb8  mov     [rbp+var_20], 0
0x180015fc0  mov     rdi, rdx
0x180015fc3  mov     esi, 80070057h
0x180015fc8  mov     rbx, [rax]
0x180015fcb  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIDCompositionAnimationPartner@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIDCompositionAnimationPartner@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>)
0x180015fd0  mov     r8, rax
0x180015fd3  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x180015fda  mov     rax, rbx
0x180015fdd  mov     rcx, rdi
0x180015fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe5  test    eax, eax
0x180015fe7  js      loc_1800160A5
0x180015fed  mov     rax, [r14]
0x180015ff0  lea     rcx, [rbp+var_20]
0x180015ff4  mov     rbx, [rax]
0x180015ff7  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIDCompositionAnimationPartner@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIDCompositionAnimationPartner@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>)
0x180015ffc  mov     r8, rax
0x180015fff  lea     rdx, _GUID_cadfc221_2187_4f55_b289_01544817b158
0x180016006  mov     rax, rbx
0x180016009  mov     rcx, r14
0x18001600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016011  test    eax, eax
0x180016013  js      loc_1800160A5
0x180016019  movups  xmm0, xmmword ptr [r15+10h]
0x18001601e  lea     rdx, [rbp+hObject]
0x180016022  mov     [rbp+hObject], 0
0x18001602a  lea     rcx, [rbp+var_10]
0x18001602e  movdqu  [rbp+var_10], xmm0
0x180016033  call    DwmpGetAnimationClockToken
0x180016038  mov     esi, eax
0x18001603a  test    eax, eax
0x18001603c  js      short loc_1800160A5
0x18001603e  mov     rdi, [rbp+var_18]
0x180016042  lea     rcx, [rbp+arg_18]
0x180016046  mov     [rbp+arg_18], 0
0x18001604e  mov     rax, [rdi]
0x180016051  mov     rbx, [rax+0E8h]
0x180016058  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIDCompositionAnimationPartner@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIDCompositionAnimationPartner@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>)
0x18001605d  mov     rdx, [rbp+hObject]
0x180016061  lea     r8, _GUID_64217f82_b1ca_430c_8a88_6cedec74c860
0x180016068  mov     r9, rax
0x18001606b  mov     rcx, rdi
0x18001606e  mov     rax, rbx
0x180016071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016076  mov     esi, eax
0x180016078  test    eax, eax
0x18001607a  js      short loc_180016092
0x18001607c  mov     rcx, [rbp+var_20]
0x180016080  mov     rdx, [rbp+arg_18]
0x180016084  mov     rax, [rcx]
0x180016087  mov     rax, [rax+48h]
0x18001608b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016090  mov     esi, eax
0x180016092  mov     rcx, [rbp+hObject]; hObject
0x180016096  call    cs:__imp_CloseHandle
0x18001609c  lea     rcx, [rbp+arg_18]
0x1800160a0  call    ?InternalRelease@?$ComPtr@UIDCompositionAnimationTriggerPartner@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(void)
0x1800160a5  lea     rcx, [rbp+var_20]
0x1800160a9  call    ?InternalRelease@?$ComPtr@UIDCompositionAnimationTriggerPartner@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(void)
0x1800160ae  lea     rcx, [rbp+var_18]
0x1800160b2  call    ?InternalRelease@?$ComPtr@UIDCompositionAnimationTriggerPartner@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(void)
0x1800160b7  mov     rbx, [rsp+50h+arg_0]
0x1800160bf  mov     eax, esi
0x1800160c1  add     rsp, 50h
0x1800160c5  pop     r15
0x1800160c7  pop     r14
0x1800160c9  pop     rdi
0x1800160ca  pop     rsi
0x1800160cb  pop     rbp
0x1800160cc  retn
```
