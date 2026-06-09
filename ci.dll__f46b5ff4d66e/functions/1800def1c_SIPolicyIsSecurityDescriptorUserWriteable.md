# SIPolicyIsSecurityDescriptorUserWriteable

- ea: `0x1800def1c`
- end: `0x1800df02a`
- name: `SIPolicyIsSecurityDescriptorUserWriteable`
- size: `270`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a22cc`

## callees

- `0x1800def1c`
- `0x1800df030`

## import_xrefs

- `ntoskrnl!RtlGetAce` at `0x1800defd1`
- `ntoskrnl!RtlGetAce` at `0x1800defd1`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1800def60`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x1800def60`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1800def9d`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1800def9d`

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
0x1800def1c  mov     [rsp-8+arg_0], rbx
0x1800def21  mov     [rsp-8+arg_8], rdi
0x1800def26  push    rbp
0x1800def27  mov     rbp, rsp
0x1800def2a  sub     rsp, 40h
0x1800def2e  mov     rbx, rdx
0x1800def31  mov     [rbp+Dacl], 0
0x1800def39  lea     rdx, [rbp+Owner]; Owner
0x1800def3d  mov     [rbp+Owner], 0
0x1800def45  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1800def49  mov     [rbp+Ace], 0
0x1800def51  mov     rdi, rcx
0x1800def54  mov     [rbp+DaclPresent], 0
0x1800def58  mov     [rbp+DaclDefaulted], 0
0x1800def5c  mov     [rbp+OwnerDefaulted], 0
0x1800def60  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1800def67  nop     dword ptr [rax+rax+00h]
0x1800def6c  test    eax, eax
0x1800def6e  js      loc_1800DF019
0x1800def74  mov     rcx, [rbp+Owner]; Sid1
0x1800def78  test    rcx, rcx
0x1800def7b  jz      loc_1800DF014
0x1800def81  call    SIPolicyIsSidKnownAdmin
0x1800def86  test    al, al
0x1800def88  jz      loc_1800DF014
0x1800def8e  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x1800def92  mov     rcx, rdi; SecurityDescriptor
0x1800def95  lea     r8, [rbp+Dacl]; Dacl
0x1800def99  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1800def9d  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800defa4  nop     dword ptr [rax+rax+00h]
0x1800defa9  test    eax, eax
0x1800defab  js      short loc_1800DF019
0x1800defad  cmp     [rbp+DaclPresent], 0
0x1800defb1  jnz     short loc_1800DEFB8
0x1800defb3  mov     byte ptr [rbx], 0
0x1800defb6  jmp     short loc_1800DF019
0x1800defb8  mov     rcx, [rbp+Dacl]; Acl
0x1800defbc  test    rcx, rcx
0x1800defbf  jz      short loc_1800DF016
0x1800defc1  xor     edi, edi
0x1800defc3  movzx   eax, word ptr [rcx+4]
0x1800defc7  cmp     edi, eax
0x1800defc9  jnb     short loc_1800DF00D
0x1800defcb  lea     r8, [rbp+Ace]; Ace
0x1800defcf  mov     edx, edi; AceIndex
0x1800defd1  call    cs:__imp_RtlGetAce
0x1800defd8  nop     dword ptr [rax+rax+00h]
0x1800defdd  test    eax, eax
0x1800defdf  js      short loc_1800DF019
0x1800defe1  mov     rcx, [rbp+Ace]
0x1800defe5  mov     al, [rcx]
0x1800defe7  test    al, al
0x1800defe9  jz      short loc_1800DEFEF
0x1800defeb  cmp     al, 9
0x1800defed  jnz     short loc_1800DF005
0x1800defef  test    dword ptr [rcx+4], 116h
0x1800deff6  jz      short loc_1800DF005
0x1800deff8  add     rcx, 8; Sid1
0x1800deffc  call    SIPolicyIsSidKnownAdmin
0x1800df001  test    al, al
0x1800df003  jz      short loc_1800DF014
0x1800df005  mov     rcx, [rbp+Dacl]
0x1800df009  inc     edi
0x1800df00b  jmp     short loc_1800DEFC3
0x1800df00d  mov     byte ptr [rbx], 0
0x1800df010  xor     eax, eax
0x1800df012  jmp     short loc_1800DF019
0x1800df014  xor     eax, eax
0x1800df016  mov     byte ptr [rbx], 1
0x1800df019  mov     rbx, [rsp+40h+arg_0]
0x1800df01e  mov     rdi, [rsp+40h+arg_8]
0x1800df023  add     rsp, 40h
0x1800df027  pop     rbp
0x1800df028  retn
```
