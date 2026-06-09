# SIPolicyIsSecurityDescriptorUserWriteable

- ea: `0x1800dff1c`
- end: `0x1800e002a`
- name: `SIPolicyIsSecurityDescriptorUserWriteable`
- size: `270`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a3d98`

## callees

- `0x1800dff1c`
- `0x1800e0030`

## import_xrefs

- `ntoskrnl!RtlGetAce` at `0x1800dffd1`
- `ntoskrnl!RtlGetAce` at `0x1800dffd1`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1800dff60`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1800dff60`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1800dff9d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1800dff9d`

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
0x1800dff1c  mov     [rsp-8+arg_0], rbx
0x1800dff21  mov     [rsp-8+arg_8], rdi
0x1800dff26  push    rbp
0x1800dff27  mov     rbp, rsp
0x1800dff2a  sub     rsp, 40h
0x1800dff2e  mov     rbx, rdx
0x1800dff31  mov     [rbp+Dacl], 0
0x1800dff39  lea     rdx, [rbp+Owner]; Owner
0x1800dff3d  mov     [rbp+Owner], 0
0x1800dff45  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1800dff49  mov     [rbp+Ace], 0
0x1800dff51  mov     rdi, rcx
0x1800dff54  mov     [rbp+DaclPresent], 0
0x1800dff58  mov     [rbp+DaclDefaulted], 0
0x1800dff5c  mov     [rbp+OwnerDefaulted], 0
0x1800dff60  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1800dff67  nop     dword ptr [rax+rax+00h]
0x1800dff6c  test    eax, eax
0x1800dff6e  js      loc_1800E0019
0x1800dff74  mov     rcx, [rbp+Owner]; Sid1
0x1800dff78  test    rcx, rcx
0x1800dff7b  jz      loc_1800E0014
0x1800dff81  call    SIPolicyIsSidKnownAdmin
0x1800dff86  test    al, al
0x1800dff88  jz      loc_1800E0014
0x1800dff8e  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x1800dff92  mov     rcx, rdi; SecurityDescriptor
0x1800dff95  lea     r8, [rbp+Dacl]; Dacl
0x1800dff99  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1800dff9d  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800dffa4  nop     dword ptr [rax+rax+00h]
0x1800dffa9  test    eax, eax
0x1800dffab  js      short loc_1800E0019
0x1800dffad  cmp     [rbp+DaclPresent], 0
0x1800dffb1  jnz     short loc_1800DFFB8
0x1800dffb3  mov     byte ptr [rbx], 0
0x1800dffb6  jmp     short loc_1800E0019
0x1800dffb8  mov     rcx, [rbp+Dacl]; Acl
0x1800dffbc  test    rcx, rcx
0x1800dffbf  jz      short loc_1800E0016
0x1800dffc1  xor     edi, edi
0x1800dffc3  movzx   eax, word ptr [rcx+4]
0x1800dffc7  cmp     edi, eax
0x1800dffc9  jnb     short loc_1800E000D
0x1800dffcb  lea     r8, [rbp+Ace]; Ace
0x1800dffcf  mov     edx, edi; AceIndex
0x1800dffd1  call    cs:__imp_RtlGetAce
0x1800dffd8  nop     dword ptr [rax+rax+00h]
0x1800dffdd  test    eax, eax
0x1800dffdf  js      short loc_1800E0019
0x1800dffe1  mov     rcx, [rbp+Ace]
0x1800dffe5  mov     al, [rcx]
0x1800dffe7  test    al, al
0x1800dffe9  jz      short loc_1800DFFEF
0x1800dffeb  cmp     al, 9
0x1800dffed  jnz     short loc_1800E0005
0x1800dffef  test    dword ptr [rcx+4], 116h
0x1800dfff6  jz      short loc_1800E0005
0x1800dfff8  add     rcx, 8; Sid1
0x1800dfffc  call    SIPolicyIsSidKnownAdmin
0x1800e0001  test    al, al
0x1800e0003  jz      short loc_1800E0014
0x1800e0005  mov     rcx, [rbp+Dacl]
0x1800e0009  inc     edi
0x1800e000b  jmp     short loc_1800DFFC3
0x1800e000d  mov     byte ptr [rbx], 0
0x1800e0010  xor     eax, eax
0x1800e0012  jmp     short loc_1800E0019
0x1800e0014  xor     eax, eax
0x1800e0016  mov     byte ptr [rbx], 1
0x1800e0019  mov     rbx, [rsp+40h+arg_0]
0x1800e001e  mov     rdi, [rsp+40h+arg_8]
0x1800e0023  add     rsp, 40h
0x1800e0027  pop     rbp
0x1800e0028  retn
```
