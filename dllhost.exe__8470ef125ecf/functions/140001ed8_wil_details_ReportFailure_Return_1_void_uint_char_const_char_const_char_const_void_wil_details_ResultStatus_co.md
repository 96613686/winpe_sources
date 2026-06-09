# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140001ed8`
- end: `0x14000216c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001d78`

## callees

- `0x140001380`
- `0x140001d16`
- `0x140001ed8`
- `0x140002374`
- `0x140002e00`
- `0x140002e80`
- `0x140002f98`
- `0x140003250`
- `0x140004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001f82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001f82`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000207d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000207d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002107`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002107`

## string_xrefs

- `0x140001f96`: `onecore\com\combase\dllhost\surrogat.cxx`

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
  v28 = "onecore\\com\\combase\\dllhost\\surrogat.cxx";
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
0x140001ed8  mov     [rsp-8+arg_10], rbx
0x140001edd  push    rbp
0x140001ede  push    rsi
0x140001edf  push    rdi
0x140001ee0  push    r14
0x140001ee2  push    r15
0x140001ee4  lea     rbp, [rsp-13D0h]
0x140001eec  mov     eax, 14D0h
0x140001ef1  call    _alloca_probe
0x140001ef6  sub     rsp, rax
0x140001ef9  mov     rax, cs:__security_cookie
0x140001f00  xor     rax, rsp
0x140001f03  mov     [rbp+13F0h+var_30], rax
0x140001f0a  mov     rdi, [rbp+13F0h+arg_28]
0x140001f11  mov     esi, edx
0x140001f13  mov     r14, rcx
0x140001f16  xor     edx, edx; Val
0x140001f18  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140001f1d  mov     r8d, 98h; Size
0x140001f23  call    memset_0
0x140001f28  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140001f2f  xor     r15d, r15d
0x140001f32  mov     [rbp+13F0h+OutputString], r15w
0x140001f3a  mov     [rbp+13F0h+var_1430], r15b
0x140001f3e  mov     ecx, [rdx]; this
0x140001f40  mov     eax, [rdx+4]
0x140001f43  mov     [rsp+14F0h+var_14C8], ecx
0x140001f47  mov     [rsp+14F0h+var_14C4], eax
0x140001f4b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140001f50  cmp     dword ptr [rdx+8], 1
0x140001f54  mov     ebx, eax
0x140001f56  lea     eax, [r15+8]
0x140001f5a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140001f62  mov     ecx, r15d
0x140001f65  cmovz   ecx, eax
0x140001f68  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140001f6c  lea     ecx, [rax-7]
0x140001f6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140001f77  inc     ecx
0x140001f79  mov     [rsp+14F0h+var_14B8], r15
0x140001f7e  mov     [rsp+14F0h+var_14C0], ecx
0x140001f82  call    cs:__imp_GetCurrentThreadId
0x140001f88  xorps   xmm0, xmm0
0x140001f8b  mov     [rsp+14F0h+var_1490], esi
0x140001f8f  mov     [rsp+14F0h+var_14B0], eax
0x140001f93  xorps   xmm1, xmm1
0x140001f96  lea     rax, aOnecoreComComb; "onecore\\com\\combase\\dllhost\\surroga"...
0x140001f9d  mov     [rsp+14F0h+var_148C], ebx
0x140001fa1  mov     [rsp+14F0h+var_1498], rax
0x140001fa6  xor     eax, eax
0x140001fa8  mov     [rbp+13F0h+var_1458], rax
0x140001fac  mov     [rbp+13F0h+var_1470], rax
0x140001fb0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140001fb7  mov     [rsp+14F0h+var_14A8], r15
0x140001fbc  mov     [rsp+14F0h+var_14A0], r15
0x140001fc1  mov     [rbp+13F0h+var_1448], rdi
0x140001fc5  mov     [rbp+13F0h+var_1440], r14
0x140001fc9  mov     [rsp+14F0h+var_1488], r15
0x140001fce  movups  [rbp+13F0h+var_1468], xmm0
0x140001fd2  movups  [rsp+14F0h+var_1480], xmm1
0x140001fd7  test    rax, rax
0x140001fda  jz      short loc_140001FE7
0x140001fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fe1  mov     [rbp+13F0h+var_1450], rax
0x140001fe5  jmp     short loc_140001FEB
0x140001fe7  mov     [rbp+13F0h+var_1450], r15
0x140001feb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140001ff2  test    rax, rax
0x140001ff5  jz      short loc_140002001
0x140001ff7  lea     rcx, [rsp+14F0h+var_14D0]
0x140001ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002001  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002008  test    rax, rax
0x14000200b  jz      short loc_140002021
0x14000200d  mov     r8d, 400h
0x140002013  lea     rdx, [rbp+13F0h+var_1430]
0x140002017  lea     rcx, [rsp+14F0h+var_14D0]
0x14000201c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002021  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002028  test    rax, rax
0x14000202b  jz      short loc_140002037
0x14000202d  lea     rcx, [rsp+14F0h+var_14D0]
0x140002032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002037  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000203e  test    rax, rax
0x140002041  jz      short loc_140002054
0x140002043  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002048  jnz     short loc_140002054
0x14000204a  lea     rcx, [rsp+14F0h+var_14D0]
0x14000204f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002054  cmp     [rsp+14F0h+var_14C8], r15d
0x140002059  jge     loc_14000215B
0x14000205f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002066  jnz     short loc_140002087
0x140002068  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000206f  test    rax, rax
0x140002072  jz      short loc_14000207D
0x140002074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002079  test    al, al
0x14000207b  jmp     short loc_140002085
0x14000207d  call    cs:__imp_IsDebuggerPresent
0x140002083  test    eax, eax
0x140002085  jz      short loc_14000208E
0x140002087  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000208c  jz      short loc_1400020B4
0x14000208e  mov     rax, cs:g_pfnResultLoggingCallback
0x140002095  test    rax, rax
0x140002098  jz      short loc_14000210D
0x14000209a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400020a1  jnz     short loc_14000210D
0x1400020a3  xor     r8d, r8d
0x1400020a6  lea     rcx, [rsp+14F0h+var_14D0]
0x1400020ab  xor     edx, edx
0x1400020ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020b2  jmp     short loc_14000210D
0x1400020b4  mov     rax, cs:g_pfnResultLoggingCallback
0x1400020bb  mov     ebx, 800h
0x1400020c0  test    rax, rax
0x1400020c3  jz      short loc_1400020E2
0x1400020c5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400020cc  jnz     short loc_1400020E2
0x1400020ce  mov     r8d, ebx
0x1400020d1  lea     rdx, [rbp+13F0h+OutputString]
0x1400020d8  lea     rcx, [rsp+14F0h+var_14D0]
0x1400020dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020e2  cmp     [rbp+13F0h+OutputString], r15w
0x1400020ea  jnz     short loc_140002100
0x1400020ec  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400020f1  mov     rdx, rbx; unsigned __int16 *
0x1400020f4  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400020fb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002100  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002107  call    cs:__imp_OutputDebugStringW
0x14000210d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002112  jnz     short loc_14000211D
0x140002114  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14000211b  jz      short loc_14000212E
0x14000211d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002124  test    rax, rax
0x140002127  jz      short loc_14000212E
0x140002129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000212e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002133  jnz     short loc_140002161
0x140002135  mov     rcx, [rbp+13F0h+var_30]
0x14000213c  xor     rcx, rsp; StackCookie
0x14000213f  call    __security_check_cookie
0x140002144  mov     rbx, [rsp+14F0h+arg_10]
0x14000214c  add     rsp, 14D0h
0x140002153  pop     r15
0x140002155  pop     r14
0x140002157  pop     rdi
0x140002158  pop     rsi
0x140002159  pop     rbp
0x14000215a  retn
0x14000215b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002161  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002166  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
