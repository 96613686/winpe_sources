# AslRegistryOpenKey

- ea: `0x18001e7d4`
- end: `0x18001e873`
- name: `AslRegistryOpenKey`
- size: `159`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ec90`
- `0x18001f680`

## callees

- `0x18001e7d4`
- `0x180036388`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18001e835`
- `ntdll!ZwOpenKey` at `0x18001e835`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001e7f1`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001e7f1`

## string_xrefs

- `0x18001e84f`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x18001e860`: `AslRegistryOpenKey`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(PHANDLE KeyHandle, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  v6 = inited;
  if ( inited < 0 )
  {
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]", inited);
  }
  else
  {
    *KeyHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)ZwOpenKey(KeyHandle, a3, &ObjectAttributes);
  }
  return v6;
}

```

## disassembly

```asm
0x18001e7d4  push    rbp
0x18001e7d6  push    rbx
0x18001e7d7  push    rsi
0x18001e7d8  push    rdi
0x18001e7d9  mov     rbp, rsp
0x18001e7dc  sub     rsp, 78h
0x18001e7e0  mov     rdi, rcx
0x18001e7e3  xorps   xmm0, xmm0
0x18001e7e6  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001e7ea  mov     esi, r8d
0x18001e7ed  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001e7f1  call    cs:__imp_RtlInitUnicodeStringEx
0x18001e7f8  nop     dword ptr [rax+rax+00h]
0x18001e7fd  xor     ecx, ecx
0x18001e7ff  mov     ebx, eax
0x18001e801  test    eax, eax
0x18001e803  js      short loc_18001E84F
0x18001e805  mov     [rdi], rcx
0x18001e808  lea     rax, [rbp+DestinationString]
0x18001e80c  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x18001e810  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001e814  xorps   xmm0, xmm0
0x18001e817  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001e81b  mov     rcx, rdi; KeyHandle
0x18001e81e  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001e826  mov     edx, esi; DesiredAccess
0x18001e828  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001e830  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001e835  call    cs:__imp_ZwOpenKey
0x18001e83c  nop     dword ptr [rax+rax+00h]
0x18001e841  mov     ebx, eax
0x18001e843  mov     eax, ebx
0x18001e845  add     rsp, 78h
0x18001e849  pop     rdi
0x18001e84a  pop     rsi
0x18001e84b  pop     rbx
0x18001e84c  pop     rbp
0x18001e84d  retn
0x18001e84f  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18001e856  mov     [rsp+78h+var_58], eax
0x18001e85a  mov     r8d, 388h
0x18001e860  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18001e867  mov     ecx, 1
0x18001e86c  call    AslLogCallPrintf
0x18001e871  jmp     short loc_18001E843
```
