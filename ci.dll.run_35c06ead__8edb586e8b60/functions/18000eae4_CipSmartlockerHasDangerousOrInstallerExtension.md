# CipSmartlockerHasDangerousOrInstallerExtension

- ea: `0x18000eae4`
- end: `0x18000ec20`
- name: `CipSmartlockerHasDangerousOrInstallerExtension`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180090654`
- `0x1800a8a90`

## callees

- `0x18000eae4`
- `0x180074b64`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000eb18`
- `ntoskrnl!ExAllocatePool2` at `0x18000eb18`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb69`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb99`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ec0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb69`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb99`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ec0f`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x18000eb4a`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x18000eb4a`

## pseudocode

```c
__int64 __fastcall CipSmartlockerHasDangerousOrInstallerExtension(__int64 a1)
{
  unsigned int v2; // esi
  unsigned int v3; // edi
  __int64 Pool2; // rbx
  int v5; // eax
  __int64 v7; // rax
  __int64 *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rsi
  unsigned int v11; // [rsp+60h] [rbp+8h] BYREF

  v11 = 0;
  if ( !a1 )
    return 0;
  v2 = 678;
  v3 = 1;
  while ( 1 )
  {
    Pool2 = ExAllocatePool2(258, v2, 1098149235);
    if ( !Pool2 )
      return 0;
    v5 = SeQuerySecurityAttributesToken(a1, L"`b", 1, Pool2, v2, &v11);
    if ( v5 != -1073741789 )
      break;
    if ( v2 >= v11 )
      goto LABEL_6;
    v2 = v11;
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
  }
  if ( v5 < 0 )
  {
LABEL_6:
    ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
    return 0;
  }
  if ( *(_DWORD *)(Pool2 + 4)
    && (v7 = *(_QWORD *)(Pool2 + 8), *(_WORD *)(v7 + 16) == 16)
    && (v8 = *(__int64 **)(v7 + 32), *((_DWORD *)v8 + 2) == 524) )
  {
    v9 = *v8;
    *(_WORD *)(v9 + 522) = 0;
    v10 = v9 + 4;
    if ( (*(_DWORD *)v9 & 0x80u) == 0 || !(unsigned int)CipCheckForExtensionAgainstList(v9 + 4, DangerousExtensions) )
      v3 = CipCheckForExtensionAgainstList(v10, &InstallerExtensions);
  }
  else
  {
    v3 = 0;
  }
  ExFreePoolWithTag((PVOID)Pool2, 0x41746D73u);
  return v3;
}

```

## disassembly

```asm
0x18000eae4  push    rbx
0x18000eae6  push    rbp
0x18000eae7  push    rsi
0x18000eae8  push    rdi
0x18000eae9  sub     rsp, 38h
0x18000eaed  mov     [rsp+58h+arg_0], 0
0x18000eaf5  mov     rbp, rcx
0x18000eaf8  test    rcx, rcx
0x18000eafb  jz      loc_18000EB83
0x18000eb01  mov     esi, 2A6h
0x18000eb06  mov     edi, 1
0x18000eb0b  mov     edx, esi
0x18000eb0d  mov     ecx, 102h
0x18000eb12  mov     r8d, 41746D73h
0x18000eb18  call    cs:__imp_ExAllocatePool2
0x18000eb1f  nop     dword ptr [rax+rax+00h]
0x18000eb24  mov     rbx, rax
0x18000eb27  test    rax, rax
0x18000eb2a  jz      short loc_18000EB75
0x18000eb2c  lea     rax, [rsp+58h+arg_0]
0x18000eb31  mov     r9, rbx
0x18000eb34  mov     [rsp+58h+var_30], rax
0x18000eb39  lea     rdx, aB; "`b"
0x18000eb40  mov     r8d, edi
0x18000eb43  mov     [rsp+58h+var_38], esi
0x18000eb47  mov     rcx, rbp
0x18000eb4a  call    cs:__imp_SeQuerySecurityAttributesToken
0x18000eb51  nop     dword ptr [rax+rax+00h]
0x18000eb56  cmp     eax, 0C0000023h
0x18000eb5b  jz      short loc_18000EB87
0x18000eb5d  test    eax, eax
0x18000eb5f  jns     short loc_18000EBAA
0x18000eb61  mov     edx, 41746D73h; Tag
0x18000eb66  mov     rcx, rbx; P
0x18000eb69  call    cs:__imp_ExFreePoolWithTag
0x18000eb70  nop     dword ptr [rax+rax+00h]
0x18000eb75  xor     edi, edi
0x18000eb77  mov     eax, edi
0x18000eb79  add     rsp, 38h
0x18000eb7d  pop     rdi
0x18000eb7e  pop     rsi
0x18000eb7f  pop     rbp
0x18000eb80  pop     rbx
0x18000eb81  retn
0x18000eb83  xor     eax, eax
0x18000eb85  jmp     short loc_18000EB79
0x18000eb87  cmp     esi, [rsp+58h+arg_0]
0x18000eb8b  jnb     short loc_18000EB61
0x18000eb8d  mov     esi, [rsp+58h+arg_0]
0x18000eb91  mov     edx, 41746D73h; Tag
0x18000eb96  mov     rcx, rbx; P
0x18000eb99  call    cs:__imp_ExFreePoolWithTag
0x18000eba0  nop     dword ptr [rax+rax+00h]
0x18000eba5  jmp     loc_18000EB0B
0x18000ebaa  xor     edx, edx
0x18000ebac  cmp     [rbx+4], edx
0x18000ebaf  jbe     short loc_18000EC05
0x18000ebb1  mov     rax, [rbx+8]
0x18000ebb5  cmp     word ptr [rax+10h], 10h
0x18000ebba  jnz     short loc_18000EC05
0x18000ebbc  mov     rcx, [rax+20h]
0x18000ebc0  cmp     dword ptr [rcx+8], 20Ch
0x18000ebc7  jnz     short loc_18000EC05
0x18000ebc9  mov     rcx, [rcx]
0x18000ebcc  xor     eax, eax
0x18000ebce  mov     [rcx+20Ah], ax
0x18000ebd5  lea     rsi, [rcx+4]
0x18000ebd9  mov     eax, [rcx]
0x18000ebdb  test    al, al
0x18000ebdd  jns     short loc_18000EBF2
0x18000ebdf  lea     rdx, DangerousExtensions
0x18000ebe6  mov     rcx, rsi
0x18000ebe9  call    CipCheckForExtensionAgainstList
0x18000ebee  test    eax, eax
0x18000ebf0  jnz     short loc_18000EC07
0x18000ebf2  lea     rdx, InstallerExtensions
0x18000ebf9  mov     rcx, rsi
0x18000ebfc  call    CipCheckForExtensionAgainstList
0x18000ec01  mov     edi, eax
0x18000ec03  jmp     short loc_18000EC07
0x18000ec05  mov     edi, edx
0x18000ec07  mov     edx, 41746D73h; Tag
0x18000ec0c  mov     rcx, rbx; P
0x18000ec0f  call    cs:__imp_ExFreePoolWithTag
0x18000ec16  nop     dword ptr [rax+rax+00h]
0x18000ec1b  jmp     loc_18000EB77
```
