# AllowedAccessExists(_ACL *,ulong,void *,int *)

- ea: `0x180023614`
- end: `0x1800236f9`
- name: `?AllowedAccessExists@@YAJPEAU_ACL@@KPEAXPEAH@Z`
- size: `229`
- prototype: `__int64 __fastcall(PACL pAcl, unsigned int, void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023030`

## callees

- `0x180023614`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023663`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800236c2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800236c2`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180023653`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180023653`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180023698`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180023698`

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
0x180023614  mov     [rsp+arg_8], rbx
0x180023619  push    rbp
0x18002361a  push    rsi
0x18002361b  push    rdi
0x18002361c  sub     rsp, 40h
0x180023620  mov     rax, cs:__security_cookie
0x180023627  xor     rax, rsp
0x18002362a  mov     [rsp+58h+var_20], rax
0x18002362f  xor     eax, eax
0x180023631  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x180023636  mov     rdi, r9
0x180023639  mov     [r9], eax
0x18002363c  mov     rbp, r8
0x18002363f  mov     [rsp+58h+pAclInformation], rax
0x180023644  mov     rsi, rcx
0x180023647  mov     [rsp+58h+var_28], eax
0x18002364b  lea     r9d, [rax+2]; dwAclInformationClass
0x18002364f  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180023653  call    cs:__imp_GetAclInformation
0x18002365a  nop     dword ptr [rax+rax+00h]
0x18002365f  test    eax, eax
0x180023661  jnz     short loc_18002367D
0x180023663  call    cs:__imp_GetLastError
0x18002366a  nop     dword ptr [rax+rax+00h]
0x18002366f  test    eax, eax
0x180023671  jle     short loc_1800236DE
0x180023673  movzx   eax, ax
0x180023676  or      eax, 80070000h
0x18002367b  jmp     short loc_1800236DE
0x18002367d  xor     ebx, ebx
0x18002367f  cmp     ebx, dword ptr [rsp+58h+pAclInformation]
0x180023683  jnb     short loc_1800236DC
0x180023685  lea     r8, [rsp+58h+pAce]; pAce
0x18002368a  mov     [rsp+58h+pAce], 0
0x180023693  mov     edx, ebx; dwAceIndex
0x180023695  mov     rcx, rsi; pAcl
0x180023698  call    cs:__imp_GetAce
0x18002369f  nop     dword ptr [rax+rax+00h]
0x1800236a4  test    eax, eax
0x1800236a6  jz      short loc_180023663
0x1800236a8  mov     rdx, [rsp+58h+pAce]
0x1800236ad  cmp     byte ptr [rdx], 0
0x1800236b0  jnz     short loc_1800236D2
0x1800236b2  cmp     dword ptr [rdx+4], 0F01FFh
0x1800236b9  jnz     short loc_1800236D2
0x1800236bb  add     rdx, 8; pSid2
0x1800236bf  mov     rcx, rbp; pSid1
0x1800236c2  call    cs:__imp_EqualSid
0x1800236c9  nop     dword ptr [rax+rax+00h]
0x1800236ce  test    eax, eax
0x1800236d0  jnz     short loc_1800236D6
0x1800236d2  inc     ebx
0x1800236d4  jmp     short loc_18002367F
0x1800236d6  mov     dword ptr [rdi], 1
0x1800236dc  xor     eax, eax
0x1800236de  mov     rcx, [rsp+58h+var_20]
0x1800236e3  xor     rcx, rsp; StackCookie
0x1800236e6  call    __security_check_cookie
0x1800236eb  mov     rbx, [rsp+58h+arg_8]
0x1800236f0  add     rsp, 40h
0x1800236f4  pop     rdi
0x1800236f5  pop     rsi
0x1800236f6  pop     rbp
0x1800236f7  retn
```
