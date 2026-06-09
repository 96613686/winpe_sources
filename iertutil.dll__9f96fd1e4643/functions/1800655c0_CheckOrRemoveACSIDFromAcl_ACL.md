# CheckOrRemoveACSIDFromAcl(_ACL *)

- ea: `0x1800655c0`
- end: `0x18006568c`
- name: `?CheckOrRemoveACSIDFromAcl@@YA_NPEAU_ACL@@@Z`
- size: `204`
- prototype: `bool __fastcall(PACL pAcl)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800306b0`

## callees

- `0x1800655c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800655fb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800655fb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180065642`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180065642`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180065616`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180065616`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180065652`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180065652`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18006566c`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18006566c`

## pseudocode

```c
char __fastcall CheckOrRemoveACSIDFromAcl(PACL pAcl)
{
  char v1; // di
  WORD i; // bx
  char *v4; // rbp
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  LPVOID pAce; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  for ( i = 0; i < pAcl->AceCount; ++i )
  {
    pAce = 0;
    if ( GetAce(pAcl, i, &pAce) )
    {
      if ( !*(_BYTE *)pAce )
      {
        v4 = (char *)pAce + 8;
        SidIdentifierAuthority = GetSidIdentifierAuthority((char *)pAce + 8);
        if ( SidIdentifierAuthority->Value[5] == 15
          && !SidIdentifierAuthority->Value[4]
          && !SidIdentifierAuthority->Value[3]
          && !SidIdentifierAuthority->Value[2]
          && !SidIdentifierAuthority->Value[1]
          && !SidIdentifierAuthority->Value[0]
          && *GetSidSubAuthorityCount(v4) >= 8u
          && *GetSidSubAuthority(v4, 0) == 2 )
        {
          return DeleteAce(pAcl, i);
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800655c0  push    rbx
0x1800655c2  push    rbp
0x1800655c3  push    rsi
0x1800655c4  push    rdi
0x1800655c5  push    r12
0x1800655c7  push    r14
0x1800655c9  sub     rsp, 28h
0x1800655cd  xor     dil, dil
0x1800655d0  mov     rsi, rcx
0x1800655d3  xor     ebx, ebx
0x1800655d5  lea     r12d, [rbx+1]
0x1800655d9  cmp     bx, [rsi+4]
0x1800655dd  jnb     loc_18006567C
0x1800655e3  movzx   r14d, bx
0x1800655e7  lea     r8, [rsp+58h+pAce]; pAce
0x1800655ec  mov     edx, r14d; dwAceIndex
0x1800655ef  mov     [rsp+58h+pAce], 0
0x1800655f8  mov     rcx, rsi; pAcl
0x1800655fb  call    cs:__imp_GetAce
0x180065601  test    eax, eax
0x180065603  jz      short loc_18006565D
0x180065605  mov     rax, [rsp+58h+pAce]
0x18006560a  cmp     [rax], dil
0x18006560d  jnz     short loc_18006565D
0x18006560f  lea     rbp, [rax+8]
0x180065613  mov     rcx, rbp; pSid
0x180065616  call    cs:__imp_GetSidIdentifierAuthority
0x18006561c  cmp     byte ptr [rax+5], 0Fh
0x180065620  jnz     short loc_18006565D
0x180065622  cmp     [rax+4], dil
0x180065626  jnz     short loc_18006565D
0x180065628  cmp     [rax+3], dil
0x18006562c  jnz     short loc_18006565D
0x18006562e  cmp     [rax+2], dil
0x180065632  jnz     short loc_18006565D
0x180065634  cmp     [rax+1], dil
0x180065638  jnz     short loc_18006565D
0x18006563a  cmp     [rax], dil
0x18006563d  jnz     short loc_18006565D
0x18006563f  mov     rcx, rbp; pSid
0x180065642  call    cs:__imp_GetSidSubAuthorityCount
0x180065648  cmp     byte ptr [rax], 8
0x18006564b  jb      short loc_18006565D
0x18006564d  xor     edx, edx; nSubAuthority
0x18006564f  mov     rcx, rbp; pSid
0x180065652  call    cs:__imp_GetSidSubAuthority
0x180065658  cmp     dword ptr [rax], 2
0x18006565b  jz      short loc_180065666
0x18006565d  add     bx, r12w
0x180065661  jmp     loc_1800655D9
0x180065666  mov     edx, r14d; dwAceIndex
0x180065669  mov     rcx, rsi; pAcl
0x18006566c  call    cs:__imp_DeleteAce
0x180065672  test    eax, eax
0x180065674  movzx   edi, dil
0x180065678  cmovnz  edi, r12d
0x18006567c  mov     al, dil
0x18006567f  add     rsp, 28h
0x180065683  pop     r14
0x180065685  pop     r12
0x180065687  pop     rdi
0x180065688  pop     rsi
0x180065689  pop     rbp
0x18006568a  pop     rbx
0x18006568b  retn
```
