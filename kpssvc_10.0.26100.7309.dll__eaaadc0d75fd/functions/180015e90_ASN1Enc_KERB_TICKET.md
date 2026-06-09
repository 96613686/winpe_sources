# ASN1Enc_KERB_TICKET

- ea: `0x180015e90`
- end: `0x1800160e3`
- name: `ASN1Enc_KERB_TICKET`
- size: `595`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f1c0`
- `0x18001050c`
- `0x1800129b8`
- `0x18001329c`
- `0x180015b30`

## callees

- `0x180010fb0`
- `0x180014614`
- `0x180015e90`
- `0x180017324`

## import_xrefs

- `MSASN1!ASN1BEREncExplicitTag` at `0x180015ec4`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015ee2`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015f02`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015f6d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015fc8`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180016016`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180016066`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015ec4`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015ee2`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015f02`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015f6d`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180015fc8`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180016016`
- `MSASN1!ASN1BEREncExplicitTag` at `0x180016066`
- `MSASN1!ASN1BEREncS32` at `0x180015f20`
- `MSASN1!ASN1BEREncS32` at `0x180015f20`
- `MSASN1!ASN1DEREncCharString` at `0x180015f8e`
- `MSASN1!ASN1DEREncCharString` at `0x180015f8e`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180015f3a`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180015fa8`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180015ff6`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180016046`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001608c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800160a2`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800160b8`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180015f3a`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180015fa8`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180015ff6`
- `MSASN1!ASN1BEREncEndOfContents` at `0x180016046`
- `MSASN1!ASN1BEREncEndOfContents` at `0x18001608c`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800160a2`
- `MSASN1!ASN1BEREncEndOfContents` at `0x1800160b8`
- `KERNEL32!lstrlenA` at `0x180015f52`
- `KERNEL32!lstrlenA` at `0x180015f52`

## pseudocode

```c
__int64 __fastcall ASN1Enc_KERB_TICKET(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  unsigned int v6; // r14d
  __int64 v7; // rdx
  unsigned int v8; // edx
  _DWORD v10[4]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v11; // [rsp+58h] [rbp+28h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+38h] BYREF

  v3 = 0;
  v10[0] = 0;
  v12 = 0;
  if ( !(_DWORD)a2 )
    a2 = 1073741825;
  v11 = 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, a2, v10) )
    return 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 16, &v12) )
    return 0;
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 0x80000000LL, &v11) )
    return 0;
  if ( !(unsigned int)ASN1BEREncS32(a1, 2, *(unsigned int *)(a3 + 4)) )
    return 0;
  if ( !(unsigned int)ASN1BEREncEndOfContents(a1, v11) )
    return 0;
  v6 = lstrlenA(*(LPCSTR *)(a3 + 8));
  if ( !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483649LL, &v11)
    || !(unsigned int)ASN1DEREncCharString(a1, 27, v6, *(_QWORD *)(a3 + 8))
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v11)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483650LL, &v11)
    || !(unsigned int)ASN1Enc_KERB_PRINCIPAL_NAME(a1, v7, (unsigned int *)(a3 + 16))
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v11)
    || !(unsigned int)ASN1BEREncExplicitTag(a1, 2147483651LL, &v11)
    || !(unsigned int)ASN1Enc_KERB_ENCRYPTED_DATA(a1, 0, a3 + 32)
    || !(unsigned int)ASN1BEREncEndOfContents(a1, v11)
    || *(char *)a3 < 0
    && (!(unsigned int)ASN1BEREncExplicitTag(a1, 2147483652LL, &v11)
     || !(unsigned int)ASN1Enc_PKERB_TICKET_EXTENSIONS(a1, v8, (__int64 **)(a3 + 64))
     || !(unsigned int)ASN1BEREncEndOfContents(a1, v11)) )
  {
    return 0;
  }
  if ( !(unsigned int)ASN1BEREncEndOfContents(a1, v12) )
    return 0;
  LOBYTE(v3) = (unsigned int)ASN1BEREncEndOfContents(a1, v10[0]) != 0;
  return v3;
}

```

## disassembly

```asm
0x180015e90  mov     [rsp-18h+arg_0], rbx
0x180015e95  mov     [rsp-18h+arg_10], rsi
0x180015e9a  push    rbp
0x180015e9b  push    rdi
0x180015e9c  push    r14
0x180015e9e  mov     rbp, rsp
0x180015ea1  sub     rsp, 30h
0x180015ea5  xor     ebx, ebx
0x180015ea7  mov     eax, 40000001h
0x180015eac  test    edx, edx
0x180015eae  mov     [rbp+var_10], ebx
0x180015eb1  mov     rsi, r8
0x180015eb4  mov     [rbp+arg_18], ebx
0x180015eb7  cmovz   edx, eax
0x180015eba  mov     [rbp+arg_8], ebx
0x180015ebd  lea     r8, [rbp+var_10]
0x180015ec1  mov     rdi, rcx
0x180015ec4  call    cs:__imp_ASN1BEREncExplicitTag
0x180015ecb  nop     dword ptr [rax+rax+00h]
0x180015ed0  test    eax, eax
0x180015ed2  jz      loc_1800160CD
0x180015ed8  lea     r8, [rbp+arg_18]
0x180015edc  mov     rcx, rdi
0x180015edf  lea     edx, [rbx+10h]
0x180015ee2  call    cs:__imp_ASN1BEREncExplicitTag
0x180015ee9  nop     dword ptr [rax+rax+00h]
0x180015eee  test    eax, eax
0x180015ef0  jz      loc_1800160CD
0x180015ef6  lea     r8, [rbp+arg_8]
0x180015efa  mov     edx, 80000000h
0x180015eff  mov     rcx, rdi
0x180015f02  call    cs:__imp_ASN1BEREncExplicitTag
0x180015f09  nop     dword ptr [rax+rax+00h]
0x180015f0e  test    eax, eax
0x180015f10  jz      loc_1800160CD
0x180015f16  mov     r8d, [rsi+4]
0x180015f1a  lea     edx, [rbx+2]
0x180015f1d  mov     rcx, rdi
0x180015f20  call    cs:__imp_ASN1BEREncS32
0x180015f27  nop     dword ptr [rax+rax+00h]
0x180015f2c  test    eax, eax
0x180015f2e  jz      loc_1800160CD
0x180015f34  mov     edx, [rbp+arg_8]
0x180015f37  mov     rcx, rdi
0x180015f3a  call    cs:__imp_ASN1BEREncEndOfContents
0x180015f41  nop     dword ptr [rax+rax+00h]
0x180015f46  test    eax, eax
0x180015f48  jz      loc_1800160CD
0x180015f4e  mov     rcx, [rsi+8]; lpString
0x180015f52  call    cs:__imp_lstrlenA
0x180015f59  nop     dword ptr [rax+rax+00h]
0x180015f5e  lea     r8, [rbp+arg_8]
0x180015f62  mov     edx, 80000001h
0x180015f67  mov     rcx, rdi
0x180015f6a  mov     r14d, eax
0x180015f6d  call    cs:__imp_ASN1BEREncExplicitTag
0x180015f74  nop     dword ptr [rax+rax+00h]
0x180015f79  test    eax, eax
0x180015f7b  jz      loc_1800160CD
0x180015f81  mov     r9, [rsi+8]
0x180015f85  lea     edx, [rbx+1Bh]
0x180015f88  mov     r8d, r14d
0x180015f8b  mov     rcx, rdi
0x180015f8e  call    cs:__imp_ASN1DEREncCharString
0x180015f95  nop     dword ptr [rax+rax+00h]
0x180015f9a  test    eax, eax
0x180015f9c  jz      loc_1800160CD
0x180015fa2  mov     edx, [rbp+arg_8]
0x180015fa5  mov     rcx, rdi
0x180015fa8  call    cs:__imp_ASN1BEREncEndOfContents
0x180015faf  nop     dword ptr [rax+rax+00h]
0x180015fb4  test    eax, eax
0x180015fb6  jz      loc_1800160CD
0x180015fbc  lea     r8, [rbp+arg_8]
0x180015fc0  mov     edx, 80000002h
0x180015fc5  mov     rcx, rdi
0x180015fc8  call    cs:__imp_ASN1BEREncExplicitTag
0x180015fcf  nop     dword ptr [rax+rax+00h]
0x180015fd4  test    eax, eax
0x180015fd6  jz      loc_1800160CD
0x180015fdc  lea     r8, [rsi+10h]
0x180015fe0  mov     rcx, rdi
0x180015fe3  call    ASN1Enc_KERB_PRINCIPAL_NAME
0x180015fe8  test    eax, eax
0x180015fea  jz      loc_1800160CD
0x180015ff0  mov     edx, [rbp+arg_8]
0x180015ff3  mov     rcx, rdi
0x180015ff6  call    cs:__imp_ASN1BEREncEndOfContents
0x180015ffd  nop     dword ptr [rax+rax+00h]
0x180016002  test    eax, eax
0x180016004  jz      loc_1800160CD
0x18001600a  lea     r8, [rbp+arg_8]
0x18001600e  mov     edx, 80000003h
0x180016013  mov     rcx, rdi
0x180016016  call    cs:__imp_ASN1BEREncExplicitTag
0x18001601d  nop     dword ptr [rax+rax+00h]
0x180016022  test    eax, eax
0x180016024  jz      loc_1800160CD
0x18001602a  lea     r8, [rsi+20h]
0x18001602e  xor     edx, edx
0x180016030  mov     rcx, rdi
0x180016033  call    ASN1Enc_KERB_ENCRYPTED_DATA
0x180016038  test    eax, eax
0x18001603a  jz      loc_1800160CD
0x180016040  mov     edx, [rbp+arg_8]
0x180016043  mov     rcx, rdi
0x180016046  call    cs:__imp_ASN1BEREncEndOfContents
0x18001604d  nop     dword ptr [rax+rax+00h]
0x180016052  test    eax, eax
0x180016054  jz      short loc_1800160CD
0x180016056  cmp     [rsi], bl
0x180016058  jge     short loc_18001609C
0x18001605a  lea     r8, [rbp+arg_8]
0x18001605e  mov     edx, 80000004h
0x180016063  mov     rcx, rdi
0x180016066  call    cs:__imp_ASN1BEREncExplicitTag
0x18001606d  nop     dword ptr [rax+rax+00h]
0x180016072  test    eax, eax
0x180016074  jz      short loc_1800160CD
0x180016076  lea     r8, [rsi+40h]
0x18001607a  mov     rcx, rdi
0x18001607d  call    ASN1Enc_PKERB_TICKET_EXTENSIONS
0x180016082  test    eax, eax
0x180016084  jz      short loc_1800160CD
0x180016086  mov     edx, [rbp+arg_8]
0x180016089  mov     rcx, rdi
0x18001608c  call    cs:__imp_ASN1BEREncEndOfContents
0x180016093  nop     dword ptr [rax+rax+00h]
0x180016098  test    eax, eax
0x18001609a  jz      short loc_1800160CD
0x18001609c  mov     edx, [rbp+arg_18]
0x18001609f  mov     rcx, rdi
0x1800160a2  call    cs:__imp_ASN1BEREncEndOfContents
0x1800160a9  nop     dword ptr [rax+rax+00h]
0x1800160ae  test    eax, eax
0x1800160b0  jz      short loc_1800160CD
0x1800160b2  mov     edx, [rbp+var_10]
0x1800160b5  mov     rcx, rdi
0x1800160b8  call    cs:__imp_ASN1BEREncEndOfContents
0x1800160bf  nop     dword ptr [rax+rax+00h]
0x1800160c4  test    eax, eax
0x1800160c6  setnz   bl
0x1800160c9  mov     eax, ebx
0x1800160cb  jmp     short loc_1800160CF
0x1800160cd  xor     eax, eax
0x1800160cf  mov     rbx, [rsp+30h+arg_0]
0x1800160d4  mov     rsi, [rsp+30h+arg_10]
0x1800160d9  add     rsp, 30h
0x1800160dd  pop     r14
0x1800160df  pop     rdi
0x1800160e0  pop     rbp
0x1800160e1  retn
```
