# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x1400448ac`
- end: `0x1400449a5`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400437d4`
- `0x1400443dc`

## callees

- `0x1400448ac`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14004496e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14004496e`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14004491d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14004491d`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400448f2`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400448f2`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140044946`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140044946`

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
0x1400448ac  mov     [rsp-18h+arg_0], rbx
0x1400448b1  mov     [rsp-18h+arg_10], rsi
0x1400448b6  push    rbp
0x1400448b7  push    rdi
0x1400448b8  push    r14
0x1400448ba  mov     rbp, rsp
0x1400448bd  sub     rsp, 30h
0x1400448c1  xor     eax, eax
0x1400448c3  mov     byte ptr [rdx], 0
0x1400448c6  mov     [r8], eax
0x1400448c9  mov     rsi, r8
0x1400448cc  mov     r14, rdx
0x1400448cf  mov     [rbp+OwnerDefaulted], 0
0x1400448d3  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1400448d7  mov     [rbp+SaclPresent], 0
0x1400448db  lea     rdx, [rbp+Owner]; Owner
0x1400448df  mov     [rbp+Owner], 0
0x1400448e7  mov     rdi, rcx
0x1400448ea  mov     [rbp+Sacl], 0
0x1400448f2  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400448f9  nop     dword ptr [rax+rax+00h]
0x1400448fe  test    eax, eax
0x140044900  js      loc_140044991
0x140044906  xor     ebx, ebx
0x140044908  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14004490c  cmp     [rbp+Owner], rbx
0x140044910  lea     rdx, [rbp+Owner]; Group
0x140044914  mov     rcx, rdi; SecurityDescriptor
0x140044917  lea     eax, [rbx+1]
0x14004491a  cmovnz  ebx, eax
0x14004491d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140044924  nop     dword ptr [rax+rax+00h]
0x140044929  test    eax, eax
0x14004492b  js      short loc_140044991
0x14004492d  cmp     [rbp+Owner], 0
0x140044932  jz      short loc_140044937
0x140044934  or      ebx, 2
0x140044937  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14004493b  mov     rcx, rdi; SecurityDescriptor
0x14004493e  lea     r8, [rbp+Sacl]; Sacl
0x140044942  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140044946  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14004494d  nop     dword ptr [rax+rax+00h]
0x140044952  test    eax, eax
0x140044954  js      short loc_140044991
0x140044956  cmp     [rbp+SaclPresent], 0
0x14004495a  jz      short loc_14004495F
0x14004495c  or      ebx, 8
0x14004495f  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140044963  mov     rcx, rdi; SecurityDescriptor
0x140044966  lea     r8, [rbp+Sacl]; Dacl
0x14004496a  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x14004496e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140044975  nop     dword ptr [rax+rax+00h]
0x14004497a  test    eax, eax
0x14004497c  js      short loc_140044991
0x14004497e  cmp     [rbp+SaclPresent], 0
0x140044982  jz      short loc_140044987
0x140044984  or      ebx, 4
0x140044987  mov     al, [rbp+OwnerDefaulted]
0x14004498a  mov     [r14], al
0x14004498d  xor     eax, eax
0x14004498f  mov     [rsi], ebx
0x140044991  mov     rbx, [rsp+30h+arg_0]
0x140044996  mov     rsi, [rsp+30h+arg_10]
0x14004499b  add     rsp, 30h
0x14004499f  pop     r14
0x1400449a1  pop     rdi
0x1400449a2  pop     rbp
0x1400449a3  retn
```
