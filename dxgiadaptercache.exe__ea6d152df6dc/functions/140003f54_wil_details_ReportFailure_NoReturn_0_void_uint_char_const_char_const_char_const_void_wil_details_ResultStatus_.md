# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003f54`
- end: `0x140004207`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `691`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003750`

## callees

- `0x140002d4c`
- `0x140003f54`
- `0x140009350`
- `0x14000b2c8`
- `0x14000ddfc`
- `0x14000fa00`
- `0x1400100dc`
- `0x1400113b0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003ffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003ffd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000419b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000419b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400040ff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400040ff`

## string_xrefs

- `0x140004007`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  char v17; // bl
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 0;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = "onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp";
  v29 = a2;
  v30 = v10;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && !v9 && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17 = 1, (v20 & 2) != 0) )
  {
    v17 = 0;
  }
  if ( v9 || v17 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v15);
    if ( v17 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x140003f54  mov     [rsp-8+arg_10], rbx
0x140003f59  mov     [rsp-8+arg_18], rsi
0x140003f5e  push    rbp
0x140003f5f  push    rdi
0x140003f60  push    r12
0x140003f62  push    r14
0x140003f64  push    r15
0x140003f66  lea     rbp, [rsp-13C0h]
0x140003f6e  mov     eax, 14C0h
0x140003f73  call    _alloca_probe
0x140003f78  sub     rsp, rax
0x140003f7b  mov     esi, edx
0x140003f7d  mov     r14, rcx
0x140003f80  mov     rdi, [rbp+13E0h+arg_28]
0x140003f87  xor     r12d, r12d
0x140003f8a  cmp     cs:g_pfnThrowPlatformException, r12
0x140003f91  setnz   r15b
0x140003f95  xor     edx, edx; Val
0x140003f97  mov     r8d, 98h; Size
0x140003f9d  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x140003fa2  call    memset_0
0x140003fa7  nop
0x140003fa8  mov     [rbp+13E0h+OutputString], r12w
0x140003fb0  mov     [rbp+13E0h+var_1420], r12b
0x140003fb4  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x140003fbb  mov     ecx, [rdx]; this
0x140003fbd  mov     [rsp+14E0h+var_14B8], ecx
0x140003fc1  mov     eax, [rdx+4]
0x140003fc4  mov     [rsp+14E0h+var_14B4], eax
0x140003fc8  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140003fcd  mov     ebx, eax
0x140003fcf  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x140003fd4  mov     ecx, r12d
0x140003fd7  lea     eax, [r12+8]
0x140003fdc  cmp     dword ptr [rdx+8], 1
0x140003fe0  cmovz   ecx, eax
0x140003fe3  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140003fe7  lea     ecx, [rax-7]
0x140003fea  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003ff2  inc     ecx
0x140003ff4  mov     [rsp+14E0h+var_14B0], ecx
0x140003ff8  mov     [rsp+14E0h+var_14A8], r12
0x140003ffd  call    cs:__imp_GetCurrentThreadId
0x140004003  mov     [rsp+14E0h+var_14A0], eax
0x140004007  lea     rax, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000400e  mov     [rsp+14E0h+var_1488], rax
0x140004013  mov     [rsp+14E0h+var_1480], esi
0x140004017  mov     [rsp+14E0h+var_147C], ebx
0x14000401b  mov     [rsp+14E0h+var_1498], r12
0x140004020  mov     [rsp+14E0h+var_1490], r12
0x140004025  mov     [rbp+13E0h+var_1438], rdi
0x140004029  mov     [rbp+13E0h+var_1430], r14
0x14000402d  mov     [rsp+14E0h+var_1478], r12
0x140004032  xorps   xmm0, xmm0
0x140004035  xor     eax, eax
0x140004037  movups  [rbp+13E0h+var_1458], xmm0
0x14000403b  mov     [rbp+13E0h+var_1448], rax
0x14000403f  xorps   xmm1, xmm1
0x140004042  movups  [rsp+14E0h+var_1470], xmm1
0x140004047  mov     [rbp+13E0h+var_1460], rax
0x14000404b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004052  test    rax, rax
0x140004055  jz      short loc_140004062
0x140004057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000405c  mov     [rbp+13E0h+var_1440], rax
0x140004060  jmp     short loc_140004066
0x140004062  mov     [rbp+13E0h+var_1440], r12
0x140004066  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000406d  test    rax, rax
0x140004070  jz      short loc_14000407C
0x140004072  lea     rcx, [rsp+14E0h+var_14C0]
0x140004077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000407c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004083  test    rax, rax
0x140004086  jz      short loc_14000409C
0x140004088  mov     r8d, 400h
0x14000408e  lea     rdx, [rbp+13E0h+var_1420]
0x140004092  lea     rcx, [rsp+14E0h+var_14C0]
0x140004097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000409c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400040a3  test    rax, rax
0x1400040a6  jz      short loc_1400040B2
0x1400040a8  lea     rcx, [rsp+14E0h+var_14C0]
0x1400040ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040b2  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400040b9  test    rax, rax
0x1400040bc  jz      short loc_1400040D4
0x1400040be  test    r15b, r15b
0x1400040c1  jnz     short loc_1400040D4
0x1400040c3  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400040c8  jnz     short loc_1400040D4
0x1400040ca  lea     rcx, [rsp+14E0h+var_14C0]
0x1400040cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040d4  cmp     [rsp+14E0h+var_14B8], r12d
0x1400040d9  jl      short loc_1400040E1
0x1400040db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400040e1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400040e8  jnz     short loc_140004109
0x1400040ea  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400040f1  test    rax, rax
0x1400040f4  jz      short loc_1400040FF
0x1400040f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040fb  test    al, al
0x1400040fd  jmp     short loc_140004107
0x1400040ff  call    cs:__imp_IsDebuggerPresent
0x140004105  test    eax, eax
0x140004107  jz      short loc_140004112
0x140004109  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000410e  mov     bl, 1
0x140004110  jz      short loc_140004115
0x140004112  mov     bl, r12b
0x140004115  test    r15b, r15b
0x140004118  jnz     short loc_140004144
0x14000411a  test    bl, bl
0x14000411c  jnz     short loc_140004144
0x14000411e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004125  test    rax, rax
0x140004128  jz      short loc_1400041A1
0x14000412a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004131  jnz     short loc_1400041A1
0x140004133  xor     r8d, r8d
0x140004136  xor     edx, edx
0x140004138  lea     rcx, [rsp+14E0h+var_14C0]
0x14000413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004142  jmp     short loc_1400041A1
0x140004144  mov     edi, 800h
0x140004149  mov     rax, cs:g_pfnResultLoggingCallback
0x140004150  test    rax, rax
0x140004153  jz      short loc_140004172
0x140004155  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000415c  jnz     short loc_140004172
0x14000415e  mov     r8d, edi
0x140004161  lea     rdx, [rbp+13E0h+OutputString]
0x140004168  lea     rcx, [rsp+14E0h+var_14C0]
0x14000416d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004172  cmp     [rbp+13E0h+OutputString], r12w
0x14000417a  jnz     short loc_140004190
0x14000417c  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140004181  mov     rdx, rdi; unsigned __int16 *
0x140004184  lea     rcx, [rbp+13E0h+OutputString]; this
0x14000418b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004190  test    bl, bl
0x140004192  jz      short loc_1400041A1
0x140004194  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x14000419b  call    cs:__imp_OutputDebugStringW
0x1400041a1  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1400041a6  jnz     short loc_1400041B1
0x1400041a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400041af  jz      short loc_1400041C3
0x1400041b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400041b8  test    rax, rax
0x1400041bb  jz      short loc_1400041C3
0x1400041bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041c2  nop
0x1400041c3  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x1400041c8  jz      short loc_1400041D5
0x1400041ca  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1400041cf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400041d5  test    r15b, r15b
0x1400041d8  jz      short loc_1400041F2
0x1400041da  lea     rdx, [rbp+13E0h+OutputString]
0x1400041e1  lea     rcx, [rsp+14E0h+var_14C0]
0x1400041e6  mov     rax, cs:g_pfnThrowPlatformException
0x1400041ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041f2  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1400041f7  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1400041fc  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140004201  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
