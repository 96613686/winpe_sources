# KerbCreateAuthenticator(KERB_ENCRYPTION_KEY *,ulong,_LARGE_INTEGER *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *,KERB_ENCRYPTION_KEY *,PKERB_AUTHORIZATION_DATA *,KERB_CHECKSUM *,uchar,KERB_ENCRYPTED_DATA *)

- ea: `0x180007b18`
- end: `0x180007dc1`
- name: `?KerbCreateAuthenticator@@YAJPEAUKERB_ENCRYPTION_KEY@@KPEAT_LARGE_INTEGER@@PEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@0PEAUPKERB_AUTHORIZATION_DATA@@PEAUKERB_CHECKSUM@@EPEAUKERB_ENCRYPTED_DATA@@@Z`
- size: `681`
- prototype: `__int64 __usercall@<rax>(struct KERB_ENCRYPTION_KEY *@<rcx>, unsigned int@<edx>, union _LARGE_INTEGER *@<r8>, struct _KERB_INTERNAL_NAME *@<r9>, struct _UNICODE_STRING *, struct KERB_ENCRYPTION_KEY *, struct PKERB_AUTHORIZATION_DATA *, struct KERB_CHECKSUM *, unsigned __int8, struct KERB_ENCRYPTED_DATA *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006250`

## callees

- `0x1800057f0`
- `0x180007b18`
- `0x180010db0`
- `0x1800116e0`
- `0x180011a20`
- `0x180011de0`
- `0x180013b20`
- `0x18001a70c`
- `0x18001a8bc`
- `0x1800210f0`
- `0x180021a54`
- `0x180023ce0`

## import_xrefs

- `MSASN1!ASN1intx_free` at `0x180007d00`
- `MSASN1!ASN1intx_free` at `0x180007d00`
- `MSASN1!ASN1intx_setuint32` at `0x180007c13`
- `MSASN1!ASN1intx_setuint32` at `0x180007c13`

## pseudocode

```c
__int64 __fastcall KerbCreateAuthenticator(
        struct KERB_ENCRYPTION_KEY *a1,
        unsigned int a2,
        union _LARGE_INTEGER *a3,
        struct _KERB_INTERNAL_NAME *a4,
        struct _UNICODE_STRING *a5,
        struct KERB_ENCRYPTION_KEY *a6,
        struct PKERB_AUTHORIZATION_DATA *a7,
        struct KERB_CHECKSUM *a8,
        unsigned __int8 a9,
        struct KERB_ENCRYPTED_DATA *a10)
{
  unsigned __int8 *v11; // rdi
  unsigned int EncryptionBufferWrapper; // ebx
  __int16 v14; // ax
  __int64 v15; // xmm1_8
  __int64 v16; // xmm1_8
  unsigned int v18; // r9d
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 *v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v21; // [rsp+40h] [rbp-C0h]
  union _LARGE_INTEGER *v22; // [rsp+48h] [rbp-B8h]
  unsigned __int8 **v23; // [rsp+50h] [rbp-B0h]
  unsigned int *v24; // [rsp+58h] [rbp-A8h]
  struct KERB_ENCRYPTED_DATA *v25; // [rsp+60h] [rbp-A0h]
  struct _STRING v26; // [rsp+68h] [rbp-98h] BYREF
  _WORD v27[2]; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+84h] [rbp-7Ch]
  void *Buffer; // [rsp+88h] [rbp-78h]
  _BYTE v30[16]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+B0h] [rbp-50h]
  int v33; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v34[20]; // [rsp+BCh] [rbp-44h] BYREF
  __int128 v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+E0h] [rbp-20h]
  _BYTE v37[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-10h]
  struct PKERB_AUTHORIZATION_DATA *v39; // [rsp+F8h] [rbp-8h]

  v11 = 0;
  v25 = a10;
  v24 = (unsigned int *)((char *)a10 + 16);
  v22 = a3;
  v21 = a2;
  v19 = 0;
  *((_QWORD *)a10 + 3) = 0;
  v20 = 0;
  v23 = (unsigned __int8 **)((char *)a10 + 24);
  memset_0(v27, 0, 0x80u);
  v28 = 5;
  Buffer = 0;
  v26 = 0;
  EncryptionBufferWrapper = KerbUnicodeStringToKerbString(&v26, a5);
  if ( !EncryptionBufferWrapper )
  {
    Buffer = v26.Buffer;
    EncryptionBufferWrapper = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)v30, a4);
    if ( !EncryptionBufferWrapper )
    {
      KerbConvertLargeIntToGeneralizedTimeWrapper((struct tagASN1generalizedtime_t *)v34, &v33, v22);
      v27[0] |= 0x20u;
      ASN1intx_setuint32(v37, v21);
      if ( !v38 )
      {
        EncryptionBufferWrapper = 60;
        goto LABEL_16;
      }
      v14 = v27[0];
      if ( a6 )
      {
        v14 = v27[0] | 0x40;
        v15 = *((_QWORD *)a6 + 2);
        v35 = *(_OWORD *)a6;
        v27[0] |= 0x40u;
        v36 = v15;
      }
      if ( a7 )
      {
        v14 |= 0x10u;
        v39 = a7;
        v27[0] = v14;
      }
      if ( a8 )
      {
        v16 = *((_QWORD *)a8 + 2);
        v31 = *(_OWORD *)a8;
        v27[0] = v14 | 0x80;
        v32 = v16;
      }
      EncryptionBufferWrapper = KerbPackData(v27, 0x22u, &v19, &v20);
      if ( EncryptionBufferWrapper )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
            EncryptionBufferWrapper);
        goto LABEL_15;
      }
      EncryptionBufferWrapper = KerbAllocateEncryptionBufferWrapper(*(_DWORD *)a1, v19, v24, v23);
      if ( EncryptionBufferWrapper )
      {
LABEL_15:
        v11 = v20;
        goto LABEL_16;
      }
      v11 = v20;
      EncryptionBufferWrapper = KerbEncryptDataEx(v25, v19, v20, v18, 0xBu, a1);
      if ( EncryptionBufferWrapper
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
          EncryptionBufferWrapper);
      }
    }
  }
LABEL_16:
  KerbFreePrincipalName((struct KERB_PRINCIPAL_NAME *)v30);
  if ( Buffer )
  {
    Pku2uFree(Buffer);
    Buffer = 0;
  }
  if ( v38 )
    ASN1intx_free(v37);
  if ( v11 )
    Pku2uFree(v11);
  return EncryptionBufferWrapper;
}

```

## disassembly

```asm
0x180007b18  push    rbp
0x180007b1a  push    rbx
0x180007b1b  push    rsi
0x180007b1c  push    rdi
0x180007b1d  push    r12
0x180007b1f  push    r13
0x180007b21  push    r14
0x180007b23  push    r15
0x180007b25  lea     rbp, [rsp-18h]
0x180007b2a  sub     rsp, 118h
0x180007b31  mov     rax, cs:__security_cookie
0x180007b38  xor     rax, rsp
0x180007b3b  mov     [rbp+50h+var_50], rax
0x180007b3f  mov     rax, [rbp+50h+arg_48]
0x180007b46  mov     r12, rcx
0x180007b49  mov     rbx, [rbp+50h+arg_20]
0x180007b50  lea     rcx, [rbp+50h+var_D0]; void *
0x180007b54  mov     rsi, [rbp+50h+arg_28]
0x180007b5b  xor     edi, edi
0x180007b5d  mov     r15, [rbp+50h+arg_30]
0x180007b64  mov     r13, r9
0x180007b67  mov     r14, [rbp+50h+arg_38]
0x180007b6e  mov     [rsp+150h+var_F0], rax
0x180007b73  add     rax, 10h
0x180007b77  mov     [rsp+150h+var_F8], rax
0x180007b7c  add     rax, 8
0x180007b80  mov     [rsp+150h+var_108], r8
0x180007b85  mov     r8d, 80h; Size
0x180007b8b  mov     [rsp+150h+var_110], edx
0x180007b8f  xor     edx, edx; Val
0x180007b91  mov     [rsp+150h+var_120], 0
0x180007b99  mov     [rax], rdi
0x180007b9c  mov     [rsp+150h+var_118], rdi
0x180007ba1  mov     [rsp+150h+var_100], rax
0x180007ba6  call    memset_0
0x180007bab  xorps   xmm0, xmm0
0x180007bae  mov     [rbp+50h+var_CC], 5
0x180007bb5  mov     rdx, rbx; struct _UNICODE_STRING *
0x180007bb8  mov     [rbp+50h+var_C8], rdi
0x180007bbc  lea     rcx, [rsp+150h+var_E8]; struct _STRING *
0x180007bc1  movups  xmmword ptr [rsp+150h+var_E8.Length], xmm0
0x180007bc6  call    ?KerbUnicodeStringToKerbString@@YAJPEAU_STRING@@PEAU_UNICODE_STRING@@@Z; KerbUnicodeStringToKerbString(_STRING *,_UNICODE_STRING *)
0x180007bcb  mov     ebx, eax
0x180007bcd  test    eax, eax
0x180007bcf  jnz     loc_180007CD6
0x180007bd5  mov     rax, [rsp+150h+var_E8.Buffer]
0x180007bda  lea     rcx, [rbp+50h+var_C0]; struct KERB_PRINCIPAL_NAME *
0x180007bde  mov     rdx, r13; struct _KERB_INTERNAL_NAME *
0x180007be1  mov     [rbp+50h+var_C8], rax
0x180007be5  call    ?KerbConvertKdcNameToPrincipalName@@YAJPEAUKERB_PRINCIPAL_NAME@@PEAU_KERB_INTERNAL_NAME@@@Z; KerbConvertKdcNameToPrincipalName(KERB_PRINCIPAL_NAME *,_KERB_INTERNAL_NAME *)
0x180007bea  mov     ebx, eax
0x180007bec  test    eax, eax
0x180007bee  jnz     loc_180007CD6
0x180007bf4  mov     r8, [rsp+150h+var_108]; union _LARGE_INTEGER *
0x180007bf9  lea     rdx, [rbp+50h+var_98]; int *
0x180007bfd  lea     rcx, [rbp+50h+var_94]; struct tagASN1generalizedtime_t *
0x180007c01  call    ?KerbConvertLargeIntToGeneralizedTimeWrapper@@YAXPEAUtagASN1generalizedtime_t@@PEAJPEAT_LARGE_INTEGER@@@Z; KerbConvertLargeIntToGeneralizedTimeWrapper(tagASN1generalizedtime_t *,long *,_LARGE_INTEGER *)
0x180007c06  mov     edx, [rsp+150h+var_110]
0x180007c0a  lea     rcx, [rbp+50h+var_68]
0x180007c0e  or      [rbp+50h+var_D0], 20h
0x180007c13  call    cs:__imp_ASN1intx_setuint32
0x180007c19  cmp     [rbp+50h+var_60], rdi
0x180007c1d  jnz     short loc_180007C27
0x180007c1f  lea     ebx, [rdi+3Ch]
0x180007c22  jmp     loc_180007CD6
0x180007c27  movzx   eax, [rbp+50h+var_D0]
0x180007c2b  test    rsi, rsi
0x180007c2e  jz      short loc_180007C49
0x180007c30  movups  xmm0, xmmword ptr [rsi]
0x180007c33  or      ax, 40h
0x180007c37  movsd   xmm1, qword ptr [rsi+10h]
0x180007c3c  movaps  [rbp+50h+var_80], xmm0
0x180007c40  mov     [rbp+50h+var_D0], ax
0x180007c44  movsd   [rbp+50h+var_70], xmm1
0x180007c49  test    r15, r15
0x180007c4c  jz      short loc_180007C5A
0x180007c4e  or      ax, 10h
0x180007c52  mov     [rbp+50h+var_58], r15
0x180007c56  mov     [rbp+50h+var_D0], ax
0x180007c5a  test    r14, r14
0x180007c5d  jz      short loc_180007C7E
0x180007c5f  movups  xmm0, xmmword ptr [r14]
0x180007c63  mov     ecx, 80h
0x180007c68  movsd   xmm1, qword ptr [r14+10h]
0x180007c6e  or      ax, cx
0x180007c71  movaps  [rbp+50h+var_B0], xmm0
0x180007c75  mov     [rbp+50h+var_D0], ax
0x180007c79  movsd   [rbp+50h+var_A0], xmm1
0x180007c7e  lea     r9, [rsp+150h+var_118]; unsigned __int8 **
0x180007c83  mov     edx, 22h ; '"'; unsigned int
0x180007c88  lea     r8, [rsp+150h+var_120]; unsigned int *
0x180007c8d  lea     rcx, [rbp+50h+var_D0]; void *
0x180007c91  call    ?KerbPackData@@YAJPEAXKPEAKPEAPEAE@Z; KerbPackData(void *,ulong,ulong *,uchar * *)
0x180007c96  mov     ebx, eax
0x180007c98  test    eax, eax
0x180007c9a  jz      loc_180007D35
0x180007ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ca7  lea     rax, WPP_GLOBAL_Control
0x180007cae  cmp     rcx, rax
0x180007cb1  jz      short loc_180007CD1
0x180007cb3  test    byte ptr [rcx+1Ch], 1
0x180007cb7  jz      short loc_180007CD1
0x180007cb9  mov     rcx, [rcx+10h]
0x180007cbd  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180007cc4  mov     edx, 47h ; 'G'
0x180007cc9  mov     r9d, ebx
0x180007ccc  call    WPP_SF_d
0x180007cd1  mov     rdi, [rsp+150h+var_118]
0x180007cd6  lea     rcx, [rbp+50h+var_C0]; struct KERB_PRINCIPAL_NAME *
0x180007cda  call    ?KerbFreePrincipalName@@YAXPEAUKERB_PRINCIPAL_NAME@@@Z; KerbFreePrincipalName(KERB_PRINCIPAL_NAME *)
0x180007cdf  mov     rcx, [rbp+50h+var_C8]; void *
0x180007ce3  test    rcx, rcx
0x180007ce6  jz      short loc_180007CF5
0x180007ce8  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180007ced  mov     [rbp+50h+var_C8], 0
0x180007cf5  cmp     [rbp+50h+var_60], 0
0x180007cfa  jz      short loc_180007D06
0x180007cfc  lea     rcx, [rbp+50h+var_68]
0x180007d00  call    cs:__imp_ASN1intx_free
0x180007d06  test    rdi, rdi
0x180007d09  jz      short loc_180007D13
0x180007d0b  mov     rcx, rdi; void *
0x180007d0e  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180007d13  mov     eax, ebx
0x180007d15  mov     rcx, [rbp+50h+var_50]
0x180007d19  xor     rcx, rsp; StackCookie
0x180007d1c  call    __security_check_cookie
0x180007d21  add     rsp, 118h
0x180007d28  pop     r15
0x180007d2a  pop     r14
0x180007d2c  pop     r13
0x180007d2e  pop     r12
0x180007d30  pop     rdi
0x180007d31  pop     rsi
0x180007d32  pop     rbx
0x180007d33  pop     rbp
0x180007d34  retn
0x180007d35  mov     r9, [rsp+150h+var_100]; unsigned __int8 **
0x180007d3a  mov     r8, [rsp+150h+var_F8]; unsigned int *
0x180007d3f  mov     edx, [rsp+150h+var_120]; unsigned int
0x180007d43  mov     ecx, [r12]; unsigned int
0x180007d47  call    ?KerbAllocateEncryptionBufferWrapper@@YAJKKPEAKPEAPEAE@Z; KerbAllocateEncryptionBufferWrapper(ulong,ulong,ulong *,uchar * *)
0x180007d4c  mov     ebx, eax
0x180007d4e  test    eax, eax
0x180007d50  jnz     loc_180007CD1
0x180007d56  mov     rdi, [rsp+150h+var_118]
0x180007d5b  mov     edx, [rsp+150h+var_120]; unsigned int
0x180007d5f  mov     r8, rdi; unsigned __int8 *
0x180007d62  mov     rcx, [rsp+150h+var_F0]; struct KERB_ENCRYPTED_DATA *
0x180007d67  mov     [rsp+150h+var_128], r12; struct KERB_ENCRYPTION_KEY *
0x180007d6c  mov     [rsp+150h+var_130], 0Bh; unsigned int
0x180007d74  call    ?KerbEncryptDataEx@@YAJPEAUKERB_ENCRYPTED_DATA@@KPEAEKKPEAUKERB_ENCRYPTION_KEY@@@Z; KerbEncryptDataEx(KERB_ENCRYPTED_DATA *,ulong,uchar *,ulong,ulong,KERB_ENCRYPTION_KEY *)
0x180007d79  mov     ebx, eax
0x180007d7b  test    eax, eax
0x180007d7d  jz      loc_180007CD6
0x180007d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d8a  lea     rax, WPP_GLOBAL_Control
0x180007d91  cmp     rcx, rax
0x180007d94  jz      loc_180007CD6
0x180007d9a  test    byte ptr [rcx+1Ch], 1
0x180007d9e  jz      loc_180007CD6
0x180007da4  mov     rcx, [rcx+10h]
0x180007da8  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x180007daf  mov     edx, 48h ; 'H'
0x180007db4  mov     r9d, ebx
0x180007db7  call    WPP_SF_d
0x180007dbc  jmp     loc_180007CD6
```
