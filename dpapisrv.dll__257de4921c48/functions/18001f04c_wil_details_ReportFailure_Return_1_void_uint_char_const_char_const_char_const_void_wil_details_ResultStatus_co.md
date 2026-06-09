# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001f04c`
- end: `0x18001f305`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001edb0`

## callees

- `0x18001d810`
- `0x18001e1b4`
- `0x18001f04c`
- `0x1800209f4`
- `0x180022444`
- `0x180023af0`
- `0x180023d00`
- `0x18003c5c0`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f112`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f112`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f29d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f29d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f20d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f20d`

## pseudocode

```c
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
0x18001f04c  push    rbp
0x18001f04e  push    rbx
0x18001f04f  push    rsi
0x18001f050  push    rdi
0x18001f051  push    r12
0x18001f053  push    r14
0x18001f055  push    r15
0x18001f057  lea     rbp, [rsp-13D0h]
0x18001f05f  mov     eax, 14D0h
0x18001f064  call    _alloca_probe
0x18001f069  sub     rsp, rax
0x18001f06c  mov     rax, cs:__security_cookie
0x18001f073  xor     rax, rsp
0x18001f076  mov     [rbp+1400h+var_40], rax
0x18001f07d  mov     rsi, r8
0x18001f080  mov     edi, edx
0x18001f082  mov     rbx, rcx
0x18001f085  mov     r14, [rbp+1400h+arg_28]
0x18001f08c  xor     edx, edx; Val
0x18001f08e  mov     r8d, 98h; Size
0x18001f094  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18001f099  call    memset_0
0x18001f09e  nop
0x18001f09f  xor     r12d, r12d
0x18001f0a2  mov     [rbp+1400h+OutputString], r12w
0x18001f0aa  mov     [rbp+1400h+var_1440], r12b
0x18001f0ae  mov     rdx, [rbp+1400h+arg_30]; int
0x18001f0b5  mov     ecx, [rdx]; this
0x18001f0b7  mov     [rsp+1500h+var_14D8], ecx
0x18001f0bb  mov     eax, [rdx+4]
0x18001f0be  mov     [rsp+1500h+var_14D4], eax
0x18001f0c2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001f0c7  mov     r15d, eax
0x18001f0ca  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18001f0d2  mov     ecx, r12d
0x18001f0d5  lea     eax, [r12+8]
0x18001f0da  cmp     dword ptr [rdx+8], 1
0x18001f0de  cmovz   ecx, eax
0x18001f0e1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18001f0e5  lea     ecx, [rax-7]
0x18001f0e8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001f0f0  inc     ecx
0x18001f0f2  mov     [rsp+1500h+var_14D0], ecx
0x18001f0f6  mov     rcx, [rbp+1400h+arg_38]
0x18001f0fd  test    rcx, rcx
0x18001f100  jz      short loc_18001F10D
0x18001f102  cmp     [rcx], r12w
0x18001f106  mov     [rsp+1500h+var_14C8], rcx
0x18001f10b  jnz     short loc_18001F112
0x18001f10d  mov     [rsp+1500h+var_14C8], r12
0x18001f112  call    cs:__imp_GetCurrentThreadId
0x18001f119  nop     dword ptr [rax+rax+00h]
0x18001f11e  mov     [rsp+1500h+var_14C0], eax
0x18001f122  mov     [rsp+1500h+var_14A8], rsi
0x18001f127  mov     [rsp+1500h+var_14A0], edi
0x18001f12b  mov     [rsp+1500h+var_149C], r15d
0x18001f130  mov     [rsp+1500h+var_14B8], r12
0x18001f135  mov     [rsp+1500h+var_14B0], r12
0x18001f13a  mov     [rbp+1400h+var_1458], r14
0x18001f13e  mov     [rbp+1400h+var_1450], rbx
0x18001f142  mov     [rsp+1500h+var_1498], r12
0x18001f147  xorps   xmm0, xmm0
0x18001f14a  xor     eax, eax
0x18001f14c  movups  [rbp+1400h+var_1478], xmm0
0x18001f150  mov     [rbp+1400h+var_1468], rax
0x18001f154  xorps   xmm1, xmm1
0x18001f157  movups  [rsp+1500h+var_1490], xmm1
0x18001f15c  mov     [rbp+1400h+var_1480], rax
0x18001f160  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001f167  test    rax, rax
0x18001f16a  jz      short loc_18001F177
0x18001f16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f171  mov     [rbp+1400h+var_1460], rax
0x18001f175  jmp     short loc_18001F17B
0x18001f177  mov     [rbp+1400h+var_1460], r12
0x18001f17b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001f182  test    rax, rax
0x18001f185  jz      short loc_18001F191
0x18001f187  lea     rcx, [rsp+1500h+var_14E0]
0x18001f18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f191  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001f198  test    rax, rax
0x18001f19b  jz      short loc_18001F1B1
0x18001f19d  mov     r8d, 400h
0x18001f1a3  lea     rdx, [rbp+1400h+var_1440]
0x18001f1a7  lea     rcx, [rsp+1500h+var_14E0]
0x18001f1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1b1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f1b8  test    rax, rax
0x18001f1bb  jz      short loc_18001F1C7
0x18001f1bd  lea     rcx, [rsp+1500h+var_14E0]
0x18001f1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1c7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f1ce  test    rax, rax
0x18001f1d1  jz      short loc_18001F1E4
0x18001f1d3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001f1d8  jnz     short loc_18001F1E4
0x18001f1da  lea     rcx, [rsp+1500h+var_14E0]
0x18001f1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1e4  cmp     [rsp+1500h+var_14D8], r12d
0x18001f1e9  jge     loc_18001F2FF
0x18001f1ef  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18001f1f6  jnz     short loc_18001F21D
0x18001f1f8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001f1ff  test    rax, rax
0x18001f202  jz      short loc_18001F20D
0x18001f204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f209  test    al, al
0x18001f20b  jmp     short loc_18001F21B
0x18001f20d  call    cs:__imp_IsDebuggerPresent
0x18001f214  nop     dword ptr [rax+rax+00h]
0x18001f219  test    eax, eax
0x18001f21b  jz      short loc_18001F224
0x18001f21d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001f222  jz      short loc_18001F24A
0x18001f224  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f22b  test    rax, rax
0x18001f22e  jz      short loc_18001F2A9
0x18001f230  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001f237  jnz     short loc_18001F2A9
0x18001f239  xor     r8d, r8d
0x18001f23c  xor     edx, edx
0x18001f23e  lea     rcx, [rsp+1500h+var_14E0]
0x18001f243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f248  jmp     short loc_18001F2A9
0x18001f24a  mov     ebx, 800h
0x18001f24f  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f256  test    rax, rax
0x18001f259  jz      short loc_18001F278
0x18001f25b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001f262  jnz     short loc_18001F278
0x18001f264  mov     r8d, ebx
0x18001f267  lea     rdx, [rbp+1400h+OutputString]
0x18001f26e  lea     rcx, [rsp+1500h+var_14E0]
0x18001f273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f278  cmp     [rbp+1400h+OutputString], r12w
0x18001f280  jnz     short loc_18001F296
0x18001f282  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18001f287  mov     rdx, rbx; unsigned __int16 *
0x18001f28a  lea     rcx, [rbp+1400h+OutputString]; this
0x18001f291  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001f296  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18001f29d  call    cs:__imp_OutputDebugStringW
0x18001f2a4  nop     dword ptr [rax+rax+00h]
0x18001f2a9  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18001f2ae  jnz     short loc_18001F2B9
0x18001f2b0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18001f2b7  jz      short loc_18001F2CB
0x18001f2b9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001f2c0  test    rax, rax
0x18001f2c3  jz      short loc_18001F2CB
0x18001f2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2ca  nop
0x18001f2cb  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18001f2d0  jnz     short loc_18001F2F4
0x18001f2d2  mov     rcx, [rbp+1400h+var_40]
0x18001f2d9  xor     rcx, rsp; StackCookie
0x18001f2dc  call    __security_check_cookie
0x18001f2e1  add     rsp, 14D0h
0x18001f2e8  pop     r15
0x18001f2ea  pop     r14
0x18001f2ec  pop     r12
0x18001f2ee  pop     rdi
0x18001f2ef  pop     rsi
0x18001f2f0  pop     rbx
0x18001f2f1  pop     rbp
0x18001f2f2  retn
0x18001f2f4  lea     rcx, [rsp+1500h+var_14E0]; this
0x18001f2f9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001f2ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
