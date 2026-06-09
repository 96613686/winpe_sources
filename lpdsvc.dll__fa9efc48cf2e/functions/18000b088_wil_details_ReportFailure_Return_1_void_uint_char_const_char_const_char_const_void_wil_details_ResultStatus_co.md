# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000b088`
- end: `0x18000b31c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ab70`

## callees

- `0x180001ce0`
- `0x180002616`
- `0x18000b088`
- `0x18000bed4`
- `0x18000cdc0`
- `0x18000d640`
- `0x18000d71c`
- `0x18000d7e0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000b132`
- `KERNEL32!GetCurrentThreadId` at `0x18000b132`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b22d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b22d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b2b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b2b7`

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
0x18000b088  mov     [rsp-8+arg_10], rbx
0x18000b08d  push    rbp
0x18000b08e  push    rsi
0x18000b08f  push    rdi
0x18000b090  push    r14
0x18000b092  push    r15
0x18000b094  lea     rbp, [rsp-13D0h]
0x18000b09c  mov     eax, 14D0h
0x18000b0a1  call    _alloca_probe
0x18000b0a6  sub     rsp, rax
0x18000b0a9  mov     rax, cs:__security_cookie
0x18000b0b0  xor     rax, rsp
0x18000b0b3  mov     [rbp+13F0h+var_30], rax
0x18000b0ba  mov     rdi, [rbp+13F0h+arg_28]
0x18000b0c1  mov     esi, edx
0x18000b0c3  mov     r14, rcx
0x18000b0c6  xor     edx, edx; Val
0x18000b0c8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000b0cd  mov     r8d, 98h; Size
0x18000b0d3  call    memset_0
0x18000b0d8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000b0df  xor     r15d, r15d
0x18000b0e2  mov     [rbp+13F0h+OutputString], r15w
0x18000b0ea  mov     [rbp+13F0h+var_1430], r15b
0x18000b0ee  mov     ecx, [rdx]; this
0x18000b0f0  mov     eax, [rdx+4]
0x18000b0f3  mov     [rsp+14F0h+var_14C8], ecx
0x18000b0f7  mov     [rsp+14F0h+var_14C4], eax
0x18000b0fb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b100  cmp     dword ptr [rdx+8], 1
0x18000b104  mov     ebx, eax
0x18000b106  lea     eax, [r15+8]
0x18000b10a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000b112  mov     ecx, r15d
0x18000b115  cmovz   ecx, eax
0x18000b118  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000b11c  lea     ecx, [rax-7]
0x18000b11f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b127  inc     ecx
0x18000b129  mov     [rsp+14F0h+var_14B8], r15
0x18000b12e  mov     [rsp+14F0h+var_14C0], ecx
0x18000b132  call    cs:__imp_GetCurrentThreadId
0x18000b138  xorps   xmm0, xmm0
0x18000b13b  mov     [rsp+14F0h+var_1490], esi
0x18000b13f  mov     [rsp+14F0h+var_14B0], eax
0x18000b143  xorps   xmm1, xmm1
0x18000b146  lea     rax, aWil; "wil"
0x18000b14d  mov     [rsp+14F0h+var_148C], ebx
0x18000b151  mov     [rsp+14F0h+var_1498], rax
0x18000b156  xor     eax, eax
0x18000b158  mov     [rbp+13F0h+var_1458], rax
0x18000b15c  mov     [rbp+13F0h+var_1470], rax
0x18000b160  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b167  mov     [rsp+14F0h+var_14A8], r15
0x18000b16c  mov     [rsp+14F0h+var_14A0], r15
0x18000b171  mov     [rbp+13F0h+var_1448], rdi
0x18000b175  mov     [rbp+13F0h+var_1440], r14
0x18000b179  mov     [rsp+14F0h+var_1488], r15
0x18000b17e  movups  [rbp+13F0h+var_1468], xmm0
0x18000b182  movups  [rsp+14F0h+var_1480], xmm1
0x18000b187  test    rax, rax
0x18000b18a  jz      short loc_18000B197
0x18000b18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b191  mov     [rbp+13F0h+var_1450], rax
0x18000b195  jmp     short loc_18000B19B
0x18000b197  mov     [rbp+13F0h+var_1450], r15
0x18000b19b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b1a2  test    rax, rax
0x18000b1a5  jz      short loc_18000B1B1
0x18000b1a7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b1b8  test    rax, rax
0x18000b1bb  jz      short loc_18000B1D1
0x18000b1bd  mov     r8d, 400h
0x18000b1c3  lea     rdx, [rbp+13F0h+var_1430]
0x18000b1c7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1d1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b1d8  test    rax, rax
0x18000b1db  jz      short loc_18000B1E7
0x18000b1dd  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1e7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b1ee  test    rax, rax
0x18000b1f1  jz      short loc_18000B204
0x18000b1f3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b1f8  jnz     short loc_18000B204
0x18000b1fa  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b204  cmp     [rsp+14F0h+var_14C8], r15d
0x18000b209  jge     loc_18000B30B
0x18000b20f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000b216  jnz     short loc_18000B237
0x18000b218  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b21f  test    rax, rax
0x18000b222  jz      short loc_18000B22D
0x18000b224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b229  test    al, al
0x18000b22b  jmp     short loc_18000B235
0x18000b22d  call    cs:__imp_IsDebuggerPresent
0x18000b233  test    eax, eax
0x18000b235  jz      short loc_18000B23E
0x18000b237  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b23c  jz      short loc_18000B264
0x18000b23e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b245  test    rax, rax
0x18000b248  jz      short loc_18000B2BD
0x18000b24a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b251  jnz     short loc_18000B2BD
0x18000b253  xor     r8d, r8d
0x18000b256  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b25b  xor     edx, edx
0x18000b25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b262  jmp     short loc_18000B2BD
0x18000b264  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b26b  mov     ebx, 800h
0x18000b270  test    rax, rax
0x18000b273  jz      short loc_18000B292
0x18000b275  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b27c  jnz     short loc_18000B292
0x18000b27e  mov     r8d, ebx
0x18000b281  lea     rdx, [rbp+13F0h+OutputString]
0x18000b288  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b292  cmp     [rbp+13F0h+OutputString], r15w
0x18000b29a  jnz     short loc_18000B2B0
0x18000b29c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000b2a1  mov     rdx, rbx; unsigned __int16 *
0x18000b2a4  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000b2ab  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b2b0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000b2b7  call    cs:__imp_OutputDebugStringW
0x18000b2bd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000b2c2  jnz     short loc_18000B2CD
0x18000b2c4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000b2cb  jz      short loc_18000B2DE
0x18000b2cd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b2d4  test    rax, rax
0x18000b2d7  jz      short loc_18000B2DE
0x18000b2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2de  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000b2e3  jnz     short loc_18000B311
0x18000b2e5  mov     rcx, [rbp+13F0h+var_30]
0x18000b2ec  xor     rcx, rsp; StackCookie
0x18000b2ef  call    __security_check_cookie
0x18000b2f4  mov     rbx, [rsp+14F0h+arg_10]
0x18000b2fc  add     rsp, 14D0h
0x18000b303  pop     r15
0x18000b305  pop     r14
0x18000b307  pop     rdi
0x18000b308  pop     rsi
0x18000b309  pop     rbp
0x18000b30a  retn
0x18000b30b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b311  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b316  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
