# ValidateEccKey

- ea: `0x18003caf8`
- end: `0x18003cd0c`
- name: `ValidateEccKey`
- size: `532`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180075bb0`
- `0x180075fb0`
- `0x1800760f0`
- `0x18007638c`
- `0x180076450`
- `0x1800766a0`
- `0x180076b28`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18003caf8`

## string_xrefs

- `0x18003cbeb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a1590`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ValidateEccKey(__int64 a1, int a2, int a3, int a4, _QWORD *a5)
{
  __int64 i; // rcx
  char *v7; // rax
  int *v8; // rax
  int v9; // edx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v13; // rax
  __int64 v14; // r9

  if ( !a1 || !a5 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
    return v11;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        60);
    return v11;
  }
  if ( a4 && !*(_QWORD *)(a1 + 16) )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        67);
    return v11;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
    {
      v14 = 628;
LABEL_42:
      v11 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v14);
      return v11;
    }
    v7 = byte_1800A6E78;
    if ( !a2 )
      v7 = byte_1800A6DB8;
    if ( *(_DWORD *)(a1 + 8) == *(_DWORD *)&v7[48 * i] )
      break;
  }
  if ( !a4 )
  {
LABEL_16:
    if ( !a3 || (v13 = *(_QWORD *)(a1 + 24)) != 0 && *(_BYTE *)(v13 + 4) )
    {
      *a5 = a1;
      return 0;
    }
    v14 = 637;
    goto LABEL_42;
  }
  v8 = &dword_1800A6E84;
  if ( !a2 )
    v8 = &dword_1800A6DC4;
  v9 = v8[12 * i];
  v10 = *(_DWORD *)(**(_QWORD **)(a1 + 16) + 12LL);
  if ( v9 )
  {
    if ( v9 == v10 )
      goto LABEL_16;
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v9,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        101);
  }
  else
  {
    if ( (unsigned int)(v10 - 14) <= 0x34 )
      goto LABEL_16;
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        0,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        91);
  }
  return v11;
}

```

## disassembly

```asm
0x18003caf8  mov     [rsp+arg_0], rbx
0x18003cafd  push    rdi
0x18003cafe  sub     rsp, 40h
0x18003cb02  mov     ebx, edx
0x18003cb04  mov     r10, rcx
0x18003cb07  test    rcx, rcx
0x18003cb0a  jz      loc_18003CC0D
0x18003cb10  mov     r11, [rsp+48h+arg_20]
0x18003cb15  test    r11, r11
0x18003cb18  jz      loc_18003CC0D
0x18003cb1e  cmp     dword ptr [rcx+4], 4D534B59h
0x18003cb25  jnz     loc_18003CBC0
0x18003cb2b  test    r9d, r9d
0x18003cb2e  jz      short loc_18003CB3B
0x18003cb30  cmp     qword ptr [rcx+10h], 0
0x18003cb35  jz      loc_18003CCB1
0x18003cb3b  xor     ecx, ecx
0x18003cb3d  cmp     ecx, 4
0x18003cb40  jnb     loc_18003CD01
0x18003cb46  lea     rdx, [rcx+rcx*2]
0x18003cb4a  add     rdx, rdx
0x18003cb4d  lea     rdi, byte_1800A6DB8
0x18003cb54  test    ebx, ebx
0x18003cb56  lea     rax, byte_1800A6E78
0x18003cb5d  cmovz   rax, rdi
0x18003cb61  mov     eax, [rax+rdx*8]
0x18003cb64  cmp     [r10+8], eax
0x18003cb68  jnz     loc_18003CC36
0x18003cb6e  test    r9d, r9d
0x18003cb71  jz      short loc_18003CBA4
0x18003cb73  test    ebx, ebx
0x18003cb75  lea     rcx, dword_1800A6DC4
0x18003cb7c  lea     rax, dword_1800A6E84
0x18003cb83  cmovz   rax, rcx
0x18003cb87  mov     edx, [rax+rdx*8]
0x18003cb8a  mov     rax, [r10+10h]
0x18003cb8e  mov     rcx, [rax]
0x18003cb91  mov     eax, [rcx+0Ch]
0x18003cb94  test    edx, edx
0x18003cb96  jz      loc_18003CC71
0x18003cb9c  cmp     edx, eax
0x18003cb9e  jnz     loc_18003CC3D
0x18003cba4  test    r8d, r8d
0x18003cba7  jnz     loc_18003CCE5
0x18003cbad  mov     [r11], r10
0x18003cbb0  xor     ebx, ebx
0x18003cbb2  mov     eax, ebx
0x18003cbb4  mov     rbx, [rsp+48h+arg_0]
0x18003cbb9  add     rsp, 40h
0x18003cbbd  pop     rdi
0x18003cbbe  retn
0x18003cbc0  mov     ebx, 0C000000Dh
0x18003cbc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cbcc  lea     rax, WPP_GLOBAL_Control
0x18003cbd3  cmp     rcx, rax
0x18003cbd6  jz      short loc_18003CBB2
0x18003cbd8  mov     eax, [rcx+2Ch]
0x18003cbdb  test    al, 1
0x18003cbdd  jz      short loc_18003CBB2
0x18003cbdf  mov     [rsp+48h+var_18], 23Ch
0x18003cbe7  mov     rcx, [rcx+18h]
0x18003cbeb  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003cbf2  mov     [rsp+48h+var_20], rax
0x18003cbf7  lea     r9, aStatus; "Status"
0x18003cbfe  mov     [rsp+48h+var_28], 0C000000Dh
0x18003cc06  call    WPP_SF_sDsd
0x18003cc0b  jmp     short loc_18003CBB2
0x18003cc0d  mov     ebx, 0C000000Dh
0x18003cc12  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc19  lea     rax, WPP_GLOBAL_Control
0x18003cc20  cmp     rcx, rax
0x18003cc23  jz      short loc_18003CBB2
0x18003cc25  mov     eax, [rcx+2Ch]
0x18003cc28  test    al, 1
0x18003cc2a  jz      short loc_18003CBB2
0x18003cc2c  mov     [rsp+48h+var_18], 233h
0x18003cc34  jmp     short loc_18003CBE7
0x18003cc36  inc     ecx
0x18003cc38  jmp     loc_18003CB3D
0x18003cc3d  mov     ebx, 0C000000Dh
0x18003cc42  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc49  lea     rax, WPP_GLOBAL_Control
0x18003cc50  cmp     rcx, rax
0x18003cc53  jz      loc_18003CBB2
0x18003cc59  mov     eax, [rcx+2Ch]
0x18003cc5c  test    al, 1
0x18003cc5e  jz      loc_18003CBB2
0x18003cc64  mov     [rsp+48h+var_18], 265h
0x18003cc6c  jmp     loc_18003CBE7
0x18003cc71  add     eax, 0FFFFFFF2h
0x18003cc74  cmp     eax, 34h ; '4'
0x18003cc77  jbe     loc_18003CBA4
0x18003cc7d  mov     ebx, 0C000000Dh
0x18003cc82  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc89  lea     rax, WPP_GLOBAL_Control
0x18003cc90  cmp     rcx, rax
0x18003cc93  jz      loc_18003CBB2
0x18003cc99  mov     eax, [rcx+2Ch]
0x18003cc9c  test    al, 1
0x18003cc9e  jz      loc_18003CBB2
0x18003cca4  mov     [rsp+48h+var_18], 25Bh
0x18003ccac  jmp     loc_18003CBE7
0x18003ccb1  mov     ebx, 0C000000Dh
0x18003ccb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ccbd  lea     rax, WPP_GLOBAL_Control
0x18003ccc4  cmp     rcx, rax
0x18003ccc7  jz      loc_18003CBB2
0x18003cccd  mov     eax, [rcx+2Ch]
0x18003ccd0  test    al, 1
0x18003ccd2  jz      loc_18003CBB2
0x18003ccd8  mov     [rsp+48h+var_18], 243h
0x18003cce0  jmp     loc_18003CBE7
0x18003cce5  mov     rax, [r10+18h]
0x18003cce9  test    rax, rax
0x18003ccec  jz      loc_1800A158A
0x18003ccf2  cmp     byte ptr [rax+4], 0
0x18003ccf6  jnz     loc_18003CBAD
0x18003ccfc  jmp     loc_1800A158A
0x18003cd01  mov     r9d, 274h
0x18003cd07  jmp     loc_1800A1590
0x1800a158a  mov     r9d, 27Dh
0x1800a1590  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a1597  mov     ecx, 0C000000Dh
0x1800a159c  lea     rdx, aStatus; "Status"
0x1800a15a3  mov     ebx, 0C000000Dh
0x1800a15a8  call    DebugTraceError
0x1800a15ad  nop
0x1800a15ae  jmp     loc_18003CBB2
```
