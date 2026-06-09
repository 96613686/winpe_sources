# NcaAPIsIsAccessGranted

- ea: `0x18001bd68`
- end: `0x18001bebb`
- name: `NcaAPIsIsAccessGranted`
- size: `339`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, HANDLE ClientToken, DWORD DesiredAccess, WINBOOL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c8e0`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x18001bd68`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be24`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001be14`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001be14`

## pseudocode

```c
__int64 __fastcall NcaAPIsIsAccessGranted(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        HANDLE ClientToken,
        DWORD DesiredAccess,
        WINBOOL *a4)
{
  signed int LastError; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  WINBOOL AccessStatus; // [rsp+40h] [rbp-19h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-15h] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-11h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+50h] [rbp-9h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp+Fh] BYREF

  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  GenericMapping = 0;
  AccessStatus = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids);
  if ( AccessCheck(
         pSecurityDescriptor,
         ClientToken,
         DesiredAccess,
         &GenericMapping,
         &PrivilegeSet,
         &PrivilegeSetLength,
         &GrantedAccess,
         &AccessStatus) )
  {
    v9 = 0;
    *a4 = AccessStatus;
    goto LABEL_11;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_12:
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
        WPP_SF_d(v10[2], 44, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, v9);
      return v9;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, v9);
LABEL_11:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  return v9;
}

```

## disassembly

```asm
0x18001bd68  push    rbp
0x18001bd6a  push    rbx
0x18001bd6b  push    rsi
0x18001bd6c  push    rdi
0x18001bd6d  push    r12
0x18001bd6f  push    r14
0x18001bd71  lea     rbp, [rsp-2Fh]
0x18001bd76  sub     rsp, 88h
0x18001bd7d  mov     rax, cs:__security_cookie
0x18001bd84  xor     rax, rsp
0x18001bd87  mov     [rbp+57h+var_38], rax
0x18001bd8b  xor     eax, eax
0x18001bd8d  mov     [rbp+57h+var_68], 14h
0x18001bd94  xorps   xmm0, xmm0
0x18001bd97  mov     [rbp+57h+var_60.Privilege.Attributes], eax
0x18001bd9a  xorps   xmm1, xmm1
0x18001bd9d  mov     [rbp+57h+var_6C], eax
0x18001bda0  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18001bda4  mov     [rbp+57h+var_70], eax
0x18001bda7  mov     rdi, r9
0x18001bdaa  movups  xmmword ptr [rbp+57h+var_60.PrivilegeCount], xmm1
0x18001bdae  mov     r14d, r8d
0x18001bdb1  mov     rsi, rdx
0x18001bdb4  mov     rbx, rcx
0x18001bdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdbe  lea     r12, WPP_GLOBAL_Control
0x18001bdc5  cmp     rcx, r12
0x18001bdc8  jz      short loc_18001BDE3
0x18001bdca  test    byte ptr [rcx+1Ch], 8
0x18001bdce  jz      short loc_18001BDE3
0x18001bdd0  mov     rcx, [rcx+10h]
0x18001bdd4  lea     edx, [rax+2Ah]
0x18001bdd7  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001bdde  call    WPP_SF_
0x18001bde3  lea     rax, [rbp+57h+var_70]
0x18001bde7  mov     r8d, r14d; DesiredAccess
0x18001bdea  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18001bdef  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18001bdf3  lea     rax, [rbp+57h+var_6C]
0x18001bdf7  mov     rdx, rsi; ClientToken
0x18001bdfa  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x18001bdff  mov     rcx, rbx; pSecurityDescriptor
0x18001be02  lea     rax, [rbp+57h+var_68]
0x18001be06  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001be0b  lea     rax, [rbp+57h+var_60]
0x18001be0f  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x18001be14  call    cs:__imp_AccessCheck
0x18001be1b  nop     dword ptr [rax+rax+00h]
0x18001be20  test    eax, eax
0x18001be22  jnz     short loc_18001BE6B
0x18001be24  call    cs:__imp_GetLastError
0x18001be2b  nop     dword ptr [rax+rax+00h]
0x18001be30  mov     ebx, eax
0x18001be32  test    eax, eax
0x18001be34  jle     short loc_18001BE3F
0x18001be36  movzx   ebx, ax
0x18001be39  or      ebx, 80070000h
0x18001be3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be46  cmp     rcx, r12
0x18001be49  jz      short loc_18001BE9C
0x18001be4b  test    byte ptr [rcx+1Ch], 1
0x18001be4f  jz      short loc_18001BE79
0x18001be51  mov     rcx, [rcx+10h]
0x18001be55  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001be5c  mov     edx, 2Bh ; '+'
0x18001be61  mov     r9d, ebx
0x18001be64  call    WPP_SF_d
0x18001be69  jmp     short loc_18001BE72
0x18001be6b  mov     eax, [rbp+57h+var_70]
0x18001be6e  xor     ebx, ebx
0x18001be70  mov     [rdi], eax
0x18001be72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be79  cmp     rcx, r12
0x18001be7c  jz      short loc_18001BE9C
0x18001be7e  test    byte ptr [rcx+1Ch], 8
0x18001be82  jz      short loc_18001BE9C
0x18001be84  mov     rcx, [rcx+10h]
0x18001be88  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001be8f  mov     edx, 2Ch ; ','
0x18001be94  mov     r9d, ebx
0x18001be97  call    WPP_SF_d
0x18001be9c  mov     eax, ebx
0x18001be9e  mov     rcx, [rbp+57h+var_38]
0x18001bea2  xor     rcx, rsp; StackCookie
0x18001bea5  call    __security_check_cookie
0x18001beaa  add     rsp, 88h
0x18001beb1  pop     r14
0x18001beb3  pop     r12
0x18001beb5  pop     rdi
0x18001beb6  pop     rsi
0x18001beb7  pop     rbx
0x18001beb8  pop     rbp
0x18001beb9  retn
```
