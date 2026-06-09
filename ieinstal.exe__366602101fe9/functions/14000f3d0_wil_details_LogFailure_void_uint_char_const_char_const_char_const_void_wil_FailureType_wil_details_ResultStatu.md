# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000f3d0`
- end: `0x14000f6db`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000e360`

## callees

- `0x14000abc0`
- `0x14000dd78`
- `0x14000eb2c`
- `0x14000f1fc`
- `0x14000f3d0`
- `0x14000fbbc`
- `0x14000fbdc`
- `0x14000fbfc`
- `0x1400104ac`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000f4f3`
- `KERNEL32!GetCurrentThreadId` at `0x14000f4f3`
- `KERNEL32!IsDebuggerPresent` at `0x14000f618`
- `KERNEL32!IsDebuggerPresent` at `0x14000f618`
- `KERNEL32!OutputDebugStringW` at `0x14000f690`
- `KERNEL32!OutputDebugStringW` at `0x14000f690`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x14000f3d0  mov     [rsp+arg_10], rbx
0x14000f3d5  mov     [rsp+arg_8], edx
0x14000f3d9  mov     [rsp+arg_0], rcx
0x14000f3de  push    rbp
0x14000f3df  push    rsi
0x14000f3e0  push    rdi
0x14000f3e1  push    r12
0x14000f3e3  push    r13
0x14000f3e5  push    r14
0x14000f3e7  push    r15
0x14000f3e9  sub     rsp, 40h
0x14000f3ed  mov     r14, [rsp+78h+arg_38]
0x14000f3f5  xor     eax, eax
0x14000f3f7  mov     rbx, [rsp+78h+arg_78]
0x14000f3ff  xor     ebp, ebp
0x14000f401  mov     r15d, [rsp+78h+arg_30]
0x14000f409  mov     r10, rcx
0x14000f40c  mov     rsi, [rsp+78h+lpOutputString]
0x14000f414  mov     r12, r9
0x14000f417  mov     r13, r8
0x14000f41a  mov     ecx, r15d
0x14000f41d  mov     [rsi], ax
0x14000f420  mov     rax, [rsp+78h+arg_60]
0x14000f428  mov     byte ptr [rax], 0
0x14000f42b  mov     edi, [r14]
0x14000f42e  mov     [rbx+8], edi
0x14000f431  mov     eax, [r14+4]
0x14000f435  mov     [rbx+0Ch], eax
0x14000f438  test    r15d, r15d
0x14000f43b  jz      short loc_14000F4A3
0x14000f43d  sub     ecx, 1
0x14000f440  jz      short loc_14000F49A
0x14000f442  sub     ecx, 1
0x14000f445  jz      short loc_14000F455
0x14000f447  cmp     ecx, 1
0x14000f44a  jnz     short loc_14000F4AC
0x14000f44c  mov     ecx, edi; this
0x14000f44e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000f453  jmp     short loc_14000F4AA
0x14000f455  test    edi, edi
0x14000f457  js      short loc_14000F491
0x14000f459  mov     rax, [rsp+78h+arg_28]
0x14000f461  mov     edi, 8007029Ch
0x14000f466  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000f46a  mov     rcx, r10; int
0x14000f46d  mov     [rsp+78h+var_50], rax; __int64
0x14000f472  mov     rax, [rsp+78h+arg_20]
0x14000f47a  mov     [rsp+78h+var_58], rax; __int64
0x14000f47f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000f484  mov     ecx, edi; this
0x14000f486  mov     [rbx+8], edi
0x14000f489  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000f48e  mov     [rbx+0Ch], eax
0x14000f491  mov     ecx, edi; this
0x14000f493  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000f498  jmp     short loc_14000F4AA
0x14000f49a  mov     ecx, edi; this
0x14000f49c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000f4a1  jmp     short loc_14000F4AA
0x14000f4a3  mov     ecx, edi; this
0x14000f4a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000f4aa  mov     ebp, eax
0x14000f4ac  mov     eax, [rsp+78h+arg_70]
0x14000f4b3  mov     [rbx+4], eax
0x14000f4b6  mov     [rbx], r15d
0x14000f4b9  cmp     dword ptr [r14+8], 1
0x14000f4be  jnz     short loc_14000F4C6
0x14000f4c0  or      eax, 8
0x14000f4c3  mov     [rbx+4], eax
0x14000f4c6  mov     eax, 1
0x14000f4cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000f4d3  inc     eax
0x14000f4d5  xor     edi, edi
0x14000f4d7  mov     [rbx+10h], eax
0x14000f4da  mov     rax, [rsp+78h+arg_40]
0x14000f4e2  test    rax, rax
0x14000f4e5  jz      short loc_14000F4EC
0x14000f4e7  cmp     [rax], di
0x14000f4ea  jnz     short loc_14000F4EF
0x14000f4ec  mov     rax, rdi
0x14000f4ef  mov     [rbx+18h], rax
0x14000f4f3  call    cs:__imp_GetCurrentThreadId
0x14000f4fa  nop     dword ptr [rax+rax+00h]
0x14000f4ff  mov     [rbx+38h], r13
0x14000f503  xorps   xmm0, xmm0
0x14000f506  mov     [rbx+20h], eax
0x14000f509  mov     eax, [rsp+78h+arg_8]
0x14000f510  mov     [rbx+40h], eax
0x14000f513  mov     rax, [rsp+78h+arg_20]
0x14000f51b  mov     [rbx+28h], rax
0x14000f51f  mov     rax, [rsp+78h+arg_28]
0x14000f527  mov     [rbx+88h], rax
0x14000f52e  mov     rax, [rsp+78h+arg_0]
0x14000f536  mov     [rbx+90h], rax
0x14000f53d  xor     eax, eax
0x14000f53f  mov     [rbx+44h], ebp
0x14000f542  mov     [rbx+30h], r12
0x14000f546  mov     [rbx+48h], rdi
0x14000f54a  movups  xmmword ptr [rbx+68h], xmm0
0x14000f54e  mov     [rbx+78h], rax
0x14000f552  movups  xmmword ptr [rbx+50h], xmm0
0x14000f556  mov     [rbx+60h], rax
0x14000f55a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000f561  test    rax, rax
0x14000f564  jz      short loc_14000F56D
0x14000f566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f56b  jmp     short loc_14000F570
0x14000f56d  mov     rax, rdi
0x14000f570  mov     [rbx+80h], rax
0x14000f577  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000f57e  test    rax, rax
0x14000f581  jz      short loc_14000F58B
0x14000f583  mov     rcx, rbx
0x14000f586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f58b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000f592  test    rax, rax
0x14000f595  jz      short loc_14000F5AD
0x14000f597  mov     rdx, [rsp+78h+arg_60]
0x14000f59f  mov     r8d, 400h
0x14000f5a5  mov     rcx, rbx
0x14000f5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5ad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000f5b4  test    rax, rax
0x14000f5b7  jz      short loc_14000F5C1
0x14000f5b9  mov     rcx, rbx
0x14000f5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5c1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000f5c8  test    rax, rax
0x14000f5cb  jz      short loc_14000F5DB
0x14000f5cd  test    byte ptr [rbx+4], 2
0x14000f5d1  jnz     short loc_14000F5DB
0x14000f5d3  mov     rcx, rbx
0x14000f5d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5db  cmp     [rbx+8], edi
0x14000f5de  jl      short loc_14000F5FA
0x14000f5e0  cmp     r15d, 3
0x14000f5e4  jnz     loc_14000F6D5
0x14000f5ea  mov     ecx, 8000FFFFh; this
0x14000f5ef  mov     [rbx+8], ecx
0x14000f5f2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000f5f7  mov     [rbx+0Ch], eax
0x14000f5fa  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000f601  jnz     short loc_14000F628
0x14000f603  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000f60a  test    rax, rax
0x14000f60d  jz      short loc_14000F618
0x14000f60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f614  test    al, al
0x14000f616  jmp     short loc_14000F626
0x14000f618  call    cs:__imp_IsDebuggerPresent
0x14000f61f  nop     dword ptr [rax+rax+00h]
0x14000f624  test    eax, eax
0x14000f626  jz      short loc_14000F62E
0x14000f628  test    byte ptr [rbx+4], 2
0x14000f62c  jz      short loc_14000F652
0x14000f62e  mov     rax, cs:g_pfnResultLoggingCallback
0x14000f635  test    rax, rax
0x14000f638  jz      short loc_14000F69C
0x14000f63a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000f641  jnz     short loc_14000F69C
0x14000f643  xor     r8d, r8d
0x14000f646  xor     edx, edx
0x14000f648  mov     rcx, rbx
0x14000f64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f650  jmp     short loc_14000F69C
0x14000f652  mov     rax, cs:g_pfnResultLoggingCallback
0x14000f659  mov     ebp, 800h
0x14000f65e  test    rax, rax
0x14000f661  jz      short loc_14000F67A
0x14000f663  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000f66a  jnz     short loc_14000F67A
0x14000f66c  mov     r8d, ebp
0x14000f66f  mov     rdx, rsi
0x14000f672  mov     rcx, rbx
0x14000f675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f67a  cmp     [rsi], di
0x14000f67d  jnz     short loc_14000F68D
0x14000f67f  mov     r8, rbx; unsigned __int64
0x14000f682  mov     rdx, rbp; unsigned __int16 *
0x14000f685  mov     rcx, rsi; this
0x14000f688  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000f68d  mov     rcx, rsi; lpOutputString
0x14000f690  call    cs:__imp_OutputDebugStringW
0x14000f697  nop     dword ptr [rax+rax+00h]
0x14000f69c  test    byte ptr [rbx+4], 4
0x14000f6a0  jnz     short loc_14000F6AB
0x14000f6a2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000f6a9  jz      short loc_14000F6BC
0x14000f6ab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000f6b2  test    rax, rax
0x14000f6b5  jz      short loc_14000F6BC
0x14000f6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6bc  mov     rbx, [rsp+78h+arg_10]
0x14000f6c4  add     rsp, 40h
0x14000f6c8  pop     r15
0x14000f6ca  pop     r14
0x14000f6cc  pop     r13
0x14000f6ce  pop     r12
0x14000f6d0  pop     rdi
0x14000f6d1  pop     rsi
0x14000f6d2  pop     rbp
0x14000f6d3  retn
0x14000f6d5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
