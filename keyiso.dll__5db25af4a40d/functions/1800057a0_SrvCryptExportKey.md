# SrvCryptExportKey

- ea: `0x1800057a0`
- end: `0x180005ba9`
- name: `SrvCryptExportKey`
- size: `1033`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, PVOID Memory, ULONG MemorySize, __int64, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800026e4`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x1800055e0`
- `0x1800057a0`
- `0x180005f00`
- `0x180006010`
- `0x18000d0ac`
- `0x180019010`

## import_xrefs

- `CRYPTBASE!SystemFunction040` at `0x180005984`
- `CRYPTBASE!SystemFunction040` at `0x180005984`
- `ntdll!RtlEnterCriticalSection` at `0x1800057d1`
- `ntdll!RtlEnterCriticalSection` at `0x1800057d1`
- `ntdll!RtlLeaveCriticalSection` at `0x180005809`
- `ntdll!RtlLeaveCriticalSection` at `0x180005809`

## string_xrefs

- `0x180005946`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005998`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800059f9`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005a59`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005ac4`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005b03`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005b55`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005b7d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptExportKey(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        PVOID Memory,
        ULONG MemorySize,
        __int64 a9,
        int a10)
{
  _QWORD *v13; // rbx
  int v14; // ebp
  _QWORD *v15; // rax
  int v16; // edx
  __int64 v17; // r15
  __int64 v18; // r13
  __int64 v19; // rbp
  __int64 v20; // r8
  int v21; // edx
  unsigned int v22; // esi
  int v23; // edi
  int v24; // eax
  NTSTATUS v26; // eax
  int v27; // eax

  if ( a1 )
  {
    v13 = 0;
    v14 = 0;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    v15 = *(_QWORD **)(a1 + 144);
    while ( v15 != (_QWORD *)(a1 + 144) )
    {
      v13 = v15 - 2;
      v15 = (_QWORD *)*v15;
      if ( v13[6] == a3 )
      {
        if ( *(_DWORD *)v13 == 1145324615 )
        {
          _InterlockedIncrement64(v13 + 1);
          v14 = 1;
        }
        break;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    if ( !v14 )
      v13 = 0;
    if ( !v13 )
    {
      v23 = -2146893786;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v16,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          36);
      return (unsigned int)v23;
    }
    v17 = 0;
    v18 = v13[4];
    if ( a4 )
    {
      v17 = SrvLookupAndReferenceKey(a1, a4, 0);
      if ( !v17 )
      {
        v23 = -2146893786;
        DebugTraceError(
          2148073510LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          1584);
        goto LABEL_21;
      }
    }
    if ( !a9 )
    {
      v23 = -2146893785;
      DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 1592);
LABEL_21:
      v24 = SrvDereferenceKey(v13);
      if ( v24 < 0 && v23 >= 0 )
        v23 = v24;
      if ( v17 )
      {
        v27 = SrvDereferenceKey(v17);
        if ( v27 < 0 && v23 >= 0 )
          return (unsigned int)v27;
      }
      return (unsigned int)v23;
    }
    v19 = 0;
    if ( a6 )
    {
      v19 = MapRPCToBufferDesc();
      if ( !v19 )
      {
        v23 = -2146893810;
        DebugTraceError(
          2148073486LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          1602);
        goto LABEL_21;
      }
    }
    if ( MemorySize )
    {
      if ( (MemorySize & 0xF) != 0 )
      {
        v23 = -2146893785;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v16,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
            80);
        goto LABEL_19;
      }
      memset_0(Memory, 0, MemorySize);
    }
    if ( a4 )
      v20 = *(_QWORD *)(v17 + 40);
    else
      v20 = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, __int64, PVOID, ULONG, __int64, int))(v18 + 192))(
            *(_QWORD *)(v18 + 296),
            v13[5],
            v20,
            a5,
            v19,
            Memory,
            MemorySize,
            a9,
            a10);
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v21,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          (unsigned int)"Status",
          v22,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          106);
      v23 = NormalizeNteStatus(v22);
    }
    else if ( MemorySize && (v26 = SystemFunction040(Memory, MemorySize, 2u), v26 < 0) )
    {
      DebugTraceError(
        (unsigned int)v26,
        "ntStatus",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        1661);
      v23 = -2146893779;
    }
    else
    {
      v23 = 0;
    }
LABEL_19:
    if ( v19 )
      FreeBufferDesc(v19);
    goto LABEL_21;
  }
  v23 = -2146893786;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)v23;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    a2,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
    (unsigned int)"Status",
    38,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
    27);
  return 2148073510LL;
}

```

## disassembly

```asm
0x1800057a0  mov     rax, rsp
0x1800057a3  push    rsi
0x1800057a4  push    rdi
0x1800057a5  push    r14
0x1800057a7  sub     rsp, 60h
0x1800057ab  mov     r14, r9
0x1800057ae  mov     rdi, r8
0x1800057b1  mov     rsi, rcx
0x1800057b4  test    rcx, rcx
0x1800057b7  jz      loc_180005924
0x1800057bd  mov     [rax+8], rbx
0x1800057c1  add     rcx, 68h ; 'h'; CriticalSection
0x1800057c5  mov     [rax+10h], rbp
0x1800057c9  xor     ebx, ebx
0x1800057cb  xor     ebp, ebp
0x1800057cd  mov     [rax-28h], r15
0x1800057d1  call    cs:__imp_RtlEnterCriticalSection
0x1800057d7  lea     rdx, [rsi+90h]
0x1800057de  mov     rax, [rdx]
0x1800057e1  cmp     rax, rdx
0x1800057e4  jz      short loc_180005805
0x1800057e6  lea     rbx, [rax-10h]
0x1800057ea  mov     rax, [rax]
0x1800057ed  cmp     [rbx+30h], rdi
0x1800057f1  jnz     short loc_1800057E1
0x1800057f3  cmp     dword ptr [rbx], 44444447h
0x1800057f9  jnz     short loc_180005805
0x1800057fb  lock inc qword ptr [rbx+8]
0x180005800  mov     ebp, 1
0x180005805  lea     rcx, [rsi+68h]; CriticalSection
0x180005809  call    cs:__imp_RtlLeaveCriticalSection
0x18000580f  xor     eax, eax
0x180005811  test    ebp, ebp
0x180005813  cmovz   rbx, rax
0x180005817  test    rbx, rbx
0x18000581a  jz      loc_1800059CF
0x180005820  xor     r15d, r15d
0x180005823  mov     [rsp+78h+var_20], r13
0x180005828  mov     r13, [rbx+20h]
0x18000582c  test    r14, r14
0x18000582f  jnz     loc_180005B35
0x180005835  mov     rsi, [rsp+78h+arg_40]
0x18000583d  test    rsi, rsi
0x180005840  jz      loc_180005B77
0x180005846  mov     rcx, [rsp+78h+arg_28]
0x18000584e  xor     ebp, ebp
0x180005850  test    rcx, rcx
0x180005853  jnz     loc_180005AAD
0x180005859  mov     edi, [rsp+78h+MemorySize]
0x180005860  mov     [rsp+78h+arg_10], r12
0x180005868  mov     r12, [rsp+78h+Memory]
0x180005870  test    edi, edi
0x180005872  jnz     loc_1800059B7
0x180005878  test    r14, r14
0x18000587b  jnz     loc_180005A26
0x180005881  xor     r8d, r8d
0x180005884  mov     eax, [rsp+78h+arg_48]
0x18000588b  mov     r9, [rsp+78h+arg_20]
0x180005893  mov     rdx, [rbx+28h]
0x180005897  mov     rcx, [r13+128h]
0x18000589e  mov     [rsp+78h+var_38], eax
0x1800058a2  mov     rax, [r13+0C0h]
0x1800058a9  mov     [rsp+78h+var_40], rsi
0x1800058ae  mov     [rsp+78h+var_48], edi
0x1800058b2  mov     [rsp+78h+var_50], r12
0x1800058b7  mov     [rsp+78h+var_58], rbp
0x1800058bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058c1  mov     esi, eax
0x1800058c3  test    eax, eax
0x1800058c5  jnz     loc_180005AE6
0x1800058cb  test    edi, edi
0x1800058cd  jnz     loc_180005979
0x1800058d3  xor     edi, edi
0x1800058d5  mov     r12, [rsp+78h+arg_10]
0x1800058dd  test    rbp, rbp
0x1800058e0  jnz     loc_180005AA0
0x1800058e6  mov     rcx, rbx
0x1800058e9  call    SrvDereferenceKey
0x1800058ee  mov     r13, [rsp+78h+var_20]
0x1800058f3  test    eax, eax
0x1800058f5  js      loc_180005B9F
0x1800058fb  test    r15, r15
0x1800058fe  jnz     loc_180005A86
0x180005904  mov     rbp, [rsp+78h+arg_8]
0x18000590c  mov     rbx, [rsp+78h+arg_0]
0x180005914  mov     r15, [rsp+78h+var_28]
0x180005919  mov     eax, edi
0x18000591b  add     rsp, 60h
0x18000591f  pop     r14
0x180005921  pop     rdi
0x180005922  pop     rsi
0x180005923  retn
0x180005924  mov     edi, 80090026h
0x180005929  mov     rcx, cs:WPP_GLOBAL_Control
0x180005930  lea     rax, WPP_GLOBAL_Control
0x180005937  cmp     rcx, rax
0x18000593a  jz      short loc_180005919
0x18000593c  test    byte ptr [rcx+1Ch], 1
0x180005940  jz      short loc_180005919
0x180005942  mov     rcx, [rcx+10h]
0x180005946  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000594d  mov     [rsp+78h+var_48], 61Bh
0x180005955  lea     r9, aStatus; "Status"
0x18000595c  mov     [rsp+78h+var_50], r8
0x180005961  mov     dword ptr [rsp+78h+var_58], 80090026h
0x180005969  call    WPP_SF_sDsd
0x18000596e  mov     eax, edi
0x180005970  add     rsp, 60h
0x180005974  pop     r14
0x180005976  pop     rdi
0x180005977  pop     rsi
0x180005978  retn
0x180005979  mov     r8d, 2; OptionFlags
0x18000597f  mov     edx, edi; MemorySize
0x180005981  mov     rcx, r12; Memory
0x180005984  call    cs:__imp_SystemFunction040
0x18000598a  test    eax, eax
0x18000598c  jns     loc_1800058D3
0x180005992  mov     r9d, 67Dh
0x180005998  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000599f  lea     rdx, aNtstatus; "ntStatus"
0x1800059a6  mov     ecx, eax
0x1800059a8  call    DebugTraceError
0x1800059ad  mov     edi, 8009002Dh
0x1800059b2  jmp     loc_1800058D5
0x1800059b7  test    dil, 0Fh
0x1800059bb  jnz     short loc_180005A2F
0x1800059bd  mov     r8, rdi; Size
0x1800059c0  xor     edx, edx; Val
0x1800059c2  mov     rcx, r12; void *
0x1800059c5  call    memset_0
0x1800059ca  jmp     loc_180005878
0x1800059cf  mov     edi, 80090026h
0x1800059d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059db  lea     rax, WPP_GLOBAL_Control
0x1800059e2  cmp     rcx, rax
0x1800059e5  jz      loc_180005904
0x1800059eb  test    byte ptr [rcx+1Ch], 1
0x1800059ef  jz      loc_180005904
0x1800059f5  mov     rcx, [rcx+10h]
0x1800059f9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005a00  mov     [rsp+78h+var_48], 624h
0x180005a08  lea     r9, aStatus; "Status"
0x180005a0f  mov     [rsp+78h+var_50], r8
0x180005a14  mov     dword ptr [rsp+78h+var_58], 80090026h
0x180005a1c  call    WPP_SF_sDsd
0x180005a21  jmp     loc_180005904
0x180005a26  mov     r8, [r15+28h]
0x180005a2a  jmp     loc_180005884
0x180005a2f  mov     edi, 80090027h
0x180005a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a3b  lea     rax, WPP_GLOBAL_Control
0x180005a42  cmp     rcx, rax
0x180005a45  jz      loc_1800058D5
0x180005a4b  test    byte ptr [rcx+1Ch], 1
0x180005a4f  jz      loc_1800058D5
0x180005a55  mov     rcx, [rcx+10h]
0x180005a59  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005a60  mov     [rsp+78h+var_48], 650h
0x180005a68  lea     r9, aStatus; "Status"
0x180005a6f  mov     [rsp+78h+var_50], r8
0x180005a74  mov     dword ptr [rsp+78h+var_58], 80090027h
0x180005a7c  call    WPP_SF_sDsd
0x180005a81  jmp     loc_1800058D5
0x180005a86  mov     rcx, r15
0x180005a89  call    SrvDereferenceKey
0x180005a8e  test    eax, eax
0x180005a90  jns     loc_180005904
0x180005a96  test    edi, edi
0x180005a98  cmovns  edi, eax
0x180005a9b  jmp     loc_180005904
0x180005aa0  mov     rcx, rbp
0x180005aa3  call    _FreeBufferDesc
0x180005aa8  jmp     loc_1800058E6
0x180005aad  call    _MapRPCToBufferDesc
0x180005ab2  mov     rbp, rax
0x180005ab5  test    rax, rax
0x180005ab8  jnz     loc_180005859
0x180005abe  mov     r9d, 642h
0x180005ac4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005acb  lea     rdx, aStatus; "Status"
0x180005ad2  mov     ecx, 8009000Eh
0x180005ad7  mov     edi, 8009000Eh
0x180005adc  call    DebugTraceError
0x180005ae1  jmp     loc_1800058E6
0x180005ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aed  lea     rax, WPP_GLOBAL_Control
0x180005af4  cmp     rcx, rax
0x180005af7  jz      short loc_180005B27
0x180005af9  test    byte ptr [rcx+1Ch], 1
0x180005afd  jz      short loc_180005B27
0x180005aff  mov     rcx, [rcx+10h]
0x180005b03  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005b0a  mov     [rsp+78h+var_48], 66Ah
0x180005b12  lea     r9, aStatus; "Status"
0x180005b19  mov     [rsp+78h+var_50], r8
0x180005b1e  mov     dword ptr [rsp+78h+var_58], esi
0x180005b22  call    WPP_SF_sDsd
0x180005b27  mov     ecx, esi
0x180005b29  call    NormalizeNteStatus
0x180005b2e  mov     edi, eax
0x180005b30  jmp     loc_1800058D5
0x180005b35  xor     r8d, r8d
0x180005b38  mov     rdx, r14
0x180005b3b  mov     rcx, rsi
0x180005b3e  call    SrvLookupAndReferenceKey
0x180005b43  mov     r15, rax
0x180005b46  test    rax, rax
0x180005b49  jnz     loc_180005835
0x180005b4f  mov     r9d, 630h
0x180005b55  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005b5c  lea     rdx, aStatus; "Status"
0x180005b63  mov     ecx, 80090026h
0x180005b68  mov     edi, 80090026h
0x180005b6d  call    DebugTraceError
0x180005b72  jmp     loc_1800058E6
0x180005b77  mov     r9d, 638h
0x180005b7d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005b84  lea     rdx, aStatus; "Status"
0x180005b8b  mov     ecx, 80090027h
0x180005b90  mov     edi, 80090027h
0x180005b95  call    DebugTraceError
0x180005b9a  jmp     loc_1800058E6
0x180005b9f  test    edi, edi
0x180005ba1  cmovns  edi, eax
0x180005ba4  jmp     loc_1800058FB
```
