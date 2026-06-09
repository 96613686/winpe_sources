# AddAces(_ACL *,uchar,uchar,_ACL * *)

- ea: `0x140192ca8`
- end: `0x140192f04`
- name: `?AddAces@@YAJPEAU_ACL@@EEPEAPEAU1@@Z`
- size: `604`
- prototype: `__int64 __fastcall(PACL Acl, unsigned __int8, unsigned __int8, struct _ACL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x140192f0c`

## callees

- `0x1400eb380`
- `0x140192ca8`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140192ce8`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140192ce8`
- `ntoskrnl!RtlMapGenericMask` at `0x140192d04`
- `ntoskrnl!RtlMapGenericMask` at `0x140192d04`
- `ntoskrnl!RtlInitializeSid` at `0x140192d57`
- `ntoskrnl!RtlInitializeSid` at `0x140192d57`
- `ntoskrnl!RtlLengthSid` at `0x140192d7e`
- `ntoskrnl!RtlLengthSid` at `0x140192da6`
- `ntoskrnl!RtlLengthSid` at `0x140192d7e`
- `ntoskrnl!RtlLengthSid` at `0x140192da6`
- `ntoskrnl!SeExports` at `0x140192d95`
- `ntoskrnl!SeExports` at `0x140192e85`
- `ntoskrnl!RtlCreateAcl` at `0x140192ded`
- `ntoskrnl!RtlCreateAcl` at `0x140192ded`
- `ntoskrnl!RtlGetAce` at `0x140192e1a`
- `ntoskrnl!RtlGetAce` at `0x140192e1a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140192e44`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140192e6e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140192ea0`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140192e44`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140192e6e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140192ea0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192eb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192ed1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192eb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192ed1`
- `ntoskrnl!ExAllocatePool2` at `0x140192d2c`
- `ntoskrnl!ExAllocatePool2` at `0x140192dc4`
- `ntoskrnl!ExAllocatePool2` at `0x140192d2c`
- `ntoskrnl!ExAllocatePool2` at `0x140192dc4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140192d13`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140192d13`

## pseudocode

```c
__int64 __fastcall AddAces(PACL Acl, __int64 a2, char a3, struct _ACL **a4)
{
  int AclSize; // r14d
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  ULONG v9; // eax
  _DWORD *Pool2; // rax
  _DWORD *v11; // rsi
  struct _ACL *v13; // rdi
  NTSTATUS v14; // ebx
  ULONG v15; // ebx
  struct _ACL *v16; // rax
  signed int i; // r14d
  DWORD AccessMask; // [rsp+20h] [rbp-20h] BYREF
  PVOID Ace; // [rsp+28h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-10h] BYREF

  AclSize = Acl->AclSize;
  Ace = 0;
  AccessMask = 0x10000000;
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
  v9 = RtlLengthRequiredSid(2u);
  Pool2 = (_DWORD *)ExAllocatePool2(256, v9, 1935885390);
  v11 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v13 = 0;
  v14 = RtlInitializeSid(Pool2, &IdentifierAuthority, 2u);
  if ( !v14 )
  {
    v11[2] = 32;
    v11[3] = 556;
    v15 = RtlLengthSid(v11) + AclSize + 16;
    if ( a3 )
      v15 += RtlLengthSid(SeExports->SeLocalServiceSid) + 16;
    v16 = (struct _ACL *)ExAllocatePool2(256, v15, 1633895502);
    v13 = v16;
    if ( v16 )
    {
      v14 = RtlCreateAcl(v16, v15, 2u);
      if ( v14 >= 0 )
      {
        for ( i = 0; i < Acl->AceCount; ++i )
        {
          v14 = RtlGetAce(Acl, i, &Ace);
          if ( v14 < 0 )
            goto LABEL_18;
          v14 = RtlAddAccessAllowedAce(v13, 2u, *((_DWORD *)Ace + 1), (char *)Ace + 8);
          if ( v14 < 0 )
            goto LABEL_18;
        }
        v14 = RtlAddAccessAllowedAce(v13, 2u, AccessMask, v11);
        if ( v14 >= 0 )
        {
          if ( a3 )
            v14 = RtlAddAccessAllowedAce(v13, 2u, AccessMask, SeExports->SeLocalServiceSid);
          *a4 = v13;
        }
      }
    }
    else
    {
      v14 = -1073741670;
    }
  }
LABEL_18:
  ExFreePoolWithTag(v11, 0);
  if ( v14 < 0 )
  {
    if ( v13 )
      ExFreePoolWithTag(v13, 0);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140192ca8  mov     [rsp-38h+arg_8], rbx
0x140192cad  push    rbp
0x140192cae  push    rsi
0x140192caf  push    rdi
0x140192cb0  push    r12
0x140192cb2  push    r13
0x140192cb4  push    r14
0x140192cb6  push    r15
0x140192cb8  mov     rbp, rsp
0x140192cbb  sub     rsp, 40h
0x140192cbf  mov     rax, cs:__security_cookie
0x140192cc6  xor     rax, rsp
0x140192cc9  mov     [rbp+var_8], rax
0x140192ccd  movzx   r14d, word ptr [rcx+2]
0x140192cd2  xor     ebx, ebx
0x140192cd4  mov     [rbp+Ace], rbx
0x140192cd8  mov     r13, r9
0x140192cdb  mov     r12b, r8b
0x140192cde  mov     [rbp+AccessMask], 10000000h
0x140192ce5  mov     r15, rcx
0x140192ce8  call    cs:__imp_IoGetFileObjectGenericMapping
0x140192cef  nop     dword ptr [rax+rax+00h]
0x140192cf4  lea     rcx, [rbp+AccessMask]; AccessMask
0x140192cf8  mov     dword ptr [rbp+IdentifierAuthority.Value], ebx
0x140192cfb  mov     rdx, rax; GenericMapping
0x140192cfe  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x140192d04  call    cs:__imp_RtlMapGenericMask
0x140192d0b  nop     dword ptr [rax+rax+00h]
0x140192d10  lea     ecx, [rbx+2]; SubAuthorityCount
0x140192d13  call    cs:__imp_RtlLengthRequiredSid
0x140192d1a  nop     dword ptr [rax+rax+00h]
0x140192d1f  mov     edx, eax
0x140192d21  mov     ecx, 100h
0x140192d26  mov     r8d, 7363444Eh
0x140192d2c  call    cs:__imp_ExAllocatePool2
0x140192d33  nop     dword ptr [rax+rax+00h]
0x140192d38  mov     rsi, rax
0x140192d3b  test    rax, rax
0x140192d3e  jnz     short loc_140192D4A
0x140192d40  mov     eax, 0C000009Ah
0x140192d45  jmp     loc_140192EDF
0x140192d4a  mov     r8b, 2; SubAuthorityCount
0x140192d4d  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x140192d51  mov     rcx, rsi; Sid
0x140192d54  mov     rdi, rbx
0x140192d57  call    cs:__imp_RtlInitializeSid
0x140192d5e  nop     dword ptr [rax+rax+00h]
0x140192d63  mov     ebx, eax
0x140192d65  test    eax, eax
0x140192d67  jnz     loc_140192EB2
0x140192d6d  mov     rcx, rsi; Sid
0x140192d70  mov     dword ptr [rsi+8], 20h ; ' '
0x140192d77  mov     dword ptr [rsi+0Ch], 22Ch
0x140192d7e  call    cs:__imp_RtlLengthSid
0x140192d85  nop     dword ptr [rax+rax+00h]
0x140192d8a  lea     ebx, [r14+10h]
0x140192d8e  add     ebx, eax
0x140192d90  test    r12b, r12b
0x140192d93  jz      short loc_140192DB7
0x140192d95  mov     rax, cs:__imp_SeExports
0x140192d9c  mov     rcx, [rax]
0x140192d9f  mov     rcx, [rcx+180h]; Sid
0x140192da6  call    cs:__imp_RtlLengthSid
0x140192dad  nop     dword ptr [rax+rax+00h]
0x140192db2  add     ebx, 10h
0x140192db5  add     ebx, eax
0x140192db7  mov     edx, ebx
0x140192db9  mov     ecx, 100h
0x140192dbe  mov     r8d, 6163444Eh
0x140192dc4  call    cs:__imp_ExAllocatePool2
0x140192dcb  nop     dword ptr [rax+rax+00h]
0x140192dd0  mov     rdi, rax
0x140192dd3  test    rax, rax
0x140192dd6  jnz     short loc_140192DE2
0x140192dd8  mov     ebx, 0C000009Ah
0x140192ddd  jmp     loc_140192EB2
0x140192de2  mov     r8d, 2; AclRevision
0x140192de8  mov     edx, ebx; AclLength
0x140192dea  mov     rcx, rdi; Acl
0x140192ded  call    cs:__imp_RtlCreateAcl
0x140192df4  nop     dword ptr [rax+rax+00h]
0x140192df9  mov     ebx, eax
0x140192dfb  test    eax, eax
0x140192dfd  js      loc_140192EB2
0x140192e03  xor     r14d, r14d
0x140192e06  movzx   eax, word ptr [r15+4]
0x140192e0b  cmp     r14d, eax
0x140192e0e  jge     short loc_140192E5B
0x140192e10  lea     r8, [rbp+Ace]; Ace
0x140192e14  mov     edx, r14d; AceIndex
0x140192e17  mov     rcx, r15; Acl
0x140192e1a  call    cs:__imp_RtlGetAce
0x140192e21  nop     dword ptr [rax+rax+00h]
0x140192e26  mov     ebx, eax
0x140192e28  test    eax, eax
0x140192e2a  js      loc_140192EB2
0x140192e30  mov     r8, [rbp+Ace]
0x140192e34  mov     edx, 2; AceRevision
0x140192e39  mov     rcx, rdi; Acl
0x140192e3c  lea     r9, [r8+8]; Sid
0x140192e40  mov     r8d, [r8+4]; AccessMask
0x140192e44  call    cs:__imp_RtlAddAccessAllowedAce
0x140192e4b  nop     dword ptr [rax+rax+00h]
0x140192e50  mov     ebx, eax
0x140192e52  test    eax, eax
0x140192e54  js      short loc_140192EB2
0x140192e56  inc     r14d
0x140192e59  jmp     short loc_140192E06
0x140192e5b  mov     r8d, [rbp+AccessMask]; AccessMask
0x140192e5f  mov     r14d, 2
0x140192e65  mov     edx, r14d; AceRevision
0x140192e68  mov     r9, rsi; Sid
0x140192e6b  mov     rcx, rdi; Acl
0x140192e6e  call    cs:__imp_RtlAddAccessAllowedAce
0x140192e75  nop     dword ptr [rax+rax+00h]
0x140192e7a  mov     ebx, eax
0x140192e7c  test    eax, eax
0x140192e7e  js      short loc_140192EB2
0x140192e80  test    r12b, r12b
0x140192e83  jz      short loc_140192EAE
0x140192e85  mov     rax, cs:__imp_SeExports
0x140192e8c  mov     edx, r14d; AceRevision
0x140192e8f  mov     r8d, [rbp+AccessMask]; AccessMask
0x140192e93  mov     rcx, rdi; Acl
0x140192e96  mov     r9, [rax]
0x140192e99  mov     r9, [r9+180h]; Sid
0x140192ea0  call    cs:__imp_RtlAddAccessAllowedAce
0x140192ea7  nop     dword ptr [rax+rax+00h]
0x140192eac  mov     ebx, eax
0x140192eae  mov     [r13+0], rdi
0x140192eb2  xor     edx, edx; Tag
0x140192eb4  mov     rcx, rsi; P
0x140192eb7  call    cs:__imp_ExFreePoolWithTag
0x140192ebe  nop     dword ptr [rax+rax+00h]
0x140192ec3  test    ebx, ebx
0x140192ec5  jns     short loc_140192EDD
0x140192ec7  test    rdi, rdi
0x140192eca  jz      short loc_140192EDD
0x140192ecc  xor     edx, edx; Tag
0x140192ece  mov     rcx, rdi; P
0x140192ed1  call    cs:__imp_ExFreePoolWithTag
0x140192ed8  nop     dword ptr [rax+rax+00h]
0x140192edd  mov     eax, ebx
0x140192edf  mov     rcx, [rbp+var_8]
0x140192ee3  xor     rcx, rsp; StackCookie
0x140192ee6  call    __security_check_cookie
0x140192eeb  mov     rbx, [rsp+40h+arg_8]
0x140192ef3  add     rsp, 40h
0x140192ef7  pop     r15
0x140192ef9  pop     r14
0x140192efb  pop     r13
0x140192efd  pop     r12
0x140192eff  pop     rdi
0x140192f00  pop     rsi
0x140192f01  pop     rbp
0x140192f02  retn
```
