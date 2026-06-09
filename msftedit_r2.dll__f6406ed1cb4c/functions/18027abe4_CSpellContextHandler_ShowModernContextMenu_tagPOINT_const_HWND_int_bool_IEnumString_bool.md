# CSpellContextHandler::ShowModernContextMenu(tagPOINT const *,HWND__ *,int,bool,IEnumString *,bool)

- ea: `0x18027abe4`
- end: `0x18027b2a6`
- name: `?ShowModernContextMenu@CSpellContextHandler@@AEAAJPEBUtagPOINT@@PEAUHWND__@@H_NPEAUIEnumString@@2@Z`
- size: `1730`
- prototype: `__int64 __usercall@<rax>(CSpellContextHandler *__hidden this@<rcx>, const struct tagPOINT *@<rdx>, HWND@<r8>, int@<r9d>, bool, struct IEnumString *, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18027a7a8`

## callees

- `0x18006ad18`
- `0x18006af48`
- `0x180130d9c`
- `0x18013ce80`
- `0x18013d268`
- `0x180278174`
- `0x180278274`
- `0x1802782c4`
- `0x180278314`
- `0x1802784b0`
- `0x1802785e4`
- `0x1802786dc`
- `0x180279218`
- `0x18027942c`
- `0x180279718`
- `0x180279b64`
- `0x180279d84`
- `0x18027abe4`
- `0x18027b7a0`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18027b255`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18027b255`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18027af94`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18027af94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18027b089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18027b089`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::ShowModernContextMenu(
        CSpellContextHandler *this,
        const struct tagPOINT *a2,
        HWND a3,
        int a4,
        bool a5,
        struct IEnumString *a6,
        bool a7)
{
  __int64 *v7; // r15
  _QWORD *v11; // rax
  HRESULT ActivationFactory; // edi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int inserted; // eax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, __int64 *); // rbx
  __int64 v22; // rcx
  unsigned int v23; // r14d
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, double *); // rbx
  double v26; // rdi
  __int64 (__fastcall *v27)(_QWORD, __int64 *); // rbx
  __int64 v28; // rdx
  __int64 v29; // r8
  HRESULT v30; // eax
  HRESULT v31; // eax
  HSTRING v32; // rbx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64 *); // rbx
  __int64 v35; // rax
  float v36; // xmm0_4
  float v37; // xmm0_4
  __int64 v38; // rax
  CSpellingCommandHandler *v39; // rax
  CSpellingCommandHandler *v40; // r15
  HRESULT (__stdcall *Clone)(IEnumString *, IEnumString **); // rbx
  __int64 v43; // [rsp+30h] [rbp-81h] BYREF
  __int64 v44; // [rsp+38h] [rbp-79h] BYREF
  HSTRING string; // [rsp+40h] [rbp-71h] BYREF
  double v46; // [rsp+48h] [rbp-69h] BYREF
  _QWORD v47[2]; // [rsp+50h] [rbp-61h] BYREF
  unsigned __int16 *v48[2]; // [rsp+60h] [rbp-51h] BYREF
  HWND hWnd; // [rsp+70h] [rbp-41h] BYREF
  __int64 v50; // [rsp+78h] [rbp-39h] BYREF
  __int64 v51; // [rsp+80h] [rbp-31h] BYREF
  __int64 v52; // [rsp+88h] [rbp-29h] BYREF
  HSTRING v53[2]; // [rsp+90h] [rbp-21h] BYREF

  v7 = (__int64 *)((char *)this + 144);
  v48[0] = (unsigned __int16 *)a2;
  if ( *((_QWORD *)this + 18) )
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 144);
  v50 = 0;
  v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(v53, L"Windows.UI.Popups.PopupMenu");
  ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>(
                        *v11,
                        &v50);
  if ( ActivationFactory < 0 )
    goto LABEL_74;
  v52 = 0;
  if ( !*((_BYTE *)this + 158) )
  {
    ActivationFactory = Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>::As<IInitializeWithWindow>(&v50, &v52);
    if ( ActivationFactory < 0 )
      goto LABEL_73;
  }
  v13 = v50;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v7);
  ActivationFactory = v14(v13, v7);
  if ( ActivationFactory < 0 )
    goto LABEL_73;
  if ( a4 == -1 )
    inserted = a5
             ? CSpellContextHandler::InsertRepeatedWordCommands(this, 0, a7)
             : CSpellContextHandler::InsertAlternates(this, 0, a6, a7);
  else
    inserted = CSpellContextHandler::InsertACCommands(this, 0, *((const unsigned __int16 **)this + 2), a7);
  ActivationFactory = inserted;
  if ( inserted < 0 )
    goto LABEL_73;
  v16 = *((_QWORD *)this + 3);
  v17 = *((_QWORD *)this + 1);
  v18 = *(_QWORD *)this;
  *(_OWORD *)v53 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, HSTRING *))(**(_QWORD **)(v16 + 72) + 216LL))(
                        *(_QWORD *)(v16 + 72),
                        v18,
                        v17,
                        v53);
  if ( ActivationFactory < 0 )
    goto LABEL_73;
  v19 = *((_QWORD *)this + 3);
  v51 = 0;
  v20 = *(_QWORD *)(v19 + 72);
  v21 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 200LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  if ( v21(v20, &v51) < 0 )
  {
    if ( *((_BYTE *)this + 158) )
    {
      string = 0;
      v46 = 0.0;
      ActivationFactory = Microsoft::WRL::Wrappers::HString::Set(
                            &string,
                            L"Windows.Graphics.Display.DisplayInformation",
                            0x2Bu);
      if ( ActivationFactory >= 0 )
      {
        v44 = 0;
        v32 = string;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
        ActivationFactory = RoGetActivationFactory(v32, &GUID_c6a02a6c_d452_44dc_ba07_96f3c6adf9d1, &v44);
        if ( ActivationFactory >= 0 )
        {
          v33 = v44;
          v43 = 0;
          v34 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          ActivationFactory = v34(v33, &v43);
          if ( ActivationFactory >= 0 )
          {
            v47[0] = 0;
            ActivationFactory = Microsoft::WRL::ComPtr<Windows::Graphics::Display::IDisplayInformation>::As<Windows::Graphics::Display::IDisplayInformation2>(
                                  &v43,
                                  v47);
            if ( ActivationFactory >= 0 )
              ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, double *))(*(_QWORD *)v47[0] + 48LL))(v47[0], &v46);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
      }
      v48[1] = (unsigned __int16 *)0x4000000040000000LL;
      v35 = HIDWORD(*(_QWORD *)v48[0]);
      v36 = (double)(int)*(_QWORD *)v48[0] / v46;
      v37 = v36 - 1.0;
      *(float *)v48 = v37;
      *((float *)v48 + 1) = (float)((double)(int)v35 / v46) - 1.0;
      WindowsDeleteString(string);
    }
    else
    {
      ActivationFactory = 0;
      v48[0] = (unsigned __int16 *)v53[0];
      *(float *)&v48[1] = *(float *)&v53[1] - *(float *)v53;
      *((float *)&v48[1] + 1) = *((float *)&v53[1] + 1) - *((float *)v53 + 1);
    }
    v38 = *((_QWORD *)this + 3);
    hWnd = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, HWND, HWND *))(**(_QWORD **)(v38 + 72) + 296LL))(
           *(_QWORD *)(v38 + 72),
           a3,
           &hWnd) )
    {
      a3 = hWnd;
    }
    if ( !*((_BYTE *)this + 158) )
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v52 + 24LL))(v52, a3);
    if ( ActivationFactory >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 72LL) + 336LL))(
        *(_QWORD *)(*((_QWORD *)this + 3) + 72LL),
        0);
      v43 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, __int64 *))(*(_QWORD *)v50 + 64LL))(
                            v50,
                            v48,
                            &v43);
      if ( ActivationFactory >= 0 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 72LL) + 304LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 72LL)) )
        {
          ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(v43);
          if ( ActivationFactory >= 0 && !*((_BYTE *)this + 157) )
            CSpellContextHandler::TelemetryLogDismissAlternates(this, a6);
        }
        else
        {
          v39 = (CSpellingCommandHandler *)operator new(0x20u);
          v40 = CSpellingCommandHandler::CSpellingCommandHandler(v39, this, 0);
          if ( a6 )
          {
            Clone = a6->lpVtbl->Clone;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 56);
            ((void (__fastcall *)(struct IEnumString *, char *))Clone)(a6, (char *)this + 56);
          }
          else
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 56);
          }
          if ( v40 )
          {
            (*(void (__fastcall **)(CSpellingCommandHandler *))(*(_QWORD *)v40 + 8LL))(v40);
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 48LL))(v43, (__int64)v40 + 8);
            *((_BYTE *)this + 155) = 1;
            (*(void (__fastcall **)(CSpellingCommandHandler *))(*(_QWORD *)v40 + 16LL))(v40);
          }
        }
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
    }
    if ( hWnd )
      DestroyWindow(hWnd);
    goto LABEL_72;
  }
  v44 = 0;
  ActivationFactory = Microsoft::WRL::ComPtr<IScrollableContextMenu>::As<IScrollableContextMenu2>(&v51, &v44);
  if ( ActivationFactory < 0 )
    goto LABEL_41;
  v22 = *v7;
  LODWORD(hWnd) = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v22 + 56LL))(v22, &hWnd);
  if ( ActivationFactory < 0 )
    goto LABEL_41;
  v23 = 0;
  while ( v23 < (unsigned int)hWnd )
  {
    v24 = *v7;
    v46 = 0.0;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    ActivationFactory = v25(v24, v23, &v46);
    if ( ActivationFactory >= 0 )
    {
      v47[0] = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(double, _QWORD *))(**(_QWORD **)&v46 + 48LL))(
                            COERCE_DOUBLE(*(_QWORD *)&v46),
                            v47);
      if ( ActivationFactory >= 0 )
      {
        v48[0] = 0;
        ActivationFactory = Windows::Internal::String::GetLpcwstr(
                              (Windows::Internal::String *)v47,
                              (const unsigned __int16 **)v48);
        if ( ActivationFactory >= 0 )
        {
          v26 = v46;
          v43 = 0;
          v27 = *(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)&v46 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          ActivationFactory = v27(*(_QWORD *)&v26, &v43);
          if ( ActivationFactory >= 0 )
          {
            v29 = 0xFFFFFFFFLL;
            LODWORD(string) = -1;
            if ( v43 )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64))(*(_QWORD *)v43 + 96LL))(
                                    v43,
                                    &string,
                                    0xFFFFFFFFLL);
              if ( ActivationFactory >= 0 )
              {
                v29 = (unsigned int)string;
                goto LABEL_26;
              }
            }
            else
            {
LABEL_26:
              if ( (_DWORD)v29 != -1 || *v48[0] )
                v30 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v44 + 24LL))(v44, v48[0]);
              else
                v30 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int16 *))(*(_QWORD *)v44 + 40LL))(
                        v44,
                        v28,
                        v29,
                        v48[0]);
              ActivationFactory = v30;
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        }
      }
      Windows::Internal::String::~String((Windows::Internal::String *)v47);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    ++v23;
    if ( ActivationFactory < 0 )
      goto LABEL_41;
  }
  LODWORD(string) = -1;
  v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, HSTRING *))(*(_QWORD *)v44 + 32LL))(
          v44,
          (unsigned int)(int)*(float *)v53,
          (unsigned int)(int)*((float *)&v53[1] + 1),
          &string);
  ActivationFactory = v31;
  if ( *((_BYTE *)this + 159) )
  {
    if ( !v31 )
      ActivationFactory = CSpellContextHandler::Invoke(this, (UINT)string, 0);
    if ( ActivationFactory >= 0 && !*((_BYTE *)this + 157) )
      CSpellContextHandler::TelemetryLogDismissAlternates(this, a6);
  }
LABEL_41:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
LABEL_72:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
LABEL_73:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
LABEL_74:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18027abe4  mov     [rsp-8+arg_18], rbx
0x18027abe9  push    rbp
0x18027abea  push    rsi
0x18027abeb  push    rdi
0x18027abec  push    r12
0x18027abee  push    r13
0x18027abf0  push    r14
0x18027abf2  push    r15
0x18027abf4  lea     rbp, [rsp-0Fh]
0x18027abf9  sub     rsp, 0C0h
0x18027ac00  mov     rax, cs:__security_cookie
0x18027ac07  xor     rax, rsp
0x18027ac0a  mov     [rbp+3Fh+var_40], rax
0x18027ac0e  mov     r12, [rbp+3Fh+arg_28]
0x18027ac12  lea     r15, [rcx+90h]
0x18027ac19  xor     ebx, ebx
0x18027ac1b  mov     [rbp+3Fh+var_90], rdx
0x18027ac1f  mov     r14d, r9d
0x18027ac22  mov     r13, r8
0x18027ac25  mov     rsi, rcx
0x18027ac28  cmp     [r15], rbx
0x18027ac2b  jz      short loc_18027AC35
0x18027ac2d  mov     rcx, r15
0x18027ac30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027ac35  lea     rdx, ?RuntimeClass_Windows_UI_Popups_PopupMenu@@3QBGB; "Windows.UI.Popups.PopupMenu"
0x18027ac3c  mov     [rbp+3Fh+var_78], rbx
0x18027ac40  lea     rcx, [rbp+3Fh+var_60]; string
0x18027ac44  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x18027ac49  lea     rdx, [rbp+3Fh+var_78]
0x18027ac4d  mov     rcx, [rax]
0x18027ac50  call    ??$ActivateInstance@V?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>)
0x18027ac55  mov     edi, eax
0x18027ac57  test    eax, eax
0x18027ac59  js      loc_18027B273
0x18027ac5f  mov     [rbp+3Fh+var_68], rbx
0x18027ac63  cmp     [rsi+9Eh], bl
0x18027ac69  jnz     short loc_18027AC82
0x18027ac6b  lea     rdx, [rbp+3Fh+var_68]
0x18027ac6f  lea     rcx, [rbp+3Fh+var_78]
0x18027ac73  call    ??$As@UIInitializeWithWindow@@@?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInitializeWithWindow@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>::As<IInitializeWithWindow>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInitializeWithWindow>>)
0x18027ac78  mov     edi, eax
0x18027ac7a  test    eax, eax
0x18027ac7c  js      loc_18027B26A
0x18027ac82  mov     rdi, [rbp+3Fh+var_78]
0x18027ac86  mov     rcx, r15
0x18027ac89  mov     rax, [rdi]
0x18027ac8c  mov     rbx, [rax+30h]
0x18027ac90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027ac95  mov     rdx, r15
0x18027ac98  mov     rcx, rdi
0x18027ac9b  mov     rax, rbx
0x18027ac9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027aca3  mov     edi, eax
0x18027aca5  test    eax, eax
0x18027aca7  js      loc_18027B26A
0x18027acad  xor     edx, edx; HMENU
0x18027acaf  mov     rcx, rsi; this
0x18027acb2  cmp     r14d, 0FFFFFFFFh
0x18027acb6  jz      short loc_18027ACC7
0x18027acb8  mov     r9b, [rbp+3Fh+arg_30]; bool
0x18027acbc  mov     r8, [rsi+10h]; unsigned __int16 *
0x18027acc0  call    ?InsertACCommands@CSpellContextHandler@@AEAAJPEAUHMENU__@@PEBG_N@Z; CSpellContextHandler::InsertACCommands(HMENU__ *,ushort const *,bool)
0x18027acc5  jmp     short loc_18027ACE4
0x18027acc7  cmp     [rbp+3Fh+arg_20], 0
0x18027accb  jz      short loc_18027ACD8
0x18027accd  mov     r8b, [rbp+3Fh+arg_30]; bool
0x18027acd1  call    ?InsertRepeatedWordCommands@CSpellContextHandler@@AEAAJPEAUHMENU__@@_N@Z; CSpellContextHandler::InsertRepeatedWordCommands(HMENU__ *,bool)
0x18027acd6  jmp     short loc_18027ACE4
0x18027acd8  mov     r9b, [rbp+3Fh+arg_30]; bool
0x18027acdc  mov     r8, r12; struct IEnumString *
0x18027acdf  call    ?InsertAlternates@CSpellContextHandler@@AEAAJPEAUHMENU__@@PEAUIEnumString@@_N@Z; CSpellContextHandler::InsertAlternates(HMENU__ *,IEnumString *,bool)
0x18027ace4  mov     edi, eax
0x18027ace6  test    eax, eax
0x18027ace8  js      loc_18027B26A
0x18027acee  mov     rax, [rsi+18h]
0x18027acf2  lea     r9, [rbp+3Fh+var_60]
0x18027acf6  mov     r8, [rsi+8]
0x18027acfa  xorps   xmm0, xmm0
0x18027acfd  mov     rdx, [rsi]
0x18027ad00  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x18027ad04  mov     rcx, [rax+48h]
0x18027ad08  mov     rax, [rcx]
0x18027ad0b  mov     rax, [rax+0D8h]
0x18027ad12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027ad17  mov     edi, eax
0x18027ad19  test    eax, eax
0x18027ad1b  js      loc_18027B26A
0x18027ad21  mov     rax, [rsi+18h]
0x18027ad25  lea     rcx, [rbp+3Fh+var_70]
0x18027ad29  mov     [rbp+3Fh+var_70], 0
0x18027ad31  mov     rdi, [rax+48h]
0x18027ad35  mov     rax, [rdi]
0x18027ad38  mov     rbx, [rax+0C8h]
0x18027ad3f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027ad44  lea     rdx, [rbp+3Fh+var_70]
0x18027ad48  mov     rcx, rdi
0x18027ad4b  mov     rax, rbx
0x18027ad4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027ad53  xor     ebx, ebx
0x18027ad55  test    eax, eax
0x18027ad57  js      loc_18027AF3D
0x18027ad5d  lea     rdx, [rbp+3Fh+var_B8]
0x18027ad61  mov     [rbp+3Fh+var_B8], rbx
0x18027ad65  lea     rcx, [rbp+3Fh+var_70]
0x18027ad69  call    ??$As@UIScrollableContextMenu2@@@?$ComPtr@UIScrollableContextMenu@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIScrollableContextMenu2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IScrollableContextMenu>::As<IScrollableContextMenu2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IScrollableContextMenu2>>)
0x18027ad6e  mov     edi, eax
0x18027ad70  test    eax, eax
0x18027ad72  js      loc_18027AF2F
0x18027ad78  mov     rcx, [r15]
0x18027ad7b  lea     rdx, [rbp+3Fh+hWnd]
0x18027ad7f  mov     dword ptr [rbp+3Fh+hWnd], ebx
0x18027ad82  mov     rax, [rcx]
0x18027ad85  mov     rax, [rax+38h]
0x18027ad89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027ad8e  mov     edi, eax
0x18027ad90  test    eax, eax
0x18027ad92  js      loc_18027AF2F
0x18027ad98  mov     r14d, ebx
0x18027ad9b  or      r13d, 0FFFFFFFFh
0x18027ad9f  cmp     r14d, dword ptr [rbp+3Fh+hWnd]
0x18027ada3  jnb     loc_18027AED7
0x18027ada9  mov     rdi, [r15]
0x18027adac  lea     rcx, [rbp+3Fh+var_A8]
0x18027adb0  mov     [rbp+3Fh+var_A8], rbx
0x18027adb4  mov     rax, [rdi]
0x18027adb7  mov     rbx, [rax+30h]
0x18027adbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027adc0  lea     r8, [rbp+3Fh+var_A8]
0x18027adc4  mov     edx, r14d
0x18027adc7  mov     rcx, rdi
0x18027adca  mov     rax, rbx
0x18027adcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027add2  xor     ebx, ebx
0x18027add4  mov     edi, eax
0x18027add6  test    eax, eax
0x18027add8  js      loc_18027AEC1
0x18027adde  mov     rcx, [rbp+3Fh+var_A8]
0x18027ade2  lea     rdx, [rbp+3Fh+var_A0]
0x18027ade6  mov     [rbp+3Fh+var_A0], rbx
0x18027adea  mov     rax, [rcx]
0x18027aded  mov     rax, [rax+30h]
0x18027adf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027adf6  mov     edi, eax
0x18027adf8  test    eax, eax
0x18027adfa  js      loc_18027AEB8
0x18027ae00  lea     rdx, [rbp+3Fh+var_90]; unsigned __int16 **
0x18027ae04  mov     [rbp+3Fh+var_90], rbx
0x18027ae08  lea     rcx, [rbp+3Fh+var_A0]; this
0x18027ae0c  call    ?GetLpcwstr@String@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::String::GetLpcwstr(ushort const * *)
0x18027ae11  mov     edi, eax
0x18027ae13  test    eax, eax
0x18027ae15  js      loc_18027AEB8
0x18027ae1b  mov     rdi, [rbp+3Fh+var_A8]
0x18027ae1f  lea     rcx, [rsp+0F0h+var_C0]
0x18027ae24  mov     [rsp+0F0h+var_C0], rbx
0x18027ae29  mov     rax, [rdi]
0x18027ae2c  mov     rbx, [rax+50h]
0x18027ae30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027ae35  lea     rdx, [rsp+0F0h+var_C0]
0x18027ae3a  mov     rcx, rdi
0x18027ae3d  mov     rax, rbx
0x18027ae40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027ae45  xor     ebx, ebx
0x18027ae47  mov     edi, eax
0x18027ae49  test    eax, eax
0x18027ae4b  js      short loc_18027AEAE
0x18027ae4d  mov     rcx, [rsp+0F0h+var_C0]
0x18027ae52  mov     r8d, r13d
0x18027ae55  mov     dword ptr [rbp+3Fh+string], r13d
0x18027ae59  test    rcx, rcx
0x18027ae5c  jz      short loc_18027AE78
0x18027ae5e  mov     rax, [rcx]
0x18027ae61  lea     rdx, [rbp+3Fh+string]
0x18027ae65  mov     rax, [rax+60h]
0x18027ae69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027ae6e  mov     edi, eax
0x18027ae70  test    eax, eax
0x18027ae72  js      short loc_18027AEAE
0x18027ae74  mov     r8d, dword ptr [rbp+3Fh+string]
0x18027ae78  mov     r9, [rbp+3Fh+var_90]
0x18027ae7c  cmp     r8d, r13d
0x18027ae7f  jnz     short loc_18027AE99
0x18027ae81  cmp     [r9], bx
0x18027ae85  jnz     short loc_18027AE99
0x18027ae87  mov     rcx, [rbp+3Fh+var_B8]
0x18027ae8b  mov     rax, [rcx]
0x18027ae8e  mov     rax, [rax+28h]
0x18027ae92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027ae97  jmp     short loc_18027AEAC
0x18027ae99  mov     rcx, [rbp+3Fh+var_B8]
0x18027ae9d  mov     rdx, r9
0x18027aea0  mov     rax, [rcx]
0x18027aea3  mov     rax, [rax+18h]
0x18027aea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027aeac  mov     edi, eax
0x18027aeae  lea     rcx, [rsp+0F0h+var_C0]
0x18027aeb3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027aeb8  lea     rcx, [rbp+3Fh+var_A0]; this
0x18027aebc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18027aec1  lea     rcx, [rbp+3Fh+var_A8]
0x18027aec5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027aeca  inc     r14d
0x18027aecd  test    edi, edi
0x18027aecf  jns     loc_18027AD9F
0x18027aed5  jmp     short loc_18027AF2F
0x18027aed7  mov     rcx, [rbp+3Fh+var_B8]
0x18027aedb  lea     r9, [rbp+3Fh+string]
0x18027aedf  cvttss2si r8d, dword ptr [rbp+3Fh+var_60+0Ch]
0x18027aee5  mov     dword ptr [rbp+3Fh+string], r13d
0x18027aee9  mov     rax, [rcx]
0x18027aeec  mov     rax, [rax+20h]
0x18027aef0  cvttss2si edx, dword ptr [rbp+3Fh+var_60]
0x18027aef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027aefa  mov     edi, eax
0x18027aefc  cmp     [rsi+9Fh], bl
0x18027af02  jz      short loc_18027AF2F
0x18027af04  test    eax, eax
0x18027af06  jnz     short loc_18027AF18
0x18027af08  mov     edx, dword ptr [rbp+3Fh+string]; item
0x18027af0b  xor     r8d, r8d; hmenu
0x18027af0e  mov     rcx, rsi; this
0x18027af11  call    ?Invoke@CSpellContextHandler@@QEAAJHPEAUHMENU__@@@Z; CSpellContextHandler::Invoke(int,HMENU__ *)
0x18027af16  mov     edi, eax
0x18027af18  test    edi, edi
0x18027af1a  js      short loc_18027AF2F
0x18027af1c  cmp     [rsi+9Dh], bl
0x18027af22  jnz     short loc_18027AF2F
0x18027af24  mov     rdx, r12; struct IEnumString *
0x18027af27  mov     rcx, rsi; this
0x18027af2a  call    ?TelemetryLogDismissAlternates@CSpellContextHandler@@AEAAXPEAUIEnumString@@@Z; CSpellContextHandler::TelemetryLogDismissAlternates(IEnumString *)
0x18027af2f  lea     rcx, [rbp+3Fh+var_B8]
0x18027af33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027af38  jmp     loc_18027B261
0x18027af3d  cmp     [rsi+9Eh], bl
0x18027af43  jz      loc_18027B097
0x18027af49  xorps   xmm0, xmm0
0x18027af4c  mov     [rbp+3Fh+string], rbx
0x18027af50  mov     r8d, 2Bh ; '+'; unsigned int
0x18027af56  movsd   [rbp+3Fh+var_A8], xmm0
0x18027af5b  lea     rdx, ?RuntimeClass_Windows_Graphics_Display_DisplayInformation@@3QBGB; "Windows.Graphics.Display.DisplayInforma"...
0x18027af62  lea     rcx, [rbp+3Fh+string]; this
0x18027af66  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18027af6b  mov     edi, eax
0x18027af6d  test    eax, eax
0x18027af6f  js      loc_18027B024
0x18027af75  mov     [rbp+3Fh+var_B8], rbx
0x18027af79  lea     rcx, [rbp+3Fh+var_B8]
0x18027af7d  mov     rbx, [rbp+3Fh+string]
0x18027af81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027af86  lea     r8, [rbp+3Fh+var_B8]
0x18027af8a  mov     rcx, rbx
0x18027af8d  lea     rdx, _GUID_c6a02a6c_d452_44dc_ba07_96f3c6adf9d1
0x18027af94  call    cs:__imp_RoGetActivationFactory
0x18027af9b  nop     dword ptr [rax+rax+00h]
0x18027afa0  xor     ebx, ebx
0x18027afa2  mov     edi, eax
0x18027afa4  test    eax, eax
0x18027afa6  js      short loc_18027B01B
0x18027afa8  mov     rdi, [rbp+3Fh+var_B8]
0x18027afac  lea     rcx, [rsp+0F0h+var_C0]
0x18027afb1  mov     [rsp+0F0h+var_C0], rbx
0x18027afb6  mov     rax, [rdi]
0x18027afb9  mov     rbx, [rax+30h]
0x18027afbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027afc2  lea     rdx, [rsp+0F0h+var_C0]
0x18027afc7  mov     rcx, rdi
0x18027afca  mov     rax, rbx
0x18027afcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027afd2  xor     ebx, ebx
0x18027afd4  mov     edi, eax
0x18027afd6  test    eax, eax
0x18027afd8  js      short loc_18027B011
0x18027afda  lea     rdx, [rbp+3Fh+var_A0]
0x18027afde  mov     [rbp+3Fh+var_A0], rbx
0x18027afe2  lea     rcx, [rsp+0F0h+var_C0]
0x18027afe7  call    ??$As@UIDisplayInformation2@Display@Graphics@Windows@@@?$ComPtr@UIDisplayInformation@Display@Graphics@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDisplayInformation2@Display@Graphics@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Display::IDisplayInformation>::As<Windows::Graphics::Display::IDisplayInformation2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Graphics::Display::IDisplayInformation2>>)
0x18027afec  mov     edi, eax
0x18027afee  test    eax, eax
0x18027aff0  js      short loc_18027B008
0x18027aff2  mov     rcx, [rbp+3Fh+var_A0]
0x18027aff6  lea     rdx, [rbp+3Fh+var_A8]
0x18027affa  mov     rax, [rcx]
0x18027affd  mov     rax, [rax+30h]
0x18027b001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027b006  mov     edi, eax
0x18027b008  lea     rcx, [rbp+3Fh+var_A0]
0x18027b00c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027b011  lea     rcx, [rsp+0F0h+var_C0]
0x18027b016  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027b01b  lea     rcx, [rbp+3Fh+var_B8]
0x18027b01f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027b024  mov     rax, [rbp+3Fh+var_90]
0x18027b028  xorps   xmm0, xmm0
0x18027b02b  mov     rcx, [rbp+3Fh+string]; string
0x18027b02f  mov     dword ptr [rbp+3Fh+var_90+8], 40000000h
0x18027b036  mov     dword ptr [rbp+3Fh+var_90+0Ch], 40000000h
0x18027b03d  mov     rax, [rax]
0x18027b040  cvtsi2sd xmm0, eax
0x18027b044  shr     rax, 20h
0x18027b048  divsd   xmm0, [rbp+3Fh+var_A8]
  ... truncated ...
```
