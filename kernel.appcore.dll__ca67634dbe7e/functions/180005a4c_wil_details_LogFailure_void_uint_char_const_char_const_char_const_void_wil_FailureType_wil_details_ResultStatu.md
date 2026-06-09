# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005a4c`
- end: `0x180005d40`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000595c`
- `0x1800092b0`
- `0x180009360`

## callees

- `0x180005610`
- `0x180005a4c`
- `0x180005d48`
- `0x1800091f4`
- `0x18000956c`
- `0x180009878`
- `0x180009894`
- `0x1800098b0`
- `0x1800099f0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b6f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c90`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c90`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005d02`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005d02`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180005a4c  mov     [rsp+arg_10], rbx
0x180005a51  mov     [rsp+arg_8], edx
0x180005a55  mov     [rsp+arg_0], rcx
0x180005a5a  push    rbp
0x180005a5b  push    rsi
0x180005a5c  push    rdi
0x180005a5d  push    r12
0x180005a5f  push    r13
0x180005a61  push    r14
0x180005a63  push    r15
0x180005a65  sub     rsp, 40h
0x180005a69  mov     r14, [rsp+78h+arg_38]
0x180005a71  xor     eax, eax
0x180005a73  mov     rbx, [rsp+78h+arg_78]
0x180005a7b  xor     ebp, ebp
0x180005a7d  mov     r15d, [rsp+78h+arg_30]
0x180005a85  mov     r10, rcx
0x180005a88  mov     rsi, [rsp+78h+lpOutputString]
0x180005a90  mov     r12, r9
0x180005a93  mov     r13, r8
0x180005a96  mov     ecx, r15d
0x180005a99  mov     [rsi], ax
0x180005a9c  mov     rax, [rsp+78h+arg_60]
0x180005aa4  mov     byte ptr [rax], 0
0x180005aa7  mov     edi, [r14]
0x180005aaa  mov     [rbx+8], edi
0x180005aad  mov     eax, [r14+4]
0x180005ab1  mov     [rbx+0Ch], eax
0x180005ab4  test    r15d, r15d
0x180005ab7  jz      short loc_180005B1F
0x180005ab9  sub     ecx, 1
0x180005abc  jz      short loc_180005B16
0x180005abe  sub     ecx, 1
0x180005ac1  jz      short loc_180005AD1
0x180005ac3  cmp     ecx, 1
0x180005ac6  jnz     short loc_180005B28
0x180005ac8  mov     ecx, edi; this
0x180005aca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005acf  jmp     short loc_180005B26
0x180005ad1  test    edi, edi
0x180005ad3  js      short loc_180005B0D
0x180005ad5  mov     rax, [rsp+78h+arg_28]
0x180005add  mov     edi, 8007029Ch
0x180005ae2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005ae6  mov     rcx, r10; int
0x180005ae9  mov     [rsp+78h+var_50], rax; __int64
0x180005aee  mov     rax, [rsp+78h+arg_20]
0x180005af6  mov     [rsp+78h+var_58], rax; __int64
0x180005afb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005b00  mov     ecx, edi; this
0x180005b02  mov     [rbx+8], edi
0x180005b05  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005b0a  mov     [rbx+0Ch], eax
0x180005b0d  mov     ecx, edi; this
0x180005b0f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005b14  jmp     short loc_180005B26
0x180005b16  mov     ecx, edi; this
0x180005b18  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005b1d  jmp     short loc_180005B26
0x180005b1f  mov     ecx, edi; this
0x180005b21  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005b26  mov     ebp, eax
0x180005b28  mov     eax, [rsp+78h+arg_70]
0x180005b2f  mov     [rbx+4], eax
0x180005b32  mov     [rbx], r15d
0x180005b35  cmp     dword ptr [r14+8], 1
0x180005b3a  jnz     short loc_180005B42
0x180005b3c  or      eax, 8
0x180005b3f  mov     [rbx+4], eax
0x180005b42  mov     eax, 1
0x180005b47  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b4f  inc     eax
0x180005b51  xor     edi, edi
0x180005b53  mov     [rbx+10h], eax
0x180005b56  mov     rax, [rsp+78h+arg_40]
0x180005b5e  test    rax, rax
0x180005b61  jz      short loc_180005B68
0x180005b63  cmp     [rax], di
0x180005b66  jnz     short loc_180005B6B
0x180005b68  mov     rax, rdi
0x180005b6b  mov     [rbx+18h], rax
0x180005b6f  call    cs:__imp_GetCurrentThreadId
0x180005b75  mov     [rbx+38h], r13
0x180005b79  xorps   xmm0, xmm0
0x180005b7c  mov     [rbx+20h], eax
0x180005b7f  mov     eax, [rsp+78h+arg_8]
0x180005b86  mov     [rbx+40h], eax
0x180005b89  mov     rax, [rsp+78h+arg_20]
0x180005b91  mov     [rbx+28h], rax
0x180005b95  mov     rax, [rsp+78h+arg_28]
0x180005b9d  mov     [rbx+88h], rax
0x180005ba4  mov     rax, [rsp+78h+arg_0]
0x180005bac  mov     [rbx+90h], rax
0x180005bb3  xor     eax, eax
0x180005bb5  mov     [rbx+44h], ebp
0x180005bb8  mov     [rbx+30h], r12
0x180005bbc  mov     [rbx+48h], rdi
0x180005bc0  movups  xmmword ptr [rbx+68h], xmm0
0x180005bc4  mov     [rbx+78h], rax
0x180005bc8  movups  xmmword ptr [rbx+50h], xmm0
0x180005bcc  mov     [rbx+60h], rax
0x180005bd0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005bd7  test    rax, rax
0x180005bda  jz      short loc_180005BE3
0x180005bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be1  jmp     short loc_180005BE6
0x180005be3  mov     rax, rdi
0x180005be6  mov     [rbx+80h], rax
0x180005bed  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005bf4  test    rax, rax
0x180005bf7  jz      short loc_180005C01
0x180005bf9  mov     rcx, rbx
0x180005bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c01  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005c08  test    rax, rax
0x180005c0b  jz      short loc_180005C23
0x180005c0d  mov     rdx, [rsp+78h+arg_60]
0x180005c15  mov     r8d, 400h
0x180005c1b  mov     rcx, rbx
0x180005c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c23  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c2a  test    rax, rax
0x180005c2d  jz      short loc_180005C37
0x180005c2f  mov     rcx, rbx
0x180005c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c37  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c3e  test    rax, rax
0x180005c41  jz      short loc_180005C51
0x180005c43  test    byte ptr [rbx+4], 2
0x180005c47  jnz     short loc_180005C51
0x180005c49  mov     rcx, rbx
0x180005c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c51  cmp     [rbx+8], edi
0x180005c54  jl      short loc_180005C72
0x180005c56  cmp     r15d, 3
0x180005c5a  jz      short loc_180005C62
0x180005c5c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005c62  mov     ecx, 8000FFFFh; this
0x180005c67  mov     [rbx+8], ecx
0x180005c6a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005c6f  mov     [rbx+0Ch], eax
0x180005c72  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005c79  jnz     short loc_180005C9A
0x180005c7b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005c82  test    rax, rax
0x180005c85  jz      short loc_180005C90
0x180005c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c8c  test    al, al
0x180005c8e  jmp     short loc_180005C98
0x180005c90  call    cs:__imp_IsDebuggerPresent
0x180005c96  test    eax, eax
0x180005c98  jz      short loc_180005CA0
0x180005c9a  test    byte ptr [rbx+4], 2
0x180005c9e  jz      short loc_180005CC4
0x180005ca0  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ca7  test    rax, rax
0x180005caa  jz      short loc_180005D08
0x180005cac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005cb3  jnz     short loc_180005D08
0x180005cb5  xor     r8d, r8d
0x180005cb8  xor     edx, edx
0x180005cba  mov     rcx, rbx
0x180005cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc2  jmp     short loc_180005D08
0x180005cc4  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ccb  mov     ebp, 800h
0x180005cd0  test    rax, rax
0x180005cd3  jz      short loc_180005CEC
0x180005cd5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005cdc  jnz     short loc_180005CEC
0x180005cde  mov     r8d, ebp
0x180005ce1  mov     rdx, rsi
0x180005ce4  mov     rcx, rbx
0x180005ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cec  cmp     [rsi], di
0x180005cef  jnz     short loc_180005CFF
0x180005cf1  mov     r8, rbx; unsigned __int64
0x180005cf4  mov     rdx, rbp; unsigned __int16 *
0x180005cf7  mov     rcx, rsi; this
0x180005cfa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005cff  mov     rcx, rsi; lpOutputString
0x180005d02  call    cs:__imp_OutputDebugStringW
0x180005d08  test    byte ptr [rbx+4], 4
0x180005d0c  jnz     short loc_180005D17
0x180005d0e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005d15  jz      short loc_180005D28
0x180005d17  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005d1e  test    rax, rax
0x180005d21  jz      short loc_180005D28
0x180005d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d28  mov     rbx, [rsp+78h+arg_10]
0x180005d30  add     rsp, 40h
0x180005d34  pop     r15
0x180005d36  pop     r14
0x180005d38  pop     r13
0x180005d3a  pop     r12
0x180005d3c  pop     rdi
0x180005d3d  pop     rsi
0x180005d3e  pop     rbp
0x180005d3f  retn
```
