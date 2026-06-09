# FIsUserAdmin

- ea: `0x1800044c8`
- end: `0x18000455c`
- name: `FIsUserAdmin`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180003720`

## callees

- `0x1800044c8`
- `0x180004564`
- `0x180004e1c`
- `0x1800054b0`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x180004505`
- `ADVAPI32!CheckTokenMembership` at `0x180004505`
- `KERNEL32!GetLastError` at `0x18000450f`
- `KERNEL32!GetLastError` at `0x18000450f`

## string_xrefs

- `0x180004515`: `CheckTokenMemberShip for local system failed. Error = %#x`

## pseudocode

```c
_BOOL8 FIsUserAdmin()
{
  DWORD LastError; // eax
  __int64 v1; // r9
  BOOL v2; // eax
  BOOL IsMember; // [rsp+20h] [rbp-20h] BYREF
  _DWORD SidToCheck[4]; // [rsp+28h] [rbp-18h] BYREF

  IsMember = 0;
  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v2 = IsMember;
  }
  else
  {
    LastError = GetLastError();
    MyDbgPrintfW(0xFFFFFFFFLL, L"CheckTokenMemberShip for local system failed. Error = %#x", LastError, v1);
    v2 = 0;
    IsMember = 0;
  }
  return v2 || FIsUserGroupMember();
}

```

## disassembly

```asm
0x1800044c8  push    rbp
0x1800044ca  mov     rbp, rsp
0x1800044cd  sub     rsp, 40h
0x1800044d1  mov     rax, cs:__security_cookie
0x1800044d8  xor     rax, rsp
0x1800044db  mov     [rbp+var_8], rax
0x1800044df  lea     r8, [rbp+IsMember]; IsMember
0x1800044e3  mov     [rbp+IsMember], 0
0x1800044ea  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x1800044ee  mov     [rbp+SidToCheck], 101h
0x1800044f5  xor     ecx, ecx; TokenHandle
0x1800044f7  mov     [rbp+var_14], 5000000h
0x1800044fe  mov     [rbp+var_10], 12h
0x180004505  call    cs:__imp_CheckTokenMembership
0x18000450b  test    eax, eax
0x18000450d  jnz     short loc_18000452E
0x18000450f  call    cs:__imp_GetLastError
0x180004515  lea     rdx, aChecktokenmemb; "CheckTokenMemberShip for local system f"...
0x18000451c  or      ecx, 0FFFFFFFFh
0x18000451f  mov     r8d, eax
0x180004522  call    MyDbgPrintfW
0x180004527  xor     eax, eax
0x180004529  mov     [rbp+IsMember], eax
0x18000452c  jmp     short loc_180004531
0x18000452e  mov     eax, [rbp+IsMember]
0x180004531  test    eax, eax
0x180004533  jnz     short loc_180004545
0x180004535  call    FIsUserGroupMember
0x18000453a  xor     ecx, ecx
0x18000453c  test    eax, eax
0x18000453e  setnz   cl
0x180004541  mov     eax, ecx
0x180004543  jmp     short loc_18000454A
0x180004545  mov     eax, 1
0x18000454a  mov     rcx, [rbp+var_8]
0x18000454e  xor     rcx, rsp; StackCookie
0x180004551  call    __security_check_cookie
0x180004556  add     rsp, 40h
0x18000455a  pop     rbp
0x18000455b  retn
```
