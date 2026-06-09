# MSCryptEccOpenProvider

- ea: `0x180040ddc`
- end: `0x180040f88`
- name: `MSCryptEccOpenProvider`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180040dc0`
- `0x180075b90`

## callees

- `0x180003f70`
- `0x18000743c`
- `0x1800082b0`
- `0x180040ddc`
- `0x180040f90`
- `0x1800762c4`

## string_xrefs

- `0x180040ed9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180040f37`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a1f65`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccOpenProvider(__int64 *a1, char *a2, int a3, unsigned int a4)
{
  wchar_t **v6; // r8
  unsigned int v7; // ecx
  unsigned __int16 *v8; // rax
  int v9; // r10d
  int v10; // r9d
  int v11; // edi
  const wchar_t *v12; // rsi
  __int64 v13; // rax
  __int64 v14; // rbx
  unsigned int v15; // edi
  __int64 v17; // r9
  int Curve; // eax
  __int64 v19; // r9
  __int64 v20; // rcx

  if ( a1 && !a3 )
  {
    v6 = &off_1800A6E70;
    v7 = 0;
    if ( !a4 )
      v6 = &off_1800A6DB0;
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
    v11 = (int)v6[6 * v7 + 1];
    if ( v11 )
    {
      v12 = v6[6 * v7 + 3];
      v13 = MSCryptAlloc(24);
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
        Curve = LoadCurve((_QWORD *)(v13 + 16), v11, v12, 2 * (int)v17 + 2);
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
0x180040ddc  push    rbx
0x180040dde  push    rbp
0x180040ddf  push    rsi
0x180040de0  push    rdi
0x180040de1  push    r14
0x180040de3  push    r15
0x180040de5  sub     rsp, 48h
0x180040de9  xor     r15d, r15d
0x180040dec  mov     ebp, r9d
0x180040def  mov     rbx, rdx
0x180040df2  mov     r14, rcx
0x180040df5  test    rcx, rcx
0x180040df8  jz      loc_180040EB6
0x180040dfe  test    r8d, r8d
0x180040e01  jnz     loc_180040EB6
0x180040e07  test    r9d, r9d
0x180040e0a  lea     rax, off_1800A6DB0; "ECDH_P256"
0x180040e11  lea     r8, off_1800A6E70; "ECDSA_P256"
0x180040e18  mov     ecx, r15d
0x180040e1b  cmovz   r8, rax
0x180040e1f  cmp     ecx, 4
0x180040e22  jnb     loc_180040F73
0x180040e28  mov     eax, ecx
0x180040e2a  lea     rdx, [rax+rax*2]
0x180040e2e  mov     rax, rbx
0x180040e31  add     rdx, rdx
0x180040e34  mov     r11, [r8+rdx*8]
0x180040e38  sub     r11, rbx
0x180040e3b  movzx   r9d, word ptr [rax]
0x180040e3f  movzx   r10d, word ptr [rax+r11]
0x180040e44  sub     r9d, r10d
0x180040e47  jnz     short loc_180040E52
0x180040e49  add     rax, 2
0x180040e4d  test    r10d, r10d
0x180040e50  jnz     short loc_180040E3B
0x180040e52  test    r9d, r9d
0x180040e55  jz      short loc_180040E5B
0x180040e57  inc     ecx
0x180040e59  jmp     short loc_180040E1F
0x180040e5b  mov     edi, [r8+rdx*8+8]
0x180040e60  test    edi, edi
0x180040e62  jz      loc_180040F73
0x180040e68  mov     rsi, [r8+rdx*8+18h]
0x180040e6d  mov     ecx, 18h
0x180040e72  call    MSCryptAlloc
0x180040e77  mov     rbx, rax
0x180040e7a  test    rax, rax
0x180040e7d  jz      loc_180040F5E
0x180040e83  mov     [rax+0Ch], r15
0x180040e87  mov     [rax+14h], r15d
0x180040e8b  mov     dword ptr [rax], 18h
0x180040e91  mov     dword ptr [rax+4], 4D53414Ch
0x180040e98  mov     [rax+8], edi
0x180040e9b  test    rsi, rsi
0x180040e9e  jnz     short loc_180040F03
0x180040ea0  mov     [r14], rbx
0x180040ea3  mov     edi, r15d
0x180040ea6  mov     eax, edi
0x180040ea8  add     rsp, 48h
0x180040eac  pop     r15
0x180040eae  pop     r14
0x180040eb0  pop     rdi
0x180040eb1  pop     rsi
0x180040eb2  pop     rbp
0x180040eb3  pop     rbx
0x180040eb4  retn
0x180040eb6  mov     edi, 0C000000Dh
0x180040ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ec2  lea     rax, WPP_GLOBAL_Control
0x180040ec9  cmp     rcx, rax
0x180040ecc  jz      short loc_180040EA6
0x180040ece  mov     eax, [rcx+2Ch]
0x180040ed1  test    al, 1
0x180040ed3  jz      short loc_180040EA6
0x180040ed5  mov     rcx, [rcx+18h]
0x180040ed9  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040ee0  mov     [rsp+78h+var_48], 0A36h
0x180040ee8  lea     r9, aStatus; "Status"
0x180040eef  mov     [rsp+78h+var_50], rax
0x180040ef4  mov     [rsp+78h+var_58], 0C000000Dh
0x180040efc  call    WPP_SF_sDsd
0x180040f01  jmp     short loc_180040EA6
0x180040f03  or      r9, 0FFFFFFFFFFFFFFFFh
0x180040f07  inc     r9
0x180040f0a  cmp     [rsi+r9*2], r15w
0x180040f0f  jnz     short loc_180040F07
0x180040f11  lea     r9d, ds:2[r9*2]
0x180040f19  mov     r8, rsi
0x180040f1c  lea     rcx, [rax+10h]
0x180040f20  mov     edx, edi
0x180040f22  call    LoadCurve
0x180040f27  mov     edi, eax
0x180040f29  test    eax, eax
0x180040f2b  jns     loc_180040EA0
0x180040f31  mov     r9d, 0A65h
0x180040f37  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180040f3e  lea     rdx, aStatus; "Status"
0x180040f45  mov     ecx, eax
0x180040f47  call    DebugTraceError
0x180040f4c  mov     r8d, ebp
0x180040f4f  xor     edx, edx
0x180040f51  mov     rcx, rbx
0x180040f54  call    MSCryptEccCloseProvider
0x180040f59  jmp     loc_180040EA6
0x180040f5e  mov     edi, 0C0000017h
0x180040f63  mov     r9d, 0A55h
0x180040f69  mov     ecx, 0C0000017h
0x180040f6e  jmp     loc_1800A1F5E
0x180040f73  mov     edi, 0C00000BBh
0x180040f78  mov     r9d, 0A4Dh
0x180040f7e  mov     ecx, 0C00000BBh
0x180040f83  jmp     loc_1800A1F5E
0x1800a1f5e  lea     rdx, aStatus; "Status"
0x1800a1f65  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1f6c  call    DebugTraceError
0x1800a1f71  nop
0x1800a1f72  jmp     loc_180040EA6
```
