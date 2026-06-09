# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003e58`
- end: `0x1400040fe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003640`

## callees

- `0x140002190`
- `0x140002c2c`
- `0x140003e58`
- `0x1400073e4`
- `0x140009708`
- `0x14000cad0`
- `0x14000cdec`
- `0x14000fe00`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003f1e`
- `KERNEL32!GetCurrentThreadId` at `0x140003f1e`
- `KERNEL32!IsDebuggerPresent` at `0x140004013`
- `KERNEL32!IsDebuggerPresent` at `0x140004013`
- `KERNEL32!OutputDebugStringW` at `0x14000409d`
- `KERNEL32!OutputDebugStringW` at `0x14000409d`

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
0x140003e58  push    rbp
0x140003e5a  push    rbx
0x140003e5b  push    rsi
0x140003e5c  push    rdi
0x140003e5d  push    r12
0x140003e5f  push    r14
0x140003e61  push    r15
0x140003e63  lea     rbp, [rsp-13D0h]
0x140003e6b  mov     eax, 14D0h
0x140003e70  call    _alloca_probe
0x140003e75  sub     rsp, rax
0x140003e78  mov     rax, cs:__security_cookie
0x140003e7f  xor     rax, rsp
0x140003e82  mov     [rbp+1400h+var_40], rax
0x140003e89  mov     rsi, r8
0x140003e8c  mov     edi, edx
0x140003e8e  mov     rbx, rcx
0x140003e91  mov     r14, [rbp+1400h+arg_28]
0x140003e98  xor     edx, edx; Val
0x140003e9a  mov     r8d, 98h; Size
0x140003ea0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003ea5  call    memset_0
0x140003eaa  nop
0x140003eab  xor     r12d, r12d
0x140003eae  mov     [rbp+1400h+OutputString], r12w
0x140003eb6  mov     [rbp+1400h+var_1440], r12b
0x140003eba  mov     rdx, [rbp+1400h+arg_30]; int
0x140003ec1  mov     ecx, [rdx]; this
0x140003ec3  mov     [rsp+1500h+var_14D8], ecx
0x140003ec7  mov     eax, [rdx+4]
0x140003eca  mov     [rsp+1500h+var_14D4], eax
0x140003ece  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003ed3  mov     r15d, eax
0x140003ed6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003ede  mov     ecx, r12d
0x140003ee1  lea     eax, [r12+8]
0x140003ee6  cmp     dword ptr [rdx+8], 1
0x140003eea  cmovz   ecx, eax
0x140003eed  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003ef1  lea     ecx, [rax-7]
0x140003ef4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003efc  inc     ecx
0x140003efe  mov     [rsp+1500h+var_14D0], ecx
0x140003f02  mov     rcx, [rbp+1400h+arg_38]
0x140003f09  test    rcx, rcx
0x140003f0c  jz      short loc_140003F19
0x140003f0e  cmp     [rcx], r12w
0x140003f12  mov     [rsp+1500h+var_14C8], rcx
0x140003f17  jnz     short loc_140003F1E
0x140003f19  mov     [rsp+1500h+var_14C8], r12
0x140003f1e  call    cs:__imp_GetCurrentThreadId
0x140003f24  mov     [rsp+1500h+var_14C0], eax
0x140003f28  mov     [rsp+1500h+var_14A8], rsi
0x140003f2d  mov     [rsp+1500h+var_14A0], edi
0x140003f31  mov     [rsp+1500h+var_149C], r15d
0x140003f36  mov     [rsp+1500h+var_14B8], r12
0x140003f3b  mov     [rsp+1500h+var_14B0], r12
0x140003f40  mov     [rbp+1400h+var_1458], r14
0x140003f44  mov     [rbp+1400h+var_1450], rbx
0x140003f48  mov     [rsp+1500h+var_1498], r12
0x140003f4d  xorps   xmm0, xmm0
0x140003f50  xor     eax, eax
0x140003f52  movups  [rbp+1400h+var_1478], xmm0
0x140003f56  mov     [rbp+1400h+var_1468], rax
0x140003f5a  xorps   xmm1, xmm1
0x140003f5d  movups  [rsp+1500h+var_1490], xmm1
0x140003f62  mov     [rbp+1400h+var_1480], rax
0x140003f66  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003f6d  test    rax, rax
0x140003f70  jz      short loc_140003F7D
0x140003f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f77  mov     [rbp+1400h+var_1460], rax
0x140003f7b  jmp     short loc_140003F81
0x140003f7d  mov     [rbp+1400h+var_1460], r12
0x140003f81  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003f88  test    rax, rax
0x140003f8b  jz      short loc_140003F97
0x140003f8d  lea     rcx, [rsp+1500h+var_14E0]
0x140003f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f97  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003f9e  test    rax, rax
0x140003fa1  jz      short loc_140003FB7
0x140003fa3  mov     r8d, 400h
0x140003fa9  lea     rdx, [rbp+1400h+var_1440]
0x140003fad  lea     rcx, [rsp+1500h+var_14E0]
0x140003fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fb7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003fbe  test    rax, rax
0x140003fc1  jz      short loc_140003FCD
0x140003fc3  lea     rcx, [rsp+1500h+var_14E0]
0x140003fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fcd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003fd4  test    rax, rax
0x140003fd7  jz      short loc_140003FEA
0x140003fd9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003fde  jnz     short loc_140003FEA
0x140003fe0  lea     rcx, [rsp+1500h+var_14E0]
0x140003fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fea  cmp     [rsp+1500h+var_14D8], r12d
0x140003fef  jge     loc_1400040F8
0x140003ff5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003ffc  jnz     short loc_14000401D
0x140003ffe  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004005  test    rax, rax
0x140004008  jz      short loc_140004013
0x14000400a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000400f  test    al, al
0x140004011  jmp     short loc_14000401B
0x140004013  call    cs:__imp_IsDebuggerPresent
0x140004019  test    eax, eax
0x14000401b  jz      short loc_140004024
0x14000401d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140004022  jz      short loc_14000404A
0x140004024  mov     rax, cs:g_pfnResultLoggingCallback
0x14000402b  test    rax, rax
0x14000402e  jz      short loc_1400040A3
0x140004030  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004037  jnz     short loc_1400040A3
0x140004039  xor     r8d, r8d
0x14000403c  xor     edx, edx
0x14000403e  lea     rcx, [rsp+1500h+var_14E0]
0x140004043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004048  jmp     short loc_1400040A3
0x14000404a  mov     ebx, 800h
0x14000404f  mov     rax, cs:g_pfnResultLoggingCallback
0x140004056  test    rax, rax
0x140004059  jz      short loc_140004078
0x14000405b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004062  jnz     short loc_140004078
0x140004064  mov     r8d, ebx
0x140004067  lea     rdx, [rbp+1400h+OutputString]
0x14000406e  lea     rcx, [rsp+1500h+var_14E0]
0x140004073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004078  cmp     [rbp+1400h+OutputString], r12w
0x140004080  jnz     short loc_140004096
0x140004082  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140004087  mov     rdx, rbx; unsigned __int16 *
0x14000408a  lea     rcx, [rbp+1400h+OutputString]; this
0x140004091  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004096  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000409d  call    cs:__imp_OutputDebugStringW
0x1400040a3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400040a8  jnz     short loc_1400040B3
0x1400040aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400040b1  jz      short loc_1400040C5
0x1400040b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400040ba  test    rax, rax
0x1400040bd  jz      short loc_1400040C5
0x1400040bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040c4  nop
0x1400040c5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400040ca  jnz     short loc_1400040ED
0x1400040cc  mov     rcx, [rbp+1400h+var_40]
0x1400040d3  xor     rcx, rsp; StackCookie
0x1400040d6  call    __security_check_cookie
0x1400040db  add     rsp, 14D0h
0x1400040e2  pop     r15
0x1400040e4  pop     r14
0x1400040e6  pop     r12
0x1400040e8  pop     rdi
0x1400040e9  pop     rsi
0x1400040ea  pop     rbx
0x1400040eb  pop     rbp
0x1400040ec  retn
0x1400040ed  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400040f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400040f8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
