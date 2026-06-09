# AslRegistryOpenSubKey

- ea: `0x18000a67c`
- end: `0x18000a71c`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000adf8`

## callees

- `0x180007738`
- `0x18000a67c`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18000a70d`
- `ntdll!ZwOpenKey` at `0x18000a70d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000a6ad`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000a6ad`

## string_xrefs

- `0x18000a6b9`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x18000a6ca`: `AslRegistryOpenSubKey`

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
0x18000a67c  push    rbp
0x18000a67e  push    rbx
0x18000a67f  push    rsi
0x18000a680  push    rdi
0x18000a681  mov     rbp, rsp
0x18000a684  sub     rsp, 78h
0x18000a688  xorps   xmm0, xmm0
0x18000a68b  xor     eax, eax
0x18000a68d  mov     [rcx], rax
0x18000a690  mov     rsi, rdx
0x18000a693  mov     rdi, rcx
0x18000a696  mov     rdx, r8; SourceString
0x18000a699  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000a69d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a6a1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000a6a5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000a6a9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18000a6ad  call    cs:__imp_RtlInitUnicodeStringEx
0x18000a6b3  mov     ebx, eax
0x18000a6b5  test    eax, eax
0x18000a6b7  jns     short loc_18000A6DF
0x18000a6b9  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18000a6c0  mov     [rsp+78h+var_58], eax
0x18000a6c4  mov     r8d, 3BEh
0x18000a6ca  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18000a6d1  mov     ecx, 1
0x18000a6d6  call    AslLogCallPrintf
0x18000a6db  mov     eax, ebx
0x18000a6dd  jmp     short loc_18000A713
0x18000a6df  lea     rax, [rbp+DestinationString]
0x18000a6e3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18000a6ea  xorps   xmm0, xmm0
0x18000a6ed  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000a6f1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18000a6f5  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18000a6f9  mov     edx, 20019h; DesiredAccess
0x18000a6fe  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18000a705  mov     rcx, rdi; KeyHandle
0x18000a708  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a70d  call    cs:__imp_ZwOpenKey
0x18000a713  add     rsp, 78h
0x18000a717  pop     rdi
0x18000a718  pop     rsi
0x18000a719  pop     rbx
0x18000a71a  pop     rbp
0x18000a71b  retn
```
