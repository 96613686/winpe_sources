# MSCryptEccOpenProvider

- ea: `0x18004196c`
- end: `0x180041b18`
- name: `MSCryptEccOpenProvider`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180041950`
- `0x1800765a0`

## callees

- `0x180003f70`
- `0x18000743c`
- `0x1800082b0`
- `0x18004196c`
- `0x180041b20`
- `0x180076cd4`

## string_xrefs

- `0x180041a69`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180041ac7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a3d95`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccOpenProvider(__int64 *a1, char *a2, int a3, unsigned int a4)
{
  wchar_t **v6; // r8
  unsigned int v7; // ecx
  unsigned __int16 *v8; // rax
  int v9; // r10d
  __int64 v10; // r9
  unsigned int v11; // edi
  wchar_t *v12; // rsi
  __int64 v13; // rax
  __int64 v14; // rbx
  unsigned int v15; // edi
  __int64 v17; // r9
  int Curve; // eax
  __int64 v19; // r9
  __int64 v20; // rcx

  if ( a1 && !a3 )
  {
    v6 = &off_1800A8E70;
    v7 = 0;
    if ( !a4 )
      v6 = &off_1800A8DB0;
    while ( 1 )
    {
      if ( v7 >= 4 )
        goto LABEL_24;
      v8 = (unsigned __int16 *)a2;
      do
      {
        v9 = *(unsigned __int16 *)((char *)v8 + (char *)v6[6 * v7] - a2);
        v10 = (unsigned int)*v8 - v9;
        if ( (_DWORD)v10 )
          break;
        ++v8;
      }
      while ( v9 );
      if ( !(_DWORD)v10 )
        break;
      ++v7;
    }
    v11 = (unsigned int)v6[6 * v7 + 1];
    if ( v11 )
    {
      v12 = v6[6 * v7 + 3];
      v13 = MSCryptAlloc(24, 6LL * v7, v6, v10);
      v14 = v13;
      if ( v13 )
      {
        *(_QWORD *)(v13 + 12) = 0;
        *(_DWORD *)(v13 + 20) = 0;
        *(_DWORD *)v13 = 24;
        *(_DWORD *)(v13 + 4) = 1297301836;
        *(_DWORD *)(v13 + 8) = v11;
        if ( !v12 )
          goto LABEL_14;
        v17 = -1;
        do
          ++v17;
        while ( v12[v17] );
        Curve = LoadCurve(v13 + 16, v11, v12, (unsigned int)(2 * v17 + 2));
        v15 = Curve;
        if ( Curve < 0 )
        {
          DebugTraceError(
            (unsigned int)Curve,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            2661);
          MSCryptEccCloseProvider(v14, 0, a4);
        }
        else
        {
LABEL_14:
          *a1 = v14;
          return 0;
        }
        return v15;
      }
      v15 = -1073741801;
      v19 = 2645;
      v20 = 3221225495LL;
    }
    else
    {
LABEL_24:
      v15 = -1073741637;
      v19 = 2637;
      v20 = 3221225659LL;
    }
    DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v19);
    return v15;
  }
  v15 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      54);
  return v15;
}

```

## disassembly

```asm
0x18004196c  push    rbx
0x18004196e  push    rbp
0x18004196f  push    rsi
0x180041970  push    rdi
0x180041971  push    r14
0x180041973  push    r15
0x180041975  sub     rsp, 48h
0x180041979  xor     r15d, r15d
0x18004197c  mov     ebp, r9d
0x18004197f  mov     rbx, rdx
0x180041982  mov     r14, rcx
0x180041985  test    rcx, rcx
0x180041988  jz      loc_180041A46
0x18004198e  test    r8d, r8d
0x180041991  jnz     loc_180041A46
0x180041997  test    r9d, r9d
0x18004199a  lea     rax, off_1800A8DB0; "ECDH_P256"
0x1800419a1  lea     r8, off_1800A8E70; "ECDSA_P256"
0x1800419a8  mov     ecx, r15d
0x1800419ab  cmovz   r8, rax
0x1800419af  cmp     ecx, 4
0x1800419b2  jnb     loc_180041B03
0x1800419b8  mov     eax, ecx
0x1800419ba  lea     rdx, [rax+rax*2]
0x1800419be  mov     rax, rbx
0x1800419c1  add     rdx, rdx
0x1800419c4  mov     r11, [r8+rdx*8]
0x1800419c8  sub     r11, rbx
0x1800419cb  movzx   r9d, word ptr [rax]
0x1800419cf  movzx   r10d, word ptr [rax+r11]
0x1800419d4  sub     r9d, r10d
0x1800419d7  jnz     short loc_1800419E2
0x1800419d9  add     rax, 2
0x1800419dd  test    r10d, r10d
0x1800419e0  jnz     short loc_1800419CB
0x1800419e2  test    r9d, r9d
0x1800419e5  jz      short loc_1800419EB
0x1800419e7  inc     ecx
0x1800419e9  jmp     short loc_1800419AF
0x1800419eb  mov     edi, [r8+rdx*8+8]
0x1800419f0  test    edi, edi
0x1800419f2  jz      loc_180041B03
0x1800419f8  mov     rsi, [r8+rdx*8+18h]
0x1800419fd  mov     ecx, 18h
0x180041a02  call    MSCryptAlloc
0x180041a07  mov     rbx, rax
0x180041a0a  test    rax, rax
0x180041a0d  jz      loc_180041AEE
0x180041a13  mov     [rax+0Ch], r15
0x180041a17  mov     [rax+14h], r15d
0x180041a1b  mov     dword ptr [rax], 18h
0x180041a21  mov     dword ptr [rax+4], 4D53414Ch
0x180041a28  mov     [rax+8], edi
0x180041a2b  test    rsi, rsi
0x180041a2e  jnz     short loc_180041A93
0x180041a30  mov     [r14], rbx
0x180041a33  mov     edi, r15d
0x180041a36  mov     eax, edi
0x180041a38  add     rsp, 48h
0x180041a3c  pop     r15
0x180041a3e  pop     r14
0x180041a40  pop     rdi
0x180041a41  pop     rsi
0x180041a42  pop     rbp
0x180041a43  pop     rbx
0x180041a44  retn
0x180041a46  mov     edi, 0C000000Dh
0x180041a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a52  lea     rax, WPP_GLOBAL_Control
0x180041a59  cmp     rcx, rax
0x180041a5c  jz      short loc_180041A36
0x180041a5e  mov     eax, [rcx+2Ch]
0x180041a61  test    al, 1
0x180041a63  jz      short loc_180041A36
0x180041a65  mov     rcx, [rcx+18h]
0x180041a69  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041a70  mov     [rsp+78h+var_48], 0A36h
0x180041a78  lea     r9, aStatus; "Status"
0x180041a7f  mov     [rsp+78h+var_50], rax
0x180041a84  mov     [rsp+78h+var_58], 0C000000Dh
0x180041a8c  call    WPP_SF_sDsd
0x180041a91  jmp     short loc_180041A36
0x180041a93  or      r9, 0FFFFFFFFFFFFFFFFh
0x180041a97  inc     r9
0x180041a9a  cmp     [rsi+r9*2], r15w
0x180041a9f  jnz     short loc_180041A97
0x180041aa1  lea     r9d, ds:2[r9*2]
0x180041aa9  mov     r8, rsi
0x180041aac  lea     rcx, [rax+10h]
0x180041ab0  mov     edx, edi
0x180041ab2  call    LoadCurve
0x180041ab7  mov     edi, eax
0x180041ab9  test    eax, eax
0x180041abb  jns     loc_180041A30
0x180041ac1  mov     r9d, 0A65h
0x180041ac7  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041ace  lea     rdx, aStatus; "Status"
0x180041ad5  mov     ecx, eax
0x180041ad7  call    DebugTraceError
0x180041adc  mov     r8d, ebp
0x180041adf  xor     edx, edx
0x180041ae1  mov     rcx, rbx
0x180041ae4  call    MSCryptEccCloseProvider
0x180041ae9  jmp     loc_180041A36
0x180041aee  mov     edi, 0C0000017h
0x180041af3  mov     r9d, 0A55h
0x180041af9  mov     ecx, 0C0000017h
0x180041afe  jmp     loc_1800A3D8E
0x180041b03  mov     edi, 0C00000BBh
0x180041b08  mov     r9d, 0A4Dh
0x180041b0e  mov     ecx, 0C00000BBh
0x180041b13  jmp     loc_1800A3D8E
0x1800a3d8e  lea     rdx, aStatus; "Status"
0x1800a3d95  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a3d9c  call    DebugTraceError
0x1800a3da1  nop
0x1800a3da2  jmp     loc_180041A36
```
