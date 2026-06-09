# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x100071c8`
- end: `0x10007459`
- name: `?LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@2@ABUResultStatus@12@PBG_NPAGIPADIW4FailureFlags@2@PAUFailureInfo@2@@Z`
- size: `657`
- prototype: `void __userpurge(int@<edx>, int@<ecx>, wil::details *this, void *, unsigned int, const char *, const char *, const char *, _WORD *, enum wil::FailureType, struct wil::details::ResultStatus *lpOutputString, const unsigned __int16 *, _BYTE *, unsigned __int16 *, unsigned int, wil *, unsigned int, enum wil::FailureFlags, struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1000f748`

## callees

- `0x10006a5c`
- `0x10006d70`
- `0x10006d89`
- `0x10006da2`
- `0x10006dc0`
- `0x10006f61`
- `0x100071c8`
- `0x10007624`
- `0x1000f149`
- `0x1002d510`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x10007422`
- `KERNEL32!OutputDebugStringW` at `0x10007422`
- `KERNEL32!GetCurrentThreadId` at `0x100072a9`
- `KERNEL32!GetCurrentThreadId` at `0x100072a9`
- `KERNEL32!IsDebuggerPresent` at `0x100073af`
- `KERNEL32!IsDebuggerPresent` at `0x100073af`

## pseudocode

```c
void __userpurge wil::details::LogFailure(
        int a1@<edx>,
        int a2@<ecx>,
        wil::details *this,
        void *a4,
        unsigned int a5,
        const char *a6,
        const char *a7,
        const char *a8,
        _WORD *a9,
        enum wil::FailureType a10,
        struct wil::details::ResultStatus *lpOutputString,
        const unsigned __int16 *a12,
        _BYTE *a13,
        unsigned __int16 *a14,
        unsigned int a15,
        wil *a16,
        unsigned int a17,
        enum wil::FailureFlags a18,
        struct wil::FailureInfo *a19)
{
  int v19; // edi
  int v20; // eax
  int v21; // edi
  _WORD *v22; // eax
  int v23; // eax
  CD3DSurfaceAllocator *v24; // edi
  int v25; // eax
  wil::details::in1diag3 *v26; // [esp+0h] [ebp-18h]
  unsigned int v27; // [esp+4h] [ebp-14h]
  const struct wil::FailureInfo *v28; // [esp+8h] [ebp-10h]

  LOWORD(lpOutputString->hr) = 0;
  *a13 = 0;
  v19 = *(_DWORD *)a8;
  *((_DWORD *)a16 + 2) = *(_DWORD *)a8;
  *((_DWORD *)a16 + 3) = *((_DWORD *)a8 + 1);
  if ( !a7 )
  {
    v20 = wil::details::RecordException((void *)v19);
    goto LABEL_10;
  }
  if ( a7 == (const char *)1 )
  {
    v20 = wil::details::RecordReturn((void *)v19);
    goto LABEL_10;
  }
  if ( a7 == (const char *)2 )
  {
    if ( v19 >= 0 )
    {
      v19 = -2147024228;
      wil::details::ReportFailure_Hr<2>(a2, a1, this, a4, a5, a6, -2147024228, a2);
      *((_DWORD *)a16 + 2) = -2147024228;
      *((_DWORD *)a16 + 3) = wil::details::HrToNtStatus(-2147024228);
    }
    v20 = wil::details::RecordLog((void *)v19);
    goto LABEL_10;
  }
  if ( a7 == (const char *)3 )
  {
    v20 = wil::details::RecordFailFast((wil::details *)v19, (int)v26);
LABEL_10:
    v21 = v20;
    goto LABEL_13;
  }
  v21 = 0;
LABEL_13:
  *(_DWORD *)a16 = a7;
  *((_DWORD *)a16 + 1) = a15;
  if ( *((_DWORD *)a8 + 2) == 1 )
    *((_DWORD *)a16 + 1) = a15 | 8;
  *((_DWORD *)a16 + 4) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *((_DWORD *)a16 + 5) = v22;
  *((_DWORD *)a16 + 6) = GetCurrentThreadId();
  *((_DWORD *)a16 + 9) = this;
  *((_DWORD *)a16 + 10) = a1;
  *((_DWORD *)a16 + 7) = a5;
  *((_DWORD *)a16 + 8) = a4;
  *((_DWORD *)a16 + 20) = a6;
  *((_DWORD *)a16 + 11) = v21;
  *((_DWORD *)a16 + 21) = a2;
  *((_DWORD *)a16 + 12) = 0;
  *((_DWORD *)a16 + 16) = 0;
  *((_DWORD *)a16 + 17) = 0;
  *((_DWORD *)a16 + 18) = 0;
  *((_DWORD *)a16 + 13) = 0;
  *((_DWORD *)a16 + 14) = 0;
  *((_DWORD *)a16 + 15) = 0;
  if ( wil::details::g_pfnGetModuleName )
    v23 = ((int (__thiscall *)(CD3DSurfaceAllocator *))wil::details::g_pfnGetModuleName)(wil::details::g_pfnGetModuleName);
  else
    v23 = 0;
  v24 = wil::details::g_pfnNotifyFailure;
  *((_DWORD *)a16 + 19) = v23;
  if ( v24 )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, wil *))v24)(v24, a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, wil *, _BYTE *, int))wil::details::g_pfnGetContextAndNotifyFailure)(
      wil::details::g_pfnGetContextAndNotifyFailure,
      a16,
      a13,
      1024);
  if ( wil::details::g_pfnLoggingCallback )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, wil *))wil::details::g_pfnLoggingCallback)(
      wil::details::g_pfnLoggingCallback,
      a16);
  if ( wil::details::g_pfnOriginateCallback && (*((_BYTE *)a16 + 4) & 2) == 0 )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, wil *))wil::details::g_pfnOriginateCallback)(
      wil::details::g_pfnOriginateCallback,
      a16);
  if ( *((int *)a16 + 2) >= 0 )
  {
    if ( a7 != (const char *)3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v26);
    *((_DWORD *)a16 + 2) = -2147418113;
    *((_DWORD *)a16 + 3) = wil::details::HrToNtStatus(-2147418113);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (v25 = IsDebuggerPresent())
       : (v25 = (unsigned __int8)((int (__thiscall *)(CD3DSurfaceAllocator *))wil::g_pfnIsDebuggerPresent)(wil::g_pfnIsDebuggerPresent)),
         v25))
    && (*((_BYTE *)a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      ((void (__thiscall *)(CD3DSurfaceAllocator *, wil *, struct wil::details::ResultStatus *, int))g_pfnResultLoggingCallback)(
        g_pfnResultLoggingCallback,
        a16,
        lpOutputString,
        2048);
    if ( !LOWORD(lpOutputString->hr) )
      wil::GetFailureLogString(
        2048,
        (wil::details *)lpOutputString,
        (const unsigned __int16 *)lpOutputString,
        a16,
        (unsigned __int16 *)v26,
        v27,
        v28);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    ((void (__thiscall *)(CD3DSurfaceAllocator *, wil *, _DWORD, _DWORD))g_pfnResultLoggingCallback)(
      g_pfnResultLoggingCallback,
      a16,
      0,
      0);
  }
  if ( (*((_BYTE *)a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      ((void (__thiscall *)(CD3DSurfaceAllocator *))wil::details::g_pfnDebugBreak)(wil::details::g_pfnDebugBreak);
  }
}

```

## disassembly

```asm
0x100071c8  mov     edi, edi
0x100071ca  push    ebp
0x100071cb  mov     ebp, esp
0x100071cd  and     esp, 0FFFFFFF8h
0x100071d0  sub     esp, 0Ch
0x100071d3  push    ebx; struct wil::FailureInfo *
0x100071d4  mov     ebx, [ebp+lpOutputString]
0x100071d7  xor     eax, eax
0x100071d9  push    esi; unsigned int
0x100071da  mov     esi, [ebp+arg_34]
0x100071dd  push    edi; this
0x100071de  mov     [ebx], ax
0x100071e1  mov     eax, [ebp+arg_28]
0x100071e4  mov     [esp+18h+var_8], edx
0x100071e8  mov     [esp+18h+var_4], ecx
0x100071ec  mov     [esp+18h+var_C], 0
0x100071f4  mov     byte ptr [eax], 0
0x100071f7  mov     eax, [ebp+arg_14]
0x100071fa  mov     edi, [eax]
0x100071fc  mov     [esi+8], edi
0x100071ff  mov     eax, [eax+4]
0x10007202  mov     [esi+0Ch], eax
0x10007205  mov     eax, [ebp+arg_10]
0x10007208  sub     eax, 0
0x1000720b  jz      short loc_10007261
0x1000720d  sub     eax, 1
0x10007210  jz      short loc_10007256
0x10007212  sub     eax, 1
0x10007215  jz      short loc_10007224
0x10007217  sub     eax, 1
0x1000721a  jnz     short loc_1000726A
0x1000721c  push    edi; this
0x1000721d  call    ?RecordFailFast@details@wil@@YGHJ@Z; wil::details::RecordFailFast(long)
0x10007222  jmp     short loc_1000725D
0x10007224  test    edi, edi
0x10007226  js      short loc_1000724D
0x10007228  push    ecx
0x10007229  mov     edi, 8007029Ch
0x1000722e  push    edi
0x1000722f  push    [ebp+arg_C]
0x10007232  push    [ebp+arg_8]
0x10007235  push    [ebp+arg_4]
0x10007238  push    [ebp+this]
0x1000723b  call    ??$ReportFailure_Hr@$01@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x10007240  mov     ecx, edi
0x10007242  mov     [esi+8], edi
0x10007245  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x1000724a  mov     [esi+0Ch], eax
0x1000724d  mov     ecx, edi
0x1000724f  call    ?RecordLog@details@wil@@YGHJ@Z; wil::details::RecordLog(long)
0x10007254  jmp     short loc_1000725D
0x10007256  mov     ecx, edi
0x10007258  call    ?RecordReturn@details@wil@@YGHJ@Z; wil::details::RecordReturn(long)
0x1000725d  mov     edi, eax
0x1000725f  jmp     short loc_1000726E
0x10007261  mov     ecx, edi
0x10007263  call    ?RecordException@details@wil@@YGHJ@Z; wil::details::RecordException(long)
0x10007268  jmp     short loc_1000725D
0x1000726a  mov     edi, [esp+18h+var_C]
0x1000726e  mov     eax, [ebp+arg_10]
0x10007271  mov     edx, [ebp+arg_14]
0x10007274  mov     ecx, [ebp+arg_30]
0x10007277  mov     [esi], eax
0x10007279  xor     eax, eax
0x1000727b  inc     eax
0x1000727c  mov     [esi+4], ecx
0x1000727f  cmp     [edx+8], eax
0x10007282  jnz     short loc_1000728A
0x10007284  or      ecx, 8
0x10007287  mov     [esi+4], ecx
0x1000728a  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x10007292  inc     eax
0x10007293  mov     [esi+10h], eax
0x10007296  mov     eax, [ebp+arg_18]
0x10007299  test    eax, eax
0x1000729b  jz      short loc_100072A4
0x1000729d  xor     ecx, ecx
0x1000729f  cmp     [eax], cx
0x100072a2  jnz     short loc_100072A6
0x100072a4  xor     eax, eax
0x100072a6  mov     [esi+14h], eax
0x100072a9  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x100072af  mov     [esi+18h], eax
0x100072b2  xor     ecx, ecx
0x100072b4  mov     eax, [ebp+this]
0x100072b7  mov     [esi+24h], eax
0x100072ba  mov     eax, [esp+18h+var_8]
0x100072be  mov     [esi+28h], eax
0x100072c1  mov     eax, [ebp+arg_8]
0x100072c4  mov     [esi+1Ch], eax
0x100072c7  mov     eax, [ebp+arg_4]
0x100072ca  mov     [esi+20h], eax
0x100072cd  mov     eax, [ebp+arg_C]
0x100072d0  mov     [esi+50h], eax
0x100072d3  mov     eax, [esp+18h+var_4]
0x100072d7  mov     [esi+2Ch], edi
0x100072da  lea     edi, [esi+40h]
0x100072dd  mov     [esi+54h], eax
0x100072e0  xor     eax, eax
0x100072e2  mov     [esi+30h], ecx
0x100072e5  stosd
0x100072e6  stosd
0x100072e7  stosd
0x100072e8  xor     eax, eax
0x100072ea  lea     edi, [esi+34h]
0x100072ed  stosd
0x100072ee  stosd
0x100072ef  stosd
0x100072f0  mov     edi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x100072f6  test    edi, edi
0x100072f8  jz      short loc_10007306
0x100072fa  mov     ecx, edi; this
0x100072fc  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10007302  call    edi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x10007304  jmp     short loc_10007308
0x10007306  mov     eax, ecx
0x10007308  mov     edi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000730e  mov     [esi+4Ch], eax
0x10007311  test    edi, edi
0x10007313  jz      short loc_10007320
0x10007315  push    esi
0x10007316  mov     ecx, edi; this
0x10007318  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000731e  call    edi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x10007320  mov     edi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x10007326  test    edi, edi
0x10007328  jz      short loc_1000733D
0x1000732a  push    400h
0x1000732f  push    [ebp+arg_28]
0x10007332  mov     ecx, edi; this
0x10007334  push    esi
0x10007335  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000733b  call    edi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000733d  mov     edi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x10007343  test    edi, edi
0x10007345  jz      short loc_10007352
0x10007347  push    esi
0x10007348  mov     ecx, edi; this
0x1000734a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10007350  call    edi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x10007352  mov     edi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x10007358  test    edi, edi
0x1000735a  jz      short loc_1000736D
0x1000735c  test    byte ptr [esi+4], 2
0x10007360  jnz     short loc_1000736D
0x10007362  push    esi
0x10007363  mov     ecx, edi; this
0x10007365  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000736b  call    edi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000736d  cmp     dword ptr [esi+8], 0
0x10007371  jl      short loc_1000738D
0x10007373  cmp     [ebp+arg_10], 3
0x10007377  jnz     loc_10007454
0x1000737d  mov     ecx, 8000FFFFh
0x10007382  mov     [esi+8], ecx
0x10007385  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x1000738a  mov     [esi+0Ch], eax
0x1000738d  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x10007394  jnz     short loc_100073BF
0x10007396  mov     edi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000739c  test    edi, edi
0x1000739e  jz      short loc_100073AF
0x100073a0  mov     ecx, edi; this
0x100073a2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100073a8  call    edi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x100073aa  movzx   eax, al
0x100073ad  jmp     short loc_100073BB
0x100073af  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x100073b5  neg     eax
0x100073b7  sbb     eax, eax
0x100073b9  neg     eax
0x100073bb  test    eax, eax
0x100073bd  jz      short loc_100073C5
0x100073bf  test    byte ptr [esi+4], 2
0x100073c3  jz      short loc_100073E9
0x100073c5  mov     edi, _g_pfnResultLoggingCallback
0x100073cb  test    edi, edi
0x100073cd  jz      short loc_10007428
0x100073cf  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x100073d6  jnz     short loc_10007428
0x100073d8  xor     eax, eax
0x100073da  mov     ecx, edi; this
0x100073dc  push    eax
0x100073dd  push    eax
0x100073de  push    esi
0x100073df  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100073e5  call    edi ; _g_pfnResultLoggingCallback
0x100073e7  jmp     short loc_10007428
0x100073e9  mov     edi, _g_pfnResultLoggingCallback
0x100073ef  test    edi, edi
0x100073f1  jz      short loc_1000740D
0x100073f3  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x100073fa  jnz     short loc_1000740D
0x100073fc  push    800h
0x10007401  push    ebx
0x10007402  push    esi
0x10007403  mov     ecx, edi; this
0x10007405  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000740b  call    edi ; _g_pfnResultLoggingCallback
0x1000740d  xor     eax, eax
0x1000740f  cmp     [ebx], ax
0x10007412  jnz     short loc_10007421
0x10007414  push    esi; this
0x10007415  mov     edx, 800h
0x1000741a  mov     ecx, ebx
0x1000741c  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x10007421  push    ebx; lpOutputString
0x10007422  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x10007428  test    byte ptr [esi+4], 4
0x1000742c  jnz     short loc_10007437
0x1000742e  cmp     ?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x10007435  jz      short loc_1000744B
0x10007437  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000743d  test    esi, esi
0x1000743f  jz      short loc_1000744B
0x10007441  mov     ecx, esi; this
0x10007443  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10007449  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000744b  pop     edi
0x1000744c  pop     esi
0x1000744d  pop     ebx
0x1000744e  mov     esp, ebp
0x10007450  pop     ebp
0x10007451  retn    38h ; '8'
0x10007454  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
