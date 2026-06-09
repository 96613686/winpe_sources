# CuipIsTokenLowIL(void *,int *)

- ea: `0x140009070`
- end: `0x140009123`
- name: `?CuipIsTokenLowIL@@YAKPEAXPEAH@Z`
- size: `179`
- prototype: `DWORD __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007ce0`

## callees

- `0x140009070`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009113`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1400090c3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1400090d2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1400090c3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1400090d2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400090b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400090b4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400090e2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400090e2`

## pseudocode

```c
DWORD __fastcall CuipIsTokenLowIL(void *a1, int *a2)
{
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  *a2 = 0;
  ReturnLength[0] = 0;
  if ( !GetTokenInformation(a1, TokenIntegrityLevel, TokenInformation, 0x54u, ReturnLength) )
    return GetLastError();
  if ( !*GetSidSubAuthorityCount(TokenInformation[0])
    || (SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]),
        *GetSidSubAuthority(TokenInformation[0], (unsigned int)*SidSubAuthorityCount - 1) < 0x2000) )
  {
    *a2 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140009070  mov     [rsp+arg_10], rbx
0x140009075  push    rdi
0x140009076  sub     rsp, 0B0h
0x14000907d  mov     rax, cs:__security_cookie
0x140009084  xor     rax, rsp
0x140009087  mov     [rsp+0B8h+var_18], rax
0x14000908f  xor     ebx, ebx
0x140009091  lea     rax, [rsp+0B8h+var_88]
0x140009096  mov     [rdx], ebx
0x140009098  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x14000909d  mov     rdi, rdx
0x1400090a0  mov     [rsp+0B8h+var_88], ebx
0x1400090a4  mov     edx, 19h; TokenInformationClass
0x1400090a9  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1400090ae  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1400090b4  call    cs:__imp_GetTokenInformation
0x1400090ba  test    eax, eax
0x1400090bc  jz      short loc_140009113
0x1400090be  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x1400090c3  call    cs:__imp_GetSidSubAuthorityCount
0x1400090c9  cmp     [rax], bl
0x1400090cb  jz      short loc_14000911B
0x1400090cd  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x1400090d2  call    cs:__imp_GetSidSubAuthorityCount
0x1400090d8  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x1400090dd  movzx   edx, byte ptr [rax]
0x1400090e0  dec     edx; nSubAuthority
0x1400090e2  call    cs:__imp_GetSidSubAuthority
0x1400090e8  cmp     dword ptr [rax], 2000h
0x1400090ee  jb      short loc_14000911B
0x1400090f0  mov     eax, ebx
0x1400090f2  mov     rcx, [rsp+0B8h+var_18]
0x1400090fa  xor     rcx, rsp; StackCookie
0x1400090fd  call    __security_check_cookie
0x140009102  mov     rbx, [rsp+0B8h+arg_10]
0x14000910a  add     rsp, 0B0h
0x140009111  pop     rdi
0x140009112  retn
0x140009113  call    cs:__imp_GetLastError
0x140009119  jmp     short loc_1400090F2
0x14000911b  mov     dword ptr [rdi], 1
0x140009121  jmp     short loc_1400090F0
```
