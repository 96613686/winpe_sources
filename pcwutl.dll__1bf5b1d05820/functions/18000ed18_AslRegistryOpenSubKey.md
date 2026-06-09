# AslRegistryOpenSubKey

- ea: `0x18000ed18`
- end: `0x18000edb8`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015b58`

## callees

- `0x18000e240`
- `0x18000ed18`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18000eda9`
- `ntdll!ZwOpenKey` at `0x18000eda9`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000ed49`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000ed49`

## string_xrefs

- `0x18000ed55`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x18000ed66`: `AslRegistryOpenSubKey`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenSubKey(PHANDLE KeyHandle, void *a2, const WCHAR *a3)
{
  NTSTATUS inited; // eax
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  *KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  inited = RtlInitUnicodeStringEx(&DestinationString, a3);
  v6 = inited;
  if ( inited >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a2;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryOpenSubKey", 958, "AslRegistryOpenSubKey passed bad Path [%x]", inited);
    return v6;
  }
}

```

## disassembly

```asm
0x18000ed18  push    rbp
0x18000ed1a  push    rbx
0x18000ed1b  push    rsi
0x18000ed1c  push    rdi
0x18000ed1d  mov     rbp, rsp
0x18000ed20  sub     rsp, 78h
0x18000ed24  xorps   xmm0, xmm0
0x18000ed27  xor     eax, eax
0x18000ed29  mov     [rcx], rax
0x18000ed2c  mov     rsi, rdx
0x18000ed2f  mov     rdi, rcx
0x18000ed32  mov     rdx, r8; SourceString
0x18000ed35  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000ed39  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000ed3d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000ed41  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000ed45  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000ed49  call    cs:__imp_RtlInitUnicodeStringEx
0x18000ed4f  mov     ebx, eax
0x18000ed51  test    eax, eax
0x18000ed53  jns     short loc_18000ED7B
0x18000ed55  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18000ed5c  mov     [rsp+78h+var_58], eax
0x18000ed60  mov     r8d, 3BEh
0x18000ed66  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18000ed6d  mov     ecx, 1
0x18000ed72  call    AslLogCallPrintf
0x18000ed77  mov     eax, ebx
0x18000ed79  jmp     short loc_18000EDAF
0x18000ed7b  lea     rax, [rbp+DestinationString]
0x18000ed7f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000ed86  xorps   xmm0, xmm0
0x18000ed89  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000ed8d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000ed91  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18000ed95  mov     edx, 20019h; DesiredAccess
0x18000ed9a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000eda1  mov     rcx, rdi; KeyHandle
0x18000eda4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000eda9  call    cs:__imp_ZwOpenKey
0x18000edaf  add     rsp, 78h
0x18000edb3  pop     rdi
0x18000edb4  pop     rsi
0x18000edb5  pop     rbx
0x18000edb6  pop     rbp
0x18000edb7  retn
```
