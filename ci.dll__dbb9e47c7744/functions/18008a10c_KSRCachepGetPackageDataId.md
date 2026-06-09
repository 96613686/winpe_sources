# KSRCachepGetPackageDataId

- ea: `0x18008a10c`
- end: `0x18008a292`
- name: `KSRCachepGetPackageDataId`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089b88`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18008a10c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18008a24f`
- `ntoskrnl!ZwClose` at `0x18008a264`
- `ntoskrnl!ZwClose` at `0x18008a24f`
- `ntoskrnl!ZwClose` at `0x18008a264`
- `ntoskrnl!ZwOpenKey` at `0x18008a191`
- `ntoskrnl!ZwOpenKey` at `0x18008a1d6`
- `ntoskrnl!ZwOpenKey` at `0x18008a191`
- `ntoskrnl!ZwOpenKey` at `0x18008a1d6`
- `ntoskrnl!ZwEnumerateKey` at `0x18008a206`
- `ntoskrnl!ZwEnumerateKey` at `0x18008a206`

## string_xrefs

- `0x18008a140`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Index\PackageFullName`

## pseudocode

```c
__int64 __fastcall KSRCachepGetPackageDataId(struct _UNICODE_STRING *a1, __int64 a2)
{
  NTSTATUS v4; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v9[2]; // [rsp+48h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-31h] BYREF
  _BYTE KeyInformation[12]; // [rsp+88h] [rbp-1h] BYREF
  unsigned int Size; // [rsp+94h] [rbp+Bh]
  size_t Size_4; // [rsp+98h] [rbp+Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v9[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\Package\\"
           "Index\\PackageFullName";
  v9[0] = 15859952;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
  Handle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
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
        if ( Size > 0x24 || *(unsigned __int16 *)(a2 + 2) < Size )
        {
          v4 = -1073741789;
        }
        else
        {
          memmove(*(void **)(a2 + 8), &Size_4, Size);
          *(_WORD *)a2 = Size;
        }
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008a10c  mov     [rsp-8+arg_10], rbx
0x18008a111  push    rbp
0x18008a112  push    rsi
0x18008a113  push    rdi
0x18008a114  lea     rbp, [rsp-47h]
0x18008a119  sub     rsp, 0D0h
0x18008a120  mov     rax, cs:__security_cookie
0x18008a127  xor     rax, rsp
0x18008a12a  mov     [rbp+57h+var_18], rax
0x18008a12e  xor     eax, eax
0x18008a130  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008a138  mov     [rbp+57h+KeyHandle], rax
0x18008a13c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008a140  lea     rax, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008a147  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a14f  mov     [rbp+57h+var_90], rax
0x18008a153  mov     rdi, rdx
0x18008a156  lea     rax, [rbp+57h+var_98]
0x18008a15a  mov     [rbp+57h+var_98], 0F200F0h
0x18008a162  mov     rsi, rcx
0x18008a165  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008a169  xorps   xmm0, xmm0
0x18008a16c  mov     [rbp+57h+Handle], 0
0x18008a174  mov     edx, 20019h; DesiredAccess
0x18008a179  mov     [rbp+57h+var_B0], 0
0x18008a180  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008a184  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008a18c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a191  call    cs:__imp_ZwOpenKey
0x18008a198  nop     dword ptr [rax+rax+00h]
0x18008a19d  mov     ebx, eax
0x18008a19f  test    eax, eax
0x18008a1a1  js      loc_18008A246
0x18008a1a7  mov     rax, [rbp+57h+KeyHandle]
0x18008a1ab  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008a1af  xorps   xmm0, xmm0
0x18008a1b2  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008a1b6  mov     edx, 20019h; DesiredAccess
0x18008a1bb  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008a1c2  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18008a1c6  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a1cd  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a1d2  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18008a1d6  call    cs:__imp_ZwOpenKey
0x18008a1dd  nop     dword ptr [rax+rax+00h]
0x18008a1e2  mov     ebx, eax
0x18008a1e4  test    eax, eax
0x18008a1e6  js      short loc_18008A246
0x18008a1e8  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008a1ec  lea     rax, [rbp+57h+var_B0]
0x18008a1f0  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x18008a1f5  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x18008a1f9  xor     r8d, r8d; KeyInformationClass
0x18008a1fc  mov     [rsp+0E0h+Length], 3Ah ; ':'; Length
0x18008a204  xor     edx, edx; Index
0x18008a206  call    cs:__imp_ZwEnumerateKey
0x18008a20d  nop     dword ptr [rax+rax+00h]
0x18008a212  mov     ebx, eax
0x18008a214  test    eax, eax
0x18008a216  js      short loc_18008A246
0x18008a218  mov     ecx, dword ptr [rbp+57h+Size]
0x18008a21b  cmp     ecx, 24h ; '$'
0x18008a21e  jbe     short loc_18008A227
0x18008a220  mov     ebx, 0C0000023h
0x18008a225  jmp     short loc_18008A246
0x18008a227  movzx   eax, word ptr [rdi+2]
0x18008a22b  cmp     eax, ecx
0x18008a22d  jb      short loc_18008A220
0x18008a22f  mov     r8, rcx; Size
0x18008a232  lea     rdx, [rbp+57h+Size+4]; Src
0x18008a236  mov     rcx, [rdi+8]; void *
0x18008a23a  call    memmove
0x18008a23f  movzx   eax, word ptr [rbp+57h+Size]
0x18008a243  mov     [rdi], ax
0x18008a246  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008a24a  test    rcx, rcx
0x18008a24d  jz      short loc_18008A25B
0x18008a24f  call    cs:__imp_ZwClose
0x18008a256  nop     dword ptr [rax+rax+00h]
0x18008a25b  mov     rcx, [rbp+57h+Handle]; Handle
0x18008a25f  test    rcx, rcx
0x18008a262  jz      short loc_18008A270
0x18008a264  call    cs:__imp_ZwClose
0x18008a26b  nop     dword ptr [rax+rax+00h]
0x18008a270  mov     eax, ebx
0x18008a272  mov     rcx, [rbp+57h+var_18]
0x18008a276  xor     rcx, rsp; StackCookie
0x18008a279  call    __security_check_cookie
0x18008a27e  mov     rbx, [rsp+0E0h+arg_10]
0x18008a286  add     rsp, 0D0h
0x18008a28d  pop     rdi
0x18008a28e  pop     rsi
0x18008a28f  pop     rbp
0x18008a290  retn
```
