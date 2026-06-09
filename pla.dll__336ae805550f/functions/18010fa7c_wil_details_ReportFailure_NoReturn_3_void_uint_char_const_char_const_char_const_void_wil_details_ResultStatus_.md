# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18010fa7c`
- end: `0x18010fcdc`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18010f848`

## callees

- `0x18010c0f0`
- `0x18010fa7c`
- `0x1801128dc`
- `0x180113060`
- `0x180116d00`
- `0x18013ae9a`
- `0x18013af70`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18010fcaa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18010fcaa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18010fc20`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18010fc20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010fb1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010fb1d`

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
0x18010fa7c  mov     [rsp-8+arg_18], rbx
0x18010fa81  push    rbp
0x18010fa82  push    rsi
0x18010fa83  push    rdi
0x18010fa84  push    r12
0x18010fa86  push    r13
0x18010fa88  push    r14
0x18010fa8a  push    r15
0x18010fa8c  lea     rbp, [rsp-13C0h]
0x18010fa94  mov     eax, 14C0h
0x18010fa99  call    _alloca_probe
0x18010fa9e  sub     rsp, rax
0x18010faa1  mov     rsi, [rbp+13F0h+arg_28]
0x18010faa8  mov     r15, r8
0x18010faab  mov     r14d, edx
0x18010faae  mov     r12, rcx
0x18010fab1  xor     edx, edx; Val
0x18010fab3  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18010fab8  mov     r8d, 98h; Size
0x18010fabe  call    memset_0
0x18010fac3  mov     rbx, [rbp+13F0h+arg_30]
0x18010faca  xor     r13d, r13d
0x18010facd  mov     [rbp+13F0h+OutputString], r13w
0x18010fad5  mov     [rbp+13F0h+var_1430], r13b
0x18010fad9  mov     ecx, [rbx]; this
0x18010fadb  mov     eax, [rbx+4]
0x18010fade  mov     [rsp+14F0h+var_14C8], ecx
0x18010fae2  mov     [rsp+14F0h+var_14C4], eax
0x18010fae6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18010faeb  cmp     dword ptr [rbx+8], 1
0x18010faef  mov     edi, eax
0x18010faf1  lea     eax, [r13+8]
0x18010faf5  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18010fafd  mov     ecx, r13d
0x18010fb00  cmovz   ecx, eax
0x18010fb03  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18010fb07  lea     ecx, [rax-7]
0x18010fb0a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18010fb12  inc     ecx
0x18010fb14  mov     [rsp+14F0h+var_14B8], r13
0x18010fb19  mov     [rsp+14F0h+var_14C0], ecx
0x18010fb1d  call    cs:__imp_GetCurrentThreadId
0x18010fb23  xorps   xmm0, xmm0
0x18010fb26  mov     [rsp+14F0h+var_1498], r15
0x18010fb2b  mov     [rsp+14F0h+var_14B0], eax
0x18010fb2f  xorps   xmm1, xmm1
0x18010fb32  xor     eax, eax
0x18010fb34  mov     [rsp+14F0h+var_1490], r14d
0x18010fb39  mov     [rbp+13F0h+var_1458], rax
0x18010fb3d  mov     [rbp+13F0h+var_1470], rax
0x18010fb41  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18010fb48  mov     [rsp+14F0h+var_148C], edi
0x18010fb4c  mov     [rsp+14F0h+var_14A8], r13
0x18010fb51  mov     [rsp+14F0h+var_14A0], r13
0x18010fb56  mov     [rbp+13F0h+var_1448], rsi
0x18010fb5a  mov     [rbp+13F0h+var_1440], r12
0x18010fb5e  mov     [rsp+14F0h+var_1488], r13
0x18010fb63  movups  [rbp+13F0h+var_1468], xmm0
0x18010fb67  movups  [rsp+14F0h+var_1480], xmm1
0x18010fb6c  test    rax, rax
0x18010fb6f  jz      short loc_18010FB7C
0x18010fb71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fb76  mov     [rbp+13F0h+var_1450], rax
0x18010fb7a  jmp     short loc_18010FB80
0x18010fb7c  mov     [rbp+13F0h+var_1450], r13
0x18010fb80  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18010fb87  test    rax, rax
0x18010fb8a  jz      short loc_18010FB96
0x18010fb8c  lea     rcx, [rsp+14F0h+var_14D0]
0x18010fb91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fb96  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18010fb9d  test    rax, rax
0x18010fba0  jz      short loc_18010FBB6
0x18010fba2  mov     r8d, 400h
0x18010fba8  lea     rdx, [rbp+13F0h+var_1430]
0x18010fbac  lea     rcx, [rsp+14F0h+var_14D0]
0x18010fbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fbb6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18010fbbd  test    rax, rax
0x18010fbc0  jz      short loc_18010FBCC
0x18010fbc2  lea     rcx, [rsp+14F0h+var_14D0]
0x18010fbc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fbcc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18010fbd3  test    rax, rax
0x18010fbd6  jz      short loc_18010FBE9
0x18010fbd8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18010fbdd  jnz     short loc_18010FBE9
0x18010fbdf  lea     rcx, [rsp+14F0h+var_14D0]
0x18010fbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fbe9  cmp     [rsp+14F0h+var_14C8], r13d
0x18010fbee  jl      short loc_18010FC02
0x18010fbf0  mov     ecx, 8000FFFFh; this
0x18010fbf5  mov     [rsp+14F0h+var_14C8], ecx
0x18010fbf9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18010fbfe  mov     [rsp+14F0h+var_14C4], eax
0x18010fc02  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18010fc09  jnz     short loc_18010FC2A
0x18010fc0b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18010fc12  test    rax, rax
0x18010fc15  jz      short loc_18010FC20
0x18010fc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fc1c  test    al, al
0x18010fc1e  jmp     short loc_18010FC28
0x18010fc20  call    cs:__imp_IsDebuggerPresent
0x18010fc26  test    eax, eax
0x18010fc28  jz      short loc_18010FC31
0x18010fc2a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18010fc2f  jz      short loc_18010FC57
0x18010fc31  mov     rax, cs:g_pfnResultLoggingCallback
0x18010fc38  test    rax, rax
0x18010fc3b  jz      short loc_18010FCB0
0x18010fc3d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18010fc44  jnz     short loc_18010FCB0
0x18010fc46  xor     r8d, r8d
0x18010fc49  lea     rcx, [rsp+14F0h+var_14D0]
0x18010fc4e  xor     edx, edx
0x18010fc50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fc55  jmp     short loc_18010FCB0
0x18010fc57  mov     rax, cs:g_pfnResultLoggingCallback
0x18010fc5e  mov     ebx, 800h
0x18010fc63  test    rax, rax
0x18010fc66  jz      short loc_18010FC85
0x18010fc68  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18010fc6f  jnz     short loc_18010FC85
0x18010fc71  mov     r8d, ebx
0x18010fc74  lea     rdx, [rbp+13F0h+OutputString]
0x18010fc7b  lea     rcx, [rsp+14F0h+var_14D0]
0x18010fc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fc85  cmp     [rbp+13F0h+OutputString], r13w
0x18010fc8d  jnz     short loc_18010FCA3
0x18010fc8f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18010fc94  mov     rdx, rbx; unsigned __int16 *
0x18010fc97  lea     rcx, [rbp+13F0h+OutputString]; this
0x18010fc9e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18010fca3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18010fcaa  call    cs:__imp_OutputDebugStringW
0x18010fcb0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18010fcb5  jnz     short loc_18010FCC0
0x18010fcb7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18010fcbe  jz      short loc_18010FCD1
0x18010fcc0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18010fcc7  test    rax, rax
0x18010fcca  jz      short loc_18010FCD1
0x18010fccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fcd1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18010fcd6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
