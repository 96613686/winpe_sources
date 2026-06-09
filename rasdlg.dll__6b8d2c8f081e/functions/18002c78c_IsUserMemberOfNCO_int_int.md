# IsUserMemberOfNCO(int *,int *)

- ea: `0x18002c78c`
- end: `0x18002c886`
- name: `?IsUserMemberOfNCO@@YAJPEAH0@Z`
- size: `250`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ca9c`

## callees

- `0x18002c78c`
- `0x18002c88c`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c82d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c82d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002c823`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002c823`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002c85d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002c85d`

## pseudocode

```c
__int64 __fastcall IsUserMemberOfNCO(int *a1, int *a2)
{
  int *v4; // r8
  signed int LastError; // eax
  signed int v6; // ebx
  PSID pSid1; // [rsp+60h] [rbp-19h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-11h] BYREF
  char v9; // [rsp+70h] [rbp-9h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = &v9;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !a1 )
    return 2147942487LL;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Cu, 0, 0, 0, 0, 0, 0, &pSid1) )
    goto LABEL_7;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
LABEL_7:
    v6 = IsUserMemberOfSID(pSid1, a1, v4);
  if ( pSid1 )
    FreeSid(pSid1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c78c  mov     [rsp-8+arg_8], rbx
0x18002c791  mov     [rsp-8+arg_10], rdi
0x18002c796  push    rbp
0x18002c797  lea     rbp, [rsp-57h]
0x18002c79c  sub     rsp, 0D0h
0x18002c7a3  mov     rax, cs:__security_cookie
0x18002c7aa  xor     rax, rsp
0x18002c7ad  mov     [rbp+57h+var_10], rax
0x18002c7b1  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x18002c7b8  lea     rax, [rbp+57h+var_60]
0x18002c7bc  mov     [rbp+57h+pSid1], rax
0x18002c7c0  mov     rdi, rcx
0x18002c7c3  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18002c7c9  test    rcx, rcx
0x18002c7cc  jnz     short loc_18002C7D8
0x18002c7ce  mov     eax, 80070057h
0x18002c7d3  jmp     loc_18002C865
0x18002c7d8  lea     rax, [rbp+57h+pSid1]
0x18002c7dc  mov     r9d, 22Ch; nSubAuthority1
0x18002c7e2  mov     [rsp+0D0h+pSid], rax; pSid
0x18002c7e7  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18002c7eb  mov     [rsp+0D0h+nSubAuthority7], 0; nSubAuthority7
0x18002c7f3  mov     r8d, 20h ; ' '; nSubAuthority0
0x18002c7f9  mov     [rsp+0D0h+nSubAuthority6], 0; nSubAuthority6
0x18002c801  mov     dl, 2; nSubAuthorityCount
0x18002c803  mov     [rsp+0D0h+nSubAuthority5], 0; nSubAuthority5
0x18002c80b  mov     [rsp+0D0h+nSubAuthority4], 0; nSubAuthority4
0x18002c813  mov     [rsp+0D0h+nSubAuthority3], 0; nSubAuthority3
0x18002c81b  mov     [rsp+0D0h+nSubAuthority2], 0; nSubAuthority2
0x18002c823  call    cs:__imp_AllocateAndInitializeSid
0x18002c829  test    eax, eax
0x18002c82b  jnz     short loc_18002C846
0x18002c82d  call    cs:__imp_GetLastError
0x18002c833  mov     ebx, eax
0x18002c835  test    eax, eax
0x18002c837  jle     short loc_18002C842
0x18002c839  movzx   ebx, ax
0x18002c83c  or      ebx, 80070000h
0x18002c842  test    ebx, ebx
0x18002c844  js      short loc_18002C854
0x18002c846  mov     rcx, [rbp+57h+pSid1]; pSid1
0x18002c84a  mov     rdx, rdi; int *
0x18002c84d  call    ?IsUserMemberOfSID@@YAJPEAXPEAH1@Z; IsUserMemberOfSID(void *,int *,int *)
0x18002c852  mov     ebx, eax
0x18002c854  mov     rcx, [rbp+57h+pSid1]; pSid
0x18002c858  test    rcx, rcx
0x18002c85b  jz      short loc_18002C863
0x18002c85d  call    cs:__imp_FreeSid
0x18002c863  mov     eax, ebx
0x18002c865  mov     rcx, [rbp+57h+var_10]
0x18002c869  xor     rcx, rsp; StackCookie
0x18002c86c  call    __security_check_cookie
0x18002c871  lea     r11, [rsp+0D0h+var_s0]
0x18002c879  mov     rbx, [r11+18h]
0x18002c87d  mov     rdi, [r11+20h]
0x18002c881  mov     rsp, r11
0x18002c884  pop     rbp
0x18002c885  retn
```
