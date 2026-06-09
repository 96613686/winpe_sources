# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006e10`
- end: `0x180007109`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003f94`

## callees

- `0x1800039a0`
- `0x1800063c4`
- `0x180006b64`
- `0x180006e10`
- `0x180007ac0`
- `0x180007ae0`
- `0x180007c0c`
- `0x180007c28`
- `0x18000a3bc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f33`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007052`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007052`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
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
0x180006e10  mov     [rsp+arg_10], rbx
0x180006e15  mov     [rsp+arg_8], edx
0x180006e19  mov     [rsp+arg_0], rcx
0x180006e1e  push    rbp
0x180006e1f  push    rsi
0x180006e20  push    rdi
0x180006e21  push    r12
0x180006e23  push    r13
0x180006e25  push    r14
0x180006e27  push    r15
0x180006e29  sub     rsp, 40h
0x180006e2d  mov     r12, r9
0x180006e30  mov     r13, r8
0x180006e33  mov     r10, rcx
0x180006e36  xor     eax, eax
0x180006e38  mov     rsi, [rsp+78h+lpOutputString]
0x180006e40  mov     [rsi], ax
0x180006e43  mov     rax, [rsp+78h+arg_60]
0x180006e4b  mov     byte ptr [rax], 0
0x180006e4e  mov     r14, [rsp+78h+arg_38]
0x180006e56  mov     edi, [r14]
0x180006e59  mov     rbx, [rsp+78h+arg_78]
0x180006e61  mov     [rbx+8], edi
0x180006e64  mov     eax, [r14+4]
0x180006e68  mov     [rbx+0Ch], eax
0x180006e6b  xor     ebp, ebp
0x180006e6d  mov     r15d, [rsp+78h+arg_30]
0x180006e75  mov     ecx, r15d
0x180006e78  test    r15d, r15d
0x180006e7b  jz      short loc_180006EE3
0x180006e7d  sub     ecx, 1
0x180006e80  jz      short loc_180006EDA
0x180006e82  sub     ecx, 1
0x180006e85  jz      short loc_180006E95
0x180006e87  cmp     ecx, 1
0x180006e8a  jnz     short loc_180006EEC
0x180006e8c  mov     ecx, edi; this
0x180006e8e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006e93  jmp     short loc_180006EEA
0x180006e95  test    edi, edi
0x180006e97  js      short loc_180006ED1
0x180006e99  mov     edi, 8007029Ch
0x180006e9e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006ea2  mov     rax, [rsp+78h+arg_28]
0x180006eaa  mov     [rsp+78h+var_50], rax; __int64
0x180006eaf  mov     rax, [rsp+78h+arg_20]
0x180006eb7  mov     [rsp+78h+var_58], rax; __int64
0x180006ebc  mov     rcx, r10; int
0x180006ebf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006ec4  mov     [rbx+8], edi
0x180006ec7  mov     ecx, edi; this
0x180006ec9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006ece  mov     [rbx+0Ch], eax
0x180006ed1  mov     ecx, edi; this
0x180006ed3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006ed8  jmp     short loc_180006EEA
0x180006eda  mov     ecx, edi; this
0x180006edc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ee1  jmp     short loc_180006EEA
0x180006ee3  mov     ecx, edi; this
0x180006ee5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006eea  mov     ebp, eax
0x180006eec  mov     [rbx], r15d
0x180006eef  mov     eax, [rsp+78h+arg_70]
0x180006ef6  mov     [rbx+4], eax
0x180006ef9  cmp     dword ptr [r14+8], 1
0x180006efe  jnz     short loc_180006F06
0x180006f00  or      eax, 8
0x180006f03  mov     [rbx+4], eax
0x180006f06  mov     eax, 1
0x180006f0b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006f13  inc     eax
0x180006f15  mov     [rbx+10h], eax
0x180006f18  mov     rax, [rsp+78h+arg_40]
0x180006f20  xor     edi, edi
0x180006f22  test    rax, rax
0x180006f25  jz      short loc_180006F2C
0x180006f27  cmp     [rax], di
0x180006f2a  jnz     short loc_180006F2F
0x180006f2c  mov     rax, rdi
0x180006f2f  mov     [rbx+18h], rax
0x180006f33  call    cs:__imp_GetCurrentThreadId
0x180006f39  mov     [rbx+20h], eax
0x180006f3c  mov     [rbx+38h], r13
0x180006f40  mov     eax, [rsp+78h+arg_8]
0x180006f47  mov     [rbx+40h], eax
0x180006f4a  mov     [rbx+44h], ebp
0x180006f4d  mov     rax, [rsp+78h+arg_20]
0x180006f55  mov     [rbx+28h], rax
0x180006f59  mov     [rbx+30h], r12
0x180006f5d  mov     rax, [rsp+78h+arg_28]
0x180006f65  mov     [rbx+88h], rax
0x180006f6c  mov     rax, [rsp+78h+arg_0]
0x180006f74  mov     [rbx+90h], rax
0x180006f7b  mov     [rbx+48h], rdi
0x180006f7f  xorps   xmm0, xmm0
0x180006f82  xor     eax, eax
0x180006f84  movups  xmmword ptr [rbx+68h], xmm0
0x180006f88  mov     [rbx+78h], rax
0x180006f8c  movups  xmmword ptr [rbx+50h], xmm0
0x180006f90  mov     [rbx+60h], rax
0x180006f94  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006f9b  test    rax, rax
0x180006f9e  jz      short loc_180006FA7
0x180006fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa5  jmp     short loc_180006FAA
0x180006fa7  mov     rax, rdi
0x180006faa  mov     [rbx+80h], rax
0x180006fb1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006fb8  test    rax, rax
0x180006fbb  jz      short loc_180006FC5
0x180006fbd  mov     rcx, rbx
0x180006fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006fcc  test    rax, rax
0x180006fcf  jz      short loc_180006FE7
0x180006fd1  mov     r8d, 400h
0x180006fd7  mov     rdx, [rsp+78h+arg_60]
0x180006fdf  mov     rcx, rbx
0x180006fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006fee  test    rax, rax
0x180006ff1  jz      short loc_180006FFB
0x180006ff3  mov     rcx, rbx
0x180006ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007002  test    rax, rax
0x180007005  jz      short loc_180007015
0x180007007  test    byte ptr [rbx+4], 2
0x18000700b  jnz     short loc_180007015
0x18000700d  mov     rcx, rbx
0x180007010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007015  cmp     [rbx+8], edi
0x180007018  jl      short loc_180007034
0x18000701a  cmp     r15d, 3
0x18000701e  jnz     loc_180007103
0x180007024  mov     ecx, 8000FFFFh; this
0x180007029  mov     [rbx+8], ecx
0x18000702c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007031  mov     [rbx+0Ch], eax
0x180007034  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000703b  jnz     short loc_18000705C
0x18000703d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007044  test    rax, rax
0x180007047  jz      short loc_180007052
0x180007049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000704e  test    al, al
0x180007050  jmp     short loc_18000705A
0x180007052  call    cs:__imp_IsDebuggerPresent
0x180007058  test    eax, eax
0x18000705a  jz      short loc_180007062
0x18000705c  test    byte ptr [rbx+4], 2
0x180007060  jz      short loc_180007086
0x180007062  mov     rax, cs:g_pfnResultLoggingCallback
0x180007069  test    rax, rax
0x18000706c  jz      short loc_1800070CA
0x18000706e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007075  jnz     short loc_1800070CA
0x180007077  xor     r8d, r8d
0x18000707a  xor     edx, edx
0x18000707c  mov     rcx, rbx
0x18000707f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007084  jmp     short loc_1800070CA
0x180007086  mov     ebp, 800h
0x18000708b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007092  test    rax, rax
0x180007095  jz      short loc_1800070AE
0x180007097  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000709e  jnz     short loc_1800070AE
0x1800070a0  mov     r8d, ebp
0x1800070a3  mov     rdx, rsi
0x1800070a6  mov     rcx, rbx
0x1800070a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ae  cmp     [rsi], di
0x1800070b1  jnz     short loc_1800070C1
0x1800070b3  mov     r8, rbx; unsigned __int64
0x1800070b6  mov     rdx, rbp; wchar_t *
0x1800070b9  mov     rcx, rsi; this
0x1800070bc  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800070c1  mov     rcx, rsi; lpOutputString
0x1800070c4  call    cs:__imp_OutputDebugStringW
0x1800070ca  test    byte ptr [rbx+4], 4
0x1800070ce  jnz     short loc_1800070D9
0x1800070d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800070d7  jz      short loc_1800070EB
0x1800070d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800070e0  test    rax, rax
0x1800070e3  jz      short loc_1800070EB
0x1800070e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ea  nop
0x1800070eb  mov     rbx, [rsp+78h+arg_10]
0x1800070f3  add     rsp, 40h
0x1800070f7  pop     r15
0x1800070f9  pop     r14
0x1800070fb  pop     r13
0x1800070fd  pop     r12
0x1800070ff  pop     rdi
0x180007100  pop     rsi
0x180007101  pop     rbp
0x180007102  retn
0x180007103  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
