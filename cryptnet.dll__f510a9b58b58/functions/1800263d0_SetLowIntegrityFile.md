# _SetLowIntegrityFile

- ea: `0x1800263d0`
- end: `0x18002643e`
- name: `_SetLowIntegrityFile`
- size: `110`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003170`
- `0x180006710`

## callees

- `0x1800263d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026426`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026426`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180026411`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180026411`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800263fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800263fc`

## pseudocode

```c
__int64 __fastcall SetLowIntegrityFile(LPCWSTR lpFileName)
{
  unsigned int v1; // ebx
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+40h] [rbp+18h] BYREF

  v1 = 0;
  pSecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"S:(ML;OICI;NW;;;LW)", 1u, &pSecurityDescriptor, 0) )
    v1 = SetFileSecurityW(lpFileName, 0x10u, pSecurityDescriptor);
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  return v1;
}

```

## disassembly

```asm
0x1800263d0  mov     rax, rsp
0x1800263d3  mov     [rax+8], rbx
0x1800263d7  mov     [rax+10h], rsi
0x1800263db  push    rdi
0x1800263dc  sub     rsp, 20h
0x1800263e0  xor     ebx, ebx
0x1800263e2  lea     r8, [rax+18h]; SecurityDescriptor
0x1800263e6  mov     rdi, rcx
0x1800263e9  mov     [rax+18h], rbx
0x1800263ed  xor     r9d, r9d; SecurityDescriptorSize
0x1800263f0  lea     rcx, StringSecurityDescriptor; "S:(ML;OICI;NW;;;LW)"
0x1800263f7  lea     esi, [rbx+1]
0x1800263fa  mov     edx, esi; StringSDRevision
0x1800263fc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180026402  test    eax, eax
0x180026404  jz      short loc_18002641C
0x180026406  mov     r8, [rsp+28h+pSecurityDescriptor]; pSecurityDescriptor
0x18002640b  lea     edx, [rbx+10h]; SecurityInformation
0x18002640e  mov     rcx, rdi; lpFileName
0x180026411  call    cs:__imp_SetFileSecurityW
0x180026417  test    eax, eax
0x180026419  cmovnz  ebx, esi
0x18002641c  mov     rcx, [rsp+28h+pSecurityDescriptor]; hMem
0x180026421  test    rcx, rcx
0x180026424  jz      short loc_18002642C
0x180026426  call    cs:__imp_LocalFree
0x18002642c  mov     rsi, [rsp+28h+arg_8]
0x180026431  mov     eax, ebx
0x180026433  mov     rbx, [rsp+28h+arg_0]
0x180026438  add     rsp, 20h
0x18002643c  pop     rdi
0x18002643d  retn
```
