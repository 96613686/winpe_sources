# HbEvtpSecFwUpdateRegistry

- ea: `0x1400130f8`
- end: `0x140013203`
- name: `HbEvtpSecFwUpdateRegistry`
- size: `267`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400129f4`

## callees

- `0x1400130f8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400131ec`
- `ntoskrnl!ZwClose` at `0x1400131ec`
- `ntoskrnl!ZwCreateKey` at `0x140013167`
- `ntoskrnl!ZwCreateKey` at `0x140013167`
- `ntoskrnl!ZwSetValueKey` at `0x14001319e`
- `ntoskrnl!ZwSetValueKey` at `0x1400131d5`
- `ntoskrnl!ZwSetValueKey` at `0x14001319e`
- `ntoskrnl!ZwSetValueKey` at `0x1400131d5`

## pseudocode

```c
__int64 __fastcall HbEvtpSecFwUpdateRegistry(int a1, __int64 a2)
{
  NTSTATUS v3; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  __int64 v6; // [rsp+98h] [rbp+28h] BYREF
  int Data; // [rsp+A0h] [rbp+30h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+38h] BYREF

  v6 = a2;
  Data = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)aFh;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v3 >= 0 )
  {
    Data = a1;
    v3 = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
    if ( v3 >= 0 )
      v3 = ZwSetValueKey(KeyHandle, &stru_1400090F0, 0, 0xBu, &v6, 8u);
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400130f8  mov     [rsp-18h+arg_8], rdx
0x1400130fd  push    rbp
0x1400130fe  push    rbx
0x1400130ff  push    rdi
0x140013100  mov     rbp, rsp
0x140013103  sub     rsp, 70h
0x140013107  xor     eax, eax
0x140013109  mov     [rsp+70h+Disposition], 0; Disposition
0x140013112  mov     [rbp+Data], eax
0x140013115  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140013119  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14001311d  mov     edi, ecx
0x14001311f  lea     rax, aFh; "fh"
0x140013126  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x14001312e  xorps   xmm0, xmm0
0x140013131  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140013135  xor     r9d, r9d; TitleIndex
0x140013138  mov     [rbp+KeyHandle], 0
0x140013140  mov     edx, 0F003Fh; DesiredAccess
0x140013145  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001314d  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140013151  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140013159  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001315e  mov     [rsp+70h+Class], 0; Class
0x140013167  call    cs:__imp_ZwCreateKey
0x14001316e  nop     dword ptr [rax+rax+00h]
0x140013173  mov     ebx, eax
0x140013175  test    eax, eax
0x140013177  js      short loc_1400131E3
0x140013179  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14001317d  lea     rax, [rbp+Data]
0x140013181  mov     r9d, 4; Type
0x140013187  mov     [rbp+Data], edi
0x14001318a  mov     [rsp+70h+CreateOptions], r9d; DataSize
0x14001318f  lea     rdx, ValueName; ValueName
0x140013196  xor     r8d, r8d; TitleIndex
0x140013199  mov     [rsp+70h+Class], rax; Data
0x14001319e  call    cs:__imp_ZwSetValueKey
0x1400131a5  nop     dword ptr [rax+rax+00h]
0x1400131aa  mov     ebx, eax
0x1400131ac  test    eax, eax
0x1400131ae  js      short loc_1400131E3
0x1400131b0  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400131b4  lea     rax, [rbp+arg_8]
0x1400131b8  mov     [rsp+70h+CreateOptions], 8; DataSize
0x1400131c0  lea     rdx, stru_1400090F0; ValueName
0x1400131c7  mov     r9d, 0Bh; Type
0x1400131cd  mov     [rsp+70h+Class], rax; Data
0x1400131d2  xor     r8d, r8d; TitleIndex
0x1400131d5  call    cs:__imp_ZwSetValueKey
0x1400131dc  nop     dword ptr [rax+rax+00h]
0x1400131e1  mov     ebx, eax
0x1400131e3  mov     rcx, [rbp+KeyHandle]; Handle
0x1400131e7  test    rcx, rcx
0x1400131ea  jz      short loc_1400131F8
0x1400131ec  call    cs:__imp_ZwClose
0x1400131f3  nop     dword ptr [rax+rax+00h]
0x1400131f8  mov     eax, ebx
0x1400131fa  add     rsp, 70h
0x1400131fe  pop     rdi
0x1400131ff  pop     rbx
0x140013200  pop     rbp
0x140013201  retn
```
