# UlpCopyTokenIntegrityLevel

- ea: `0x1c012d9cc`
- end: `0x1c012daf1`
- name: `UlpCopyTokenIntegrityLevel`
- size: `293`
- prototype: `__int64 __fastcall(HANDLE Handle, HANDLE)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c012d4d0`

## callees

- `0x1c012d9cc`

## import_xrefs

- `ntoskrnl!ZwQuerySecurityObject` at `0x1c012da0b`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1c012da6a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1c012da0b`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1c012da6a`
- `ntoskrnl!ZwSetSecurityObject` at `0x1c012dab5`
- `ntoskrnl!ZwSetSecurityObject` at `0x1c012dab5`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1c012da8b`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1c012da8b`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c012da34`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c012da34`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c012dacf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c012dacf`

## pseudocode

```c
__int64 __fastcall UlpCopyTokenIntegrityLevel(HANDLE Handle, HANDLE a2)
{
  NTSTATUS SaclSecurityDescriptor; // ebx
  PVOID PoolWithTagPriority; // rdi
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
    PoolWithTagPriority = ExAllocatePoolWithTagPriority(PagedPool, Length, 0x44536C55u, LowPoolPriority);
    if ( PoolWithTagPriority )
    {
      SaclSecurityDescriptor = ZwQuerySecurityObject(Handle, 0x10u, PoolWithTagPriority, Length, &Length);
      if ( SaclSecurityDescriptor >= 0 )
      {
        SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(PoolWithTagPriority, &SaclPresent, &Sacl, &SaclDefaulted);
        if ( SaclSecurityDescriptor >= 0 )
        {
          if ( SaclPresent && Sacl )
            SaclSecurityDescriptor = ZwSetSecurityObject(a2, 0x10u, PoolWithTagPriority);
          else
            SaclSecurityDescriptor = -1073741811;
        }
      }
      ExFreePoolWithTag(PoolWithTagPriority, 0);
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
0x1c012d9cc  mov     [rsp-18h+arg_0], rbx
0x1c012d9d1  mov     [rsp-18h+arg_8], rsi
0x1c012d9d6  push    rbp
0x1c012d9d7  push    rdi
0x1c012d9d8  push    r14
0x1c012d9da  mov     rbp, rsp
0x1c012d9dd  sub     rsp, 40h
0x1c012d9e1  and     [rbp+Length], 0
0x1c012d9e5  lea     rax, [rbp+Length]
0x1c012d9e9  and     [rbp+Sacl], 0
0x1c012d9ee  xor     r9d, r9d; Length
0x1c012d9f1  mov     r14, rdx
0x1c012d9f4  mov     [rbp+SaclDefaulted], 0
0x1c012d9f8  xor     r8d, r8d; SecurityDescriptor
0x1c012d9fb  mov     [rbp+SaclPresent], 0
0x1c012d9ff  mov     rsi, rcx
0x1c012da02  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x1c012da07  lea     edx, [r9+10h]; SecurityInformation
0x1c012da0b  call    cs:__imp_ZwQuerySecurityObject
0x1c012da12  nop     dword ptr [rax+rax+00h]
0x1c012da17  mov     ebx, eax
0x1c012da19  cmp     eax, 0C0000023h
0x1c012da1e  jnz     loc_1C012DADB
0x1c012da24  mov     edx, [rbp+Length]; NumberOfBytes
0x1c012da27  xor     r9d, r9d; Priority
0x1c012da2a  mov     r8d, 44536C55h; Tag
0x1c012da30  lea     ecx, [r9+1]; PoolType
0x1c012da34  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c012da3b  nop     dword ptr [rax+rax+00h]
0x1c012da40  mov     rdi, rax
0x1c012da43  test    rax, rax
0x1c012da46  jnz     short loc_1C012DA52
0x1c012da48  mov     ebx, 0C000009Ah
0x1c012da4d  jmp     loc_1C012DADB
0x1c012da52  mov     r9d, [rbp+Length]; Length
0x1c012da56  lea     rax, [rbp+Length]
0x1c012da5a  mov     r8, rdi; SecurityDescriptor
0x1c012da5d  mov     [rsp+40h+LengthNeeded], rax; LengthNeeded
0x1c012da62  mov     edx, 10h; SecurityInformation
0x1c012da67  mov     rcx, rsi; Handle
0x1c012da6a  call    cs:__imp_ZwQuerySecurityObject
0x1c012da71  nop     dword ptr [rax+rax+00h]
0x1c012da76  mov     ebx, eax
0x1c012da78  test    eax, eax
0x1c012da7a  js      short loc_1C012DACA
0x1c012da7c  lea     r9, [rbp+SaclDefaulted]; SaclDefaulted
0x1c012da80  mov     rcx, rdi; SecurityDescriptor
0x1c012da83  lea     r8, [rbp+Sacl]; Sacl
0x1c012da87  lea     rdx, [rbp+SaclPresent]; SaclPresent
0x1c012da8b  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1c012da92  nop     dword ptr [rax+rax+00h]
0x1c012da97  mov     ebx, eax
0x1c012da99  test    eax, eax
0x1c012da9b  js      short loc_1C012DACA
0x1c012da9d  cmp     [rbp+SaclPresent], 0
0x1c012daa1  jz      short loc_1C012DAC5
0x1c012daa3  cmp     [rbp+Sacl], 0
0x1c012daa8  jz      short loc_1C012DAC5
0x1c012daaa  mov     r8, rdi; SecurityDescriptor
0x1c012daad  mov     edx, 10h; SecurityInformation
0x1c012dab2  mov     rcx, r14; Handle
0x1c012dab5  call    cs:__imp_ZwSetSecurityObject
0x1c012dabc  nop     dword ptr [rax+rax+00h]
0x1c012dac1  mov     ebx, eax
0x1c012dac3  jmp     short loc_1C012DACA
0x1c012dac5  mov     ebx, 0C000000Dh
0x1c012daca  xor     edx, edx; Tag
0x1c012dacc  mov     rcx, rdi; P
0x1c012dacf  call    cs:__imp_ExFreePoolWithTag
0x1c012dad6  nop     dword ptr [rax+rax+00h]
0x1c012dadb  mov     rsi, [rsp+40h+arg_8]
0x1c012dae0  mov     eax, ebx
0x1c012dae2  mov     rbx, [rsp+40h+arg_0]
0x1c012dae7  add     rsp, 40h
0x1c012daeb  pop     r14
0x1c012daed  pop     rdi
0x1c012daee  pop     rbp
0x1c012daef  retn
```
