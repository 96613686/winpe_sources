# StSecpInitializePolicyCache

- ea: `0x14000ddd0`
- end: `0x14000df2d`
- name: `StSecpInitializePolicyCache`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000d604`

## callees

- `0x14000ddd0`
- `0x140012a40`
- `0x140013160`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000de84`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000de84`
- `ntoskrnl!ZwOpenKey` at `0x14000de40`
- `ntoskrnl!ZwOpenKey` at `0x14000dee0`
- `ntoskrnl!ZwOpenKey` at `0x14000de40`
- `ntoskrnl!ZwOpenKey` at `0x14000dee0`
- `ntoskrnl!ZwClose` at `0x14000de6d`
- `ntoskrnl!ZwClose` at `0x14000df13`
- `ntoskrnl!ZwClose` at `0x14000de6d`
- `ntoskrnl!ZwClose` at `0x14000df13`

## string_xrefs

- `0x14000dddd`: `\Registry\Machine\System\ControlSet001\Control\StSec\SecurityDescriptors`
- `0x14000de79`: `\Registry\Machine\System\ControlSet001\Control\StSec\FolderProperties`

## pseudocode

```c
__int64 StSecpInitializePolicyCache()
{
  int SecurityDescriptorPolicy; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  *(_QWORD *)&DestinationString.Length = 9568400;
  DestinationString.Buffer = L"\\Registry\\Machine\\System\\ControlSet001\\Control\\StSec\\SecurityDescriptors";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  qword_1400096A8 = (__int64)&g_StSecSecurityDescriptorCacheListHead;
  g_StSecSecurityDescriptorCacheListHead = (__int64)&g_StSecSecurityDescriptorCacheListHead;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  SecurityDescriptorPolicy = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( SecurityDescriptorPolicy >= 0 )
  {
    SecurityDescriptorPolicy = StSecpGetSecurityDescriptorPolicy(KeyHandle);
    if ( SecurityDescriptorPolicy >= 0 )
    {
      ZwClose(KeyHandle);
      RtlInitUnicodeString(
        &DestinationString,
        L"\\Registry\\Machine\\System\\ControlSet001\\Control\\StSec\\FolderProperties");
      KeyHandle = 0;
      qword_1400096B8 = (__int64)&g_StSecFolderPropertyCacheListHead;
      g_StSecFolderPropertyCacheListHead = (__int64)&g_StSecFolderPropertyCacheListHead;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      SecurityDescriptorPolicy = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
      if ( SecurityDescriptorPolicy < 0 )
      {
        if ( SecurityDescriptorPolicy == -1073741772 )
          SecurityDescriptorPolicy = 0;
      }
      else
      {
        SecurityDescriptorPolicy = StSecpGetFolderPropertyPolicy(KeyHandle);
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)SecurityDescriptorPolicy;
}

```

## disassembly

```asm
0x14000ddd0  mov     [rsp-8+arg_8], rbx
0x14000ddd5  push    rbp
0x14000ddd6  mov     rbp, rsp
0x14000ddd9  sub     rsp, 60h
0x14000dddd  lea     rax, aRegistryMachin_4; "\\Registry\\Machine\\System\\ControlSet"...
0x14000dde4  mov     qword ptr [rbp+DestinationString.Length], 920090h
0x14000ddec  mov     [rbp+DestinationString.Buffer], rax
0x14000ddf0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000ddf4  xor     eax, eax
0x14000ddf6  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000ddfe  mov     [rbp+KeyHandle], rax
0x14000de02  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000de06  lea     rax, g_StSecSecurityDescriptorCacheListHead
0x14000de0d  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000de15  mov     cs:qword_1400096A8, rax
0x14000de1c  xorps   xmm0, xmm0
0x14000de1f  mov     cs:g_StSecSecurityDescriptorCacheListHead, rax
0x14000de26  mov     edx, 20019h; DesiredAccess
0x14000de2b  lea     rax, [rbp+DestinationString]
0x14000de2f  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000de37  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000de3b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000de40  call    cs:__imp_ZwOpenKey
0x14000de47  nop     dword ptr [rax+rax+00h]
0x14000de4c  mov     ebx, eax
0x14000de4e  test    eax, eax
0x14000de50  js      loc_14000DF0A
0x14000de56  mov     rcx, [rbp+KeyHandle]
0x14000de5a  call    StSecpGetSecurityDescriptorPolicy
0x14000de5f  mov     ebx, eax
0x14000de61  test    eax, eax
0x14000de63  js      loc_14000DF0A
0x14000de69  mov     rcx, [rbp+KeyHandle]; Handle
0x14000de6d  call    cs:__imp_ZwClose
0x14000de74  nop     dword ptr [rax+rax+00h]
0x14000de79  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\ControlSet"...
0x14000de80  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000de84  call    cs:__imp_RtlInitUnicodeString
0x14000de8b  nop     dword ptr [rax+rax+00h]
0x14000de90  lea     rax, g_StSecFolderPropertyCacheListHead
0x14000de97  mov     [rbp+KeyHandle], 0
0x14000de9f  mov     cs:qword_1400096B8, rax
0x14000dea6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000deaa  mov     cs:g_StSecFolderPropertyCacheListHead, rax
0x14000deb1  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000deb5  lea     rax, [rbp+DestinationString]
0x14000deb9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000dec0  xorps   xmm0, xmm0
0x14000dec3  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000dec7  mov     edx, 20019h; DesiredAccess
0x14000decc  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000ded4  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000dedb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000dee0  call    cs:__imp_ZwOpenKey
0x14000dee7  nop     dword ptr [rax+rax+00h]
0x14000deec  mov     ebx, eax
0x14000deee  test    eax, eax
0x14000def0  js      short loc_14000DEFF
0x14000def2  mov     rcx, [rbp+KeyHandle]
0x14000def6  call    StSecpGetFolderPropertyPolicy
0x14000defb  mov     ebx, eax
0x14000defd  jmp     short loc_14000DF0A
0x14000deff  xor     eax, eax
0x14000df01  cmp     ebx, 0C0000034h
0x14000df07  cmovz   ebx, eax
0x14000df0a  mov     rcx, [rbp+KeyHandle]; Handle
0x14000df0e  test    rcx, rcx
0x14000df11  jz      short loc_14000DF1F
0x14000df13  call    cs:__imp_ZwClose
0x14000df1a  nop     dword ptr [rax+rax+00h]
0x14000df1f  mov     eax, ebx
0x14000df21  mov     rbx, [rsp+60h+arg_8]
0x14000df26  add     rsp, 60h
0x14000df2a  pop     rbp
0x14000df2b  retn
```
