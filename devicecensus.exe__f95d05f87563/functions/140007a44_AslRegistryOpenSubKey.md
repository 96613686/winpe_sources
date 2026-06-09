# AslRegistryOpenSubKey

- ea: `0x140007a44`
- end: `0x140007ae4`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140008c40`

## callees

- `0x140007074`
- `0x140007a44`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140007a75`
- `ntdll!RtlInitUnicodeStringEx` at `0x140007a75`
- `ntdll!ZwOpenKey` at `0x140007ad5`
- `ntdll!ZwOpenKey` at `0x140007ad5`

## string_xrefs

- `0x140007a81`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x140007a92`: `AslRegistryOpenSubKey`

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
0x140007a44  push    rbp
0x140007a46  push    rbx
0x140007a47  push    rsi
0x140007a48  push    rdi
0x140007a49  mov     rbp, rsp
0x140007a4c  sub     rsp, 78h
0x140007a50  xorps   xmm0, xmm0
0x140007a53  xor     eax, eax
0x140007a55  mov     [rcx], rax
0x140007a58  mov     rsi, rdx
0x140007a5b  mov     rdi, rcx
0x140007a5e  mov     rdx, r8; SourceString
0x140007a61  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140007a65  lea     rcx, [rbp+DestinationString]; DestinationString
0x140007a69  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140007a6d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140007a71  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140007a75  call    cs:__imp_RtlInitUnicodeStringEx
0x140007a7b  mov     ebx, eax
0x140007a7d  test    eax, eax
0x140007a7f  jns     short loc_140007AA7
0x140007a81  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x140007a88  mov     [rsp+78h+var_58], eax
0x140007a8c  mov     r8d, 3BEh
0x140007a92  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x140007a99  mov     ecx, 1
0x140007a9e  call    AslLogCallPrintf
0x140007aa3  mov     eax, ebx
0x140007aa5  jmp     short loc_140007ADB
0x140007aa7  lea     rax, [rbp+DestinationString]
0x140007aab  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140007ab2  xorps   xmm0, xmm0
0x140007ab5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140007ab9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140007abd  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x140007ac1  mov     edx, 20019h; DesiredAccess
0x140007ac6  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140007acd  mov     rcx, rdi; KeyHandle
0x140007ad0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140007ad5  call    cs:__imp_ZwOpenKey
0x140007adb  add     rsp, 78h
0x140007adf  pop     rdi
0x140007ae0  pop     rsi
0x140007ae1  pop     rbx
0x140007ae2  pop     rbp
0x140007ae3  retn
```
