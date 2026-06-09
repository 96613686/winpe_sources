# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180059850`
- end: `0x180059b48`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800586ec`
- `0x180058a38`

## callees

- `0x18004dda0`
- `0x18005862c`
- `0x180059264`
- `0x180059850`
- `0x180059e2c`
- `0x180059e50`
- `0x180059ec0`
- `0x180059edc`
- `0x18005a808`
- `0x180096010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180059973`
- `KERNEL32!GetCurrentThreadId` at `0x180059973`
- `KERNEL32!OutputDebugStringW` at `0x180059b04`
- `KERNEL32!OutputDebugStringW` at `0x180059b04`
- `KERNEL32!IsDebuggerPresent` at `0x180059a92`
- `KERNEL32!IsDebuggerPresent` at `0x180059a92`

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
0x180059850  mov     [rsp+arg_10], rbx
0x180059855  mov     [rsp+arg_8], edx
0x180059859  mov     [rsp+arg_0], rcx
0x18005985e  push    rbp
0x18005985f  push    rsi
0x180059860  push    rdi
0x180059861  push    r12
0x180059863  push    r13
0x180059865  push    r14
0x180059867  push    r15
0x180059869  sub     rsp, 40h
0x18005986d  mov     r14, [rsp+78h+arg_38]
0x180059875  xor     eax, eax
0x180059877  mov     rbx, [rsp+78h+arg_78]
0x18005987f  xor     ebp, ebp
0x180059881  mov     r15d, [rsp+78h+arg_30]
0x180059889  mov     r10, rcx
0x18005988c  mov     rsi, [rsp+78h+lpOutputString]
0x180059894  mov     r12, r9
0x180059897  mov     r13, r8
0x18005989a  mov     ecx, r15d
0x18005989d  mov     [rsi], ax
0x1800598a0  mov     rax, [rsp+78h+arg_60]
0x1800598a8  mov     byte ptr [rax], 0
0x1800598ab  mov     edi, [r14]
0x1800598ae  mov     [rbx+8], edi
0x1800598b1  mov     eax, [r14+4]
0x1800598b5  mov     [rbx+0Ch], eax
0x1800598b8  test    r15d, r15d
0x1800598bb  jz      short loc_180059923
0x1800598bd  sub     ecx, 1
0x1800598c0  jz      short loc_18005991A
0x1800598c2  sub     ecx, 1
0x1800598c5  jz      short loc_1800598D5
0x1800598c7  cmp     ecx, 1
0x1800598ca  jnz     short loc_18005992C
0x1800598cc  mov     ecx, edi; this
0x1800598ce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800598d3  jmp     short loc_18005992A
0x1800598d5  test    edi, edi
0x1800598d7  js      short loc_180059911
0x1800598d9  mov     rax, [rsp+78h+arg_28]
0x1800598e1  mov     edi, 8007029Ch
0x1800598e6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800598ea  mov     rcx, r10; int
0x1800598ed  mov     [rsp+78h+var_50], rax; __int64
0x1800598f2  mov     rax, [rsp+78h+arg_20]
0x1800598fa  mov     [rsp+78h+var_58], rax; __int64
0x1800598ff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180059904  mov     ecx, edi; this
0x180059906  mov     [rbx+8], edi
0x180059909  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005990e  mov     [rbx+0Ch], eax
0x180059911  mov     ecx, edi; this
0x180059913  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180059918  jmp     short loc_18005992A
0x18005991a  mov     ecx, edi; this
0x18005991c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180059921  jmp     short loc_18005992A
0x180059923  mov     ecx, edi; this
0x180059925  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005992a  mov     ebp, eax
0x18005992c  mov     eax, [rsp+78h+arg_70]
0x180059933  mov     [rbx+4], eax
0x180059936  mov     [rbx], r15d
0x180059939  cmp     dword ptr [r14+8], 1
0x18005993e  jnz     short loc_180059946
0x180059940  or      eax, 8
0x180059943  mov     [rbx+4], eax
0x180059946  mov     eax, 1
0x18005994b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180059953  inc     eax
0x180059955  xor     edi, edi
0x180059957  mov     [rbx+10h], eax
0x18005995a  mov     rax, [rsp+78h+arg_40]
0x180059962  test    rax, rax
0x180059965  jz      short loc_18005996C
0x180059967  cmp     [rax], di
0x18005996a  jnz     short loc_18005996F
0x18005996c  mov     rax, rdi
0x18005996f  mov     [rbx+18h], rax
0x180059973  call    cs:__imp_GetCurrentThreadId
0x180059979  mov     [rbx+38h], r13
0x18005997d  xorps   xmm0, xmm0
0x180059980  mov     [rbx+20h], eax
0x180059983  mov     eax, [rsp+78h+arg_8]
0x18005998a  mov     [rbx+40h], eax
0x18005998d  mov     rax, [rsp+78h+arg_20]
0x180059995  mov     [rbx+28h], rax
0x180059999  mov     rax, [rsp+78h+arg_28]
0x1800599a1  mov     [rbx+88h], rax
0x1800599a8  mov     rax, [rsp+78h+arg_0]
0x1800599b0  mov     [rbx+90h], rax
0x1800599b7  xor     eax, eax
0x1800599b9  mov     [rbx+44h], ebp
0x1800599bc  mov     [rbx+30h], r12
0x1800599c0  mov     [rbx+48h], rdi
0x1800599c4  movups  xmmword ptr [rbx+68h], xmm0
0x1800599c8  mov     [rbx+78h], rax
0x1800599cc  movups  xmmword ptr [rbx+50h], xmm0
0x1800599d0  mov     [rbx+60h], rax
0x1800599d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800599db  test    rax, rax
0x1800599de  jz      short loc_1800599E7
0x1800599e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599e5  jmp     short loc_1800599EA
0x1800599e7  mov     rax, rdi
0x1800599ea  mov     [rbx+80h], rax
0x1800599f1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800599f8  test    rax, rax
0x1800599fb  jz      short loc_180059A05
0x1800599fd  mov     rcx, rbx
0x180059a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a05  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180059a0c  test    rax, rax
0x180059a0f  jz      short loc_180059A27
0x180059a11  mov     rdx, [rsp+78h+arg_60]
0x180059a19  mov     r8d, 400h
0x180059a1f  mov     rcx, rbx
0x180059a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a27  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180059a2e  test    rax, rax
0x180059a31  jz      short loc_180059A3B
0x180059a33  mov     rcx, rbx
0x180059a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a3b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180059a42  test    rax, rax
0x180059a45  jz      short loc_180059A55
0x180059a47  test    byte ptr [rbx+4], 2
0x180059a4b  jnz     short loc_180059A55
0x180059a4d  mov     rcx, rbx
0x180059a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a55  cmp     [rbx+8], edi
0x180059a58  jl      short loc_180059A74
0x180059a5a  cmp     r15d, 3
0x180059a5e  jnz     loc_180059B42
0x180059a64  mov     ecx, 8000FFFFh; this
0x180059a69  mov     [rbx+8], ecx
0x180059a6c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180059a71  mov     [rbx+0Ch], eax
0x180059a74  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180059a7b  jnz     short loc_180059A9C
0x180059a7d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180059a84  test    rax, rax
0x180059a87  jz      short loc_180059A92
0x180059a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a8e  test    al, al
0x180059a90  jmp     short loc_180059A9A
0x180059a92  call    cs:__imp_IsDebuggerPresent
0x180059a98  test    eax, eax
0x180059a9a  jz      short loc_180059AA2
0x180059a9c  test    byte ptr [rbx+4], 2
0x180059aa0  jz      short loc_180059AC6
0x180059aa2  mov     rax, cs:g_pfnResultLoggingCallback
0x180059aa9  test    rax, rax
0x180059aac  jz      short loc_180059B0A
0x180059aae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180059ab5  jnz     short loc_180059B0A
0x180059ab7  xor     r8d, r8d
0x180059aba  xor     edx, edx
0x180059abc  mov     rcx, rbx
0x180059abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ac4  jmp     short loc_180059B0A
0x180059ac6  mov     rax, cs:g_pfnResultLoggingCallback
0x180059acd  mov     ebp, 800h
0x180059ad2  test    rax, rax
0x180059ad5  jz      short loc_180059AEE
0x180059ad7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180059ade  jnz     short loc_180059AEE
0x180059ae0  mov     r8d, ebp
0x180059ae3  mov     rdx, rsi
0x180059ae6  mov     rcx, rbx
0x180059ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059aee  cmp     [rsi], di
0x180059af1  jnz     short loc_180059B01
0x180059af3  mov     r8, rbx; unsigned __int64
0x180059af6  mov     rdx, rbp; unsigned __int16 *
0x180059af9  mov     rcx, rsi; this
0x180059afc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180059b01  mov     rcx, rsi; lpOutputString
0x180059b04  call    cs:__imp_OutputDebugStringW
0x180059b0a  test    byte ptr [rbx+4], 4
0x180059b0e  jnz     short loc_180059B19
0x180059b10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180059b17  jz      short loc_180059B2A
0x180059b19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180059b20  test    rax, rax
0x180059b23  jz      short loc_180059B2A
0x180059b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b2a  mov     rbx, [rsp+78h+arg_10]
0x180059b32  add     rsp, 40h
0x180059b36  pop     r15
0x180059b38  pop     r14
0x180059b3a  pop     r13
0x180059b3c  pop     r12
0x180059b3e  pop     rdi
0x180059b3f  pop     rsi
0x180059b40  pop     rbp
0x180059b41  retn
0x180059b42  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
