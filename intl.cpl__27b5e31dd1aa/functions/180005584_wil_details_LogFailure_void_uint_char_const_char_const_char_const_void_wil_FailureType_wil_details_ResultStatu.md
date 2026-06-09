# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005584`
- end: `0x180005881`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003c90`
- `0x180003fdc`

## callees

- `0x180003bd0`
- `0x180004ba4`
- `0x1800053c0`
- `0x180005584`
- `0x180005ba8`
- `0x180005bd0`
- `0x180005be4`
- `0x180005c00`
- `0x180006984`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000583c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000583c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800057ca`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180005584  mov     [rsp+arg_10], rbx
0x180005589  mov     [rsp+arg_8], edx
0x18000558d  mov     [rsp+arg_0], rcx
0x180005592  push    rbp
0x180005593  push    rsi
0x180005594  push    rdi
0x180005595  push    r12
0x180005597  push    r13
0x180005599  push    r14
0x18000559b  push    r15
0x18000559d  sub     rsp, 40h
0x1800055a1  mov     r12, r9
0x1800055a4  mov     r13, r8
0x1800055a7  mov     r10, rcx
0x1800055aa  xor     eax, eax
0x1800055ac  mov     rsi, [rsp+78h+lpOutputString]
0x1800055b4  mov     [rsi], ax
0x1800055b7  mov     rax, [rsp+78h+arg_60]
0x1800055bf  mov     byte ptr [rax], 0
0x1800055c2  mov     r14, [rsp+78h+arg_38]
0x1800055ca  mov     edi, [r14]
0x1800055cd  mov     rbx, [rsp+78h+arg_78]
0x1800055d5  mov     [rbx+8], edi
0x1800055d8  mov     eax, [r14+4]
0x1800055dc  mov     [rbx+0Ch], eax
0x1800055df  xor     ebp, ebp
0x1800055e1  mov     r15d, [rsp+78h+arg_30]
0x1800055e9  mov     ecx, r15d
0x1800055ec  test    r15d, r15d
0x1800055ef  jz      short loc_18000565B
0x1800055f1  sub     ecx, 1
0x1800055f4  jz      short loc_180005652
0x1800055f6  sub     ecx, 1
0x1800055f9  jz      short loc_180005609
0x1800055fb  cmp     ecx, 1
0x1800055fe  jnz     short loc_180005664
0x180005600  mov     ecx, edi; this
0x180005602  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005607  jmp     short loc_180005662
0x180005609  test    edi, edi
0x18000560b  js      short loc_180005649
0x18000560d  mov     [rsp+78h+var_40], ebp
0x180005611  mov     edi, 8007029Ch
0x180005616  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000561a  mov     rax, [rsp+78h+arg_28]
0x180005622  mov     [rsp+78h+var_50], rax; __int64
0x180005627  mov     rax, [rsp+78h+arg_20]
0x18000562f  mov     [rsp+78h+var_58], rax; __int64
0x180005634  mov     rcx, r10; int
0x180005637  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000563c  mov     [rbx+8], edi
0x18000563f  mov     ecx, edi; this
0x180005641  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005646  mov     [rbx+0Ch], eax
0x180005649  mov     ecx, edi; this
0x18000564b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005650  jmp     short loc_180005662
0x180005652  mov     ecx, edi; this
0x180005654  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005659  jmp     short loc_180005662
0x18000565b  mov     ecx, edi; this
0x18000565d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005662  mov     ebp, eax
0x180005664  mov     [rbx], r15d
0x180005667  mov     eax, [rsp+78h+arg_70]
0x18000566e  mov     [rbx+4], eax
0x180005671  cmp     dword ptr [r14+8], 1
0x180005676  jnz     short loc_18000567E
0x180005678  or      eax, 8
0x18000567b  mov     [rbx+4], eax
0x18000567e  mov     eax, 1
0x180005683  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000568b  inc     eax
0x18000568d  mov     [rbx+10h], eax
0x180005690  mov     rax, [rsp+78h+arg_40]
0x180005698  xor     edi, edi
0x18000569a  test    rax, rax
0x18000569d  jz      short loc_1800056A4
0x18000569f  cmp     [rax], di
0x1800056a2  jnz     short loc_1800056A7
0x1800056a4  mov     rax, rdi
0x1800056a7  mov     [rbx+18h], rax
0x1800056ab  call    cs:__imp_GetCurrentThreadId
0x1800056b1  mov     [rbx+20h], eax
0x1800056b4  mov     [rbx+38h], r13
0x1800056b8  mov     eax, [rsp+78h+arg_8]
0x1800056bf  mov     [rbx+40h], eax
0x1800056c2  mov     [rbx+44h], ebp
0x1800056c5  mov     rax, [rsp+78h+arg_20]
0x1800056cd  mov     [rbx+28h], rax
0x1800056d1  mov     [rbx+30h], r12
0x1800056d5  mov     rax, [rsp+78h+arg_28]
0x1800056dd  mov     [rbx+88h], rax
0x1800056e4  mov     rax, [rsp+78h+arg_0]
0x1800056ec  mov     [rbx+90h], rax
0x1800056f3  mov     [rbx+48h], rdi
0x1800056f7  xorps   xmm0, xmm0
0x1800056fa  xor     eax, eax
0x1800056fc  movups  xmmword ptr [rbx+68h], xmm0
0x180005700  mov     [rbx+78h], rax
0x180005704  movups  xmmword ptr [rbx+50h], xmm0
0x180005708  mov     [rbx+60h], rax
0x18000570c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005713  test    rax, rax
0x180005716  jz      short loc_18000571F
0x180005718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000571d  jmp     short loc_180005722
0x18000571f  mov     rax, rdi
0x180005722  mov     [rbx+80h], rax
0x180005729  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005730  test    rax, rax
0x180005733  jz      short loc_18000573D
0x180005735  mov     rcx, rbx
0x180005738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000573d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005744  test    rax, rax
0x180005747  jz      short loc_18000575F
0x180005749  mov     r8d, 400h
0x18000574f  mov     rdx, [rsp+78h+arg_60]
0x180005757  mov     rcx, rbx
0x18000575a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000575f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005766  test    rax, rax
0x180005769  jz      short loc_180005773
0x18000576b  mov     rcx, rbx
0x18000576e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005773  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000577a  test    rax, rax
0x18000577d  jz      short loc_18000578D
0x18000577f  test    byte ptr [rbx+4], 2
0x180005783  jnz     short loc_18000578D
0x180005785  mov     rcx, rbx
0x180005788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000578d  cmp     [rbx+8], edi
0x180005790  jl      short loc_1800057AC
0x180005792  cmp     r15d, 3
0x180005796  jnz     loc_18000587B
0x18000579c  mov     ecx, 8000FFFFh; this
0x1800057a1  mov     [rbx+8], ecx
0x1800057a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800057a9  mov     [rbx+0Ch], eax
0x1800057ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800057b3  jnz     short loc_1800057D4
0x1800057b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800057bc  test    rax, rax
0x1800057bf  jz      short loc_1800057CA
0x1800057c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c6  test    al, al
0x1800057c8  jmp     short loc_1800057D2
0x1800057ca  call    cs:__imp_IsDebuggerPresent
0x1800057d0  test    eax, eax
0x1800057d2  jz      short loc_1800057DA
0x1800057d4  test    byte ptr [rbx+4], 2
0x1800057d8  jz      short loc_1800057FE
0x1800057da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800057e1  test    rax, rax
0x1800057e4  jz      short loc_180005842
0x1800057e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800057ed  jnz     short loc_180005842
0x1800057ef  xor     r8d, r8d
0x1800057f2  xor     edx, edx
0x1800057f4  mov     rcx, rbx
0x1800057f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057fc  jmp     short loc_180005842
0x1800057fe  mov     ebp, 800h
0x180005803  mov     rax, cs:g_pfnResultLoggingCallback
0x18000580a  test    rax, rax
0x18000580d  jz      short loc_180005826
0x18000580f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005816  jnz     short loc_180005826
0x180005818  mov     r8d, ebp
0x18000581b  mov     rdx, rsi
0x18000581e  mov     rcx, rbx
0x180005821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005826  cmp     [rsi], di
0x180005829  jnz     short loc_180005839
0x18000582b  mov     r8, rbx; unsigned __int64
0x18000582e  mov     rdx, rbp; unsigned __int16 *
0x180005831  mov     rcx, rsi; this
0x180005834  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005839  mov     rcx, rsi; lpOutputString
0x18000583c  call    cs:__imp_OutputDebugStringW
0x180005842  test    byte ptr [rbx+4], 4
0x180005846  jnz     short loc_180005851
0x180005848  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000584f  jz      short loc_180005863
0x180005851  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005858  test    rax, rax
0x18000585b  jz      short loc_180005863
0x18000585d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005862  nop
0x180005863  mov     rbx, [rsp+78h+arg_10]
0x18000586b  add     rsp, 40h
0x18000586f  pop     r15
0x180005871  pop     r14
0x180005873  pop     r13
0x180005875  pop     r12
0x180005877  pop     rdi
0x180005878  pop     rsi
0x180005879  pop     rbp
0x18000587a  retn
0x18000587b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
