# RegQueryZoneFromKey

- ea: `0x14008a78c`
- end: `0x14008a854`
- name: `RegQueryZoneFromKey`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140088b50`
- `0x140088e28`
- `0x1400893f0`
- `0x14008974c`

## callees

- `0x14008a3d4`
- `0x14008a78c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14008a7e1`
- `ntoskrnl!ZwOpenKey` at `0x14008a7e1`
- `ntoskrnl!ZwClose` at `0x14008a835`
- `ntoskrnl!ZwClose` at `0x14008a835`

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
0x14008a78c  mov     [rsp-8+arg_10], rbx
0x14008a791  mov     [rsp-8+arg_18], rdi
0x14008a796  push    rbp
0x14008a797  mov     rbp, rsp
0x14008a79a  sub     rsp, 50h
0x14008a79e  mov     eax, 3
0x14008a7a3  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x14008a7a7  mov     [r8], eax
0x14008a7aa  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14008a7ae  mov     rdi, r8
0x14008a7b1  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x14008a7b5  xorps   xmm0, xmm0
0x14008a7b8  mov     [rbp+KeyHandle], 0
0x14008a7c0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14008a7c4  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14008a7cc  mov     edx, 20019h; DesiredAccess
0x14008a7d1  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14008a7d9  mov     [rbp+arg_0], eax
0x14008a7dc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14008a7e1  call    cs:__imp_ZwOpenKey
0x14008a7e8  nop     dword ptr [rax+rax+00h]
0x14008a7ed  mov     ebx, eax
0x14008a7ef  test    eax, eax
0x14008a7f1  js      short loc_14008A82C
0x14008a7f3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14008a7f7  lea     r8, [rbp+arg_0]
0x14008a7fb  lea     rdx, aFile; "file"
0x14008a802  call    RegQueryDwordValueByHandle
0x14008a807  mov     ebx, eax
0x14008a809  test    eax, eax
0x14008a80b  jns     short loc_14008A827
0x14008a80d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14008a811  lea     r8, [rbp+arg_0]
0x14008a815  lea     rdx, asc_140066E54; "*"
0x14008a81c  call    RegQueryDwordValueByHandle
0x14008a821  mov     ebx, eax
0x14008a823  test    eax, eax
0x14008a825  js      short loc_14008A82C
0x14008a827  mov     eax, [rbp+arg_0]
0x14008a82a  mov     [rdi], eax
0x14008a82c  mov     rcx, [rbp+KeyHandle]; Handle
0x14008a830  test    rcx, rcx
0x14008a833  jz      short loc_14008A841
0x14008a835  call    cs:__imp_ZwClose
0x14008a83c  nop     dword ptr [rax+rax+00h]
0x14008a841  mov     rdi, [rsp+50h+arg_18]
0x14008a846  mov     eax, ebx
0x14008a848  mov     rbx, [rsp+50h+arg_10]
0x14008a84d  add     rsp, 50h
0x14008a851  pop     rbp
0x14008a852  retn
```
