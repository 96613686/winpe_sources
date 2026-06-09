# AslRegistryOpenSubKey

- ea: `0x1800675e8`
- end: `0x180067688`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007298c`

## callees

- `0x180066c10`
- `0x1800675e8`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180067619`
- `ntdll!RtlInitUnicodeStringEx` at `0x180067619`
- `ntdll!ZwOpenKey` at `0x180067679`
- `ntdll!ZwOpenKey` at `0x180067679`

## string_xrefs

- `0x180067625`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x180067636`: `AslRegistryOpenSubKey`

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
0x1800675e8  push    rbp
0x1800675ea  push    rbx
0x1800675eb  push    rsi
0x1800675ec  push    rdi
0x1800675ed  mov     rbp, rsp
0x1800675f0  sub     rsp, 78h
0x1800675f4  xorps   xmm0, xmm0
0x1800675f7  xor     eax, eax
0x1800675f9  mov     [rcx], rax
0x1800675fc  mov     rsi, rdx
0x1800675ff  mov     rdi, rcx
0x180067602  mov     rdx, r8; SourceString
0x180067605  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180067609  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006760d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180067611  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180067615  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180067619  call    cs:__imp_RtlInitUnicodeStringEx
0x18006761f  mov     ebx, eax
0x180067621  test    eax, eax
0x180067623  jns     short loc_18006764B
0x180067625  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18006762c  mov     [rsp+78h+var_58], eax
0x180067630  mov     r8d, 3BEh
0x180067636  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18006763d  mov     ecx, 1
0x180067642  call    AslLogCallPrintf
0x180067647  mov     eax, ebx
0x180067649  jmp     short loc_18006767F
0x18006764b  lea     rax, [rbp+DestinationString]
0x18006764f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180067656  xorps   xmm0, xmm0
0x180067659  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006765d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180067661  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180067665  mov     edx, 20019h; DesiredAccess
0x18006766a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180067671  mov     rcx, rdi; KeyHandle
0x180067674  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180067679  call    cs:__imp_ZwOpenKey
0x18006767f  add     rsp, 78h
0x180067683  pop     rdi
0x180067684  pop     rsi
0x180067685  pop     rbx
0x180067686  pop     rbp
0x180067687  retn
```
