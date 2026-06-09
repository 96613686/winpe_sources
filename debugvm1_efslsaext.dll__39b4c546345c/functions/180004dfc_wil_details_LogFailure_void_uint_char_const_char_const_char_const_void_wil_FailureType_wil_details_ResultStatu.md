# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004dfc`
- end: `0x1800050f4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800037d8`

## callees

- `0x180002b90`
- `0x180003214`
- `0x18000459c`
- `0x180004c24`
- `0x180004dfc`
- `0x1800054f8`
- `0x180005514`
- `0x180005530`
- `0x1800062ec`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050b0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050b0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000503e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000503e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f1f`

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
0x180004dfc  mov     [rsp+arg_10], rbx
0x180004e01  mov     [rsp+arg_8], edx
0x180004e05  mov     [rsp+arg_0], rcx
0x180004e0a  push    rbp
0x180004e0b  push    rsi
0x180004e0c  push    rdi
0x180004e0d  push    r12
0x180004e0f  push    r13
0x180004e11  push    r14
0x180004e13  push    r15
0x180004e15  sub     rsp, 40h
0x180004e19  mov     r14, [rsp+78h+arg_38]
0x180004e21  xor     eax, eax
0x180004e23  mov     rbx, [rsp+78h+arg_78]
0x180004e2b  xor     ebp, ebp
0x180004e2d  mov     r15d, [rsp+78h+arg_30]
0x180004e35  mov     r10, rcx
0x180004e38  mov     rsi, [rsp+78h+lpOutputString]
0x180004e40  mov     r12, r9
0x180004e43  mov     r13, r8
0x180004e46  mov     ecx, r15d
0x180004e49  mov     [rsi], ax
0x180004e4c  mov     rax, [rsp+78h+arg_60]
0x180004e54  mov     byte ptr [rax], 0
0x180004e57  mov     edi, [r14]
0x180004e5a  mov     [rbx+8], edi
0x180004e5d  mov     eax, [r14+4]
0x180004e61  mov     [rbx+0Ch], eax
0x180004e64  test    r15d, r15d
0x180004e67  jz      short loc_180004ECF
0x180004e69  sub     ecx, 1
0x180004e6c  jz      short loc_180004EC6
0x180004e6e  sub     ecx, 1
0x180004e71  jz      short loc_180004E81
0x180004e73  cmp     ecx, 1
0x180004e76  jnz     short loc_180004ED8
0x180004e78  mov     ecx, edi; this
0x180004e7a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004e7f  jmp     short loc_180004ED6
0x180004e81  test    edi, edi
0x180004e83  js      short loc_180004EBD
0x180004e85  mov     rax, [rsp+78h+arg_28]
0x180004e8d  mov     edi, 8007029Ch
0x180004e92  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004e96  mov     rcx, r10; int
0x180004e99  mov     [rsp+78h+var_50], rax; __int64
0x180004e9e  mov     rax, [rsp+78h+arg_20]
0x180004ea6  mov     [rsp+78h+var_58], rax; __int64
0x180004eab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004eb0  mov     ecx, edi; this
0x180004eb2  mov     [rbx+8], edi
0x180004eb5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004eba  mov     [rbx+0Ch], eax
0x180004ebd  mov     ecx, edi; this
0x180004ebf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004ec4  jmp     short loc_180004ED6
0x180004ec6  mov     ecx, edi; this
0x180004ec8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004ecd  jmp     short loc_180004ED6
0x180004ecf  mov     ecx, edi; this
0x180004ed1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004ed6  mov     ebp, eax
0x180004ed8  mov     eax, [rsp+78h+arg_70]
0x180004edf  mov     [rbx+4], eax
0x180004ee2  mov     [rbx], r15d
0x180004ee5  cmp     dword ptr [r14+8], 1
0x180004eea  jnz     short loc_180004EF2
0x180004eec  or      eax, 8
0x180004eef  mov     [rbx+4], eax
0x180004ef2  mov     eax, 1
0x180004ef7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004eff  inc     eax
0x180004f01  xor     edi, edi
0x180004f03  mov     [rbx+10h], eax
0x180004f06  mov     rax, [rsp+78h+arg_40]
0x180004f0e  test    rax, rax
0x180004f11  jz      short loc_180004F18
0x180004f13  cmp     [rax], di
0x180004f16  jnz     short loc_180004F1B
0x180004f18  mov     rax, rdi
0x180004f1b  mov     [rbx+18h], rax
0x180004f1f  call    cs:__imp_GetCurrentThreadId
0x180004f25  mov     [rbx+38h], r13
0x180004f29  xorps   xmm0, xmm0
0x180004f2c  mov     [rbx+20h], eax
0x180004f2f  mov     eax, [rsp+78h+arg_8]
0x180004f36  mov     [rbx+40h], eax
0x180004f39  mov     rax, [rsp+78h+arg_20]
0x180004f41  mov     [rbx+28h], rax
0x180004f45  mov     rax, [rsp+78h+arg_28]
0x180004f4d  mov     [rbx+88h], rax
0x180004f54  mov     rax, [rsp+78h+arg_0]
0x180004f5c  mov     [rbx+90h], rax
0x180004f63  xor     eax, eax
0x180004f65  mov     [rbx+44h], ebp
0x180004f68  mov     [rbx+30h], r12
0x180004f6c  mov     [rbx+48h], rdi
0x180004f70  movups  xmmword ptr [rbx+68h], xmm0
0x180004f74  mov     [rbx+78h], rax
0x180004f78  movups  xmmword ptr [rbx+50h], xmm0
0x180004f7c  mov     [rbx+60h], rax
0x180004f80  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004f87  test    rax, rax
0x180004f8a  jz      short loc_180004F93
0x180004f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f91  jmp     short loc_180004F96
0x180004f93  mov     rax, rdi
0x180004f96  mov     [rbx+80h], rax
0x180004f9d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fa4  test    rax, rax
0x180004fa7  jz      short loc_180004FB1
0x180004fa9  mov     rcx, rbx
0x180004fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004fb8  test    rax, rax
0x180004fbb  jz      short loc_180004FD3
0x180004fbd  mov     rdx, [rsp+78h+arg_60]
0x180004fc5  mov     r8d, 400h
0x180004fcb  mov     rcx, rbx
0x180004fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004fda  test    rax, rax
0x180004fdd  jz      short loc_180004FE7
0x180004fdf  mov     rcx, rbx
0x180004fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004fee  test    rax, rax
0x180004ff1  jz      short loc_180005001
0x180004ff3  test    byte ptr [rbx+4], 2
0x180004ff7  jnz     short loc_180005001
0x180004ff9  mov     rcx, rbx
0x180004ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005001  cmp     [rbx+8], edi
0x180005004  jl      short loc_180005020
0x180005006  cmp     r15d, 3
0x18000500a  jnz     loc_1800050EE
0x180005010  mov     ecx, 8000FFFFh; this
0x180005015  mov     [rbx+8], ecx
0x180005018  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000501d  mov     [rbx+0Ch], eax
0x180005020  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005027  jnz     short loc_180005048
0x180005029  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005030  test    rax, rax
0x180005033  jz      short loc_18000503E
0x180005035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000503a  test    al, al
0x18000503c  jmp     short loc_180005046
0x18000503e  call    cs:__imp_IsDebuggerPresent
0x180005044  test    eax, eax
0x180005046  jz      short loc_18000504E
0x180005048  test    byte ptr [rbx+4], 2
0x18000504c  jz      short loc_180005072
0x18000504e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005055  test    rax, rax
0x180005058  jz      short loc_1800050B6
0x18000505a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005061  jnz     short loc_1800050B6
0x180005063  xor     r8d, r8d
0x180005066  xor     edx, edx
0x180005068  mov     rcx, rbx
0x18000506b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005070  jmp     short loc_1800050B6
0x180005072  mov     rax, cs:g_pfnResultLoggingCallback
0x180005079  mov     ebp, 800h
0x18000507e  test    rax, rax
0x180005081  jz      short loc_18000509A
0x180005083  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000508a  jnz     short loc_18000509A
0x18000508c  mov     r8d, ebp
0x18000508f  mov     rdx, rsi
0x180005092  mov     rcx, rbx
0x180005095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509a  cmp     [rsi], di
0x18000509d  jnz     short loc_1800050AD
0x18000509f  mov     r8, rbx; unsigned __int64
0x1800050a2  mov     rdx, rbp; unsigned __int16 *
0x1800050a5  mov     rcx, rsi; this
0x1800050a8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800050ad  mov     rcx, rsi; lpOutputString
0x1800050b0  call    cs:__imp_OutputDebugStringW
0x1800050b6  test    byte ptr [rbx+4], 4
0x1800050ba  jnz     short loc_1800050C5
0x1800050bc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800050c3  jz      short loc_1800050D6
0x1800050c5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800050cc  test    rax, rax
0x1800050cf  jz      short loc_1800050D6
0x1800050d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d6  mov     rbx, [rsp+78h+arg_10]
0x1800050de  add     rsp, 40h
0x1800050e2  pop     r15
0x1800050e4  pop     r14
0x1800050e6  pop     r13
0x1800050e8  pop     r12
0x1800050ea  pop     rdi
0x1800050eb  pop     rsi
0x1800050ec  pop     rbp
0x1800050ed  retn
0x1800050ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
