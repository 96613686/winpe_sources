# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800218ec`
- end: `0x180021bf8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001ef8c`
- `0x18001f30c`
- `0x18003a46c`

## callees

- `0x180013d68`
- `0x18001eec4`
- `0x1800209f4`
- `0x1800218ec`
- `0x180022298`
- `0x1800222c0`
- `0x180022424`
- `0x180022444`
- `0x180023d00`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021a0f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021bac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021bac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021b34`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180021b34`

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
0x1800218ec  mov     [rsp+arg_10], rbx
0x1800218f1  mov     [rsp+arg_8], edx
0x1800218f5  mov     [rsp+arg_0], rcx
0x1800218fa  push    rbp
0x1800218fb  push    rsi
0x1800218fc  push    rdi
0x1800218fd  push    r12
0x1800218ff  push    r13
0x180021901  push    r14
0x180021903  push    r15
0x180021905  sub     rsp, 40h
0x180021909  mov     r12, r9
0x18002190c  mov     r13, r8
0x18002190f  mov     r10, rcx
0x180021912  xor     eax, eax
0x180021914  mov     rsi, [rsp+78h+lpOutputString]
0x18002191c  mov     [rsi], ax
0x18002191f  mov     rax, [rsp+78h+arg_60]
0x180021927  mov     byte ptr [rax], 0
0x18002192a  mov     r14, [rsp+78h+arg_38]
0x180021932  mov     edi, [r14]
0x180021935  mov     rbx, [rsp+78h+arg_78]
0x18002193d  mov     [rbx+8], edi
0x180021940  mov     eax, [r14+4]
0x180021944  mov     [rbx+0Ch], eax
0x180021947  xor     ebp, ebp
0x180021949  mov     r15d, [rsp+78h+arg_30]
0x180021951  mov     ecx, r15d
0x180021954  test    r15d, r15d
0x180021957  jz      short loc_1800219BF
0x180021959  sub     ecx, 1
0x18002195c  jz      short loc_1800219B6
0x18002195e  sub     ecx, 1
0x180021961  jz      short loc_180021971
0x180021963  cmp     ecx, 1
0x180021966  jnz     short loc_1800219C8
0x180021968  mov     ecx, edi; this
0x18002196a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002196f  jmp     short loc_1800219C6
0x180021971  test    edi, edi
0x180021973  js      short loc_1800219AD
0x180021975  mov     edi, 8007029Ch
0x18002197a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002197e  mov     rax, [rsp+78h+arg_28]
0x180021986  mov     [rsp+78h+var_50], rax; __int64
0x18002198b  mov     rax, [rsp+78h+arg_20]
0x180021993  mov     [rsp+78h+var_58], rax; __int64
0x180021998  mov     rcx, r10; int
0x18002199b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800219a0  mov     [rbx+8], edi
0x1800219a3  mov     ecx, edi; this
0x1800219a5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800219aa  mov     [rbx+0Ch], eax
0x1800219ad  mov     ecx, edi; this
0x1800219af  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800219b4  jmp     short loc_1800219C6
0x1800219b6  mov     ecx, edi; this
0x1800219b8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800219bd  jmp     short loc_1800219C6
0x1800219bf  mov     ecx, edi; this
0x1800219c1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800219c6  mov     ebp, eax
0x1800219c8  mov     [rbx], r15d
0x1800219cb  mov     eax, [rsp+78h+arg_70]
0x1800219d2  mov     [rbx+4], eax
0x1800219d5  cmp     dword ptr [r14+8], 1
0x1800219da  jnz     short loc_1800219E2
0x1800219dc  or      eax, 8
0x1800219df  mov     [rbx+4], eax
0x1800219e2  mov     eax, 1
0x1800219e7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800219ef  inc     eax
0x1800219f1  mov     [rbx+10h], eax
0x1800219f4  mov     rax, [rsp+78h+arg_40]
0x1800219fc  xor     edi, edi
0x1800219fe  test    rax, rax
0x180021a01  jz      short loc_180021A08
0x180021a03  cmp     [rax], di
0x180021a06  jnz     short loc_180021A0B
0x180021a08  mov     rax, rdi
0x180021a0b  mov     [rbx+18h], rax
0x180021a0f  call    cs:__imp_GetCurrentThreadId
0x180021a16  nop     dword ptr [rax+rax+00h]
0x180021a1b  mov     [rbx+20h], eax
0x180021a1e  mov     [rbx+38h], r13
0x180021a22  mov     eax, [rsp+78h+arg_8]
0x180021a29  mov     [rbx+40h], eax
0x180021a2c  mov     [rbx+44h], ebp
0x180021a2f  mov     rax, [rsp+78h+arg_20]
0x180021a37  mov     [rbx+28h], rax
0x180021a3b  mov     [rbx+30h], r12
0x180021a3f  mov     rax, [rsp+78h+arg_28]
0x180021a47  mov     [rbx+88h], rax
0x180021a4e  mov     rax, [rsp+78h+arg_0]
0x180021a56  mov     [rbx+90h], rax
0x180021a5d  mov     [rbx+48h], rdi
0x180021a61  xorps   xmm0, xmm0
0x180021a64  xor     eax, eax
0x180021a66  movups  xmmword ptr [rbx+68h], xmm0
0x180021a6a  mov     [rbx+78h], rax
0x180021a6e  movups  xmmword ptr [rbx+50h], xmm0
0x180021a72  mov     [rbx+60h], rax
0x180021a76  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180021a7d  test    rax, rax
0x180021a80  jz      short loc_180021A89
0x180021a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a87  jmp     short loc_180021A8C
0x180021a89  mov     rax, rdi
0x180021a8c  mov     [rbx+80h], rax
0x180021a93  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180021a9a  test    rax, rax
0x180021a9d  jz      short loc_180021AA7
0x180021a9f  mov     rcx, rbx
0x180021aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aa7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021aae  test    rax, rax
0x180021ab1  jz      short loc_180021AC9
0x180021ab3  mov     r8d, 400h
0x180021ab9  mov     rdx, [rsp+78h+arg_60]
0x180021ac1  mov     rcx, rbx
0x180021ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ac9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021ad0  test    rax, rax
0x180021ad3  jz      short loc_180021ADD
0x180021ad5  mov     rcx, rbx
0x180021ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021add  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180021ae4  test    rax, rax
0x180021ae7  jz      short loc_180021AF7
0x180021ae9  test    byte ptr [rbx+4], 2
0x180021aed  jnz     short loc_180021AF7
0x180021aef  mov     rcx, rbx
0x180021af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021af7  cmp     [rbx+8], edi
0x180021afa  jl      short loc_180021B16
0x180021afc  cmp     r15d, 3
0x180021b00  jnz     loc_180021BF2
0x180021b06  mov     ecx, 8000FFFFh; this
0x180021b0b  mov     [rbx+8], ecx
0x180021b0e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180021b13  mov     [rbx+0Ch], eax
0x180021b16  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180021b1d  jnz     short loc_180021B44
0x180021b1f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021b26  test    rax, rax
0x180021b29  jz      short loc_180021B34
0x180021b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b30  test    al, al
0x180021b32  jmp     short loc_180021B42
0x180021b34  call    cs:__imp_IsDebuggerPresent
0x180021b3b  nop     dword ptr [rax+rax+00h]
0x180021b40  test    eax, eax
0x180021b42  jz      short loc_180021B4A
0x180021b44  test    byte ptr [rbx+4], 2
0x180021b48  jz      short loc_180021B6E
0x180021b4a  mov     rax, cs:g_pfnResultLoggingCallback
0x180021b51  test    rax, rax
0x180021b54  jz      short loc_180021BB8
0x180021b56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180021b5d  jnz     short loc_180021BB8
0x180021b5f  xor     r8d, r8d
0x180021b62  xor     edx, edx
0x180021b64  mov     rcx, rbx
0x180021b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b6c  jmp     short loc_180021BB8
0x180021b6e  mov     ebp, 800h
0x180021b73  mov     rax, cs:g_pfnResultLoggingCallback
0x180021b7a  test    rax, rax
0x180021b7d  jz      short loc_180021B96
0x180021b7f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180021b86  jnz     short loc_180021B96
0x180021b88  mov     r8d, ebp
0x180021b8b  mov     rdx, rsi
0x180021b8e  mov     rcx, rbx
0x180021b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b96  cmp     [rsi], di
0x180021b99  jnz     short loc_180021BA9
0x180021b9b  mov     r8, rbx; unsigned __int64
0x180021b9e  mov     rdx, rbp; unsigned __int16 *
0x180021ba1  mov     rcx, rsi; this
0x180021ba4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180021ba9  mov     rcx, rsi; lpOutputString
0x180021bac  call    cs:__imp_OutputDebugStringW
0x180021bb3  nop     dword ptr [rax+rax+00h]
0x180021bb8  test    byte ptr [rbx+4], 4
0x180021bbc  jnz     short loc_180021BC7
0x180021bbe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180021bc5  jz      short loc_180021BD9
0x180021bc7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180021bce  test    rax, rax
0x180021bd1  jz      short loc_180021BD9
0x180021bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bd8  nop
0x180021bd9  mov     rbx, [rsp+78h+arg_10]
0x180021be1  add     rsp, 40h
0x180021be5  pop     r15
0x180021be7  pop     r14
0x180021be9  pop     r13
0x180021beb  pop     r12
0x180021bed  pop     rdi
0x180021bee  pop     rsi
0x180021bef  pop     rbp
0x180021bf0  retn
0x180021bf2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
