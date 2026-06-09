# SeUtilSecurityInfoFromSecurityDescriptor

- ea: `0x14008420c`
- end: `0x140084305`
- name: `SeUtilSecurityInfoFromSecurityDescriptor`
- size: `249`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140083134`
- `0x140083d3c`

## callees

- `0x14008420c`

## import_xrefs

- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400842a6`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400842a6`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140084252`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140084252`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14008427d`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14008427d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400842ce`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1400842ce`

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
0x14008420c  mov     [rsp-18h+arg_0], rbx
0x140084211  mov     [rsp-18h+arg_10], rsi
0x140084216  push    rbp
0x140084217  push    rdi
0x140084218  push    r14
0x14008421a  mov     rbp, rsp
0x14008421d  sub     rsp, 30h
0x140084221  xor     eax, eax
0x140084223  mov     byte ptr [rdx], 0
0x140084226  mov     [r8], eax
0x140084229  mov     rsi, r8
0x14008422c  mov     r14, rdx
0x14008422f  mov     [rbp+OwnerDefaulted], 0
0x140084233  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x140084237  mov     [rbp+SaclPresent], 0
0x14008423b  lea     rdx, [rbp+Owner]; Owner
0x14008423f  mov     [rbp+Owner], 0
0x140084247  mov     rdi, rcx
0x14008424a  mov     [rbp+Sacl], 0
0x140084252  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140084259  nop     dword ptr [rax+rax+00h]
0x14008425e  test    eax, eax
0x140084260  js      loc_1400842F1
0x140084266  xor     ebx, ebx
0x140084268  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x14008426c  cmp     [rbp+Owner], rbx
0x140084270  lea     rdx, [rbp+Owner]; Group
0x140084274  mov     rcx, rdi; SecurityDescriptor
0x140084277  lea     eax, [rbx+1]
0x14008427a  cmovnz  ebx, eax
0x14008427d  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140084284  nop     dword ptr [rax+rax+00h]
0x140084289  test    eax, eax
0x14008428b  js      short loc_1400842F1
0x14008428d  cmp     [rbp+Owner], 0
0x140084292  jz      short loc_140084297
0x140084294  or      ebx, 2
0x140084297  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x14008429b  mov     rcx, rdi; SecurityDescriptor
0x14008429e  lea     r8, [rbp+Sacl]; Sacl
0x1400842a2  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1400842a6  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400842ad  nop     dword ptr [rax+rax+00h]
0x1400842b2  test    eax, eax
0x1400842b4  js      short loc_1400842F1
0x1400842b6  cmp     [rbp+SaclPresent], 0
0x1400842ba  jz      short loc_1400842BF
0x1400842bc  or      ebx, 8
0x1400842bf  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1400842c3  mov     rcx, rdi; SecurityDescriptor
0x1400842c6  lea     r8, [rbp+Sacl]; Dacl
0x1400842ca  lea     rdx, [rbp+SaclPresent]; DaclPresent
0x1400842ce  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400842d5  nop     dword ptr [rax+rax+00h]
0x1400842da  test    eax, eax
0x1400842dc  js      short loc_1400842F1
0x1400842de  cmp     [rbp+SaclPresent], 0
0x1400842e2  jz      short loc_1400842E7
0x1400842e4  or      ebx, 4
0x1400842e7  mov     al, [rbp+OwnerDefaulted]
0x1400842ea  mov     [r14], al
0x1400842ed  xor     eax, eax
0x1400842ef  mov     [rsi], ebx
0x1400842f1  mov     rbx, [rsp+30h+arg_0]
0x1400842f6  mov     rsi, [rsp+30h+arg_10]
0x1400842fb  add     rsp, 30h
0x1400842ff  pop     r14
0x140084301  pop     rdi
0x140084302  pop     rbp
0x140084303  retn
```
