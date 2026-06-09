# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14000e4ac`
- end: `0x14000e5a5`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d3d4`
- `0x14000dfdc`

## callees

- `0x14000e4ac`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000e56e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000e56e`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000e546`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000e546`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000e4f2`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000e4f2`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000e51d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000e51d`

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
0x14000e4ac  mov     [rsp-18h+arg_0], rbx
0x14000e4b1  mov     [rsp-18h+arg_10], rsi
0x14000e4b6  push    rbp
0x14000e4b7  push    rdi
0x14000e4b8  push    r14
0x14000e4ba  mov     rbp, rsp
0x14000e4bd  sub     rsp, 30h
0x14000e4c1  xor     eax, eax
0x14000e4c3  mov     byte ptr [rdx], 0
0x14000e4c6  mov     [r8], eax
0x14000e4c9  mov     rsi, r8
0x14000e4cc  mov     r14, rdx
0x14000e4cf  mov     [rbp+OwnerDefaulted], 0
0x14000e4d3  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x14000e4d7  mov     [rbp+SaclPresent], 0
0x14000e4db  lea     rdx, [rbp+Owner]; Owner
0x14000e4df  mov     [rbp+Owner], 0
0x14000e4e7  mov     rdi, rcx
0x14000e4ea  mov     [rbp+Sacl], 0
0x14000e4f2  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14000e4f9  nop     dword ptr [rax+rax+00h]
0x14000e4fe  test    eax, eax
0x14000e500  js      loc_14000E591
0x14000e506  xor     ebx, ebx
0x14000e508  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14000e50c  cmp     [rbp+Owner], rbx
0x14000e510  lea     rdx, [rbp+Owner]; Group
0x14000e514  mov     rcx, rdi; SecurityDescriptor
0x14000e517  lea     eax, [rbx+1]
0x14000e51a  cmovnz  ebx, eax
0x14000e51d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14000e524  nop     dword ptr [rax+rax+00h]
0x14000e529  test    eax, eax
0x14000e52b  js      short loc_14000E591
0x14000e52d  cmp     [rbp+Owner], 0
0x14000e532  jz      short loc_14000E537
0x14000e534  or      ebx, 2
0x14000e537  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14000e53b  mov     rcx, rdi; SecurityDescriptor
0x14000e53e  lea     r8, [rbp+Sacl]; Sacl
0x14000e542  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x14000e546  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14000e54d  nop     dword ptr [rax+rax+00h]
0x14000e552  test    eax, eax
0x14000e554  js      short loc_14000E591
0x14000e556  cmp     [rbp+SaclPresent], 0
0x14000e55a  jz      short loc_14000E55F
0x14000e55c  or      ebx, 8
0x14000e55f  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x14000e563  mov     rcx, rdi; SecurityDescriptor
0x14000e566  lea     r8, [rbp+Sacl]; Dacl
0x14000e56a  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14000e56e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000e575  nop     dword ptr [rax+rax+00h]
0x14000e57a  test    eax, eax
0x14000e57c  js      short loc_14000E591
0x14000e57e  cmp     [rbp+SaclPresent], 0
0x14000e582  jz      short loc_14000E587
0x14000e584  or      ebx, 4
0x14000e587  mov     al, [rbp+OwnerDefaulted]
0x14000e58a  mov     [r14], al
0x14000e58d  xor     eax, eax
0x14000e58f  mov     [rsi], ebx
0x14000e591  mov     rbx, [rsp+30h+arg_0]
0x14000e596  mov     rsi, [rsp+30h+arg_10]
0x14000e59b  add     rsp, 30h
0x14000e59f  pop     r14
0x14000e5a1  pop     rdi
0x14000e5a2  pop     rbp
0x14000e5a3  retn
```
