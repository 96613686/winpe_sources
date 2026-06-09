# KSRCachepGetPackageDataKey

- ea: `0x18008a298`
- end: `0x18008a512`
- name: `KSRCachepGetPackageDataKey`
- size: `634`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089aa8`
- `0x180089e24`

## callees

- `0x18002bf20`
- `0x18008a298`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18008a4a4`
- `ntoskrnl!ZwClose` at `0x18008a4b9`
- `ntoskrnl!ZwClose` at `0x18008a4ce`
- `ntoskrnl!ZwClose` at `0x18008a4e4`
- `ntoskrnl!ZwClose` at `0x18008a4a4`
- `ntoskrnl!ZwClose` at `0x18008a4b9`
- `ntoskrnl!ZwClose` at `0x18008a4ce`
- `ntoskrnl!ZwClose` at `0x18008a4e4`
- `ntoskrnl!ZwOpenKey` at `0x18008a34a`
- `ntoskrnl!ZwOpenKey` at `0x18008a395`
- `ntoskrnl!ZwOpenKey` at `0x18008a3dc`
- `ntoskrnl!ZwOpenKey` at `0x18008a478`
- `ntoskrnl!ZwOpenKey` at `0x18008a34a`
- `ntoskrnl!ZwOpenKey` at `0x18008a395`
- `ntoskrnl!ZwOpenKey` at `0x18008a3dc`
- `ntoskrnl!ZwOpenKey` at `0x18008a478`
- `ntoskrnl!ZwEnumerateKey` at `0x18008a410`
- `ntoskrnl!ZwEnumerateKey` at `0x18008a410`

## string_xrefs

- `0x18008a2ea`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Data`
- `0x18008a2d3`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Index\PackageFullName`

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
0x18008a298  mov     [rsp-8+arg_10], rbx
0x18008a29d  push    rbp
0x18008a29e  push    rsi
0x18008a29f  push    rdi
0x18008a2a0  lea     rbp, [rsp-47h]
0x18008a2a5  sub     rsp, 100h
0x18008a2ac  mov     rax, cs:__security_cookie
0x18008a2b3  xor     rax, rsp
0x18008a2b6  mov     [rbp+57h+var_18], rax
0x18008a2ba  xor     eax, eax
0x18008a2bc  mov     qword ptr [rdx], 0
0x18008a2c3  mov     [rbp+57h+KeyHandle], rax
0x18008a2c7  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18008a2cc  mov     [rbp+57h+var_90], rax
0x18008a2d0  xorps   xmm0, xmm0
0x18008a2d3  lea     rax, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008a2da  mov     qword ptr [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x18008a2e3  mov     [rbp+57h+var_80], rax
0x18008a2e7  mov     rdi, rdx
0x18008a2ea  lea     rax, aRegistryMachin_23; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008a2f1  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a2f9  mov     [rbp+57h+var_70], rax
0x18008a2fd  mov     rsi, rcx
0x18008a300  lea     rax, [rbp+57h+var_88]
0x18008a304  mov     [rbp+57h+var_88], 0F200F0h
0x18008a30c  mov     edx, 20019h; DesiredAccess
0x18008a311  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008a315  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008a319  mov     [rbp+57h+var_78], 0D000CEh
0x18008a321  mov     [rbp+57h+Handle], 0
0x18008a329  mov     [rbp+57h+var_A8], 0
0x18008a330  movups  [rbp+57h+var_68], xmm0
0x18008a334  mov     [rsp+110h+var_E0], 0
0x18008a33d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008a345  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a34a  call    cs:__imp_ZwOpenKey
0x18008a351  nop     dword ptr [rax+rax+00h]
0x18008a356  mov     ebx, eax
0x18008a358  test    eax, eax
0x18008a35a  js      loc_18008A49B
0x18008a360  lea     rax, [rbp+57h+var_78]
0x18008a364  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x18008a36c  xorps   xmm0, xmm0
0x18008a36f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008a373  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18008a378  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008a380  mov     edx, 20019h; DesiredAccess
0x18008a385  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a38c  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x18008a390  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a395  call    cs:__imp_ZwOpenKey
0x18008a39c  nop     dword ptr [rax+rax+00h]
0x18008a3a1  mov     ebx, eax
0x18008a3a3  test    eax, eax
0x18008a3a5  js      loc_18008A49B
0x18008a3ab  mov     rax, [rbp+57h+KeyHandle]
0x18008a3af  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18008a3b4  xorps   xmm0, xmm0
0x18008a3b7  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008a3bb  mov     edx, 20019h; DesiredAccess
0x18008a3c0  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x18008a3c8  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18008a3cc  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a3d3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a3d8  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18008a3dc  call    cs:__imp_ZwOpenKey
0x18008a3e3  nop     dword ptr [rax+rax+00h]
0x18008a3e8  mov     ebx, eax
0x18008a3ea  test    eax, eax
0x18008a3ec  js      loc_18008A49B
0x18008a3f2  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008a3f6  lea     rax, [rbp+57h+var_A8]
0x18008a3fa  mov     [rsp+110h+ResultLength], rax; ResultLength
0x18008a3ff  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x18008a403  xor     r8d, r8d; KeyInformationClass
0x18008a406  mov     [rsp+110h+Length], 3Ah ; ':'; Length
0x18008a40e  xor     edx, edx; Index
0x18008a410  call    cs:__imp_ZwEnumerateKey
0x18008a417  nop     dword ptr [rax+rax+00h]
0x18008a41c  mov     ebx, eax
0x18008a41e  test    eax, eax
0x18008a420  js      short loc_18008A49B
0x18008a422  mov     rax, [rbp+57h+var_4C]
0x18008a426  cmp     eax, 24h ; '$'
0x18008a429  jbe     short loc_18008A432
0x18008a42b  mov     ebx, 0C0000023h
0x18008a430  jmp     short loc_18008A49B
0x18008a432  mov     word ptr [rbp+57h+var_68], ax
0x18008a436  lea     rcx, [rbp+57h+var_4C+4]
0x18008a43a  mov     word ptr [rbp+57h+var_68+2], ax
0x18008a43e  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x18008a443  mov     rax, [rbp+57h+var_90]
0x18008a447  xorps   xmm0, xmm0
0x18008a44a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008a44e  mov     edx, 20019h; DesiredAccess
0x18008a453  lea     rax, [rbp+57h+var_68]
0x18008a457  mov     qword ptr [rbp+57h+var_68+8], rcx
0x18008a45b  lea     rcx, [rsp+110h+var_E0]; KeyHandle
0x18008a460  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008a464  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x18008a46c  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a473  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a478  call    cs:__imp_ZwOpenKey
0x18008a47f  nop     dword ptr [rax+rax+00h]
0x18008a484  mov     ebx, eax
0x18008a486  test    eax, eax
0x18008a488  js      short loc_18008A49B
0x18008a48a  mov     rax, [rsp+110h+var_E0]
0x18008a48f  mov     [rdi], rax
0x18008a492  mov     [rsp+110h+var_E0], 0
0x18008a49b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008a49f  test    rcx, rcx
0x18008a4a2  jz      short loc_18008A4B0
0x18008a4a4  call    cs:__imp_ZwClose
0x18008a4ab  nop     dword ptr [rax+rax+00h]
0x18008a4b0  mov     rcx, [rbp+57h+Handle]; Handle
0x18008a4b4  test    rcx, rcx
0x18008a4b7  jz      short loc_18008A4C5
0x18008a4b9  call    cs:__imp_ZwClose
0x18008a4c0  nop     dword ptr [rax+rax+00h]
0x18008a4c5  mov     rcx, [rbp+57h+var_90]; Handle
0x18008a4c9  test    rcx, rcx
0x18008a4cc  jz      short loc_18008A4DA
0x18008a4ce  call    cs:__imp_ZwClose
0x18008a4d5  nop     dword ptr [rax+rax+00h]
0x18008a4da  mov     rcx, [rsp+110h+var_E0]; Handle
0x18008a4df  test    rcx, rcx
0x18008a4e2  jz      short loc_18008A4F0
0x18008a4e4  call    cs:__imp_ZwClose
0x18008a4eb  nop     dword ptr [rax+rax+00h]
0x18008a4f0  mov     eax, ebx
0x18008a4f2  mov     rcx, [rbp+57h+var_18]
0x18008a4f6  xor     rcx, rsp; StackCookie
0x18008a4f9  call    __security_check_cookie
0x18008a4fe  mov     rbx, [rsp+110h+arg_10]
0x18008a506  add     rsp, 100h
0x18008a50d  pop     rdi
0x18008a50e  pop     rsi
0x18008a50f  pop     rbp
0x18008a510  retn
```
