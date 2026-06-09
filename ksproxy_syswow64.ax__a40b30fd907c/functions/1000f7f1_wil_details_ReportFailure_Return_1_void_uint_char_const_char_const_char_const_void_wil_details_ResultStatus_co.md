# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1000f7f1`
- end: `0x1000fa63`
- name: `??$ReportFailure_Return@$00@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `626`
- prototype: `void __fastcall(int, int, int, int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1000f4db`

## callees

- `0x10006a5c`
- `0x10006d89`
- `0x10007460`
- `0x10007624`
- `0x1000f7f1`
- `0x1002d510`
- `0x1003aba0`
- `0x1003b810`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1000fa0e`
- `KERNEL32!OutputDebugStringW` at `0x1000fa0e`
- `KERNEL32!GetCurrentThreadId` at `0x1000f876`
- `KERNEL32!GetCurrentThreadId` at `0x1000f876`
- `KERNEL32!IsDebuggerPresent` at `0x1000f97e`
- `KERNEL32!IsDebuggerPresent` at `0x1000f97e`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  int v10; // eax
  int v11; // eax
  int v12; // ecx
  int v13; // edi
  int v14; // eax
  wil::details::in1diag3 *v15; // [esp+Ch] [ebp-1478h]
  const struct wil::FailureInfo *v16; // [esp+10h] [ebp-1474h]
  const struct wil::FailureInfo *v17; // [esp+14h] [ebp-1470h]
  int v20; // [esp+24h] [ebp-1460h] BYREF
  int v21; // [esp+28h] [ebp-145Ch]
  void *v22; // [esp+2Ch] [ebp-1458h]
  int v23; // [esp+30h] [ebp-1454h]
  signed __int32 v24; // [esp+34h] [ebp-1450h]
  int v25; // [esp+38h] [ebp-144Ch]
  DWORD CurrentThreadId; // [esp+3Ch] [ebp-1448h]
  int v27; // [esp+40h] [ebp-1444h]
  int v28; // [esp+44h] [ebp-1440h]
  int v29; // [esp+48h] [ebp-143Ch]
  int v30; // [esp+4Ch] [ebp-1438h]
  int v31; // [esp+50h] [ebp-1434h]
  int v32; // [esp+54h] [ebp-1430h]
  int v33; // [esp+58h] [ebp-142Ch]
  int v34; // [esp+5Ch] [ebp-1428h]
  int v35; // [esp+60h] [ebp-1424h]
  int v36; // [esp+64h] [ebp-1420h]
  int v37; // [esp+68h] [ebp-141Ch]
  int v38; // [esp+6Ch] [ebp-1418h]
  int v39; // [esp+70h] [ebp-1414h]
  int v40; // [esp+74h] [ebp-1410h]
  int v41; // [esp+78h] [ebp-140Ch]
  char v42[1024]; // [esp+7Ch] [ebp-1408h] BYREF
  WCHAR OutputString[2050]; // [esp+47Ch] [ebp-1008h] BYREF

  OutputString[0] = 0;
  v42[0] = 0;
  v10 = *(_DWORD *)(a7 + 4);
  v22 = *(void **)a7;
  v23 = v10;
  v11 = wil::details::RecordReturn(v22);
  v12 = 0;
  v13 = v11;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v12 = 8;
  v20 = 1;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a2;
  v40 = a6;
  v29 = a3;
  v31 = v13;
  v41 = a1;
  v27 = 0;
  v28 = 0;
  v32 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    v39 = ((int (__thiscall *)(CD3DSurfaceAllocator *))wil::details::g_pfnGetModuleName)(wil::details::g_pfnGetModuleName);
  else
    v39 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *))wil::details::g_pfnNotifyFailure)(
      wil::details::g_pfnNotifyFailure,
      &v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *, char *, int))wil::details::g_pfnGetContextAndNotifyFailure)(
      wil::details::g_pfnGetContextAndNotifyFailure,
      &v20,
      v42,
      1024);
  if ( wil::details::g_pfnLoggingCallback )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *))wil::details::g_pfnLoggingCallback)(
      wil::details::g_pfnLoggingCallback,
      &v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *))wil::details::g_pfnOriginateCallback)(
      wil::details::g_pfnOriginateCallback,
      &v20);
  if ( (int)v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (v14 = IsDebuggerPresent())
       : (v14 = (unsigned __int8)((int (__thiscall *)(CD3DSurfaceAllocator *))wil::g_pfnIsDebuggerPresent)(wil::g_pfnIsDebuggerPresent)),
         v14))
    && (v21 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      ((void (__thiscall *)(CD3DSurfaceAllocator *, int *, WCHAR *, int))g_pfnResultLoggingCallback)(
        g_pfnResultLoggingCallback,
        &v20,
        OutputString,
        2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(
        2048,
        (wil::details *)OutputString,
        0,
        (wil *)&v20,
        (unsigned __int16 *)v15,
        (unsigned int)v16,
        v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *, _DWORD, _DWORD))g_pfnResultLoggingCallback)(
      g_pfnResultLoggingCallback,
      &v20,
      0,
      0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    ((void (__thiscall *)(CD3DSurfaceAllocator *))wil::details::g_pfnDebugBreak)(wil::details::g_pfnDebugBreak);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast(&v20, v15, v16);
}

```

## disassembly

```asm
0x1000f7f1  mov     edi, edi
0x1000f7f3  push    ebp
0x1000f7f4  mov     ebp, esp
0x1000f7f6  and     esp, 0FFFFFFF8h
0x1000f7f9  mov     eax, 146Ch
0x1000f7fe  call    __chkstk
0x1000f803  mov     eax, ___security_cookie
0x1000f808  xor     eax, esp
0x1000f80a  mov     [esp+146Ch+var_4], eax
0x1000f811  mov     eax, [ebp+arg_C]
0x1000f814  push    ebx; struct wil::FailureInfo *
0x1000f815  mov     ebx, [ebp+arg_0]
0x1000f818  push    esi; struct wil::FailureInfo *
0x1000f819  mov     esi, [ebp+arg_10]
0x1000f81c  mov     [esp+1474h+var_1468], eax
0x1000f820  xor     eax, eax
0x1000f822  mov     [esp+1474h+OutputString], ax
0x1000f82a  mov     [esp+1474h+var_1408], al
0x1000f82e  mov     eax, [esi+4]
0x1000f831  mov     [esp+1474h+var_1464], ecx
0x1000f835  mov     ecx, [esi]
0x1000f837  push    edi; this
0x1000f838  mov     [esp+1478h+var_146C], edx
0x1000f83c  mov     [esp+1478h+var_1458], ecx
0x1000f840  mov     [esp+1478h+var_1454], eax
0x1000f844  call    ?RecordReturn@details@wil@@YGHJ@Z; wil::details::RecordReturn(long)
0x1000f849  xor     edx, edx
0x1000f84b  xor     ecx, ecx
0x1000f84d  inc     edx
0x1000f84e  mov     edi, eax
0x1000f850  cmp     [esi+8], edx
0x1000f853  push    8
0x1000f855  pop     eax
0x1000f856  cmovz   ecx, eax
0x1000f859  mov     [esp+1478h+var_1460], edx
0x1000f85d  mov     [esp+1478h+var_145C], ecx
0x1000f861  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1000f869  inc     edx
0x1000f86a  mov     [esp+1478h+var_1450], edx
0x1000f86e  mov     [esp+1478h+var_144C], 0
0x1000f876  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000f87c  mov     [esp+1478h+var_1448], eax
0x1000f880  mov     eax, [esp+1478h+var_146C]
0x1000f884  mov     [esp+1478h+var_1438], eax
0x1000f888  mov     eax, [esp+1478h+var_1468]
0x1000f88c  mov     [esp+1478h+var_1410], eax
0x1000f890  mov     eax, [esp+1478h+var_1464]
0x1000f894  mov     [esp+1478h+var_143C], ebx
0x1000f898  xor     ebx, ebx
0x1000f89a  mov     [esp+1478h+var_1434], edi
0x1000f89e  lea     edi, [esp+1478h+var_1420]
0x1000f8a2  mov     [esp+1478h+var_140C], eax
0x1000f8a6  xor     eax, eax
0x1000f8a8  mov     esi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1000f8ae  mov     [esp+1478h+var_1444], ebx
0x1000f8b2  mov     [esp+1478h+var_1440], ebx
0x1000f8b6  mov     [esp+1478h+var_1430], ebx
0x1000f8ba  stosd
0x1000f8bb  stosd
0x1000f8bc  stosd
0x1000f8bd  xor     eax, eax
0x1000f8bf  lea     edi, [esp+1478h+var_142C]
0x1000f8c3  stosd
0x1000f8c4  stosd
0x1000f8c5  stosd
0x1000f8c6  test    esi, esi
0x1000f8c8  jz      short loc_1000F8DA
0x1000f8ca  mov     ecx, esi; this
0x1000f8cc  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f8d2  call    esi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1000f8d4  mov     [esp+1478h+var_1414], eax
0x1000f8d8  jmp     short loc_1000F8DE
0x1000f8da  mov     [esp+1478h+var_1414], ebx
0x1000f8de  mov     esi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000f8e4  test    esi, esi
0x1000f8e6  jz      short loc_1000F8F7
0x1000f8e8  lea     eax, [esp+1478h+var_1460]
0x1000f8ec  mov     ecx, esi; this
0x1000f8ee  push    eax
0x1000f8ef  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f8f5  call    esi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000f8f7  mov     esi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000f8fd  test    esi, esi
0x1000f8ff  jz      short loc_1000F91A
0x1000f901  push    400h
0x1000f906  lea     eax, [esp+147Ch+var_1408]
0x1000f90a  mov     ecx, esi; this
0x1000f90c  push    eax
0x1000f90d  lea     eax, [esp+1480h+var_1460]
0x1000f911  push    eax
0x1000f912  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f918  call    esi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000f91a  mov     esi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000f920  test    esi, esi
0x1000f922  jz      short loc_1000F933
0x1000f924  lea     eax, [esp+1478h+var_1460]
0x1000f928  mov     ecx, esi; this
0x1000f92a  push    eax
0x1000f92b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f931  call    esi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000f933  mov     esi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000f939  test    esi, esi
0x1000f93b  jz      short loc_1000F953
0x1000f93d  test    byte ptr [esp+1478h+var_145C], 2
0x1000f942  jnz     short loc_1000F953
0x1000f944  lea     eax, [esp+1478h+var_1460]
0x1000f948  mov     ecx, esi; this
0x1000f94a  push    eax
0x1000f94b  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f951  call    esi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000f953  cmp     [esp+1478h+var_1458], ebx
0x1000f957  jge     loc_1000FA55
0x1000f95d  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x1000f963  jnz     short loc_1000F98E
0x1000f965  mov     esi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000f96b  test    esi, esi
0x1000f96d  jz      short loc_1000F97E
0x1000f96f  mov     ecx, esi; this
0x1000f971  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f977  call    esi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000f979  movzx   eax, al
0x1000f97c  jmp     short loc_1000F98A
0x1000f97e  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x1000f984  neg     eax
0x1000f986  sbb     eax, eax
0x1000f988  neg     eax
0x1000f98a  test    eax, eax
0x1000f98c  jz      short loc_1000F995
0x1000f98e  test    byte ptr [esp+1478h+var_145C], 2
0x1000f993  jz      short loc_1000F9BA
0x1000f995  mov     esi, _g_pfnResultLoggingCallback
0x1000f99b  test    esi, esi
0x1000f99d  jz      short loc_1000FA14
0x1000f99f  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x1000f9a5  jnz     short loc_1000FA14
0x1000f9a7  push    ebx
0x1000f9a8  push    ebx
0x1000f9a9  lea     eax, [esp+1480h+var_1460]
0x1000f9ad  mov     ecx, esi; this
0x1000f9af  push    eax
0x1000f9b0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f9b6  call    esi ; _g_pfnResultLoggingCallback
0x1000f9b8  jmp     short loc_1000FA14
0x1000f9ba  mov     esi, _g_pfnResultLoggingCallback
0x1000f9c0  mov     edi, 800h
0x1000f9c5  test    esi, esi
0x1000f9c7  jz      short loc_1000F9E9
0x1000f9c9  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x1000f9cf  jnz     short loc_1000F9E9
0x1000f9d1  push    edi
0x1000f9d2  lea     eax, [esp+147Ch+OutputString]
0x1000f9d9  mov     ecx, esi; this
0x1000f9db  push    eax
0x1000f9dc  lea     eax, [esp+1480h+var_1460]
0x1000f9e0  push    eax
0x1000f9e1  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f9e7  call    esi ; _g_pfnResultLoggingCallback
0x1000f9e9  cmp     [esp+1478h+OutputString], bx
0x1000f9f1  jnz     short loc_1000FA06
0x1000f9f3  lea     eax, [esp+1478h+var_1460]
0x1000f9f7  mov     edx, edi
0x1000f9f9  push    eax; this
0x1000f9fa  lea     ecx, [esp+147Ch+OutputString]
0x1000fa01  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x1000fa06  lea     eax, [esp+1478h+OutputString]
0x1000fa0d  push    eax; lpOutputString
0x1000fa0e  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1000fa14  test    byte ptr [esp+1478h+var_145C], 4
0x1000fa19  jnz     short loc_1000FA23
0x1000fa1b  cmp     ?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x1000fa21  jz      short loc_1000FA37
0x1000fa23  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000fa29  test    esi, esi
0x1000fa2b  jz      short loc_1000FA37
0x1000fa2d  mov     ecx, esi; this
0x1000fa2f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000fa35  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000fa37  test    byte ptr [esp+1478h+var_145C], 1
0x1000fa3c  jnz     short loc_1000FA5A
0x1000fa3e  mov     ecx, [esp+1478h+var_4]
0x1000fa45  pop     edi
0x1000fa46  pop     esi
0x1000fa47  pop     ebx
0x1000fa48  xor     ecx, esp; StackCookie
0x1000fa4a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000fa4f  mov     esp, ebp
0x1000fa51  pop     ebp
0x1000fa52  retn    20h ; ' '
0x1000fa55  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1000fa5a  lea     ecx, [esp+1478h+var_1460]
0x1000fa5e  call    ?WilFailFast@details@wil@@YGXABUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
