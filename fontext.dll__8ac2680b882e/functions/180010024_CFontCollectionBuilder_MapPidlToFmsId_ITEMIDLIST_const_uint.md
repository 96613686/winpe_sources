# CFontCollectionBuilder::_MapPidlToFmsId(_ITEMIDLIST const *,uint *)

- ea: `0x180010024`
- end: `0x1800101c3`
- name: `?_MapPidlToFmsId@CFontCollectionBuilder@@AEAAJPEFBU_ITEMIDLIST@@PEAI@Z`
- size: `415`
- prototype: `__int64 __fastcall(CFontCollectionBuilder *__hidden this, const struct _ITEMIDLIST *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180009eb8`

## callees

- `0x180008aec`
- `0x180009038`
- `0x1800093e4`
- `0x18000ad10`
- `0x18000ae20`
- `0x18000dab0`
- `0x18000e374`
- `0x18000f518`
- `0x180010024`
- `0x180022c10`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `fms!FmsGetFilteredFontList` at `0x18001011b`
- `fms!FmsGetFilteredFontList` at `0x18001011b`

## string_xrefs

- `0x180010051`: `_MapPidlToFmsId`
- `0x1800100da`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18001012e`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x180010170`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CFontCollectionBuilder::_MapPidlToFmsId(
        CFontCollectionBuilder *this,
        const struct _ITEMIDLIST *a2,
        unsigned int *a3)
{
  unsigned int v6; // r8d
  signed int v7; // ebx
  int v8; // eax
  int FilteredFontList; // eax
  int v11; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v12[3]; // [rsp+24h] [rbp-DCh] BYREF
  _QWORD v13[42]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v14[384]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v13,
    "_MapPidlToFmsId");
  v13[0] = &FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::`vftable';
  FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::StartActivity((FontFldrTraceLoggingTelemetry::_MapPidlToFmsId *)v13);
  v11 = 0;
  if ( a2 && a3 )
  {
    v7 = -2147467259;
    if ( *(_QWORD *)this )
    {
      memset_0(v14, 0, sizeof(v14));
      v8 = FID_InvariantName(a2, v14, 0x180u);
      v7 = v8;
      if ( v8 >= 0 )
      {
        v12[0] = CFontCollectionBuilder::_FilterFmsEnumeratorOnString(this, v14, 5);
        if ( v12[0] == 1 )
        {
          FilteredFontList = FmsGetFilteredFontList(*(_QWORD *)this, v12, &v11);
          v7 = FilteredFontList;
          if ( FilteredFontList < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x85,
              (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
              (const char *)(unsigned int)FilteredFontList,
              v11);
        }
        CFontCollectionBuilder::_ApplyDefaultFmsFilter(this);
        if ( v7 >= 0 )
          goto LABEL_13;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x7F,
          (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
          (const char *)(unsigned int)v8,
          v11);
      }
    }
  }
  else
  {
    v7 = -2147024809;
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x8F, v6, (const char *)0x80070057LL, v11);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x92,
    (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
    (const char *)(unsigned int)v7,
    v11);
  if ( v7 >= 0 )
LABEL_13:
    *a3 = v11;
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v13, v7);
  FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::~_MapPidlToFmsId((FontFldrTraceLoggingTelemetry::_MapPidlToFmsId *)v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010024  push    rbp
0x180010026  push    rbx
0x180010027  push    rsi
0x180010028  push    rdi
0x180010029  push    r14
0x18001002b  lea     rbp, [rsp-390h]
0x180010033  sub     rsp, 490h
0x18001003a  mov     rax, cs:__security_cookie
0x180010041  xor     rax, rsp
0x180010044  mov     [rbp+3B0h+var_30], rax
0x18001004b  mov     r14, rdx
0x18001004e  mov     rdi, rcx
0x180010051  lea     rdx, aMappidltofmsid; "_MapPidlToFmsId"
0x180010058  mov     rsi, r8
0x18001005b  lea     rcx, [rsp+4B0h+var_480]
0x180010060  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010065  lea     rax, ??_7_MapPidlToFmsId@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::`vftable'
0x18001006c  lea     rcx, [rsp+4B0h+var_480]; this
0x180010071  mov     [rsp+4B0h+var_480], rax
0x180010076  call    ?StartActivity@_MapPidlToFmsId@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::StartActivity(void)
0x18001007b  mov     [rsp+4B0h+var_490], 0; int
0x180010083  test    r14, r14
0x180010086  jz      loc_180010150
0x18001008c  test    rsi, rsi
0x18001008f  jz      loc_180010150
0x180010095  cmp     qword ptr [rdi], 0
0x180010099  mov     ebx, 80004005h
0x18001009e  jz      loc_180010169
0x1800100a4  xor     edx, edx; Val
0x1800100a6  lea     rcx, [rbp+3B0h+var_330]; void *
0x1800100ad  mov     r8d, 300h; Size
0x1800100b3  call    memset_0
0x1800100b8  mov     r8d, 180h; unsigned __int64
0x1800100be  lea     rdx, [rbp+3B0h+var_330]; unsigned __int16 *
0x1800100c5  mov     rcx, r14; struct _ITEMIDLIST *
0x1800100c8  call    ?FID_InvariantName@@YAJPEFBU_ITEMIDLIST@@PEAG_K@Z; FID_InvariantName(_ITEMIDLIST const *,ushort *,unsigned __int64)
0x1800100cd  mov     ebx, eax
0x1800100cf  test    eax, eax
0x1800100d1  jns     short loc_1800100F0
0x1800100d3  mov     rcx, [rbp+3B8h]; this
0x1800100da  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x1800100e1  mov     r9d, eax; char *
0x1800100e4  mov     edx, 7Fh; void *
0x1800100e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800100ee  jmp     short loc_180010169
0x1800100f0  mov     r8d, 5
0x1800100f6  lea     rdx, [rbp+3B0h+var_330]
0x1800100fd  mov     rcx, rdi
0x180010100  call    ?_FilterFmsEnumeratorOnString@CFontCollectionBuilder@@AEAAIPEBGW4_FONT_PROPERTY_TYPE@@@Z; CFontCollectionBuilder::_FilterFmsEnumeratorOnString(ushort const *,_FONT_PROPERTY_TYPE)
0x180010105  mov     [rsp+4B0h+var_48C], eax
0x180010109  cmp     eax, 1
0x18001010c  jnz     short loc_180010142
0x18001010e  mov     rcx, [rdi]
0x180010111  lea     r8, [rsp+4B0h+var_490]
0x180010116  lea     rdx, [rsp+4B0h+var_48C]
0x18001011b  call    cs:__imp_FmsGetFilteredFontList
0x180010121  mov     ebx, eax
0x180010123  test    eax, eax
0x180010125  jns     short loc_180010142
0x180010127  mov     rcx, [rbp+3B8h]; this
0x18001012e  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180010135  mov     r9d, eax; char *
0x180010138  mov     edx, 85h; void *
0x18001013d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010142  mov     rcx, rdi; this
0x180010145  call    ?_ApplyDefaultFmsFilter@CFontCollectionBuilder@@AEAAJXZ; CFontCollectionBuilder::_ApplyDefaultFmsFilter(void)
0x18001014a  test    ebx, ebx
0x18001014c  jns     short loc_180010188
0x18001014e  jmp     short loc_180010169
0x180010150  mov     rcx, [rbp+3B8h]; this
0x180010157  mov     ebx, 80070057h
0x18001015c  mov     r9d, ebx; char *
0x18001015f  mov     edx, 8Fh; void *
0x180010164  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180010169  mov     rcx, [rbp+3B8h]; this
0x180010170  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180010177  mov     r9d, ebx; char *
0x18001017a  mov     edx, 92h; void *
0x18001017f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010184  test    ebx, ebx
0x180010186  js      short loc_18001018E
0x180010188  mov     eax, [rsp+4B0h+var_490]
0x18001018c  mov     [rsi], eax
0x18001018e  mov     edx, ebx
0x180010190  lea     rcx, [rsp+4B0h+var_480]
0x180010195  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001019a  lea     rcx, [rsp+4B0h+var_480]; this
0x18001019f  call    ??1_MapPidlToFmsId@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::_MapPidlToFmsId::~_MapPidlToFmsId(void)
0x1800101a4  mov     eax, ebx
0x1800101a6  mov     rcx, [rbp+3B0h+var_30]
0x1800101ad  xor     rcx, rsp; StackCookie
0x1800101b0  call    __security_check_cookie
0x1800101b5  add     rsp, 490h
0x1800101bc  pop     r14
0x1800101be  pop     rdi
0x1800101bf  pop     rsi
0x1800101c0  pop     rbx
0x1800101c1  pop     rbp
0x1800101c2  retn
```
