# ASN1Dec_KERB_ENCRYPTED_DATA

- ea: `0x180005800`
- end: `0x1800059bc`
- name: `ASN1Dec_KERB_ENCRYPTED_DATA`
- size: `444`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022a0`
- `0x180002d80`
- `0x180002f80`
- `0x180004160`
- `0x180006b90`
- `0x180007844`
- `0x180007e28`
- `0x180009020`
- `0x180009fd0`
- `0x18000bbf0`
- `0x18000c268`
- `0x18000c370`

## callees

- `0x180005800`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x1800058be`
- `MSASN1!ASN1BERDecPeekTag` at `0x1800058be`
- `MSASN1!ASN1BERDecOctetString` at `0x180005960`
- `MSASN1!ASN1BERDecOctetString` at `0x180005960`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800058a2`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005922`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000597c`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005997`
- `MSASN1!ASN1BERDecEndOfContents` at `0x1800058a2`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005922`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000597c`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180005997`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000583a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180005863`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800058e3`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180005943`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000583a`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180005863`
- `MSASN1!ASN1BERDecExplicitTag` at `0x1800058e3`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180005943`
- `MSASN1!ASN1BERDecS32Val` at `0x180005882`
- `MSASN1!ASN1BERDecS32Val` at `0x180005902`
- `MSASN1!ASN1BERDecS32Val` at `0x180005882`
- `MSASN1!ASN1BERDecS32Val` at `0x180005902`

## pseudocode

```c
__int64 __fastcall ASN1Dec_KERB_ENCRYPTED_DATA(__int64 a1, __int64 a2, _BYTE *a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  int v12; // [rsp+68h] [rbp+28h] BYREF
  __int64 v13; // [rsp+78h] [rbp+38h] BYREF

  v3 = 0;
  v9 = 0;
  v11 = 0;
  v13 = 0;
  v10 = 0;
  if ( !(_DWORD)a2 )
    a2 = 16;
  v12 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, a2, &v9, &v11) )
    return 0;
  v6 = v9;
  *a3 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(v6, 0x80000000LL, &v13, &v10) )
    return 0;
  if ( !(unsigned int)ASN1BERDecS32Val(v13, 2, a3 + 4) )
    return 0;
  if ( !(unsigned int)ASN1BERDecEndOfContents(v9, v13, v10) )
    return 0;
  ASN1BERDecPeekTag(v9, &v12);
  if ( v12 == -2147483647 )
  {
    v7 = v9;
    *a3 |= 0x80u;
    if ( !(unsigned int)ASN1BERDecExplicitTag(v7, 2147483649LL, &v13, &v10)
      || !(unsigned int)ASN1BERDecS32Val(v13, 2, a3 + 8)
      || !(unsigned int)ASN1BERDecEndOfContents(v9, v13, v10) )
    {
      return 0;
    }
  }
  if ( !(unsigned int)ASN1BERDecExplicitTag(v9, 2147483650LL, &v13, &v10)
    || !(unsigned int)ASN1BERDecOctetString(v13, 4, a3 + 16)
    || !(unsigned int)ASN1BERDecEndOfContents(v9, v13, v10) )
  {
    return 0;
  }
  LOBYTE(v3) = (unsigned int)ASN1BERDecEndOfContents(a1, v9, v11) != 0;
  return v3;
}

```

## disassembly

```asm
0x180005800  mov     [rsp-18h+arg_0], rbx
0x180005805  push    rbp
0x180005806  push    rsi
0x180005807  push    rdi
0x180005808  mov     rbp, rsp
0x18000580b  sub     rsp, 40h
0x18000580f  xor     ebx, ebx
0x180005811  lea     r9, [rbp+var_10]
0x180005815  test    edx, edx
0x180005817  mov     [rbp+var_20], rbx
0x18000581b  mov     rdi, r8
0x18000581e  mov     [rbp+var_10], rbx
0x180005822  lea     r8, [rbp+var_20]
0x180005826  mov     [rbp+arg_18], rbx
0x18000582a  lea     eax, [rbx+10h]
0x18000582d  mov     [rbp+var_18], rbx
0x180005831  cmovz   edx, eax
0x180005834  mov     [rbp+arg_8], ebx
0x180005837  mov     rsi, rcx
0x18000583a  call    cs:__imp_ASN1BERDecExplicitTag
0x180005841  nop     dword ptr [rax+rax+00h]
0x180005846  test    eax, eax
0x180005848  jz      loc_1800059AC
0x18000584e  mov     rcx, [rbp+var_20]
0x180005852  lea     r9, [rbp+var_18]
0x180005856  xor     eax, eax
0x180005858  lea     r8, [rbp+arg_18]
0x18000585c  mov     edx, 80000000h
0x180005861  mov     [rdi], al
0x180005863  call    cs:__imp_ASN1BERDecExplicitTag
0x18000586a  nop     dword ptr [rax+rax+00h]
0x18000586f  test    eax, eax
0x180005871  jz      loc_1800059AC
0x180005877  mov     rcx, [rbp+arg_18]
0x18000587b  lea     r8, [rdi+4]
0x18000587f  lea     edx, [rbx+2]
0x180005882  call    cs:__imp_ASN1BERDecS32Val
0x180005889  nop     dword ptr [rax+rax+00h]
0x18000588e  test    eax, eax
0x180005890  jz      loc_1800059AC
0x180005896  mov     r8, [rbp+var_18]
0x18000589a  mov     rdx, [rbp+arg_18]
0x18000589e  mov     rcx, [rbp+var_20]
0x1800058a2  call    cs:__imp_ASN1BERDecEndOfContents
0x1800058a9  nop     dword ptr [rax+rax+00h]
0x1800058ae  test    eax, eax
0x1800058b0  jz      loc_1800059AC
0x1800058b6  mov     rcx, [rbp+var_20]
0x1800058ba  lea     rdx, [rbp+arg_8]
0x1800058be  call    cs:__imp_ASN1BERDecPeekTag
0x1800058c5  nop     dword ptr [rax+rax+00h]
0x1800058ca  mov     edx, 80000001h
0x1800058cf  cmp     [rbp+arg_8], edx
0x1800058d2  jnz     short loc_180005932
0x1800058d4  mov     rcx, [rbp+var_20]
0x1800058d8  lea     r9, [rbp+var_18]
0x1800058dc  or      byte ptr [rdi], 80h
0x1800058df  lea     r8, [rbp+arg_18]
0x1800058e3  call    cs:__imp_ASN1BERDecExplicitTag
0x1800058ea  nop     dword ptr [rax+rax+00h]
0x1800058ef  test    eax, eax
0x1800058f1  jz      loc_1800059AC
0x1800058f7  mov     rcx, [rbp+arg_18]
0x1800058fb  lea     r8, [rdi+8]
0x1800058ff  lea     edx, [rbx+2]
0x180005902  call    cs:__imp_ASN1BERDecS32Val
0x180005909  nop     dword ptr [rax+rax+00h]
0x18000590e  test    eax, eax
0x180005910  jz      loc_1800059AC
0x180005916  mov     r8, [rbp+var_18]
0x18000591a  mov     rdx, [rbp+arg_18]
0x18000591e  mov     rcx, [rbp+var_20]
0x180005922  call    cs:__imp_ASN1BERDecEndOfContents
0x180005929  nop     dword ptr [rax+rax+00h]
0x18000592e  test    eax, eax
0x180005930  jz      short loc_1800059AC
0x180005932  mov     rcx, [rbp+var_20]
0x180005936  lea     r9, [rbp+var_18]
0x18000593a  lea     r8, [rbp+arg_18]
0x18000593e  mov     edx, 80000002h
0x180005943  call    cs:__imp_ASN1BERDecExplicitTag
0x18000594a  nop     dword ptr [rax+rax+00h]
0x18000594f  test    eax, eax
0x180005951  jz      short loc_1800059AC
0x180005953  mov     rcx, [rbp+arg_18]
0x180005957  lea     r8, [rdi+10h]
0x18000595b  mov     edx, 4
0x180005960  call    cs:__imp_ASN1BERDecOctetString
0x180005967  nop     dword ptr [rax+rax+00h]
0x18000596c  test    eax, eax
0x18000596e  jz      short loc_1800059AC
0x180005970  mov     r8, [rbp+var_18]
0x180005974  mov     rdx, [rbp+arg_18]
0x180005978  mov     rcx, [rbp+var_20]
0x18000597c  call    cs:__imp_ASN1BERDecEndOfContents
0x180005983  nop     dword ptr [rax+rax+00h]
0x180005988  test    eax, eax
0x18000598a  jz      short loc_1800059AC
0x18000598c  mov     r8, [rbp+var_10]
0x180005990  mov     rcx, rsi
0x180005993  mov     rdx, [rbp+var_20]
0x180005997  call    cs:__imp_ASN1BERDecEndOfContents
0x18000599e  nop     dword ptr [rax+rax+00h]
0x1800059a3  test    eax, eax
0x1800059a5  setnz   bl
0x1800059a8  mov     eax, ebx
0x1800059aa  jmp     short loc_1800059AE
0x1800059ac  xor     eax, eax
0x1800059ae  mov     rbx, [rsp+40h+arg_0]
0x1800059b3  add     rsp, 40h
0x1800059b7  pop     rdi
0x1800059b8  pop     rsi
0x1800059b9  pop     rbp
0x1800059ba  retn
```
