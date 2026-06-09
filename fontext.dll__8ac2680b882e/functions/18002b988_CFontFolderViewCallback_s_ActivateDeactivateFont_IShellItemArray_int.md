# CFontFolderViewCallback::s_ActivateDeactivateFont(IShellItemArray *,int)

- ea: `0x18002b988`
- end: `0x18002bb62`
- name: `?s_ActivateDeactivateFont@CFontFolderViewCallback@@CAJPEAUIShellItemArray@@H@Z`
- size: `474`
- prototype: `static int(struct IShellItemArray *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bd40`
- `0x18002bd70`

## callees

- `0x18000f518`
- `0x180014144`
- `0x18001914c`
- `0x180022c58`
- `0x18002a4fc`
- `0x18002a8d0`
- `0x18002a90c`
- `0x18002a95c`
- `0x18002a9bc`
- `0x18002aae4`
- `0x18002b01c`
- `0x18002b988`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bafd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bafd`
- `USER32!LoadCursorW` at `0x18002ba4c`
- `USER32!LoadCursorW` at `0x18002ba4c`
- `USER32!SetCursor` at `0x18002ba5d`
- `USER32!SetCursor` at `0x18002bb1f`
- `USER32!SetCursor` at `0x18002ba5d`
- `USER32!SetCursor` at `0x18002bb1f`

## string_xrefs

- `0x18002b9eb`: `shell\osshell\fontfldr\fontext2\dll\view.cpp`
- `0x18002ba2c`: `shell\osshell\fontfldr\fontext2\dll\view.cpp`
- `0x18002bac5`: `shell\osshell\fontfldr\fontext2\dll\view.cpp`

## pseudocode

```c
__int64 __fastcall CFontFolderViewCallback::s_ActivateDeactivateFont(struct IShellItemArray *a1, int a2, __int64 a3)
{
  struct IShellItemArrayVtbl *lpVtbl; // rax
  int v6; // eax
  unsigned int v7; // esi
  HCURSOR CursorW; // rax
  HCURSOR v9; // r14
  unsigned int i; // edi
  struct IShellItemArrayVtbl *v11; // rcx
  int PidlFromShellItem; // eax
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  struct IShellItem *v17; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v18[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "ActivateDeactivateFont",
    a3);
  v18[0] = &FontFldrTraceLoggingTelemetry::ActivateDeactivateFont::`vftable';
  FontFldrTraceLoggingTelemetry::ActivateDeactivateFont::StartActivity((FontFldrTraceLoggingTelemetry::ActivateDeactivateFont *)v18);
  if ( !a1 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
      (const char *)0x80070057LL,
      v15);
  lpVtbl = a1->lpVtbl;
  v15 = 0;
  v6 = ((__int64 (__fastcall *)(struct IShellItemArray *, int *))lpVtbl->GetCount)(a1, &v15);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
      (const char *)(unsigned int)v6,
      v15);
    goto LABEL_21;
  }
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v9 = 0;
  if ( CursorW )
    v9 = SetCursor(CursorW);
  for ( i = 0; i < v15; ++i )
  {
    v11 = a1->lpVtbl;
    v17 = 0;
    PidlFromShellItem = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, struct IShellItem **))v11->GetItemAt)(
                          a1,
                          i,
                          &v17);
    if ( PidlFromShellItem >= 0 )
    {
      pv = 0;
      PidlFromShellItem = GetPidlFromShellItem(v17, (struct _ITEMIDLIST **)&pv);
      if ( PidlFromShellItem >= 0 )
      {
        if ( (unsigned int)FID_IsFolder((const struct _ITEMIDLIST *)pv) )
          SetFontFamilyActivationState((const struct _ITEMIDLIST *)pv, a2);
        else
          SetFontActivationState((const struct _ITEMIDLIST *)pv, a2);
        CoTaskMemFree(pv);
        continue;
      }
      v13 = 524;
    }
    else
    {
      v13 = 520;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\view.cpp",
      (const char *)(unsigned int)PidlFromShellItem,
      v15);
  }
  PersistActivationState(a2);
  if ( v9 )
    SetCursor(v9);
  RefreshFontFolderView();
LABEL_21:
  wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v18, v7);
  FontFldrTraceLoggingTelemetry::ActivateDeactivateFont::~ActivateDeactivateFont((FontFldrTraceLoggingTelemetry::ActivateDeactivateFont *)v18);
  return v7;
}

```

## disassembly

```asm
0x18002b988  push    rbp
0x18002b98a  push    rsi
0x18002b98b  push    rdi
0x18002b98c  push    r12
0x18002b98e  push    r14
0x18002b990  push    r15
0x18002b992  lea     rbp, [rsp-0A8h]
0x18002b99a  sub     rsp, 1A8h
0x18002b9a1  mov     rax, cs:__security_cookie
0x18002b9a8  xor     rax, rsp
0x18002b9ab  mov     [rbp+0D0h+var_40], rax
0x18002b9b2  mov     r15d, edx
0x18002b9b5  mov     r12, rcx
0x18002b9b8  lea     rdx, aActivatedeacti; "ActivateDeactivateFont"
0x18002b9bf  lea     rcx, [rsp+1D0h+var_190]
0x18002b9c4  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002b9c9  lea     rax, ??_7ActivateDeactivateFont@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::ActivateDeactivateFont::`vftable'
0x18002b9d0  lea     rcx, [rsp+1D0h+var_190]; this
0x18002b9d5  mov     [rsp+1D0h+var_190], rax
0x18002b9da  call    ?StartActivity@ActivateDeactivateFont@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::ActivateDeactivateFont::StartActivity(void)
0x18002b9df  test    r12, r12
0x18002b9e2  jnz     short loc_18002BA02
0x18002b9e4  mov     rcx, [rbp+0D8h]; this
0x18002b9eb  lea     r8, aShellOsshellFo_3; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18002b9f2  mov     r9d, 80070057h; char *
0x18002b9f8  mov     edx, 1F5h; void *
0x18002b9fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ba02  mov     rax, [r12]
0x18002ba06  lea     rdx, [rsp+1D0h+var_1B0]
0x18002ba0b  mov     rcx, r12
0x18002ba0e  mov     [rsp+1D0h+var_1B0], 0; int
0x18002ba16  mov     rax, [rax+38h]
0x18002ba1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba1f  mov     esi, eax
0x18002ba21  test    eax, eax
0x18002ba23  jns     short loc_18002BA45
0x18002ba25  mov     rcx, [rbp+0D8h]; this
0x18002ba2c  lea     r8, aShellOsshellFo_3; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18002ba33  mov     r9d, eax; char *
0x18002ba36  mov     edx, 1F9h; void *
0x18002ba3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ba40  jmp     loc_18002BB2A
0x18002ba45  mov     edx, 7F02h; lpCursorName
0x18002ba4a  xor     ecx, ecx; hInstance
0x18002ba4c  call    cs:__imp_LoadCursorW
0x18002ba52  xor     r14d, r14d
0x18002ba55  test    rax, rax
0x18002ba58  jz      short loc_18002BA66
0x18002ba5a  mov     rcx, rax; hCursor
0x18002ba5d  call    cs:__imp_SetCursor
0x18002ba63  mov     r14, rax
0x18002ba66  xor     edi, edi
0x18002ba68  cmp     [rsp+1D0h+var_1B0], edi
0x18002ba6c  jbe     loc_18002BB0F
0x18002ba72  mov     rcx, [r12]
0x18002ba76  lea     r8, [rsp+1D0h+var_1A0]
0x18002ba7b  mov     edx, edi
0x18002ba7d  mov     [rsp+1D0h+var_1A0], 0
0x18002ba86  mov     rax, [rcx+40h]
0x18002ba8a  mov     rcx, r12
0x18002ba8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba92  test    eax, eax
0x18002ba94  jns     short loc_18002BA9D
0x18002ba96  mov     edx, 208h
0x18002ba9b  jmp     short loc_18002BABE
0x18002ba9d  mov     rcx, [rsp+1D0h+var_1A0]; struct IShellItem *
0x18002baa2  lea     rdx, [rsp+1D0h+pv]; struct _ITEMIDLIST **
0x18002baa7  mov     [rsp+1D0h+pv], 0
0x18002bab0  call    ?GetPidlFromShellItem@@YAJPEAUIShellItem@@PEAPEFAU_ITEMIDLIST@@@Z; GetPidlFromShellItem(IShellItem *,_ITEMIDLIST * *)
0x18002bab5  test    eax, eax
0x18002bab7  jns     short loc_18002BAD6
0x18002bab9  mov     edx, 20Ch; void *
0x18002babe  mov     rcx, [rbp+0D8h]; this
0x18002bac5  lea     r8, aShellOsshellFo_3; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18002bacc  mov     r9d, eax; char *
0x18002bacf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002bad4  jmp     short loc_18002BB03
0x18002bad6  mov     rcx, [rsp+1D0h+pv]; struct _ITEMIDLIST *
0x18002badb  call    ?FID_IsFolder@@YAHPEFBU_ITEMIDLIST@@@Z; FID_IsFolder(_ITEMIDLIST const *)
0x18002bae0  mov     rcx, [rsp+1D0h+pv]; struct _ITEMIDLIST *
0x18002bae5  mov     edx, r15d; int
0x18002bae8  test    eax, eax
0x18002baea  jz      short loc_18002BAF3
0x18002baec  call    ?SetFontFamilyActivationState@@YAJPEFBU_ITEMIDLIST@@H@Z; SetFontFamilyActivationState(_ITEMIDLIST const *,int)
0x18002baf1  jmp     short loc_18002BAF8
0x18002baf3  call    ?SetFontActivationState@@YAJPEFBU_ITEMIDLIST@@H@Z; SetFontActivationState(_ITEMIDLIST const *,int)
0x18002baf8  mov     rcx, [rsp+1D0h+pv]; pv
0x18002bafd  call    cs:__imp_CoTaskMemFree
0x18002bb03  inc     edi
0x18002bb05  cmp     edi, [rsp+1D0h+var_1B0]
0x18002bb09  jb      loc_18002BA72
0x18002bb0f  mov     ecx, r15d; int
0x18002bb12  call    ?PersistActivationState@@YAJH@Z; PersistActivationState(int)
0x18002bb17  test    r14, r14
0x18002bb1a  jz      short loc_18002BB25
0x18002bb1c  mov     rcx, r14; hCursor
0x18002bb1f  call    cs:__imp_SetCursor
0x18002bb25  call    ?RefreshFontFolderView@@YAXXZ; RefreshFontFolderView(void)
0x18002bb2a  mov     edx, esi
0x18002bb2c  lea     rcx, [rsp+1D0h+var_190]
0x18002bb31  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002bb36  lea     rcx, [rsp+1D0h+var_190]; this
0x18002bb3b  call    ??1ActivateDeactivateFont@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::ActivateDeactivateFont::~ActivateDeactivateFont(void)
0x18002bb40  mov     eax, esi
0x18002bb42  mov     rcx, [rbp+0D0h+var_40]
0x18002bb49  xor     rcx, rsp; StackCookie
0x18002bb4c  call    __security_check_cookie
0x18002bb51  add     rsp, 1A8h
0x18002bb58  pop     r15
0x18002bb5a  pop     r14
0x18002bb5c  pop     r12
0x18002bb5e  pop     rdi
0x18002bb5f  pop     rsi
0x18002bb60  pop     rbp
0x18002bb61  retn
```
