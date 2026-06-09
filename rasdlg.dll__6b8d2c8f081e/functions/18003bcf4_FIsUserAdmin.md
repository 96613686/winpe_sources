# FIsUserAdmin

- ea: `0x18003bcf4`
- end: `0x18003bd9a`
- name: `FIsUserAdmin`
- size: `166`
- prototype: `_BOOL8()`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013b90`
- `0x18001abbc`
- `0x18002d820`
- `0x18002de30`
- `0x18002e75c`
- `0x18002f0dc`
- `0x18003bda0`

## callees

- `0x18003bcf4`
- `0x18003bdd4`
- `0x18004d110`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003bd3b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003bd3b`
- `RASAPI32!RasMobileCore` at `0x18003bd27`
- `RASAPI32!RasMobileCore` at `0x18003bd27`
- `rtutils!TracePrintfExA` at `0x18003bd5a`
- `rtutils!TracePrintfExA` at `0x18003bd5a`

## string_xrefs

- `0x18003bd50`: `CheckTokenMemberShip for local system failed.`

## pseudocode

```c
_BOOL8 FIsUserAdmin()
{
  WINBOOL v0; // eax
  WINBOOL IsMember; // [rsp+20h] [rbp-20h] BYREF
  _DWORD SidToCheck[4]; // [rsp+28h] [rbp-18h] BYREF

  IsMember = 0;
  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  if ( (unsigned int)RasMobileCore() )
    return 1;
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v0 = IsMember;
  }
  else
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "CheckTokenMemberShip for local system failed.");
    v0 = 0;
    IsMember = 0;
  }
  return v0 || (unsigned int)FIsUserGroupMember(0x220u) != 0;
}

```

## disassembly

```asm
0x18003bcf4  push    rbp
0x18003bcf6  mov     rbp, rsp
0x18003bcf9  sub     rsp, 40h
0x18003bcfd  mov     rax, cs:__security_cookie
0x18003bd04  xor     rax, rsp
0x18003bd07  mov     [rbp+var_8], rax
0x18003bd0b  mov     [rbp+IsMember], 0
0x18003bd12  mov     [rbp+SidToCheck], 101h
0x18003bd19  mov     [rbp+var_14], 5000000h
0x18003bd20  mov     [rbp+var_10], 12h
0x18003bd27  call    cs:__imp_RasMobileCore
0x18003bd2d  test    eax, eax
0x18003bd2f  jnz     short loc_18003BD83
0x18003bd31  lea     r8, [rbp+IsMember]; IsMember
0x18003bd35  xor     ecx, ecx; TokenHandle
0x18003bd37  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18003bd3b  call    cs:__imp_CheckTokenMembership
0x18003bd41  test    eax, eax
0x18003bd43  jnz     short loc_18003BD67
0x18003bd45  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003bd4b  cmp     ecx, 0FFFFFFFFh
0x18003bd4e  jz      short loc_18003BD60
0x18003bd50  lea     r8, aChecktokenmemb; "CheckTokenMemberShip for local system f"...
0x18003bd57  lea     edx, [rax+0Ch]; dwFlags
0x18003bd5a  call    cs:__imp_TracePrintfExA
0x18003bd60  xor     eax, eax
0x18003bd62  mov     [rbp+IsMember], eax
0x18003bd65  jmp     short loc_18003BD6A
0x18003bd67  mov     eax, [rbp+IsMember]
0x18003bd6a  test    eax, eax
0x18003bd6c  jnz     short loc_18003BD83
0x18003bd6e  mov     ecx, 220h; nSubAuthority1
0x18003bd73  call    FIsUserGroupMember
0x18003bd78  xor     ecx, ecx
0x18003bd7a  test    eax, eax
0x18003bd7c  setnz   cl
0x18003bd7f  mov     eax, ecx
0x18003bd81  jmp     short loc_18003BD88
0x18003bd83  mov     eax, 1
0x18003bd88  mov     rcx, [rbp+var_8]
0x18003bd8c  xor     rcx, rsp; StackCookie
0x18003bd8f  call    __security_check_cookie
0x18003bd94  add     rsp, 40h
0x18003bd98  pop     rbp
0x18003bd99  retn
```
