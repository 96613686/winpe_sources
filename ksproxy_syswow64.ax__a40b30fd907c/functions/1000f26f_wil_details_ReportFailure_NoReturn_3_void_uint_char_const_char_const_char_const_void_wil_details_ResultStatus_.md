# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1000f26f`
- end: `0x1000f4c3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@@Z`
- size: `596`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x100074ed`

## callees

- `0x10006a5c`
- `0x10006dc0`
- `0x10006f61`
- `0x10007460`
- `0x1000f26f`
- `0x1002d510`
- `0x1003b810`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1000f491`
- `KERNEL32!OutputDebugStringW` at `0x1000f491`
- `KERNEL32!GetCurrentThreadId` at `0x1000f2eb`
- `KERNEL32!GetCurrentThreadId` at `0x1000f2eb`
- `KERNEL32!IsDebuggerPresent` at `0x1000f401`
- `KERNEL32!IsDebuggerPresent` at `0x1000f401`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7)
{
  wil::details *v7; // ecx
  unsigned int v8; // eax
  int v9; // eax
  int v10; // ecx
  int v11; // edi
  int v12; // eax
  int v13; // [esp+Ch] [ebp-1470h]
  unsigned __int16 *v14; // [esp+Ch] [ebp-1470h]
  const struct wil::FailureInfo *v15; // [esp+10h] [ebp-146Ch]
  const struct wil::FailureInfo *v16; // [esp+14h] [ebp-1468h]
  int v19; // [esp+24h] [ebp-1458h] BYREF
  int v20; // [esp+28h] [ebp-1454h]
  int v21; // [esp+2Ch] [ebp-1450h]
  unsigned int v22; // [esp+30h] [ebp-144Ch]
  signed __int32 v23; // [esp+34h] [ebp-1448h]
  int v24; // [esp+38h] [ebp-1444h]
  DWORD CurrentThreadId; // [esp+3Ch] [ebp-1440h]
  int v26; // [esp+40h] [ebp-143Ch]
  int v27; // [esp+44h] [ebp-1438h]
  int v28; // [esp+48h] [ebp-1434h]
  int v29; // [esp+4Ch] [ebp-1430h]
  int v30; // [esp+50h] [ebp-142Ch]
  int v31; // [esp+54h] [ebp-1428h]
  int v32; // [esp+58h] [ebp-1424h]
  int v33; // [esp+5Ch] [ebp-1420h]
  int v34; // [esp+60h] [ebp-141Ch]
  int v35; // [esp+64h] [ebp-1418h]
  int v36; // [esp+68h] [ebp-1414h]
  int v37; // [esp+6Ch] [ebp-1410h]
  int v38; // [esp+70h] [ebp-140Ch]
  int v39; // [esp+74h] [ebp-1408h]
  int v40; // [esp+78h] [ebp-1404h]
  char v41[1024]; // [esp+7Ch] [ebp-1400h] BYREF
  WCHAR OutputString[2048]; // [esp+47Ch] [ebp-1000h] BYREF

  v7 = *(wil::details **)a7;
  OutputString[0] = 0;
  v41[0] = 0;
  v8 = *(_DWORD *)(a7 + 4);
  v21 = (int)v7;
  v22 = v8;
  v9 = wil::details::RecordFailFast(v7, v13);
  v19 = 3;
  v10 = 0;
  v11 = v9;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v10 = 8;
  v20 = v10;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v39 = a6;
  v28 = a3;
  v30 = v11;
  v40 = a1;
  v26 = 0;
  v27 = 0;
  v31 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    v38 = ((int (__thiscall *)(CD3DSurfaceAllocator *))wil::details::g_pfnGetModuleName)(wil::details::g_pfnGetModuleName);
  else
    v38 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *))wil::details::g_pfnNotifyFailure)(
      wil::details::g_pfnNotifyFailure,
      &v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *, char *, int))wil::details::g_pfnGetContextAndNotifyFailure)(
      wil::details::g_pfnGetContextAndNotifyFailure,
      &v19,
      v41,
      1024);
  if ( wil::details::g_pfnLoggingCallback )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *))wil::details::g_pfnLoggingCallback)(
      wil::details::g_pfnLoggingCallback,
      &v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *))wil::details::g_pfnOriginateCallback)(
      wil::details::g_pfnOriginateCallback,
      &v19);
  if ( v21 >= 0 )
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus(-2147418113);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (v12 = IsDebuggerPresent())
       : (v12 = (unsigned __int8)((int (__thiscall *)(CD3DSurfaceAllocator *))wil::g_pfnIsDebuggerPresent)(wil::g_pfnIsDebuggerPresent)),
         v12))
    && (v20 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      ((void (__thiscall *)(CD3DSurfaceAllocator *, int *, WCHAR *, int))g_pfnResultLoggingCallback)(
        g_pfnResultLoggingCallback,
        &v19,
        OutputString,
        2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(2048, (wil::details *)OutputString, 0, (wil *)&v19, v14, (unsigned int)v15, v16);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    ((void (__thiscall *)(CD3DSurfaceAllocator *, int *, _DWORD, _DWORD))g_pfnResultLoggingCallback)(
      g_pfnResultLoggingCallback,
      &v19,
      0,
      0);
  }
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      ((void (__thiscall *)(CD3DSurfaceAllocator *))wil::details::g_pfnDebugBreak)(wil::details::g_pfnDebugBreak);
  }
  wil::details::WilFailFast(&v19, (wil::details *)v14, v15);
}

```

## disassembly

```asm
0x1000f26f  mov     edi, edi
0x1000f271  push    ebp
0x1000f272  mov     ebp, esp
0x1000f274  and     esp, 0FFFFFFF8h
0x1000f277  mov     eax, 1464h
0x1000f27c  call    __chkstk
0x1000f281  mov     eax, [ebp+arg_C]
0x1000f284  push    ebx; struct wil::FailureInfo *
0x1000f285  mov     ebx, [ebp+arg_0]
0x1000f288  push    esi; struct wil::FailureInfo *
0x1000f289  mov     esi, [ebp+arg_10]
0x1000f28c  mov     [esp+146Ch+var_1460], eax
0x1000f290  xor     eax, eax
0x1000f292  push    edi; this
0x1000f293  mov     [esp+1470h+var_145C], ecx
0x1000f297  mov     ecx, [esi]
0x1000f299  mov     [esp+1470h+OutputString], ax
0x1000f2a1  mov     [esp+1470h+var_1400], al
0x1000f2a5  mov     eax, [esi+4]
0x1000f2a8  push    ecx; this
0x1000f2a9  mov     [esp+1474h+var_1464], edx
0x1000f2ad  mov     [esp+1474h+var_1450], ecx
0x1000f2b1  mov     [esp+1474h+var_144C], eax
0x1000f2b5  call    ?RecordFailFast@details@wil@@YGHJ@Z; wil::details::RecordFailFast(long)
0x1000f2ba  xor     edx, edx
0x1000f2bc  mov     [esp+1470h+var_1458], 3
0x1000f2c4  xor     ecx, ecx
0x1000f2c6  inc     edx
0x1000f2c7  cmp     [esi+8], edx
0x1000f2ca  mov     edi, eax
0x1000f2cc  push    8
0x1000f2ce  pop     eax
0x1000f2cf  cmovz   ecx, eax
0x1000f2d2  mov     [esp+1470h+var_1454], ecx
0x1000f2d6  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1000f2de  inc     edx
0x1000f2df  mov     [esp+1470h+var_1448], edx
0x1000f2e3  mov     [esp+1470h+var_1444], 0
0x1000f2eb  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000f2f1  mov     [esp+1470h+var_1440], eax
0x1000f2f5  mov     eax, [esp+1470h+var_1464]
0x1000f2f9  mov     [esp+1470h+var_1430], eax
0x1000f2fd  mov     eax, [esp+1470h+var_1460]
0x1000f301  mov     [esp+1470h+var_1408], eax
0x1000f305  mov     eax, [esp+1470h+var_145C]
0x1000f309  mov     [esp+1470h+var_1434], ebx
0x1000f30d  xor     ebx, ebx
0x1000f30f  mov     [esp+1470h+var_142C], edi
0x1000f313  lea     edi, [esp+1470h+var_1418]
0x1000f317  mov     [esp+1470h+var_1404], eax
0x1000f31b  xor     eax, eax
0x1000f31d  mov     esi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1000f323  mov     [esp+1470h+var_143C], ebx
0x1000f327  mov     [esp+1470h+var_1438], ebx
0x1000f32b  mov     [esp+1470h+var_1428], ebx
0x1000f32f  stosd
0x1000f330  stosd
0x1000f331  stosd
0x1000f332  xor     eax, eax
0x1000f334  lea     edi, [esp+1470h+var_1424]
0x1000f338  stosd
0x1000f339  stosd
0x1000f33a  stosd
0x1000f33b  test    esi, esi
0x1000f33d  jz      short loc_1000F34F
0x1000f33f  mov     ecx, esi; this
0x1000f341  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f347  call    esi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x1000f349  mov     [esp+1470h+var_140C], eax
0x1000f34d  jmp     short loc_1000F353
0x1000f34f  mov     [esp+1470h+var_140C], ebx
0x1000f353  mov     esi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000f359  test    esi, esi
0x1000f35b  jz      short loc_1000F36C
0x1000f35d  lea     eax, [esp+1470h+var_1458]
0x1000f361  mov     ecx, esi; this
0x1000f363  push    eax
0x1000f364  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f36a  call    esi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x1000f36c  mov     esi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000f372  test    esi, esi
0x1000f374  jz      short loc_1000F38F
0x1000f376  push    400h
0x1000f37b  lea     eax, [esp+1474h+var_1400]
0x1000f37f  mov     ecx, esi; this
0x1000f381  push    eax
0x1000f382  lea     eax, [esp+1478h+var_1458]
0x1000f386  push    eax
0x1000f387  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f38d  call    esi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x1000f38f  mov     esi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000f395  test    esi, esi
0x1000f397  jz      short loc_1000F3A8
0x1000f399  lea     eax, [esp+1470h+var_1458]
0x1000f39d  mov     ecx, esi; this
0x1000f39f  push    eax
0x1000f3a0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f3a6  call    esi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000f3a8  mov     esi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000f3ae  test    esi, esi
0x1000f3b0  jz      short loc_1000F3C8
0x1000f3b2  test    byte ptr [esp+1470h+var_1454], 2
0x1000f3b7  jnz     short loc_1000F3C8
0x1000f3b9  lea     eax, [esp+1470h+var_1458]
0x1000f3bd  mov     ecx, esi; this
0x1000f3bf  push    eax
0x1000f3c0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f3c6  call    esi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x1000f3c8  cmp     [esp+1470h+var_1450], ebx
0x1000f3cc  jl      short loc_1000F3E0
0x1000f3ce  mov     ecx, 8000FFFFh
0x1000f3d3  mov     [esp+1470h+var_1450], ecx
0x1000f3d7  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x1000f3dc  mov     [esp+1470h+var_144C], eax
0x1000f3e0  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x1000f3e6  jnz     short loc_1000F411
0x1000f3e8  mov     esi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000f3ee  test    esi, esi
0x1000f3f0  jz      short loc_1000F401
0x1000f3f2  mov     ecx, esi; this
0x1000f3f4  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f3fa  call    esi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x1000f3fc  movzx   eax, al
0x1000f3ff  jmp     short loc_1000F40D
0x1000f401  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x1000f407  neg     eax
0x1000f409  sbb     eax, eax
0x1000f40b  neg     eax
0x1000f40d  test    eax, eax
0x1000f40f  jz      short loc_1000F418
0x1000f411  test    byte ptr [esp+1470h+var_1454], 2
0x1000f416  jz      short loc_1000F43D
0x1000f418  mov     esi, _g_pfnResultLoggingCallback
0x1000f41e  test    esi, esi
0x1000f420  jz      short loc_1000F497
0x1000f422  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x1000f428  jnz     short loc_1000F497
0x1000f42a  push    ebx
0x1000f42b  push    ebx
0x1000f42c  lea     eax, [esp+1478h+var_1458]
0x1000f430  mov     ecx, esi; this
0x1000f432  push    eax
0x1000f433  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f439  call    esi ; _g_pfnResultLoggingCallback
0x1000f43b  jmp     short loc_1000F497
0x1000f43d  mov     esi, _g_pfnResultLoggingCallback
0x1000f443  mov     edi, 800h
0x1000f448  test    esi, esi
0x1000f44a  jz      short loc_1000F46C
0x1000f44c  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x1000f452  jnz     short loc_1000F46C
0x1000f454  push    edi
0x1000f455  lea     eax, [esp+1474h+OutputString]
0x1000f45c  mov     ecx, esi; this
0x1000f45e  push    eax
0x1000f45f  lea     eax, [esp+1478h+var_1458]
0x1000f463  push    eax
0x1000f464  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f46a  call    esi ; _g_pfnResultLoggingCallback
0x1000f46c  cmp     [esp+1470h+OutputString], bx
0x1000f474  jnz     short loc_1000F489
0x1000f476  lea     eax, [esp+1470h+var_1458]
0x1000f47a  mov     edx, edi
0x1000f47c  push    eax; this
0x1000f47d  lea     ecx, [esp+1474h+OutputString]
0x1000f484  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x1000f489  lea     eax, [esp+1470h+OutputString]
0x1000f490  push    eax; lpOutputString
0x1000f491  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x1000f497  test    byte ptr [esp+1470h+var_1454], 4
0x1000f49c  jnz     short loc_1000F4A6
0x1000f49e  cmp     ?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x1000f4a4  jz      short loc_1000F4BA
0x1000f4a6  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000f4ac  test    esi, esi
0x1000f4ae  jz      short loc_1000F4BA
0x1000f4b0  mov     ecx, esi; this
0x1000f4b2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f4b8  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x1000f4ba  lea     ecx, [esp+1470h+var_1458]
0x1000f4be  call    ?WilFailFast@details@wil@@YGXABUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
