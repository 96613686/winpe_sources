# CNG_Encrypt

- ea: `0x180002f74`
- end: `0x180003148`
- name: `CNG_Encrypt`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002c34`

## callees

- `0x180002f74`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x180003021`
- `bcrypt!BCryptEncrypt` at `0x180003021`

## string_xrefs

- `0x18000305b`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x1800030b0`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180003126`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`

## pseudocode

```c
__int64 __fastcall CNG_Encrypt(
        __int64 a1,
        UCHAR *a2,
        ULONG a3,
        UCHAR *a4,
        unsigned int cbOutput,
        ULONG *pcbResult,
        int a7)
{
  const void *v8; // rbp
  ULONG dwFlags; // r9d
  unsigned int v10; // edi
  __int64 v14; // rcx
  UCHAR *pbIV; // rdx
  ULONG cbIV; // r8d
  int v17; // eax
  unsigned int v18; // eax
  int v19; // edx
  unsigned int v20; // ebx
  __int64 v22; // rcx

  v8 = 0;
  dwFlags = 0;
  v10 = 0;
  if ( (*(_DWORD *)(a1 + 112) & 0x10000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 64) < 0x98u )
    {
      v20 = -2146893779;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          (unsigned int)"Status",
          45,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          237);
      return v20;
    }
    v14 = *(_QWORD *)(a1 + 72);
    pbIV = *(UCHAR **)(v14 + 136);
    cbIV = *(_DWORD *)(v14 + 144);
    *(_QWORD *)(v14 + 56) = v14 + 116;
    v17 = *(_DWORD *)(v14 + 80);
    *(_DWORD *)(v14 + 64) = 16;
    if ( a7 )
    {
      v8 = *(const void **)(v14 + 40);
      v18 = v17 & 0xFFFFFFFE;
      v10 = *(_DWORD *)(v14 + 48);
    }
    else
    {
      v18 = v17 | 1;
    }
    *(_DWORD *)(v14 + 80) = v18;
  }
  else
  {
    pbIV = 0;
    cbIV = 0;
    if ( a7 )
      dwFlags = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 72LL);
  }
  v20 = BCryptEncrypt(
          *(BCRYPT_KEY_HANDLE *)(a1 + 16),
          a2,
          a3,
          *(void **)(a1 + 72),
          pbIV,
          cbIV,
          a4,
          cbOutput,
          pcbResult,
          dwFlags);
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        (unsigned int)"Status",
        v20,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        25);
  }
  else
  {
    if ( v8 && v10 )
    {
      if ( a4 )
      {
        v22 = *pcbResult;
        if ( cbOutput < (unsigned int)v22 + v10 )
        {
          v20 = -2146893784;
          DebugTraceError(
            2148073512LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
            1061);
          return v20;
        }
        memcpy_0(&a4[v22], v8, v10);
      }
      *pcbResult += v10;
    }
    return 0;
  }
  return v20;
}

```

## disassembly

```asm
0x180002f74  push    rbx
0x180002f76  push    rbp
0x180002f77  push    rsi
0x180002f78  push    rdi
0x180002f79  push    r14
0x180002f7b  push    r15
0x180002f7d  sub     rsp, 58h
0x180002f81  mov     r14, r9
0x180002f84  xor     ebp, ebp
0x180002f86  xor     r9d, r9d
0x180002f89  xor     edi, edi
0x180002f8b  test    dword ptr [rcx+70h], 10000000h
0x180002f92  mov     r11d, r8d
0x180002f95  mov     rbx, rdx
0x180002f98  mov     r10, rcx
0x180002f9b  jz      loc_1800030C6
0x180002fa1  cmp     dword ptr [rcx+40h], 98h
0x180002fa8  jb      loc_18000308A
0x180002fae  mov     rcx, [rcx+48h]
0x180002fb2  lea     rax, [rcx+74h]
0x180002fb6  mov     rdx, [rcx+88h]
0x180002fbd  mov     r8d, [rcx+90h]
0x180002fc4  mov     [rcx+38h], rax
0x180002fc8  mov     eax, [rcx+50h]
0x180002fcb  mov     dword ptr [rcx+40h], 10h
0x180002fd2  cmp     [rsp+88h+arg_30], edi
0x180002fd9  jnz     loc_1800030E5
0x180002fdf  or      eax, 1
0x180002fe2  mov     [rcx+50h], eax
0x180002fe5  mov     rsi, [rsp+88h+arg_28]
0x180002fed  mov     r15d, [rsp+88h+arg_20]
0x180002ff5  mov     rcx, [r10+10h]; hKey
0x180002ff9  mov     [rsp+88h+dwFlags], r9d; dwFlags
0x180002ffe  mov     r9, [r10+48h]; pPaddingInfo
0x180003002  mov     [rsp+88h+pcbResult], rsi; pcbResult
0x180003007  mov     [rsp+88h+cbOutput], r15d; cbOutput
0x18000300c  mov     [rsp+88h+pbOutput], r14; pbOutput
0x180003011  mov     [rsp+88h+cbIV], r8d; cbIV
0x180003016  mov     r8d, r11d; cbInput
0x180003019  mov     [rsp+88h+pbIV], rdx; pbIV
0x18000301e  mov     rdx, rbx; pbInput
0x180003021  call    cs:__imp_BCryptEncrypt
0x180003027  mov     ebx, eax
0x180003029  test    eax, eax
0x18000302b  jnz     short loc_18000303A
0x18000302d  test    rbp, rbp
0x180003030  jnz     loc_1800030F4
0x180003036  xor     ebx, ebx
0x180003038  jmp     short loc_18000307B
0x18000303a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003041  lea     rax, WPP_GLOBAL_Control
0x180003048  cmp     rcx, rax
0x18000304b  jz      short loc_18000307B
0x18000304d  test    byte ptr [rcx+1Ch], 1
0x180003051  jz      short loc_18000307B
0x180003053  mov     dword ptr [rsp+88h+pbOutput], 419h
0x18000305b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003062  mov     qword ptr [rsp+88h+cbIV], r8
0x180003067  mov     dword ptr [rsp+88h+pbIV], ebx
0x18000306b  mov     rcx, [rcx+10h]
0x18000306f  lea     r9, aStatus; "Status"
0x180003076  call    WPP_SF_sDsd
0x18000307b  mov     eax, ebx
0x18000307d  add     rsp, 58h
0x180003081  pop     r15
0x180003083  pop     r14
0x180003085  pop     rdi
0x180003086  pop     rsi
0x180003087  pop     rbp
0x180003088  pop     rbx
0x180003089  retn
0x18000308a  mov     ebx, 8009002Dh
0x18000308f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003096  lea     rax, WPP_GLOBAL_Control
0x18000309d  cmp     rcx, rax
0x1800030a0  jz      short loc_18000307B
0x1800030a2  test    byte ptr [rcx+1Ch], 1
0x1800030a6  jz      short loc_18000307B
0x1800030a8  mov     dword ptr [rsp+88h+pbOutput], 3EDh
0x1800030b0  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800030b7  mov     qword ptr [rsp+88h+cbIV], r8
0x1800030bc  mov     dword ptr [rsp+88h+pbIV], 8009002Dh
0x1800030c4  jmp     short loc_18000306B
0x1800030c6  xor     edx, edx
0x1800030c8  xor     r8d, r8d
0x1800030cb  cmp     [rsp+88h+arg_30], edx
0x1800030d2  jz      loc_180002FE5
0x1800030d8  mov     rax, [rcx+18h]
0x1800030dc  mov     r9d, [rax+48h]
0x1800030e0  jmp     loc_180002FE5
0x1800030e5  mov     rbp, [rcx+28h]
0x1800030e9  and     eax, 0FFFFFFFEh
0x1800030ec  mov     edi, [rcx+30h]
0x1800030ef  jmp     loc_180002FE2
0x1800030f4  test    edi, edi
0x1800030f6  jz      loc_180003036
0x1800030fc  test    r14, r14
0x1800030ff  jz      short loc_180003119
0x180003101  mov     ecx, [rsi]
0x180003103  lea     eax, [rcx+rdi]
0x180003106  cmp     r15d, eax
0x180003109  jb      short loc_180003120
0x18000310b  mov     r8d, edi; Size
0x18000310e  add     rcx, r14; void *
0x180003111  mov     rdx, rbp; Src
0x180003114  call    memcpy_0
0x180003119  add     [rsi], edi
0x18000311b  jmp     loc_180003036
0x180003120  mov     r9d, 425h
0x180003126  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000312d  lea     rdx, aStatus; "Status"
0x180003134  mov     ecx, 80090028h
0x180003139  mov     ebx, 80090028h
0x18000313e  call    DebugTraceError
0x180003143  jmp     loc_18000307B
```
