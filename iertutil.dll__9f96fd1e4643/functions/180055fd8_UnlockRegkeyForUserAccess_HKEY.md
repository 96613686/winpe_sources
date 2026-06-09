# UnlockRegkeyForUserAccess(HKEY__ *)

- ea: `0x180055fd8`
- end: `0x180056131`
- name: `?UnlockRegkeyForUserAccess@@YAXPEAUHKEY__@@@Z`
- size: `345`
- prototype: `void __fastcall(HKEY handle)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180055e70`
- `0x180055f10`

## callees

- `0x180055fd8`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005610a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005610a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18005609a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18005609a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180056069`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180056069`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x1800560b9`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x1800560b9`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180056039`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180056039`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800560fb`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800560fb`

## pseudocode

```c
void __fastcall UnlockRegkeyForUserAccess(HKEY handle)
{
  char v2; // di
  signed int v3; // ebx
  PACL pAcl; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-20h] BYREF
  __int64 pAclInformation; // [rsp+58h] [rbp-18h] BYREF
  int v8; // [rsp+60h] [rbp-10h]

  hMem = 0;
  pAcl = 0;
  if ( !GetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, &pAcl, 0, &hMem) )
  {
    if ( pAcl )
    {
      pAclInformation = 0;
      v8 = 0;
      if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v2 = 0;
        v3 = pAclInformation - 1;
        if ( (int)pAclInformation - 1 >= 0 )
        {
          do
          {
            pAce = 0;
            if ( GetAce(pAcl, v3, &pAce) && *(_BYTE *)pAce == 1 && *((_DWORD *)pAce + 1) == 2 && DeleteAce(pAcl, v3) )
              v2 = 1;
            --v3;
          }
          while ( v3 >= 0 );
          if ( v2 )
            SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, pAcl, 0);
        }
      }
    }
  }
  if ( hMem )
    LocalFree(hMem);
}

```

## disassembly

```asm
0x180055fd8  mov     r11, rsp
0x180055fdb  mov     [r11+10h], rbx
0x180055fdf  mov     [r11+18h], rsi
0x180055fe3  push    rbp
0x180055fe4  push    rdi
0x180055fe5  push    r15
0x180055fe7  mov     rbp, rsp
0x180055fea  sub     rsp, 70h
0x180055fee  mov     rax, cs:__security_cookie
0x180055ff5  xor     rax, rsp
0x180055ff8  mov     [rbp+var_8], rax
0x180055ffc  xor     r9d, r9d; ppsidOwner
0x180055fff  mov     [rbp+hMem], 0
0x180056007  lea     rax, [rbp+hMem]
0x18005600b  mov     [rbp+pAcl], 0
0x180056013  mov     [r11-50h], rax
0x180056017  mov     rsi, rcx
0x18005601a  mov     qword ptr [r11-58h], 0
0x180056022  lea     rax, [rbp+pAcl]
0x180056026  lea     edx, [r9+4]; ObjectType
0x18005602a  mov     [r11-60h], rax
0x18005602e  mov     r8d, edx; SecurityInfo
0x180056031  mov     qword ptr [r11-68h], 0
0x180056039  call    cs:__imp_GetSecurityInfo
0x18005603f  test    eax, eax
0x180056041  jnz     loc_180056101
0x180056047  mov     rcx, [rbp+pAcl]; pAcl
0x18005604b  test    rcx, rcx
0x18005604e  jz      loc_180056101
0x180056054  xor     eax, eax
0x180056056  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18005605a  mov     [rbp+pAclInformation], rax
0x18005605e  mov     [rbp+var_10], eax
0x180056061  lea     r9d, [rax+2]; dwAclInformationClass
0x180056065  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180056069  call    cs:__imp_GetAclInformation
0x18005606f  test    eax, eax
0x180056071  jz      loc_180056101
0x180056077  mov     ebx, dword ptr [rbp+pAclInformation]
0x18005607a  xor     dil, dil
0x18005607d  sub     ebx, 1
0x180056080  js      short loc_180056101
0x180056082  mov     r15d, 1
0x180056088  mov     rcx, [rbp+pAcl]; pAcl
0x18005608c  lea     r8, [rbp+pAce]; pAce
0x180056090  mov     edx, ebx; dwAceIndex
0x180056092  mov     [rbp+pAce], 0
0x18005609a  call    cs:__imp_GetAce
0x1800560a0  test    eax, eax
0x1800560a2  jz      short loc_1800560C9
0x1800560a4  mov     rax, [rbp+pAce]
0x1800560a8  cmp     [rax], r15b
0x1800560ab  jnz     short loc_1800560C9
0x1800560ad  cmp     dword ptr [rax+4], 2
0x1800560b1  jnz     short loc_1800560C9
0x1800560b3  mov     rcx, [rbp+pAcl]; pAcl
0x1800560b7  mov     edx, ebx; dwAceIndex
0x1800560b9  call    cs:__imp_DeleteAce
0x1800560bf  test    eax, eax
0x1800560c1  movzx   edi, dil
0x1800560c5  cmovnz  edi, r15d
0x1800560c9  sub     ebx, r15d
0x1800560cc  jns     short loc_180056088
0x1800560ce  test    dil, dil
0x1800560d1  jz      short loc_180056101
0x1800560d3  mov     rax, [rbp+pAcl]
0x1800560d7  xor     r9d, r9d; psidOwner
0x1800560da  mov     [rsp+70h+pSacl], 0; pSacl
0x1800560e3  mov     rcx, rsi; handle
0x1800560e6  mov     [rsp+70h+pDacl], rax; pDacl
0x1800560eb  mov     [rsp+70h+psidGroup], 0; psidGroup
0x1800560f4  lea     edx, [r9+4]; ObjectType
0x1800560f8  mov     r8d, edx; SecurityInfo
0x1800560fb  call    cs:__imp_SetSecurityInfo
0x180056101  mov     rcx, [rbp+hMem]; hMem
0x180056105  test    rcx, rcx
0x180056108  jz      short loc_180056110
0x18005610a  call    cs:__imp_LocalFree
0x180056110  mov     rcx, [rbp+var_8]
0x180056114  xor     rcx, rsp; StackCookie
0x180056117  call    __security_check_cookie
0x18005611c  lea     r11, [rsp+70h+var_s0]
0x180056121  mov     rbx, [r11+28h]
0x180056125  mov     rsi, [r11+30h]
0x180056129  mov     rsp, r11
0x18005612c  pop     r15
0x18005612e  pop     rdi
0x18005612f  pop     rbp
0x180056130  retn
```
