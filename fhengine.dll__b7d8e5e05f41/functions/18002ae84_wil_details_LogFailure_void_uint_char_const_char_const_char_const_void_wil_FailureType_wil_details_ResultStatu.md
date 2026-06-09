# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002ae84`
- end: `0x18002b17d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180027200`

## callees

- `0x180026c3c`
- `0x18002a094`
- `0x18002aa30`
- `0x18002ae84`
- `0x18002be2c`
- `0x18002be50`
- `0x18002bfd4`
- `0x18002bff0`
- `0x18002e22c`
- `0x180034010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18002b138`
- `KERNEL32!OutputDebugStringW` at `0x18002b138`
- `KERNEL32!IsDebuggerPresent` at `0x18002b0c6`
- `KERNEL32!IsDebuggerPresent` at `0x18002b0c6`
- `KERNEL32!GetCurrentThreadId` at `0x18002afa7`
- `KERNEL32!GetCurrentThreadId` at `0x18002afa7`

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
  wil::details *v28; // [rsp+30h] [rbp-48h]

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x18002ae84  mov     [rsp+arg_10], rbx
0x18002ae89  mov     [rsp+arg_8], edx
0x18002ae8d  mov     [rsp+arg_0], rcx
0x18002ae92  push    rbp
0x18002ae93  push    rsi
0x18002ae94  push    rdi
0x18002ae95  push    r12
0x18002ae97  push    r13
0x18002ae99  push    r14
0x18002ae9b  push    r15
0x18002ae9d  sub     rsp, 40h
0x18002aea1  mov     r12, r9
0x18002aea4  mov     r13, r8
0x18002aea7  mov     r10, rcx
0x18002aeaa  xor     eax, eax
0x18002aeac  mov     rsi, [rsp+78h+lpOutputString]
0x18002aeb4  mov     [rsi], ax
0x18002aeb7  mov     rax, [rsp+78h+arg_60]
0x18002aebf  mov     byte ptr [rax], 0
0x18002aec2  mov     r14, [rsp+78h+arg_38]
0x18002aeca  mov     edi, [r14]
0x18002aecd  mov     rbx, [rsp+78h+arg_78]
0x18002aed5  mov     [rbx+8], edi
0x18002aed8  mov     eax, [r14+4]
0x18002aedc  mov     [rbx+0Ch], eax
0x18002aedf  xor     ebp, ebp
0x18002aee1  mov     r15d, [rsp+78h+arg_30]
0x18002aee9  mov     ecx, r15d
0x18002aeec  test    r15d, r15d
0x18002aeef  jz      short loc_18002AF57
0x18002aef1  sub     ecx, 1
0x18002aef4  jz      short loc_18002AF4E
0x18002aef6  sub     ecx, 1
0x18002aef9  jz      short loc_18002AF09
0x18002aefb  cmp     ecx, 1
0x18002aefe  jnz     short loc_18002AF60
0x18002af00  mov     ecx, edi; this
0x18002af02  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002af07  jmp     short loc_18002AF5E
0x18002af09  test    edi, edi
0x18002af0b  js      short loc_18002AF45
0x18002af0d  mov     edi, 8007029Ch
0x18002af12  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002af16  mov     rax, [rsp+78h+arg_28]
0x18002af1e  mov     [rsp+78h+var_50], rax; __int64
0x18002af23  mov     rax, [rsp+78h+arg_20]
0x18002af2b  mov     [rsp+78h+var_58], rax; __int64
0x18002af30  mov     rcx, r10; int
0x18002af33  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002af38  mov     [rbx+8], edi
0x18002af3b  mov     ecx, edi; this
0x18002af3d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002af42  mov     [rbx+0Ch], eax
0x18002af45  mov     ecx, edi; this
0x18002af47  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002af4c  jmp     short loc_18002AF5E
0x18002af4e  mov     ecx, edi; this
0x18002af50  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002af55  jmp     short loc_18002AF5E
0x18002af57  mov     ecx, edi; this
0x18002af59  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002af5e  mov     ebp, eax
0x18002af60  mov     [rbx], r15d
0x18002af63  mov     eax, [rsp+78h+arg_70]
0x18002af6a  mov     [rbx+4], eax
0x18002af6d  cmp     dword ptr [r14+8], 1
0x18002af72  jnz     short loc_18002AF7A
0x18002af74  or      eax, 8
0x18002af77  mov     [rbx+4], eax
0x18002af7a  mov     eax, 1
0x18002af7f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002af87  inc     eax
0x18002af89  mov     [rbx+10h], eax
0x18002af8c  mov     rax, [rsp+78h+arg_40]
0x18002af94  xor     edi, edi
0x18002af96  test    rax, rax
0x18002af99  jz      short loc_18002AFA0
0x18002af9b  cmp     [rax], di
0x18002af9e  jnz     short loc_18002AFA3
0x18002afa0  mov     rax, rdi
0x18002afa3  mov     [rbx+18h], rax
0x18002afa7  call    cs:__imp_GetCurrentThreadId
0x18002afad  mov     [rbx+20h], eax
0x18002afb0  mov     [rbx+38h], r13
0x18002afb4  mov     eax, [rsp+78h+arg_8]
0x18002afbb  mov     [rbx+40h], eax
0x18002afbe  mov     [rbx+44h], ebp
0x18002afc1  mov     rax, [rsp+78h+arg_20]
0x18002afc9  mov     [rbx+28h], rax
0x18002afcd  mov     [rbx+30h], r12
0x18002afd1  mov     rax, [rsp+78h+arg_28]
0x18002afd9  mov     [rbx+88h], rax
0x18002afe0  mov     rax, [rsp+78h+arg_0]
0x18002afe8  mov     [rbx+90h], rax
0x18002afef  mov     [rbx+48h], rdi
0x18002aff3  xorps   xmm0, xmm0
0x18002aff6  xor     eax, eax
0x18002aff8  movups  xmmword ptr [rbx+68h], xmm0
0x18002affc  mov     [rbx+78h], rax
0x18002b000  movups  xmmword ptr [rbx+50h], xmm0
0x18002b004  mov     [rbx+60h], rax
0x18002b008  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002b00f  test    rax, rax
0x18002b012  jz      short loc_18002B01B
0x18002b014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b019  jmp     short loc_18002B01E
0x18002b01b  mov     rax, rdi
0x18002b01e  mov     [rbx+80h], rax
0x18002b025  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002b02c  test    rax, rax
0x18002b02f  jz      short loc_18002B039
0x18002b031  mov     rcx, rbx
0x18002b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b039  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002b040  test    rax, rax
0x18002b043  jz      short loc_18002B05B
0x18002b045  mov     r8d, 400h
0x18002b04b  mov     rdx, [rsp+78h+arg_60]
0x18002b053  mov     rcx, rbx
0x18002b056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b05b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002b062  test    rax, rax
0x18002b065  jz      short loc_18002B06F
0x18002b067  mov     rcx, rbx
0x18002b06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b06f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002b076  test    rax, rax
0x18002b079  jz      short loc_18002B089
0x18002b07b  test    byte ptr [rbx+4], 2
0x18002b07f  jnz     short loc_18002B089
0x18002b081  mov     rcx, rbx
0x18002b084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b089  cmp     [rbx+8], edi
0x18002b08c  jl      short loc_18002B0A8
0x18002b08e  cmp     r15d, 3
0x18002b092  jnz     loc_18002B177
0x18002b098  mov     ecx, 8000FFFFh; this
0x18002b09d  mov     [rbx+8], ecx
0x18002b0a0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002b0a5  mov     [rbx+0Ch], eax
0x18002b0a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002b0af  jnz     short loc_18002B0D0
0x18002b0b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002b0b8  test    rax, rax
0x18002b0bb  jz      short loc_18002B0C6
0x18002b0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0c2  test    al, al
0x18002b0c4  jmp     short loc_18002B0CE
0x18002b0c6  call    cs:__imp_IsDebuggerPresent
0x18002b0cc  test    eax, eax
0x18002b0ce  jz      short loc_18002B0D6
0x18002b0d0  test    byte ptr [rbx+4], 2
0x18002b0d4  jz      short loc_18002B0FA
0x18002b0d6  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b0dd  test    rax, rax
0x18002b0e0  jz      short loc_18002B13E
0x18002b0e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002b0e9  jnz     short loc_18002B13E
0x18002b0eb  xor     r8d, r8d
0x18002b0ee  xor     edx, edx
0x18002b0f0  mov     rcx, rbx
0x18002b0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0f8  jmp     short loc_18002B13E
0x18002b0fa  mov     ebp, 800h
0x18002b0ff  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b106  test    rax, rax
0x18002b109  jz      short loc_18002B122
0x18002b10b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002b112  jnz     short loc_18002B122
0x18002b114  mov     r8d, ebp
0x18002b117  mov     rdx, rsi
0x18002b11a  mov     rcx, rbx
0x18002b11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b122  cmp     [rsi], di
0x18002b125  jnz     short loc_18002B135
0x18002b127  mov     r8, rbx; unsigned __int64
0x18002b12a  mov     rdx, rbp; unsigned __int16 *
0x18002b12d  mov     rcx, rsi; this
0x18002b130  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002b135  mov     rcx, rsi; lpOutputString
0x18002b138  call    cs:__imp_OutputDebugStringW
0x18002b13e  test    byte ptr [rbx+4], 4
0x18002b142  jnz     short loc_18002B14D
0x18002b144  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002b14b  jz      short loc_18002B15F
0x18002b14d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002b154  test    rax, rax
0x18002b157  jz      short loc_18002B15F
0x18002b159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b15e  nop
0x18002b15f  mov     rbx, [rsp+78h+arg_10]
0x18002b167  add     rsp, 40h
0x18002b16b  pop     r15
0x18002b16d  pop     r14
0x18002b16f  pop     r13
0x18002b171  pop     r12
0x18002b173  pop     rdi
0x18002b174  pop     rsi
0x18002b175  pop     rbp
0x18002b176  retn
0x18002b177  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
