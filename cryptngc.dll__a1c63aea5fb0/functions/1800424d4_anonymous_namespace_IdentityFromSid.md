# _anonymous_namespace_::IdentityFromSid

- ea: `0x1800424d4`
- end: `0x18004255d`
- name: `_anonymous_namespace_::IdentityFromSid`
- size: `137`
- prototype: `__int64 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004242c`

## callees

- `0x180006538`
- `0x180028360`
- `0x1800424d4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800424e4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800424e4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180042547`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180042547`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180042522`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180042522`

## string_xrefs

- `0x1800424f3`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`
- `0x180042531`: `onecore\ds\security\ngc\utils\bio\lib\bioutils.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::IdentityFromSid(PSID pSid, _DWORD *a2)
{
  const char *v5; // r9
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( IsValidSid(pSid) )
  {
    *a2 = 3;
    if ( CopySid(0x44u, a2 + 2, pSid) )
    {
      a2[1] = GetLengthSid(pSid);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x183,
               (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\bioutils.cpp",
               v5);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\bioutils.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800424d4  mov     [rsp+arg_0], rbx
0x1800424d9  push    rdi; int
0x1800424da  sub     rsp, 20h
0x1800424de  mov     rbx, rdx
0x1800424e1  mov     rdi, rcx
0x1800424e4  call    cs:__imp_IsValidSid
0x1800424ea  test    eax, eax
0x1800424ec  jnz     short loc_180042510
0x1800424ee  mov     rcx, [rsp+28h]; this
0x1800424f3  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x1800424fa  mov     ebx, 80070057h
0x1800424ff  mov     edx, 180h; void *
0x180042504  mov     r9d, ebx; char *
0x180042507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004250c  mov     eax, ebx
0x18004250e  jmp     short loc_180042552
0x180042510  lea     rdx, [rbx+8]; pDestinationSid
0x180042514  mov     dword ptr [rbx], 3
0x18004251a  mov     r8, rdi; pSourceSid
0x18004251d  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180042522  call    cs:__imp_CopySid
0x180042528  test    eax, eax
0x18004252a  jnz     short loc_180042544
0x18004252c  mov     rcx, [rsp+28h]; this
0x180042531  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180042538  mov     edx, 183h; void *
0x18004253d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042542  jmp     short loc_180042552
0x180042544  mov     rcx, rdi; pSid
0x180042547  call    cs:__imp_GetLengthSid
0x18004254d  mov     [rbx+4], eax
0x180042550  xor     eax, eax
0x180042552  mov     rbx, [rsp+28h+arg_0]
0x180042557  add     rsp, 20h
0x18004255b  pop     rdi
0x18004255c  retn
```
