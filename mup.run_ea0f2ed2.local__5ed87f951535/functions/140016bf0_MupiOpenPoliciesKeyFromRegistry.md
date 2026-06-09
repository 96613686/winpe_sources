# MupiOpenPoliciesKeyFromRegistry

- ea: `0x140016bf0`
- end: `0x140016d6e`
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

- `0x140016bf0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140016d2c`
- `ntoskrnl!ZwClose` at `0x140016d2c`
- `ntoskrnl!ZwOpenKey` at `0x140016c3a`
- `ntoskrnl!ZwOpenKey` at `0x140016c3a`
- `ntoskrnl!ZwCreateKey` at `0x140016d0f`
- `ntoskrnl!ZwCreateKey` at `0x140016d0f`

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
0x140016bf0  push    rbp
0x140016bf2  push    rbx
0x140016bf3  push    rsi
0x140016bf4  push    rdi
0x140016bf5  push    r12
0x140016bf7  push    r15
0x140016bf9  lea     rbp, [rsp-2Fh]
0x140016bfe  sub     rsp, 88h
0x140016c05  xor     eax, eax
0x140016c07  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016c0f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140016c13  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140016c17  lea     rax, MUPI_REGISTRY_POLICIES_KEY_PATH
0x140016c1e  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140016c26  xorps   xmm0, xmm0
0x140016c29  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016c2d  mov     edx, 20019h; DesiredAccess
0x140016c32  mov     rdi, rcx
0x140016c35  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016c3a  call    cs:__imp_ZwOpenKey
0x140016c41  nop     dword ptr [rax+rax+00h]
0x140016c46  mov     ebx, eax
0x140016c48  cmp     eax, 0C0000034h
0x140016c4d  jnz     loc_140016D61
0x140016c53  movups  xmm0, xmmword ptr cs:MUPI_REGISTRY_POLICIES_KEY_PATH
0x140016c5a  xor     esi, esi
0x140016c5c  mov     r15d, 8Ah
0x140016c62  xor     edx, edx
0x140016c64  movdqu  [rbp+57h+var_70], xmm0
0x140016c69  lea     r12d, [rsi+2]
0x140016c6d  mov     word ptr [rbp+57h+var_70], dx
0x140016c71  cmp     dx, r15w
0x140016c75  ja      loc_140016D61
0x140016c7b  mov     [rbp+57h+KeyHandle], 0
0x140016c83  jmp     short loc_140016C9E
0x140016c85  mov     rax, qword ptr [rbp+57h+var_70+8]
0x140016c89  movzx   ecx, dx
0x140016c8c  shr     rcx, 1
0x140016c8f  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140016c94  jz      short loc_140016CA9
0x140016c96  add     dx, r12w
0x140016c9a  mov     word ptr [rbp+57h+var_70], dx
0x140016c9e  movzx   eax, dx
0x140016ca1  add     eax, r12d
0x140016ca4  cmp     eax, r15d
0x140016ca7  jbe     short loc_140016C85
0x140016ca9  lea     eax, [rdx-1]
0x140016cac  mov     ecx, 89h
0x140016cb1  cmp     ax, cx
0x140016cb4  ja      short loc_140016CB9
0x140016cb6  inc     si
0x140016cb9  cmp     si, 4
0x140016cbd  jbe     short loc_140016D3C
0x140016cbf  lea     rax, [rbp+57h+var_70]
0x140016cc3  mov     [rsp+0B0h+Disposition], 0; Disposition
0x140016ccc  xorps   xmm0, xmm0
0x140016ccf  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x140016cd7  xor     r9d, r9d; TitleIndex
0x140016cda  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016cde  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140016ce2  mov     [rsp+0B0h+Class], 0; Class
0x140016ceb  mov     edx, 20019h; DesiredAccess
0x140016cf0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016cf7  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140016cfb  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140016d03  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016d08  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140016d0f  call    cs:__imp_ZwCreateKey
0x140016d16  nop     dword ptr [rax+rax+00h]
0x140016d1b  mov     ebx, eax
0x140016d1d  test    eax, eax
0x140016d1f  js      short loc_140016D65
0x140016d21  cmp     word ptr [rbp+57h+var_70], r15w
0x140016d26  jz      short loc_140016D45
0x140016d28  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140016d2c  call    cs:__imp_ZwClose
0x140016d33  nop     dword ptr [rax+rax+00h]
0x140016d38  movzx   edx, word ptr [rbp+57h+var_70]
0x140016d3c  add     dx, r12w
0x140016d40  jmp     loc_140016C6D
0x140016d45  mov     rax, [rbp+57h+KeyHandle]
0x140016d49  mov     [rdi], rax
0x140016d4c  xor     ebx, ebx
0x140016d4e  mov     eax, ebx
0x140016d50  add     rsp, 88h
0x140016d57  pop     r15
0x140016d59  pop     r12
0x140016d5b  pop     rdi
0x140016d5c  pop     rsi
0x140016d5d  pop     rbx
0x140016d5e  pop     rbp
0x140016d5f  retn
0x140016d61  test    ebx, ebx
0x140016d63  jns     short loc_140016D4C
0x140016d65  mov     qword ptr [rdi], 0
0x140016d6c  jmp     short loc_140016D4E
```
