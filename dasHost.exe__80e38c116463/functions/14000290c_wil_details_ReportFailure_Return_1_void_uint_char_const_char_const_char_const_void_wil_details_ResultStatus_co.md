# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000290c`
- end: `0x140002bb2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002398`

## callees

- `0x140001570`
- `0x1400020d0`
- `0x14000290c`
- `0x140004c14`
- `0x140005e28`
- `0x1400081e0`
- `0x1400083ac`
- `0x14001a7d0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400029d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400029d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002b51`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002b51`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002ac7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002ac7`

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
0x14000290c  push    rbp
0x14000290e  push    rbx
0x14000290f  push    rsi
0x140002910  push    rdi
0x140002911  push    r12
0x140002913  push    r14
0x140002915  push    r15
0x140002917  lea     rbp, [rsp-13D0h]
0x14000291f  mov     eax, 14D0h
0x140002924  call    _alloca_probe
0x140002929  sub     rsp, rax
0x14000292c  mov     rax, cs:__security_cookie
0x140002933  xor     rax, rsp
0x140002936  mov     [rbp+1400h+var_40], rax
0x14000293d  mov     rsi, r8
0x140002940  mov     edi, edx
0x140002942  mov     rbx, rcx
0x140002945  mov     r14, [rbp+1400h+arg_28]
0x14000294c  xor     edx, edx; Val
0x14000294e  mov     r8d, 98h; Size
0x140002954  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140002959  call    memset_0
0x14000295e  nop
0x14000295f  xor     r12d, r12d
0x140002962  mov     [rbp+1400h+OutputString], r12w
0x14000296a  mov     [rbp+1400h+var_1440], r12b
0x14000296e  mov     rdx, [rbp+1400h+arg_30]; int
0x140002975  mov     ecx, [rdx]; this
0x140002977  mov     [rsp+1500h+var_14D8], ecx
0x14000297b  mov     eax, [rdx+4]
0x14000297e  mov     [rsp+1500h+var_14D4], eax
0x140002982  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002987  mov     r15d, eax
0x14000298a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002992  mov     ecx, r12d
0x140002995  lea     eax, [r12+8]
0x14000299a  cmp     dword ptr [rdx+8], 1
0x14000299e  cmovz   ecx, eax
0x1400029a1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400029a5  lea     ecx, [rax-7]
0x1400029a8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400029b0  inc     ecx
0x1400029b2  mov     [rsp+1500h+var_14D0], ecx
0x1400029b6  mov     rcx, [rbp+1400h+arg_38]
0x1400029bd  test    rcx, rcx
0x1400029c0  jz      short loc_1400029CD
0x1400029c2  cmp     [rcx], r12w
0x1400029c6  mov     [rsp+1500h+var_14C8], rcx
0x1400029cb  jnz     short loc_1400029D2
0x1400029cd  mov     [rsp+1500h+var_14C8], r12
0x1400029d2  call    cs:__imp_GetCurrentThreadId
0x1400029d8  mov     [rsp+1500h+var_14C0], eax
0x1400029dc  mov     [rsp+1500h+var_14A8], rsi
0x1400029e1  mov     [rsp+1500h+var_14A0], edi
0x1400029e5  mov     [rsp+1500h+var_149C], r15d
0x1400029ea  mov     [rsp+1500h+var_14B8], r12
0x1400029ef  mov     [rsp+1500h+var_14B0], r12
0x1400029f4  mov     [rbp+1400h+var_1458], r14
0x1400029f8  mov     [rbp+1400h+var_1450], rbx
0x1400029fc  mov     [rsp+1500h+var_1498], r12
0x140002a01  xorps   xmm0, xmm0
0x140002a04  xor     eax, eax
0x140002a06  movups  [rbp+1400h+var_1478], xmm0
0x140002a0a  mov     [rbp+1400h+var_1468], rax
0x140002a0e  xorps   xmm1, xmm1
0x140002a11  movups  [rsp+1500h+var_1490], xmm1
0x140002a16  mov     [rbp+1400h+var_1480], rax
0x140002a1a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002a21  test    rax, rax
0x140002a24  jz      short loc_140002A31
0x140002a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a2b  mov     [rbp+1400h+var_1460], rax
0x140002a2f  jmp     short loc_140002A35
0x140002a31  mov     [rbp+1400h+var_1460], r12
0x140002a35  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002a3c  test    rax, rax
0x140002a3f  jz      short loc_140002A4B
0x140002a41  lea     rcx, [rsp+1500h+var_14E0]
0x140002a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a4b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002a52  test    rax, rax
0x140002a55  jz      short loc_140002A6B
0x140002a57  mov     r8d, 400h
0x140002a5d  lea     rdx, [rbp+1400h+var_1440]
0x140002a61  lea     rcx, [rsp+1500h+var_14E0]
0x140002a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a6b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a72  test    rax, rax
0x140002a75  jz      short loc_140002A81
0x140002a77  lea     rcx, [rsp+1500h+var_14E0]
0x140002a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a81  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a88  test    rax, rax
0x140002a8b  jz      short loc_140002A9E
0x140002a8d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002a92  jnz     short loc_140002A9E
0x140002a94  lea     rcx, [rsp+1500h+var_14E0]
0x140002a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a9e  cmp     [rsp+1500h+var_14D8], r12d
0x140002aa3  jge     loc_140002BAC
0x140002aa9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002ab0  jnz     short loc_140002AD1
0x140002ab2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002ab9  test    rax, rax
0x140002abc  jz      short loc_140002AC7
0x140002abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ac3  test    al, al
0x140002ac5  jmp     short loc_140002ACF
0x140002ac7  call    cs:__imp_IsDebuggerPresent
0x140002acd  test    eax, eax
0x140002acf  jz      short loc_140002AD8
0x140002ad1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002ad6  jz      short loc_140002AFE
0x140002ad8  mov     rax, cs:g_pfnResultLoggingCallback
0x140002adf  test    rax, rax
0x140002ae2  jz      short loc_140002B57
0x140002ae4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002aeb  jnz     short loc_140002B57
0x140002aed  xor     r8d, r8d
0x140002af0  xor     edx, edx
0x140002af2  lea     rcx, [rsp+1500h+var_14E0]
0x140002af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002afc  jmp     short loc_140002B57
0x140002afe  mov     ebx, 800h
0x140002b03  mov     rax, cs:g_pfnResultLoggingCallback
0x140002b0a  test    rax, rax
0x140002b0d  jz      short loc_140002B2C
0x140002b0f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002b16  jnz     short loc_140002B2C
0x140002b18  mov     r8d, ebx
0x140002b1b  lea     rdx, [rbp+1400h+OutputString]
0x140002b22  lea     rcx, [rsp+1500h+var_14E0]
0x140002b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b2c  cmp     [rbp+1400h+OutputString], r12w
0x140002b34  jnz     short loc_140002B4A
0x140002b36  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140002b3b  mov     rdx, rbx; unsigned __int16 *
0x140002b3e  lea     rcx, [rbp+1400h+OutputString]; this
0x140002b45  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002b4a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002b51  call    cs:__imp_OutputDebugStringW
0x140002b57  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140002b5c  jnz     short loc_140002B67
0x140002b5e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002b65  jz      short loc_140002B79
0x140002b67  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002b6e  test    rax, rax
0x140002b71  jz      short loc_140002B79
0x140002b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b78  nop
0x140002b79  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002b7e  jnz     short loc_140002BA1
0x140002b80  mov     rcx, [rbp+1400h+var_40]
0x140002b87  xor     rcx, rsp; StackCookie
0x140002b8a  call    __security_check_cookie
0x140002b8f  add     rsp, 14D0h
0x140002b96  pop     r15
0x140002b98  pop     r14
0x140002b9a  pop     r12
0x140002b9c  pop     rdi
0x140002b9d  pop     rsi
0x140002b9e  pop     rbx
0x140002b9f  pop     rbp
0x140002ba0  retn
0x140002ba1  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002ba6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002bac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
