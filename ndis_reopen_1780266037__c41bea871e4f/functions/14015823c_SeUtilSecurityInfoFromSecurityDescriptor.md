# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14015823c`
- end: `0x140158335`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140157164`
- `0x140157d6c`

## callees

- `0x14015823c`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1401582fe`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1401582fe`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140158282`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140158282`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1401582ad`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x1401582ad`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1401582d6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1401582d6`

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
0x14015823c  mov     [rsp-18h+arg_0], rbx
0x140158241  mov     [rsp-18h+arg_10], rsi
0x140158246  push    rbp
0x140158247  push    rdi
0x140158248  push    r14
0x14015824a  mov     rbp, rsp
0x14015824d  sub     rsp, 30h
0x140158251  xor     eax, eax
0x140158253  mov     byte ptr [rdx], 0
0x140158256  mov     [r8], eax
0x140158259  mov     rsi, r8
0x14015825c  mov     r14, rdx
0x14015825f  mov     [rbp+OwnerDefaulted], 0
0x140158263  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140158267  mov     [rbp+SaclPresent], 0
0x14015826b  lea     rdx, [rbp+Owner]; Owner
0x14015826f  mov     [rbp+Owner], 0
0x140158277  mov     rdi, rcx
0x14015827a  mov     [rbp+Sacl], 0
0x140158282  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140158289  nop     dword ptr [rax+rax+00h]
0x14015828e  test    eax, eax
0x140158290  js      loc_140158321
0x140158296  xor     ebx, ebx
0x140158298  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14015829c  cmp     [rbp+Owner], rbx
0x1401582a0  lea     rdx, [rbp+Owner]; Group
0x1401582a4  mov     rcx, rdi; SecurityDescriptor
0x1401582a7  lea     eax, [rbx+1]
0x1401582aa  cmovnz  ebx, eax
0x1401582ad  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1401582b4  nop     dword ptr [rax+rax+00h]
0x1401582b9  test    eax, eax
0x1401582bb  js      short loc_140158321
0x1401582bd  cmp     [rbp+Owner], 0
0x1401582c2  jz      short loc_1401582C7
0x1401582c4  or      ebx, 2
0x1401582c7  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x1401582cb  mov     rcx, rdi; SecurityDescriptor
0x1401582ce  lea     r8, [rbp+Sacl]; Sacl
0x1401582d2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1401582d6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1401582dd  nop     dword ptr [rax+rax+00h]
0x1401582e2  test    eax, eax
0x1401582e4  js      short loc_140158321
0x1401582e6  cmp     [rbp+SaclPresent], 0
0x1401582ea  jz      short loc_1401582EF
0x1401582ec  or      ebx, 8
0x1401582ef  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1401582f3  mov     rcx, rdi; SecurityDescriptor
0x1401582f6  lea     r8, [rbp+Sacl]; Dacl
0x1401582fa  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x1401582fe  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140158305  nop     dword ptr [rax+rax+00h]
0x14015830a  test    eax, eax
0x14015830c  js      short loc_140158321
0x14015830e  cmp     [rbp+SaclPresent], 0
0x140158312  jz      short loc_140158317
0x140158314  or      ebx, 4
0x140158317  mov     al, [rbp+OwnerDefaulted]
0x14015831a  mov     [r14], al
0x14015831d  xor     eax, eax
0x14015831f  mov     [rsi], ebx
0x140158321  mov     rbx, [rsp+30h+arg_0]
0x140158326  mov     rsi, [rsp+30h+arg_10]
0x14015832b  add     rsp, 30h
0x14015832f  pop     r14
0x140158331  pop     rdi
0x140158332  pop     rbp
0x140158333  retn
```
