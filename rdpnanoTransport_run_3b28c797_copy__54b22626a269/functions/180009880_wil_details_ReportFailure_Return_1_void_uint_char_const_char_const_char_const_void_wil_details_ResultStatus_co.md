# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180009880`
- end: `0x180009b38`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180008f88`

## callees

- `0x180009880`
- `0x18000ae24`
- `0x18000bbd4`
- `0x18000cac4`
- `0x18000cba4`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180009a3d`
- `KERNEL32!IsDebuggerPresent` at `0x180009a3d`
- `KERNEL32!OutputDebugStringW` at `0x180009aaf`
- `KERNEL32!OutputDebugStringW` at `0x180009aaf`
- `KERNEL32!GetCurrentThreadId` at `0x180009941`
- `KERNEL32!GetCurrentThreadId` at `0x180009941`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  int IsDebuggerPresent; // ecx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh]
  int v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v24; // [rsp+40h] [rbp-C0h]
  _WORD *v25; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h]
  int v31; // [rsp+74h] [rbp-8Ch]
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int128 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int128 v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C0h] [rbp-40h]
  char v40[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v19 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, a2);
  v20 = 1;
  v21 = a10;
  if ( a7[2] == 1 )
    v21 = a10 | 8;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v25 = a8, v14) )
    v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v19;
  v27 = a5;
  v28 = a4;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && wil::g_fResultOutputDebugString
    && (v21 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v20, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v17);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v15);
}

```

## disassembly

```asm
0x180009880  push    rbp
0x180009882  push    rbx
0x180009883  push    rsi
0x180009884  push    rdi
0x180009885  push    r12
0x180009887  push    r13
0x180009889  push    r14
0x18000988b  push    r15
0x18000988d  lea     rbp, [rsp-13E8h]
0x180009895  mov     eax, 14E8h
0x18000989a  call    _alloca_probe
0x18000989f  sub     rsp, rax
0x1800098a2  mov     rax, cs:__security_cookie
0x1800098a9  xor     rax, rsp
0x1800098ac  mov     [rbp+1420h+var_50], rax
0x1800098b3  mov     r15, r9
0x1800098b6  mov     r14, r8
0x1800098b9  mov     esi, edx
0x1800098bb  mov     rdi, rcx
0x1800098be  mov     r12, [rbp+1420h+arg_20]
0x1800098c5  mov     r13, [rbp+1420h+arg_28]
0x1800098cc  xor     eax, eax
0x1800098ce  mov     [rbp+1420h+OutputString], ax
0x1800098d5  mov     [rbp+1420h+var_1450], al
0x1800098d8  mov     rbx, [rbp+1420h+arg_30]
0x1800098df  mov     ecx, [rbx]; this
0x1800098e1  mov     [rsp+1520h+var_14E8], ecx
0x1800098e5  mov     eax, [rbx+4]
0x1800098e8  mov     [rsp+1520h+var_14E4], eax
0x1800098ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800098f1  mov     [rsp+1520h+var_1500], eax
0x1800098f5  mov     eax, 1
0x1800098fa  mov     dword ptr [rsp+1520h+var_14F0], eax
0x1800098fe  mov     ecx, [rbp+1420h+arg_48]
0x180009904  mov     dword ptr [rsp+1520h+var_14F0+4], ecx
0x180009908  cmp     [rbx+8], eax
0x18000990b  jnz     short loc_180009914
0x18000990d  or      ecx, 8
0x180009910  mov     dword ptr [rsp+1520h+var_14F0+4], ecx
0x180009914  mov     ecx, eax
0x180009916  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000991e  add     ecx, eax
0x180009920  mov     [rsp+1520h+var_14E0], ecx
0x180009924  mov     rax, [rbp+1420h+arg_38]
0x18000992b  xor     ebx, ebx
0x18000992d  test    rax, rax
0x180009930  jz      short loc_18000993C
0x180009932  cmp     [rax], bx
0x180009935  mov     [rsp+1520h+var_14D8], rax
0x18000993a  jnz     short loc_180009941
0x18000993c  mov     [rsp+1520h+var_14D8], rbx
0x180009941  call    cs:__imp_GetCurrentThreadId
0x180009947  mov     [rsp+1520h+var_14D0], eax
0x18000994b  mov     [rsp+1520h+var_14B8], r14
0x180009950  mov     [rsp+1520h+var_14B0], esi
0x180009954  mov     eax, [rsp+1520h+var_1500]
0x180009958  mov     [rsp+1520h+var_14AC], eax
0x18000995c  mov     [rsp+1520h+var_14C8], r12
0x180009961  mov     [rsp+1520h+var_14C0], r15
0x180009966  mov     [rbp+1420h+var_1468], r13
0x18000996a  mov     [rbp+1420h+var_1460], rdi
0x18000996e  mov     [rsp+1520h+var_14A8], rbx
0x180009973  xorps   xmm0, xmm0
0x180009976  xor     eax, eax
0x180009978  movups  [rbp+1420h+var_1488], xmm0
0x18000997c  mov     [rbp+1420h+var_1478], rax
0x180009980  xorps   xmm1, xmm1
0x180009983  movups  [rbp+1420h+var_14A0], xmm1
0x180009987  mov     [rbp+1420h+var_1490], rax
0x18000998b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009992  test    rax, rax
0x180009995  jz      short loc_1800099A3
0x180009997  call    cs:__guard_dispatch_icall_fptr
0x18000999d  mov     [rbp+1420h+var_1470], rax
0x1800099a1  jmp     short loc_1800099A7
0x1800099a3  mov     [rbp+1420h+var_1470], rbx
0x1800099a7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800099ae  test    rax, rax
0x1800099b1  jz      short loc_1800099BE
0x1800099b3  lea     rcx, [rsp+1520h+var_14F0]
0x1800099b8  call    cs:__guard_dispatch_icall_fptr
0x1800099be  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800099c5  test    rax, rax
0x1800099c8  jz      short loc_1800099DF
0x1800099ca  mov     r8d, 400h
0x1800099d0  lea     rdx, [rbp+1420h+var_1450]
0x1800099d4  lea     rcx, [rsp+1520h+var_14F0]
0x1800099d9  call    cs:__guard_dispatch_icall_fptr
0x1800099df  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800099e6  test    rax, rax
0x1800099e9  jz      short loc_1800099F6
0x1800099eb  lea     rcx, [rsp+1520h+var_14F0]
0x1800099f0  call    cs:__guard_dispatch_icall_fptr
0x1800099f6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800099fd  test    rax, rax
0x180009a00  jz      short loc_180009A14
0x180009a02  test    byte ptr [rsp+1520h+var_14F0+4], 2
0x180009a07  jnz     short loc_180009A14
0x180009a09  lea     rcx, [rsp+1520h+var_14F0]
0x180009a0e  call    cs:__guard_dispatch_icall_fptr
0x180009a14  cmp     [rsp+1520h+var_14E8], ebx
0x180009a18  jge     loc_180009B32
0x180009a1e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x180009a24  jnz     short loc_180009A4E
0x180009a26  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009a2d  test    rax, rax
0x180009a30  jz      short loc_180009A3D
0x180009a32  call    cs:__guard_dispatch_icall_fptr
0x180009a38  movzx   ecx, al
0x180009a3b  jmp     short loc_180009A4A
0x180009a3d  call    cs:__imp_IsDebuggerPresent
0x180009a43  mov     ecx, ebx
0x180009a45  test    eax, eax
0x180009a47  setnz   cl
0x180009a4a  test    ecx, ecx
0x180009a4c  jz      short loc_180009AB7
0x180009a4e  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, bl; bool wil::g_fResultOutputDebugString
0x180009a54  jz      short loc_180009AB7
0x180009a56  test    byte ptr [rsp+1520h+var_14F0+4], 2
0x180009a5b  jnz     short loc_180009AB7
0x180009a5d  mov     edi, 800h
0x180009a62  mov     rax, cs:g_pfnResultLoggingCallback
0x180009a69  test    rax, rax
0x180009a6c  jz      short loc_180009A8B
0x180009a6e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180009a74  jnz     short loc_180009A8B
0x180009a76  mov     r8d, edi
0x180009a79  lea     rdx, [rbp+1420h+OutputString]
0x180009a80  lea     rcx, [rsp+1520h+var_14F0]
0x180009a85  call    cs:__guard_dispatch_icall_fptr
0x180009a8b  cmp     [rbp+1420h+OutputString], bx
0x180009a92  jnz     short loc_180009AA8
0x180009a94  lea     r8, [rsp+1520h+var_14F0]; unsigned __int64
0x180009a99  mov     rdx, rdi; wchar_t *
0x180009a9c  lea     rcx, [rbp+1420h+OutputString]; this
0x180009aa3  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180009aa8  lea     rcx, [rbp+1420h+OutputString]; lpOutputString
0x180009aaf  call    cs:__imp_OutputDebugStringW
0x180009ab5  jmp     short loc_180009ADB
0x180009ab7  mov     rax, cs:g_pfnResultLoggingCallback
0x180009abe  test    rax, rax
0x180009ac1  jz      short loc_180009ADB
0x180009ac3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180009ac9  jnz     short loc_180009ADB
0x180009acb  xor     r8d, r8d
0x180009ace  xor     edx, edx
0x180009ad0  lea     rcx, [rsp+1520h+var_14F0]
0x180009ad5  call    cs:__guard_dispatch_icall_fptr
0x180009adb  test    byte ptr [rsp+1520h+var_14F0+4], 4
0x180009ae0  jnz     short loc_180009AEA
0x180009ae2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x180009ae8  jz      short loc_180009AFD
0x180009aea  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009af1  test    rax, rax
0x180009af4  jz      short loc_180009AFD
0x180009af6  call    cs:__guard_dispatch_icall_fptr
0x180009afc  nop
0x180009afd  test    byte ptr [rsp+1520h+var_14F0+4], 1
0x180009b02  jnz     short loc_180009B27
0x180009b04  mov     rcx, [rbp+1420h+var_50]
0x180009b0b  xor     rcx, rsp; StackCookie
0x180009b0e  call    __security_check_cookie
0x180009b13  add     rsp, 14E8h
0x180009b1a  pop     r15
0x180009b1c  pop     r14
0x180009b1e  pop     r13
0x180009b20  pop     r12
0x180009b22  pop     rdi
0x180009b23  pop     rsi
0x180009b24  pop     rbx
0x180009b25  pop     rbp
0x180009b26  retn
0x180009b27  lea     rcx, [rsp+1520h+var_14F0]; this
0x180009b2c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009b32  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
