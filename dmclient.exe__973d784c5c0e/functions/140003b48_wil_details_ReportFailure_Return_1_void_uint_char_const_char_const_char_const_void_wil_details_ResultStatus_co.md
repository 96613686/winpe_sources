# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003b48`
- end: `0x140003de8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400032c4`

## callees

- `0x140003b48`
- `0x140006d84`
- `0x14000ae14`
- `0x14000bd4c`
- `0x14000bfc4`
- `0x1400195e2`
- `0x140019610`
- `0x1400196d0`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003bf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003bf6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003d80`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003d80`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003cf0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003cf0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x140003b48  push    rbp
0x140003b4a  push    rbx
0x140003b4b  push    rsi
0x140003b4c  push    rdi
0x140003b4d  push    r12
0x140003b4f  push    r14
0x140003b51  push    r15
0x140003b53  lea     rbp, [rsp-13D0h]
0x140003b5b  mov     eax, 14D0h
0x140003b60  call    _alloca_probe
0x140003b65  sub     rsp, rax
0x140003b68  mov     rax, cs:__security_cookie
0x140003b6f  xor     rax, rsp
0x140003b72  mov     [rbp+1400h+var_40], rax
0x140003b79  mov     r14, r8
0x140003b7c  mov     esi, edx
0x140003b7e  mov     r15, rcx
0x140003b81  mov     rdi, [rbp+1400h+arg_28]
0x140003b88  xor     edx, edx; Val
0x140003b8a  mov     r8d, 98h; Size
0x140003b90  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003b95  call    memset_0
0x140003b9a  nop
0x140003b9b  xor     r12d, r12d
0x140003b9e  mov     [rbp+1400h+OutputString], r12w
0x140003ba6  mov     [rbp+1400h+var_1440], r12b
0x140003baa  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140003bb1  mov     ecx, [rdx]; this
0x140003bb3  mov     [rsp+1500h+var_14D8], ecx
0x140003bb7  mov     eax, [rdx+4]
0x140003bba  mov     [rsp+1500h+var_14D4], eax
0x140003bbe  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003bc3  mov     ebx, eax
0x140003bc5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003bcd  mov     ecx, r12d
0x140003bd0  lea     eax, [r12+8]
0x140003bd5  cmp     dword ptr [rdx+8], 1
0x140003bd9  cmovz   ecx, eax
0x140003bdc  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003be0  lea     ecx, [rax-7]
0x140003be3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003beb  inc     ecx
0x140003bed  mov     [rsp+1500h+var_14D0], ecx
0x140003bf1  mov     [rsp+1500h+var_14C8], r12
0x140003bf6  call    cs:__imp_GetCurrentThreadId
0x140003bfd  nop     dword ptr [rax+rax+00h]
0x140003c02  mov     [rsp+1500h+var_14C0], eax
0x140003c06  mov     [rsp+1500h+var_14A8], r14
0x140003c0b  mov     [rsp+1500h+var_14A0], esi
0x140003c0f  mov     [rsp+1500h+var_149C], ebx
0x140003c13  mov     [rsp+1500h+var_14B8], r12
0x140003c18  mov     [rsp+1500h+var_14B0], r12
0x140003c1d  mov     [rbp+1400h+var_1458], rdi
0x140003c21  mov     [rbp+1400h+var_1450], r15
0x140003c25  mov     [rsp+1500h+var_1498], r12
0x140003c2a  xorps   xmm0, xmm0
0x140003c2d  xor     eax, eax
0x140003c2f  movups  [rbp+1400h+var_1478], xmm0
0x140003c33  mov     [rbp+1400h+var_1468], rax
0x140003c37  xorps   xmm1, xmm1
0x140003c3a  movups  [rsp+1500h+var_1490], xmm1
0x140003c3f  mov     [rbp+1400h+var_1480], rax
0x140003c43  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003c4a  test    rax, rax
0x140003c4d  jz      short loc_140003C5A
0x140003c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c54  mov     [rbp+1400h+var_1460], rax
0x140003c58  jmp     short loc_140003C5E
0x140003c5a  mov     [rbp+1400h+var_1460], r12
0x140003c5e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003c65  test    rax, rax
0x140003c68  jz      short loc_140003C74
0x140003c6a  lea     rcx, [rsp+1500h+var_14E0]
0x140003c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c74  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003c7b  test    rax, rax
0x140003c7e  jz      short loc_140003C94
0x140003c80  mov     r8d, 400h
0x140003c86  lea     rdx, [rbp+1400h+var_1440]
0x140003c8a  lea     rcx, [rsp+1500h+var_14E0]
0x140003c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c94  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003c9b  test    rax, rax
0x140003c9e  jz      short loc_140003CAA
0x140003ca0  lea     rcx, [rsp+1500h+var_14E0]
0x140003ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003caa  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003cb1  test    rax, rax
0x140003cb4  jz      short loc_140003CC7
0x140003cb6  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003cbb  jnz     short loc_140003CC7
0x140003cbd  lea     rcx, [rsp+1500h+var_14E0]
0x140003cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cc7  cmp     [rsp+1500h+var_14D8], r12d
0x140003ccc  jge     loc_140003DE2
0x140003cd2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003cd9  jnz     short loc_140003D00
0x140003cdb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003ce2  test    rax, rax
0x140003ce5  jz      short loc_140003CF0
0x140003ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cec  test    al, al
0x140003cee  jmp     short loc_140003CFE
0x140003cf0  call    cs:__imp_IsDebuggerPresent
0x140003cf7  nop     dword ptr [rax+rax+00h]
0x140003cfc  test    eax, eax
0x140003cfe  jz      short loc_140003D07
0x140003d00  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003d05  jz      short loc_140003D2D
0x140003d07  mov     rax, cs:g_pfnResultLoggingCallback
0x140003d0e  test    rax, rax
0x140003d11  jz      short loc_140003D8C
0x140003d13  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003d1a  jnz     short loc_140003D8C
0x140003d1c  xor     r8d, r8d
0x140003d1f  xor     edx, edx
0x140003d21  lea     rcx, [rsp+1500h+var_14E0]
0x140003d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d2b  jmp     short loc_140003D8C
0x140003d2d  mov     ebx, 800h
0x140003d32  mov     rax, cs:g_pfnResultLoggingCallback
0x140003d39  test    rax, rax
0x140003d3c  jz      short loc_140003D5B
0x140003d3e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003d45  jnz     short loc_140003D5B
0x140003d47  mov     r8d, ebx
0x140003d4a  lea     rdx, [rbp+1400h+OutputString]
0x140003d51  lea     rcx, [rsp+1500h+var_14E0]
0x140003d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d5b  cmp     [rbp+1400h+OutputString], r12w
0x140003d63  jnz     short loc_140003D79
0x140003d65  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140003d6a  mov     rdx, rbx; unsigned __int16 *
0x140003d6d  lea     rcx, [rbp+1400h+OutputString]; this
0x140003d74  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003d79  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003d80  call    cs:__imp_OutputDebugStringW
0x140003d87  nop     dword ptr [rax+rax+00h]
0x140003d8c  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140003d91  jnz     short loc_140003D9C
0x140003d93  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003d9a  jz      short loc_140003DAE
0x140003d9c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003da3  test    rax, rax
0x140003da6  jz      short loc_140003DAE
0x140003da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dad  nop
0x140003dae  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003db3  jnz     short loc_140003DD7
0x140003db5  mov     rcx, [rbp+1400h+var_40]
0x140003dbc  xor     rcx, rsp; StackCookie
0x140003dbf  call    __security_check_cookie
0x140003dc4  add     rsp, 14D0h
0x140003dcb  pop     r15
0x140003dcd  pop     r14
0x140003dcf  pop     r12
0x140003dd1  pop     rdi
0x140003dd2  pop     rsi
0x140003dd3  pop     rbx
0x140003dd4  pop     rbp
0x140003dd5  retn
0x140003dd7  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003ddc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003de2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
