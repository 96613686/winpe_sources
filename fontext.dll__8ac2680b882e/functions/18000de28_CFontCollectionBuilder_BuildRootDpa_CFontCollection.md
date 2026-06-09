# CFontCollectionBuilder::_BuildRootDpa(CFontCollection * *)

- ea: `0x18000de28`
- end: `0x18000e13d`
- name: `?_BuildRootDpa@CFontCollectionBuilder@@AEAAJPEAPEAVCFontCollection@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CFontCollectionBuilder *__hidden this, struct CFontCollection **)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000912c`

## callees

- `0x180006624`
- `0x180008aec`
- `0x180008e28`
- `0x18000a5c0`
- `0x18000ae20`
- `0x18000dab0`
- `0x18000de28`
- `0x18000e374`
- `0x18000f074`
- `0x18000f518`
- `0x18000f548`
- `0x18000fc40`
- `0x18001bd38`
- `0x18001bdec`
- `0x18001bf04`
- `0x18001bf80`
- `0x18001c0d0`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0f5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000df12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000df12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e005`
- `fms!FmsGetFilteredPropertyList` at `0x18000debe`
- `fms!FmsGetFilteredPropertyList` at `0x18000df3b`
- `fms!FmsGetFilteredPropertyList` at `0x18000debe`
- `fms!FmsGetFilteredPropertyList` at `0x18000df3b`

## string_xrefs

- `0x18000ded6`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000dfec`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000e014`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000e088`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000e09e`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000e0d8`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CFontCollectionBuilder::_BuildRootDpa(CFontCollectionBuilder *this, struct CFontCollection **a2)
{
  int inited; // eax
  int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r15
  int FilteredPropertyList; // eax
  unsigned __int64 v13; // rdx
  __int64 v14; // rdx
  CFontCollection *v15; // rax
  unsigned __int16 *v16; // rbx
  const unsigned __int16 *v17; // rdi
  unsigned int i; // r14d
  unsigned int v19; // eax
  bool v20; // cc
  int FacePidlFromFmsEnumerator; // eax
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rdx
  HANDLE v25; // rax
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD dwBytes[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v32[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v32,
    "_BuildRootDpa");
  v32[0] = &FontFldrTraceLoggingTelemetry::_BuildRootDpa::`vftable';
  FontFldrTraceLoggingTelemetry::_BuildRootDpa::StartActivity((FontFldrTraceLoggingTelemetry::_BuildRootDpa *)v32);
  inited = CFontCollectionBuilder::_InitFmsEnumerator(this);
  v5 = inited;
  if ( inited < 0 )
  {
    v6 = 227;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)(unsigned int)inited,
      v27);
    goto LABEL_34;
  }
  v7 = *(_QWORD *)this;
  dwBytes[0] = 0;
  v30 = 0;
  v27 = 0;
  inited = FmsGetFilteredPropertyList(v7, 2, &v30, dwBytes);
  v5 = inited;
  if ( inited < 0 )
  {
    v6 = 239;
    goto LABEL_5;
  }
  if ( dwBytes[0] )
  {
    v8 = dwBytes[0];
    v5 = -2147024882;
    ProcessHeap = GetProcessHeap();
    v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v8);
    v11 = v10;
    if ( v10 )
    {
      v28 = (int)v10;
      FilteredPropertyList = FmsGetFilteredPropertyList(*(_QWORD *)this, 2, &v30, dwBytes);
      v5 = FilteredPropertyList;
      if ( FilteredPropertyList < 0 )
      {
        v14 = 252;
        goto LABEL_32;
      }
      v5 = -2147024882;
      v15 = (CFontCollection *)DirectUI::HAllocAndZero((DirectUI *)0x60, v13);
      if ( !v15 )
        goto LABEL_33;
      v16 = (unsigned __int16 *)CFontCollection::CFontCollection(v15);
      if ( !v16 )
        goto LABEL_33;
      v17 = v11;
      for ( i = 0; i < v30; v17 += v23 + 1 )
      {
        v19 = CFontCollectionBuilder::_FilterFmsEnumeratorOnString(this, v17, 2);
        *(_QWORD *)&dwBytes[1] = 0;
        v20 = v19 <= 1;
        if ( v19 == 1 )
        {
          FacePidlFromFmsEnumerator = CFontCollectionBuilder::_MakeFacePidlFromFmsEnumerator(
                                        this,
                                        v17,
                                        (struct _ITEMIDLIST **)&dwBytes[1]);
        }
        else
        {
          FacePidlFromFmsEnumerator = -2147467259;
          if ( v20 )
            goto LABEL_20;
          FacePidlFromFmsEnumerator = CFontCollectionBuilder::_MakeFamilyPidlFromFmsEnumerator(
                                        this,
                                        v17,
                                        (struct _ITEMIDLIST **)&dwBytes[1]);
        }
        if ( FacePidlFromFmsEnumerator >= 0 )
        {
          v22 = CFontCollection::AddItem((CFontCollection *)v16, *(const struct _ITEMIDLIST **)&dwBytes[1]);
          if ( v22 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x11A,
              (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
              (const char *)(unsigned int)v22,
              v28);
            CoTaskMemFree(*(LPVOID *)&dwBytes[1]);
          }
          goto LABEL_21;
        }
LABEL_20:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
          (const char *)(unsigned int)FacePidlFromFmsEnumerator,
          v28);
LABEL_21:
        v23 = -1;
        do
          ++v23;
        while ( v17[v23] );
        ++i;
      }
      v5 = CFontCollection::MarkCurrentTime((CFontCollection *)v16);
      if ( v5 >= 0 )
      {
        v5 = StringCchCopyW(v16 + 4, 0x20u, L"ROOT");
        if ( v5 >= 0 )
        {
          *a2 = (struct CFontCollection *)v16;
          goto LABEL_30;
        }
        v24 = 296;
      }
      else
      {
        v24 = 293;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
        (const char *)(unsigned int)v5,
        v28);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
        (const char *)(unsigned int)v5,
        v29);
      CFontCollection::Release((CFontCollection *)v16);
LABEL_30:
      FilteredPropertyList = CFontCollectionBuilder::_ApplyDefaultFmsFilter(this);
      if ( FilteredPropertyList >= 0 )
      {
LABEL_33:
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v11);
        goto LABEL_34;
      }
      v14 = 308;
LABEL_32:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
        (const char *)(unsigned int)FilteredPropertyList,
        v28);
      goto LABEL_33;
    }
  }
LABEL_34:
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v32, (unsigned int)v5);
  FontFldrTraceLoggingTelemetry::_BuildRootDpa::~_BuildRootDpa((FontFldrTraceLoggingTelemetry::_BuildRootDpa *)v32);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000de28  mov     [rsp-8+arg_10], rbx
0x18000de2d  push    rbp
0x18000de2e  push    rsi
0x18000de2f  push    rdi
0x18000de30  push    r12
0x18000de32  push    r13
0x18000de34  push    r14
0x18000de36  push    r15
0x18000de38  lea     rbp, [rsp-0A0h]
0x18000de40  sub     rsp, 1A0h
0x18000de47  mov     rax, cs:__security_cookie
0x18000de4e  xor     rax, rsp
0x18000de51  mov     [rbp+0D0h+var_40], rax
0x18000de58  mov     r12, rdx
0x18000de5b  mov     rsi, rcx
0x18000de5e  lea     rdx, aBuildrootdpa; "_BuildRootDpa"
0x18000de65  lea     rcx, [rsp+1D0h+var_190]
0x18000de6a  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000de6f  lea     rax, ??_7_BuildRootDpa@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::_BuildRootDpa::`vftable'
0x18000de76  lea     rcx, [rsp+1D0h+var_190]; this
0x18000de7b  mov     [rsp+1D0h+var_190], rax
0x18000de80  call    ?StartActivity@_BuildRootDpa@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::_BuildRootDpa::StartActivity(void)
0x18000de85  mov     rcx, rsi; this
0x18000de88  call    ?_InitFmsEnumerator@CFontCollectionBuilder@@AEAAJXZ; CFontCollectionBuilder::_InitFmsEnumerator(void)
0x18000de8d  xor     r13d, r13d
0x18000de90  mov     edi, eax
0x18000de92  test    eax, eax
0x18000de94  jns     short loc_18000DE9D
0x18000de96  mov     edx, 0E3h
0x18000de9b  jmp     short loc_18000DECF
0x18000de9d  mov     rcx, [rsi]
0x18000dea0  lea     r9, [rsp+1D0h+dwBytes]
0x18000dea5  lea     r8, [rsp+1D0h+var_1A0]
0x18000deaa  mov     dword ptr [rsp+1D0h+dwBytes], r13d
0x18000deaf  mov     edx, 2
0x18000deb4  mov     [rsp+1D0h+var_1A0], r13d
0x18000deb9  mov     qword ptr [rsp+1D0h+var_1B0], r13; int
0x18000debe  call    cs:__imp_FmsGetFilteredPropertyList
0x18000dec4  mov     edi, eax
0x18000dec6  test    eax, eax
0x18000dec8  jns     short loc_18000DEEA
0x18000deca  mov     edx, 0EFh; void *
0x18000decf  mov     rcx, [rbp+0D8h]; this
0x18000ded6  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000dedd  mov     r9d, eax; char *
0x18000dee0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dee5  jmp     loc_18000E0FB
0x18000deea  mov     eax, dword ptr [rsp+1D0h+dwBytes]
0x18000deee  test    eax, eax
0x18000def0  jz      loc_18000E0FB
0x18000def6  mov     r14d, 8007000Eh
0x18000defc  mov     ebx, eax
0x18000defe  mov     edi, r14d
0x18000df01  call    cs:__imp_GetProcessHeap
0x18000df07  mov     r8d, ebx; dwBytes
0x18000df0a  mov     edx, 8; dwFlags
0x18000df0f  mov     rcx, rax; hHeap
0x18000df12  call    cs:__imp_HeapAlloc
0x18000df18  mov     r15, rax
0x18000df1b  test    rax, rax
0x18000df1e  jz      loc_18000E0FB
0x18000df24  mov     rcx, [rsi]
0x18000df27  lea     r9, [rsp+1D0h+dwBytes]
0x18000df2c  lea     r8, [rsp+1D0h+var_1A0]
0x18000df31  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x18000df36  mov     edx, 2
0x18000df3b  call    cs:__imp_FmsGetFilteredPropertyList
0x18000df41  mov     edi, eax
0x18000df43  test    eax, eax
0x18000df45  jns     short loc_18000DF51
0x18000df47  mov     edx, 0FCh
0x18000df4c  jmp     loc_18000E0D1
0x18000df51  mov     ecx, 60h ; '`'; this
0x18000df56  mov     edi, r14d
0x18000df59  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000df5e  test    rax, rax
0x18000df61  jz      loc_18000E0E7
0x18000df67  mov     rcx, rax; this
0x18000df6a  call    ??0CFontCollection@@QEAA@XZ; CFontCollection::CFontCollection(void)
0x18000df6f  mov     rbx, rax
0x18000df72  test    rax, rax
0x18000df75  jz      loc_18000E0E7
0x18000df7b  mov     rdi, r15
0x18000df7e  mov     r14d, r13d
0x18000df81  cmp     [rsp+1D0h+var_1A0], r13d
0x18000df86  jbe     loc_18000E04C
0x18000df8c  mov     r8d, 2
0x18000df92  mov     rdx, rdi
0x18000df95  mov     rcx, rsi
0x18000df98  call    ?_FilterFmsEnumeratorOnString@CFontCollectionBuilder@@AEAAIPEBGW4_FONT_PROPERTY_TYPE@@@Z; CFontCollectionBuilder::_FilterFmsEnumeratorOnString(ushort const *,_FONT_PROPERTY_TYPE)
0x18000df9d  mov     qword ptr [rsp+1D0h+dwBytes+4], r13
0x18000dfa2  cmp     eax, 1
0x18000dfa5  jnz     short loc_18000DFB9
0x18000dfa7  lea     r8, [rsp+1D0h+dwBytes+4]; struct _ITEMIDLIST **
0x18000dfac  mov     rdx, rdi; unsigned __int16 *
0x18000dfaf  mov     rcx, rsi; this
0x18000dfb2  call    ?_MakeFacePidlFromFmsEnumerator@CFontCollectionBuilder@@AEAAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; CFontCollectionBuilder::_MakeFacePidlFromFmsEnumerator(ushort const *,_ITEMIDLIST * *)
0x18000dfb7  jmp     short loc_18000DFD0
0x18000dfb9  mov     eax, 80004005h
0x18000dfbe  jbe     short loc_18000E00D
0x18000dfc0  lea     r8, [rsp+1D0h+dwBytes+4]; struct _ITEMIDLIST **
0x18000dfc5  mov     rdx, rdi; unsigned __int16 *
0x18000dfc8  mov     rcx, rsi; this
0x18000dfcb  call    ?_MakeFamilyPidlFromFmsEnumerator@CFontCollectionBuilder@@AEAAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; CFontCollectionBuilder::_MakeFamilyPidlFromFmsEnumerator(ushort const *,_ITEMIDLIST * *)
0x18000dfd0  test    eax, eax
0x18000dfd2  js      short loc_18000E00D
0x18000dfd4  mov     rdx, qword ptr [rsp+1D0h+dwBytes+4]; struct _ITEMIDLIST *
0x18000dfd9  mov     rcx, rbx; this
0x18000dfdc  call    ?AddItem@CFontCollection@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFontCollection::AddItem(_ITEMIDLIST const *)
0x18000dfe1  test    eax, eax
0x18000dfe3  jns     short loc_18000E028
0x18000dfe5  mov     rcx, [rbp+0D8h]; this
0x18000dfec  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000dff3  mov     r9d, eax; char *
0x18000dff6  mov     edx, 11Ah; void *
0x18000dffb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e000  mov     rcx, qword ptr [rsp+1D0h+dwBytes+4]; pv
0x18000e005  call    cs:__imp_CoTaskMemFree
0x18000e00b  jmp     short loc_18000E028
0x18000e00d  mov     rcx, [rbp+0D8h]; this
0x18000e014  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000e01b  mov     r9d, eax; char *
0x18000e01e  mov     edx, 117h; void *
0x18000e023  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e028  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e02c  inc     rax
0x18000e02f  cmp     [rdi+rax*2], r13w
0x18000e034  jnz     short loc_18000E02C
0x18000e036  lea     rdi, [rdi+rax*2]
0x18000e03a  inc     r14d
0x18000e03d  add     rdi, 2
0x18000e041  cmp     r14d, [rsp+1D0h+var_1A0]
0x18000e046  jb      loc_18000DF8C
0x18000e04c  mov     rcx, rbx; this
0x18000e04f  call    ?MarkCurrentTime@CFontCollection@@QEAAJXZ; CFontCollection::MarkCurrentTime(void)
0x18000e054  mov     edi, eax
0x18000e056  test    eax, eax
0x18000e058  jns     short loc_18000E061
0x18000e05a  mov     edx, 125h
0x18000e05f  jmp     short loc_18000E081
0x18000e061  lea     rcx, [rbx+8]; unsigned __int16 *
0x18000e065  mov     edx, 20h ; ' '; unsigned __int64
0x18000e06a  lea     r8, c_szRootEnumeratorName; "ROOT"
0x18000e071  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e076  mov     edi, eax
0x18000e078  test    eax, eax
0x18000e07a  jns     short loc_18000E0BC
0x18000e07c  mov     edx, 128h; void *
0x18000e081  mov     rcx, [rbp+0D8h]; this
0x18000e088  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000e08f  mov     r9d, edi; char *
0x18000e092  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e097  mov     rcx, [rbp+0D8h]; this
0x18000e09e  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000e0a5  mov     r9d, edi; char *
0x18000e0a8  mov     edx, 12Eh; void *
0x18000e0ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e0b2  mov     rcx, rbx; this
0x18000e0b5  call    ?Release@CFontCollection@@QEAAKXZ; CFontCollection::Release(void)
0x18000e0ba  jmp     short loc_18000E0C0
0x18000e0bc  mov     [r12], rbx
0x18000e0c0  mov     rcx, rsi; this
0x18000e0c3  call    ?_ApplyDefaultFmsFilter@CFontCollectionBuilder@@AEAAJXZ; CFontCollectionBuilder::_ApplyDefaultFmsFilter(void)
0x18000e0c8  test    eax, eax
0x18000e0ca  jns     short loc_18000E0E7
0x18000e0cc  mov     edx, 134h; void *
0x18000e0d1  mov     rcx, [rbp+0D8h]; this
0x18000e0d8  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000e0df  mov     r9d, eax; char *
0x18000e0e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e0e7  call    cs:__imp_GetProcessHeap
0x18000e0ed  mov     r8, r15; lpMem
0x18000e0f0  xor     edx, edx; dwFlags
0x18000e0f2  mov     rcx, rax; hHeap
0x18000e0f5  call    cs:__imp_HeapFree
0x18000e0fb  mov     edx, edi
0x18000e0fd  lea     rcx, [rsp+1D0h+var_190]
0x18000e102  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000e107  lea     rcx, [rsp+1D0h+var_190]; this
0x18000e10c  call    ??1_BuildRootDpa@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::_BuildRootDpa::~_BuildRootDpa(void)
0x18000e111  mov     eax, edi
0x18000e113  mov     rcx, [rbp+0D0h+var_40]
0x18000e11a  xor     rcx, rsp; StackCookie
0x18000e11d  call    __security_check_cookie
0x18000e122  mov     rbx, [rsp+1D0h+arg_10]
0x18000e12a  add     rsp, 1A0h
0x18000e131  pop     r15
0x18000e133  pop     r14
0x18000e135  pop     r13
0x18000e137  pop     r12
0x18000e139  pop     rdi
0x18000e13a  pop     rsi
0x18000e13b  pop     rbp
0x18000e13c  retn
```
