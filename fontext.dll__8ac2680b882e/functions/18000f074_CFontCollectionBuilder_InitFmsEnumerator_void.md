# CFontCollectionBuilder::_InitFmsEnumerator(void)

- ea: `0x18000f074`
- end: `0x18000f191`
- name: `?_InitFmsEnumerator@CFontCollectionBuilder@@AEAAJXZ`
- size: `285`
- prototype: `__int64 __fastcall(CFontCollectionBuilder *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18000db98`
- `0x18000de28`

## callees

- `0x180008aec`
- `0x180008f5c`
- `0x18000aa04`
- `0x18000ae20`
- `0x18000dab0`
- `0x18000f074`
- `0x18000f518`
- `0x180031070`

## import_xrefs

- `fms!FmsResetEnumerator` at `0x18000f0eb`
- `fms!FmsResetEnumerator` at `0x18000f0eb`
- `fms!FmsInitializeEnumerator` at `0x18000f126`
- `fms!FmsInitializeEnumerator` at `0x18000f126`
- `fms!FmsFreeEnumerator` at `0x18000f0ce`
- `fms!FmsFreeEnumerator` at `0x18000f0ce`

## string_xrefs

- `0x18000f0fd`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`
- `0x18000f13a`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CFontCollectionBuilder::_InitFmsEnumerator(CFontCollectionBuilder *this)
{
  int v2; // eax
  unsigned int v3; // edi
  int v4; // eax
  int v6[84]; // [rsp+20h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v6,
    "_InitFmsEnumerator");
  *(_QWORD *)v6 = &FontFldrTraceLoggingTelemetry::_InitFmsEnumerator::`vftable';
  FontFldrTraceLoggingTelemetry::_InitFmsEnumerator::StartActivity((FontFldrTraceLoggingTelemetry::_InitFmsEnumerator *)v6);
  if ( !*(_QWORD *)this )
    goto LABEL_8;
  if ( !*((_DWORD *)this + 2) )
  {
    if ( *((_DWORD *)this + 3) )
    {
      v2 = FmsResetEnumerator();
      if ( v2 >= 0 )
        *((_DWORD *)this + 3) = 0;
      else
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1A1,
          (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
          (const char *)(unsigned int)v2,
          v6[0]);
    }
LABEL_8:
    v3 = 0;
    if ( *(_QWORD *)this )
      goto LABEL_12;
    goto LABEL_9;
  }
  FmsFreeEnumerator(this);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
LABEL_9:
  v4 = FmsInitializeEnumerator(this, 0);
  v3 = v4;
  if ( v4 >= 0 )
    CFontCollectionBuilder::_ApplyDefaultFmsFilter(this);
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
      (const char *)(unsigned int)v4,
      v6[0]);
LABEL_12:
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v6, v3);
  FontFldrTraceLoggingTelemetry::_InitFmsEnumerator::~_InitFmsEnumerator((FontFldrTraceLoggingTelemetry::_InitFmsEnumerator *)v6);
  return v3;
}

```

## disassembly

```asm
0x18000f074  mov     [rsp+arg_8], rbx
0x18000f079  push    rdi
0x18000f07a  sub     rsp, 180h
0x18000f081  mov     rax, cs:__security_cookie
0x18000f088  xor     rax, rsp
0x18000f08b  mov     [rsp+188h+var_18], rax
0x18000f093  mov     rbx, rcx
0x18000f096  lea     rdx, aInitfmsenumera; "_InitFmsEnumerator"
0x18000f09d  lea     rcx, [rsp+188h+var_168]
0x18000f0a2  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000f0a7  lea     rax, ??_7_InitFmsEnumerator@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::_InitFmsEnumerator::`vftable'
0x18000f0ae  lea     rcx, [rsp+188h+var_168]; this
0x18000f0b3  mov     qword ptr [rsp+188h+var_168], rax; int
0x18000f0b8  call    ?StartActivity@_InitFmsEnumerator@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::_InitFmsEnumerator::StartActivity(void)
0x18000f0bd  mov     rcx, [rbx]
0x18000f0c0  test    rcx, rcx
0x18000f0c3  jz      short loc_18000F11A
0x18000f0c5  cmp     dword ptr [rbx+8], 0
0x18000f0c9  jz      short loc_18000F0E5
0x18000f0cb  mov     rcx, rbx
0x18000f0ce  call    cs:__imp_FmsFreeEnumerator
0x18000f0d4  mov     qword ptr [rbx], 0
0x18000f0db  mov     qword ptr [rbx+8], 0
0x18000f0e3  jmp     short loc_18000F121
0x18000f0e5  cmp     dword ptr [rbx+0Ch], 0
0x18000f0e9  jz      short loc_18000F11A
0x18000f0eb  call    cs:__imp_FmsResetEnumerator
0x18000f0f1  test    eax, eax
0x18000f0f3  jns     short loc_18000F113
0x18000f0f5  mov     rcx, [rsp+188h]; this
0x18000f0fd  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000f104  mov     r9d, eax; char *
0x18000f107  mov     edx, 1A1h; void *
0x18000f10c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f111  jmp     short loc_18000F11A
0x18000f113  mov     dword ptr [rbx+0Ch], 0
0x18000f11a  xor     edi, edi
0x18000f11c  cmp     [rbx], rdi
0x18000f11f  jnz     short loc_18000F158
0x18000f121  xor     edx, edx
0x18000f123  mov     rcx, rbx
0x18000f126  call    cs:__imp_FmsInitializeEnumerator
0x18000f12c  mov     edi, eax
0x18000f12e  test    eax, eax
0x18000f130  jns     short loc_18000F150
0x18000f132  mov     rcx, [rsp+188h]; this
0x18000f13a  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x18000f141  mov     r9d, eax; char *
0x18000f144  mov     edx, 1ABh; void *
0x18000f149  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f14e  jmp     short loc_18000F158
0x18000f150  mov     rcx, rbx; this
0x18000f153  call    ?_ApplyDefaultFmsFilter@CFontCollectionBuilder@@AEAAJXZ; CFontCollectionBuilder::_ApplyDefaultFmsFilter(void)
0x18000f158  mov     edx, edi
0x18000f15a  lea     rcx, [rsp+188h+var_168]
0x18000f15f  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000f164  lea     rcx, [rsp+188h+var_168]; this
0x18000f169  call    ??1_InitFmsEnumerator@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::_InitFmsEnumerator::~_InitFmsEnumerator(void)
0x18000f16e  mov     eax, edi
0x18000f170  mov     rcx, [rsp+188h+var_18]
0x18000f178  xor     rcx, rsp; StackCookie
0x18000f17b  call    __security_check_cookie
0x18000f180  mov     rbx, [rsp+188h+arg_8]
0x18000f188  add     rsp, 180h
0x18000f18f  pop     rdi
0x18000f190  retn
```
