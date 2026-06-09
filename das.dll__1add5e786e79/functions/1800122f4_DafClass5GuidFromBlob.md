# DafClass5GuidFromBlob

- ea: `0x1800122f4`
- end: `0x180012585`
- name: `DafClass5GuidFromBlob`
- size: `657`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800133c4`
- `0x180032484`
- `0x18005c3bc`

## callees

- `0x1800122f4`
- `0x18003bc80`
- `0x18007e9d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001247a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001252a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012543`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001247a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001252a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012543`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012551`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800123b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012488`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800123b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012488`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180012361`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180012361`
- `bcrypt!BCryptHashData` at `0x180012425`
- `bcrypt!BCryptHashData` at `0x18001243f`
- `bcrypt!BCryptHashData` at `0x180012425`
- `bcrypt!BCryptHashData` at `0x18001243f`
- `bcrypt!BCryptDestroyHash` at `0x18001250e`
- `bcrypt!BCryptDestroyHash` at `0x18001250e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001251f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001251f`
- `bcrypt!BCryptGetProperty` at `0x180012395`
- `bcrypt!BCryptGetProperty` at `0x18001246b`
- `bcrypt!BCryptGetProperty` at `0x180012395`
- `bcrypt!BCryptGetProperty` at `0x18001246b`
- `bcrypt!BCryptCreateHash` at `0x1800123e6`
- `bcrypt!BCryptCreateHash` at `0x1800123e6`
- `bcrypt!BCryptFinishHash` at `0x1800124af`
- `bcrypt!BCryptFinishHash` at `0x1800124af`

## pseudocode

```c
__int64 __fastcall DafClass5GuidFromBlob(__int128 *a1, UCHAR *a2, ULONG a3, _OWORD *a4)
{
  __int128 v4; // xmm0
  UCHAR *v8; // r14
  UCHAR *v9; // rdi
  size_t v10; // r15
  NTSTATUS Property; // ebx
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  bool v14; // sf
  unsigned int v15; // ebx
  HANDLE v16; // rax
  __int16 v17; // ax
  HANDLE v18; // rax
  HANDLE v19; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-29h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-25h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-21h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-19h] BYREF
  ULONG cbInput; // [rsp+58h] [rbp-11h]
  UCHAR pbInput[16]; // [rsp+60h] [rbp-9h] BYREF

  v4 = *a1;
  cbInput = a3;
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
          Property = BCryptHashData(phHash, a2, cbInput, 0);
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
0x1800122f4  push    rbp
0x1800122f6  push    rbx
0x1800122f7  push    rsi
0x1800122f8  push    rdi
0x1800122f9  push    r12
0x1800122fb  push    r13
0x1800122fd  push    r14
0x1800122ff  push    r15
0x180012301  lea     rbp, [rsp-1Fh]
0x180012306  sub     rsp, 88h
0x18001230d  mov     rax, cs:__security_cookie
0x180012314  xor     rax, rsp
0x180012317  mov     [rbp+57h+var_50], rax
0x18001231b  movups  xmm0, xmmword ptr [rcx]
0x18001231e  xor     eax, eax
0x180012320  mov     [rbp+57h+cbInput], r8d
0x180012324  mov     rsi, r9
0x180012327  mov     [rbp+57h+phAlgorithm], rax
0x18001232b  movdqu  xmmword ptr [rbp+57h+pbInput], xmm0
0x180012330  mov     [rbp+57h+phHash], rax
0x180012334  mov     r13, rdx
0x180012337  xorps   xmm0, xmm0
0x18001233a  mov     dword ptr [rbp+57h+pbOutput], eax
0x18001233d  movups  xmmword ptr [r9], xmm0
0x180012341  mov     r12, rcx
0x180012344  mov     [rbp+57h+var_7C], eax
0x180012347  xor     r9d, r9d; dwFlags
0x18001234a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180012351  lea     rdx, pszAlgId; "SHA1"
0x180012358  mov     r14d, eax
0x18001235b  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18001235f  mov     edi, eax
0x180012361  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180012367  lea     r15d, [rdi+10h]
0x18001236b  mov     ebx, eax
0x18001236d  test    eax, eax
0x18001236f  js      loc_180012447
0x180012375  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180012379  lea     rax, [rbp+57h+var_7C]
0x18001237d  mov     [rsp+0C0h+dwFlags], edi; dwFlags
0x180012381  lea     r9d, [rdi+4]; cbOutput
0x180012385  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180012389  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18001238e  lea     rdx, pszProperty; "ObjectLength"
0x180012395  call    cs:__imp_BCryptGetProperty
0x18001239b  mov     ebx, eax
0x18001239d  test    eax, eax
0x18001239f  js      loc_180012447
0x1800123a5  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x1800123a8  call    cs:__imp_GetProcessHeap
0x1800123ae  mov     r8d, ebx; dwBytes
0x1800123b1  xor     edx, edx; dwFlags
0x1800123b3  mov     rcx, rax; hHeap
0x1800123b6  call    cs:__imp_HeapAlloc
0x1800123bc  mov     r14, rax
0x1800123bf  xor     eax, eax
0x1800123c1  test    r14, r14
0x1800123c4  jz      loc_180012496
0x1800123ca  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x1800123ce  lea     rdx, [rbp+57h+phHash]; phHash
0x1800123d2  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800123d6  mov     r8, r14; pbHashObject
0x1800123d9  mov     [rsp+0C0h+var_90], eax; dwFlags
0x1800123dd  mov     [rsp+0C0h+dwFlags], eax; cbSecret
0x1800123e1  mov     [rsp+0C0h+pcbResult], rax; pbSecret
0x1800123e6  call    cs:__imp_BCryptCreateHash
0x1800123ec  mov     ebx, eax
0x1800123ee  test    eax, eax
0x1800123f0  js      short loc_180012447
0x1800123f2  mov     eax, [r12]
0x1800123f6  lea     rdx, [rbp+57h+pbInput]; pbInput
0x1800123fa  mov     rcx, [rbp+57h+phHash]; hHash
0x1800123fe  xor     r9d, r9d; dwFlags
0x180012401  bswap   eax
0x180012403  mov     dword ptr [rbp+57h+pbInput], eax
0x180012406  mov     r8d, r15d; cbInput
0x180012409  movzx   eax, word ptr [r12+4]
0x18001240f  ror     ax, 8
0x180012413  mov     word ptr [rbp+57h+pbInput+4], ax
0x180012417  movzx   eax, word ptr [r12+6]
0x18001241d  ror     ax, 8
0x180012421  mov     word ptr [rbp+57h+pbInput+6], ax
0x180012425  call    cs:__imp_BCryptHashData
0x18001242b  mov     ebx, eax
0x18001242d  test    eax, eax
0x18001242f  js      short loc_180012447
0x180012431  mov     r8d, [rbp+57h+cbInput]; cbInput
0x180012435  xor     r9d, r9d; dwFlags
0x180012438  mov     rcx, [rbp+57h+phHash]; hHash
0x18001243c  mov     rdx, r13; pbInput
0x18001243f  call    cs:__imp_BCryptHashData
0x180012445  mov     ebx, eax
0x180012447  test    ebx, ebx
0x180012449  jnz     short loc_18001249F
0x18001244b  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18001244f  lea     rax, [rbp+57h+var_7C]
0x180012453  mov     [rsp+0C0h+dwFlags], edi; dwFlags
0x180012457  lea     r9d, [rbx+4]; cbOutput
0x18001245b  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18001245f  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x180012464  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18001246b  call    cs:__imp_BCryptGetProperty
0x180012471  mov     ebx, eax
0x180012473  test    eax, eax
0x180012475  jnz     short loc_18001249D
0x180012477  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x18001247a  call    cs:__imp_GetProcessHeap
0x180012480  mov     r8d, ebx; dwBytes
0x180012483  xor     edx, edx; dwFlags
0x180012485  mov     rcx, rax; hHeap
0x180012488  call    cs:__imp_HeapAlloc
0x18001248e  mov     rdi, rax
0x180012491  test    rax, rax
0x180012494  jnz     short loc_1800124A1
0x180012496  mov     ebx, 0C0000017h
0x18001249b  jmp     short loc_180012505
0x18001249d  test    ebx, ebx
0x18001249f  js      short loc_180012505
0x1800124a1  mov     r8d, dword ptr [rbp+57h+pbOutput]; cbOutput
0x1800124a5  xor     r9d, r9d; dwFlags
0x1800124a8  mov     rcx, [rbp+57h+phHash]; hHash
0x1800124ac  mov     rdx, rdi; pbOutput
0x1800124af  call    cs:__imp_BCryptFinishHash
0x1800124b5  mov     ebx, eax
0x1800124b7  test    eax, eax
0x1800124b9  js      short loc_180012505
0x1800124bb  cmp     dword ptr [rbp+57h+pbOutput], r15d
0x1800124bf  jnb     short loc_1800124C5
0x1800124c1  mov     r15d, dword ptr [rbp+57h+pbOutput]
0x1800124c5  mov     r8, r15; Size
0x1800124c8  mov     rdx, rdi; Src
0x1800124cb  mov     rcx, rsi; void *
0x1800124ce  call    memcpy_0
0x1800124d3  mov     eax, [rsi]
0x1800124d5  mov     ecx, 0FFFh
0x1800124da  bswap   eax
0x1800124dc  mov     [rsi], eax
0x1800124de  movzx   eax, word ptr [rsi+4]
0x1800124e2  ror     ax, 8
0x1800124e6  mov     [rsi+4], ax
0x1800124ea  movzx   eax, word ptr [rsi+6]
0x1800124ee  and     byte ptr [rsi+8], 3Fh
0x1800124f2  ror     ax, 8
0x1800124f6  and     ax, cx
0x1800124f9  or      ax, 5000h
0x1800124fd  or      byte ptr [rsi+8], 80h
0x180012501  mov     [rsi+6], ax
0x180012505  mov     rcx, [rbp+57h+phHash]; hHash
0x180012509  test    rcx, rcx
0x18001250c  jz      short loc_180012514
0x18001250e  call    cs:__imp_BCryptDestroyHash
0x180012514  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180012518  test    rcx, rcx
0x18001251b  jz      short loc_180012525
0x18001251d  xor     edx, edx; dwFlags
0x18001251f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180012525  test    r14, r14
0x180012528  jz      short loc_18001253E
0x18001252a  call    cs:__imp_GetProcessHeap
0x180012530  mov     r8, r14; lpMem
0x180012533  xor     edx, edx; dwFlags
0x180012535  mov     rcx, rax; hHeap
0x180012538  call    cs:__imp_HeapFree
0x18001253e  test    rdi, rdi
0x180012541  jz      short loc_180012557
0x180012543  call    cs:__imp_GetProcessHeap
0x180012549  mov     r8, rdi; lpMem
0x18001254c  xor     edx, edx; dwFlags
0x18001254e  mov     rcx, rax; hHeap
0x180012551  call    cs:__imp_HeapFree
0x180012557  test    ebx, ebx
0x180012559  js      short loc_18001255F
0x18001255b  xor     ebx, ebx
0x18001255d  jmp     short loc_180012563
0x18001255f  bts     ebx, 1Ch
0x180012563  mov     eax, ebx
0x180012565  mov     rcx, [rbp+57h+var_50]
0x180012569  xor     rcx, rsp; StackCookie
0x18001256c  call    __security_check_cookie
0x180012571  add     rsp, 88h
0x180012578  pop     r15
0x18001257a  pop     r14
0x18001257c  pop     r13
0x18001257e  pop     r12
0x180012580  pop     rdi
0x180012581  pop     rsi
0x180012582  pop     rbx
0x180012583  pop     rbp
0x180012584  retn
```
