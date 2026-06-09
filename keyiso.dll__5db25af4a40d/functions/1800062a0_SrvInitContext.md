# SrvInitContext

- ea: `0x1800062a0`
- end: `0x1800064a6`
- name: `SrvInitContext`
- size: `518`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a268`

## callees

- `0x180004470`
- `0x1800062a0`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180006374`
- `ntdll!RtlDeleteCriticalSection` at `0x18000637d`
- `ntdll!RtlDeleteCriticalSection` at `0x1800063a7`
- `ntdll!RtlDeleteCriticalSection` at `0x1800063b0`
- `ntdll!RtlDeleteCriticalSection` at `0x180006374`
- `ntdll!RtlDeleteCriticalSection` at `0x18000637d`
- `ntdll!RtlDeleteCriticalSection` at `0x1800063a7`
- `ntdll!RtlDeleteCriticalSection` at `0x1800063b0`
- `ntdll!RtlInitializeCriticalSection` at `0x1800062ef`
- `ntdll!RtlInitializeCriticalSection` at `0x180006306`
- `ntdll!RtlInitializeCriticalSection` at `0x180006320`
- `ntdll!RtlInitializeCriticalSection` at `0x180006333`
- `ntdll!RtlInitializeCriticalSection` at `0x1800062ef`
- `ntdll!RtlInitializeCriticalSection` at `0x180006306`
- `ntdll!RtlInitializeCriticalSection` at `0x180006320`
- `ntdll!RtlInitializeCriticalSection` at `0x180006333`

## string_xrefs

- `0x1800063bf`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`
- `0x180006402`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`
- `0x18000642f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`
- `0x18000647d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvInitContext(__int64 a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  NTSTATUS v5; // edi
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rcx

  *(_QWORD *)(a2 + 88) = a2 + 80;
  v3 = (struct _RTL_CRITICAL_SECTION *)(a2 + 40);
  *(_QWORD *)(a2 + 80) = a2 + 80;
  *(_QWORD *)(a2 + 152) = a2 + 144;
  *(_QWORD *)(a2 + 144) = a2 + 144;
  *(_QWORD *)(a2 + 216) = a2 + 208;
  *(_QWORD *)(a2 + 208) = a2 + 208;
  *(_QWORD *)(a2 + 280) = a2 + 272;
  *(_QWORD *)(a2 + 272) = a2 + 272;
  v5 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 40));
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v6,
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
        194);
    return (unsigned int)v5;
  }
  v5 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 104));
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v7,
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
        201);
  }
  else
  {
    v5 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 168));
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)WPP_GLOBAL_Control,
          v8,
          (unsigned int)"Status",
          v5,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
          209);
      RtlDeleteCriticalSection(v3);
      v11 = (struct _RTL_CRITICAL_SECTION *)(a2 + 104);
      goto LABEL_10;
    }
    v5 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 232));
    if ( v5 >= 0 )
    {
      *(_DWORD *)a2 = 1717986913;
      result = 0;
      *(_QWORD *)(a2 + 8) = a1;
      return result;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v9,
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
        218);
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 104));
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 168));
  }
  v11 = v3;
LABEL_10:
  RtlDeleteCriticalSection(v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800062a0  push    rbx
0x1800062a2  push    rbp
0x1800062a3  push    rsi
0x1800062a4  push    rdi
0x1800062a5  push    r14
0x1800062a7  push    r15
0x1800062a9  sub     rsp, 48h
0x1800062ad  lea     rax, [rdx+50h]
0x1800062b1  mov     r15, rcx
0x1800062b4  mov     [rax+8], rax
0x1800062b8  lea     rsi, [rdx+28h]
0x1800062bc  mov     [rax], rax
0x1800062bf  mov     rcx, rsi; CriticalSection
0x1800062c2  lea     rax, [rdx+90h]
0x1800062c9  mov     rbx, rdx
0x1800062cc  mov     [rax+8], rax
0x1800062d0  mov     [rax], rax
0x1800062d3  lea     rax, [rdx+0D0h]
0x1800062da  mov     [rax+8], rax
0x1800062de  mov     [rax], rax
0x1800062e1  lea     rax, [rdx+110h]
0x1800062e8  mov     [rax+8], rax
0x1800062ec  mov     [rax], rax
0x1800062ef  call    cs:__imp_RtlInitializeCriticalSection
0x1800062f5  mov     edi, eax
0x1800062f7  test    eax, eax
0x1800062f9  js      loc_1800063E5
0x1800062ff  lea     rbp, [rbx+68h]
0x180006303  mov     rcx, rbp; CriticalSection
0x180006306  call    cs:__imp_RtlInitializeCriticalSection
0x18000630c  mov     edi, eax
0x18000630e  test    eax, eax
0x180006310  js      loc_180006458
0x180006316  lea     r14, [rbx+0A8h]
0x18000631d  mov     rcx, r14; CriticalSection
0x180006320  call    cs:__imp_RtlInitializeCriticalSection
0x180006326  mov     edi, eax
0x180006328  test    eax, eax
0x18000632a  js      short loc_180006358
0x18000632c  lea     rcx, [rbx+0E8h]; CriticalSection
0x180006333  call    cs:__imp_RtlInitializeCriticalSection
0x180006339  mov     edi, eax
0x18000633b  test    eax, eax
0x18000633d  js      short loc_180006387
0x18000633f  mov     dword ptr [rbx], 66666661h
0x180006345  xor     eax, eax
0x180006347  mov     [rbx+8], r15
0x18000634b  add     rsp, 48h
0x18000634f  pop     r15
0x180006351  pop     r14
0x180006353  pop     rdi
0x180006354  pop     rsi
0x180006355  pop     rbp
0x180006356  pop     rbx
0x180006357  retn
0x180006358  mov     rdx, cs:WPP_GLOBAL_Control
0x18000635f  lea     rcx, WPP_GLOBAL_Control
0x180006366  cmp     rdx, rcx
0x180006369  jz      short loc_180006371
0x18000636b  test    byte ptr [rdx+1Ch], 1
0x18000636f  jnz     short loc_1800063BB
0x180006371  mov     rcx, rsi; CriticalSection
0x180006374  call    cs:__imp_RtlDeleteCriticalSection
0x18000637a  mov     rcx, rbp; CriticalSection
0x18000637d  call    cs:__imp_RtlDeleteCriticalSection
0x180006383  mov     eax, edi
0x180006385  jmp     short loc_18000634B
0x180006387  mov     rdx, cs:WPP_GLOBAL_Control
0x18000638e  lea     rcx, WPP_GLOBAL_Control
0x180006395  cmp     rdx, rcx
0x180006398  jz      short loc_1800063A4
0x18000639a  test    byte ptr [rdx+1Ch], 1
0x18000639e  jnz     loc_18000642B
0x1800063a4  mov     rcx, rbp; CriticalSection
0x1800063a7  call    cs:__imp_RtlDeleteCriticalSection
0x1800063ad  mov     rcx, r14; CriticalSection
0x1800063b0  call    cs:__imp_RtlDeleteCriticalSection
0x1800063b6  mov     rcx, rsi
0x1800063b9  jmp     short loc_18000637D
0x1800063bb  mov     rcx, [rdx+10h]
0x1800063bf  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800063c6  mov     [rsp+78h+var_48], 3D1h
0x1800063ce  lea     r9, aStatus; "Status"
0x1800063d5  mov     [rsp+78h+var_50], rax
0x1800063da  mov     [rsp+78h+var_58], edi
0x1800063de  call    WPP_SF_sDsd
0x1800063e3  jmp     short loc_180006371
0x1800063e5  mov     rdx, cs:WPP_GLOBAL_Control
0x1800063ec  lea     rcx, WPP_GLOBAL_Control
0x1800063f3  cmp     rdx, rcx
0x1800063f6  jz      short loc_180006383
0x1800063f8  test    byte ptr [rdx+1Ch], 1
0x1800063fc  jz      short loc_180006383
0x1800063fe  mov     rcx, [rdx+10h]
0x180006402  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006409  mov     [rsp+78h+var_48], 3C2h
0x180006411  lea     r9, aStatus; "Status"
0x180006418  mov     [rsp+78h+var_50], rax
0x18000641d  mov     [rsp+78h+var_58], edi
0x180006421  call    WPP_SF_sDsd
0x180006426  jmp     loc_180006383
0x18000642b  mov     rcx, [rdx+10h]
0x18000642f  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006436  mov     [rsp+78h+var_48], 3DAh
0x18000643e  lea     r9, aStatus; "Status"
0x180006445  mov     [rsp+78h+var_50], rax
0x18000644a  mov     [rsp+78h+var_58], edi
0x18000644e  call    WPP_SF_sDsd
0x180006453  jmp     loc_1800063A4
0x180006458  mov     rdx, cs:WPP_GLOBAL_Control
0x18000645f  lea     rcx, WPP_GLOBAL_Control
0x180006466  cmp     rdx, rcx
0x180006469  jz      loc_1800063B6
0x18000646f  test    byte ptr [rdx+1Ch], 1
0x180006473  jz      loc_1800063B6
0x180006479  mov     rcx, [rdx+10h]
0x18000647d  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006484  mov     [rsp+78h+var_48], 3C9h
0x18000648c  lea     r9, aStatus; "Status"
0x180006493  mov     [rsp+78h+var_50], rax
0x180006498  mov     [rsp+78h+var_58], edi
0x18000649c  call    WPP_SF_sDsd
0x1800064a1  jmp     loc_1800063B6
```
