# CMSG_AddRecipient

- ea: `0x180003f1c`
- end: `0x180004235`
- name: `CMSG_AddRecipient`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003150`

## callees

- `0x180003f1c`
- `0x18000423c`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`
- `0x180020010`

## import_xrefs

- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180003f7d`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180003f7d`
- `NTASN1!__imp_RtlAsn1Decode` at `0x180003fc8`
- `NTASN1!__imp_RtlAsn1Decode` at `0x180004027`
- `NTASN1!__imp_RtlAsn1Decode` at `0x180003fc8`
- `NTASN1!__imp_RtlAsn1Decode` at `0x180004027`

## string_xrefs

- `0x18000413c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`
- `0x1800041ba`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`

## pseudocode

```c
__int64 __fastcall CMSG_AddRecipient(__int64 a1, __int64 a2)
{
  unsigned int Buffer; // eax
  unsigned int v4; // ebx
  int v5; // edx
  _OWORD *v6; // rsi
  int v7; // edx
  int v8; // eax
  __int64 v9; // rdx
  int v10; // edx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v14; // r9
  const void *v15; // r15
  __int64 v16; // rax
  _OWORD *v17; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+80h] [rbp+30h] BYREF
  __int64 v19; // [rsp+90h] [rbp+40h] BYREF
  __int64 v20; // [rsp+98h] [rbp+48h] BYREF

  v17 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  Buffer = RtlAsn1EncodeAndAllocate(ASN1_NCRYPT_MODULE_HANDLE, 22, 0, a1 + 16, &v18, &v20, a2);
  v4 = Buffer;
  if ( Buffer )
  {
    v14 = 188;
LABEL_23:
    DebugTraceError(Buffer, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c", v14);
    goto LABEL_8;
  }
  Buffer = RtlAsn1Decode(ASN1_NCRYPT_MODULE_HANDLE, 22, 0x200000, v18, v20, 0, 0, &v19, v17);
  v4 = Buffer;
  if ( Buffer )
  {
    v14 = 204;
    goto LABEL_23;
  }
  v4 = CMSG_AllocateBuffer(a1, v19, &v17);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
        (unsigned int)"Status",
        v4,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
        215);
    goto LABEL_8;
  }
  v6 = v17;
  v4 = RtlAsn1Decode(ASN1_NCRYPT_MODULE_HANDLE, 22, 0x200000, v18, v20, 0, v17, &v19, v17);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
        (unsigned int)"Status",
        v4,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
        231);
    goto LABEL_8;
  }
  v8 = *(_DWORD *)(a1 + 264);
  v9 = (v8 & 0xFFFFFFC0) + 64;
  if ( v8 )
  {
    if ( v8 + 1 < (unsigned int)v9 )
      goto LABEL_7;
    v15 = *(const void **)(a1 + 272);
    Buffer = CMSG_AllocateBuffer(a1, 160LL * ((v8 & 0xFFFFFFC0) + 128), a1 + 272);
    v4 = Buffer;
    if ( !Buffer )
    {
      v16 = *(unsigned int *)(a1 + 264);
      if ( (_DWORD)v16 )
        memcpy_0(*(void **)(a1 + 272), v15, 160 * v16);
      goto LABEL_7;
    }
    v14 = 269;
    goto LABEL_23;
  }
  v4 = CMSG_AllocateBuffer(a1, 160 * v9, a1 + 272);
  if ( !v4 )
  {
LABEL_7:
    v11 = *(_QWORD *)(a1 + 272);
    v12 = 160LL * *(unsigned int *)(a1 + 264);
    *(_OWORD *)(v12 + v11) = *v6;
    *(_OWORD *)(v12 + v11 + 16) = v6[1];
    *(_OWORD *)(v12 + v11 + 32) = v6[2];
    *(_OWORD *)(v12 + v11 + 48) = v6[3];
    *(_OWORD *)(v12 + v11 + 64) = v6[4];
    *(_OWORD *)(v12 + v11 + 80) = v6[5];
    *(_OWORD *)(v12 + v11 + 96) = v6[6];
    *(_OWORD *)(v12 + v11 + 112) = v6[7];
    *(_OWORD *)(v12 + v11 + 128) = v6[8];
    *(_OWORD *)(v12 + v11 + 144) = v6[9];
    ++*(_DWORD *)(a1 + 264);
    v4 = 0;
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
      (unsigned int)"Status",
      v4,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
      250);
LABEL_8:
  if ( v18 )
    (*(void (**)(void))(a1 + 32))();
  return v4;
}

```

## disassembly

```asm
0x180003f1c  mov     r11, rsp
0x180003f1f  mov     [r11+10h], rbx
0x180003f23  push    rbp
0x180003f24  push    rsi
0x180003f25  push    rdi
0x180003f26  push    r14
0x180003f28  push    r15
0x180003f2a  mov     rbp, rsp
0x180003f2d  sub     rsp, 50h
0x180003f31  mov     [r11-48h], rdx
0x180003f35  lea     rax, [rbp+arg_18]
0x180003f39  mov     [r11-50h], rax
0x180003f3d  lea     r9, [rcx+10h]
0x180003f41  xor     r8d, r8d
0x180003f44  mov     [rbp+var_10], 0
0x180003f4c  mov     rdi, rcx
0x180003f4f  mov     [rbp+arg_10], 0
0x180003f57  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180003f5e  lea     rax, [rbp+arg_0]
0x180003f62  mov     [rbp+arg_0], 0
0x180003f6a  lea     r14d, [r8+16h]
0x180003f6e  mov     [rbp+arg_18], 0
0x180003f76  mov     edx, r14d
0x180003f79  mov     [r11-58h], rax
0x180003f7d  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x180003f83  mov     ebx, eax
0x180003f85  test    eax, eax
0x180003f87  jnz     loc_1800041AC
0x180003f8d  mov     r9, [rbp+arg_0]
0x180003f91  lea     rax, [rbp+arg_10]
0x180003f95  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180003f9c  mov     r15d, 200000h
0x180003fa2  mov     [rsp+50h+var_18], rax
0x180003fa7  mov     r8d, r15d
0x180003faa  mov     rax, [rbp+arg_18]
0x180003fae  mov     edx, r14d
0x180003fb1  mov     [rsp+50h+var_20], 0
0x180003fba  mov     [rsp+50h+var_28], 0
0x180003fc3  mov     [rsp+50h+var_30], rax
0x180003fc8  call    cs:__imp_RtlAsn1Decode
0x180003fce  mov     ebx, eax
0x180003fd0  test    eax, eax
0x180003fd2  jnz     loc_1800041D4
0x180003fd8  mov     rdx, [rbp+arg_10]
0x180003fdc  lea     r8, [rbp+var_10]
0x180003fe0  mov     rcx, rdi
0x180003fe3  call    CMSG_AllocateBuffer
0x180003fe8  mov     ebx, eax
0x180003fea  test    eax, eax
0x180003fec  jnz     loc_18000415A
0x180003ff2  mov     rsi, [rbp+var_10]
0x180003ff6  lea     rax, [rbp+arg_10]
0x180003ffa  mov     r9, [rbp+arg_0]
0x180003ffe  mov     r8d, r15d
0x180004001  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180004008  mov     edx, r14d
0x18000400b  mov     [rsp+50h+var_18], rax
0x180004010  mov     rax, [rbp+arg_18]
0x180004014  mov     [rsp+50h+var_20], rsi
0x180004019  mov     [rsp+50h+var_28], 0
0x180004022  mov     [rsp+50h+var_30], rax
0x180004027  call    cs:__imp_RtlAsn1Decode
0x18000402d  mov     ebx, eax
0x18000402f  test    eax, eax
0x180004031  jnz     loc_180004181
0x180004037  mov     eax, [rdi+108h]
0x18000403d  mov     ecx, eax
0x18000403f  and     ecx, 0FFFFFFC0h
0x180004042  lea     edx, [rcx+40h]
0x180004045  test    eax, eax
0x180004047  jnz     loc_1800041DC
0x18000404d  lea     rdx, [rdx+rdx*4]
0x180004051  mov     rcx, rdi
0x180004054  shl     rdx, 5
0x180004058  lea     r8, [rdi+110h]
0x18000405f  call    CMSG_AllocateBuffer
0x180004064  mov     ebx, eax
0x180004066  test    eax, eax
0x180004068  jnz     loc_180004117
0x18000406e  mov     eax, [rdi+108h]
0x180004074  movups  xmm0, xmmword ptr [rsi]
0x180004077  lea     rcx, [rax+rax*4]
0x18000407b  mov     rax, [rdi+110h]
0x180004082  shl     rcx, 5
0x180004086  movups  xmmword ptr [rcx+rax], xmm0
0x18000408a  movups  xmm1, xmmword ptr [rsi+10h]
0x18000408e  movups  xmmword ptr [rcx+rax+10h], xmm1
0x180004093  movups  xmm0, xmmword ptr [rsi+20h]
0x180004097  movups  xmmword ptr [rcx+rax+20h], xmm0
0x18000409c  movups  xmm1, xmmword ptr [rsi+30h]
0x1800040a0  movups  xmmword ptr [rcx+rax+30h], xmm1
0x1800040a5  movups  xmm0, xmmword ptr [rsi+40h]
0x1800040a9  movups  xmmword ptr [rcx+rax+40h], xmm0
0x1800040ae  movups  xmm1, xmmword ptr [rsi+50h]
0x1800040b2  movups  xmmword ptr [rcx+rax+50h], xmm1
0x1800040b7  movups  xmm0, xmmword ptr [rsi+60h]
0x1800040bb  movups  xmmword ptr [rcx+rax+60h], xmm0
0x1800040c0  movups  xmm1, xmmword ptr [rsi+70h]
0x1800040c4  movups  xmmword ptr [rcx+rax+70h], xmm1
0x1800040c9  movups  xmm0, xmmword ptr [rsi+80h]
0x1800040d0  movups  xmmword ptr [rcx+rax+80h], xmm0
0x1800040d8  movups  xmm1, xmmword ptr [rsi+90h]
0x1800040df  movups  xmmword ptr [rcx+rax+90h], xmm1
0x1800040e7  inc     dword ptr [rdi+108h]
0x1800040ed  xor     ebx, ebx
0x1800040ef  mov     rcx, [rbp+arg_0]
0x1800040f3  test    rcx, rcx
0x1800040f6  jz      short loc_180004101
0x1800040f8  mov     rax, [rdi+20h]
0x1800040fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004101  mov     eax, ebx
0x180004103  mov     rbx, [rsp+50h+arg_8]
0x18000410b  add     rsp, 50h
0x18000410f  pop     r15
0x180004111  pop     r14
0x180004113  pop     rdi
0x180004114  pop     rsi
0x180004115  pop     rbp
0x180004116  retn
0x180004117  mov     rcx, cs:WPP_GLOBAL_Control
0x18000411e  lea     rax, WPP_GLOBAL_Control
0x180004125  cmp     rcx, rax
0x180004128  jz      short loc_1800040EF
0x18000412a  test    byte ptr [rcx+1Ch], 1
0x18000412e  jz      short loc_1800040EF
0x180004130  mov     dword ptr [rsp+50h+var_20], 0FAh
0x180004138  mov     rcx, [rcx+10h]
0x18000413c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004143  mov     [rsp+50h+var_28], r8
0x180004148  lea     r9, aStatus; "Status"
0x18000414f  mov     dword ptr [rsp+50h+var_30], ebx
0x180004153  call    WPP_SF_sDsd
0x180004158  jmp     short loc_1800040EF
0x18000415a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004161  lea     rax, WPP_GLOBAL_Control
0x180004168  cmp     rcx, rax
0x18000416b  jz      short loc_1800040EF
0x18000416d  test    byte ptr [rcx+1Ch], 1
0x180004171  jz      loc_1800040EF
0x180004177  mov     dword ptr [rsp+50h+var_20], 0D7h
0x18000417f  jmp     short loc_180004138
0x180004181  mov     rcx, cs:WPP_GLOBAL_Control
0x180004188  lea     rax, WPP_GLOBAL_Control
0x18000418f  cmp     rcx, rax
0x180004192  jz      loc_1800040EF
0x180004198  test    byte ptr [rcx+1Ch], 1
0x18000419c  jz      loc_1800040EF
0x1800041a2  mov     dword ptr [rsp+50h+var_20], 0E7h
0x1800041aa  jmp     short loc_180004138
0x1800041ac  mov     r9d, 0BCh
0x1800041b2  jmp     short loc_1800041BA
0x1800041b4  mov     r9d, 10Dh
0x1800041ba  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800041c1  mov     ecx, eax
0x1800041c3  lea     rdx, aStatus; "Status"
0x1800041ca  call    DebugTraceError
0x1800041cf  jmp     loc_1800040EF
0x1800041d4  mov     r9d, 0CCh
0x1800041da  jmp     short loc_1800041BA
0x1800041dc  inc     eax
0x1800041de  cmp     eax, edx
0x1800041e0  jb      loc_18000406E
0x1800041e6  lea     eax, [rcx+80h]
0x1800041ec  mov     rcx, rdi
0x1800041ef  lea     rdx, [rax+rax*4]
0x1800041f3  lea     r14, [rdi+110h]
0x1800041fa  shl     rdx, 5
0x1800041fe  mov     r15, [r14]
0x180004201  mov     r8, r14
0x180004204  call    CMSG_AllocateBuffer
0x180004209  mov     ebx, eax
0x18000420b  test    eax, eax
0x18000420d  jnz     short loc_1800041B4
0x18000420f  mov     eax, [rdi+108h]
0x180004215  test    eax, eax
0x180004217  jz      loc_18000406E
0x18000421d  mov     rcx, [r14]; void *
0x180004220  lea     r8, [rax+rax*4]
0x180004224  shl     r8, 5; Size
0x180004228  mov     rdx, r15; Src
0x18000422b  call    memcpy_0
0x180004230  jmp     loc_18000406E
```
