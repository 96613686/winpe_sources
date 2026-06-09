# IsUserMemberOfNCO(int *,int *)

- ea: `0x180046544`
- end: `0x180046641`
- name: `?IsUserMemberOfNCO@@YAJPEAH0@Z`
- size: `253`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046a74`

## callees

- `0x18001e1e0`
- `0x18003f604`
- `0x180046544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800465e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800465e5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180046618`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180046618`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800465db`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800465db`

## pseudocode

```c
__int64 __fastcall IsUserMemberOfNCO(int *a1, int *a2)
{
  signed int LastError; // eax
  signed int v5; // ebx
  PSID pSid1; // [rsp+60h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-11h] BYREF
  char v8; // [rsp+70h] [rbp-9h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = &v8;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !a1 )
    return 2147942487LL;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Cu, 0, 0, 0, 0, 0, 0, &pSid1) )
    goto LABEL_7;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
LABEL_7:
    v5 = IsUserMemberOfSID(pSid1, a1, 0);
  if ( pSid1 )
    FreeSid(pSid1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180046544  mov     [rsp-8+arg_8], rbx
0x180046549  mov     [rsp-8+arg_10], rdi
0x18004654e  push    rbp
0x18004654f  lea     rbp, [rsp-57h]
0x180046554  sub     rsp, 0D0h
0x18004655b  mov     rax, cs:__security_cookie
0x180046562  xor     rax, rsp
0x180046565  mov     [rbp+57h+var_10], rax
0x180046569  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x180046570  lea     rax, [rbp+57h+var_60]
0x180046574  mov     [rbp+57h+pSid1], rax
0x180046578  mov     rdi, rcx
0x18004657b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180046581  test    rcx, rcx
0x180046584  jnz     short loc_180046590
0x180046586  mov     eax, 80070057h
0x18004658b  jmp     loc_180046620
0x180046590  lea     rax, [rbp+57h+pSid1]
0x180046594  mov     r9d, 22Ch; nSubAuthority1
0x18004659a  mov     [rsp+0D0h+pSid], rax; pSid
0x18004659f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800465a3  mov     [rsp+0D0h+nSubAuthority7], 0; nSubAuthority7
0x1800465ab  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800465b1  mov     [rsp+0D0h+nSubAuthority6], 0; nSubAuthority6
0x1800465b9  mov     dl, 2; nSubAuthorityCount
0x1800465bb  mov     [rsp+0D0h+nSubAuthority5], 0; nSubAuthority5
0x1800465c3  mov     [rsp+0D0h+nSubAuthority4], 0; nSubAuthority4
0x1800465cb  mov     [rsp+0D0h+nSubAuthority3], 0; nSubAuthority3
0x1800465d3  mov     [rsp+0D0h+nSubAuthority2], 0; nSubAuthority2
0x1800465db  call    cs:__imp_AllocateAndInitializeSid
0x1800465e1  test    eax, eax
0x1800465e3  jnz     short loc_1800465FE
0x1800465e5  call    cs:__imp_GetLastError
0x1800465eb  mov     ebx, eax
0x1800465ed  test    eax, eax
0x1800465ef  jle     short loc_1800465FA
0x1800465f1  movzx   ebx, ax
0x1800465f4  or      ebx, 80070000h
0x1800465fa  test    ebx, ebx
0x1800465fc  js      short loc_18004660F
0x1800465fe  mov     rcx, [rbp+57h+pSid1]; pSid1
0x180046602  xor     r8d, r8d; int *
0x180046605  mov     rdx, rdi; int *
0x180046608  call    ?IsUserMemberOfSID@@YAJPEAXPEAH1@Z; IsUserMemberOfSID(void *,int *,int *)
0x18004660d  mov     ebx, eax
0x18004660f  mov     rcx, [rbp+57h+pSid1]; pSid
0x180046613  test    rcx, rcx
0x180046616  jz      short loc_18004661E
0x180046618  call    cs:__imp_FreeSid
0x18004661e  mov     eax, ebx
0x180046620  mov     rcx, [rbp+57h+var_10]
0x180046624  xor     rcx, rsp; StackCookie
0x180046627  call    __security_check_cookie
0x18004662c  lea     r11, [rsp+0D0h+var_s0]
0x180046634  mov     rbx, [r11+18h]
0x180046638  mov     rdi, [r11+20h]
0x18004663c  mov     rsp, r11
0x18004663f  pop     rbp
0x180046640  retn
```
