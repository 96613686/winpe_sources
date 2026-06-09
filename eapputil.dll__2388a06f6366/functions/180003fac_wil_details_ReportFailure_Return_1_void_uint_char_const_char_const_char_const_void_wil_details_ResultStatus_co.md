# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003fac`
- end: `0x180004252`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003a3c`

## callees

- `0x1800021d0`
- `0x180002b78`
- `0x180003fac`
- `0x180005584`
- `0x180006610`
- `0x180007950`
- `0x180007a2c`
- `0x180030510`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004072`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004072`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004167`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004167`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800041f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800041f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180003fac  push    rbp
0x180003fae  push    rbx
0x180003faf  push    rsi
0x180003fb0  push    rdi
0x180003fb1  push    r12
0x180003fb3  push    r14
0x180003fb5  push    r15
0x180003fb7  lea     rbp, [rsp-13D0h]
0x180003fbf  mov     eax, 14D0h
0x180003fc4  call    _alloca_probe
0x180003fc9  sub     rsp, rax
0x180003fcc  mov     rax, cs:__security_cookie
0x180003fd3  xor     rax, rsp
0x180003fd6  mov     [rbp+1400h+var_40], rax
0x180003fdd  mov     rsi, r8
0x180003fe0  mov     edi, edx
0x180003fe2  mov     rbx, rcx
0x180003fe5  mov     r14, [rbp+1400h+arg_28]
0x180003fec  xor     edx, edx; Val
0x180003fee  mov     r8d, 98h; Size
0x180003ff4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003ff9  call    memset_0
0x180003ffe  nop
0x180003fff  xor     r12d, r12d
0x180004002  mov     [rbp+1400h+OutputString], r12w
0x18000400a  mov     [rbp+1400h+var_1440], r12b
0x18000400e  mov     rdx, [rbp+1400h+arg_30]; int
0x180004015  mov     ecx, [rdx]; this
0x180004017  mov     [rsp+1500h+var_14D8], ecx
0x18000401b  mov     eax, [rdx+4]
0x18000401e  mov     [rsp+1500h+var_14D4], eax
0x180004022  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004027  mov     r15d, eax
0x18000402a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004032  mov     ecx, r12d
0x180004035  lea     eax, [r12+8]
0x18000403a  cmp     dword ptr [rdx+8], 1
0x18000403e  cmovz   ecx, eax
0x180004041  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004045  lea     ecx, [rax-7]
0x180004048  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004050  inc     ecx
0x180004052  mov     [rsp+1500h+var_14D0], ecx
0x180004056  mov     rcx, [rbp+1400h+arg_38]
0x18000405d  test    rcx, rcx
0x180004060  jz      short loc_18000406D
0x180004062  cmp     [rcx], r12w
0x180004066  mov     [rsp+1500h+var_14C8], rcx
0x18000406b  jnz     short loc_180004072
0x18000406d  mov     [rsp+1500h+var_14C8], r12
0x180004072  call    cs:__imp_GetCurrentThreadId
0x180004078  mov     [rsp+1500h+var_14C0], eax
0x18000407c  mov     [rsp+1500h+var_14A8], rsi
0x180004081  mov     [rsp+1500h+var_14A0], edi
0x180004085  mov     [rsp+1500h+var_149C], r15d
0x18000408a  mov     [rsp+1500h+var_14B8], r12
0x18000408f  mov     [rsp+1500h+var_14B0], r12
0x180004094  mov     [rbp+1400h+var_1458], r14
0x180004098  mov     [rbp+1400h+var_1450], rbx
0x18000409c  mov     [rsp+1500h+var_1498], r12
0x1800040a1  xorps   xmm0, xmm0
0x1800040a4  xor     eax, eax
0x1800040a6  movups  [rbp+1400h+var_1478], xmm0
0x1800040aa  mov     [rbp+1400h+var_1468], rax
0x1800040ae  xorps   xmm1, xmm1
0x1800040b1  movups  [rsp+1500h+var_1490], xmm1
0x1800040b6  mov     [rbp+1400h+var_1480], rax
0x1800040ba  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800040c1  test    rax, rax
0x1800040c4  jz      short loc_1800040D1
0x1800040c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040cb  mov     [rbp+1400h+var_1460], rax
0x1800040cf  jmp     short loc_1800040D5
0x1800040d1  mov     [rbp+1400h+var_1460], r12
0x1800040d5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800040dc  test    rax, rax
0x1800040df  jz      short loc_1800040EB
0x1800040e1  lea     rcx, [rsp+1500h+var_14E0]
0x1800040e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040eb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800040f2  test    rax, rax
0x1800040f5  jz      short loc_18000410B
0x1800040f7  mov     r8d, 400h
0x1800040fd  lea     rdx, [rbp+1400h+var_1440]
0x180004101  lea     rcx, [rsp+1500h+var_14E0]
0x180004106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000410b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004112  test    rax, rax
0x180004115  jz      short loc_180004121
0x180004117  lea     rcx, [rsp+1500h+var_14E0]
0x18000411c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004121  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004128  test    rax, rax
0x18000412b  jz      short loc_18000413E
0x18000412d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004132  jnz     short loc_18000413E
0x180004134  lea     rcx, [rsp+1500h+var_14E0]
0x180004139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413e  cmp     [rsp+1500h+var_14D8], r12d
0x180004143  jge     loc_18000424C
0x180004149  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004150  jnz     short loc_180004171
0x180004152  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004159  test    rax, rax
0x18000415c  jz      short loc_180004167
0x18000415e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004163  test    al, al
0x180004165  jmp     short loc_18000416F
0x180004167  call    cs:__imp_IsDebuggerPresent
0x18000416d  test    eax, eax
0x18000416f  jz      short loc_180004178
0x180004171  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004176  jz      short loc_18000419E
0x180004178  mov     rax, cs:g_pfnResultLoggingCallback
0x18000417f  test    rax, rax
0x180004182  jz      short loc_1800041F7
0x180004184  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000418b  jnz     short loc_1800041F7
0x18000418d  xor     r8d, r8d
0x180004190  xor     edx, edx
0x180004192  lea     rcx, [rsp+1500h+var_14E0]
0x180004197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000419c  jmp     short loc_1800041F7
0x18000419e  mov     ebx, 800h
0x1800041a3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800041aa  test    rax, rax
0x1800041ad  jz      short loc_1800041CC
0x1800041af  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800041b6  jnz     short loc_1800041CC
0x1800041b8  mov     r8d, ebx
0x1800041bb  lea     rdx, [rbp+1400h+OutputString]
0x1800041c2  lea     rcx, [rsp+1500h+var_14E0]
0x1800041c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041cc  cmp     [rbp+1400h+OutputString], r12w
0x1800041d4  jnz     short loc_1800041EA
0x1800041d6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800041db  mov     rdx, rbx; unsigned __int16 *
0x1800041de  lea     rcx, [rbp+1400h+OutputString]; this
0x1800041e5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800041ea  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800041f1  call    cs:__imp_OutputDebugStringW
0x1800041f7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800041fc  jnz     short loc_180004207
0x1800041fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004205  jz      short loc_180004219
0x180004207  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000420e  test    rax, rax
0x180004211  jz      short loc_180004219
0x180004213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004218  nop
0x180004219  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000421e  jnz     short loc_180004241
0x180004220  mov     rcx, [rbp+1400h+var_40]
0x180004227  xor     rcx, rsp; StackCookie
0x18000422a  call    __security_check_cookie
0x18000422f  add     rsp, 14D0h
0x180004236  pop     r15
0x180004238  pop     r14
0x18000423a  pop     r12
0x18000423c  pop     rdi
0x18000423d  pop     rsi
0x18000423e  pop     rbx
0x18000423f  pop     rbp
0x180004240  retn
0x180004241  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004246  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000424c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
