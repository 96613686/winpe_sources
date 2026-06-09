# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x1400121fc`
- end: `0x1400122f5`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011124`
- `0x140011d2c`

## callees

- `0x1400121fc`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140012296`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140012296`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140012242`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140012242`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14001226d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14001226d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400122be`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400122be`

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
0x1400121fc  mov     [rsp-18h+arg_0], rbx
0x140012201  mov     [rsp-18h+arg_10], rsi
0x140012206  push    rbp
0x140012207  push    rdi
0x140012208  push    r14
0x14001220a  mov     rbp, rsp
0x14001220d  sub     rsp, 30h
0x140012211  xor     eax, eax
0x140012213  mov     byte ptr [rdx], 0
0x140012216  mov     [r8], eax
0x140012219  mov     rsi, r8
0x14001221c  mov     r14, rdx
0x14001221f  mov     [rbp+OwnerDefaulted], 0
0x140012223  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140012227  mov     [rbp+SaclPresent], 0
0x14001222b  lea     rdx, [rbp+Owner]; Owner
0x14001222f  mov     [rbp+Owner], 0
0x140012237  mov     rdi, rcx
0x14001223a  mov     [rbp+Sacl], 0
0x140012242  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140012249  nop     dword ptr [rax+rax+00h]
0x14001224e  test    eax, eax
0x140012250  js      loc_1400122E1
0x140012256  xor     ebx, ebx
0x140012258  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14001225c  cmp     [rbp+Owner], rbx
0x140012260  lea     rdx, [rbp+Owner]; Group
0x140012264  mov     rcx, rdi; SecurityDescriptor
0x140012267  lea     eax, [rbx+1]
0x14001226a  cmovnz  ebx, eax
0x14001226d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140012274  nop     dword ptr [rax+rax+00h]
0x140012279  test    eax, eax
0x14001227b  js      short loc_1400122E1
0x14001227d  cmp     [rbp+Owner], 0
0x140012282  jz      short loc_140012287
0x140012284  or      ebx, 2
0x140012287  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14001228b  mov     rcx, rdi; SecurityDescriptor
0x14001228e  lea     r8, [rbp+Sacl]; Sacl
0x140012292  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140012296  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x14001229d  nop     dword ptr [rax+rax+00h]
0x1400122a2  test    eax, eax
0x1400122a4  js      short loc_1400122E1
0x1400122a6  cmp     [rbp+SaclPresent], 0
0x1400122aa  jz      short loc_1400122AF
0x1400122ac  or      ebx, 8
0x1400122af  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1400122b3  mov     rcx, rdi; SecurityDescriptor
0x1400122b6  lea     r8, [rbp+Sacl]; Dacl
0x1400122ba  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x1400122be  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400122c5  nop     dword ptr [rax+rax+00h]
0x1400122ca  test    eax, eax
0x1400122cc  js      short loc_1400122E1
0x1400122ce  cmp     [rbp+SaclPresent], 0
0x1400122d2  jz      short loc_1400122D7
0x1400122d4  or      ebx, 4
0x1400122d7  mov     al, [rbp+OwnerDefaulted]
0x1400122da  mov     [r14], al
0x1400122dd  xor     eax, eax
0x1400122df  mov     [rsi], ebx
0x1400122e1  mov     rbx, [rsp+30h+arg_0]
0x1400122e6  mov     rsi, [rsp+30h+arg_10]
0x1400122eb  add     rsp, 30h
0x1400122ef  pop     r14
0x1400122f1  pop     rdi
0x1400122f2  pop     rbp
0x1400122f3  retn
```
