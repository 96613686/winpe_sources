# IsUserSystemAccount(void)

- ea: `0x1800ac858`
- end: `0x1800ac930`
- name: `?IsUserSystemAccount@@YA_NXZ`
- size: `216`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cb564`

## callees

- `0x1800ac858`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ac89e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ac8cf`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ac900`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ac89e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ac8cf`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ac900`

## pseudocode

```c
char IsUserSystemAccount(void)
{
  char v0; // bl
  int SidToCheck; // [rsp+20h] [rbp-20h] BYREF
  int v3; // [rsp+24h] [rbp-1Ch]
  int v4; // [rsp+28h] [rbp-18h]
  WINBOOL IsMember; // [rsp+30h] [rbp-10h] BYREF

  SidToCheck = 257;
  IsMember = 0;
  v3 = 83886080;
  v4 = 20;
  v0 = 1;
  if ( !CheckTokenMembership(0, &SidToCheck, &IsMember) || !IsMember )
  {
    SidToCheck = 257;
    v3 = 83886080;
    v4 = 18;
    IsMember = 0;
    if ( !CheckTokenMembership(0, &SidToCheck, &IsMember) || !IsMember )
    {
      SidToCheck = 257;
      v3 = 83886080;
      v4 = 19;
      IsMember = 0;
      if ( !CheckTokenMembership(0, &SidToCheck, &IsMember) || !IsMember )
        return 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800ac858  mov     [rsp-8+arg_0], rbx
0x1800ac85d  mov     [rsp-8+arg_8], rdi
0x1800ac862  push    rbp
0x1800ac863  mov     rbp, rsp
0x1800ac866  sub     rsp, 40h
0x1800ac86a  mov     rax, cs:__security_cookie
0x1800ac871  xor     rax, rsp
0x1800ac874  mov     [rbp+var_8], rax
0x1800ac878  xor     edi, edi
0x1800ac87a  mov     [rbp+SidToCheck], 101h
0x1800ac881  lea     r8, [rbp+IsMember]; IsMember
0x1800ac885  mov     [rbp+IsMember], edi
0x1800ac888  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x1800ac88c  mov     [rbp+var_1C], 5000000h
0x1800ac893  xor     ecx, ecx; TokenHandle
0x1800ac895  mov     [rbp+var_18], 14h
0x1800ac89c  mov     bl, 1
0x1800ac89e  call    cs:__imp_CheckTokenMembership
0x1800ac8a4  test    eax, eax
0x1800ac8a6  jz      short loc_1800AC8AD
0x1800ac8a8  cmp     [rbp+IsMember], edi
0x1800ac8ab  jnz     short loc_1800AC912
0x1800ac8ad  lea     r8, [rbp+IsMember]; IsMember
0x1800ac8b1  mov     [rbp+SidToCheck], 101h
0x1800ac8b8  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x1800ac8bc  mov     [rbp+var_1C], 5000000h
0x1800ac8c3  xor     ecx, ecx; TokenHandle
0x1800ac8c5  mov     [rbp+var_18], 12h
0x1800ac8cc  mov     [rbp+IsMember], edi
0x1800ac8cf  call    cs:__imp_CheckTokenMembership
0x1800ac8d5  test    eax, eax
0x1800ac8d7  jz      short loc_1800AC8DE
0x1800ac8d9  cmp     [rbp+IsMember], edi
0x1800ac8dc  jnz     short loc_1800AC912
0x1800ac8de  lea     r8, [rbp+IsMember]; IsMember
0x1800ac8e2  mov     [rbp+SidToCheck], 101h
0x1800ac8e9  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x1800ac8ed  mov     [rbp+var_1C], 5000000h
0x1800ac8f4  xor     ecx, ecx; TokenHandle
0x1800ac8f6  mov     [rbp+var_18], 13h
0x1800ac8fd  mov     [rbp+IsMember], edi
0x1800ac900  call    cs:__imp_CheckTokenMembership
0x1800ac906  test    eax, eax
0x1800ac908  jz      short loc_1800AC90F
0x1800ac90a  cmp     [rbp+IsMember], edi
0x1800ac90d  jnz     short loc_1800AC912
0x1800ac90f  mov     bl, dil
0x1800ac912  mov     al, bl
0x1800ac914  mov     rcx, [rbp+var_8]
0x1800ac918  xor     rcx, rsp; StackCookie
0x1800ac91b  call    __security_check_cookie
0x1800ac920  mov     rbx, [rsp+40h+arg_0]
0x1800ac925  mov     rdi, [rsp+40h+arg_8]
0x1800ac92a  add     rsp, 40h
0x1800ac92e  pop     rbp
0x1800ac92f  retn
```
