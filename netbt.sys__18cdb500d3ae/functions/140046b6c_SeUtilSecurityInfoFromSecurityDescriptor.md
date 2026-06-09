# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x140046b6c`
- end: `0x140046c65`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140045a94`
- `0x14004669c`

## callees

- `0x140046b6c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140046c06`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140046c06`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140046bb2`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140046bb2`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140046bdd`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140046bdd`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140046c2e`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140046c2e`

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
0x140046b6c  mov     [rsp-18h+arg_0], rbx
0x140046b71  mov     [rsp-18h+arg_10], rsi
0x140046b76  push    rbp
0x140046b77  push    rdi
0x140046b78  push    r14
0x140046b7a  mov     rbp, rsp
0x140046b7d  sub     rsp, 30h
0x140046b81  xor     eax, eax
0x140046b83  mov     byte ptr [rdx], 0
0x140046b86  mov     [r8], eax
0x140046b89  mov     rsi, r8
0x140046b8c  mov     r14, rdx
0x140046b8f  mov     [rbp+OwnerDefaulted], 0
0x140046b93  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140046b97  mov     [rbp+SaclPresent], 0
0x140046b9b  lea     rdx, [rbp+Owner]; Owner
0x140046b9f  mov     [rbp+Owner], 0
0x140046ba7  mov     rdi, rcx
0x140046baa  mov     [rbp+Sacl], 0
0x140046bb2  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140046bb9  nop     dword ptr [rax+rax+00h]
0x140046bbe  test    eax, eax
0x140046bc0  js      loc_140046C51
0x140046bc6  xor     ebx, ebx
0x140046bc8  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x140046bcc  cmp     [rbp+Owner], rbx
0x140046bd0  lea     rdx, [rbp+Owner]; Group
0x140046bd4  mov     rcx, rdi; SecurityDescriptor
0x140046bd7  lea     eax, [rbx+1]
0x140046bda  cmovnz  ebx, eax
0x140046bdd  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140046be4  nop     dword ptr [rax+rax+00h]
0x140046be9  test    eax, eax
0x140046beb  js      short loc_140046C51
0x140046bed  cmp     [rbp+Owner], 0
0x140046bf2  jz      short loc_140046BF7
0x140046bf4  or      ebx, 2
0x140046bf7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x140046bfb  mov     rcx, rdi; SecurityDescriptor
0x140046bfe  lea     r8, [rbp+Sacl]; Sacl
0x140046c02  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140046c06  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140046c0d  nop     dword ptr [rax+rax+00h]
0x140046c12  test    eax, eax
0x140046c14  js      short loc_140046C51
0x140046c16  cmp     [rbp+SaclPresent], 0
0x140046c1a  jz      short loc_140046C1F
0x140046c1c  or      ebx, 8
0x140046c1f  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140046c23  mov     rcx, rdi; SecurityDescriptor
0x140046c26  lea     r8, [rbp+Sacl]; Dacl
0x140046c2a  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x140046c2e  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140046c35  nop     dword ptr [rax+rax+00h]
0x140046c3a  test    eax, eax
0x140046c3c  js      short loc_140046C51
0x140046c3e  cmp     [rbp+SaclPresent], 0
0x140046c42  jz      short loc_140046C47
0x140046c44  or      ebx, 4
0x140046c47  mov     al, [rbp+OwnerDefaulted]
0x140046c4a  mov     [r14], al
0x140046c4d  xor     eax, eax
0x140046c4f  mov     [rsi], ebx
0x140046c51  mov     rbx, [rsp+30h+arg_0]
0x140046c56  mov     rsi, [rsp+30h+arg_10]
0x140046c5b  add     rsp, 30h
0x140046c5f  pop     r14
0x140046c61  pop     rdi
0x140046c62  pop     rbp
0x140046c63  retn
```
