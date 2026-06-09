# InitializeSecurityStructures(void)

- ea: `0x1800990c0`
- end: `0x180099310`
- name: `?InitializeSecurityStructures@@YAHXZ`
- size: `592`
- prototype: `int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007685c`

## callees

- `0x180046650`
- `0x180098628`
- `0x1800990c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009912c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009919a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800991e7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180099226`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180099268`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800992a6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800992e1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009912c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009919a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800991e7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180099226`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180099268`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800992a6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800992e1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180099148`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180099148`

## pseudocode

```c
__int64 InitializeSecurityStructures(void)
{
  unsigned int v0; // ebx
  struct _SID_IDENTIFIER_AUTHORITY v2; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&v2.Value[4] = 1280;
  *(_DWORD *)v2.Value = 0;
  v0 = 1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &gAppContainerAllAppsSid)
    || !ConvertStringSidToSidW(
          L"S-1-15-3-1024-4044835139-2658482041-3127973164-329287231-3865880861-1938685643-461067658-1087000422",
          &gLPACCapabilitySid)
    || !AllocateAndInitializeSid(
          &v2,
          6u,
          0x63u,
          0xCE5DBACu,
          0x76F17EC4u,
          0xE5F30EDB,
          0x8F58C130,
          0x9C65577D,
          0,
          0,
          &gRestrictedSpoolerServiceSid)
    || !CreateServerSecurityDescriptor()
    || !AllocateAndInitializeSid(&v2, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pLocalSystemSid)
    || !AllocateAndInitializeSid(&v2, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &pNetworkLogonSid)
    || !AllocateAndInitializeSid(&v2, 2u, 0x20u, 0x222u, 0, 0, 0, 0, 0, 0, &pGuestsSid)
    || !AllocateAndInitializeSid(&v2, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pLocalAdminSid)
    || !AllocateAndInitializeSid(&v2, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &gpLocalService) )
  {
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x1800990c0  mov     [rsp-8+arg_0], rbx
0x1800990c5  mov     [rsp-8+arg_8], rdi
0x1800990ca  push    rbp
0x1800990cb  mov     rbp, rsp
0x1800990ce  sub     rsp, 80h
0x1800990d5  mov     rax, cs:__security_cookie
0x1800990dc  xor     rax, rsp
0x1800990df  mov     [rbp+var_10], rax
0x1800990e3  xor     edi, edi
0x1800990e5  mov     word ptr [rbp+var_20.Value+4], 500h
0x1800990eb  lea     rax, ?gAppContainerAllAppsSid@@3PEAXEA; void * gAppContainerAllAppsSid
0x1800990f2  mov     dword ptr [rbp+var_20.Value], edi
0x1800990f5  mov     [rsp+80h+pSid], rax; pSid
0x1800990fa  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800990fe  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180099102  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180099106  lea     r8d, [rdi+2]; nSubAuthority0
0x18009910a  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18009910e  lea     ebx, [rdi+1]
0x180099111  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180099115  mov     r9d, ebx; nSubAuthority1
0x180099118  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18009911c  mov     dl, r8b; nSubAuthorityCount
0x18009911f  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180099123  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180099126  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 0F00h
0x18009912c  call    cs:__imp_AllocateAndInitializeSid
0x180099132  test    eax, eax
0x180099134  jz      loc_1800992EB
0x18009913a  lea     rdx, ?gLPACCapabilitySid@@3PEAXEA; Sid
0x180099141  lea     rcx, StringSid; "S-1-15-3-1024-4044835139-2658482041-312"...
0x180099148  call    cs:__imp_ConvertStringSidToSidW
0x18009914e  test    eax, eax
0x180099150  jz      loc_1800992EB
0x180099156  lea     rax, ?gRestrictedSpoolerServiceSid@@3PEAXEA; void * gRestrictedSpoolerServiceSid
0x18009915d  mov     r9d, 0CE5DBACh; nSubAuthority1
0x180099163  mov     [rsp+80h+pSid], rax; pSid
0x180099168  lea     r8d, [rdi+63h]; nSubAuthority0
0x18009916c  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180099170  lea     rcx, [rbp+var_20]; pIdentifierAuthority
0x180099174  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180099178  mov     dl, 6; nSubAuthorityCount
0x18009917a  mov     [rsp+80h+nSubAuthority5], 9C65577Dh; nSubAuthority5
0x180099182  mov     [rsp+80h+nSubAuthority4], 8F58C130h; nSubAuthority4
0x18009918a  mov     [rsp+80h+nSubAuthority3], 0E5F30EDBh; nSubAuthority3
0x180099192  mov     [rsp+80h+nSubAuthority2], 76F17EC4h; nSubAuthority2
0x18009919a  call    cs:__imp_AllocateAndInitializeSid
0x1800991a0  test    eax, eax
0x1800991a2  jz      loc_1800992EB
0x1800991a8  call    ?CreateServerSecurityDescriptor@@YAPEAXXZ; CreateServerSecurityDescriptor(void)
0x1800991ad  test    rax, rax
0x1800991b0  jz      loc_1800992EB
0x1800991b6  lea     rax, ?pLocalSystemSid@@3PEAXEA; void * pLocalSystemSid
0x1800991bd  xor     r9d, r9d; nSubAuthority1
0x1800991c0  mov     [rsp+80h+pSid], rax; pSid
0x1800991c5  lea     r8d, [rdi+12h]; nSubAuthority0
0x1800991c9  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800991cd  lea     rcx, [rbp+var_20]; pIdentifierAuthority
0x1800991d1  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800991d5  mov     dl, bl; nSubAuthorityCount
0x1800991d7  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800991db  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800991df  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800991e3  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800991e7  call    cs:__imp_AllocateAndInitializeSid
0x1800991ed  test    eax, eax
0x1800991ef  jz      loc_1800992EB
0x1800991f5  lea     rax, ?pNetworkLogonSid@@3PEAXEA; void * pNetworkLogonSid
0x1800991fc  xor     r9d, r9d; nSubAuthority1
0x1800991ff  mov     [rsp+80h+pSid], rax; pSid
0x180099204  lea     r8d, [rdi+2]; nSubAuthority0
0x180099208  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18009920c  lea     rcx, [rbp+var_20]; pIdentifierAuthority
0x180099210  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180099214  mov     dl, bl; nSubAuthorityCount
0x180099216  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18009921a  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18009921e  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180099222  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180099226  call    cs:__imp_AllocateAndInitializeSid
0x18009922c  test    eax, eax
0x18009922e  jz      loc_1800992EB
0x180099234  lea     rax, ?pGuestsSid@@3PEAXEA; void * pGuestsSid
0x18009923b  mov     r9d, 222h; nSubAuthority1
0x180099241  mov     [rsp+80h+pSid], rax; pSid
0x180099246  lea     r8d, [rdi+20h]; nSubAuthority0
0x18009924a  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18009924e  lea     rcx, [rbp+var_20]; pIdentifierAuthority
0x180099252  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180099256  mov     dl, 2; nSubAuthorityCount
0x180099258  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18009925c  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180099260  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180099264  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180099268  call    cs:__imp_AllocateAndInitializeSid
0x18009926e  test    eax, eax
0x180099270  jz      short loc_1800992EB
0x180099272  lea     rax, ?pLocalAdminSid@@3PEAXEA; void * pLocalAdminSid
0x180099279  mov     r9d, 220h; nSubAuthority1
0x18009927f  mov     [rsp+80h+pSid], rax; pSid
0x180099284  lea     r8d, [rdi+20h]; nSubAuthority0
0x180099288  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18009928c  lea     rcx, [rbp+var_20]; pIdentifierAuthority
0x180099290  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180099294  mov     dl, 2; nSubAuthorityCount
0x180099296  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18009929a  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18009929e  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800992a2  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800992a6  call    cs:__imp_AllocateAndInitializeSid
0x1800992ac  test    eax, eax
0x1800992ae  jz      short loc_1800992EB
0x1800992b0  lea     rax, ?gpLocalService@@3PEAXEA; void * gpLocalService
0x1800992b7  xor     r9d, r9d; nSubAuthority1
0x1800992ba  mov     [rsp+80h+pSid], rax; pSid
0x1800992bf  lea     r8d, [rdi+13h]; nSubAuthority0
0x1800992c3  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800992c7  lea     rcx, [rbp+var_20]; pIdentifierAuthority
0x1800992cb  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800992cf  mov     dl, bl; nSubAuthorityCount
0x1800992d1  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800992d5  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800992d9  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800992dd  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800992e1  call    cs:__imp_AllocateAndInitializeSid
0x1800992e7  test    eax, eax
0x1800992e9  jnz     short loc_1800992ED
0x1800992eb  mov     ebx, edi
0x1800992ed  mov     eax, ebx
0x1800992ef  mov     rcx, [rbp+var_10]
0x1800992f3  xor     rcx, rsp; StackCookie
0x1800992f6  call    __security_check_cookie
0x1800992fb  lea     r11, [rsp+80h+var_s0]
0x180099303  mov     rbx, [r11+10h]
0x180099307  mov     rdi, [r11+18h]
0x18009930b  mov     rsp, r11
0x18009930e  pop     rbp
0x18009930f  retn
```
