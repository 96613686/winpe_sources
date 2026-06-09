# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400128c8`
- end: `0x140012b5c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400123a8`

## callees

- `0x1400128c8`
- `0x140014574`
- `0x140015a24`
- `0x140017510`
- `0x1400176cc`
- `0x14001830e`
- `0x140018350`
- `0x1400183e0`
- `0x140019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140012a6d`
- `KERNEL32!IsDebuggerPresent` at `0x140012a6d`
- `KERNEL32!OutputDebugStringW` at `0x140012af7`
- `KERNEL32!OutputDebugStringW` at `0x140012af7`
- `KERNEL32!GetCurrentThreadId` at `0x140012972`
- `KERNEL32!GetCurrentThreadId` at `0x140012972`

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
0x1400128c8  mov     [rsp-8+arg_10], rbx
0x1400128cd  push    rbp
0x1400128ce  push    rsi
0x1400128cf  push    rdi
0x1400128d0  push    r14
0x1400128d2  push    r15
0x1400128d4  lea     rbp, [rsp-13D0h]
0x1400128dc  mov     eax, 14D0h
0x1400128e1  call    _alloca_probe
0x1400128e6  sub     rsp, rax
0x1400128e9  mov     rax, cs:__security_cookie
0x1400128f0  xor     rax, rsp
0x1400128f3  mov     [rbp+13F0h+var_30], rax
0x1400128fa  mov     rdi, [rbp+13F0h+arg_28]
0x140012901  mov     esi, edx
0x140012903  mov     r14, rcx
0x140012906  xor     edx, edx; Val
0x140012908  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14001290d  mov     r8d, 98h; Size
0x140012913  call    memset_0
0x140012918  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14001291f  xor     r15d, r15d
0x140012922  mov     [rbp+13F0h+OutputString], r15w
0x14001292a  mov     [rbp+13F0h+var_1430], r15b
0x14001292e  mov     ecx, [rdx]; this
0x140012930  mov     eax, [rdx+4]
0x140012933  mov     [rsp+14F0h+var_14C8], ecx
0x140012937  mov     [rsp+14F0h+var_14C4], eax
0x14001293b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140012940  cmp     dword ptr [rdx+8], 1
0x140012944  mov     ebx, eax
0x140012946  lea     eax, [r15+8]
0x14001294a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140012952  mov     ecx, r15d
0x140012955  cmovz   ecx, eax
0x140012958  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14001295c  lea     ecx, [rax-7]
0x14001295f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140012967  inc     ecx
0x140012969  mov     [rsp+14F0h+var_14B8], r15
0x14001296e  mov     [rsp+14F0h+var_14C0], ecx
0x140012972  call    cs:__imp_GetCurrentThreadId
0x140012978  xorps   xmm0, xmm0
0x14001297b  mov     [rsp+14F0h+var_1490], esi
0x14001297f  mov     [rsp+14F0h+var_14B0], eax
0x140012983  xorps   xmm1, xmm1
0x140012986  lea     rax, aWil; "wil"
0x14001298d  mov     [rsp+14F0h+var_148C], ebx
0x140012991  mov     [rsp+14F0h+var_1498], rax
0x140012996  xor     eax, eax
0x140012998  mov     [rbp+13F0h+var_1458], rax
0x14001299c  mov     [rbp+13F0h+var_1470], rax
0x1400129a0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400129a7  mov     [rsp+14F0h+var_14A8], r15
0x1400129ac  mov     [rsp+14F0h+var_14A0], r15
0x1400129b1  mov     [rbp+13F0h+var_1448], rdi
0x1400129b5  mov     [rbp+13F0h+var_1440], r14
0x1400129b9  mov     [rsp+14F0h+var_1488], r15
0x1400129be  movups  [rbp+13F0h+var_1468], xmm0
0x1400129c2  movups  [rsp+14F0h+var_1480], xmm1
0x1400129c7  test    rax, rax
0x1400129ca  jz      short loc_1400129D7
0x1400129cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129d1  mov     [rbp+13F0h+var_1450], rax
0x1400129d5  jmp     short loc_1400129DB
0x1400129d7  mov     [rbp+13F0h+var_1450], r15
0x1400129db  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400129e2  test    rax, rax
0x1400129e5  jz      short loc_1400129F1
0x1400129e7  lea     rcx, [rsp+14F0h+var_14D0]
0x1400129ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400129f8  test    rax, rax
0x1400129fb  jz      short loc_140012A11
0x1400129fd  mov     r8d, 400h
0x140012a03  lea     rdx, [rbp+13F0h+var_1430]
0x140012a07  lea     rcx, [rsp+14F0h+var_14D0]
0x140012a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a11  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140012a18  test    rax, rax
0x140012a1b  jz      short loc_140012A27
0x140012a1d  lea     rcx, [rsp+14F0h+var_14D0]
0x140012a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a27  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140012a2e  test    rax, rax
0x140012a31  jz      short loc_140012A44
0x140012a33  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140012a38  jnz     short loc_140012A44
0x140012a3a  lea     rcx, [rsp+14F0h+var_14D0]
0x140012a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a44  cmp     [rsp+14F0h+var_14C8], r15d
0x140012a49  jge     loc_140012B4B
0x140012a4f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140012a56  jnz     short loc_140012A77
0x140012a58  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140012a5f  test    rax, rax
0x140012a62  jz      short loc_140012A6D
0x140012a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a69  test    al, al
0x140012a6b  jmp     short loc_140012A75
0x140012a6d  call    cs:__imp_IsDebuggerPresent
0x140012a73  test    eax, eax
0x140012a75  jz      short loc_140012A7E
0x140012a77  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140012a7c  jz      short loc_140012AA4
0x140012a7e  mov     rax, cs:g_pfnResultLoggingCallback
0x140012a85  test    rax, rax
0x140012a88  jz      short loc_140012AFD
0x140012a8a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140012a91  jnz     short loc_140012AFD
0x140012a93  xor     r8d, r8d
0x140012a96  lea     rcx, [rsp+14F0h+var_14D0]
0x140012a9b  xor     edx, edx
0x140012a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012aa2  jmp     short loc_140012AFD
0x140012aa4  mov     rax, cs:g_pfnResultLoggingCallback
0x140012aab  mov     ebx, 800h
0x140012ab0  test    rax, rax
0x140012ab3  jz      short loc_140012AD2
0x140012ab5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140012abc  jnz     short loc_140012AD2
0x140012abe  mov     r8d, ebx
0x140012ac1  lea     rdx, [rbp+13F0h+OutputString]
0x140012ac8  lea     rcx, [rsp+14F0h+var_14D0]
0x140012acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ad2  cmp     [rbp+13F0h+OutputString], r15w
0x140012ada  jnz     short loc_140012AF0
0x140012adc  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140012ae1  mov     rdx, rbx; unsigned __int16 *
0x140012ae4  lea     rcx, [rbp+13F0h+OutputString]; this
0x140012aeb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140012af0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140012af7  call    cs:__imp_OutputDebugStringW
0x140012afd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140012b02  jnz     short loc_140012B0D
0x140012b04  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140012b0b  jz      short loc_140012B1E
0x140012b0d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140012b14  test    rax, rax
0x140012b17  jz      short loc_140012B1E
0x140012b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b1e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140012b23  jnz     short loc_140012B51
0x140012b25  mov     rcx, [rbp+13F0h+var_30]
0x140012b2c  xor     rcx, rsp; StackCookie
0x140012b2f  call    __security_check_cookie
0x140012b34  mov     rbx, [rsp+14F0h+arg_10]
0x140012b3c  add     rsp, 14D0h
0x140012b43  pop     r15
0x140012b45  pop     r14
0x140012b47  pop     rdi
0x140012b48  pop     rsi
0x140012b49  pop     rbp
0x140012b4a  retn
0x140012b4b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140012b51  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140012b56  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
