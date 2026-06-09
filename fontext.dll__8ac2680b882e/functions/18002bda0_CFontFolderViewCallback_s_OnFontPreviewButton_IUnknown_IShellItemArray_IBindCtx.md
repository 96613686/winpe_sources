# CFontFolderViewCallback::s_OnFontPreviewButton(IUnknown *,IShellItemArray *,IBindCtx *)

- ea: `0x18002bda0`
- end: `0x18002c0ef`
- name: `?s_OnFontPreviewButton@CFontFolderViewCallback@@SAJPEAUIUnknown@@PEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `847`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f518`
- `0x180014144`
- `0x18001914c`
- `0x180022c58`
- `0x18002976c`
- `0x18002a408`
- `0x18002a4fc`
- `0x18002a614`
- `0x18002a7cc`
- `0x18002ab80`
- `0x18002b0dc`
- `0x18002bda0`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c089`

## string_xrefs

- `0x18002be0b`: `shell\osshell\fontfldr\fontext2\dll\view.cpp`
- `0x18002be4d`: `shell\osshell\fontfldr\fontext2\dll\view.cpp`
- `0x18002be6e`: `shell\osshell\fontfldr\fontext2\dll\view.cpp`

## pseudocode

```c
__int64 __fastcall CFontFolderViewCallback::s_OnFontPreviewButton(
        struct IUnknown *a1,
        struct IShellItemArray *a2,
        struct IBindCtx *a3)
{
  struct IShellItemArrayVtbl *lpVtbl; // rax
  int v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // esi
  unsigned int v12; // r14d
  struct IShellItemArrayVtbl *v13; // rax
  int v14; // eax
  int PidlFromShellItem; // eax
  int NumberOfFontsInFamily; // eax
  unsigned int v17; // esi
  struct IShellItemArrayVtbl *v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  struct _ITEMIDLIST *v21; // r14
  int IsFolder; // eax
  struct IUnknownVtbl *v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  int v27; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  struct IShellItem *v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v30; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v31[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v31,
    "OnFontPreviewButton",
    a3);
  v31[0] = &FontFldrTraceLoggingTelemetry::OnFontPreviewButton::`vftable';
  FontFldrTraceLoggingTelemetry::OnFontPreviewButton::StartActivity((FontFldrTraceLoggingTelemetry::OnFontPreviewButton *)v31);
  if ( !a2 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
      (const char *)0x80070057LL,
      v27);
LABEL_22:
    v7 = -2147467259;
    goto LABEL_41;
  }
  lpVtbl = a2->lpVtbl;
  v27 = 0;
  v6 = ((__int64 (__fastcall *)(struct IShellItemArray *, int *))lpVtbl->GetCount)(a2, &v27);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (unsigned int)v6;
    v9 = 233;
    goto LABEL_5;
  }
  v10 = v27;
  v11 = 0;
  v12 = 0;
  if ( !v27 )
    goto LABEL_21;
  do
  {
    if ( v7 < 0 )
      goto LABEL_16;
    v13 = a2->lpVtbl;
    v29 = 0;
    v14 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))v13->GetItemAt)(
            a2,
            v12,
            &v29);
    v7 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF2,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
        (const char *)(unsigned int)v14,
        v27);
      goto LABEL_14;
    }
    pv = 0;
    PidlFromShellItem = GetPidlFromShellItem(v29, (struct _ITEMIDLIST **)&pv);
    v7 = PidlFromShellItem;
    if ( PidlFromShellItem >= 0 )
    {
      if ( (unsigned int)FID_IsFolder((const struct _ITEMIDLIST *)pv) )
      {
        v30 = 0;
        NumberOfFontsInFamily = GetNumberOfFontsInFamily((const struct _ITEMIDLIST *)pv, &v30);
        v7 = NumberOfFontsInFamily;
        if ( NumberOfFontsInFamily >= 0 )
          v11 += v30;
        else
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFA,
            (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
            (const char *)(unsigned int)NumberOfFontsInFamily,
            v27);
        goto LABEL_13;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
        (const char *)(unsigned int)PidlFromShellItem,
        v27);
    }
    ++v11;
LABEL_13:
    CoTaskMemFree(pv);
    ((void (__fastcall *)(struct IShellItem *))v29->lpVtbl->Release)(v29);
LABEL_14:
    v10 = v27;
    ++v12;
  }
  while ( v12 < v27 );
  if ( v7 >= 0 )
  {
LABEL_21:
    if ( !a1 )
      goto LABEL_22;
    if ( v11 > 5 )
    {
      if ( !(unsigned int)ConfirmMultiplePreviewWindows(v11, (HWND)a1[6].lpVtbl, 8121) )
        goto LABEL_41;
      v10 = v27;
    }
    v17 = 0;
    if ( !v10 )
      goto LABEL_41;
    while ( 1 )
    {
      if ( v7 < 0 )
        goto LABEL_41;
      v18 = a2->lpVtbl;
      v29 = 0;
      v19 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))v18->GetItemAt)(
              a2,
              v17,
              &v29);
      v7 = v19;
      if ( v19 >= 0 )
      {
        pv = 0;
        v19 = GetPidlFromShellItem(v29, (struct _ITEMIDLIST **)&pv);
        v7 = v19;
        if ( v19 >= 0 )
        {
          v21 = (struct _ITEMIDLIST *)pv;
          IsFolder = FID_IsFolder((const struct _ITEMIDLIST *)pv);
          v23 = a1[6].lpVtbl;
          if ( IsFolder )
          {
            v24 = OpenFontViewerForChildren((HWND)v23, 0, v21);
            v7 = v24;
            if ( v24 < 0 )
            {
              v25 = 293;
              goto LABEL_38;
            }
          }
          else
          {
            v24 = OpenFontViewer((HWND)v23, 0, v21);
            v7 = v24;
            if ( v24 < 0 )
            {
              v25 = 297;
LABEL_38:
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)v25,
                (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
                (const char *)(unsigned int)v24,
                v27);
            }
          }
          CoTaskMemFree(v21);
          ((void (__fastcall *)(struct IShellItem *))v29->lpVtbl->Release)(v29);
          goto LABEL_40;
        }
        v20 = 289;
      }
      else
      {
        v20 = 285;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
        (const char *)(unsigned int)v19,
        v27);
LABEL_40:
      if ( ++v17 >= v27 )
        goto LABEL_41;
    }
  }
LABEL_16:
  v8 = (unsigned int)v7;
  v9 = 264;
LABEL_5:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
    (const char *)v8,
    v27);
LABEL_41:
  wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v31,
    (unsigned int)v7);
  FontFldrTraceLoggingTelemetry::OnFontPreviewButton::~OnFontPreviewButton((FontFldrTraceLoggingTelemetry::OnFontPreviewButton *)v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002bda0  mov     [rsp-8+arg_10], rbx
0x18002bda5  mov     [rsp-8+arg_18], rsi
0x18002bdaa  push    rbp
0x18002bdab  push    rdi
0x18002bdac  push    r12
0x18002bdae  push    r13
0x18002bdb0  push    r14
0x18002bdb2  lea     rbp, [rsp-0A0h]
0x18002bdba  sub     rsp, 1A0h
0x18002bdc1  mov     rax, cs:__security_cookie
0x18002bdc8  xor     rax, rsp
0x18002bdcb  mov     [rbp+0C0h+var_30], rax
0x18002bdd2  mov     r12, rdx
0x18002bdd5  mov     r13, rcx
0x18002bdd8  lea     rdx, aOnfontpreviewb; "OnFontPreviewButton"
0x18002bddf  lea     rcx, [rsp+1C0h+var_180]
0x18002bde4  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002bde9  lea     rax, ??_7OnFontPreviewButton@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::OnFontPreviewButton::`vftable'
0x18002bdf0  lea     rcx, [rsp+1C0h+var_180]; this
0x18002bdf5  mov     [rsp+1C0h+var_180], rax
0x18002bdfa  call    ?StartActivity@OnFontPreviewButton@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::OnFontPreviewButton::StartActivity(void)
0x18002bdff  test    r12, r12
0x18002be02  jnz     short loc_18002BE27
0x18002be04  mov     rcx, [rbp+0C8h]; this
0x18002be0b  lea     r8, aShellOsshellFo_3; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18002be12  mov     r9d, 80070057h; char *
0x18002be18  mov     edx, 0E1h; void *
0x18002be1d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002be22  jmp     loc_18002BF96
0x18002be27  mov     rax, [r12]
0x18002be2b  lea     rdx, [rsp+1C0h+var_1A0]
0x18002be30  mov     rcx, r12
0x18002be33  mov     [rsp+1C0h+var_1A0], 0; int
0x18002be3b  mov     rax, [rax+38h]
0x18002be3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be44  mov     ebx, eax
0x18002be46  test    eax, eax
0x18002be48  jns     short loc_18002BE6A
0x18002be4a  mov     r9d, eax; char *
0x18002be4d  lea     r8, aShellOsshellFo_3; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18002be54  mov     edx, 0E9h; void *
0x18002be59  mov     rcx, [rbp+0C8h]; this
0x18002be60  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002be65  jmp     loc_18002C0AC
0x18002be6a  mov     eax, [rsp+1C0h+var_1A0]
0x18002be6e  lea     rdi, aShellOsshellFo_3; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18002be75  xor     esi, esi
0x18002be77  xor     r14d, r14d
0x18002be7a  test    eax, eax
0x18002be7c  jz      loc_18002BF91
0x18002be82  test    ebx, ebx
0x18002be84  js      loc_18002BF31
0x18002be8a  mov     rax, [r12]
0x18002be8e  lea     r8, [rsp+1C0h+var_190]
0x18002be93  mov     edx, r14d
0x18002be96  mov     [rsp+1C0h+var_190], 0
0x18002be9f  mov     rcx, r12
0x18002bea2  mov     rax, [rax+40h]
0x18002bea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002beab  mov     ebx, eax
0x18002bead  test    eax, eax
0x18002beaf  jns     short loc_18002BECA
0x18002beb1  mov     rcx, [rbp+0C8h]; this
0x18002beb8  mov     r9d, eax; char *
0x18002bebb  mov     r8, rdi; unsigned int
0x18002bebe  mov     edx, 0F2h; void *
0x18002bec3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002bec8  jmp     short loc_18002BF1D
0x18002beca  mov     rcx, [rsp+1C0h+var_190]; struct IShellItem *
0x18002becf  lea     rdx, [rsp+1C0h+pv]; struct _ITEMIDLIST **
0x18002bed4  mov     [rsp+1C0h+pv], 0
0x18002bedd  call    ?GetPidlFromShellItem@@YAJPEAUIShellItem@@PEAPEFAU_ITEMIDLIST@@@Z; GetPidlFromShellItem(IShellItem *,_ITEMIDLIST * *)
0x18002bee2  mov     ebx, eax
0x18002bee4  test    eax, eax
0x18002bee6  jns     short loc_18002BF41
0x18002bee8  mov     rcx, [rbp+0C8h]; this
0x18002beef  mov     r9d, eax; char *
0x18002bef2  mov     r8, rdi; unsigned int
0x18002bef5  mov     edx, 0F6h; void *
0x18002befa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002beff  inc     esi
0x18002bf01  mov     rcx, [rsp+1C0h+pv]; pv
0x18002bf06  call    cs:__imp_CoTaskMemFree
0x18002bf0c  mov     rcx, [rsp+1C0h+var_190]
0x18002bf11  mov     rax, [rcx]
0x18002bf14  mov     rax, [rax+10h]
0x18002bf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf1d  mov     eax, [rsp+1C0h+var_1A0]
0x18002bf21  inc     r14d
0x18002bf24  cmp     r14d, eax
0x18002bf27  jb      loc_18002BE82
0x18002bf2d  test    ebx, ebx
0x18002bf2f  jns     short loc_18002BF91
0x18002bf31  mov     r9d, ebx
0x18002bf34  mov     r8, rdi
0x18002bf37  mov     edx, 108h
0x18002bf3c  jmp     loc_18002BE59
0x18002bf41  mov     rcx, [rsp+1C0h+pv]; struct _ITEMIDLIST *
0x18002bf46  call    ?FID_IsFolder@@YAHPEFBU_ITEMIDLIST@@@Z; FID_IsFolder(_ITEMIDLIST const *)
0x18002bf4b  test    eax, eax
0x18002bf4d  jz      short loc_18002BEFF
0x18002bf4f  mov     rcx, [rsp+1C0h+pv]; struct _ITEMIDLIST *
0x18002bf54  lea     rdx, [rsp+1C0h+var_188]; unsigned int *
0x18002bf59  mov     [rsp+1C0h+var_188], 0
0x18002bf61  call    ?GetNumberOfFontsInFamily@@YAJPEFBU_ITEMIDLIST@@PEAK@Z; GetNumberOfFontsInFamily(_ITEMIDLIST const *,ulong *)
0x18002bf66  mov     ebx, eax
0x18002bf68  test    eax, eax
0x18002bf6a  jns     short loc_18002BF88
0x18002bf6c  mov     rcx, [rbp+0C8h]; this
0x18002bf73  mov     r9d, eax; char *
0x18002bf76  mov     r8, rdi; unsigned int
0x18002bf79  mov     edx, 0FAh; void *
0x18002bf7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002bf83  jmp     loc_18002BF01
0x18002bf88  add     esi, [rsp+1C0h+var_188]
0x18002bf8c  jmp     loc_18002BF01
0x18002bf91  test    r13, r13
0x18002bf94  jnz     short loc_18002BFA0
0x18002bf96  mov     ebx, 80004005h
0x18002bf9b  jmp     loc_18002C0AC
0x18002bfa0  cmp     esi, 5
0x18002bfa3  jbe     short loc_18002BFC2
0x18002bfa5  mov     rdx, [r13+30h]; HWND
0x18002bfa9  mov     r8d, 1FB9h; int
0x18002bfaf  mov     ecx, esi; unsigned int
0x18002bfb1  call    ?ConfirmMultiplePreviewWindows@@YAHKPEAUHWND__@@H@Z; ConfirmMultiplePreviewWindows(ulong,HWND__ *,int)
0x18002bfb6  test    eax, eax
0x18002bfb8  jz      loc_18002C0AC
0x18002bfbe  mov     eax, [rsp+1C0h+var_1A0]
0x18002bfc2  xor     esi, esi
0x18002bfc4  test    eax, eax
0x18002bfc6  jz      loc_18002C0AC
0x18002bfcc  test    ebx, ebx
0x18002bfce  js      loc_18002C0AC
0x18002bfd4  mov     rax, [r12]
0x18002bfd8  lea     r8, [rsp+1C0h+var_190]
0x18002bfdd  mov     edx, esi
0x18002bfdf  mov     [rsp+1C0h+var_190], 0
0x18002bfe8  mov     rcx, r12
0x18002bfeb  mov     rax, [rax+40h]
0x18002bfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bff4  mov     ebx, eax
0x18002bff6  test    eax, eax
0x18002bff8  jns     short loc_18002C001
0x18002bffa  mov     edx, 11Dh
0x18002bfff  jmp     short loc_18002C024
0x18002c001  mov     rcx, [rsp+1C0h+var_190]; struct IShellItem *
0x18002c006  lea     rdx, [rsp+1C0h+pv]; struct _ITEMIDLIST **
0x18002c00b  mov     [rsp+1C0h+pv], 0
0x18002c014  call    ?GetPidlFromShellItem@@YAJPEAUIShellItem@@PEAPEFAU_ITEMIDLIST@@@Z; GetPidlFromShellItem(IShellItem *,_ITEMIDLIST * *)
0x18002c019  mov     ebx, eax
0x18002c01b  test    eax, eax
0x18002c01d  jns     short loc_18002C038
0x18002c01f  mov     edx, 121h; void *
0x18002c024  mov     rcx, [rbp+0C8h]; this
0x18002c02b  mov     r8, rdi; unsigned int
0x18002c02e  mov     r9d, eax; char *
0x18002c031  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c036  jmp     short loc_18002C0A0
0x18002c038  mov     r14, [rsp+1C0h+pv]
0x18002c03d  mov     rcx, r14; struct _ITEMIDLIST *
0x18002c040  call    ?FID_IsFolder@@YAHPEFBU_ITEMIDLIST@@@Z; FID_IsFolder(_ITEMIDLIST const *)
0x18002c045  mov     rcx, [r13+30h]; HWND
0x18002c049  xor     edx, edx; int
0x18002c04b  mov     r8, r14; struct _ITEMIDLIST *
0x18002c04e  test    eax, eax
0x18002c050  jz      short loc_18002C064
0x18002c052  call    ?OpenFontViewerForChildren@@YAJPEAUHWND__@@HPEFBU_ITEMIDLIST@@@Z; OpenFontViewerForChildren(HWND__ *,int,_ITEMIDLIST const *)
0x18002c057  mov     ebx, eax
0x18002c059  test    eax, eax
0x18002c05b  jns     short loc_18002C086
0x18002c05d  mov     edx, 125h
0x18002c062  jmp     short loc_18002C074
0x18002c064  call    ?OpenFontViewer@@YAJPEAUHWND__@@HPEFBU_ITEMIDLIST@@@Z; OpenFontViewer(HWND__ *,int,_ITEMIDLIST const *)
0x18002c069  mov     ebx, eax
0x18002c06b  test    eax, eax
0x18002c06d  jns     short loc_18002C086
0x18002c06f  mov     edx, 129h; void *
0x18002c074  mov     rcx, [rbp+0C8h]; this
0x18002c07b  mov     r9d, eax; char *
0x18002c07e  mov     r8, rdi; unsigned int
0x18002c081  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c086  mov     rcx, r14; pv
0x18002c089  call    cs:__imp_CoTaskMemFree
0x18002c08f  mov     rcx, [rsp+1C0h+var_190]
0x18002c094  mov     rax, [rcx]
0x18002c097  mov     rax, [rax+10h]
0x18002c09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0a0  inc     esi
0x18002c0a2  cmp     esi, [rsp+1C0h+var_1A0]
0x18002c0a6  jb      loc_18002BFCC
0x18002c0ac  mov     edx, ebx
0x18002c0ae  lea     rcx, [rsp+1C0h+var_180]
0x18002c0b3  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002c0b8  lea     rcx, [rsp+1C0h+var_180]; this
0x18002c0bd  call    ??1OnFontPreviewButton@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::OnFontPreviewButton::~OnFontPreviewButton(void)
0x18002c0c2  mov     eax, ebx
0x18002c0c4  mov     rcx, [rbp+0C0h+var_30]
0x18002c0cb  xor     rcx, rsp; StackCookie
0x18002c0ce  call    __security_check_cookie
0x18002c0d3  lea     r11, [rsp+1C0h+var_20]
0x18002c0db  mov     rbx, [r11+40h]
0x18002c0df  mov     rsi, [r11+48h]
0x18002c0e3  mov     rsp, r11
0x18002c0e6  pop     r14
0x18002c0e8  pop     r13
0x18002c0ea  pop     r12
0x18002c0ec  pop     rdi
0x18002c0ed  pop     rbp
0x18002c0ee  retn
```
