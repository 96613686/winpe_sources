# AddAces(_ACL *,uchar,uchar,_ACL * *)

- ea: `0x14018cc98`
- end: `0x14018cef4`
- name: `?AddAces@@YAJPEAU_ACL@@EEPEAPEAU1@@Z`
- size: `604`
- prototype: `__int64 __fastcall(PACL Acl, unsigned __int8, unsigned __int8, struct _ACL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x14018cefc`

## callees

- `0x1400e6160`
- `0x14018cc98`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14018ccd8`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14018ccd8`
- `ntoskrnl!RtlMapGenericMask` at `0x14018ccf4`
- `ntoskrnl!RtlMapGenericMask` at `0x14018ccf4`
- `ntoskrnl!RtlInitializeSid` at `0x14018cd47`
- `ntoskrnl!RtlInitializeSid` at `0x14018cd47`
- `ntoskrnl!RtlLengthSid` at `0x14018cd6e`
- `ntoskrnl!RtlLengthSid` at `0x14018cd96`
- `ntoskrnl!RtlLengthSid` at `0x14018cd6e`
- `ntoskrnl!RtlLengthSid` at `0x14018cd96`
- `ntoskrnl!SeExports` at `0x14018cd85`
- `ntoskrnl!SeExports` at `0x14018ce75`
- `ntoskrnl!RtlCreateAcl` at `0x14018cddd`
- `ntoskrnl!RtlCreateAcl` at `0x14018cddd`
- `ntoskrnl!RtlGetAce` at `0x14018ce0a`
- `ntoskrnl!RtlGetAce` at `0x14018ce0a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018ce34`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018ce5e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018ce90`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018ce34`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018ce5e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14018ce90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018cea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018cec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018cea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018cec1`
- `ntoskrnl!ExAllocatePool2` at `0x14018cd1c`
- `ntoskrnl!ExAllocatePool2` at `0x14018cdb4`
- `ntoskrnl!ExAllocatePool2` at `0x14018cd1c`
- `ntoskrnl!ExAllocatePool2` at `0x14018cdb4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14018cd03`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14018cd03`

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
0x14018cc98  mov     [rsp-38h+arg_8], rbx
0x14018cc9d  push    rbp
0x14018cc9e  push    rsi
0x14018cc9f  push    rdi
0x14018cca0  push    r12
0x14018cca2  push    r13
0x14018cca4  push    r14
0x14018cca6  push    r15
0x14018cca8  mov     rbp, rsp
0x14018ccab  sub     rsp, 40h
0x14018ccaf  mov     rax, cs:__security_cookie
0x14018ccb6  xor     rax, rsp
0x14018ccb9  mov     [rbp+var_8], rax
0x14018ccbd  movzx   r14d, word ptr [rcx+2]
0x14018ccc2  xor     ebx, ebx
0x14018ccc4  mov     [rbp+Ace], rbx
0x14018ccc8  mov     r13, r9
0x14018cccb  mov     r12b, r8b
0x14018ccce  mov     [rbp+AccessMask], 10000000h
0x14018ccd5  mov     r15, rcx
0x14018ccd8  call    cs:__imp_IoGetFileObjectGenericMapping
0x14018ccdf  nop     dword ptr [rax+rax+00h]
0x14018cce4  lea     rcx, [rbp+AccessMask]; AccessMask
0x14018cce8  mov     dword ptr [rbp+IdentifierAuthority.Value], ebx
0x14018cceb  mov     rdx, rax; GenericMapping
0x14018ccee  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14018ccf4  call    cs:__imp_RtlMapGenericMask
0x14018ccfb  nop     dword ptr [rax+rax+00h]
0x14018cd00  lea     ecx, [rbx+2]; SubAuthorityCount
0x14018cd03  call    cs:__imp_RtlLengthRequiredSid
0x14018cd0a  nop     dword ptr [rax+rax+00h]
0x14018cd0f  mov     edx, eax
0x14018cd11  mov     ecx, 100h
0x14018cd16  mov     r8d, 7363444Eh
0x14018cd1c  call    cs:__imp_ExAllocatePool2
0x14018cd23  nop     dword ptr [rax+rax+00h]
0x14018cd28  mov     rsi, rax
0x14018cd2b  test    rax, rax
0x14018cd2e  jnz     short loc_14018CD3A
0x14018cd30  mov     eax, 0C000009Ah
0x14018cd35  jmp     loc_14018CECF
0x14018cd3a  mov     r8b, 2; SubAuthorityCount
0x14018cd3d  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14018cd41  mov     rcx, rsi; Sid
0x14018cd44  mov     rdi, rbx
0x14018cd47  call    cs:__imp_RtlInitializeSid
0x14018cd4e  nop     dword ptr [rax+rax+00h]
0x14018cd53  mov     ebx, eax
0x14018cd55  test    eax, eax
0x14018cd57  jnz     loc_14018CEA2
0x14018cd5d  mov     rcx, rsi; Sid
0x14018cd60  mov     dword ptr [rsi+8], 20h ; ' '
0x14018cd67  mov     dword ptr [rsi+0Ch], 22Ch
0x14018cd6e  call    cs:__imp_RtlLengthSid
0x14018cd75  nop     dword ptr [rax+rax+00h]
0x14018cd7a  lea     ebx, [r14+10h]
0x14018cd7e  add     ebx, eax
0x14018cd80  test    r12b, r12b
0x14018cd83  jz      short loc_14018CDA7
0x14018cd85  mov     rax, cs:__imp_SeExports
0x14018cd8c  mov     rcx, [rax]
0x14018cd8f  mov     rcx, [rcx+180h]; Sid
0x14018cd96  call    cs:__imp_RtlLengthSid
0x14018cd9d  nop     dword ptr [rax+rax+00h]
0x14018cda2  add     ebx, 10h
0x14018cda5  add     ebx, eax
0x14018cda7  mov     edx, ebx
0x14018cda9  mov     ecx, 100h
0x14018cdae  mov     r8d, 6163444Eh
0x14018cdb4  call    cs:__imp_ExAllocatePool2
0x14018cdbb  nop     dword ptr [rax+rax+00h]
0x14018cdc0  mov     rdi, rax
0x14018cdc3  test    rax, rax
0x14018cdc6  jnz     short loc_14018CDD2
0x14018cdc8  mov     ebx, 0C000009Ah
0x14018cdcd  jmp     loc_14018CEA2
0x14018cdd2  mov     r8d, 2; AclRevision
0x14018cdd8  mov     edx, ebx; AclLength
0x14018cdda  mov     rcx, rdi; Acl
0x14018cddd  call    cs:__imp_RtlCreateAcl
0x14018cde4  nop     dword ptr [rax+rax+00h]
0x14018cde9  mov     ebx, eax
0x14018cdeb  test    eax, eax
0x14018cded  js      loc_14018CEA2
0x14018cdf3  xor     r14d, r14d
0x14018cdf6  movzx   eax, word ptr [r15+4]
0x14018cdfb  cmp     r14d, eax
0x14018cdfe  jge     short loc_14018CE4B
0x14018ce00  lea     r8, [rbp+Ace]; Ace
0x14018ce04  mov     edx, r14d; AceIndex
0x14018ce07  mov     rcx, r15; Acl
0x14018ce0a  call    cs:__imp_RtlGetAce
0x14018ce11  nop     dword ptr [rax+rax+00h]
0x14018ce16  mov     ebx, eax
0x14018ce18  test    eax, eax
0x14018ce1a  js      loc_14018CEA2
0x14018ce20  mov     r8, [rbp+Ace]
0x14018ce24  mov     edx, 2; AceRevision
0x14018ce29  mov     rcx, rdi; Acl
0x14018ce2c  lea     r9, [r8+8]; Sid
0x14018ce30  mov     r8d, [r8+4]; AccessMask
0x14018ce34  call    cs:__imp_RtlAddAccessAllowedAce
0x14018ce3b  nop     dword ptr [rax+rax+00h]
0x14018ce40  mov     ebx, eax
0x14018ce42  test    eax, eax
0x14018ce44  js      short loc_14018CEA2
0x14018ce46  inc     r14d
0x14018ce49  jmp     short loc_14018CDF6
0x14018ce4b  mov     r8d, [rbp+AccessMask]; AccessMask
0x14018ce4f  mov     r14d, 2
0x14018ce55  mov     edx, r14d; AceRevision
0x14018ce58  mov     r9, rsi; Sid
0x14018ce5b  mov     rcx, rdi; Acl
0x14018ce5e  call    cs:__imp_RtlAddAccessAllowedAce
0x14018ce65  nop     dword ptr [rax+rax+00h]
0x14018ce6a  mov     ebx, eax
0x14018ce6c  test    eax, eax
0x14018ce6e  js      short loc_14018CEA2
0x14018ce70  test    r12b, r12b
0x14018ce73  jz      short loc_14018CE9E
0x14018ce75  mov     rax, cs:__imp_SeExports
0x14018ce7c  mov     edx, r14d; AceRevision
0x14018ce7f  mov     r8d, [rbp+AccessMask]; AccessMask
0x14018ce83  mov     rcx, rdi; Acl
0x14018ce86  mov     r9, [rax]
0x14018ce89  mov     r9, [r9+180h]; Sid
0x14018ce90  call    cs:__imp_RtlAddAccessAllowedAce
0x14018ce97  nop     dword ptr [rax+rax+00h]
0x14018ce9c  mov     ebx, eax
0x14018ce9e  mov     [r13+0], rdi
0x14018cea2  xor     edx, edx; Tag
0x14018cea4  mov     rcx, rsi; P
0x14018cea7  call    cs:__imp_ExFreePoolWithTag
0x14018ceae  nop     dword ptr [rax+rax+00h]
0x14018ceb3  test    ebx, ebx
0x14018ceb5  jns     short loc_14018CECD
0x14018ceb7  test    rdi, rdi
0x14018ceba  jz      short loc_14018CECD
0x14018cebc  xor     edx, edx; Tag
0x14018cebe  mov     rcx, rdi; P
0x14018cec1  call    cs:__imp_ExFreePoolWithTag
0x14018cec8  nop     dword ptr [rax+rax+00h]
0x14018cecd  mov     eax, ebx
0x14018cecf  mov     rcx, [rbp+var_8]
0x14018ced3  xor     rcx, rsp; StackCookie
0x14018ced6  call    __security_check_cookie
0x14018cedb  mov     rbx, [rsp+40h+arg_8]
0x14018cee3  add     rsp, 40h
0x14018cee7  pop     r15
0x14018cee9  pop     r14
0x14018ceeb  pop     r13
0x14018ceed  pop     r12
0x14018ceef  pop     rdi
0x14018cef0  pop     rsi
0x14018cef1  pop     rbp
0x14018cef2  retn
```
