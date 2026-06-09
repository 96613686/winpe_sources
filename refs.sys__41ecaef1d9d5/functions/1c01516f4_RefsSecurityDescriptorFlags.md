# RefsSecurityDescriptorFlags

- ea: `0x1c01516f4`
- end: `0x1c015178a`
- name: `RefsSecurityDescriptorFlags`
- size: `150`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c015152c`
- `0x1c01c4b24`

## callees

- `0x1c01516f4`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1c015171c`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x1c015171c`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x1c0151731`
- `ntoskrnl!RtlOwnerAcesPresent` at `0x1c0151731`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1c0151759`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1c0151759`
- `ntoskrnl!RtlFindAceByType` at `0x1c0181b83`
- `ntoskrnl!RtlFindAceByType` at `0x1c0181ba8`
- `ntoskrnl!RtlFindAceByType` at `0x1c0181b83`
- `ntoskrnl!RtlFindAceByType` at `0x1c0181ba8`

## pseudocode

```c
__int64 __fastcall RefsSecurityDescriptorFlags(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  unsigned int v1; // ebx
  unsigned __int8 DaclPresent; // [rsp+48h] [rbp+28h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+50h] [rbp+30h] BYREF
  PACL Dacl; // [rsp+58h] [rbp+38h] BYREF

  Dacl = 0;
  v1 = 0;
  DaclDefaulted = 0;
  DaclPresent = 0;
  RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
  if ( !DaclPresent || !(unsigned __int8)RtlOwnerAcesPresent(Dacl) )
    v1 = 1;
  DaclPresent = 0;
  RtlGetSaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
  if ( !DaclPresent || !RtlFindAceByType(Dacl, 17) )
    v1 |= 2u;
  if ( !DaclPresent || !RtlFindAceByType(Dacl, 21) )
    v1 |= 4u;
  return v1;
}

```

## disassembly

```asm
0x1c01516f4  push    rbp
0x1c01516f6  push    rbx
0x1c01516f7  push    rdi
0x1c01516f8  mov     rbp, rsp
0x1c01516fb  sub     rsp, 20h
0x1c01516ff  and     [rbp+Dacl], 0
0x1c0151704  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x1c0151708  xor     ebx, ebx
0x1c015170a  mov     [rbp+DaclDefaulted], 0
0x1c015170e  lea     r8, [rbp+Dacl]; Dacl
0x1c0151712  mov     [rbp+DaclPresent], bl
0x1c0151715  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1c0151719  mov     rdi, rcx
0x1c015171c  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1c0151723  nop     dword ptr [rax+rax+00h]
0x1c0151728  cmp     [rbp+DaclPresent], bl
0x1c015172b  jz      short loc_1C0151741
0x1c015172d  mov     rcx, [rbp+Dacl]
0x1c0151731  call    cs:__imp_RtlOwnerAcesPresent
0x1c0151738  nop     dword ptr [rax+rax+00h]
0x1c015173d  test    al, al
0x1c015173f  jnz     short loc_1C0151746
0x1c0151741  mov     ebx, 1
0x1c0151746  lea     r9, [rbp+DaclDefaulted]; SaclDefaulted
0x1c015174a  mov     [rbp+DaclPresent], 0
0x1c015174e  lea     r8, [rbp+Dacl]; Sacl
0x1c0151752  mov     rcx, rdi; SecurityDescriptor
0x1c0151755  lea     rdx, [rbp+DaclPresent]; SaclPresent
0x1c0151759  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1c0151760  nop     dword ptr [rax+rax+00h]
0x1c0151765  cmp     [rbp+DaclPresent], 0
0x1c0151769  jnz     loc_1C0181B78
0x1c015176f  or      ebx, 2
0x1c0151772  cmp     [rbp+DaclPresent], 0
0x1c0151776  jnz     loc_1C0181B9D
0x1c015177c  or      ebx, 4
0x1c015177f  mov     eax, ebx
0x1c0151781  add     rsp, 20h
0x1c0151785  pop     rdi
0x1c0151786  pop     rbx
0x1c0151787  pop     rbp
0x1c0151788  retn
0x1c0181b78  mov     rcx, [rbp+Dacl]
0x1c0181b7c  xor     r8d, r8d
0x1c0181b7f  lea     edx, [r8+11h]
0x1c0181b83  call    cs:__imp_RtlFindAceByType
0x1c0181b8a  nop     dword ptr [rax+rax+00h]
0x1c0181b8f  test    rax, rax
0x1c0181b92  jnz     loc_1C0151772
0x1c0181b98  jmp     loc_1C015176F
0x1c0181b9d  mov     rcx, [rbp+Dacl]
0x1c0181ba1  xor     r8d, r8d
0x1c0181ba4  lea     edx, [r8+15h]
0x1c0181ba8  call    cs:__imp_RtlFindAceByType
0x1c0181baf  nop     dword ptr [rax+rax+00h]
0x1c0181bb4  test    rax, rax
0x1c0181bb7  jnz     loc_1C015177F
0x1c0181bbd  jmp     loc_1C015177C
```
