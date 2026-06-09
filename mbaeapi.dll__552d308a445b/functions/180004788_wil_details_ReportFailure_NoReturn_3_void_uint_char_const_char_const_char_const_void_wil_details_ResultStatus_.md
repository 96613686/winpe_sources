# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004788`
- end: `0x180004a01`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800044f4`

## callees

- `0x180002efc`
- `0x180004788`
- `0x180006fe4`
- `0x18000778c`
- `0x180008410`
- `0x18000ab80`
- `0x1800588d0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004841`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004841`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800049ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800049ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004944`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004944`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180004788  mov     [rsp-8+arg_18], rbx
0x18000478d  push    rbp
0x18000478e  push    rsi
0x18000478f  push    rdi
0x180004790  push    r12
0x180004792  push    r13
0x180004794  push    r14
0x180004796  push    r15
0x180004798  lea     rbp, [rsp-13C0h]
0x1800047a0  mov     eax, 14C0h
0x1800047a5  call    _alloca_probe
0x1800047aa  sub     rsp, rax
0x1800047ad  mov     r14, r8
0x1800047b0  mov     esi, edx
0x1800047b2  mov     rdi, rcx
0x1800047b5  mov     r15, [rbp+13F0h+arg_28]
0x1800047bc  xor     edx, edx; Val
0x1800047be  mov     r8d, 98h; Size
0x1800047c4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800047c9  call    memset_0
0x1800047ce  nop
0x1800047cf  xor     r13d, r13d
0x1800047d2  mov     [rbp+13F0h+OutputString], r13w
0x1800047da  mov     [rbp+13F0h+var_1430], r13b
0x1800047de  mov     rbx, [rbp+13F0h+arg_30]
0x1800047e5  mov     ecx, [rbx]; this
0x1800047e7  mov     [rsp+14F0h+var_14C8], ecx
0x1800047eb  mov     eax, [rbx+4]
0x1800047ee  mov     [rsp+14F0h+var_14C4], eax
0x1800047f2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800047f7  mov     r12d, eax
0x1800047fa  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004802  mov     ecx, r13d
0x180004805  lea     eax, [r13+8]
0x180004809  cmp     dword ptr [rbx+8], 1
0x18000480d  cmovz   ecx, eax
0x180004810  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004814  lea     ecx, [rax-7]
0x180004817  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000481f  inc     ecx
0x180004821  mov     [rsp+14F0h+var_14C0], ecx
0x180004825  mov     rcx, [rbp+13F0h+arg_38]
0x18000482c  test    rcx, rcx
0x18000482f  jz      short loc_18000483C
0x180004831  cmp     [rcx], r13w
0x180004835  mov     [rsp+14F0h+var_14B8], rcx
0x18000483a  jnz     short loc_180004841
0x18000483c  mov     [rsp+14F0h+var_14B8], r13
0x180004841  call    cs:__imp_GetCurrentThreadId
0x180004847  mov     [rsp+14F0h+var_14B0], eax
0x18000484b  mov     [rsp+14F0h+var_1498], r14
0x180004850  mov     [rsp+14F0h+var_1490], esi
0x180004854  mov     [rsp+14F0h+var_148C], r12d
0x180004859  mov     [rsp+14F0h+var_14A8], r13
0x18000485e  mov     [rsp+14F0h+var_14A0], r13
0x180004863  mov     [rbp+13F0h+var_1448], r15
0x180004867  mov     [rbp+13F0h+var_1440], rdi
0x18000486b  mov     [rsp+14F0h+var_1488], r13
0x180004870  xorps   xmm0, xmm0
0x180004873  xor     eax, eax
0x180004875  movups  [rbp+13F0h+var_1468], xmm0
0x180004879  mov     [rbp+13F0h+var_1458], rax
0x18000487d  xorps   xmm1, xmm1
0x180004880  movups  [rsp+14F0h+var_1480], xmm1
0x180004885  mov     [rbp+13F0h+var_1470], rax
0x180004889  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004890  test    rax, rax
0x180004893  jz      short loc_1800048A0
0x180004895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489a  mov     [rbp+13F0h+var_1450], rax
0x18000489e  jmp     short loc_1800048A4
0x1800048a0  mov     [rbp+13F0h+var_1450], r13
0x1800048a4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800048ab  test    rax, rax
0x1800048ae  jz      short loc_1800048BA
0x1800048b0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ba  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800048c1  test    rax, rax
0x1800048c4  jz      short loc_1800048DA
0x1800048c6  mov     r8d, 400h
0x1800048cc  lea     rdx, [rbp+13F0h+var_1430]
0x1800048d0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048da  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048e1  test    rax, rax
0x1800048e4  jz      short loc_1800048F0
0x1800048e6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800048eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048f0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048f7  test    rax, rax
0x1800048fa  jz      short loc_18000490D
0x1800048fc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004901  jnz     short loc_18000490D
0x180004903  lea     rcx, [rsp+14F0h+var_14D0]
0x180004908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000490d  cmp     [rsp+14F0h+var_14C8], r13d
0x180004912  jl      short loc_180004926
0x180004914  mov     ecx, 8000FFFFh; this
0x180004919  mov     [rsp+14F0h+var_14C8], ecx
0x18000491d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004922  mov     [rsp+14F0h+var_14C4], eax
0x180004926  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000492d  jnz     short loc_18000494E
0x18000492f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004936  test    rax, rax
0x180004939  jz      short loc_180004944
0x18000493b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004940  test    al, al
0x180004942  jmp     short loc_18000494C
0x180004944  call    cs:__imp_IsDebuggerPresent
0x18000494a  test    eax, eax
0x18000494c  jz      short loc_180004955
0x18000494e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004953  jz      short loc_18000497B
0x180004955  mov     rax, cs:g_pfnResultLoggingCallback
0x18000495c  test    rax, rax
0x18000495f  jz      short loc_1800049D4
0x180004961  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004968  jnz     short loc_1800049D4
0x18000496a  xor     r8d, r8d
0x18000496d  xor     edx, edx
0x18000496f  lea     rcx, [rsp+14F0h+var_14D0]
0x180004974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004979  jmp     short loc_1800049D4
0x18000497b  mov     ebx, 800h
0x180004980  mov     rax, cs:g_pfnResultLoggingCallback
0x180004987  test    rax, rax
0x18000498a  jz      short loc_1800049A9
0x18000498c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004993  jnz     short loc_1800049A9
0x180004995  mov     r8d, ebx
0x180004998  lea     rdx, [rbp+13F0h+OutputString]
0x18000499f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800049a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a9  cmp     [rbp+13F0h+OutputString], r13w
0x1800049b1  jnz     short loc_1800049C7
0x1800049b3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800049b8  mov     rdx, rbx; unsigned __int16 *
0x1800049bb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800049c2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800049c7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800049ce  call    cs:__imp_OutputDebugStringW
0x1800049d4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800049d9  jnz     short loc_1800049E4
0x1800049db  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800049e2  jz      short loc_1800049F6
0x1800049e4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800049eb  test    rax, rax
0x1800049ee  jz      short loc_1800049F6
0x1800049f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f5  nop
0x1800049f6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800049fb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
