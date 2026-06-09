# PAL_System_Initialize(void)

- ea: `0x18001e40c`
- end: `0x18001e548`
- name: `?PAL_System_Initialize@@YAJXZ`
- size: `316`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002164c`

## callees

- `0x18000160c`
- `0x18001d114`
- `0x18001e40c`
- `0x18001e550`
- `0x18001ef44`
- `0x18002a278`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18001e427`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18001e427`

## string_xrefs

- `0x18001e4be`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_Initialize(_UNKNOWN **a1, __int64 a2, __int64 a3, __int64 a4)
{
  int inited; // ebx
  int CurrentThreadActivityIdPrefix; // eax
  int v7; // [rsp+28h] [rbp-40h]
  const char *v8; // [rsp+50h] [rbp-18h] BYREF
  int v9; // [rsp+70h] [rbp+8h] BYREF
  int v10; // [rsp+78h] [rbp+10h] BYREF
  const char *v11; // [rsp+80h] [rbp+18h] BYREF
  const char *v12; // [rsp+88h] [rbp+20h] BYREF

  if ( g_PAL_SYS_initState == 1 || (inited = -2147467259, g_PAL_SYS_initState == 3) )
  {
    g_PAL_SYS_threadContextIndex = TlsAlloc();
    inited = PAL_Init_Timer_Globals();
    if ( inited >= 0 )
    {
      g_PAL_SYS_initState = 2;
      g_PAL_SYS_dbgConfig = 0;
      inited = 0;
      dword_180044D58 = 0;
      return (unsigned int)inited;
    }
    a1 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = inited;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_fa7f44a4abfa34436a622488f906f8c4_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Failed to initialize timer globals",
        v7);
    }
  }
  if ( (unsigned int)dword_180044008 > 2 )
  {
    v9 = 91;
    v11 = "PAL_System_Initialize";
    v10 = -2147467259;
    v12 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
    v8 = "PAL_System_Initialize failed. Cleaning-up.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)a1,
      (__int64)&dword_18003EFCC,
      a3,
      a4,
      (const unsigned __int16 **)&v8,
      (__int64)&v10,
      (const unsigned __int16 **)&v12,
      (__int64)&v9,
      (const unsigned __int16 **)&v11);
  }
  PAL_System_Terminate();
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001e40c  push    rbx
0x18001e40e  sub     rsp, 60h
0x18001e412  mov     eax, cs:?g_PAL_SYS_initState@@3W4PAL_SYS_STATE@@A; PAL_SYS_STATE g_PAL_SYS_initState
0x18001e418  cmp     eax, 1
0x18001e41b  jz      short loc_18001E427
0x18001e41d  mov     ebx, 80004005h
0x18001e422  cmp     eax, 3
0x18001e425  jnz     short loc_18001E495
0x18001e427  call    cs:__imp_TlsAlloc
0x18001e42d  mov     cs:?g_PAL_SYS_threadContextIndex@@3KA, eax; ulong g_PAL_SYS_threadContextIndex
0x18001e433  call    ?PAL_Init_Timer_Globals@@YAJXZ; PAL_Init_Timer_Globals(void)
0x18001e438  mov     ebx, eax
0x18001e43a  test    eax, eax
0x18001e43c  jns     loc_18001E525
0x18001e442  mov     rax, cs:WPP_GLOBAL_Control
0x18001e449  lea     rcx, WPP_GLOBAL_Control
0x18001e450  cmp     rax, rcx
0x18001e453  jz      short loc_18001E495
0x18001e455  test    byte ptr [rax+1Ch], 8
0x18001e459  jz      short loc_18001E495
0x18001e45b  cmp     byte ptr [rax+19h], 2
0x18001e45f  jb      short loc_18001E495
0x18001e461  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e466  lea     rcx, aFailedToInitia_4; "Failed to initialize timer globals"
0x18001e46d  mov     dword ptr [rsp+68h+var_40], ebx
0x18001e471  mov     [rsp+68h+var_48], rcx
0x18001e476  lea     r8, WPP_fa7f44a4abfa34436a622488f906f8c4_Traceguids
0x18001e47d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e484  mov     edx, 0Ah
0x18001e489  mov     r9d, eax
0x18001e48c  mov     rcx, [rcx+10h]
0x18001e490  call    WPP_SF_DsD
0x18001e495  mov     eax, cs:dword_180044008
0x18001e49b  cmp     eax, 2
0x18001e49e  jbe     short loc_18001E51E
0x18001e4a0  lea     rax, aPalSystemIniti; "PAL_System_Initialize"
0x18001e4a7  mov     [rsp+68h+arg_0], 5Bh ; '['
0x18001e4af  mov     [rsp+68h+arg_10], rax
0x18001e4b7  lea     rdx, dword_18003EFCC
0x18001e4be  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001e4c5  mov     [rsp+68h+arg_8], 80004005h
0x18001e4cd  mov     [rsp+68h+arg_18], rax
0x18001e4d5  lea     rax, aPalSystemIniti_0; "PAL_System_Initialize failed. Cleaning-"...
0x18001e4dc  mov     [rsp+68h+var_18], rax
0x18001e4e1  lea     rax, [rsp+68h+arg_10]
0x18001e4e9  mov     [rsp+68h+var_28], rax
0x18001e4ee  lea     rax, [rsp+68h+arg_0]
0x18001e4f3  mov     [rsp+68h+var_30], rax
0x18001e4f8  lea     rax, [rsp+68h+arg_18]
0x18001e500  mov     [rsp+68h+var_38], rax
0x18001e505  lea     rax, [rsp+68h+arg_8]
0x18001e50a  mov     [rsp+68h+var_40], rax
0x18001e50f  lea     rax, [rsp+68h+var_18]
0x18001e514  mov     [rsp+68h+var_48], rax
0x18001e519  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001e51e  call    ?PAL_System_Terminate@@YAJXZ; PAL_System_Terminate(void)
0x18001e523  jmp     short loc_18001E540
0x18001e525  xor     eax, eax
0x18001e527  mov     cs:?g_PAL_SYS_initState@@3W4PAL_SYS_STATE@@A, 2; PAL_SYS_STATE g_PAL_SYS_initState
0x18001e531  mov     cs:?g_PAL_SYS_dbgConfig@@3UtagPAL_SYS_DBG_CONFIG@@A, rax; tagPAL_SYS_DBG_CONFIG g_PAL_SYS_dbgConfig
0x18001e538  xor     ebx, ebx
0x18001e53a  mov     cs:dword_180044D58, eax
0x18001e540  mov     eax, ebx
0x18001e542  add     rsp, 60h
0x18001e546  pop     rbx
0x18001e547  retn
```
