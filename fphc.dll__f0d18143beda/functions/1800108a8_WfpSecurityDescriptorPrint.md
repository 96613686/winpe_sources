# WfpSecurityDescriptorPrint

- ea: `0x1800108a8`
- end: `0x18001096e`
- name: `WfpSecurityDescriptorPrint`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f2d8`

## callees

- `0x1800108a8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001090b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001090b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010903`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010903`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800108dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800108dd`

## string_xrefs

- `0x180010936`: `<invalid access control list>`

## pseudocode

```c
HLOCAL __fastcall WfpSecurityDescriptorPrint(void (*a1)(__int64, const wchar_t *, ...), __int64 a2, void *a3)
{
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD v8; // eax
  bool v9; // zf
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(__int64, const wchar_t *); // rax
  const wchar_t *v12; // rdx
  HLOCAL hMem; // [rsp+58h] [rbp+20h] BYREF

  hMem = 0;
  if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(a3, 1u, 0xFu, (LPWSTR *)&hMem, 0) )
  {
    a1(a2, L"\n%s\n", hMem);
    return LocalFree(hMem);
  }
  v6 = GetLastError() - 87;
  if ( v6 )
  {
    v7 = v6 - 1218;
    if ( v7 )
    {
      v8 = v7 - 27;
      if ( v8 )
      {
        v9 = v8 == 4;
        v10 = a2;
        v11 = (__int64 (__fastcall *)(__int64, const wchar_t *))a1;
        if ( v9 )
          v12 = L"<invalid access control list>";
        else
          v12 = L"<invalid>";
        return (HLOCAL)v11(v10, v12);
      }
      v12 = L"<none mapped>";
    }
    else
    {
      v12 = L"<unknown SDDL revision>";
    }
  }
  else
  {
    v12 = L"<invalid parameter>";
  }
  v10 = a2;
  v11 = (__int64 (__fastcall *)(__int64, const wchar_t *))a1;
  return (HLOCAL)v11(v10, v12);
}

```

## disassembly

```asm
0x1800108a8  mov     r11, rsp
0x1800108ab  mov     [r11+8], rbx
0x1800108af  push    rdi
0x1800108b0  sub     rsp, 30h
0x1800108b4  mov     rax, r8
0x1800108b7  mov     qword ptr [r11+20h], 0
0x1800108bf  mov     rbx, rdx
0x1800108c2  mov     qword ptr [r11-18h], 0
0x1800108ca  mov     edx, 1; RequestedStringSDRevision
0x1800108cf  lea     r9, [r11+20h]; StringSecurityDescriptor
0x1800108d3  mov     rdi, rcx
0x1800108d6  mov     rcx, rax; SecurityDescriptor
0x1800108d9  lea     r8d, [rdx+0Eh]; SecurityInformation
0x1800108dd  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800108e3  test    eax, eax
0x1800108e5  jz      short loc_18001090B
0x1800108e7  mov     r8, [rsp+38h+hMem]
0x1800108ec  lea     rdx, aS_0; "\n%s\n"
0x1800108f3  mov     rcx, rbx
0x1800108f6  mov     rax, rdi
0x1800108f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108fe  mov     rcx, [rsp+38h+hMem]; hMem
0x180010903  call    cs:__imp_LocalFree
0x180010909  jmp     short loc_180010963
0x18001090b  call    cs:__imp_GetLastError
0x180010911  sub     eax, 57h ; 'W'
0x180010914  jz      short loc_180010951
0x180010916  sub     eax, 4C2h
0x18001091b  jz      short loc_180010948
0x18001091d  sub     eax, 1Bh
0x180010920  jz      short loc_18001093F
0x180010922  cmp     eax, 4
0x180010925  mov     rcx, rbx
0x180010928  mov     rax, rdi
0x18001092b  jz      short loc_180010936
0x18001092d  lea     rdx, aInvalid; "<invalid>"
0x180010934  jmp     short loc_18001095E
0x180010936  lea     rdx, aInvalidAccessC; "<invalid access control list>"
0x18001093d  jmp     short loc_18001095E
0x18001093f  lea     rdx, aNoneMapped; "<none mapped>"
0x180010946  jmp     short loc_180010958
0x180010948  lea     rdx, aUnknownSddlRev; "<unknown SDDL revision>"
0x18001094f  jmp     short loc_180010958
0x180010951  lea     rdx, aInvalidParamet_0; "<invalid parameter>"
0x180010958  mov     rcx, rbx
0x18001095b  mov     rax, rdi
0x18001095e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010963  mov     rbx, [rsp+38h+arg_0]
0x180010968  add     rsp, 30h
0x18001096c  pop     rdi
0x18001096d  retn
```
