# RFCOMMAddCapabilitySids

- ea: `0x140005964`
- end: `0x140005c32`
- name: `RFCOMMAddCapabilitySids`
- size: `718`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400060c4`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140005964`
- `0x140020380`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140005ab8`
- `ntoskrnl!ExAllocatePool2` at `0x140005b87`
- `ntoskrnl!ExAllocatePool2` at `0x140005ab8`
- `ntoskrnl!ExAllocatePool2` at `0x140005b87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005c00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005c16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005c00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005c16`
- `ntoskrnl!ObGetObjectSecurity` at `0x14000599a`
- `ntoskrnl!ObGetObjectSecurity` at `0x14000599a`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140005a44`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140005a44`
- `ntoskrnl!RtlLengthSid` at `0x140005a78`
- `ntoskrnl!RtlLengthSid` at `0x140005a8d`
- `ntoskrnl!RtlLengthSid` at `0x140005a78`
- `ntoskrnl!RtlLengthSid` at `0x140005a8d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140005b02`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140005b48`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140005b02`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140005b48`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140005ba7`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140005ba7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140005bbe`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140005bbe`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x140005bd5`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x140005bd5`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140005bea`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140005bea`

## pseudocode

```c
__int64 __fastcall RFCOMMAddCapabilitySids(void *a1)
{
  int v2; // edx
  NTSTATUS ObjectSecurity; // ebx
  int v4; // r9d
  __int16 v6; // bx
  __int16 v7; // ax
  __int64 v8; // rbx
  struct _ACL *Pool2; // rax
  struct _ACL *v10; // rsi
  void *v11; // rbx
  unsigned int v12; // edi
  void *v13; // rax
  PACL Dacl; // [rsp+30h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int8 DaclPresent; // [rsp+78h] [rbp+38h] BYREF

  MemoryAllocated = 0;
  SecurityDescriptor = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  Dacl = 0;
  ObjectSecurity = ObGetObjectSecurity(a1, &SecurityDescriptor, &MemoryAllocated);
  if ( ObjectSecurity < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)ObjectSecurity;
    v4 = 10;
LABEL_4:
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      15,
      v4,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      ObjectSecurity);
    return (unsigned int)ObjectSecurity;
  }
  if ( !SecurityDescriptor )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v2,
        15,
        11,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
    return 3221225687LL;
  }
  ObjectSecurity = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
  if ( ObjectSecurity < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)ObjectSecurity;
    v4 = 12;
    goto LABEL_4;
  }
  v6 = RtlLengthSid(qword_140022B48);
  v7 = RtlLengthSid(qword_140022B68);
  v8 = (unsigned __int16)(Dacl->AclSize + v6 + v7 + 16);
  Pool2 = (struct _ACL *)ExAllocatePool2(64, v8, 1111713362);
  v10 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, Dacl, Dacl->AclSize);
    v10->AclSize = v8;
    ObjectSecurity = RtlAddAccessAllowedAce(v10, 2u, 0xC0010000, qword_140022B68);
    if ( ObjectSecurity < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)ObjectSecurity;
      v4 = 13;
      goto LABEL_4;
    }
    ObjectSecurity = RtlAddAccessAllowedAce(v10, 2u, 0xC0010000, qword_140022B48);
    if ( ObjectSecurity < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)ObjectSecurity;
      v4 = 14;
      goto LABEL_4;
    }
    v13 = (void *)ExAllocatePool2(64, 40, 1111713362);
    v11 = v13;
    if ( v13 )
    {
      RtlCreateSecurityDescriptor(v13, 1u);
      RtlSetDaclSecurityDescriptor(v11, 1u, v10, 0);
      v12 = ObSetSecurityObjectByPointer(a1, 4, v11);
      goto LABEL_24;
    }
  }
  else
  {
    v11 = 0;
  }
  v12 = -1073741670;
LABEL_24:
  ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return v12;
}

```

## disassembly

```asm
0x140005964  mov     [rsp-18h+arg_0], rbx
0x140005969  push    rbp
0x14000596a  push    rsi
0x14000596b  push    rdi
0x14000596c  mov     rbp, rsp
0x14000596f  sub     rsp, 40h
0x140005973  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x140005977  mov     [rbp+MemoryAllocated], 0
0x14000597b  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000597f  mov     [rbp+SecurityDescriptor], 0
0x140005987  mov     rdi, rcx
0x14000598a  mov     [rbp+DaclPresent], 0
0x14000598e  mov     [rbp+DaclDefaulted], 0
0x140005992  mov     [rbp+Dacl], 0
0x14000599a  call    cs:__imp_ObGetObjectSecurity
0x1400059a1  nop     dword ptr [rax+rax+00h]
0x1400059a6  mov     ebx, eax
0x1400059a8  test    eax, eax
0x1400059aa  jns     short loc_1400059EF
0x1400059ac  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400059b3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400059ba  jz      short loc_1400059E8
0x1400059bc  mov     r9d, 0Ah
0x1400059c2  lea     rcx, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400059c9  mov     [rsp+40h+var_18], ebx
0x1400059cd  mov     [rsp+40h+var_20], rcx
0x1400059d2  mov     r8d, 0Fh
0x1400059d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059df  mov     rcx, [rcx+40h]
0x1400059e3  call    WPP_RECORDER_SF_d
0x1400059e8  mov     eax, ebx
0x1400059ea  jmp     loc_140005C24
0x1400059ef  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400059f3  test    rcx, rcx
0x1400059f6  jnz     short loc_140005A38
0x1400059f8  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400059ff  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140005a06  jz      short loc_140005A2E
0x140005a08  lea     rcx, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140005a0f  mov     r9d, 0Bh
0x140005a15  mov     [rsp+40h+var_20], rcx
0x140005a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a21  lea     r8d, [r9+4]
0x140005a25  mov     rcx, [rcx+40h]
0x140005a29  call    WPP_RECORDER_SF_
0x140005a2e  mov     eax, 0C00000D7h
0x140005a33  jmp     loc_140005C24
0x140005a38  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x140005a3c  lea     r8, [rbp+Dacl]; Dacl
0x140005a40  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x140005a44  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140005a4b  nop     dword ptr [rax+rax+00h]
0x140005a50  mov     ebx, eax
0x140005a52  test    eax, eax
0x140005a54  jns     short loc_140005A71
0x140005a56  lea     rcx, WPP_RECORDER_INITIALIZED
0x140005a5d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140005a64  jz      short loc_1400059E8
0x140005a66  mov     r9d, 0Ch
0x140005a6c  jmp     loc_1400059C2
0x140005a71  lea     rcx, qword_140022B48; Sid
0x140005a78  call    cs:__imp_RtlLengthSid
0x140005a7f  nop     dword ptr [rax+rax+00h]
0x140005a84  lea     rcx, qword_140022B68; Sid
0x140005a8b  mov     ebx, eax
0x140005a8d  call    cs:__imp_RtlLengthSid
0x140005a94  nop     dword ptr [rax+rax+00h]
0x140005a99  mov     rcx, [rbp+Dacl]
0x140005a9d  mov     r8d, 42436652h
0x140005aa3  add     ax, 10h
0x140005aa7  add     ax, bx
0x140005aaa  add     ax, [rcx+2]
0x140005aae  mov     ecx, 40h ; '@'
0x140005ab3  movzx   ebx, ax
0x140005ab6  mov     edx, ebx
0x140005ab8  call    cs:__imp_ExAllocatePool2
0x140005abf  nop     dword ptr [rax+rax+00h]
0x140005ac4  mov     rsi, rax
0x140005ac7  test    rax, rax
0x140005aca  jnz     short loc_140005AD8
0x140005acc  xor     ebx, ebx
0x140005ace  mov     edi, 0C000009Ah
0x140005ad3  jmp     loc_140005BE3
0x140005ad8  mov     rdx, [rbp+Dacl]; Src
0x140005adc  mov     rcx, rsi; void *
0x140005adf  movzx   r8d, word ptr [rdx+2]; Size
0x140005ae4  call    memmove
0x140005ae9  lea     r9, qword_140022B68; Sid
0x140005af0  mov     [rsi+2], bx
0x140005af4  mov     edx, 2; AceRevision
0x140005af9  mov     r8d, 0C0010000h; AccessMask
0x140005aff  mov     rcx, rsi; Acl
0x140005b02  call    cs:__imp_RtlAddAccessAllowedAce
0x140005b09  nop     dword ptr [rax+rax+00h]
0x140005b0e  mov     ebx, eax
0x140005b10  test    eax, eax
0x140005b12  jns     short loc_140005B33
0x140005b14  lea     rcx, WPP_RECORDER_INITIALIZED
0x140005b1b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140005b22  jz      loc_1400059E8
0x140005b28  mov     r9d, 0Dh
0x140005b2e  jmp     loc_1400059C2
0x140005b33  lea     r9, qword_140022B48; Sid
0x140005b3a  mov     edx, 2; AceRevision
0x140005b3f  mov     r8d, 0C0010000h; AccessMask
0x140005b45  mov     rcx, rsi; Acl
0x140005b48  call    cs:__imp_RtlAddAccessAllowedAce
0x140005b4f  nop     dword ptr [rax+rax+00h]
0x140005b54  mov     ebx, eax
0x140005b56  test    eax, eax
0x140005b58  jns     short loc_140005B79
0x140005b5a  lea     rcx, WPP_RECORDER_INITIALIZED
0x140005b61  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140005b68  jz      loc_1400059E8
0x140005b6e  mov     r9d, 0Eh
0x140005b74  jmp     loc_1400059C2
0x140005b79  mov     edx, 28h ; '('
0x140005b7e  mov     r8d, 42436652h
0x140005b84  lea     ecx, [rdx+18h]
0x140005b87  call    cs:__imp_ExAllocatePool2
0x140005b8e  nop     dword ptr [rax+rax+00h]
0x140005b93  mov     rbx, rax
0x140005b96  test    rax, rax
0x140005b99  jz      loc_140005ACE
0x140005b9f  mov     edx, 1; Revision
0x140005ba4  mov     rcx, rax; SecurityDescriptor
0x140005ba7  call    cs:__imp_RtlCreateSecurityDescriptor
0x140005bae  nop     dword ptr [rax+rax+00h]
0x140005bb3  xor     r9d, r9d; DaclDefaulted
0x140005bb6  mov     r8, rsi; Dacl
0x140005bb9  mov     dl, 1; DaclPresent
0x140005bbb  mov     rcx, rbx; SecurityDescriptor
0x140005bbe  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140005bc5  nop     dword ptr [rax+rax+00h]
0x140005bca  mov     r8, rbx
0x140005bcd  mov     edx, 4
0x140005bd2  mov     rcx, rdi
0x140005bd5  call    cs:__imp_ObSetSecurityObjectByPointer
0x140005bdc  nop     dword ptr [rax+rax+00h]
0x140005be1  mov     edi, eax
0x140005be3  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x140005be6  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140005bea  call    cs:__imp_ObReleaseObjectSecurity
0x140005bf1  nop     dword ptr [rax+rax+00h]
0x140005bf6  test    rbx, rbx
0x140005bf9  jz      short loc_140005C0C
0x140005bfb  xor     edx, edx; Tag
0x140005bfd  mov     rcx, rbx; P
0x140005c00  call    cs:__imp_ExFreePoolWithTag
0x140005c07  nop     dword ptr [rax+rax+00h]
0x140005c0c  test    rsi, rsi
0x140005c0f  jz      short loc_140005C22
0x140005c11  xor     edx, edx; Tag
0x140005c13  mov     rcx, rsi; P
0x140005c16  call    cs:__imp_ExFreePoolWithTag
0x140005c1d  nop     dword ptr [rax+rax+00h]
0x140005c22  mov     eax, edi
0x140005c24  mov     rbx, [rsp+40h+arg_0]
0x140005c29  add     rsp, 40h
0x140005c2d  pop     rdi
0x140005c2e  pop     rsi
0x140005c2f  pop     rbp
0x140005c30  retn
```
