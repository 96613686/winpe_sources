# FIsUserAdmin

- ea: `0x1800021e8`
- end: `0x18000227c`
- name: `FIsUserAdmin`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180002020`

## callees

- `0x1800021e8`
- `0x180002284`
- `0x180002444`
- `0x1800026e0`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x180002225`
- `ADVAPI32!CheckTokenMembership` at `0x180002225`
- `KERNEL32!GetLastError` at `0x18000222f`
- `KERNEL32!GetLastError` at `0x18000222f`

## string_xrefs

- `0x180002235`: `CheckTokenMemberShip for local system failed. Error = %#x`

## pseudocode

```c
_BOOL8 FIsUserAdmin()
{
  DWORD LastError; // eax
  BOOL v1; // eax
  BOOL IsMember; // [rsp+20h] [rbp-20h] BYREF
  _DWORD SidToCheck[4]; // [rsp+28h] [rbp-18h] BYREF

  IsMember = 0;
  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v1 = IsMember;
  }
  else
  {
    LastError = GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"CheckTokenMemberShip for local system failed. Error = %#x", LastError);
    v1 = 0;
    IsMember = 0;
  }
  return v1 || FIsUserGroupMember();
}

```

## disassembly

```asm
0x1800021e8  push    rbp
0x1800021ea  mov     rbp, rsp
0x1800021ed  sub     rsp, 40h
0x1800021f1  mov     rax, cs:__security_cookie
0x1800021f8  xor     rax, rsp
0x1800021fb  mov     [rbp+var_8], rax
0x1800021ff  lea     r8, [rbp+IsMember]; IsMember
0x180002203  mov     [rbp+IsMember], 0
0x18000220a  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x18000220e  mov     [rbp+SidToCheck], 101h
0x180002215  xor     ecx, ecx; TokenHandle
0x180002217  mov     [rbp+var_14], 5000000h
0x18000221e  mov     [rbp+var_10], 12h
0x180002225  call    cs:__imp_CheckTokenMembership
0x18000222b  test    eax, eax
0x18000222d  jnz     short loc_18000224E
0x18000222f  call    cs:__imp_GetLastError
0x180002235  lea     rdx, aChecktokenmemb; "CheckTokenMemberShip for local system f"...
0x18000223c  or      ecx, 0FFFFFFFFh
0x18000223f  mov     r8d, eax
0x180002242  call    MyDbgPrintfW
0x180002247  xor     eax, eax
0x180002249  mov     [rbp+IsMember], eax
0x18000224c  jmp     short loc_180002251
0x18000224e  mov     eax, [rbp+IsMember]
0x180002251  test    eax, eax
0x180002253  jnz     short loc_180002265
0x180002255  call    FIsUserGroupMember
0x18000225a  xor     ecx, ecx
0x18000225c  test    eax, eax
0x18000225e  setnz   cl
0x180002261  mov     eax, ecx
0x180002263  jmp     short loc_18000226A
0x180002265  mov     eax, 1
0x18000226a  mov     rcx, [rbp+var_8]
0x18000226e  xor     rcx, rsp; StackCookie
0x180002271  call    __security_check_cookie
0x180002276  add     rsp, 40h
0x18000227a  pop     rbp
0x18000227b  retn
```
