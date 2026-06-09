# _anonymous_namespace_::GetSystemSecurityDescriptor

- ea: `0x1800454d0`
- end: `0x180045527`
- name: `_anonymous_namespace_::GetSystemSecurityDescriptor`
- size: `87`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045698`

## callees

- `0x18000b0d4`
- `0x1800454d0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800454f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800454f7`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetSystemSecurityDescriptor(PSECURITY_DESCRIPTOR *SecurityDescriptor)
{
  const char *v1; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ULONG SecurityDescriptorSize; // [rsp+30h] [rbp+8h] BYREF

  *SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GA;;;SY)",
         1u,
         SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    return 0;
  }
  else
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x85,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
             v1);
  }
}

```

## disassembly

```asm
0x1800454d0  sub     rsp, 28h
0x1800454d4  mov     qword ptr [rcx], 0
0x1800454db  lea     r9, [rsp+28h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800454e0  mov     r8, rcx; SecurityDescriptor
0x1800454e3  mov     [rsp+28h+SecurityDescriptorSize], 0
0x1800454eb  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x1800454f2  mov     edx, 1; StringSDRevision
0x1800454f7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800454fe  nop     dword ptr [rax+rax+00h]
0x180045503  test    eax, eax
0x180045505  jnz     short loc_18004551F
0x180045507  mov     rcx, [rsp+28h]; this
0x18004550c  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180045513  mov     edx, 85h; void *
0x180045518  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004551d  jmp     short loc_180045521
0x18004551f  xor     eax, eax
0x180045521  add     rsp, 28h
0x180045525  retn
```
