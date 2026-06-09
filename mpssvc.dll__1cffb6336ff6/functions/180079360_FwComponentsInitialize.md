# FwComponentsInitialize

- ea: `0x180079360`
- end: `0x180079573`
- name: `FwComponentsInitialize`
- size: `531`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180074d20`
- `0x180076c20`

## callees

- `0x180001880`
- `0x1800093b0`
- `0x18000af3c`
- `0x180017110`
- `0x18005cf9c`
- `0x180079360`
- `0x18007957c`
- `0x1800e6010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800793dd`
- `ntdll!EtwEventWrite` at `0x1800794f1`
- `ntdll!EtwEventWrite` at `0x1800793dd`
- `ntdll!EtwEventWrite` at `0x1800794f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007944e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007944e`
- `fwbase!FwReportReturnError` at `0x180079517`
- `fwbase!FwReportReturnError` at `0x18007955e`
- `fwbase!FwReportReturnError` at `0x180079517`
- `fwbase!FwReportReturnError` at `0x18007955e`

## string_xrefs

- `0x180079510`: `FwComponentsInitialize`
- `0x180079557`: `FwComponentsInitialize`

## pseudocode

```c
__int64 __fastcall FwComponentsInitialize(unsigned int a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // ebx
  __int64 v7; // rcx
  unsigned int v8; // edi
  __int64 v9; // rcx
  DWORD CurrentProcessId; // eax
  __int64 v11; // r8
  __int64 v13[7]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v14; // [rsp+80h] [rbp+8h] BYREF
  __int64 v15; // [rsp+88h] [rbp+10h] BYREF
  __int64 v16; // [rsp+90h] [rbp+18h] BYREF
  __int64 v17; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_382d0cf40c9a3ae0ed10c2ab9c5de819_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, a2, a3, a4);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = 0;
  if ( a1 )
  {
    v9 = g_Provider;
    while ( 1 )
    {
      if ( v9 )
        EtwEventWrite(v9, *(_QWORD *)(56LL * v8 + a2 + 16), 0, 0);
      v6 = (*(__int64 (**)(void))(56LL * v8 + a2))();
      if ( v6 < 0 && !bDidComponentInitFailTelemeter && dword_180126458 )
      {
        if ( (unsigned int)dword_180126458 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180126458, 0x800000000000LL) )
        {
          v16 = 0x1000000;
          CurrentProcessId = GetCurrentProcessId();
          LODWORD(v15) = v6;
          LODWORD(v14) = CurrentProcessId;
          v13[0] = 1;
          v17 = *(_QWORD *)(56LL * v8 + a2 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (int)&dword_180126458,
            (int)&byte_18010E8DF,
            v11,
            (__int64)v13,
            (const char **)&v17,
            (__int64)&v15,
            (__int64)&v14,
            (__int64)&v16);
        }
        bDidComponentInitFailTelemeter = 1;
      }
      v9 = g_Provider;
      if ( g_Provider )
      {
        EtwEventWrite(g_Provider, *(_QWORD *)(56LL * v8 + a2 + 24), 0, 0);
        v9 = g_Provider;
      }
      if ( v6 < 0 )
        break;
      if ( ++v8 >= a1 )
        goto LABEL_23;
    }
    FwReportReturnError("FwComponentsInitialize", (unsigned int)v6, a3);
    FwComponentsShutdown(v8, a2);
LABEL_23:
    v7 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(v7 + 16), 15, WPP_382d0cf40c9a3ae0ed10c2ab9c5de819_Traceguids, (unsigned int)v6);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwComponentsInitialize", (unsigned int)v6, a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180079360  push    rbx
0x180079362  push    rbp
0x180079363  push    rsi
0x180079364  push    rdi
0x180079365  push    r15
0x180079367  sub     rsp, 50h
0x18007936b  mov     rsi, rdx
0x18007936e  mov     ebp, ecx
0x180079370  xor     ebx, ebx
0x180079372  mov     rcx, cs:WPP_GLOBAL_Control
0x180079379  lea     r15, WPP_GLOBAL_Control
0x180079380  cmp     rcx, r15
0x180079383  jz      short loc_1800793A5
0x180079385  test    byte ptr [rcx+1Ch], 8
0x180079389  jz      short loc_1800793A5
0x18007938b  mov     rcx, [rcx+10h]
0x18007938f  lea     edx, [rbx+0Eh]
0x180079392  lea     r8, WPP_382d0cf40c9a3ae0ed10c2ab9c5de819_Traceguids
0x180079399  call    WPP_SF_
0x18007939e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800793a5  test    rsi, rsi
0x1800793a8  jnz     short loc_1800793B6
0x1800793aa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800793af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800793b6  xor     edi, edi
0x1800793b8  test    ebp, ebp
0x1800793ba  jz      loc_18007952E
0x1800793c0  mov     rcx, cs:g_Provider
0x1800793c7  mov     ebx, edi
0x1800793c9  test    rcx, rcx
0x1800793cc  jz      short loc_1800793E3
0x1800793ce  imul    rdx, rbx, 38h ; '8'
0x1800793d2  xor     r9d, r9d
0x1800793d5  xor     r8d, r8d
0x1800793d8  mov     rdx, [rdx+rsi+10h]
0x1800793dd  call    cs:__imp_EtwEventWrite
0x1800793e3  imul    rax, rbx, 38h ; '8'
0x1800793e7  mov     rax, [rax+rsi]
0x1800793eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800793f0  mov     ebx, eax
0x1800793f2  test    eax, eax
0x1800793f4  jns     loc_1800794D4
0x1800793fa  cmp     cs:bDidComponentInitFailTelemeter, 0
0x180079401  jnz     loc_1800794D4
0x180079407  mov     ecx, cs:dword_180126458
0x18007940d  test    ecx, ecx
0x18007940f  jz      loc_1800794D4
0x180079415  mov     ecx, cs:dword_180126458
0x18007941b  cmp     ecx, 5
0x18007941e  jbe     loc_1800794CA
0x180079424  mov     rdx, 800000000000h
0x18007942e  lea     rcx, dword_180126458
0x180079435  call    _tlgKeywordOn
0x18007943a  test    al, al
0x18007943c  jz      loc_1800794CA
0x180079442  mov     [rsp+78h+arg_10], 1000000h
0x18007944e  call    cs:__imp_GetCurrentProcessId
0x180079454  lea     r9, [rsp+78h+var_38]
0x180079459  mov     dword ptr [rsp+78h+arg_8], ebx
0x180079460  mov     dword ptr [rsp+78h+arg_0], eax
0x180079467  lea     rcx, dword_180126458; int
0x18007946e  mov     eax, edi
0x180079470  imul    rdx, rax, 38h ; '8'
0x180079474  mov     [rsp+78h+var_38], 1
0x18007947d  mov     rax, [rdx+rsi+30h]
0x180079482  lea     rdx, byte_18010E8DF
0x180079489  mov     [rsp+78h+arg_18], rax
0x180079491  lea     rax, [rsp+78h+arg_10]
0x180079499  mov     [rsp+78h+var_40], rax; __int64
0x18007949e  lea     rax, [rsp+78h+arg_0]
0x1800794a6  mov     [rsp+78h+var_48], rax; __int64
0x1800794ab  lea     rax, [rsp+78h+arg_8]
0x1800794b3  mov     [rsp+78h+var_50], rax; __int64
0x1800794b8  lea     rax, [rsp+78h+arg_18]
0x1800794c0  mov     [rsp+78h+var_58], rax; __int64
0x1800794c5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@42@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800794ca  mov     cs:bDidComponentInitFailTelemeter, 1
0x1800794d4  mov     rcx, cs:g_Provider
0x1800794db  test    rcx, rcx
0x1800794de  jz      short loc_1800794FE
0x1800794e0  mov     eax, edi
0x1800794e2  xor     r9d, r9d
0x1800794e5  imul    rdx, rax, 38h ; '8'
0x1800794e9  xor     r8d, r8d
0x1800794ec  mov     rdx, [rdx+rsi+18h]
0x1800794f1  call    cs:__imp_EtwEventWrite
0x1800794f7  mov     rcx, cs:g_Provider
0x1800794fe  test    ebx, ebx
0x180079500  js      short loc_18007950E
0x180079502  inc     edi
0x180079504  cmp     edi, ebp
0x180079506  jb      loc_1800793C7
0x18007950c  jmp     short loc_180079527
0x18007950e  mov     edx, ebx
0x180079510  lea     rcx, aFwcomponentsin; "FwComponentsInitialize"
0x180079517  call    cs:__imp_FwReportReturnError
0x18007951d  mov     rdx, rsi
0x180079520  mov     ecx, edi
0x180079522  call    FwComponentsShutdown
0x180079527  mov     rcx, cs:WPP_GLOBAL_Control
0x18007952e  cmp     rcx, r15
0x180079531  jz      short loc_180079551
0x180079533  test    byte ptr [rcx+1Ch], 8
0x180079537  jz      short loc_180079551
0x180079539  mov     rcx, [rcx+10h]
0x18007953d  lea     r8, WPP_382d0cf40c9a3ae0ed10c2ab9c5de819_Traceguids
0x180079544  mov     edx, 0Fh
0x180079549  mov     r9d, ebx
0x18007954c  call    WPP_SF_d
0x180079551  test    ebx, ebx
0x180079553  jns     short loc_180079566
0x180079555  mov     edx, ebx
0x180079557  lea     rcx, aFwcomponentsin; "FwComponentsInitialize"
0x18007955e  call    cs:__imp_FwReportReturnError
0x180079564  mov     ebx, eax
0x180079566  mov     eax, ebx
0x180079568  add     rsp, 50h
0x18007956c  pop     r15
0x18007956e  pop     rdi
0x18007956f  pop     rsi
0x180079570  pop     rbp
0x180079571  pop     rbx
0x180079572  retn
```
