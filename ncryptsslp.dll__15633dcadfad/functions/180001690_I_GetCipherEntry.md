# I_GetCipherEntry

- ea: `0x180001690`
- end: `0x180001928`
- name: `I_GetCipherEntry`
- size: `664`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180006b60`

## callees

- `0x180001690`
- `0x180001de8`
- `0x18000b594`
- `0x18000b654`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x1800017b3`
- `bcrypt!BCryptSetProperty` at `0x1800017b3`
- `bcrypt!BCryptGetProperty` at `0x1800017e7`
- `bcrypt!BCryptGetProperty` at `0x180001846`
- `bcrypt!BCryptGetProperty` at `0x1800017e7`
- `bcrypt!BCryptGetProperty` at `0x180001846`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000181c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800018b8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000191d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000181c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800018b8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000191d`

## string_xrefs

- `0x18000171b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180001858`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000188f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180001903`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall I_GetCipherEntry(unsigned int a1, char a2, __int64 a3)
{
  __int64 *v5; // rbx
  __int64 *v6; // rbx
  LPCWSTR *v7; // rcx
  unsigned int AlgorithmHandle; // edi
  char v10; // dl
  int v11; // r8d
  BCRYPT_HANDLE v12; // r14
  NTSTATUS v13; // eax
  char v14; // dl
  int v15; // r8d
  void *v16; // rdi
  NTSTATUS Property; // eax
  int pbOutput; // [rsp+70h] [rbp+8h] BYREF
  ULONG pcbResult; // [rsp+78h] [rbp+10h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+88h] [rbp+20h] BYREF

  hObject = 0;
  pbOutput = 0;
  if ( (a2 & 1) != 0 )
    v5 = l_NonPagedCipherEntryCache;
  else
    v5 = l_PagedCipherEntryCache;
  v6 = &v5[2 * a1];
  if ( a1 >= g_dwCipherInfoTotalCount || (_mm_lfence(), (v7 = (LPCWSTR *)g_pCipherInfo[a1]) == 0) )
  {
    AlgorithmHandle = 1168;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        144,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        117);
    return AlgorithmHandle;
  }
  if ( *((_DWORD *)v6 + 3) )
  {
LABEL_10:
    AlgorithmHandle = 0;
    *(_QWORD *)a3 = *v6;
    *(_DWORD *)(a3 + 8) = *((_DWORD *)v6 + 2);
    return AlgorithmHandle;
  }
  AlgorithmHandle = GetAlgorithmHandle(*v7, &hObject, (UCHAR *)&pbOutput, a2);
  if ( (AlgorithmHandle & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v11,
        (unsigned int)"Status",
        AlgorithmHandle,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        131);
  }
  else
  {
    v12 = hObject;
    if ( a1 != 5 )
      goto LABEL_16;
    pcbResult = 0;
    v13 = BCryptSetProperty(hObject, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
    AlgorithmHandle = v13;
    if ( v13 < 0 )
    {
      DebugTraceError(
        (unsigned int)v13,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        4754);
      BCryptCloseAlgorithmProvider(v12, 0);
      return AlgorithmHandle;
    }
    AlgorithmHandle = BCryptGetProperty(v12, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( (AlgorithmHandle & 0x80000000) == 0 )
    {
LABEL_16:
      v16 = (void *)_InterlockedCompareExchange64(v6, (signed __int64)v12, 0);
      if ( v16 )
      {
        pcbResult = 0;
        BCryptCloseAlgorithmProvider(v12, 0);
        Property = BCryptGetProperty(v16, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
        AlgorithmHandle = Property;
        if ( Property < 0 )
        {
          DebugTraceError(
            (unsigned int)Property,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            4794);
          return AlgorithmHandle;
        }
      }
      *((_DWORD *)v6 + 2) = pbOutput;
      *((_DWORD *)v6 + 3) = 1;
      goto LABEL_10;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v15,
        (unsigned int)"Status",
        AlgorithmHandle,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        160);
    BCryptCloseAlgorithmProvider(v12, 0);
  }
  return AlgorithmHandle;
}

```

## disassembly

```asm
0x180001690  push    rbx
0x180001692  push    rbp
0x180001693  push    rsi
0x180001694  push    rdi
0x180001695  push    r15
0x180001697  sub     rsp, 40h
0x18000169b  xor     r15d, r15d
0x18000169e  mov     r9d, ecx
0x1800016a1  shl     r9, 4
0x1800016a5  lea     rax, __ImageBase
0x1800016ac  mov     ebp, ecx
0x1800016ae  mov     rsi, r8
0x1800016b1  mov     [rsp+68h+hObject], r15
0x1800016b9  mov     [rsp+68h+pbOutput], r15d
0x1800016be  test    dl, 1
0x1800016c1  jnz     loc_1800018F1
0x1800016c7  lea     rbx, rva l_PagedCipherEntryCache[rax]
0x1800016ce  add     rbx, r9
0x1800016d1  mov     [rsp+68h+arg_10], r14
0x1800016d9  cmp     ebp, cs:g_dwCipherInfoTotalCount
0x1800016df  jnb     short loc_1800016F1
0x1800016e1  lfence
0x1800016e4  mov     rcx, rva g_pCipherInfo[rax+rbp*8]
0x1800016ec  test    rcx, rcx
0x1800016ef  jnz     short loc_180001739
0x1800016f1  mov     edi, 490h
0x1800016f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016fd  lea     rax, WPP_GLOBAL_Control
0x180001704  cmp     rcx, rax
0x180001707  jz      short loc_18000174E
0x180001709  test    byte ptr [rcx+1Ch], 1
0x18000170d  jz      short loc_18000174E
0x18000170f  mov     [rsp+68h+var_38], 1275h
0x180001717  mov     rcx, [rcx+10h]
0x18000171b  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001722  mov     qword ptr [rsp+68h+var_40], rax
0x180001727  lea     r9, aStatus; "Status"
0x18000172e  mov     [rsp+68h+dwFlags], edi
0x180001732  call    WPP_SF_sDsd
0x180001737  jmp     short loc_18000174E
0x180001739  cmp     [rbx+0Ch], r15d
0x18000173d  jz      short loc_180001763
0x18000173f  mov     rax, [rbx]
0x180001742  mov     edi, r15d
0x180001745  mov     [rsi], rax
0x180001748  mov     eax, [rbx+8]
0x18000174b  mov     [rsi+8], eax
0x18000174e  mov     r14, [rsp+68h+arg_10]
0x180001756  mov     eax, edi
0x180001758  add     rsp, 40h
0x18000175c  pop     r15
0x18000175e  pop     rdi
0x18000175f  pop     rsi
0x180001760  pop     rbp
0x180001761  pop     rbx
0x180001762  retn
0x180001763  mov     rcx, [rcx]; pszAlgId
0x180001766  lea     r8, [rsp+68h+pbOutput]
0x18000176b  mov     r9d, edx
0x18000176e  lea     rdx, [rsp+68h+hObject]
0x180001776  call    GetAlgorithmHandle
0x18000177b  mov     edi, eax
0x18000177d  test    eax, eax
0x18000177f  js      loc_1800018C3
0x180001785  mov     r14, [rsp+68h+hObject]
0x18000178d  cmp     ebp, 5
0x180001790  jnz     short loc_1800017F3
0x180001792  mov     r9d, 20h ; ' '; cbInput
0x180001798  mov     [rsp+68h+pcbResult], r15d
0x18000179d  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x1800017a4  mov     [rsp+68h+dwFlags], r15d; dwFlags
0x1800017a9  lea     rdx, pszProperty; "ChainingMode"
0x1800017b0  mov     rcx, r14; hObject
0x1800017b3  call    cs:__imp_BCryptSetProperty
0x1800017b9  mov     edi, eax
0x1800017bb  test    eax, eax
0x1800017bd  js      loc_1800018FD
0x1800017c3  lea     rax, [rsp+68h+pcbResult]
0x1800017c8  mov     [rsp+68h+var_40], r15d; dwFlags
0x1800017cd  mov     r9d, 4; cbOutput
0x1800017d3  mov     qword ptr [rsp+68h+dwFlags], rax; pcbResult
0x1800017d8  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x1800017dd  mov     rcx, r14; hObject
0x1800017e0  lea     rdx, aObjectlength; "ObjectLength"
0x1800017e7  call    cs:__imp_BCryptGetProperty
0x1800017ed  mov     edi, eax
0x1800017ef  test    eax, eax
0x1800017f1  js      short loc_180001872
0x1800017f3  xor     eax, eax
0x1800017f5  lock cmpxchg [rbx], r14
0x1800017fa  mov     rdi, rax
0x1800017fd  jnz     short loc_180001812
0x1800017ff  mov     eax, [rsp+68h+pbOutput]
0x180001803  mov     [rbx+8], eax
0x180001806  mov     dword ptr [rbx+0Ch], 1
0x18000180d  jmp     loc_18000173F
0x180001812  xor     edx, edx; dwFlags
0x180001814  mov     [rsp+68h+pcbResult], r15d
0x180001819  mov     rcx, r14; hAlgorithm
0x18000181c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180001822  lea     rax, [rsp+68h+pcbResult]
0x180001827  mov     [rsp+68h+var_40], r15d; dwFlags
0x18000182c  mov     r9d, 4; cbOutput
0x180001832  mov     qword ptr [rsp+68h+dwFlags], rax; pcbResult
0x180001837  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x18000183c  mov     rcx, rdi; hObject
0x18000183f  lea     rdx, aObjectlength; "ObjectLength"
0x180001846  call    cs:__imp_BCryptGetProperty
0x18000184c  mov     edi, eax
0x18000184e  test    eax, eax
0x180001850  jns     short loc_1800017FF
0x180001852  mov     r9d, 12BAh
0x180001858  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000185f  lea     rdx, aStatus; "Status"
0x180001866  mov     ecx, eax
0x180001868  call    DebugTraceError
0x18000186d  jmp     loc_18000174E
0x180001872  mov     rcx, cs:WPP_GLOBAL_Control
0x180001879  lea     rax, WPP_GLOBAL_Control
0x180001880  cmp     rcx, rax
0x180001883  jz      short loc_1800018B3
0x180001885  test    byte ptr [rcx+1Ch], 1
0x180001889  jz      short loc_1800018B3
0x18000188b  mov     rcx, [rcx+10h]
0x18000188f  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001896  mov     [rsp+68h+var_38], 12A0h
0x18000189e  lea     r9, aStatus; "Status"
0x1800018a5  mov     qword ptr [rsp+68h+var_40], rax
0x1800018aa  mov     [rsp+68h+dwFlags], edi
0x1800018ae  call    WPP_SF_sDsd
0x1800018b3  xor     edx, edx; dwFlags
0x1800018b5  mov     rcx, r14; hAlgorithm
0x1800018b8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800018be  jmp     loc_18000174E
0x1800018c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018ca  lea     rax, WPP_GLOBAL_Control
0x1800018d1  cmp     rcx, rax
0x1800018d4  jz      loc_18000174E
0x1800018da  test    byte ptr [rcx+1Ch], 1
0x1800018de  jz      loc_18000174E
0x1800018e4  mov     [rsp+68h+var_38], 1283h
0x1800018ec  jmp     loc_180001717
0x1800018f1  lea     rbx, rva l_NonPagedCipherEntryCache[rax]
0x1800018f8  jmp     loc_1800016CE
0x1800018fd  mov     r9d, 1292h
0x180001903  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000190a  lea     rdx, aStatus; "Status"
0x180001911  mov     ecx, eax
0x180001913  call    DebugTraceError
0x180001918  xor     edx, edx; dwFlags
0x18000191a  mov     rcx, r14; hAlgorithm
0x18000191d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180001923  jmp     loc_18000174E
```
