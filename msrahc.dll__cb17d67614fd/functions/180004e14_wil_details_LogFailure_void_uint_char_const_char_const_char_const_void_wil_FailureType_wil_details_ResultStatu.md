# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004e14`
- end: `0x18000510d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180002974`
- `0x180002cb8`

## callees

- `0x1800028b4`
- `0x1800042f4`
- `0x180004b14`
- `0x180004e14`
- `0x180005a2c`
- `0x180005a50`
- `0x180005bd4`
- `0x180005bf0`
- `0x1800076d8`
- `0x18001c010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180005056`
- `KERNEL32!IsDebuggerPresent` at `0x180005056`
- `KERNEL32!OutputDebugStringW` at `0x1800050c8`
- `KERNEL32!OutputDebugStringW` at `0x1800050c8`
- `KERNEL32!GetCurrentThreadId` at `0x180004f37`
- `KERNEL32!GetCurrentThreadId` at `0x180004f37`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180004e14  mov     [rsp+arg_10], rbx
0x180004e19  mov     [rsp+arg_8], edx
0x180004e1d  mov     [rsp+arg_0], rcx
0x180004e22  push    rbp
0x180004e23  push    rsi
0x180004e24  push    rdi
0x180004e25  push    r12
0x180004e27  push    r13
0x180004e29  push    r14
0x180004e2b  push    r15
0x180004e2d  sub     rsp, 40h
0x180004e31  mov     r12, r9
0x180004e34  mov     r13, r8
0x180004e37  mov     r10, rcx
0x180004e3a  xor     eax, eax
0x180004e3c  mov     rsi, [rsp+78h+lpOutputString]
0x180004e44  mov     [rsi], ax
0x180004e47  mov     rax, [rsp+78h+arg_60]
0x180004e4f  mov     byte ptr [rax], 0
0x180004e52  mov     r14, [rsp+78h+arg_38]
0x180004e5a  mov     edi, [r14]
0x180004e5d  mov     rbx, [rsp+78h+arg_78]
0x180004e65  mov     [rbx+8], edi
0x180004e68  mov     eax, [r14+4]
0x180004e6c  mov     [rbx+0Ch], eax
0x180004e6f  xor     ebp, ebp
0x180004e71  mov     r15d, [rsp+78h+arg_30]
0x180004e79  mov     ecx, r15d
0x180004e7c  test    r15d, r15d
0x180004e7f  jz      short loc_180004EE7
0x180004e81  sub     ecx, 1
0x180004e84  jz      short loc_180004EDE
0x180004e86  sub     ecx, 1
0x180004e89  jz      short loc_180004E99
0x180004e8b  cmp     ecx, 1
0x180004e8e  jnz     short loc_180004EF0
0x180004e90  mov     ecx, edi; this
0x180004e92  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004e97  jmp     short loc_180004EEE
0x180004e99  test    edi, edi
0x180004e9b  js      short loc_180004ED5
0x180004e9d  mov     edi, 8007029Ch
0x180004ea2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004ea6  mov     rax, [rsp+78h+arg_28]
0x180004eae  mov     [rsp+78h+var_50], rax; __int64
0x180004eb3  mov     rax, [rsp+78h+arg_20]
0x180004ebb  mov     [rsp+78h+var_58], rax; __int64
0x180004ec0  mov     rcx, r10; int
0x180004ec3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004ec8  mov     [rbx+8], edi
0x180004ecb  mov     ecx, edi; this
0x180004ecd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004ed2  mov     [rbx+0Ch], eax
0x180004ed5  mov     ecx, edi; this
0x180004ed7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004edc  jmp     short loc_180004EEE
0x180004ede  mov     ecx, edi; this
0x180004ee0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004ee5  jmp     short loc_180004EEE
0x180004ee7  mov     ecx, edi; this
0x180004ee9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004eee  mov     ebp, eax
0x180004ef0  mov     [rbx], r15d
0x180004ef3  mov     eax, [rsp+78h+arg_70]
0x180004efa  mov     [rbx+4], eax
0x180004efd  cmp     dword ptr [r14+8], 1
0x180004f02  jnz     short loc_180004F0A
0x180004f04  or      eax, 8
0x180004f07  mov     [rbx+4], eax
0x180004f0a  mov     eax, 1
0x180004f0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f17  inc     eax
0x180004f19  mov     [rbx+10h], eax
0x180004f1c  mov     rax, [rsp+78h+arg_40]
0x180004f24  xor     edi, edi
0x180004f26  test    rax, rax
0x180004f29  jz      short loc_180004F30
0x180004f2b  cmp     [rax], di
0x180004f2e  jnz     short loc_180004F33
0x180004f30  mov     rax, rdi
0x180004f33  mov     [rbx+18h], rax
0x180004f37  call    cs:__imp_GetCurrentThreadId
0x180004f3d  mov     [rbx+20h], eax
0x180004f40  mov     [rbx+38h], r13
0x180004f44  mov     eax, [rsp+78h+arg_8]
0x180004f4b  mov     [rbx+40h], eax
0x180004f4e  mov     [rbx+44h], ebp
0x180004f51  mov     rax, [rsp+78h+arg_20]
0x180004f59  mov     [rbx+28h], rax
0x180004f5d  mov     [rbx+30h], r12
0x180004f61  mov     rax, [rsp+78h+arg_28]
0x180004f69  mov     [rbx+88h], rax
0x180004f70  mov     rax, [rsp+78h+arg_0]
0x180004f78  mov     [rbx+90h], rax
0x180004f7f  mov     [rbx+48h], rdi
0x180004f83  xorps   xmm0, xmm0
0x180004f86  xor     eax, eax
0x180004f88  movups  xmmword ptr [rbx+68h], xmm0
0x180004f8c  mov     [rbx+78h], rax
0x180004f90  movups  xmmword ptr [rbx+50h], xmm0
0x180004f94  mov     [rbx+60h], rax
0x180004f98  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004f9f  test    rax, rax
0x180004fa2  jz      short loc_180004FAB
0x180004fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa9  jmp     short loc_180004FAE
0x180004fab  mov     rax, rdi
0x180004fae  mov     [rbx+80h], rax
0x180004fb5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fbc  test    rax, rax
0x180004fbf  jz      short loc_180004FC9
0x180004fc1  mov     rcx, rbx
0x180004fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004fd0  test    rax, rax
0x180004fd3  jz      short loc_180004FEB
0x180004fd5  mov     r8d, 400h
0x180004fdb  mov     rdx, [rsp+78h+arg_60]
0x180004fe3  mov     rcx, rbx
0x180004fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004feb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ff2  test    rax, rax
0x180004ff5  jz      short loc_180004FFF
0x180004ff7  mov     rcx, rbx
0x180004ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005006  test    rax, rax
0x180005009  jz      short loc_180005019
0x18000500b  test    byte ptr [rbx+4], 2
0x18000500f  jnz     short loc_180005019
0x180005011  mov     rcx, rbx
0x180005014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005019  cmp     [rbx+8], edi
0x18000501c  jl      short loc_180005038
0x18000501e  cmp     r15d, 3
0x180005022  jnz     loc_180005107
0x180005028  mov     ecx, 8000FFFFh; this
0x18000502d  mov     [rbx+8], ecx
0x180005030  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005035  mov     [rbx+0Ch], eax
0x180005038  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000503f  jnz     short loc_180005060
0x180005041  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005048  test    rax, rax
0x18000504b  jz      short loc_180005056
0x18000504d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005052  test    al, al
0x180005054  jmp     short loc_18000505E
0x180005056  call    cs:__imp_IsDebuggerPresent
0x18000505c  test    eax, eax
0x18000505e  jz      short loc_180005066
0x180005060  test    byte ptr [rbx+4], 2
0x180005064  jz      short loc_18000508A
0x180005066  mov     rax, cs:g_pfnResultLoggingCallback
0x18000506d  test    rax, rax
0x180005070  jz      short loc_1800050CE
0x180005072  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005079  jnz     short loc_1800050CE
0x18000507b  xor     r8d, r8d
0x18000507e  xor     edx, edx
0x180005080  mov     rcx, rbx
0x180005083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005088  jmp     short loc_1800050CE
0x18000508a  mov     ebp, 800h
0x18000508f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005096  test    rax, rax
0x180005099  jz      short loc_1800050B2
0x18000509b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800050a2  jnz     short loc_1800050B2
0x1800050a4  mov     r8d, ebp
0x1800050a7  mov     rdx, rsi
0x1800050aa  mov     rcx, rbx
0x1800050ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b2  cmp     [rsi], di
0x1800050b5  jnz     short loc_1800050C5
0x1800050b7  mov     r8, rbx; unsigned __int64
0x1800050ba  mov     rdx, rbp; unsigned __int16 *
0x1800050bd  mov     rcx, rsi; this
0x1800050c0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800050c5  mov     rcx, rsi; lpOutputString
0x1800050c8  call    cs:__imp_OutputDebugStringW
0x1800050ce  test    byte ptr [rbx+4], 4
0x1800050d2  jnz     short loc_1800050DD
0x1800050d4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800050db  jz      short loc_1800050EF
0x1800050dd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800050e4  test    rax, rax
0x1800050e7  jz      short loc_1800050EF
0x1800050e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ee  nop
0x1800050ef  mov     rbx, [rsp+78h+arg_10]
0x1800050f7  add     rsp, 40h
0x1800050fb  pop     r15
0x1800050fd  pop     r14
0x1800050ff  pop     r13
0x180005101  pop     r12
0x180005103  pop     rdi
0x180005104  pop     rsi
0x180005105  pop     rbp
0x180005106  retn
0x180005107  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
