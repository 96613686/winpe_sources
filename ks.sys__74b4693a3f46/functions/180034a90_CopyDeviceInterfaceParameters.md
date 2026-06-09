# CopyDeviceInterfaceParameters

- ea: `0x180034a90`
- end: `0x180034c19`
- name: `CopyDeviceInterfaceParameters`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800636e4`

## callees

- `0x180034a90`
- `0x180063400`
- `0x180065d44`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180034b7c`
- `ntoskrnl!ZwCreateKey` at `0x180034b7c`
- `ntoskrnl!ZwClose` at `0x180034bd8`
- `ntoskrnl!ZwClose` at `0x180034bf2`
- `ntoskrnl!ZwClose` at `0x180034bd8`
- `ntoskrnl!ZwClose` at `0x180034bf2`
- `ntoskrnl!ZwOpenKey` at `0x180034af7`
- `ntoskrnl!ZwOpenKey` at `0x180034af7`

## pseudocode

```c
__int64 __fastcall CopyDeviceInterfaceParameters(void *a1, UNICODE_STRING *a2, __int64 a3)
{
  NTSTATUS v6; // ebx
  void *v7; // rcx
  HANDLE v8; // rcx
  HANDLE Handle[2]; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+28h] BYREF

  KeyHandle = 0;
  *(_OWORD *)Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a2 )
  {
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.ObjectName = a2;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v6 < 0 )
    {
      KeyHandle = 0;
      goto LABEL_15;
    }
  }
  else
  {
    KeyHandle = a1;
  }
  v7 = *(void **)(a3 + 8);
  Handle[0] = *(HANDLE *)a3;
  Handle[1] = 0;
  if ( !a2 )
  {
    Handle[1] = v7;
    goto LABEL_9;
  }
  ObjectAttributes.RootDirectory = v7;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 704;
  ObjectAttributes.ObjectName = a2;
  v6 = ZwCreateKey(&Handle[1], 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v6 >= 0 )
  {
LABEL_9:
    v6 = EnumerateRegistrySubKeys(KeyHandle, 0, CopyDeviceInterfaceParameters, Handle);
    if ( v6 >= 0 )
      v6 = EnumerateRegistryValues(KeyHandle);
    v8 = Handle[1];
    goto LABEL_12;
  }
  v8 = 0;
  Handle[1] = 0;
LABEL_12:
  if ( v8 && v8 != *(HANDLE *)(a3 + 8) )
    ZwClose(v8);
LABEL_15:
  if ( KeyHandle && KeyHandle != a1 )
    ZwClose(KeyHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180034a90  mov     [rsp-18h+arg_0], rbx
0x180034a95  mov     [rsp-18h+arg_10], rsi
0x180034a9a  push    rbp
0x180034a9b  push    rdi
0x180034a9c  push    r14
0x180034a9e  mov     rbp, rsp
0x180034aa1  sub     rsp, 80h
0x180034aa8  xorps   xmm0, xmm0
0x180034aab  xor     eax, eax
0x180034aad  mov     [rbp+KeyHandle], rax
0x180034ab1  mov     r14, r8
0x180034ab4  mov     rdi, rdx
0x180034ab7  mov     rsi, rcx
0x180034aba  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180034abe  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180034ac2  movups  xmmword ptr [rbp+Handle], xmm0
0x180034ac6  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180034aca  test    rdx, rdx
0x180034acd  jz      short loc_180034B16
0x180034acf  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180034ad3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180034ad7  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x180034adb  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180034adf  mov     edx, 20019h; DesiredAccess
0x180034ae4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180034aeb  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180034af2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180034af7  call    cs:__imp_ZwOpenKey
0x180034afe  nop     dword ptr [rax+rax+00h]
0x180034b03  mov     ebx, eax
0x180034b05  test    eax, eax
0x180034b07  jns     short loc_180034B1C
0x180034b09  mov     [rbp+KeyHandle], 0
0x180034b11  jmp     loc_180034BE4
0x180034b16  xor     ebx, ebx
0x180034b18  mov     [rbp+KeyHandle], rsi
0x180034b1c  mov     rax, [r14]
0x180034b1f  mov     rcx, [r14+8]
0x180034b23  mov     [rbp+Handle], rax
0x180034b27  mov     [rbp+Handle+8], 0
0x180034b2f  test    rdi, rdi
0x180034b32  jz      short loc_180034B96
0x180034b34  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180034b38  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180034b3c  xorps   xmm0, xmm0
0x180034b3f  mov     [rsp+80h+Disposition], 0; Disposition
0x180034b48  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x180034b50  lea     rcx, [rbp+Handle+8]; KeyHandle
0x180034b54  xor     r9d, r9d; TitleIndex
0x180034b57  mov     [rsp+80h+Class], 0; Class
0x180034b60  mov     edx, 2001Fh; DesiredAccess
0x180034b65  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180034b6c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180034b71  mov     [rbp+ObjectAttributes.Attributes], 2C0h
0x180034b78  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x180034b7c  call    cs:__imp_ZwCreateKey
0x180034b83  nop     dword ptr [rax+rax+00h]
0x180034b88  mov     ebx, eax
0x180034b8a  test    eax, eax
0x180034b8c  jns     short loc_180034B9E
0x180034b8e  xor     ecx, ecx
0x180034b90  mov     [rbp+Handle+8], rcx
0x180034b94  jmp     short loc_180034BCD
0x180034b96  mov     [rbp+Handle+8], rcx
0x180034b9a  test    ebx, ebx
0x180034b9c  js      short loc_180034BCD
0x180034b9e  mov     rcx, [rbp+KeyHandle]
0x180034ba2  lea     r9, [rbp+Handle]
0x180034ba6  lea     r8, CopyDeviceInterfaceParameters
0x180034bad  xor     edx, edx
0x180034baf  call    EnumerateRegistrySubKeys
0x180034bb4  mov     ebx, eax
0x180034bb6  test    eax, eax
0x180034bb8  js      short loc_180034BC9
0x180034bba  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180034bbe  lea     r8, [rbp+Handle]
0x180034bc2  call    EnumerateRegistryValues
0x180034bc7  mov     ebx, eax
0x180034bc9  mov     rcx, [rbp+Handle+8]; Handle
0x180034bcd  test    rcx, rcx
0x180034bd0  jz      short loc_180034BE4
0x180034bd2  cmp     rcx, [r14+8]
0x180034bd6  jz      short loc_180034BE4
0x180034bd8  call    cs:__imp_ZwClose
0x180034bdf  nop     dword ptr [rax+rax+00h]
0x180034be4  mov     rcx, [rbp+KeyHandle]; Handle
0x180034be8  test    rcx, rcx
0x180034beb  jz      short loc_180034BFE
0x180034bed  cmp     rcx, rsi
0x180034bf0  jz      short loc_180034BFE
0x180034bf2  call    cs:__imp_ZwClose
0x180034bf9  nop     dword ptr [rax+rax+00h]
0x180034bfe  lea     r11, [rsp+80h+var_s0]
0x180034c06  mov     eax, ebx
0x180034c08  mov     rbx, [r11+20h]
0x180034c0c  mov     rsi, [r11+30h]
0x180034c10  mov     rsp, r11
0x180034c13  pop     r14
0x180034c15  pop     rdi
0x180034c16  pop     rbp
0x180034c17  retn
```
