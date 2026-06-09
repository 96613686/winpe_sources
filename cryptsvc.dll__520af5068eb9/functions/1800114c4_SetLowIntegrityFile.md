# _SetLowIntegrityFile

- ea: `0x1800114c4`
- end: `0x180011532`
- name: `_SetLowIntegrityFile`
- size: `110`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180006db0`
- `0x180009030`

## callees

- `0x1800114c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001151a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001151a`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180011505`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180011505`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800114f0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800114f0`

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
0x1800114c4  mov     rax, rsp
0x1800114c7  mov     [rax+8], rbx
0x1800114cb  mov     [rax+10h], rsi
0x1800114cf  push    rdi
0x1800114d0  sub     rsp, 20h
0x1800114d4  xor     ebx, ebx
0x1800114d6  lea     r8, [rax+18h]; SecurityDescriptor
0x1800114da  mov     rdi, rcx
0x1800114dd  mov     [rax+18h], rbx
0x1800114e1  xor     r9d, r9d; SecurityDescriptorSize
0x1800114e4  lea     rcx, StringSecurityDescriptor; "S:(ML;OICI;NW;;;LW)"
0x1800114eb  lea     esi, [rbx+1]
0x1800114ee  mov     edx, esi; StringSDRevision
0x1800114f0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800114f6  test    eax, eax
0x1800114f8  jz      short loc_180011510
0x1800114fa  mov     r8, [rsp+28h+pSecurityDescriptor]; pSecurityDescriptor
0x1800114ff  lea     edx, [rbx+10h]; SecurityInformation
0x180011502  mov     rcx, rdi; lpFileName
0x180011505  call    cs:__imp_SetFileSecurityW
0x18001150b  test    eax, eax
0x18001150d  cmovnz  ebx, esi
0x180011510  mov     rcx, [rsp+28h+pSecurityDescriptor]; hMem
0x180011515  test    rcx, rcx
0x180011518  jz      short loc_180011520
0x18001151a  call    cs:__imp_LocalFree
0x180011520  mov     rsi, [rsp+28h+arg_8]
0x180011525  mov     eax, ebx
0x180011527  mov     rbx, [rsp+28h+arg_0]
0x18001152c  add     rsp, 20h
0x180011530  pop     rdi
0x180011531  retn
```
