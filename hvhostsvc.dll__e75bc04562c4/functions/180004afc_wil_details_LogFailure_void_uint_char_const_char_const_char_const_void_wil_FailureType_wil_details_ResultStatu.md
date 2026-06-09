# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004afc`
- end: `0x180004df5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800030cc`
- `0x180003410`
- `0x180006810`

## callees

- `0x18000300c`
- `0x180003fb4`
- `0x180004764`
- `0x180004afc`
- `0x1800051ec`
- `0x180005210`
- `0x180005224`
- `0x180005240`
- `0x180005fc4`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c1f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d3e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d3e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004db0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004db0`

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
0x180004afc  mov     [rsp+arg_10], rbx
0x180004b01  mov     [rsp+arg_8], edx
0x180004b05  mov     [rsp+arg_0], rcx
0x180004b0a  push    rbp
0x180004b0b  push    rsi
0x180004b0c  push    rdi
0x180004b0d  push    r12
0x180004b0f  push    r13
0x180004b11  push    r14
0x180004b13  push    r15
0x180004b15  sub     rsp, 40h
0x180004b19  mov     r12, r9
0x180004b1c  mov     r13, r8
0x180004b1f  mov     r10, rcx
0x180004b22  xor     eax, eax
0x180004b24  mov     rsi, [rsp+78h+lpOutputString]
0x180004b2c  mov     [rsi], ax
0x180004b2f  mov     rax, [rsp+78h+arg_60]
0x180004b37  mov     byte ptr [rax], 0
0x180004b3a  mov     r14, [rsp+78h+arg_38]
0x180004b42  mov     edi, [r14]
0x180004b45  mov     rbx, [rsp+78h+arg_78]
0x180004b4d  mov     [rbx+8], edi
0x180004b50  mov     eax, [r14+4]
0x180004b54  mov     [rbx+0Ch], eax
0x180004b57  xor     ebp, ebp
0x180004b59  mov     r15d, [rsp+78h+arg_30]
0x180004b61  mov     ecx, r15d
0x180004b64  test    r15d, r15d
0x180004b67  jz      short loc_180004BCF
0x180004b69  sub     ecx, 1
0x180004b6c  jz      short loc_180004BC6
0x180004b6e  sub     ecx, 1
0x180004b71  jz      short loc_180004B81
0x180004b73  cmp     ecx, 1
0x180004b76  jnz     short loc_180004BD8
0x180004b78  mov     ecx, edi; this
0x180004b7a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004b7f  jmp     short loc_180004BD6
0x180004b81  test    edi, edi
0x180004b83  js      short loc_180004BBD
0x180004b85  mov     edi, 8007029Ch
0x180004b8a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004b8e  mov     rax, [rsp+78h+arg_28]
0x180004b96  mov     [rsp+78h+var_50], rax; __int64
0x180004b9b  mov     rax, [rsp+78h+arg_20]
0x180004ba3  mov     [rsp+78h+var_58], rax; __int64
0x180004ba8  mov     rcx, r10; int
0x180004bab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004bb0  mov     [rbx+8], edi
0x180004bb3  mov     ecx, edi; this
0x180004bb5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004bba  mov     [rbx+0Ch], eax
0x180004bbd  mov     ecx, edi; this
0x180004bbf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004bc4  jmp     short loc_180004BD6
0x180004bc6  mov     ecx, edi; this
0x180004bc8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004bcd  jmp     short loc_180004BD6
0x180004bcf  mov     ecx, edi; this
0x180004bd1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004bd6  mov     ebp, eax
0x180004bd8  mov     [rbx], r15d
0x180004bdb  mov     eax, [rsp+78h+arg_70]
0x180004be2  mov     [rbx+4], eax
0x180004be5  cmp     dword ptr [r14+8], 1
0x180004bea  jnz     short loc_180004BF2
0x180004bec  or      eax, 8
0x180004bef  mov     [rbx+4], eax
0x180004bf2  mov     eax, 1
0x180004bf7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004bff  inc     eax
0x180004c01  mov     [rbx+10h], eax
0x180004c04  mov     rax, [rsp+78h+arg_40]
0x180004c0c  xor     edi, edi
0x180004c0e  test    rax, rax
0x180004c11  jz      short loc_180004C18
0x180004c13  cmp     [rax], di
0x180004c16  jnz     short loc_180004C1B
0x180004c18  mov     rax, rdi
0x180004c1b  mov     [rbx+18h], rax
0x180004c1f  call    cs:__imp_GetCurrentThreadId
0x180004c25  mov     [rbx+20h], eax
0x180004c28  mov     [rbx+38h], r13
0x180004c2c  mov     eax, [rsp+78h+arg_8]
0x180004c33  mov     [rbx+40h], eax
0x180004c36  mov     [rbx+44h], ebp
0x180004c39  mov     rax, [rsp+78h+arg_20]
0x180004c41  mov     [rbx+28h], rax
0x180004c45  mov     [rbx+30h], r12
0x180004c49  mov     rax, [rsp+78h+arg_28]
0x180004c51  mov     [rbx+88h], rax
0x180004c58  mov     rax, [rsp+78h+arg_0]
0x180004c60  mov     [rbx+90h], rax
0x180004c67  mov     [rbx+48h], rdi
0x180004c6b  xorps   xmm0, xmm0
0x180004c6e  xor     eax, eax
0x180004c70  movups  xmmword ptr [rbx+68h], xmm0
0x180004c74  mov     [rbx+78h], rax
0x180004c78  movups  xmmword ptr [rbx+50h], xmm0
0x180004c7c  mov     [rbx+60h], rax
0x180004c80  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004c87  test    rax, rax
0x180004c8a  jz      short loc_180004C93
0x180004c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c91  jmp     short loc_180004C96
0x180004c93  mov     rax, rdi
0x180004c96  mov     [rbx+80h], rax
0x180004c9d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004ca4  test    rax, rax
0x180004ca7  jz      short loc_180004CB1
0x180004ca9  mov     rcx, rbx
0x180004cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004cb8  test    rax, rax
0x180004cbb  jz      short loc_180004CD3
0x180004cbd  mov     r8d, 400h
0x180004cc3  mov     rdx, [rsp+78h+arg_60]
0x180004ccb  mov     rcx, rbx
0x180004cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cd3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004cda  test    rax, rax
0x180004cdd  jz      short loc_180004CE7
0x180004cdf  mov     rcx, rbx
0x180004ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004cee  test    rax, rax
0x180004cf1  jz      short loc_180004D01
0x180004cf3  test    byte ptr [rbx+4], 2
0x180004cf7  jnz     short loc_180004D01
0x180004cf9  mov     rcx, rbx
0x180004cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d01  cmp     [rbx+8], edi
0x180004d04  jl      short loc_180004D20
0x180004d06  cmp     r15d, 3
0x180004d0a  jnz     loc_180004DEF
0x180004d10  mov     ecx, 8000FFFFh; this
0x180004d15  mov     [rbx+8], ecx
0x180004d18  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004d1d  mov     [rbx+0Ch], eax
0x180004d20  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004d27  jnz     short loc_180004D48
0x180004d29  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004d30  test    rax, rax
0x180004d33  jz      short loc_180004D3E
0x180004d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3a  test    al, al
0x180004d3c  jmp     short loc_180004D46
0x180004d3e  call    cs:__imp_IsDebuggerPresent
0x180004d44  test    eax, eax
0x180004d46  jz      short loc_180004D4E
0x180004d48  test    byte ptr [rbx+4], 2
0x180004d4c  jz      short loc_180004D72
0x180004d4e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d55  test    rax, rax
0x180004d58  jz      short loc_180004DB6
0x180004d5a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004d61  jnz     short loc_180004DB6
0x180004d63  xor     r8d, r8d
0x180004d66  xor     edx, edx
0x180004d68  mov     rcx, rbx
0x180004d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d70  jmp     short loc_180004DB6
0x180004d72  mov     ebp, 800h
0x180004d77  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d7e  test    rax, rax
0x180004d81  jz      short loc_180004D9A
0x180004d83  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004d8a  jnz     short loc_180004D9A
0x180004d8c  mov     r8d, ebp
0x180004d8f  mov     rdx, rsi
0x180004d92  mov     rcx, rbx
0x180004d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d9a  cmp     [rsi], di
0x180004d9d  jnz     short loc_180004DAD
0x180004d9f  mov     r8, rbx; unsigned __int64
0x180004da2  mov     rdx, rbp; unsigned __int16 *
0x180004da5  mov     rcx, rsi; this
0x180004da8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004dad  mov     rcx, rsi; lpOutputString
0x180004db0  call    cs:__imp_OutputDebugStringW
0x180004db6  test    byte ptr [rbx+4], 4
0x180004dba  jnz     short loc_180004DC5
0x180004dbc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004dc3  jz      short loc_180004DD7
0x180004dc5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004dcc  test    rax, rax
0x180004dcf  jz      short loc_180004DD7
0x180004dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd6  nop
0x180004dd7  mov     rbx, [rsp+78h+arg_10]
0x180004ddf  add     rsp, 40h
0x180004de3  pop     r15
0x180004de5  pop     r14
0x180004de7  pop     r13
0x180004de9  pop     r12
0x180004deb  pop     rdi
0x180004dec  pop     rsi
0x180004ded  pop     rbp
0x180004dee  retn
0x180004def  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
