# UlpCopyTokenIntegrityLevel

- ea: `0x140130b08`
- end: `0x140130c40`
- name: `UlpCopyTokenIntegrityLevel`
- size: `312`
- prototype: `__int64 __fastcall(HANDLE Handle, HANDLE)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140130538`

## callees

- `0x140130b08`

## import_xrefs

- `ntoskrnl!ZwSetSecurityObject` at `0x140130c04`
- `ntoskrnl!ZwSetSecurityObject` at `0x140130c04`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140130b4d`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140130bb9`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140130b4d`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140130bb9`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140130bda`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x140130bda`
- `ntoskrnl!ExAllocatePool3` at `0x140130b83`
- `ntoskrnl!ExAllocatePool3` at `0x140130b83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140130c1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140130c1e`

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
0x140130b08  mov     [rsp-18h+arg_0], rbx
0x140130b0d  mov     [rsp-18h+arg_8], rsi
0x140130b12  push    rbp
0x140130b13  push    rdi
0x140130b14  push    r14
0x140130b16  mov     rbp, rsp
0x140130b19  sub     rsp, 40h
0x140130b1d  xor     r9d, r9d; Length
0x140130b20  mov     [rbp+Length], 0
0x140130b27  mov     r14, rdx
0x140130b2a  mov     [rbp+Sacl], 0
0x140130b32  lea     rax, [rbp+Length]
0x140130b36  mov     [rbp+SaclDefaulted], 0
0x140130b3a  xor     r8d, r8d; SecurityDescriptor
0x140130b3d  mov     [rbp+SaclPresent], 0
0x140130b41  lea     edx, [r9+10h]; SecurityInformation
0x140130b45  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x140130b4a  mov     rsi, rcx
0x140130b4d  call    cs:__imp_ZwQuerySecurityObject
0x140130b54  nop     dword ptr [rax+rax+00h]
0x140130b59  mov     ebx, eax
0x140130b5b  cmp     eax, 0C0000023h
0x140130b60  jnz     loc_140130C2A
0x140130b66  mov     edx, [rbp+Length]
0x140130b69  lea     r9, UxLowPriorityPool
0x140130b70  mov     ecx, 102h
0x140130b75  mov     dword ptr [rsp+40h+LengthNeeded], 1
0x140130b7d  mov     r8d, 44536C55h
0x140130b83  call    cs:__imp_ExAllocatePool3
0x140130b8a  nop     dword ptr [rax+rax+00h]
0x140130b8f  mov     rdi, rax
0x140130b92  test    rax, rax
0x140130b95  jnz     short loc_140130BA1
0x140130b97  mov     ebx, 0C000009Ah
0x140130b9c  jmp     loc_140130C2A
0x140130ba1  mov     r9d, [rbp+Length]; Length
0x140130ba5  lea     rax, [rbp+Length]
0x140130ba9  mov     r8, rdi; SecurityDescriptor
0x140130bac  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x140130bb1  mov     edx, 10h; SecurityInformation
0x140130bb6  mov     rcx, rsi; Handle
0x140130bb9  call    cs:__imp_ZwQuerySecurityObject
0x140130bc0  nop     dword ptr [rax+rax+00h]
0x140130bc5  mov     ebx, eax
0x140130bc7  test    eax, eax
0x140130bc9  js      short loc_140130C19
0x140130bcb  lea     r9, [rbp+SaclDefaulted]; SaclDefaulted
0x140130bcf  mov     rcx, rdi; SecurityDescriptor
0x140130bd2  lea     r8, [rbp+Sacl]; Sacl
0x140130bd6  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x140130bda  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x140130be1  nop     dword ptr [rax+rax+00h]
0x140130be6  mov     ebx, eax
0x140130be8  test    eax, eax
0x140130bea  js      short loc_140130C19
0x140130bec  cmp     [rbp+SaclPresent], 0
0x140130bf0  jz      short loc_140130C14
0x140130bf2  cmp     [rbp+Sacl], 0
0x140130bf7  jz      short loc_140130C14
0x140130bf9  mov     r8, rdi; SecurityDescriptor
0x140130bfc  mov     edx, 10h; SecurityInformation
0x140130c01  mov     rcx, r14; Handle
0x140130c04  call    cs:__imp_ZwSetSecurityObject
0x140130c0b  nop     dword ptr [rax+rax+00h]
0x140130c10  mov     ebx, eax
0x140130c12  jmp     short loc_140130C19
0x140130c14  mov     ebx, 0C000000Dh
0x140130c19  xor     edx, edx; Tag
0x140130c1b  mov     rcx, rdi; P
0x140130c1e  call    cs:__imp_ExFreePoolWithTag
0x140130c25  nop     dword ptr [rax+rax+00h]
0x140130c2a  mov     rsi, [rsp+40h+arg_8]
0x140130c2f  mov     eax, ebx
0x140130c31  mov     rbx, [rsp+40h+arg_0]
0x140130c36  add     rsp, 40h
0x140130c3a  pop     r14
0x140130c3c  pop     rdi
0x140130c3d  pop     rbp
0x140130c3e  retn
```
