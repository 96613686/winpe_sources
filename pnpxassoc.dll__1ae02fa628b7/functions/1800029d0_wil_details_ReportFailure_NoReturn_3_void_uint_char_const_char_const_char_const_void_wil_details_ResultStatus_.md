# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800029d0`
- end: `0x180002c30`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002774`

## callees

- `0x1800029d0`
- `0x180003af4`
- `0x18000428c`
- `0x1800049b0`
- `0x180005260`
- `0x180012dce`
- `0x180012e90`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002a71`
- `KERNEL32!GetCurrentThreadId` at `0x180002a71`
- `KERNEL32!OutputDebugStringW` at `0x180002bfe`
- `KERNEL32!OutputDebugStringW` at `0x180002bfe`
- `KERNEL32!IsDebuggerPresent` at `0x180002b74`
- `KERNEL32!IsDebuggerPresent` at `0x180002b74`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x1800029d0  mov     [rsp-8+arg_18], rbx
0x1800029d5  push    rbp
0x1800029d6  push    rsi
0x1800029d7  push    rdi
0x1800029d8  push    r12
0x1800029da  push    r13
0x1800029dc  push    r14
0x1800029de  push    r15
0x1800029e0  lea     rbp, [rsp-13C0h]
0x1800029e8  mov     eax, 14C0h
0x1800029ed  call    _alloca_probe
0x1800029f2  sub     rsp, rax
0x1800029f5  mov     rsi, [rbp+13F0h+arg_28]
0x1800029fc  mov     r15, r8
0x1800029ff  mov     r14d, edx
0x180002a02  mov     r12, rcx
0x180002a05  xor     edx, edx; Val
0x180002a07  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002a0c  mov     r8d, 98h; Size
0x180002a12  call    memset_0
0x180002a17  mov     rbx, [rbp+13F0h+arg_30]
0x180002a1e  xor     r13d, r13d
0x180002a21  mov     [rbp+13F0h+OutputString], r13w
0x180002a29  mov     [rbp+13F0h+var_1430], r13b
0x180002a2d  mov     ecx, [rbx]; this
0x180002a2f  mov     eax, [rbx+4]
0x180002a32  mov     [rsp+14F0h+var_14C8], ecx
0x180002a36  mov     [rsp+14F0h+var_14C4], eax
0x180002a3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002a3f  cmp     dword ptr [rbx+8], 1
0x180002a43  mov     edi, eax
0x180002a45  lea     eax, [r13+8]
0x180002a49  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002a51  mov     ecx, r13d
0x180002a54  cmovz   ecx, eax
0x180002a57  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002a5b  lea     ecx, [rax-7]
0x180002a5e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002a66  inc     ecx
0x180002a68  mov     [rsp+14F0h+var_14B8], r13
0x180002a6d  mov     [rsp+14F0h+var_14C0], ecx
0x180002a71  call    cs:__imp_GetCurrentThreadId
0x180002a77  xorps   xmm0, xmm0
0x180002a7a  mov     [rsp+14F0h+var_1498], r15
0x180002a7f  mov     [rsp+14F0h+var_14B0], eax
0x180002a83  xorps   xmm1, xmm1
0x180002a86  xor     eax, eax
0x180002a88  mov     [rsp+14F0h+var_1490], r14d
0x180002a8d  mov     [rbp+13F0h+var_1458], rax
0x180002a91  mov     [rbp+13F0h+var_1470], rax
0x180002a95  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a9c  mov     [rsp+14F0h+var_148C], edi
0x180002aa0  mov     [rsp+14F0h+var_14A8], r13
0x180002aa5  mov     [rsp+14F0h+var_14A0], r13
0x180002aaa  mov     [rbp+13F0h+var_1448], rsi
0x180002aae  mov     [rbp+13F0h+var_1440], r12
0x180002ab2  mov     [rsp+14F0h+var_1488], r13
0x180002ab7  movups  [rbp+13F0h+var_1468], xmm0
0x180002abb  movups  [rsp+14F0h+var_1480], xmm1
0x180002ac0  test    rax, rax
0x180002ac3  jz      short loc_180002AD0
0x180002ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aca  mov     [rbp+13F0h+var_1450], rax
0x180002ace  jmp     short loc_180002AD4
0x180002ad0  mov     [rbp+13F0h+var_1450], r13
0x180002ad4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002adb  test    rax, rax
0x180002ade  jz      short loc_180002AEA
0x180002ae0  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aea  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002af1  test    rax, rax
0x180002af4  jz      short loc_180002B0A
0x180002af6  mov     r8d, 400h
0x180002afc  lea     rdx, [rbp+13F0h+var_1430]
0x180002b00  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b0a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b11  test    rax, rax
0x180002b14  jz      short loc_180002B20
0x180002b16  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b20  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b27  test    rax, rax
0x180002b2a  jz      short loc_180002B3D
0x180002b2c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002b31  jnz     short loc_180002B3D
0x180002b33  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3d  cmp     [rsp+14F0h+var_14C8], r13d
0x180002b42  jl      short loc_180002B56
0x180002b44  mov     ecx, 8000FFFFh; this
0x180002b49  mov     [rsp+14F0h+var_14C8], ecx
0x180002b4d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002b52  mov     [rsp+14F0h+var_14C4], eax
0x180002b56  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002b5d  jnz     short loc_180002B7E
0x180002b5f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002b66  test    rax, rax
0x180002b69  jz      short loc_180002B74
0x180002b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b70  test    al, al
0x180002b72  jmp     short loc_180002B7C
0x180002b74  call    cs:__imp_IsDebuggerPresent
0x180002b7a  test    eax, eax
0x180002b7c  jz      short loc_180002B85
0x180002b7e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002b83  jz      short loc_180002BAB
0x180002b85  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b8c  test    rax, rax
0x180002b8f  jz      short loc_180002C04
0x180002b91  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002b98  jnz     short loc_180002C04
0x180002b9a  xor     r8d, r8d
0x180002b9d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ba2  xor     edx, edx
0x180002ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba9  jmp     short loc_180002C04
0x180002bab  mov     rax, cs:g_pfnResultLoggingCallback
0x180002bb2  mov     ebx, 800h
0x180002bb7  test    rax, rax
0x180002bba  jz      short loc_180002BD9
0x180002bbc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002bc3  jnz     short loc_180002BD9
0x180002bc5  mov     r8d, ebx
0x180002bc8  lea     rdx, [rbp+13F0h+OutputString]
0x180002bcf  lea     rcx, [rsp+14F0h+var_14D0]
0x180002bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd9  cmp     [rbp+13F0h+OutputString], r13w
0x180002be1  jnz     short loc_180002BF7
0x180002be3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002be8  mov     rdx, rbx; unsigned __int16 *
0x180002beb  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002bf2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002bf7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002bfe  call    cs:__imp_OutputDebugStringW
0x180002c04  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002c09  jnz     short loc_180002C14
0x180002c0b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002c12  jz      short loc_180002C25
0x180002c14  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002c1b  test    rax, rax
0x180002c1e  jz      short loc_180002C25
0x180002c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c25  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002c2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
