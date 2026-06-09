# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005060`
- end: `0x180005359`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003814`

## callees

- `0x180003220`
- `0x1800046f4`
- `0x180004e9c`
- `0x180005060`
- `0x1800055e4`
- `0x180005600`
- `0x180005614`
- `0x180005630`
- `0x1800067ac`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005183`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005314`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005314`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800052a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800052a2`

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
0x180005060  mov     [rsp+arg_10], rbx
0x180005065  mov     [rsp+arg_8], edx
0x180005069  mov     [rsp+arg_0], rcx
0x18000506e  push    rbp
0x18000506f  push    rsi
0x180005070  push    rdi
0x180005071  push    r12
0x180005073  push    r13
0x180005075  push    r14
0x180005077  push    r15
0x180005079  sub     rsp, 40h
0x18000507d  mov     r12, r9
0x180005080  mov     r13, r8
0x180005083  mov     r10, rcx
0x180005086  xor     eax, eax
0x180005088  mov     rsi, [rsp+78h+lpOutputString]
0x180005090  mov     [rsi], ax
0x180005093  mov     rax, [rsp+78h+arg_60]
0x18000509b  mov     byte ptr [rax], 0
0x18000509e  mov     r14, [rsp+78h+arg_38]
0x1800050a6  mov     edi, [r14]
0x1800050a9  mov     rbx, [rsp+78h+arg_78]
0x1800050b1  mov     [rbx+8], edi
0x1800050b4  mov     eax, [r14+4]
0x1800050b8  mov     [rbx+0Ch], eax
0x1800050bb  xor     ebp, ebp
0x1800050bd  mov     r15d, [rsp+78h+arg_30]
0x1800050c5  mov     ecx, r15d
0x1800050c8  test    r15d, r15d
0x1800050cb  jz      short loc_180005133
0x1800050cd  sub     ecx, 1
0x1800050d0  jz      short loc_18000512A
0x1800050d2  sub     ecx, 1
0x1800050d5  jz      short loc_1800050E5
0x1800050d7  cmp     ecx, 1
0x1800050da  jnz     short loc_18000513C
0x1800050dc  mov     ecx, edi; this
0x1800050de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800050e3  jmp     short loc_18000513A
0x1800050e5  test    edi, edi
0x1800050e7  js      short loc_180005121
0x1800050e9  mov     edi, 8007029Ch
0x1800050ee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800050f2  mov     rax, [rsp+78h+arg_28]
0x1800050fa  mov     [rsp+78h+var_50], rax; __int64
0x1800050ff  mov     rax, [rsp+78h+arg_20]
0x180005107  mov     [rsp+78h+var_58], rax; __int64
0x18000510c  mov     rcx, r10; int
0x18000510f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005114  mov     [rbx+8], edi
0x180005117  mov     ecx, edi; this
0x180005119  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000511e  mov     [rbx+0Ch], eax
0x180005121  mov     ecx, edi; this
0x180005123  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005128  jmp     short loc_18000513A
0x18000512a  mov     ecx, edi; this
0x18000512c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005131  jmp     short loc_18000513A
0x180005133  mov     ecx, edi; this
0x180005135  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000513a  mov     ebp, eax
0x18000513c  mov     [rbx], r15d
0x18000513f  mov     eax, [rsp+78h+arg_70]
0x180005146  mov     [rbx+4], eax
0x180005149  cmp     dword ptr [r14+8], 1
0x18000514e  jnz     short loc_180005156
0x180005150  or      eax, 8
0x180005153  mov     [rbx+4], eax
0x180005156  mov     eax, 1
0x18000515b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005163  inc     eax
0x180005165  mov     [rbx+10h], eax
0x180005168  mov     rax, [rsp+78h+arg_40]
0x180005170  xor     edi, edi
0x180005172  test    rax, rax
0x180005175  jz      short loc_18000517C
0x180005177  cmp     [rax], di
0x18000517a  jnz     short loc_18000517F
0x18000517c  mov     rax, rdi
0x18000517f  mov     [rbx+18h], rax
0x180005183  call    cs:__imp_GetCurrentThreadId
0x180005189  mov     [rbx+20h], eax
0x18000518c  mov     [rbx+38h], r13
0x180005190  mov     eax, [rsp+78h+arg_8]
0x180005197  mov     [rbx+40h], eax
0x18000519a  mov     [rbx+44h], ebp
0x18000519d  mov     rax, [rsp+78h+arg_20]
0x1800051a5  mov     [rbx+28h], rax
0x1800051a9  mov     [rbx+30h], r12
0x1800051ad  mov     rax, [rsp+78h+arg_28]
0x1800051b5  mov     [rbx+88h], rax
0x1800051bc  mov     rax, [rsp+78h+arg_0]
0x1800051c4  mov     [rbx+90h], rax
0x1800051cb  mov     [rbx+48h], rdi
0x1800051cf  xorps   xmm0, xmm0
0x1800051d2  xor     eax, eax
0x1800051d4  movups  xmmword ptr [rbx+68h], xmm0
0x1800051d8  mov     [rbx+78h], rax
0x1800051dc  movups  xmmword ptr [rbx+50h], xmm0
0x1800051e0  mov     [rbx+60h], rax
0x1800051e4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800051eb  test    rax, rax
0x1800051ee  jz      short loc_1800051F7
0x1800051f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f5  jmp     short loc_1800051FA
0x1800051f7  mov     rax, rdi
0x1800051fa  mov     [rbx+80h], rax
0x180005201  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005208  test    rax, rax
0x18000520b  jz      short loc_180005215
0x18000520d  mov     rcx, rbx
0x180005210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005215  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000521c  test    rax, rax
0x18000521f  jz      short loc_180005237
0x180005221  mov     r8d, 400h
0x180005227  mov     rdx, [rsp+78h+arg_60]
0x18000522f  mov     rcx, rbx
0x180005232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005237  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000523e  test    rax, rax
0x180005241  jz      short loc_18000524B
0x180005243  mov     rcx, rbx
0x180005246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000524b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005252  test    rax, rax
0x180005255  jz      short loc_180005265
0x180005257  test    byte ptr [rbx+4], 2
0x18000525b  jnz     short loc_180005265
0x18000525d  mov     rcx, rbx
0x180005260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005265  cmp     [rbx+8], edi
0x180005268  jl      short loc_180005284
0x18000526a  cmp     r15d, 3
0x18000526e  jnz     loc_180005353
0x180005274  mov     ecx, 8000FFFFh; this
0x180005279  mov     [rbx+8], ecx
0x18000527c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005281  mov     [rbx+0Ch], eax
0x180005284  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000528b  jnz     short loc_1800052AC
0x18000528d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005294  test    rax, rax
0x180005297  jz      short loc_1800052A2
0x180005299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000529e  test    al, al
0x1800052a0  jmp     short loc_1800052AA
0x1800052a2  call    cs:__imp_IsDebuggerPresent
0x1800052a8  test    eax, eax
0x1800052aa  jz      short loc_1800052B2
0x1800052ac  test    byte ptr [rbx+4], 2
0x1800052b0  jz      short loc_1800052D6
0x1800052b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052b9  test    rax, rax
0x1800052bc  jz      short loc_18000531A
0x1800052be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800052c5  jnz     short loc_18000531A
0x1800052c7  xor     r8d, r8d
0x1800052ca  xor     edx, edx
0x1800052cc  mov     rcx, rbx
0x1800052cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d4  jmp     short loc_18000531A
0x1800052d6  mov     ebp, 800h
0x1800052db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052e2  test    rax, rax
0x1800052e5  jz      short loc_1800052FE
0x1800052e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800052ee  jnz     short loc_1800052FE
0x1800052f0  mov     r8d, ebp
0x1800052f3  mov     rdx, rsi
0x1800052f6  mov     rcx, rbx
0x1800052f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052fe  cmp     [rsi], di
0x180005301  jnz     short loc_180005311
0x180005303  mov     r8, rbx; unsigned __int64
0x180005306  mov     rdx, rbp; unsigned __int16 *
0x180005309  mov     rcx, rsi; this
0x18000530c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005311  mov     rcx, rsi; lpOutputString
0x180005314  call    cs:__imp_OutputDebugStringW
0x18000531a  test    byte ptr [rbx+4], 4
0x18000531e  jnz     short loc_180005329
0x180005320  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005327  jz      short loc_18000533B
0x180005329  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005330  test    rax, rax
0x180005333  jz      short loc_18000533B
0x180005335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000533a  nop
0x18000533b  mov     rbx, [rsp+78h+arg_10]
0x180005343  add     rsp, 40h
0x180005347  pop     r15
0x180005349  pop     r14
0x18000534b  pop     r13
0x18000534d  pop     r12
0x18000534f  pop     rdi
0x180005350  pop     rsi
0x180005351  pop     rbp
0x180005352  retn
0x180005353  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
