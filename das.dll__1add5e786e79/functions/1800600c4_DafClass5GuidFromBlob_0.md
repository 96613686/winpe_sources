# DafClass5GuidFromBlob_0

- ea: `0x1800600c4`
- end: `0x180060359`
- name: `DafClass5GuidFromBlob_0`
- size: `661`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180060360`

## callees

- `0x18003bc80`
- `0x1800600c4`
- `0x18007e9d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060242`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800602fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060242`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800602fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060313`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060308`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060321`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060308`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060321`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006017f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060250`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006017f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060250`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006012a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006012a`
- `bcrypt!BCryptHashData` at `0x1800601ee`
- `bcrypt!BCryptHashData` at `0x180060207`
- `bcrypt!BCryptHashData` at `0x1800601ee`
- `bcrypt!BCryptHashData` at `0x180060207`
- `bcrypt!BCryptDestroyHash` at `0x1800602de`
- `bcrypt!BCryptDestroyHash` at `0x1800602de`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800602ef`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800602ef`
- `bcrypt!BCryptGetProperty` at `0x18006015e`
- `bcrypt!BCryptGetProperty` at `0x180060233`
- `bcrypt!BCryptGetProperty` at `0x18006015e`
- `bcrypt!BCryptGetProperty` at `0x180060233`
- `bcrypt!BCryptCreateHash` at `0x1800601af`
- `bcrypt!BCryptCreateHash` at `0x1800601af`
- `bcrypt!BCryptFinishHash` at `0x180060277`
- `bcrypt!BCryptFinishHash` at `0x180060277`

## pseudocode

```c
__int64 __fastcall DafClass5GuidFromBlob_0(__int128 *a1, UCHAR *a2, __int64 a3, _OWORD *a4)
{
  __int128 v4; // xmm0
  UCHAR *v8; // rsi
  UCHAR *v9; // rdi
  size_t v10; // r14
  NTSTATUS Property; // ebx
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  bool v14; // sf
  unsigned int v15; // ebx
  HANDLE v16; // rax
  __int16 v17; // ax
  HANDLE v18; // rax
  HANDLE v19; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-2Ch] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  UCHAR pbInput[16]; // [rsp+58h] [rbp-18h] BYREF

  v4 = *a1;
  phAlgorithm = 0;
  *(_OWORD *)pbInput = v4;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  *a4 = 0;
  pcbResult = 0;
  v8 = 0;
  v9 = 0;
  v10 = 16;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v12 = *(_DWORD *)pbOutput;
      ProcessHeap = GetProcessHeap();
      v8 = (UCHAR *)HeapAlloc(ProcessHeap, 0, v12);
      if ( !v8 )
      {
LABEL_10:
        Property = -1073741801;
        goto LABEL_17;
      }
      Property = BCryptCreateHash(phAlgorithm, &phHash, v8, *(ULONG *)pbOutput, 0, 0, 0);
      if ( Property >= 0 )
      {
        *(_DWORD *)pbInput = _byteswap_ulong(*(_DWORD *)a1);
        *(_WORD *)&pbInput[4] = __ROR2__(*((_WORD *)a1 + 2), 8);
        *(_WORD *)&pbInput[6] = __ROR2__(*((_WORD *)a1 + 3), 8);
        Property = BCryptHashData(phHash, pbInput, 0x10u, 0);
        if ( Property >= 0 )
          Property = BCryptHashData(phHash, a2, 0x10u, 0);
      }
    }
  }
  v14 = Property < 0;
  if ( Property )
  {
LABEL_12:
    if ( v14 )
      goto LABEL_17;
    goto LABEL_13;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property )
  {
    v14 = Property < 0;
    goto LABEL_12;
  }
  v15 = *(_DWORD *)pbOutput;
  v16 = GetProcessHeap();
  v9 = (UCHAR *)HeapAlloc(v16, 0, v15);
  if ( !v9 )
    goto LABEL_10;
LABEL_13:
  Property = BCryptFinishHash(phHash, v9, *(ULONG *)pbOutput, 0);
  if ( Property >= 0 )
  {
    if ( *(_DWORD *)pbOutput < 0x10u )
      v10 = *(unsigned int *)pbOutput;
    memcpy_0(a4, v9, v10);
    *(_DWORD *)a4 = _byteswap_ulong(*(_DWORD *)a4);
    *((_WORD *)a4 + 2) = __ROR2__(*((_WORD *)a4 + 2), 8);
    v17 = *((_WORD *)a4 + 3);
    *((_BYTE *)a4 + 8) &= 0x3Fu;
    *((_BYTE *)a4 + 8) |= 0x80u;
    *((_WORD *)a4 + 3) = __ROR2__(v17, 8) & 0xFFF | 0x5000;
  }
LABEL_17:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v8 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v8);
  }
  if ( v9 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v9);
  }
  if ( Property < 0 )
    return (unsigned int)(Property | 0x10000000);
  else
    return 0;
}

```

## disassembly

```asm
0x1800600c4  mov     [rsp-38h+arg_10], rbx
0x1800600c9  push    rbp
0x1800600ca  push    rsi
0x1800600cb  push    rdi
0x1800600cc  push    r12
0x1800600ce  push    r13
0x1800600d0  push    r14
0x1800600d2  push    r15
0x1800600d4  mov     rbp, rsp
0x1800600d7  sub     rsp, 70h
0x1800600db  mov     rax, cs:__security_cookie
0x1800600e2  xor     rax, rsp
0x1800600e5  mov     [rbp+var_8], rax
0x1800600e9  movups  xmm0, xmmword ptr [rcx]
0x1800600ec  xor     eax, eax
0x1800600ee  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800600f5  mov     r15, r9
0x1800600f8  mov     [rbp+phAlgorithm], rax
0x1800600fc  movdqu  xmmword ptr [rbp+pbInput], xmm0
0x180060101  mov     [rbp+phHash], rax
0x180060105  mov     r13, rdx
0x180060108  xorps   xmm0, xmm0
0x18006010b  mov     dword ptr [rbp+pbOutput], eax
0x18006010e  movups  xmmword ptr [r9], xmm0
0x180060112  mov     r12, rcx
0x180060115  mov     [rbp+var_2C], eax
0x180060118  xor     r9d, r9d; dwFlags
0x18006011b  lea     rdx, pszAlgId; "SHA1"
0x180060122  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180060126  mov     esi, eax
0x180060128  mov     edi, eax
0x18006012a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180060130  lea     r14d, [rdi+10h]
0x180060134  mov     ebx, eax
0x180060136  test    eax, eax
0x180060138  js      loc_18006020F
0x18006013e  mov     rcx, [rbp+phAlgorithm]; hObject
0x180060142  lea     rax, [rbp+var_2C]
0x180060146  mov     [rsp+70h+dwFlags], esi; dwFlags
0x18006014a  lea     r9d, [rdi+4]; cbOutput
0x18006014e  lea     r8, [rbp+pbOutput]; pbOutput
0x180060152  mov     [rsp+70h+pcbResult], rax; pcbResult
0x180060157  lea     rdx, pszProperty; "ObjectLength"
0x18006015e  call    cs:__imp_BCryptGetProperty
0x180060164  mov     ebx, eax
0x180060166  test    eax, eax
0x180060168  js      loc_18006020F
0x18006016e  mov     ebx, dword ptr [rbp+pbOutput]
0x180060171  call    cs:__imp_GetProcessHeap
0x180060177  mov     r8d, ebx; dwBytes
0x18006017a  xor     edx, edx; dwFlags
0x18006017c  mov     rcx, rax; hHeap
0x18006017f  call    cs:__imp_HeapAlloc
0x180060185  mov     rsi, rax
0x180060188  xor     eax, eax
0x18006018a  test    rsi, rsi
0x18006018d  jz      loc_18006025E
0x180060193  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x180060197  lea     rdx, [rbp+phHash]; phHash
0x18006019b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18006019f  mov     r8, rsi; pbHashObject
0x1800601a2  mov     [rsp+70h+var_40], eax; dwFlags
0x1800601a6  mov     [rsp+70h+dwFlags], eax; cbSecret
0x1800601aa  mov     [rsp+70h+pcbResult], rax; pbSecret
0x1800601af  call    cs:__imp_BCryptCreateHash
0x1800601b5  mov     ebx, eax
0x1800601b7  test    eax, eax
0x1800601b9  js      short loc_18006020F
0x1800601bb  mov     eax, [r12]
0x1800601bf  lea     rdx, [rbp+pbInput]; pbInput
0x1800601c3  mov     rcx, [rbp+phHash]; hHash
0x1800601c7  xor     r9d, r9d; dwFlags
0x1800601ca  bswap   eax
0x1800601cc  mov     dword ptr [rbp+pbInput], eax
0x1800601cf  mov     r8d, r14d; cbInput
0x1800601d2  movzx   eax, word ptr [r12+4]
0x1800601d8  ror     ax, 8
0x1800601dc  mov     word ptr [rbp+pbInput+4], ax
0x1800601e0  movzx   eax, word ptr [r12+6]
0x1800601e6  ror     ax, 8
0x1800601ea  mov     word ptr [rbp+pbInput+6], ax
0x1800601ee  call    cs:__imp_BCryptHashData
0x1800601f4  mov     ebx, eax
0x1800601f6  test    eax, eax
0x1800601f8  js      short loc_18006020F
0x1800601fa  mov     rcx, [rbp+phHash]; hHash
0x1800601fe  xor     r9d, r9d; dwFlags
0x180060201  mov     r8d, r14d; cbInput
0x180060204  mov     rdx, r13; pbInput
0x180060207  call    cs:__imp_BCryptHashData
0x18006020d  mov     ebx, eax
0x18006020f  test    ebx, ebx
0x180060211  jnz     short loc_180060267
0x180060213  mov     rcx, [rbp+phAlgorithm]; hObject
0x180060217  lea     rax, [rbp+var_2C]
0x18006021b  mov     [rsp+70h+dwFlags], edi; dwFlags
0x18006021f  lea     r9d, [rbx+4]; cbOutput
0x180060223  lea     r8, [rbp+pbOutput]; pbOutput
0x180060227  mov     [rsp+70h+pcbResult], rax; pcbResult
0x18006022c  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180060233  call    cs:__imp_BCryptGetProperty
0x180060239  mov     ebx, eax
0x18006023b  test    eax, eax
0x18006023d  jnz     short loc_180060265
0x18006023f  mov     ebx, dword ptr [rbp+pbOutput]
0x180060242  call    cs:__imp_GetProcessHeap
0x180060248  mov     r8d, ebx; dwBytes
0x18006024b  xor     edx, edx; dwFlags
0x18006024d  mov     rcx, rax; hHeap
0x180060250  call    cs:__imp_HeapAlloc
0x180060256  mov     rdi, rax
0x180060259  test    rax, rax
0x18006025c  jnz     short loc_180060269
0x18006025e  mov     ebx, 0C0000017h
0x180060263  jmp     short loc_1800602D5
0x180060265  test    ebx, ebx
0x180060267  js      short loc_1800602D5
0x180060269  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x18006026d  xor     r9d, r9d; dwFlags
0x180060270  mov     rcx, [rbp+phHash]; hHash
0x180060274  mov     rdx, rdi; pbOutput
0x180060277  call    cs:__imp_BCryptFinishHash
0x18006027d  mov     ebx, eax
0x18006027f  test    eax, eax
0x180060281  js      short loc_1800602D5
0x180060283  cmp     dword ptr [rbp+pbOutput], r14d
0x180060287  jnb     short loc_18006028D
0x180060289  mov     r14d, dword ptr [rbp+pbOutput]
0x18006028d  mov     r8, r14; Size
0x180060290  mov     rdx, rdi; Src
0x180060293  mov     rcx, r15; void *
0x180060296  call    memcpy_0
0x18006029b  mov     eax, [r15]
0x18006029e  mov     ecx, 0FFFh
0x1800602a3  bswap   eax
0x1800602a5  mov     [r15], eax
0x1800602a8  movzx   eax, word ptr [r15+4]
0x1800602ad  ror     ax, 8
0x1800602b1  mov     [r15+4], ax
0x1800602b6  movzx   eax, word ptr [r15+6]
0x1800602bb  and     byte ptr [r15+8], 3Fh
0x1800602c0  ror     ax, 8
0x1800602c4  and     ax, cx
0x1800602c7  or      ax, 5000h
0x1800602cb  or      byte ptr [r15+8], 80h
0x1800602d0  mov     [r15+6], ax
0x1800602d5  mov     rcx, [rbp+phHash]; hHash
0x1800602d9  test    rcx, rcx
0x1800602dc  jz      short loc_1800602E4
0x1800602de  call    cs:__imp_BCryptDestroyHash
0x1800602e4  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800602e8  test    rcx, rcx
0x1800602eb  jz      short loc_1800602F5
0x1800602ed  xor     edx, edx; dwFlags
0x1800602ef  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800602f5  test    rsi, rsi
0x1800602f8  jz      short loc_18006030E
0x1800602fa  call    cs:__imp_GetProcessHeap
0x180060300  mov     r8, rsi; lpMem
0x180060303  xor     edx, edx; dwFlags
0x180060305  mov     rcx, rax; hHeap
0x180060308  call    cs:__imp_HeapFree
0x18006030e  test    rdi, rdi
0x180060311  jz      short loc_180060327
0x180060313  call    cs:__imp_GetProcessHeap
0x180060319  mov     r8, rdi; lpMem
0x18006031c  xor     edx, edx; dwFlags
0x18006031e  mov     rcx, rax; hHeap
0x180060321  call    cs:__imp_HeapFree
0x180060327  test    ebx, ebx
0x180060329  js      short loc_18006032F
0x18006032b  xor     ebx, ebx
0x18006032d  jmp     short loc_180060333
0x18006032f  bts     ebx, 1Ch
0x180060333  mov     eax, ebx
0x180060335  mov     rcx, [rbp+var_8]
0x180060339  xor     rcx, rsp; StackCookie
0x18006033c  call    __security_check_cookie
0x180060341  mov     rbx, [rsp+70h+arg_10]
0x180060349  add     rsp, 70h
0x18006034d  pop     r15
0x18006034f  pop     r14
0x180060351  pop     r13
0x180060353  pop     r12
0x180060355  pop     rdi
0x180060356  pop     rsi
0x180060357  pop     rbp
0x180060358  retn
```
