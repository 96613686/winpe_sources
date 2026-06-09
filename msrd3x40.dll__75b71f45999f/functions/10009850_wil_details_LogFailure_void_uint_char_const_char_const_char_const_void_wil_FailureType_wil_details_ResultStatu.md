# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x10009850`
- end: `0x10009b16`
- name: `?LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@2@ABUResultStatus@12@PBG_NPAGIPADIW4FailureFlags@2@PAUFailureInfo@2@@Z`
- size: `710`
- prototype: `void __stdcall __high(void *, unsigned int, const char *, const char *, const char *, void *, enum wil::FailureType, const struct wil::details::ResultStatus *, const unsigned __int16 *, bool, unsigned __int16 *, unsigned int, char *, unsigned int, enum wil::FailureFlags, struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1000e770`

## callees

- `0x10008670`
- `0x10008b00`
- `0x10008b20`
- `0x10008b40`
- `0x10008b60`
- `0x10008e20`
- `0x10009850`
- `0x10009e60`
- `0x1000db60`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000994a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000994a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x10009ad4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x10009ad4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x10009a62`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x10009a62`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        _WORD *a9,
        int a10,
        LPCWSTR lpOutputString,
        int a12,
        _BYTE *a13,
        int a14,
        int a15,
        wil *a16)
{
  wil::details *v16; // ecx
  int v17; // eax
  _WORD *v18; // eax
  DWORD CurrentThreadId; // eax
  int (__thiscall *v20)(_DWORD); // edi
  int v21; // eax
  void (__thiscall *v22)(_DWORD, wil *); // edi
  int IsDebuggerPresent; // eax
  wil::details *v24; // [esp+0h] [ebp-28h]
  unsigned int v25; // [esp+4h] [ebp-24h]
  const struct wil::FailureInfo *v26; // [esp+8h] [ebp-20h]
  int v29; // [esp+18h] [ebp-10h]

  *lpOutputString = 0;
  v29 = 0;
  *a13 = 0;
  v16 = *(wil::details **)a8;
  *((_DWORD *)a16 + 2) = *(_DWORD *)a8;
  *((_DWORD *)a16 + 3) = *(_DWORD *)(a8 + 4);
  switch ( a7 )
  {
    case 0:
      v17 = wil::details::RecordException(v24, v25);
      goto LABEL_8;
    case 1:
      v17 = wil::details::RecordReturn(v24, v25);
      goto LABEL_8;
    case 2:
      if ( (int)v16 >= 0 )
      {
        wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, -2147024228, v16);
        *((_DWORD *)a16 + 2) = -2147024228;
        *((_DWORD *)a16 + 3) = wil::details::HrToNtStatus(v24, v25);
      }
      v17 = wil::details::RecordLog(v24, v25);
      goto LABEL_8;
    case 3:
      v17 = wil::details::RecordFailFast(v16, (int)v24);
LABEL_8:
      v29 = v17;
      break;
    default:
      break;
  }
  *(_DWORD *)a16 = a7;
  *((_DWORD *)a16 + 1) = a15;
  if ( *(_DWORD *)(a8 + 8) == 1 )
    *((_DWORD *)a16 + 1) = a15 | 8;
  *((_DWORD *)a16 + 4) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v18 = a9;
  if ( !a9 || !*a9 )
    v18 = 0;
  *((_DWORD *)a16 + 5) = v18;
  CurrentThreadId = GetCurrentThreadId();
  v20 = (int (__thiscall *)(_DWORD))wil::details::g_pfnGetModuleName;
  *((_DWORD *)a16 + 6) = CurrentThreadId;
  *((_DWORD *)a16 + 9) = a3;
  *((_DWORD *)a16 + 10) = a2;
  *((_DWORD *)a16 + 11) = v29;
  *((_DWORD *)a16 + 7) = a5;
  *((_DWORD *)a16 + 8) = a4;
  *((_DWORD *)a16 + 20) = a6;
  *((_DWORD *)a16 + 21) = a1;
  *((_DWORD *)a16 + 12) = 0;
  *((_QWORD *)a16 + 8) = 0;
  *((_DWORD *)a16 + 18) = 0;
  *(_QWORD *)((char *)a16 + 52) = 0;
  *((_DWORD *)a16 + 15) = 0;
  if ( v20 )
    v21 = v20(v20);
  else
    v21 = 0;
  v22 = (void (__thiscall *)(_DWORD, wil *))wil::details::g_pfnNotifyFailure;
  *((_DWORD *)a16 + 19) = v21;
  if ( v22 )
    v22(v22, a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(wil::details::g_pfnGetContextAndNotifyFailure, a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(wil::details::g_pfnLoggingCallback, a16);
  if ( wil::details::g_pfnOriginateCallback && (*((_BYTE *)a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(wil::details::g_pfnOriginateCallback, a16);
  if ( *((int *)a16 + 2) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *((_DWORD *)a16 + 2) = -2147418113;
    *((_DWORD *)a16 + 3) = wil::details::HrToNtStatus(v24, v25);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(wil::g_pfnIsDebuggerPresent)),
         IsDebuggerPresent))
    && (*((_BYTE *)a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, a16, lpOutputString, 2048);
    if ( !*lpOutputString )
      wil::GetFailureLogString(a16, (unsigned __int16 *)v24, v25, v26);
    OutputDebugStringW(lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, a16, 0, 0);
  }
  if ( (*((_BYTE *)a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(wil::details::g_pfnDebugBreak);
  }
}

```

## disassembly

```asm
0x10009850  mov     edi, edi
0x10009852  push    ebp
0x10009853  mov     ebp, esp
0x10009855  push    0FFFFFFFFh
0x10009857  push    offset ?OnSignaled@SubscriptionList@details_abi@wil@@QAEXAAVsrwlock@3@@Z_SEH
0x1000985c  mov     eax, large fs:0
0x10009862  push    eax
0x10009863  sub     esp, 0Ch
0x10009866  push    ebx
0x10009867  push    esi; struct wil::FailureInfo *
0x10009868  push    edi; unsigned int
0x10009869  mov     eax, ___security_cookie
0x1000986e  xor     eax, ebp
0x10009870  push    eax; this
0x10009871  lea     eax, [ebp+var_C]
0x10009874  mov     large fs:0, eax
0x1000987a  mov     [ebp+var_14], edx
0x1000987d  mov     [ebp+var_18], ecx
0x10009880  mov     ebx, [ebp+lpOutputString]
0x10009883  xor     eax, eax
0x10009885  mov     esi, [ebp+arg_34]
0x10009888  mov     edx, [ebp+arg_10]
0x1000988b  mov     edi, [ebp+arg_30]
0x1000988e  mov     [ebx], ax
0x10009891  mov     eax, [ebp+arg_28]
0x10009894  mov     [ebp+var_10], 0
0x1000989b  mov     byte ptr [eax], 0
0x1000989e  mov     eax, [ebp+arg_14]
0x100098a1  mov     ecx, [eax]
0x100098a3  mov     [esi+8], ecx
0x100098a6  mov     eax, [eax+4]
0x100098a9  mov     [esi+0Ch], eax
0x100098ac  cmp     edx, 3; switch 4 cases
0x100098af  ja      short def_100098B1; jumptable 100098B1 default case
0x100098b1  jmp     ds:jpt_100098B1[edx*4]; switch jump
0x100098b8  call    ?RecordException@details@wil@@YGHJ@Z; jumptable 100098B1 case 0
0x100098bd  jmp     short loc_1000990D
0x100098bf  call    ?RecordReturn@details@wil@@YGHJ@Z; jumptable 100098B1 case 1
0x100098c4  jmp     short loc_1000990D
0x100098c6  test    ecx, ecx; jumptable 100098B1 case 2
0x100098c8  js      short loc_10009900
0x100098ca  mov     edx, [ebp+var_14]
0x100098cd  push    ecx
0x100098ce  mov     ecx, [ebp+var_18]
0x100098d1  push    8007029Ch
0x100098d6  push    [ebp+arg_C]
0x100098d9  push    [ebp+arg_8]
0x100098dc  push    [ebp+arg_4]
0x100098df  push    [ebp+arg_0]
0x100098e2  call    ??$ReportFailure_Hr@$01@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x100098e7  mov     ecx, 8007029Ch
0x100098ec  mov     dword ptr [esi+8], 8007029Ch
0x100098f3  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x100098f8  mov     [esi+0Ch], eax
0x100098fb  mov     ecx, 8007029Ch
0x10009900  call    ?RecordLog@details@wil@@YGHJ@Z; wil::details::RecordLog(long)
0x10009905  jmp     short loc_1000990D
0x10009907  push    ecx; jumptable 100098B1 case 3
0x10009908  call    ?RecordFailFast@details@wil@@YGHJ@Z; wil::details::RecordFailFast(long)
0x1000990d  mov     [ebp+var_10], eax
0x10009910  mov     eax, [ebp+arg_10]; jumptable 100098B1 default case
0x10009913  mov     [esi], eax
0x10009915  mov     eax, [ebp+arg_14]
0x10009918  mov     [esi+4], edi
0x1000991b  cmp     dword ptr [eax+8], 1
0x1000991f  jnz     short loc_10009927
0x10009921  or      edi, 8
0x10009924  mov     [esi+4], edi
0x10009927  mov     eax, 1
0x1000992c  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x10009934  inc     eax
0x10009935  mov     [esi+10h], eax
0x10009938  mov     eax, [ebp+arg_18]
0x1000993b  test    eax, eax
0x1000993d  jz      short loc_10009945
0x1000993f  cmp     word ptr [eax], 0
0x10009943  jnz     short loc_10009947
0x10009945  xor     eax, eax
0x10009947  mov     [esi+14h], eax
0x1000994a  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10009950  mov     edi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x10009956  xorps   xmm0, xmm0
0x10009959  mov     [esi+18h], eax
0x1000995c  mov     eax, [ebp+arg_0]
0x1000995f  mov     [esi+24h], eax
0x10009962  mov     eax, [ebp+var_14]
0x10009965  mov     [esi+28h], eax
0x10009968  mov     eax, [ebp+var_10]
0x1000996b  mov     [esi+2Ch], eax
0x1000996e  mov     eax, [ebp+arg_8]
0x10009971  mov     [esi+1Ch], eax
0x10009974  mov     eax, [ebp+arg_4]
0x10009977  mov     [esi+20h], eax
0x1000997a  mov     eax, [ebp+arg_C]
0x1000997d  mov     [esi+50h], eax
0x10009980  mov     eax, [ebp+var_18]
0x10009983  mov     [esi+54h], eax
0x10009986  mov     dword ptr [esi+30h], 0
0x1000998d  movq    qword ptr [esi+40h], xmm0
0x10009992  mov     dword ptr [esi+48h], 0
0x10009999  movq    qword ptr [esi+34h], xmm0
0x1000999e  mov     dword ptr [esi+3Ch], 0
0x100099a5  test    edi, edi
0x100099a7  jz      short loc_100099B5
0x100099a9  mov     ecx, edi
0x100099ab  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100099b1  call    edi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x100099b3  jmp     short loc_100099B7
0x100099b5  xor     eax, eax
0x100099b7  mov     edi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x100099bd  mov     [esi+4Ch], eax
0x100099c0  test    edi, edi
0x100099c2  jz      short loc_100099CF
0x100099c4  push    esi; void *
0x100099c5  mov     ecx, edi
0x100099c7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100099cd  call    edi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x100099cf  mov     edi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x100099d5  test    edi, edi
0x100099d7  jz      short loc_100099EC
0x100099d9  push    400h
0x100099de  push    [ebp+arg_28]; unsigned int
0x100099e1  mov     ecx, edi
0x100099e3  push    esi; void *
0x100099e4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100099ea  call    edi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x100099ec  mov     edi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x100099f2  test    edi, edi
0x100099f4  jz      short loc_10009A01
0x100099f6  push    esi; void *
0x100099f7  mov     ecx, edi
0x100099f9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100099ff  call    edi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x10009a01  mov     edi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x10009a07  test    edi, edi
0x10009a09  jz      short loc_10009A1C
0x10009a0b  test    byte ptr [esi+4], 2
0x10009a0f  jnz     short loc_10009A1C
0x10009a11  push    esi; void *
0x10009a12  mov     ecx, edi
0x10009a14  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10009a1a  call    edi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x10009a1c  cmp     dword ptr [esi+8], 0
0x10009a20  jl      short loc_10009A40
0x10009a22  cmp     [ebp+arg_10], 3
0x10009a26  jnz     loc_10009B11
0x10009a2c  mov     ecx, 8000FFFFh
0x10009a31  mov     dword ptr [esi+8], 8000FFFFh
0x10009a38  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x10009a3d  mov     [esi+0Ch], eax
0x10009a40  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x10009a47  jnz     short loc_10009A72
0x10009a49  mov     edi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x10009a4f  test    edi, edi
0x10009a51  jz      short loc_10009A62
0x10009a53  mov     ecx, edi
0x10009a55  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10009a5b  call    edi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x10009a5d  movzx   eax, al
0x10009a60  jmp     short loc_10009A6E
0x10009a62  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x10009a68  neg     eax
0x10009a6a  sbb     eax, eax
0x10009a6c  neg     eax
0x10009a6e  test    eax, eax
0x10009a70  jz      short loc_10009A78
0x10009a72  test    byte ptr [esi+4], 2
0x10009a76  jz      short loc_10009A9C
0x10009a78  mov     edi, _g_pfnResultLoggingCallback
0x10009a7e  test    edi, edi
0x10009a80  jz      short loc_10009ADA
0x10009a82  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x10009a89  jnz     short loc_10009ADA
0x10009a8b  push    0
0x10009a8d  push    0; unsigned int
0x10009a8f  push    esi; void *
0x10009a90  mov     ecx, edi
0x10009a92  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10009a98  call    edi ; _g_pfnResultLoggingCallback
0x10009a9a  jmp     short loc_10009ADA
0x10009a9c  mov     edi, _g_pfnResultLoggingCallback
0x10009aa2  test    edi, edi
0x10009aa4  jz      short loc_10009AC0
0x10009aa6  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x10009aad  jnz     short loc_10009AC0
0x10009aaf  push    800h
0x10009ab4  push    ebx; unsigned int
0x10009ab5  push    esi; void *
0x10009ab6  mov     ecx, edi
0x10009ab8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10009abe  call    edi ; _g_pfnResultLoggingCallback
0x10009ac0  cmp     word ptr [ebx], 0
0x10009ac4  jnz     short loc_10009AD3
0x10009ac6  push    esi; this
0x10009ac7  mov     edx, 800h
0x10009acc  mov     ecx, ebx
0x10009ace  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x10009ad3  push    ebx; lpOutputString
0x10009ad4  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x10009ada  test    byte ptr [esi+4], 4
0x10009ade  jnz     short loc_10009AE9
0x10009ae0  cmp     ?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x10009ae7  jz      short loc_10009AFD
0x10009ae9  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x10009aef  test    esi, esi
0x10009af1  jz      short loc_10009AFD
0x10009af3  mov     ecx, esi
0x10009af5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10009afb  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x10009afd  mov     ecx, [ebp+var_C]
0x10009b00  mov     large fs:0, ecx
0x10009b07  pop     ecx
0x10009b08  pop     edi
0x10009b09  pop     esi
0x10009b0a  pop     ebx
0x10009b0b  mov     esp, ebp
0x10009b0d  pop     ebp
0x10009b0e  retn    38h ; '8'
0x10009b11  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1005f5d0  nop
0x1005f5d1  nop
0x1005f5d2  mov     edx, [esp-4+arg_4]
0x1005f5d6  lea     eax, [edx+0Ch]
0x1005f5d9  mov     ecx, [edx-1Ch]
0x1005f5dc  xor     ecx, eax; StackCookie
0x1005f5de  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f5e3  mov     eax, offset stru_10062AB0
0x1005f5e8  jmp     ___CxxFrameHandler3
```
