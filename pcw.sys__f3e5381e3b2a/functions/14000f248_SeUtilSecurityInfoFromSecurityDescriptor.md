# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14000f248`
- end: `0x14000f341`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f4e4`
- `0x1400100fc`

## callees

- `0x14000f248`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000f2e2`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x14000f2e2`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000f28e`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14000f28e`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000f2b9`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14000f2b9`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000f30a`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14000f30a`

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
0x14000f248  mov     [rsp-18h+arg_0], rbx
0x14000f24d  mov     [rsp-18h+arg_10], rsi
0x14000f252  push    rbp
0x14000f253  push    rdi
0x14000f254  push    r14
0x14000f256  mov     rbp, rsp
0x14000f259  sub     rsp, 30h
0x14000f25d  xor     eax, eax
0x14000f25f  mov     byte ptr [rdx], 0
0x14000f262  mov     [r8], eax
0x14000f265  mov     rsi, r8
0x14000f268  mov     r14, rdx
0x14000f26b  mov     [rbp+OwnerDefaulted], 0
0x14000f26f  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x14000f273  mov     [rbp+SaclPresent], 0
0x14000f277  lea     rdx, [rbp+Owner]; Owner
0x14000f27b  mov     [rbp+Owner], 0
0x14000f283  mov     rdi, rcx
0x14000f286  mov     [rbp+Sacl], 0
0x14000f28e  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14000f295  nop     dword ptr [rax+rax+00h]
0x14000f29a  test    eax, eax
0x14000f29c  js      loc_14000F32D
0x14000f2a2  xor     ebx, ebx
0x14000f2a4  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14000f2a8  cmp     [rbp+Owner], rbx
0x14000f2ac  lea     rdx, [rbp+Owner]; Group
0x14000f2b0  mov     rcx, rdi; SecurityDescriptor
0x14000f2b3  lea     eax, [rbx+1]
0x14000f2b6  cmovnz  ebx, eax
0x14000f2b9  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14000f2c0  nop     dword ptr [rax+rax+00h]
0x14000f2c5  test    eax, eax
0x14000f2c7  js      short loc_14000F32D
0x14000f2c9  cmp     [rbp+Owner], 0
0x14000f2ce  jz      short loc_14000F2D3
0x14000f2d0  or      ebx, 2
0x14000f2d3  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14000f2d7  mov     rcx, rdi; SecurityDescriptor
0x14000f2da  lea     r8, [rbp+Sacl]; Sacl
0x14000f2de  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x14000f2e2  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14000f2e9  nop     dword ptr [rax+rax+00h]
0x14000f2ee  test    eax, eax
0x14000f2f0  js      short loc_14000F32D
0x14000f2f2  cmp     [rbp+SaclPresent], 0
0x14000f2f6  jz      short loc_14000F2FB
0x14000f2f8  or      ebx, 8
0x14000f2fb  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x14000f2ff  mov     rcx, rdi; SecurityDescriptor
0x14000f302  lea     r8, [rbp+Sacl]; Dacl
0x14000f306  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14000f30a  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14000f311  nop     dword ptr [rax+rax+00h]
0x14000f316  test    eax, eax
0x14000f318  js      short loc_14000F32D
0x14000f31a  cmp     [rbp+SaclPresent], 0
0x14000f31e  jz      short loc_14000F323
0x14000f320  or      ebx, 4
0x14000f323  mov     al, [rbp+OwnerDefaulted]
0x14000f326  mov     [r14], al
0x14000f329  xor     eax, eax
0x14000f32b  mov     [rsi], ebx
0x14000f32d  mov     rbx, [rsp+30h+arg_0]
0x14000f332  mov     rsi, [rsp+30h+arg_10]
0x14000f337  add     rsp, 30h
0x14000f33b  pop     r14
0x14000f33d  pop     rdi
0x14000f33e  pop     rbp
0x14000f33f  retn
```
