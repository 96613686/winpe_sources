# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008388`
- end: `0x180008689`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003da0`

## callees

- `0x1800037c4`
- `0x180007470`
- `0x180008000`
- `0x180008388`
- `0x180009088`
- `0x1800090b0`
- `0x1800091e4`
- `0x180009200`
- `0x18000f33c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800084b3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008644`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008644`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800085d2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800085d2`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x180008388  mov     rax, rsp
0x18000838b  mov     [rax+10h], edx
0x18000838e  mov     [rax+8], rcx
0x180008392  push    rbp
0x180008393  push    rsi
0x180008394  push    rdi
0x180008395  push    r12
0x180008397  push    r13
0x180008399  push    r14
0x18000839b  push    r15
0x18000839d  sub     rsp, 50h
0x1800083a1  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800083a9  mov     [rax+18h], rbx
0x1800083ad  mov     r12, r9
0x1800083b0  mov     r13, r8
0x1800083b3  mov     r10, rcx
0x1800083b6  xor     eax, eax
0x1800083b8  mov     rsi, [rsp+88h+lpOutputString]
0x1800083c0  mov     [rsi], ax
0x1800083c3  mov     rax, [rsp+88h+arg_60]
0x1800083cb  mov     byte ptr [rax], 0
0x1800083ce  mov     r14, [rsp+88h+arg_38]
0x1800083d6  mov     edi, [r14]
0x1800083d9  mov     rbx, [rsp+88h+arg_78]
0x1800083e1  mov     [rbx+8], edi
0x1800083e4  mov     eax, [r14+4]
0x1800083e8  mov     [rbx+0Ch], eax
0x1800083eb  xor     ebp, ebp
0x1800083ed  mov     r15d, [rsp+88h+arg_30]
0x1800083f5  mov     ecx, r15d
0x1800083f8  test    r15d, r15d
0x1800083fb  jz      short loc_180008463
0x1800083fd  sub     ecx, 1
0x180008400  jz      short loc_18000845A
0x180008402  sub     ecx, 1
0x180008405  jz      short loc_180008415
0x180008407  cmp     ecx, 1
0x18000840a  jnz     short loc_18000846C
0x18000840c  mov     ecx, edi; this
0x18000840e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008413  jmp     short loc_18000846A
0x180008415  test    edi, edi
0x180008417  js      short loc_180008451
0x180008419  mov     edi, 8007029Ch
0x18000841e  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x180008422  mov     rax, [rsp+88h+arg_28]
0x18000842a  mov     [rsp+88h+var_60], rax; __int64
0x18000842f  mov     rax, [rsp+88h+arg_20]
0x180008437  mov     [rsp+88h+var_68], rax; __int64
0x18000843c  mov     rcx, r10; int
0x18000843f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008444  mov     [rbx+8], edi
0x180008447  mov     ecx, edi; this
0x180008449  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000844e  mov     [rbx+0Ch], eax
0x180008451  mov     ecx, edi; this
0x180008453  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008458  jmp     short loc_18000846A
0x18000845a  mov     ecx, edi; this
0x18000845c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008461  jmp     short loc_18000846A
0x180008463  mov     ecx, edi; this
0x180008465  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000846a  mov     ebp, eax
0x18000846c  mov     [rbx], r15d
0x18000846f  mov     eax, [rsp+88h+arg_70]
0x180008476  mov     [rbx+4], eax
0x180008479  cmp     dword ptr [r14+8], 1
0x18000847e  jnz     short loc_180008486
0x180008480  or      eax, 8
0x180008483  mov     [rbx+4], eax
0x180008486  mov     eax, 1
0x18000848b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008493  inc     eax
0x180008495  mov     [rbx+10h], eax
0x180008498  mov     rax, [rsp+88h+arg_40]
0x1800084a0  xor     edi, edi
0x1800084a2  test    rax, rax
0x1800084a5  jz      short loc_1800084AC
0x1800084a7  cmp     [rax], di
0x1800084aa  jnz     short loc_1800084AF
0x1800084ac  mov     rax, rdi
0x1800084af  mov     [rbx+18h], rax
0x1800084b3  call    cs:__imp_GetCurrentThreadId
0x1800084b9  mov     [rbx+20h], eax
0x1800084bc  mov     [rbx+38h], r13
0x1800084c0  mov     eax, [rsp+88h+arg_8]
0x1800084c7  mov     [rbx+40h], eax
0x1800084ca  mov     [rbx+44h], ebp
0x1800084cd  mov     rax, [rsp+88h+arg_20]
0x1800084d5  mov     [rbx+28h], rax
0x1800084d9  mov     [rbx+30h], r12
0x1800084dd  mov     rax, [rsp+88h+arg_28]
0x1800084e5  mov     [rbx+88h], rax
0x1800084ec  mov     rax, [rsp+88h+arg_0]
0x1800084f4  mov     [rbx+90h], rax
0x1800084fb  mov     [rbx+48h], rdi
0x1800084ff  xorps   xmm0, xmm0
0x180008502  xor     eax, eax
0x180008504  movups  xmmword ptr [rbx+68h], xmm0
0x180008508  mov     [rbx+78h], rax
0x18000850c  movups  xmmword ptr [rbx+50h], xmm0
0x180008510  mov     [rbx+60h], rax
0x180008514  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000851b  test    rax, rax
0x18000851e  jz      short loc_180008527
0x180008520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008525  jmp     short loc_18000852A
0x180008527  mov     rax, rdi
0x18000852a  mov     [rbx+80h], rax
0x180008531  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008538  test    rax, rax
0x18000853b  jz      short loc_180008545
0x18000853d  mov     rcx, rbx
0x180008540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008545  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000854c  test    rax, rax
0x18000854f  jz      short loc_180008567
0x180008551  mov     r8d, 400h
0x180008557  mov     rdx, [rsp+88h+arg_60]
0x18000855f  mov     rcx, rbx
0x180008562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008567  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000856e  test    rax, rax
0x180008571  jz      short loc_18000857B
0x180008573  mov     rcx, rbx
0x180008576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008582  test    rax, rax
0x180008585  jz      short loc_180008595
0x180008587  test    byte ptr [rbx+4], 2
0x18000858b  jnz     short loc_180008595
0x18000858d  mov     rcx, rbx
0x180008590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008595  cmp     [rbx+8], edi
0x180008598  jl      short loc_1800085B4
0x18000859a  cmp     r15d, 3
0x18000859e  jnz     loc_180008683
0x1800085a4  mov     ecx, 8000FFFFh; this
0x1800085a9  mov     [rbx+8], ecx
0x1800085ac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800085b1  mov     [rbx+0Ch], eax
0x1800085b4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800085bb  jnz     short loc_1800085DC
0x1800085bd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800085c4  test    rax, rax
0x1800085c7  jz      short loc_1800085D2
0x1800085c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ce  test    al, al
0x1800085d0  jmp     short loc_1800085DA
0x1800085d2  call    cs:__imp_IsDebuggerPresent
0x1800085d8  test    eax, eax
0x1800085da  jz      short loc_1800085E2
0x1800085dc  test    byte ptr [rbx+4], 2
0x1800085e0  jz      short loc_180008606
0x1800085e2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800085e9  test    rax, rax
0x1800085ec  jz      short loc_18000864A
0x1800085ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800085f5  jnz     short loc_18000864A
0x1800085f7  xor     r8d, r8d
0x1800085fa  xor     edx, edx
0x1800085fc  mov     rcx, rbx
0x1800085ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008604  jmp     short loc_18000864A
0x180008606  mov     ebp, 800h
0x18000860b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008612  test    rax, rax
0x180008615  jz      short loc_18000862E
0x180008617  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000861e  jnz     short loc_18000862E
0x180008620  mov     r8d, ebp
0x180008623  mov     rdx, rsi
0x180008626  mov     rcx, rbx
0x180008629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000862e  cmp     [rsi], di
0x180008631  jnz     short loc_180008641
0x180008633  mov     r8, rbx; unsigned __int64
0x180008636  mov     rdx, rbp; unsigned __int16 *
0x180008639  mov     rcx, rsi; Buffer
0x18000863c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008641  mov     rcx, rsi; lpOutputString
0x180008644  call    cs:__imp_OutputDebugStringW
0x18000864a  test    byte ptr [rbx+4], 4
0x18000864e  jnz     short loc_180008659
0x180008650  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008657  jz      short loc_18000866B
0x180008659  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008660  test    rax, rax
0x180008663  jz      short loc_18000866B
0x180008665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000866a  nop
0x18000866b  mov     rbx, [rsp+88h+arg_10]
0x180008673  add     rsp, 50h
0x180008677  pop     r15
0x180008679  pop     r14
0x18000867b  pop     r13
0x18000867d  pop     r12
0x18000867f  pop     rdi
0x180008680  pop     rsi
0x180008681  pop     rbp
0x180008682  retn
0x180008683  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
