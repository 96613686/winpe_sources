# SrvCryptNotifyChangeKey

- ea: `0x18000ec30`
- end: `0x18000ef4e`
- name: `SrvCryptNotifyChangeKey`
- size: `798`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800025b0`
- `0x180003cf0`
- `0x1800048f0`
- `0x180005510`
- `0x180006280`
- `0x180009e34`
- `0x18000ec30`
- `0x18000f5a4`
- `0x18000f5e8`
- `0x180019010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000ecdc`
- `ntdll!RtlEnterCriticalSection` at `0x18000ee63`
- `ntdll!RtlEnterCriticalSection` at `0x18000ecdc`
- `ntdll!RtlEnterCriticalSection` at `0x18000ee63`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ed0a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ee91`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ed0a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ee91`

## string_xrefs

- `0x18000ec72`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000edab`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000ee07`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000eee3`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000ef0b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptNotifyChangeKey(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4)
{
  __int64 v7; // rdi
  __int64 v8; // r9
  int v9; // ebx
  __int64 v10; // rcx
  unsigned __int64 v11; // r15
  int v12; // ebx
  _QWORD *v13; // rax
  __int64 v14; // r8
  __int64 v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r8
  _QWORD *v21; // rbx
  __int64 v22; // r9
  _QWORD *v23; // rax
  __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // esi
  int v27; // eax
  int v28; // esi
  int v29; // eax
  _QWORD *v31; // [rsp+20h] [rbp-58h] BYREF
  __int64 v32; // [rsp+80h] [rbp+8h] BYREF

  v32 = 0;
  if ( !a1 )
  {
    v7 = 0;
    v8 = 2557;
LABEL_3:
    v9 = -2146893786;
    v10 = 2148073510LL;
LABEL_4:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v8);
    goto LABEL_35;
  }
  v7 = SrvLookupAndReferenceProvider(a1, a2, 0);
  if ( !v7 )
  {
    v8 = 2566;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v8 = 2573;
LABEL_9:
    v9 = -2146893785;
    v10 = 2148073511LL;
    goto LABEL_4;
  }
  if ( (a4 & 1) == 0 )
  {
    v31 = (_QWORD *)*a3;
    v11 = 0;
    v12 = 0;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v7 + 304));
    v13 = *(_QWORD **)(v7 + 344);
    while ( v13 != (_QWORD *)(v7 + 344) )
    {
      v11 = (unsigned __int64)v13;
      v13 = (_QWORD *)*v13;
      if ( *(_QWORD **)(v11 + 24) == v31 )
      {
        v12 = 1;
        break;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v7 + 304));
    v15 = v11 & -(__int64)(v12 != 0);
    if ( !v15 )
    {
      v8 = 2590;
      goto LABEL_9;
    }
    v32 = *(_QWORD *)(v15 + 16);
    if ( (a4 & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v14, *a3);
      SrvRemoveProviderNotifyEventFromList(v7, v15);
      *a3 = -1;
      MSCryptFree(v15);
    }
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(v7 + 224))(*(_QWORD *)(v7 + 296), &v32, a4);
  v17 = v16;
  if ( v16 )
  {
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 2643);
    v9 = NormalizeNteStatus(v17);
    goto LABEL_35;
  }
  if ( (a4 & 1) == 0 )
  {
LABEL_34:
    v32 = 0;
    v9 = 0;
    goto LABEL_35;
  }
  v18 = v32;
  v31 = 0;
  *a3 = -1;
  v19 = CreateProviderNotifyEventMapping(a1, v18, &v31);
  v9 = v19;
  if ( !v19 )
  {
    v21 = v31;
    v22 = v31[3];
    *a3 = v22;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v20, v22);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v7 + 304));
    v23 = (_QWORD *)(v7 + 344);
    v24 = *(_QWORD *)(v7 + 344);
    if ( *(_QWORD *)(v24 + 8) != v7 + 344 )
      __fastfail(3u);
    *v21 = v24;
    v21[1] = v23;
    *(_QWORD *)(v24 + 8) = v21;
    *v23 = v21;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v7 + 304));
    goto LABEL_34;
  }
  DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 2679);
  if ( v31 )
    MSCryptFree(v31);
LABEL_35:
  if ( (unsigned __int64)(v32 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v25 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(v7 + 224))(*(_QWORD *)(v7 + 296), &v32, 2);
    v26 = v25;
    if ( v25 < 0 )
    {
      DebugTraceError(
        (unsigned int)v25,
        "tmpStatus",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        2732);
      v27 = NormalizeNteStatus(v26);
      v28 = v27;
      if ( v27 < 0 )
        DebugTraceError(
          (unsigned int)v27,
          "tmpStatus",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          2737);
      if ( v9 >= 0 )
        v9 = v28;
    }
  }
  if ( v7 )
  {
    v29 = SrvDereferenceProvider(v7);
    if ( v29 < 0 && v9 >= 0 )
      return (unsigned int)v29;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ec30  mov     rax, rsp
0x18000ec33  push    rbx
0x18000ec34  push    rbp
0x18000ec35  push    rsi
0x18000ec36  push    rdi
0x18000ec37  push    r12
0x18000ec39  push    r13
0x18000ec3b  push    r14
0x18000ec3d  push    r15
0x18000ec3f  sub     rsp, 38h
0x18000ec43  mov     qword ptr [rax+8], 0
0x18000ec4b  mov     r12d, r9d
0x18000ec4e  mov     rsi, r8
0x18000ec51  mov     r14, rcx
0x18000ec54  test    rcx, rcx
0x18000ec57  jnz     short loc_18000EC83
0x18000ec59  xor     edi, edi
0x18000ec5b  mov     r9d, 9FDh
0x18000ec61  mov     ebx, 80090026h
0x18000ec66  mov     ecx, 80090026h
0x18000ec6b  lea     rdx, aStatus; "Status"
0x18000ec72  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ec79  call    DebugTraceError
0x18000ec7e  jmp     loc_18000EEA5
0x18000ec83  xor     r8d, r8d
0x18000ec86  call    SrvLookupAndReferenceProvider
0x18000ec8b  mov     rdi, rax
0x18000ec8e  test    rax, rax
0x18000ec91  jnz     short loc_18000EC9B
0x18000ec93  mov     r9d, 0A06h
0x18000ec99  jmp     short loc_18000EC61
0x18000ec9b  test    rsi, rsi
0x18000ec9e  jnz     short loc_18000ECB2
0x18000eca0  mov     r9d, 0A0Dh
0x18000eca6  mov     ebx, 80090027h
0x18000ecab  mov     ecx, 80090027h
0x18000ecb0  jmp     short loc_18000EC6B
0x18000ecb2  mov     ebp, r12d
0x18000ecb5  lea     r15, WPP_GLOBAL_Control
0x18000ecbc  and     ebp, 1
0x18000ecbf  jnz     loc_18000ED81
0x18000ecc5  mov     rax, [rsi]
0x18000ecc8  lea     r13, [rdi+130h]
0x18000eccf  mov     rcx, r13; CriticalSection
0x18000ecd2  mov     [rsp+78h+var_58], rax
0x18000ecd7  xor     r15d, r15d
0x18000ecda  xor     ebx, ebx
0x18000ecdc  call    cs:__imp_RtlEnterCriticalSection
0x18000ece2  mov     rcx, [rsp+78h+var_58]
0x18000ece7  lea     rdx, [rdi+158h]
0x18000ecee  mov     rax, [rdx]
0x18000ecf1  cmp     rax, rdx
0x18000ecf4  jz      short loc_18000ED07
0x18000ecf6  mov     r15, rax
0x18000ecf9  mov     rax, [rax]
0x18000ecfc  cmp     [r15+18h], rcx
0x18000ed00  jnz     short loc_18000ECF1
0x18000ed02  mov     ebx, 1
0x18000ed07  mov     rcx, r13; CriticalSection
0x18000ed0a  call    cs:__imp_RtlLeaveCriticalSection
0x18000ed10  neg     ebx
0x18000ed12  sbb     rbx, rbx
0x18000ed15  and     rbx, r15
0x18000ed18  jnz     short loc_18000ED22
0x18000ed1a  mov     r9d, 0A1Eh
0x18000ed20  jmp     short loc_18000ECA6
0x18000ed22  mov     rax, [rbx+10h]
0x18000ed26  mov     [rsp+78h+arg_0], rax
0x18000ed2e  test    r12b, 2
0x18000ed32  jz      short loc_18000ED7A
0x18000ed34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed3b  lea     r15, WPP_GLOBAL_Control
0x18000ed42  cmp     rcx, r15
0x18000ed45  jz      short loc_18000ED5E
0x18000ed47  test    byte ptr [rcx+1Ch], 8
0x18000ed4b  jz      short loc_18000ED5E
0x18000ed4d  mov     r9, [rsi]
0x18000ed50  mov     edx, 0Ah
0x18000ed55  mov     rcx, [rcx+10h]
0x18000ed59  call    WPP_SF_I
0x18000ed5e  mov     rdx, rbx
0x18000ed61  mov     rcx, rdi
0x18000ed64  call    SrvRemoveProviderNotifyEventFromList
0x18000ed69  mov     rcx, rbx
0x18000ed6c  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18000ed73  call    MSCryptFree
0x18000ed78  jmp     short loc_18000ED81
0x18000ed7a  lea     r15, WPP_GLOBAL_Control
0x18000ed81  mov     rcx, [rdi+128h]
0x18000ed88  lea     rdx, [rsp+78h+arg_0]
0x18000ed90  mov     rax, [rdi+0E0h]
0x18000ed97  mov     r8d, r12d
0x18000ed9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed9f  mov     ebx, eax
0x18000eda1  test    eax, eax
0x18000eda3  jz      short loc_18000EDCE
0x18000eda5  mov     r9d, 0A53h
0x18000edab  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000edb2  lea     rdx, aStatus; "Status"
0x18000edb9  mov     ecx, eax
0x18000edbb  call    DebugTraceError
0x18000edc0  mov     ecx, ebx
0x18000edc2  call    NormalizeNteStatus
0x18000edc7  mov     ebx, eax
0x18000edc9  jmp     loc_18000EEA5
0x18000edce  test    ebp, ebp
0x18000edd0  jz      loc_18000EE97
0x18000edd6  mov     rdx, [rsp+78h+arg_0]
0x18000edde  lea     r8, [rsp+78h+var_58]
0x18000ede3  mov     rcx, r14
0x18000ede6  mov     [rsp+78h+var_58], 0
0x18000edef  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18000edf6  call    _CreateProviderNotifyEventMapping
0x18000edfb  mov     ebx, eax
0x18000edfd  test    eax, eax
0x18000edff  jz      short loc_18000EE2D
0x18000ee01  mov     r9d, 0A77h
0x18000ee07  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ee0e  lea     rdx, aStatus; "Status"
0x18000ee15  mov     ecx, eax
0x18000ee17  call    DebugTraceError
0x18000ee1c  mov     rcx, [rsp+78h+var_58]
0x18000ee21  test    rcx, rcx
0x18000ee24  jz      short loc_18000EEA5
0x18000ee26  call    MSCryptFree
0x18000ee2b  jmp     short loc_18000EEA5
0x18000ee2d  mov     rbx, [rsp+78h+var_58]
0x18000ee32  mov     r9, [rbx+18h]
0x18000ee36  mov     [rsi], r9
0x18000ee39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee40  cmp     rcx, r15
0x18000ee43  jz      short loc_18000EE59
0x18000ee45  test    byte ptr [rcx+1Ch], 8
0x18000ee49  jz      short loc_18000EE59
0x18000ee4b  mov     rcx, [rcx+10h]
0x18000ee4f  mov     edx, 0Bh
0x18000ee54  call    WPP_SF_I
0x18000ee59  lea     rsi, [rdi+130h]
0x18000ee60  mov     rcx, rsi; CriticalSection
0x18000ee63  call    cs:__imp_RtlEnterCriticalSection
0x18000ee69  lea     rax, [rdi+158h]
0x18000ee70  mov     rcx, [rax]
0x18000ee73  cmp     [rcx+8], rax
0x18000ee77  jz      short loc_18000EE80
0x18000ee79  mov     ecx, 3
0x18000ee7e  int     29h; Win8: RtlFailFast(ecx)
0x18000ee80  mov     [rbx], rcx
0x18000ee83  mov     [rbx+8], rax
0x18000ee87  mov     [rcx+8], rbx
0x18000ee8b  mov     rcx, rsi; CriticalSection
0x18000ee8e  mov     [rax], rbx
0x18000ee91  call    cs:__imp_RtlLeaveCriticalSection
0x18000ee97  mov     [rsp+78h+arg_0], 0
0x18000eea3  xor     ebx, ebx
0x18000eea5  mov     rax, [rsp+78h+arg_0]
0x18000eead  dec     rax
0x18000eeb0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000eeb4  ja      short loc_18000EF25
0x18000eeb6  mov     rcx, [rdi+128h]
0x18000eebd  lea     rdx, [rsp+78h+arg_0]
0x18000eec5  mov     rax, [rdi+0E0h]
0x18000eecc  mov     r8d, 2
0x18000eed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed7  mov     esi, eax
0x18000eed9  test    eax, eax
0x18000eedb  jns     short loc_18000EF25
0x18000eedd  mov     r9d, 0AACh
0x18000eee3  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eeea  lea     rdx, aTmpstatus; "tmpStatus"
0x18000eef1  mov     ecx, eax
0x18000eef3  call    DebugTraceError
0x18000eef8  mov     ecx, esi
0x18000eefa  call    NormalizeNteStatus
0x18000eeff  mov     esi, eax
0x18000ef01  test    eax, eax
0x18000ef03  jns     short loc_18000EF20
0x18000ef05  mov     r9d, 0AB1h
0x18000ef0b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ef12  lea     rdx, aTmpstatus; "tmpStatus"
0x18000ef19  mov     ecx, eax
0x18000ef1b  call    DebugTraceError
0x18000ef20  test    ebx, ebx
0x18000ef22  cmovns  ebx, esi
0x18000ef25  test    rdi, rdi
0x18000ef28  jz      short loc_18000EF3B
0x18000ef2a  mov     rcx, rdi
0x18000ef2d  call    SrvDereferenceProvider
0x18000ef32  test    eax, eax
0x18000ef34  jns     short loc_18000EF3B
0x18000ef36  test    ebx, ebx
0x18000ef38  cmovns  ebx, eax
0x18000ef3b  mov     eax, ebx
0x18000ef3d  add     rsp, 38h
0x18000ef41  pop     r15
0x18000ef43  pop     r14
0x18000ef45  pop     r13
0x18000ef47  pop     r12
0x18000ef49  pop     rdi
0x18000ef4a  pop     rsi
0x18000ef4b  pop     rbp
0x18000ef4c  pop     rbx
0x18000ef4d  retn
```
