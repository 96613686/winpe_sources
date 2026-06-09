# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1000e820`
- end: `0x1000eb20`
- name: `??$ReportFailure_Return@$00@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1000dfd0`

## callees

- `0x10008670`
- `0x10008b20`
- `0x10009b40`
- `0x10009e60`
- `0x1000e820`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f490`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000e8cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000e8cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1000eab6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1000eab6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1000ea1b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1000ea1b`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int *a7,
        int a8,
        int a9,
        int a10)
{
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // edx
  int IsDebuggerPresent; // eax
  wil::details *v16; // [esp+0h] [ebp-1480h]
  wil::details::in1diag3 *v17; // [esp+0h] [ebp-1480h]
  int v18; // [esp+4h] [ebp-147Ch]
  const struct wil::FailureInfo *v19; // [esp+4h] [ebp-147Ch]
  const struct wil::FailureInfo *v20; // [esp+8h] [ebp-1478h]
  int v21; // [esp+10h] [ebp-1470h] BYREF
  int v22; // [esp+14h] [ebp-146Ch]
  int v23; // [esp+18h] [ebp-1468h]
  int v24; // [esp+1Ch] [ebp-1464h]
  signed __int32 v25; // [esp+20h] [ebp-1460h]
  int v26; // [esp+24h] [ebp-145Ch]
  DWORD CurrentThreadId; // [esp+28h] [ebp-1458h]
  int v28; // [esp+2Ch] [ebp-1454h]
  int v29; // [esp+30h] [ebp-1450h]
  const char *v30; // [esp+34h] [ebp-144Ch]
  int v31; // [esp+38h] [ebp-1448h]
  int v32; // [esp+3Ch] [ebp-1444h]
  int v33; // [esp+40h] [ebp-1440h]
  __int64 v34; // [esp+44h] [ebp-143Ch]
  int v35; // [esp+4Ch] [ebp-1434h]
  __int64 v36; // [esp+50h] [ebp-1430h]
  int v37; // [esp+58h] [ebp-1428h]
  int ModuleName; // [esp+5Ch] [ebp-1424h]
  int v39; // [esp+60h] [ebp-1420h]
  int v40; // [esp+64h] [ebp-141Ch]
  int v41; // [esp+6Ch] [ebp-1414h]
  WCHAR OutputString[2048]; // [esp+70h] [ebp-1410h] BYREF
  unsigned int v43[256]; // [esp+1070h] [ebp-410h] BYREF
  int v44; // [esp+147Ch] [ebp-4h]

  v41 = a1;
  v44 = 0;
  OutputString[0] = 0;
  LOBYTE(v43[0]) = 0;
  v11 = a7[1];
  v23 = *a7;
  v24 = v11;
  v12 = wil::details::RecordReturn(v16, v18);
  v13 = 0;
  v21 = 1;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v26 = 0;
  v32 = v12;
  CurrentThreadId = GetCurrentThreadId();
  v30 = "wil";
  v31 = a2;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = v41;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(wil::details::g_pfnGetModuleName);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(wil::details::g_pfnNotifyFailure, &v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(wil::details::g_pfnGetContextAndNotifyFailure, &v21, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(wil::details::g_pfnLoggingCallback, &v21);
  if ( wil::details::g_pfnOriginateCallback && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(wil::details::g_pfnOriginateCallback, &v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(wil::g_pfnIsDebuggerPresent)),
         IsDebuggerPresent))
    && (v22 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, &v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)&v21, (unsigned __int16 *)v17, (unsigned int)v19, v20);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, &v21, 0, 0);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(wil::details::g_pfnDebugBreak);
  v44 = -1;
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast(v17, v19);
}

```

## disassembly

```asm
0x1000e820  mov     edi, edi
0x1000e822  push    ebp
0x1000e823  mov     ebp, esp
0x1000e825  push    0FFFFFFFFh
0x1000e827  push    offset ??$ReportFailure_Return@$00@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z_SEH
0x1000e82c  mov     eax, large fs:0
0x1000e832  push    eax
0x1000e833  mov     eax, 1464h
0x1000e838  call    __chkstk
0x1000e83d  mov     eax, ___security_cookie
0x1000e842  xor     eax, ebp
0x1000e844  mov     [ebp+var_10], eax
0x1000e847  push    ebx
0x1000e848  push    esi; struct wil::FailureInfo *
0x1000e849  push    edi; struct wil::FailureInfo *
0x1000e84a  push    eax; this
0x1000e84b  lea     eax, [ebp+var_C]
0x1000e84e  mov     large fs:0, eax
0x1000e854  mov     edi, edx
0x1000e856  mov     [ebp+var_1414], ecx
0x1000e85c  mov     ebx, [ebp+arg_C]
0x1000e85f  mov     edx, [ebp+arg_10]
0x1000e862  xor     eax, eax
0x1000e864  mov     [ebp+var_4], 0
0x1000e86b  mov     [ebp+OutputString], ax
0x1000e872  mov     byte ptr [ebp+var_410], al
0x1000e878  mov     ecx, [edx]
0x1000e87a  mov     eax, [edx+4]
0x1000e87d  mov     [ebp+var_1468], ecx
0x1000e883  mov     [ebp+var_1464], eax
0x1000e889  call    ?RecordReturn@details@wil@@YGHJ@Z; wil::details::RecordReturn(long)
0x1000e88e  xor     ecx, ecx
0x1000e890  mov     [ebp+var_1470], 1
0x1000e89a  cmp     dword ptr [edx+8], 1
0x1000e89e  mov     esi, eax
0x1000e8a0  mov     eax, 8
0x1000e8a5  cmovz   ecx, eax
0x1000e8a8  mov     [ebp+var_146C], ecx
0x1000e8ae  mov     ecx, 1
0x1000e8b3  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1000e8bb  inc     ecx
0x1000e8bc  mov     [ebp+var_1460], ecx
0x1000e8c2  mov     [ebp+var_145C], 0
0x1000e8cc  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000e8d2  mov     [ebp+var_1444], esi
0x1000e8d8  xorps   xmm0, xmm0
0x1000e8db  mov     esi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1000e8e1  mov     [ebp+var_1458], eax
0x1000e8e7  mov     eax, [ebp+var_1414]
0x1000e8ed  mov     [ebp+var_144C], offset aWil; "wil"
0x1000e8f7  mov     [ebp+var_1448], edi
0x1000e8fd  mov     [ebp+var_1454], 0
0x1000e907  mov     [ebp+var_1450], 0
0x1000e911  mov     [ebp+var_1420], ebx
0x1000e917  mov     [ebp+var_141C], eax
0x1000e91d  mov     [ebp+var_1440], 0
0x1000e927  movq    [ebp+var_1430], xmm0
0x1000e92f  mov     [ebp+var_1428], 0
0x1000e939  movq    [ebp+var_143C], xmm0
0x1000e941  mov     [ebp+var_1434], 0
0x1000e94b  test    esi, esi
0x1000e94d  jz      short loc_1000E961
0x1000e94f  mov     ecx, esi
0x1000e951  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000e957  call    esi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1000e959  mov     [ebp+var_1424], eax
0x1000e95f  jmp     short loc_1000E96B
0x1000e961  mov     [ebp+var_1424], 0
0x1000e96b  mov     esi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000e971  test    esi, esi
0x1000e973  jz      short loc_1000E986
0x1000e975  lea     eax, [ebp+var_1470]
0x1000e97b  mov     ecx, esi
0x1000e97d  push    eax; void *
0x1000e97e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000e984  call    esi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000e986  mov     esi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000e98c  test    esi, esi
0x1000e98e  jz      short loc_1000E9AD
0x1000e990  push    400h
0x1000e995  lea     eax, [ebp+var_410]
0x1000e99b  mov     ecx, esi
0x1000e99d  push    eax; unsigned int
0x1000e99e  lea     eax, [ebp+var_1470]
0x1000e9a4  push    eax; void *
0x1000e9a5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000e9ab  call    esi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000e9ad  mov     esi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000e9b3  test    esi, esi
0x1000e9b5  jz      short loc_1000E9C8
0x1000e9b7  lea     eax, [ebp+var_1470]
0x1000e9bd  mov     ecx, esi
0x1000e9bf  push    eax; void *
0x1000e9c0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000e9c6  call    esi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000e9c8  mov     esi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000e9ce  test    esi, esi
0x1000e9d0  jz      short loc_1000E9EC
0x1000e9d2  test    byte ptr [ebp+var_146C], 2
0x1000e9d9  jnz     short loc_1000E9EC
0x1000e9db  lea     eax, [ebp+var_1470]
0x1000e9e1  mov     ecx, esi
0x1000e9e3  push    eax; void *
0x1000e9e4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000e9ea  call    esi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000e9ec  cmp     [ebp+var_1468], 0
0x1000e9f3  jge     loc_1000EB10
0x1000e9f9  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1000ea00  jnz     short loc_1000EA2B
0x1000ea02  mov     esi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000ea08  test    esi, esi
0x1000ea0a  jz      short loc_1000EA1B
0x1000ea0c  mov     ecx, esi
0x1000ea0e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000ea14  call    esi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000ea16  movzx   eax, al
0x1000ea19  jmp     short loc_1000EA27
0x1000ea1b  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x1000ea21  neg     eax
0x1000ea23  sbb     eax, eax
0x1000ea25  neg     eax
0x1000ea27  test    eax, eax
0x1000ea29  jz      short loc_1000EA34
0x1000ea2b  test    byte ptr [ebp+var_146C], 2
0x1000ea32  jz      short loc_1000EA5E
0x1000ea34  mov     esi, _g_pfnResultLoggingCallback
0x1000ea3a  test    esi, esi
0x1000ea3c  jz      short loc_1000EABC
0x1000ea3e  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1000ea45  jnz     short loc_1000EABC
0x1000ea47  push    0
0x1000ea49  push    0; unsigned int
0x1000ea4b  lea     eax, [ebp+var_1470]
0x1000ea51  mov     ecx, esi
0x1000ea53  push    eax; void *
0x1000ea54  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000ea5a  call    esi ; _g_pfnResultLoggingCallback
0x1000ea5c  jmp     short loc_1000EABC
0x1000ea5e  mov     esi, _g_pfnResultLoggingCallback
0x1000ea64  test    esi, esi
0x1000ea66  jz      short loc_1000EA8E
0x1000ea68  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1000ea6f  jnz     short loc_1000EA8E
0x1000ea71  push    800h
0x1000ea76  lea     eax, [ebp+OutputString]
0x1000ea7c  mov     ecx, esi
0x1000ea7e  push    eax; unsigned int
0x1000ea7f  lea     eax, [ebp+var_1470]
0x1000ea85  push    eax; void *
0x1000ea86  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000ea8c  call    esi ; _g_pfnResultLoggingCallback
0x1000ea8e  cmp     [ebp+OutputString], 0
0x1000ea96  jnz     short loc_1000EAAF
0x1000ea98  lea     eax, [ebp+var_1470]
0x1000ea9e  mov     edx, 800h
0x1000eaa3  push    eax; this
0x1000eaa4  lea     ecx, [ebp+OutputString]
0x1000eaaa  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x1000eaaf  lea     eax, [ebp+OutputString]
0x1000eab5  push    eax; lpOutputString
0x1000eab6  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1000eabc  test    byte ptr [ebp+var_146C], 4
0x1000eac3  jnz     short loc_1000EACE
0x1000eac5  cmp     ?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1000eacc  jz      short loc_1000EAE2
0x1000eace  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000ead4  test    esi, esi
0x1000ead6  jz      short loc_1000EAE2
0x1000ead8  mov     ecx, esi
0x1000eada  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000eae0  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000eae2  mov     [ebp+var_4], 0FFFFFFFFh
0x1000eae9  test    byte ptr [ebp+var_146C], 1
0x1000eaf0  jnz     short loc_1000EB15
0x1000eaf2  mov     ecx, [ebp+var_C]
0x1000eaf5  mov     large fs:0, ecx
0x1000eafc  pop     ecx
0x1000eafd  pop     edi
0x1000eafe  pop     esi
0x1000eaff  pop     ebx
0x1000eb00  mov     ecx, [ebp+var_10]
0x1000eb03  xor     ecx, ebp; StackCookie
0x1000eb05  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000eb0a  mov     esp, ebp
0x1000eb0c  pop     ebp
0x1000eb0d  retn    20h ; ' '
0x1000eb10  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1000eb15  lea     ecx, [ebp+var_1470]
0x1000eb1b  call    ?WilFailFast@details@wil@@YGXABUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f9e0  nop
0x1005f9e1  nop
0x1005f9e2  mov     edx, [esp-4+arg_4]
0x1005f9e6  lea     eax, [edx+0Ch]
0x1005f9e9  mov     ecx, [edx-1474h]
0x1005f9ef  xor     ecx, eax; StackCookie
0x1005f9f1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f9f6  mov     ecx, [edx-4]
0x1005f9f9  xor     ecx, eax; StackCookie
0x1005f9fb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005fa00  mov     eax, offset stru_10062B00
0x1005fa05  jmp     ___CxxFrameHandler3
```
