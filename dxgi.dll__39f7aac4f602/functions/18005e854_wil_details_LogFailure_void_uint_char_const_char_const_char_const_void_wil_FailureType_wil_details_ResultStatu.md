# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005e854`
- end: `0x18005eb4d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18005e758`
- `0x18007c66c`
- `0x18007c72c`
- `0x180088b68`

## callees

- `0x18003ea90`
- `0x18005e854`
- `0x18007c5b4`
- `0x18007d3dc`
- `0x18007de9c`
- `0x18007dec0`
- `0x18007ded4`
- `0x18007def0`
- `0x18007e8ac`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e97b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e97b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005ea9c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005ea9c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005eb0e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005eb0e`

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
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
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
0x18005e854  mov     [rsp+arg_10], rbx
0x18005e859  mov     [rsp+arg_8], edx
0x18005e85d  mov     [rsp+arg_0], rcx
0x18005e862  push    rbp
0x18005e863  push    rsi
0x18005e864  push    rdi
0x18005e865  push    r12
0x18005e867  push    r13
0x18005e869  push    r14
0x18005e86b  push    r15
0x18005e86d  sub     rsp, 40h
0x18005e871  mov     r12, r9
0x18005e874  mov     r13, r8
0x18005e877  mov     r10, rcx
0x18005e87a  xor     eax, eax
0x18005e87c  mov     rsi, [rsp+78h+lpOutputString]
0x18005e884  mov     [rsi], ax
0x18005e887  mov     rax, [rsp+78h+arg_60]
0x18005e88f  mov     byte ptr [rax], 0
0x18005e892  mov     r14, [rsp+78h+arg_38]
0x18005e89a  mov     edi, [r14]
0x18005e89d  mov     rbx, [rsp+78h+arg_78]
0x18005e8a5  mov     [rbx+8], edi
0x18005e8a8  mov     eax, [r14+4]
0x18005e8ac  mov     [rbx+0Ch], eax
0x18005e8af  xor     ebp, ebp
0x18005e8b1  mov     r15d, [rsp+78h+arg_30]
0x18005e8b9  mov     ecx, r15d
0x18005e8bc  test    r15d, r15d
0x18005e8bf  jz      short loc_18005E92B
0x18005e8c1  sub     ecx, 1
0x18005e8c4  jz      short loc_18005E922
0x18005e8c6  sub     ecx, 1
0x18005e8c9  jz      short loc_18005E8D9
0x18005e8cb  cmp     ecx, 1
0x18005e8ce  jnz     short loc_18005E934
0x18005e8d0  mov     ecx, edi; this
0x18005e8d2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18005e8d7  jmp     short loc_18005E932
0x18005e8d9  test    edi, edi
0x18005e8db  js      short loc_18005E919
0x18005e8dd  mov     [rsp+78h+var_40], ebp
0x18005e8e1  mov     edi, 8007029Ch
0x18005e8e6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18005e8ea  mov     rax, [rsp+78h+arg_28]
0x18005e8f2  mov     [rsp+78h+var_50], rax; __int64
0x18005e8f7  mov     rax, [rsp+78h+arg_20]
0x18005e8ff  mov     [rsp+78h+var_58], rax; __int64
0x18005e904  mov     rcx, r10; int
0x18005e907  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18005e90c  mov     [rbx+8], edi
0x18005e90f  mov     ecx, edi; this
0x18005e911  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005e916  mov     [rbx+0Ch], eax
0x18005e919  mov     ecx, edi; this
0x18005e91b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18005e920  jmp     short loc_18005E932
0x18005e922  mov     ecx, edi; this
0x18005e924  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005e929  jmp     short loc_18005E932
0x18005e92b  mov     ecx, edi; this
0x18005e92d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005e932  mov     ebp, eax
0x18005e934  mov     [rbx], r15d
0x18005e937  mov     eax, [rsp+78h+arg_70]
0x18005e93e  mov     [rbx+4], eax
0x18005e941  cmp     dword ptr [r14+8], 1
0x18005e946  jnz     short loc_18005E94E
0x18005e948  or      eax, 8
0x18005e94b  mov     [rbx+4], eax
0x18005e94e  mov     eax, 1
0x18005e953  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005e95b  inc     eax
0x18005e95d  mov     [rbx+10h], eax
0x18005e960  mov     rax, [rsp+78h+arg_40]
0x18005e968  xor     edi, edi
0x18005e96a  test    rax, rax
0x18005e96d  jz      short loc_18005E974
0x18005e96f  cmp     [rax], di
0x18005e972  jnz     short loc_18005E977
0x18005e974  mov     rax, rdi
0x18005e977  mov     [rbx+18h], rax
0x18005e97b  call    cs:__imp_GetCurrentThreadId
0x18005e981  mov     [rbx+20h], eax
0x18005e984  mov     [rbx+38h], r13
0x18005e988  mov     eax, [rsp+78h+arg_8]
0x18005e98f  mov     [rbx+40h], eax
0x18005e992  mov     [rbx+44h], ebp
0x18005e995  mov     rax, [rsp+78h+arg_20]
0x18005e99d  mov     [rbx+28h], rax
0x18005e9a1  mov     [rbx+30h], r12
0x18005e9a5  mov     rax, [rsp+78h+arg_28]
0x18005e9ad  mov     [rbx+88h], rax
0x18005e9b4  mov     rax, [rsp+78h+arg_0]
0x18005e9bc  mov     [rbx+90h], rax
0x18005e9c3  mov     [rbx+48h], rdi
0x18005e9c7  xorps   xmm0, xmm0
0x18005e9ca  xor     eax, eax
0x18005e9cc  movups  xmmword ptr [rbx+68h], xmm0
0x18005e9d0  mov     [rbx+78h], rax
0x18005e9d4  movups  xmmword ptr [rbx+50h], xmm0
0x18005e9d8  mov     [rbx+60h], rax
0x18005e9dc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005e9e3  test    rax, rax
0x18005e9e6  jz      short loc_18005E9EF
0x18005e9e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9ed  jmp     short loc_18005E9F2
0x18005e9ef  mov     rax, rdi
0x18005e9f2  mov     [rbx+80h], rax
0x18005e9f9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005ea00  test    rax, rax
0x18005ea03  jz      short loc_18005EA0D
0x18005ea05  mov     rcx, rbx
0x18005ea08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea0d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005ea14  test    rax, rax
0x18005ea17  jz      short loc_18005EA2F
0x18005ea19  mov     r8d, 400h
0x18005ea1f  mov     rdx, [rsp+78h+arg_60]
0x18005ea27  mov     rcx, rbx
0x18005ea2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea2f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005ea36  test    rax, rax
0x18005ea39  jz      short loc_18005EA43
0x18005ea3b  mov     rcx, rbx
0x18005ea3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea43  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005ea4a  test    rax, rax
0x18005ea4d  jz      short loc_18005EA5D
0x18005ea4f  test    byte ptr [rbx+4], 2
0x18005ea53  jnz     short loc_18005EA5D
0x18005ea55  mov     rcx, rbx
0x18005ea58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea5d  cmp     [rbx+8], edi
0x18005ea60  jl      short loc_18005EA7E
0x18005ea62  cmp     r15d, 3
0x18005ea66  jz      short loc_18005EA6E
0x18005ea68  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18005ea6e  mov     ecx, 8000FFFFh; this
0x18005ea73  mov     [rbx+8], ecx
0x18005ea76  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005ea7b  mov     [rbx+0Ch], eax
0x18005ea7e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005ea85  jnz     short loc_18005EAA6
0x18005ea87  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005ea8e  test    rax, rax
0x18005ea91  jz      short loc_18005EA9C
0x18005ea93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea98  test    al, al
0x18005ea9a  jmp     short loc_18005EAA4
0x18005ea9c  call    cs:__imp_IsDebuggerPresent
0x18005eaa2  test    eax, eax
0x18005eaa4  jz      short loc_18005EAAC
0x18005eaa6  test    byte ptr [rbx+4], 2
0x18005eaaa  jz      short loc_18005EAD0
0x18005eaac  mov     rax, cs:g_pfnResultLoggingCallback
0x18005eab3  test    rax, rax
0x18005eab6  jz      short loc_18005EB14
0x18005eab8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005eabf  jnz     short loc_18005EB14
0x18005eac1  xor     r8d, r8d
0x18005eac4  xor     edx, edx
0x18005eac6  mov     rcx, rbx
0x18005eac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eace  jmp     short loc_18005EB14
0x18005ead0  mov     ebp, 800h
0x18005ead5  mov     rax, cs:g_pfnResultLoggingCallback
0x18005eadc  test    rax, rax
0x18005eadf  jz      short loc_18005EAF8
0x18005eae1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005eae8  jnz     short loc_18005EAF8
0x18005eaea  mov     r8d, ebp
0x18005eaed  mov     rdx, rsi
0x18005eaf0  mov     rcx, rbx
0x18005eaf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eaf8  cmp     [rsi], di
0x18005eafb  jnz     short loc_18005EB0B
0x18005eafd  mov     r8, rbx; unsigned __int64
0x18005eb00  mov     rdx, rbp; unsigned __int16 *
0x18005eb03  mov     rcx, rsi; this
0x18005eb06  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005eb0b  mov     rcx, rsi; lpOutputString
0x18005eb0e  call    cs:__imp_OutputDebugStringW
0x18005eb14  test    byte ptr [rbx+4], 4
0x18005eb18  jnz     short loc_18005EB23
0x18005eb1a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18005eb21  jz      short loc_18005EB35
0x18005eb23  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005eb2a  test    rax, rax
0x18005eb2d  jz      short loc_18005EB35
0x18005eb2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb34  nop
0x18005eb35  mov     rbx, [rsp+78h+arg_10]
0x18005eb3d  add     rsp, 40h
0x18005eb41  pop     r15
0x18005eb43  pop     r14
0x18005eb45  pop     r13
0x18005eb47  pop     r12
0x18005eb49  pop     rdi
0x18005eb4a  pop     rsi
0x18005eb4b  pop     rbp
0x18005eb4c  retn
```
