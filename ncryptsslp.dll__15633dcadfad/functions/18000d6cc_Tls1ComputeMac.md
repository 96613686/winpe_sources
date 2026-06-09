# Tls1ComputeMac

- ea: `0x18000d6cc`
- end: `0x18000d9e2`
- name: `Tls1ComputeMac`
- size: `790`
- prototype: `__int64 __fastcall(int, int, int, int, PUCHAR, ULONG cbInput, PUCHAR pbOutput, ULONG cbOutput)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c1c0`
- `0x18000f2d0`

## callees

- `0x180009160`
- `0x18000b594`
- `0x18000b654`
- `0x18000d6cc`
- `0x18000d9f0`
- `0x180018ac0`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000d82b`
- `bcrypt!BCryptHashData` at `0x18000d84c`
- `bcrypt!BCryptHashData` at `0x18000d82b`
- `bcrypt!BCryptHashData` at `0x18000d84c`
- `bcrypt!BCryptCreateHash` at `0x18000d80c`
- `bcrypt!BCryptCreateHash` at `0x18000d80c`
- `bcrypt!BCryptFinishHash` at `0x18000d869`
- `bcrypt!BCryptFinishHash` at `0x18000d869`
- `bcrypt!BCryptDestroyHash` at `0x18000d884`
- `bcrypt!BCryptDestroyHash` at `0x18000d884`

## string_xrefs

- `0x18000d8ef`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000d96d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000d9c8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1ComputeMac(
        __int64 a1,
        __int64 a2,
        char a3,
        int a4,
        PUCHAR a5,
        ULONG cbInput,
        PUCHAR pbOutput,
        ULONG cbOutput)
{
  __int64 v8; // r14
  UCHAR *p_phHash; // rdi
  int v11; // edx
  NTSTATUS v12; // ebx
  __int64 v13; // rsi
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  NTSTATUS v20; // eax
  _QWORD *v22; // rcx
  UCHAR *v23; // rax
  __int64 v24; // r9
  __int64 v25; // [rsp+0h] [rbp-40h] BYREF
  PUCHAR pbSecret; // [rsp+20h] [rbp-20h]
  ULONG cbSecret[2]; // [rsp+28h] [rbp-18h]
  ULONG dwFlags; // [rsp+30h] [rbp-10h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+0h] BYREF
  __int64 v30; // [rsp+48h] [rbp+8h] BYREF
  UCHAR pbInput[16]; // [rsp+50h] [rbp+10h] BYREF

  v8 = a2;
  phHash = 0;
  LOBYTE(a2) = a3;
  p_phHash = 0;
  v12 = Tls1BuildHmacHeader(a4, a2, *(unsigned __int16 *)(v8 + 8), (unsigned __int16)cbInput, (__int64)pbInput);
  if ( v12 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    dwFlags = 285;
    goto LABEL_25;
  }
  v13 = 32LL * *(unsigned int *)(*(_QWORD *)(v8 + 16) + 72LL);
  v14 = *(unsigned int *)(v13 + a1 + 292);
  if ( !*(_DWORD *)(v13 + a1 + 292) )
    goto LABEL_41;
  if ( v14 > g_ulMaxStackAllocSize )
    goto LABEL_41;
  v15 = v14 + g_ulAdditionalProbeSize + 8;
  if ( v15 < v14 || !(unsigned int)VerifyStackAvailable(v15) )
    goto LABEL_41;
  v16 = v14 + 23;
  if ( v14 + 23 <= v14 + 8 )
    v16 = 0xFFFFFFFFFFFFFF0LL;
  v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
  v18 = alloca(v17);
  v19 = alloca(v17);
  p_phHash = (UCHAR *)&phHash;
  if ( &v25 == (__int64 *)-64LL || (LODWORD(phHash) = 1801679955, (p_phHash = (UCHAR *)&v30) == 0) )
  {
LABEL_41:
    if ( v14 + 8 >= v14 )
    {
      v23 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_phHash = v23;
      if ( v23 )
      {
        *(_DWORD *)v23 = 1885431112;
        p_phHash = v23 + 8;
      }
    }
  }
  if ( !p_phHash )
  {
    v12 = -2146893810;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    dwFlags = 304;
    *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
    LODWORD(pbSecret) = -2146893810;
LABEL_26:
    WPP_SF_sDsd(
      v22[2],
      v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      (unsigned int)"Status",
      (char)pbSecret,
      *(__int64 *)cbSecret,
      dwFlags);
    goto LABEL_16;
  }
  v12 = BCryptCreateHash(
          *(BCRYPT_ALG_HANDLE *)(v13 + a1 + 280),
          &phHash,
          p_phHash,
          *(_DWORD *)(v13 + a1 + 292),
          (PUCHAR)(v8 + 56),
          *(_DWORD *)(v8 + 104),
          0);
  if ( v12 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    dwFlags = 319;
LABEL_25:
    *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
    LODWORD(pbSecret) = v12;
    goto LABEL_26;
  }
  v20 = BCryptHashData(phHash, pbInput, 0xDu, 0);
  v12 = v20;
  if ( v20 < 0 )
  {
    v24 = 332;
  }
  else
  {
    v12 = BCryptHashData(phHash, a5, cbInput, 0);
    if ( v12 < 0 )
      goto LABEL_16;
    v20 = BCryptFinishHash(phHash, pbOutput, cbOutput, 0);
    v12 = v20;
    if ( v20 >= 0 )
    {
      v12 = 0;
      goto LABEL_16;
    }
    v24 = 351;
  }
  DebugTraceError((unsigned int)v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v24);
LABEL_16:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash && *((_DWORD *)p_phHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d6cc  push    rbp
0x18000d6ce  push    rsi
0x18000d6cf  push    rdi
0x18000d6d0  push    r12
0x18000d6d2  push    r13
0x18000d6d4  push    r14
0x18000d6d6  push    r15
0x18000d6d8  sub     rsp, 70h
0x18000d6dc  lea     rbp, [rsp+40h]
0x18000d6e1  mov     [rbp+60h+arg_10], rbx
0x18000d6e8  mov     rax, cs:__security_cookie
0x18000d6ef  xor     rax, rbp
0x18000d6f2  mov     [rbp+60h+var_40], rax
0x18000d6f6  mov     r13, [rbp+60h+arg_20]
0x18000d6fd  mov     r14, rdx
0x18000d700  mov     r12, [rbp+60h+pbOutput]
0x18000d707  mov     r15, rcx
0x18000d70a  mov     rax, r9
0x18000d70d  mov     [rbp+60h+phHash], 0
0x18000d715  movzx   r9d, word ptr [rbp+60h+cbInput]
0x18000d71d  lea     rcx, [rbp+60h+pbInput]
0x18000d721  mov     dl, r8b
0x18000d724  mov     [rsp+0A0h+pbSecret], rcx
0x18000d729  movzx   r8d, word ptr [r14+8]
0x18000d72e  mov     rcx, rax
0x18000d731  call    Tls1BuildHmacHeader
0x18000d736  xor     edi, edi
0x18000d738  mov     ebx, eax
0x18000d73a  test    eax, eax
0x18000d73c  js      loc_18000D914
0x18000d742  mov     rax, [r14+10h]
0x18000d746  mov     esi, [rax+48h]
0x18000d749  shl     rsi, 5
0x18000d74d  mov     ebx, [rsi+r15+124h]
0x18000d755  test    rbx, rbx
0x18000d758  jz      loc_18000D986
0x18000d75e  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000d765  ja      loc_18000D986
0x18000d76b  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000d772  add     rcx, 8
0x18000d776  add     rcx, rbx
0x18000d779  cmp     rcx, rbx
0x18000d77c  jb      loc_18000D986
0x18000d782  call    VerifyStackAvailable
0x18000d787  test    eax, eax
0x18000d789  jz      loc_18000D986
0x18000d78f  lea     rax, [rbx+8]
0x18000d793  lea     rcx, [rax+0Fh]
0x18000d797  cmp     rcx, rax
0x18000d79a  ja      short loc_18000D7A6
0x18000d79c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000d7a6  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000d7aa  mov     rax, rcx
0x18000d7ad  call    _alloca_probe
0x18000d7b2  sub     rsp, rcx
0x18000d7b5  lea     rdi, [rsp+0A0h+phHash]
0x18000d7ba  test    rdi, rdi
0x18000d7bd  jz      loc_18000D986
0x18000d7c3  mov     dword ptr [rdi], 6B637453h
0x18000d7c9  add     rdi, 8
0x18000d7cd  jz      loc_18000D986
0x18000d7d3  test    rdi, rdi
0x18000d7d6  jz      loc_18000D93F
0x18000d7dc  mov     eax, [r14+68h]
0x18000d7e0  lea     rcx, [r14+38h]
0x18000d7e4  mov     r9d, [rsi+r15+124h]; cbHashObject
0x18000d7ec  lea     rdx, [rbp+60h+phHash]; phHash
0x18000d7f0  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x18000d7f8  mov     r8, rdi; pbHashObject
0x18000d7fb  mov     [rsp+0A0h+cbSecret], eax; cbSecret
0x18000d7ff  mov     [rsp+0A0h+pbSecret], rcx; pbSecret
0x18000d804  mov     rcx, [rsi+r15+118h]; hAlgorithm
0x18000d80c  call    cs:__imp_BCryptCreateHash
0x18000d812  mov     ebx, eax
0x18000d814  test    eax, eax
0x18000d816  js      loc_18000D8CE
0x18000d81c  mov     rcx, [rbp+60h+phHash]; hHash
0x18000d820  lea     rdx, [rbp+60h+pbInput]; pbInput
0x18000d824  xor     r9d, r9d; dwFlags
0x18000d827  lea     r8d, [r9+0Dh]; cbInput
0x18000d82b  call    cs:__imp_BCryptHashData
0x18000d831  mov     ebx, eax
0x18000d833  test    eax, eax
0x18000d835  js      loc_18000D9BA
0x18000d83b  mov     r8d, [rbp+60h+cbInput]; cbInput
0x18000d842  xor     r9d, r9d; dwFlags
0x18000d845  mov     rcx, [rbp+60h+phHash]; hHash
0x18000d849  mov     rdx, r13; pbInput
0x18000d84c  call    cs:__imp_BCryptHashData
0x18000d852  mov     ebx, eax
0x18000d854  test    eax, eax
0x18000d856  js      short loc_18000D87B
0x18000d858  mov     r8d, [rbp+60h+cbOutput]; cbOutput
0x18000d85f  xor     r9d, r9d; dwFlags
0x18000d862  mov     rcx, [rbp+60h+phHash]; hHash
0x18000d866  mov     rdx, r12; pbOutput
0x18000d869  call    cs:__imp_BCryptFinishHash
0x18000d86f  mov     ebx, eax
0x18000d871  test    eax, eax
0x18000d873  js      loc_18000D9C2
0x18000d879  xor     ebx, ebx
0x18000d87b  mov     rcx, [rbp+60h+phHash]; hHash
0x18000d87f  test    rcx, rcx
0x18000d882  jz      short loc_18000D88A
0x18000d884  call    cs:__imp_BCryptDestroyHash
0x18000d88a  test    rdi, rdi
0x18000d88d  jnz     short loc_18000D8B4
0x18000d88f  mov     eax, ebx
0x18000d891  mov     rcx, [rbp+60h+var_40]
0x18000d895  xor     rcx, rbp; StackCookie
0x18000d898  call    __security_check_cookie
0x18000d89d  mov     rbx, [rbp+60h+arg_10]
0x18000d8a4  lea     rsp, [rbp+30h]
0x18000d8a8  pop     r15
0x18000d8aa  pop     r14
0x18000d8ac  pop     r13
0x18000d8ae  pop     r12
0x18000d8b0  pop     rdi
0x18000d8b1  pop     rsi
0x18000d8b2  pop     rbp
0x18000d8b3  retn
0x18000d8b4  lea     rcx, [rdi-8]
0x18000d8b8  cmp     dword ptr [rcx], 70616548h
0x18000d8be  jnz     short loc_18000D88F
0x18000d8c0  mov     rax, cs:g_pfnFree
0x18000d8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8cc  jmp     short loc_18000D88F
0x18000d8ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8d5  lea     rax, WPP_GLOBAL_Control
0x18000d8dc  cmp     rcx, rax
0x18000d8df  jz      short loc_18000D87B
0x18000d8e1  test    byte ptr [rcx+1Ch], 1
0x18000d8e5  jz      short loc_18000D87B
0x18000d8e7  mov     [rsp+0A0h+dwFlags], 13Fh
0x18000d8ef  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d8f6  mov     qword ptr [rsp+0A0h+cbSecret], r8
0x18000d8fb  mov     dword ptr [rsp+0A0h+pbSecret], ebx
0x18000d8ff  mov     rcx, [rcx+10h]
0x18000d903  lea     r9, aStatus; "Status"
0x18000d90a  call    WPP_SF_sDsd
0x18000d90f  jmp     loc_18000D87B
0x18000d914  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d91b  lea     rax, WPP_GLOBAL_Control
0x18000d922  cmp     rcx, rax
0x18000d925  jz      loc_18000D87B
0x18000d92b  test    byte ptr [rcx+1Ch], 1
0x18000d92f  jz      loc_18000D87B
0x18000d935  mov     [rsp+0A0h+dwFlags], 11Dh
0x18000d93d  jmp     short loc_18000D8EF
0x18000d93f  mov     ebx, 8009000Eh
0x18000d944  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d94b  lea     rax, WPP_GLOBAL_Control
0x18000d952  cmp     rcx, rax
0x18000d955  jz      loc_18000D87B
0x18000d95b  test    byte ptr [rcx+1Ch], 1
0x18000d95f  jz      loc_18000D87B
0x18000d965  mov     [rsp+0A0h+dwFlags], 130h
0x18000d96d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d974  mov     qword ptr [rsp+0A0h+cbSecret], r8
0x18000d979  mov     dword ptr [rsp+0A0h+pbSecret], 8009000Eh
0x18000d981  jmp     loc_18000D8FF
0x18000d986  lea     rcx, [rbx+8]
0x18000d98a  cmp     rcx, rbx
0x18000d98d  jb      loc_18000D7D3
0x18000d993  mov     rax, cs:g_pfnAllocate
0x18000d99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d99f  mov     rdi, rax
0x18000d9a2  test    rax, rax
0x18000d9a5  jz      loc_18000D7D3
0x18000d9ab  mov     dword ptr [rax], 70616548h
0x18000d9b1  add     rdi, 8
0x18000d9b5  jmp     loc_18000D7D3
0x18000d9ba  mov     r9d, 14Ch
0x18000d9c0  jmp     short loc_18000D9C8
0x18000d9c2  mov     r9d, 15Fh
0x18000d9c8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d9cf  mov     ecx, eax
0x18000d9d1  lea     rdx, aStatus; "Status"
0x18000d9d8  call    DebugTraceError
0x18000d9dd  jmp     loc_18000D87B
```
