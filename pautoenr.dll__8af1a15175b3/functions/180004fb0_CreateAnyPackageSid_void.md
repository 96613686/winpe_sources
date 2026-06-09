# _CreateAnyPackageSid(void)

- ea: `0x180004fb0`
- end: `0x180005038`
- name: `?_CreateAnyPackageSid@@YAPEAXXZ`
- size: `136`
- prototype: `PSID(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001100`

## callees

- `0x180004fb0`
- `0x180007d20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180005011`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180005011`

## pseudocode

```c
PSID _CreateAnyPackageSid(void)
{
  bool v0; // zf
  PSID result; // rax
  PSID pSid; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v0 = !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &pSid);
  result = 0;
  if ( !v0 )
    return pSid;
  return result;
}

```

## disassembly

```asm
0x180004fb0  push    rbx
0x180004fb2  sub     rsp, 80h
0x180004fb9  mov     rax, cs:__security_cookie
0x180004fc0  xor     rax, rsp
0x180004fc3  mov     [rsp+88h+var_18], rax
0x180004fc8  xor     ebx, ebx
0x180004fca  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 0F00h
0x180004fd1  lea     rax, [rsp+88h+var_28]
0x180004fd6  mov     [rsp+88h+var_28], rbx
0x180004fdb  mov     [rsp+88h+pSid], rax; pSid
0x180004fe0  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x180004fe5  mov     [rsp+88h+nSubAuthority7], ebx; nSubAuthority7
0x180004fe9  mov     r8d, 2; nSubAuthority0
0x180004fef  mov     [rsp+88h+nSubAuthority6], ebx; nSubAuthority6
0x180004ff3  mov     r9d, 1; nSubAuthority1
0x180004ff9  mov     [rsp+88h+nSubAuthority5], ebx; nSubAuthority5
0x180004ffd  movzx   edx, r8b; nSubAuthorityCount
0x180005001  mov     [rsp+88h+nSubAuthority4], ebx; nSubAuthority4
0x180005005  mov     [rsp+88h+nSubAuthority3], ebx; nSubAuthority3
0x180005009  mov     [rsp+88h+nSubAuthority2], ebx; nSubAuthority2
0x18000500d  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], ebx
0x180005011  call    cs:__imp_AllocateAndInitializeSid
0x180005017  test    eax, eax
0x180005019  mov     eax, ebx
0x18000501b  jz      short loc_180005022
0x18000501d  mov     rax, [rsp+88h+var_28]
0x180005022  mov     rcx, [rsp+88h+var_18]
0x180005027  xor     rcx, rsp; StackCookie
0x18000502a  call    __security_check_cookie
0x18000502f  add     rsp, 80h
0x180005036  pop     rbx
0x180005037  retn
```
