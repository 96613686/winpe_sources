# SrvCryptDecrypt

- ea: `0x1800035c0`
- end: `0x180003870`
- name: `SrvCryptDecrypt`
- size: `688`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x18000a520`
- `0x180019010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800035f1`
- `ntdll!RtlEnterCriticalSection` at `0x1800035f1`
- `ntdll!RtlLeaveCriticalSection` at `0x180003629`
- `ntdll!RtlLeaveCriticalSection` at `0x180003629`

## string_xrefs

- `0x180003724`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003781`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000380f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000384d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800037c6`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvCryptDecrypt(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  volatile signed __int64 *v12; // rbx
  int v13; // ebp
  _QWORD *v14; // rax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // eax
  unsigned int v18; // edi
  int v20; // eax
  unsigned int v21; // ebx

  if ( !a1 )
  {
    v18 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        165);
      return 2148073510LL;
    }
    return v18;
  }
  v12 = 0;
  v13 = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
  v14 = *(_QWORD **)(a1 + 144);
  while ( v14 != (_QWORD *)(a1 + 144) )
  {
    v12 = v14 - 2;
    v14 = (_QWORD *)*v14;
    if ( *((_QWORD *)v12 + 6) == a3 )
    {
      if ( *(_DWORD *)v12 == 1145324615 )
      {
        _InterlockedIncrement64(v12 + 1);
        v13 = 1;
      }
      break;
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
  if ( !v13 )
    v12 = 0;
  if ( v12 )
  {
    if ( a4 && a5 && (v15 = a9, a9) )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*((_QWORD *)v12 + 4) + 152LL))(
              *(_QWORD *)(*((_QWORD *)v12 + 4) + 296LL),
              *((_QWORD *)v12 + 5),
              a4);
      v18 = v17;
      if ( v17 )
      {
        DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 716);
        v18 = NormalizeNteStatus(v18);
      }
    }
    else
    {
      v18 = -2146893785;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          v16,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          183);
    }
    if ( _InterlockedExchangeAdd64(v12 + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    {
      v20 = SrvFreeKey((PVOID)v12);
      v21 = v20;
      if ( v20 < 0 )
      {
        DebugTraceError(
          (unsigned int)v20,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
          740);
        if ( (v18 & 0x80000000) == 0 )
          return v21;
      }
    }
    return v18;
  }
  v18 = -2146893786;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v18;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v15,
    v16,
    (unsigned int)"Status",
    38,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
    174);
  return 2148073510LL;
}

```

## disassembly

```asm
0x1800035c0  mov     rax, rsp
0x1800035c3  push    rsi
0x1800035c4  push    rdi
0x1800035c5  push    r15
0x1800035c7  sub     rsp, 50h
0x1800035cb  mov     r15, r9
0x1800035ce  mov     rdi, r8
0x1800035d1  mov     rsi, rcx
0x1800035d4  test    rcx, rcx
0x1800035d7  jz      loc_180003702
0x1800035dd  mov     [rax+10h], rbx
0x1800035e1  add     rcx, 68h ; 'h'; CriticalSection
0x1800035e5  mov     [rax+18h], rbp
0x1800035e9  xor     ebx, ebx
0x1800035eb  xor     ebp, ebp
0x1800035ed  mov     [rax+20h], r14
0x1800035f1  call    cs:__imp_RtlEnterCriticalSection
0x1800035f7  lea     rdx, [rsi+90h]
0x1800035fe  mov     rax, [rdx]
0x180003601  cmp     rax, rdx
0x180003604  jz      short loc_180003625
0x180003606  lea     rbx, [rax-10h]
0x18000360a  mov     rax, [rax]
0x18000360d  cmp     [rbx+30h], rdi
0x180003611  jnz     short loc_180003601
0x180003613  cmp     dword ptr [rbx], 44444447h
0x180003619  jnz     short loc_180003625
0x18000361b  lock inc qword ptr [rbx+8]
0x180003620  mov     ebp, 1
0x180003625  lea     rcx, [rsi+68h]; CriticalSection
0x180003629  call    cs:__imp_RtlLeaveCriticalSection
0x18000362f  mov     r14, [rsp+68h+arg_18]
0x180003637  xor     eax, eax
0x180003639  test    ebp, ebp
0x18000363b  mov     rbp, [rsp+68h+arg_10]
0x180003643  cmovz   rbx, rax
0x180003647  test    rbx, rbx
0x18000364a  jz      loc_1800037E5
0x180003650  test    r15, r15
0x180003653  jz      loc_180003757
0x180003659  mov     r9d, [rsp+68h+arg_20]
0x180003661  test    r9d, r9d
0x180003664  jz      loc_180003757
0x18000366a  mov     rdx, [rsp+68h+arg_40]
0x180003672  test    rdx, rdx
0x180003675  jz      loc_180003757
0x18000367b  mov     eax, [rsp+68h+arg_48]
0x180003682  mov     r8, r15
0x180003685  mov     rcx, [rbx+20h]
0x180003689  mov     [rsp+68h+var_28], eax
0x18000368d  mov     eax, [rsp+68h+arg_38]
0x180003694  mov     [rsp+68h+var_30], rdx
0x180003699  mov     r10, [rcx+98h]
0x1800036a0  mov     rdx, [rbx+28h]
0x1800036a4  mov     rcx, [rcx+128h]
0x1800036ab  mov     [rsp+68h+var_38], eax
0x1800036af  mov     rax, [rsp+68h+arg_30]
0x1800036b7  mov     [rsp+68h+var_40], rax
0x1800036bc  mov     rax, [rsp+68h+arg_28]
0x1800036c4  mov     [rsp+68h+var_48], rax
0x1800036c9  mov     rax, r10
0x1800036cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d1  mov     edi, eax
0x1800036d3  test    eax, eax
0x1800036d5  jnz     loc_180003847
0x1800036db  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800036e2  lock xadd [rbx+8], rax
0x1800036e8  cmp     rax, 1
0x1800036ec  jz      loc_1800037AE
0x1800036f2  mov     rbx, [rsp+68h+arg_8]
0x1800036f7  mov     eax, edi
0x1800036f9  add     rsp, 50h
0x1800036fd  pop     r15
0x1800036ff  pop     rdi
0x180003700  pop     rsi
0x180003701  retn
0x180003702  mov     edi, 80090026h
0x180003707  mov     rcx, cs:WPP_GLOBAL_Control
0x18000370e  lea     rax, WPP_GLOBAL_Control
0x180003715  cmp     rcx, rax
0x180003718  jz      short loc_1800036F7
0x18000371a  test    byte ptr [rcx+1Ch], 1
0x18000371e  jz      short loc_1800036F7
0x180003720  mov     rcx, [rcx+10h]
0x180003724  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000372b  mov     [rsp+68h+var_38], 2A5h
0x180003733  lea     r9, aStatus; "Status"
0x18000373a  mov     [rsp+68h+var_40], rax
0x18000373f  mov     dword ptr [rsp+68h+var_48], 80090026h
0x180003747  call    WPP_SF_sDsd
0x18000374c  mov     eax, edi
0x18000374e  add     rsp, 50h
0x180003752  pop     r15
0x180003754  pop     rdi
0x180003755  pop     rsi
0x180003756  retn
0x180003757  mov     edi, 80090027h
0x18000375c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003763  lea     rax, WPP_GLOBAL_Control
0x18000376a  cmp     rcx, rax
0x18000376d  jz      loc_1800036DB
0x180003773  test    byte ptr [rcx+1Ch], 1
0x180003777  jz      loc_1800036DB
0x18000377d  mov     rcx, [rcx+10h]
0x180003781  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003788  mov     [rsp+68h+var_38], 2B7h
0x180003790  lea     r9, aStatus; "Status"
0x180003797  mov     [rsp+68h+var_40], rax
0x18000379c  mov     dword ptr [rsp+68h+var_48], 80090027h
0x1800037a4  call    WPP_SF_sDsd
0x1800037a9  jmp     loc_1800036DB
0x1800037ae  mov     rcx, rbx; P
0x1800037b1  call    SrvFreeKey
0x1800037b6  mov     ebx, eax
0x1800037b8  test    eax, eax
0x1800037ba  jns     loc_1800036F2
0x1800037c0  mov     r9d, 2E4h
0x1800037c6  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800037cd  lea     rdx, aStatus; "Status"
0x1800037d4  mov     ecx, eax
0x1800037d6  call    DebugTraceError
0x1800037db  test    edi, edi
0x1800037dd  cmovns  edi, ebx
0x1800037e0  jmp     loc_1800036F2
0x1800037e5  mov     edi, 80090026h
0x1800037ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037f1  lea     rax, WPP_GLOBAL_Control
0x1800037f8  cmp     rcx, rax
0x1800037fb  jz      loc_1800036F2
0x180003801  test    byte ptr [rcx+1Ch], 1
0x180003805  jz      loc_1800036F2
0x18000380b  mov     rcx, [rcx+10h]
0x18000380f  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003816  mov     [rsp+68h+var_38], 2AEh
0x18000381e  lea     r9, aStatus; "Status"
0x180003825  mov     [rsp+68h+var_40], rax
0x18000382a  mov     dword ptr [rsp+68h+var_48], 80090026h
0x180003832  call    WPP_SF_sDsd
0x180003837  mov     rbx, [rsp+68h+arg_8]
0x18000383c  mov     eax, edi
0x18000383e  add     rsp, 50h
0x180003842  pop     r15
0x180003844  pop     rdi
0x180003845  pop     rsi
0x180003846  retn
0x180003847  mov     r9d, 2CCh
0x18000384d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003854  lea     rdx, aStatus; "Status"
0x18000385b  mov     ecx, edi
0x18000385d  call    DebugTraceError
0x180003862  mov     ecx, edi
0x180003864  call    NormalizeNteStatus
0x180003869  mov     edi, eax
0x18000386b  jmp     loc_1800036DB
```
