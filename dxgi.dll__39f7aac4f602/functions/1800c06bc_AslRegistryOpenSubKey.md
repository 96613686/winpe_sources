# AslRegistryOpenSubKey

- ea: `0x1800c06bc`
- end: `0x1800c075c`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bfd74`

## callees

- `0x18004281c`
- `0x1800c06bc`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x1800c074d`
- `ntdll!ZwOpenKey` at `0x1800c074d`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800c06ed`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800c06ed`

## string_xrefs

- `0x1800c06f9`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x1800c070a`: `AslRegistryOpenSubKey`

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
0x1800c06bc  push    rbp
0x1800c06be  push    rbx
0x1800c06bf  push    rsi
0x1800c06c0  push    rdi
0x1800c06c1  mov     rbp, rsp
0x1800c06c4  sub     rsp, 78h
0x1800c06c8  xorps   xmm0, xmm0
0x1800c06cb  xor     eax, eax
0x1800c06cd  mov     [rcx], rax
0x1800c06d0  mov     rsi, rdx
0x1800c06d3  mov     rdi, rcx
0x1800c06d6  mov     rdx, r8; SourceString
0x1800c06d9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800c06dd  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800c06e1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800c06e5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800c06e9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800c06ed  call    cs:__imp_RtlInitUnicodeStringEx
0x1800c06f3  mov     ebx, eax
0x1800c06f5  test    eax, eax
0x1800c06f7  jns     short loc_1800C071F
0x1800c06f9  lea     r9, aAslregistryope_0; "AslRegistryOpenSubKey passed bad Path ["...
0x1800c0700  mov     [rsp+78h+var_58], eax
0x1800c0704  mov     r8d, 3BEh
0x1800c070a  lea     rdx, aAslregistryope; "AslRegistryOpenSubKey"
0x1800c0711  mov     ecx, 1
0x1800c0716  call    AslLogCallPrintf
0x1800c071b  mov     eax, ebx
0x1800c071d  jmp     short loc_1800C0753
0x1800c071f  lea     rax, [rbp+DestinationString]
0x1800c0723  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800c072a  xorps   xmm0, xmm0
0x1800c072d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800c0731  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800c0735  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1800c0739  mov     edx, 20019h; DesiredAccess
0x1800c073e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800c0745  mov     rcx, rdi; KeyHandle
0x1800c0748  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c074d  call    cs:__imp_ZwOpenKey
0x1800c0753  add     rsp, 78h
0x1800c0757  pop     rdi
0x1800c0758  pop     rsi
0x1800c0759  pop     rbx
0x1800c075a  pop     rbp
0x1800c075b  retn
```
