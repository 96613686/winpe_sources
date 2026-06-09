# ASN1Dec_KERB_TICKET

- ea: `0x18000bbf0`
- end: `0x18000bea3`
- name: `ASN1Dec_KERB_TICKET`
- size: `691`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002f80`
- `0x18000493c`
- `0x180007844`
- `0x180008378`
- `0x18000b800`

## callees

- `0x180005800`
- `0x180009d9c`
- `0x18000bbf0`
- `0x18000d96c`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x18000bdf5`
- `MSASN1!ASN1BERDecPeekTag` at `0x18000bdf5`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000bcbf`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000bd23`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000bd7d`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000bdd9`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000be47`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000be63`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000be7e`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000bcbf`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000bd23`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000bd7d`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000bdd9`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000be47`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000be63`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000be7e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bc34`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bc57`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bc80`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bce4`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bd48`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bda2`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000be1a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bc34`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bc57`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bc80`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bce4`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bd48`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000bda2`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000be1a`
- `MSASN1!ASN1BERDecZeroCharString` at `0x18000bd03`
- `MSASN1!ASN1BERDecZeroCharString` at `0x18000bd03`
- `MSASN1!ASN1BERDecS32Val` at `0x18000bc9f`
- `MSASN1!ASN1BERDecS32Val` at `0x18000bc9f`

## pseudocode

```c
__int64 __fastcall ASN1Dec_KERB_TICKET(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v11; // [rsp+20h] [rbp-30h] BYREF
  __int64 v12; // [rsp+28h] [rbp-28h] BYREF
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  int v16; // [rsp+78h] [rbp+28h] BYREF
  __int64 v17; // [rsp+88h] [rbp+38h] BYREF

  v3 = 0;
  v11 = 0;
  v14 = 0;
  v13 = 0;
  if ( !(_DWORD)a2 )
    a2 = 1073741825;
  v15 = 0;
  v17 = 0;
  v12 = 0;
  v16 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v13, &v15) )
    return 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v13, 16, &v11, &v14) )
    return 0;
  v6 = v11;
  *(_BYTE *)a3 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v6, 0x80000000LL, &v17, &v12) )
    return 0;
  if ( !(unsigned int)ASN1BERDecS32Val(v17, 2, a3 + 4) )
    return 0;
  if ( !(unsigned int)ASN1BERDecEndOfContents(v11, v17, v12) )
    return 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v11, 2147483649LL, &v17, &v12) )
    return 0;
  if ( !(unsigned int)ASN1BERDecZeroCharString(v17, 27, a3 + 8) )
    return 0;
  if ( !(unsigned int)ASN1BERDecEndOfContents(v11, v17, v12) )
    return 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v11, 2147483650LL, &v17, &v12) )
    return 0;
  if ( !(unsigned int)ASN1Dec_KERB_PRINCIPAL_NAME(v17, v7, a3 + 16) )
    return 0;
  if ( !(unsigned int)ASN1BERDecEndOfContents(v11, v17, v12) )
    return 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v11, 2147483651LL, &v17, &v12) )
    return 0;
  if ( !(unsigned int)ASN1Dec_KERB_ENCRYPTED_DATA(v17, 0, (_BYTE *)(a3 + 32)) )
    return 0;
  if ( !(unsigned int)ASN1BERDecEndOfContents(v11, v17, v12) )
    return 0;
  ASN1BERDecPeekTag(v11, &v16);
  if ( v16 == -2147483644 )
  {
    v8 = v11;
    *(_BYTE *)a3 |= 0x80u;
    if ( !(unsigned int)ASN1BERDecExplicitTag(v8, 2147483652LL, &v17, &v12)
      || !(unsigned int)ASN1Dec_PKERB_TICKET_EXTENSIONS(v17, v9, (__int64 *)(a3 + 64))
      || !(unsigned int)ASN1BERDecEndOfContents(v11, v17, v12) )
    {
      return 0;
    }
  }
  if ( !(unsigned int)ASN1BERDecEndOfContents(v13, v11, v14) )
    return 0;
  LOBYTE(v3) = (unsigned int)ASN1BERDecEndOfContents(a1, v13, v15) != 0;
  return v3;
}

```

## disassembly

```asm
0x18000bbf0  mov     [rsp-18h+arg_0], rbx
0x18000bbf5  push    rbp
0x18000bbf6  push    rsi
0x18000bbf7  push    rdi
0x18000bbf8  mov     rbp, rsp
0x18000bbfb  sub     rsp, 50h
0x18000bbff  xor     ebx, ebx
0x18000bc01  lea     r9, [rbp+var_10]
0x18000bc05  test    edx, edx
0x18000bc07  mov     [rbp+var_30], rbx
0x18000bc0b  mov     eax, 40000001h
0x18000bc10  mov     [rbp+var_18], rbx
0x18000bc14  mov     rdi, r8
0x18000bc17  mov     [rbp+var_20], rbx
0x18000bc1b  cmovz   edx, eax
0x18000bc1e  mov     [rbp+var_10], rbx
0x18000bc22  lea     r8, [rbp+var_20]
0x18000bc26  mov     [rbp+arg_18], rbx
0x18000bc2a  mov     rsi, rcx
0x18000bc2d  mov     [rbp+var_28], rbx
0x18000bc31  mov     [rbp+arg_8], ebx
0x18000bc34  call    cs:__imp_ASN1BERDecExplicitTag
0x18000bc3b  nop     dword ptr [rax+rax+00h]
0x18000bc40  test    eax, eax
0x18000bc42  jz      loc_18000BE93
0x18000bc48  mov     rcx, [rbp+var_20]
0x18000bc4c  lea     r9, [rbp+var_18]
0x18000bc50  lea     r8, [rbp+var_30]
0x18000bc54  lea     edx, [rbx+10h]
0x18000bc57  call    cs:__imp_ASN1BERDecExplicitTag
0x18000bc5e  nop     dword ptr [rax+rax+00h]
0x18000bc63  test    eax, eax
0x18000bc65  jz      loc_18000BE93
0x18000bc6b  mov     rcx, [rbp+var_30]
0x18000bc6f  lea     r9, [rbp+var_28]
0x18000bc73  xor     eax, eax
0x18000bc75  lea     r8, [rbp+arg_18]
0x18000bc79  mov     edx, 80000000h
0x18000bc7e  mov     [rdi], al
0x18000bc80  call    cs:__imp_ASN1BERDecExplicitTag
0x18000bc87  nop     dword ptr [rax+rax+00h]
0x18000bc8c  test    eax, eax
0x18000bc8e  jz      loc_18000BE93
0x18000bc94  mov     rcx, [rbp+arg_18]
0x18000bc98  lea     r8, [rdi+4]
0x18000bc9c  lea     edx, [rbx+2]
0x18000bc9f  call    cs:__imp_ASN1BERDecS32Val
0x18000bca6  nop     dword ptr [rax+rax+00h]
0x18000bcab  test    eax, eax
0x18000bcad  jz      loc_18000BE93
0x18000bcb3  mov     r8, [rbp+var_28]
0x18000bcb7  mov     rdx, [rbp+arg_18]
0x18000bcbb  mov     rcx, [rbp+var_30]
0x18000bcbf  call    cs:__imp_ASN1BERDecEndOfContents
0x18000bcc6  nop     dword ptr [rax+rax+00h]
0x18000bccb  test    eax, eax
0x18000bccd  jz      loc_18000BE93
0x18000bcd3  mov     rcx, [rbp+var_30]
0x18000bcd7  lea     r9, [rbp+var_28]
0x18000bcdb  lea     r8, [rbp+arg_18]
0x18000bcdf  mov     edx, 80000001h
0x18000bce4  call    cs:__imp_ASN1BERDecExplicitTag
0x18000bceb  nop     dword ptr [rax+rax+00h]
0x18000bcf0  test    eax, eax
0x18000bcf2  jz      loc_18000BE93
0x18000bcf8  mov     rcx, [rbp+arg_18]
0x18000bcfc  lea     r8, [rdi+8]
0x18000bd00  lea     edx, [rbx+1Bh]
0x18000bd03  call    cs:__imp_ASN1BERDecZeroCharString
0x18000bd0a  nop     dword ptr [rax+rax+00h]
0x18000bd0f  test    eax, eax
0x18000bd11  jz      loc_18000BE93
0x18000bd17  mov     r8, [rbp+var_28]
0x18000bd1b  mov     rdx, [rbp+arg_18]
0x18000bd1f  mov     rcx, [rbp+var_30]
0x18000bd23  call    cs:__imp_ASN1BERDecEndOfContents
0x18000bd2a  nop     dword ptr [rax+rax+00h]
0x18000bd2f  test    eax, eax
0x18000bd31  jz      loc_18000BE93
0x18000bd37  mov     rcx, [rbp+var_30]
0x18000bd3b  lea     r9, [rbp+var_28]
0x18000bd3f  lea     r8, [rbp+arg_18]
0x18000bd43  mov     edx, 80000002h
0x18000bd48  call    cs:__imp_ASN1BERDecExplicitTag
0x18000bd4f  nop     dword ptr [rax+rax+00h]
0x18000bd54  test    eax, eax
0x18000bd56  jz      loc_18000BE93
0x18000bd5c  mov     rcx, [rbp+arg_18]
0x18000bd60  lea     r8, [rdi+10h]
0x18000bd64  call    ASN1Dec_KERB_PRINCIPAL_NAME
0x18000bd69  test    eax, eax
0x18000bd6b  jz      loc_18000BE93
0x18000bd71  mov     r8, [rbp+var_28]
0x18000bd75  mov     rdx, [rbp+arg_18]
0x18000bd79  mov     rcx, [rbp+var_30]
0x18000bd7d  call    cs:__imp_ASN1BERDecEndOfContents
0x18000bd84  nop     dword ptr [rax+rax+00h]
0x18000bd89  test    eax, eax
0x18000bd8b  jz      loc_18000BE93
0x18000bd91  mov     rcx, [rbp+var_30]
0x18000bd95  lea     r9, [rbp+var_28]
0x18000bd99  lea     r8, [rbp+arg_18]
0x18000bd9d  mov     edx, 80000003h
0x18000bda2  call    cs:__imp_ASN1BERDecExplicitTag
0x18000bda9  nop     dword ptr [rax+rax+00h]
0x18000bdae  test    eax, eax
0x18000bdb0  jz      loc_18000BE93
0x18000bdb6  mov     rcx, [rbp+arg_18]
0x18000bdba  lea     r8, [rdi+20h]
0x18000bdbe  xor     edx, edx
0x18000bdc0  call    ASN1Dec_KERB_ENCRYPTED_DATA
0x18000bdc5  test    eax, eax
0x18000bdc7  jz      loc_18000BE93
0x18000bdcd  mov     r8, [rbp+var_28]
0x18000bdd1  mov     rdx, [rbp+arg_18]
0x18000bdd5  mov     rcx, [rbp+var_30]
0x18000bdd9  call    cs:__imp_ASN1BERDecEndOfContents
0x18000bde0  nop     dword ptr [rax+rax+00h]
0x18000bde5  test    eax, eax
0x18000bde7  jz      loc_18000BE93
0x18000bded  mov     rcx, [rbp+var_30]
0x18000bdf1  lea     rdx, [rbp+arg_8]
0x18000bdf5  call    cs:__imp_ASN1BERDecPeekTag
0x18000bdfc  nop     dword ptr [rax+rax+00h]
0x18000be01  mov     edx, 80000004h
0x18000be06  cmp     [rbp+arg_8], edx
0x18000be09  jnz     short loc_18000BE57
0x18000be0b  mov     rcx, [rbp+var_30]
0x18000be0f  lea     r9, [rbp+var_28]
0x18000be13  or      byte ptr [rdi], 80h
0x18000be16  lea     r8, [rbp+arg_18]
0x18000be1a  call    cs:__imp_ASN1BERDecExplicitTag
0x18000be21  nop     dword ptr [rax+rax+00h]
0x18000be26  test    eax, eax
0x18000be28  jz      short loc_18000BE93
0x18000be2a  mov     rcx, [rbp+arg_18]
0x18000be2e  lea     r8, [rdi+40h]
0x18000be32  call    ASN1Dec_PKERB_TICKET_EXTENSIONS
0x18000be37  test    eax, eax
0x18000be39  jz      short loc_18000BE93
0x18000be3b  mov     r8, [rbp+var_28]
0x18000be3f  mov     rdx, [rbp+arg_18]
0x18000be43  mov     rcx, [rbp+var_30]
0x18000be47  call    cs:__imp_ASN1BERDecEndOfContents
0x18000be4e  nop     dword ptr [rax+rax+00h]
0x18000be53  test    eax, eax
0x18000be55  jz      short loc_18000BE93
0x18000be57  mov     r8, [rbp+var_18]
0x18000be5b  mov     rdx, [rbp+var_30]
0x18000be5f  mov     rcx, [rbp+var_20]
0x18000be63  call    cs:__imp_ASN1BERDecEndOfContents
0x18000be6a  nop     dword ptr [rax+rax+00h]
0x18000be6f  test    eax, eax
0x18000be71  jz      short loc_18000BE93
0x18000be73  mov     r8, [rbp+var_10]
0x18000be77  mov     rcx, rsi
0x18000be7a  mov     rdx, [rbp+var_20]
0x18000be7e  call    cs:__imp_ASN1BERDecEndOfContents
0x18000be85  nop     dword ptr [rax+rax+00h]
0x18000be8a  test    eax, eax
0x18000be8c  setnz   bl
0x18000be8f  mov     eax, ebx
0x18000be91  jmp     short loc_18000BE95
0x18000be93  xor     eax, eax
0x18000be95  mov     rbx, [rsp+50h+arg_0]
0x18000be9a  add     rsp, 50h
0x18000be9e  pop     rdi
0x18000be9f  pop     rsi
0x18000bea0  pop     rbp
0x18000bea1  retn
```
