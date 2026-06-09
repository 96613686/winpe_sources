# IsAdminWithHighIL(void)

- ea: `0x140003af8`
- end: `0x140003bef`
- name: `?IsAdminWithHighIL@@YAHXZ`
- size: `247`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004108`
- `0x14000ba88`

## callees

- `0x140003af8`
- `0x1400109c0`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x140003b7a`
- `ADVAPI32!CheckTokenMembership` at `0x140003b7a`
- `ADVAPI32!FreeSid` at `0x140003bbf`
- `ADVAPI32!FreeSid` at `0x140003bbf`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140003b60`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140003b60`
- `iertutil!__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z` at `0x140003b9c`
- `iertutil!__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z` at `0x140003b9c`

## pseudocode

```c
__int64 IsAdminWithHighIL(void)
{
  unsigned int v0; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v3; // [rsp+64h] [rbp-1Ch] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  v0 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      if ( IsMember )
      {
        v3 = 4096;
        if ( !GetProcessIntegrityLevel(0, &v3) )
          LOBYTE(v0) = v3 >= 0x3000;
      }
    }
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v0;
}

```

## disassembly

```asm
0x140003af8  mov     [rsp-8+arg_0], rbx
0x140003afd  mov     [rsp-8+arg_8], rdi
0x140003b02  push    rbp
0x140003b03  mov     rbp, rsp
0x140003b06  sub     rsp, 80h
0x140003b0d  mov     rax, cs:__security_cookie
0x140003b14  xor     rax, rsp
0x140003b17  mov     [rbp+var_8], rax
0x140003b1b  xor     edi, edi
0x140003b1d  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x140003b23  lea     rax, [rbp+SidToCheck]
0x140003b27  mov     [rbp+IsMember], edi
0x140003b2a  mov     [rsp+80h+pSid], rax; pSid
0x140003b2f  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x140003b33  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x140003b37  mov     r9d, 220h; nSubAuthority1
0x140003b3d  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x140003b41  lea     r8d, [rdi+20h]; nSubAuthority0
0x140003b45  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x140003b49  mov     dl, 2; nSubAuthorityCount
0x140003b4b  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x140003b4f  mov     ebx, edi
0x140003b51  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x140003b55  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x140003b59  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x140003b5c  mov     [rbp+SidToCheck], rdi
0x140003b60  call    cs:__imp_AllocateAndInitializeSid
0x140003b67  nop     dword ptr [rax+rax+00h]
0x140003b6c  test    eax, eax
0x140003b6e  jz      short loc_140003BB6
0x140003b70  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x140003b74  lea     r8, [rbp+IsMember]; IsMember
0x140003b78  xor     ecx, ecx; TokenHandle
0x140003b7a  call    cs:__imp_CheckTokenMembership
0x140003b81  nop     dword ptr [rax+rax+00h]
0x140003b86  test    eax, eax
0x140003b88  jz      short loc_140003BB6
0x140003b8a  cmp     [rbp+IsMember], edi
0x140003b8d  jz      short loc_140003BB6
0x140003b8f  lea     rdx, [rbp+var_1C]
0x140003b93  mov     [rbp+var_1C], 1000h
0x140003b9a  xor     ecx, ecx
0x140003b9c  call    cs:__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z; GetProcessIntegrityLevel(void *,ulong *)
0x140003ba3  nop     dword ptr [rax+rax+00h]
0x140003ba8  test    eax, eax
0x140003baa  jnz     short loc_140003BB6
0x140003bac  cmp     [rbp+var_1C], 3000h
0x140003bb3  setnb   bl
0x140003bb6  mov     rcx, [rbp+SidToCheck]; pSid
0x140003bba  test    rcx, rcx
0x140003bbd  jz      short loc_140003BCB
0x140003bbf  call    cs:__imp_FreeSid
0x140003bc6  nop     dword ptr [rax+rax+00h]
0x140003bcb  mov     eax, ebx
0x140003bcd  mov     rcx, [rbp+var_8]
0x140003bd1  xor     rcx, rsp; StackCookie
0x140003bd4  call    __security_check_cookie
0x140003bd9  lea     r11, [rsp+80h+var_s0]
0x140003be1  mov     rbx, [r11+10h]
0x140003be5  mov     rdi, [r11+18h]
0x140003be9  mov     rsp, r11
0x140003bec  pop     rbp
0x140003bed  retn
```
