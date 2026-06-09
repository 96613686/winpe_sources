# SIPolicyIsSecurityDescriptorUserWriteable

- ea: `0x1800dff0c`
- end: `0x1800e001a`
- name: `SIPolicyIsSecurityDescriptorUserWriteable`
- size: `270`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a38fc`

## callees

- `0x1800dff0c`
- `0x1800e0020`

## import_xrefs

- `ntoskrnl!RtlGetAce` at `0x1800dffc1`
- `ntoskrnl!RtlGetAce` at `0x1800dffc1`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1800dff50`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1800dff50`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1800dff8d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1800dff8d`

## pseudocode

```c
NTSTATUS __fastcall SIPolicyIsSecurityDescriptorUserWriteable(PSECURITY_DESCRIPTOR SecurityDescriptor, _BYTE *a2)
{
  NTSTATUS result; // eax
  PACL v5; // rcx
  ULONG i; // edi
  unsigned __int8 DaclDefaulted[8]; // [rsp+20h] [rbp-20h] BYREF
  PACL Dacl; // [rsp+28h] [rbp-18h] BYREF
  PSID Owner; // [rsp+30h] [rbp-10h] BYREF
  PVOID Ace; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int8 DaclPresent; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+68h] [rbp+28h] BYREF

  Dacl = 0;
  Owner = 0;
  Ace = 0;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  OwnerDefaulted = 0;
  result = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  if ( result < 0 )
    return result;
  if ( !Owner || !(unsigned __int8)SIPolicyIsSidKnownAdmin(Owner) )
  {
LABEL_17:
    result = 0;
LABEL_18:
    *a2 = 1;
    return result;
  }
  result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, DaclDefaulted);
  if ( result < 0 )
    return result;
  if ( !DaclPresent )
  {
    *a2 = 0;
    return result;
  }
  v5 = Dacl;
  if ( !Dacl )
    goto LABEL_18;
  for ( i = 0; i < v5->AceCount; ++i )
  {
    result = RtlGetAce(v5, i, &Ace);
    if ( result < 0 )
      return result;
    if ( (!*(_BYTE *)Ace || *(_BYTE *)Ace == 9)
      && (*((_DWORD *)Ace + 1) & 0x116) != 0
      && !(unsigned __int8)SIPolicyIsSidKnownAdmin((char *)Ace + 8) )
    {
      goto LABEL_17;
    }
    v5 = Dacl;
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800dff0c  mov     [rsp-8+arg_0], rbx
0x1800dff11  mov     [rsp-8+arg_8], rdi
0x1800dff16  push    rbp
0x1800dff17  mov     rbp, rsp
0x1800dff1a  sub     rsp, 40h
0x1800dff1e  mov     rbx, rdx
0x1800dff21  mov     [rbp+Dacl], 0
0x1800dff29  lea     rdx, [rbp+Owner]; Owner
0x1800dff2d  mov     [rbp+Owner], 0
0x1800dff35  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1800dff39  mov     [rbp+Ace], 0
0x1800dff41  mov     rdi, rcx
0x1800dff44  mov     [rbp+DaclPresent], 0
0x1800dff48  mov     [rbp+DaclDefaulted], 0
0x1800dff4c  mov     [rbp+OwnerDefaulted], 0
0x1800dff50  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1800dff57  nop     dword ptr [rax+rax+00h]
0x1800dff5c  test    eax, eax
0x1800dff5e  js      loc_1800E0009
0x1800dff64  mov     rcx, [rbp+Owner]; Sid1
0x1800dff68  test    rcx, rcx
0x1800dff6b  jz      loc_1800E0004
0x1800dff71  call    SIPolicyIsSidKnownAdmin
0x1800dff76  test    al, al
0x1800dff78  jz      loc_1800E0004
0x1800dff7e  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x1800dff82  mov     rcx, rdi; SecurityDescriptor
0x1800dff85  lea     r8, [rbp+Dacl]; Dacl
0x1800dff89  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1800dff8d  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800dff94  nop     dword ptr [rax+rax+00h]
0x1800dff99  test    eax, eax
0x1800dff9b  js      short loc_1800E0009
0x1800dff9d  cmp     [rbp+DaclPresent], 0
0x1800dffa1  jnz     short loc_1800DFFA8
0x1800dffa3  mov     byte ptr [rbx], 0
0x1800dffa6  jmp     short loc_1800E0009
0x1800dffa8  mov     rcx, [rbp+Dacl]; Acl
0x1800dffac  test    rcx, rcx
0x1800dffaf  jz      short loc_1800E0006
0x1800dffb1  xor     edi, edi
0x1800dffb3  movzx   eax, word ptr [rcx+4]
0x1800dffb7  cmp     edi, eax
0x1800dffb9  jnb     short loc_1800DFFFD
0x1800dffbb  lea     r8, [rbp+Ace]; Ace
0x1800dffbf  mov     edx, edi; AceIndex
0x1800dffc1  call    cs:__imp_RtlGetAce
0x1800dffc8  nop     dword ptr [rax+rax+00h]
0x1800dffcd  test    eax, eax
0x1800dffcf  js      short loc_1800E0009
0x1800dffd1  mov     rcx, [rbp+Ace]
0x1800dffd5  mov     al, [rcx]
0x1800dffd7  test    al, al
0x1800dffd9  jz      short loc_1800DFFDF
0x1800dffdb  cmp     al, 9
0x1800dffdd  jnz     short loc_1800DFFF5
0x1800dffdf  test    dword ptr [rcx+4], 116h
0x1800dffe6  jz      short loc_1800DFFF5
0x1800dffe8  add     rcx, 8; Sid1
0x1800dffec  call    SIPolicyIsSidKnownAdmin
0x1800dfff1  test    al, al
0x1800dfff3  jz      short loc_1800E0004
0x1800dfff5  mov     rcx, [rbp+Dacl]
0x1800dfff9  inc     edi
0x1800dfffb  jmp     short loc_1800DFFB3
0x1800dfffd  mov     byte ptr [rbx], 0
0x1800e0000  xor     eax, eax
0x1800e0002  jmp     short loc_1800E0009
0x1800e0004  xor     eax, eax
0x1800e0006  mov     byte ptr [rbx], 1
0x1800e0009  mov     rbx, [rsp+40h+arg_0]
0x1800e000e  mov     rdi, [rsp+40h+arg_8]
0x1800e0013  add     rsp, 40h
0x1800e0017  pop     rbp
0x1800e0018  retn
```
