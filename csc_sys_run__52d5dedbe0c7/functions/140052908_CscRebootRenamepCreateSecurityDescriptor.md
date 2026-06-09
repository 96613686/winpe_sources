# CscRebootRenamepCreateSecurityDescriptor

- ea: `0x140052908`
- end: `0x1400529ef`
- name: `CscRebootRenamepCreateSecurityDescriptor`
- size: `231`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140052e44`

## callees

- `0x14002f140`
- `0x140052908`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140052949`
- `ntoskrnl!ExAllocatePool2` at `0x140052949`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400529d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400529d7`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400529b8`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400529b8`
- `ntoskrnl!RtlLengthSid` at `0x14005292f`
- `ntoskrnl!RtlLengthSid` at `0x140052995`
- `ntoskrnl!RtlLengthSid` at `0x14005292f`
- `ntoskrnl!RtlLengthSid` at `0x140052995`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14005296c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14005296c`
- `ntoskrnl!SeExports` at `0x140052911`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140052981`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140052981`

## pseudocode

```c
__int64 __fastcall CscRebootRenamepCreateSecurityDescriptor(_QWORD *a1)
{
  PSID SeLocalSystemSid; // rbp
  ULONG v3; // eax
  __int64 v4; // r9
  char *Pool2; // rax
  char *v6; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  char *v8; // rbx
  ULONG v9; // eax

  *a1 = 0;
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  v3 = RtlLengthSid(SeLocalSystemSid);
  Pool2 = (char *)ExAllocatePool2(256, v3 + 40, 1383232323, v4);
  v6 = Pool2;
  if ( Pool2 )
  {
    SecurityDescriptor = RtlCreateSecurityDescriptor(Pool2, 1u);
    if ( SecurityDescriptor < 0
      || (v8 = &v6[RtlLengthSecurityDescriptor(v6)],
          v9 = RtlLengthSid(SeLocalSystemSid),
          memmove(v8, SeLocalSystemSid, v9),
          SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v6, v8, 0),
          SecurityDescriptor < 0) )
    {
      ExFreePoolWithTag(v6, 0x52727343u);
    }
    else
    {
      *a1 = v6;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x140052908  push    rbx
0x14005290a  push    rbp
0x14005290b  push    rsi
0x14005290c  push    rdi
0x14005290d  sub     rsp, 28h
0x140052911  mov     rax, cs:__imp_SeExports
0x140052918  mov     rsi, rcx
0x14005291b  mov     qword ptr [rcx], 0
0x140052922  mov     rdx, [rax]
0x140052925  mov     rbp, [rdx+108h]
0x14005292c  mov     rcx, rbp; Sid
0x14005292f  call    cs:__imp_RtlLengthSid
0x140052936  nop     dword ptr [rax+rax+00h]
0x14005293b  mov     ecx, 100h
0x140052940  mov     r8d, 52727343h
0x140052946  lea     edx, [rax+28h]
0x140052949  call    cs:__imp_ExAllocatePool2
0x140052950  nop     dword ptr [rax+rax+00h]
0x140052955  mov     rdi, rax
0x140052958  test    rax, rax
0x14005295b  jnz     short loc_140052964
0x14005295d  mov     ebx, 0C000009Ah
0x140052962  jmp     short loc_1400529E3
0x140052964  mov     edx, 1; Revision
0x140052969  mov     rcx, rdi; SecurityDescriptor
0x14005296c  call    cs:__imp_RtlCreateSecurityDescriptor
0x140052973  nop     dword ptr [rax+rax+00h]
0x140052978  mov     ebx, eax
0x14005297a  test    eax, eax
0x14005297c  js      short loc_1400529CF
0x14005297e  mov     rcx, rdi; SecurityDescriptor
0x140052981  call    cs:__imp_RtlLengthSecurityDescriptor
0x140052988  nop     dword ptr [rax+rax+00h]
0x14005298d  mov     ebx, eax
0x14005298f  mov     rcx, rbp; Sid
0x140052992  add     rbx, rdi
0x140052995  call    cs:__imp_RtlLengthSid
0x14005299c  nop     dword ptr [rax+rax+00h]
0x1400529a1  mov     r8d, eax; Size
0x1400529a4  mov     rdx, rbp; Src
0x1400529a7  mov     rcx, rbx; void *
0x1400529aa  call    memmove
0x1400529af  xor     r8d, r8d; OwnerDefaulted
0x1400529b2  mov     rdx, rbx; Owner
0x1400529b5  mov     rcx, rdi; SecurityDescriptor
0x1400529b8  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1400529bf  nop     dword ptr [rax+rax+00h]
0x1400529c4  mov     ebx, eax
0x1400529c6  test    eax, eax
0x1400529c8  js      short loc_1400529CF
0x1400529ca  mov     [rsi], rdi
0x1400529cd  jmp     short loc_1400529E3
0x1400529cf  mov     edx, 52727343h; Tag
0x1400529d4  mov     rcx, rdi; P
0x1400529d7  call    cs:__imp_ExFreePoolWithTag
0x1400529de  nop     dword ptr [rax+rax+00h]
0x1400529e3  mov     eax, ebx
0x1400529e5  add     rsp, 28h
0x1400529e9  pop     rdi
0x1400529ea  pop     rsi
0x1400529eb  pop     rbp
0x1400529ec  pop     rbx
0x1400529ed  retn
```
