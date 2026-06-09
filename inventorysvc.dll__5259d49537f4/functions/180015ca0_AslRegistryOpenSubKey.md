# AslRegistryOpenSubKey

- ea: `0x180015ca0`
- end: `0x180015d40`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016e90`

## callees

- `0x1800152d0`
- `0x180015ca0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180015cd1`
- `ntdll!RtlInitUnicodeStringEx` at `0x180015cd1`
- `ntdll!ZwOpenKey` at `0x180015d31`
- `ntdll!ZwOpenKey` at `0x180015d31`

## string_xrefs

- `0x180015cdd`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x180015cee`: `AslRegistryOpenSubKey`

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
0x180015ca0  push    rbp
0x180015ca2  push    rbx
0x180015ca3  push    rsi
0x180015ca4  push    rdi
0x180015ca5  mov     rbp, rsp
0x180015ca8  sub     rsp, 78h
0x180015cac  xorps   xmm0, xmm0
0x180015caf  xor     eax, eax
0x180015cb1  mov     [rcx], rax
0x180015cb4  mov     rsi, rdx
0x180015cb7  mov     rdi, rcx
0x180015cba  mov     rdx, r8; SourceString
0x180015cbd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180015cc1  lea     rcx, [rbp+DestinationString]; DestinationString
0x180015cc5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180015cc9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180015ccd  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180015cd1  call    cs:__imp_RtlInitUnicodeStringEx
0x180015cd7  mov     ebx, eax
0x180015cd9  test    eax, eax
0x180015cdb  jns     short loc_180015D03
0x180015cdd  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x180015ce4  mov     [rsp+78h+var_58], eax
0x180015ce8  mov     r8d, 3BEh
0x180015cee  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x180015cf5  mov     ecx, 1
0x180015cfa  call    AslLogCallPrintf
0x180015cff  mov     eax, ebx
0x180015d01  jmp     short loc_180015D37
0x180015d03  lea     rax, [rbp+DestinationString]
0x180015d07  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180015d0e  xorps   xmm0, xmm0
0x180015d11  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180015d15  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180015d19  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180015d1d  mov     edx, 20019h; DesiredAccess
0x180015d22  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180015d29  mov     rcx, rdi; KeyHandle
0x180015d2c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180015d31  call    cs:__imp_ZwOpenKey
0x180015d37  add     rsp, 78h
0x180015d3b  pop     rdi
0x180015d3c  pop     rsi
0x180015d3d  pop     rbx
0x180015d3e  pop     rbp
0x180015d3f  retn
```
