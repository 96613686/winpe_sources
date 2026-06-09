# AslRegistryOpenKey

- ea: `0x18000ec80`
- end: `0x18000ed12`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b8e8`
- `0x180015b58`

## callees

- `0x18000e240`
- `0x18000ec80`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18000ecff`
- `ntdll!ZwOpenKey` at `0x18000ecff`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000ec9d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000ec9d`

## string_xrefs

- `0x18000ecab`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x18000ecbc`: `AslRegistryOpenKey`

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
  if ( inited >= 0 )
  {
    *KeyHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)ZwOpenKey(KeyHandle, a3, &ObjectAttributes);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]", inited);
  }
  return v6;
}

```

## disassembly

```asm
0x18000ec80  push    rbp
0x18000ec82  push    rbx
0x18000ec83  push    rsi
0x18000ec84  push    rdi
0x18000ec85  mov     rbp, rsp
0x18000ec88  sub     rsp, 78h
0x18000ec8c  mov     rdi, rcx
0x18000ec8f  xorps   xmm0, xmm0
0x18000ec92  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000ec96  mov     esi, r8d
0x18000ec99  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000ec9d  call    cs:__imp_RtlInitUnicodeStringEx
0x18000eca3  xor     ecx, ecx
0x18000eca5  mov     ebx, eax
0x18000eca7  test    eax, eax
0x18000eca9  jns     short loc_18000ECCF
0x18000ecab  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18000ecb2  mov     [rsp+78h+var_58], eax
0x18000ecb6  mov     r8d, 388h
0x18000ecbc  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18000ecc3  mov     ecx, 1
0x18000ecc8  call    AslLogCallPrintf
0x18000eccd  jmp     short loc_18000ED07
0x18000eccf  mov     [rdi], rcx
0x18000ecd2  lea     rax, [rbp+DestinationString]
0x18000ecd6  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x18000ecda  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000ecde  xorps   xmm0, xmm0
0x18000ece1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000ece5  mov     rcx, rdi; KeyHandle
0x18000ece8  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000ecf0  mov     edx, esi; DesiredAccess
0x18000ecf2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000ecfa  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ecff  call    cs:__imp_ZwOpenKey
0x18000ed05  mov     ebx, eax
0x18000ed07  mov     eax, ebx
0x18000ed09  add     rsp, 78h
0x18000ed0d  pop     rdi
0x18000ed0e  pop     rsi
0x18000ed0f  pop     rbx
0x18000ed10  pop     rbp
0x18000ed11  retn
```
