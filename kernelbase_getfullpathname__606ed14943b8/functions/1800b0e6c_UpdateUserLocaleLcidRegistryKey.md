# UpdateUserLocaleLcidRegistryKey

- ea: `0x1800b0e6c`
- end: `0x1800b1048`
- name: `UpdateUserLocaleLcidRegistryKey`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800af910`

## callees

- `0x18002bea0`
- `0x1800b0e6c`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800b0eea`
- `ntdll!RtlInitUnicodeString` at `0x1800b0f01`
- `ntdll!RtlInitUnicodeString` at `0x1800b0eea`
- `ntdll!RtlInitUnicodeString` at `0x1800b0f01`
- `ntdll!NtOpenKey` at `0x1800b0f50`
- `ntdll!NtOpenKey` at `0x1800b0f50`
- `ntdll!NtSetValueKey` at `0x1800b0fec`
- `ntdll!NtSetValueKey` at `0x1800b0fec`
- `ntdll!NtDeleteValueKey` at `0x1800b0f80`
- `ntdll!NtDeleteValueKey` at `0x1800b0f80`
- `ntdll!RtlIsMultiSessionSku` at `0x1800b0f66`
- `ntdll!RtlIsMultiSessionSku` at `0x1800b0f66`
- `ntdll!NtClose` at `0x1800b0fff`
- `ntdll!NtClose` at `0x1800b1015`
- `ntdll!NtClose` at `0x1800b0fff`
- `ntdll!NtClose` at `0x1800b1015`

## pseudocode

```c
__int64 __fastcall UpdateUserLocaleLcidRegistryKey(unsigned int a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  HANDLE v4; // rcx
  char *v5; // r8
  __int16 v6; // ax
  char *v7; // rdx
  unsigned int v8; // ecx
  HANDLE KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v13; // [rsp+80h] [rbp-80h] BYREF
  _WORD Data[7]; // [rsp+90h] [rbp-70h] BYREF
  char v15; // [rsp+9Eh] [rbp-62h] BYREF
  __int16 v16; // [rsp+A0h] [rbp-60h]

  Handle = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v13 = 0;
  DestinationString = 0;
  result = OpenGlobalizationUserSettingsKey(0x20019u, 0, &Handle);
  v3 = result;
  if ( (int)result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Locale");
    RtlInitUnicodeString(&v13, L"Control Panel\\International");
    v4 = Handle;
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.ObjectName = &v13;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 1600;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( a1 )
    {
      v3 = NtOpenKey(&KeyHandle, 0x40000000u, &ObjectAttributes);
      if ( v3 >= 0 )
      {
        if ( (unsigned __int8)RtlIsMultiSessionSku() )
        {
          v5 = &v15;
          v16 = 0;
          do
          {
            v6 = 48;
            v7 = v5 - 2;
            v8 = a1 & 0xF;
            if ( v8 > 9 )
              v6 = 55;
            a1 >>= 4;
            *(_WORD *)v5 = v8 + v6;
            v5 -= 2;
          }
          while ( v7 >= (char *)Data );
          v3 = NtSetValueKey(KeyHandle, &DestinationString, 0, 1u, Data, 0x12u);
        }
        else
        {
          NtDeleteValueKey(KeyHandle, &DestinationString);
        }
        NtClose(KeyHandle);
      }
      v4 = Handle;
    }
    if ( v4 )
      NtClose(v4);
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800b0e6c  mov     [rsp-8+arg_0], rbx
0x1800b0e71  mov     [rsp-8+arg_8], rdi
0x1800b0e76  push    rbp
0x1800b0e77  lea     rbp, [rsp-0A0h]
0x1800b0e7f  sub     rsp, 1A0h
0x1800b0e86  mov     rax, cs:__security_cookie
0x1800b0e8d  xor     rax, rsp
0x1800b0e90  mov     [rbp+0A0h+var_10], rax
0x1800b0e97  xorps   xmm0, xmm0
0x1800b0e9a  lea     r8, [rsp+1A0h+Handle]; KeyHandle
0x1800b0e9f  xor     eax, eax
0x1800b0ea1  mov     edi, ecx
0x1800b0ea3  xorps   xmm1, xmm1
0x1800b0ea6  mov     [rsp+1A0h+Handle], rax
0x1800b0eab  movups  xmmword ptr [rsp+1A0h+ObjectAttributes.ObjectName], xmm0
0x1800b0eb0  xor     edx, edx; Sid
0x1800b0eb2  mov     [rsp+1A0h+KeyHandle], rax
0x1800b0eb7  mov     ecx, 20019h; DesiredAccess
0x1800b0ebc  movups  xmmword ptr [rsp+1A0h+ObjectAttributes+1Ch], xmm0
0x1800b0ec1  movups  xmmword ptr [rsp+1A0h+ObjectAttributes.Length], xmm0
0x1800b0ec6  movups  xmmword ptr [rbp+0A0h+var_120.Length], xmm0
0x1800b0eca  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm1
0x1800b0ecf  call    OpenGlobalizationUserSettingsKey
0x1800b0ed4  mov     ebx, eax
0x1800b0ed6  test    eax, eax
0x1800b0ed8  js      loc_1800B1023
0x1800b0ede  lea     rdx, aLocale; "Locale"
0x1800b0ee5  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x1800b0eea  call    cs:__imp_RtlInitUnicodeString
0x1800b0ef1  nop     dword ptr [rax+rax+00h]
0x1800b0ef6  lea     rdx, aControlPanelIn; "Control Panel\\International"
0x1800b0efd  lea     rcx, [rbp+0A0h+var_120]; DestinationString
0x1800b0f01  call    cs:__imp_RtlInitUnicodeString
0x1800b0f08  nop     dword ptr [rax+rax+00h]
0x1800b0f0d  mov     rcx, [rsp+1A0h+Handle]
0x1800b0f12  lea     rax, [rbp+0A0h+var_120]
0x1800b0f16  mov     [rsp+1A0h+ObjectAttributes.RootDirectory], rcx
0x1800b0f1b  xorps   xmm0, xmm0
0x1800b0f1e  mov     [rsp+1A0h+ObjectAttributes.ObjectName], rax
0x1800b0f23  mov     [rsp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x1800b0f2b  mov     [rsp+1A0h+ObjectAttributes.Attributes], 640h
0x1800b0f33  movdqu  xmmword ptr [rsp+1A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b0f39  test    edi, edi
0x1800b0f3b  jz      loc_1800B1010
0x1800b0f41  lea     r8, [rsp+1A0h+ObjectAttributes]; ObjectAttributes
0x1800b0f46  mov     edx, 40000000h; DesiredAccess
0x1800b0f4b  lea     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x1800b0f50  call    cs:__imp_NtOpenKey
0x1800b0f57  nop     dword ptr [rax+rax+00h]
0x1800b0f5c  mov     ebx, eax
0x1800b0f5e  test    eax, eax
0x1800b0f60  js      loc_1800B100B
0x1800b0f66  call    cs:__imp_RtlIsMultiSessionSku
0x1800b0f6d  nop     dword ptr [rax+rax+00h]
0x1800b0f72  test    al, al
0x1800b0f74  jnz     short loc_1800B0F8E
0x1800b0f76  mov     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x1800b0f7b  lea     rdx, [rsp+1A0h+DestinationString]; ValueName
0x1800b0f80  call    cs:__imp_NtDeleteValueKey
0x1800b0f87  nop     dword ptr [rax+rax+00h]
0x1800b0f8c  jmp     short loc_1800B0FFA
0x1800b0f8e  xor     eax, eax
0x1800b0f90  lea     r8, [rbp+0A0h+var_102]
0x1800b0f94  mov     [rbp+0A0h+var_100], ax
0x1800b0f98  mov     eax, 30h ; '0'
0x1800b0f9d  lea     rdx, [r8-2]
0x1800b0fa1  mov     ecx, edi
0x1800b0fa3  and     ecx, 0Fh
0x1800b0fa6  cmp     ecx, 9
0x1800b0fa9  lea     r9d, [rax+7]
0x1800b0fad  cmova   ax, r9w
0x1800b0fb2  shr     edi, 4
0x1800b0fb5  add     ax, cx
0x1800b0fb8  mov     [r8], ax
0x1800b0fbc  lea     rax, [rbp+0A0h+var_110]
0x1800b0fc0  mov     r8, rdx
0x1800b0fc3  cmp     rdx, rax
0x1800b0fc6  jnb     short loc_1800B0F98
0x1800b0fc8  mov     rcx, [rsp+1A0h+KeyHandle]; KeyHandle
0x1800b0fcd  lea     rax, [rbp+0A0h+var_110]
0x1800b0fd1  mov     [rsp+1A0h+DataSize], 12h; DataSize
0x1800b0fd9  lea     rdx, [rsp+1A0h+DestinationString]; ValueName
0x1800b0fde  mov     r9d, 1; Type
0x1800b0fe4  mov     [rsp+1A0h+Data], rax; Data
0x1800b0fe9  xor     r8d, r8d; TitleIndex
0x1800b0fec  call    cs:__imp_NtSetValueKey
0x1800b0ff3  nop     dword ptr [rax+rax+00h]
0x1800b0ff8  mov     ebx, eax
0x1800b0ffa  mov     rcx, [rsp+1A0h+KeyHandle]; Handle
0x1800b0fff  call    cs:__imp_NtClose
0x1800b1006  nop     dword ptr [rax+rax+00h]
0x1800b100b  mov     rcx, [rsp+1A0h+Handle]; Handle
0x1800b1010  test    rcx, rcx
0x1800b1013  jz      short loc_1800B1021
0x1800b1015  call    cs:__imp_NtClose
0x1800b101c  nop     dword ptr [rax+rax+00h]
0x1800b1021  mov     eax, ebx
0x1800b1023  mov     rcx, [rbp+0A0h+var_10]
0x1800b102a  xor     rcx, rsp; StackCookie
0x1800b102d  call    __security_check_cookie
0x1800b1032  lea     r11, [rsp+1A0h+var_s0]
0x1800b103a  mov     rbx, [r11+10h]
0x1800b103e  mov     rdi, [r11+18h]
0x1800b1042  mov     rsp, r11
0x1800b1045  pop     rbp
0x1800b1046  retn
```
