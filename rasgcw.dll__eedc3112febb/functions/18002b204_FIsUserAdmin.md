# FIsUserAdmin

- ea: `0x18002b204`
- end: `0x18002b2aa`
- name: `FIsUserAdmin`
- size: `166`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011bc0`
- `0x1800202e0`
- `0x180020c48`

## callees

- `0x18002b204`
- `0x18002b2b0`
- `0x18002f3b0`

## import_xrefs

- `RASAPI32!RasMobileCore` at `0x18002b237`
- `RASAPI32!RasMobileCore` at `0x18002b237`
- `rtutils!TracePrintfExA` at `0x18002b26a`
- `rtutils!TracePrintfExA` at `0x18002b26a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002b24b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002b24b`

## string_xrefs

- `0x18002b260`: `CheckTokenMemberShip for local system failed.`

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
0x18002b204  push    rbp
0x18002b206  mov     rbp, rsp
0x18002b209  sub     rsp, 40h
0x18002b20d  mov     rax, cs:__security_cookie
0x18002b214  xor     rax, rsp
0x18002b217  mov     [rbp+var_8], rax
0x18002b21b  mov     [rbp+IsMember], 0
0x18002b222  mov     [rbp+SidToCheck], 101h
0x18002b229  mov     [rbp+var_14], 5000000h
0x18002b230  mov     [rbp+var_10], 12h
0x18002b237  call    cs:__imp_RasMobileCore
0x18002b23d  test    eax, eax
0x18002b23f  jnz     short loc_18002B293
0x18002b241  lea     r8, [rbp+IsMember]; IsMember
0x18002b245  xor     ecx, ecx; TokenHandle
0x18002b247  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18002b24b  call    cs:__imp_CheckTokenMembership
0x18002b251  test    eax, eax
0x18002b253  jnz     short loc_18002B277
0x18002b255  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002b25b  cmp     ecx, 0FFFFFFFFh
0x18002b25e  jz      short loc_18002B270
0x18002b260  lea     r8, aChecktokenmemb_0; "CheckTokenMemberShip for local system f"...
0x18002b267  lea     edx, [rax+0Ch]; dwFlags
0x18002b26a  call    cs:__imp_TracePrintfExA
0x18002b270  xor     eax, eax
0x18002b272  mov     [rbp+IsMember], eax
0x18002b275  jmp     short loc_18002B27A
0x18002b277  mov     eax, [rbp+IsMember]
0x18002b27a  test    eax, eax
0x18002b27c  jnz     short loc_18002B293
0x18002b27e  mov     ecx, 220h; nSubAuthority1
0x18002b283  call    FIsUserGroupMember
0x18002b288  xor     ecx, ecx
0x18002b28a  test    eax, eax
0x18002b28c  setnz   cl
0x18002b28f  mov     eax, ecx
0x18002b291  jmp     short loc_18002B298
0x18002b293  mov     eax, 1
0x18002b298  mov     rcx, [rbp+var_8]
0x18002b29c  xor     rcx, rsp; StackCookie
0x18002b29f  call    __security_check_cookie
0x18002b2a4  add     rsp, 40h
0x18002b2a8  pop     rbp
0x18002b2a9  retn
```
