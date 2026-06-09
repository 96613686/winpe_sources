# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002ef8`
- end: `0x18000318c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800029e0`

## callees

- `0x180001190`
- `0x180001962`
- `0x180002ef8`
- `0x180003d14`
- `0x180004c20`
- `0x180005620`
- `0x1800056fc`
- `0x18000b390`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fa2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003127`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003127`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000309d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000309d`

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
0x180002ef8  mov     [rsp-8+arg_10], rbx
0x180002efd  push    rbp
0x180002efe  push    rsi
0x180002eff  push    rdi
0x180002f00  push    r14
0x180002f02  push    r15
0x180002f04  lea     rbp, [rsp-13D0h]
0x180002f0c  mov     eax, 14D0h
0x180002f11  call    _alloca_probe
0x180002f16  sub     rsp, rax
0x180002f19  mov     rax, cs:__security_cookie
0x180002f20  xor     rax, rsp
0x180002f23  mov     [rbp+13F0h+var_30], rax
0x180002f2a  mov     rdi, [rbp+13F0h+arg_28]
0x180002f31  mov     esi, edx
0x180002f33  mov     r14, rcx
0x180002f36  xor     edx, edx; Val
0x180002f38  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002f3d  mov     r8d, 98h; Size
0x180002f43  call    memset_0
0x180002f48  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002f4f  xor     r15d, r15d
0x180002f52  mov     [rbp+13F0h+OutputString], r15w
0x180002f5a  mov     [rbp+13F0h+var_1430], r15b
0x180002f5e  mov     ecx, [rdx]; this
0x180002f60  mov     eax, [rdx+4]
0x180002f63  mov     [rsp+14F0h+var_14C8], ecx
0x180002f67  mov     [rsp+14F0h+var_14C4], eax
0x180002f6b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002f70  cmp     dword ptr [rdx+8], 1
0x180002f74  mov     ebx, eax
0x180002f76  lea     eax, [r15+8]
0x180002f7a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002f82  mov     ecx, r15d
0x180002f85  cmovz   ecx, eax
0x180002f88  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002f8c  lea     ecx, [rax-7]
0x180002f8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002f97  inc     ecx
0x180002f99  mov     [rsp+14F0h+var_14B8], r15
0x180002f9e  mov     [rsp+14F0h+var_14C0], ecx
0x180002fa2  call    cs:__imp_GetCurrentThreadId
0x180002fa8  xorps   xmm0, xmm0
0x180002fab  mov     [rsp+14F0h+var_1490], esi
0x180002faf  mov     [rsp+14F0h+var_14B0], eax
0x180002fb3  xorps   xmm1, xmm1
0x180002fb6  lea     rax, aWil; "wil"
0x180002fbd  mov     [rsp+14F0h+var_148C], ebx
0x180002fc1  mov     [rsp+14F0h+var_1498], rax
0x180002fc6  xor     eax, eax
0x180002fc8  mov     [rbp+13F0h+var_1458], rax
0x180002fcc  mov     [rbp+13F0h+var_1470], rax
0x180002fd0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002fd7  mov     [rsp+14F0h+var_14A8], r15
0x180002fdc  mov     [rsp+14F0h+var_14A0], r15
0x180002fe1  mov     [rbp+13F0h+var_1448], rdi
0x180002fe5  mov     [rbp+13F0h+var_1440], r14
0x180002fe9  mov     [rsp+14F0h+var_1488], r15
0x180002fee  movups  [rbp+13F0h+var_1468], xmm0
0x180002ff2  movups  [rsp+14F0h+var_1480], xmm1
0x180002ff7  test    rax, rax
0x180002ffa  jz      short loc_180003007
0x180002ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003001  mov     [rbp+13F0h+var_1450], rax
0x180003005  jmp     short loc_18000300B
0x180003007  mov     [rbp+13F0h+var_1450], r15
0x18000300b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003012  test    rax, rax
0x180003015  jz      short loc_180003021
0x180003017  lea     rcx, [rsp+14F0h+var_14D0]
0x18000301c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003021  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003028  test    rax, rax
0x18000302b  jz      short loc_180003041
0x18000302d  mov     r8d, 400h
0x180003033  lea     rdx, [rbp+13F0h+var_1430]
0x180003037  lea     rcx, [rsp+14F0h+var_14D0]
0x18000303c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003041  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003048  test    rax, rax
0x18000304b  jz      short loc_180003057
0x18000304d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003057  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000305e  test    rax, rax
0x180003061  jz      short loc_180003074
0x180003063  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003068  jnz     short loc_180003074
0x18000306a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000306f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003074  cmp     [rsp+14F0h+var_14C8], r15d
0x180003079  jge     loc_18000317B
0x18000307f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003086  jnz     short loc_1800030A7
0x180003088  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000308f  test    rax, rax
0x180003092  jz      short loc_18000309D
0x180003094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003099  test    al, al
0x18000309b  jmp     short loc_1800030A5
0x18000309d  call    cs:__imp_IsDebuggerPresent
0x1800030a3  test    eax, eax
0x1800030a5  jz      short loc_1800030AE
0x1800030a7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800030ac  jz      short loc_1800030D4
0x1800030ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030b5  test    rax, rax
0x1800030b8  jz      short loc_18000312D
0x1800030ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800030c1  jnz     short loc_18000312D
0x1800030c3  xor     r8d, r8d
0x1800030c6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030cb  xor     edx, edx
0x1800030cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d2  jmp     short loc_18000312D
0x1800030d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030db  mov     ebx, 800h
0x1800030e0  test    rax, rax
0x1800030e3  jz      short loc_180003102
0x1800030e5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800030ec  jnz     short loc_180003102
0x1800030ee  mov     r8d, ebx
0x1800030f1  lea     rdx, [rbp+13F0h+OutputString]
0x1800030f8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003102  cmp     [rbp+13F0h+OutputString], r15w
0x18000310a  jnz     short loc_180003120
0x18000310c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003111  mov     rdx, rbx; unsigned __int16 *
0x180003114  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000311b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003120  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003127  call    cs:__imp_OutputDebugStringW
0x18000312d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003132  jnz     short loc_18000313D
0x180003134  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000313b  jz      short loc_18000314E
0x18000313d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003144  test    rax, rax
0x180003147  jz      short loc_18000314E
0x180003149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003153  jnz     short loc_180003181
0x180003155  mov     rcx, [rbp+13F0h+var_30]
0x18000315c  xor     rcx, rsp; StackCookie
0x18000315f  call    __security_check_cookie
0x180003164  mov     rbx, [rsp+14F0h+arg_10]
0x18000316c  add     rsp, 14D0h
0x180003173  pop     r15
0x180003175  pop     r14
0x180003177  pop     rdi
0x180003178  pop     rsi
0x180003179  pop     rbp
0x18000317a  retn
0x18000317b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003181  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003186  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
