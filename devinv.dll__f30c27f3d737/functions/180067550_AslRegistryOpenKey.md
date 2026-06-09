# AslRegistryOpenKey

- ea: `0x180067550`
- end: `0x1800675e2`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006b3a0`
- `0x18007298c`

## callees

- `0x180066c10`
- `0x180067550`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18006756d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18006756d`
- `ntdll!ZwOpenKey` at `0x1800675cf`
- `ntdll!ZwOpenKey` at `0x1800675cf`

## string_xrefs

- `0x18006757b`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x18006758c`: `AslRegistryOpenKey`

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
0x180067550  push    rbp
0x180067552  push    rbx
0x180067553  push    rsi
0x180067554  push    rdi
0x180067555  mov     rbp, rsp
0x180067558  sub     rsp, 78h
0x18006755c  mov     rdi, rcx
0x18006755f  xorps   xmm0, xmm0
0x180067562  lea     rcx, [rbp+DestinationString]; DestinationString
0x180067566  mov     esi, r8d
0x180067569  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006756d  call    cs:__imp_RtlInitUnicodeStringEx
0x180067573  xor     ecx, ecx
0x180067575  mov     ebx, eax
0x180067577  test    eax, eax
0x180067579  jns     short loc_18006759F
0x18006757b  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x180067582  mov     [rsp+78h+var_58], eax
0x180067586  mov     r8d, 388h
0x18006758c  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x180067593  mov     ecx, 1
0x180067598  call    AslLogCallPrintf
0x18006759d  jmp     short loc_1800675D7
0x18006759f  mov     [rdi], rcx
0x1800675a2  lea     rax, [rbp+DestinationString]
0x1800675a6  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1800675aa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800675ae  xorps   xmm0, xmm0
0x1800675b1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800675b5  mov     rcx, rdi; KeyHandle
0x1800675b8  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800675c0  mov     edx, esi; DesiredAccess
0x1800675c2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800675ca  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800675cf  call    cs:__imp_ZwOpenKey
0x1800675d5  mov     ebx, eax
0x1800675d7  mov     eax, ebx
0x1800675d9  add     rsp, 78h
0x1800675dd  pop     rdi
0x1800675de  pop     rsi
0x1800675df  pop     rbx
0x1800675e0  pop     rbp
0x1800675e1  retn
```
