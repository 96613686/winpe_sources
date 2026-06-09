# LsaDbpIsValidDomainSid(void *)

- ea: `0x18000bdfc`
- end: `0x18000bead`
- name: `?LsaDbpIsValidDomainSid@@YAJPEAX@Z`
- size: `177`
- prototype: `__int64 __fastcall(PSID Sid1)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a2bc`
- `0x18000e9f0`

## callees

- `0x180001670`
- `0x18000bdfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be41`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18000be37`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x18000be37`
- `ntdll!RtlValidSid` at `0x18000be20`
- `ntdll!RtlValidSid` at `0x18000be20`
- `ntdll!RtlEqualSid` at `0x18000be81`
- `ntdll!RtlEqualSid` at `0x18000be81`

## pseudocode

```c
__int64 __fastcall LsaDbpIsValidDomainSid(PSID Sid1)
{
  DWORD v2; // eax
  DWORD v3; // eax
  DWORD v4; // eax
  DWORD v5; // eax
  unsigned int v6; // ebx
  DWORD cbDomainSid; // [rsp+20h] [rbp-58h] BYREF
  _BYTE pDomainSid[68]; // [rsp+24h] [rbp-54h] BYREF

  cbDomainSid = 68;
  if ( !RtlValidSid(Sid1) )
    return (unsigned int)-1073741704;
  if ( GetWindowsAccountDomainSid(Sid1, pDomainSid, &cbDomainSid) )
  {
    v6 = 0;
    if ( RtlEqualSid(Sid1, pDomainSid) )
      return v6;
    return (unsigned int)-1073741704;
  }
  v2 = GetLastError() - 87;
  if ( !v2 )
    return (unsigned int)-1073741811;
  v3 = v2 - 35;
  if ( !v3 )
    return (unsigned int)-2147483643;
  v4 = v3 - 1135;
  if ( !v4 )
    return (unsigned int)-1073741704;
  v5 = v4 - 1;
  if ( !v5 || v5 == 79 )
    return (unsigned int)-1073741704;
  return (unsigned int)-1073741595;
}

```

## disassembly

```asm
0x18000bdfc  mov     [rsp+arg_8], rbx
0x18000be01  push    rdi
0x18000be02  sub     rsp, 70h
0x18000be06  mov     rax, cs:__security_cookie
0x18000be0d  xor     rax, rsp
0x18000be10  mov     [rsp+78h+var_10], rax
0x18000be15  mov     rdi, rcx
0x18000be18  mov     [rsp+78h+cbDomainSid], 44h ; 'D'
0x18000be20  call    cs:__imp_RtlValidSid
0x18000be26  test    al, al
0x18000be28  jz      short loc_18000BE8B
0x18000be2a  lea     r8, [rsp+78h+cbDomainSid]; cbDomainSid
0x18000be2f  mov     rcx, rdi; pSid
0x18000be32  lea     rdx, [rsp+78h+pDomainSid]; pDomainSid
0x18000be37  call    cs:__imp_GetWindowsAccountDomainSid
0x18000be3d  test    eax, eax
0x18000be3f  jnz     short loc_18000BE77
0x18000be41  call    cs:__imp_GetLastError
0x18000be47  sub     eax, 57h ; 'W'
0x18000be4a  jz      short loc_18000BE70
0x18000be4c  sub     eax, 23h ; '#'
0x18000be4f  jz      short loc_18000BE69
0x18000be51  sub     eax, 46Fh
0x18000be56  jz      short loc_18000BE8B
0x18000be58  sub     eax, 1
0x18000be5b  jz      short loc_18000BE8B
0x18000be5d  cmp     eax, 4Fh ; 'O'
0x18000be60  jz      short loc_18000BE8B
0x18000be62  mov     ebx, 0C00000E5h
0x18000be67  jmp     short loc_18000BE90
0x18000be69  mov     ebx, 80000005h
0x18000be6e  jmp     short loc_18000BE90
0x18000be70  mov     ebx, 0C000000Dh
0x18000be75  jmp     short loc_18000BE90
0x18000be77  lea     rdx, [rsp+78h+pDomainSid]; Sid2
0x18000be7c  mov     rcx, rdi; Sid1
0x18000be7f  xor     ebx, ebx
0x18000be81  call    cs:__imp_RtlEqualSid
0x18000be87  test    al, al
0x18000be89  jnz     short loc_18000BE90
0x18000be8b  mov     ebx, 0C0000078h
0x18000be90  mov     eax, ebx
0x18000be92  mov     rcx, [rsp+78h+var_10]
0x18000be97  xor     rcx, rsp; StackCookie
0x18000be9a  call    __security_check_cookie
0x18000be9f  mov     rbx, [rsp+78h+arg_8]
0x18000bea7  add     rsp, 70h
0x18000beab  pop     rdi
0x18000beac  retn
```
