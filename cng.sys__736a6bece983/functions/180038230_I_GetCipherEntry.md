# I_GetCipherEntry

- ea: `0x180038230`
- end: `0x18003831b`
- name: `I_GetCipherEntry`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800840cc`

## callees

- `0x1800023e0`
- `0x180003c70`
- `0x18000743c`
- `0x180038230`
- `0x18005a4d0`
- `0x180082598`

## string_xrefs

- `0x1800382dd`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800382fc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a2db1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a2e27`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

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
0x180038230  push    rbx
0x180038232  push    rsi
0x180038233  push    rdi
0x180038234  push    r14
0x180038236  sub     rsp, 38h
0x18003823a  xor     r14d, r14d
0x18003823d  mov     r9d, ecx
0x180038240  shl     r9, 4
0x180038244  lea     rax, cs:180000000h
0x18003824b  mov     esi, ecx
0x18003824d  mov     rdi, r8
0x180038250  mov     [rsp+58h+hObject], r14
0x180038255  mov     [rsp+58h+pbOutput], r14d
0x18003825a  test    dl, 1
0x18003825d  jnz     short loc_1800382AF
0x18003825f  lea     rbx, rva l_PagedCipherEntryCache[rax]
0x180038266  add     rbx, r9
0x180038269  cmp     esi, cs:g_dwCipherInfoTotalCount
0x18003826f  jnb     loc_1800382F6
0x180038275  lfence
0x180038278  mov     rcx, rva g_pCipherInfo[rax+rsi*8]
0x180038280  test    rcx, rcx
0x180038283  jz      short loc_1800382F6
0x180038285  mov     [rsp+58h+var_28], rbp
0x18003828a  cmp     [rbx+0Ch], r14d
0x18003828e  jz      short loc_1800382B8
0x180038290  mov     rax, [rbx]
0x180038293  mov     [rdi], rax
0x180038296  mov     eax, [rbx+8]
0x180038299  mov     [rdi+8], eax
0x18003829c  mov     eax, r14d
0x18003829f  mov     rbp, [rsp+58h+var_28]
0x1800382a4  add     rsp, 38h
0x1800382a8  pop     r14
0x1800382aa  pop     rdi
0x1800382ab  pop     rsi
0x1800382ac  pop     rbx
0x1800382ad  retn
0x1800382af  lea     rbx, rva l_NonPagedCipherEntryCache[rax]
0x1800382b6  jmp     short loc_180038266
0x1800382b8  mov     rcx, [rcx]; pszAlgId
0x1800382bb  lea     r8, [rsp+58h+pbOutput]
0x1800382c0  mov     r9d, edx
0x1800382c3  lea     rdx, [rsp+58h+hObject]
0x1800382c8  call    GetAlgorithmHandle
0x1800382cd  mov     ebp, eax
0x1800382cf  test    eax, eax
0x1800382d1  jns     loc_1800A2D3A
0x1800382d7  mov     r9d, 1283h
0x1800382dd  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800382e4  lea     rdx, aStatus; "Status"
0x1800382eb  mov     ecx, eax
0x1800382ed  call    DebugTraceError
0x1800382f2  mov     eax, ebp
0x1800382f4  jmp     short loc_18003829F
0x1800382f6  mov     r9d, 1275h
0x1800382fc  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180038303  lea     rdx, aStatus; "Status"
0x18003830a  mov     ecx, 490h
0x18003830f  call    DebugTraceError
0x180038314  mov     eax, 490h
0x180038319  jmp     short loc_1800382A4
0x1800a2d3a  mov     rbp, [rsp+58h+hObject]
0x1800a2d3f  cmp     esi, 5
0x1800a2d42  jnz     loc_1800A2DD7
0x1800a2d48  mov     r9d, 20h ; ' '; cbInput
0x1800a2d4e  mov     [rsp+58h+pcbResult], r14d
0x1800a2d53  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x1800a2d5a  mov     [rsp+58h+dwFlags], r14d; dwFlags
0x1800a2d5f  lea     rdx, aChainingmode; "ChainingMode"
0x1800a2d66  mov     rcx, rbp; hObject
0x1800a2d69  call    BCryptSetProperty
0x1800a2d6e  mov     esi, eax
0x1800a2d70  test    eax, eax
0x1800a2d72  jns     short loc_1800A2D7C
0x1800a2d74  mov     r9d, 1292h
0x1800a2d7a  jmp     short loc_1800A2DB1
0x1800a2d7c  lea     rax, [rsp+58h+pcbResult]
0x1800a2d81  mov     [rsp+58h+var_30], r14d; dwFlags
0x1800a2d86  mov     r9d, 4; cbOutput
0x1800a2d8c  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x1800a2d91  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x1800a2d96  mov     rcx, rbp; hObject
0x1800a2d99  lea     rdx, aObjectlength; "ObjectLength"
0x1800a2da0  call    BCryptGetProperty
0x1800a2da5  mov     esi, eax
0x1800a2da7  test    eax, eax
0x1800a2da9  jns     short loc_1800A2DD7
0x1800a2dab  mov     r9d, 12A0h
0x1800a2db1  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a2db8  mov     ecx, esi
0x1800a2dba  lea     rdx, aStatus; "Status"
0x1800a2dc1  call    DebugTraceError
0x1800a2dc6  xor     edx, edx; dwFlags
0x1800a2dc8  mov     rcx, rbp; hAlgorithm
0x1800a2dcb  call    BCryptCloseAlgorithmProvider
0x1800a2dd0  mov     eax, esi
0x1800a2dd2  jmp     loc_18003829F
0x1800a2dd7  xor     eax, eax
0x1800a2dd9  lock cmpxchg [rbx], rbp
0x1800a2dde  mov     rsi, rax
0x1800a2de1  jz      short loc_1800A2E3E
0x1800a2de3  xor     edx, edx; dwFlags
0x1800a2de5  mov     [rsp+58h+pcbResult], r14d
0x1800a2dea  mov     rcx, rbp; hAlgorithm
0x1800a2ded  call    BCryptCloseAlgorithmProvider
0x1800a2df2  lea     rax, [rsp+58h+pcbResult]
0x1800a2df7  mov     [rsp+58h+var_30], r14d; dwFlags
0x1800a2dfc  mov     r9d, 4; cbOutput
0x1800a2e02  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x1800a2e07  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x1800a2e0c  mov     rcx, rsi; hObject
0x1800a2e0f  lea     rdx, aObjectlength; "ObjectLength"
0x1800a2e16  call    BCryptGetProperty
0x1800a2e1b  mov     esi, eax
0x1800a2e1d  test    eax, eax
0x1800a2e1f  jns     short loc_1800A2E3E
0x1800a2e21  mov     r9d, 12BAh
0x1800a2e27  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a2e2e  lea     rdx, aStatus; "Status"
0x1800a2e35  mov     ecx, eax
0x1800a2e37  call    DebugTraceError
0x1800a2e3c  jmp     short loc_1800A2DD0
0x1800a2e3e  mov     eax, [rsp+58h+pbOutput]
0x1800a2e42  mov     [rbx+8], eax
0x1800a2e45  mov     dword ptr [rbx+0Ch], 1
0x1800a2e4c  jmp     loc_180038290
```
