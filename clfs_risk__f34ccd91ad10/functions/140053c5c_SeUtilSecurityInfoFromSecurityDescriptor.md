# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x140053c5c`
- end: `0x140053d55`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140052b84`
- `0x14005378c`

## callees

- `0x140053c5c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140053cf6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140053cf6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140053ca2`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140053ca2`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140053ccd`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140053ccd`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140053d1e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140053d1e`

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
0x140053c5c  mov     [rsp-18h+arg_0], rbx
0x140053c61  mov     [rsp-18h+arg_10], rsi
0x140053c66  push    rbp
0x140053c67  push    rdi
0x140053c68  push    r14
0x140053c6a  mov     rbp, rsp
0x140053c6d  sub     rsp, 30h
0x140053c71  xor     eax, eax
0x140053c73  mov     byte ptr [rdx], 0
0x140053c76  mov     [r8], eax
0x140053c79  mov     rsi, r8
0x140053c7c  mov     r14, rdx
0x140053c7f  mov     [rbp+OwnerDefaulted], 0
0x140053c83  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140053c87  mov     [rbp+SaclPresent], 0
0x140053c8b  lea     rdx, [rbp+Owner]; Owner
0x140053c8f  mov     [rbp+Owner], 0
0x140053c97  mov     rdi, rcx
0x140053c9a  mov     [rbp+Sacl], 0
0x140053ca2  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140053ca9  nop     dword ptr [rax+rax+00h]
0x140053cae  test    eax, eax
0x140053cb0  js      loc_140053D41
0x140053cb6  xor     ebx, ebx
0x140053cb8  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x140053cbc  cmp     [rbp+Owner], rbx
0x140053cc0  lea     rdx, [rbp+Owner]; Group
0x140053cc4  mov     rcx, rdi; SecurityDescriptor
0x140053cc7  lea     eax, [rbx+1]
0x140053cca  cmovnz  ebx, eax
0x140053ccd  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140053cd4  nop     dword ptr [rax+rax+00h]
0x140053cd9  test    eax, eax
0x140053cdb  js      short loc_140053D41
0x140053cdd  cmp     [rbp+Owner], 0
0x140053ce2  jz      short loc_140053CE7
0x140053ce4  or      ebx, 2
0x140053ce7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x140053ceb  mov     rcx, rdi; SecurityDescriptor
0x140053cee  lea     r8, [rbp+Sacl]; Sacl
0x140053cf2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140053cf6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140053cfd  nop     dword ptr [rax+rax+00h]
0x140053d02  test    eax, eax
0x140053d04  js      short loc_140053D41
0x140053d06  cmp     [rbp+SaclPresent], 0
0x140053d0a  jz      short loc_140053D0F
0x140053d0c  or      ebx, 8
0x140053d0f  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140053d13  mov     rcx, rdi; SecurityDescriptor
0x140053d16  lea     r8, [rbp+Sacl]; Dacl
0x140053d1a  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x140053d1e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140053d25  nop     dword ptr [rax+rax+00h]
0x140053d2a  test    eax, eax
0x140053d2c  js      short loc_140053D41
0x140053d2e  cmp     [rbp+SaclPresent], 0
0x140053d32  jz      short loc_140053D37
0x140053d34  or      ebx, 4
0x140053d37  mov     al, [rbp+OwnerDefaulted]
0x140053d3a  mov     [r14], al
0x140053d3d  xor     eax, eax
0x140053d3f  mov     [rsi], ebx
0x140053d41  mov     rbx, [rsp+30h+arg_0]
0x140053d46  mov     rsi, [rsp+30h+arg_10]
0x140053d4b  add     rsp, 30h
0x140053d4f  pop     r14
0x140053d51  pop     rdi
0x140053d52  pop     rbp
0x140053d53  retn
```
