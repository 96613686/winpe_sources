# CscCheckTokenMembership

- ea: `0x140086dd8`
- end: `0x140086ead`
- name: `CscCheckTokenMembership`
- size: `213`
- prototype: `char __fastcall(PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext, PSECURITY_DESCRIPTOR SecurityDescriptor, KPROCESSOR_MODE)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004e438`

## callees

- `0x1400190ec`
- `0x14002f010`
- `0x140086dd8`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x140086e4d`
- `ntoskrnl!SeAccessCheck` at `0x140086e4d`

## pseudocode

```c
char __fastcall CscCheckTokenMembership(
        PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        KPROCESSOR_MODE a3)
{
  int v3; // ebx
  unsigned int v5; // [rsp+50h] [rbp-28h] BYREF
  DWORD v6; // [rsp+54h] [rbp-24h] BYREF
  struct _GENERIC_MAPPING v7; // [rsp+58h] [rbp-20h] BYREF

  v7.GenericRead = 131073;
  v7.GenericAll = 2031617;
  v5 = 0;
  v7.GenericWrite = 0x20000;
  v7.GenericExecute = 0x20000;
  v6 = 0;
  v3 = SeAccessCheck(SecurityDescriptor, SubjectSecurityContext, 0, 1u, 0, 0, &v7, a3, &v6, (PNTSTATUS)&v5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids, v5, v3);
  return v3;
}

```

## disassembly

```asm
0x140086dd8  mov     r11, rsp
0x140086ddb  push    rbx
0x140086ddc  sub     rsp, 70h
0x140086de0  mov     rax, cs:__security_cookie
0x140086de7  xor     rax, rsp
0x140086dea  mov     [rsp+78h+var_10], rax
0x140086def  mov     rax, rdx
0x140086df2  mov     [rsp+78h+var_20], 20001h
0x140086dfa  xor     r9d, r9d
0x140086dfd  mov     [rsp+78h+var_14], 1F0001h
0x140086e05  mov     edx, 20000h
0x140086e0a  mov     [r11-28h], r9d
0x140086e0e  mov     [rsp+78h+var_1C], edx
0x140086e12  mov     [rsp+78h+var_18], edx
0x140086e16  lea     rdx, [r11-28h]
0x140086e1a  mov     [r11-30h], rdx
0x140086e1e  lea     rdx, [r11-24h]
0x140086e22  mov     [r11-38h], rdx
0x140086e26  lea     rdx, [r11-20h]
0x140086e2a  mov     [r11-40h], r8b
0x140086e2e  xor     r8d, r8d; SubjectContextLocked
0x140086e31  mov     [r11-48h], rdx
0x140086e35  mov     rdx, rcx; SubjectSecurityContext
0x140086e38  mov     [r11-50h], r9
0x140086e3c  mov     rcx, rax; SecurityDescriptor
0x140086e3f  mov     [r11-58h], r9d
0x140086e43  mov     [r11-24h], r9d
0x140086e47  mov     r9d, 1; DesiredAccess
0x140086e4d  call    cs:__imp_SeAccessCheck
0x140086e54  nop     dword ptr [rax+rax+00h]
0x140086e59  movzx   ebx, al
0x140086e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140086e63  lea     rax, WPP_GLOBAL_Control
0x140086e6a  cmp     rcx, rax
0x140086e6d  jz      short loc_140086E77
0x140086e6f  mov     edx, [rcx+2Ch]
0x140086e72  test    dl, 40h
0x140086e75  jnz     short loc_140086E8D
0x140086e77  mov     al, bl
0x140086e79  mov     rcx, [rsp+78h+var_10]
0x140086e7e  xor     rcx, rsp; StackCookie
0x140086e81  call    __security_check_cookie
0x140086e86  add     rsp, 70h
0x140086e8a  pop     rbx
0x140086e8b  retn
0x140086e8d  mov     r9d, [rsp+78h+var_28]
0x140086e92  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x140086e99  mov     rcx, [rcx+18h]
0x140086e9d  mov     edx, 1Bh
0x140086ea2  mov     [rsp+78h+var_58], ebx
0x140086ea6  call    WPP_SF_Dd
0x140086eab  jmp     short loc_140086E77
```
