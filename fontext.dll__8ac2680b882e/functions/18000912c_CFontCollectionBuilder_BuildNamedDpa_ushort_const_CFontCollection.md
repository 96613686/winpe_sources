# CFontCollectionBuilder::BuildNamedDpa(ushort const *,CFontCollection * *)

- ea: `0x18000912c`
- end: `0x18000925c`
- name: `?BuildNamedDpa@CFontCollectionBuilder@@QEAAJPEBGPEAPEAVCFontCollection@@@Z`
- size: `304`
- prototype: `int(CFontCollectionBuilder *__hidden this, const unsigned __int16 *, struct CFontCollection **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b34c`

## callees

- `0x180008aec`
- `0x180008ca4`
- `0x18000912c`
- `0x18000a2b4`
- `0x18000ae20`
- `0x18000db98`
- `0x18000de28`
- `0x18000f518`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009184`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009184`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000921b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000921b`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800091c8`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800091c8`

## string_xrefs

- `0x180009209`: `shell\osshell\fontfldr\fontext2\dll\collectionbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CFontCollectionBuilder::BuildNamedDpa(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        struct CFontCollection **a3)
{
  RTL_SRWLOCK *v6; // rbp
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int lpString2; // [rsp+20h] [rbp-1A8h]
  _QWORD v12[42]; // [rsp+50h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v12,
    "BuildNamedDpa");
  v12[0] = &FontFldrTraceLoggingTelemetry::BuildNamedDpa::`vftable';
  FontFldrTraceLoggingTelemetry::BuildNamedDpa::StartActivity((FontFldrTraceLoggingTelemetry::BuildNamedDpa *)v12);
  v6 = this + 2;
  AcquireSRWLockExclusive(this + 2);
  if ( CompareStringEx(&psz, 1u, a2, -1, L"ROOT", -1, 0, 0, 0) == 2 )
  {
    v7 = CFontCollectionBuilder::_BuildRootDpa((CFontCollectionBuilder *)this, a3);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 84;
LABEL_6:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shell\\osshell\\fontfldr\\fontext2\\dll\\collectionbuilder.cpp",
        (const char *)(unsigned int)v7,
        lpString2);
    }
  }
  else
  {
    v7 = CFontCollectionBuilder::_BuildFamilyDpa((CFontCollectionBuilder *)this, a2, a3);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 88;
      goto LABEL_6;
    }
  }
  ReleaseSRWLockExclusive(v6);
  wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v12, v8);
  FontFldrTraceLoggingTelemetry::BuildNamedDpa::~BuildNamedDpa((FontFldrTraceLoggingTelemetry::BuildNamedDpa *)v12);
  return v8;
}

```

## disassembly

```asm
0x18000912c  mov     [rsp+arg_18], rbx
0x180009131  push    rbp
0x180009132  push    rsi
0x180009133  push    rdi
0x180009134  sub     rsp, 1B0h
0x18000913b  mov     rax, cs:__security_cookie
0x180009142  xor     rax, rsp
0x180009145  mov     [rsp+1C8h+var_28], rax
0x18000914d  mov     rsi, rdx
0x180009150  mov     rbx, rcx
0x180009153  lea     rdx, aBuildnameddpa; "BuildNamedDpa"
0x18000915a  mov     rdi, r8
0x18000915d  lea     rcx, [rsp+1C8h+var_178]
0x180009162  call    ??0?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180009167  lea     rax, ??_7BuildNamedDpa@FontFldrTraceLoggingTelemetry@@6B@; const FontFldrTraceLoggingTelemetry::BuildNamedDpa::`vftable'
0x18000916e  lea     rcx, [rsp+1C8h+var_178]; this
0x180009173  mov     [rsp+1C8h+var_178], rax
0x180009178  call    ?StartActivity@BuildNamedDpa@FontFldrTraceLoggingTelemetry@@QEAAXXZ; FontFldrTraceLoggingTelemetry::BuildNamedDpa::StartActivity(void)
0x18000917d  lea     rbp, [rbx+10h]
0x180009181  mov     rcx, rbp; SRWLock
0x180009184  call    cs:__imp_AcquireSRWLockExclusive
0x18000918a  mov     [rsp+1C8h+lParam], 0; lParam
0x180009193  lea     rax, c_szRootEnumeratorName; "ROOT"
0x18000919a  or      r9d, 0FFFFFFFFh; cchCount1
0x18000919e  mov     [rsp+1C8h+lpReserved], 0; lpReserved
0x1800091a7  mov     [rsp+1C8h+lpVersionInformation], 0; lpVersionInformation
0x1800091b0  lea     rcx, psz; lpLocaleName
0x1800091b7  mov     [rsp+1C8h+cchCount2], r9d; cchCount2
0x1800091bc  mov     r8, rsi; lpString1
0x1800091bf  mov     [rsp+1C8h+lpString2], rax; int
0x1800091c4  lea     edx, [r9+2]; dwCmpFlags
0x1800091c8  call    cs:__imp_CompareStringEx
0x1800091ce  mov     rcx, rbx; this
0x1800091d1  cmp     eax, 2
0x1800091d4  jnz     short loc_1800091EB
0x1800091d6  mov     rdx, rdi; struct CFontCollection **
0x1800091d9  call    ?_BuildRootDpa@CFontCollectionBuilder@@AEAAJPEAPEAVCFontCollection@@@Z; CFontCollectionBuilder::_BuildRootDpa(CFontCollection * *)
0x1800091de  mov     ebx, eax
0x1800091e0  test    eax, eax
0x1800091e2  jns     short loc_180009218
0x1800091e4  mov     edx, 54h ; 'T'
0x1800091e9  jmp     short loc_180009201
0x1800091eb  mov     r8, rdi; struct CFontCollection **
0x1800091ee  mov     rdx, rsi; unsigned __int16 *
0x1800091f1  call    ?_BuildFamilyDpa@CFontCollectionBuilder@@AEAAJPEBGPEAPEAVCFontCollection@@@Z; CFontCollectionBuilder::_BuildFamilyDpa(ushort const *,CFontCollection * *)
0x1800091f6  mov     ebx, eax
0x1800091f8  test    eax, eax
0x1800091fa  jns     short loc_180009218
0x1800091fc  mov     edx, 58h ; 'X'; void *
0x180009201  mov     rcx, [rsp+1C8h]; this
0x180009209  lea     r8, aShellOsshellFo_1; "shell\\osshell\\fontfldr\\fontext2\\dll"...
0x180009210  mov     r9d, eax; char *
0x180009213  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009218  mov     rcx, rbp; SRWLock
0x18000921b  call    cs:__imp_ReleaseSRWLockExclusive
0x180009221  mov     edx, ebx
0x180009223  lea     rcx, [rsp+1C8h+var_178]
0x180009228  call    ?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000922d  lea     rcx, [rsp+1C8h+var_178]; this
0x180009232  call    ??1BuildNamedDpa@FontFldrTraceLoggingTelemetry@@QEAA@XZ; FontFldrTraceLoggingTelemetry::BuildNamedDpa::~BuildNamedDpa(void)
0x180009237  mov     eax, ebx
0x180009239  mov     rcx, [rsp+1C8h+var_28]
0x180009241  xor     rcx, rsp; StackCookie
0x180009244  call    __security_check_cookie
0x180009249  mov     rbx, [rsp+1C8h+arg_18]
0x180009251  add     rsp, 1B0h
0x180009258  pop     rdi
0x180009259  pop     rsi
0x18000925a  pop     rbp
0x18000925b  retn
```
