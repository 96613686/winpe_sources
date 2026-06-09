# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800e4d6c`
- end: `0x1800e5025`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800e48d4`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800a9fc0`
- `0x1800e4d6c`
- `0x1800ea714`
- `0x1800ec884`
- `0x1800ee8f0`
- `0x1800ef1b8`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e4e32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e4e32`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e4f2d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e4f2d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e4fbd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e4fbd`

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
0x1800e4d6c  push    rbp
0x1800e4d6e  push    rbx
0x1800e4d6f  push    rsi
0x1800e4d70  push    rdi
0x1800e4d71  push    r12
0x1800e4d73  push    r14
0x1800e4d75  push    r15
0x1800e4d77  lea     rbp, [rsp-13D0h]
0x1800e4d7f  mov     eax, 14D0h
0x1800e4d84  call    _alloca_probe
0x1800e4d89  sub     rsp, rax
0x1800e4d8c  mov     rax, cs:__security_cookie
0x1800e4d93  xor     rax, rsp
0x1800e4d96  mov     [rbp+1400h+var_40], rax
0x1800e4d9d  mov     rsi, r8
0x1800e4da0  mov     edi, edx
0x1800e4da2  mov     rbx, rcx
0x1800e4da5  mov     r14, [rbp+1400h+arg_28]
0x1800e4dac  xor     edx, edx; Val
0x1800e4dae  mov     r8d, 98h; Size
0x1800e4db4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800e4db9  call    memset_0
0x1800e4dbe  nop
0x1800e4dbf  xor     r12d, r12d
0x1800e4dc2  mov     [rbp+1400h+OutputString], r12w
0x1800e4dca  mov     [rbp+1400h+var_1440], r12b
0x1800e4dce  mov     rdx, [rbp+1400h+arg_30]; int
0x1800e4dd5  mov     ecx, [rdx]; this
0x1800e4dd7  mov     [rsp+1500h+var_14D8], ecx
0x1800e4ddb  mov     eax, [rdx+4]
0x1800e4dde  mov     [rsp+1500h+var_14D4], eax
0x1800e4de2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800e4de7  mov     r15d, eax
0x1800e4dea  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800e4df2  mov     ecx, r12d
0x1800e4df5  lea     eax, [r12+8]
0x1800e4dfa  cmp     dword ptr [rdx+8], 1
0x1800e4dfe  cmovz   ecx, eax
0x1800e4e01  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800e4e05  lea     ecx, [rax-7]
0x1800e4e08  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800e4e10  inc     ecx
0x1800e4e12  mov     [rsp+1500h+var_14D0], ecx
0x1800e4e16  mov     rcx, [rbp+1400h+arg_38]
0x1800e4e1d  test    rcx, rcx
0x1800e4e20  jz      short loc_1800E4E2D
0x1800e4e22  cmp     [rcx], r12w
0x1800e4e26  mov     [rsp+1500h+var_14C8], rcx
0x1800e4e2b  jnz     short loc_1800E4E32
0x1800e4e2d  mov     [rsp+1500h+var_14C8], r12
0x1800e4e32  call    cs:__imp_GetCurrentThreadId
0x1800e4e39  nop     dword ptr [rax+rax+00h]
0x1800e4e3e  mov     [rsp+1500h+var_14C0], eax
0x1800e4e42  mov     [rsp+1500h+var_14A8], rsi
0x1800e4e47  mov     [rsp+1500h+var_14A0], edi
0x1800e4e4b  mov     [rsp+1500h+var_149C], r15d
0x1800e4e50  mov     [rsp+1500h+var_14B8], r12
0x1800e4e55  mov     [rsp+1500h+var_14B0], r12
0x1800e4e5a  mov     [rbp+1400h+var_1458], r14
0x1800e4e5e  mov     [rbp+1400h+var_1450], rbx
0x1800e4e62  mov     [rsp+1500h+var_1498], r12
0x1800e4e67  xorps   xmm0, xmm0
0x1800e4e6a  xor     eax, eax
0x1800e4e6c  movups  [rbp+1400h+var_1478], xmm0
0x1800e4e70  mov     [rbp+1400h+var_1468], rax
0x1800e4e74  xorps   xmm1, xmm1
0x1800e4e77  movups  [rsp+1500h+var_1490], xmm1
0x1800e4e7c  mov     [rbp+1400h+var_1480], rax
0x1800e4e80  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800e4e87  test    rax, rax
0x1800e4e8a  jz      short loc_1800E4E97
0x1800e4e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4e91  mov     [rbp+1400h+var_1460], rax
0x1800e4e95  jmp     short loc_1800E4E9B
0x1800e4e97  mov     [rbp+1400h+var_1460], r12
0x1800e4e9b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800e4ea2  test    rax, rax
0x1800e4ea5  jz      short loc_1800E4EB1
0x1800e4ea7  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4eb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800e4eb8  test    rax, rax
0x1800e4ebb  jz      short loc_1800E4ED1
0x1800e4ebd  mov     r8d, 400h
0x1800e4ec3  lea     rdx, [rbp+1400h+var_1440]
0x1800e4ec7  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4ed1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e4ed8  test    rax, rax
0x1800e4edb  jz      short loc_1800E4EE7
0x1800e4edd  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4ee7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e4eee  test    rax, rax
0x1800e4ef1  jz      short loc_1800E4F04
0x1800e4ef3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800e4ef8  jnz     short loc_1800E4F04
0x1800e4efa  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4f04  cmp     [rsp+1500h+var_14D8], r12d
0x1800e4f09  jge     loc_1800E501F
0x1800e4f0f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800e4f16  jnz     short loc_1800E4F3D
0x1800e4f18  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800e4f1f  test    rax, rax
0x1800e4f22  jz      short loc_1800E4F2D
0x1800e4f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4f29  test    al, al
0x1800e4f2b  jmp     short loc_1800E4F3B
0x1800e4f2d  call    cs:__imp_IsDebuggerPresent
0x1800e4f34  nop     dword ptr [rax+rax+00h]
0x1800e4f39  test    eax, eax
0x1800e4f3b  jz      short loc_1800E4F44
0x1800e4f3d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800e4f42  jz      short loc_1800E4F6A
0x1800e4f44  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e4f4b  test    rax, rax
0x1800e4f4e  jz      short loc_1800E4FC9
0x1800e4f50  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800e4f57  jnz     short loc_1800E4FC9
0x1800e4f59  xor     r8d, r8d
0x1800e4f5c  xor     edx, edx
0x1800e4f5e  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4f68  jmp     short loc_1800E4FC9
0x1800e4f6a  mov     ebx, 800h
0x1800e4f6f  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e4f76  test    rax, rax
0x1800e4f79  jz      short loc_1800E4F98
0x1800e4f7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800e4f82  jnz     short loc_1800E4F98
0x1800e4f84  mov     r8d, ebx
0x1800e4f87  lea     rdx, [rbp+1400h+OutputString]
0x1800e4f8e  lea     rcx, [rsp+1500h+var_14E0]
0x1800e4f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4f98  cmp     [rbp+1400h+OutputString], r12w
0x1800e4fa0  jnz     short loc_1800E4FB6
0x1800e4fa2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800e4fa7  mov     rdx, rbx; unsigned __int16 *
0x1800e4faa  lea     rcx, [rbp+1400h+OutputString]; this
0x1800e4fb1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800e4fb6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800e4fbd  call    cs:__imp_OutputDebugStringW
0x1800e4fc4  nop     dword ptr [rax+rax+00h]
0x1800e4fc9  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800e4fce  jnz     short loc_1800E4FD9
0x1800e4fd0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800e4fd7  jz      short loc_1800E4FEB
0x1800e4fd9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800e4fe0  test    rax, rax
0x1800e4fe3  jz      short loc_1800E4FEB
0x1800e4fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4fea  nop
0x1800e4feb  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800e4ff0  jnz     short loc_1800E5014
0x1800e4ff2  mov     rcx, [rbp+1400h+var_40]
0x1800e4ff9  xor     rcx, rsp; StackCookie
0x1800e4ffc  call    __security_check_cookie
0x1800e5001  add     rsp, 14D0h
0x1800e5008  pop     r15
0x1800e500a  pop     r14
0x1800e500c  pop     r12
0x1800e500e  pop     rdi
0x1800e500f  pop     rsi
0x1800e5010  pop     rbx
0x1800e5011  pop     rbp
0x1800e5012  retn
0x1800e5014  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800e5019  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800e501f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
