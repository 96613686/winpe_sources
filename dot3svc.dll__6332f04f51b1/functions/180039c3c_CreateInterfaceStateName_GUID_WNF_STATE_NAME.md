# CreateInterfaceStateName(_GUID,_WNF_STATE_NAME *)

- ea: `0x180039c3c`
- end: `0x180039cf3`
- name: `?CreateInterfaceStateName@@YAJU_GUID@@PEAU_WNF_STATE_NAME@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct _WNF_STATE_NAME *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180039818`

## callees

- `0x180039c3c`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x180039cc6`
- `ntdll!NtCreateWnfStateName` at `0x180039cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039ce0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039ce0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180039c80`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180039c80`

## pseudocode

```c
__int64 __fastcall CreateInterfaceStateName(struct _GUID *a1, struct _WNF_STATE_NAME *a2)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  int WnfStateName; // eax
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+54h] [rbp+Ch]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+10h] BYREF

  v8 = HIDWORD(a1);
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( a2 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;;0x10003;;;SY)(A;;0x10002;;;S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142)(A;;0x10002;"
            ";;S-1-5-80-3787436395-2174616005-3003730137-1094982900-1570567328)(A;;1;;;IU)(A;;1;;;S-1-5-80-4155767994-387"
            "4329934-3800885181-2130851812-726865888)",
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize) )
    {
      v3 = 0;
      WnfStateName = NtCreateWnfStateName(a2, 3, 0, 0, 0, 4096, SecurityDescriptor);
      if ( WnfStateName < 0 )
        v3 = WnfStateName | 0x10000000;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v3;
}

```

## disassembly

```asm
0x180039c3c  mov     rax, rsp
0x180039c3f  mov     [rax+18h], rbx
0x180039c43  mov     [rax+8], rcx
0x180039c47  push    rdi
0x180039c48  sub     rsp, 40h
0x180039c4c  mov     qword ptr [rax+10h], 0
0x180039c54  mov     rdi, rdx
0x180039c57  mov     dword ptr [rax+8], 0
0x180039c5e  test    rdx, rdx
0x180039c61  jnz     short loc_180039C6A
0x180039c63  mov     ebx, 80004003h
0x180039c68  jmp     short loc_180039CE6
0x180039c6a  lea     r9, [rsp+48h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180039c6f  mov     edx, 1; StringSDRevision
0x180039c74  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180039c79  lea     rcx, StringSecurityDescriptor; "D:(A;;0x10003;;;SY)(A;;0x10002;;;S-1-5-"...
0x180039c80  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180039c86  test    eax, eax
0x180039c88  jnz     short loc_180039CA1
0x180039c8a  call    cs:__imp_GetLastError
0x180039c90  mov     ebx, eax
0x180039c92  test    eax, eax
0x180039c94  jle     short loc_180039CD6
0x180039c96  movzx   ebx, ax
0x180039c99  or      ebx, 80070000h
0x180039c9f  jmp     short loc_180039CD6
0x180039ca1  mov     rax, [rsp+48h+SecurityDescriptor]
0x180039ca6  xor     ebx, ebx
0x180039ca8  mov     [rsp+48h+var_18], rax
0x180039cad  xor     r9d, r9d
0x180039cb0  mov     [rsp+48h+var_20], 1000h
0x180039cb8  xor     r8d, r8d
0x180039cbb  mov     rcx, rdi
0x180039cbe  mov     [rsp+48h+var_28], rbx
0x180039cc3  lea     edx, [rbx+3]
0x180039cc6  call    cs:__imp_NtCreateWnfStateName
0x180039ccc  test    eax, eax
0x180039cce  jns     short loc_180039CD6
0x180039cd0  mov     ebx, eax
0x180039cd2  bts     ebx, 1Ch
0x180039cd6  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x180039cdb  test    rcx, rcx
0x180039cde  jz      short loc_180039CE6
0x180039ce0  call    cs:__imp_LocalFree
0x180039ce6  mov     eax, ebx
0x180039ce8  mov     rbx, [rsp+48h+arg_10]
0x180039ced  add     rsp, 40h
0x180039cf1  pop     rdi
0x180039cf2  retn
```
