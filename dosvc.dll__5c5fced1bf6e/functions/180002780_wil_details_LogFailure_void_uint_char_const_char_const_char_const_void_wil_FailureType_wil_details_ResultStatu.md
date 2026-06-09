# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180002780`
- end: `0x180002a78`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180002670`
- `0x1800061cc`
- `0x180006280`
- `0x180008b38`

## callees

- `0x180002780`
- `0x180002b90`
- `0x180006108`
- `0x180006dd4`
- `0x18000782c`
- `0x180007850`
- `0x180007864`
- `0x180007880`
- `0x18000843c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002897`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a40`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a40`

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
  unsigned int v19; // ebp
  int v20; // r14d
  int v21; // eax
  _WORD *v22; // rax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 (*ModuleName)(void); // rax
  const WCHAR *v26; // rax
  wil::details *v27; // [rsp+30h] [rbp-58h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v20 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v21 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v21 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v21 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v21 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v20 = v21;
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
  *(_DWORD *)(a16 + 68) = v20;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  ModuleName = wil::details::g_pfnGetModuleName;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = (__int64 (*)(void))wil::details::g_pfnGetModuleName();
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent )
  {
    if ( wil::g_pfnIsDebuggerPresent )
    {
      if ( !(unsigned __int8)wil::g_pfnIsDebuggerPresent() )
        goto LABEL_38;
    }
    else if ( !IsDebuggerPresent() )
    {
LABEL_38:
      if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
        g_pfnResultLoggingCallback(a16, 0, 0, v24);
      goto LABEL_47;
    }
  }
  if ( (*(_BYTE *)(a16 + 4) & 2) != 0 )
    goto LABEL_38;
  if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
    g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v24);
  v26 = (const WCHAR *)lpOutputString;
  if ( !*(_WORD *)lpOutputString )
  {
    wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    v26 = (const WCHAR *)lpOutputString;
  }
  OutputDebugStringW(v26);
LABEL_47:
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180002780  mov     [rsp+arg_0], rcx
0x180002785  push    rbx
0x180002786  push    rbp
0x180002787  push    rsi
0x180002788  push    rdi
0x180002789  push    r12
0x18000278b  push    r13
0x18000278d  push    r14
0x18000278f  push    r15
0x180002791  sub     rsp, 48h
0x180002795  mov     r15, r9
0x180002798  mov     r12, r8
0x18000279b  mov     r13d, edx
0x18000279e  mov     r10, rcx
0x1800027a1  xor     eax, eax
0x1800027a3  mov     rcx, [rsp+88h+lpOutputString]
0x1800027ab  mov     [rcx], ax
0x1800027ae  mov     rax, [rsp+88h+arg_60]
0x1800027b6  mov     byte ptr [rax], 0
0x1800027b9  mov     rdi, [rsp+88h+arg_38]
0x1800027c1  mov     ebp, [rdi]
0x1800027c3  mov     rbx, [rsp+88h+arg_78]
0x1800027cb  mov     [rbx+8], ebp
0x1800027ce  mov     eax, [rdi+4]
0x1800027d1  mov     [rbx+0Ch], eax
0x1800027d4  xor     r14d, r14d
0x1800027d7  mov     esi, [rsp+88h+arg_30]
0x1800027de  mov     ecx, esi
0x1800027e0  test    esi, esi
0x1800027e2  jz      short loc_18000284A
0x1800027e4  sub     ecx, 1
0x1800027e7  jz      short loc_180002841
0x1800027e9  sub     ecx, 1
0x1800027ec  jz      short loc_1800027FC
0x1800027ee  cmp     ecx, 1
0x1800027f1  jnz     short loc_180002854
0x1800027f3  mov     ecx, ebp; this
0x1800027f5  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800027fa  jmp     short loc_180002851
0x1800027fc  test    ebp, ebp
0x1800027fe  js      short loc_180002838
0x180002800  mov     ebp, 8007029Ch
0x180002805  mov     dword ptr [rsp+88h+var_58], ebp; wil::details *
0x180002809  mov     rax, [rsp+88h+arg_28]
0x180002811  mov     [rsp+88h+var_60], rax; __int64
0x180002816  mov     rax, [rsp+88h+arg_20]
0x18000281e  mov     [rsp+88h+var_68], rax; __int64
0x180002823  mov     rcx, r10; int
0x180002826  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000282b  mov     [rbx+8], ebp
0x18000282e  mov     ecx, ebp; this
0x180002830  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002835  mov     [rbx+0Ch], eax
0x180002838  mov     ecx, ebp; this
0x18000283a  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000283f  jmp     short loc_180002851
0x180002841  mov     ecx, ebp; this
0x180002843  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002848  jmp     short loc_180002851
0x18000284a  mov     ecx, ebp; this
0x18000284c  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180002851  mov     r14d, eax
0x180002854  mov     [rbx], esi
0x180002856  mov     eax, [rsp+88h+arg_70]
0x18000285d  mov     [rbx+4], eax
0x180002860  cmp     dword ptr [rdi+8], 1
0x180002864  jnz     short loc_18000286C
0x180002866  or      eax, 8
0x180002869  mov     [rbx+4], eax
0x18000286c  mov     eax, 1
0x180002871  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002879  inc     eax
0x18000287b  mov     [rbx+10h], eax
0x18000287e  mov     rax, [rsp+88h+arg_40]
0x180002886  test    rax, rax
0x180002889  jz      short loc_180002891
0x18000288b  cmp     word ptr [rax], 0
0x18000288f  jnz     short loc_180002893
0x180002891  xor     eax, eax
0x180002893  mov     [rbx+18h], rax
0x180002897  call    cs:__imp_GetCurrentThreadId
0x18000289d  mov     [rbx+20h], eax
0x1800028a0  mov     [rbx+38h], r12
0x1800028a4  mov     [rbx+40h], r13d
0x1800028a8  mov     [rbx+44h], r14d
0x1800028ac  mov     rax, [rsp+88h+arg_20]
0x1800028b4  mov     [rbx+28h], rax
0x1800028b8  mov     [rbx+30h], r15
0x1800028bc  mov     rax, [rsp+88h+arg_28]
0x1800028c4  mov     [rbx+88h], rax
0x1800028cb  mov     rax, [rsp+88h+arg_0]
0x1800028d3  mov     [rbx+90h], rax
0x1800028da  mov     qword ptr [rbx+48h], 0
0x1800028e2  xorps   xmm0, xmm0
0x1800028e5  xor     eax, eax
0x1800028e7  movups  xmmword ptr [rbx+68h], xmm0
0x1800028eb  mov     [rbx+78h], rax
0x1800028ef  movups  xmmword ptr [rbx+50h], xmm0
0x1800028f3  mov     [rbx+60h], rax
0x1800028f7  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800028fe  test    rax, rax
0x180002901  jz      short loc_180002908
0x180002903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002908  mov     [rbx+80h], rax
0x18000290f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002916  test    rax, rax
0x180002919  jz      short loc_180002923
0x18000291b  mov     rcx, rbx
0x18000291e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002923  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000292a  test    rax, rax
0x18000292d  jz      short loc_180002945
0x18000292f  mov     r8d, 400h
0x180002935  mov     rdx, [rsp+88h+arg_60]
0x18000293d  mov     rcx, rbx
0x180002940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002945  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000294c  test    rax, rax
0x18000294f  jz      short loc_180002959
0x180002951  mov     rcx, rbx
0x180002954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002959  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002960  test    rax, rax
0x180002963  jz      short loc_180002973
0x180002965  test    byte ptr [rbx+4], 2
0x180002969  jnz     short loc_180002973
0x18000296b  mov     rcx, rbx
0x18000296e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002973  cmp     dword ptr [rbx+8], 0
0x180002977  jl      short loc_180002998
0x180002979  cmp     esi, 3
0x18000297c  jz      short loc_180002984
0x18000297e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002984  mov     dword ptr [rbx+8], 8000FFFFh
0x18000298b  mov     ecx, 8000FFFFh; this
0x180002990  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002995  mov     [rbx+0Ch], eax
0x180002998  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x18000299f  jnz     short loc_1800029C2
0x1800029a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800029a8  test    rax, rax
0x1800029ab  jz      short loc_1800029B8
0x1800029ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029b2  test    al, al
0x1800029b4  jnz     short loc_1800029C2
0x1800029b6  jmp     short loc_1800029C8
0x1800029b8  call    cs:__imp_IsDebuggerPresent
0x1800029be  test    eax, eax
0x1800029c0  jz      short loc_1800029C8
0x1800029c2  test    byte ptr [rbx+4], 2
0x1800029c6  jz      short loc_1800029EC
0x1800029c8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029cf  test    rax, rax
0x1800029d2  jz      short loc_180002A46
0x1800029d4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800029db  jnz     short loc_180002A46
0x1800029dd  xor     r8d, r8d
0x1800029e0  xor     edx, edx
0x1800029e2  mov     rcx, rbx
0x1800029e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ea  jmp     short loc_180002A46
0x1800029ec  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029f3  test    rax, rax
0x1800029f6  jz      short loc_180002A17
0x1800029f8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800029ff  jnz     short loc_180002A17
0x180002a01  mov     r8d, 800h
0x180002a07  mov     rdx, [rsp+88h+lpOutputString]
0x180002a0f  mov     rcx, rbx
0x180002a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a17  mov     rax, [rsp+88h+lpOutputString]
0x180002a1f  cmp     word ptr [rax], 0
0x180002a23  jnz     short loc_180002A3D
0x180002a25  mov     r8, rbx; unsigned __int64
0x180002a28  mov     edx, 800h; unsigned __int16 *
0x180002a2d  mov     rcx, rax; this
0x180002a30  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002a35  mov     rax, [rsp+88h+lpOutputString]
0x180002a3d  mov     rcx, rax; lpOutputString
0x180002a40  call    cs:__imp_OutputDebugStringW
0x180002a46  test    byte ptr [rbx+4], 4
0x180002a4a  jnz     short loc_180002A55
0x180002a4c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180002a53  jz      short loc_180002A67
0x180002a55  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a5c  test    rax, rax
0x180002a5f  jz      short loc_180002A67
0x180002a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a66  nop
0x180002a67  add     rsp, 48h
0x180002a6b  pop     r15
0x180002a6d  pop     r14
0x180002a6f  pop     r13
0x180002a71  pop     r12
0x180002a73  pop     rdi
0x180002a74  pop     rsi
0x180002a75  pop     rbp
0x180002a76  pop     rbx
0x180002a77  retn
```
