# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180264690`
- end: `0x180264924`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18023cd74`

## callees

- `0x18025b100`
- `0x18025bb98`
- `0x180264690`
- `0x1802659e4`
- `0x18026701c`
- `0x1802681b8`
- `0x1802683c4`
- `0x1802f5310`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18026473a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18026473a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180264835`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180264835`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1802648bf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1802648bf`

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
0x180264690  mov     [rsp-8+arg_10], rbx
0x180264695  push    rbp
0x180264696  push    rsi
0x180264697  push    rdi
0x180264698  push    r14
0x18026469a  push    r15
0x18026469c  lea     rbp, [rsp-13D0h]
0x1802646a4  mov     eax, 14D0h
0x1802646a9  call    _alloca_probe
0x1802646ae  sub     rsp, rax
0x1802646b1  mov     rax, cs:__security_cookie
0x1802646b8  xor     rax, rsp
0x1802646bb  mov     [rbp+13F0h+var_30], rax
0x1802646c2  mov     rdi, [rbp+13F0h+arg_28]
0x1802646c9  mov     esi, edx
0x1802646cb  mov     r14, rcx
0x1802646ce  xor     edx, edx; Val
0x1802646d0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1802646d5  mov     r8d, 98h; Size
0x1802646db  call    memset_0
0x1802646e0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1802646e7  xor     r15d, r15d
0x1802646ea  mov     [rbp+13F0h+OutputString], r15w
0x1802646f2  mov     [rbp+13F0h+var_1430], r15b
0x1802646f6  mov     ecx, [rdx]; this
0x1802646f8  mov     eax, [rdx+4]
0x1802646fb  mov     [rsp+14F0h+var_14C8], ecx
0x1802646ff  mov     [rsp+14F0h+var_14C4], eax
0x180264703  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180264708  cmp     dword ptr [rdx+8], 1
0x18026470c  mov     ebx, eax
0x18026470e  lea     eax, [r15+8]
0x180264712  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18026471a  mov     ecx, r15d
0x18026471d  cmovz   ecx, eax
0x180264720  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180264724  lea     ecx, [rax-7]
0x180264727  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18026472f  inc     ecx
0x180264731  mov     [rsp+14F0h+var_14B8], r15
0x180264736  mov     [rsp+14F0h+var_14C0], ecx
0x18026473a  call    cs:__imp_GetCurrentThreadId
0x180264740  xorps   xmm0, xmm0
0x180264743  mov     [rsp+14F0h+var_1490], esi
0x180264747  mov     [rsp+14F0h+var_14B0], eax
0x18026474b  xorps   xmm1, xmm1
0x18026474e  lea     rax, aWil; "wil"
0x180264755  mov     [rsp+14F0h+var_148C], ebx
0x180264759  mov     [rsp+14F0h+var_1498], rax
0x18026475e  xor     eax, eax
0x180264760  mov     [rbp+13F0h+var_1458], rax
0x180264764  mov     [rbp+13F0h+var_1470], rax
0x180264768  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18026476f  mov     [rsp+14F0h+var_14A8], r15
0x180264774  mov     [rsp+14F0h+var_14A0], r15
0x180264779  mov     [rbp+13F0h+var_1448], rdi
0x18026477d  mov     [rbp+13F0h+var_1440], r14
0x180264781  mov     [rsp+14F0h+var_1488], r15
0x180264786  movups  [rbp+13F0h+var_1468], xmm0
0x18026478a  movups  [rsp+14F0h+var_1480], xmm1
0x18026478f  test    rax, rax
0x180264792  jz      short loc_18026479F
0x180264794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180264799  mov     [rbp+13F0h+var_1450], rax
0x18026479d  jmp     short loc_1802647A3
0x18026479f  mov     [rbp+13F0h+var_1450], r15
0x1802647a3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1802647aa  test    rax, rax
0x1802647ad  jz      short loc_1802647B9
0x1802647af  lea     rcx, [rsp+14F0h+var_14D0]
0x1802647b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802647b9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1802647c0  test    rax, rax
0x1802647c3  jz      short loc_1802647D9
0x1802647c5  mov     r8d, 400h
0x1802647cb  lea     rdx, [rbp+13F0h+var_1430]
0x1802647cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1802647d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802647d9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1802647e0  test    rax, rax
0x1802647e3  jz      short loc_1802647EF
0x1802647e5  lea     rcx, [rsp+14F0h+var_14D0]
0x1802647ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802647ef  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1802647f6  test    rax, rax
0x1802647f9  jz      short loc_18026480C
0x1802647fb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180264800  jnz     short loc_18026480C
0x180264802  lea     rcx, [rsp+14F0h+var_14D0]
0x180264807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026480c  cmp     [rsp+14F0h+var_14C8], r15d
0x180264811  jge     loc_180264913
0x180264817  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18026481e  jnz     short loc_18026483F
0x180264820  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180264827  test    rax, rax
0x18026482a  jz      short loc_180264835
0x18026482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180264831  test    al, al
0x180264833  jmp     short loc_18026483D
0x180264835  call    cs:__imp_IsDebuggerPresent
0x18026483b  test    eax, eax
0x18026483d  jz      short loc_180264846
0x18026483f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180264844  jz      short loc_18026486C
0x180264846  mov     rax, cs:g_pfnResultLoggingCallback
0x18026484d  test    rax, rax
0x180264850  jz      short loc_1802648C5
0x180264852  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180264859  jnz     short loc_1802648C5
0x18026485b  xor     r8d, r8d
0x18026485e  lea     rcx, [rsp+14F0h+var_14D0]
0x180264863  xor     edx, edx
0x180264865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026486a  jmp     short loc_1802648C5
0x18026486c  mov     rax, cs:g_pfnResultLoggingCallback
0x180264873  mov     ebx, 800h
0x180264878  test    rax, rax
0x18026487b  jz      short loc_18026489A
0x18026487d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180264884  jnz     short loc_18026489A
0x180264886  mov     r8d, ebx
0x180264889  lea     rdx, [rbp+13F0h+OutputString]
0x180264890  lea     rcx, [rsp+14F0h+var_14D0]
0x180264895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026489a  cmp     [rbp+13F0h+OutputString], r15w
0x1802648a2  jnz     short loc_1802648B8
0x1802648a4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1802648a9  mov     rdx, rbx; unsigned __int16 *
0x1802648ac  lea     rcx, [rbp+13F0h+OutputString]; this
0x1802648b3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1802648b8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1802648bf  call    cs:__imp_OutputDebugStringW
0x1802648c5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1802648ca  jnz     short loc_1802648D5
0x1802648cc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1802648d3  jz      short loc_1802648E6
0x1802648d5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1802648dc  test    rax, rax
0x1802648df  jz      short loc_1802648E6
0x1802648e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802648e6  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1802648eb  jnz     short loc_180264919
0x1802648ed  mov     rcx, [rbp+13F0h+var_30]
0x1802648f4  xor     rcx, rsp; StackCookie
0x1802648f7  call    __security_check_cookie
0x1802648fc  mov     rbx, [rsp+14F0h+arg_10]
0x180264904  add     rsp, 14D0h
0x18026490b  pop     r15
0x18026490d  pop     r14
0x18026490f  pop     rdi
0x180264910  pop     rsi
0x180264911  pop     rbp
0x180264912  retn
0x180264913  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180264919  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18026491e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
