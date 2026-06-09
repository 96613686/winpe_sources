# InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)

- ea: `0x18003afb0`
- end: `0x18003b037`
- name: `?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z`
- size: `135`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029258`
- `0x18002a990`
- `0x18003a734`
- `0x18003aa60`
- `0x1800a1d90`
- `0x1800e25fc`
- `0x1800e5a54`
- `0x1801a572c`

## callees

- `0x18003afb0`
- `0x18008daac`
- `0x1800af9b8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003afe6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003afe6`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18003afc8`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18003afc8`

## string_xrefs

- `0x18003aff5`: `onecoreuap\windows\moderncore\inputv2\utilities\inputsecuritydescriptor\lib\inputsecuritydescriptor.cpp`
- `0x18003b01e`: `onecoreuap\windows\moderncore\inputv2\utilities\inputsecuritydescriptor\lib\inputsecuritydescriptor.cpp`

## pseudocode

```c
int __fastcall InputSecurityDescriptor::QueryDescriptor(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  int TransientObjectSecurityDescriptor; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_BYTE *)(a1 + 8) = 1;
  TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(8, a3, a1);
  if ( TransientObjectSecurityDescriptor == -1073741772 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;GA;;;SY)(A;;0x001F0003;;;WD)(A;;0x001F0003;;;AC)(A;;0x001F0003;;;S-1-15-3-1024-1502825166-1963708345-2"
             "616377461-2562897074-4192028372-3968301570-1997628692-1435953622)",
            1u,
            (PSECURITY_DESCRIPTOR *)a1,
            0) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x46,
               (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\inputsecuritydescriptor\\lib\\inputsec"
                             "uritydescriptor.cpp",
               v7);
    *(_BYTE *)(a1 + 8) = 0;
    return 0;
  }
  if ( TransientObjectSecurityDescriptor >= 0 )
    return 0;
  return wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x4C,
           (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\inputsecuritydescriptor\\lib\\inputsecuritydescriptor.cpp",
           (const char *)(unsigned int)TransientObjectSecurityDescriptor,
           a5);
}

```

## disassembly

```asm
0x18003afb0  push    rbx
0x18003afb2  sub     rsp, 20h
0x18003afb6  mov     rdx, r8
0x18003afb9  mov     byte ptr [rcx+8], 1
0x18003afbd  mov     r8, rcx
0x18003afc0  mov     rbx, rcx
0x18003afc3  mov     ecx, 8
0x18003afc8  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18003afce  cmp     eax, 0C0000034h
0x18003afd3  jnz     short loc_18003B015
0x18003afd5  xor     r9d, r9d; SecurityDescriptorSize
0x18003afd8  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;0x001F0003;;;WD)(A;;0"...
0x18003afdf  mov     r8, rbx; SecurityDescriptor
0x18003afe2  lea     edx, [r9+1]; StringSDRevision
0x18003afe6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003afec  test    eax, eax
0x18003afee  jnz     short loc_18003B009
0x18003aff0  mov     rcx, [rsp+28h]; this
0x18003aff5  lea     r8, aOnecoreuapWind_121; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003affc  lea     edx, [rax+46h]; void *
0x18003afff  add     rsp, 20h
0x18003b003  pop     rbx
0x18003b004  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b009  mov     byte ptr [rbx+8], 0
0x18003b00d  xor     eax, eax
0x18003b00f  add     rsp, 20h
0x18003b013  pop     rbx
0x18003b014  retn
0x18003b015  test    eax, eax
0x18003b017  jns     short loc_18003B00D
0x18003b019  mov     rcx, [rsp+28h]; this
0x18003b01e  lea     r8, aOnecoreuapWind_121; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003b025  mov     r9d, eax; char *
0x18003b028  mov     edx, 4Ch ; 'L'; void *
0x18003b02d  add     rsp, 20h
0x18003b031  pop     rbx
0x18003b032  jmp     ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
```
