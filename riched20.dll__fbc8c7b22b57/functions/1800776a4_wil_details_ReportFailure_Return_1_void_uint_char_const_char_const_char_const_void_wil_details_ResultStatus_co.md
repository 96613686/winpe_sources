# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800776a4`
- end: `0x18007794b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18007719c`

## callees

- `0x1800776a4`
- `0x180079424`
- `0x18007b70c`
- `0x18007d05c`
- `0x18007d230`
- `0x180093bca`
- `0x180093c00`
- `0x180093c90`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007774e`
- `KERNEL32!GetCurrentThreadId` at `0x18007774e`
- `KERNEL32!IsDebuggerPresent` at `0x18007784f`
- `KERNEL32!IsDebuggerPresent` at `0x18007784f`
- `KERNEL32!OutputDebugStringW` at `0x1800778df`
- `KERNEL32!OutputDebugStringW` at `0x1800778df`

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
0x1800776a4  mov     [rsp-8+arg_10], rbx
0x1800776a9  push    rbp
0x1800776aa  push    rsi
0x1800776ab  push    rdi
0x1800776ac  push    r14
0x1800776ae  push    r15
0x1800776b0  lea     rbp, [rsp-13D0h]
0x1800776b8  mov     eax, 14D0h
0x1800776bd  call    _alloca_probe
0x1800776c2  sub     rsp, rax
0x1800776c5  mov     rax, cs:__security_cookie
0x1800776cc  xor     rax, rsp
0x1800776cf  mov     [rbp+13F0h+var_30], rax
0x1800776d6  mov     rdi, [rbp+13F0h+arg_28]
0x1800776dd  mov     esi, edx
0x1800776df  mov     r14, rcx
0x1800776e2  xor     edx, edx; Val
0x1800776e4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800776e9  mov     r8d, 98h; Size
0x1800776ef  call    memset_0
0x1800776f4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800776fb  xor     r15d, r15d
0x1800776fe  mov     [rbp+13F0h+OutputString], r15w
0x180077706  mov     [rbp+13F0h+var_1430], r15b
0x18007770a  mov     ecx, [rdx]; this
0x18007770c  mov     eax, [rdx+4]
0x18007770f  mov     [rsp+14F0h+var_14C8], ecx
0x180077713  mov     [rsp+14F0h+var_14C4], eax
0x180077717  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18007771c  cmp     dword ptr [rdx+8], 1
0x180077720  mov     ebx, eax
0x180077722  lea     eax, [r15+8]
0x180077726  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18007772e  mov     ecx, r15d
0x180077731  cmovz   ecx, eax
0x180077734  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180077738  lea     ecx, [rax-7]
0x18007773b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180077743  inc     ecx
0x180077745  mov     [rsp+14F0h+var_14B8], r15
0x18007774a  mov     [rsp+14F0h+var_14C0], ecx
0x18007774e  call    cs:__imp_GetCurrentThreadId
0x180077755  nop     dword ptr [rax+rax+00h]
0x18007775a  xorps   xmm0, xmm0
0x18007775d  mov     [rsp+14F0h+var_1490], esi
0x180077761  mov     [rsp+14F0h+var_14B0], eax
0x180077765  xorps   xmm1, xmm1
0x180077768  lea     rax, aWil; "wil"
0x18007776f  mov     [rsp+14F0h+var_148C], ebx
0x180077773  mov     [rsp+14F0h+var_1498], rax
0x180077778  xor     eax, eax
0x18007777a  mov     [rbp+13F0h+var_1458], rax
0x18007777e  mov     [rbp+13F0h+var_1470], rax
0x180077782  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180077789  mov     [rsp+14F0h+var_14A8], r15
0x18007778e  mov     [rsp+14F0h+var_14A0], r15
0x180077793  mov     [rbp+13F0h+var_1448], rdi
0x180077797  mov     [rbp+13F0h+var_1440], r14
0x18007779b  mov     [rsp+14F0h+var_1488], r15
0x1800777a0  movups  [rbp+13F0h+var_1468], xmm0
0x1800777a4  movups  [rsp+14F0h+var_1480], xmm1
0x1800777a9  test    rax, rax
0x1800777ac  jz      short loc_1800777B9
0x1800777ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800777b3  mov     [rbp+13F0h+var_1450], rax
0x1800777b7  jmp     short loc_1800777BD
0x1800777b9  mov     [rbp+13F0h+var_1450], r15
0x1800777bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800777c4  test    rax, rax
0x1800777c7  jz      short loc_1800777D3
0x1800777c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800777ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800777d3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800777da  test    rax, rax
0x1800777dd  jz      short loc_1800777F3
0x1800777df  mov     r8d, 400h
0x1800777e5  lea     rdx, [rbp+13F0h+var_1430]
0x1800777e9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800777ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800777f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800777fa  test    rax, rax
0x1800777fd  jz      short loc_180077809
0x1800777ff  lea     rcx, [rsp+14F0h+var_14D0]
0x180077804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077809  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180077810  test    rax, rax
0x180077813  jz      short loc_180077826
0x180077815  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18007781a  jnz     short loc_180077826
0x18007781c  lea     rcx, [rsp+14F0h+var_14D0]
0x180077821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077826  cmp     [rsp+14F0h+var_14C8], r15d
0x18007782b  jge     loc_18007793A
0x180077831  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180077838  jnz     short loc_18007785F
0x18007783a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180077841  test    rax, rax
0x180077844  jz      short loc_18007784F
0x180077846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007784b  test    al, al
0x18007784d  jmp     short loc_18007785D
0x18007784f  call    cs:__imp_IsDebuggerPresent
0x180077856  nop     dword ptr [rax+rax+00h]
0x18007785b  test    eax, eax
0x18007785d  jz      short loc_180077866
0x18007785f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180077864  jz      short loc_18007788C
0x180077866  mov     rax, cs:g_pfnResultLoggingCallback
0x18007786d  test    rax, rax
0x180077870  jz      short loc_1800778EB
0x180077872  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180077879  jnz     short loc_1800778EB
0x18007787b  xor     r8d, r8d
0x18007787e  lea     rcx, [rsp+14F0h+var_14D0]
0x180077883  xor     edx, edx
0x180077885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007788a  jmp     short loc_1800778EB
0x18007788c  mov     rax, cs:g_pfnResultLoggingCallback
0x180077893  mov     ebx, 800h
0x180077898  test    rax, rax
0x18007789b  jz      short loc_1800778BA
0x18007789d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800778a4  jnz     short loc_1800778BA
0x1800778a6  mov     r8d, ebx
0x1800778a9  lea     rdx, [rbp+13F0h+OutputString]
0x1800778b0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800778b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778ba  cmp     [rbp+13F0h+OutputString], r15w
0x1800778c2  jnz     short loc_1800778D8
0x1800778c4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800778c9  mov     rdx, rbx; unsigned __int16 *
0x1800778cc  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800778d3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800778d8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800778df  call    cs:__imp_OutputDebugStringW
0x1800778e6  nop     dword ptr [rax+rax+00h]
0x1800778eb  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800778f0  jnz     short loc_1800778FB
0x1800778f2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800778f9  jz      short loc_18007790C
0x1800778fb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180077902  test    rax, rax
0x180077905  jz      short loc_18007790C
0x180077907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007790c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180077911  jnz     short loc_180077940
0x180077913  mov     rcx, [rbp+13F0h+var_30]
0x18007791a  xor     rcx, rsp; StackCookie
0x18007791d  call    __security_check_cookie
0x180077922  mov     rbx, [rsp+14F0h+arg_10]
0x18007792a  add     rsp, 14D0h
0x180077931  pop     r15
0x180077933  pop     r14
0x180077935  pop     rdi
0x180077936  pop     rsi
0x180077937  pop     rbp
0x180077938  retn
0x18007793a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180077940  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180077945  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
