# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800f10ac`
- end: `0x1800f13ad`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ef9b4`
- `0x1800efd10`

## callees

- `0x1800c6d40`
- `0x1800ef8fc`
- `0x1800f0894`
- `0x1800f10ac`
- `0x1800f1678`
- `0x1800f16a0`
- `0x1800f16b4`
- `0x1800f16d0`
- `0x1800f21e4`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f11d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f11d7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f1368`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f1368`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f12f6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f12f6`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x1800f10ac  mov     rax, rsp
0x1800f10af  mov     [rax+10h], edx
0x1800f10b2  mov     [rax+8], rcx
0x1800f10b6  push    rbp
0x1800f10b7  push    rsi
0x1800f10b8  push    rdi
0x1800f10b9  push    r12
0x1800f10bb  push    r13
0x1800f10bd  push    r14
0x1800f10bf  push    r15
0x1800f10c1  sub     rsp, 50h
0x1800f10c5  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800f10cd  mov     [rax+18h], rbx
0x1800f10d1  mov     r12, r9
0x1800f10d4  mov     r13, r8
0x1800f10d7  mov     r10, rcx
0x1800f10da  xor     eax, eax
0x1800f10dc  mov     rsi, [rsp+88h+lpOutputString]
0x1800f10e4  mov     [rsi], ax
0x1800f10e7  mov     rax, [rsp+88h+arg_60]
0x1800f10ef  mov     byte ptr [rax], 0
0x1800f10f2  mov     r14, [rsp+88h+arg_38]
0x1800f10fa  mov     edi, [r14]
0x1800f10fd  mov     rbx, [rsp+88h+arg_78]
0x1800f1105  mov     [rbx+8], edi
0x1800f1108  mov     eax, [r14+4]
0x1800f110c  mov     [rbx+0Ch], eax
0x1800f110f  xor     ebp, ebp
0x1800f1111  mov     r15d, [rsp+88h+arg_30]
0x1800f1119  mov     ecx, r15d
0x1800f111c  test    r15d, r15d
0x1800f111f  jz      short loc_1800F1187
0x1800f1121  sub     ecx, 1
0x1800f1124  jz      short loc_1800F117E
0x1800f1126  sub     ecx, 1
0x1800f1129  jz      short loc_1800F1139
0x1800f112b  cmp     ecx, 1
0x1800f112e  jnz     short loc_1800F1190
0x1800f1130  mov     ecx, edi; this
0x1800f1132  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800f1137  jmp     short loc_1800F118E
0x1800f1139  test    edi, edi
0x1800f113b  js      short loc_1800F1175
0x1800f113d  mov     edi, 8007029Ch
0x1800f1142  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x1800f1146  mov     rax, [rsp+88h+arg_28]
0x1800f114e  mov     [rsp+88h+var_60], rax; __int64
0x1800f1153  mov     rax, [rsp+88h+arg_20]
0x1800f115b  mov     [rsp+88h+var_68], rax; __int64
0x1800f1160  mov     rcx, r10; int
0x1800f1163  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800f1168  mov     [rbx+8], edi
0x1800f116b  mov     ecx, edi; this
0x1800f116d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800f1172  mov     [rbx+0Ch], eax
0x1800f1175  mov     ecx, edi; this
0x1800f1177  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800f117c  jmp     short loc_1800F118E
0x1800f117e  mov     ecx, edi; this
0x1800f1180  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800f1185  jmp     short loc_1800F118E
0x1800f1187  mov     ecx, edi; this
0x1800f1189  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800f118e  mov     ebp, eax
0x1800f1190  mov     [rbx], r15d
0x1800f1193  mov     eax, [rsp+88h+arg_70]
0x1800f119a  mov     [rbx+4], eax
0x1800f119d  cmp     dword ptr [r14+8], 1
0x1800f11a2  jnz     short loc_1800F11AA
0x1800f11a4  or      eax, 8
0x1800f11a7  mov     [rbx+4], eax
0x1800f11aa  mov     eax, 1
0x1800f11af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800f11b7  inc     eax
0x1800f11b9  mov     [rbx+10h], eax
0x1800f11bc  mov     rax, [rsp+88h+arg_40]
0x1800f11c4  xor     edi, edi
0x1800f11c6  test    rax, rax
0x1800f11c9  jz      short loc_1800F11D0
0x1800f11cb  cmp     [rax], di
0x1800f11ce  jnz     short loc_1800F11D3
0x1800f11d0  mov     rax, rdi
0x1800f11d3  mov     [rbx+18h], rax
0x1800f11d7  call    cs:__imp_GetCurrentThreadId
0x1800f11dd  mov     [rbx+20h], eax
0x1800f11e0  mov     [rbx+38h], r13
0x1800f11e4  mov     eax, [rsp+88h+arg_8]
0x1800f11eb  mov     [rbx+40h], eax
0x1800f11ee  mov     [rbx+44h], ebp
0x1800f11f1  mov     rax, [rsp+88h+arg_20]
0x1800f11f9  mov     [rbx+28h], rax
0x1800f11fd  mov     [rbx+30h], r12
0x1800f1201  mov     rax, [rsp+88h+arg_28]
0x1800f1209  mov     [rbx+88h], rax
0x1800f1210  mov     rax, [rsp+88h+arg_0]
0x1800f1218  mov     [rbx+90h], rax
0x1800f121f  mov     [rbx+48h], rdi
0x1800f1223  xorps   xmm0, xmm0
0x1800f1226  xor     eax, eax
0x1800f1228  movups  xmmword ptr [rbx+68h], xmm0
0x1800f122c  mov     [rbx+78h], rax
0x1800f1230  movups  xmmword ptr [rbx+50h], xmm0
0x1800f1234  mov     [rbx+60h], rax
0x1800f1238  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800f123f  test    rax, rax
0x1800f1242  jz      short loc_1800F124B
0x1800f1244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1249  jmp     short loc_1800F124E
0x1800f124b  mov     rax, rdi
0x1800f124e  mov     [rbx+80h], rax
0x1800f1255  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800f125c  test    rax, rax
0x1800f125f  jz      short loc_1800F1269
0x1800f1261  mov     rcx, rbx
0x1800f1264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1269  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800f1270  test    rax, rax
0x1800f1273  jz      short loc_1800F128B
0x1800f1275  mov     r8d, 400h
0x1800f127b  mov     rdx, [rsp+88h+arg_60]
0x1800f1283  mov     rcx, rbx
0x1800f1286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f128b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f1292  test    rax, rax
0x1800f1295  jz      short loc_1800F129F
0x1800f1297  mov     rcx, rbx
0x1800f129a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f129f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f12a6  test    rax, rax
0x1800f12a9  jz      short loc_1800F12B9
0x1800f12ab  test    byte ptr [rbx+4], 2
0x1800f12af  jnz     short loc_1800F12B9
0x1800f12b1  mov     rcx, rbx
0x1800f12b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f12b9  cmp     [rbx+8], edi
0x1800f12bc  jl      short loc_1800F12D8
0x1800f12be  cmp     r15d, 3
0x1800f12c2  jnz     loc_1800F13A7
0x1800f12c8  mov     ecx, 8000FFFFh; this
0x1800f12cd  mov     [rbx+8], ecx
0x1800f12d0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800f12d5  mov     [rbx+0Ch], eax
0x1800f12d8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800f12df  jnz     short loc_1800F1300
0x1800f12e1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800f12e8  test    rax, rax
0x1800f12eb  jz      short loc_1800F12F6
0x1800f12ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f12f2  test    al, al
0x1800f12f4  jmp     short loc_1800F12FE
0x1800f12f6  call    cs:__imp_IsDebuggerPresent
0x1800f12fc  test    eax, eax
0x1800f12fe  jz      short loc_1800F1306
0x1800f1300  test    byte ptr [rbx+4], 2
0x1800f1304  jz      short loc_1800F132A
0x1800f1306  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f130d  test    rax, rax
0x1800f1310  jz      short loc_1800F136E
0x1800f1312  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800f1319  jnz     short loc_1800F136E
0x1800f131b  xor     r8d, r8d
0x1800f131e  xor     edx, edx
0x1800f1320  mov     rcx, rbx
0x1800f1323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1328  jmp     short loc_1800F136E
0x1800f132a  mov     ebp, 800h
0x1800f132f  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f1336  test    rax, rax
0x1800f1339  jz      short loc_1800F1352
0x1800f133b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800f1342  jnz     short loc_1800F1352
0x1800f1344  mov     r8d, ebp
0x1800f1347  mov     rdx, rsi
0x1800f134a  mov     rcx, rbx
0x1800f134d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1352  cmp     [rsi], di
0x1800f1355  jnz     short loc_1800F1365
0x1800f1357  mov     r8, rbx; unsigned __int64
0x1800f135a  mov     rdx, rbp; wchar_t *
0x1800f135d  mov     rcx, rsi; this
0x1800f1360  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800f1365  mov     rcx, rsi; lpOutputString
0x1800f1368  call    cs:__imp_OutputDebugStringW
0x1800f136e  test    byte ptr [rbx+4], 4
0x1800f1372  jnz     short loc_1800F137D
0x1800f1374  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800f137b  jz      short loc_1800F138F
0x1800f137d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800f1384  test    rax, rax
0x1800f1387  jz      short loc_1800F138F
0x1800f1389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f138e  nop
0x1800f138f  mov     rbx, [rsp+88h+arg_10]
0x1800f1397  add     rsp, 50h
0x1800f139b  pop     r15
0x1800f139d  pop     r14
0x1800f139f  pop     r13
0x1800f13a1  pop     r12
0x1800f13a3  pop     rdi
0x1800f13a4  pop     rsi
0x1800f13a5  pop     rbp
0x1800f13a6  retn
0x1800f13a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
