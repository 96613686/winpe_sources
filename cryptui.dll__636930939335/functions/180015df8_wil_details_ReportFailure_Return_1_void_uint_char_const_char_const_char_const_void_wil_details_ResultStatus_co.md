# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180015df8`
- end: `0x18001608c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180015ac0`

## callees

- `0x180015df8`
- `0x180019524`
- `0x18001b4d0`
- `0x18001cad8`
- `0x18001cd80`
- `0x18003e582`
- `0x18003e5c0`
- `0x18003e680`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015ea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015ea2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016027`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016027`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015f9d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015f9d`

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
0x180015df8  mov     [rsp-8+arg_10], rbx
0x180015dfd  push    rbp
0x180015dfe  push    rsi
0x180015dff  push    rdi
0x180015e00  push    r14
0x180015e02  push    r15
0x180015e04  lea     rbp, [rsp-13D0h]
0x180015e0c  mov     eax, 14D0h
0x180015e11  call    _alloca_probe
0x180015e16  sub     rsp, rax
0x180015e19  mov     rax, cs:__security_cookie
0x180015e20  xor     rax, rsp
0x180015e23  mov     [rbp+13F0h+var_30], rax
0x180015e2a  mov     rdi, [rbp+13F0h+arg_28]
0x180015e31  mov     esi, edx
0x180015e33  mov     r14, rcx
0x180015e36  xor     edx, edx; Val
0x180015e38  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180015e3d  mov     r8d, 98h; Size
0x180015e43  call    memset_0
0x180015e48  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180015e4f  xor     r15d, r15d
0x180015e52  mov     [rbp+13F0h+OutputString], r15w
0x180015e5a  mov     [rbp+13F0h+var_1430], r15b
0x180015e5e  mov     ecx, [rdx]; this
0x180015e60  mov     eax, [rdx+4]
0x180015e63  mov     [rsp+14F0h+var_14C8], ecx
0x180015e67  mov     [rsp+14F0h+var_14C4], eax
0x180015e6b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180015e70  cmp     dword ptr [rdx+8], 1
0x180015e74  mov     ebx, eax
0x180015e76  lea     eax, [r15+8]
0x180015e7a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180015e82  mov     ecx, r15d
0x180015e85  cmovz   ecx, eax
0x180015e88  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180015e8c  lea     ecx, [rax-7]
0x180015e8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015e97  inc     ecx
0x180015e99  mov     [rsp+14F0h+var_14B8], r15
0x180015e9e  mov     [rsp+14F0h+var_14C0], ecx
0x180015ea2  call    cs:__imp_GetCurrentThreadId
0x180015ea8  xorps   xmm0, xmm0
0x180015eab  mov     [rsp+14F0h+var_1490], esi
0x180015eaf  mov     [rsp+14F0h+var_14B0], eax
0x180015eb3  xorps   xmm1, xmm1
0x180015eb6  lea     rax, aWil; "wil"
0x180015ebd  mov     [rsp+14F0h+var_148C], ebx
0x180015ec1  mov     [rsp+14F0h+var_1498], rax
0x180015ec6  xor     eax, eax
0x180015ec8  mov     [rbp+13F0h+var_1458], rax
0x180015ecc  mov     [rbp+13F0h+var_1470], rax
0x180015ed0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180015ed7  mov     [rsp+14F0h+var_14A8], r15
0x180015edc  mov     [rsp+14F0h+var_14A0], r15
0x180015ee1  mov     [rbp+13F0h+var_1448], rdi
0x180015ee5  mov     [rbp+13F0h+var_1440], r14
0x180015ee9  mov     [rsp+14F0h+var_1488], r15
0x180015eee  movups  [rbp+13F0h+var_1468], xmm0
0x180015ef2  movups  [rsp+14F0h+var_1480], xmm1
0x180015ef7  test    rax, rax
0x180015efa  jz      short loc_180015F07
0x180015efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f01  mov     [rbp+13F0h+var_1450], rax
0x180015f05  jmp     short loc_180015F0B
0x180015f07  mov     [rbp+13F0h+var_1450], r15
0x180015f0b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015f12  test    rax, rax
0x180015f15  jz      short loc_180015F21
0x180015f17  lea     rcx, [rsp+14F0h+var_14D0]
0x180015f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f21  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015f28  test    rax, rax
0x180015f2b  jz      short loc_180015F41
0x180015f2d  mov     r8d, 400h
0x180015f33  lea     rdx, [rbp+13F0h+var_1430]
0x180015f37  lea     rcx, [rsp+14F0h+var_14D0]
0x180015f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f41  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015f48  test    rax, rax
0x180015f4b  jz      short loc_180015F57
0x180015f4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180015f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f57  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015f5e  test    rax, rax
0x180015f61  jz      short loc_180015F74
0x180015f63  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180015f68  jnz     short loc_180015F74
0x180015f6a  lea     rcx, [rsp+14F0h+var_14D0]
0x180015f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f74  cmp     [rsp+14F0h+var_14C8], r15d
0x180015f79  jge     loc_18001607B
0x180015f7f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180015f86  jnz     short loc_180015FA7
0x180015f88  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015f8f  test    rax, rax
0x180015f92  jz      short loc_180015F9D
0x180015f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f99  test    al, al
0x180015f9b  jmp     short loc_180015FA5
0x180015f9d  call    cs:__imp_IsDebuggerPresent
0x180015fa3  test    eax, eax
0x180015fa5  jz      short loc_180015FAE
0x180015fa7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180015fac  jz      short loc_180015FD4
0x180015fae  mov     rax, cs:g_pfnResultLoggingCallback
0x180015fb5  test    rax, rax
0x180015fb8  jz      short loc_18001602D
0x180015fba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180015fc1  jnz     short loc_18001602D
0x180015fc3  xor     r8d, r8d
0x180015fc6  lea     rcx, [rsp+14F0h+var_14D0]
0x180015fcb  xor     edx, edx
0x180015fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fd2  jmp     short loc_18001602D
0x180015fd4  mov     rax, cs:g_pfnResultLoggingCallback
0x180015fdb  mov     ebx, 800h
0x180015fe0  test    rax, rax
0x180015fe3  jz      short loc_180016002
0x180015fe5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180015fec  jnz     short loc_180016002
0x180015fee  mov     r8d, ebx
0x180015ff1  lea     rdx, [rbp+13F0h+OutputString]
0x180015ff8  lea     rcx, [rsp+14F0h+var_14D0]
0x180015ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016002  cmp     [rbp+13F0h+OutputString], r15w
0x18001600a  jnz     short loc_180016020
0x18001600c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180016011  mov     rdx, rbx; unsigned __int16 *
0x180016014  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001601b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180016020  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180016027  call    cs:__imp_OutputDebugStringW
0x18001602d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180016032  jnz     short loc_18001603D
0x180016034  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001603b  jz      short loc_18001604E
0x18001603d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016044  test    rax, rax
0x180016047  jz      short loc_18001604E
0x180016049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001604e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180016053  jnz     short loc_180016081
0x180016055  mov     rcx, [rbp+13F0h+var_30]
0x18001605c  xor     rcx, rsp; StackCookie
0x18001605f  call    __security_check_cookie
0x180016064  mov     rbx, [rsp+14F0h+arg_10]
0x18001606c  add     rsp, 14D0h
0x180016073  pop     r15
0x180016075  pop     r14
0x180016077  pop     rdi
0x180016078  pop     rsi
0x180016079  pop     rbp
0x18001607a  retn
0x18001607b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180016081  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180016086  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
