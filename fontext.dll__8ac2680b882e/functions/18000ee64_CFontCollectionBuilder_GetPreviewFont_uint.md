# CFontCollectionBuilder::_GetPreviewFont(uint *)

- ea: `0x18000ee64`
- end: `0x18000f06e`
- name: `?_GetPreviewFont@CFontCollectionBuilder@@AEAAJPEAI@Z`
- size: `522`
- prototype: `__int64 __fastcall(CFontCollectionBuilder *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000fc40`

## callees

- `0x180008aec`
- `0x180008f30`
- `0x18000a968`
- `0x18000ae20`
- `0x18000ee64`
- `0x18000f3b0`
- `0x18000f518`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eff1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eff1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000efe3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000efe3`
- `fms!FmsGetFilteredFontList` at `0x18000ef19`
- `fms!FmsGetFilteredFontList` at `0x18000ef85`
- `fms!FmsGetFilteredFontList` at `0x18000ef19`
- `fms!FmsGetFilteredFontList` at `0x18000ef85`

## string_xrefs

- `0x18000eece`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000eef1`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000ef2c`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000ef98`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000f010`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CFontCollectionBuilder::_GetPreviewFont(CFontCollectionBuilder *this, unsigned int *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // esi
  int FilteredFontList; // eax
  signed int v7; // edi
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v10; // rax
  unsigned int *v11; // r14
  int v12; // eax
  unsigned int i; // r13d
  unsigned int v14; // ebx
  HANDLE v15; // rax
  int v17[4]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v18[42]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "_GetPreviewFont");
  v18[0] = &FontFldrTraceLoggingTelemetry::_GetPreviewFont::`vftable';
  FontFldrTraceLoggingTelemetry::_GetPreviewFont::StartActivity((FontFldrTraceLoggingTelemetry::_GetPreviewFont *)v18);
  if ( !*(_QWORD *)this )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x50C,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)0x80004003LL,
      v17[0]);
  if ( !a2 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x50D,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)0x80070057LL,
      v17[0]);
  v4 = *(_QWORD *)this;
  v5 = 0;
  v17[0] = 0;
  FilteredFontList = FmsGetFilteredFontList(v4, v17, 0);
  v7 = FilteredFontList;
  if ( FilteredFontList >= 0 )
  {
    if ( v17[0] )
    {
      v8 = 4LL * (unsigned int)v17[0];
      ProcessHeap = GetProcessHeap();
      v10 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v8);
      v11 = v10;
      if ( v10 )
      {
        v12 = FmsGetFilteredFontList(*(_QWORD *)this, v17, v10);
        v7 = v12;
        if ( v12 >= 0 )
        {
          v5 = *v11;
          for ( i = 1; i < v17[0]; v5 = v14 )
          {
            v14 = v11[i];
            if ( !(unsigned int)CFontCollectionBuilder::_IsFirstFmsFontBetter(this, v14, v5) )
              v14 = v5;
            ++i;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x521,
            (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
            (const char *)(unsigned int)v12,
            v17[0]);
        }
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v11);
        if ( v7 >= 0 )
          goto LABEL_20;
      }
      else
      {
        v7 = -2147024882;
      }
    }
    else
    {
      v7 = -2147467259;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x515,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)(unsigned int)FilteredFontList,
      v17[0]);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x534,
    (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
    (const char *)(unsigned int)v7,
    v17[0]);
  if ( v7 >= 0 )
LABEL_20:
    *a2 = v5;
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v18, v7);
  FontFldrTraceLoggingTelemetry::_GetPreviewFont::~_GetPreviewFont((FontFldrTraceLoggingTelemetry::_GetPreviewFont *)v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ee64  mov     [rsp-8+arg_10], rbx
0x18000ee69  push    rbp
0x18000ee6a  push    rsi
0x18000ee6b  push    rdi
0x18000ee6c  push    r12
0x18000ee6e  push    r13
0x18000ee70  push    r14
0x18000ee72  push    r15
0x18000ee74  lea     rbp, [rsp-90h]
0x18000ee7c  sub     rsp, 190h
0x18000ee83  mov     rax, cs:__security_cookie
0x18000ee8a  xor     rax, rsp
0x18000ee8d  mov     [rbp+0C0h+var_40], rax
0x18000ee94  mov     r12, rdx
0x18000ee97  mov     r15, rcx
0x18000ee9a  lea     rdx, aGetpreviewfont; "_GetPreviewFont"
0x18000eea1  lea     rcx, [rsp+1C0h+var_190]
0x18000eea6  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000eeab  lea     rax, ??_7_GetPreviewFont@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::_GetPreviewFont::`vftable'
0x18000eeb2  lea     rcx, [rsp+1C0h+var_190]; this
0x18000eeb7  mov     [rsp+1C0h+var_190], rax
0x18000eebc  call    ?StartActivity@_GetPreviewFont@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::_GetPreviewFont::StartActivity(void)
0x18000eec1  cmp     qword ptr [r15], 0
0x18000eec5  jnz     short loc_18000EEE5
0x18000eec7  mov     rcx, [rbp+0C8h]; this
0x18000eece  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000eed5  mov     r9d, 80004003h; char *
0x18000eedb  mov     edx, 50Ch; void *
0x18000eee0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000eee5  test    r12, r12
0x18000eee8  jnz     short loc_18000EF08
0x18000eeea  mov     rcx, [rbp+0C8h]; this
0x18000eef1  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000eef8  mov     r9d, 80070057h; char *
0x18000eefe  mov     edx, 50Dh; void *
0x18000ef03  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ef08  mov     rcx, [r15]
0x18000ef0b  lea     rdx, [rsp+1C0h+var_1A0]
0x18000ef10  xor     esi, esi
0x18000ef12  xor     r8d, r8d
0x18000ef15  mov     [rsp+1C0h+var_1A0], esi; int
0x18000ef19  call    cs:__imp_FmsGetFilteredFontList
0x18000ef1f  mov     edi, eax
0x18000ef21  test    eax, eax
0x18000ef23  jns     short loc_18000EF45
0x18000ef25  mov     rcx, [rbp+0C8h]; this
0x18000ef2c  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000ef33  mov     r9d, eax; char *
0x18000ef36  mov     edx, 515h; void *
0x18000ef3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ef40  jmp     loc_18000F009
0x18000ef45  mov     eax, [rsp+1C0h+var_1A0]
0x18000ef49  test    eax, eax
0x18000ef4b  jz      loc_18000F004
0x18000ef51  mov     ebx, eax
0x18000ef53  shl     rbx, 2
0x18000ef57  call    cs:__imp_GetProcessHeap
0x18000ef5d  mov     r8, rbx; dwBytes
0x18000ef60  mov     edx, 8; dwFlags
0x18000ef65  mov     rcx, rax; hHeap
0x18000ef68  call    cs:__imp_HeapAlloc
0x18000ef6e  mov     r14, rax
0x18000ef71  test    rax, rax
0x18000ef74  jz      loc_18000EFFD
0x18000ef7a  mov     rcx, [r15]
0x18000ef7d  lea     rdx, [rsp+1C0h+var_1A0]
0x18000ef82  mov     r8, rax
0x18000ef85  call    cs:__imp_FmsGetFilteredFontList
0x18000ef8b  mov     edi, eax
0x18000ef8d  test    eax, eax
0x18000ef8f  jns     short loc_18000EFAE
0x18000ef91  mov     rcx, [rbp+0C8h]; this
0x18000ef98  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000ef9f  mov     r9d, eax; char *
0x18000efa2  mov     edx, 521h; void *
0x18000efa7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000efac  jmp     short loc_18000EFE3
0x18000efae  mov     esi, [r14]
0x18000efb1  mov     r13d, 1
0x18000efb7  cmp     [rsp+1C0h+var_1A0], r13d
0x18000efbc  jbe     short loc_18000EFE3
0x18000efbe  mov     eax, r13d
0x18000efc1  mov     r8d, esi; unsigned int
0x18000efc4  mov     rcx, r15; this
0x18000efc7  mov     ebx, [r14+rax*4]
0x18000efcb  mov     edx, ebx; unsigned int
0x18000efcd  call    ?_IsFirstFmsFontBetter@CFontCollectionBuilder@@AEAAHII@Z; CFontCollectionBuilder::_IsFirstFmsFontBetter(uint,uint)
0x18000efd2  test    eax, eax
0x18000efd4  cmovz   ebx, esi
0x18000efd7  inc     r13d
0x18000efda  mov     esi, ebx
0x18000efdc  cmp     r13d, [rsp+1C0h+var_1A0]
0x18000efe1  jb      short loc_18000EFBE
0x18000efe3  call    cs:__imp_GetProcessHeap
0x18000efe9  mov     r8, r14; lpMem
0x18000efec  xor     edx, edx; dwFlags
0x18000efee  mov     rcx, rax; hHeap
0x18000eff1  call    cs:__imp_HeapFree
0x18000eff7  test    edi, edi
0x18000eff9  jns     short loc_18000F028
0x18000effb  jmp     short loc_18000F009
0x18000effd  mov     edi, 8007000Eh
0x18000f002  jmp     short loc_18000F009
0x18000f004  mov     edi, 80004005h
0x18000f009  mov     rcx, [rbp+0C8h]; this
0x18000f010  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000f017  mov     r9d, edi; char *
0x18000f01a  mov     edx, 534h; void *
0x18000f01f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f024  test    edi, edi
0x18000f026  js      short loc_18000F02C
0x18000f028  mov     [r12], esi
0x18000f02c  mov     edx, edi
0x18000f02e  lea     rcx, [rsp+1C0h+var_190]
0x18000f033  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000f038  lea     rcx, [rsp+1C0h+var_190]; this
0x18000f03d  call    ??1_GetPreviewFont@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::_GetPreviewFont::~_GetPreviewFont(void)
0x18000f042  mov     eax, edi
0x18000f044  mov     rcx, [rbp+0C0h+var_40]
0x18000f04b  xor     rcx, rsp; StackCookie
0x18000f04e  call    __security_check_cookie
0x18000f053  mov     rbx, [rsp+1C0h+arg_10]
0x18000f05b  add     rsp, 190h
0x18000f062  pop     r15
0x18000f064  pop     r14
0x18000f066  pop     r13
0x18000f068  pop     r12
0x18000f06a  pop     rdi
0x18000f06b  pop     rsi
0x18000f06c  pop     rbp
0x18000f06d  retn
```
