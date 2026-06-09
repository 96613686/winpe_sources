# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x140043f3c`
- end: `0x140044035`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140042e54`
- `0x140043a6c`

## callees

- `0x140043f3c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140043fd6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140043fd6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140043f82`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140043f82`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140043fad`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140043fad`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140043ffe`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140043ffe`

## pseudocode

```c
NTSTATUS __fastcall SeUtilSecurityInfoFromSecurityDescriptor(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        unsigned __int8 *a2,
        _DWORD *a3)
{
  NTSTATUS result; // eax
  int v7; // ebx
  PSID Owner; // [rsp+20h] [rbp-10h] BYREF
  PACL Sacl; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int8 SaclPresent; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  *a3 = 0;
  OwnerDefaulted = 0;
  SaclPresent = 0;
  Owner = 0;
  Sacl = 0;
  result = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  if ( result >= 0 )
  {
    v7 = Owner != 0;
    result = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
    if ( result >= 0 )
    {
      if ( Owner )
        v7 |= 2u;
      result = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &OwnerDefaulted);
      if ( result >= 0 )
      {
        if ( SaclPresent )
          v7 |= 8u;
        result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &OwnerDefaulted);
        if ( result >= 0 )
        {
          if ( SaclPresent )
            v7 |= 4u;
          *a2 = OwnerDefaulted;
          result = 0;
          *a3 = v7;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140043f3c  mov     [rsp-18h+arg_0], rbx
0x140043f41  mov     [rsp-18h+arg_10], rsi
0x140043f46  push    rbp
0x140043f47  push    rdi
0x140043f48  push    r14
0x140043f4a  mov     rbp, rsp
0x140043f4d  sub     rsp, 30h
0x140043f51  xor     eax, eax
0x140043f53  mov     byte ptr [rdx], 0
0x140043f56  mov     [r8], eax
0x140043f59  mov     rsi, r8
0x140043f5c  mov     r14, rdx
0x140043f5f  mov     [rbp+OwnerDefaulted], 0
0x140043f63  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140043f67  mov     [rbp+SaclPresent], 0
0x140043f6b  lea     rdx, [rbp+Owner]; Owner
0x140043f6f  mov     [rbp+Owner], 0
0x140043f77  mov     rdi, rcx
0x140043f7a  mov     [rbp+Sacl], 0
0x140043f82  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140043f89  nop     dword ptr [rax+rax+00h]
0x140043f8e  test    eax, eax
0x140043f90  js      loc_140044021
0x140043f96  xor     ebx, ebx
0x140043f98  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x140043f9c  cmp     [rbp+Owner], rbx
0x140043fa0  lea     rdx, [rbp+Owner]; Group
0x140043fa4  mov     rcx, rdi; SecurityDescriptor
0x140043fa7  lea     eax, [rbx+1]
0x140043faa  cmovnz  ebx, eax
0x140043fad  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140043fb4  nop     dword ptr [rax+rax+00h]
0x140043fb9  test    eax, eax
0x140043fbb  js      short loc_140044021
0x140043fbd  cmp     [rbp+Owner], 0
0x140043fc2  jz      short loc_140043FC7
0x140043fc4  or      ebx, 2
0x140043fc7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x140043fcb  mov     rcx, rdi; SecurityDescriptor
0x140043fce  lea     r8, [rbp+Sacl]; Sacl
0x140043fd2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140043fd6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140043fdd  nop     dword ptr [rax+rax+00h]
0x140043fe2  test    eax, eax
0x140043fe4  js      short loc_140044021
0x140043fe6  cmp     [rbp+SaclPresent], 0
0x140043fea  jz      short loc_140043FEF
0x140043fec  or      ebx, 8
0x140043fef  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140043ff3  mov     rcx, rdi; SecurityDescriptor
0x140043ff6  lea     r8, [rbp+Sacl]; Dacl
0x140043ffa  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x140043ffe  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140044005  nop     dword ptr [rax+rax+00h]
0x14004400a  test    eax, eax
0x14004400c  js      short loc_140044021
0x14004400e  cmp     [rbp+SaclPresent], 0
0x140044012  jz      short loc_140044017
0x140044014  or      ebx, 4
0x140044017  mov     al, [rbp+OwnerDefaulted]
0x14004401a  mov     [r14], al
0x14004401d  xor     eax, eax
0x14004401f  mov     [rsi], ebx
0x140044021  mov     rbx, [rsp+30h+arg_0]
0x140044026  mov     rsi, [rsp+30h+arg_10]
0x14004402b  add     rsp, 30h
0x14004402f  pop     r14
0x140044031  pop     rdi
0x140044032  pop     rbp
0x140044033  retn
```
