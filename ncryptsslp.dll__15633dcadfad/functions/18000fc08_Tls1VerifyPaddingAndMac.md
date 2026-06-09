# Tls1VerifyPaddingAndMac

- ea: `0x18000fc08`
- end: `0x18000ffea`
- name: `Tls1VerifyPaddingAndMac`
- size: `994`
- prototype: `__int64 __fastcall(__int64, __int64, ULONG, __int64, PUCHAR, ULONG cbInput, ULONG *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f2d0`

## callees

- `0x180009160`
- `0x18000b594`
- `0x18000b654`
- `0x18000fc08`
- `0x180018ac0`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000fe18`
- `bcrypt!BCryptHashData` at `0x18000fe38`
- `bcrypt!BCryptHashData` at `0x18000fe18`
- `bcrypt!BCryptHashData` at `0x18000fe38`
- `bcrypt!BCryptCreateHash` at `0x18000fdf9`
- `bcrypt!BCryptCreateHash` at `0x18000fdf9`
- `bcrypt!BCryptDestroyHash` at `0x18000fe58`
- `bcrypt!BCryptDestroyHash` at `0x18000fe58`

## string_xrefs

- `0x18000fec0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000ff13`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000ffbf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1VerifyPaddingAndMac(
        __int64 a1,
        __int64 a2,
        ULONG a3,
        __int64 a4,
        PUCHAR a5,
        ULONG cbInput,
        ULONG *a7)
{
  char v7; // r10
  __int64 v8; // rsi
  __int64 v9; // r14
  __int16 v10; // cx
  UCHAR *p_phHash; // rbx
  __int64 v12; // rax
  unsigned __int64 v13; // rdi
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  NTSTATUS v18; // edi
  NTSTATUS v19; // eax
  _QWORD *v21; // rcx
  UCHAR *v22; // rax
  __int64 v23; // [rsp+0h] [rbp-40h] BYREF
  PUCHAR pbSecret; // [rsp+20h] [rbp-20h]
  ULONG cbSecret[2]; // [rsp+28h] [rbp-18h]
  ULONG dwFlags; // [rsp+30h] [rbp-10h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+0h] BYREF
  ULONG v28; // [rsp+48h] [rbp+8h] BYREF
  __int64 v29; // [rsp+50h] [rbp+10h]
  UCHAR pbInput[8]; // [rsp+60h] [rbp+20h] BYREF
  int v31; // [rsp+68h] [rbp+28h]
  char v32; // [rsp+6Ch] [rbp+2Ch]

  v7 = a3;
  v8 = a2;
  *(_QWORD *)pbInput = 0;
  v31 = 0;
  v32 = 0;
  phHash = 0;
  if ( a1 && (v9 = a1 + 272, a1 != -272) && a2 && (a2 = *(_QWORD *)(a2 + 16)) != 0 && a5 && cbInput && a7 )
  {
    v10 = *(_WORD *)(v8 + 8);
    p_phHash = 0;
    a3 = cbInput - a5[cbInput - 1] - *(_DWORD *)(a2 + 68) - 1;
    pbInput[0] = HIBYTE(a4);
    pbInput[1] = BYTE6(a4);
    pbInput[2] = BYTE5(a4);
    pbInput[3] = BYTE4(a4);
    pbInput[4] = BYTE3(a4);
    pbInput[5] = BYTE2(a4);
    pbInput[6] = BYTE1(a4);
    BYTE1(v31) = HIBYTE(v10);
    HIBYTE(v31) = BYTE1(a3);
    pbInput[7] = a4;
    LOBYTE(v31) = v7;
    BYTE2(v31) = v10;
    v32 = a3;
    v12 = 32LL * *(unsigned int *)(a2 + 72);
    v28 = a3;
    v29 = v12;
    v13 = *(unsigned int *)(v12 + v9 + 20);
    if ( !*(_DWORD *)(v12 + v9 + 20)
      || v13 > g_ulMaxStackAllocSize
      || v13 + g_ulAdditionalProbeSize + 8 < v13
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_47;
    }
    v14 = v13 + 23;
    if ( v13 + 23 <= v13 + 8 )
      v14 = 0xFFFFFFFFFFFFFF0LL;
    v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
    v16 = alloca(v15);
    v17 = alloca(v15);
    p_phHash = (UCHAR *)&phHash;
    if ( &v23 == (__int64 *)-64LL || (LODWORD(phHash) = 1801679955, (p_phHash = (UCHAR *)&v28) == 0) )
    {
LABEL_47:
      if ( v13 + 8 >= v13 )
      {
        v22 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_phHash = v22;
        if ( v22 )
        {
          *(_DWORD *)v22 = 1885431112;
          p_phHash = v22 + 8;
        }
      }
    }
    if ( !p_phHash )
    {
      v18 = -2146893810;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      dwFlags = 457;
      *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
      LODWORD(pbSecret) = -2146893810;
      goto LABEL_31;
    }
    v18 = BCryptCreateHash(
            *(BCRYPT_ALG_HANDLE *)(v29 + v9 + 8),
            &phHash,
            p_phHash,
            *(_DWORD *)(v29 + v9 + 20),
            (PUCHAR)(v8 + 56),
            *(_DWORD *)(v8 + 104),
            0);
    if ( v18 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      dwFlags = 471;
    }
    else
    {
      v18 = BCryptHashData(phHash, pbInput, 0xDu, 0);
      if ( v18 >= 0 )
      {
        v19 = BCryptHashData(phHash, a5, cbInput, 4u);
        v18 = v19;
        if ( v19 < 0 )
          DebugTraceError(
            (unsigned int)v19,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            503);
        else
          *a7 = v28;
        goto LABEL_21;
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      dwFlags = 482;
    }
  }
  else
  {
    v18 = 87;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v18;
    p_phHash = 0;
    dwFlags = 401;
  }
  *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
  LODWORD(pbSecret) = v18;
LABEL_31:
  WPP_SF_sDsd(v21[2], a2, (_WORD)a3, (unsigned int)"Status", (char)pbSecret, *(__int64 *)cbSecret, dwFlags);
LABEL_21:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash && *((_DWORD *)p_phHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18000fc08  push    rbp
0x18000fc0a  push    rsi
0x18000fc0b  push    rdi
0x18000fc0c  push    r12
0x18000fc0e  push    r13
0x18000fc10  push    r14
0x18000fc12  push    r15
0x18000fc14  sub     rsp, 80h
0x18000fc1b  lea     rbp, [rsp+40h]
0x18000fc20  mov     [rbp+70h+arg_10], rbx
0x18000fc27  mov     rax, cs:__security_cookie
0x18000fc2e  xor     rax, rbp
0x18000fc31  mov     [rbp+70h+var_40], rax
0x18000fc35  mov     r12, [rbp+70h+arg_20]
0x18000fc3c  xor     eax, eax
0x18000fc3e  mov     r15d, [rbp+70h+cbInput]
0x18000fc45  mov     r10d, r8d
0x18000fc48  mov     r13, [rbp+70h+arg_30]
0x18000fc4f  mov     rsi, rdx
0x18000fc52  mov     qword ptr [rbp+70h+pbInput], rax
0x18000fc56  mov     [rbp+70h+var_48], eax
0x18000fc59  mov     [rbp+70h+var_44], al
0x18000fc5c  mov     [rbp+70h+phHash], rax
0x18000fc60  test    rcx, rcx
0x18000fc63  jz      loc_18000FE98
0x18000fc69  lea     r14, [rcx+110h]
0x18000fc70  test    r14, r14
0x18000fc73  jz      loc_18000FE98
0x18000fc79  test    rdx, rdx
0x18000fc7c  jz      loc_18000FE98
0x18000fc82  mov     rdx, [rdx+10h]
0x18000fc86  test    rdx, rdx
0x18000fc89  jz      loc_18000FE98
0x18000fc8f  test    r12, r12
0x18000fc92  jz      loc_18000FE98
0x18000fc98  cmp     r15d, 1
0x18000fc9c  jb      loc_18000FE98
0x18000fca2  test    r13, r13
0x18000fca5  jz      loc_18000FE98
0x18000fcab  movzx   ecx, word ptr [rsi+8]
0x18000fcaf  lea     eax, [r15-1]
0x18000fcb3  movzx   eax, byte ptr [rax+r12]
0x18000fcb8  mov     r8d, r15d
0x18000fcbb  sub     r8d, eax
0x18000fcbe  xor     ebx, ebx
0x18000fcc0  sub     r8d, [rdx+44h]
0x18000fcc4  mov     rax, r9
0x18000fcc7  shr     rax, 38h
0x18000fccb  dec     r8d
0x18000fcce  mov     [rbp+70h+pbInput], al
0x18000fcd1  mov     rax, r9
0x18000fcd4  shr     rax, 30h
0x18000fcd8  mov     [rbp+70h+pbInput+1], al
0x18000fcdb  mov     rax, r9
0x18000fcde  shr     rax, 28h
0x18000fce2  mov     [rbp+70h+pbInput+2], al
0x18000fce5  mov     rax, r9
0x18000fce8  shr     rax, 20h
0x18000fcec  mov     [rbp+70h+pbInput+3], al
0x18000fcef  mov     rax, r9
0x18000fcf2  shr     rax, 18h
0x18000fcf6  mov     [rbp+70h+pbInput+4], al
0x18000fcf9  mov     rax, r9
0x18000fcfc  shr     rax, 10h
0x18000fd00  mov     [rbp+70h+pbInput+5], al
0x18000fd03  mov     rax, r9
0x18000fd06  shr     rax, 8
0x18000fd0a  mov     [rbp+70h+pbInput+6], al
0x18000fd0d  movzx   eax, cx
0x18000fd10  shr     ax, 8
0x18000fd14  mov     byte ptr [rbp+70h+var_48+1], al
0x18000fd17  movzx   eax, r8w
0x18000fd1b  shr     ax, 8
0x18000fd1f  mov     byte ptr [rbp+70h+var_48+3], al
0x18000fd22  mov     [rbp+70h+pbInput+7], r9b
0x18000fd26  mov     byte ptr [rbp+70h+var_48], r10b
0x18000fd2a  mov     byte ptr [rbp+70h+var_48+2], cl
0x18000fd2d  mov     [rbp+70h+var_44], r8b
0x18000fd31  mov     eax, [rdx+48h]
0x18000fd34  shl     rax, 5
0x18000fd38  mov     [rbp+70h+var_68], r8d
0x18000fd3c  mov     [rbp+70h+var_60], rax
0x18000fd40  mov     edi, [rax+r14+14h]
0x18000fd45  test    rdi, rdi
0x18000fd48  jz      loc_18000FF85
0x18000fd4e  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18000fd55  ja      loc_18000FF85
0x18000fd5b  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000fd62  add     rcx, 8
0x18000fd66  add     rcx, rdi
0x18000fd69  cmp     rcx, rdi
0x18000fd6c  jb      loc_18000FF85
0x18000fd72  call    VerifyStackAvailable
0x18000fd77  test    eax, eax
0x18000fd79  jz      loc_18000FF85
0x18000fd7f  lea     rax, [rdi+8]
0x18000fd83  lea     rcx, [rax+0Fh]
0x18000fd87  cmp     rcx, rax
0x18000fd8a  ja      short loc_18000FD96
0x18000fd8c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000fd96  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000fd9a  mov     rax, rcx
0x18000fd9d  call    _alloca_probe
0x18000fda2  sub     rsp, rcx
0x18000fda5  lea     rbx, [rsp+0B0h+phHash]
0x18000fdaa  test    rbx, rbx
0x18000fdad  jz      loc_18000FF85
0x18000fdb3  mov     dword ptr [rbx], 6B637453h
0x18000fdb9  add     rbx, 8
0x18000fdbd  jz      loc_18000FF85
0x18000fdc3  test    rbx, rbx
0x18000fdc6  jz      loc_18000FEE5
0x18000fdcc  mov     eax, [rsi+68h]
0x18000fdcf  lea     rcx, [rsi+38h]
0x18000fdd3  mov     [rsp+0B0h+dwFlags], 0; dwFlags
0x18000fddb  lea     rdx, [rbp+70h+phHash]; phHash
0x18000fddf  mov     [rsp+0B0h+cbSecret], eax; cbSecret
0x18000fde3  mov     r8, rbx; pbHashObject
0x18000fde6  mov     [rsp+0B0h+pbSecret], rcx; pbSecret
0x18000fdeb  mov     rcx, [rbp+70h+var_60]
0x18000fdef  mov     r9d, [rcx+r14+14h]; cbHashObject
0x18000fdf4  mov     rcx, [rcx+r14+8]; hAlgorithm
0x18000fdf9  call    cs:__imp_BCryptCreateHash
0x18000fdff  mov     edi, eax
0x18000fe01  test    eax, eax
0x18000fe03  js      loc_18000FF29
0x18000fe09  mov     rcx, [rbp+70h+phHash]; hHash
0x18000fe0d  lea     rdx, [rbp+70h+pbInput]; pbInput
0x18000fe11  xor     r9d, r9d; dwFlags
0x18000fe14  lea     r8d, [r9+0Dh]; cbInput
0x18000fe18  call    cs:__imp_BCryptHashData
0x18000fe1e  mov     edi, eax
0x18000fe20  test    eax, eax
0x18000fe22  js      loc_18000FF57
0x18000fe28  mov     rcx, [rbp+70h+phHash]; hHash
0x18000fe2c  mov     r9d, 4; dwFlags
0x18000fe32  mov     r8d, r15d; cbInput
0x18000fe35  mov     rdx, r12; pbInput
0x18000fe38  call    cs:__imp_BCryptHashData
0x18000fe3e  mov     edi, eax
0x18000fe40  test    eax, eax
0x18000fe42  js      loc_18000FFB9
0x18000fe48  mov     eax, [rbp+70h+var_68]
0x18000fe4b  mov     [r13+0], eax
0x18000fe4f  mov     rcx, [rbp+70h+phHash]; hHash
0x18000fe53  test    rcx, rcx
0x18000fe56  jz      short loc_18000FE5E
0x18000fe58  call    cs:__imp_BCryptDestroyHash
0x18000fe5e  test    rbx, rbx
0x18000fe61  jz      short loc_18000FE73
0x18000fe63  lea     rcx, [rbx-8]
0x18000fe67  cmp     dword ptr [rcx], 70616548h
0x18000fe6d  jz      loc_18000FFD9
0x18000fe73  mov     eax, edi
0x18000fe75  mov     rcx, [rbp+70h+var_40]
0x18000fe79  xor     rcx, rbp; StackCookie
0x18000fe7c  call    __security_check_cookie
0x18000fe81  mov     rbx, [rbp+70h+arg_10]
0x18000fe88  lea     rsp, [rbp+40h]
0x18000fe8c  pop     r15
0x18000fe8e  pop     r14
0x18000fe90  pop     r13
0x18000fe92  pop     r12
0x18000fe94  pop     rdi
0x18000fe95  pop     rsi
0x18000fe96  pop     rbp
0x18000fe97  retn
0x18000fe98  mov     edi, 57h ; 'W'
0x18000fe9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fea4  lea     rax, WPP_GLOBAL_Control
0x18000feab  cmp     rcx, rax
0x18000feae  jz      short loc_18000FE73
0x18000feb0  test    byte ptr [rcx+1Ch], 1
0x18000feb4  jz      short loc_18000FE73
0x18000feb6  xor     ebx, ebx
0x18000feb8  mov     [rsp+0B0h+dwFlags], 191h
0x18000fec0  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fec7  mov     qword ptr [rsp+0B0h+cbSecret], rax
0x18000fecc  mov     dword ptr [rsp+0B0h+pbSecret], edi
0x18000fed0  mov     rcx, [rcx+10h]
0x18000fed4  lea     r9, aStatus; "Status"
0x18000fedb  call    WPP_SF_sDsd
0x18000fee0  jmp     loc_18000FE4F
0x18000fee5  mov     edi, 8009000Eh
0x18000feea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fef1  lea     rax, WPP_GLOBAL_Control
0x18000fef8  cmp     rcx, rax
0x18000fefb  jz      loc_18000FE4F
0x18000ff01  test    byte ptr [rcx+1Ch], 1
0x18000ff05  jz      loc_18000FE4F
0x18000ff0b  mov     [rsp+0B0h+dwFlags], 1C9h
0x18000ff13  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ff1a  mov     qword ptr [rsp+0B0h+cbSecret], rax
0x18000ff1f  mov     dword ptr [rsp+0B0h+pbSecret], 8009000Eh
0x18000ff27  jmp     short loc_18000FED0
0x18000ff29  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff30  lea     rax, WPP_GLOBAL_Control
0x18000ff37  cmp     rcx, rax
0x18000ff3a  jz      loc_18000FE4F
0x18000ff40  test    byte ptr [rcx+1Ch], 1
0x18000ff44  jz      loc_18000FE4F
0x18000ff4a  mov     [rsp+0B0h+dwFlags], 1D7h
0x18000ff52  jmp     loc_18000FEC0
0x18000ff57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff5e  lea     rax, WPP_GLOBAL_Control
0x18000ff65  cmp     rcx, rax
0x18000ff68  jz      loc_18000FE4F
0x18000ff6e  test    byte ptr [rcx+1Ch], 1
0x18000ff72  jz      loc_18000FE4F
0x18000ff78  mov     [rsp+0B0h+dwFlags], 1E2h
0x18000ff80  jmp     loc_18000FEC0
0x18000ff85  lea     rcx, [rdi+8]
0x18000ff89  cmp     rcx, rdi
0x18000ff8c  jb      loc_18000FDC3
0x18000ff92  mov     rax, cs:g_pfnAllocate
0x18000ff99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff9e  mov     rbx, rax
0x18000ffa1  test    rax, rax
0x18000ffa4  jz      loc_18000FDC3
0x18000ffaa  mov     dword ptr [rax], 70616548h
0x18000ffb0  add     rbx, 8
0x18000ffb4  jmp     loc_18000FDC3
0x18000ffb9  mov     r9d, 1F7h
0x18000ffbf  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ffc6  lea     rdx, aStatus; "Status"
0x18000ffcd  mov     ecx, eax
0x18000ffcf  call    DebugTraceError
0x18000ffd4  jmp     loc_18000FE4F
0x18000ffd9  mov     rax, cs:g_pfnFree
0x18000ffe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffe5  jmp     loc_18000FE73
```
