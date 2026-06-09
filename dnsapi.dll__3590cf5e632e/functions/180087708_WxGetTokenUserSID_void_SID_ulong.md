# WxGetTokenUserSID(void *,_SID *,ulong)

- ea: `0x180087708`
- end: `0x180087840`
- name: `?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z`
- size: `312`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pDestinationSid, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c9f20`

## callees

- `0x180087708`
- `0x18008b5f0`
- `0x18008bf98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800877a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800877f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800877a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800877f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180087797`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180087797`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800877e0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800877e0`

## pseudocode

```c
signed int __fastcall WxGetTokenUserSID(HANDLE TokenHandle, PSID pDestinationSid)
{
  signed int result; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  int v6; // [rsp+34h] [rbp-84h]
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  v6 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  if ( TokenHandle )
  {
    if ( pDestinationSid )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
      {
        if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
        {
          return 0;
        }
        else
        {
          result = GetLastError();
          if ( result > 0 )
            result = (unsigned __int16)result | 0x80070000;
          v6 = 32;
          if ( result >= 0 )
            return -2147418113;
        }
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        v6 = 31;
        if ( result >= 0 )
          return -2147418113;
      }
    }
    else
    {
      result = -2147024809;
      v6 = 28;
    }
  }
  else
  {
    result = -2147024809;
    v6 = 27;
  }
  return result;
}

```

## disassembly

```asm
0x180087708  mov     [rsp+arg_10], rbx
0x18008770d  push    rdi
0x18008770e  sub     rsp, 0B0h
0x180087715  mov     rax, cs:__security_cookie
0x18008771c  xor     rax, rsp
0x18008771f  mov     [rsp+0B8h+var_18], rax
0x180087727  mov     rbx, rdx
0x18008772a  mov     [rsp+0B8h+var_84], 0
0x180087732  xor     edx, edx; Val
0x180087734  mov     rdi, rcx
0x180087737  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x18008773c  lea     r8d, [rdx+58h]; Size
0x180087740  call    memset_0
0x180087745  mov     [rsp+0B8h+var_88], 0
0x18008774d  test    rdi, rdi
0x180087750  jnz     short loc_180087764
0x180087752  mov     eax, 80070057h
0x180087757  mov     [rsp+0B8h+var_84], 1Bh
0x18008775f  jmp     loc_18008781E
0x180087764  test    rbx, rbx
0x180087767  jnz     short loc_18008777B
0x180087769  mov     eax, 80070057h
0x18008776e  mov     [rsp+0B8h+var_84], 1Ch
0x180087776  jmp     loc_18008781E
0x18008777b  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180087781  lea     rax, [rsp+0B8h+var_88]
0x180087786  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18008778b  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180087790  mov     rcx, rdi; TokenHandle
0x180087793  lea     edx, [r9-57h]; TokenInformationClass
0x180087797  call    cs:__imp_GetTokenInformation
0x18008779e  nop     dword ptr [rax+rax+00h]
0x1800877a3  test    eax, eax
0x1800877a5  jnz     short loc_1800877D3
0x1800877a7  call    cs:__imp_GetLastError
0x1800877ae  nop     dword ptr [rax+rax+00h]
0x1800877b3  test    eax, eax
0x1800877b5  jle     short loc_1800877BF
0x1800877b7  movzx   eax, ax
0x1800877ba  or      eax, 80070000h
0x1800877bf  test    eax, eax
0x1800877c1  mov     [rsp+0B8h+var_84], 1Fh
0x1800877c9  mov     ecx, 8000FFFFh
0x1800877ce  cmovns  eax, ecx
0x1800877d1  jmp     short loc_18008781E
0x1800877d3  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x1800877d8  mov     rdx, rbx; pDestinationSid
0x1800877db  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800877e0  call    cs:__imp_CopySid
0x1800877e7  nop     dword ptr [rax+rax+00h]
0x1800877ec  test    eax, eax
0x1800877ee  jnz     short loc_18008781C
0x1800877f0  call    cs:__imp_GetLastError
0x1800877f7  nop     dword ptr [rax+rax+00h]
0x1800877fc  test    eax, eax
0x1800877fe  jle     short loc_180087808
0x180087800  movzx   eax, ax
0x180087803  or      eax, 80070000h
0x180087808  test    eax, eax
0x18008780a  mov     [rsp+0B8h+var_84], 20h ; ' '
0x180087812  mov     ecx, 8000FFFFh
0x180087817  cmovns  eax, ecx
0x18008781a  jmp     short loc_18008781E
0x18008781c  xor     eax, eax
0x18008781e  mov     rcx, [rsp+0B8h+var_18]
0x180087826  xor     rcx, rsp; StackCookie
0x180087829  call    __security_check_cookie
0x18008782e  mov     rbx, [rsp+0B8h+arg_10]
0x180087836  add     rsp, 0B0h
0x18008783d  pop     rdi
0x18008783e  retn
```
