# KSRCachepGetPackageDataKey

- ea: `0x18008acb4`
- end: `0x18008af2e`
- name: `KSRCachepGetPackageDataKey`
- size: `634`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008a4c4`
- `0x18008a840`

## callees

- `0x18002c0d0`
- `0x18008acb4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18008aec0`
- `ntoskrnl!ZwClose` at `0x18008aed5`
- `ntoskrnl!ZwClose` at `0x18008aeea`
- `ntoskrnl!ZwClose` at `0x18008af00`
- `ntoskrnl!ZwClose` at `0x18008aec0`
- `ntoskrnl!ZwClose` at `0x18008aed5`
- `ntoskrnl!ZwClose` at `0x18008aeea`
- `ntoskrnl!ZwClose` at `0x18008af00`
- `ntoskrnl!ZwOpenKey` at `0x18008ad66`
- `ntoskrnl!ZwOpenKey` at `0x18008adb1`
- `ntoskrnl!ZwOpenKey` at `0x18008adf8`
- `ntoskrnl!ZwOpenKey` at `0x18008ae94`
- `ntoskrnl!ZwOpenKey` at `0x18008ad66`
- `ntoskrnl!ZwOpenKey` at `0x18008adb1`
- `ntoskrnl!ZwOpenKey` at `0x18008adf8`
- `ntoskrnl!ZwOpenKey` at `0x18008ae94`
- `ntoskrnl!ZwEnumerateKey` at `0x18008ae2c`
- `ntoskrnl!ZwEnumerateKey` at `0x18008ae2c`

## string_xrefs

- `0x18008ad06`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Data`
- `0x18008acef`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Index\PackageFullName`

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
0x18008acb4  mov     [rsp-8+arg_10], rbx
0x18008acb9  push    rbp
0x18008acba  push    rsi
0x18008acbb  push    rdi
0x18008acbc  lea     rbp, [rsp-47h]
0x18008acc1  sub     rsp, 100h
0x18008acc8  mov     rax, cs:__security_cookie
0x18008accf  xor     rax, rsp
0x18008acd2  mov     [rbp+57h+var_18], rax
0x18008acd6  xor     eax, eax
0x18008acd8  mov     qword ptr [rdx], 0
0x18008acdf  mov     [rbp+57h+KeyHandle], rax
0x18008ace3  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18008ace8  mov     [rbp+57h+var_90], rax
0x18008acec  xorps   xmm0, xmm0
0x18008acef  lea     rax, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008acf6  mov     qword ptr [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x18008acff  mov     [rbp+57h+var_80], rax
0x18008ad03  mov     rdi, rdx
0x18008ad06  lea     rax, aRegistryMachin_23; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008ad0d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008ad15  mov     [rbp+57h+var_70], rax
0x18008ad19  mov     rsi, rcx
0x18008ad1c  lea     rax, [rbp+57h+var_88]
0x18008ad20  mov     [rbp+57h+var_88], 0F200F0h
0x18008ad28  mov     edx, 20019h; DesiredAccess
0x18008ad2d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008ad31  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008ad35  mov     [rbp+57h+var_78], 0D000CEh
0x18008ad3d  mov     [rbp+57h+Handle], 0
0x18008ad45  mov     [rbp+57h+var_A8], 0
0x18008ad4c  movups  [rbp+57h+var_68], xmm0
0x18008ad50  mov     [rsp+110h+var_E0], 0
0x18008ad59  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008ad61  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008ad66  call    cs:__imp_ZwOpenKey
0x18008ad6d  nop     dword ptr [rax+rax+00h]
0x18008ad72  mov     ebx, eax
0x18008ad74  test    eax, eax
0x18008ad76  js      loc_18008AEB7
0x18008ad7c  lea     rax, [rbp+57h+var_78]
0x18008ad80  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x18008ad88  xorps   xmm0, xmm0
0x18008ad8b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008ad8f  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18008ad94  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008ad9c  mov     edx, 20019h; DesiredAccess
0x18008ada1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008ada8  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x18008adac  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008adb1  call    cs:__imp_ZwOpenKey
0x18008adb8  nop     dword ptr [rax+rax+00h]
0x18008adbd  mov     ebx, eax
0x18008adbf  test    eax, eax
0x18008adc1  js      loc_18008AEB7
0x18008adc7  mov     rax, [rbp+57h+KeyHandle]
0x18008adcb  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18008add0  xorps   xmm0, xmm0
0x18008add3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008add7  mov     edx, 20019h; DesiredAccess
0x18008addc  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x18008ade4  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18008ade8  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008adef  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008adf4  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18008adf8  call    cs:__imp_ZwOpenKey
0x18008adff  nop     dword ptr [rax+rax+00h]
0x18008ae04  mov     ebx, eax
0x18008ae06  test    eax, eax
0x18008ae08  js      loc_18008AEB7
0x18008ae0e  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008ae12  lea     rax, [rbp+57h+var_A8]
0x18008ae16  mov     [rsp+110h+ResultLength], rax; ResultLength
0x18008ae1b  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x18008ae1f  xor     r8d, r8d; KeyInformationClass
0x18008ae22  mov     [rsp+110h+Length], 3Ah ; ':'; Length
0x18008ae2a  xor     edx, edx; Index
0x18008ae2c  call    cs:__imp_ZwEnumerateKey
0x18008ae33  nop     dword ptr [rax+rax+00h]
0x18008ae38  mov     ebx, eax
0x18008ae3a  test    eax, eax
0x18008ae3c  js      short loc_18008AEB7
0x18008ae3e  mov     rax, [rbp+57h+var_4C]
0x18008ae42  cmp     eax, 24h ; '$'
0x18008ae45  jbe     short loc_18008AE4E
0x18008ae47  mov     ebx, 0C0000023h
0x18008ae4c  jmp     short loc_18008AEB7
0x18008ae4e  mov     word ptr [rbp+57h+var_68], ax
0x18008ae52  lea     rcx, [rbp+57h+var_4C+4]
0x18008ae56  mov     word ptr [rbp+57h+var_68+2], ax
0x18008ae5a  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18008ae5f  mov     rax, [rbp+57h+var_90]
0x18008ae63  xorps   xmm0, xmm0
0x18008ae66  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008ae6a  mov     edx, 20019h; DesiredAccess
0x18008ae6f  lea     rax, [rbp+57h+var_68]
0x18008ae73  mov     qword ptr [rbp+57h+var_68+8], rcx
0x18008ae77  lea     rcx, [rsp+110h+var_E0]; KeyHandle
0x18008ae7c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008ae80  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x18008ae88  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008ae8f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008ae94  call    cs:__imp_ZwOpenKey
0x18008ae9b  nop     dword ptr [rax+rax+00h]
0x18008aea0  mov     ebx, eax
0x18008aea2  test    eax, eax
0x18008aea4  js      short loc_18008AEB7
0x18008aea6  mov     rax, [rsp+110h+var_E0]
0x18008aeab  mov     [rdi], rax
0x18008aeae  mov     [rsp+110h+var_E0], 0
0x18008aeb7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008aebb  test    rcx, rcx
0x18008aebe  jz      short loc_18008AECC
0x18008aec0  call    cs:__imp_ZwClose
0x18008aec7  nop     dword ptr [rax+rax+00h]
0x18008aecc  mov     rcx, [rbp+57h+Handle]; Handle
0x18008aed0  test    rcx, rcx
0x18008aed3  jz      short loc_18008AEE1
0x18008aed5  call    cs:__imp_ZwClose
0x18008aedc  nop     dword ptr [rax+rax+00h]
0x18008aee1  mov     rcx, [rbp+57h+var_90]; Handle
0x18008aee5  test    rcx, rcx
0x18008aee8  jz      short loc_18008AEF6
0x18008aeea  call    cs:__imp_ZwClose
0x18008aef1  nop     dword ptr [rax+rax+00h]
0x18008aef6  mov     rcx, [rsp+110h+var_E0]; Handle
0x18008aefb  test    rcx, rcx
0x18008aefe  jz      short loc_18008AF0C
0x18008af00  call    cs:__imp_ZwClose
0x18008af07  nop     dword ptr [rax+rax+00h]
0x18008af0c  mov     eax, ebx
0x18008af0e  mov     rcx, [rbp+57h+var_18]
0x18008af12  xor     rcx, rsp; StackCookie
0x18008af15  call    __security_check_cookie
0x18008af1a  mov     rbx, [rsp+110h+arg_10]
0x18008af22  add     rsp, 100h
0x18008af29  pop     rdi
0x18008af2a  pop     rsi
0x18008af2b  pop     rbp
0x18008af2c  retn
```
