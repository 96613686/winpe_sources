# I_GetCipherEntry

- ea: `0x1800417a0`
- end: `0x18004188b`
- name: `I_GetCipherEntry`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008d2cc`

## callees

- `0x18000c500`
- `0x18000dd90`
- `0x18001155c`
- `0x1800417a0`
- `0x180063db0`
- `0x18008b798`

## string_xrefs

- `0x18004184d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18004186c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a7d1f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a7d95`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall I_GetCipherEntry(unsigned int a1, char a2, __int64 a3)
{
  __int64 *v5; // rbx
  __int64 *v6; // rbx
  LPCWSTR *v7; // rcx
  int AlgorithmHandle; // eax
  unsigned int v10; // ebp
  BCRYPT_HANDLE v11; // rbp
  NTSTATUS Property; // esi
  __int64 v13; // r9
  void *v14; // rsi
  NTSTATUS v15; // eax
  int pbOutput; // [rsp+60h] [rbp+8h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp+10h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+78h] [rbp+20h]

  hObject = 0;
  pbOutput = 0;
  if ( (a2 & 1) != 0 )
    v5 = l_NonPagedCipherEntryCache;
  else
    v5 = l_PagedCipherEntryCache;
  v6 = &v5[2 * a1];
  if ( a1 >= g_dwCipherInfoTotalCount || (_mm_lfence(), (v7 = (LPCWSTR *)g_pCipherInfo[a1]) == 0) )
  {
    DebugTraceError(1168, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 4725);
    return 1168;
  }
  if ( *((_DWORD *)v6 + 3) )
    goto LABEL_6;
  AlgorithmHandle = GetAlgorithmHandle(*v7);
  v10 = AlgorithmHandle;
  if ( AlgorithmHandle < 0 )
  {
    DebugTraceError(
      (unsigned int)AlgorithmHandle,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      4739);
    return v10;
  }
  v11 = hObject;
  if ( a1 == 5 )
  {
    pcbResult = 0;
    Property = BCryptSetProperty(hObject, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
    if ( Property < 0 )
    {
      v13 = 4754;
LABEL_17:
      DebugTraceError(
        (unsigned int)Property,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v13);
      BCryptCloseAlgorithmProvider(v11, 0);
      return (unsigned int)Property;
    }
    Property = BCryptGetProperty(v11, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
    {
      v13 = 4768;
      goto LABEL_17;
    }
  }
  v14 = (void *)_InterlockedCompareExchange64(v6, (signed __int64)v11, 0);
  if ( v14 )
  {
    pcbResult = 0;
    BCryptCloseAlgorithmProvider(v11, 0);
    v15 = BCryptGetProperty(v14, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    Property = v15;
    if ( v15 < 0 )
    {
      DebugTraceError(
        (unsigned int)v15,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        4794);
      return (unsigned int)Property;
    }
  }
  *((_DWORD *)v6 + 2) = pbOutput;
  *((_DWORD *)v6 + 3) = 1;
LABEL_6:
  *(_QWORD *)a3 = *v6;
  *(_DWORD *)(a3 + 8) = *((_DWORD *)v6 + 2);
  return 0;
}

```

## disassembly

```asm
0x1800417a0  push    rbx
0x1800417a2  push    rsi
0x1800417a3  push    rdi
0x1800417a4  push    r14
0x1800417a6  sub     rsp, 38h
0x1800417aa  xor     r14d, r14d
0x1800417ad  mov     r9d, ecx
0x1800417b0  shl     r9, 4
0x1800417b4  lea     rax, cs:180000000h
0x1800417bb  mov     esi, ecx
0x1800417bd  mov     rdi, r8
0x1800417c0  mov     [rsp+58h+hObject], r14
0x1800417c5  mov     [rsp+58h+pbOutput], r14d
0x1800417ca  test    dl, 1
0x1800417cd  jnz     short loc_18004181F
0x1800417cf  lea     rbx, rva l_PagedCipherEntryCache[rax]
0x1800417d6  add     rbx, r9
0x1800417d9  cmp     esi, cs:g_dwCipherInfoTotalCount
0x1800417df  jnb     loc_180041866
0x1800417e5  lfence
0x1800417e8  mov     rcx, rva g_pCipherInfo[rax+rsi*8]
0x1800417f0  test    rcx, rcx
0x1800417f3  jz      short loc_180041866
0x1800417f5  mov     [rsp+58h+var_28], rbp
0x1800417fa  cmp     [rbx+0Ch], r14d
0x1800417fe  jz      short loc_180041828
0x180041800  mov     rax, [rbx]
0x180041803  mov     [rdi], rax
0x180041806  mov     eax, [rbx+8]
0x180041809  mov     [rdi+8], eax
0x18004180c  mov     eax, r14d
0x18004180f  mov     rbp, [rsp+58h+var_28]
0x180041814  add     rsp, 38h
0x180041818  pop     r14
0x18004181a  pop     rdi
0x18004181b  pop     rsi
0x18004181c  pop     rbx
0x18004181d  retn
0x18004181f  lea     rbx, rva l_NonPagedCipherEntryCache[rax]
0x180041826  jmp     short loc_1800417D6
0x180041828  mov     rcx, [rcx]; pszAlgId
0x18004182b  lea     r8, [rsp+58h+pbOutput]
0x180041830  mov     r9d, edx
0x180041833  lea     rdx, [rsp+58h+hObject]
0x180041838  call    GetAlgorithmHandle
0x18004183d  mov     ebp, eax
0x18004183f  test    eax, eax
0x180041841  jns     loc_1800A7CA8
0x180041847  mov     r9d, 1283h
0x18004184d  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041854  lea     rdx, aStatus; "Status"
0x18004185b  mov     ecx, eax
0x18004185d  call    DebugTraceError
0x180041862  mov     eax, ebp
0x180041864  jmp     short loc_18004180F
0x180041866  mov     r9d, 1275h
0x18004186c  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041873  lea     rdx, aStatus; "Status"
0x18004187a  mov     ecx, 490h
0x18004187f  call    DebugTraceError
0x180041884  mov     eax, 490h
0x180041889  jmp     short loc_180041814
0x1800a7ca8  mov     rbp, [rsp+58h+hObject]
0x1800a7cad  cmp     esi, 5
0x1800a7cb0  jnz     loc_1800A7D45
0x1800a7cb6  mov     r9d, 20h ; ' '; cbInput
0x1800a7cbc  mov     [rsp+58h+pcbResult], r14d
0x1800a7cc1  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x1800a7cc8  mov     [rsp+58h+dwFlags], r14d; dwFlags
0x1800a7ccd  lea     rdx, aChainingmode; "ChainingMode"
0x1800a7cd4  mov     rcx, rbp; hObject
0x1800a7cd7  call    BCryptSetProperty
0x1800a7cdc  mov     esi, eax
0x1800a7cde  test    eax, eax
0x1800a7ce0  jns     short loc_1800A7CEA
0x1800a7ce2  mov     r9d, 1292h
0x1800a7ce8  jmp     short loc_1800A7D1F
0x1800a7cea  lea     rax, [rsp+58h+pcbResult]
0x1800a7cef  mov     [rsp+58h+var_30], r14d; dwFlags
0x1800a7cf4  mov     r9d, 4; cbOutput
0x1800a7cfa  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x1800a7cff  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x1800a7d04  mov     rcx, rbp; hObject
0x1800a7d07  lea     rdx, aObjectlength; "ObjectLength"
0x1800a7d0e  call    BCryptGetProperty
0x1800a7d13  mov     esi, eax
0x1800a7d15  test    eax, eax
0x1800a7d17  jns     short loc_1800A7D45
0x1800a7d19  mov     r9d, 12A0h
0x1800a7d1f  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a7d26  mov     ecx, esi
0x1800a7d28  lea     rdx, aStatus; "Status"
0x1800a7d2f  call    DebugTraceError
0x1800a7d34  xor     edx, edx; dwFlags
0x1800a7d36  mov     rcx, rbp; hAlgorithm
0x1800a7d39  call    BCryptCloseAlgorithmProvider
0x1800a7d3e  mov     eax, esi
0x1800a7d40  jmp     loc_18004180F
0x1800a7d45  xor     eax, eax
0x1800a7d47  lock cmpxchg [rbx], rbp
0x1800a7d4c  mov     rsi, rax
0x1800a7d4f  jz      short loc_1800A7DAC
0x1800a7d51  xor     edx, edx; dwFlags
0x1800a7d53  mov     [rsp+58h+pcbResult], r14d
0x1800a7d58  mov     rcx, rbp; hAlgorithm
0x1800a7d5b  call    BCryptCloseAlgorithmProvider
0x1800a7d60  lea     rax, [rsp+58h+pcbResult]
0x1800a7d65  mov     [rsp+58h+var_30], r14d; dwFlags
0x1800a7d6a  mov     r9d, 4; cbOutput
0x1800a7d70  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x1800a7d75  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x1800a7d7a  mov     rcx, rsi; hObject
0x1800a7d7d  lea     rdx, aObjectlength; "ObjectLength"
0x1800a7d84  call    BCryptGetProperty
0x1800a7d89  mov     esi, eax
0x1800a7d8b  test    eax, eax
0x1800a7d8d  jns     short loc_1800A7DAC
0x1800a7d8f  mov     r9d, 12BAh
0x1800a7d95  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a7d9c  lea     rdx, aStatus; "Status"
0x1800a7da3  mov     ecx, eax
0x1800a7da5  call    DebugTraceError
0x1800a7daa  jmp     short loc_1800A7D3E
0x1800a7dac  mov     eax, [rsp+58h+pbOutput]
0x1800a7db0  mov     [rbx+8], eax
0x1800a7db3  mov     dword ptr [rbx+0Ch], 1
0x1800a7dba  jmp     loc_180041800
```
