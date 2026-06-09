# Mso::Security::HrGetTokenIL(void *,ulong *)

- ea: `0x1801224d8`
- end: `0x18012257d`
- name: `?HrGetTokenIL@Security@Mso@@YAJPEAXPEAK@Z`
- size: `165`
- prototype: `__int64 __fastcall(Mso::Security *__hidden this, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801223c0`
- `0x180122448`

## callees

- `0x18003e690`
- `0x1801224d8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180122532`
- `KERNEL32!GetLastError` at `0x180122532`
- `ADVAPI32!GetTokenInformation` at `0x180122528`
- `ADVAPI32!GetTokenInformation` at `0x180122528`
- `ADVAPI32!GetSidSubAuthority` at `0x18012254f`
- `ADVAPI32!GetSidSubAuthority` at `0x18012254f`

## pseudocode

```c
signed int __fastcall Mso::Security::HrGetTokenIL(Mso::Security *this, DWORD *a2, unsigned int *a3)
{
  signed int result; // eax
  bool v5; // zf
  PDWORD SidSubAuthority; // rcx
  DWORD ReturnLength; // [rsp+30h] [rbp-38h] BYREF
  PSID TokenInformation[4]; // [rsp+38h] [rbp-30h] BYREF

  ReturnLength = 0;
  if ( !a2 )
    return -2147467261;
  *a2 = 0x2000;
  if ( !this )
    return -2147467261;
  if ( GetTokenInformation(this, TokenIntegrityLevel, TokenInformation, 0x1Cu, &ReturnLength) )
    goto LABEL_8;
  result = GetLastError();
  v5 = result == 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result == 0;
  }
  if ( v5 )
  {
LABEL_8:
    SidSubAuthority = GetSidSubAuthority(TokenInformation[0], 0);
    if ( SidSubAuthority )
    {
      result = 0;
      *a2 = *SidSubAuthority;
    }
    else
    {
      return -2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801224d8  push    rbx
0x1801224da  sub     rsp, 60h
0x1801224de  mov     rax, cs:__security_cookie
0x1801224e5  xor     rax, rsp
0x1801224e8  mov     [rsp+68h+var_10], rax
0x1801224ed  mov     rbx, rdx
0x1801224f0  mov     [rsp+68h+var_38], 0
0x1801224f8  test    rdx, rdx
0x1801224fb  jnz     short loc_180122504
0x1801224fd  mov     eax, 80004003h
0x180122502  jmp     short loc_18012256A
0x180122504  mov     dword ptr [rdx], 2000h
0x18012250a  test    rcx, rcx
0x18012250d  jz      short loc_1801224FD
0x18012250f  lea     rax, [rsp+68h+var_38]
0x180122514  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180122519  mov     r9d, 1Ch; TokenInformationLength
0x18012251f  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x180122524  lea     edx, [r9-3]; TokenInformationClass
0x180122528  call    cs:__imp_GetTokenInformation
0x18012252e  test    eax, eax
0x180122530  jnz     short loc_180122548
0x180122532  call    cs:__imp_GetLastError
0x180122538  test    eax, eax
0x18012253a  jle     short loc_180122546
0x18012253c  movzx   eax, ax
0x18012253f  or      eax, 80070000h
0x180122544  test    eax, eax
0x180122546  jnz     short loc_18012256A
0x180122548  xor     edx, edx; nSubAuthority
0x18012254a  mov     rcx, [rsp+68h+TokenInformation]; pSid
0x18012254f  call    cs:__imp_GetSidSubAuthority
0x180122555  mov     rcx, rax
0x180122558  test    rax, rax
0x18012255b  jnz     short loc_180122564
0x18012255d  mov     eax, 80004005h
0x180122562  jmp     short loc_18012256A
0x180122564  xor     eax, eax
0x180122566  mov     ecx, [rcx]
0x180122568  mov     [rbx], ecx
0x18012256a  mov     rcx, [rsp+68h+var_10]
0x18012256f  xor     rcx, rsp; StackCookie
0x180122572  call    __security_check_cookie
0x180122577  add     rsp, 60h
0x18012257b  pop     rbx
0x18012257c  retn
```
