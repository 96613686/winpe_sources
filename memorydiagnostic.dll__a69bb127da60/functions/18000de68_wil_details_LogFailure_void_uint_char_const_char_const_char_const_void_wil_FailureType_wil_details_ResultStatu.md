# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000de68`
- end: `0x18000e161`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005d50`

## callees

- `0x180005324`
- `0x18000cd54`
- `0x18000d5a0`
- `0x18000de68`
- `0x18000f25c`
- `0x18000f280`
- `0x18000f3ac`
- `0x18000f3c8`
- `0x1800155f4`
- `0x180023010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000e0aa`
- `KERNEL32!IsDebuggerPresent` at `0x18000e0aa`
- `KERNEL32!OutputDebugStringW` at `0x18000e11c`
- `KERNEL32!OutputDebugStringW` at `0x18000e11c`
- `KERNEL32!GetCurrentThreadId` at `0x18000df8b`
- `KERNEL32!GetCurrentThreadId` at `0x18000df8b`

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
0x18000de68  mov     [rsp+arg_10], rbx
0x18000de6d  mov     [rsp+arg_8], edx
0x18000de71  mov     [rsp+arg_0], rcx
0x18000de76  push    rbp
0x18000de77  push    rsi
0x18000de78  push    rdi
0x18000de79  push    r12
0x18000de7b  push    r13
0x18000de7d  push    r14
0x18000de7f  push    r15
0x18000de81  sub     rsp, 40h
0x18000de85  mov     r12, r9
0x18000de88  mov     r13, r8
0x18000de8b  mov     r10, rcx
0x18000de8e  xor     eax, eax
0x18000de90  mov     rsi, [rsp+78h+lpOutputString]
0x18000de98  mov     [rsi], ax
0x18000de9b  mov     rax, [rsp+78h+arg_60]
0x18000dea3  mov     byte ptr [rax], 0
0x18000dea6  mov     r14, [rsp+78h+arg_38]
0x18000deae  mov     edi, [r14]
0x18000deb1  mov     rbx, [rsp+78h+arg_78]
0x18000deb9  mov     [rbx+8], edi
0x18000debc  mov     eax, [r14+4]
0x18000dec0  mov     [rbx+0Ch], eax
0x18000dec3  xor     ebp, ebp
0x18000dec5  mov     r15d, [rsp+78h+arg_30]
0x18000decd  mov     ecx, r15d
0x18000ded0  test    r15d, r15d
0x18000ded3  jz      short loc_18000DF3B
0x18000ded5  sub     ecx, 1
0x18000ded8  jz      short loc_18000DF32
0x18000deda  sub     ecx, 1
0x18000dedd  jz      short loc_18000DEED
0x18000dedf  cmp     ecx, 1
0x18000dee2  jnz     short loc_18000DF44
0x18000dee4  mov     ecx, edi; this
0x18000dee6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000deeb  jmp     short loc_18000DF42
0x18000deed  test    edi, edi
0x18000deef  js      short loc_18000DF29
0x18000def1  mov     edi, 8007029Ch
0x18000def6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000defa  mov     rax, [rsp+78h+arg_28]
0x18000df02  mov     [rsp+78h+var_50], rax; __int64
0x18000df07  mov     rax, [rsp+78h+arg_20]
0x18000df0f  mov     [rsp+78h+var_58], rax; __int64
0x18000df14  mov     rcx, r10; int
0x18000df17  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000df1c  mov     [rbx+8], edi
0x18000df1f  mov     ecx, edi; this
0x18000df21  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000df26  mov     [rbx+0Ch], eax
0x18000df29  mov     ecx, edi; this
0x18000df2b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000df30  jmp     short loc_18000DF42
0x18000df32  mov     ecx, edi; this
0x18000df34  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000df39  jmp     short loc_18000DF42
0x18000df3b  mov     ecx, edi; this
0x18000df3d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000df42  mov     ebp, eax
0x18000df44  mov     [rbx], r15d
0x18000df47  mov     eax, [rsp+78h+arg_70]
0x18000df4e  mov     [rbx+4], eax
0x18000df51  cmp     dword ptr [r14+8], 1
0x18000df56  jnz     short loc_18000DF5E
0x18000df58  or      eax, 8
0x18000df5b  mov     [rbx+4], eax
0x18000df5e  mov     eax, 1
0x18000df63  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000df6b  inc     eax
0x18000df6d  mov     [rbx+10h], eax
0x18000df70  mov     rax, [rsp+78h+arg_40]
0x18000df78  xor     edi, edi
0x18000df7a  test    rax, rax
0x18000df7d  jz      short loc_18000DF84
0x18000df7f  cmp     [rax], di
0x18000df82  jnz     short loc_18000DF87
0x18000df84  mov     rax, rdi
0x18000df87  mov     [rbx+18h], rax
0x18000df8b  call    cs:__imp_GetCurrentThreadId
0x18000df91  mov     [rbx+20h], eax
0x18000df94  mov     [rbx+38h], r13
0x18000df98  mov     eax, [rsp+78h+arg_8]
0x18000df9f  mov     [rbx+40h], eax
0x18000dfa2  mov     [rbx+44h], ebp
0x18000dfa5  mov     rax, [rsp+78h+arg_20]
0x18000dfad  mov     [rbx+28h], rax
0x18000dfb1  mov     [rbx+30h], r12
0x18000dfb5  mov     rax, [rsp+78h+arg_28]
0x18000dfbd  mov     [rbx+88h], rax
0x18000dfc4  mov     rax, [rsp+78h+arg_0]
0x18000dfcc  mov     [rbx+90h], rax
0x18000dfd3  mov     [rbx+48h], rdi
0x18000dfd7  xorps   xmm0, xmm0
0x18000dfda  xor     eax, eax
0x18000dfdc  movups  xmmword ptr [rbx+68h], xmm0
0x18000dfe0  mov     [rbx+78h], rax
0x18000dfe4  movups  xmmword ptr [rbx+50h], xmm0
0x18000dfe8  mov     [rbx+60h], rax
0x18000dfec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000dff3  test    rax, rax
0x18000dff6  jz      short loc_18000DFFF
0x18000dff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dffd  jmp     short loc_18000E002
0x18000dfff  mov     rax, rdi
0x18000e002  mov     [rbx+80h], rax
0x18000e009  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e010  test    rax, rax
0x18000e013  jz      short loc_18000E01D
0x18000e015  mov     rcx, rbx
0x18000e018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e01d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e024  test    rax, rax
0x18000e027  jz      short loc_18000E03F
0x18000e029  mov     r8d, 400h
0x18000e02f  mov     rdx, [rsp+78h+arg_60]
0x18000e037  mov     rcx, rbx
0x18000e03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e03f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e046  test    rax, rax
0x18000e049  jz      short loc_18000E053
0x18000e04b  mov     rcx, rbx
0x18000e04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e053  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e05a  test    rax, rax
0x18000e05d  jz      short loc_18000E06D
0x18000e05f  test    byte ptr [rbx+4], 2
0x18000e063  jnz     short loc_18000E06D
0x18000e065  mov     rcx, rbx
0x18000e068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e06d  cmp     [rbx+8], edi
0x18000e070  jl      short loc_18000E08C
0x18000e072  cmp     r15d, 3
0x18000e076  jnz     loc_18000E15B
0x18000e07c  mov     ecx, 8000FFFFh; this
0x18000e081  mov     [rbx+8], ecx
0x18000e084  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e089  mov     [rbx+0Ch], eax
0x18000e08c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e093  jnz     short loc_18000E0B4
0x18000e095  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e09c  test    rax, rax
0x18000e09f  jz      short loc_18000E0AA
0x18000e0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0a6  test    al, al
0x18000e0a8  jmp     short loc_18000E0B2
0x18000e0aa  call    cs:__imp_IsDebuggerPresent
0x18000e0b0  test    eax, eax
0x18000e0b2  jz      short loc_18000E0BA
0x18000e0b4  test    byte ptr [rbx+4], 2
0x18000e0b8  jz      short loc_18000E0DE
0x18000e0ba  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e0c1  test    rax, rax
0x18000e0c4  jz      short loc_18000E122
0x18000e0c6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e0cd  jnz     short loc_18000E122
0x18000e0cf  xor     r8d, r8d
0x18000e0d2  xor     edx, edx
0x18000e0d4  mov     rcx, rbx
0x18000e0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0dc  jmp     short loc_18000E122
0x18000e0de  mov     ebp, 800h
0x18000e0e3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e0ea  test    rax, rax
0x18000e0ed  jz      short loc_18000E106
0x18000e0ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e0f6  jnz     short loc_18000E106
0x18000e0f8  mov     r8d, ebp
0x18000e0fb  mov     rdx, rsi
0x18000e0fe  mov     rcx, rbx
0x18000e101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e106  cmp     [rsi], di
0x18000e109  jnz     short loc_18000E119
0x18000e10b  mov     r8, rbx; unsigned __int64
0x18000e10e  mov     rdx, rbp; unsigned __int16 *
0x18000e111  mov     rcx, rsi; this
0x18000e114  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e119  mov     rcx, rsi; lpOutputString
0x18000e11c  call    cs:__imp_OutputDebugStringW
0x18000e122  test    byte ptr [rbx+4], 4
0x18000e126  jnz     short loc_18000E131
0x18000e128  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e12f  jz      short loc_18000E143
0x18000e131  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e138  test    rax, rax
0x18000e13b  jz      short loc_18000E143
0x18000e13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e142  nop
0x18000e143  mov     rbx, [rsp+78h+arg_10]
0x18000e14b  add     rsp, 40h
0x18000e14f  pop     r15
0x18000e151  pop     r14
0x18000e153  pop     r13
0x18000e155  pop     r12
0x18000e157  pop     rdi
0x18000e158  pop     rsi
0x18000e159  pop     rbp
0x18000e15a  retn
0x18000e15b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
