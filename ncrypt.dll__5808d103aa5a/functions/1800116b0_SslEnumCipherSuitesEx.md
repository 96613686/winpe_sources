# SslEnumCipherSuitesEx

- ea: `0x1800116b0`
- end: `0x180011944`
- name: `SslEnumCipherSuitesEx`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x1800116b0`
- `0x180011cd0`
- `0x180020010`

## string_xrefs

- `0x1800117a8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001181c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800118be`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001192c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslEnumCipherSuitesEx(__int64 a1, __int64 a2, __int64 *a3, __int64 *a4, DWORD a5)
{
  NCRYPT_KEY_HANDLE *v7; // rdx
  __int64 v8; // rbp
  NCryptKeyName **v9; // r8
  PVOID *v10; // r9
  __int64 v11; // rbx
  __int64 *v12; // rdi
  __int64 *v13; // rax
  __int64 *v14; // rsi
  __int64 v15; // rdx
  unsigned int v16; // ebx
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 *v20; // rax

  v8 = ValidateSslProvHandle();
  if ( v8 )
  {
    if ( *(_WORD *)(v8 + 32) < 4u )
    {
      v16 = -2146893783;
      v18 = 1336;
      v19 = 2148073513LL;
LABEL_34:
      DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v18);
      return NormalizeNteStatus(v16, v7, v9, v10, a5);
    }
    v11 = 0;
    if ( v7 )
    {
      v11 = ValidateSslKeyHandle(v7);
      if ( !v11 )
      {
        v16 = -2146893786;
        v18 = 1346;
        v19 = 2148073510LL;
        goto LABEL_34;
      }
    }
    if ( !a3 || !a4 )
    {
      v16 = -2146893785;
      v18 = 1354;
      v19 = 2148073511LL;
      goto LABEL_34;
    }
    v12 = 0;
    if ( !*v10 )
    {
      v20 = (__int64 *)SafeAllocaAllocateFromHeap(32);
      v12 = v20;
      if ( !v20 )
      {
        v16 = -2146893810;
        v18 = 1371;
        v19 = 2148073486LL;
        goto LABEL_34;
      }
      *(_OWORD *)v20 = 0;
      *((_OWORD *)v20 + 1) = 0;
    }
    v13 = (__int64 *)SafeAllocaAllocateFromHeap(32);
    v14 = v13;
    if ( v13 )
    {
      *(_OWORD *)v13 = 0;
      *((_OWORD *)v13 + 1) = 0;
      if ( v11 )
        v15 = *(_QWORD *)(v11 + 16);
      else
        v15 = 0;
      v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, __int64 *, DWORD))(v8 + 328))(
              *(_QWORD *)(v8 + 424),
              v15,
              a3,
              a4,
              a5);
      if ( (v16 & 0x80000000) == 0 )
      {
        if ( v12 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v8 + 16));
          *v12 = v8;
          v12[1] = *a4;
          MSCryptAddMemoryBuffer(&SslpProviderBufferList, v12);
        }
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 16));
        *v14 = v8;
        v14[1] = *a3;
        MSCryptAddMemoryBuffer(&SslpProviderBufferList, v14);
        v16 = 0;
        return NormalizeNteStatus(v16, v7, v9, v10, a5);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v7,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          (unsigned int)"Status",
          v16,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          125);
    }
    else
    {
      v16 = -2146893810;
      DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1387);
    }
    if ( v12 )
      MSCryptFree(v12);
    if ( v14 )
      MSCryptFree(v14);
  }
  else
  {
    v16 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v7,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        43);
  }
  return NormalizeNteStatus(v16, v7, v9, v10, a5);
}

```

## disassembly

```asm
0x1800116b0  push    rbx
0x1800116b2  push    rbp
0x1800116b3  push    rsi
0x1800116b4  push    rdi
0x1800116b5  push    r14
0x1800116b7  push    r15
0x1800116b9  sub     rsp, 48h
0x1800116bd  mov     r14, r9
0x1800116c0  mov     r15, r8
0x1800116c3  call    ValidateSslProvHandle
0x1800116c8  mov     rbp, rax
0x1800116cb  test    rax, rax
0x1800116ce  jz      loc_1800117FA
0x1800116d4  mov     eax, 4
0x1800116d9  cmp     ax, [rbp+20h]
0x1800116dd  ja      loc_180011846
0x1800116e3  xor     ebx, ebx
0x1800116e5  test    rdx, rdx
0x1800116e8  jnz     loc_18001185B
0x1800116ee  test    r15, r15
0x1800116f1  jz      loc_18001191C
0x1800116f7  test    r14, r14
0x1800116fa  jz      loc_18001191C
0x180011700  xor     edi, edi
0x180011702  lea     esi, [rdi+20h]
0x180011705  cmp     [r9], rdi
0x180011708  jz      loc_180011884
0x18001170e  mov     rcx, rsi
0x180011711  call    SafeAllocaAllocateFromHeap
0x180011716  mov     rsi, rax
0x180011719  test    rax, rax
0x18001171c  jz      loc_1800118B8
0x180011722  xorps   xmm0, xmm0
0x180011725  movups  xmmword ptr [rax], xmm0
0x180011728  movups  xmmword ptr [rax+10h], xmm0
0x18001172c  test    rbx, rbx
0x18001172f  jnz     loc_1800117F1
0x180011735  xor     edx, edx
0x180011737  mov     ecx, [rsp+78h+arg_20]
0x18001173e  mov     r9, r14
0x180011741  mov     rax, [rbp+148h]
0x180011748  mov     r8, r15
0x18001174b  mov     [rsp+78h+var_58], ecx
0x18001174f  mov     rcx, [rbp+1A8h]
0x180011756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001175b  mov     ebx, eax
0x18001175d  test    eax, eax
0x18001175f  js      short loc_18001178B
0x180011761  test    rdi, rdi
0x180011764  jnz     loc_1800118FA
0x18001176a  lock inc dword ptr [rbp+10h]
0x18001176e  mov     [rsi], rbp
0x180011771  lea     rcx, SslpProviderBufferList
0x180011778  mov     rax, [r15]
0x18001177b  mov     rdx, rsi
0x18001177e  mov     [rsi+8], rax
0x180011782  call    MSCryptAddMemoryBuffer
0x180011787  xor     ebx, ebx
0x180011789  jmp     short loc_1800117DE
0x18001178b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011792  lea     rax, WPP_GLOBAL_Control
0x180011799  cmp     rcx, rax
0x18001179c  jz      short loc_1800117CC
0x18001179e  test    byte ptr [rcx+1Ch], 1
0x1800117a2  jz      short loc_1800117CC
0x1800117a4  mov     rcx, [rcx+10h]
0x1800117a8  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800117af  mov     [rsp+78h+var_48], 57Dh
0x1800117b7  lea     r9, aStatus; "Status"
0x1800117be  mov     [rsp+78h+var_50], r8
0x1800117c3  mov     [rsp+78h+var_58], ebx
0x1800117c7  call    WPP_SF_sDsd
0x1800117cc  test    rdi, rdi
0x1800117cf  jnz     loc_1800118E0
0x1800117d5  test    rsi, rsi
0x1800117d8  jnz     loc_1800118ED
0x1800117de  mov     ecx, ebx
0x1800117e0  add     rsp, 48h
0x1800117e4  pop     r15
0x1800117e6  pop     r14
0x1800117e8  pop     rdi
0x1800117e9  pop     rsi
0x1800117ea  pop     rbp
0x1800117eb  pop     rbx
0x1800117ec  jmp     NormalizeNteStatus
0x1800117f1  mov     rdx, [rbx+10h]
0x1800117f5  jmp     loc_180011737
0x1800117fa  mov     ebx, 80090026h
0x1800117ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180011806  lea     rax, WPP_GLOBAL_Control
0x18001180d  cmp     rcx, rax
0x180011810  jz      short loc_1800117DE
0x180011812  test    byte ptr [rcx+1Ch], 1
0x180011816  jz      short loc_1800117DE
0x180011818  mov     rcx, [rcx+10h]
0x18001181c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011823  mov     [rsp+78h+var_48], 52Bh
0x18001182b  lea     r9, aStatus; "Status"
0x180011832  mov     [rsp+78h+var_50], r8
0x180011837  mov     [rsp+78h+var_58], 80090026h
0x18001183f  call    WPP_SF_sDsd
0x180011844  jmp     short loc_1800117DE
0x180011846  mov     ebx, 80090029h
0x18001184b  mov     r9d, 538h
0x180011851  mov     ecx, 80090029h
0x180011856  jmp     loc_18001192C
0x18001185b  mov     rcx, rdx
0x18001185e  call    ValidateSslKeyHandle
0x180011863  mov     rbx, rax
0x180011866  test    rax, rax
0x180011869  jnz     loc_1800116EE
0x18001186f  mov     ebx, 80090026h
0x180011874  mov     r9d, 542h
0x18001187a  mov     ecx, 80090026h
0x18001187f  jmp     loc_18001192C
0x180011884  mov     rcx, rsi
0x180011887  call    SafeAllocaAllocateFromHeap
0x18001188c  mov     rdi, rax
0x18001188f  test    rax, rax
0x180011892  jnz     short loc_1800118A9
0x180011894  mov     ebx, 8009000Eh
0x180011899  mov     r9d, 55Bh
0x18001189f  mov     ecx, 8009000Eh
0x1800118a4  jmp     loc_18001192C
0x1800118a9  xorps   xmm0, xmm0
0x1800118ac  movups  xmmword ptr [rax], xmm0
0x1800118af  movups  xmmword ptr [rax+10h], xmm0
0x1800118b3  jmp     loc_18001170E
0x1800118b8  mov     r9d, 56Bh
0x1800118be  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800118c5  lea     rdx, aStatus; "Status"
0x1800118cc  mov     ecx, 8009000Eh
0x1800118d1  mov     ebx, 8009000Eh
0x1800118d6  call    DebugTraceError
0x1800118db  jmp     loc_1800117CC
0x1800118e0  mov     rcx, rdi
0x1800118e3  call    MSCryptFree
0x1800118e8  jmp     loc_1800117D5
0x1800118ed  mov     rcx, rsi
0x1800118f0  call    MSCryptFree
0x1800118f5  jmp     loc_1800117DE
0x1800118fa  lock inc dword ptr [rbp+10h]
0x1800118fe  mov     [rdi], rbp
0x180011901  lea     rcx, SslpProviderBufferList
0x180011908  mov     rax, [r14]
0x18001190b  mov     rdx, rdi
0x18001190e  mov     [rdi+8], rax
0x180011912  call    MSCryptAddMemoryBuffer
0x180011917  jmp     loc_18001176A
0x18001191c  mov     ebx, 80090027h
0x180011921  mov     r9d, 54Ah
0x180011927  mov     ecx, 80090027h
0x18001192c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011933  lea     rdx, aStatus; "Status"
0x18001193a  call    DebugTraceError
0x18001193f  jmp     loc_1800117DE
```
