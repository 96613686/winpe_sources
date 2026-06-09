# SecurityHelper::IsInAdministratorGroup(void *)

- ea: `0x1800381d8`
- end: `0x180038340`
- name: `?IsInAdministratorGroup@SecurityHelper@@YAHPEAX@Z`
- size: `360`
- prototype: `__int64 __fastcall(SecurityHelper *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c3d0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800381d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180038222`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003826e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800382ba`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180038302`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180038222`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003826e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800382ba`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180038302`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180038236`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180038282`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800382ce`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180038316`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180038236`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180038282`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800382ce`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180038316`

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
0x1800381d8  mov     [rsp-8+arg_0], rbx
0x1800381dd  push    rbp
0x1800381de  lea     rbp, [rsp-57h]
0x1800381e3  sub     rsp, 90h
0x1800381ea  mov     rax, cs:__security_cookie
0x1800381f1  xor     rax, rsp
0x1800381f4  mov     [rbp+57h+var_10], rax
0x1800381f8  mov     ebx, 44h ; 'D'
0x1800381fd  mov     [rbp+57h+IsMember], 0
0x180038204  mov     r8d, ebx; Size
0x180038207  lea     rcx, [rbp+57h+pSid]; void *
0x18003820b  xor     edx, edx; Val
0x18003820d  call    memset_0
0x180038212  lea     r9, [rbp+57h+cbSid]; cbSid
0x180038216  mov     [rbp+57h+cbSid], ebx
0x180038219  lea     r8, [rbp+57h+pSid]; pSid
0x18003821d  xor     edx, edx; DomainSid
0x18003821f  lea     ecx, [rbx-2Ah]; WellKnownSidType
0x180038222  call    cs:__imp_CreateWellKnownSid
0x180038228  test    eax, eax
0x18003822a  jz      short loc_180038245
0x18003822c  lea     r8, [rbp+57h+IsMember]; IsMember
0x180038230  xor     ecx, ecx; TokenHandle
0x180038232  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180038236  call    cs:__imp_CheckTokenMembership
0x18003823c  test    eax, eax
0x18003823e  jnz     short loc_180038245
0x180038240  mov     [rbp+57h+IsMember], eax
0x180038243  jmp     short loc_180038248
0x180038245  mov     eax, [rbp+57h+IsMember]
0x180038248  test    eax, eax
0x18003824a  jnz     loc_180038323
0x180038250  mov     r8, rbx; Size
0x180038253  lea     rcx, [rbp+57h+pSid]; void *
0x180038257  xor     edx, edx; Val
0x180038259  call    memset_0
0x18003825e  xor     edx, edx; DomainSid
0x180038260  mov     [rbp+57h+cbSid], ebx
0x180038263  lea     r9, [rbp+57h+cbSid]; cbSid
0x180038267  lea     r8, [rbp+57h+pSid]; pSid
0x18003826b  lea     ecx, [rdx+26h]; WellKnownSidType
0x18003826e  call    cs:__imp_CreateWellKnownSid
0x180038274  test    eax, eax
0x180038276  jz      short loc_180038291
0x180038278  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003827c  xor     ecx, ecx; TokenHandle
0x18003827e  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180038282  call    cs:__imp_CheckTokenMembership
0x180038288  test    eax, eax
0x18003828a  jnz     short loc_180038291
0x18003828c  mov     [rbp+57h+IsMember], eax
0x18003828f  jmp     short loc_180038294
0x180038291  mov     eax, [rbp+57h+IsMember]
0x180038294  test    eax, eax
0x180038296  jnz     loc_180038323
0x18003829c  mov     r8, rbx; Size
0x18003829f  lea     rcx, [rbp+57h+pSid]; void *
0x1800382a3  xor     edx, edx; Val
0x1800382a5  call    memset_0
0x1800382aa  xor     edx, edx; DomainSid
0x1800382ac  mov     [rbp+57h+cbSid], ebx
0x1800382af  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800382b3  lea     r8, [rbp+57h+pSid]; pSid
0x1800382b7  lea     ecx, [rdx+29h]; WellKnownSidType
0x1800382ba  call    cs:__imp_CreateWellKnownSid
0x1800382c0  test    eax, eax
0x1800382c2  jz      short loc_1800382DD
0x1800382c4  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800382c8  xor     ecx, ecx; TokenHandle
0x1800382ca  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800382ce  call    cs:__imp_CheckTokenMembership
0x1800382d4  test    eax, eax
0x1800382d6  jnz     short loc_1800382DD
0x1800382d8  mov     [rbp+57h+IsMember], eax
0x1800382db  jmp     short loc_1800382E0
0x1800382dd  mov     eax, [rbp+57h+IsMember]
0x1800382e0  test    eax, eax
0x1800382e2  jnz     short loc_180038323
0x1800382e4  mov     r8, rbx; Size
0x1800382e7  lea     rcx, [rbp+57h+pSid]; void *
0x1800382eb  xor     edx, edx; Val
0x1800382ed  call    memset_0
0x1800382f2  xor     edx, edx; DomainSid
0x1800382f4  mov     [rbp+57h+cbSid], ebx
0x1800382f7  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800382fb  lea     r8, [rbp+57h+pSid]; pSid
0x1800382ff  lea     ecx, [rdx+30h]; WellKnownSidType
0x180038302  call    cs:__imp_CreateWellKnownSid
0x180038308  test    eax, eax
0x18003830a  jz      short loc_180038320
0x18003830c  lea     r8, [rbp+57h+IsMember]; IsMember
0x180038310  xor     ecx, ecx; TokenHandle
0x180038312  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180038316  call    cs:__imp_CheckTokenMembership
0x18003831c  test    eax, eax
0x18003831e  jz      short loc_180038323
0x180038320  mov     eax, [rbp+57h+IsMember]
0x180038323  mov     rcx, [rbp+57h+var_10]
0x180038327  xor     rcx, rsp; StackCookie
0x18003832a  call    __security_check_cookie
0x18003832f  mov     rbx, [rsp+90h+arg_0]
0x180038337  add     rsp, 90h
0x18003833e  pop     rbp
0x18003833f  retn
```
