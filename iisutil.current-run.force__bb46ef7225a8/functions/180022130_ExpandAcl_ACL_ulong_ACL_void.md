# ExpandAcl(_ACL *,ulong,_ACL * *,void *)

- ea: `0x180022130`
- end: `0x180022232`
- name: `?ExpandAcl@@YAJPEAU_ACL@@KPEAPEAU1@PEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(PACL pAcl, unsigned int, struct _ACL **, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180021a1c`

## callees

- `0x1800183f8`
- `0x180018438`
- `0x180022130`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002220a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002220a`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800221ed`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800221ed`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180022170`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180022170`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800221ae`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800221ae`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022181`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022181`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800221ca`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800221ca`

## pseudocode

```c
signed int __fastcall ExpandAcl(PACL pAcl, int a2, struct _ACL **a3, void *a4)
{
  signed int v8; // ebx
  struct _ACL *v9; // rax
  struct _ACL *v10; // rdi
  signed int result; // eax
  DWORD i; // ebx
  LPVOID pAce; // [rsp+30h] [rbp-48h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-40h] BYREF
  int v15; // [rsp+40h] [rbp-38h]

  pAclInformation = 0;
  v15 = 0;
  pAce = 0;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    goto LABEL_12;
  v8 = GetLengthSid(a4) + a2 + 32;
  v9 = (struct _ACL *)operator new(v8);
  v10 = v9;
  if ( !v9 )
    return -2147024882;
  if ( !InitializeAcl(v9, v8, 2u) )
  {
LABEL_11:
    operator delete(v10);
LABEL_12:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    if ( !GetAce(pAcl, i, &pAce) || !AddAce(v10, 2u, i, pAce, *((unsigned __int16 *)pAce + 1)) )
      goto LABEL_11;
  }
  *a3 = v10;
  return 0;
}

```

## disassembly

```asm
0x180022130  push    rbx
0x180022132  push    rbp
0x180022133  push    rsi
0x180022134  push    rdi
0x180022135  sub     rsp, 58h
0x180022139  mov     rax, cs:__security_cookie
0x180022140  xor     rax, rsp
0x180022143  mov     [rsp+78h+var_30], rax
0x180022148  xor     eax, eax
0x18002214a  mov     rdi, r9
0x18002214d  mov     rsi, r8
0x180022150  mov     [rsp+78h+pAclInformation], rax
0x180022155  mov     ebx, edx
0x180022157  mov     [rsp+78h+var_38], eax
0x18002215b  lea     rdx, [rsp+78h+pAclInformation]; pAclInformation
0x180022160  mov     [rsp+78h+pAce], rax
0x180022165  lea     r9d, [rax+2]; dwAclInformationClass
0x180022169  mov     rbp, rcx
0x18002216c  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180022170  call    cs:__imp_GetAclInformation
0x180022176  test    eax, eax
0x180022178  jz      loc_18002220A
0x18002217e  mov     rcx, rdi; pSid
0x180022181  call    cs:__imp_GetLengthSid
0x180022187  add     ebx, 20h ; ' '
0x18002218a  add     ebx, eax
0x18002218c  movsxd  rcx, ebx; Size
0x18002218f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022194  mov     rdi, rax
0x180022197  test    rax, rax
0x18002219a  jnz     short loc_1800221A3
0x18002219c  mov     eax, 8007000Eh
0x1800221a1  jmp     short loc_18002221C
0x1800221a3  mov     r8d, 2; dwAclRevision
0x1800221a9  mov     edx, ebx; nAclLength
0x1800221ab  mov     rcx, rdi; pAcl
0x1800221ae  call    cs:__imp_InitializeAcl
0x1800221b4  test    eax, eax
0x1800221b6  jz      short loc_180022202
0x1800221b8  xor     ebx, ebx
0x1800221ba  cmp     ebx, dword ptr [rsp+78h+pAclInformation]
0x1800221be  jnb     short loc_1800221FB
0x1800221c0  lea     r8, [rsp+78h+pAce]; pAce
0x1800221c5  mov     edx, ebx; dwAceIndex
0x1800221c7  mov     rcx, rbp; pAcl
0x1800221ca  call    cs:__imp_GetAce
0x1800221d0  test    eax, eax
0x1800221d2  jz      short loc_180022202
0x1800221d4  mov     r9, [rsp+78h+pAce]; pAceList
0x1800221d9  mov     r8d, ebx; dwStartingAceIndex
0x1800221dc  mov     edx, 2; dwAceRevision
0x1800221e1  mov     rcx, rdi; pAcl
0x1800221e4  movzx   eax, word ptr [r9+2]
0x1800221e9  mov     [rsp+78h+nAceListLength], eax; nAceListLength
0x1800221ed  call    cs:__imp_AddAce
0x1800221f3  test    eax, eax
0x1800221f5  jz      short loc_180022202
0x1800221f7  inc     ebx
0x1800221f9  jmp     short loc_1800221BA
0x1800221fb  mov     [rsi], rdi
0x1800221fe  xor     eax, eax
0x180022200  jmp     short loc_18002221C
0x180022202  mov     rcx, rdi; Block
0x180022205  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002220a  call    cs:__imp_GetLastError
0x180022210  test    eax, eax
0x180022212  jle     short loc_18002221C
0x180022214  movzx   eax, ax
0x180022217  or      eax, 80070000h
0x18002221c  mov     rcx, [rsp+78h+var_30]
0x180022221  xor     rcx, rsp; StackCookie
0x180022224  call    __security_check_cookie
0x180022229  add     rsp, 58h
0x18002222d  pop     rdi
0x18002222e  pop     rsi
0x18002222f  pop     rbp
0x180022230  pop     rbx
0x180022231  retn
```
