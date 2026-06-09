# DwmpSetBlurredWallpaperSurface

- ea: `0x180006670`
- end: `0x180006a9a`
- name: `DwmpSetBlurredWallpaperSurface`
- size: `1066`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001684`
- `0x180004d20`
- `0x180006670`
- `0x18000a5c8`
- `0x18000a600`
- `0x18000c68c`
- `0x18000c9c0`
- `0x18000ca24`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a8f`
- `win32u!NtDCompositionSetBlurredWallpaperSurface` at `0x180006876`
- `win32u!NtDCompositionSetBlurredWallpaperSurface` at `0x180006876`

## string_xrefs

- `0x1800068c7`: `clientcore\windows\dwm\dwmapi\composition.cpp`
- `0x18000690a`: `clientcore\windows\dwm\dwmapi\composition.cpp`
- `0x180006987`: `clientcore\windows\dwm\dwmapi\composition.cpp`
- `0x1800069b4`: `clientcore\windows\dwm\dwmapi\composition.cpp`
- `0x1800069d1`: `clientcore\windows\dwm\dwmapi\composition.cpp`
- `0x1800069f6`: `clientcore\windows\dwm\dwmapi\composition.cpp`
- `0x180006a3c`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpSetBlurredWallpaperSurface(__int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *), __int64 a2)
{
  __int64 v2; // rsi
  __int64 (__fastcall **v4)(_QWORD, GUID *, __int64 *); // rax
  int v5; // eax
  unsigned int v6; // edi
  __int64 (__fastcall **v7)(_QWORD, GUID *, __int64 *); // rax
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rax
  __int64 (__fastcall **v12)(__int64, GUID *, __int64); // rdx
  __int64 v13; // r9
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  __int64 (__fastcall **v17)(__int64, GUID *, __int64); // rdx
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // rdi
  HANDLE v21; // rbx
  __int64 (__fastcall *v22)(__int64, HANDLE *); // r14
  int v23; // eax
  void *v24; // rdx
  unsigned int v25; // r8d
  int v26; // eax
  HANDLE v27; // rcx
  bool v28; // cc
  __int64 v30; // rdx
  _QWORD *v31; // [rsp+20h] [rbp-30h] BYREF
  __int64 v32; // [rsp+28h] [rbp-28h] BYREF
  _QWORD *v33; // [rsp+30h] [rbp-20h] BYREF
  __int64 v34; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v35[16]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v37; // [rsp+80h] [rbp+30h] BYREF
  __int64 v38; // [rsp+90h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+48h] BYREF

  hObject = 0;
  v2 = a2;
  if ( a1 )
  {
    if ( a2 )
    {
      v4 = *a1;
      v38 = 0;
      v5 = (*v4)(a1, &GUID_1527540d_42c7_47a6_a408_668f79a90dfb, &v38);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AC,
          (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
          (const char *)(unsigned int)v5,
          (int)v31);
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        return v6;
      }
      v7 = *a1;
      v37 = 0;
      v8 = (*v7)(a1, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, &v37);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
          (const char *)(unsigned int)v8,
          (int)v31);
      }
      else
      {
        v31 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v37 + 48LL))(v37, &v31);
        v9 = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B3,
            (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
            (const char *)(unsigned int)v10,
            (int)v31);
        }
        else
        {
          v32 = 0;
          v11 = IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(&v32, *v31);
          v14 = (*v12)(v13, &GUID_ddda6469_6c17_4be6_8c72_188063dea2ef, v11);
          v9 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B6,
              (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
              (const char *)(unsigned int)v14,
              (int)v31);
            if ( v32 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            if ( v31 )
              (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
            if ( v37 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            v27 = hObject;
            v28 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
            goto LABEL_27;
          }
          v33 = 0;
          v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v32 + 112LL))(v32, v37, &v33);
          v9 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B9,
              (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
              (const char *)(unsigned int)v15,
              (int)v31);
          }
          else
          {
            v34 = 0;
            v16 = IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(&v34, *v33);
            v19 = (*v17)(v18, &GUID_be4059cd_d6d0_40d9_999d_60c7a6340dcc, v16);
            v9 = v19;
            if ( v19 < 0 )
            {
              v30 = 444;
            }
            else
            {
              v20 = v34;
              v21 = hObject;
              v22 = *(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v34 + 48LL);
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              {
                wil::last_error_context::last_error_context((wil::last_error_context *)v35);
                CloseHandle(v21);
                wil::last_error_context::~last_error_context((wil::last_error_context *)v35);
              }
              hObject = 0;
              v19 = v22(v20, &hObject);
              v9 = v19;
              if ( v19 >= 0 )
              {
                if ( v34 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                if ( v33 )
                  (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
                if ( v32 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                if ( v31 )
                  (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
                if ( v37 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                if ( v38 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                goto LABEL_25;
              }
              v30 = 446;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v30,
              (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
              (const char *)(unsigned int)v19,
              (int)v31);
            wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(&v34);
          }
          wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(&v33);
          wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(&v32);
        }
        wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(&v31);
      }
      wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(&v37);
      wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(&v38);
    }
    else
    {
      v9 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A8,
        (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
        (const char *)0x80070057LL,
        (int)v31);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return v9;
  }
  v2 = 0;
LABEL_25:
  v23 = NtDCompositionSetBlurredWallpaperSurface(hObject, v2);
  if ( v23 < 0 )
  {
    v26 = wil::details::in1diag3::Return_NtStatus(retaddr, v24, v25, (const char *)(unsigned int)v23, (int)v31);
    v27 = hObject;
    v9 = v26;
    v28 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_27:
    if ( v28 )
      CloseHandle(v27);
    return v9;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180006670  push    rbp
0x180006672  push    rbx
0x180006673  push    rsi
0x180006674  push    rdi
0x180006675  push    r14
0x180006677  mov     rbp, rsp
0x18000667a  sub     rsp, 50h
0x18000667e  mov     [rbp+hObject], 0
0x180006686  mov     rsi, rdx
0x180006689  mov     rbx, rcx
0x18000668c  test    rcx, rcx
0x18000668f  jz      loc_18000686D
0x180006695  test    rdx, rdx
0x180006698  jz      loc_180006983
0x18000669e  mov     rax, [rcx]
0x1800066a1  lea     r8, [rbp+arg_10]
0x1800066a5  lea     rdx, _GUID_1527540d_42c7_47a6_a408_668f79a90dfb
0x1800066ac  mov     [rbp+arg_10], 0
0x1800066b4  mov     rax, [rax]
0x1800066b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066bc  mov     edi, eax
0x1800066be  test    eax, eax
0x1800066c0  js      loc_1800068C3
0x1800066c6  mov     rax, [rbx]
0x1800066c9  lea     r8, [rbp+arg_0]
0x1800066cd  lea     rdx, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x1800066d4  mov     [rbp+arg_0], 0
0x1800066dc  mov     rcx, rbx
0x1800066df  mov     rax, [rax]
0x1800066e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e7  mov     ebx, eax
0x1800066e9  test    eax, eax
0x1800066eb  js      loc_1800069B0
0x1800066f1  mov     rcx, [rbp+arg_0]
0x1800066f5  lea     rdx, [rbp+var_30]
0x1800066f9  mov     [rbp+var_30], 0
0x180006701  mov     rax, [rcx]
0x180006704  mov     rax, [rax+30h]
0x180006708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000670d  mov     ebx, eax
0x18000670f  test    eax, eax
0x180006711  js      loc_1800069CD
0x180006717  mov     r9, [rbp+var_30]
0x18000671b  lea     rcx, [rbp+var_28]
0x18000671f  mov     [rbp+var_28], 0
0x180006727  mov     rdx, [r9]
0x18000672a  call    ??$IID_PPV_ARGS_Helper@UICompositorInternal@Internal@Composition@UI@Windows@@@@YAPEAPEAXPEAPEAUICompositorInternal@Internal@Composition@UI@Windows@@@Z; IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(Windows::UI::Composition::Internal::ICompositorInternal * *)
0x18000672f  mov     r8, rax
0x180006732  mov     rcx, r9
0x180006735  mov     rax, [rdx]
0x180006738  lea     rdx, _GUID_ddda6469_6c17_4be6_8c72_188063dea2ef
0x18000673f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006744  mov     ebx, eax
0x180006746  test    eax, eax
0x180006748  js      loc_180006906
0x18000674e  mov     rcx, [rbp+var_28]
0x180006752  lea     r8, [rbp+var_20]
0x180006756  mov     rdx, [rbp+arg_0]
0x18000675a  mov     [rbp+var_20], 0
0x180006762  mov     rax, [rcx]
0x180006765  mov     rax, [rax+70h]
0x180006769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000676e  mov     ebx, eax
0x180006770  test    eax, eax
0x180006772  js      loc_1800069F2
0x180006778  mov     r9, [rbp+var_20]
0x18000677c  lea     rcx, [rbp+var_18]
0x180006780  mov     [rbp+var_18], 0
0x180006788  mov     rdx, [r9]
0x18000678b  call    ??$IID_PPV_ARGS_Helper@UICompositorInternal@Internal@Composition@UI@Windows@@@@YAPEAPEAXPEAPEAUICompositorInternal@Internal@Composition@UI@Windows@@@Z; IID_PPV_ARGS_Helper<Windows::UI::Composition::Internal::ICompositorInternal>(Windows::UI::Composition::Internal::ICompositorInternal * *)
0x180006790  mov     r8, rax
0x180006793  mov     rcx, r9
0x180006796  mov     rax, [rdx]
0x180006799  lea     rdx, _GUID_be4059cd_d6d0_40d9_999d_60c7a6340dcc
0x1800067a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a5  mov     ebx, eax
0x1800067a7  test    eax, eax
0x1800067a9  js      loc_180006A0C
0x1800067af  mov     rdi, [rbp+var_18]
0x1800067b3  mov     rbx, [rbp+hObject]
0x1800067b7  mov     rax, [rdi]
0x1800067ba  mov     r14, [rax+30h]
0x1800067be  lea     rax, [rbx-1]
0x1800067c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800067c6  jbe     loc_180006A13
0x1800067cc  lea     rdx, [rbp+hObject]
0x1800067d0  mov     [rbp+hObject], 0
0x1800067d8  mov     rcx, rdi
0x1800067db  mov     rax, r14
0x1800067de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067e3  mov     ebx, eax
0x1800067e5  test    eax, eax
0x1800067e7  js      loc_180006A33
0x1800067ed  mov     rcx, [rbp+var_18]
0x1800067f1  test    rcx, rcx
0x1800067f4  jz      short loc_180006802
0x1800067f6  mov     rax, [rcx]
0x1800067f9  mov     rax, [rax+10h]
0x1800067fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006802  mov     rcx, [rbp+var_20]
0x180006806  test    rcx, rcx
0x180006809  jz      short loc_180006817
0x18000680b  mov     rax, [rcx]
0x18000680e  mov     rax, [rax+10h]
0x180006812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006817  mov     rcx, [rbp+var_28]
0x18000681b  test    rcx, rcx
0x18000681e  jz      short loc_18000682C
0x180006820  mov     rax, [rcx]
0x180006823  mov     rax, [rax+10h]
0x180006827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000682c  mov     rcx, [rbp+var_30]
0x180006830  test    rcx, rcx
0x180006833  jz      short loc_180006841
0x180006835  mov     rax, [rcx]
0x180006838  mov     rax, [rax+10h]
0x18000683c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006841  mov     rcx, [rbp+arg_0]
0x180006845  test    rcx, rcx
0x180006848  jz      short loc_180006856
0x18000684a  mov     rax, [rcx]
0x18000684d  mov     rax, [rax+10h]
0x180006851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006856  mov     rcx, [rbp+arg_10]
0x18000685a  test    rcx, rcx
0x18000685d  jz      short loc_18000686F
0x18000685f  mov     rax, [rcx]
0x180006862  mov     rax, [rax+10h]
0x180006866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000686b  jmp     short loc_18000686F
0x18000686d  xor     esi, esi
0x18000686f  mov     rcx, [rbp+hObject]
0x180006873  mov     rdx, rsi
0x180006876  call    cs:__imp_NtDCompositionSetBlurredWallpaperSurface
0x18000687c  test    eax, eax
0x18000687e  jns     short loc_1800068AD
0x180006880  mov     rcx, [rbp+28h]; this
0x180006884  mov     r9d, eax; char *
0x180006887  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000688c  mov     rcx, [rbp+hObject]; hObject
0x180006890  mov     ebx, eax
0x180006892  lea     rdx, [rcx-1]
0x180006896  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000689a  jbe     loc_1800069E7
0x1800068a0  mov     eax, ebx
0x1800068a2  add     rsp, 50h
0x1800068a6  pop     r14
0x1800068a8  pop     rdi
0x1800068a9  pop     rsi
0x1800068aa  pop     rbx
0x1800068ab  pop     rbp
0x1800068ac  retn
0x1800068ad  mov     rcx, [rbp+hObject]; hObject
0x1800068b1  lea     rax, [rcx-1]
0x1800068b5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800068b9  jbe     loc_180006A8F
0x1800068bf  xor     eax, eax
0x1800068c1  jmp     short loc_1800068A2
0x1800068c3  mov     rcx, [rbp+28h]; this
0x1800068c7  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x1800068ce  mov     r9d, edi; char *
0x1800068d1  mov     edx, 1ACh; void *
0x1800068d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800068db  mov     rcx, [rbp+arg_10]
0x1800068df  test    rcx, rcx
0x1800068e2  jz      short loc_1800068F0
0x1800068e4  mov     rdx, [rcx]
0x1800068e7  mov     rax, [rdx+10h]
0x1800068eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f0  mov     rcx, [rbp+hObject]; hObject
0x1800068f4  lea     rax, [rcx-1]
0x1800068f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800068fc  jbe     loc_1800069A5
0x180006902  mov     eax, edi
0x180006904  jmp     short loc_1800068A2
0x180006906  mov     rcx, [rbp+28h]; this
0x18000690a  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180006911  mov     r9d, ebx; char *
0x180006914  mov     edx, 1B6h; void *
0x180006919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000691e  mov     rcx, [rbp+var_28]
0x180006922  test    rcx, rcx
0x180006925  jz      short loc_180006933
0x180006927  mov     rdx, [rcx]
0x18000692a  mov     rax, [rdx+10h]
0x18000692e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006933  mov     rcx, [rbp+var_30]
0x180006937  test    rcx, rcx
0x18000693a  jz      short loc_180006948
0x18000693c  mov     rax, [rcx]
0x18000693f  mov     rax, [rax+10h]
0x180006943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006948  mov     rcx, [rbp+arg_0]
0x18000694c  test    rcx, rcx
0x18000694f  jz      short loc_18000695D
0x180006951  mov     rax, [rcx]
0x180006954  mov     rax, [rax+10h]
0x180006958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000695d  mov     rcx, [rbp+arg_10]
0x180006961  test    rcx, rcx
0x180006964  jz      short loc_180006972
0x180006966  mov     rax, [rcx]
0x180006969  mov     rax, [rax+10h]
0x18000696d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006972  mov     rcx, [rbp+hObject]
0x180006976  lea     rax, [rcx-1]
0x18000697a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000697e  jmp     loc_18000689A
0x180006983  mov     rcx, [rbp+28h]; this
0x180006987  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x18000698e  mov     ebx, 80070057h
0x180006993  mov     edx, 1A8h; void *
0x180006998  mov     r9d, ebx; char *
0x18000699b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069a0  jmp     loc_180006A81
0x1800069a5  call    cs:__imp_CloseHandle
0x1800069ab  jmp     loc_180006902
0x1800069b0  mov     rcx, [rbp+28h]; this
0x1800069b4  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x1800069bb  mov     r9d, eax; char *
0x1800069be  mov     edx, 1B0h; void *
0x1800069c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069c8  jmp     loc_180006A6F
0x1800069cd  mov     rcx, [rbp+28h]; this
0x1800069d1  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x1800069d8  mov     r9d, eax; char *
0x1800069db  mov     edx, 1B3h; void *
0x1800069e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069e5  jmp     short loc_180006A66
0x1800069e7  call    cs:__imp_CloseHandle
0x1800069ed  jmp     loc_1800068A0
0x1800069f2  mov     rcx, [rbp+28h]; this
0x1800069f6  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x1800069fd  mov     r9d, eax; char *
0x180006a00  mov     edx, 1B9h; void *
0x180006a05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a0a  jmp     short loc_180006A54
0x180006a0c  mov     edx, 1BCh
0x180006a11  jmp     short loc_180006A38
0x180006a13  lea     rcx, [rbp+var_10]; this
0x180006a17  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006a1c  mov     rcx, rbx; hObject
0x180006a1f  call    cs:__imp_CloseHandle
0x180006a25  lea     rcx, [rbp+var_10]; this
0x180006a29  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006a2e  jmp     loc_1800067CC
0x180006a33  mov     edx, 1BEh; void *
0x180006a38  mov     rcx, [rbp+28h]; this
0x180006a3c  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180006a43  mov     r9d, eax; char *
0x180006a46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a4b  lea     rcx, [rbp+var_18]
0x180006a4f  call    ??1?$com_ptr_t@UICompositionObject@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(void)
0x180006a54  lea     rcx, [rbp+var_20]
0x180006a58  call    ??1?$com_ptr_t@UICompositionObject@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(void)
0x180006a5d  lea     rcx, [rbp+var_28]
0x180006a61  call    ??1?$com_ptr_t@UICompositionObject@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(void)
0x180006a66  lea     rcx, [rbp+var_30]
0x180006a6a  call    ??1?$com_ptr_t@UICompositionObject@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(void)
0x180006a6f  lea     rcx, [rbp+arg_0]
0x180006a73  call    ??1?$com_ptr_t@UICompositionObject@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(void)
0x180006a78  lea     rcx, [rbp+arg_10]
0x180006a7c  call    ??1?$com_ptr_t@UICompositionObject@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionObject,wil::err_returncode_policy>(void)
0x180006a81  lea     rcx, [rbp+hObject]
0x180006a85  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006a8a  jmp     loc_1800068A0
0x180006a8f  call    cs:__imp_CloseHandle
0x180006a95  jmp     loc_1800068BF
```
