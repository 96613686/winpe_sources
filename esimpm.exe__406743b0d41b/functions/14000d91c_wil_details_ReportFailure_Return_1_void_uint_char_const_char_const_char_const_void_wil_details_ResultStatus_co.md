# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000d91c`
- end: `0x14000dbb2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000d3c4`

## callees

- `0x140002f60`
- `0x140003b28`
- `0x14000d91c`
- `0x14000fdf4`
- `0x140011658`
- `0x140013bb0`
- `0x140013d7c`
- `0x14003bcc0`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d9c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000d9c7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000db4c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000db4c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000dac2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000dac2`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x14000d91c  mov     [rsp-8+arg_10], rbx
0x14000d921  push    rbp
0x14000d922  push    rsi
0x14000d923  push    rdi
0x14000d924  push    r14
0x14000d926  push    r15
0x14000d928  lea     rbp, [rsp-13D0h]
0x14000d930  mov     eax, 14D0h
0x14000d935  call    _alloca_probe
0x14000d93a  sub     rsp, rax
0x14000d93d  mov     rax, cs:__security_cookie
0x14000d944  xor     rax, rsp
0x14000d947  mov     [rbp+13F0h+var_30], rax
0x14000d94e  mov     esi, edx
0x14000d950  mov     r14, rcx
0x14000d953  mov     rdi, [rbp+13F0h+arg_28]
0x14000d95a  xor     edx, edx; Val
0x14000d95c  mov     r8d, 98h; Size
0x14000d962  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000d967  call    memset_0
0x14000d96c  nop
0x14000d96d  xor     r15d, r15d
0x14000d970  mov     [rbp+13F0h+OutputString], r15w
0x14000d978  mov     [rbp+13F0h+var_1430], r15b
0x14000d97c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000d983  mov     ecx, [rdx]; this
0x14000d985  mov     [rsp+14F0h+var_14C8], ecx
0x14000d989  mov     eax, [rdx+4]
0x14000d98c  mov     [rsp+14F0h+var_14C4], eax
0x14000d990  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000d995  mov     ebx, eax
0x14000d997  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000d99f  mov     ecx, r15d
0x14000d9a2  lea     eax, [r15+8]
0x14000d9a6  cmp     dword ptr [rdx+8], 1
0x14000d9aa  cmovz   ecx, eax
0x14000d9ad  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000d9b1  lea     ecx, [rax-7]
0x14000d9b4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000d9bc  inc     ecx
0x14000d9be  mov     [rsp+14F0h+var_14C0], ecx
0x14000d9c2  mov     [rsp+14F0h+var_14B8], r15
0x14000d9c7  call    cs:__imp_GetCurrentThreadId
0x14000d9cd  mov     [rsp+14F0h+var_14B0], eax
0x14000d9d1  lea     rax, aWil; "wil"
0x14000d9d8  mov     [rsp+14F0h+var_1498], rax
0x14000d9dd  mov     [rsp+14F0h+var_1490], esi
0x14000d9e1  mov     [rsp+14F0h+var_148C], ebx
0x14000d9e5  mov     [rsp+14F0h+var_14A8], r15
0x14000d9ea  mov     [rsp+14F0h+var_14A0], r15
0x14000d9ef  mov     [rbp+13F0h+var_1448], rdi
0x14000d9f3  mov     [rbp+13F0h+var_1440], r14
0x14000d9f7  mov     [rsp+14F0h+var_1488], r15
0x14000d9fc  xorps   xmm0, xmm0
0x14000d9ff  xor     eax, eax
0x14000da01  movups  [rbp+13F0h+var_1468], xmm0
0x14000da05  mov     [rbp+13F0h+var_1458], rax
0x14000da09  xorps   xmm1, xmm1
0x14000da0c  movups  [rsp+14F0h+var_1480], xmm1
0x14000da11  mov     [rbp+13F0h+var_1470], rax
0x14000da15  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000da1c  test    rax, rax
0x14000da1f  jz      short loc_14000DA2C
0x14000da21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da26  mov     [rbp+13F0h+var_1450], rax
0x14000da2a  jmp     short loc_14000DA30
0x14000da2c  mov     [rbp+13F0h+var_1450], r15
0x14000da30  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000da37  test    rax, rax
0x14000da3a  jz      short loc_14000DA46
0x14000da3c  lea     rcx, [rsp+14F0h+var_14D0]
0x14000da41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da46  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000da4d  test    rax, rax
0x14000da50  jz      short loc_14000DA66
0x14000da52  mov     r8d, 400h
0x14000da58  lea     rdx, [rbp+13F0h+var_1430]
0x14000da5c  lea     rcx, [rsp+14F0h+var_14D0]
0x14000da61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da66  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000da6d  test    rax, rax
0x14000da70  jz      short loc_14000DA7C
0x14000da72  lea     rcx, [rsp+14F0h+var_14D0]
0x14000da77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da7c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000da83  test    rax, rax
0x14000da86  jz      short loc_14000DA99
0x14000da88  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000da8d  jnz     short loc_14000DA99
0x14000da8f  lea     rcx, [rsp+14F0h+var_14D0]
0x14000da94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da99  cmp     [rsp+14F0h+var_14C8], r15d
0x14000da9e  jge     loc_14000DBAC
0x14000daa4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000daab  jnz     short loc_14000DACC
0x14000daad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000dab4  test    rax, rax
0x14000dab7  jz      short loc_14000DAC2
0x14000dab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dabe  test    al, al
0x14000dac0  jmp     short loc_14000DACA
0x14000dac2  call    cs:__imp_IsDebuggerPresent
0x14000dac8  test    eax, eax
0x14000daca  jz      short loc_14000DAD3
0x14000dacc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000dad1  jz      short loc_14000DAF9
0x14000dad3  mov     rax, cs:g_pfnResultLoggingCallback
0x14000dada  test    rax, rax
0x14000dadd  jz      short loc_14000DB52
0x14000dadf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000dae6  jnz     short loc_14000DB52
0x14000dae8  xor     r8d, r8d
0x14000daeb  xor     edx, edx
0x14000daed  lea     rcx, [rsp+14F0h+var_14D0]
0x14000daf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000daf7  jmp     short loc_14000DB52
0x14000daf9  mov     ebx, 800h
0x14000dafe  mov     rax, cs:g_pfnResultLoggingCallback
0x14000db05  test    rax, rax
0x14000db08  jz      short loc_14000DB27
0x14000db0a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000db11  jnz     short loc_14000DB27
0x14000db13  mov     r8d, ebx
0x14000db16  lea     rdx, [rbp+13F0h+OutputString]
0x14000db1d  lea     rcx, [rsp+14F0h+var_14D0]
0x14000db22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db27  cmp     [rbp+13F0h+OutputString], r15w
0x14000db2f  jnz     short loc_14000DB45
0x14000db31  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000db36  mov     rdx, rbx; unsigned __int16 *
0x14000db39  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000db40  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000db45  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000db4c  call    cs:__imp_OutputDebugStringW
0x14000db52  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000db57  jnz     short loc_14000DB62
0x14000db59  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14000db60  jz      short loc_14000DB74
0x14000db62  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000db69  test    rax, rax
0x14000db6c  jz      short loc_14000DB74
0x14000db6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db73  nop
0x14000db74  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000db79  jnz     short loc_14000DBA1
0x14000db7b  mov     rcx, [rbp+13F0h+var_30]
0x14000db82  xor     rcx, rsp; StackCookie
0x14000db85  call    __security_check_cookie
0x14000db8a  mov     rbx, [rsp+14F0h+arg_10]
0x14000db92  add     rsp, 14D0h
0x14000db99  pop     r15
0x14000db9b  pop     r14
0x14000db9d  pop     rdi
0x14000db9e  pop     rsi
0x14000db9f  pop     rbp
0x14000dba0  retn
0x14000dba1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000dba6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000dbac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
