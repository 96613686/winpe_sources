# CFontCollectionBuilder::_BuildFamilyDpa(ushort const *,CFontCollection * *)

- ea: `0x18000db98`
- end: `0x18000de22`
- name: `?_BuildFamilyDpa@CFontCollectionBuilder@@AEAAJPEBGPEAPEAVCFontCollection@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(CFontCollectionBuilder *__hidden this, const unsigned __int16 *, struct CFontCollection **)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000912c`

## callees

- `0x180006624`
- `0x180008aec`
- `0x180008dfc`
- `0x18000a524`
- `0x18000ae20`
- `0x18000dab0`
- `0x18000db98`
- `0x18000e374`
- `0x18000f074`
- `0x18000f518`
- `0x18000f6b8`
- `0x18001bd38`
- `0x18001bdec`
- `0x18001bf04`
- `0x18001bf80`
- `0x18001c0d0`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ddd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ddd2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dc66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dc51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ddc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd4e`
- `fms!FmsGetFilteredFontList` at `0x18000dc83`
- `fms!FmsGetFilteredFontList` at `0x18000dc83`

## string_xrefs

- `0x18000dc0d`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000dc96`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000dcda`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CFontCollectionBuilder::_BuildFamilyDpa(
        CFontCollectionBuilder *this,
        const unsigned __int16 *a2,
        struct CFontCollection **a3)
{
  int inited; // eax
  int v7; // ebx
  unsigned int v8; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // r15
  int FilteredFontList; // eax
  unsigned __int64 v13; // rdx
  CFontCollection *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 i; // rbx
  unsigned int v17; // edx
  int FacePidlFromFmsId; // eax
  int v19; // eax
  __int64 v20; // rdx
  HANDLE v21; // rax
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v25[42]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "_BuildFamilyDpa");
  v25[0] = &FontFldrTraceLoggingTelemetry::_BuildFamilyDpa::`vftable';
  FontFldrTraceLoggingTelemetry::_BuildFamilyDpa::StartActivity((FontFldrTraceLoggingTelemetry::_BuildFamilyDpa *)v25);
  inited = CFontCollectionBuilder::_InitFmsEnumerator(this);
  v7 = inited;
  if ( inited >= 0 )
  {
    v7 = -2147467259;
    v8 = CFontCollectionBuilder::_FilterFmsEnumeratorOnString(this, a2, 2);
    v23 = v8;
    if ( !v8 )
      goto LABEL_22;
    v7 = -2147024882;
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 8u, 4LL * v8);
    v11 = v10;
    if ( !v10 )
      goto LABEL_22;
    FilteredFontList = FmsGetFilteredFontList(*(_QWORD *)this, &v23, v10);
    v7 = FilteredFontList;
    if ( FilteredFontList >= 0 )
    {
      v7 = -2147024882;
      v14 = (CFontCollection *)DirectUI::HAllocAndZero((DirectUI *)0x60, v13);
      if ( !v14 )
        goto LABEL_21;
      v15 = (unsigned __int16 *)CFontCollection::CFontCollection(v14);
      if ( !v15 )
        goto LABEL_21;
      for ( i = 0; (unsigned int)i < v23; i = (unsigned int)(i + 1) )
      {
        v17 = v11[i];
        pv = 0;
        FacePidlFromFmsId = CFontCollectionBuilder::_MakeFacePidlFromFmsId(this, v17, a2, (struct _ITEMIDLIST **)&pv);
        if ( FacePidlFromFmsId >= 0 )
        {
          v19 = CFontCollection::AddItem((CFontCollection *)v15, (const struct _ITEMIDLIST *)pv);
          if ( v19 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x16A,
              (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
              (const char *)(unsigned int)v19,
              v23);
            CoTaskMemFree(pv);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x168,
            (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
            (const char *)(unsigned int)FacePidlFromFmsId,
            v23);
        }
      }
      v7 = CFontCollection::MarkCurrentTime((CFontCollection *)v15);
      if ( v7 >= 0 )
      {
        v7 = StringCchCopyW(v15 + 4, 0x20u, a2);
        if ( v7 >= 0 )
        {
          *a3 = (struct CFontCollection *)v15;
          goto LABEL_21;
        }
        v20 = 374;
      }
      else
      {
        v20 = 371;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
        (const char *)(unsigned int)v7,
        v23);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x17C,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
        (const char *)(unsigned int)v7,
        v23);
      CFontCollection::Release((CFontCollection *)v15);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15D,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
        (const char *)(unsigned int)FilteredFontList,
        v23);
    }
LABEL_21:
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v11);
LABEL_22:
    CFontCollectionBuilder::_ApplyDefaultFmsFilter(this);
    goto LABEL_23;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x150,
    (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
    (const char *)(unsigned int)inited,
    v23);
LABEL_23:
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25, (unsigned int)v7);
  FontFldrTraceLoggingTelemetry::_BuildFamilyDpa::~_BuildFamilyDpa((FontFldrTraceLoggingTelemetry::_BuildFamilyDpa *)v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000db98  mov     [rsp-8+arg_18], rbx
0x18000db9d  push    rbp
0x18000db9e  push    rsi
0x18000db9f  push    rdi
0x18000dba0  push    r12
0x18000dba2  push    r13
0x18000dba4  push    r14
0x18000dba6  push    r15
0x18000dba8  lea     rbp, [rsp-90h]
0x18000dbb0  sub     rsp, 190h
0x18000dbb7  mov     rax, cs:__security_cookie
0x18000dbbe  xor     rax, rsp
0x18000dbc1  mov     [rbp+0C0h+var_40], rax
0x18000dbc8  mov     r12, rdx
0x18000dbcb  mov     r14, rcx
0x18000dbce  lea     rdx, aBuildfamilydpa; "_BuildFamilyDpa"
0x18000dbd5  mov     r13, r8
0x18000dbd8  lea     rcx, [rsp+1C0h+var_190]
0x18000dbdd  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000dbe2  lea     rax, ??_7_BuildFamilyDpa@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::_BuildFamilyDpa::`vftable'
0x18000dbe9  lea     rcx, [rsp+1C0h+var_190]; this
0x18000dbee  mov     [rsp+1C0h+var_190], rax
0x18000dbf3  call    ?StartActivity@_BuildFamilyDpa@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::_BuildFamilyDpa::StartActivity(void)
0x18000dbf8  mov     rcx, r14; this
0x18000dbfb  call    ?_InitFmsEnumerator@CFontCollectionBuilder@@AEAAJXZ; CFontCollectionBuilder::_InitFmsEnumerator(void)
0x18000dc00  mov     ebx, eax
0x18000dc02  test    eax, eax
0x18000dc04  jns     short loc_18000DC26
0x18000dc06  mov     rcx, [rbp+0C8h]; this
0x18000dc0d  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000dc14  mov     r9d, eax; char *
0x18000dc17  mov     edx, 150h; void *
0x18000dc1c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dc21  jmp     loc_18000DDE0
0x18000dc26  mov     r8d, 2
0x18000dc2c  mov     rdx, r12
0x18000dc2f  mov     rcx, r14
0x18000dc32  mov     ebx, 80004005h
0x18000dc37  call    ?_FilterFmsEnumeratorOnString@CFontCollectionBuilder@@AEAAIPEBGW4_FONT_PROPERTY_TYPE@@@Z; CFontCollectionBuilder::_FilterFmsEnumeratorOnString(ushort const *,_FONT_PROPERTY_TYPE)
0x18000dc3c  mov     edi, eax
0x18000dc3e  mov     [rsp+1C0h+var_1A0], edi; int
0x18000dc42  test    eax, eax
0x18000dc44  jz      loc_18000DDD8
0x18000dc4a  mov     esi, 8007000Eh
0x18000dc4f  mov     ebx, esi
0x18000dc51  call    cs:__imp_GetProcessHeap
0x18000dc57  mov     r8d, edi
0x18000dc5a  mov     edx, 8; dwFlags
0x18000dc5f  shl     r8, 2; dwBytes
0x18000dc63  mov     rcx, rax; hHeap
0x18000dc66  call    cs:__imp_HeapAlloc
0x18000dc6c  mov     r15, rax
0x18000dc6f  test    rax, rax
0x18000dc72  jz      loc_18000DDD8
0x18000dc78  mov     rcx, [r14]
0x18000dc7b  lea     rdx, [rsp+1C0h+var_1A0]
0x18000dc80  mov     r8, rax
0x18000dc83  call    cs:__imp_FmsGetFilteredFontList
0x18000dc89  mov     ebx, eax
0x18000dc8b  test    eax, eax
0x18000dc8d  jns     short loc_18000DCAF
0x18000dc8f  mov     rcx, [rbp+0C8h]; this
0x18000dc96  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000dc9d  mov     r9d, eax; char *
0x18000dca0  mov     edx, 15Dh; void *
0x18000dca5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dcaa  jmp     loc_18000DDC4
0x18000dcaf  mov     ecx, 60h ; '`'; this
0x18000dcb4  mov     ebx, esi
0x18000dcb6  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000dcbb  test    rax, rax
0x18000dcbe  jz      loc_18000DDC4
0x18000dcc4  mov     rcx, rax; this
0x18000dcc7  call    ??0CFontCollection@@QEAA@XZ; CFontCollection::CFontCollection(void)
0x18000dccc  mov     rsi, rax
0x18000dccf  test    rax, rax
0x18000dcd2  jz      loc_18000DDC4
0x18000dcd8  xor     ebx, ebx
0x18000dcda  lea     rdi, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000dce1  cmp     [rsp+1C0h+var_1A0], ebx
0x18000dce5  jbe     short loc_18000DD5C
0x18000dce7  mov     edx, [r15+rbx*4]; unsigned int
0x18000dceb  lea     r9, [rsp+1C0h+pv]; struct _ITEMIDLIST **
0x18000dcf0  mov     r8, r12; unsigned __int16 *
0x18000dcf3  mov     [rsp+1C0h+pv], 0
0x18000dcfc  mov     rcx, r14; this
0x18000dcff  call    ?_MakeFacePidlFromFmsId@CFontCollectionBuilder@@AEAAJIPEBGPEAPEFAU_ITEMIDLIST@@@Z; CFontCollectionBuilder::_MakeFacePidlFromFmsId(uint,ushort const *,_ITEMIDLIST * *)
0x18000dd04  test    eax, eax
0x18000dd06  jns     short loc_18000DD21
0x18000dd08  mov     rcx, [rbp+0C8h]; this
0x18000dd0f  mov     r9d, eax; char *
0x18000dd12  mov     r8, rdi; unsigned int
0x18000dd15  mov     edx, 168h; void *
0x18000dd1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dd1f  jmp     short loc_18000DD54
0x18000dd21  mov     rdx, [rsp+1C0h+pv]; struct _ITEMIDLIST *
0x18000dd26  mov     rcx, rsi; this
0x18000dd29  call    ?AddItem@CFontCollection@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFontCollection::AddItem(_ITEMIDLIST const *)
0x18000dd2e  test    eax, eax
0x18000dd30  jns     short loc_18000DD54
0x18000dd32  mov     rcx, [rbp+0C8h]; this
0x18000dd39  mov     r9d, eax; char *
0x18000dd3c  mov     r8, rdi; unsigned int
0x18000dd3f  mov     edx, 16Ah; void *
0x18000dd44  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dd49  mov     rcx, [rsp+1C0h+pv]; pv
0x18000dd4e  call    cs:__imp_CoTaskMemFree
0x18000dd54  inc     ebx
0x18000dd56  cmp     ebx, [rsp+1C0h+var_1A0]
0x18000dd5a  jb      short loc_18000DCE7
0x18000dd5c  mov     rcx, rsi; this
0x18000dd5f  call    ?MarkCurrentTime@CFontCollection@@QEAAJXZ; CFontCollection::MarkCurrentTime(void)
0x18000dd64  mov     ebx, eax
0x18000dd66  test    eax, eax
0x18000dd68  jns     short loc_18000DD71
0x18000dd6a  mov     edx, 173h
0x18000dd6f  jmp     short loc_18000DD8D
0x18000dd71  lea     rcx, [rsi+8]; unsigned __int16 *
0x18000dd75  mov     r8, r12; unsigned __int16 *
0x18000dd78  mov     edx, 20h ; ' '; unsigned __int64
0x18000dd7d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dd82  mov     ebx, eax
0x18000dd84  test    eax, eax
0x18000dd86  jns     short loc_18000DDC0
0x18000dd88  mov     edx, 176h; void *
0x18000dd8d  mov     rcx, [rbp+0C8h]; this
0x18000dd94  mov     r9d, ebx; char *
0x18000dd97  mov     r8, rdi; unsigned int
0x18000dd9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dd9f  mov     rcx, [rbp+0C8h]; this
0x18000dda6  mov     r9d, ebx; char *
0x18000dda9  mov     r8, rdi; unsigned int
0x18000ddac  mov     edx, 17Ch; void *
0x18000ddb1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ddb6  mov     rcx, rsi; this
0x18000ddb9  call    ?Release@CFontCollection@@QEAAKXZ; CFontCollection::Release(void)
0x18000ddbe  jmp     short loc_18000DDC4
0x18000ddc0  mov     [r13+0], rsi
0x18000ddc4  call    cs:__imp_GetProcessHeap
0x18000ddca  mov     r8, r15; lpMem
0x18000ddcd  xor     edx, edx; dwFlags
0x18000ddcf  mov     rcx, rax; hHeap
0x18000ddd2  call    cs:__imp_HeapFree
0x18000ddd8  mov     rcx, r14; this
0x18000dddb  call    ?_ApplyDefaultFmsFilter@CFontCollectionBuilder@@AEAAJXZ; CFontCollectionBuilder::_ApplyDefaultFmsFilter(void)
0x18000dde0  mov     edx, ebx
0x18000dde2  lea     rcx, [rsp+1C0h+var_190]
0x18000dde7  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000ddec  lea     rcx, [rsp+1C0h+var_190]; this
0x18000ddf1  call    ??1_BuildFamilyDpa@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::_BuildFamilyDpa::~_BuildFamilyDpa(void)
0x18000ddf6  mov     eax, ebx
0x18000ddf8  mov     rcx, [rbp+0C0h+var_40]
0x18000ddff  xor     rcx, rsp; StackCookie
0x18000de02  call    __security_check_cookie
0x18000de07  mov     rbx, [rsp+1C0h+arg_18]
0x18000de0f  add     rsp, 190h
0x18000de16  pop     r15
0x18000de18  pop     r14
0x18000de1a  pop     r13
0x18000de1c  pop     r12
0x18000de1e  pop     rdi
0x18000de1f  pop     rsi
0x18000de20  pop     rbp
0x18000de21  retn
```
