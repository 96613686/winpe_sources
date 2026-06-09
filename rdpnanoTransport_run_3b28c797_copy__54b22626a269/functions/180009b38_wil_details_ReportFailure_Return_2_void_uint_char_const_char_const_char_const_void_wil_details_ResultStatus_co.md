# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180009b38`
- end: `0x180009e30`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180008fa0`

## callees

- `0x1800094d0`
- `0x180009b38`
- `0x18000ae24`
- `0x18000b708`
- `0x18000bbbc`
- `0x18000cac4`
- `0x18000cba4`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180009d31`
- `KERNEL32!IsDebuggerPresent` at `0x180009d31`
- `KERNEL32!OutputDebugStringW` at `0x180009da5`
- `KERNEL32!OutputDebugStringW` at `0x180009da5`
- `KERNEL32!GetCurrentThreadId` at `0x180009c37`
- `KERNEL32!GetCurrentThreadId` at `0x180009c37`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  bool v18; // zf
  const struct wil::FailureInfo *v19; // rdx
  wil::details::in1diag3 *v20; // rcx
  const struct wil::FailureInfo *v21; // r9
  int IsDebuggerPresent; // ecx
  wil::details *v23; // [rsp+30h] [rbp-D0h]
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+54h] [rbp-ACh]
  int v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v28; // [rsp+60h] [rbp-A0h]
  _WORD *v29; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+94h] [rbp-6Ch]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int128 v37; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  __int128 v39; // [rsp+B8h] [rbp-48h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  __int64 v43; // [rsp+E0h] [rbp-20h]
  char v44[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v14 = 0;
  OutputString[0] = 0;
  v44[0] = 0;
  v15 = *a7;
  v26 = v15;
  v27 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v23) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v23, 0);
    v26 = -2147024228;
    v27 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v24 = 2;
  v25 = a10;
  if ( a7[2] == 1 )
    v25 = a10 | 8;
  v28 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v29 = a8, v18) )
    v29 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v33 = a3;
  v34 = a2;
  v35 = v17;
  v31 = a5;
  v32 = a4;
  v42 = a6;
  v43 = a1;
  v36 = 0;
  v39 = 0;
  v40 = 0;
  v37 = 0;
  v38 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v24);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v24, v44, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v24);
  if ( wil::details::g_pfnOriginateCallback && (v25 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v24);
  if ( v26 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && wil::g_fResultOutputDebugString
    && (v25 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v24, OutputString, 2048, v21);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v24, v21);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v24, 0, 0, v21);
  }
  if ( ((v25 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v25 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v24, v19);
}

```

## disassembly

```asm
0x180009b38  push    rbp
0x180009b3a  push    rbx
0x180009b3b  push    rsi
0x180009b3c  push    rdi
0x180009b3d  push    r12
0x180009b3f  push    r13
0x180009b41  push    r14
0x180009b43  push    r15
0x180009b45  lea     rbp, [rsp-1408h]
0x180009b4d  mov     eax, 1508h
0x180009b52  call    _alloca_probe
0x180009b57  sub     rsp, rax
0x180009b5a  mov     rax, cs:__security_cookie
0x180009b61  xor     rax, rsp
0x180009b64  mov     [rbp+1440h+var_50], rax
0x180009b6b  mov     r12, r9
0x180009b6e  mov     r15, r8
0x180009b71  mov     r14d, edx
0x180009b74  mov     rsi, rcx
0x180009b77  mov     r13, [rbp+1440h+arg_20]
0x180009b7e  mov     rcx, [rbp+1440h+arg_28]
0x180009b85  mov     [rsp+1540h+var_1500], rcx
0x180009b8a  xor     edx, edx
0x180009b8c  mov     [rbp+1440h+OutputString], dx
0x180009b93  mov     [rbp+1440h+var_1450], dl
0x180009b96  mov     rdi, [rbp+1440h+arg_30]
0x180009b9d  mov     ebx, [rdi]
0x180009b9f  mov     [rsp+1540h+var_14E8], ebx
0x180009ba3  mov     eax, [rdi+4]
0x180009ba6  mov     [rsp+1540h+var_14E4], eax
0x180009baa  test    ebx, ebx
0x180009bac  js      short loc_180009BDF
0x180009bae  mov     [rsp+1540h+var_1508], edx; int
0x180009bb2  mov     ebx, 8007029Ch
0x180009bb7  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180009bbb  mov     [rsp+1540h+var_1518], rcx; __int64
0x180009bc0  mov     [rsp+1540h+var_1520], r13; __int64
0x180009bc5  mov     edx, r14d; int
0x180009bc8  mov     rcx, rsi; int
0x180009bcb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009bd0  mov     [rsp+1540h+var_14E8], ebx
0x180009bd4  mov     ecx, ebx; this
0x180009bd6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009bdb  mov     [rsp+1540h+var_14E4], eax
0x180009bdf  mov     ecx, ebx; this
0x180009be1  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009be6  mov     ebx, eax
0x180009be8  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180009bf0  mov     ecx, [rbp+1440h+arg_48]
0x180009bf6  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180009bfa  cmp     dword ptr [rdi+8], 1
0x180009bfe  jnz     short loc_180009C07
0x180009c00  or      ecx, 8
0x180009c03  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180009c07  mov     ecx, 1
0x180009c0c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009c14  inc     ecx
0x180009c16  mov     [rsp+1540h+var_14E0], ecx
0x180009c1a  mov     rax, [rbp+1440h+arg_38]
0x180009c21  xor     edi, edi
0x180009c23  test    rax, rax
0x180009c26  jz      short loc_180009C32
0x180009c28  cmp     [rax], di
0x180009c2b  mov     [rsp+1540h+var_14D8], rax
0x180009c30  jnz     short loc_180009C37
0x180009c32  mov     [rsp+1540h+var_14D8], rdi
0x180009c37  call    cs:__imp_GetCurrentThreadId
0x180009c3d  mov     [rsp+1540h+var_14D0], eax
0x180009c41  mov     [rbp+1440h+var_14B8], r15
0x180009c45  mov     [rbp+1440h+var_14B0], r14d
0x180009c49  mov     [rbp+1440h+var_14AC], ebx
0x180009c4c  mov     [rsp+1540h+var_14C8], r13
0x180009c51  mov     [rbp+1440h+var_14C0], r12
0x180009c55  mov     rax, [rsp+1540h+var_1500]
0x180009c5a  mov     [rbp+1440h+var_1468], rax
0x180009c5e  mov     [rbp+1440h+var_1460], rsi
0x180009c62  mov     [rbp+1440h+var_14A8], rdi
0x180009c66  xorps   xmm0, xmm0
0x180009c69  xor     eax, eax
0x180009c6b  movups  [rbp+1440h+var_1488], xmm0
0x180009c6f  mov     [rbp+1440h+var_1478], rax
0x180009c73  xorps   xmm1, xmm1
0x180009c76  movups  [rbp+1440h+var_14A0], xmm1
0x180009c7a  mov     [rbp+1440h+var_1490], rax
0x180009c7e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009c85  test    rax, rax
0x180009c88  jz      short loc_180009C96
0x180009c8a  call    cs:__guard_dispatch_icall_fptr
0x180009c90  mov     [rbp+1440h+var_1470], rax
0x180009c94  jmp     short loc_180009C9A
0x180009c96  mov     [rbp+1440h+var_1470], rdi
0x180009c9a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009ca1  test    rax, rax
0x180009ca4  jz      short loc_180009CB1
0x180009ca6  lea     rcx, [rsp+1540h+var_14F0]
0x180009cab  call    cs:__guard_dispatch_icall_fptr
0x180009cb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009cb8  test    rax, rax
0x180009cbb  jz      short loc_180009CD2
0x180009cbd  mov     r8d, 400h
0x180009cc3  lea     rdx, [rbp+1440h+var_1450]
0x180009cc7  lea     rcx, [rsp+1540h+var_14F0]
0x180009ccc  call    cs:__guard_dispatch_icall_fptr
0x180009cd2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009cd9  test    rax, rax
0x180009cdc  jz      short loc_180009CE9
0x180009cde  lea     rcx, [rsp+1540h+var_14F0]
0x180009ce3  call    cs:__guard_dispatch_icall_fptr
0x180009ce9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009cf0  test    rax, rax
0x180009cf3  jz      short loc_180009D07
0x180009cf5  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180009cfa  jnz     short loc_180009D07
0x180009cfc  lea     rcx, [rsp+1540h+var_14F0]
0x180009d01  call    cs:__guard_dispatch_icall_fptr
0x180009d07  cmp     [rsp+1540h+var_14E8], edi
0x180009d0b  jge     loc_180009E2A
0x180009d11  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009d18  jnz     short loc_180009D42
0x180009d1a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009d21  test    rax, rax
0x180009d24  jz      short loc_180009D31
0x180009d26  call    cs:__guard_dispatch_icall_fptr
0x180009d2c  movzx   ecx, al
0x180009d2f  jmp     short loc_180009D3E
0x180009d31  call    cs:__imp_IsDebuggerPresent
0x180009d37  mov     ecx, edi
0x180009d39  test    eax, eax
0x180009d3b  setnz   cl
0x180009d3e  test    ecx, ecx
0x180009d40  jz      short loc_180009DAD
0x180009d42  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, dil; bool wil::g_fResultOutputDebugString
0x180009d49  jz      short loc_180009DAD
0x180009d4b  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180009d50  jnz     short loc_180009DAD
0x180009d52  mov     ebx, 800h
0x180009d57  mov     rax, cs:g_pfnResultLoggingCallback
0x180009d5e  test    rax, rax
0x180009d61  jz      short loc_180009D81
0x180009d63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009d6a  jnz     short loc_180009D81
0x180009d6c  mov     r8d, ebx
0x180009d6f  lea     rdx, [rbp+1440h+OutputString]
0x180009d76  lea     rcx, [rsp+1540h+var_14F0]
0x180009d7b  call    cs:__guard_dispatch_icall_fptr
0x180009d81  cmp     [rbp+1440h+OutputString], di
0x180009d88  jnz     short loc_180009D9E
0x180009d8a  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180009d8f  mov     rdx, rbx; wchar_t *
0x180009d92  lea     rcx, [rbp+1440h+OutputString]; this
0x180009d99  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180009d9e  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180009da5  call    cs:__imp_OutputDebugStringW
0x180009dab  jmp     short loc_180009DD2
0x180009dad  mov     rax, cs:g_pfnResultLoggingCallback
0x180009db4  test    rax, rax
0x180009db7  jz      short loc_180009DD2
0x180009db9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009dc0  jnz     short loc_180009DD2
0x180009dc2  xor     r8d, r8d
0x180009dc5  xor     edx, edx
0x180009dc7  lea     rcx, [rsp+1540h+var_14F0]
0x180009dcc  call    cs:__guard_dispatch_icall_fptr
0x180009dd2  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180009dd7  jnz     short loc_180009DE2
0x180009dd9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009de0  jz      short loc_180009DF5
0x180009de2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009de9  test    rax, rax
0x180009dec  jz      short loc_180009DF5
0x180009dee  call    cs:__guard_dispatch_icall_fptr
0x180009df4  nop
0x180009df5  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180009dfa  jnz     short loc_180009E1F
0x180009dfc  mov     rcx, [rbp+1440h+var_50]
0x180009e03  xor     rcx, rsp; StackCookie
0x180009e06  call    __security_check_cookie
0x180009e0b  add     rsp, 1508h
0x180009e12  pop     r15
0x180009e14  pop     r14
0x180009e16  pop     r13
0x180009e18  pop     r12
0x180009e1a  pop     rdi
0x180009e1b  pop     rsi
0x180009e1c  pop     rbx
0x180009e1d  pop     rbp
0x180009e1e  retn
0x180009e1f  lea     rcx, [rsp+1540h+var_14F0]; this
0x180009e24  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009e2a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
