# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001ba78`
- end: `0x18001bd1f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001b53c`

## callees

- `0x18001ba78`
- `0x18001d9d4`
- `0x180023dec`
- `0x18002619c`
- `0x180026388`
- `0x18003100e`
- `0x180031040`
- `0x180031100`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001bc23`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001bc23`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001bcb3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001bcb3`

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
0x18001ba78  mov     [rsp-8+arg_10], rbx
0x18001ba7d  push    rbp
0x18001ba7e  push    rsi
0x18001ba7f  push    rdi
0x18001ba80  push    r14
0x18001ba82  push    r15
0x18001ba84  lea     rbp, [rsp-13D0h]
0x18001ba8c  mov     eax, 14D0h
0x18001ba91  call    _alloca_probe
0x18001ba96  sub     rsp, rax
0x18001ba99  mov     rax, cs:__security_cookie
0x18001baa0  xor     rax, rsp
0x18001baa3  mov     [rbp+13F0h+var_30], rax
0x18001baaa  mov     rdi, [rbp+13F0h+arg_28]
0x18001bab1  mov     esi, edx
0x18001bab3  mov     r14, rcx
0x18001bab6  xor     edx, edx; Val
0x18001bab8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001babd  mov     r8d, 98h; Size
0x18001bac3  call    memset_0
0x18001bac8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001bacf  xor     r15d, r15d
0x18001bad2  mov     [rbp+13F0h+OutputString], r15w
0x18001bada  mov     [rbp+13F0h+var_1430], r15b
0x18001bade  mov     ecx, [rdx]; this
0x18001bae0  mov     eax, [rdx+4]
0x18001bae3  mov     [rsp+14F0h+var_14C8], ecx
0x18001bae7  mov     [rsp+14F0h+var_14C4], eax
0x18001baeb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001baf0  cmp     dword ptr [rdx+8], 1
0x18001baf4  mov     ebx, eax
0x18001baf6  lea     eax, [r15+8]
0x18001bafa  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18001bb02  mov     ecx, r15d
0x18001bb05  cmovz   ecx, eax
0x18001bb08  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001bb0c  lea     ecx, [rax-7]
0x18001bb0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18001bb17  inc     ecx
0x18001bb19  mov     [rsp+14F0h+var_14B8], r15
0x18001bb1e  mov     [rsp+14F0h+var_14C0], ecx
0x18001bb22  call    cs:__imp_GetCurrentThreadId
0x18001bb29  nop     dword ptr [rax+rax+00h]
0x18001bb2e  xorps   xmm0, xmm0
0x18001bb31  mov     [rsp+14F0h+var_1490], esi
0x18001bb35  mov     [rsp+14F0h+var_14B0], eax
0x18001bb39  xorps   xmm1, xmm1
0x18001bb3c  lea     rax, aWil; "wil"
0x18001bb43  mov     [rsp+14F0h+var_148C], ebx
0x18001bb47  mov     [rsp+14F0h+var_1498], rax
0x18001bb4c  xor     eax, eax
0x18001bb4e  mov     [rbp+13F0h+var_1458], rax
0x18001bb52  mov     [rbp+13F0h+var_1470], rax
0x18001bb56  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001bb5d  mov     [rsp+14F0h+var_14A8], r15
0x18001bb62  mov     [rsp+14F0h+var_14A0], r15
0x18001bb67  mov     [rbp+13F0h+var_1448], rdi
0x18001bb6b  mov     [rbp+13F0h+var_1440], r14
0x18001bb6f  mov     [rsp+14F0h+var_1488], r15
0x18001bb74  movups  [rbp+13F0h+var_1468], xmm0
0x18001bb78  movups  [rsp+14F0h+var_1480], xmm1
0x18001bb7d  test    rax, rax
0x18001bb80  jz      short loc_18001BB8D
0x18001bb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb87  mov     [rbp+13F0h+var_1450], rax
0x18001bb8b  jmp     short loc_18001BB91
0x18001bb8d  mov     [rbp+13F0h+var_1450], r15
0x18001bb91  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001bb98  test    rax, rax
0x18001bb9b  jz      short loc_18001BBA7
0x18001bb9d  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bba7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001bbae  test    rax, rax
0x18001bbb1  jz      short loc_18001BBC7
0x18001bbb3  mov     r8d, 400h
0x18001bbb9  lea     rdx, [rbp+13F0h+var_1430]
0x18001bbbd  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bbc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbc7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001bbce  test    rax, rax
0x18001bbd1  jz      short loc_18001BBDD
0x18001bbd3  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbdd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001bbe4  test    rax, rax
0x18001bbe7  jz      short loc_18001BBFA
0x18001bbe9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001bbee  jnz     short loc_18001BBFA
0x18001bbf0  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbfa  cmp     [rsp+14F0h+var_14C8], r15d
0x18001bbff  jge     loc_18001BD0E
0x18001bc05  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001bc0c  jnz     short loc_18001BC33
0x18001bc0e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001bc15  test    rax, rax
0x18001bc18  jz      short loc_18001BC23
0x18001bc1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc1f  test    al, al
0x18001bc21  jmp     short loc_18001BC31
0x18001bc23  call    cs:__imp_IsDebuggerPresent
0x18001bc2a  nop     dword ptr [rax+rax+00h]
0x18001bc2f  test    eax, eax
0x18001bc31  jz      short loc_18001BC3A
0x18001bc33  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001bc38  jz      short loc_18001BC60
0x18001bc3a  mov     rax, cs:g_pfnResultLoggingCallback
0x18001bc41  test    rax, rax
0x18001bc44  jz      short loc_18001BCBF
0x18001bc46  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001bc4d  jnz     short loc_18001BCBF
0x18001bc4f  xor     r8d, r8d
0x18001bc52  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bc57  xor     edx, edx
0x18001bc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc5e  jmp     short loc_18001BCBF
0x18001bc60  mov     rax, cs:g_pfnResultLoggingCallback
0x18001bc67  mov     ebx, 800h
0x18001bc6c  test    rax, rax
0x18001bc6f  jz      short loc_18001BC8E
0x18001bc71  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001bc78  jnz     short loc_18001BC8E
0x18001bc7a  mov     r8d, ebx
0x18001bc7d  lea     rdx, [rbp+13F0h+OutputString]
0x18001bc84  lea     rcx, [rsp+14F0h+var_14D0]
0x18001bc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc8e  cmp     [rbp+13F0h+OutputString], r15w
0x18001bc96  jnz     short loc_18001BCAC
0x18001bc98  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001bc9d  mov     rdx, rbx; unsigned __int16 *
0x18001bca0  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001bca7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001bcac  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001bcb3  call    cs:__imp_OutputDebugStringW
0x18001bcba  nop     dword ptr [rax+rax+00h]
0x18001bcbf  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001bcc4  jnz     short loc_18001BCCF
0x18001bcc6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001bccd  jz      short loc_18001BCE0
0x18001bccf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001bcd6  test    rax, rax
0x18001bcd9  jz      short loc_18001BCE0
0x18001bcdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bce0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001bce5  jnz     short loc_18001BD14
0x18001bce7  mov     rcx, [rbp+13F0h+var_30]
0x18001bcee  xor     rcx, rsp; StackCookie
0x18001bcf1  call    __security_check_cookie
0x18001bcf6  mov     rbx, [rsp+14F0h+arg_10]
0x18001bcfe  add     rsp, 14D0h
0x18001bd05  pop     r15
0x18001bd07  pop     r14
0x18001bd09  pop     rdi
0x18001bd0a  pop     rsi
0x18001bd0b  pop     rbp
0x18001bd0c  retn
0x18001bd0e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001bd14  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001bd19  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
