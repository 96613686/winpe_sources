# InitializeStandardSids

- ea: `0x14000fd50`
- end: `0x14000fe86`
- name: `InitializeStandardSids`
- size: `310`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000facc`

## callees

- `0x14000fce8`
- `0x14000fd50`
- `0x140018350`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x14000fddc`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000fe17`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000fe51`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000fddc`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000fe17`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000fe51`

## pseudocode

```c
__int64 InitializeStandardSids()
{
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v2; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_DWORD *)v2.Value = 0;
  *(_WORD *)&v2.Value[4] = 256;
  if ( qword_140021BA8 && qword_140021BB0 && pSid )
    return 1;
  FreeStandardSids();
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &qword_140021BA8) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
      && AllocateAndInitializeSid(&v2, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &qword_140021BB0) )
    {
      return 1;
    }
  }
  FreeStandardSids();
  return 0;
}

```

## disassembly

```asm
0x14000fd50  mov     [rsp-8+arg_0], rbx
0x14000fd55  push    rbp
0x14000fd56  mov     rbp, rsp
0x14000fd59  sub     rsp, 80h
0x14000fd60  mov     rax, cs:__security_cookie
0x14000fd67  xor     rax, rsp
0x14000fd6a  mov     [rbp+var_10], rax
0x14000fd6e  xor     ebx, ebx
0x14000fd70  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x14000fd76  cmp     cs:qword_140021BA8, rbx
0x14000fd7d  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x14000fd80  mov     dword ptr [rbp+var_18.Value], ebx
0x14000fd83  mov     word ptr [rbp+var_18.Value+4], 100h
0x14000fd89  jz      short loc_14000FDA1
0x14000fd8b  cmp     cs:qword_140021BB0, rbx
0x14000fd92  jz      short loc_14000FDA1
0x14000fd94  cmp     cs:pSid, rbx
0x14000fd9b  jnz     loc_14000FE5B
0x14000fda1  call    FreeStandardSids
0x14000fda6  lea     rax, qword_140021BA8
0x14000fdad  mov     r9d, 220h; nSubAuthority1
0x14000fdb3  mov     [rsp+80h+pSid], rax; pSid
0x14000fdb8  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14000fdbc  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x14000fdc0  mov     r8d, 20h ; ' '; nSubAuthority0
0x14000fdc6  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x14000fdca  mov     dl, 2; nSubAuthorityCount
0x14000fdcc  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x14000fdd0  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x14000fdd4  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x14000fdd8  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x14000fddc  call    cs:__imp_AllocateAndInitializeSid
0x14000fde2  test    eax, eax
0x14000fde4  jz      short loc_14000FE62
0x14000fde6  lea     rax, pSid
0x14000fded  xor     r9d, r9d; nSubAuthority1
0x14000fdf0  mov     [rsp+80h+pSid], rax; pSid
0x14000fdf5  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x14000fdf9  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x14000fdfd  mov     dl, 1; nSubAuthorityCount
0x14000fdff  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x14000fe03  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x14000fe07  lea     r8d, [r9+12h]; nSubAuthority0
0x14000fe0b  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x14000fe0f  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x14000fe13  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x14000fe17  call    cs:__imp_AllocateAndInitializeSid
0x14000fe1d  test    eax, eax
0x14000fe1f  jz      short loc_14000FE62
0x14000fe21  lea     rax, qword_140021BB0
0x14000fe28  xor     r9d, r9d; nSubAuthority1
0x14000fe2b  mov     [rsp+80h+pSid], rax; pSid
0x14000fe30  lea     rcx, [rbp+var_18]; pIdentifierAuthority
0x14000fe34  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x14000fe38  xor     r8d, r8d; nSubAuthority0
0x14000fe3b  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x14000fe3f  mov     dl, 1; nSubAuthorityCount
0x14000fe41  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x14000fe45  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x14000fe49  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x14000fe4d  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x14000fe51  call    cs:__imp_AllocateAndInitializeSid
0x14000fe57  test    eax, eax
0x14000fe59  jz      short loc_14000FE62
0x14000fe5b  mov     eax, 1
0x14000fe60  jmp     short loc_14000FE69
0x14000fe62  call    FreeStandardSids
0x14000fe67  xor     eax, eax
0x14000fe69  mov     rcx, [rbp+var_10]
0x14000fe6d  xor     rcx, rsp; StackCookie
0x14000fe70  call    __security_check_cookie
0x14000fe75  mov     rbx, [rsp+80h+arg_0]
0x14000fe7d  add     rsp, 80h
0x14000fe84  pop     rbp
0x14000fe85  retn
```
