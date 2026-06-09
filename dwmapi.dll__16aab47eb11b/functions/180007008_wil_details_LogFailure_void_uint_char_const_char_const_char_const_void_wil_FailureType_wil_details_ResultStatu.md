# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007008`
- end: `0x180007300`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006c28`
- `0x18000bd8c`
- `0x18000e260`

## callees

- `0x180004ff4`
- `0x180006d2c`
- `0x180007008`
- `0x180009874`
- `0x180009bc4`
- `0x18000ee78`
- `0x18000f9ec`
- `0x18000fa10`
- `0x180010968`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000712f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000712f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800072c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800072c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007250`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007250`

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
0x180007008  mov     [rsp+arg_10], rbx
0x18000700d  mov     [rsp+arg_8], edx
0x180007011  mov     [rsp+arg_0], rcx
0x180007016  push    rbp
0x180007017  push    rsi
0x180007018  push    rdi
0x180007019  push    r12
0x18000701b  push    r13
0x18000701d  push    r14
0x18000701f  push    r15
0x180007021  sub     rsp, 40h
0x180007025  mov     r14, [rsp+78h+arg_38]
0x18000702d  xor     eax, eax
0x18000702f  mov     rbx, [rsp+78h+arg_78]
0x180007037  xor     ebp, ebp
0x180007039  mov     r15d, [rsp+78h+arg_30]
0x180007041  mov     r10, rcx
0x180007044  mov     rsi, [rsp+78h+lpOutputString]
0x18000704c  mov     r12, r9
0x18000704f  mov     r13, r8
0x180007052  mov     ecx, r15d
0x180007055  mov     [rsi], ax
0x180007058  mov     rax, [rsp+78h+arg_60]
0x180007060  mov     byte ptr [rax], 0
0x180007063  mov     edi, [r14]
0x180007066  mov     [rbx+8], edi
0x180007069  mov     eax, [r14+4]
0x18000706d  mov     [rbx+0Ch], eax
0x180007070  test    r15d, r15d
0x180007073  jz      short loc_1800070DF
0x180007075  sub     ecx, 1
0x180007078  jz      short loc_1800070D6
0x18000707a  sub     ecx, 1
0x18000707d  jz      short loc_18000708D
0x18000707f  cmp     ecx, 1
0x180007082  jnz     short loc_1800070E8
0x180007084  mov     ecx, edi; this
0x180007086  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000708b  jmp     short loc_1800070E6
0x18000708d  test    edi, edi
0x18000708f  js      short loc_1800070CD
0x180007091  mov     rax, [rsp+78h+arg_28]
0x180007099  mov     edi, 8007029Ch
0x18000709e  mov     [rsp+78h+var_40], ebp
0x1800070a2  mov     rcx, r10; int
0x1800070a5  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800070a9  mov     [rsp+78h+var_50], rax; __int64
0x1800070ae  mov     rax, [rsp+78h+arg_20]
0x1800070b6  mov     [rsp+78h+var_58], rax; __int64
0x1800070bb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800070c0  mov     ecx, edi; this
0x1800070c2  mov     [rbx+8], edi
0x1800070c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800070ca  mov     [rbx+0Ch], eax
0x1800070cd  mov     ecx, edi; this
0x1800070cf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800070d4  jmp     short loc_1800070E6
0x1800070d6  mov     ecx, edi; this
0x1800070d8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800070dd  jmp     short loc_1800070E6
0x1800070df  mov     ecx, edi; this
0x1800070e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800070e6  mov     ebp, eax
0x1800070e8  mov     eax, [rsp+78h+arg_70]
0x1800070ef  mov     [rbx+4], eax
0x1800070f2  mov     [rbx], r15d
0x1800070f5  cmp     dword ptr [r14+8], 1
0x1800070fa  jnz     short loc_180007102
0x1800070fc  or      eax, 8
0x1800070ff  mov     [rbx+4], eax
0x180007102  mov     eax, 1
0x180007107  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000710f  inc     eax
0x180007111  xor     edi, edi
0x180007113  mov     [rbx+10h], eax
0x180007116  mov     rax, [rsp+78h+arg_40]
0x18000711e  test    rax, rax
0x180007121  jz      short loc_180007128
0x180007123  cmp     [rax], di
0x180007126  jnz     short loc_18000712B
0x180007128  mov     rax, rdi
0x18000712b  mov     [rbx+18h], rax
0x18000712f  call    cs:__imp_GetCurrentThreadId
0x180007135  mov     [rbx+38h], r13
0x180007139  xorps   xmm0, xmm0
0x18000713c  mov     [rbx+20h], eax
0x18000713f  mov     eax, [rsp+78h+arg_8]
0x180007146  mov     [rbx+40h], eax
0x180007149  mov     rax, [rsp+78h+arg_20]
0x180007151  mov     [rbx+28h], rax
0x180007155  mov     rax, [rsp+78h+arg_28]
0x18000715d  mov     [rbx+88h], rax
0x180007164  mov     rax, [rsp+78h+arg_0]
0x18000716c  mov     [rbx+90h], rax
0x180007173  xor     eax, eax
0x180007175  mov     [rbx+44h], ebp
0x180007178  mov     [rbx+30h], r12
0x18000717c  mov     [rbx+48h], rdi
0x180007180  movups  xmmword ptr [rbx+68h], xmm0
0x180007184  mov     [rbx+78h], rax
0x180007188  movups  xmmword ptr [rbx+50h], xmm0
0x18000718c  mov     [rbx+60h], rax
0x180007190  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007197  test    rax, rax
0x18000719a  jz      short loc_1800071A3
0x18000719c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a1  jmp     short loc_1800071A6
0x1800071a3  mov     rax, rdi
0x1800071a6  mov     [rbx+80h], rax
0x1800071ad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800071b4  test    rax, rax
0x1800071b7  jz      short loc_1800071C1
0x1800071b9  mov     rcx, rbx
0x1800071bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800071c8  test    rax, rax
0x1800071cb  jz      short loc_1800071E3
0x1800071cd  mov     rdx, [rsp+78h+arg_60]
0x1800071d5  mov     r8d, 400h
0x1800071db  mov     rcx, rbx
0x1800071de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800071ea  test    rax, rax
0x1800071ed  jz      short loc_1800071F7
0x1800071ef  mov     rcx, rbx
0x1800071f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071f7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800071fe  test    rax, rax
0x180007201  jz      short loc_180007211
0x180007203  test    byte ptr [rbx+4], 2
0x180007207  jnz     short loc_180007211
0x180007209  mov     rcx, rbx
0x18000720c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007211  cmp     [rbx+8], edi
0x180007214  jl      short loc_180007232
0x180007216  cmp     r15d, 3
0x18000721a  jz      short loc_180007222
0x18000721c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007222  mov     ecx, 8000FFFFh; this
0x180007227  mov     [rbx+8], ecx
0x18000722a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000722f  mov     [rbx+0Ch], eax
0x180007232  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007239  jnz     short loc_18000725A
0x18000723b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007242  test    rax, rax
0x180007245  jz      short loc_180007250
0x180007247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000724c  test    al, al
0x18000724e  jmp     short loc_180007258
0x180007250  call    cs:__imp_IsDebuggerPresent
0x180007256  test    eax, eax
0x180007258  jz      short loc_180007260
0x18000725a  test    byte ptr [rbx+4], 2
0x18000725e  jz      short loc_180007284
0x180007260  mov     rax, cs:g_pfnResultLoggingCallback
0x180007267  test    rax, rax
0x18000726a  jz      short loc_1800072C8
0x18000726c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007273  jnz     short loc_1800072C8
0x180007275  xor     r8d, r8d
0x180007278  xor     edx, edx
0x18000727a  mov     rcx, rbx
0x18000727d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007282  jmp     short loc_1800072C8
0x180007284  mov     rax, cs:g_pfnResultLoggingCallback
0x18000728b  mov     ebp, 800h
0x180007290  test    rax, rax
0x180007293  jz      short loc_1800072AC
0x180007295  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000729c  jnz     short loc_1800072AC
0x18000729e  mov     r8d, ebp
0x1800072a1  mov     rdx, rsi
0x1800072a4  mov     rcx, rbx
0x1800072a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072ac  cmp     [rsi], di
0x1800072af  jnz     short loc_1800072BF
0x1800072b1  mov     r8, rbx; unsigned __int64
0x1800072b4  mov     rdx, rbp; unsigned __int16 *
0x1800072b7  mov     rcx, rsi; this
0x1800072ba  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800072bf  mov     rcx, rsi; lpOutputString
0x1800072c2  call    cs:__imp_OutputDebugStringW
0x1800072c8  test    byte ptr [rbx+4], 4
0x1800072cc  jnz     short loc_1800072D7
0x1800072ce  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800072d5  jz      short loc_1800072E8
0x1800072d7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800072de  test    rax, rax
0x1800072e1  jz      short loc_1800072E8
0x1800072e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e8  mov     rbx, [rsp+78h+arg_10]
0x1800072f0  add     rsp, 40h
0x1800072f4  pop     r15
0x1800072f6  pop     r14
0x1800072f8  pop     r13
0x1800072fa  pop     r12
0x1800072fc  pop     rdi
0x1800072fd  pop     rsi
0x1800072fe  pop     rbp
0x1800072ff  retn
```
