# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x140018a1c`
- end: `0x140018b15`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017954`
- `0x14001854c`

## callees

- `0x140018a1c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140018ab6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140018ab6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140018a62`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140018a62`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140018a8d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140018a8d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140018ade`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140018ade`

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
0x140018a1c  mov     [rsp-18h+arg_0], rbx
0x140018a21  mov     [rsp-18h+arg_10], rsi
0x140018a26  push    rbp
0x140018a27  push    rdi
0x140018a28  push    r14
0x140018a2a  mov     rbp, rsp
0x140018a2d  sub     rsp, 30h
0x140018a31  xor     eax, eax
0x140018a33  mov     byte ptr [rdx], 0
0x140018a36  mov     [r8], eax
0x140018a39  mov     rsi, r8
0x140018a3c  mov     r14, rdx
0x140018a3f  mov     [rbp+OwnerDefaulted], 0
0x140018a43  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140018a47  mov     [rbp+SaclPresent], 0
0x140018a4b  lea     rdx, [rbp+Owner]; Owner
0x140018a4f  mov     [rbp+Owner], 0
0x140018a57  mov     rdi, rcx
0x140018a5a  mov     [rbp+Sacl], 0
0x140018a62  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140018a69  nop     dword ptr [rax+rax+00h]
0x140018a6e  test    eax, eax
0x140018a70  js      loc_140018B01
0x140018a76  xor     ebx, ebx
0x140018a78  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x140018a7c  cmp     [rbp+Owner], rbx
0x140018a80  lea     rdx, [rbp+Owner]; Group
0x140018a84  mov     rcx, rdi; SecurityDescriptor
0x140018a87  lea     eax, [rbx+1]
0x140018a8a  cmovnz  ebx, eax
0x140018a8d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140018a94  nop     dword ptr [rax+rax+00h]
0x140018a99  test    eax, eax
0x140018a9b  js      short loc_140018B01
0x140018a9d  cmp     [rbp+Owner], 0
0x140018aa2  jz      short loc_140018AA7
0x140018aa4  or      ebx, 2
0x140018aa7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x140018aab  mov     rcx, rdi; SecurityDescriptor
0x140018aae  lea     r8, [rbp+Sacl]; Sacl
0x140018ab2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140018ab6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140018abd  nop     dword ptr [rax+rax+00h]
0x140018ac2  test    eax, eax
0x140018ac4  js      short loc_140018B01
0x140018ac6  cmp     [rbp+SaclPresent], 0
0x140018aca  jz      short loc_140018ACF
0x140018acc  or      ebx, 8
0x140018acf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x140018ad3  mov     rcx, rdi; SecurityDescriptor
0x140018ad6  lea     r8, [rbp+Sacl]; Dacl
0x140018ada  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x140018ade  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140018ae5  nop     dword ptr [rax+rax+00h]
0x140018aea  test    eax, eax
0x140018aec  js      short loc_140018B01
0x140018aee  cmp     [rbp+SaclPresent], 0
0x140018af2  jz      short loc_140018AF7
0x140018af4  or      ebx, 4
0x140018af7  mov     al, [rbp+OwnerDefaulted]
0x140018afa  mov     [r14], al
0x140018afd  xor     eax, eax
0x140018aff  mov     [rsi], ebx
0x140018b01  mov     rbx, [rsp+30h+arg_0]
0x140018b06  mov     rsi, [rsp+30h+arg_10]
0x140018b0b  add     rsp, 30h
0x140018b0f  pop     r14
0x140018b11  pop     rdi
0x140018b12  pop     rbp
0x140018b13  retn
```
