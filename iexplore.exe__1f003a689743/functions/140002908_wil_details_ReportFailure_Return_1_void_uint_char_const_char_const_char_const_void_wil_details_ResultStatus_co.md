# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002908`
- end: `0x140002b9c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400025d0`

## callees

- `0x140001fc3`
- `0x140002908`
- `0x140003654`
- `0x140004850`
- `0x140005148`
- `0x1400052fc`
- `0x1400059b0`
- `0x140005a40`
- `0x140006010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x140002b37`
- `KERNEL32!OutputDebugStringW` at `0x140002b37`
- `KERNEL32!IsDebuggerPresent` at `0x140002aad`
- `KERNEL32!IsDebuggerPresent` at `0x140002aad`
- `KERNEL32!GetCurrentThreadId` at `0x1400029b2`
- `KERNEL32!GetCurrentThreadId` at `0x1400029b2`

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
0x140002908  mov     [rsp-8+arg_10], rbx
0x14000290d  push    rbp
0x14000290e  push    rsi
0x14000290f  push    rdi
0x140002910  push    r14
0x140002912  push    r15
0x140002914  lea     rbp, [rsp-13D0h]
0x14000291c  mov     eax, 14D0h
0x140002921  call    _alloca_probe
0x140002926  sub     rsp, rax
0x140002929  mov     rax, cs:__security_cookie
0x140002930  xor     rax, rsp
0x140002933  mov     [rbp+13F0h+var_30], rax
0x14000293a  mov     rdi, [rbp+13F0h+arg_28]
0x140002941  mov     esi, edx
0x140002943  mov     r14, rcx
0x140002946  xor     edx, edx; Val
0x140002948  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000294d  mov     r8d, 98h; Size
0x140002953  call    memset_0
0x140002958  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000295f  xor     r15d, r15d
0x140002962  mov     [rbp+13F0h+OutputString], r15w
0x14000296a  mov     [rbp+13F0h+var_1430], r15b
0x14000296e  mov     ecx, [rdx]; this
0x140002970  mov     eax, [rdx+4]
0x140002973  mov     [rsp+14F0h+var_14C8], ecx
0x140002977  mov     [rsp+14F0h+var_14C4], eax
0x14000297b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002980  cmp     dword ptr [rdx+8], 1
0x140002984  mov     ebx, eax
0x140002986  lea     eax, [r15+8]
0x14000298a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002992  mov     ecx, r15d
0x140002995  cmovz   ecx, eax
0x140002998  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000299c  lea     ecx, [rax-7]
0x14000299f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400029a7  inc     ecx
0x1400029a9  mov     [rsp+14F0h+var_14B8], r15
0x1400029ae  mov     [rsp+14F0h+var_14C0], ecx
0x1400029b2  call    cs:__imp_GetCurrentThreadId
0x1400029b8  xorps   xmm0, xmm0
0x1400029bb  mov     [rsp+14F0h+var_1490], esi
0x1400029bf  mov     [rsp+14F0h+var_14B0], eax
0x1400029c3  xorps   xmm1, xmm1
0x1400029c6  lea     rax, aWil; "wil"
0x1400029cd  mov     [rsp+14F0h+var_148C], ebx
0x1400029d1  mov     [rsp+14F0h+var_1498], rax
0x1400029d6  xor     eax, eax
0x1400029d8  mov     [rbp+13F0h+var_1458], rax
0x1400029dc  mov     [rbp+13F0h+var_1470], rax
0x1400029e0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400029e7  mov     [rsp+14F0h+var_14A8], r15
0x1400029ec  mov     [rsp+14F0h+var_14A0], r15
0x1400029f1  mov     [rbp+13F0h+var_1448], rdi
0x1400029f5  mov     [rbp+13F0h+var_1440], r14
0x1400029f9  mov     [rsp+14F0h+var_1488], r15
0x1400029fe  movups  [rbp+13F0h+var_1468], xmm0
0x140002a02  movups  [rsp+14F0h+var_1480], xmm1
0x140002a07  test    rax, rax
0x140002a0a  jz      short loc_140002A17
0x140002a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a11  mov     [rbp+13F0h+var_1450], rax
0x140002a15  jmp     short loc_140002A1B
0x140002a17  mov     [rbp+13F0h+var_1450], r15
0x140002a1b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002a22  test    rax, rax
0x140002a25  jz      short loc_140002A31
0x140002a27  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a31  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002a38  test    rax, rax
0x140002a3b  jz      short loc_140002A51
0x140002a3d  mov     r8d, 400h
0x140002a43  lea     rdx, [rbp+13F0h+var_1430]
0x140002a47  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a51  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a58  test    rax, rax
0x140002a5b  jz      short loc_140002A67
0x140002a5d  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a67  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a6e  test    rax, rax
0x140002a71  jz      short loc_140002A84
0x140002a73  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002a78  jnz     short loc_140002A84
0x140002a7a  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a84  cmp     [rsp+14F0h+var_14C8], r15d
0x140002a89  jge     loc_140002B8B
0x140002a8f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002a96  jnz     short loc_140002AB7
0x140002a98  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002a9f  test    rax, rax
0x140002aa2  jz      short loc_140002AAD
0x140002aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002aa9  test    al, al
0x140002aab  jmp     short loc_140002AB5
0x140002aad  call    cs:__imp_IsDebuggerPresent
0x140002ab3  test    eax, eax
0x140002ab5  jz      short loc_140002ABE
0x140002ab7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002abc  jz      short loc_140002AE4
0x140002abe  mov     rax, cs:g_pfnResultLoggingCallback
0x140002ac5  test    rax, rax
0x140002ac8  jz      short loc_140002B3D
0x140002aca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002ad1  jnz     short loc_140002B3D
0x140002ad3  xor     r8d, r8d
0x140002ad6  lea     rcx, [rsp+14F0h+var_14D0]
0x140002adb  xor     edx, edx
0x140002add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ae2  jmp     short loc_140002B3D
0x140002ae4  mov     rax, cs:g_pfnResultLoggingCallback
0x140002aeb  mov     ebx, 800h
0x140002af0  test    rax, rax
0x140002af3  jz      short loc_140002B12
0x140002af5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002afc  jnz     short loc_140002B12
0x140002afe  mov     r8d, ebx
0x140002b01  lea     rdx, [rbp+13F0h+OutputString]
0x140002b08  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b12  cmp     [rbp+13F0h+OutputString], r15w
0x140002b1a  jnz     short loc_140002B30
0x140002b1c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002b21  mov     rdx, rbx; unsigned __int16 *
0x140002b24  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002b2b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002b30  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002b37  call    cs:__imp_OutputDebugStringW
0x140002b3d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002b42  jnz     short loc_140002B4D
0x140002b44  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140002b4b  jz      short loc_140002B5E
0x140002b4d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002b54  test    rax, rax
0x140002b57  jz      short loc_140002B5E
0x140002b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b5e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002b63  jnz     short loc_140002B91
0x140002b65  mov     rcx, [rbp+13F0h+var_30]
0x140002b6c  xor     rcx, rsp; StackCookie
0x140002b6f  call    __security_check_cookie
0x140002b74  mov     rbx, [rsp+14F0h+arg_10]
0x140002b7c  add     rsp, 14D0h
0x140002b83  pop     r15
0x140002b85  pop     r14
0x140002b87  pop     rdi
0x140002b88  pop     rsi
0x140002b89  pop     rbp
0x140002b8a  retn
0x140002b8b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002b91  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002b96  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
