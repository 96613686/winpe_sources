# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1000dcc0`
- end: `0x1000dfbd`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@@Z`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x10009c00`

## callees

- `0x10008670`
- `0x10008b60`
- `0x10008e20`
- `0x10009b40`
- `0x1000dcc0`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f490`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000dd77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000dd77`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1000df7f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1000df7f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1000dee4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1000dee4`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int *a7)
{
  int v7; // eax
  int v8; // eax
  int v9; // ecx
  int v10; // edi
  int IsDebuggerPresent; // eax
  int v12; // [esp+0h] [ebp-1488h]
  wil::details *v13; // [esp+0h] [ebp-1488h]
  const struct wil::FailureInfo *v14; // [esp+4h] [ebp-1484h]
  const struct wil::FailureInfo *v15; // [esp+8h] [ebp-1480h]
  int v16; // [esp+10h] [ebp-1478h] BYREF
  int v17; // [esp+14h] [ebp-1474h]
  int v18; // [esp+18h] [ebp-1470h]
  int v19; // [esp+1Ch] [ebp-146Ch]
  signed __int32 v20; // [esp+20h] [ebp-1468h]
  int v21; // [esp+24h] [ebp-1464h]
  DWORD CurrentThreadId; // [esp+28h] [ebp-1460h]
  int v23; // [esp+2Ch] [ebp-145Ch]
  int v24; // [esp+30h] [ebp-1458h]
  int v25; // [esp+34h] [ebp-1454h]
  int v26; // [esp+38h] [ebp-1450h]
  int v27; // [esp+3Ch] [ebp-144Ch]
  int v28; // [esp+40h] [ebp-1448h]
  __int64 v29; // [esp+44h] [ebp-1444h]
  int v30; // [esp+4Ch] [ebp-143Ch]
  __int64 v31; // [esp+50h] [ebp-1438h]
  int v32; // [esp+58h] [ebp-1430h]
  int ModuleName; // [esp+5Ch] [ebp-142Ch]
  int v34; // [esp+60h] [ebp-1428h]
  int v35; // [esp+64h] [ebp-1424h]
  int v36; // [esp+6Ch] [ebp-141Ch]
  int v37; // [esp+70h] [ebp-1418h]
  int v38; // [esp+74h] [ebp-1414h]
  WCHAR OutputString[2048]; // [esp+78h] [ebp-1410h] BYREF
  unsigned int v40[257]; // [esp+1078h] [ebp-410h] BYREF
  int v41; // [esp+1484h] [ebp-4h]

  v38 = a2;
  v36 = a1;
  v37 = a6;
  v41 = 0;
  OutputString[0] = 0;
  LOBYTE(v40[0]) = 0;
  v7 = a7[1];
  v18 = *a7;
  v19 = v7;
  v8 = wil::details::RecordFailFast((wil::details *)v18, v12);
  v9 = 0;
  v16 = 3;
  v10 = v8;
  if ( a7[2] == 1 )
    v9 = 8;
  v17 = v9;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = v38;
  v34 = v37;
  v25 = a3;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v35 = v36;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(wil::details::g_pfnGetModuleName);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(wil::details::g_pfnNotifyFailure, &v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(wil::details::g_pfnGetContextAndNotifyFailure, &v16, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(wil::details::g_pfnLoggingCallback, &v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(wil::details::g_pfnOriginateCallback, &v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus(v13, (int)v14);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(wil::g_pfnIsDebuggerPresent)),
         IsDebuggerPresent))
    && (v17 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, &v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)&v16, (unsigned __int16 *)v13, (unsigned int)v14, v15);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, &v16, 0, 0);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(wil::details::g_pfnDebugBreak);
  }
  v41 = -1;
  wil::details::WilFailFast(v13, v14);
}

```

## disassembly

```asm
0x1000dcc0  mov     edi, edi
0x1000dcc2  push    ebp
0x1000dcc3  mov     ebp, esp
0x1000dcc5  push    0FFFFFFFFh
0x1000dcc7  push    offset ??$ReportFailure_NoReturn@$02@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@@Z_SEH
0x1000dccc  mov     eax, large fs:0
0x1000dcd2  push    eax
0x1000dcd3  mov     eax, 146Ch
0x1000dcd8  call    __chkstk
0x1000dcdd  push    ebx
0x1000dcde  push    esi; struct wil::FailureInfo *
0x1000dcdf  push    edi; struct wil::FailureInfo *
0x1000dce0  mov     eax, ___security_cookie
0x1000dce5  xor     eax, ebp
0x1000dce7  push    eax; this
0x1000dce8  lea     eax, [ebp+var_C]
0x1000dceb  mov     large fs:0, eax
0x1000dcf1  mov     [ebp+var_1414], edx
0x1000dcf7  mov     [ebp+var_141C], ecx
0x1000dcfd  mov     eax, [ebp+arg_C]
0x1000dd00  mov     ebx, [ebp+arg_0]
0x1000dd03  mov     [ebp+var_1418], eax
0x1000dd09  mov     esi, [ebp+arg_10]
0x1000dd0c  xor     eax, eax
0x1000dd0e  mov     [ebp+var_4], 0
0x1000dd15  mov     [ebp+OutputString], ax
0x1000dd1c  mov     byte ptr [ebp+var_410], al
0x1000dd22  mov     ecx, [esi]
0x1000dd24  mov     eax, [esi+4]
0x1000dd27  push    ecx; this
0x1000dd28  mov     [ebp+var_1470], ecx
0x1000dd2e  mov     [ebp+var_146C], eax
0x1000dd34  call    ?RecordFailFast@details@wil@@YGHJ@Z; wil::details::RecordFailFast(long)
0x1000dd39  xor     ecx, ecx
0x1000dd3b  mov     [ebp+var_1478], 3
0x1000dd45  cmp     dword ptr [esi+8], 1
0x1000dd49  mov     edi, eax
0x1000dd4b  mov     eax, 8
0x1000dd50  cmovz   ecx, eax
0x1000dd53  mov     [ebp+var_1474], ecx
0x1000dd59  mov     ecx, 1
0x1000dd5e  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1000dd66  inc     ecx
0x1000dd67  mov     [ebp+var_1468], ecx
0x1000dd6d  mov     [ebp+var_1464], 0
0x1000dd77  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000dd7d  mov     esi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1000dd83  xorps   xmm0, xmm0
0x1000dd86  mov     [ebp+var_1460], eax
0x1000dd8c  mov     eax, [ebp+var_1414]
0x1000dd92  mov     [ebp+var_1450], eax
0x1000dd98  mov     eax, [ebp+var_1418]
0x1000dd9e  mov     [ebp+var_1428], eax
0x1000dda4  mov     eax, [ebp+var_141C]
0x1000ddaa  mov     [ebp+var_1454], ebx
0x1000ddb0  mov     [ebp+var_144C], edi
0x1000ddb6  mov     [ebp+var_145C], 0
0x1000ddc0  mov     [ebp+var_1458], 0
0x1000ddca  mov     [ebp+var_1424], eax
0x1000ddd0  mov     [ebp+var_1448], 0
0x1000ddda  movq    [ebp+var_1438], xmm0
0x1000dde2  mov     [ebp+var_1430], 0
0x1000ddec  movq    [ebp+var_1444], xmm0
0x1000ddf4  mov     [ebp+var_143C], 0
0x1000ddfe  test    esi, esi
0x1000de00  jz      short loc_1000DE14
0x1000de02  mov     ecx, esi
0x1000de04  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000de0a  call    esi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1000de0c  mov     [ebp+var_142C], eax
0x1000de12  jmp     short loc_1000DE1E
0x1000de14  mov     [ebp+var_142C], 0
0x1000de1e  mov     esi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000de24  test    esi, esi
0x1000de26  jz      short loc_1000DE39
0x1000de28  lea     eax, [ebp+var_1478]
0x1000de2e  mov     ecx, esi
0x1000de30  push    eax; void *
0x1000de31  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000de37  call    esi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000de39  mov     esi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000de3f  test    esi, esi
0x1000de41  jz      short loc_1000DE60
0x1000de43  push    400h
0x1000de48  lea     eax, [ebp+var_410]
0x1000de4e  mov     ecx, esi
0x1000de50  push    eax; unsigned int
0x1000de51  lea     eax, [ebp+var_1478]
0x1000de57  push    eax; void *
0x1000de58  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000de5e  call    esi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000de60  mov     esi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000de66  test    esi, esi
0x1000de68  jz      short loc_1000DE7B
0x1000de6a  lea     eax, [ebp+var_1478]
0x1000de70  mov     ecx, esi
0x1000de72  push    eax; void *
0x1000de73  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000de79  call    esi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000de7b  mov     esi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000de81  test    esi, esi
0x1000de83  jz      short loc_1000DE9F
0x1000de85  test    byte ptr [ebp+var_1474], 2
0x1000de8c  jnz     short loc_1000DE9F
0x1000de8e  lea     eax, [ebp+var_1478]
0x1000de94  mov     ecx, esi
0x1000de96  push    eax; void *
0x1000de97  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000de9d  call    esi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000de9f  cmp     [ebp+var_1470], 0
0x1000dea6  jl      short loc_1000DEC2
0x1000dea8  mov     ecx, 8000FFFFh
0x1000dead  mov     [ebp+var_1470], 8000FFFFh
0x1000deb7  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x1000debc  mov     [ebp+var_146C], eax
0x1000dec2  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1000dec9  jnz     short loc_1000DEF4
0x1000decb  mov     esi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000ded1  test    esi, esi
0x1000ded3  jz      short loc_1000DEE4
0x1000ded5  mov     ecx, esi
0x1000ded7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000dedd  call    esi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000dedf  movzx   eax, al
0x1000dee2  jmp     short loc_1000DEF0
0x1000dee4  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x1000deea  neg     eax
0x1000deec  sbb     eax, eax
0x1000deee  neg     eax
0x1000def0  test    eax, eax
0x1000def2  jz      short loc_1000DEFD
0x1000def4  test    byte ptr [ebp+var_1474], 2
0x1000defb  jz      short loc_1000DF27
0x1000defd  mov     esi, _g_pfnResultLoggingCallback
0x1000df03  test    esi, esi
0x1000df05  jz      short loc_1000DF85
0x1000df07  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1000df0e  jnz     short loc_1000DF85
0x1000df10  push    0
0x1000df12  push    0; unsigned int
0x1000df14  lea     eax, [ebp+var_1478]
0x1000df1a  mov     ecx, esi
0x1000df1c  push    eax; void *
0x1000df1d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000df23  call    esi ; _g_pfnResultLoggingCallback
0x1000df25  jmp     short loc_1000DF85
0x1000df27  mov     esi, _g_pfnResultLoggingCallback
0x1000df2d  test    esi, esi
0x1000df2f  jz      short loc_1000DF57
0x1000df31  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1000df38  jnz     short loc_1000DF57
0x1000df3a  push    800h
0x1000df3f  lea     eax, [ebp+OutputString]
0x1000df45  mov     ecx, esi
0x1000df47  push    eax; unsigned int
0x1000df48  lea     eax, [ebp+var_1478]
0x1000df4e  push    eax; void *
0x1000df4f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000df55  call    esi ; _g_pfnResultLoggingCallback
0x1000df57  cmp     [ebp+OutputString], 0
0x1000df5f  jnz     short loc_1000DF78
0x1000df61  lea     eax, [ebp+var_1478]
0x1000df67  mov     edx, 800h
0x1000df6c  push    eax; this
0x1000df6d  lea     ecx, [ebp+OutputString]
0x1000df73  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x1000df78  lea     eax, [ebp+OutputString]
0x1000df7e  push    eax; lpOutputString
0x1000df7f  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1000df85  test    byte ptr [ebp+var_1474], 4
0x1000df8c  jnz     short loc_1000DF97
0x1000df8e  cmp     ?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1000df95  jz      short loc_1000DFAB
0x1000df97  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000df9d  test    esi, esi
0x1000df9f  jz      short loc_1000DFAB
0x1000dfa1  mov     ecx, esi
0x1000dfa3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000dfa9  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000dfab  lea     ecx, [ebp+var_1478]
0x1000dfb1  mov     [ebp+var_4], 0FFFFFFFFh
0x1000dfb8  call    ?WilFailFast@details@wil@@YGXABUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f920  nop
0x1005f921  nop
0x1005f922  mov     edx, [esp-4+arg_4]
0x1005f926  lea     eax, [edx+0Ch]
0x1005f929  mov     ecx, [edx-147Ch]
0x1005f92f  xor     ecx, eax; StackCookie
0x1005f931  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f936  mov     eax, offset stru_10062B00
0x1005f93b  jmp     ___CxxFrameHandler3
```
