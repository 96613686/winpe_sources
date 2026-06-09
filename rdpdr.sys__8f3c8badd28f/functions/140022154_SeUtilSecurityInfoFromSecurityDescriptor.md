# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x140022154`
- end: `0x14002224d`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021094`
- `0x140021c84`

## callees

- `0x140022154`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140022216`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140022216`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400221ee`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400221ee`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14002219a`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14002219a`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1400221c5`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1400221c5`

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
0x140022154  mov     [rsp-18h+arg_0], rbx
0x140022159  mov     [rsp-18h+arg_10], rsi
0x14002215e  push    rbp
0x14002215f  push    rdi
0x140022160  push    r14
0x140022162  mov     rbp, rsp
0x140022165  sub     rsp, 30h
0x140022169  xor     eax, eax
0x14002216b  mov     byte ptr [rdx], 0
0x14002216e  mov     [r8], eax
0x140022171  mov     rsi, r8
0x140022174  mov     r14, rdx
0x140022177  mov     [rbp+OwnerDefaulted], 0
0x14002217b  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x14002217f  mov     [rbp+SaclPresent], 0
0x140022183  lea     rdx, [rbp+Owner]; Owner
0x140022187  mov     [rbp+Owner], 0
0x14002218f  mov     rdi, rcx
0x140022192  mov     [rbp+Sacl], 0
0x14002219a  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1400221a1  nop     dword ptr [rax+rax+00h]
0x1400221a6  test    eax, eax
0x1400221a8  js      loc_140022239
0x1400221ae  xor     ebx, ebx
0x1400221b0  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x1400221b4  cmp     [rbp+Owner], rbx
0x1400221b8  lea     rdx, [rbp+Owner]; Group
0x1400221bc  mov     rcx, rdi; SecurityDescriptor
0x1400221bf  lea     eax, [rbx+1]
0x1400221c2  cmovnz  ebx, eax
0x1400221c5  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1400221cc  nop     dword ptr [rax+rax+00h]
0x1400221d1  test    eax, eax
0x1400221d3  js      short loc_140022239
0x1400221d5  cmp     [rbp+Owner], 0
0x1400221da  jz      short loc_1400221DF
0x1400221dc  or      ebx, 2
0x1400221df  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x1400221e3  mov     rcx, rdi; SecurityDescriptor
0x1400221e6  lea     r8, [rbp+Sacl]; Sacl
0x1400221ea  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1400221ee  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400221f5  nop     dword ptr [rax+rax+00h]
0x1400221fa  test    eax, eax
0x1400221fc  js      short loc_140022239
0x1400221fe  cmp     [rbp+SaclPresent], 0
0x140022202  jz      short loc_140022207
0x140022204  or      ebx, 8
0x140022207  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x14002220b  mov     rcx, rdi; SecurityDescriptor
0x14002220e  lea     r8, [rbp+Sacl]; Dacl
0x140022212  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x140022216  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14002221d  nop     dword ptr [rax+rax+00h]
0x140022222  test    eax, eax
0x140022224  js      short loc_140022239
0x140022226  cmp     [rbp+SaclPresent], 0
0x14002222a  jz      short loc_14002222F
0x14002222c  or      ebx, 4
0x14002222f  mov     al, [rbp+OwnerDefaulted]
0x140022232  mov     [r14], al
0x140022235  xor     eax, eax
0x140022237  mov     [rsi], ebx
0x140022239  mov     rbx, [rsp+30h+arg_0]
0x14002223e  mov     rsi, [rsp+30h+arg_10]
0x140022243  add     rsp, 30h
0x140022247  pop     r14
0x140022249  pop     rdi
0x14002224a  pop     rbp
0x14002224b  retn
```
