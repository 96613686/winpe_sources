# RouterAesKeyWrap

- ea: `0x18005ca4c`
- end: `0x18005ce0f`
- name: `RouterAesKeyWrap`
- size: `963`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800599c0`

## callees

- `0x18000743c`
- `0x180018e40`
- `0x180018f30`
- `0x18005ca4c`
- `0x18005ce18`
- `0x18009f650`
- `0x18009f6d0`
- `0x18009f780`

## string_xrefs

- `0x18005cb5c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005cbd9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005cc1f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005cd27`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

## pseudocode

```c
__int64 __fastcall RouterAesKeyWrap(__int64 a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v5; // rax
  __int64 v7; // r10
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, const wchar_t *, unsigned int *, __int64, int *, _DWORD); // r14
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // r8
  __int64 (__fastcall *v12)(__int64, const wchar_t *, int *, __int64, int *, _DWORD); // rax
  int v13; // eax
  __int64 v14; // r12
  unsigned int v15; // ebx
  __int64 v16; // r13
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // r14d
  unsigned int v21; // edi
  void *v22; // r15
  char *p_Src; // rdi
  __int64 v24; // rax
  int KeyDataBlob; // eax
  unsigned int v26; // r13d
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rax
  unsigned int v29; // r14d
  unsigned int i; // ecx
  int v31; // eax
  size_t v32; // r8
  void *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int128 *v36; // rax
  unsigned __int64 *v37; // rax
  size_t *p_Size; // rax
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h]
  void *v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v46)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // [rsp+88h] [rbp-78h]
  unsigned __int64 v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h]
  __int64 v49; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h]
  size_t Size; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v53; // [rsp+C0h] [rbp-40h] BYREF
  char Src; // [rsp+D0h] [rbp-30h] BYREF

  v5 = *(_QWORD *)(a1 + 8);
  v7 = *(_QWORD *)(a2 + 16);
  v8 = *(_QWORD *)(a1 + 16);
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, __int64, int *, _DWORD))(v5 + 64);
  v10 = *(_QWORD *)(a2 + 8);
  v44 = a3;
  v43 = a1;
  v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD))(v10 + 96);
  v12 = *(__int64 (__fastcall **)(__int64, const wchar_t *, int *, __int64, int *, _DWORD))(v10 + 64);
  v46 = v11;
  v45 = v7;
  v13 = v12(v7, L"BlockLength", &v42, 4, &v41, 0);
  v14 = 8;
  v15 = v13;
  v16 = 16;
  if ( v13 < 0 )
  {
    v17 = 186;
LABEL_7:
    v18 = (unsigned int)v13;
LABEL_8:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c", v17);
LABEL_47:
    *a5 = 0;
    goto LABEL_39;
  }
  if ( v41 != 4 || v42 != 16 )
  {
    v15 = -1073741816;
    v17 = 194;
    v18 = 3221225480LL;
    goto LABEL_8;
  }
  v13 = v9(v8, L"KeyLength", &v40, 4, &v41, 0);
  v15 = v13;
  if ( v13 < 0 )
  {
    v17 = 208;
    goto LABEL_7;
  }
  v19 = v40 >> 3;
  v20 = v40 >> 3;
  v40 >>= 3;
  if ( v41 != 4 || (v20 & 7) != 0 )
  {
    v15 = -1073741816;
    goto LABEL_47;
  }
  v21 = v19 + 8;
  if ( !v44 )
  {
    v15 = 0;
LABEL_19:
    *a5 = v21;
    goto LABEL_39;
  }
  if ( a4 < v21 )
  {
    v15 = -1073741789;
    goto LABEL_19;
  }
  Size = v21;
  if ( v21 > 0x48 )
  {
    v24 = BCryptAlloc(v21);
    v22 = (void *)v24;
    if ( !v24 )
    {
      v15 = -1073741801;
      DebugTraceError(
        3221225495LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
        256);
      goto LABEL_19;
    }
    v19 = v40;
    p_Src = (char *)v24;
  }
  else
  {
    v22 = 0;
    p_Src = &Src;
  }
  KeyDataBlob = RouterGetKeyDataBlob(v43, p_Src + 8, v19);
  v15 = KeyDataBlob;
  if ( KeyDataBlob >= 0 )
  {
    v26 = v20;
    v27 = (unsigned __int64)v40 >> 3;
    v28 = 0xA6A6A6A6A6A6A6A6uLL;
    v47 = v27;
    v29 = 0;
LABEL_24:
    if ( v29 >= 6 )
    {
      v32 = Size;
      v33 = v44;
      *(_QWORD *)p_Src = v28;
      memmove(v33, p_Src, v32);
      v15 = 0;
    }
    else
    {
      for ( i = 0; ; i = v43 + 1 )
      {
        LODWORD(v43) = i;
        v48 = i;
        if ( i >= v27 )
        {
          ++v29;
          goto LABEL_24;
        }
        v50 = v28;
        v49 = 8 * i;
        v51 = *(_QWORD *)&p_Src[v49 + 8];
        v53 = 0;
        v31 = v46(v45, &v50, 16, 0, &v53, 16, &v50, 16, &v41, 0);
        v15 = v31;
        if ( v31 < 0 )
          break;
        v27 = v47;
        v28 = v50 ^ _byteswap_uint64(v48 + 1 + v47 * v29);
        *(_QWORD *)&p_Src[v49 + 8] = v51;
      }
      DebugTraceError(
        (unsigned int)v31,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
        309);
    }
    v20 = v26;
  }
  else
  {
    DebugTraceError(
      (unsigned int)KeyDataBlob,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
      274);
    v26 = v20;
  }
  *a5 = v20 + 8;
  if ( p_Src )
  {
    v34 = v26 + 8;
    if ( v26 != -8 )
    {
      do
      {
        *p_Src++ = 0;
        --v34;
      }
      while ( v34 );
    }
  }
  if ( v22 )
    BCryptFree(v22);
  v16 = 16;
LABEL_39:
  v35 = 16;
  v36 = &v53;
  do
  {
    *(_BYTE *)v36 = 0;
    v36 = (__int128 *)((char *)v36 + 1);
    --v35;
  }
  while ( v35 );
  v37 = &v50;
  do
  {
    *(_BYTE *)v37 = 0;
    v37 = (unsigned __int64 *)((char *)v37 + 1);
    --v16;
  }
  while ( v16 );
  p_Size = &Size;
  do
  {
    *(_BYTE *)p_Size = 0;
    p_Size = (size_t *)((char *)p_Size + 1);
    --v14;
  }
  while ( v14 );
  return v15;
}

```

## disassembly

```asm
0x18005ca4c  mov     [rsp-8+arg_18], rbx
0x18005ca51  push    rbp
0x18005ca52  push    rsi
0x18005ca53  push    rdi
0x18005ca54  push    r12
0x18005ca56  push    r13
0x18005ca58  push    r14
0x18005ca5a  push    r15
0x18005ca5c  lea     rbp, [rsp-30h]
0x18005ca61  sub     rsp, 130h
0x18005ca68  mov     rax, cs:__security_cookie
0x18005ca6f  xor     rax, rsp
0x18005ca72  mov     [rbp+60h+var_40], rax
0x18005ca76  mov     rax, [rcx+8]
0x18005ca7a  mov     r15d, r9d
0x18005ca7d  mov     r10, [rdx+10h]
0x18005ca81  xor     r9d, r9d
0x18005ca84  mov     rdi, [rcx+10h]
0x18005ca88  mov     rsi, [rbp+60h+arg_20]
0x18005ca8f  mov     [rsp+160h+var_F8], r9d
0x18005ca94  mov     [rsp+160h+var_100], r9d
0x18005ca99  mov     [rsp+160h+var_FC], r9d
0x18005ca9e  mov     r14, [rax+40h]
0x18005caa2  mov     rax, [rdx+8]
0x18005caa6  lea     rdx, aBlocklength; "BlockLength"
0x18005caad  mov     [rsp+160h+var_E8], r8
0x18005cab2  mov     [rsp+160h+var_F0], rcx
0x18005cab7  lea     rcx, [rsp+160h+var_FC]
0x18005cabc  mov     [rsp+160h+var_138], r9d
0x18005cac1  mov     r9d, 4
0x18005cac7  mov     r8, [rax+60h]
0x18005cacb  mov     rax, [rax+40h]
0x18005cacf  mov     [rbp+60h+var_D8], r8
0x18005cad3  lea     r8, [rsp+160h+var_F8]
0x18005cad8  mov     [rsp+160h+var_140], rcx
0x18005cadd  mov     rcx, r10
0x18005cae0  mov     [rbp+60h+var_E0], r10
0x18005cae4  call    _guard_dispatch_icall
0x18005cae9  mov     r12d, 8
0x18005caef  mov     ebx, eax
0x18005caf1  lea     r13d, [r12+8]
0x18005caf6  test    eax, eax
0x18005caf8  jns     short loc_18005CB02
0x18005cafa  mov     r9d, 0BAh
0x18005cb00  jmp     short loc_18005CB53
0x18005cb02  cmp     [rsp+160h+var_FC], 4
0x18005cb07  jnz     loc_18005CDFA
0x18005cb0d  cmp     [rsp+160h+var_F8], r13d
0x18005cb12  jnz     loc_18005CDFA
0x18005cb18  lea     rax, [rsp+160h+var_FC]
0x18005cb1d  mov     [rsp+160h+var_138], 0
0x18005cb25  mov     [rsp+160h+var_140], rax
0x18005cb2a  lea     r8, [rsp+160h+var_100]
0x18005cb2f  mov     rax, r14
0x18005cb32  lea     rdx, aKeylength; "KeyLength"
0x18005cb39  mov     r9d, 4
0x18005cb3f  mov     rcx, rdi
0x18005cb42  call    _guard_dispatch_icall
0x18005cb47  mov     ebx, eax
0x18005cb49  test    eax, eax
0x18005cb4b  jns     short loc_18005CB6D
0x18005cb4d  mov     r9d, 0D0h
0x18005cb53  mov     ecx, eax
0x18005cb55  lea     rdx, aStatus; "Status"
0x18005cb5c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cb63  call    DebugTraceError
0x18005cb68  jmp     loc_18005CDF2
0x18005cb6d  mov     r8d, [rsp+160h+var_100]
0x18005cb72  shr     r8d, 3
0x18005cb76  cmp     [rsp+160h+var_FC], 4
0x18005cb7b  mov     r14d, r8d
0x18005cb7e  mov     [rsp+160h+var_100], r8d
0x18005cb83  jnz     loc_18005CDED
0x18005cb89  test    r14b, 7
0x18005cb8d  jnz     loc_18005CDED
0x18005cb93  cmp     [rsp+160h+var_E8], 0
0x18005cb99  lea     edi, [r8+8]
0x18005cb9d  jnz     short loc_18005CBA3
0x18005cb9f  xor     ebx, ebx
0x18005cba1  jmp     short loc_18005CBF6
0x18005cba3  cmp     r15d, edi
0x18005cba6  jnb     short loc_18005CBAF
0x18005cba8  mov     ebx, 0C0000023h
0x18005cbad  jmp     short loc_18005CBF6
0x18005cbaf  mov     eax, edi
0x18005cbb1  mov     [rbp+60h+Size], rax
0x18005cbb5  cmp     edi, 48h ; 'H'
0x18005cbb8  ja      short loc_18005CBC3
0x18005cbba  xor     r15d, r15d
0x18005cbbd  lea     rdi, [rbp+60h+Src]
0x18005cbc1  jmp     short loc_18005CC05
0x18005cbc3  mov     rcx, rax
0x18005cbc6  call    BCryptAlloc
0x18005cbcb  mov     r15, rax
0x18005cbce  test    rax, rax
0x18005cbd1  jnz     short loc_18005CBFD
0x18005cbd3  mov     r9d, 100h
0x18005cbd9  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cbe0  lea     rdx, aStatus; "Status"
0x18005cbe7  mov     ecx, 0C0000017h
0x18005cbec  mov     ebx, 0C0000017h
0x18005cbf1  call    DebugTraceError
0x18005cbf6  mov     [rsi], edi
0x18005cbf8  jmp     loc_18005CD90
0x18005cbfd  mov     r8d, [rsp+160h+var_100]
0x18005cc02  mov     rdi, rax
0x18005cc05  mov     rcx, [rsp+160h+var_F0]
0x18005cc0a  lea     rdx, [rdi+8]
0x18005cc0e  call    RouterGetKeyDataBlob
0x18005cc13  mov     ebx, eax
0x18005cc15  test    eax, eax
0x18005cc17  jns     short loc_18005CC3C
0x18005cc19  mov     r9d, 112h
0x18005cc1f  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cc26  lea     rdx, aStatus; "Status"
0x18005cc2d  mov     ecx, eax
0x18005cc2f  call    DebugTraceError
0x18005cc34  mov     r13d, r14d
0x18005cc37  jmp     loc_18005CD57
0x18005cc3c  mov     edx, [rsp+160h+var_100]
0x18005cc40  mov     r13d, r14d
0x18005cc43  shr     rdx, 3
0x18005cc47  mov     rax, 0A6A6A6A6A6A6A6A6h
0x18005cc51  mov     [rbp+60h+var_D0], rdx
0x18005cc55  xor     r14d, r14d
0x18005cc58  cmp     r14d, 6
0x18005cc5c  jnb     loc_18005CD3E
0x18005cc62  xor     ecx, ecx
0x18005cc64  mov     r8d, ecx
0x18005cc67  mov     dword ptr [rsp+160h+var_F0], ecx
0x18005cc6b  mov     [rbp+60h+var_C8], r8
0x18005cc6f  cmp     r8, rdx
0x18005cc72  jnb     loc_18005CD19
0x18005cc78  mov     [rbp+60h+var_B8], rax
0x18005cc7c  lea     rdx, [rbp+60h+var_B8]
0x18005cc80  lea     eax, ds:0[rcx*8]
0x18005cc87  mov     [rsp+160h+var_118], 0
0x18005cc8f  mov     [rbp+60h+var_C0], rax
0x18005cc93  lea     rcx, [rbp+60h+var_B8]
0x18005cc97  mov     rax, [rax+rdi+8]
0x18005cc9c  xorps   xmm0, xmm0
0x18005cc9f  mov     [rbp+60h+var_B0], rax
0x18005cca3  xor     r9d, r9d
0x18005cca6  lea     rax, [rsp+160h+var_FC]
0x18005ccab  mov     [rsp+160h+var_120], rax
0x18005ccb0  mov     eax, 10h
0x18005ccb5  mov     [rsp+160h+var_128], eax
0x18005ccb9  mov     r8d, eax
0x18005ccbc  mov     [rsp+160h+var_130], rcx
0x18005ccc1  lea     rcx, [rbp+60h+var_A0]
0x18005ccc5  mov     [rsp+160h+var_138], eax
0x18005ccc9  mov     rax, [rbp+60h+var_D8]
0x18005cccd  mov     [rsp+160h+var_140], rcx
0x18005ccd2  mov     rcx, [rbp+60h+var_E0]
0x18005ccd6  movups  [rbp+60h+var_A0], xmm0
0x18005ccda  call    _guard_dispatch_icall
0x18005ccdf  mov     ebx, eax
0x18005cce1  test    eax, eax
0x18005cce3  js      short loc_18005CD21
0x18005cce5  mov     rdx, [rbp+60h+var_D0]
0x18005cce9  mov     rcx, [rbp+60h+var_C8]
0x18005cced  mov     r8, [rbp+60h+var_C0]
0x18005ccf1  inc     rcx
0x18005ccf4  mov     eax, r14d
0x18005ccf7  imul    rax, rdx
0x18005ccfb  add     rax, rcx
0x18005ccfe  mov     rcx, [rbp+60h+var_B0]
0x18005cd02  bswap   rax
0x18005cd05  xor     rax, [rbp+60h+var_B8]
0x18005cd09  mov     [r8+rdi+8], rcx
0x18005cd0e  mov     ecx, dword ptr [rsp+160h+var_F0]
0x18005cd12  inc     ecx
0x18005cd14  jmp     loc_18005CC64
0x18005cd19  inc     r14d
0x18005cd1c  jmp     loc_18005CC58
0x18005cd21  mov     r9d, 135h
0x18005cd27  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cd2e  lea     rdx, aStatus; "Status"
0x18005cd35  mov     ecx, eax
0x18005cd37  call    DebugTraceError
0x18005cd3c  jmp     short loc_18005CD54
0x18005cd3e  mov     r8, [rbp+60h+Size]; Size
0x18005cd42  mov     rdx, rdi; Src
0x18005cd45  mov     rcx, [rsp+160h+var_E8]; void *
0x18005cd4a  mov     [rdi], rax
0x18005cd4d  call    memmove
0x18005cd52  xor     ebx, ebx
0x18005cd54  mov     r14d, r13d
0x18005cd57  mov     eax, r12d
0x18005cd5a  mov     ecx, r12d
0x18005cd5d  add     eax, r14d
0x18005cd60  mov     [rsi], eax
0x18005cd62  test    rdi, rdi
0x18005cd65  jz      short loc_18005CD7D
0x18005cd67  lea     eax, [rcx+r13]
0x18005cd6b  mov     ecx, eax
0x18005cd6d  test    eax, eax
0x18005cd6f  jz      short loc_18005CD7D
0x18005cd71  mov     byte ptr [rdi], 0
0x18005cd74  inc     rdi
0x18005cd77  sub     rcx, 1
0x18005cd7b  jnz     short loc_18005CD71
0x18005cd7d  test    r15, r15
0x18005cd80  jz      short loc_18005CD8A
0x18005cd82  mov     rcx, r15; P
0x18005cd85  call    BCryptFree
0x18005cd8a  mov     r13d, 10h
0x18005cd90  mov     rcx, r13
0x18005cd93  lea     rax, [rbp+60h+var_A0]
0x18005cd97  mov     byte ptr [rax], 0
0x18005cd9a  inc     rax
0x18005cd9d  sub     rcx, 1
0x18005cda1  jnz     short loc_18005CD97
0x18005cda3  lea     rax, [rbp+60h+var_B8]
0x18005cda7  mov     byte ptr [rax], 0
0x18005cdaa  inc     rax
0x18005cdad  sub     r13, 1
0x18005cdb1  jnz     short loc_18005CDA7
0x18005cdb3  lea     rax, [rbp+60h+Size]
0x18005cdb7  mov     byte ptr [rax], 0
0x18005cdba  inc     rax
0x18005cdbd  sub     r12, 1
0x18005cdc1  jnz     short loc_18005CDB7
0x18005cdc3  mov     eax, ebx
0x18005cdc5  mov     rcx, [rbp+60h+var_40]
0x18005cdc9  xor     rcx, rsp; StackCookie
0x18005cdcc  call    __security_check_cookie
0x18005cdd1  mov     rbx, [rsp+160h+arg_18]
0x18005cdd9  add     rsp, 130h
0x18005cde0  pop     r15
0x18005cde2  pop     r14
0x18005cde4  pop     r13
0x18005cde6  pop     r12
0x18005cde8  pop     rdi
0x18005cde9  pop     rsi
0x18005cdea  pop     rbp
0x18005cdeb  retn
0x18005cded  mov     ebx, 0C0000008h
0x18005cdf2  mov     dword ptr [rsi], 0
0x18005cdf8  jmp     short loc_18005CD90
0x18005cdfa  mov     ebx, 0C0000008h
0x18005cdff  mov     r9d, 0C2h
0x18005ce05  mov     ecx, 0C0000008h
0x18005ce0a  jmp     loc_18005CB55
```
