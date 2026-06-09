# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x1400abb2c`
- end: `0x1400abc25`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400aaa54`
- `0x1400ab65c`

## callees

- `0x1400abb2c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400abbc6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400abbc6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400abb72`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1400abb72`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1400abb9d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1400abb9d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400abbee`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400abbee`

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
0x1400abb2c  mov     [rsp-18h+arg_0], rbx
0x1400abb31  mov     [rsp-18h+arg_10], rsi
0x1400abb36  push    rbp
0x1400abb37  push    rdi
0x1400abb38  push    r14
0x1400abb3a  mov     rbp, rsp
0x1400abb3d  sub     rsp, 30h
0x1400abb41  xor     eax, eax
0x1400abb43  mov     byte ptr [rdx], 0
0x1400abb46  mov     [r8], eax
0x1400abb49  mov     rsi, r8
0x1400abb4c  mov     r14, rdx
0x1400abb4f  mov     [rbp+OwnerDefaulted], 0
0x1400abb53  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1400abb57  mov     [rbp+SaclPresent], 0
0x1400abb5b  lea     rdx, [rbp+Owner]; Owner
0x1400abb5f  mov     [rbp+Owner], 0
0x1400abb67  mov     rdi, rcx
0x1400abb6a  mov     [rbp+Sacl], 0
0x1400abb72  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400abb79  nop     dword ptr [rax+rax+00h]
0x1400abb7e  test    eax, eax
0x1400abb80  js      loc_1400ABC11
0x1400abb86  xor     ebx, ebx
0x1400abb88  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x1400abb8c  cmp     [rbp+Owner], rbx
0x1400abb90  lea     rdx, [rbp+Owner]; Group
0x1400abb94  mov     rcx, rdi; SecurityDescriptor
0x1400abb97  lea     eax, [rbx+1]
0x1400abb9a  cmovnz  ebx, eax
0x1400abb9d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1400abba4  nop     dword ptr [rax+rax+00h]
0x1400abba9  test    eax, eax
0x1400abbab  js      short loc_1400ABC11
0x1400abbad  cmp     [rbp+Owner], 0
0x1400abbb2  jz      short loc_1400ABBB7
0x1400abbb4  or      ebx, 2
0x1400abbb7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x1400abbbb  mov     rcx, rdi; SecurityDescriptor
0x1400abbbe  lea     r8, [rbp+Sacl]; Sacl
0x1400abbc2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1400abbc6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400abbcd  nop     dword ptr [rax+rax+00h]
0x1400abbd2  test    eax, eax
0x1400abbd4  js      short loc_1400ABC11
0x1400abbd6  cmp     [rbp+SaclPresent], 0
0x1400abbda  jz      short loc_1400ABBDF
0x1400abbdc  or      ebx, 8
0x1400abbdf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1400abbe3  mov     rcx, rdi; SecurityDescriptor
0x1400abbe6  lea     r8, [rbp+Sacl]; Dacl
0x1400abbea  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x1400abbee  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400abbf5  nop     dword ptr [rax+rax+00h]
0x1400abbfa  test    eax, eax
0x1400abbfc  js      short loc_1400ABC11
0x1400abbfe  cmp     [rbp+SaclPresent], 0
0x1400abc02  jz      short loc_1400ABC07
0x1400abc04  or      ebx, 4
0x1400abc07  mov     al, [rbp+OwnerDefaulted]
0x1400abc0a  mov     [r14], al
0x1400abc0d  xor     eax, eax
0x1400abc0f  mov     [rsi], ebx
0x1400abc11  mov     rbx, [rsp+30h+arg_0]
0x1400abc16  mov     rsi, [rsp+30h+arg_10]
0x1400abc1b  add     rsp, 30h
0x1400abc1f  pop     r14
0x1400abc21  pop     rdi
0x1400abc22  pop     rbp
0x1400abc23  retn
```
