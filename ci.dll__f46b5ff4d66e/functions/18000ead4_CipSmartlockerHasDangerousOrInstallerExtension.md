# CipSmartlockerHasDangerousOrInstallerExtension

- ea: `0x18000ead4`
- end: `0x18000ec10`
- name: `CipSmartlockerHasDangerousOrInstallerExtension`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009dd98`
- `0x1800a82c0`

## callees

- `0x18000ead4`
- `0x1800735d4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000eb08`
- `ntoskrnl!ExAllocatePool2` at `0x18000eb08`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb59`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb89`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ebff`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb59`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000eb89`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ebff`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x18000eb3a`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x18000eb3a`

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
0x18000ead4  push    rbx
0x18000ead6  push    rbp
0x18000ead7  push    rsi
0x18000ead8  push    rdi
0x18000ead9  sub     rsp, 38h
0x18000eadd  mov     [rsp+58h+arg_0], 0
0x18000eae5  mov     rbp, rcx
0x18000eae8  test    rcx, rcx
0x18000eaeb  jz      loc_18000EB73
0x18000eaf1  mov     esi, 2A6h
0x18000eaf6  mov     edi, 1
0x18000eafb  mov     edx, esi
0x18000eafd  mov     ecx, 102h
0x18000eb02  mov     r8d, 41746D73h
0x18000eb08  call    cs:__imp_ExAllocatePool2
0x18000eb0f  nop     dword ptr [rax+rax+00h]
0x18000eb14  mov     rbx, rax
0x18000eb17  test    rax, rax
0x18000eb1a  jz      short loc_18000EB65
0x18000eb1c  lea     rax, [rsp+58h+arg_0]
0x18000eb21  mov     r9, rbx
0x18000eb24  mov     [rsp+58h+var_30], rax
0x18000eb29  lea     rdx, aB; "`b"
0x18000eb30  mov     r8d, edi
0x18000eb33  mov     [rsp+58h+var_38], esi
0x18000eb37  mov     rcx, rbp
0x18000eb3a  call    cs:__imp_SeQuerySecurityAttributesToken
0x18000eb41  nop     dword ptr [rax+rax+00h]
0x18000eb46  cmp     eax, 0C0000023h
0x18000eb4b  jz      short loc_18000EB77
0x18000eb4d  test    eax, eax
0x18000eb4f  jns     short loc_18000EB9A
0x18000eb51  mov     edx, 41746D73h; Tag
0x18000eb56  mov     rcx, rbx; P
0x18000eb59  call    cs:__imp_ExFreePoolWithTag
0x18000eb60  nop     dword ptr [rax+rax+00h]
0x18000eb65  xor     edi, edi
0x18000eb67  mov     eax, edi
0x18000eb69  add     rsp, 38h
0x18000eb6d  pop     rdi
0x18000eb6e  pop     rsi
0x18000eb6f  pop     rbp
0x18000eb70  pop     rbx
0x18000eb71  retn
0x18000eb73  xor     eax, eax
0x18000eb75  jmp     short loc_18000EB69
0x18000eb77  cmp     esi, [rsp+58h+arg_0]
0x18000eb7b  jnb     short loc_18000EB51
0x18000eb7d  mov     esi, [rsp+58h+arg_0]
0x18000eb81  mov     edx, 41746D73h; Tag
0x18000eb86  mov     rcx, rbx; P
0x18000eb89  call    cs:__imp_ExFreePoolWithTag
0x18000eb90  nop     dword ptr [rax+rax+00h]
0x18000eb95  jmp     loc_18000EAFB
0x18000eb9a  xor     edx, edx
0x18000eb9c  cmp     [rbx+4], edx
0x18000eb9f  jbe     short loc_18000EBF5
0x18000eba1  mov     rax, [rbx+8]
0x18000eba5  cmp     word ptr [rax+10h], 10h
0x18000ebaa  jnz     short loc_18000EBF5
0x18000ebac  mov     rcx, [rax+20h]
0x18000ebb0  cmp     dword ptr [rcx+8], 20Ch
0x18000ebb7  jnz     short loc_18000EBF5
0x18000ebb9  mov     rcx, [rcx]
0x18000ebbc  xor     eax, eax
0x18000ebbe  mov     [rcx+20Ah], ax
0x18000ebc5  lea     rsi, [rcx+4]
0x18000ebc9  mov     eax, [rcx]
0x18000ebcb  test    al, al
0x18000ebcd  jns     short loc_18000EBE2
0x18000ebcf  lea     rdx, DangerousExtensions
0x18000ebd6  mov     rcx, rsi
0x18000ebd9  call    CipCheckForExtensionAgainstList
0x18000ebde  test    eax, eax
0x18000ebe0  jnz     short loc_18000EBF7
0x18000ebe2  lea     rdx, InstallerExtensions
0x18000ebe9  mov     rcx, rsi
0x18000ebec  call    CipCheckForExtensionAgainstList
0x18000ebf1  mov     edi, eax
0x18000ebf3  jmp     short loc_18000EBF7
0x18000ebf5  mov     edi, edx
0x18000ebf7  mov     edx, 41746D73h; Tag
0x18000ebfc  mov     rcx, rbx; P
0x18000ebff  call    cs:__imp_ExFreePoolWithTag
0x18000ec06  nop     dword ptr [rax+rax+00h]
0x18000ec0b  jmp     loc_18000EB67
```
