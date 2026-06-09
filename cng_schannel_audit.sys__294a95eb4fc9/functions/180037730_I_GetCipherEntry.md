# I_GetCipherEntry

- ea: `0x180037730`
- end: `0x18003781b`
- name: `I_GetCipherEntry`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800830dc`

## callees

- `0x1800023e0`
- `0x180003c70`
- `0x18000743c`
- `0x180037730`
- `0x180059be0`
- `0x1800815a8`

## string_xrefs

- `0x1800377dd`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800377fc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a0f81`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800a0ff7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

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
0x180037730  push    rbx
0x180037732  push    rsi
0x180037733  push    rdi
0x180037734  push    r14
0x180037736  sub     rsp, 38h
0x18003773a  xor     r14d, r14d
0x18003773d  mov     r9d, ecx
0x180037740  shl     r9, 4
0x180037744  lea     rax, cs:180000000h
0x18003774b  mov     esi, ecx
0x18003774d  mov     rdi, r8
0x180037750  mov     [rsp+58h+hObject], r14
0x180037755  mov     [rsp+58h+pbOutput], r14d
0x18003775a  test    dl, 1
0x18003775d  jnz     short loc_1800377AF
0x18003775f  lea     rbx, rva l_PagedCipherEntryCache[rax]
0x180037766  add     rbx, r9
0x180037769  cmp     esi, cs:g_dwCipherInfoTotalCount
0x18003776f  jnb     loc_1800377F6
0x180037775  lfence
0x180037778  mov     rcx, rva g_pCipherInfo[rax+rsi*8]
0x180037780  test    rcx, rcx
0x180037783  jz      short loc_1800377F6
0x180037785  mov     [rsp+58h+var_28], rbp
0x18003778a  cmp     [rbx+0Ch], r14d
0x18003778e  jz      short loc_1800377B8
0x180037790  mov     rax, [rbx]
0x180037793  mov     [rdi], rax
0x180037796  mov     eax, [rbx+8]
0x180037799  mov     [rdi+8], eax
0x18003779c  mov     eax, r14d
0x18003779f  mov     rbp, [rsp+58h+var_28]
0x1800377a4  add     rsp, 38h
0x1800377a8  pop     r14
0x1800377aa  pop     rdi
0x1800377ab  pop     rsi
0x1800377ac  pop     rbx
0x1800377ad  retn
0x1800377af  lea     rbx, rva l_NonPagedCipherEntryCache[rax]
0x1800377b6  jmp     short loc_180037766
0x1800377b8  mov     rcx, [rcx]; pszAlgId
0x1800377bb  lea     r8, [rsp+58h+pbOutput]
0x1800377c0  mov     r9d, edx
0x1800377c3  lea     rdx, [rsp+58h+hObject]
0x1800377c8  call    GetAlgorithmHandle
0x1800377cd  mov     ebp, eax
0x1800377cf  test    eax, eax
0x1800377d1  jns     loc_1800A0F0A
0x1800377d7  mov     r9d, 1283h
0x1800377dd  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800377e4  lea     rdx, aStatus; "Status"
0x1800377eb  mov     ecx, eax
0x1800377ed  call    DebugTraceError
0x1800377f2  mov     eax, ebp
0x1800377f4  jmp     short loc_18003779F
0x1800377f6  mov     r9d, 1275h
0x1800377fc  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180037803  lea     rdx, aStatus; "Status"
0x18003780a  mov     ecx, 490h
0x18003780f  call    DebugTraceError
0x180037814  mov     eax, 490h
0x180037819  jmp     short loc_1800377A4
0x1800a0f0a  mov     rbp, [rsp+58h+hObject]
0x1800a0f0f  cmp     esi, 5
0x1800a0f12  jnz     loc_1800A0FA7
0x1800a0f18  mov     r9d, 20h ; ' '; cbInput
0x1800a0f1e  mov     [rsp+58h+pcbResult], r14d
0x1800a0f23  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x1800a0f2a  mov     [rsp+58h+dwFlags], r14d; dwFlags
0x1800a0f2f  lea     rdx, aChainingmode; "ChainingMode"
0x1800a0f36  mov     rcx, rbp; hObject
0x1800a0f39  call    BCryptSetProperty
0x1800a0f3e  mov     esi, eax
0x1800a0f40  test    eax, eax
0x1800a0f42  jns     short loc_1800A0F4C
0x1800a0f44  mov     r9d, 1292h
0x1800a0f4a  jmp     short loc_1800A0F81
0x1800a0f4c  lea     rax, [rsp+58h+pcbResult]
0x1800a0f51  mov     [rsp+58h+var_30], r14d; dwFlags
0x1800a0f56  mov     r9d, 4; cbOutput
0x1800a0f5c  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x1800a0f61  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x1800a0f66  mov     rcx, rbp; hObject
0x1800a0f69  lea     rdx, aObjectlength; "ObjectLength"
0x1800a0f70  call    BCryptGetProperty
0x1800a0f75  mov     esi, eax
0x1800a0f77  test    eax, eax
0x1800a0f79  jns     short loc_1800A0FA7
0x1800a0f7b  mov     r9d, 12A0h
0x1800a0f81  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a0f88  mov     ecx, esi
0x1800a0f8a  lea     rdx, aStatus; "Status"
0x1800a0f91  call    DebugTraceError
0x1800a0f96  xor     edx, edx; dwFlags
0x1800a0f98  mov     rcx, rbp; hAlgorithm
0x1800a0f9b  call    BCryptCloseAlgorithmProvider
0x1800a0fa0  mov     eax, esi
0x1800a0fa2  jmp     loc_18003779F
0x1800a0fa7  xor     eax, eax
0x1800a0fa9  lock cmpxchg [rbx], rbp
0x1800a0fae  mov     rsi, rax
0x1800a0fb1  jz      short loc_1800A100E
0x1800a0fb3  xor     edx, edx; dwFlags
0x1800a0fb5  mov     [rsp+58h+pcbResult], r14d
0x1800a0fba  mov     rcx, rbp; hAlgorithm
0x1800a0fbd  call    BCryptCloseAlgorithmProvider
0x1800a0fc2  lea     rax, [rsp+58h+pcbResult]
0x1800a0fc7  mov     [rsp+58h+var_30], r14d; dwFlags
0x1800a0fcc  mov     r9d, 4; cbOutput
0x1800a0fd2  mov     qword ptr [rsp+58h+dwFlags], rax; pcbResult
0x1800a0fd7  lea     r8, [rsp+58h+pbOutput]; pbOutput
0x1800a0fdc  mov     rcx, rsi; hObject
0x1800a0fdf  lea     rdx, aObjectlength; "ObjectLength"
0x1800a0fe6  call    BCryptGetProperty
0x1800a0feb  mov     esi, eax
0x1800a0fed  test    eax, eax
0x1800a0fef  jns     short loc_1800A100E
0x1800a0ff1  mov     r9d, 12BAh
0x1800a0ff7  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a0ffe  lea     rdx, aStatus; "Status"
0x1800a1005  mov     ecx, eax
0x1800a1007  call    DebugTraceError
0x1800a100c  jmp     short loc_1800A0FA0
0x1800a100e  mov     eax, [rsp+58h+pbOutput]
0x1800a1012  mov     [rbx+8], eax
0x1800a1015  mov     dword ptr [rbx+0Ch], 1
0x1800a101c  jmp     loc_180037790
```
