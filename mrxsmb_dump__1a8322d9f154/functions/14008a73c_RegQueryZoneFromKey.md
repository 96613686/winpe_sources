# RegQueryZoneFromKey

- ea: `0x14008a73c`
- end: `0x14008a804`
- name: `RegQueryZoneFromKey`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140088b00`
- `0x140088dd8`
- `0x1400893a0`
- `0x1400896fc`

## callees

- `0x14008a384`
- `0x14008a73c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14008a791`
- `ntoskrnl!ZwOpenKey` at `0x14008a791`
- `ntoskrnl!ZwClose` at `0x14008a7e5`
- `ntoskrnl!ZwClose` at `0x14008a7e5`

## pseudocode

```c
__int64 __fastcall RegQueryZoneFromKey(void *a1, UNICODE_STRING *a2, _DWORD *a3)
{
  NTSTATUS DwordValueByHandle; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+68h] [rbp+18h] BYREF

  ObjectAttributes.RootDirectory = a1;
  *a3 = 3;
  ObjectAttributes.ObjectName = a2;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DwordValueByHandle = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( DwordValueByHandle >= 0 )
  {
    DwordValueByHandle = RegQueryDwordValueByHandle(KeyHandle);
    if ( DwordValueByHandle >= 0
      || (DwordValueByHandle = RegQueryDwordValueByHandle(KeyHandle), DwordValueByHandle >= 0) )
    {
      *a3 = 3;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)DwordValueByHandle;
}

```

## disassembly

```asm
0x14008a73c  mov     [rsp-8+arg_10], rbx
0x14008a741  mov     [rsp-8+arg_18], rdi
0x14008a746  push    rbp
0x14008a747  mov     rbp, rsp
0x14008a74a  sub     rsp, 50h
0x14008a74e  mov     eax, 3
0x14008a753  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x14008a757  mov     [r8], eax
0x14008a75a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14008a75e  mov     rdi, r8
0x14008a761  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x14008a765  xorps   xmm0, xmm0
0x14008a768  mov     [rbp+KeyHandle], 0
0x14008a770  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14008a774  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14008a77c  mov     edx, 20019h; DesiredAccess
0x14008a781  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14008a789  mov     [rbp+arg_0], eax
0x14008a78c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14008a791  call    cs:__imp_ZwOpenKey
0x14008a798  nop     dword ptr [rax+rax+00h]
0x14008a79d  mov     ebx, eax
0x14008a79f  test    eax, eax
0x14008a7a1  js      short loc_14008A7DC
0x14008a7a3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14008a7a7  lea     r8, [rbp+arg_0]
0x14008a7ab  lea     rdx, aFile; "file"
0x14008a7b2  call    RegQueryDwordValueByHandle
0x14008a7b7  mov     ebx, eax
0x14008a7b9  test    eax, eax
0x14008a7bb  jns     short loc_14008A7D7
0x14008a7bd  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14008a7c1  lea     r8, [rbp+arg_0]
0x14008a7c5  lea     rdx, asc_140066E60; "*"
0x14008a7cc  call    RegQueryDwordValueByHandle
0x14008a7d1  mov     ebx, eax
0x14008a7d3  test    eax, eax
0x14008a7d5  js      short loc_14008A7DC
0x14008a7d7  mov     eax, [rbp+arg_0]
0x14008a7da  mov     [rdi], eax
0x14008a7dc  mov     rcx, [rbp+KeyHandle]; Handle
0x14008a7e0  test    rcx, rcx
0x14008a7e3  jz      short loc_14008A7F1
0x14008a7e5  call    cs:__imp_ZwClose
0x14008a7ec  nop     dword ptr [rax+rax+00h]
0x14008a7f1  mov     rdi, [rsp+50h+arg_18]
0x14008a7f6  mov     eax, ebx
0x14008a7f8  mov     rbx, [rsp+50h+arg_10]
0x14008a7fd  add     rsp, 50h
0x14008a801  pop     rbp
0x14008a802  retn
```
