# KSRCachepGetPackageDataKey

- ea: `0x180088c68`
- end: `0x180088ee2`
- name: `KSRCachepGetPackageDataKey`
- size: `634`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180088478`
- `0x1800887f4`

## callees

- `0x18002bef0`
- `0x180088c68`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180088e74`
- `ntoskrnl!ZwClose` at `0x180088e89`
- `ntoskrnl!ZwClose` at `0x180088e9e`
- `ntoskrnl!ZwClose` at `0x180088eb4`
- `ntoskrnl!ZwClose` at `0x180088e74`
- `ntoskrnl!ZwClose` at `0x180088e89`
- `ntoskrnl!ZwClose` at `0x180088e9e`
- `ntoskrnl!ZwClose` at `0x180088eb4`
- `ntoskrnl!ZwOpenKey` at `0x180088d1a`
- `ntoskrnl!ZwOpenKey` at `0x180088d65`
- `ntoskrnl!ZwOpenKey` at `0x180088dac`
- `ntoskrnl!ZwOpenKey` at `0x180088e48`
- `ntoskrnl!ZwOpenKey` at `0x180088d1a`
- `ntoskrnl!ZwOpenKey` at `0x180088d65`
- `ntoskrnl!ZwOpenKey` at `0x180088dac`
- `ntoskrnl!ZwOpenKey` at `0x180088e48`
- `ntoskrnl!ZwEnumerateKey` at `0x180088de0`
- `ntoskrnl!ZwEnumerateKey` at `0x180088de0`

## string_xrefs

- `0x180088ca3`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Index\PackageFullName`
- `0x180088cba`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Data`

## pseudocode

```c
__int64 __fastcall KSRCachepGetPackageDataKey(struct _UNICODE_STRING *a1, HANDLE *a2)
{
  NTSTATUS v4; // ebx
  HANDLE v6; // [rsp+30h] [rbp-89h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-81h] BYREF
  ULONG ResultLength; // [rsp+68h] [rbp-51h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-41h] BYREF
  HANDLE v11; // [rsp+80h] [rbp-39h] BYREF
  _QWORD v12[2]; // [rsp+88h] [rbp-31h] BYREF
  _QWORD v13[2]; // [rsp+98h] [rbp-21h] BYREF
  __int128 v14; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE KeyInformation[12]; // [rsp+B8h] [rbp-1h] BYREF
  unsigned int v16; // [rsp+C4h] [rbp+Bh]
  __int64 v17; // [rsp+C8h] [rbp+Fh] BYREF

  *a2 = 0;
  KeyHandle = 0;
  v11 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v12[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\Package\\"
            "Index\\PackageFullName";
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v13[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\Package\\Data";
  v12[0] = 15859952;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
  v13[0] = 13631694;
  Handle = 0;
  ResultLength = 0;
  v14 = 0;
  v6 = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v13;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = ZwOpenKey(&v11, 0x20019u, &ObjectAttributes);
    if ( v4 >= 0 )
    {
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ObjectAttributes.ObjectName = a1;
      v4 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
      if ( v4 >= 0 )
      {
        v4 = ZwEnumerateKey(Handle, 0, KeyBasicInformation, KeyInformation, 0x3Au, &ResultLength);
        if ( v4 >= 0 )
        {
          if ( v16 <= 0x24 )
          {
            LOWORD(v14) = v16;
            WORD1(v14) = v16;
            ObjectAttributes.RootDirectory = v11;
            *((_QWORD *)&v14 + 1) = &v17;
            ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
            ObjectAttributes.Length = 48;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v4 = ZwOpenKey(&v6, 0x20019u, &ObjectAttributes);
            if ( v4 >= 0 )
            {
              *a2 = v6;
              v6 = 0;
            }
          }
          else
          {
            v4 = -1073741789;
          }
        }
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  if ( v11 )
    ZwClose(v11);
  if ( v6 )
    ZwClose(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180088c68  mov     [rsp-8+arg_10], rbx
0x180088c6d  push    rbp
0x180088c6e  push    rsi
0x180088c6f  push    rdi
0x180088c70  lea     rbp, [rsp-47h]
0x180088c75  sub     rsp, 100h
0x180088c7c  mov     rax, cs:__security_cookie
0x180088c83  xor     rax, rsp
0x180088c86  mov     [rbp+57h+var_18], rax
0x180088c8a  xor     eax, eax
0x180088c8c  mov     qword ptr [rdx], 0
0x180088c93  mov     [rbp+57h+KeyHandle], rax
0x180088c97  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x180088c9c  mov     [rbp+57h+var_90], rax
0x180088ca0  xorps   xmm0, xmm0
0x180088ca3  lea     rax, aRegistryMachin_22; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180088caa  mov     qword ptr [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x180088cb3  mov     [rbp+57h+var_80], rax
0x180088cb7  mov     rdi, rdx
0x180088cba  lea     rax, aRegistryMachin_24; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180088cc1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180088cc9  mov     [rbp+57h+var_70], rax
0x180088ccd  mov     rsi, rcx
0x180088cd0  lea     rax, [rbp+57h+var_88]
0x180088cd4  mov     [rbp+57h+var_88], 0F200F0h
0x180088cdc  mov     edx, 20019h; DesiredAccess
0x180088ce1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180088ce5  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180088ce9  mov     [rbp+57h+var_78], 0D000CEh
0x180088cf1  mov     [rbp+57h+Handle], 0
0x180088cf9  mov     [rbp+57h+var_A8], 0
0x180088d00  movups  [rbp+57h+var_68], xmm0
0x180088d04  mov     [rsp+110h+var_E0], 0
0x180088d0d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180088d15  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088d1a  call    cs:__imp_ZwOpenKey
0x180088d21  nop     dword ptr [rax+rax+00h]
0x180088d26  mov     ebx, eax
0x180088d28  test    eax, eax
0x180088d2a  js      loc_180088E6B
0x180088d30  lea     rax, [rbp+57h+var_78]
0x180088d34  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x180088d3c  xorps   xmm0, xmm0
0x180088d3f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180088d43  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x180088d48  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180088d50  mov     edx, 20019h; DesiredAccess
0x180088d55  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180088d5c  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x180088d60  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088d65  call    cs:__imp_ZwOpenKey
0x180088d6c  nop     dword ptr [rax+rax+00h]
0x180088d71  mov     ebx, eax
0x180088d73  test    eax, eax
0x180088d75  js      loc_180088E6B
0x180088d7b  mov     rax, [rbp+57h+KeyHandle]
0x180088d7f  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x180088d84  xorps   xmm0, xmm0
0x180088d87  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180088d8b  mov     edx, 20019h; DesiredAccess
0x180088d90  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x180088d98  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180088d9c  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180088da3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088da8  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180088dac  call    cs:__imp_ZwOpenKey
0x180088db3  nop     dword ptr [rax+rax+00h]
0x180088db8  mov     ebx, eax
0x180088dba  test    eax, eax
0x180088dbc  js      loc_180088E6B
0x180088dc2  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180088dc6  lea     rax, [rbp+57h+var_A8]
0x180088dca  mov     [rsp+110h+ResultLength], rax; ResultLength
0x180088dcf  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x180088dd3  xor     r8d, r8d; KeyInformationClass
0x180088dd6  mov     [rsp+110h+Length], 3Ah ; ':'; Length
0x180088dde  xor     edx, edx; Index
0x180088de0  call    cs:__imp_ZwEnumerateKey
0x180088de7  nop     dword ptr [rax+rax+00h]
0x180088dec  mov     ebx, eax
0x180088dee  test    eax, eax
0x180088df0  js      short loc_180088E6B
0x180088df2  mov     rax, [rbp+57h+var_4C]
0x180088df6  cmp     eax, 24h ; '$'
0x180088df9  jbe     short loc_180088E02
0x180088dfb  mov     ebx, 0C0000023h
0x180088e00  jmp     short loc_180088E6B
0x180088e02  mov     word ptr [rbp+57h+var_68], ax
0x180088e06  lea     rcx, [rbp+57h+var_4C+4]
0x180088e0a  mov     word ptr [rbp+57h+var_68+2], ax
0x180088e0e  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x180088e13  mov     rax, [rbp+57h+var_90]
0x180088e17  xorps   xmm0, xmm0
0x180088e1a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180088e1e  mov     edx, 20019h; DesiredAccess
0x180088e23  lea     rax, [rbp+57h+var_68]
0x180088e27  mov     qword ptr [rbp+57h+var_68+8], rcx
0x180088e2b  lea     rcx, [rsp+110h+var_E0]; KeyHandle
0x180088e30  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180088e34  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x180088e3c  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180088e43  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088e48  call    cs:__imp_ZwOpenKey
0x180088e4f  nop     dword ptr [rax+rax+00h]
0x180088e54  mov     ebx, eax
0x180088e56  test    eax, eax
0x180088e58  js      short loc_180088E6B
0x180088e5a  mov     rax, [rsp+110h+var_E0]
0x180088e5f  mov     [rdi], rax
0x180088e62  mov     [rsp+110h+var_E0], 0
0x180088e6b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180088e6f  test    rcx, rcx
0x180088e72  jz      short loc_180088E80
0x180088e74  call    cs:__imp_ZwClose
0x180088e7b  nop     dword ptr [rax+rax+00h]
0x180088e80  mov     rcx, [rbp+57h+Handle]; Handle
0x180088e84  test    rcx, rcx
0x180088e87  jz      short loc_180088E95
0x180088e89  call    cs:__imp_ZwClose
0x180088e90  nop     dword ptr [rax+rax+00h]
0x180088e95  mov     rcx, [rbp+57h+var_90]; Handle
0x180088e99  test    rcx, rcx
0x180088e9c  jz      short loc_180088EAA
0x180088e9e  call    cs:__imp_ZwClose
0x180088ea5  nop     dword ptr [rax+rax+00h]
0x180088eaa  mov     rcx, [rsp+110h+var_E0]; Handle
0x180088eaf  test    rcx, rcx
0x180088eb2  jz      short loc_180088EC0
0x180088eb4  call    cs:__imp_ZwClose
0x180088ebb  nop     dword ptr [rax+rax+00h]
0x180088ec0  mov     eax, ebx
0x180088ec2  mov     rcx, [rbp+57h+var_18]
0x180088ec6  xor     rcx, rsp; StackCookie
0x180088ec9  call    __security_check_cookie
0x180088ece  mov     rbx, [rsp+110h+arg_10]
0x180088ed6  add     rsp, 100h
0x180088edd  pop     rdi
0x180088ede  pop     rsi
0x180088edf  pop     rbp
0x180088ee0  retn
```
