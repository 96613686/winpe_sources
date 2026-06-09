# IsUserMemberOfNCO(int *,int *)

- ea: `0x180010928`
- end: `0x180010a22`
- name: `?IsUserMemberOfNCO@@YAJPEAH0@Z`
- size: `250`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011bc0`

## callees

- `0x180010928`
- `0x180010a28`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109c9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800109f9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800109f9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800109bf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800109bf`

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
0x180010928  mov     [rsp-8+arg_8], rbx
0x18001092d  mov     [rsp-8+arg_10], rdi
0x180010932  push    rbp
0x180010933  lea     rbp, [rsp-57h]
0x180010938  sub     rsp, 0D0h
0x18001093f  mov     rax, cs:__security_cookie
0x180010946  xor     rax, rsp
0x180010949  mov     [rbp+57h+var_10], rax
0x18001094d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x180010954  lea     rax, [rbp+57h+var_60]
0x180010958  mov     [rbp+57h+pSid1], rax
0x18001095c  mov     rdi, rcx
0x18001095f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180010965  test    rcx, rcx
0x180010968  jnz     short loc_180010974
0x18001096a  mov     eax, 80070057h
0x18001096f  jmp     loc_180010A01
0x180010974  lea     rax, [rbp+57h+pSid1]
0x180010978  mov     r9d, 22Ch; nSubAuthority1
0x18001097e  mov     [rsp+0D0h+pSid], rax; pSid
0x180010983  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180010987  mov     [rsp+0D0h+nSubAuthority7], 0; nSubAuthority7
0x18001098f  mov     r8d, 20h ; ' '; nSubAuthority0
0x180010995  mov     [rsp+0D0h+nSubAuthority6], 0; nSubAuthority6
0x18001099d  mov     dl, 2; nSubAuthorityCount
0x18001099f  mov     [rsp+0D0h+nSubAuthority5], 0; nSubAuthority5
0x1800109a7  mov     [rsp+0D0h+nSubAuthority4], 0; nSubAuthority4
0x1800109af  mov     [rsp+0D0h+nSubAuthority3], 0; nSubAuthority3
0x1800109b7  mov     [rsp+0D0h+nSubAuthority2], 0; nSubAuthority2
0x1800109bf  call    cs:__imp_AllocateAndInitializeSid
0x1800109c5  test    eax, eax
0x1800109c7  jnz     short loc_1800109E2
0x1800109c9  call    cs:__imp_GetLastError
0x1800109cf  mov     ebx, eax
0x1800109d1  test    eax, eax
0x1800109d3  jle     short loc_1800109DE
0x1800109d5  movzx   ebx, ax
0x1800109d8  or      ebx, 80070000h
0x1800109de  test    ebx, ebx
0x1800109e0  js      short loc_1800109F0
0x1800109e2  mov     rcx, [rbp+57h+pSid1]; pSid1
0x1800109e6  mov     rdx, rdi; int *
0x1800109e9  call    ?IsUserMemberOfSID@@YAJPEAXPEAH1@Z; IsUserMemberOfSID(void *,int *,int *)
0x1800109ee  mov     ebx, eax
0x1800109f0  mov     rcx, [rbp+57h+pSid1]; pSid
0x1800109f4  test    rcx, rcx
0x1800109f7  jz      short loc_1800109FF
0x1800109f9  call    cs:__imp_FreeSid
0x1800109ff  mov     eax, ebx
0x180010a01  mov     rcx, [rbp+57h+var_10]
0x180010a05  xor     rcx, rsp; StackCookie
0x180010a08  call    __security_check_cookie
0x180010a0d  lea     r11, [rsp+0D0h+var_s0]
0x180010a15  mov     rbx, [r11+18h]
0x180010a19  mov     rdi, [r11+20h]
0x180010a1d  mov     rsp, r11
0x180010a20  pop     rbp
0x180010a21  retn
```
