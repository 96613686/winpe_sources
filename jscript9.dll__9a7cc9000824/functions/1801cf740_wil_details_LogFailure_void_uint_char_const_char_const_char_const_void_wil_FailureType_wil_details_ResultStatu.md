# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1801cf740`
- end: `0x1801cfaa1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `865`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1801cc6e8`
- `0x1801ccb10`

## callees

- `0x180196328`
- `0x1801cc5b0`
- `0x1801ce414`
- `0x1801cf740`
- `0x1801d072c`
- `0x1801d0760`
- `0x1801d09b0`
- `0x1801d09d8`
- `0x1801d2804`
- `0x180364010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1801cf9bf`
- `KERNEL32!IsDebuggerPresent` at `0x1801cf9bf`
- `KERNEL32!GetCurrentThreadId` at `0x1801cf885`
- `KERNEL32!GetCurrentThreadId` at `0x1801cf885`
- `KERNEL32!OutputDebugStringW` at `0x1801cfa5c`
- `KERNEL32!OutputDebugStringW` at `0x1801cfa5c`

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
        char a10,
        wil *lpOutputString,
        unsigned __int16 *a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v16; // edi
  int v17; // esi
  int v18; // eax
  int v19; // edx
  _WORD *v20; // rax
  int v21; // edx
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 (*ModuleName)(void); // rax
  bool v25; // zf
  bool v26; // di
  wil::details *v27; // [rsp+30h] [rbp-68h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v16 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v17 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v18 = wil::details::RecordReturn((wil::details *)v16, a2);
        break;
      case 2:
        if ( (v16 & 0x80000000) == 0 )
        {
          v16 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27, 0);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v19);
        }
        v18 = wil::details::RecordLog((wil::details *)v16, a2);
        break;
      case 3:
        v18 = wil::details::RecordFailFast((wil::details *)v16, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v18 = wil::details::RecordException((wil::details *)v16, a2);
  }
  v17 = v18;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = a9;
  if ( !a9 || !*a9 )
    v20 = 0;
  *(_QWORD *)(a16 + 24) = v20;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v17;
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
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, a14);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && !a10 && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v21);
  }
  v26 = (wil::g_fIsDebuggerPresent
      || (!wil::g_pfnIsDebuggerPresent
        ? (v25 = !IsDebuggerPresent())
        : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
          !v25))
     && wil::g_fResultOutputDebugString
     && (*(_BYTE *)(a16 + 4) & 2) == 0;
  if ( a10 || v26 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, a12);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, a12, a16, v23);
    if ( v26 )
      OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
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
0x1801cf740  mov     qword ptr [rsp+arg_18], r9
0x1801cf745  mov     qword ptr [rsp+arg_10], r8
0x1801cf74a  mov     [rsp+arg_8], edx
0x1801cf74e  mov     qword ptr [rsp+arg_0], rcx
0x1801cf753  push    rbx
0x1801cf754  push    rbp
0x1801cf755  push    rsi
0x1801cf756  push    rdi
0x1801cf757  push    r12
0x1801cf759  push    r13
0x1801cf75b  push    r14
0x1801cf75d  push    r15
0x1801cf75f  sub     rsp, 58h
0x1801cf763  mov     [rsp+98h+var_58], 0FFFFFFFFFFFFFFFEh
0x1801cf76c  xor     eax, eax
0x1801cf76e  mov     r14, [rsp+98h+lpOutputString]
0x1801cf776  mov     [r14], ax
0x1801cf77a  mov     r12, [rsp+98h+arg_60]
0x1801cf782  mov     [r12], al
0x1801cf786  mov     r15, [rsp+98h+arg_38]
0x1801cf78e  mov     edi, [r15]
0x1801cf791  mov     rbx, [rsp+98h+arg_78]
0x1801cf799  mov     [rbx+8], edi
0x1801cf79c  mov     eax, [r15+4]
0x1801cf7a0  mov     [rbx+0Ch], eax
0x1801cf7a3  xor     esi, esi
0x1801cf7a5  mov     ebp, [rsp+98h+arg_30]
0x1801cf7ac  mov     ecx, ebp
0x1801cf7ae  mov     r13, [rsp+98h+arg_28]
0x1801cf7b6  test    ebp, ebp
0x1801cf7b8  jz      short loc_1801CF838
0x1801cf7ba  sub     ecx, 1
0x1801cf7bd  jz      short loc_1801CF82F
0x1801cf7bf  sub     ecx, 1
0x1801cf7c2  jz      short loc_1801CF7D2
0x1801cf7c4  cmp     ecx, 1
0x1801cf7c7  jnz     short loc_1801CF841
0x1801cf7c9  mov     ecx, edi; this
0x1801cf7cb  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1801cf7d0  jmp     short loc_1801CF83F
0x1801cf7d2  test    edi, edi
0x1801cf7d4  js      short loc_1801CF826
0x1801cf7d6  mov     [rsp+98h+var_60], esi; int
0x1801cf7da  mov     edi, 8007029Ch
0x1801cf7df  mov     dword ptr [rsp+98h+var_68], edi; wil::details *
0x1801cf7e3  mov     [rsp+98h+var_70], r13; __int64
0x1801cf7e8  mov     rax, [rsp+98h+arg_20]
0x1801cf7f0  mov     [rsp+98h+var_78], rax; __int64
0x1801cf7f5  mov     r9, qword ptr [rsp+98h+arg_18]; int
0x1801cf7fd  mov     r8, qword ptr [rsp+98h+arg_10]; int
0x1801cf805  mov     edx, [rsp+98h+arg_8]; int
0x1801cf80c  mov     rcx, qword ptr [rsp+98h+arg_0]; int
0x1801cf814  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1801cf819  mov     [rbx+8], edi
0x1801cf81c  mov     ecx, edi; this
0x1801cf81e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1801cf823  mov     [rbx+0Ch], eax
0x1801cf826  mov     ecx, edi; this
0x1801cf828  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1801cf82d  jmp     short loc_1801CF83F
0x1801cf82f  mov     ecx, edi; this
0x1801cf831  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1801cf836  jmp     short loc_1801CF83F
0x1801cf838  mov     ecx, edi; this
0x1801cf83a  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1801cf83f  mov     esi, eax
0x1801cf841  mov     [rbx], ebp
0x1801cf843  mov     eax, [rsp+98h+arg_70]
0x1801cf84a  mov     [rbx+4], eax
0x1801cf84d  cmp     dword ptr [r15+8], 1
0x1801cf852  jnz     short loc_1801CF85A
0x1801cf854  or      eax, 8
0x1801cf857  mov     [rbx+4], eax
0x1801cf85a  mov     eax, 1
0x1801cf85f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1801cf867  inc     eax
0x1801cf869  mov     [rbx+10h], eax
0x1801cf86c  mov     rax, [rsp+98h+arg_40]
0x1801cf874  test    rax, rax
0x1801cf877  jz      short loc_1801CF87F
0x1801cf879  cmp     word ptr [rax], 0
0x1801cf87d  jnz     short loc_1801CF881
0x1801cf87f  xor     eax, eax
0x1801cf881  mov     [rbx+18h], rax
0x1801cf885  call    cs:__imp_GetCurrentThreadId
0x1801cf88c  nop     dword ptr [rax+rax+00h]
0x1801cf891  mov     [rbx+20h], eax
0x1801cf894  mov     rax, qword ptr [rsp+98h+arg_10]
0x1801cf89c  mov     [rbx+38h], rax
0x1801cf8a0  mov     eax, [rsp+98h+arg_8]
0x1801cf8a7  mov     [rbx+40h], eax
0x1801cf8aa  mov     [rbx+44h], esi
0x1801cf8ad  mov     rax, [rsp+98h+arg_20]
0x1801cf8b5  mov     [rbx+28h], rax
0x1801cf8b9  mov     rax, qword ptr [rsp+98h+arg_18]
0x1801cf8c1  mov     [rbx+30h], rax
0x1801cf8c5  mov     [rbx+88h], r13
0x1801cf8cc  mov     rax, qword ptr [rsp+98h+arg_0]
0x1801cf8d4  mov     [rbx+90h], rax
0x1801cf8db  mov     qword ptr [rbx+48h], 0
0x1801cf8e3  xorps   xmm0, xmm0
0x1801cf8e6  xor     eax, eax
0x1801cf8e8  movups  xmmword ptr [rbx+68h], xmm0
0x1801cf8ec  mov     [rbx+78h], rax
0x1801cf8f0  movups  xmmword ptr [rbx+50h], xmm0
0x1801cf8f4  mov     [rbx+60h], rax
0x1801cf8f8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1801cf8ff  test    rax, rax
0x1801cf902  jz      short loc_1801CF909
0x1801cf904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf909  mov     [rbx+80h], rax
0x1801cf910  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1801cf917  test    rax, rax
0x1801cf91a  jz      short loc_1801CF924
0x1801cf91c  mov     rcx, rbx
0x1801cf91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf924  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1801cf92b  test    rax, rax
0x1801cf92e  jz      short loc_1801CF943
0x1801cf930  mov     r8, [rsp+98h+arg_68]
0x1801cf938  mov     rdx, r12
0x1801cf93b  mov     rcx, rbx
0x1801cf93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf943  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801cf94a  test    rax, rax
0x1801cf94d  jz      short loc_1801CF957
0x1801cf94f  mov     rcx, rbx
0x1801cf952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf957  movzx   esi, [rsp+98h+arg_48]
0x1801cf95f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801cf966  test    rax, rax
0x1801cf969  jz      short loc_1801CF97E
0x1801cf96b  test    sil, sil
0x1801cf96e  jnz     short loc_1801CF97E
0x1801cf970  test    byte ptr [rbx+4], 2
0x1801cf974  jnz     short loc_1801CF97E
0x1801cf976  mov     rcx, rbx
0x1801cf979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf97e  cmp     dword ptr [rbx+8], 0
0x1801cf982  jl      short loc_1801CF9A1
0x1801cf984  cmp     ebp, 3
0x1801cf987  jnz     loc_1801CFA9B
0x1801cf98d  mov     dword ptr [rbx+8], 8000FFFFh
0x1801cf994  mov     ecx, 8000FFFFh; this
0x1801cf999  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1801cf99e  mov     [rbx+0Ch], eax
0x1801cf9a1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1801cf9a8  jnz     short loc_1801CF9CF
0x1801cf9aa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1801cf9b1  test    rax, rax
0x1801cf9b4  jz      short loc_1801CF9BF
0x1801cf9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf9bb  test    al, al
0x1801cf9bd  jmp     short loc_1801CF9CD
0x1801cf9bf  call    cs:__imp_IsDebuggerPresent
0x1801cf9c6  nop     dword ptr [rax+rax+00h]
0x1801cf9cb  test    eax, eax
0x1801cf9cd  jz      short loc_1801CF9E3
0x1801cf9cf  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x1801cf9d6  jz      short loc_1801CF9E3
0x1801cf9d8  test    byte ptr [rbx+4], 2
0x1801cf9dc  jnz     short loc_1801CF9E3
0x1801cf9de  mov     dil, 1
0x1801cf9e1  jmp     short loc_1801CF9E6
0x1801cf9e3  xor     dil, dil
0x1801cf9e6  test    sil, sil
0x1801cf9e9  jnz     short loc_1801CFA14
0x1801cf9eb  test    dil, dil
0x1801cf9ee  jnz     short loc_1801CFA14
0x1801cf9f0  mov     rax, cs:g_pfnResultLoggingCallback
0x1801cf9f7  test    rax, rax
0x1801cf9fa  jz      short loc_1801CFA68
0x1801cf9fc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801cfa03  jnz     short loc_1801CFA68
0x1801cfa05  xor     r8d, r8d
0x1801cfa08  xor     edx, edx
0x1801cfa0a  mov     rcx, rbx
0x1801cfa0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cfa12  jmp     short loc_1801CFA68
0x1801cfa14  mov     rsi, [rsp+98h+arg_58]
0x1801cfa1c  mov     rax, cs:g_pfnResultLoggingCallback
0x1801cfa23  test    rax, rax
0x1801cfa26  jz      short loc_1801CFA3F
0x1801cfa28  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1801cfa2f  jnz     short loc_1801CFA3F
0x1801cfa31  mov     r8, rsi
0x1801cfa34  mov     rdx, r14
0x1801cfa37  mov     rcx, rbx
0x1801cfa3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cfa3f  cmp     word ptr [r14], 0
0x1801cfa44  jnz     short loc_1801CFA54
0x1801cfa46  mov     r8, rbx; unsigned __int64
0x1801cfa49  mov     rdx, rsi; unsigned __int16 *
0x1801cfa4c  mov     rcx, r14; this
0x1801cfa4f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1801cfa54  test    dil, dil
0x1801cfa57  jz      short loc_1801CFA68
0x1801cfa59  mov     rcx, r14; lpOutputString
0x1801cfa5c  call    cs:__imp_OutputDebugStringW
0x1801cfa63  nop     dword ptr [rax+rax+00h]
0x1801cfa68  test    byte ptr [rbx+4], 4
0x1801cfa6c  jnz     short loc_1801CFA77
0x1801cfa6e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1801cfa75  jz      short loc_1801CFA89
0x1801cfa77  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1801cfa7e  test    rax, rax
0x1801cfa81  jz      short loc_1801CFA89
0x1801cfa83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cfa88  nop
0x1801cfa89  add     rsp, 58h
0x1801cfa8d  pop     r15
0x1801cfa8f  pop     r14
0x1801cfa91  pop     r13
0x1801cfa93  pop     r12
0x1801cfa95  pop     rdi
0x1801cfa96  pop     rsi
0x1801cfa97  pop     rbp
0x1801cfa98  pop     rbx
0x1801cfa99  retn
0x1801cfa9b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
