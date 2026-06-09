# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800471d0`
- end: `0x180047464`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180038a78`

## callees

- `0x180039610`
- `0x180039fb4`
- `0x1800471d0`
- `0x180048028`
- `0x180049030`
- `0x180049ca8`
- `0x180049dd8`
- `0x180087590`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180047375`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180047375`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800473ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800473ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004727a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004727a`

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
0x1800471d0  mov     [rsp-8+arg_10], rbx
0x1800471d5  push    rbp
0x1800471d6  push    rsi
0x1800471d7  push    rdi
0x1800471d8  push    r14
0x1800471da  push    r15
0x1800471dc  lea     rbp, [rsp-13D0h]
0x1800471e4  mov     eax, 14D0h
0x1800471e9  call    _alloca_probe
0x1800471ee  sub     rsp, rax
0x1800471f1  mov     rax, cs:__security_cookie
0x1800471f8  xor     rax, rsp
0x1800471fb  mov     [rbp+13F0h+var_30], rax
0x180047202  mov     rdi, [rbp+13F0h+arg_28]
0x180047209  mov     esi, edx
0x18004720b  mov     r14, rcx
0x18004720e  xor     edx, edx; Val
0x180047210  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180047215  mov     r8d, 98h; Size
0x18004721b  call    memset_0
0x180047220  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180047227  xor     r15d, r15d
0x18004722a  mov     [rbp+13F0h+OutputString], r15w
0x180047232  mov     [rbp+13F0h+var_1430], r15b
0x180047236  mov     ecx, [rdx]; this
0x180047238  mov     eax, [rdx+4]
0x18004723b  mov     [rsp+14F0h+var_14C8], ecx
0x18004723f  mov     [rsp+14F0h+var_14C4], eax
0x180047243  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180047248  cmp     dword ptr [rdx+8], 1
0x18004724c  mov     ebx, eax
0x18004724e  lea     eax, [r15+8]
0x180047252  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18004725a  mov     ecx, r15d
0x18004725d  cmovz   ecx, eax
0x180047260  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180047264  lea     ecx, [rax-7]
0x180047267  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004726f  inc     ecx
0x180047271  mov     [rsp+14F0h+var_14B8], r15
0x180047276  mov     [rsp+14F0h+var_14C0], ecx
0x18004727a  call    cs:__imp_GetCurrentThreadId
0x180047280  xorps   xmm0, xmm0
0x180047283  mov     [rsp+14F0h+var_1490], esi
0x180047287  mov     [rsp+14F0h+var_14B0], eax
0x18004728b  xorps   xmm1, xmm1
0x18004728e  lea     rax, aWil; "wil"
0x180047295  mov     [rsp+14F0h+var_148C], ebx
0x180047299  mov     [rsp+14F0h+var_1498], rax
0x18004729e  xor     eax, eax
0x1800472a0  mov     [rbp+13F0h+var_1458], rax
0x1800472a4  mov     [rbp+13F0h+var_1470], rax
0x1800472a8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800472af  mov     [rsp+14F0h+var_14A8], r15
0x1800472b4  mov     [rsp+14F0h+var_14A0], r15
0x1800472b9  mov     [rbp+13F0h+var_1448], rdi
0x1800472bd  mov     [rbp+13F0h+var_1440], r14
0x1800472c1  mov     [rsp+14F0h+var_1488], r15
0x1800472c6  movups  [rbp+13F0h+var_1468], xmm0
0x1800472ca  movups  [rsp+14F0h+var_1480], xmm1
0x1800472cf  test    rax, rax
0x1800472d2  jz      short loc_1800472DF
0x1800472d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472d9  mov     [rbp+13F0h+var_1450], rax
0x1800472dd  jmp     short loc_1800472E3
0x1800472df  mov     [rbp+13F0h+var_1450], r15
0x1800472e3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800472ea  test    rax, rax
0x1800472ed  jz      short loc_1800472F9
0x1800472ef  lea     rcx, [rsp+14F0h+var_14D0]
0x1800472f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800472f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180047300  test    rax, rax
0x180047303  jz      short loc_180047319
0x180047305  mov     r8d, 400h
0x18004730b  lea     rdx, [rbp+13F0h+var_1430]
0x18004730f  lea     rcx, [rsp+14F0h+var_14D0]
0x180047314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047319  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180047320  test    rax, rax
0x180047323  jz      short loc_18004732F
0x180047325  lea     rcx, [rsp+14F0h+var_14D0]
0x18004732a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004732f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180047336  test    rax, rax
0x180047339  jz      short loc_18004734C
0x18004733b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180047340  jnz     short loc_18004734C
0x180047342  lea     rcx, [rsp+14F0h+var_14D0]
0x180047347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004734c  cmp     [rsp+14F0h+var_14C8], r15d
0x180047351  jge     loc_180047453
0x180047357  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18004735e  jnz     short loc_18004737F
0x180047360  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180047367  test    rax, rax
0x18004736a  jz      short loc_180047375
0x18004736c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047371  test    al, al
0x180047373  jmp     short loc_18004737D
0x180047375  call    cs:__imp_IsDebuggerPresent
0x18004737b  test    eax, eax
0x18004737d  jz      short loc_180047386
0x18004737f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180047384  jz      short loc_1800473AC
0x180047386  mov     rax, cs:g_pfnResultLoggingCallback
0x18004738d  test    rax, rax
0x180047390  jz      short loc_180047405
0x180047392  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180047399  jnz     short loc_180047405
0x18004739b  xor     r8d, r8d
0x18004739e  lea     rcx, [rsp+14F0h+var_14D0]
0x1800473a3  xor     edx, edx
0x1800473a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473aa  jmp     short loc_180047405
0x1800473ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800473b3  mov     ebx, 800h
0x1800473b8  test    rax, rax
0x1800473bb  jz      short loc_1800473DA
0x1800473bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800473c4  jnz     short loc_1800473DA
0x1800473c6  mov     r8d, ebx
0x1800473c9  lea     rdx, [rbp+13F0h+OutputString]
0x1800473d0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800473d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800473da  cmp     [rbp+13F0h+OutputString], r15w
0x1800473e2  jnz     short loc_1800473F8
0x1800473e4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800473e9  mov     rdx, rbx; unsigned __int16 *
0x1800473ec  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800473f3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800473f8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800473ff  call    cs:__imp_OutputDebugStringW
0x180047405  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18004740a  jnz     short loc_180047415
0x18004740c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180047413  jz      short loc_180047426
0x180047415  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004741c  test    rax, rax
0x18004741f  jz      short loc_180047426
0x180047421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047426  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18004742b  jnz     short loc_180047459
0x18004742d  mov     rcx, [rbp+13F0h+var_30]
0x180047434  xor     rcx, rsp; StackCookie
0x180047437  call    __security_check_cookie
0x18004743c  mov     rbx, [rsp+14F0h+arg_10]
0x180047444  add     rsp, 14D0h
0x18004744b  pop     r15
0x18004744d  pop     r14
0x18004744f  pop     rdi
0x180047450  pop     rsi
0x180047451  pop     rbp
0x180047452  retn
0x180047453  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180047459  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18004745e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
