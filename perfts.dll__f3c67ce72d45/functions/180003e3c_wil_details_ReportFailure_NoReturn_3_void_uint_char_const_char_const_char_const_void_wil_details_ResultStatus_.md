# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003e3c`
- end: `0x1800040bc`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003c3c`

## callees

- `0x180003e3c`
- `0x180005d24`
- `0x1800062e8`
- `0x1800081f0`
- `0x180008dc0`
- `0x1800098f6`
- `0x1800099f0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180004089`
- `KERNEL32!OutputDebugStringW` at `0x180004089`
- `KERNEL32!IsDebuggerPresent` at `0x180003fff`
- `KERNEL32!IsDebuggerPresent` at `0x180003fff`
- `KERNEL32!GetCurrentThreadId` at `0x180003ef5`
- `KERNEL32!GetCurrentThreadId` at `0x180003ef5`

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
        int *a7,
        _WORD *a8)
{
  int v10; // edx
  int v11; // r15d
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
  _WORD *v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  const char *v26; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

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
  if ( !a8 || (v16 = *a8 == 0, v22 = a8, v16) )
    v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = "clientcore\\termsrv\\newsvc\\lagcounter\\lagcounter.cpp";
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
0x180003e3c  mov     [rsp-8+arg_10], rbx
0x180003e41  mov     [rsp-8+arg_18], rsi
0x180003e46  push    rbp
0x180003e47  push    rdi
0x180003e48  push    r12
0x180003e4a  push    r14
0x180003e4c  push    r15
0x180003e4e  lea     rbp, [rsp-13C0h]
0x180003e56  mov     eax, 14C0h
0x180003e5b  call    _alloca_probe
0x180003e60  sub     rsp, rax
0x180003e63  mov     esi, edx
0x180003e65  mov     rdi, rcx
0x180003e68  mov     r14, [rbp+13E0h+arg_28]
0x180003e6f  xor     edx, edx; Val
0x180003e71  mov     r8d, 98h; Size
0x180003e77  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180003e7c  call    memset_0
0x180003e81  nop
0x180003e82  xor     r12d, r12d
0x180003e85  mov     [rbp+13E0h+OutputString], r12w
0x180003e8d  mov     [rbp+13E0h+var_1420], r12b
0x180003e91  mov     rbx, [rbp+13E0h+arg_30]
0x180003e98  mov     ecx, [rbx]; this
0x180003e9a  mov     [rsp+14E0h+var_14B8], ecx
0x180003e9e  mov     eax, [rbx+4]
0x180003ea1  mov     [rsp+14E0h+var_14B4], eax
0x180003ea5  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003eaa  mov     r15d, eax
0x180003ead  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180003eb5  mov     ecx, r12d
0x180003eb8  lea     eax, [r12+8]
0x180003ebd  cmp     dword ptr [rbx+8], 1
0x180003ec1  cmovz   ecx, eax
0x180003ec4  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180003ec8  lea     ecx, [rax-7]
0x180003ecb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003ed3  inc     ecx
0x180003ed5  mov     [rsp+14E0h+var_14B0], ecx
0x180003ed9  mov     rcx, [rbp+13E0h+arg_38]
0x180003ee0  test    rcx, rcx
0x180003ee3  jz      short loc_180003EF0
0x180003ee5  cmp     [rcx], r12w
0x180003ee9  mov     [rsp+14E0h+var_14A8], rcx
0x180003eee  jnz     short loc_180003EF5
0x180003ef0  mov     [rsp+14E0h+var_14A8], r12
0x180003ef5  call    cs:__imp_GetCurrentThreadId
0x180003efb  mov     [rsp+14E0h+var_14A0], eax
0x180003eff  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\newsvc\\lagcounter"...
0x180003f06  mov     [rsp+14E0h+var_1488], rax
0x180003f0b  mov     [rsp+14E0h+var_1480], esi
0x180003f0f  mov     [rsp+14E0h+var_147C], r15d
0x180003f14  mov     [rsp+14E0h+var_1498], r12
0x180003f19  mov     [rsp+14E0h+var_1490], r12
0x180003f1e  mov     [rbp+13E0h+var_1438], r14
0x180003f22  mov     [rbp+13E0h+var_1430], rdi
0x180003f26  mov     [rsp+14E0h+var_1478], r12
0x180003f2b  xorps   xmm0, xmm0
0x180003f2e  xor     eax, eax
0x180003f30  movups  [rbp+13E0h+var_1458], xmm0
0x180003f34  mov     [rbp+13E0h+var_1448], rax
0x180003f38  xorps   xmm1, xmm1
0x180003f3b  movups  [rsp+14E0h+var_1470], xmm1
0x180003f40  mov     [rbp+13E0h+var_1460], rax
0x180003f44  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003f4b  test    rax, rax
0x180003f4e  jz      short loc_180003F5B
0x180003f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f55  mov     [rbp+13E0h+var_1440], rax
0x180003f59  jmp     short loc_180003F5F
0x180003f5b  mov     [rbp+13E0h+var_1440], r12
0x180003f5f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003f66  test    rax, rax
0x180003f69  jz      short loc_180003F75
0x180003f6b  lea     rcx, [rsp+14E0h+var_14C0]
0x180003f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f75  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003f7c  test    rax, rax
0x180003f7f  jz      short loc_180003F95
0x180003f81  mov     r8d, 400h
0x180003f87  lea     rdx, [rbp+13E0h+var_1420]
0x180003f8b  lea     rcx, [rsp+14E0h+var_14C0]
0x180003f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f95  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003f9c  test    rax, rax
0x180003f9f  jz      short loc_180003FAB
0x180003fa1  lea     rcx, [rsp+14E0h+var_14C0]
0x180003fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003fb2  test    rax, rax
0x180003fb5  jz      short loc_180003FC8
0x180003fb7  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003fbc  jnz     short loc_180003FC8
0x180003fbe  lea     rcx, [rsp+14E0h+var_14C0]
0x180003fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc8  cmp     [rsp+14E0h+var_14B8], r12d
0x180003fcd  jl      short loc_180003FE1
0x180003fcf  mov     ecx, 8000FFFFh; this
0x180003fd4  mov     [rsp+14E0h+var_14B8], ecx
0x180003fd8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003fdd  mov     [rsp+14E0h+var_14B4], eax
0x180003fe1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003fe8  jnz     short loc_180004009
0x180003fea  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003ff1  test    rax, rax
0x180003ff4  jz      short loc_180003FFF
0x180003ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ffb  test    al, al
0x180003ffd  jmp     short loc_180004007
0x180003fff  call    cs:__imp_IsDebuggerPresent
0x180004005  test    eax, eax
0x180004007  jz      short loc_180004010
0x180004009  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000400e  jz      short loc_180004036
0x180004010  mov     rax, cs:g_pfnResultLoggingCallback
0x180004017  test    rax, rax
0x18000401a  jz      short loc_18000408F
0x18000401c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004023  jnz     short loc_18000408F
0x180004025  xor     r8d, r8d
0x180004028  xor     edx, edx
0x18000402a  lea     rcx, [rsp+14E0h+var_14C0]
0x18000402f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004034  jmp     short loc_18000408F
0x180004036  mov     ebx, 800h
0x18000403b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004042  test    rax, rax
0x180004045  jz      short loc_180004064
0x180004047  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000404e  jnz     short loc_180004064
0x180004050  mov     r8d, ebx
0x180004053  lea     rdx, [rbp+13E0h+OutputString]
0x18000405a  lea     rcx, [rsp+14E0h+var_14C0]
0x18000405f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004064  cmp     [rbp+13E0h+OutputString], r12w
0x18000406c  jnz     short loc_180004082
0x18000406e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180004073  mov     rdx, rbx; unsigned __int16 *
0x180004076  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000407d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004082  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180004089  call    cs:__imp_OutputDebugStringW
0x18000408f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180004094  jnz     short loc_18000409F
0x180004096  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000409d  jz      short loc_1800040B1
0x18000409f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800040a6  test    rax, rax
0x1800040a9  jz      short loc_1800040B1
0x1800040ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b0  nop
0x1800040b1  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800040b6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
