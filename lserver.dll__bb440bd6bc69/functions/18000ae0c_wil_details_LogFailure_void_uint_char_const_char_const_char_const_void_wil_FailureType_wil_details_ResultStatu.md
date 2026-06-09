# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18000ae0c`
- end: `0x18000b114`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005f80`

## callees

- `0x18000599c`
- `0x180009574`
- `0x18000a33c`
- `0x18000ae0c`
- `0x18000bc6c`
- `0x18000bc90`
- `0x18000bca4`
- `0x18000bcc4`
- `0x18000e748`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000b0c8`
- `KERNEL32!OutputDebugStringW` at `0x18000b0c8`
- `KERNEL32!IsDebuggerPresent` at `0x18000b04f`
- `KERNEL32!IsDebuggerPresent` at `0x18000b04f`
- `KERNEL32!GetCurrentThreadId` at `0x18000af2b`
- `KERNEL32!GetCurrentThreadId` at `0x18000af2b`

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
        unsigned __int64 a15)
{
  unsigned int v17; // edi
  int v18; // esi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  int v22; // edx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  v18 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v17, a2);
        break;
      case 2:
        if ( (v17 & 0x80000000) == 0 )
        {
          v17 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v17, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v17, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v17, a2);
  }
  v18 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  *(_DWORD *)(a15 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 64) = a2;
  *(_DWORD *)(a15 + 68) = v18;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v22);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v26)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18000ae0c  mov     [rsp+arg_10], rbx
0x18000ae11  mov     [rsp+arg_8], edx
0x18000ae15  mov     [rsp+arg_0], rcx
0x18000ae1a  push    rbp
0x18000ae1b  push    rsi
0x18000ae1c  push    rdi
0x18000ae1d  push    r12
0x18000ae1f  push    r13
0x18000ae21  push    r14
0x18000ae23  push    r15
0x18000ae25  sub     rsp, 40h
0x18000ae29  mov     r12, r9
0x18000ae2c  mov     r13, r8
0x18000ae2f  mov     r10, rcx
0x18000ae32  xor     r8d, r8d
0x18000ae35  mov     r14, [rsp+78h+lpOutputString]
0x18000ae3d  mov     [r14], r8w
0x18000ae41  mov     rax, [rsp+78h+arg_60]
0x18000ae49  mov     [rax], r8b
0x18000ae4c  mov     rbx, [rsp+78h+arg_70]
0x18000ae54  mov     r15, [rsp+78h+arg_38]
0x18000ae5c  mov     edi, [r15]
0x18000ae5f  mov     [rbx+8], edi
0x18000ae62  mov     eax, [r15+4]
0x18000ae66  mov     [rbx+0Ch], eax
0x18000ae69  mov     esi, r8d
0x18000ae6c  mov     ebp, [rsp+78h+arg_30]
0x18000ae73  mov     ecx, ebp
0x18000ae75  test    ebp, ebp
0x18000ae77  jz      short loc_18000AEE2
0x18000ae79  sub     ecx, 1
0x18000ae7c  jz      short loc_18000AED9
0x18000ae7e  sub     ecx, 1
0x18000ae81  jz      short loc_18000AE91
0x18000ae83  cmp     ecx, 1
0x18000ae86  jnz     short loc_18000AEEB
0x18000ae88  mov     ecx, edi; this
0x18000ae8a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ae8f  jmp     short loc_18000AEE9
0x18000ae91  test    edi, edi
0x18000ae93  js      short loc_18000AED0
0x18000ae95  mov     edi, 8007029Ch
0x18000ae9a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ae9e  mov     rax, [rsp+78h+arg_28]
0x18000aea6  mov     [rsp+78h+var_50], rax; __int64
0x18000aeab  mov     rax, [rsp+78h+arg_20]
0x18000aeb3  mov     [rsp+78h+var_58], rax; __int64
0x18000aeb8  mov     r8, r13; int
0x18000aebb  mov     rcx, r10; int
0x18000aebe  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000aec3  mov     [rbx+8], edi
0x18000aec6  mov     ecx, edi; this
0x18000aec8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000aecd  mov     [rbx+0Ch], eax
0x18000aed0  mov     ecx, edi; this
0x18000aed2  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000aed7  jmp     short loc_18000AEE9
0x18000aed9  mov     ecx, edi; this
0x18000aedb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000aee0  jmp     short loc_18000AEE9
0x18000aee2  mov     ecx, edi; this
0x18000aee4  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000aee9  mov     esi, eax
0x18000aeeb  mov     [rbx], ebp
0x18000aeed  xor     edi, edi
0x18000aeef  mov     [rbx+4], edi
0x18000aef2  cmp     dword ptr [r15+8], 1
0x18000aef7  jnz     short loc_18000AF00
0x18000aef9  mov     dword ptr [rbx+4], 8
0x18000af00  mov     eax, 1
0x18000af05  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000af0d  inc     eax
0x18000af0f  mov     [rbx+10h], eax
0x18000af12  mov     rax, [rsp+78h+arg_40]
0x18000af1a  test    rax, rax
0x18000af1d  jz      short loc_18000AF24
0x18000af1f  cmp     [rax], di
0x18000af22  jnz     short loc_18000AF27
0x18000af24  mov     rax, rdi
0x18000af27  mov     [rbx+18h], rax
0x18000af2b  call    cs:__imp_GetCurrentThreadId
0x18000af32  nop     dword ptr [rax+rax+00h]
0x18000af37  mov     [rbx+20h], eax
0x18000af3a  mov     [rbx+38h], r13
0x18000af3e  mov     eax, [rsp+78h+arg_8]
0x18000af45  mov     [rbx+40h], eax
0x18000af48  mov     [rbx+44h], esi
0x18000af4b  mov     rax, [rsp+78h+arg_20]
0x18000af53  mov     [rbx+28h], rax
0x18000af57  mov     [rbx+30h], r12
0x18000af5b  mov     rax, [rsp+78h+arg_28]
0x18000af63  mov     [rbx+88h], rax
0x18000af6a  mov     rax, [rsp+78h+arg_0]
0x18000af72  mov     [rbx+90h], rax
0x18000af79  mov     [rbx+48h], rdi
0x18000af7d  xorps   xmm0, xmm0
0x18000af80  xor     eax, eax
0x18000af82  movups  xmmword ptr [rbx+68h], xmm0
0x18000af86  mov     [rbx+78h], rax
0x18000af8a  movups  xmmword ptr [rbx+50h], xmm0
0x18000af8e  mov     [rbx+60h], rax
0x18000af92  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000af99  test    rax, rax
0x18000af9c  jz      short loc_18000AFA5
0x18000af9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afa3  jmp     short loc_18000AFA8
0x18000afa5  mov     rax, rdi
0x18000afa8  mov     [rbx+80h], rax
0x18000afaf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000afb6  test    rax, rax
0x18000afb9  jz      short loc_18000AFC3
0x18000afbb  mov     rcx, rbx
0x18000afbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afc3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000afca  test    rax, rax
0x18000afcd  jz      short loc_18000AFE5
0x18000afcf  mov     r8d, 400h
0x18000afd5  mov     rdx, [rsp+78h+arg_60]
0x18000afdd  mov     rcx, rbx
0x18000afe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afe5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000afec  test    rax, rax
0x18000afef  jz      short loc_18000AFF9
0x18000aff1  mov     rcx, rbx
0x18000aff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aff9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b000  test    rax, rax
0x18000b003  jz      short loc_18000B013
0x18000b005  test    byte ptr [rbx+4], 2
0x18000b009  jnz     short loc_18000B013
0x18000b00b  mov     rcx, rbx
0x18000b00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b013  cmp     [rbx+8], edi
0x18000b016  jl      short loc_18000B031
0x18000b018  cmp     ebp, 3
0x18000b01b  jnz     loc_18000B10E
0x18000b021  mov     ecx, 8000FFFFh; this
0x18000b026  mov     [rbx+8], ecx
0x18000b029  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b02e  mov     [rbx+0Ch], eax
0x18000b031  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000b038  jnz     short loc_18000B05F
0x18000b03a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b041  test    rax, rax
0x18000b044  jz      short loc_18000B04F
0x18000b046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b04b  test    al, al
0x18000b04d  jmp     short loc_18000B05D
0x18000b04f  call    cs:__imp_IsDebuggerPresent
0x18000b056  nop     dword ptr [rax+rax+00h]
0x18000b05b  test    eax, eax
0x18000b05d  jz      short loc_18000B065
0x18000b05f  test    byte ptr [rbx+4], 2
0x18000b063  jz      short loc_18000B089
0x18000b065  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b06c  test    rax, rax
0x18000b06f  jz      short loc_18000B0D4
0x18000b071  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b078  jnz     short loc_18000B0D4
0x18000b07a  xor     r8d, r8d
0x18000b07d  xor     edx, edx
0x18000b07f  mov     rcx, rbx
0x18000b082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b087  jmp     short loc_18000B0D4
0x18000b089  mov     esi, 800h
0x18000b08e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b095  test    rax, rax
0x18000b098  jz      short loc_18000B0B1
0x18000b09a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b0a1  jnz     short loc_18000B0B1
0x18000b0a3  mov     r8d, esi
0x18000b0a6  mov     rdx, r14
0x18000b0a9  mov     rcx, rbx
0x18000b0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b1  cmp     [r14], di
0x18000b0b5  jnz     short loc_18000B0C5
0x18000b0b7  mov     r8, rbx; unsigned __int64
0x18000b0ba  mov     rdx, rsi; unsigned __int16 *
0x18000b0bd  mov     rcx, r14; this
0x18000b0c0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b0c5  mov     rcx, r14; lpOutputString
0x18000b0c8  call    cs:__imp_OutputDebugStringW
0x18000b0cf  nop     dword ptr [rax+rax+00h]
0x18000b0d4  test    byte ptr [rbx+4], 4
0x18000b0d8  jnz     short loc_18000B0E3
0x18000b0da  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000b0e1  jz      short loc_18000B0F5
0x18000b0e3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b0ea  test    rax, rax
0x18000b0ed  jz      short loc_18000B0F5
0x18000b0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0f4  nop
0x18000b0f5  mov     rbx, [rsp+78h+arg_10]
0x18000b0fd  add     rsp, 40h
0x18000b101  pop     r15
0x18000b103  pop     r14
0x18000b105  pop     r13
0x18000b107  pop     r12
0x18000b109  pop     rdi
0x18000b10a  pop     rsi
0x18000b10b  pop     rbp
0x18000b10c  retn
0x18000b10e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
