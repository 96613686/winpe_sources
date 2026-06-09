# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18004bca8`
- end: `0x18004bf4e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003fb4c`

## callees

- `0x180047240`
- `0x180047f78`
- `0x18004a3d4`
- `0x18004bca8`
- `0x18004e470`
- `0x18004f294`
- `0x18004f52c`
- `0x180077ad0`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bd6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bd6e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004beed`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004beed`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004be63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004be63`

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
0x18004bca8  push    rbp
0x18004bcaa  push    rbx
0x18004bcab  push    rsi
0x18004bcac  push    rdi
0x18004bcad  push    r12
0x18004bcaf  push    r14
0x18004bcb1  push    r15
0x18004bcb3  lea     rbp, [rsp-13D0h]
0x18004bcbb  mov     eax, 14D0h
0x18004bcc0  call    _alloca_probe
0x18004bcc5  sub     rsp, rax
0x18004bcc8  mov     rax, cs:__security_cookie
0x18004bccf  xor     rax, rsp
0x18004bcd2  mov     [rbp+1400h+var_40], rax
0x18004bcd9  mov     rsi, r8
0x18004bcdc  mov     edi, edx
0x18004bcde  mov     rbx, rcx
0x18004bce1  mov     r14, [rbp+1400h+arg_28]
0x18004bce8  xor     edx, edx; Val
0x18004bcea  mov     r8d, 98h; Size
0x18004bcf0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18004bcf5  call    memset_0
0x18004bcfa  nop
0x18004bcfb  xor     r12d, r12d
0x18004bcfe  mov     [rbp+1400h+OutputString], r12w
0x18004bd06  mov     [rbp+1400h+var_1440], r12b
0x18004bd0a  mov     rdx, [rbp+1400h+arg_30]; int
0x18004bd11  mov     ecx, [rdx]; this
0x18004bd13  mov     [rsp+1500h+var_14D8], ecx
0x18004bd17  mov     eax, [rdx+4]
0x18004bd1a  mov     [rsp+1500h+var_14D4], eax
0x18004bd1e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004bd23  mov     r15d, eax
0x18004bd26  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18004bd2e  mov     ecx, r12d
0x18004bd31  lea     eax, [r12+8]
0x18004bd36  cmp     dword ptr [rdx+8], 1
0x18004bd3a  cmovz   ecx, eax
0x18004bd3d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18004bd41  lea     ecx, [rax-7]
0x18004bd44  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004bd4c  inc     ecx
0x18004bd4e  mov     [rsp+1500h+var_14D0], ecx
0x18004bd52  mov     rcx, [rbp+1400h+arg_38]
0x18004bd59  test    rcx, rcx
0x18004bd5c  jz      short loc_18004BD69
0x18004bd5e  cmp     [rcx], r12w
0x18004bd62  mov     [rsp+1500h+var_14C8], rcx
0x18004bd67  jnz     short loc_18004BD6E
0x18004bd69  mov     [rsp+1500h+var_14C8], r12
0x18004bd6e  call    cs:__imp_GetCurrentThreadId
0x18004bd74  mov     [rsp+1500h+var_14C0], eax
0x18004bd78  mov     [rsp+1500h+var_14A8], rsi
0x18004bd7d  mov     [rsp+1500h+var_14A0], edi
0x18004bd81  mov     [rsp+1500h+var_149C], r15d
0x18004bd86  mov     [rsp+1500h+var_14B8], r12
0x18004bd8b  mov     [rsp+1500h+var_14B0], r12
0x18004bd90  mov     [rbp+1400h+var_1458], r14
0x18004bd94  mov     [rbp+1400h+var_1450], rbx
0x18004bd98  mov     [rsp+1500h+var_1498], r12
0x18004bd9d  xorps   xmm0, xmm0
0x18004bda0  xor     eax, eax
0x18004bda2  movups  [rbp+1400h+var_1478], xmm0
0x18004bda6  mov     [rbp+1400h+var_1468], rax
0x18004bdaa  xorps   xmm1, xmm1
0x18004bdad  movups  [rsp+1500h+var_1490], xmm1
0x18004bdb2  mov     [rbp+1400h+var_1480], rax
0x18004bdb6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004bdbd  test    rax, rax
0x18004bdc0  jz      short loc_18004BDCD
0x18004bdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdc7  mov     [rbp+1400h+var_1460], rax
0x18004bdcb  jmp     short loc_18004BDD1
0x18004bdcd  mov     [rbp+1400h+var_1460], r12
0x18004bdd1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004bdd8  test    rax, rax
0x18004bddb  jz      short loc_18004BDE7
0x18004bddd  lea     rcx, [rsp+1500h+var_14E0]
0x18004bde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bde7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004bdee  test    rax, rax
0x18004bdf1  jz      short loc_18004BE07
0x18004bdf3  mov     r8d, 400h
0x18004bdf9  lea     rdx, [rbp+1400h+var_1440]
0x18004bdfd  lea     rcx, [rsp+1500h+var_14E0]
0x18004be02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be07  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004be0e  test    rax, rax
0x18004be11  jz      short loc_18004BE1D
0x18004be13  lea     rcx, [rsp+1500h+var_14E0]
0x18004be18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be1d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004be24  test    rax, rax
0x18004be27  jz      short loc_18004BE3A
0x18004be29  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18004be2e  jnz     short loc_18004BE3A
0x18004be30  lea     rcx, [rsp+1500h+var_14E0]
0x18004be35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be3a  cmp     [rsp+1500h+var_14D8], r12d
0x18004be3f  jge     loc_18004BF48
0x18004be45  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18004be4c  jnz     short loc_18004BE6D
0x18004be4e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004be55  test    rax, rax
0x18004be58  jz      short loc_18004BE63
0x18004be5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be5f  test    al, al
0x18004be61  jmp     short loc_18004BE6B
0x18004be63  call    cs:__imp_IsDebuggerPresent
0x18004be69  test    eax, eax
0x18004be6b  jz      short loc_18004BE74
0x18004be6d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18004be72  jz      short loc_18004BE9A
0x18004be74  mov     rax, cs:g_pfnResultLoggingCallback
0x18004be7b  test    rax, rax
0x18004be7e  jz      short loc_18004BEF3
0x18004be80  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18004be87  jnz     short loc_18004BEF3
0x18004be89  xor     r8d, r8d
0x18004be8c  xor     edx, edx
0x18004be8e  lea     rcx, [rsp+1500h+var_14E0]
0x18004be93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be98  jmp     short loc_18004BEF3
0x18004be9a  mov     ebx, 800h
0x18004be9f  mov     rax, cs:g_pfnResultLoggingCallback
0x18004bea6  test    rax, rax
0x18004bea9  jz      short loc_18004BEC8
0x18004beab  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18004beb2  jnz     short loc_18004BEC8
0x18004beb4  mov     r8d, ebx
0x18004beb7  lea     rdx, [rbp+1400h+OutputString]
0x18004bebe  lea     rcx, [rsp+1500h+var_14E0]
0x18004bec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bec8  cmp     [rbp+1400h+OutputString], r12w
0x18004bed0  jnz     short loc_18004BEE6
0x18004bed2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18004bed7  mov     rdx, rbx; unsigned __int16 *
0x18004beda  lea     rcx, [rbp+1400h+OutputString]; this
0x18004bee1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004bee6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18004beed  call    cs:__imp_OutputDebugStringW
0x18004bef3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18004bef8  jnz     short loc_18004BF03
0x18004befa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18004bf01  jz      short loc_18004BF15
0x18004bf03  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004bf0a  test    rax, rax
0x18004bf0d  jz      short loc_18004BF15
0x18004bf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf14  nop
0x18004bf15  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18004bf1a  jnz     short loc_18004BF3D
0x18004bf1c  mov     rcx, [rbp+1400h+var_40]
0x18004bf23  xor     rcx, rsp; StackCookie
0x18004bf26  call    __security_check_cookie
0x18004bf2b  add     rsp, 14D0h
0x18004bf32  pop     r15
0x18004bf34  pop     r14
0x18004bf36  pop     r12
0x18004bf38  pop     rdi
0x18004bf39  pop     rsi
0x18004bf3a  pop     rbx
0x18004bf3b  pop     rbp
0x18004bf3c  retn
0x18004bf3d  lea     rcx, [rsp+1500h+var_14E0]; this
0x18004bf42  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18004bf48  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
