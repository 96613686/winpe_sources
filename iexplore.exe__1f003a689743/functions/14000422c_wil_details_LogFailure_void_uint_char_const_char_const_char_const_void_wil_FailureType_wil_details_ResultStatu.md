# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000422c`
- end: `0x140004524`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140002858`
- `0x140002ba4`

## callees

- `0x140002798`
- `0x140003654`
- `0x140003e28`
- `0x14000422c`
- `0x140004804`
- `0x140004820`
- `0x140004834`
- `0x140004850`
- `0x1400052fc`
- `0x140006010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1400044e0`
- `KERNEL32!OutputDebugStringW` at `0x1400044e0`
- `KERNEL32!IsDebuggerPresent` at `0x14000446e`
- `KERNEL32!IsDebuggerPresent` at `0x14000446e`
- `KERNEL32!GetCurrentThreadId` at `0x14000434f`
- `KERNEL32!GetCurrentThreadId` at `0x14000434f`

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
0x14000422c  mov     [rsp+arg_10], rbx
0x140004231  mov     [rsp+arg_8], edx
0x140004235  mov     [rsp+arg_0], rcx
0x14000423a  push    rbp
0x14000423b  push    rsi
0x14000423c  push    rdi
0x14000423d  push    r12
0x14000423f  push    r13
0x140004241  push    r14
0x140004243  push    r15
0x140004245  sub     rsp, 40h
0x140004249  mov     r14, [rsp+78h+arg_38]
0x140004251  xor     eax, eax
0x140004253  mov     rbx, [rsp+78h+arg_78]
0x14000425b  xor     ebp, ebp
0x14000425d  mov     r15d, [rsp+78h+arg_30]
0x140004265  mov     r10, rcx
0x140004268  mov     rsi, [rsp+78h+lpOutputString]
0x140004270  mov     r12, r9
0x140004273  mov     r13, r8
0x140004276  mov     ecx, r15d
0x140004279  mov     [rsi], ax
0x14000427c  mov     rax, [rsp+78h+arg_60]
0x140004284  mov     byte ptr [rax], 0
0x140004287  mov     edi, [r14]
0x14000428a  mov     [rbx+8], edi
0x14000428d  mov     eax, [r14+4]
0x140004291  mov     [rbx+0Ch], eax
0x140004294  test    r15d, r15d
0x140004297  jz      short loc_1400042FF
0x140004299  sub     ecx, 1
0x14000429c  jz      short loc_1400042F6
0x14000429e  sub     ecx, 1
0x1400042a1  jz      short loc_1400042B1
0x1400042a3  cmp     ecx, 1
0x1400042a6  jnz     short loc_140004308
0x1400042a8  mov     ecx, edi; this
0x1400042aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400042af  jmp     short loc_140004306
0x1400042b1  test    edi, edi
0x1400042b3  js      short loc_1400042ED
0x1400042b5  mov     rax, [rsp+78h+arg_28]
0x1400042bd  mov     edi, 8007029Ch
0x1400042c2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400042c6  mov     rcx, r10; int
0x1400042c9  mov     [rsp+78h+var_50], rax; __int64
0x1400042ce  mov     rax, [rsp+78h+arg_20]
0x1400042d6  mov     [rsp+78h+var_58], rax; __int64
0x1400042db  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400042e0  mov     ecx, edi; this
0x1400042e2  mov     [rbx+8], edi
0x1400042e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400042ea  mov     [rbx+0Ch], eax
0x1400042ed  mov     ecx, edi; this
0x1400042ef  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400042f4  jmp     short loc_140004306
0x1400042f6  mov     ecx, edi; this
0x1400042f8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400042fd  jmp     short loc_140004306
0x1400042ff  mov     ecx, edi; this
0x140004301  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004306  mov     ebp, eax
0x140004308  mov     eax, [rsp+78h+arg_70]
0x14000430f  mov     [rbx+4], eax
0x140004312  mov     [rbx], r15d
0x140004315  cmp     dword ptr [r14+8], 1
0x14000431a  jnz     short loc_140004322
0x14000431c  or      eax, 8
0x14000431f  mov     [rbx+4], eax
0x140004322  mov     eax, 1
0x140004327  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000432f  inc     eax
0x140004331  xor     edi, edi
0x140004333  mov     [rbx+10h], eax
0x140004336  mov     rax, [rsp+78h+arg_40]
0x14000433e  test    rax, rax
0x140004341  jz      short loc_140004348
0x140004343  cmp     [rax], di
0x140004346  jnz     short loc_14000434B
0x140004348  mov     rax, rdi
0x14000434b  mov     [rbx+18h], rax
0x14000434f  call    cs:__imp_GetCurrentThreadId
0x140004355  mov     [rbx+38h], r13
0x140004359  xorps   xmm0, xmm0
0x14000435c  mov     [rbx+20h], eax
0x14000435f  mov     eax, [rsp+78h+arg_8]
0x140004366  mov     [rbx+40h], eax
0x140004369  mov     rax, [rsp+78h+arg_20]
0x140004371  mov     [rbx+28h], rax
0x140004375  mov     rax, [rsp+78h+arg_28]
0x14000437d  mov     [rbx+88h], rax
0x140004384  mov     rax, [rsp+78h+arg_0]
0x14000438c  mov     [rbx+90h], rax
0x140004393  xor     eax, eax
0x140004395  mov     [rbx+44h], ebp
0x140004398  mov     [rbx+30h], r12
0x14000439c  mov     [rbx+48h], rdi
0x1400043a0  movups  xmmword ptr [rbx+68h], xmm0
0x1400043a4  mov     [rbx+78h], rax
0x1400043a8  movups  xmmword ptr [rbx+50h], xmm0
0x1400043ac  mov     [rbx+60h], rax
0x1400043b0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400043b7  test    rax, rax
0x1400043ba  jz      short loc_1400043C3
0x1400043bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043c1  jmp     short loc_1400043C6
0x1400043c3  mov     rax, rdi
0x1400043c6  mov     [rbx+80h], rax
0x1400043cd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400043d4  test    rax, rax
0x1400043d7  jz      short loc_1400043E1
0x1400043d9  mov     rcx, rbx
0x1400043dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043e1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400043e8  test    rax, rax
0x1400043eb  jz      short loc_140004403
0x1400043ed  mov     rdx, [rsp+78h+arg_60]
0x1400043f5  mov     r8d, 400h
0x1400043fb  mov     rcx, rbx
0x1400043fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004403  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000440a  test    rax, rax
0x14000440d  jz      short loc_140004417
0x14000440f  mov     rcx, rbx
0x140004412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004417  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000441e  test    rax, rax
0x140004421  jz      short loc_140004431
0x140004423  test    byte ptr [rbx+4], 2
0x140004427  jnz     short loc_140004431
0x140004429  mov     rcx, rbx
0x14000442c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004431  cmp     [rbx+8], edi
0x140004434  jl      short loc_140004450
0x140004436  cmp     r15d, 3
0x14000443a  jnz     loc_14000451E
0x140004440  mov     ecx, 8000FFFFh; this
0x140004445  mov     [rbx+8], ecx
0x140004448  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000444d  mov     [rbx+0Ch], eax
0x140004450  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004457  jnz     short loc_140004478
0x140004459  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004460  test    rax, rax
0x140004463  jz      short loc_14000446E
0x140004465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000446a  test    al, al
0x14000446c  jmp     short loc_140004476
0x14000446e  call    cs:__imp_IsDebuggerPresent
0x140004474  test    eax, eax
0x140004476  jz      short loc_14000447E
0x140004478  test    byte ptr [rbx+4], 2
0x14000447c  jz      short loc_1400044A2
0x14000447e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004485  test    rax, rax
0x140004488  jz      short loc_1400044E6
0x14000448a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004491  jnz     short loc_1400044E6
0x140004493  xor     r8d, r8d
0x140004496  xor     edx, edx
0x140004498  mov     rcx, rbx
0x14000449b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044a0  jmp     short loc_1400044E6
0x1400044a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400044a9  mov     ebp, 800h
0x1400044ae  test    rax, rax
0x1400044b1  jz      short loc_1400044CA
0x1400044b3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400044ba  jnz     short loc_1400044CA
0x1400044bc  mov     r8d, ebp
0x1400044bf  mov     rdx, rsi
0x1400044c2  mov     rcx, rbx
0x1400044c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044ca  cmp     [rsi], di
0x1400044cd  jnz     short loc_1400044DD
0x1400044cf  mov     r8, rbx; unsigned __int64
0x1400044d2  mov     rdx, rbp; unsigned __int16 *
0x1400044d5  mov     rcx, rsi; this
0x1400044d8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400044dd  mov     rcx, rsi; lpOutputString
0x1400044e0  call    cs:__imp_OutputDebugStringW
0x1400044e6  test    byte ptr [rbx+4], 4
0x1400044ea  jnz     short loc_1400044F5
0x1400044ec  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400044f3  jz      short loc_140004506
0x1400044f5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400044fc  test    rax, rax
0x1400044ff  jz      short loc_140004506
0x140004501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004506  mov     rbx, [rsp+78h+arg_10]
0x14000450e  add     rsp, 40h
0x140004512  pop     r15
0x140004514  pop     r14
0x140004516  pop     r13
0x140004518  pop     r12
0x14000451a  pop     rdi
0x14000451b  pop     rsi
0x14000451c  pop     rbp
0x14000451d  retn
0x14000451e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
