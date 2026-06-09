# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18005879c`
- end: `0x180058a30`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18005852c`

## callees

- `0x18005879c`
- `0x180059264`
- `0x180059edc`
- `0x18005a5f8`
- `0x18005a808`
- `0x18009429a`
- `0x1800942d0`
- `0x180094360`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180058846`
- `KERNEL32!GetCurrentThreadId` at `0x180058846`
- `KERNEL32!OutputDebugStringW` at `0x1800589cb`
- `KERNEL32!OutputDebugStringW` at `0x1800589cb`
- `KERNEL32!IsDebuggerPresent` at `0x180058941`
- `KERNEL32!IsDebuggerPresent` at `0x180058941`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x18005879c  mov     [rsp-8+arg_10], rbx
0x1800587a1  push    rbp
0x1800587a2  push    rsi
0x1800587a3  push    rdi
0x1800587a4  push    r14
0x1800587a6  push    r15
0x1800587a8  lea     rbp, [rsp-13D0h]
0x1800587b0  mov     eax, 14D0h
0x1800587b5  call    _alloca_probe
0x1800587ba  sub     rsp, rax
0x1800587bd  mov     rax, cs:__security_cookie
0x1800587c4  xor     rax, rsp
0x1800587c7  mov     [rbp+13F0h+var_30], rax
0x1800587ce  mov     rdi, [rbp+13F0h+arg_28]
0x1800587d5  mov     esi, edx
0x1800587d7  mov     r14, rcx
0x1800587da  xor     edx, edx; Val
0x1800587dc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800587e1  mov     r8d, 98h; Size
0x1800587e7  call    memset_0
0x1800587ec  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800587f3  xor     r15d, r15d
0x1800587f6  mov     [rbp+13F0h+OutputString], r15w
0x1800587fe  mov     [rbp+13F0h+var_1430], r15b
0x180058802  mov     ecx, [rdx]; this
0x180058804  mov     eax, [rdx+4]
0x180058807  mov     [rsp+14F0h+var_14C8], ecx
0x18005880b  mov     [rsp+14F0h+var_14C4], eax
0x18005880f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180058814  cmp     dword ptr [rdx+8], 1
0x180058818  mov     ebx, eax
0x18005881a  lea     eax, [r15+8]
0x18005881e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180058826  mov     ecx, r15d
0x180058829  cmovz   ecx, eax
0x18005882c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180058830  lea     ecx, [rax-7]
0x180058833  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005883b  inc     ecx
0x18005883d  mov     [rsp+14F0h+var_14B8], r15
0x180058842  mov     [rsp+14F0h+var_14C0], ecx
0x180058846  call    cs:__imp_GetCurrentThreadId
0x18005884c  xorps   xmm0, xmm0
0x18005884f  mov     [rsp+14F0h+var_1490], esi
0x180058853  mov     [rsp+14F0h+var_14B0], eax
0x180058857  xorps   xmm1, xmm1
0x18005885a  lea     rax, aWil; "wil"
0x180058861  mov     [rsp+14F0h+var_148C], ebx
0x180058865  mov     [rsp+14F0h+var_1498], rax
0x18005886a  xor     eax, eax
0x18005886c  mov     [rbp+13F0h+var_1458], rax
0x180058870  mov     [rbp+13F0h+var_1470], rax
0x180058874  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005887b  mov     [rsp+14F0h+var_14A8], r15
0x180058880  mov     [rsp+14F0h+var_14A0], r15
0x180058885  mov     [rbp+13F0h+var_1448], rdi
0x180058889  mov     [rbp+13F0h+var_1440], r14
0x18005888d  mov     [rsp+14F0h+var_1488], r15
0x180058892  movups  [rbp+13F0h+var_1468], xmm0
0x180058896  movups  [rsp+14F0h+var_1480], xmm1
0x18005889b  test    rax, rax
0x18005889e  jz      short loc_1800588AB
0x1800588a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588a5  mov     [rbp+13F0h+var_1450], rax
0x1800588a9  jmp     short loc_1800588AF
0x1800588ab  mov     [rbp+13F0h+var_1450], r15
0x1800588af  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800588b6  test    rax, rax
0x1800588b9  jz      short loc_1800588C5
0x1800588bb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800588c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588c5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800588cc  test    rax, rax
0x1800588cf  jz      short loc_1800588E5
0x1800588d1  mov     r8d, 400h
0x1800588d7  lea     rdx, [rbp+13F0h+var_1430]
0x1800588db  lea     rcx, [rsp+14F0h+var_14D0]
0x1800588e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588e5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800588ec  test    rax, rax
0x1800588ef  jz      short loc_1800588FB
0x1800588f1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800588f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588fb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180058902  test    rax, rax
0x180058905  jz      short loc_180058918
0x180058907  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18005890c  jnz     short loc_180058918
0x18005890e  lea     rcx, [rsp+14F0h+var_14D0]
0x180058913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058918  cmp     [rsp+14F0h+var_14C8], r15d
0x18005891d  jge     loc_180058A1F
0x180058923  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18005892a  jnz     short loc_18005894B
0x18005892c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180058933  test    rax, rax
0x180058936  jz      short loc_180058941
0x180058938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005893d  test    al, al
0x18005893f  jmp     short loc_180058949
0x180058941  call    cs:__imp_IsDebuggerPresent
0x180058947  test    eax, eax
0x180058949  jz      short loc_180058952
0x18005894b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180058950  jz      short loc_180058978
0x180058952  mov     rax, cs:g_pfnResultLoggingCallback
0x180058959  test    rax, rax
0x18005895c  jz      short loc_1800589D1
0x18005895e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180058965  jnz     short loc_1800589D1
0x180058967  xor     r8d, r8d
0x18005896a  lea     rcx, [rsp+14F0h+var_14D0]
0x18005896f  xor     edx, edx
0x180058971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058976  jmp     short loc_1800589D1
0x180058978  mov     rax, cs:g_pfnResultLoggingCallback
0x18005897f  mov     ebx, 800h
0x180058984  test    rax, rax
0x180058987  jz      short loc_1800589A6
0x180058989  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180058990  jnz     short loc_1800589A6
0x180058992  mov     r8d, ebx
0x180058995  lea     rdx, [rbp+13F0h+OutputString]
0x18005899c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800589a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589a6  cmp     [rbp+13F0h+OutputString], r15w
0x1800589ae  jnz     short loc_1800589C4
0x1800589b0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800589b5  mov     rdx, rbx; unsigned __int16 *
0x1800589b8  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800589bf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800589c4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800589cb  call    cs:__imp_OutputDebugStringW
0x1800589d1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800589d6  jnz     short loc_1800589E1
0x1800589d8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800589df  jz      short loc_1800589F2
0x1800589e1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800589e8  test    rax, rax
0x1800589eb  jz      short loc_1800589F2
0x1800589ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589f2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800589f7  jnz     short loc_180058A25
0x1800589f9  mov     rcx, [rbp+13F0h+var_30]
0x180058a00  xor     rcx, rsp; StackCookie
0x180058a03  call    __security_check_cookie
0x180058a08  mov     rbx, [rsp+14F0h+arg_10]
0x180058a10  add     rsp, 14D0h
0x180058a17  pop     r15
0x180058a19  pop     r14
0x180058a1b  pop     rdi
0x180058a1c  pop     rsi
0x180058a1d  pop     rbp
0x180058a1e  retn
0x180058a1f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180058a25  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180058a2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
