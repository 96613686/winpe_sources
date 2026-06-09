# FapRemoveAcesForTypeAndFlagsAndSid

- ea: `0x18002a898`
- end: `0x18002a957`
- name: `FapRemoveAcesForTypeAndFlagsAndSid`
- size: `191`
- prototype: `__int64 __fastcall(PACL pAcl)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800244a4`

## callees

- `0x1800254e0`
- `0x18002a898`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002a901`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002a901`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002a91e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002a91e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002a8e3`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002a8e3`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18002a92d`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18002a92d`

## pseudocode

```c
void __fastcall FapRemoveAcesForTypeAndFlagsAndSid(PACL pAcl, __int64 a2, __int64 a3, void *a4)
{
  DWORD v6; // edi
  DWORD i; // ebx
  LPVOID pAce; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+28h] [rbp-30h] BYREF
  int v10; // [rsp+30h] [rbp-28h]

  if ( pAcl )
  {
    v9 = 0;
    v10 = 0;
    pAce = 0;
    if ( a4 )
    {
      if ( GetAclInformation(pAcl, &v9, 0xCu, AclSizeInformation) )
      {
        v6 = v9;
        for ( i = 0; i < v6; ++i )
        {
          GetAce(pAcl, i, &pAce);
          if ( !*(_BYTE *)pAce && !*((_BYTE *)pAce + 1) )
          {
            if ( EqualSid(a4, (char *)pAce + 8) )
            {
              DeleteAce(pAcl, i);
              --v6;
              --i;
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18002a898  test    rcx, rcx
0x18002a89b  jz      locret_18002A956
0x18002a8a1  mov     r11, rsp
0x18002a8a4  mov     [r11+10h], rbx
0x18002a8a8  push    rbp
0x18002a8a9  push    rsi
0x18002a8aa  push    rdi
0x18002a8ab  sub     rsp, 40h
0x18002a8af  mov     rax, cs:__security_cookie
0x18002a8b6  xor     rax, rsp
0x18002a8b9  mov     [rsp+58h+var_20], rax
0x18002a8be  xor     eax, eax
0x18002a8c0  mov     rbp, r9
0x18002a8c3  mov     [r11-30h], rax
0x18002a8c7  mov     rsi, rcx
0x18002a8ca  mov     [rsp+58h+var_28], eax
0x18002a8ce  mov     [r11-38h], rax
0x18002a8d2  test    r9, r9
0x18002a8d5  jz      short loc_18002A93D
0x18002a8d7  lea     r9d, [rax+2]; dwAclInformationClass
0x18002a8db  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18002a8df  lea     rdx, [r11-30h]; pAclInformation
0x18002a8e3  call    cs:__imp_GetAclInformation
0x18002a8e9  test    eax, eax
0x18002a8eb  jz      short loc_18002A93D
0x18002a8ed  mov     edi, dword ptr [rsp+58h+var_30]
0x18002a8f1  xor     ebx, ebx
0x18002a8f3  test    edi, edi
0x18002a8f5  jz      short loc_18002A93D
0x18002a8f7  lea     r8, [rsp+58h+pAce]; pAce
0x18002a8fc  mov     edx, ebx; dwAceIndex
0x18002a8fe  mov     rcx, rsi; pAcl
0x18002a901  call    cs:__imp_GetAce
0x18002a907  mov     rdx, [rsp+58h+pAce]
0x18002a90c  cmp     byte ptr [rdx], 0
0x18002a90f  jnz     short loc_18002A937
0x18002a911  cmp     byte ptr [rdx+1], 0
0x18002a915  jnz     short loc_18002A937
0x18002a917  add     rdx, 8; pSid2
0x18002a91b  mov     rcx, rbp; pSid1
0x18002a91e  call    cs:__imp_EqualSid
0x18002a924  test    eax, eax
0x18002a926  jz      short loc_18002A937
0x18002a928  mov     edx, ebx; dwAceIndex
0x18002a92a  mov     rcx, rsi; pAcl
0x18002a92d  call    cs:__imp_DeleteAce
0x18002a933  dec     edi
0x18002a935  dec     ebx
0x18002a937  inc     ebx
0x18002a939  cmp     ebx, edi
0x18002a93b  jb      short loc_18002A8F7
0x18002a93d  mov     rcx, [rsp+58h+var_20]
0x18002a942  xor     rcx, rsp; StackCookie
0x18002a945  call    __security_check_cookie
0x18002a94a  mov     rbx, [rsp+58h+arg_8]
0x18002a94f  add     rsp, 40h
0x18002a953  pop     rdi
0x18002a954  pop     rsi
0x18002a955  pop     rbp
0x18002a956  retn
```
