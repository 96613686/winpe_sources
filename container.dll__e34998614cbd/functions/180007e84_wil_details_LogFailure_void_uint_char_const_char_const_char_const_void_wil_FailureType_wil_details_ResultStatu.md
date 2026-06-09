# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007e84`
- end: `0x180008190`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800048d8`

## callees

- `0x180003f6c`
- `0x1800070f4`
- `0x180007a58`
- `0x180007e84`
- `0x180008df0`
- `0x180008e10`
- `0x180008f58`
- `0x180008f78`
- `0x18000bd9c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fa7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800080cc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800080cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008144`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008144`

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
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

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
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x180007e84  mov     [rsp+arg_10], rbx
0x180007e89  mov     [rsp+arg_8], edx
0x180007e8d  mov     [rsp+arg_0], rcx
0x180007e92  push    rbp
0x180007e93  push    rsi
0x180007e94  push    rdi
0x180007e95  push    r12
0x180007e97  push    r13
0x180007e99  push    r14
0x180007e9b  push    r15
0x180007e9d  sub     rsp, 40h
0x180007ea1  mov     r12, r9
0x180007ea4  mov     r13, r8
0x180007ea7  mov     r10, rcx
0x180007eaa  xor     eax, eax
0x180007eac  mov     rsi, [rsp+78h+lpOutputString]
0x180007eb4  mov     [rsi], ax
0x180007eb7  mov     rax, [rsp+78h+arg_60]
0x180007ebf  mov     byte ptr [rax], 0
0x180007ec2  mov     r14, [rsp+78h+arg_38]
0x180007eca  mov     edi, [r14]
0x180007ecd  mov     rbx, [rsp+78h+arg_78]
0x180007ed5  mov     [rbx+8], edi
0x180007ed8  mov     eax, [r14+4]
0x180007edc  mov     [rbx+0Ch], eax
0x180007edf  xor     ebp, ebp
0x180007ee1  mov     r15d, [rsp+78h+arg_30]
0x180007ee9  mov     ecx, r15d
0x180007eec  test    r15d, r15d
0x180007eef  jz      short loc_180007F57
0x180007ef1  sub     ecx, 1
0x180007ef4  jz      short loc_180007F4E
0x180007ef6  sub     ecx, 1
0x180007ef9  jz      short loc_180007F09
0x180007efb  cmp     ecx, 1
0x180007efe  jnz     short loc_180007F60
0x180007f00  mov     ecx, edi; this
0x180007f02  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007f07  jmp     short loc_180007F5E
0x180007f09  test    edi, edi
0x180007f0b  js      short loc_180007F45
0x180007f0d  mov     edi, 8007029Ch
0x180007f12  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007f16  mov     rax, [rsp+78h+arg_28]
0x180007f1e  mov     [rsp+78h+var_50], rax; __int64
0x180007f23  mov     rax, [rsp+78h+arg_20]
0x180007f2b  mov     [rsp+78h+var_58], rax; __int64
0x180007f30  mov     rcx, r10; int
0x180007f33  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007f38  mov     [rbx+8], edi
0x180007f3b  mov     ecx, edi; this
0x180007f3d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007f42  mov     [rbx+0Ch], eax
0x180007f45  mov     ecx, edi; this
0x180007f47  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007f4c  jmp     short loc_180007F5E
0x180007f4e  mov     ecx, edi; this
0x180007f50  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007f55  jmp     short loc_180007F5E
0x180007f57  mov     ecx, edi; this
0x180007f59  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007f5e  mov     ebp, eax
0x180007f60  mov     [rbx], r15d
0x180007f63  mov     eax, [rsp+78h+arg_70]
0x180007f6a  mov     [rbx+4], eax
0x180007f6d  cmp     dword ptr [r14+8], 1
0x180007f72  jnz     short loc_180007F7A
0x180007f74  or      eax, 8
0x180007f77  mov     [rbx+4], eax
0x180007f7a  mov     eax, 1
0x180007f7f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007f87  inc     eax
0x180007f89  mov     [rbx+10h], eax
0x180007f8c  mov     rax, [rsp+78h+arg_40]
0x180007f94  xor     edi, edi
0x180007f96  test    rax, rax
0x180007f99  jz      short loc_180007FA0
0x180007f9b  cmp     [rax], di
0x180007f9e  jnz     short loc_180007FA3
0x180007fa0  mov     rax, rdi
0x180007fa3  mov     [rbx+18h], rax
0x180007fa7  call    cs:__imp_GetCurrentThreadId
0x180007fae  nop     dword ptr [rax+rax+00h]
0x180007fb3  mov     [rbx+20h], eax
0x180007fb6  mov     [rbx+38h], r13
0x180007fba  mov     eax, [rsp+78h+arg_8]
0x180007fc1  mov     [rbx+40h], eax
0x180007fc4  mov     [rbx+44h], ebp
0x180007fc7  mov     rax, [rsp+78h+arg_20]
0x180007fcf  mov     [rbx+28h], rax
0x180007fd3  mov     [rbx+30h], r12
0x180007fd7  mov     rax, [rsp+78h+arg_28]
0x180007fdf  mov     [rbx+88h], rax
0x180007fe6  mov     rax, [rsp+78h+arg_0]
0x180007fee  mov     [rbx+90h], rax
0x180007ff5  mov     [rbx+48h], rdi
0x180007ff9  xorps   xmm0, xmm0
0x180007ffc  xor     eax, eax
0x180007ffe  movups  xmmword ptr [rbx+68h], xmm0
0x180008002  mov     [rbx+78h], rax
0x180008006  movups  xmmword ptr [rbx+50h], xmm0
0x18000800a  mov     [rbx+60h], rax
0x18000800e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008015  test    rax, rax
0x180008018  jz      short loc_180008021
0x18000801a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000801f  jmp     short loc_180008024
0x180008021  mov     rax, rdi
0x180008024  mov     [rbx+80h], rax
0x18000802b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008032  test    rax, rax
0x180008035  jz      short loc_18000803F
0x180008037  mov     rcx, rbx
0x18000803a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000803f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008046  test    rax, rax
0x180008049  jz      short loc_180008061
0x18000804b  mov     r8d, 400h
0x180008051  mov     rdx, [rsp+78h+arg_60]
0x180008059  mov     rcx, rbx
0x18000805c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008061  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008068  test    rax, rax
0x18000806b  jz      short loc_180008075
0x18000806d  mov     rcx, rbx
0x180008070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008075  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000807c  test    rax, rax
0x18000807f  jz      short loc_18000808F
0x180008081  test    byte ptr [rbx+4], 2
0x180008085  jnz     short loc_18000808F
0x180008087  mov     rcx, rbx
0x18000808a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808f  cmp     [rbx+8], edi
0x180008092  jl      short loc_1800080AE
0x180008094  cmp     r15d, 3
0x180008098  jnz     loc_18000818A
0x18000809e  mov     ecx, 8000FFFFh; this
0x1800080a3  mov     [rbx+8], ecx
0x1800080a6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800080ab  mov     [rbx+0Ch], eax
0x1800080ae  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800080b5  jnz     short loc_1800080DC
0x1800080b7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800080be  test    rax, rax
0x1800080c1  jz      short loc_1800080CC
0x1800080c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c8  test    al, al
0x1800080ca  jmp     short loc_1800080DA
0x1800080cc  call    cs:__imp_IsDebuggerPresent
0x1800080d3  nop     dword ptr [rax+rax+00h]
0x1800080d8  test    eax, eax
0x1800080da  jz      short loc_1800080E2
0x1800080dc  test    byte ptr [rbx+4], 2
0x1800080e0  jz      short loc_180008106
0x1800080e2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800080e9  test    rax, rax
0x1800080ec  jz      short loc_180008150
0x1800080ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800080f5  jnz     short loc_180008150
0x1800080f7  xor     r8d, r8d
0x1800080fa  xor     edx, edx
0x1800080fc  mov     rcx, rbx
0x1800080ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008104  jmp     short loc_180008150
0x180008106  mov     ebp, 800h
0x18000810b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008112  test    rax, rax
0x180008115  jz      short loc_18000812E
0x180008117  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000811e  jnz     short loc_18000812E
0x180008120  mov     r8d, ebp
0x180008123  mov     rdx, rsi
0x180008126  mov     rcx, rbx
0x180008129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000812e  cmp     [rsi], di
0x180008131  jnz     short loc_180008141
0x180008133  mov     r8, rbx; unsigned __int64
0x180008136  mov     rdx, rbp; unsigned __int16 *
0x180008139  mov     rcx, rsi; this
0x18000813c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008141  mov     rcx, rsi; lpOutputString
0x180008144  call    cs:__imp_OutputDebugStringW
0x18000814b  nop     dword ptr [rax+rax+00h]
0x180008150  test    byte ptr [rbx+4], 4
0x180008154  jnz     short loc_18000815F
0x180008156  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000815d  jz      short loc_180008171
0x18000815f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008166  test    rax, rax
0x180008169  jz      short loc_180008171
0x18000816b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008170  nop
0x180008171  mov     rbx, [rsp+78h+arg_10]
0x180008179  add     rsp, 40h
0x18000817d  pop     r15
0x18000817f  pop     r14
0x180008181  pop     r13
0x180008183  pop     r12
0x180008185  pop     rdi
0x180008186  pop     rsi
0x180008187  pop     rbp
0x180008188  retn
0x18000818a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
