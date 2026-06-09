# SrvCryptImportKey

- ea: `0x180003880`
- end: `0x180003cdb`
- name: `SrvCryptImportKey`
- size: `1115`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, int, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800026e4`
- `0x180003880`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180005540`
- `0x1800055e0`
- `0x180005f00`
- `0x180006010`
- `0x180006e60`
- `0x18000a6cc`
- `0x18000a798`
- `0x180019010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180003970`
- `ntdll!RtlAllocateHeap` at `0x180003970`
- `ntdll!RtlEnterCriticalSection` at `0x1800038b8`
- `ntdll!RtlEnterCriticalSection` at `0x180003a08`
- `ntdll!RtlEnterCriticalSection` at `0x1800038b8`
- `ntdll!RtlEnterCriticalSection` at `0x180003a08`
- `ntdll!RtlLeaveCriticalSection` at `0x1800038f1`
- `ntdll!RtlLeaveCriticalSection` at `0x180003a52`
- `ntdll!RtlLeaveCriticalSection` at `0x1800038f1`
- `ntdll!RtlLeaveCriticalSection` at `0x180003a52`

## string_xrefs

- `0x180003ae4`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003b3b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003bac`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003c02`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003c55`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003ca9`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptImportKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        int a8,
        int a9)
{
  volatile signed __int64 *v12; // rbx
  int v13; // ebp
  _QWORD *v14; // rax
  int v15; // edx
  __int64 v16; // r13
  __int64 v17; // r12
  int v18; // edx
  char *Heap; // rdi
  __int64 v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // ebp
  __int64 v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  int v26; // esi
  int v28; // eax
  __int64 v29; // r9
  __int64 v30; // rcx
  int v31; // eax

  if ( a1 )
  {
    v12 = 0;
    v13 = 0;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 40));
    v14 = *(_QWORD **)(a1 + 80);
    while ( v14 != (_QWORD *)(a1 + 80) )
    {
      v12 = v14 - 2;
      v14 = (_QWORD *)*v14;
      if ( *((_QWORD *)v12 + 45) == a2 )
      {
        if ( *(_DWORD *)v12 == 1145324614 )
        {
          _InterlockedIncrement64(v12 + 1);
          v13 = 1;
        }
        break;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 40));
    if ( !v13 )
      v12 = 0;
    if ( v12 )
    {
      v16 = 0;
      if ( a3 )
      {
        v16 = SrvLookupAndReferenceKey(a1, a3, 0);
        if ( !v16 )
        {
          v26 = -2146893786;
          DebugTraceError(
            2148073510LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
            2001);
LABEL_28:
          if ( _InterlockedExchangeAdd64(v12 + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
          {
            v28 = SrvFreeProvider((PVOID)v12);
            if ( v28 < 0 && v26 >= 0 )
              return (unsigned int)v28;
          }
          return (unsigned int)v26;
        }
      }
      if ( a6 )
      {
        if ( a7 && a8 )
        {
          v17 = 0;
          if ( !a5 || (v17 = MapRPCToBufferDesc()) != 0 )
          {
            Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x38u);
            if ( Heap )
            {
              *(_OWORD *)Heap = 0;
              *((_OWORD *)Heap + 1) = 0;
              *((_OWORD *)Heap + 2) = 0;
              *((_QWORD *)Heap + 6) = 0;
              if ( a3 )
                v20 = *(_QWORD *)(v16 + 40);
              else
                v20 = 0;
              v21 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, char *, __int64, int, int))v12 + 23))(
                      *((_QWORD *)v12 + 37),
                      v20,
                      a4,
                      v17,
                      Heap + 40,
                      a7,
                      a8,
                      a9);
              v22 = v21;
              if ( v21 )
              {
                DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 2065);
                v26 = NormalizeNteStatus(v22);
              }
              else
              {
                *(_QWORD *)Heap = 1145324615;
                *((_QWORD *)Heap + 1) = 1;
                _InterlockedIncrement64(v12 + 1);
                *((_QWORD *)Heap + 4) = v12;
                RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
                v23 = ++*(_QWORD *)(a1 + 160);
                *((_QWORD *)Heap + 6) = v23;
                *a6 = v23;
                _InterlockedIncrement64((volatile signed __int64 *)Heap + 1);
                v24 = (_QWORD *)(a1 + 144);
                v25 = *(_QWORD *)(a1 + 144);
                if ( *(_QWORD *)(v25 + 8) != a1 + 144 )
                  __fastfail(3u);
                *((_QWORD *)Heap + 3) = v24;
                *((_QWORD *)Heap + 2) = v25;
                *(_QWORD *)(v25 + 8) = Heap + 16;
                *v24 = Heap + 16;
                RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
                if ( (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline() )
                  IncrementKeyIsoPerfCounter(*(PPERF_COUNTERSET_INSTANCE *)(a1 + 296), 2u);
                Heap = 0;
                v26 = 0;
              }
            }
            else
            {
              v26 = -2146893810;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v18,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                  (unsigned int)"Status",
                  14,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                  250);
              }
            }
            if ( v17 )
              FreeBufferDesc(v17);
            if ( Heap )
              SrvCryptLocalFree(Heap);
            goto LABEL_27;
          }
          v26 = -2146893810;
          v29 = 2026;
          v30 = 2148073486LL;
LABEL_53:
          DebugTraceError(v30, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v29);
LABEL_27:
          if ( v16 )
          {
            v31 = SrvDereferenceKey(v16);
            if ( v31 < 0 && v26 >= 0 )
              v26 = v31;
          }
          goto LABEL_28;
        }
        v29 = 2016;
      }
      else
      {
        v29 = 2009;
      }
      v26 = -2146893785;
      v30 = 2148073511LL;
      goto LABEL_53;
    }
    v26 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        198);
  }
  else
  {
    v26 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        189);
  }
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180003880  mov     [rsp+arg_8], rbx
0x180003885  mov     [rsp+arg_18], r9
0x18000388a  mov     [rsp+arg_10], r8
0x18000388f  push    rbp
0x180003890  push    rsi
0x180003891  push    rdi
0x180003892  push    r12
0x180003894  push    r13
0x180003896  push    r14
0x180003898  push    r15
0x18000389a  sub     rsp, 50h
0x18000389e  mov     r15, r8
0x1800038a1  mov     rdi, rdx
0x1800038a4  mov     rsi, rcx
0x1800038a7  test    rcx, rcx
0x1800038aa  jz      loc_180003B82
0x1800038b0  xor     ebx, ebx
0x1800038b2  xor     ebp, ebp
0x1800038b4  add     rcx, 28h ; '('; CriticalSection
0x1800038b8  call    cs:__imp_RtlEnterCriticalSection
0x1800038be  mov     rax, [rsi+50h]
0x1800038c2  lea     rcx, [rsi+50h]
0x1800038c6  cmp     rax, rcx
0x1800038c9  jz      short loc_1800038ED
0x1800038cb  lea     rbx, [rax-10h]
0x1800038cf  mov     rax, [rax]
0x1800038d2  cmp     [rbx+168h], rdi
0x1800038d9  jnz     short loc_1800038C6
0x1800038db  cmp     dword ptr [rbx], 44444446h
0x1800038e1  jnz     short loc_1800038ED
0x1800038e3  lock inc qword ptr [rbx+8]
0x1800038e8  mov     ebp, 1
0x1800038ed  lea     rcx, [rsi+28h]; CriticalSection
0x1800038f1  call    cs:__imp_RtlLeaveCriticalSection
0x1800038f7  xor     eax, eax
0x1800038f9  test    ebp, ebp
0x1800038fb  cmovz   rbx, rax
0x1800038ff  test    rbx, rbx
0x180003902  jz      loc_180003B11
0x180003908  xor     r13d, r13d
0x18000390b  test    r15, r15
0x18000390e  jnz     loc_180003BE2
0x180003914  mov     r14, [rsp+88h+arg_28]
0x18000391c  test    r14, r14
0x18000391f  jz      loc_180003C24
0x180003925  mov     rbp, [rsp+88h+arg_30]
0x18000392d  test    rbp, rbp
0x180003930  jz      loc_180003C99
0x180003936  mov     r15d, [rsp+88h+arg_38]
0x18000393e  test    r15d, r15d
0x180003941  jz      loc_180003C99
0x180003947  mov     rcx, [rsp+88h+arg_20]
0x18000394f  xor     r12d, r12d
0x180003952  test    rcx, rcx
0x180003955  jnz     loc_180003C2C
0x18000395b  mov     rcx, gs:60h
0x180003964  xor     edx, edx; Flags
0x180003966  mov     r8d, 38h ; '8'; Size
0x18000396c  mov     rcx, [rcx+30h]; HeapHandle
0x180003970  call    cs:__imp_RtlAllocateHeap
0x180003976  mov     rdi, rax
0x180003979  test    rax, rax
0x18000397c  jz      loc_180003AC2
0x180003982  xorps   xmm0, xmm0
0x180003985  xor     eax, eax
0x180003987  movups  xmmword ptr [rdi], xmm0
0x18000398a  movups  xmmword ptr [rdi+10h], xmm0
0x18000398e  movups  xmmword ptr [rdi+20h], xmm0
0x180003992  mov     [rdi+30h], rax
0x180003996  cmp     [rsp+88h+arg_10], rax
0x18000399e  jnz     loc_180003BD9
0x1800039a4  xor     edx, edx
0x1800039a6  mov     eax, [rsp+88h+arg_40]
0x1800039ad  lea     rcx, [rdi+28h]
0x1800039b1  mov     r8, [rsp+88h+arg_18]
0x1800039b9  mov     r9, r12
0x1800039bc  mov     [rsp+88h+var_50], eax
0x1800039c0  mov     rax, [rbx+0B8h]
0x1800039c7  mov     [rsp+88h+var_58], r15d
0x1800039cc  mov     [rsp+88h+var_60], rbp
0x1800039d1  mov     [rsp+88h+var_68], rcx
0x1800039d6  mov     rcx, [rbx+128h]
0x1800039dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e2  mov     ebp, eax
0x1800039e4  test    eax, eax
0x1800039e6  jnz     loc_180003C4F
0x1800039ec  mov     qword ptr [rdi], 44444447h
0x1800039f3  mov     qword ptr [rdi+8], 1
0x1800039fb  lock inc qword ptr [rbx+8]
0x180003a00  lea     rcx, [rsi+68h]; CriticalSection
0x180003a04  mov     [rdi+20h], rbx
0x180003a08  call    cs:__imp_RtlEnterCriticalSection
0x180003a0e  inc     qword ptr [rsi+0A0h]
0x180003a15  mov     rax, [rsi+0A0h]
0x180003a1c  mov     [rdi+30h], rax
0x180003a20  mov     [r14], rax
0x180003a23  lock inc qword ptr [rdi+8]
0x180003a28  lea     rcx, [rsi+90h]
0x180003a2f  mov     rdx, [rcx]
0x180003a32  cmp     [rdx+8], rcx
0x180003a36  jnz     loc_180003C78
0x180003a3c  lea     rax, [rdi+10h]
0x180003a40  mov     [rax+8], rcx
0x180003a44  mov     [rax], rdx
0x180003a47  mov     [rdx+8], rax
0x180003a4b  mov     [rcx], rax
0x180003a4e  lea     rcx, [rsi+68h]; CriticalSection
0x180003a52  call    cs:__imp_RtlLeaveCriticalSection
0x180003a58  call    Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline
0x180003a5d  test    eax, eax
0x180003a5f  jz      short loc_180003A72
0x180003a61  mov     rcx, [rsi+128h]; Instance
0x180003a68  mov     edx, 2; CounterId
0x180003a6d  call    IncrementKeyIsoPerfCounter
0x180003a72  xor     edi, edi
0x180003a74  xor     esi, esi
0x180003a76  test    r12, r12
0x180003a79  jnz     loc_180003C7F
0x180003a7f  test    rdi, rdi
0x180003a82  jnz     loc_180003C8C
0x180003a88  test    r13, r13
0x180003a8b  jnz     loc_180003CC1
0x180003a91  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003a98  lock xadd [rbx+8], rax
0x180003a9e  cmp     rax, 1
0x180003aa2  jz      loc_180003B68
0x180003aa8  mov     rbx, [rsp+88h+arg_8]
0x180003ab0  mov     eax, esi
0x180003ab2  add     rsp, 50h
0x180003ab6  pop     r15
0x180003ab8  pop     r14
0x180003aba  pop     r13
0x180003abc  pop     r12
0x180003abe  pop     rdi
0x180003abf  pop     rsi
0x180003ac0  pop     rbp
0x180003ac1  retn
0x180003ac2  mov     esi, 8009000Eh
0x180003ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ace  lea     rax, WPP_GLOBAL_Control
0x180003ad5  cmp     rcx, rax
0x180003ad8  jz      short loc_180003A76
0x180003ada  test    byte ptr [rcx+1Ch], 1
0x180003ade  jz      short loc_180003A76
0x180003ae0  mov     rcx, [rcx+10h]
0x180003ae4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003aeb  mov     [rsp+88h+var_58], 7FAh
0x180003af3  lea     r9, aStatus; "Status"
0x180003afa  mov     [rsp+88h+var_60], r8
0x180003aff  mov     dword ptr [rsp+88h+var_68], 8009000Eh
0x180003b07  call    WPP_SF_sDsd
0x180003b0c  jmp     loc_180003A76
0x180003b11  mov     esi, 80090026h
0x180003b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b1d  lea     rax, WPP_GLOBAL_Control
0x180003b24  cmp     rcx, rax
0x180003b27  jz      loc_180003AA8
0x180003b2d  test    byte ptr [rcx+1Ch], 1
0x180003b31  jz      loc_180003AA8
0x180003b37  mov     rcx, [rcx+10h]
0x180003b3b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003b42  mov     [rsp+88h+var_58], 7C6h
0x180003b4a  lea     r9, aStatus; "Status"
0x180003b51  mov     [rsp+88h+var_60], r8
0x180003b56  mov     dword ptr [rsp+88h+var_68], 80090026h
0x180003b5e  call    WPP_SF_sDsd
0x180003b63  jmp     loc_180003AA8
0x180003b68  mov     rcx, rbx; P
0x180003b6b  call    SrvFreeProvider
0x180003b70  test    eax, eax
0x180003b72  jns     loc_180003AA8
0x180003b78  test    esi, esi
0x180003b7a  cmovns  esi, eax
0x180003b7d  jmp     loc_180003AA8
0x180003b82  mov     esi, 80090026h
0x180003b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b8e  lea     rax, WPP_GLOBAL_Control
0x180003b95  cmp     rcx, rax
0x180003b98  jz      loc_180003AA8
0x180003b9e  test    byte ptr [rcx+1Ch], 1
0x180003ba2  jz      loc_180003AA8
0x180003ba8  mov     rcx, [rcx+10h]
0x180003bac  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003bb3  mov     [rsp+88h+var_58], 7BDh
0x180003bbb  lea     r9, aStatus; "Status"
0x180003bc2  mov     [rsp+88h+var_60], r8
0x180003bc7  mov     dword ptr [rsp+88h+var_68], 80090026h
0x180003bcf  call    WPP_SF_sDsd
0x180003bd4  jmp     loc_180003AA8
0x180003bd9  mov     rdx, [r13+28h]
0x180003bdd  jmp     loc_1800039A6
0x180003be2  xor     r8d, r8d
0x180003be5  mov     rdx, r15
0x180003be8  mov     rcx, rsi
0x180003beb  call    SrvLookupAndReferenceKey
0x180003bf0  mov     r13, rax
0x180003bf3  test    rax, rax
0x180003bf6  jnz     loc_180003914
0x180003bfc  mov     r9d, 7D1h
0x180003c02  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003c09  lea     rdx, aStatus; "Status"
0x180003c10  mov     ecx, 80090026h
0x180003c15  mov     esi, 80090026h
0x180003c1a  call    DebugTraceError
0x180003c1f  jmp     loc_180003A91
0x180003c24  mov     r9d, 7D9h
0x180003c2a  jmp     short loc_180003C9F
0x180003c2c  call    _MapRPCToBufferDesc
0x180003c31  mov     r12, rax
0x180003c34  test    rax, rax
0x180003c37  jnz     loc_18000395B
0x180003c3d  mov     esi, 8009000Eh
0x180003c42  mov     r9d, 7EAh
0x180003c48  mov     ecx, 8009000Eh
0x180003c4d  jmp     short loc_180003CA9
0x180003c4f  mov     r9d, 811h
0x180003c55  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003c5c  lea     rdx, aStatus; "Status"
0x180003c63  mov     ecx, ebp
0x180003c65  call    DebugTraceError
0x180003c6a  mov     ecx, ebp
0x180003c6c  call    NormalizeNteStatus
0x180003c71  mov     esi, eax
0x180003c73  jmp     loc_180003A76
0x180003c78  mov     ecx, 3
0x180003c7d  int     29h; Win8: RtlFailFast(ecx)
0x180003c7f  mov     rcx, r12
0x180003c82  call    _FreeBufferDesc
0x180003c87  jmp     loc_180003A7F
0x180003c8c  mov     rcx, rdi; P
0x180003c8f  call    SrvCryptLocalFree
0x180003c94  jmp     loc_180003A88
0x180003c99  mov     r9d, 7E0h
0x180003c9f  mov     esi, 80090027h
0x180003ca4  mov     ecx, 80090027h
0x180003ca9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003cb0  lea     rdx, aStatus; "Status"
0x180003cb7  call    DebugTraceError
0x180003cbc  jmp     loc_180003A88
0x180003cc1  mov     rcx, r13
0x180003cc4  call    SrvDereferenceKey
0x180003cc9  test    eax, eax
0x180003ccb  jns     loc_180003A91
0x180003cd1  test    esi, esi
0x180003cd3  cmovns  esi, eax
0x180003cd6  jmp     loc_180003A91
```
