# AslRegistryOpenKey

- ea: `0x18001a93c`
- end: `0x18001a9ce`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ada8`
- `0x18001b710`

## callees

- `0x18001a93c`
- `0x180035ea4`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18001a997`
- `ntdll!ZwOpenKey` at `0x18001a997`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a959`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a959`

## string_xrefs

- `0x18001a9aa`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x18001a9bb`: `AslRegistryOpenKey`

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
0x18001a93c  push    rbp
0x18001a93e  push    rbx
0x18001a93f  push    rsi
0x18001a940  push    rdi
0x18001a941  mov     rbp, rsp
0x18001a944  sub     rsp, 78h
0x18001a948  mov     rdi, rcx
0x18001a94b  xorps   xmm0, xmm0
0x18001a94e  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001a952  mov     esi, r8d
0x18001a955  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001a959  call    cs:__imp_RtlInitUnicodeStringEx
0x18001a95f  xor     ecx, ecx
0x18001a961  mov     ebx, eax
0x18001a963  test    eax, eax
0x18001a965  js      short loc_18001A9AA
0x18001a967  mov     [rdi], rcx
0x18001a96a  lea     rax, [rbp+DestinationString]
0x18001a96e  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x18001a972  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001a976  xorps   xmm0, xmm0
0x18001a979  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001a97d  mov     rcx, rdi; KeyHandle
0x18001a980  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001a988  mov     edx, esi; DesiredAccess
0x18001a98a  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001a992  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001a997  call    cs:__imp_ZwOpenKey
0x18001a99d  mov     ebx, eax
0x18001a99f  mov     eax, ebx
0x18001a9a1  add     rsp, 78h
0x18001a9a5  pop     rdi
0x18001a9a6  pop     rsi
0x18001a9a7  pop     rbx
0x18001a9a8  pop     rbp
0x18001a9a9  retn
0x18001a9aa  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18001a9b1  mov     [rsp+78h+var_58], eax
0x18001a9b5  mov     r8d, 388h
0x18001a9bb  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18001a9c2  mov     ecx, 1
0x18001a9c7  call    AslLogCallPrintf
0x18001a9cc  jmp     short loc_18001A99F
```
