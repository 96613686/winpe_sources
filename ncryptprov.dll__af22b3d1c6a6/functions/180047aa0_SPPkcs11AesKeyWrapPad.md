# SPPkcs11AesKeyWrapPad

- ea: `0x180047aa0`
- end: `0x180047ef6`
- name: `SPPkcs11AesKeyWrapPad`
- size: `1110`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, UCHAR *, ULONG *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180047efc`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180038970`
- `0x1800398b0`
- `0x18004722c`
- `0x180047aa0`
- `0x180062310`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x180047c7f`
- `bcrypt!BCryptEncrypt` at `0x180047da4`
- `bcrypt!BCryptEncrypt` at `0x180047c7f`
- `bcrypt!BCryptEncrypt` at `0x180047da4`
- `bcrypt!BCryptGetProperty` at `0x180047b38`
- `bcrypt!BCryptGetProperty` at `0x180047b38`

## string_xrefs

- `0x180047ba2`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180047c97`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180047cda`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180047e17`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180047e68`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall SPPkcs11AesKeyWrapPad(void *a1, void *a2, unsigned int a3, UCHAR *a4, ULONG *a5)
{
  size_t v6; // rsi
  char *v7; // r14
  __int64 v8; // rdi
  __int64 v9; // r15
  __int64 v10; // r9
  NTSTATUS Property; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  unsigned int v14; // edi
  unsigned int v15; // r15d
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  unsigned int v19; // esi
  ULONG cbOutput; // r13d
  NTSTATUS v21; // eax
  unsigned __int64 v22; // rax
  __int64 v23; // rsi
  void *v24; // rdx
  __int64 v25; // rdi
  NTSTATUS v26; // eax
  PUCHAR v27; // rcx
  UCHAR *v28; // rax
  UCHAR *v29; // rax
  __int64 v30; // rcx
  ULONG *v31; // rax
  __int64 v32; // rcx
  _BYTE *v33; // rax
  _DWORD Size[3]; // [rsp+50h] [rbp-61h] BYREF
  ULONG v36; // [rsp+5Ch] [rbp-55h] BYREF
  void *Src; // [rsp+60h] [rbp-51h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+68h] [rbp-49h]
  PUCHAR v39; // [rsp+70h] [rbp-41h]
  ULONG v40[2]; // [rsp+78h] [rbp-39h] BYREF
  UCHAR pbInput[8]; // [rsp+80h] [rbp-31h] BYREF
  _QWORD v42[3]; // [rsp+88h] [rbp-29h] BYREF
  UCHAR pbIV[16]; // [rsp+A0h] [rbp-11h] BYREF

  Src = a2;
  v39 = a4;
  v6 = a3;
  v7 = 0;
  hKey = a1;
  Size[2] = 0;
  Size[1] = 0;
  v8 = 32;
  v36 = 0;
  v9 = 16;
  v40[0] = 0;
  if ( !a5 )
  {
    v10 = 4958;
LABEL_36:
    v12 = -1073741811;
    v13 = 3221225485LL;
    goto LABEL_37;
  }
  if ( !a2 || !a3 )
  {
    v10 = 4965;
    goto LABEL_36;
  }
  Property = BCryptGetProperty(a1, L"BlockLength", (PUCHAR)&Size[2], 4u, &Size[1], 0);
  v12 = Property;
  if ( Property < 0 )
  {
    v10 = 4979;
    v13 = (unsigned int)Property;
LABEL_37:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v10);
    goto LABEL_38;
  }
  if ( *(_QWORD *)&Size[1] != 0x1000000004LL )
  {
    v12 = -1073741816;
    v10 = 4986;
    v13 = 3221225480LL;
    goto LABEL_37;
  }
  v14 = -(int)v6 & 7;
  if ( v14 + (unsigned int)v6 < (unsigned int)v6 )
  {
    v12 = -1073741675;
    v17 = 4998;
    v18 = 3221225621LL;
    goto LABEL_11;
  }
  v15 = (v14 + (unsigned int)v6) >> 3;
  v16 = RtlULongLongToULong(8LL * (v15 + 1), v40);
  v12 = v16;
  if ( v16 < 0 )
  {
    v17 = 5009;
    v18 = (unsigned int)v16;
LABEL_11:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v17);
    v8 = 32;
    v9 = 16;
LABEL_38:
    v19 = 0;
    goto LABEL_39;
  }
  if ( !a4 )
  {
    v9 = 16;
    *a5 = v40[0];
LABEL_14:
    v12 = 0;
    v8 = 32;
    v19 = 0;
    goto LABEL_39;
  }
  cbOutput = v40[0];
  if ( *a5 < v40[0] )
  {
    v12 = -1073741789;
    v17 = 5023;
    v18 = 3221225507LL;
    goto LABEL_11;
  }
  if ( v15 == 1 )
  {
    *(_DWORD *)pbInput = -1504093786;
    *(_DWORD *)&pbInput[4] = _byteswap_ulong(v6);
    memcpy_0(v42, Src, v6);
    if ( v14 )
      memset_0((char *)v42 + v6, 0, v14);
    v9 = 16;
    *(_OWORD *)pbIV = 0;
    v21 = BCryptEncrypt(hKey, pbInput, 0x10u, 0, pbIV, 0x10u, v39, cbOutput, &v36, 0);
    v12 = v21;
    if ( v21 < 0 )
    {
      DebugTraceError((unsigned int)v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 5061);
      v8 = 32;
      goto LABEL_38;
    }
    *a5 = cbOutput;
    goto LABEL_14;
  }
  Size[0] = v40[0] - 8;
  v7 = (char *)SafeAllocaAllocateFromHeap(v40[0] - 8);
  if ( v7 )
  {
    v40[1] = _byteswap_ulong(v6);
    v40[0] = -1504093786;
    memcpy_0(v7, Src, v6);
    memset_0(&v7[v6], 0, v14);
    v22 = *(_QWORD *)v40;
    v23 = 0;
    v24 = (void *)v15;
    Src = (void *)v15;
    while ( 1 )
    {
      v25 = 1;
      v9 = 16;
      if ( v24 )
        break;
LABEL_30:
      if ( ++v23 >= 6 )
      {
        v27 = v39;
        v19 = Size[0];
        *(_QWORD *)v39 = v22;
        memcpy_0(v27 + 8, v7, Size[0]);
        v12 = 0;
        *a5 = cbOutput;
        v8 = 32;
        goto LABEL_39;
      }
    }
    while ( 1 )
    {
      *(_QWORD *)pbInput = v22;
      v42[0] = *(_QWORD *)&v7[8 * v25 - 8];
      *(_OWORD *)pbIV = 0;
      v26 = BCryptEncrypt(hKey, pbInput, 0x10u, 0, pbIV, 0x10u, pbInput, 0x20u, &v36, 0);
      v12 = v26;
      if ( v26 < 0 )
        break;
      v24 = Src;
      v22 = *(_QWORD *)pbInput ^ _byteswap_uint64(v25 + v23 * (_QWORD)Src);
      *(_QWORD *)&v7[8 * v25++ - 8] = v42[0];
      if ( v25 > (__int64)v24 )
        goto LABEL_30;
    }
    DebugTraceError((unsigned int)v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 5111);
  }
  else
  {
    v12 = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 5076);
    v9 = 16;
  }
  v19 = Size[0];
  v8 = 32;
LABEL_39:
  v28 = pbIV;
  do
  {
    *v28++ = 0;
    --v9;
  }
  while ( v9 );
  v29 = pbInput;
  do
  {
    *v29++ = 0;
    --v8;
  }
  while ( v8 );
  v30 = 8;
  v31 = v40;
  do
  {
    *(_BYTE *)v31 = 0;
    v31 = (ULONG *)((char *)v31 + 1);
    --v30;
  }
  while ( v30 );
  if ( v7 )
  {
    v32 = v19;
    v33 = v7;
    if ( v19 )
    {
      do
      {
        *v33++ = 0;
        --v32;
      }
      while ( v32 );
    }
    MSCryptFree(v7);
  }
  return v12;
}

```

## disassembly

```asm
0x180047aa0  push    rbp
0x180047aa2  push    rbx
0x180047aa3  push    rsi
0x180047aa4  push    rdi
0x180047aa5  push    r12
0x180047aa7  push    r13
0x180047aa9  push    r14
0x180047aab  push    r15
0x180047aad  lea     rbp, [rsp-17h]
0x180047ab2  sub     rsp, 0C8h
0x180047ab9  mov     rax, cs:__security_cookie
0x180047ac0  xor     rax, rsp
0x180047ac3  mov     [rbp+4Fh+var_50], rax
0x180047ac7  mov     r12, [rbp+4Fh+arg_20]
0x180047acb  mov     rax, rdx
0x180047ace  mov     [rbp+4Fh+Src], rdx
0x180047ad2  mov     r13, r9
0x180047ad5  xor     edx, edx
0x180047ad7  mov     [rbp+4Fh+var_90], r9
0x180047adb  mov     esi, r8d
0x180047ade  mov     r14d, edx
0x180047ae1  mov     [rbp+4Fh+hKey], rcx
0x180047ae5  mov     dword ptr [rbp+4Fh+Size+8], edx
0x180047ae8  mov     dword ptr [rbp+4Fh+Size+4], edx
0x180047aeb  lea     edi, [rdx+20h]
0x180047aee  mov     [rbp+4Fh+var_A4], edx
0x180047af1  lea     r15d, [rdx+10h]
0x180047af5  mov     [rbp+4Fh+var_88], edx
0x180047af8  test    r12, r12
0x180047afb  jnz     short loc_180047B08
0x180047afd  mov     r9d, 135Eh
0x180047b03  jmp     loc_180047E5E
0x180047b08  test    rax, rax
0x180047b0b  jz      loc_180047E58
0x180047b11  cmp     esi, 1
0x180047b14  jb      loc_180047E58
0x180047b1a  mov     [rsp+100h+dwFlags], edx; dwFlags
0x180047b1e  lea     rax, [rbp+4Fh+Size+4]
0x180047b22  lea     rdx, aBlocklength; "BlockLength"
0x180047b29  mov     [rsp+100h+pcbResult], rax; pcbResult
0x180047b2e  mov     r9d, 4; cbOutput
0x180047b34  lea     r8, [rbp+4Fh+Size+8]; pbOutput
0x180047b38  call    cs:__imp_BCryptGetProperty
0x180047b3f  nop     dword ptr [rax+rax+00h]
0x180047b44  mov     ebx, eax
0x180047b46  test    eax, eax
0x180047b48  jns     short loc_180047B57
0x180047b4a  mov     r9d, 1373h
0x180047b50  mov     ecx, eax
0x180047b52  jmp     loc_180047E68
0x180047b57  cmp     dword ptr [rbp+4Fh+Size+4], 4
0x180047b5b  jnz     loc_180047E46
0x180047b61  cmp     dword ptr [rbp+4Fh+Size+8], r15d
0x180047b65  jnz     loc_180047E46
0x180047b6b  mov     edi, esi
0x180047b6d  neg     edi
0x180047b6f  and     edi, 7
0x180047b72  lea     r15d, [rdi+rsi]
0x180047b76  cmp     r15d, esi
0x180047b79  jb      loc_180047E31
0x180047b7f  shr     r15d, 3
0x180047b83  lea     rdx, [rbp+4Fh+var_88]
0x180047b87  lea     ecx, [r15+1]
0x180047b8b  shl     rcx, 3
0x180047b8f  call    RtlULongLongToULong
0x180047b94  mov     ebx, eax
0x180047b96  test    eax, eax
0x180047b98  jns     short loc_180047BC3
0x180047b9a  mov     r9d, 1391h
0x180047ba0  mov     ecx, eax
0x180047ba2  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047ba9  lea     rdx, aStatus; "Status"
0x180047bb0  call    DebugTraceError
0x180047bb5  mov     edi, 20h ; ' '
0x180047bba  lea     r15d, [rdi-10h]
0x180047bbe  jmp     loc_180047E7B
0x180047bc3  test    r13, r13
0x180047bc6  jnz     short loc_180047BE1
0x180047bc8  mov     eax, [rbp+4Fh+var_88]
0x180047bcb  lea     r15d, [r13+10h]
0x180047bcf  mov     [r12], eax
0x180047bd3  xor     ebx, ebx
0x180047bd5  mov     edi, 20h ; ' '
0x180047bda  mov     esi, ebx
0x180047bdc  jmp     loc_180047E7E
0x180047be1  mov     r13d, [rbp+4Fh+var_88]
0x180047be5  cmp     [r12], r13d
0x180047be9  jnb     short loc_180047BFD
0x180047beb  mov     ebx, 0C0000023h
0x180047bf0  mov     r9d, 139Fh
0x180047bf6  mov     ecx, 0C0000023h
0x180047bfb  jmp     short loc_180047BA2
0x180047bfd  cmp     r15d, 1
0x180047c01  jnz     loc_180047CBE
0x180047c07  mov     rdx, [rbp+4Fh+Src]; Src
0x180047c0b  lea     rcx, [rbp+4Fh+var_78]; void *
0x180047c0f  mov     eax, esi
0x180047c11  mov     dword ptr [rbp+4Fh+pbInput], 0A65959A6h
0x180047c18  bswap   eax
0x180047c1a  mov     r8, rsi; Size
0x180047c1d  mov     dword ptr [rbp+4Fh+pbInput+4], eax
0x180047c20  call    memcpy_0
0x180047c25  test    edi, edi
0x180047c27  jz      short loc_180047C3A
0x180047c29  lea     rcx, [rbp+4Fh+var_78]
0x180047c2d  mov     r8d, edi; Size
0x180047c30  add     rcx, rsi; void *
0x180047c33  xor     edx, edx; Val
0x180047c35  call    memset_0
0x180047c3a  mov     rcx, [rbp+4Fh+var_90]
0x180047c3e  lea     rax, [rbp+4Fh+var_A4]
0x180047c42  mov     [rsp+100h+var_B8], r14d; dwFlags
0x180047c47  lea     rdx, [rbp+4Fh+pbInput]; pbInput
0x180047c4b  mov     [rsp+100h+var_C0], rax; pcbResult
0x180047c50  mov     r15d, 10h
0x180047c56  mov     [rsp+100h+cbOutput], r13d; cbOutput
0x180047c5b  lea     rax, [rbp+4Fh+pbIV]
0x180047c5f  mov     [rsp+100h+var_D0], rcx; pbOutput
0x180047c64  xorps   xmm0, xmm0
0x180047c67  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180047c6b  xor     r9d, r9d; pPaddingInfo
0x180047c6e  mov     [rsp+100h+dwFlags], r15d; cbIV
0x180047c73  mov     r8d, r15d; cbInput
0x180047c76  mov     [rsp+100h+pcbResult], rax; pbIV
0x180047c7b  movups  xmmword ptr [rbp+4Fh+pbIV], xmm0
0x180047c7f  call    cs:__imp_BCryptEncrypt
0x180047c86  nop     dword ptr [rax+rax+00h]
0x180047c8b  mov     ebx, eax
0x180047c8d  test    eax, eax
0x180047c8f  jns     short loc_180047CB5
0x180047c91  mov     r9d, 13C5h
0x180047c97  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047c9e  lea     rdx, aStatus; "Status"
0x180047ca5  mov     ecx, eax
0x180047ca7  call    DebugTraceError
0x180047cac  lea     edi, [r15+10h]
0x180047cb0  jmp     loc_180047E7B
0x180047cb5  mov     [r12], r13d
0x180047cb9  jmp     loc_180047BD3
0x180047cbe  lea     eax, [r13-8]
0x180047cc2  mov     ecx, eax
0x180047cc4  mov     dword ptr [rbp+4Fh+Size], eax
0x180047cc7  call    SafeAllocaAllocateFromHeap
0x180047ccc  mov     r14, rax
0x180047ccf  test    rax, rax
0x180047cd2  jnz     short loc_180047D08
0x180047cd4  mov     r9d, 13D4h
0x180047cda  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047ce1  lea     rdx, aStatus; "Status"
0x180047ce8  mov     ecx, 0C0000017h
0x180047ced  mov     ebx, 0C0000017h
0x180047cf2  call    DebugTraceError
0x180047cf7  lea     r15d, [r14+10h]
0x180047cfb  mov     esi, dword ptr [rbp+4Fh+Size]
0x180047cfe  mov     edi, 20h ; ' '
0x180047d03  jmp     loc_180047E7E
0x180047d08  mov     rdx, [rbp+4Fh+Src]; Src
0x180047d0c  mov     eax, esi
0x180047d0e  bswap   eax
0x180047d10  mov     r8, rsi; Size
0x180047d13  mov     [rbp+4Fh+var_88+4], eax
0x180047d16  mov     rcx, r14; void *
0x180047d19  mov     [rbp+4Fh+var_88], 0A65959A6h
0x180047d20  call    memcpy_0
0x180047d25  mov     r8d, edi; Size
0x180047d28  lea     rcx, [rsi+r14]; void *
0x180047d2c  xor     edx, edx; Val
0x180047d2e  call    memset_0
0x180047d33  mov     rax, qword ptr [rbp+4Fh+var_88]
0x180047d37  xor     esi, esi
0x180047d39  mov     edx, r15d
0x180047d3c  mov     [rbp+4Fh+Src], rdx
0x180047d40  mov     edi, 1
0x180047d45  lea     r15d, [rdi+0Fh]
0x180047d49  cmp     rdx, rdi
0x180047d4c  jb      loc_180047DE0
0x180047d52  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180047d56  lea     rdx, [rbp+4Fh+pbInput]; pbInput
0x180047d5a  mov     qword ptr [rbp+4Fh+pbInput], rax
0x180047d5e  xorps   xmm0, xmm0
0x180047d61  mov     rax, [r14+rdi*8-8]
0x180047d66  xor     r9d, r9d; pPaddingInfo
0x180047d69  mov     [rsp+100h+var_B8], 0; dwFlags
0x180047d71  mov     r8d, r15d; cbInput
0x180047d74  mov     [rbp+4Fh+var_78], rax
0x180047d78  lea     rax, [rbp+4Fh+var_A4]
0x180047d7c  mov     [rsp+100h+var_C0], rax; pcbResult
0x180047d81  lea     rax, [rbp+4Fh+pbInput]
0x180047d85  mov     [rsp+100h+cbOutput], 20h ; ' '; cbOutput
0x180047d8d  mov     [rsp+100h+var_D0], rax; pbOutput
0x180047d92  lea     rax, [rbp+4Fh+pbIV]
0x180047d96  mov     [rsp+100h+dwFlags], r15d; cbIV
0x180047d9b  mov     [rsp+100h+pcbResult], rax; pbIV
0x180047da0  movups  xmmword ptr [rbp+4Fh+pbIV], xmm0
0x180047da4  call    cs:__imp_BCryptEncrypt
0x180047dab  nop     dword ptr [rax+rax+00h]
0x180047db0  mov     ebx, eax
0x180047db2  test    eax, eax
0x180047db4  js      short loc_180047E11
0x180047db6  mov     rdx, [rbp+4Fh+Src]
0x180047dba  mov     rcx, [rbp+4Fh+var_78]
0x180047dbe  mov     rax, rdx
0x180047dc1  imul    rax, rsi
0x180047dc5  add     rax, rdi
0x180047dc8  bswap   rax
0x180047dcb  xor     rax, qword ptr [rbp+4Fh+pbInput]
0x180047dcf  mov     [r14+rdi*8-8], rcx
0x180047dd4  inc     rdi
0x180047dd7  cmp     rdi, rdx
0x180047dda  jle     loc_180047D52
0x180047de0  inc     rsi
0x180047de3  cmp     rsi, 6
0x180047de7  jl      loc_180047D40
0x180047ded  mov     rcx, [rbp+4Fh+var_90]
0x180047df1  mov     rdx, r14; Src
0x180047df4  mov     esi, dword ptr [rbp+4Fh+Size]
0x180047df7  mov     r8d, esi; Size
0x180047dfa  mov     [rcx], rax
0x180047dfd  add     rcx, 8; void *
0x180047e01  call    memcpy_0
0x180047e06  xor     ebx, ebx
0x180047e08  mov     [r12], r13d
0x180047e0c  lea     edi, [rbx+20h]
0x180047e0f  jmp     short loc_180047E7E
0x180047e11  mov     r9d, 13F7h
0x180047e17  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047e1e  lea     rdx, aStatus; "Status"
0x180047e25  mov     ecx, eax
0x180047e27  call    DebugTraceError
0x180047e2c  jmp     loc_180047CFB
0x180047e31  mov     ebx, 0C0000095h
0x180047e36  mov     r9d, 1386h
0x180047e3c  mov     ecx, 0C0000095h
0x180047e41  jmp     loc_180047BA2
0x180047e46  mov     ebx, 0C0000008h
0x180047e4b  mov     r9d, 137Ah
0x180047e51  mov     ecx, 0C0000008h
0x180047e56  jmp     short loc_180047E68
0x180047e58  mov     r9d, 1365h
0x180047e5e  mov     ebx, 0C000000Dh
0x180047e63  mov     ecx, 0C000000Dh
0x180047e68  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180047e6f  lea     rdx, aStatus; "Status"
0x180047e76  call    DebugTraceError
0x180047e7b  mov     esi, r14d
0x180047e7e  lea     rax, [rbp+4Fh+pbIV]
0x180047e82  mov     byte ptr [rax], 0
0x180047e85  inc     rax
0x180047e88  sub     r15, 1
0x180047e8c  jnz     short loc_180047E82
0x180047e8e  lea     rax, [rbp+4Fh+pbInput]
0x180047e92  mov     byte ptr [rax], 0
0x180047e95  inc     rax
0x180047e98  sub     rdi, 1
0x180047e9c  jnz     short loc_180047E92
0x180047e9e  lea     ecx, [rdi+8]
0x180047ea1  lea     rax, [rbp+4Fh+var_88]
0x180047ea5  mov     byte ptr [rax], 0
0x180047ea8  inc     rax
0x180047eab  sub     rcx, 1
0x180047eaf  jnz     short loc_180047EA5
0x180047eb1  test    r14, r14
0x180047eb4  jz      short loc_180047ED3
0x180047eb6  mov     ecx, esi
0x180047eb8  mov     rax, r14
0x180047ebb  test    esi, esi
0x180047ebd  jz      short loc_180047ECB
0x180047ebf  mov     byte ptr [rax], 0
0x180047ec2  inc     rax
0x180047ec5  sub     rcx, 1
0x180047ec9  jnz     short loc_180047EBF
0x180047ecb  mov     rcx, r14
0x180047ece  call    MSCryptFree
0x180047ed3  mov     eax, ebx
0x180047ed5  mov     rcx, [rbp+4Fh+var_50]
0x180047ed9  xor     rcx, rsp; StackCookie
0x180047edc  call    __security_check_cookie
0x180047ee1  add     rsp, 0C8h
0x180047ee8  pop     r15
0x180047eea  pop     r14
0x180047eec  pop     r13
0x180047eee  pop     r12
0x180047ef0  pop     rdi
0x180047ef1  pop     rsi
0x180047ef2  pop     rbx
0x180047ef3  pop     rbp
0x180047ef4  retn
```
