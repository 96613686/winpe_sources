# DfsGetObjStringSD

- ea: `0x140059608`
- end: `0x140059683`
- name: `DfsGetObjStringSD`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005a010`
- `0x14005a52c`

## callees

- `0x140059608`
- `0x14005968c`
- `0x1400599c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005965d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14005964d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14005964d`

## pseudocode

```c
__int64 __fastcall DfsGetObjStringSD(LDAP *a1, __int64 a2, LPWSTR *a3)
{
  DWORD DSObjSecDesc; // ebx
  int v6; // [rsp+68h] [rbp+20h] BYREF

  v6 = 0;
  DSObjSecDesc = DfsReadDSObjSecDesc(a1, (__int64)&v6);
  if ( !DSObjSecDesc )
  {
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(0, 1u, 4u, a3, 0) )
      DSObjSecDesc = GetLastError();
    DfsDeallocateSecurityData(0);
  }
  return DSObjSecDesc;
}

```

## disassembly

```asm
0x140059608  mov     r11, rsp
0x14005960b  mov     [r11+8], rbx
0x14005960f  push    rdi
0x140059610  sub     rsp, 40h
0x140059614  and     qword ptr [r11-18h], 0
0x140059619  lea     rax, [r11+20h]
0x14005961d  and     [rsp+48h+arg_18], 0
0x140059622  lea     r9, [r11-18h]
0x140059626  mov     [r11-28h], rax
0x14005962a  mov     rdi, r8
0x14005962d  call    DfsReadDSObjSecDesc
0x140059632  mov     ebx, eax
0x140059634  test    eax, eax
0x140059636  jnz     short loc_140059675
0x140059638  mov     rcx, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x14005963d  lea     edx, [rax+1]; RequestedStringSDRevision
0x140059640  and     [rsp+48h+var_28], 0
0x140059646  lea     r8d, [rax+4]; SecurityInformation
0x14005964a  mov     r9, rdi; StringSecurityDescriptor
0x14005964d  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x140059654  nop     dword ptr [rax+rax+00h]
0x140059659  test    eax, eax
0x14005965b  jnz     short loc_14005966B
0x14005965d  call    cs:__imp_GetLastError
0x140059664  nop     dword ptr [rax+rax+00h]
0x140059669  mov     ebx, eax
0x14005966b  mov     rcx, [rsp+48h+SecurityDescriptor]
0x140059670  call    DfsDeallocateSecurityData
0x140059675  mov     eax, ebx
0x140059677  mov     rbx, [rsp+48h+arg_0]
0x14005967c  add     rsp, 40h
0x140059680  pop     rdi
0x140059681  retn
```
