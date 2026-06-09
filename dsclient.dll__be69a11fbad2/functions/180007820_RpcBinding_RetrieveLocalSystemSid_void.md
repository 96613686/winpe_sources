# RpcBinding::RetrieveLocalSystemSid(void * *)

- ea: `0x180007820`
- end: `0x1800078b7`
- name: `?RetrieveLocalSystemSid@RpcBinding@@AEAAJPEAPEAX@Z`
- size: `151`
- prototype: `int __fastcall(RpcBinding *this, void **pSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180004fb0`

## callees

- `0x180007820`
- `0x180009950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000788f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000788f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180007885`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180007885`

## pseudocode

```c
int __fastcall RpcBinding::RetrieveLocalSystemSid(RpcBinding *this, void **pSid)
{
  int result; // eax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, pSid) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007820  sub     rsp, 78h
0x180007824  mov     rax, cs:__security_cookie
0x18000782b  xor     rax, rsp
0x18000782e  mov     [rsp+78h+var_10], rax
0x180007833  mov     [rsp+78h+pSid], rdx; pSid
0x180007838  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x18000783d  mov     [rsp+78h+nSubAuthority7], 0; nSubAuthority7
0x180007845  xor     r9d, r9d; nSubAuthority1
0x180007848  mov     [rsp+78h+nSubAuthority6], 0; nSubAuthority6
0x180007850  mov     dl, 1; nSubAuthorityCount
0x180007852  mov     [rsp+78h+nSubAuthority5], 0; nSubAuthority5
0x18000785a  mov     [rsp+78h+nSubAuthority4], 0; nSubAuthority4
0x180007862  mov     [rsp+78h+nSubAuthority3], 0; nSubAuthority3
0x18000786a  lea     r8d, [r9+12h]; nSubAuthority0
0x18000786e  mov     [rsp+78h+nSubAuthority2], 0; nSubAuthority2
0x180007876  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], 0
0x18000787e  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 500h
0x180007885  call    cs:__imp_AllocateAndInitializeSid
0x18000788b  test    eax, eax
0x18000788d  jnz     short loc_1800078A3
0x18000788f  call    cs:__imp_GetLastError
0x180007895  test    eax, eax
0x180007897  jle     short loc_1800078A5
0x180007899  movzx   eax, ax
0x18000789c  or      eax, 80070000h
0x1800078a1  jmp     short loc_1800078A5
0x1800078a3  xor     eax, eax
0x1800078a5  mov     rcx, [rsp+78h+var_10]
0x1800078aa  xor     rcx, rsp; StackCookie
0x1800078ad  call    __security_check_cookie
0x1800078b2  add     rsp, 78h
0x1800078b6  retn
```
