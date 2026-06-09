# MupiOpenPoliciesKeyFromRegistry

- ea: `0x140016c40`
- end: `0x140016dbe`
- name: `MupiOpenPoliciesKeyFromRegistry`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140004b40`
- `0x140004c30`
- `0x140004e60`

## callees

- `0x140016c40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140016d7c`
- `ntoskrnl!ZwClose` at `0x140016d7c`
- `ntoskrnl!ZwOpenKey` at `0x140016c8a`
- `ntoskrnl!ZwOpenKey` at `0x140016c8a`
- `ntoskrnl!ZwCreateKey` at `0x140016d5f`
- `ntoskrnl!ZwCreateKey` at `0x140016d5f`

## pseudocode

```c
__int64 __fastcall MupiOpenPoliciesKeyFromRegistry(void **a1)
{
  NTSTATUS v2; // ebx
  unsigned __int16 v3; // si
  unsigned __int16 v4; // dx
  __int128 v6; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  void *KeyHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)MUPI_REGISTRY_POLICIES_KEY_PATH;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(a1, 0x20019u, &ObjectAttributes);
  if ( v2 == -1073741772 )
  {
    v3 = 0;
    v4 = 0;
    v6 = *(_OWORD *)MUPI_REGISTRY_POLICIES_KEY_PATH;
    while ( 1 )
    {
      LOWORD(v6) = v4;
      if ( v4 > 0x8Au )
        break;
      KeyHandle = 0;
      while ( (unsigned int)v4 + 2 <= 0x8A && *(_WORD *)(*((_QWORD *)&v6 + 1) + 2 * ((unsigned __int64)v4 >> 1)) != 92 )
      {
        v4 += 2;
        LOWORD(v6) = v4;
      }
      if ( (unsigned __int16)(v4 - 1) <= 0x89u )
        ++v3;
      if ( v3 > 4u )
      {
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v6;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 576;
        v2 = ZwCreateKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
        if ( v2 < 0 )
          goto LABEL_19;
        if ( (_WORD)v6 == 138 )
        {
          *a1 = KeyHandle;
          return 0;
        }
        ZwClose(KeyHandle);
        v4 = v6;
      }
      v4 += 2;
    }
  }
  if ( v2 >= 0 )
    return 0;
  else
LABEL_19:
    *a1 = 0;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140016c40  push    rbp
0x140016c42  push    rbx
0x140016c43  push    rsi
0x140016c44  push    rdi
0x140016c45  push    r12
0x140016c47  push    r15
0x140016c49  lea     rbp, [rsp-2Fh]
0x140016c4e  sub     rsp, 88h
0x140016c55  xor     eax, eax
0x140016c57  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016c5f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140016c63  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140016c67  lea     rax, MUPI_REGISTRY_POLICIES_KEY_PATH
0x140016c6e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140016c76  xorps   xmm0, xmm0
0x140016c79  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016c7d  mov     edx, 20019h; DesiredAccess
0x140016c82  mov     rdi, rcx
0x140016c85  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016c8a  call    cs:__imp_ZwOpenKey
0x140016c91  nop     dword ptr [rax+rax+00h]
0x140016c96  mov     ebx, eax
0x140016c98  cmp     eax, 0C0000034h
0x140016c9d  jnz     loc_140016DB1
0x140016ca3  movups  xmm0, xmmword ptr cs:MUPI_REGISTRY_POLICIES_KEY_PATH
0x140016caa  xor     esi, esi
0x140016cac  mov     r15d, 8Ah
0x140016cb2  xor     edx, edx
0x140016cb4  movdqu  [rbp+57h+var_70], xmm0
0x140016cb9  lea     r12d, [rsi+2]
0x140016cbd  mov     word ptr [rbp+57h+var_70], dx
0x140016cc1  cmp     dx, r15w
0x140016cc5  ja      loc_140016DB1
0x140016ccb  mov     [rbp+57h+KeyHandle], 0
0x140016cd3  jmp     short loc_140016CEE
0x140016cd5  mov     rax, qword ptr [rbp+57h+var_70+8]
0x140016cd9  movzx   ecx, dx
0x140016cdc  shr     rcx, 1
0x140016cdf  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140016ce4  jz      short loc_140016CF9
0x140016ce6  add     dx, r12w
0x140016cea  mov     word ptr [rbp+57h+var_70], dx
0x140016cee  movzx   eax, dx
0x140016cf1  add     eax, r12d
0x140016cf4  cmp     eax, r15d
0x140016cf7  jbe     short loc_140016CD5
0x140016cf9  lea     eax, [rdx-1]
0x140016cfc  mov     ecx, 89h
0x140016d01  cmp     ax, cx
0x140016d04  ja      short loc_140016D09
0x140016d06  inc     si
0x140016d09  cmp     si, 4
0x140016d0d  jbe     short loc_140016D8C
0x140016d0f  lea     rax, [rbp+57h+var_70]
0x140016d13  mov     [rsp+0B0h+Disposition], 0; Disposition
0x140016d1c  xorps   xmm0, xmm0
0x140016d1f  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x140016d27  xor     r9d, r9d; TitleIndex
0x140016d2a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016d2e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140016d32  mov     [rsp+0B0h+Class], 0; Class
0x140016d3b  mov     edx, 20019h; DesiredAccess
0x140016d40  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016d47  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140016d4b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140016d53  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016d58  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140016d5f  call    cs:__imp_ZwCreateKey
0x140016d66  nop     dword ptr [rax+rax+00h]
0x140016d6b  mov     ebx, eax
0x140016d6d  test    eax, eax
0x140016d6f  js      short loc_140016DB5
0x140016d71  cmp     word ptr [rbp+57h+var_70], r15w
0x140016d76  jz      short loc_140016D95
0x140016d78  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140016d7c  call    cs:__imp_ZwClose
0x140016d83  nop     dword ptr [rax+rax+00h]
0x140016d88  movzx   edx, word ptr [rbp+57h+var_70]
0x140016d8c  add     dx, r12w
0x140016d90  jmp     loc_140016CBD
0x140016d95  mov     rax, [rbp+57h+KeyHandle]
0x140016d99  mov     [rdi], rax
0x140016d9c  xor     ebx, ebx
0x140016d9e  mov     eax, ebx
0x140016da0  add     rsp, 88h
0x140016da7  pop     r15
0x140016da9  pop     r12
0x140016dab  pop     rdi
0x140016dac  pop     rsi
0x140016dad  pop     rbx
0x140016dae  pop     rbp
0x140016daf  retn
0x140016db1  test    ebx, ebx
0x140016db3  jns     short loc_140016D9C
0x140016db5  mov     qword ptr [rdi], 0
0x140016dbc  jmp     short loc_140016D9E
```
