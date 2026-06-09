# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14000a41c`
- end: `0x14000a515`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009344`
- `0x140009f4c`

## callees

- `0x14000a41c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000a4b6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000a4b6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000a462`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000a462`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000a48d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000a48d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000a4de`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000a4de`

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
0x14000a41c  mov     [rsp-18h+arg_0], rbx
0x14000a421  mov     [rsp-18h+arg_10], rsi
0x14000a426  push    rbp
0x14000a427  push    rdi
0x14000a428  push    r14
0x14000a42a  mov     rbp, rsp
0x14000a42d  sub     rsp, 30h
0x14000a431  xor     eax, eax
0x14000a433  mov     byte ptr [rdx], 0
0x14000a436  mov     [r8], eax
0x14000a439  mov     rsi, r8
0x14000a43c  mov     r14, rdx
0x14000a43f  mov     [rbp+OwnerDefaulted], 0
0x14000a443  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x14000a447  mov     [rbp+SaclPresent], 0
0x14000a44b  lea     rdx, [rbp+Owner]; Owner
0x14000a44f  mov     [rbp+Owner], 0
0x14000a457  mov     rdi, rcx
0x14000a45a  mov     [rbp+Sacl], 0
0x14000a462  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14000a469  nop     dword ptr [rax+rax+00h]
0x14000a46e  test    eax, eax
0x14000a470  js      loc_14000A501
0x14000a476  xor     ebx, ebx
0x14000a478  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14000a47c  cmp     [rbp+Owner], rbx
0x14000a480  lea     rdx, [rbp+Owner]; Group
0x14000a484  mov     rcx, rdi; SecurityDescriptor
0x14000a487  lea     eax, [rbx+1]
0x14000a48a  cmovnz  ebx, eax
0x14000a48d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14000a494  nop     dword ptr [rax+rax+00h]
0x14000a499  test    eax, eax
0x14000a49b  js      short loc_14000A501
0x14000a49d  cmp     [rbp+Owner], 0
0x14000a4a2  jz      short loc_14000A4A7
0x14000a4a4  or      ebx, 2
0x14000a4a7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14000a4ab  mov     rcx, rdi; SecurityDescriptor
0x14000a4ae  lea     r8, [rbp+Sacl]; Sacl
0x14000a4b2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x14000a4b6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14000a4bd  nop     dword ptr [rax+rax+00h]
0x14000a4c2  test    eax, eax
0x14000a4c4  js      short loc_14000A501
0x14000a4c6  cmp     [rbp+SaclPresent], 0
0x14000a4ca  jz      short loc_14000A4CF
0x14000a4cc  or      ebx, 8
0x14000a4cf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x14000a4d3  mov     rcx, rdi; SecurityDescriptor
0x14000a4d6  lea     r8, [rbp+Sacl]; Dacl
0x14000a4da  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14000a4de  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000a4e5  nop     dword ptr [rax+rax+00h]
0x14000a4ea  test    eax, eax
0x14000a4ec  js      short loc_14000A501
0x14000a4ee  cmp     [rbp+SaclPresent], 0
0x14000a4f2  jz      short loc_14000A4F7
0x14000a4f4  or      ebx, 4
0x14000a4f7  mov     al, [rbp+OwnerDefaulted]
0x14000a4fa  mov     [r14], al
0x14000a4fd  xor     eax, eax
0x14000a4ff  mov     [rsi], ebx
0x14000a501  mov     rbx, [rsp+30h+arg_0]
0x14000a506  mov     rsi, [rsp+30h+arg_10]
0x14000a50b  add     rsp, 30h
0x14000a50f  pop     r14
0x14000a511  pop     rdi
0x14000a512  pop     rbp
0x14000a513  retn
```
