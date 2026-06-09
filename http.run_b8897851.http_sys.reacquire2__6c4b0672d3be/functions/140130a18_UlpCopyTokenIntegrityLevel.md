# UlpCopyTokenIntegrityLevel

- ea: `0x140130a18`
- end: `0x140130b50`
- name: `UlpCopyTokenIntegrityLevel`
- size: `312`
- prototype: `__int64 __fastcall(HANDLE Handle, HANDLE)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140130448`

## callees

- `0x140130a18`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x140130b14`
- `ntoskrnl!ZwSetSecurityObject` at `0x140130b14`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140130a5d`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140130ac9`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140130a5d`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140130ac9`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140130aea`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140130aea`
- `ntoskrnl!ExAllocatePool3` at `0x140130a93`
- `ntoskrnl!ExAllocatePool3` at `0x140130a93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140130b2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140130b2e`

## pseudocode

```c
__int64 __fastcall UlpCopyTokenIntegrityLevel(HANDLE Handle, HANDLE a2)
{
  NTSTATUS SaclSecurityDescriptor; // ebx
  void *Pool3; // rdi
  ULONG Length; // [rsp+30h] [rbp-10h] BYREF
  PACL Sacl; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int8 SaclPresent; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int8 SaclDefaulted; // [rsp+78h] [rbp+38h] BYREF

  Length = 0;
  Sacl = 0;
  SaclDefaulted = 0;
  SaclPresent = 0;
  SaclSecurityDescriptor = ZwQuerySecurityObject(Handle, 0x10u, 0, 0, &Length);
  if ( SaclSecurityDescriptor == -1073741789 )
  {
    Pool3 = (void *)ExAllocatePool3(258, Length, 1146317909, UxLowPriorityPool, 1);
    if ( Pool3 )
    {
      SaclSecurityDescriptor = ZwQuerySecurityObject(Handle, 0x10u, Pool3, Length, &Length);
      if ( SaclSecurityDescriptor >= 0 )
      {
        SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(Pool3, &SaclPresent, &Sacl, &SaclDefaulted);
        if ( SaclSecurityDescriptor >= 0 )
        {
          if ( SaclPresent && Sacl )
            SaclSecurityDescriptor = ZwSetSecurityObject(a2, 0x10u, Pool3);
          else
            SaclSecurityDescriptor = -1073741811;
        }
      }
      ExFreePoolWithTag(Pool3, 0);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)SaclSecurityDescriptor;
}

```

## disassembly

```asm
0x140130a18  mov     [rsp-18h+arg_0], rbx
0x140130a1d  mov     [rsp-18h+arg_8], rsi
0x140130a22  push    rbp
0x140130a23  push    rdi
0x140130a24  push    r14
0x140130a26  mov     rbp, rsp
0x140130a29  sub     rsp, 40h
0x140130a2d  xor     r9d, r9d; Length
0x140130a30  mov     [rbp+Length], 0
0x140130a37  mov     r14, rdx
0x140130a3a  mov     [rbp+Sacl], 0
0x140130a42  lea     rax, [rbp+Length]
0x140130a46  mov     [rbp+SaclDefaulted], 0
0x140130a4a  xor     r8d, r8d; SecurityDescriptor
0x140130a4d  mov     [rbp+SaclPresent], 0
0x140130a51  lea     edx, [r9+10h]; SecurityInformation
0x140130a55  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x140130a5a  mov     rsi, rcx
0x140130a5d  call    cs:__imp_ZwQuerySecurityObject
0x140130a64  nop     dword ptr [rax+rax+00h]
0x140130a69  mov     ebx, eax
0x140130a6b  cmp     eax, 0C0000023h
0x140130a70  jnz     loc_140130B3A
0x140130a76  mov     edx, [rbp+Length]
0x140130a79  lea     r9, UxLowPriorityPool
0x140130a80  mov     ecx, 102h
0x140130a85  mov     dword ptr [rsp+40h+LengthNeeded], 1
0x140130a8d  mov     r8d, 44536C55h
0x140130a93  call    cs:__imp_ExAllocatePool3
0x140130a9a  nop     dword ptr [rax+rax+00h]
0x140130a9f  mov     rdi, rax
0x140130aa2  test    rax, rax
0x140130aa5  jnz     short loc_140130AB1
0x140130aa7  mov     ebx, 0C000009Ah
0x140130aac  jmp     loc_140130B3A
0x140130ab1  mov     r9d, [rbp+Length]; Length
0x140130ab5  lea     rax, [rbp+Length]
0x140130ab9  mov     r8, rdi; SecurityDescriptor
0x140130abc  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x140130ac1  mov     edx, 10h; SecurityInformation
0x140130ac6  mov     rcx, rsi; Handle
0x140130ac9  call    cs:__imp_ZwQuerySecurityObject
0x140130ad0  nop     dword ptr [rax+rax+00h]
0x140130ad5  mov     ebx, eax
0x140130ad7  test    eax, eax
0x140130ad9  js      short loc_140130B29
0x140130adb  lea     r9, [rbp+SaclDefaulted]; SaclDefaulted
0x140130adf  mov     rcx, rdi; SecurityDescriptor
0x140130ae2  lea     r8, [rbp+Sacl]; Sacl
0x140130ae6  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140130aea  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140130af1  nop     dword ptr [rax+rax+00h]
0x140130af6  mov     ebx, eax
0x140130af8  test    eax, eax
0x140130afa  js      short loc_140130B29
0x140130afc  cmp     [rbp+SaclPresent], 0
0x140130b00  jz      short loc_140130B24
0x140130b02  cmp     [rbp+Sacl], 0
0x140130b07  jz      short loc_140130B24
0x140130b09  mov     r8, rdi; SecurityDescriptor
0x140130b0c  mov     edx, 10h; SecurityInformation
0x140130b11  mov     rcx, r14; Handle
0x140130b14  call    cs:__imp_ZwSetSecurityObject
0x140130b1b  nop     dword ptr [rax+rax+00h]
0x140130b20  mov     ebx, eax
0x140130b22  jmp     short loc_140130B29
0x140130b24  mov     ebx, 0C000000Dh
0x140130b29  xor     edx, edx; Tag
0x140130b2b  mov     rcx, rdi; P
0x140130b2e  call    cs:__imp_ExFreePoolWithTag
0x140130b35  nop     dword ptr [rax+rax+00h]
0x140130b3a  mov     rsi, [rsp+40h+arg_8]
0x140130b3f  mov     eax, ebx
0x140130b41  mov     rbx, [rsp+40h+arg_0]
0x140130b46  add     rsp, 40h
0x140130b4a  pop     r14
0x140130b4c  pop     rdi
0x140130b4d  pop     rbp
0x140130b4e  retn
```
