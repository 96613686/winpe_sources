# GetTokenPackageSID(void *,ulong,void *)

- ea: `0x1800542c0`
- end: `0x180054363`
- name: `?GetTokenPackageSID@@YAJPEAXK0@Z`
- size: `163`
- prototype: `int(void *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800530e0`

## callees

- `0x1800542c0`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054330`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180054303`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180054303`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180054322`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180054322`

## pseudocode

```c
int __fastcall GetTokenPackageSID(void *a1, DWORD a2, void *a3)
{
  int result; // eax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-138h] BYREF
  PSID TokenInformation[34]; // [rsp+40h] [rbp-128h] BYREF

  ReturnLength[0] = 264;
  if ( !GetTokenInformation(a1, TokenAppContainerSid, TokenInformation, 0x108u, ReturnLength) )
    goto LABEL_6;
  if ( !TokenInformation[0] )
    return 1;
  if ( CopySid(a2, a3, TokenInformation[0]) )
    return 0;
LABEL_6:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800542c0  mov     [rsp+arg_18], rbx
0x1800542c5  push    rdi
0x1800542c6  sub     rsp, 160h
0x1800542cd  mov     rax, cs:__security_cookie
0x1800542d4  xor     rax, rsp
0x1800542d7  mov     [rsp+168h+var_18], rax
0x1800542df  mov     rdi, r8
0x1800542e2  lea     rax, [rsp+168h+var_138]
0x1800542e7  mov     ebx, edx
0x1800542e9  mov     [rsp+168h+ReturnLength], rax; ReturnLength
0x1800542ee  mov     r9d, 108h; TokenInformationLength
0x1800542f4  lea     r8, [rsp+168h+TokenInformation]; TokenInformation
0x1800542f9  mov     edx, 1Fh; TokenInformationClass
0x1800542fe  mov     [rsp+168h+var_138], r9d
0x180054303  call    cs:__imp_GetTokenInformation
0x180054309  test    eax, eax
0x18005430b  jz      short loc_180054330
0x18005430d  mov     r8, [rsp+168h+TokenInformation]; pSourceSid
0x180054312  test    r8, r8
0x180054315  jnz     short loc_18005431D
0x180054317  lea     eax, [r8+1]
0x18005431b  jmp     short loc_180054342
0x18005431d  mov     rdx, rdi; pDestinationSid
0x180054320  mov     ecx, ebx; nDestinationSidLength
0x180054322  call    cs:__imp_CopySid
0x180054328  test    eax, eax
0x18005432a  jz      short loc_180054330
0x18005432c  xor     eax, eax
0x18005432e  jmp     short loc_180054342
0x180054330  call    cs:__imp_GetLastError
0x180054336  test    eax, eax
0x180054338  jle     short loc_180054342
0x18005433a  movzx   eax, ax
0x18005433d  or      eax, 80070000h
0x180054342  mov     rcx, [rsp+168h+var_18]
0x18005434a  xor     rcx, rsp; StackCookie
0x18005434d  call    __security_check_cookie
0x180054352  mov     rbx, [rsp+168h+arg_18]
0x18005435a  add     rsp, 160h
0x180054361  pop     rdi
0x180054362  retn
```
