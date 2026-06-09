# WxGetTokenIntegrityLevel(void *,ulong *)

- ea: `0x180077824`
- end: `0x180077904`
- name: `?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z`
- size: `224`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f3c0`

## callees

- `0x180046ec0`
- `0x180047818`
- `0x180077824`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077895`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800778c5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800778c5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800778d7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800778d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007788b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007788b`

## pseudocode

```c
__int64 __fastcall WxGetTokenIntegrityLevel(HANDLE TokenHandle, unsigned int *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-98h] BYREF
  int v9; // [rsp+34h] [rbp-94h]
  PSID TokenInformation[14]; // [rsp+40h] [rbp-88h] BYREF

  v9 = 0;
  memset_0(TokenInformation, 0, 0x6Cu);
  ReturnLength = 108;
  *a2 = 4096;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x6Cu, &ReturnLength) )
  {
    v5 = 0;
    SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
    *a2 = *GetSidSubAuthority(TokenInformation[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v9 = 307;
    if ( v5 >= 0 )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180077824  mov     [rsp+arg_10], rbx
0x180077829  push    rdi
0x18007782a  sub     rsp, 0C0h
0x180077831  mov     rax, cs:__security_cookie
0x180077838  xor     rax, rsp
0x18007783b  mov     [rsp+0C8h+var_18], rax
0x180077843  mov     rdi, rdx
0x180077846  mov     [rsp+0C8h+var_94], 0
0x18007784e  xor     edx, edx; Val
0x180077850  mov     rbx, rcx
0x180077853  lea     rcx, [rsp+0C8h+TokenInformation]; void *
0x180077858  lea     r8d, [rdx+6Ch]; Size
0x18007785c  call    memset_0
0x180077861  mov     r9d, 6Ch ; 'l'; TokenInformationLength
0x180077867  mov     [rsp+0C8h+var_98], 6Ch ; 'l'
0x18007786f  lea     rax, [rsp+0C8h+var_98]
0x180077874  mov     dword ptr [rdi], 1000h
0x18007787a  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x18007787f  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180077884  mov     rcx, rbx; TokenHandle
0x180077887  lea     edx, [r9-53h]; TokenInformationClass
0x18007788b  call    cs:__imp_GetTokenInformation
0x180077891  test    eax, eax
0x180077893  jnz     short loc_1800778BE
0x180077895  call    cs:__imp_GetLastError
0x18007789b  mov     ebx, eax
0x18007789d  test    eax, eax
0x18007789f  jle     short loc_1800778AA
0x1800778a1  movzx   ebx, ax
0x1800778a4  or      ebx, 80070000h
0x1800778aa  test    ebx, ebx
0x1800778ac  mov     [rsp+0C8h+var_94], 133h
0x1800778b4  mov     eax, 8000FFFFh
0x1800778b9  cmovns  ebx, eax
0x1800778bc  jmp     short loc_1800778E1
0x1800778be  mov     rcx, [rsp+0C8h+TokenInformation]; pSid
0x1800778c3  xor     ebx, ebx
0x1800778c5  call    cs:__imp_GetSidSubAuthorityCount
0x1800778cb  mov     cl, [rax]
0x1800778cd  dec     cl
0x1800778cf  movzx   edx, cl; nSubAuthority
0x1800778d2  mov     rcx, [rsp+0C8h+TokenInformation]; pSid
0x1800778d7  call    cs:__imp_GetSidSubAuthority
0x1800778dd  mov     ecx, [rax]
0x1800778df  mov     [rdi], ecx
0x1800778e1  mov     eax, ebx
0x1800778e3  mov     rcx, [rsp+0C8h+var_18]
0x1800778eb  xor     rcx, rsp; StackCookie
0x1800778ee  call    __security_check_cookie
0x1800778f3  mov     rbx, [rsp+0C8h+arg_10]
0x1800778fb  add     rsp, 0C0h
0x180077902  pop     rdi
0x180077903  retn
```
