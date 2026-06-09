# FIsSidGroupMembershipOfCaller(ushort const *)

- ea: `0x180031858`
- end: `0x1800318a7`
- name: `?FIsSidGroupMembershipOfCaller@@YAHPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180031674`
- `0x1800316e8`

## callees

- `0x180031858`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x180031872`
- `ADVAPI32!ConvertStringSidToSidW` at `0x180031872`
- `ADVAPI32!CheckTokenMembership` at `0x180031888`
- `ADVAPI32!CheckTokenMembership` at `0x180031888`
- `KERNEL32!LocalFree` at `0x180031898`
- `KERNEL32!LocalFree` at `0x180031898`

## pseudocode

```c
__int64 __fastcall FIsSidGroupMembershipOfCaller(const unsigned __int16 *a1)
{
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  IsMember = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
    CheckTokenMembership(0, Sid, &IsMember);
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180031858  sub     rsp, 28h
0x18003185c  lea     rdx, [rsp+28h+Sid]; Sid
0x180031861  mov     [rsp+28h+IsMember], 0
0x180031869  mov     [rsp+28h+Sid], 0
0x180031872  call    cs:__imp_ConvertStringSidToSidW
0x180031878  test    eax, eax
0x18003187a  jz      short loc_18003188E
0x18003187c  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x180031881  lea     r8, [rsp+28h+IsMember]; IsMember
0x180031886  xor     ecx, ecx; TokenHandle
0x180031888  call    cs:__imp_CheckTokenMembership
0x18003188e  mov     rcx, [rsp+28h+Sid]; hMem
0x180031893  test    rcx, rcx
0x180031896  jz      short loc_18003189E
0x180031898  call    cs:__imp_LocalFree
0x18003189e  mov     eax, [rsp+28h+IsMember]
0x1800318a2  add     rsp, 28h
0x1800318a6  retn
```
