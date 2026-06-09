# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005a08`
- end: `0x180005d01`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800040fc`

## callees

- `0x180003b08`
- `0x1800050a4`
- `0x180005844`
- `0x180005a08`
- `0x180005f94`
- `0x180005fb0`
- `0x180005fc4`
- `0x180005fe0`
- `0x18000714c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b2b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005cbc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005cbc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c4a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c4a`

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
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x180005a08  mov     [rsp+arg_10], rbx
0x180005a0d  mov     [rsp+arg_8], edx
0x180005a11  mov     [rsp+arg_0], rcx
0x180005a16  push    rbp
0x180005a17  push    rsi
0x180005a18  push    rdi
0x180005a19  push    r12
0x180005a1b  push    r13
0x180005a1d  push    r14
0x180005a1f  push    r15
0x180005a21  sub     rsp, 40h
0x180005a25  mov     r12, r9
0x180005a28  mov     r13, r8
0x180005a2b  mov     r10, rcx
0x180005a2e  xor     eax, eax
0x180005a30  mov     rsi, [rsp+78h+lpOutputString]
0x180005a38  mov     [rsi], ax
0x180005a3b  mov     rax, [rsp+78h+arg_60]
0x180005a43  mov     byte ptr [rax], 0
0x180005a46  mov     r14, [rsp+78h+arg_38]
0x180005a4e  mov     edi, [r14]
0x180005a51  mov     rbx, [rsp+78h+arg_78]
0x180005a59  mov     [rbx+8], edi
0x180005a5c  mov     eax, [r14+4]
0x180005a60  mov     [rbx+0Ch], eax
0x180005a63  xor     ebp, ebp
0x180005a65  mov     r15d, [rsp+78h+arg_30]
0x180005a6d  mov     ecx, r15d
0x180005a70  test    r15d, r15d
0x180005a73  jz      short loc_180005ADB
0x180005a75  sub     ecx, 1
0x180005a78  jz      short loc_180005AD2
0x180005a7a  sub     ecx, 1
0x180005a7d  jz      short loc_180005A8D
0x180005a7f  cmp     ecx, 1
0x180005a82  jnz     short loc_180005AE4
0x180005a84  mov     ecx, edi; this
0x180005a86  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005a8b  jmp     short loc_180005AE2
0x180005a8d  test    edi, edi
0x180005a8f  js      short loc_180005AC9
0x180005a91  mov     edi, 8007029Ch
0x180005a96  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005a9a  mov     rax, [rsp+78h+arg_28]
0x180005aa2  mov     [rsp+78h+var_50], rax; __int64
0x180005aa7  mov     rax, [rsp+78h+arg_20]
0x180005aaf  mov     [rsp+78h+var_58], rax; __int64
0x180005ab4  mov     rcx, r10; int
0x180005ab7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005abc  mov     [rbx+8], edi
0x180005abf  mov     ecx, edi; this
0x180005ac1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005ac6  mov     [rbx+0Ch], eax
0x180005ac9  mov     ecx, edi; this
0x180005acb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005ad0  jmp     short loc_180005AE2
0x180005ad2  mov     ecx, edi; this
0x180005ad4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005ad9  jmp     short loc_180005AE2
0x180005adb  mov     ecx, edi; this
0x180005add  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005ae2  mov     ebp, eax
0x180005ae4  mov     [rbx], r15d
0x180005ae7  mov     eax, [rsp+78h+arg_70]
0x180005aee  mov     [rbx+4], eax
0x180005af1  cmp     dword ptr [r14+8], 1
0x180005af6  jnz     short loc_180005AFE
0x180005af8  or      eax, 8
0x180005afb  mov     [rbx+4], eax
0x180005afe  mov     eax, 1
0x180005b03  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b0b  inc     eax
0x180005b0d  mov     [rbx+10h], eax
0x180005b10  mov     rax, [rsp+78h+arg_40]
0x180005b18  xor     edi, edi
0x180005b1a  test    rax, rax
0x180005b1d  jz      short loc_180005B24
0x180005b1f  cmp     [rax], di
0x180005b22  jnz     short loc_180005B27
0x180005b24  mov     rax, rdi
0x180005b27  mov     [rbx+18h], rax
0x180005b2b  call    cs:__imp_GetCurrentThreadId
0x180005b31  mov     [rbx+20h], eax
0x180005b34  mov     [rbx+38h], r13
0x180005b38  mov     eax, [rsp+78h+arg_8]
0x180005b3f  mov     [rbx+40h], eax
0x180005b42  mov     [rbx+44h], ebp
0x180005b45  mov     rax, [rsp+78h+arg_20]
0x180005b4d  mov     [rbx+28h], rax
0x180005b51  mov     [rbx+30h], r12
0x180005b55  mov     rax, [rsp+78h+arg_28]
0x180005b5d  mov     [rbx+88h], rax
0x180005b64  mov     rax, [rsp+78h+arg_0]
0x180005b6c  mov     [rbx+90h], rax
0x180005b73  mov     [rbx+48h], rdi
0x180005b77  xorps   xmm0, xmm0
0x180005b7a  xor     eax, eax
0x180005b7c  movups  xmmword ptr [rbx+68h], xmm0
0x180005b80  mov     [rbx+78h], rax
0x180005b84  movups  xmmword ptr [rbx+50h], xmm0
0x180005b88  mov     [rbx+60h], rax
0x180005b8c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005b93  test    rax, rax
0x180005b96  jz      short loc_180005B9F
0x180005b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b9d  jmp     short loc_180005BA2
0x180005b9f  mov     rax, rdi
0x180005ba2  mov     [rbx+80h], rax
0x180005ba9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005bb0  test    rax, rax
0x180005bb3  jz      short loc_180005BBD
0x180005bb5  mov     rcx, rbx
0x180005bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bbd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005bc4  test    rax, rax
0x180005bc7  jz      short loc_180005BDF
0x180005bc9  mov     r8d, 400h
0x180005bcf  mov     rdx, [rsp+78h+arg_60]
0x180005bd7  mov     rcx, rbx
0x180005bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bdf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005be6  test    rax, rax
0x180005be9  jz      short loc_180005BF3
0x180005beb  mov     rcx, rbx
0x180005bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005bfa  test    rax, rax
0x180005bfd  jz      short loc_180005C0D
0x180005bff  test    byte ptr [rbx+4], 2
0x180005c03  jnz     short loc_180005C0D
0x180005c05  mov     rcx, rbx
0x180005c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c0d  cmp     [rbx+8], edi
0x180005c10  jl      short loc_180005C2C
0x180005c12  cmp     r15d, 3
0x180005c16  jnz     loc_180005CFB
0x180005c1c  mov     ecx, 8000FFFFh; this
0x180005c21  mov     [rbx+8], ecx
0x180005c24  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005c29  mov     [rbx+0Ch], eax
0x180005c2c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005c33  jnz     short loc_180005C54
0x180005c35  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005c3c  test    rax, rax
0x180005c3f  jz      short loc_180005C4A
0x180005c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c46  test    al, al
0x180005c48  jmp     short loc_180005C52
0x180005c4a  call    cs:__imp_IsDebuggerPresent
0x180005c50  test    eax, eax
0x180005c52  jz      short loc_180005C5A
0x180005c54  test    byte ptr [rbx+4], 2
0x180005c58  jz      short loc_180005C7E
0x180005c5a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c61  test    rax, rax
0x180005c64  jz      short loc_180005CC2
0x180005c66  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005c6d  jnz     short loc_180005CC2
0x180005c6f  xor     r8d, r8d
0x180005c72  xor     edx, edx
0x180005c74  mov     rcx, rbx
0x180005c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c7c  jmp     short loc_180005CC2
0x180005c7e  mov     ebp, 800h
0x180005c83  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c8a  test    rax, rax
0x180005c8d  jz      short loc_180005CA6
0x180005c8f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005c96  jnz     short loc_180005CA6
0x180005c98  mov     r8d, ebp
0x180005c9b  mov     rdx, rsi
0x180005c9e  mov     rcx, rbx
0x180005ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ca6  cmp     [rsi], di
0x180005ca9  jnz     short loc_180005CB9
0x180005cab  mov     r8, rbx; unsigned __int64
0x180005cae  mov     rdx, rbp; unsigned __int16 *
0x180005cb1  mov     rcx, rsi; this
0x180005cb4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005cb9  mov     rcx, rsi; lpOutputString
0x180005cbc  call    cs:__imp_OutputDebugStringW
0x180005cc2  test    byte ptr [rbx+4], 4
0x180005cc6  jnz     short loc_180005CD1
0x180005cc8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005ccf  jz      short loc_180005CE3
0x180005cd1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005cd8  test    rax, rax
0x180005cdb  jz      short loc_180005CE3
0x180005cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ce2  nop
0x180005ce3  mov     rbx, [rsp+78h+arg_10]
0x180005ceb  add     rsp, 40h
0x180005cef  pop     r15
0x180005cf1  pop     r14
0x180005cf3  pop     r13
0x180005cf5  pop     r12
0x180005cf7  pop     rdi
0x180005cf8  pop     rsi
0x180005cf9  pop     rbp
0x180005cfa  retn
0x180005cfb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
