# SecGetFileObjectMandatoryLabel

- ea: `0x140042998`
- end: `0x140042acd`
- name: `SecGetFileObjectMandatoryLabel`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b1e8`

## callees

- `0x140011650`
- `0x14002b1c4`
- `0x140042998`

## import_xrefs

- `ntoskrnl!RtlSubAuthoritySid` at `0x140042a80`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140042a80`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x140042a59`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x140042a6c`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x140042a59`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x140042a6c`
- `ntoskrnl!ObGetObjectSecurity` at `0x1400429dc`
- `ntoskrnl!ObGetObjectSecurity` at `0x1400429dc`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140042a9f`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140042a9f`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140042a02`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140042a02`

## pseudocode

```c
__int64 __fastcall SecGetFileObjectMandatoryLabel(void *a1, ULONG *a2)
{
  ULONG v2; // ebx
  NTSTATUS ObjectSecurity; // edi
  PACL v5; // rcx
  __int64 AceByType; // rax
  void *v7; // rsi
  PUCHAR v8; // rax
  PACL Sacl; // [rsp+20h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int8 SaclPresent; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+31h] [rbp-Fh] BYREF
  unsigned __int8 SaclDefaulted[2]; // [rsp+32h] [rbp-Eh] BYREF
  int v15; // [rsp+34h] [rbp-Ch] BYREF

  v2 = 0;
  SecurityDescriptor = 0;
  MemoryAllocated = 0;
  v15 = 0;
  SaclPresent = 0;
  SaclDefaulted[0] = 0;
  Sacl = 0;
  ObjectSecurity = ObGetObjectSecurity(a1, &SecurityDescriptor, &MemoryAllocated);
  if ( ObjectSecurity >= 0 )
  {
    ObjectSecurity = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, SaclDefaulted);
    if ( ObjectSecurity >= 0 )
    {
      if ( !SaclPresent )
        goto LABEL_13;
      v5 = Sacl;
      if ( !Sacl )
        goto LABEL_13;
      while ( 1 )
      {
        AceByType = SecRtlFindAceByType(v5, 17, &v15);
        if ( AceByType )
        {
          if ( (*(_BYTE *)(AceByType + 1) & 8) == 0 )
            break;
        }
        ++v15;
        if ( !AceByType )
          goto LABEL_13;
        v5 = Sacl;
      }
      v7 = (void *)(AceByType + 8);
      if ( AceByType != -8 )
      {
        if ( *RtlSubAuthorityCountSid((PSID)(AceByType + 8)) )
        {
          v8 = RtlSubAuthorityCountSid(v7);
          v2 = *RtlSubAuthoritySid(v7, (unsigned int)*v8 - 1);
        }
        *a2 = v2;
      }
      else
      {
LABEL_13:
        ObjectSecurity = -1073741637;
      }
    }
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
  }
  return (unsigned int)ObjectSecurity;
}

```

## disassembly

```asm
0x140042998  mov     [rsp-18h+arg_10], rbx
0x14004299d  mov     [rsp-18h+arg_18], rsi
0x1400429a2  push    rbp
0x1400429a3  push    rdi
0x1400429a4  push    r14
0x1400429a6  mov     rbp, rsp
0x1400429a9  sub     rsp, 40h
0x1400429ad  mov     rax, cs:__security_cookie
0x1400429b4  xor     rax, rsp
0x1400429b7  mov     [rbp+var_8], rax
0x1400429bb  xor     ebx, ebx
0x1400429bd  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x1400429c1  mov     r14, rdx
0x1400429c4  mov     [rbp+SecurityDescriptor], rbx
0x1400429c8  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400429cc  mov     [rbp+MemoryAllocated], bl
0x1400429cf  mov     [rbp+var_C], ebx
0x1400429d2  mov     [rbp+SaclPresent], bl
0x1400429d5  mov     [rbp+SaclDefaulted], bl
0x1400429d8  mov     [rbp+Sacl], rbx
0x1400429dc  call    cs:__imp_ObGetObjectSecurity
0x1400429e3  nop     dword ptr [rax+rax+00h]
0x1400429e8  mov     edi, eax
0x1400429ea  test    eax, eax
0x1400429ec  js      loc_140042AAB
0x1400429f2  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400429f6  lea     r9, [rbp+SaclDefaulted]; SaclDefaulted
0x1400429fa  lea     r8, [rbp+Sacl]; Sacl
0x1400429fe  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140042a02  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140042a09  nop     dword ptr [rax+rax+00h]
0x140042a0e  mov     edi, eax
0x140042a10  test    eax, eax
0x140042a12  js      loc_140042A98
0x140042a18  cmp     [rbp+SaclPresent], bl
0x140042a1b  jz      short loc_140042A93
0x140042a1d  mov     rcx, [rbp+Sacl]
0x140042a21  test    rcx, rcx
0x140042a24  jz      short loc_140042A93
0x140042a26  lea     r8, [rbp+var_C]
0x140042a2a  mov     edx, 11h
0x140042a2f  call    SecRtlFindAceByType
0x140042a34  test    rax, rax
0x140042a37  jz      short loc_140042A3F
0x140042a39  test    byte ptr [rax+1], 8
0x140042a3d  jz      short loc_140042A4D
0x140042a3f  inc     [rbp+var_C]
0x140042a42  test    rax, rax
0x140042a45  jz      short loc_140042A93
0x140042a47  mov     rcx, [rbp+Sacl]
0x140042a4b  jmp     short loc_140042A26
0x140042a4d  lea     rsi, [rax+8]
0x140042a51  test    rsi, rsi
0x140042a54  jz      short loc_140042A93
0x140042a56  mov     rcx, rsi; Sid
0x140042a59  call    cs:__imp_RtlSubAuthorityCountSid
0x140042a60  nop     dword ptr [rax+rax+00h]
0x140042a65  cmp     [rax], bl
0x140042a67  jz      short loc_140042A8E
0x140042a69  mov     rcx, rsi; Sid
0x140042a6c  call    cs:__imp_RtlSubAuthorityCountSid
0x140042a73  nop     dword ptr [rax+rax+00h]
0x140042a78  mov     rcx, rsi; Sid
0x140042a7b  movzx   edx, byte ptr [rax]
0x140042a7e  dec     edx; SubAuthority
0x140042a80  call    cs:__imp_RtlSubAuthoritySid
0x140042a87  nop     dword ptr [rax+rax+00h]
0x140042a8c  mov     ebx, [rax]
0x140042a8e  mov     [r14], ebx
0x140042a91  jmp     short loc_140042A98
0x140042a93  mov     edi, 0C00000BBh
0x140042a98  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x140042a9b  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140042a9f  call    cs:__imp_ObReleaseObjectSecurity
0x140042aa6  nop     dword ptr [rax+rax+00h]
0x140042aab  mov     eax, edi
0x140042aad  mov     rcx, [rbp+var_8]
0x140042ab1  xor     rcx, rsp; StackCookie
0x140042ab4  call    __security_check_cookie
0x140042ab9  mov     rbx, [rsp+40h+arg_10]
0x140042abe  mov     rsi, [rsp+40h+arg_18]
0x140042ac3  add     rsp, 40h
0x140042ac7  pop     r14
0x140042ac9  pop     rdi
0x140042aca  pop     rbp
0x140042acb  retn
```
