# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001702c`
- end: `0x1800172b9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180016ed8`

## callees

- `0x180002bf4`
- `0x180006d3c`
- `0x180007338`
- `0x180007494`
- `0x18001702c`
- `0x18002c802`
- `0x18002c840`
- `0x18002c900`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800170da`
- `KERNEL32!GetCurrentThreadId` at `0x1800170da`
- `KERNEL32!OutputDebugStringW` at `0x180017258`
- `KERNEL32!OutputDebugStringW` at `0x180017258`
- `KERNEL32!IsDebuggerPresent` at `0x1800171ce`
- `KERNEL32!IsDebuggerPresent` at `0x1800171ce`

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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
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
0x18001702c  push    rbp
0x18001702e  push    rbx
0x18001702f  push    rsi
0x180017030  push    rdi
0x180017031  push    r12
0x180017033  push    r14
0x180017035  push    r15
0x180017037  lea     rbp, [rsp-13D0h]
0x18001703f  mov     eax, 14D0h
0x180017044  call    _alloca_probe
0x180017049  sub     rsp, rax
0x18001704c  mov     rax, cs:__security_cookie
0x180017053  xor     rax, rsp
0x180017056  mov     [rbp+1400h+var_40], rax
0x18001705d  mov     r14, r8
0x180017060  mov     esi, edx
0x180017062  mov     r15, rcx
0x180017065  mov     rdi, [rbp+1400h+arg_28]
0x18001706c  xor     edx, edx; Val
0x18001706e  mov     r8d, 98h; Size
0x180017074  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180017079  call    memset_0
0x18001707e  nop
0x18001707f  xor     r12d, r12d
0x180017082  mov     [rbp+1400h+OutputString], r12w
0x18001708a  mov     [rbp+1400h+var_1440], r12b
0x18001708e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180017095  mov     ecx, [rdx]; this
0x180017097  mov     [rsp+1500h+var_14D8], ecx
0x18001709b  mov     eax, [rdx+4]
0x18001709e  mov     [rsp+1500h+var_14D4], eax
0x1800170a2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800170a7  mov     ebx, eax
0x1800170a9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800170b1  mov     ecx, r12d
0x1800170b4  lea     eax, [r12+8]
0x1800170b9  cmp     dword ptr [rdx+8], 1
0x1800170bd  cmovz   ecx, eax
0x1800170c0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800170c4  lea     ecx, [rax-7]
0x1800170c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800170cf  inc     ecx
0x1800170d1  mov     [rsp+1500h+var_14D0], ecx
0x1800170d5  mov     [rsp+1500h+var_14C8], r12
0x1800170da  call    cs:__imp_GetCurrentThreadId
0x1800170e0  mov     [rsp+1500h+var_14C0], eax
0x1800170e4  mov     [rsp+1500h+var_14A8], r14
0x1800170e9  mov     [rsp+1500h+var_14A0], esi
0x1800170ed  mov     [rsp+1500h+var_149C], ebx
0x1800170f1  mov     [rsp+1500h+var_14B8], r12
0x1800170f6  mov     [rsp+1500h+var_14B0], r12
0x1800170fb  mov     [rbp+1400h+var_1458], rdi
0x1800170ff  mov     [rbp+1400h+var_1450], r15
0x180017103  mov     [rsp+1500h+var_1498], r12
0x180017108  xorps   xmm0, xmm0
0x18001710b  xor     eax, eax
0x18001710d  movups  [rbp+1400h+var_1478], xmm0
0x180017111  mov     [rbp+1400h+var_1468], rax
0x180017115  xorps   xmm1, xmm1
0x180017118  movups  [rsp+1500h+var_1490], xmm1
0x18001711d  mov     [rbp+1400h+var_1480], rax
0x180017121  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180017128  test    rax, rax
0x18001712b  jz      short loc_180017138
0x18001712d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017132  mov     [rbp+1400h+var_1460], rax
0x180017136  jmp     short loc_18001713C
0x180017138  mov     [rbp+1400h+var_1460], r12
0x18001713c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180017143  test    rax, rax
0x180017146  jz      short loc_180017152
0x180017148  lea     rcx, [rsp+1500h+var_14E0]
0x18001714d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017152  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180017159  test    rax, rax
0x18001715c  jz      short loc_180017172
0x18001715e  mov     r8d, 400h
0x180017164  lea     rdx, [rbp+1400h+var_1440]
0x180017168  lea     rcx, [rsp+1500h+var_14E0]
0x18001716d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017172  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017179  test    rax, rax
0x18001717c  jz      short loc_180017188
0x18001717e  lea     rcx, [rsp+1500h+var_14E0]
0x180017183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017188  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001718f  test    rax, rax
0x180017192  jz      short loc_1800171A5
0x180017194  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180017199  jnz     short loc_1800171A5
0x18001719b  lea     rcx, [rsp+1500h+var_14E0]
0x1800171a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171a5  cmp     [rsp+1500h+var_14D8], r12d
0x1800171aa  jge     loc_1800172B3
0x1800171b0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800171b7  jnz     short loc_1800171D8
0x1800171b9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800171c0  test    rax, rax
0x1800171c3  jz      short loc_1800171CE
0x1800171c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ca  test    al, al
0x1800171cc  jmp     short loc_1800171D6
0x1800171ce  call    cs:__imp_IsDebuggerPresent
0x1800171d4  test    eax, eax
0x1800171d6  jz      short loc_1800171DF
0x1800171d8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800171dd  jz      short loc_180017205
0x1800171df  mov     rax, cs:g_pfnResultLoggingCallback
0x1800171e6  test    rax, rax
0x1800171e9  jz      short loc_18001725E
0x1800171eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800171f2  jnz     short loc_18001725E
0x1800171f4  xor     r8d, r8d
0x1800171f7  xor     edx, edx
0x1800171f9  lea     rcx, [rsp+1500h+var_14E0]
0x1800171fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017203  jmp     short loc_18001725E
0x180017205  mov     ebx, 800h
0x18001720a  mov     rax, cs:g_pfnResultLoggingCallback
0x180017211  test    rax, rax
0x180017214  jz      short loc_180017233
0x180017216  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001721d  jnz     short loc_180017233
0x18001721f  mov     r8d, ebx
0x180017222  lea     rdx, [rbp+1400h+OutputString]
0x180017229  lea     rcx, [rsp+1500h+var_14E0]
0x18001722e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017233  cmp     [rbp+1400h+OutputString], r12w
0x18001723b  jnz     short loc_180017251
0x18001723d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180017242  mov     rdx, rbx; unsigned __int16 *
0x180017245  lea     rcx, [rbp+1400h+OutputString]; pszDest
0x18001724c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180017251  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180017258  call    cs:__imp_OutputDebugStringW
0x18001725e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180017263  jnz     short loc_18001726E
0x180017265  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18001726c  jz      short loc_180017280
0x18001726e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180017275  test    rax, rax
0x180017278  jz      short loc_180017280
0x18001727a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001727f  nop
0x180017280  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180017285  jnz     short loc_1800172A8
0x180017287  mov     rcx, [rbp+1400h+var_40]
0x18001728e  xor     rcx, rsp; StackCookie
0x180017291  call    __security_check_cookie
0x180017296  add     rsp, 14D0h
0x18001729d  pop     r15
0x18001729f  pop     r14
0x1800172a1  pop     r12
0x1800172a3  pop     rdi
0x1800172a4  pop     rsi
0x1800172a5  pop     rbx
0x1800172a6  pop     rbp
0x1800172a7  retn
0x1800172a8  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800172ad  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800172b3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
