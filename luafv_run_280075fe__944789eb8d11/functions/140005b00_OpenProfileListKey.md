# OpenProfileListKey

- ea: `0x140005b00`
- end: `0x140005b7b`
- name: `OpenProfileListKey`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140005798`

## callees

- `0x140005b00`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140005b4d`
- `ntoskrnl!ZwOpenKey` at `0x140005b4d`

## pseudocode

```c
NTSTATUS __fastcall OpenProfileListKey(void **a1)
{
  NTSTATUS result; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp+10h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a1 = 0;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&g_ProfileKeyPath;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    *a1 = KeyHandle;
    return 0;
  }
  else
  {
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005b00  mov     [rsp-8+arg_8], rbx
0x140005b05  push    rbp
0x140005b06  mov     rbp, rsp
0x140005b09  sub     rsp, 50h
0x140005b0d  xor     eax, eax
0x140005b0f  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140005b17  mov     [rcx], rax
0x140005b1a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140005b1e  mov     [rbp+KeyHandle], rax
0x140005b22  mov     rbx, rcx
0x140005b25  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140005b29  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140005b2d  lea     rax, g_ProfileKeyPath
0x140005b34  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140005b3c  xorps   xmm0, xmm0
0x140005b3f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140005b43  mov     edx, 20019h; DesiredAccess
0x140005b48  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140005b4d  call    cs:__imp_ZwOpenKey
0x140005b54  nop     dword ptr [rax+rax+00h]
0x140005b59  test    eax, eax
0x140005b5b  jns     short loc_140005B66
0x140005b5d  mov     qword ptr [rbx], 0
0x140005b64  jmp     short loc_140005B6F
0x140005b66  mov     rax, [rbp+KeyHandle]
0x140005b6a  mov     [rbx], rax
0x140005b6d  xor     eax, eax
0x140005b6f  mov     rbx, [rsp+50h+arg_8]
0x140005b74  add     rsp, 50h
0x140005b78  pop     rbp
0x140005b79  retn
```
