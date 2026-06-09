# AslRegistryOpenKey

- ea: `0x1400079ac`
- end: `0x140007a3e`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle, const WCHAR *, ACCESS_MASK)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140008c40`
- `0x140009c7c`

## callees

- `0x140007074`
- `0x1400079ac`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1400079c9`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400079c9`
- `ntdll!ZwOpenKey` at `0x140007a2b`
- `ntdll!ZwOpenKey` at `0x140007a2b`

## string_xrefs

- `0x1400079d7`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x1400079e8`: `AslRegistryOpenKey`

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
0x1400079ac  push    rbp
0x1400079ae  push    rbx
0x1400079af  push    rsi
0x1400079b0  push    rdi
0x1400079b1  mov     rbp, rsp
0x1400079b4  sub     rsp, 78h
0x1400079b8  mov     rdi, rcx
0x1400079bb  xorps   xmm0, xmm0
0x1400079be  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400079c2  mov     esi, r8d
0x1400079c5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400079c9  call    cs:__imp_RtlInitUnicodeStringEx
0x1400079cf  xor     ecx, ecx
0x1400079d1  mov     ebx, eax
0x1400079d3  test    eax, eax
0x1400079d5  jns     short loc_1400079FB
0x1400079d7  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x1400079de  mov     [rsp+78h+var_58], eax
0x1400079e2  mov     r8d, 388h
0x1400079e8  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x1400079ef  mov     ecx, 1
0x1400079f4  call    AslLogCallPrintf
0x1400079f9  jmp     short loc_140007A33
0x1400079fb  mov     [rdi], rcx
0x1400079fe  lea     rax, [rbp+DestinationString]
0x140007a02  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x140007a06  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140007a0a  xorps   xmm0, xmm0
0x140007a0d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140007a11  mov     rcx, rdi; KeyHandle
0x140007a14  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140007a1c  mov     edx, esi; DesiredAccess
0x140007a1e  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140007a26  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140007a2b  call    cs:__imp_ZwOpenKey
0x140007a31  mov     ebx, eax
0x140007a33  mov     eax, ebx
0x140007a35  add     rsp, 78h
0x140007a39  pop     rdi
0x140007a3a  pop     rsi
0x140007a3b  pop     rbx
0x140007a3c  pop     rbp
0x140007a3d  retn
```
