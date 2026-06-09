# MSCryptEccOpenProvider

- ea: `0x18004adbc`
- end: `0x18004af68`
- name: `MSCryptEccOpenProvider`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004ada0`
- `0x18007fd30`

## callees

- `0x18000e090`
- `0x18001155c`
- `0x1800123d0`
- `0x18004adbc`
- `0x18004af70`
- `0x180080464`

## string_xrefs

- `0x18004aeb9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004af17`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a8d03`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccOpenProvider(__int64 *a1, char *a2, int a3, unsigned int a4)
{
  wchar_t **v6; // r8
  unsigned int v7; // ecx
  unsigned __int16 *v8; // rax
  int v9; // r10d
  int v10; // r9d
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
    v6 = &off_1800ADE70;
    v7 = 0;
    if ( !a4 )
      v6 = &off_1800ADDB0;
    while ( 1 )
    {
      if ( v7 >= 4 )
        goto LABEL_24;
      v8 = (unsigned __int16 *)a2;
      do
      {
        v9 = *(unsigned __int16 *)((char *)v8 + (char *)v6[6 * v7] - a2);
        v10 = *v8 - v9;
        if ( v10 )
          break;
        ++v8;
      }
      while ( v9 );
      if ( !v10 )
        break;
      ++v7;
    }
    v11 = (unsigned int)v6[6 * v7 + 1];
    if ( v11 )
    {
      v12 = v6[6 * v7 + 3];
      v13 = MSCryptAlloc(24, 6LL * v7);
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
0x18004adbc  push    rbx
0x18004adbe  push    rbp
0x18004adbf  push    rsi
0x18004adc0  push    rdi
0x18004adc1  push    r14
0x18004adc3  push    r15
0x18004adc5  sub     rsp, 48h
0x18004adc9  xor     r15d, r15d
0x18004adcc  mov     ebp, r9d
0x18004adcf  mov     rbx, rdx
0x18004add2  mov     r14, rcx
0x18004add5  test    rcx, rcx
0x18004add8  jz      loc_18004AE96
0x18004adde  test    r8d, r8d
0x18004ade1  jnz     loc_18004AE96
0x18004ade7  test    r9d, r9d
0x18004adea  lea     rax, off_1800ADDB0; "ECDH_P256"
0x18004adf1  lea     r8, off_1800ADE70; "ECDSA_P256"
0x18004adf8  mov     ecx, r15d
0x18004adfb  cmovz   r8, rax
0x18004adff  cmp     ecx, 4
0x18004ae02  jnb     loc_18004AF53
0x18004ae08  mov     eax, ecx
0x18004ae0a  lea     rdx, [rax+rax*2]
0x18004ae0e  mov     rax, rbx
0x18004ae11  add     rdx, rdx
0x18004ae14  mov     r11, [r8+rdx*8]
0x18004ae18  sub     r11, rbx
0x18004ae1b  movzx   r9d, word ptr [rax]
0x18004ae1f  movzx   r10d, word ptr [rax+r11]
0x18004ae24  sub     r9d, r10d
0x18004ae27  jnz     short loc_18004AE32
0x18004ae29  add     rax, 2
0x18004ae2d  test    r10d, r10d
0x18004ae30  jnz     short loc_18004AE1B
0x18004ae32  test    r9d, r9d
0x18004ae35  jz      short loc_18004AE3B
0x18004ae37  inc     ecx
0x18004ae39  jmp     short loc_18004ADFF
0x18004ae3b  mov     edi, [r8+rdx*8+8]
0x18004ae40  test    edi, edi
0x18004ae42  jz      loc_18004AF53
0x18004ae48  mov     rsi, [r8+rdx*8+18h]
0x18004ae4d  mov     ecx, 18h
0x18004ae52  call    MSCryptAlloc
0x18004ae57  mov     rbx, rax
0x18004ae5a  test    rax, rax
0x18004ae5d  jz      loc_18004AF3E
0x18004ae63  mov     [rax+0Ch], r15
0x18004ae67  mov     [rax+14h], r15d
0x18004ae6b  mov     dword ptr [rax], 18h
0x18004ae71  mov     dword ptr [rax+4], 4D53414Ch
0x18004ae78  mov     [rax+8], edi
0x18004ae7b  test    rsi, rsi
0x18004ae7e  jnz     short loc_18004AEE3
0x18004ae80  mov     [r14], rbx
0x18004ae83  mov     edi, r15d
0x18004ae86  mov     eax, edi
0x18004ae88  add     rsp, 48h
0x18004ae8c  pop     r15
0x18004ae8e  pop     r14
0x18004ae90  pop     rdi
0x18004ae91  pop     rsi
0x18004ae92  pop     rbp
0x18004ae93  pop     rbx
0x18004ae94  retn
0x18004ae96  mov     edi, 0C000000Dh
0x18004ae9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aea2  lea     rax, WPP_GLOBAL_Control
0x18004aea9  cmp     rcx, rax
0x18004aeac  jz      short loc_18004AE86
0x18004aeae  mov     eax, [rcx+2Ch]
0x18004aeb1  test    al, 1
0x18004aeb3  jz      short loc_18004AE86
0x18004aeb5  mov     rcx, [rcx+18h]
0x18004aeb9  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004aec0  mov     [rsp+78h+var_48], 0A36h
0x18004aec8  lea     r9, aStatus; "Status"
0x18004aecf  mov     [rsp+78h+var_50], rax
0x18004aed4  mov     [rsp+78h+var_58], 0C000000Dh
0x18004aedc  call    WPP_SF_sDsd
0x18004aee1  jmp     short loc_18004AE86
0x18004aee3  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004aee7  inc     r9
0x18004aeea  cmp     [rsi+r9*2], r15w
0x18004aeef  jnz     short loc_18004AEE7
0x18004aef1  lea     r9d, ds:2[r9*2]
0x18004aef9  mov     r8, rsi
0x18004aefc  lea     rcx, [rax+10h]
0x18004af00  mov     edx, edi
0x18004af02  call    LoadCurve
0x18004af07  mov     edi, eax
0x18004af09  test    eax, eax
0x18004af0b  jns     loc_18004AE80
0x18004af11  mov     r9d, 0A65h
0x18004af17  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004af1e  lea     rdx, aStatus; "Status"
0x18004af25  mov     ecx, eax
0x18004af27  call    DebugTraceError
0x18004af2c  mov     r8d, ebp
0x18004af2f  xor     edx, edx
0x18004af31  mov     rcx, rbx
0x18004af34  call    MSCryptEccCloseProvider
0x18004af39  jmp     loc_18004AE86
0x18004af3e  mov     edi, 0C0000017h
0x18004af43  mov     r9d, 0A55h
0x18004af49  mov     ecx, 0C0000017h
0x18004af4e  jmp     loc_1800A8CFC
0x18004af53  mov     edi, 0C00000BBh
0x18004af58  mov     r9d, 0A4Dh
0x18004af5e  mov     ecx, 0C00000BBh
0x18004af63  jmp     loc_1800A8CFC
0x1800a8cfc  lea     rdx, aStatus; "Status"
0x1800a8d03  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8d0a  call    DebugTraceError
0x1800a8d0f  nop
0x1800a8d10  jmp     loc_18004AE86
```
