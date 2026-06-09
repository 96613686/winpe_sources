# ValidateEccKey

- ea: `0x180046ab8`
- end: `0x180046ccc`
- name: `ValidateEccKey`
- size: `532`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007fd50`
- `0x180080150`
- `0x180080290`
- `0x18008052c`
- `0x1800805f0`
- `0x180080840`
- `0x180080cc8`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180046ab8`

## string_xrefs

- `0x180046bab`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800a832e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

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
    v7 = byte_1800ADE78;
    if ( !a2 )
      v7 = byte_1800ADDB8;
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
  v8 = &dword_1800ADE84;
  if ( !a2 )
    v8 = &dword_1800ADDC4;
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
0x180046ab8  mov     [rsp+arg_0], rbx
0x180046abd  push    rdi
0x180046abe  sub     rsp, 40h
0x180046ac2  mov     ebx, edx
0x180046ac4  mov     r10, rcx
0x180046ac7  test    rcx, rcx
0x180046aca  jz      loc_180046BCD
0x180046ad0  mov     r11, [rsp+48h+arg_20]
0x180046ad5  test    r11, r11
0x180046ad8  jz      loc_180046BCD
0x180046ade  cmp     dword ptr [rcx+4], 4D534B59h
0x180046ae5  jnz     loc_180046B80
0x180046aeb  test    r9d, r9d
0x180046aee  jz      short loc_180046AFB
0x180046af0  cmp     qword ptr [rcx+10h], 0
0x180046af5  jz      loc_180046C71
0x180046afb  xor     ecx, ecx
0x180046afd  cmp     ecx, 4
0x180046b00  jnb     loc_180046CC1
0x180046b06  lea     rdx, [rcx+rcx*2]
0x180046b0a  add     rdx, rdx
0x180046b0d  lea     rdi, byte_1800ADDB8
0x180046b14  test    ebx, ebx
0x180046b16  lea     rax, byte_1800ADE78
0x180046b1d  cmovz   rax, rdi
0x180046b21  mov     eax, [rax+rdx*8]
0x180046b24  cmp     [r10+8], eax
0x180046b28  jnz     loc_180046BF6
0x180046b2e  test    r9d, r9d
0x180046b31  jz      short loc_180046B64
0x180046b33  test    ebx, ebx
0x180046b35  lea     rcx, dword_1800ADDC4
0x180046b3c  lea     rax, dword_1800ADE84
0x180046b43  cmovz   rax, rcx
0x180046b47  mov     edx, [rax+rdx*8]
0x180046b4a  mov     rax, [r10+10h]
0x180046b4e  mov     rcx, [rax]
0x180046b51  mov     eax, [rcx+0Ch]
0x180046b54  test    edx, edx
0x180046b56  jz      loc_180046C31
0x180046b5c  cmp     edx, eax
0x180046b5e  jnz     loc_180046BFD
0x180046b64  test    r8d, r8d
0x180046b67  jnz     loc_180046CA5
0x180046b6d  mov     [r11], r10
0x180046b70  xor     ebx, ebx
0x180046b72  mov     eax, ebx
0x180046b74  mov     rbx, [rsp+48h+arg_0]
0x180046b79  add     rsp, 40h
0x180046b7d  pop     rdi
0x180046b7e  retn
0x180046b80  mov     ebx, 0C000000Dh
0x180046b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b8c  lea     rax, WPP_GLOBAL_Control
0x180046b93  cmp     rcx, rax
0x180046b96  jz      short loc_180046B72
0x180046b98  mov     eax, [rcx+2Ch]
0x180046b9b  test    al, 1
0x180046b9d  jz      short loc_180046B72
0x180046b9f  mov     [rsp+48h+var_18], 23Ch
0x180046ba7  mov     rcx, [rcx+18h]
0x180046bab  lea     rax, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046bb2  mov     [rsp+48h+var_20], rax
0x180046bb7  lea     r9, aStatus; "Status"
0x180046bbe  mov     [rsp+48h+var_28], 0C000000Dh
0x180046bc6  call    WPP_SF_sDsd
0x180046bcb  jmp     short loc_180046B72
0x180046bcd  mov     ebx, 0C000000Dh
0x180046bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180046bd9  lea     rax, WPP_GLOBAL_Control
0x180046be0  cmp     rcx, rax
0x180046be3  jz      short loc_180046B72
0x180046be5  mov     eax, [rcx+2Ch]
0x180046be8  test    al, 1
0x180046bea  jz      short loc_180046B72
0x180046bec  mov     [rsp+48h+var_18], 233h
0x180046bf4  jmp     short loc_180046BA7
0x180046bf6  inc     ecx
0x180046bf8  jmp     loc_180046AFD
0x180046bfd  mov     ebx, 0C000000Dh
0x180046c02  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c09  lea     rax, WPP_GLOBAL_Control
0x180046c10  cmp     rcx, rax
0x180046c13  jz      loc_180046B72
0x180046c19  mov     eax, [rcx+2Ch]
0x180046c1c  test    al, 1
0x180046c1e  jz      loc_180046B72
0x180046c24  mov     [rsp+48h+var_18], 265h
0x180046c2c  jmp     loc_180046BA7
0x180046c31  add     eax, 0FFFFFFF2h
0x180046c34  cmp     eax, 34h ; '4'
0x180046c37  jbe     loc_180046B64
0x180046c3d  mov     ebx, 0C000000Dh
0x180046c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c49  lea     rax, WPP_GLOBAL_Control
0x180046c50  cmp     rcx, rax
0x180046c53  jz      loc_180046B72
0x180046c59  mov     eax, [rcx+2Ch]
0x180046c5c  test    al, 1
0x180046c5e  jz      loc_180046B72
0x180046c64  mov     [rsp+48h+var_18], 25Bh
0x180046c6c  jmp     loc_180046BA7
0x180046c71  mov     ebx, 0C000000Dh
0x180046c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c7d  lea     rax, WPP_GLOBAL_Control
0x180046c84  cmp     rcx, rax
0x180046c87  jz      loc_180046B72
0x180046c8d  mov     eax, [rcx+2Ch]
0x180046c90  test    al, 1
0x180046c92  jz      loc_180046B72
0x180046c98  mov     [rsp+48h+var_18], 243h
0x180046ca0  jmp     loc_180046BA7
0x180046ca5  mov     rax, [r10+18h]
0x180046ca9  test    rax, rax
0x180046cac  jz      loc_1800A8328
0x180046cb2  cmp     byte ptr [rax+4], 0
0x180046cb6  jnz     loc_180046B6D
0x180046cbc  jmp     loc_1800A8328
0x180046cc1  mov     r9d, 274h
0x180046cc7  jmp     loc_1800A832E
0x1800a8328  mov     r9d, 27Dh
0x1800a832e  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8335  mov     ecx, 0C000000Dh
0x1800a833a  lea     rdx, aStatus; "Status"
0x1800a8341  mov     ebx, 0C000000Dh
0x1800a8346  call    DebugTraceError
0x1800a834b  nop
0x1800a834c  jmp     loc_180046B72
```
