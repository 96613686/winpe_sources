# FwComponentsInitialize

- ea: `0x18007cfa0`
- end: `0x18007d1d2`
- name: `FwComponentsInitialize`
- size: `562`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800782c0`
- `0x18007a360`

## callees

- `0x1800019b8`
- `0x1800089bc`
- `0x18000a710`
- `0x1800192e0`
- `0x180061c90`
- `0x18007cfa0`
- `0x18007d1d8`
- `0x1800ec010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18007d01d`
- `ntdll!EtwEventWrite` at `0x18007d13d`
- `ntdll!EtwEventWrite` at `0x18007d01d`
- `ntdll!EtwEventWrite` at `0x18007d13d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007d094`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007d094`
- `fwbase!FwReportReturnError` at `0x18007d169`
- `fwbase!FwReportReturnError` at `0x18007d1b6`
- `fwbase!FwReportReturnError` at `0x18007d169`
- `fwbase!FwReportReturnError` at `0x18007d1b6`

## string_xrefs

- `0x18007d162`: `FwComponentsInitialize`
- `0x18007d1af`: `FwComponentsInitialize`

## pseudocode

```c
__int64 __fastcall FwComponentsInitialize(unsigned int a1, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rcx
  unsigned int v6; // edi
  __int64 v7; // rcx
  DWORD CurrentProcessId; // eax
  __int64 v10; // [rsp+80h] [rbp+8h] BYREF
  __int64 v11; // [rsp+88h] [rbp+10h] BYREF
  __int64 v12; // [rsp+90h] [rbp+18h] BYREF
  __int64 v13; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_382d0cf40c9a3ae0ed10c2ab9c5de819_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = 0;
  if ( a1 )
  {
    v7 = g_Provider;
    while ( 1 )
    {
      if ( v7 )
        EtwEventWrite(v7, *(_QWORD *)(56LL * v6 + a2 + 16), 0, 0);
      v4 = (*(__int64 (**)(void))(56LL * v6 + a2))();
      if ( v4 < 0 && !bDidComponentInitFailTelemeter && dword_18012C458 )
      {
        if ( (unsigned int)dword_18012C458 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012C458, 0x800000000000LL) )
        {
          v12 = 0x1000000;
          CurrentProcessId = GetCurrentProcessId();
          LODWORD(v11) = v4;
          LODWORD(v10) = CurrentProcessId;
          v13 = *(_QWORD *)(56LL * v6 + a2 + 48);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (int)&dword_18012C458,
            (__int64)&v13,
            (__int64)&v11,
            (__int64)&v10,
            (__int64)&v12);
        }
        bDidComponentInitFailTelemeter = 1;
      }
      v7 = g_Provider;
      if ( g_Provider )
      {
        EtwEventWrite(g_Provider, *(_QWORD *)(56LL * v6 + a2 + 24), 0, 0);
        v7 = g_Provider;
      }
      if ( v4 < 0 )
        break;
      if ( ++v6 >= a1 )
        goto LABEL_23;
    }
    FwReportReturnError("FwComponentsInitialize", (unsigned int)v4);
    FwComponentsShutdown(v6, a2);
LABEL_23:
    v5 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v5 != &WPP_GLOBAL_Control && (*(_BYTE *)(v5 + 28) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(v5 + 16), 15, WPP_382d0cf40c9a3ae0ed10c2ab9c5de819_Traceguids, (unsigned int)v4);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwComponentsInitialize", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007cfa0  push    rbx
0x18007cfa2  push    rbp
0x18007cfa3  push    rsi
0x18007cfa4  push    rdi
0x18007cfa5  push    r15
0x18007cfa7  sub     rsp, 50h
0x18007cfab  mov     rsi, rdx
0x18007cfae  mov     ebp, ecx
0x18007cfb0  xor     ebx, ebx
0x18007cfb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cfb9  lea     r15, WPP_GLOBAL_Control
0x18007cfc0  cmp     rcx, r15
0x18007cfc3  jz      short loc_18007CFE5
0x18007cfc5  test    byte ptr [rcx+1Ch], 8
0x18007cfc9  jz      short loc_18007CFE5
0x18007cfcb  mov     rcx, [rcx+10h]
0x18007cfcf  lea     edx, [rbx+0Eh]
0x18007cfd2  lea     r8, WPP_382d0cf40c9a3ae0ed10c2ab9c5de819_Traceguids
0x18007cfd9  call    WPP_SF_
0x18007cfde  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cfe5  test    rsi, rsi
0x18007cfe8  jnz     short loc_18007CFF6
0x18007cfea  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(components != NULL) || (numComponents == 0)")
0x18007cfef  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cff6  xor     edi, edi
0x18007cff8  test    ebp, ebp
0x18007cffa  jz      loc_18007D186
0x18007d000  mov     rcx, cs:g_Provider
0x18007d007  mov     ebx, edi
0x18007d009  test    rcx, rcx
0x18007d00c  jz      short loc_18007D029
0x18007d00e  imul    rdx, rbx, 38h ; '8'
0x18007d012  xor     r9d, r9d
0x18007d015  xor     r8d, r8d
0x18007d018  mov     rdx, [rdx+rsi+10h]
0x18007d01d  call    cs:__imp_EtwEventWrite
0x18007d024  nop     dword ptr [rax+rax+00h]
0x18007d029  imul    rax, rbx, 38h ; '8'
0x18007d02d  mov     rax, [rax+rsi]
0x18007d031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d036  mov     ebx, eax
0x18007d038  test    eax, eax
0x18007d03a  jns     loc_18007D120
0x18007d040  cmp     cs:bDidComponentInitFailTelemeter, 0
0x18007d047  jnz     loc_18007D120
0x18007d04d  mov     ecx, cs:dword_18012C458
0x18007d053  test    ecx, ecx
0x18007d055  jz      loc_18007D120
0x18007d05b  mov     ecx, cs:dword_18012C458
0x18007d061  cmp     ecx, 5
0x18007d064  jbe     loc_18007D116
0x18007d06a  mov     rdx, 800000000000h
0x18007d074  lea     rcx, dword_18012C458
0x18007d07b  call    _tlgKeywordOn
0x18007d080  test    al, al
0x18007d082  jz      loc_18007D116
0x18007d088  mov     [rsp+78h+arg_10], 1000000h
0x18007d094  call    cs:__imp_GetCurrentProcessId
0x18007d09b  nop     dword ptr [rax+rax+00h]
0x18007d0a0  lea     r9, [rsp+78h+var_38]
0x18007d0a5  mov     dword ptr [rsp+78h+arg_8], ebx
0x18007d0ac  mov     dword ptr [rsp+78h+arg_0], eax
0x18007d0b3  lea     rcx, dword_18012C458; int
0x18007d0ba  mov     eax, edi
0x18007d0bc  imul    rdx, rax, 38h ; '8'
0x18007d0c0  mov     [rsp+78h+var_38], 1
0x18007d0c9  mov     rax, [rdx+rsi+30h]
0x18007d0ce  lea     rdx, word_18011477A
0x18007d0d5  mov     [rsp+78h+arg_18], rax
0x18007d0dd  lea     rax, [rsp+78h+arg_10]
0x18007d0e5  mov     [rsp+78h+var_40], rax; __int64
0x18007d0ea  lea     rax, [rsp+78h+arg_0]
0x18007d0f2  mov     [rsp+78h+var_48], rax; __int64
0x18007d0f7  lea     rax, [rsp+78h+arg_8]
0x18007d0ff  mov     [rsp+78h+var_50], rax; __int64
0x18007d104  lea     rax, [rsp+78h+arg_18]
0x18007d10c  mov     [rsp+78h+var_58], rax; __int64
0x18007d111  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@42@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18007d116  mov     cs:bDidComponentInitFailTelemeter, 1
0x18007d120  mov     rcx, cs:g_Provider
0x18007d127  test    rcx, rcx
0x18007d12a  jz      short loc_18007D150
0x18007d12c  mov     eax, edi
0x18007d12e  xor     r9d, r9d
0x18007d131  imul    rdx, rax, 38h ; '8'
0x18007d135  xor     r8d, r8d
0x18007d138  mov     rdx, [rdx+rsi+18h]
0x18007d13d  call    cs:__imp_EtwEventWrite
0x18007d144  nop     dword ptr [rax+rax+00h]
0x18007d149  mov     rcx, cs:g_Provider
0x18007d150  test    ebx, ebx
0x18007d152  js      short loc_18007D160
0x18007d154  inc     edi
0x18007d156  cmp     edi, ebp
0x18007d158  jb      loc_18007D007
0x18007d15e  jmp     short loc_18007D17F
0x18007d160  mov     edx, ebx
0x18007d162  lea     rcx, aFwcomponentsin; "FwComponentsInitialize"
0x18007d169  call    cs:__imp_FwReportReturnError
0x18007d170  nop     dword ptr [rax+rax+00h]
0x18007d175  mov     rdx, rsi
0x18007d178  mov     ecx, edi
0x18007d17a  call    FwComponentsShutdown
0x18007d17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d186  cmp     rcx, r15
0x18007d189  jz      short loc_18007D1A9
0x18007d18b  test    byte ptr [rcx+1Ch], 8
0x18007d18f  jz      short loc_18007D1A9
0x18007d191  mov     rcx, [rcx+10h]
0x18007d195  lea     r8, WPP_382d0cf40c9a3ae0ed10c2ab9c5de819_Traceguids
0x18007d19c  mov     edx, 0Fh
0x18007d1a1  mov     r9d, ebx
0x18007d1a4  call    WPP_SF_d
0x18007d1a9  test    ebx, ebx
0x18007d1ab  jns     short loc_18007D1C4
0x18007d1ad  mov     edx, ebx
0x18007d1af  lea     rcx, aFwcomponentsin; "FwComponentsInitialize"
0x18007d1b6  call    cs:__imp_FwReportReturnError
0x18007d1bd  nop     dword ptr [rax+rax+00h]
0x18007d1c2  mov     ebx, eax
0x18007d1c4  mov     eax, ebx
0x18007d1c6  add     rsp, 50h
0x18007d1ca  pop     r15
0x18007d1cc  pop     rdi
0x18007d1cd  pop     rsi
0x18007d1ce  pop     rbp
0x18007d1cf  pop     rbx
0x18007d1d0  retn
```
