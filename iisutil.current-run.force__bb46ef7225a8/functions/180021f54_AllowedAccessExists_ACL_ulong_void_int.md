# AllowedAccessExists(_ACL *,ulong,void *,int *)

- ea: `0x180021f54`
- end: `0x180022020`
- name: `?AllowedAccessExists@@YAJPEAU_ACL@@KPEAXPEAH@Z`
- size: `204`
- prototype: `__int64 __fastcall(PACL pAcl, unsigned int, void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021a1c`

## callees

- `0x180021f54`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f9d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180021ff0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180021ff0`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180021f93`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180021f93`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180021fcc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180021fcc`

## pseudocode

```c
signed int __fastcall AllowedAccessExists(PACL pAcl, __int64 a2, void *a3, int *a4)
{
  signed int result; // eax
  DWORD i; // ebx
  LPVOID pAce; // [rsp+20h] [rbp-38h] BYREF
  __int64 pAclInformation; // [rsp+28h] [rbp-30h] BYREF
  int v11; // [rsp+30h] [rbp-28h]

  *a4 = 0;
  pAclInformation = 0;
  v11 = 0;
  if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      pAce = 0;
      if ( !GetAce(pAcl, i, &pAce) )
        goto LABEL_2;
      if ( !*(_BYTE *)pAce && *((_DWORD *)pAce + 1) == 983551 && EqualSid(a3, (char *)pAce + 8) )
      {
        *a4 = 1;
        return 0;
      }
    }
    return 0;
  }
  else
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180021f54  mov     [rsp+arg_8], rbx
0x180021f59  push    rbp
0x180021f5a  push    rsi
0x180021f5b  push    rdi
0x180021f5c  sub     rsp, 40h
0x180021f60  mov     rax, cs:__security_cookie
0x180021f67  xor     rax, rsp
0x180021f6a  mov     [rsp+58h+var_20], rax
0x180021f6f  xor     eax, eax
0x180021f71  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x180021f76  mov     rdi, r9
0x180021f79  mov     [r9], eax
0x180021f7c  mov     rbp, r8
0x180021f7f  mov     [rsp+58h+pAclInformation], rax
0x180021f84  mov     rsi, rcx
0x180021f87  mov     [rsp+58h+var_28], eax
0x180021f8b  lea     r9d, [rax+2]; dwAclInformationClass
0x180021f8f  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180021f93  call    cs:__imp_GetAclInformation
0x180021f99  test    eax, eax
0x180021f9b  jnz     short loc_180021FB1
0x180021f9d  call    cs:__imp_GetLastError
0x180021fa3  test    eax, eax
0x180021fa5  jle     short loc_180022006
0x180021fa7  movzx   eax, ax
0x180021faa  or      eax, 80070000h
0x180021faf  jmp     short loc_180022006
0x180021fb1  xor     ebx, ebx
0x180021fb3  cmp     ebx, dword ptr [rsp+58h+pAclInformation]
0x180021fb7  jnb     short loc_180022004
0x180021fb9  lea     r8, [rsp+58h+pAce]; pAce
0x180021fbe  mov     [rsp+58h+pAce], 0
0x180021fc7  mov     edx, ebx; dwAceIndex
0x180021fc9  mov     rcx, rsi; pAcl
0x180021fcc  call    cs:__imp_GetAce
0x180021fd2  test    eax, eax
0x180021fd4  jz      short loc_180021F9D
0x180021fd6  mov     rdx, [rsp+58h+pAce]
0x180021fdb  cmp     byte ptr [rdx], 0
0x180021fde  jnz     short loc_180021FFA
0x180021fe0  cmp     dword ptr [rdx+4], 0F01FFh
0x180021fe7  jnz     short loc_180021FFA
0x180021fe9  add     rdx, 8; pSid2
0x180021fed  mov     rcx, rbp; pSid1
0x180021ff0  call    cs:__imp_EqualSid
0x180021ff6  test    eax, eax
0x180021ff8  jnz     short loc_180021FFE
0x180021ffa  inc     ebx
0x180021ffc  jmp     short loc_180021FB3
0x180021ffe  mov     dword ptr [rdi], 1
0x180022004  xor     eax, eax
0x180022006  mov     rcx, [rsp+58h+var_20]
0x18002200b  xor     rcx, rsp; StackCookie
0x18002200e  call    __security_check_cookie
0x180022013  mov     rbx, [rsp+58h+arg_8]
0x180022018  add     rsp, 40h
0x18002201c  pop     rdi
0x18002201d  pop     rsi
0x18002201e  pop     rbp
0x18002201f  retn
```
