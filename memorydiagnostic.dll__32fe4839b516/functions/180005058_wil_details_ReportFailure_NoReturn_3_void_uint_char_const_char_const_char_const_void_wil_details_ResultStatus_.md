# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005058`
- end: `0x1800052e3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004818`

## callees

- `0x180003374`
- `0x180005058`
- `0x18000d474`
- `0x18000dd50`
- `0x18000fb70`
- `0x180015bec`
- `0x180021f90`
- `0x180024010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000521a`
- `KERNEL32!IsDebuggerPresent` at `0x18000521a`
- `KERNEL32!OutputDebugStringW` at `0x1800052aa`
- `KERNEL32!OutputDebugStringW` at `0x1800052aa`
- `KERNEL32!GetCurrentThreadId` at `0x180005111`
- `KERNEL32!GetCurrentThreadId` at `0x180005111`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180005058  mov     [rsp-8+arg_18], rbx
0x18000505d  push    rbp
0x18000505e  push    rsi
0x18000505f  push    rdi
0x180005060  push    r12
0x180005062  push    r13
0x180005064  push    r14
0x180005066  push    r15
0x180005068  lea     rbp, [rsp-13C0h]
0x180005070  mov     eax, 14C0h
0x180005075  call    _alloca_probe
0x18000507a  sub     rsp, rax
0x18000507d  mov     r14, r8
0x180005080  mov     esi, edx
0x180005082  mov     rdi, rcx
0x180005085  mov     r15, [rbp+13F0h+arg_28]
0x18000508c  xor     edx, edx; Val
0x18000508e  mov     r8d, 98h; Size
0x180005094  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005099  call    memset_0
0x18000509e  nop
0x18000509f  xor     r13d, r13d
0x1800050a2  mov     [rbp+13F0h+OutputString], r13w
0x1800050aa  mov     [rbp+13F0h+var_1430], r13b
0x1800050ae  mov     rbx, [rbp+13F0h+arg_30]
0x1800050b5  mov     ecx, [rbx]; this
0x1800050b7  mov     [rsp+14F0h+var_14C8], ecx
0x1800050bb  mov     eax, [rbx+4]
0x1800050be  mov     [rsp+14F0h+var_14C4], eax
0x1800050c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800050c7  mov     r12d, eax
0x1800050ca  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800050d2  mov     ecx, r13d
0x1800050d5  lea     eax, [r13+8]
0x1800050d9  cmp     dword ptr [rbx+8], 1
0x1800050dd  cmovz   ecx, eax
0x1800050e0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800050e4  lea     ecx, [rax-7]
0x1800050e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x1800050ef  inc     ecx
0x1800050f1  mov     [rsp+14F0h+var_14C0], ecx
0x1800050f5  mov     rcx, [rbp+13F0h+arg_38]
0x1800050fc  test    rcx, rcx
0x1800050ff  jz      short loc_18000510C
0x180005101  cmp     [rcx], r13w
0x180005105  mov     [rsp+14F0h+var_14B8], rcx
0x18000510a  jnz     short loc_180005111
0x18000510c  mov     [rsp+14F0h+var_14B8], r13
0x180005111  call    cs:__imp_GetCurrentThreadId
0x180005118  nop     dword ptr [rax+rax+00h]
0x18000511d  mov     [rsp+14F0h+var_14B0], eax
0x180005121  mov     [rsp+14F0h+var_1498], r14
0x180005126  mov     [rsp+14F0h+var_1490], esi
0x18000512a  mov     [rsp+14F0h+var_148C], r12d
0x18000512f  mov     [rsp+14F0h+var_14A8], r13
0x180005134  mov     [rsp+14F0h+var_14A0], r13
0x180005139  mov     [rbp+13F0h+var_1448], r15
0x18000513d  mov     [rbp+13F0h+var_1440], rdi
0x180005141  mov     [rsp+14F0h+var_1488], r13
0x180005146  xorps   xmm0, xmm0
0x180005149  xor     eax, eax
0x18000514b  movups  [rbp+13F0h+var_1468], xmm0
0x18000514f  mov     [rbp+13F0h+var_1458], rax
0x180005153  xorps   xmm1, xmm1
0x180005156  movups  [rsp+14F0h+var_1480], xmm1
0x18000515b  mov     [rbp+13F0h+var_1470], rax
0x18000515f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005166  test    rax, rax
0x180005169  jz      short loc_180005176
0x18000516b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005170  mov     [rbp+13F0h+var_1450], rax
0x180005174  jmp     short loc_18000517A
0x180005176  mov     [rbp+13F0h+var_1450], r13
0x18000517a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005181  test    rax, rax
0x180005184  jz      short loc_180005190
0x180005186  lea     rcx, [rsp+14F0h+var_14D0]
0x18000518b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005190  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005197  test    rax, rax
0x18000519a  jz      short loc_1800051B0
0x18000519c  mov     r8d, 400h
0x1800051a2  lea     rdx, [rbp+13F0h+var_1430]
0x1800051a6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800051ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800051b7  test    rax, rax
0x1800051ba  jz      short loc_1800051C6
0x1800051bc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800051c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051c6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800051cd  test    rax, rax
0x1800051d0  jz      short loc_1800051E3
0x1800051d2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800051d7  jnz     short loc_1800051E3
0x1800051d9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800051de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e3  cmp     [rsp+14F0h+var_14C8], r13d
0x1800051e8  jl      short loc_1800051FC
0x1800051ea  mov     ecx, 8000FFFFh; this
0x1800051ef  mov     [rsp+14F0h+var_14C8], ecx
0x1800051f3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800051f8  mov     [rsp+14F0h+var_14C4], eax
0x1800051fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005203  jnz     short loc_18000522A
0x180005205  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000520c  test    rax, rax
0x18000520f  jz      short loc_18000521A
0x180005211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005216  test    al, al
0x180005218  jmp     short loc_180005228
0x18000521a  call    cs:__imp_IsDebuggerPresent
0x180005221  nop     dword ptr [rax+rax+00h]
0x180005226  test    eax, eax
0x180005228  jz      short loc_180005231
0x18000522a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000522f  jz      short loc_180005257
0x180005231  mov     rax, cs:g_pfnResultLoggingCallback
0x180005238  test    rax, rax
0x18000523b  jz      short loc_1800052B6
0x18000523d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180005244  jnz     short loc_1800052B6
0x180005246  xor     r8d, r8d
0x180005249  xor     edx, edx
0x18000524b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005255  jmp     short loc_1800052B6
0x180005257  mov     ebx, 800h
0x18000525c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005263  test    rax, rax
0x180005266  jz      short loc_180005285
0x180005268  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000526f  jnz     short loc_180005285
0x180005271  mov     r8d, ebx
0x180005274  lea     rdx, [rbp+13F0h+OutputString]
0x18000527b  lea     rcx, [rsp+14F0h+var_14D0]
0x180005280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005285  cmp     [rbp+13F0h+OutputString], r13w
0x18000528d  jnz     short loc_1800052A3
0x18000528f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005294  mov     rdx, rbx; unsigned __int16 *
0x180005297  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000529e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800052a3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800052aa  call    cs:__imp_OutputDebugStringW
0x1800052b1  nop     dword ptr [rax+rax+00h]
0x1800052b6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800052bb  jnz     short loc_1800052C6
0x1800052bd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800052c4  jz      short loc_1800052D8
0x1800052c6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800052cd  test    rax, rax
0x1800052d0  jz      short loc_1800052D8
0x1800052d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d7  nop
0x1800052d8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800052dd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
