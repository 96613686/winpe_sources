# CopyDeviceInterfaceParameters

- ea: `0x180034ba0`
- end: `0x180034d29`
- name: `CopyDeviceInterfaceParameters`
- size: `393`
- prototype: `__int64 __fastcall(void *, UNICODE_STRING *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063884`

## callees

- `0x180034ba0`
- `0x1800635a0`
- `0x1800666b4`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180034c8c`
- `ntoskrnl!ZwCreateKey` at `0x180034c8c`
- `ntoskrnl!ZwClose` at `0x180034ce8`
- `ntoskrnl!ZwClose` at `0x180034d02`
- `ntoskrnl!ZwClose` at `0x180034ce8`
- `ntoskrnl!ZwClose` at `0x180034d02`
- `ntoskrnl!ZwOpenKey` at `0x180034c07`
- `ntoskrnl!ZwOpenKey` at `0x180034c07`

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
0x180034ba0  mov     [rsp-18h+arg_0], rbx
0x180034ba5  mov     [rsp-18h+arg_10], rsi
0x180034baa  push    rbp
0x180034bab  push    rdi
0x180034bac  push    r14
0x180034bae  mov     rbp, rsp
0x180034bb1  sub     rsp, 80h
0x180034bb8  xorps   xmm0, xmm0
0x180034bbb  xor     eax, eax
0x180034bbd  mov     [rbp+KeyHandle], rax
0x180034bc1  mov     r14, r8
0x180034bc4  mov     rdi, rdx
0x180034bc7  mov     rsi, rcx
0x180034bca  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180034bce  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180034bd2  movups  xmmword ptr [rbp+Handle], xmm0
0x180034bd6  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180034bda  test    rdx, rdx
0x180034bdd  jz      short loc_180034C26
0x180034bdf  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180034be3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180034be7  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x180034beb  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180034bef  mov     edx, 20019h; DesiredAccess
0x180034bf4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180034bfb  mov     [rbp+ObjectAttributes.Attributes], 240h
0x180034c02  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180034c07  call    cs:__imp_ZwOpenKey
0x180034c0e  nop     dword ptr [rax+rax+00h]
0x180034c13  mov     ebx, eax
0x180034c15  test    eax, eax
0x180034c17  jns     short loc_180034C2C
0x180034c19  mov     [rbp+KeyHandle], 0
0x180034c21  jmp     loc_180034CF4
0x180034c26  xor     ebx, ebx
0x180034c28  mov     [rbp+KeyHandle], rsi
0x180034c2c  mov     rax, [r14]
0x180034c2f  mov     rcx, [r14+8]
0x180034c33  mov     [rbp+Handle], rax
0x180034c37  mov     [rbp+Handle+8], 0
0x180034c3f  test    rdi, rdi
0x180034c42  jz      short loc_180034CA6
0x180034c44  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180034c48  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180034c4c  xorps   xmm0, xmm0
0x180034c4f  mov     [rsp+80h+Disposition], 0; Disposition
0x180034c58  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x180034c60  lea     rcx, [rbp+Handle+8]; KeyHandle
0x180034c64  xor     r9d, r9d; TitleIndex
0x180034c67  mov     [rsp+80h+Class], 0; Class
0x180034c70  mov     edx, 2001Fh; DesiredAccess
0x180034c75  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180034c7c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180034c81  mov     [rbp+ObjectAttributes.Attributes], 2C0h
0x180034c88  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x180034c8c  call    cs:__imp_ZwCreateKey
0x180034c93  nop     dword ptr [rax+rax+00h]
0x180034c98  mov     ebx, eax
0x180034c9a  test    eax, eax
0x180034c9c  jns     short loc_180034CAE
0x180034c9e  xor     ecx, ecx
0x180034ca0  mov     [rbp+Handle+8], rcx
0x180034ca4  jmp     short loc_180034CDD
0x180034ca6  mov     [rbp+Handle+8], rcx
0x180034caa  test    ebx, ebx
0x180034cac  js      short loc_180034CDD
0x180034cae  mov     rcx, [rbp+KeyHandle]
0x180034cb2  lea     r9, [rbp+Handle]
0x180034cb6  lea     r8, CopyDeviceInterfaceParameters
0x180034cbd  xor     edx, edx
0x180034cbf  call    EnumerateRegistrySubKeys
0x180034cc4  mov     ebx, eax
0x180034cc6  test    eax, eax
0x180034cc8  js      short loc_180034CD9
0x180034cca  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180034cce  lea     r8, [rbp+Handle]
0x180034cd2  call    EnumerateRegistryValues
0x180034cd7  mov     ebx, eax
0x180034cd9  mov     rcx, [rbp+Handle+8]; Handle
0x180034cdd  test    rcx, rcx
0x180034ce0  jz      short loc_180034CF4
0x180034ce2  cmp     rcx, [r14+8]
0x180034ce6  jz      short loc_180034CF4
0x180034ce8  call    cs:__imp_ZwClose
0x180034cef  nop     dword ptr [rax+rax+00h]
0x180034cf4  mov     rcx, [rbp+KeyHandle]; Handle
0x180034cf8  test    rcx, rcx
0x180034cfb  jz      short loc_180034D0E
0x180034cfd  cmp     rcx, rsi
0x180034d00  jz      short loc_180034D0E
0x180034d02  call    cs:__imp_ZwClose
0x180034d09  nop     dword ptr [rax+rax+00h]
0x180034d0e  lea     r11, [rsp+80h+var_s0]
0x180034d16  mov     eax, ebx
0x180034d18  mov     rbx, [r11+20h]
0x180034d1c  mov     rsi, [r11+30h]
0x180034d20  mov     rsp, r11
0x180034d23  pop     r14
0x180034d25  pop     rdi
0x180034d26  pop     rbp
0x180034d27  retn
```
