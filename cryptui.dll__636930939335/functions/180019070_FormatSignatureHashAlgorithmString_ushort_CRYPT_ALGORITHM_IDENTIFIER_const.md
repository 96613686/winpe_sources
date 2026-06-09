# FormatSignatureHashAlgorithmString(ushort * *,_CRYPT_ALGORITHM_IDENTIFIER const *)

- ea: `0x180019070`
- end: `0x1800190d2`
- name: `?FormatSignatureHashAlgorithmString@@YAHPEAPEAGPEBU_CRYPT_ALGORITHM_IDENTIFIER@@@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned __int16 **, const struct _CRYPT_ALGORITHM_IDENTIFIER *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008b10`
- `0x18000d72c`

## callees

- `0x180017978`
- `0x180019070`

## import_xrefs

- `certca!__imp_?myGetHashAlgorithmOIDInfoFromSignatureAlgorithm@@YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEBU_CRYPT_OID_INFO@@@Z` at `0x180019098`
- `certca!__imp_?myGetHashAlgorithmOIDInfoFromSignatureAlgorithm@@YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEBU_CRYPT_OID_INFO@@@Z` at `0x180019098`

## pseudocode

```c
__int64 __fastcall FormatSignatureHashAlgorithmString(
        unsigned __int16 **a1,
        const struct _CRYPT_ALGORITHM_IDENTIFIER *a2)
{
  unsigned int v2; // ebx
  const struct _CRYPT_OID_INFO *v5; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  if ( a2->pszObjId )
  {
    v5 = 0;
    if ( !myGetHashAlgorithmOIDInfoFromSignatureAlgorithm(a2, &v5) )
      return CertUIGetOIDName(a1, 0, 1u, v5->pszOID) != 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180019070  mov     r11, rsp
0x180019073  mov     [r11+8], rbx
0x180019077  mov     [r11+18h], rsi
0x18001907b  push    rdi
0x18001907c  sub     rsp, 20h
0x180019080  xor     ebx, ebx
0x180019082  mov     rax, rdx
0x180019085  mov     rdi, rcx
0x180019088  cmp     [rdx], rbx
0x18001908b  jz      short loc_1800190C0
0x18001908d  lea     rdx, [r11+10h]
0x180019091  mov     [r11+10h], rbx
0x180019095  mov     rcx, rax
0x180019098  call    cs:__imp_?myGetHashAlgorithmOIDInfoFromSignatureAlgorithm@@YAJPEBU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEBU_CRYPT_OID_INFO@@@Z; myGetHashAlgorithmOIDInfoFromSignatureAlgorithm(_CRYPT_ALGORITHM_IDENTIFIER const *,_CRYPT_OID_INFO const * *)
0x18001909e  test    eax, eax
0x1800190a0  jnz     short loc_1800190C0
0x1800190a2  mov     r9, [rsp+28h+arg_8]
0x1800190a7  lea     esi, [rbx+1]
0x1800190aa  mov     r8d, esi; unsigned int
0x1800190ad  xor     edx, edx; unsigned int
0x1800190af  mov     rcx, rdi; unsigned __int16 **
0x1800190b2  mov     r9, [r9+8]; char *
0x1800190b6  call    ?CertUIGetOIDName@@YAHPEAPEAGKKPEBD@Z; CertUIGetOIDName(ushort * *,ulong,ulong,char const *)
0x1800190bb  test    eax, eax
0x1800190bd  cmovnz  ebx, esi
0x1800190c0  mov     rsi, [rsp+28h+arg_10]
0x1800190c5  mov     eax, ebx
0x1800190c7  mov     rbx, [rsp+28h+arg_0]
0x1800190cc  add     rsp, 20h
0x1800190d0  pop     rdi
0x1800190d1  retn
```
