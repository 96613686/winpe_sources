# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140005b48`
- end: `0x140005dcd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140005804`

## callees

- `0x1400030d3`
- `0x140005b48`
- `0x140006f1c`
- `0x140007830`
- `0x140008030`
- `0x1400090f4`
- `0x1400091d0`
- `0x14006a120`
- `0x14006a1e0`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005d47`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005d47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c0d`

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
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  bool v14; // zf
  int v15; // r15d
  int v16; // ecx
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // rdx
  __int64 v20; // rcx
  const struct wil::FailureInfo *v21; // r9
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh]
  int v24; // [rsp+28h] [rbp-D8h]
  int v25; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v26; // [rsp+30h] [rbp-D0h]
  _WORD *v27; // [rsp+38h] [rbp-C8h]
  DWORD v28; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+60h] [rbp-A0h]
  int v33; // [rsp+64h] [rbp-9Ch]
  __int64 v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  __int128 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  char v42[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v22, 0, 0x98u);
  OutputString[0] = 0;
  v42[0] = 0;
  v11 = a7[1];
  v24 = *a7;
  v25 = v11;
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v24, (int)a7);
  v14 = *(_DWORD *)(v13 + 8) == 1;
  v15 = v12;
  v22 = 1;
  v16 = 0;
  if ( v14 )
    v16 = 8;
  v23 = v16;
  v26 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v27 = a8, !*a8) )
    v27 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v31 = a3;
  v28 = CurrentThreadId;
  v32 = a2;
  v38 = 0;
  v36 = 0;
  v33 = v15;
  v29 = 0;
  v30 = 0;
  v40 = a6;
  v41 = a1;
  v34 = 0;
  v37 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v22);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v22, v42, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v22);
  if ( wil::details::g_pfnOriginateCallback && (v23 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v22);
  if ( v24 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::details::IsDebuggerPresent(v18) || (v23 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v22, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v22, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v22, v21);
    OutputDebugStringW(OutputString);
  }
  if ( ((v23 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v20);
  if ( (v23 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v22, v19);
}

```

## disassembly

```asm
0x140005b48  push    rbp
0x140005b4a  push    rbx
0x140005b4b  push    rsi
0x140005b4c  push    rdi
0x140005b4d  push    r12
0x140005b4f  push    r14
0x140005b51  push    r15
0x140005b53  lea     rbp, [rsp-13D0h]
0x140005b5b  mov     eax, 14D0h
0x140005b60  call    _alloca_probe
0x140005b65  sub     rsp, rax
0x140005b68  mov     rax, cs:__security_cookie
0x140005b6f  xor     rax, rsp
0x140005b72  mov     [rbp+1400h+var_40], rax
0x140005b79  mov     r14, [rbp+1400h+arg_28]
0x140005b80  mov     rsi, r8
0x140005b83  mov     edi, edx
0x140005b85  mov     rbx, rcx
0x140005b88  xor     edx, edx; Val
0x140005b8a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140005b8f  mov     r8d, 98h; Size
0x140005b95  call    memset_0
0x140005b9a  mov     rdx, [rbp+1400h+arg_30]; int
0x140005ba1  xor     r12d, r12d
0x140005ba4  mov     [rbp+1400h+OutputString], r12w
0x140005bac  mov     [rbp+1400h+var_1440], r12b
0x140005bb0  mov     ecx, [rdx]; this
0x140005bb2  mov     eax, [rdx+4]
0x140005bb5  mov     [rsp+1500h+var_14D8], ecx
0x140005bb9  mov     [rsp+1500h+var_14D4], eax
0x140005bbd  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005bc2  cmp     dword ptr [rdx+8], 1
0x140005bc6  mov     r15d, eax
0x140005bc9  lea     eax, [r12+8]
0x140005bce  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140005bd6  mov     ecx, r12d
0x140005bd9  cmovz   ecx, eax
0x140005bdc  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140005be0  lea     ecx, [rax-7]
0x140005be3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005beb  inc     ecx
0x140005bed  mov     [rsp+1500h+var_14D0], ecx
0x140005bf1  mov     rcx, [rbp+1400h+arg_38]
0x140005bf8  test    rcx, rcx
0x140005bfb  jz      short loc_140005C08
0x140005bfd  mov     [rsp+1500h+var_14C8], rcx
0x140005c02  cmp     [rcx], r12w
0x140005c06  jnz     short loc_140005C0D
0x140005c08  mov     [rsp+1500h+var_14C8], r12
0x140005c0d  call    cs:__imp_GetCurrentThreadId
0x140005c13  xorps   xmm0, xmm0
0x140005c16  mov     [rsp+1500h+var_14A8], rsi
0x140005c1b  mov     [rsp+1500h+var_14C0], eax
0x140005c1f  xorps   xmm1, xmm1
0x140005c22  xor     eax, eax
0x140005c24  mov     [rsp+1500h+var_14A0], edi
0x140005c28  mov     [rbp+1400h+var_1468], rax
0x140005c2c  mov     [rbp+1400h+var_1480], rax
0x140005c30  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005c37  mov     [rsp+1500h+var_149C], r15d
0x140005c3c  mov     [rsp+1500h+var_14B8], r12
0x140005c41  mov     [rsp+1500h+var_14B0], r12
0x140005c46  mov     [rbp+1400h+var_1458], r14
0x140005c4a  mov     [rbp+1400h+var_1450], rbx
0x140005c4e  mov     [rsp+1500h+var_1498], r12
0x140005c53  movups  [rbp+1400h+var_1478], xmm0
0x140005c57  movups  [rsp+1500h+var_1490], xmm1
0x140005c5c  test    rax, rax
0x140005c5f  jz      short loc_140005C6C
0x140005c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c66  mov     [rbp+1400h+var_1460], rax
0x140005c6a  jmp     short loc_140005C70
0x140005c6c  mov     [rbp+1400h+var_1460], r12
0x140005c70  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005c77  test    rax, rax
0x140005c7a  jz      short loc_140005C86
0x140005c7c  lea     rcx, [rsp+1500h+var_14E0]
0x140005c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c86  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005c8d  test    rax, rax
0x140005c90  jz      short loc_140005CA6
0x140005c92  mov     r8d, 400h
0x140005c98  lea     rdx, [rbp+1400h+var_1440]
0x140005c9c  lea     rcx, [rsp+1500h+var_14E0]
0x140005ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ca6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005cad  test    rax, rax
0x140005cb0  jz      short loc_140005CBC
0x140005cb2  lea     rcx, [rsp+1500h+var_14E0]
0x140005cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cbc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005cc3  test    rax, rax
0x140005cc6  jz      short loc_140005CD9
0x140005cc8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140005ccd  jnz     short loc_140005CD9
0x140005ccf  lea     rcx, [rsp+1500h+var_14E0]
0x140005cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cd9  cmp     [rsp+1500h+var_14D8], r12d
0x140005cde  jge     loc_140005DBC
0x140005ce4  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x140005ce9  test    al, al
0x140005ceb  jz      short loc_140005D4F
0x140005ced  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140005cf2  jnz     short loc_140005D4F
0x140005cf4  mov     rax, cs:g_pfnResultLoggingCallback
0x140005cfb  mov     ebx, 800h
0x140005d00  test    rax, rax
0x140005d03  jz      short loc_140005D22
0x140005d05  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140005d0c  jnz     short loc_140005D22
0x140005d0e  mov     r8d, ebx
0x140005d11  lea     rdx, [rbp+1400h+OutputString]
0x140005d18  lea     rcx, [rsp+1500h+var_14E0]
0x140005d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d22  cmp     [rbp+1400h+OutputString], r12w
0x140005d2a  jnz     short loc_140005D40
0x140005d2c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140005d31  mov     rdx, rbx; unsigned __int16 *
0x140005d34  lea     rcx, [rbp+1400h+OutputString]; this
0x140005d3b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005d40  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140005d47  call    cs:__imp_OutputDebugStringW
0x140005d4d  jmp     short loc_140005D73
0x140005d4f  mov     rax, cs:g_pfnResultLoggingCallback
0x140005d56  test    rax, rax
0x140005d59  jz      short loc_140005D73
0x140005d5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140005d62  jnz     short loc_140005D73
0x140005d64  xor     r8d, r8d
0x140005d67  lea     rcx, [rsp+1500h+var_14E0]
0x140005d6c  xor     edx, edx
0x140005d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d73  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140005d78  jnz     short loc_140005D83
0x140005d7a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140005d81  jz      short loc_140005D94
0x140005d83  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005d8a  test    rax, rax
0x140005d8d  jz      short loc_140005D94
0x140005d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d94  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140005d99  jnz     short loc_140005DC2
0x140005d9b  mov     rcx, [rbp+1400h+var_40]
0x140005da2  xor     rcx, rsp; StackCookie
0x140005da5  call    __security_check_cookie
0x140005daa  add     rsp, 14D0h
0x140005db1  pop     r15
0x140005db3  pop     r14
0x140005db5  pop     r12
0x140005db7  pop     rdi
0x140005db8  pop     rsi
0x140005db9  pop     rbx
0x140005dba  pop     rbp
0x140005dbb  retn
0x140005dbc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140005dc2  lea     rcx, [rsp+1500h+var_14E0]; this
0x140005dc7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
