# CreateAdminAliasSID

- ea: `0x18000abf0`
- end: `0x18000acab`
- name: `CreateAdminAliasSID`
- size: `187`
- prototype: `__int64 __fastcall(PSID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aab4`

## callees

- `0x18000abf0`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac60`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000ac56`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000ac56`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ac75`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ac75`

## pseudocode

```c
__int64 __fastcall CreateAdminAliasSID(PSID *a1)
{
  DWORD LastError; // eax
  PSID v3; // rcx
  DWORD v4; // ebx
  PSID pSid; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v7; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v7.Value[4] = 1280;
  *(_DWORD *)v7.Value = 0;
  pSid = 0;
  if ( AllocateAndInitializeSid(&v7, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v4 = 0;
    *a1 = pSid;
  }
  else
  {
    LastError = GetLastError();
    v3 = pSid;
    v4 = LastError;
    *a1 = 0;
    if ( v3 )
      FreeSid(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x18000abf0  mov     r11, rsp
0x18000abf3  mov     [r11+10h], rbx
0x18000abf7  mov     [r11+18h], rsi
0x18000abfb  push    rdi
0x18000abfc  sub     rsp, 80h
0x18000ac03  mov     rax, cs:__security_cookie
0x18000ac0a  xor     rax, rsp
0x18000ac0d  mov     [rsp+88h+var_18], rax
0x18000ac12  xor     esi, esi
0x18000ac14  mov     [rsp+88h+var_1C], 500h
0x18000ac1b  lea     rax, [r11-28h]
0x18000ac1f  mov     [rsp+88h+var_20], esi
0x18000ac23  mov     [r11-38h], rax
0x18000ac27  mov     rdi, rcx
0x18000ac2a  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x18000ac2e  lea     rcx, [r11-20h]; pIdentifierAuthority
0x18000ac32  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x18000ac36  lea     r8d, [rsi+20h]; nSubAuthority0
0x18000ac3a  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x18000ac3e  mov     r9d, 220h; nSubAuthority1
0x18000ac44  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x18000ac48  mov     dl, 2; nSubAuthorityCount
0x18000ac4a  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x18000ac4e  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x18000ac52  mov     [r11-28h], rsi
0x18000ac56  call    cs:__imp_AllocateAndInitializeSid
0x18000ac5c  test    eax, eax
0x18000ac5e  jnz     short loc_18000AC7D
0x18000ac60  call    cs:__imp_GetLastError
0x18000ac66  mov     rcx, [rsp+88h+pSid]; pSid
0x18000ac6b  mov     ebx, eax
0x18000ac6d  mov     [rdi], rsi
0x18000ac70  test    rcx, rcx
0x18000ac73  jz      short loc_18000AC87
0x18000ac75  call    cs:__imp_FreeSid
0x18000ac7b  jmp     short loc_18000AC87
0x18000ac7d  mov     rax, [rsp+88h+pSid]
0x18000ac82  mov     ebx, esi
0x18000ac84  mov     [rdi], rax
0x18000ac87  mov     eax, ebx
0x18000ac89  mov     rcx, [rsp+88h+var_18]
0x18000ac8e  xor     rcx, rsp; StackCookie
0x18000ac91  call    __security_check_cookie
0x18000ac96  lea     r11, [rsp+88h+var_8]
0x18000ac9e  mov     rbx, [r11+18h]
0x18000aca2  mov     rsi, [r11+20h]
0x18000aca6  mov     rsp, r11
0x18000aca9  pop     rdi
0x18000acaa  retn
```
