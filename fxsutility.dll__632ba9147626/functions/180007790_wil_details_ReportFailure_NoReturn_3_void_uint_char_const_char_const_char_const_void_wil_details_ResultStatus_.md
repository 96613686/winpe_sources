# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007790`
- end: `0x1800079f2`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007534`

## callees

- `0x180007790`
- `0x1800099e4`
- `0x18000a180`
- `0x18000ad60`
- `0x18000cd20`
- `0x180015cbe`
- `0x180015db0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007832`
- `KERNEL32!GetCurrentThreadId` at `0x180007832`
- `KERNEL32!OutputDebugStringW` at `0x1800079bf`
- `KERNEL32!OutputDebugStringW` at `0x1800079bf`
- `KERNEL32!IsDebuggerPresent` at `0x180007935`
- `KERNEL32!IsDebuggerPresent` at `0x180007935`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180007790  mov     [rsp-8+arg_18], rbx
0x180007795  push    rbp
0x180007796  push    rsi
0x180007797  push    rdi
0x180007798  push    r12
0x18000779a  push    r13
0x18000779c  push    r14
0x18000779e  push    r15
0x1800077a0  lea     rbp, [rsp-13C0h]
0x1800077a8  mov     eax, 14C0h
0x1800077ad  call    _alloca_probe
0x1800077b2  sub     rsp, rax
0x1800077b5  mov     r15, r8
0x1800077b8  mov     r14d, edx
0x1800077bb  mov     r12, rcx
0x1800077be  mov     rsi, [rbp+13F0h+arg_28]
0x1800077c5  xor     edx, edx; Val
0x1800077c7  mov     r8d, 98h; Size
0x1800077cd  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800077d2  call    memset_0
0x1800077d7  nop
0x1800077d8  xor     r13d, r13d
0x1800077db  mov     [rbp+13F0h+OutputString], r13w
0x1800077e3  mov     [rbp+13F0h+var_1430], r13b
0x1800077e7  mov     rbx, [rbp+13F0h+arg_30]
0x1800077ee  mov     ecx, [rbx]; this
0x1800077f0  mov     [rsp+14F0h+var_14C8], ecx
0x1800077f4  mov     eax, [rbx+4]
0x1800077f7  mov     [rsp+14F0h+var_14C4], eax
0x1800077fb  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007800  mov     edi, eax
0x180007802  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000780a  mov     ecx, r13d
0x18000780d  lea     eax, [r13+8]
0x180007811  cmp     dword ptr [rbx+8], 1
0x180007815  cmovz   ecx, eax
0x180007818  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000781c  lea     ecx, [rax-7]
0x18000781f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007827  inc     ecx
0x180007829  mov     [rsp+14F0h+var_14C0], ecx
0x18000782d  mov     [rsp+14F0h+var_14B8], r13
0x180007832  call    cs:__imp_GetCurrentThreadId
0x180007838  mov     [rsp+14F0h+var_14B0], eax
0x18000783c  mov     [rsp+14F0h+var_1498], r15
0x180007841  mov     [rsp+14F0h+var_1490], r14d
0x180007846  mov     [rsp+14F0h+var_148C], edi
0x18000784a  mov     [rsp+14F0h+var_14A8], r13
0x18000784f  mov     [rsp+14F0h+var_14A0], r13
0x180007854  mov     [rbp+13F0h+var_1448], rsi
0x180007858  mov     [rbp+13F0h+var_1440], r12
0x18000785c  mov     [rsp+14F0h+var_1488], r13
0x180007861  xorps   xmm0, xmm0
0x180007864  xor     eax, eax
0x180007866  movups  [rbp+13F0h+var_1468], xmm0
0x18000786a  mov     [rbp+13F0h+var_1458], rax
0x18000786e  xorps   xmm1, xmm1
0x180007871  movups  [rsp+14F0h+var_1480], xmm1
0x180007876  mov     [rbp+13F0h+var_1470], rax
0x18000787a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007881  test    rax, rax
0x180007884  jz      short loc_180007891
0x180007886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000788b  mov     [rbp+13F0h+var_1450], rax
0x18000788f  jmp     short loc_180007895
0x180007891  mov     [rbp+13F0h+var_1450], r13
0x180007895  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000789c  test    rax, rax
0x18000789f  jz      short loc_1800078AB
0x1800078a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800078a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ab  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800078b2  test    rax, rax
0x1800078b5  jz      short loc_1800078CB
0x1800078b7  mov     r8d, 400h
0x1800078bd  lea     rdx, [rbp+13F0h+var_1430]
0x1800078c1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800078c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078cb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800078d2  test    rax, rax
0x1800078d5  jz      short loc_1800078E1
0x1800078d7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800078dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800078e8  test    rax, rax
0x1800078eb  jz      short loc_1800078FE
0x1800078ed  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800078f2  jnz     short loc_1800078FE
0x1800078f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800078f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078fe  cmp     [rsp+14F0h+var_14C8], r13d
0x180007903  jl      short loc_180007917
0x180007905  mov     ecx, 8000FFFFh; this
0x18000790a  mov     [rsp+14F0h+var_14C8], ecx
0x18000790e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007913  mov     [rsp+14F0h+var_14C4], eax
0x180007917  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000791e  jnz     short loc_18000793F
0x180007920  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007927  test    rax, rax
0x18000792a  jz      short loc_180007935
0x18000792c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007931  test    al, al
0x180007933  jmp     short loc_18000793D
0x180007935  call    cs:__imp_IsDebuggerPresent
0x18000793b  test    eax, eax
0x18000793d  jz      short loc_180007946
0x18000793f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007944  jz      short loc_18000796C
0x180007946  mov     rax, cs:g_pfnResultLoggingCallback
0x18000794d  test    rax, rax
0x180007950  jz      short loc_1800079C5
0x180007952  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007959  jnz     short loc_1800079C5
0x18000795b  xor     r8d, r8d
0x18000795e  xor     edx, edx
0x180007960  lea     rcx, [rsp+14F0h+var_14D0]
0x180007965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000796a  jmp     short loc_1800079C5
0x18000796c  mov     ebx, 800h
0x180007971  mov     rax, cs:g_pfnResultLoggingCallback
0x180007978  test    rax, rax
0x18000797b  jz      short loc_18000799A
0x18000797d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007984  jnz     short loc_18000799A
0x180007986  mov     r8d, ebx
0x180007989  lea     rdx, [rbp+13F0h+OutputString]
0x180007990  lea     rcx, [rsp+14F0h+var_14D0]
0x180007995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000799a  cmp     [rbp+13F0h+OutputString], r13w
0x1800079a2  jnz     short loc_1800079B8
0x1800079a4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800079a9  mov     rdx, rbx; unsigned __int16 *
0x1800079ac  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800079b3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800079b8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800079bf  call    cs:__imp_OutputDebugStringW
0x1800079c5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800079ca  jnz     short loc_1800079D5
0x1800079cc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800079d3  jz      short loc_1800079E7
0x1800079d5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800079dc  test    rax, rax
0x1800079df  jz      short loc_1800079E7
0x1800079e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e6  nop
0x1800079e7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800079ec  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
