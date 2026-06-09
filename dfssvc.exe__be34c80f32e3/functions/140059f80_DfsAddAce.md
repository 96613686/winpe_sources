# DfsAddAce

- ea: `0x140059f80`
- end: `0x14005a007`
- name: `DfsAddAce`
- size: `135`
- prototype: `__int64 __fastcall(LDAP *ld, PWSTR dn, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005a010`

## callees

- `0x140059f80`
- `0x14005a780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059feb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140059fdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140059fdd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140059faf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140059faf`

## pseudocode

```c
__int64 __fastcall DfsAddAce(LDAP *ld, PWSTR dn, LPCWSTR StringSecurityDescriptor)
{
  unsigned int v5; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp-18h] BYREF
  ULONG v8; // [rsp+68h] [rbp+20h] BYREF

  hMem = 0;
  v8 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &hMem, &v8) )
  {
    v5 = DfsStampSD(dn, ld);
    LocalFree(hMem);
  }
  else
  {
    return GetLastError();
  }
  return v5;
}

```

## disassembly

```asm
0x140059f80  mov     r11, rsp
0x140059f83  mov     [r11+8], rbx
0x140059f87  push    rdi
0x140059f88  sub     rsp, 40h
0x140059f8c  and     qword ptr [r11-18h], 0
0x140059f91  lea     r9, [r11+20h]; SecurityDescriptorSize
0x140059f95  and     [rsp+48h+arg_18], 0
0x140059f9a  mov     rax, r8
0x140059f9d  mov     rbx, rdx
0x140059fa0  lea     r8, [r11-18h]; SecurityDescriptor
0x140059fa4  mov     rdi, rcx
0x140059fa7  mov     edx, 1; StringSDRevision
0x140059fac  mov     rcx, rax; StringSecurityDescriptor
0x140059faf  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140059fb6  nop     dword ptr [rax+rax+00h]
0x140059fbb  cmp     eax, 1
0x140059fbe  jnz     short loc_140059FEB
0x140059fc0  mov     r9, [rsp+48h+hMem]
0x140059fc5  mov     rcx, rbx; dn
0x140059fc8  mov     edx, [rsp+48h+arg_18]
0x140059fcc  mov     [rsp+48h+ld], rdi; ld
0x140059fd1  call    DfsStampSD
0x140059fd6  mov     rcx, [rsp+48h+hMem]; hMem
0x140059fdb  mov     ebx, eax
0x140059fdd  call    cs:__imp_LocalFree
0x140059fe4  nop     dword ptr [rax+rax+00h]
0x140059fe9  jmp     short loc_140059FF9
0x140059feb  call    cs:__imp_GetLastError
0x140059ff2  nop     dword ptr [rax+rax+00h]
0x140059ff7  mov     ebx, eax
0x140059ff9  mov     eax, ebx
0x140059ffb  mov     rbx, [rsp+48h+arg_0]
0x14005a000  add     rsp, 40h
0x14005a004  pop     rdi
0x14005a005  retn
```
