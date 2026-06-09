# CFontCollectionBuilder::_GetFontType(uint,ulong *)

- ea: `0x18000ed04`
- end: `0x18000ee5e`
- name: `?_GetFontType@CFontCollectionBuilder@@AEAAJIPEAK@Z`
- size: `346`
- prototype: `__int64 __fastcall(CFontCollectionBuilder *__hidden this, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000f6b8`
- `0x18000fc40`

## callees

- `0x180008aec`
- `0x180008f04`
- `0x18000a8cc`
- `0x18000ae20`
- `0x18000ed04`
- `0x18000f518`
- `0x180031070`

## import_xrefs

- `fms!FmsGetFontProperty` at `0x18000edc3`
- `fms!FmsGetFontProperty` at `0x18000edc3`

## string_xrefs

- `0x18000ed5e`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000ed82`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000edd7`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CFontCollectionBuilder::_GetFontType(
        CFontCollectionBuilder *this,
        unsigned int a2,
        unsigned int *a3)
{
  __int64 v6; // rcx
  int FontProperty; // eax
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-198h]
  int v11; // [rsp+30h] [rbp-188h] BYREF
  int v12[3]; // [rsp+34h] [rbp-184h] BYREF
  _QWORD v13[42]; // [rsp+40h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v13,
    "_GetFontType");
  v13[0] = &FontFldrTraceLoggingTelemetry::_GetFontType::`vftable';
  FontFldrTraceLoggingTelemetry::_GetFontType::StartActivity((FontFldrTraceLoggingTelemetry::_GetFontType *)v13);
  if ( !*(_QWORD *)this )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x403,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)0x80004003LL,
      v10);
  if ( !a3 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x404,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)0x80070057LL,
      v10);
  v6 = *(_QWORD *)this;
  v11 = 7;
  v12[0] = 4;
  FontProperty = FmsGetFontProperty(v6, a2, 1, v12);
  v8 = FontProperty;
  if ( FontProperty >= 0 )
    *a3 = 0;
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x411,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)(unsigned int)FontProperty,
      (int)&v11);
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)v13, v8);
  FontFldrTraceLoggingTelemetry::_GetFontType::~_GetFontType((FontFldrTraceLoggingTelemetry::_GetFontType *)v13);
  return v8;
}

```

## disassembly

```asm
0x18000ed04  push    rbx
0x18000ed06  push    rsi
0x18000ed07  push    rdi
0x18000ed08  sub     rsp, 1A0h
0x18000ed0f  mov     rax, cs:__security_cookie
0x18000ed16  xor     rax, rsp
0x18000ed19  mov     [rsp+1B8h+var_28], rax
0x18000ed21  mov     esi, edx
0x18000ed23  mov     rbx, rcx
0x18000ed26  lea     rdx, aGetfonttype; "_GetFontType"
0x18000ed2d  mov     rdi, r8
0x18000ed30  lea     rcx, [rsp+1B8h+var_178]
0x18000ed35  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ed3a  lea     rax, ??_7_GetFontType@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::_GetFontType::`vftable'
0x18000ed41  lea     rcx, [rsp+1B8h+var_178]; this
0x18000ed46  mov     [rsp+1B8h+var_178], rax
0x18000ed4b  call    ?StartActivity@_GetFontType@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::_GetFontType::StartActivity(void)
0x18000ed50  cmp     qword ptr [rbx], 0
0x18000ed54  jnz     short loc_18000ED75
0x18000ed56  mov     rcx, [rsp+1B8h]; this
0x18000ed5e  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000ed65  mov     r9d, 80004003h; char *
0x18000ed6b  mov     edx, 403h; void *
0x18000ed70  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ed75  test    rdi, rdi
0x18000ed78  jnz     short loc_18000ED99
0x18000ed7a  mov     rcx, [rsp+1B8h]; this
0x18000ed82  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000ed89  mov     r9d, 80070057h; char *
0x18000ed8f  mov     edx, 404h; void *
0x18000ed94  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ed99  mov     rcx, [rbx]
0x18000ed9c  lea     rax, [rsp+1B8h+var_188]
0x18000eda1  lea     r9, [rsp+1B8h+var_184]
0x18000eda6  mov     qword ptr [rsp+1B8h+var_198], rax; int
0x18000edab  mov     r8d, 1
0x18000edb1  mov     [rsp+1B8h+var_188], 7
0x18000edb9  mov     edx, esi
0x18000edbb  mov     [rsp+1B8h+var_184], 4
0x18000edc3  call    cs:__imp_FmsGetFontProperty
0x18000edc9  mov     ebx, eax
0x18000edcb  test    eax, eax
0x18000edcd  jns     short loc_18000EDED
0x18000edcf  mov     rcx, [rsp+1B8h]; this
0x18000edd7  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000edde  mov     r9d, eax; char *
0x18000ede1  mov     edx, 411h; void *
0x18000ede6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000edeb  jmp     short loc_18000EE2B
0x18000eded  mov     eax, [rsp+1B8h+var_188]
0x18000edf1  test    eax, eax
0x18000edf3  jz      short loc_18000EE24
0x18000edf5  mov     ecx, 2
0x18000edfa  sub     eax, ecx
0x18000edfc  jz      short loc_18000EE1D
0x18000edfe  sub     eax, 1
0x18000ee01  jz      short loc_18000EE16
0x18000ee03  sub     eax, 1
0x18000ee06  jz      short loc_18000EE16
0x18000ee08  sub     eax, 1
0x18000ee0b  jz      short loc_18000EE29
0x18000ee0d  cmp     eax, 1
0x18000ee10  jz      short loc_18000EE24
0x18000ee12  xor     ecx, ecx
0x18000ee14  jmp     short loc_18000EE29
0x18000ee16  mov     ecx, 5
0x18000ee1b  jmp     short loc_18000EE29
0x18000ee1d  mov     ecx, 3
0x18000ee22  jmp     short loc_18000EE29
0x18000ee24  mov     ecx, 1
0x18000ee29  mov     [rdi], ecx
0x18000ee2b  mov     edx, ebx
0x18000ee2d  lea     rcx, [rsp+1B8h+var_178]
0x18000ee32  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000ee37  lea     rcx, [rsp+1B8h+var_178]; this
0x18000ee3c  call    ??1_GetFontType@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::_GetFontType::~_GetFontType(void)
0x18000ee41  mov     eax, ebx
0x18000ee43  mov     rcx, [rsp+1B8h+var_28]
0x18000ee4b  xor     rcx, rsp; StackCookie
0x18000ee4e  call    __security_check_cookie
0x18000ee53  add     rsp, 1A0h
0x18000ee5a  pop     rdi
0x18000ee5b  pop     rsi
0x18000ee5c  pop     rbx
0x18000ee5d  retn
```
