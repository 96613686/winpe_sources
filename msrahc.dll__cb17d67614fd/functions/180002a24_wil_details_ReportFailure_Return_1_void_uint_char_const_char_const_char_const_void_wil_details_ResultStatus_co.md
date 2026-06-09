# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002a24`
- end: `0x180002cb1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800026e4`

## callees

- `0x180002a24`
- `0x1800042f4`
- `0x180005bf0`
- `0x1800073e8`
- `0x1800076d8`
- `0x18001a5a2`
- `0x18001a5e0`
- `0x18001a6a0`
- `0x18001c010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180002bc6`
- `KERNEL32!IsDebuggerPresent` at `0x180002bc6`
- `KERNEL32!OutputDebugStringW` at `0x180002c50`
- `KERNEL32!OutputDebugStringW` at `0x180002c50`
- `KERNEL32!GetCurrentThreadId` at `0x180002ad2`
- `KERNEL32!GetCurrentThreadId` at `0x180002ad2`

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
0x180002a24  push    rbp
0x180002a26  push    rbx
0x180002a27  push    rsi
0x180002a28  push    rdi
0x180002a29  push    r12
0x180002a2b  push    r14
0x180002a2d  push    r15
0x180002a2f  lea     rbp, [rsp-13D0h]
0x180002a37  mov     eax, 14D0h
0x180002a3c  call    _alloca_probe
0x180002a41  sub     rsp, rax
0x180002a44  mov     rax, cs:__security_cookie
0x180002a4b  xor     rax, rsp
0x180002a4e  mov     [rbp+1400h+var_40], rax
0x180002a55  mov     r14, r8
0x180002a58  mov     esi, edx
0x180002a5a  mov     r15, rcx
0x180002a5d  mov     rdi, [rbp+1400h+arg_28]
0x180002a64  xor     edx, edx; Val
0x180002a66  mov     r8d, 98h; Size
0x180002a6c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002a71  call    memset_0
0x180002a76  nop
0x180002a77  xor     r12d, r12d
0x180002a7a  mov     [rbp+1400h+OutputString], r12w
0x180002a82  mov     [rbp+1400h+var_1440], r12b
0x180002a86  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180002a8d  mov     ecx, [rdx]; this
0x180002a8f  mov     [rsp+1500h+var_14D8], ecx
0x180002a93  mov     eax, [rdx+4]
0x180002a96  mov     [rsp+1500h+var_14D4], eax
0x180002a9a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002a9f  mov     ebx, eax
0x180002aa1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002aa9  mov     ecx, r12d
0x180002aac  lea     eax, [r12+8]
0x180002ab1  cmp     dword ptr [rdx+8], 1
0x180002ab5  cmovz   ecx, eax
0x180002ab8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002abc  lea     ecx, [rax-7]
0x180002abf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002ac7  inc     ecx
0x180002ac9  mov     [rsp+1500h+var_14D0], ecx
0x180002acd  mov     [rsp+1500h+var_14C8], r12
0x180002ad2  call    cs:__imp_GetCurrentThreadId
0x180002ad8  mov     [rsp+1500h+var_14C0], eax
0x180002adc  mov     [rsp+1500h+var_14A8], r14
0x180002ae1  mov     [rsp+1500h+var_14A0], esi
0x180002ae5  mov     [rsp+1500h+var_149C], ebx
0x180002ae9  mov     [rsp+1500h+var_14B8], r12
0x180002aee  mov     [rsp+1500h+var_14B0], r12
0x180002af3  mov     [rbp+1400h+var_1458], rdi
0x180002af7  mov     [rbp+1400h+var_1450], r15
0x180002afb  mov     [rsp+1500h+var_1498], r12
0x180002b00  xorps   xmm0, xmm0
0x180002b03  xor     eax, eax
0x180002b05  movups  [rbp+1400h+var_1478], xmm0
0x180002b09  mov     [rbp+1400h+var_1468], rax
0x180002b0d  xorps   xmm1, xmm1
0x180002b10  movups  [rsp+1500h+var_1490], xmm1
0x180002b15  mov     [rbp+1400h+var_1480], rax
0x180002b19  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002b20  test    rax, rax
0x180002b23  jz      short loc_180002B30
0x180002b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b2a  mov     [rbp+1400h+var_1460], rax
0x180002b2e  jmp     short loc_180002B34
0x180002b30  mov     [rbp+1400h+var_1460], r12
0x180002b34  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002b3b  test    rax, rax
0x180002b3e  jz      short loc_180002B4A
0x180002b40  lea     rcx, [rsp+1500h+var_14E0]
0x180002b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b4a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002b51  test    rax, rax
0x180002b54  jz      short loc_180002B6A
0x180002b56  mov     r8d, 400h
0x180002b5c  lea     rdx, [rbp+1400h+var_1440]
0x180002b60  lea     rcx, [rsp+1500h+var_14E0]
0x180002b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b6a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b71  test    rax, rax
0x180002b74  jz      short loc_180002B80
0x180002b76  lea     rcx, [rsp+1500h+var_14E0]
0x180002b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b80  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b87  test    rax, rax
0x180002b8a  jz      short loc_180002B9D
0x180002b8c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002b91  jnz     short loc_180002B9D
0x180002b93  lea     rcx, [rsp+1500h+var_14E0]
0x180002b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b9d  cmp     [rsp+1500h+var_14D8], r12d
0x180002ba2  jge     loc_180002CAB
0x180002ba8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002baf  jnz     short loc_180002BD0
0x180002bb1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002bb8  test    rax, rax
0x180002bbb  jz      short loc_180002BC6
0x180002bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc2  test    al, al
0x180002bc4  jmp     short loc_180002BCE
0x180002bc6  call    cs:__imp_IsDebuggerPresent
0x180002bcc  test    eax, eax
0x180002bce  jz      short loc_180002BD7
0x180002bd0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002bd5  jz      short loc_180002BFD
0x180002bd7  mov     rax, cs:g_pfnResultLoggingCallback
0x180002bde  test    rax, rax
0x180002be1  jz      short loc_180002C56
0x180002be3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002bea  jnz     short loc_180002C56
0x180002bec  xor     r8d, r8d
0x180002bef  xor     edx, edx
0x180002bf1  lea     rcx, [rsp+1500h+var_14E0]
0x180002bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bfb  jmp     short loc_180002C56
0x180002bfd  mov     ebx, 800h
0x180002c02  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c09  test    rax, rax
0x180002c0c  jz      short loc_180002C2B
0x180002c0e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002c15  jnz     short loc_180002C2B
0x180002c17  mov     r8d, ebx
0x180002c1a  lea     rdx, [rbp+1400h+OutputString]
0x180002c21  lea     rcx, [rsp+1500h+var_14E0]
0x180002c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2b  cmp     [rbp+1400h+OutputString], r12w
0x180002c33  jnz     short loc_180002C49
0x180002c35  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002c3a  mov     rdx, rbx; unsigned __int16 *
0x180002c3d  lea     rcx, [rbp+1400h+OutputString]; this
0x180002c44  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002c49  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002c50  call    cs:__imp_OutputDebugStringW
0x180002c56  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002c5b  jnz     short loc_180002C66
0x180002c5d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002c64  jz      short loc_180002C78
0x180002c66  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002c6d  test    rax, rax
0x180002c70  jz      short loc_180002C78
0x180002c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c77  nop
0x180002c78  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002c7d  jnz     short loc_180002CA0
0x180002c7f  mov     rcx, [rbp+1400h+var_40]
0x180002c86  xor     rcx, rsp; StackCookie
0x180002c89  call    __security_check_cookie
0x180002c8e  add     rsp, 14D0h
0x180002c95  pop     r15
0x180002c97  pop     r14
0x180002c99  pop     r12
0x180002c9b  pop     rdi
0x180002c9c  pop     rsi
0x180002c9d  pop     rbx
0x180002c9e  pop     rbp
0x180002c9f  retn
0x180002ca0  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002ca5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002cab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
