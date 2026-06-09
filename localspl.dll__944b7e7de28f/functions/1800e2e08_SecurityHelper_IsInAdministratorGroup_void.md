# SecurityHelper::IsInAdministratorGroup(void *)

- ea: `0x1800e2e08`
- end: `0x1800e2f70`
- name: `?IsInAdministratorGroup@SecurityHelper@@YAHPEAX@Z`
- size: `360`
- prototype: `__int64 __fastcall(SecurityHelper *__hidden this, void *)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022264`
- `0x180038434`
- `0x180055700`
- `0x180055800`
- `0x180055bd0`
- `0x180088380`
- `0x18008d670`
- `0x18008d770`
- `0x18008f550`
- `0x18008f5f0`
- `0x18008f680`

## callees

- `0x180046650`
- `0x180047330`
- `0x1800e2e08`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800e2e66`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800e2eb2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800e2efe`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800e2f46`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800e2e66`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800e2eb2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800e2efe`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800e2f46`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e2e52`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e2e9e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e2eea`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e2f32`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e2e52`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e2e9e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e2eea`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800e2f32`

## pseudocode

```c
WINBOOL __fastcall SecurityHelper::IsInAdministratorGroup(SecurityHelper *this, void *a2)
{
  WINBOOL result; // eax
  WINBOOL IsMember; // [rsp+20h] [rbp-19h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-15h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-9h] BYREF

  IsMember = 0;
  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid)
    || (result = CheckTokenMembership(0, pSid, &IsMember)) != 0 )
  {
    result = IsMember;
  }
  else
  {
    IsMember = 0;
  }
  if ( !result )
  {
    memset_0(pSid, 0, 0x44u);
    cbSid[0] = 68;
    if ( !CreateWellKnownSid(WinAccountAdministratorSid, 0, pSid, cbSid)
      || (result = CheckTokenMembership(0, pSid, &IsMember)) != 0 )
    {
      result = IsMember;
    }
    else
    {
      IsMember = 0;
    }
    if ( !result )
    {
      memset_0(pSid, 0, 0x44u);
      cbSid[0] = 68;
      if ( !CreateWellKnownSid(WinAccountDomainAdminsSid, 0, pSid, cbSid)
        || (result = CheckTokenMembership(0, pSid, &IsMember)) != 0 )
      {
        result = IsMember;
      }
      else
      {
        IsMember = 0;
      }
      if ( !result )
      {
        memset_0(pSid, 0, 0x44u);
        cbSid[0] = 68;
        if ( !CreateWellKnownSid(WinAccountEnterpriseAdminsSid, 0, pSid, cbSid) )
          return IsMember;
        result = CheckTokenMembership(0, pSid, &IsMember);
        if ( result )
          return IsMember;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800e2e08  mov     [rsp-8+arg_0], rbx
0x1800e2e0d  push    rbp
0x1800e2e0e  lea     rbp, [rsp-57h]
0x1800e2e13  sub     rsp, 90h
0x1800e2e1a  mov     rax, cs:__security_cookie
0x1800e2e21  xor     rax, rsp
0x1800e2e24  mov     [rbp+57h+var_10], rax
0x1800e2e28  mov     ebx, 44h ; 'D'
0x1800e2e2d  mov     [rbp+57h+IsMember], 0
0x1800e2e34  mov     r8d, ebx; Size
0x1800e2e37  lea     rcx, [rbp+57h+pSid]; void *
0x1800e2e3b  xor     edx, edx; Val
0x1800e2e3d  call    memset_0
0x1800e2e42  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800e2e46  mov     [rbp+57h+cbSid], ebx
0x1800e2e49  lea     r8, [rbp+57h+pSid]; pSid
0x1800e2e4d  xor     edx, edx; DomainSid
0x1800e2e4f  lea     ecx, [rbx-2Ah]; WellKnownSidType
0x1800e2e52  call    cs:__imp_CreateWellKnownSid
0x1800e2e58  test    eax, eax
0x1800e2e5a  jz      short loc_1800E2E75
0x1800e2e5c  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800e2e60  xor     ecx, ecx; TokenHandle
0x1800e2e62  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800e2e66  call    cs:__imp_CheckTokenMembership
0x1800e2e6c  test    eax, eax
0x1800e2e6e  jnz     short loc_1800E2E75
0x1800e2e70  mov     [rbp+57h+IsMember], eax
0x1800e2e73  jmp     short loc_1800E2E78
0x1800e2e75  mov     eax, [rbp+57h+IsMember]
0x1800e2e78  test    eax, eax
0x1800e2e7a  jnz     loc_1800E2F53
0x1800e2e80  mov     r8, rbx; Size
0x1800e2e83  lea     rcx, [rbp+57h+pSid]; void *
0x1800e2e87  xor     edx, edx; Val
0x1800e2e89  call    memset_0
0x1800e2e8e  xor     edx, edx; DomainSid
0x1800e2e90  mov     [rbp+57h+cbSid], ebx
0x1800e2e93  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800e2e97  lea     r8, [rbp+57h+pSid]; pSid
0x1800e2e9b  lea     ecx, [rdx+26h]; WellKnownSidType
0x1800e2e9e  call    cs:__imp_CreateWellKnownSid
0x1800e2ea4  test    eax, eax
0x1800e2ea6  jz      short loc_1800E2EC1
0x1800e2ea8  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800e2eac  xor     ecx, ecx; TokenHandle
0x1800e2eae  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800e2eb2  call    cs:__imp_CheckTokenMembership
0x1800e2eb8  test    eax, eax
0x1800e2eba  jnz     short loc_1800E2EC1
0x1800e2ebc  mov     [rbp+57h+IsMember], eax
0x1800e2ebf  jmp     short loc_1800E2EC4
0x1800e2ec1  mov     eax, [rbp+57h+IsMember]
0x1800e2ec4  test    eax, eax
0x1800e2ec6  jnz     loc_1800E2F53
0x1800e2ecc  mov     r8, rbx; Size
0x1800e2ecf  lea     rcx, [rbp+57h+pSid]; void *
0x1800e2ed3  xor     edx, edx; Val
0x1800e2ed5  call    memset_0
0x1800e2eda  xor     edx, edx; DomainSid
0x1800e2edc  mov     [rbp+57h+cbSid], ebx
0x1800e2edf  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800e2ee3  lea     r8, [rbp+57h+pSid]; pSid
0x1800e2ee7  lea     ecx, [rdx+29h]; WellKnownSidType
0x1800e2eea  call    cs:__imp_CreateWellKnownSid
0x1800e2ef0  test    eax, eax
0x1800e2ef2  jz      short loc_1800E2F0D
0x1800e2ef4  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800e2ef8  xor     ecx, ecx; TokenHandle
0x1800e2efa  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800e2efe  call    cs:__imp_CheckTokenMembership
0x1800e2f04  test    eax, eax
0x1800e2f06  jnz     short loc_1800E2F0D
0x1800e2f08  mov     [rbp+57h+IsMember], eax
0x1800e2f0b  jmp     short loc_1800E2F10
0x1800e2f0d  mov     eax, [rbp+57h+IsMember]
0x1800e2f10  test    eax, eax
0x1800e2f12  jnz     short loc_1800E2F53
0x1800e2f14  mov     r8, rbx; Size
0x1800e2f17  lea     rcx, [rbp+57h+pSid]; void *
0x1800e2f1b  xor     edx, edx; Val
0x1800e2f1d  call    memset_0
0x1800e2f22  xor     edx, edx; DomainSid
0x1800e2f24  mov     [rbp+57h+cbSid], ebx
0x1800e2f27  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800e2f2b  lea     r8, [rbp+57h+pSid]; pSid
0x1800e2f2f  lea     ecx, [rdx+30h]; WellKnownSidType
0x1800e2f32  call    cs:__imp_CreateWellKnownSid
0x1800e2f38  test    eax, eax
0x1800e2f3a  jz      short loc_1800E2F50
0x1800e2f3c  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800e2f40  xor     ecx, ecx; TokenHandle
0x1800e2f42  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800e2f46  call    cs:__imp_CheckTokenMembership
0x1800e2f4c  test    eax, eax
0x1800e2f4e  jz      short loc_1800E2F53
0x1800e2f50  mov     eax, [rbp+57h+IsMember]
0x1800e2f53  mov     rcx, [rbp+57h+var_10]
0x1800e2f57  xor     rcx, rsp; StackCookie
0x1800e2f5a  call    __security_check_cookie
0x1800e2f5f  mov     rbx, [rsp+90h+arg_0]
0x1800e2f67  add     rsp, 90h
0x1800e2f6e  pop     rbp
0x1800e2f6f  retn
```
