# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006bfc`
- end: `0x180006e87`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000688c`

## callees

- `0x180004de0`
- `0x180005858`
- `0x180006bfc`
- `0x180008b14`
- `0x18000a87c`
- `0x18000c388`
- `0x18000c594`
- `0x180023d20`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ca9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ca9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d9d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d9d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006e27`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006e27`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
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
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180006bfc  push    rbp
0x180006bfe  push    rbx
0x180006bff  push    rsi
0x180006c00  push    rdi
0x180006c01  push    r12
0x180006c03  push    r14
0x180006c05  push    r15
0x180006c07  lea     rbp, [rsp-13D0h]
0x180006c0f  mov     eax, 14D0h
0x180006c14  call    _alloca_probe
0x180006c19  sub     rsp, rax
0x180006c1c  mov     rax, cs:__security_cookie
0x180006c23  xor     rax, rsp
0x180006c26  mov     [rbp+1400h+var_40], rax
0x180006c2d  mov     rdi, [rbp+1400h+arg_28]
0x180006c34  mov     r14, r8
0x180006c37  mov     esi, edx
0x180006c39  mov     r15, rcx
0x180006c3c  xor     edx, edx; Val
0x180006c3e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006c43  mov     r8d, 98h; Size
0x180006c49  call    memset_0
0x180006c4e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180006c55  xor     r12d, r12d
0x180006c58  mov     [rbp+1400h+OutputString], r12w
0x180006c60  mov     [rbp+1400h+var_1440], r12b
0x180006c64  mov     ecx, [rdx]; this
0x180006c66  mov     eax, [rdx+4]
0x180006c69  mov     [rsp+1500h+var_14D8], ecx
0x180006c6d  mov     [rsp+1500h+var_14D4], eax
0x180006c71  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006c76  cmp     dword ptr [rdx+8], 1
0x180006c7a  mov     ebx, eax
0x180006c7c  lea     eax, [r12+8]
0x180006c81  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006c89  mov     ecx, r12d
0x180006c8c  cmovz   ecx, eax
0x180006c8f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006c93  lea     ecx, [rax-7]
0x180006c96  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006c9e  inc     ecx
0x180006ca0  mov     [rsp+1500h+var_14C8], r12
0x180006ca5  mov     [rsp+1500h+var_14D0], ecx
0x180006ca9  call    cs:__imp_GetCurrentThreadId
0x180006caf  xorps   xmm0, xmm0
0x180006cb2  mov     [rsp+1500h+var_14A8], r14
0x180006cb7  mov     [rsp+1500h+var_14C0], eax
0x180006cbb  xorps   xmm1, xmm1
0x180006cbe  xor     eax, eax
0x180006cc0  mov     [rsp+1500h+var_14A0], esi
0x180006cc4  mov     [rbp+1400h+var_1468], rax
0x180006cc8  mov     [rbp+1400h+var_1480], rax
0x180006ccc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006cd3  mov     [rsp+1500h+var_149C], ebx
0x180006cd7  mov     [rsp+1500h+var_14B8], r12
0x180006cdc  mov     [rsp+1500h+var_14B0], r12
0x180006ce1  mov     [rbp+1400h+var_1458], rdi
0x180006ce5  mov     [rbp+1400h+var_1450], r15
0x180006ce9  mov     [rsp+1500h+var_1498], r12
0x180006cee  movups  [rbp+1400h+var_1478], xmm0
0x180006cf2  movups  [rsp+1500h+var_1490], xmm1
0x180006cf7  test    rax, rax
0x180006cfa  jz      short loc_180006D07
0x180006cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d01  mov     [rbp+1400h+var_1460], rax
0x180006d05  jmp     short loc_180006D0B
0x180006d07  mov     [rbp+1400h+var_1460], r12
0x180006d0b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006d12  test    rax, rax
0x180006d15  jz      short loc_180006D21
0x180006d17  lea     rcx, [rsp+1500h+var_14E0]
0x180006d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d21  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006d28  test    rax, rax
0x180006d2b  jz      short loc_180006D41
0x180006d2d  mov     r8d, 400h
0x180006d33  lea     rdx, [rbp+1400h+var_1440]
0x180006d37  lea     rcx, [rsp+1500h+var_14E0]
0x180006d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d41  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d48  test    rax, rax
0x180006d4b  jz      short loc_180006D57
0x180006d4d  lea     rcx, [rsp+1500h+var_14E0]
0x180006d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d57  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d5e  test    rax, rax
0x180006d61  jz      short loc_180006D74
0x180006d63  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006d68  jnz     short loc_180006D74
0x180006d6a  lea     rcx, [rsp+1500h+var_14E0]
0x180006d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d74  cmp     [rsp+1500h+var_14D8], r12d
0x180006d79  jge     loc_180006E76
0x180006d7f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006d86  jnz     short loc_180006DA7
0x180006d88  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006d8f  test    rax, rax
0x180006d92  jz      short loc_180006D9D
0x180006d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d99  test    al, al
0x180006d9b  jmp     short loc_180006DA5
0x180006d9d  call    cs:__imp_IsDebuggerPresent
0x180006da3  test    eax, eax
0x180006da5  jz      short loc_180006DAE
0x180006da7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006dac  jz      short loc_180006DD4
0x180006dae  mov     rax, cs:g_pfnResultLoggingCallback
0x180006db5  test    rax, rax
0x180006db8  jz      short loc_180006E2D
0x180006dba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006dc1  jnz     short loc_180006E2D
0x180006dc3  xor     r8d, r8d
0x180006dc6  lea     rcx, [rsp+1500h+var_14E0]
0x180006dcb  xor     edx, edx
0x180006dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd2  jmp     short loc_180006E2D
0x180006dd4  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ddb  mov     ebx, 800h
0x180006de0  test    rax, rax
0x180006de3  jz      short loc_180006E02
0x180006de5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006dec  jnz     short loc_180006E02
0x180006dee  mov     r8d, ebx
0x180006df1  lea     rdx, [rbp+1400h+OutputString]
0x180006df8  lea     rcx, [rsp+1500h+var_14E0]
0x180006dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e02  cmp     [rbp+1400h+OutputString], r12w
0x180006e0a  jnz     short loc_180006E20
0x180006e0c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006e11  mov     rdx, rbx; unsigned __int16 *
0x180006e14  lea     rcx, [rbp+1400h+OutputString]; this
0x180006e1b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006e20  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006e27  call    cs:__imp_OutputDebugStringW
0x180006e2d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006e32  jnz     short loc_180006E3D
0x180006e34  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006e3b  jz      short loc_180006E4E
0x180006e3d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006e44  test    rax, rax
0x180006e47  jz      short loc_180006E4E
0x180006e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e4e  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006e53  jnz     short loc_180006E7C
0x180006e55  mov     rcx, [rbp+1400h+var_40]
0x180006e5c  xor     rcx, rsp; StackCookie
0x180006e5f  call    __security_check_cookie
0x180006e64  add     rsp, 14D0h
0x180006e6b  pop     r15
0x180006e6d  pop     r14
0x180006e6f  pop     r12
0x180006e71  pop     rdi
0x180006e72  pop     rsi
0x180006e73  pop     rbx
0x180006e74  pop     rbp
0x180006e75  retn
0x180006e76  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006e7c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006e81  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
