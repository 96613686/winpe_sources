# KSRCachepGetSupplierPackageDataId

- ea: `0x18008b1e0`
- end: `0x18008b3ab`
- name: `KSRCachepGetSupplierPackageDataId`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008a5a4`

## callees

- `0x18002c0d0`
- `0x18008b1e0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18008b2f2`
- `ntoskrnl!ZwQueryValueKey` at `0x18008b2f2`
- `ntoskrnl!ZwClose` at `0x18008b363`
- `ntoskrnl!ZwClose` at `0x18008b378`
- `ntoskrnl!ZwClose` at `0x18008b363`
- `ntoskrnl!ZwClose` at `0x18008b378`
- `ntoskrnl!ZwOpenKey` at `0x18008b277`
- `ntoskrnl!ZwOpenKey` at `0x18008b2bc`
- `ntoskrnl!ZwOpenKey` at `0x18008b277`
- `ntoskrnl!ZwOpenKey` at `0x18008b2bc`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18008b329`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18008b329`

## string_xrefs

- `0x18008b213`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\DependencyGraph\Data`

## pseudocode

```c
__int64 __fastcall KSRCachepGetSupplierPackageDataId(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS v4; // ebx
  __int64 v5; // rax
  ULONG Length; // [rsp+30h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-41h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v10[2]; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-11h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+98h] [rbp+1Fh] BYREF
  int v14; // [rsp+9Ch] [rbp+23h]
  unsigned int v15; // [rsp+A0h] [rbp+27h]
  ULONG Value; // [rsp+A4h] [rbp+2Bh]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v10[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\DependencyGraph\\Data";
  v10[0] = 14680286;
  ValueName.Buffer = L"SupplierPackage";
  *(_QWORD *)&ValueName.Length = 2097182;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v10;
  KeyHandle = 0;
  Handle = 0;
  Length = 20;
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
      v4 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, Length, &Length);
      if ( v4 >= 0 )
      {
        if ( v14 == 4 && v15 >= 4 )
        {
          if ( a2->MaximumLength >= 0x12u )
          {
            v4 = RtlIntegerToUnicodeString(Value, 0x10u, a2);
            if ( v4 >= 0 )
            {
              v5 = -1;
              do
                ++v5;
              while ( a2->Buffer[v5] );
              a2->Length = 2 * v5;
            }
          }
          else
          {
            v4 = -1073741789;
          }
        }
        else
        {
          v4 = -1073741788;
        }
      }
    }
  }
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008b1e0  mov     [rsp-8+arg_10], rbx
0x18008b1e5  mov     [rsp-8+arg_18], rsi
0x18008b1ea  push    rbp
0x18008b1eb  push    rdi
0x18008b1ec  push    r14
0x18008b1ee  lea     rbp, [rsp-47h]
0x18008b1f3  sub     rsp, 0C0h
0x18008b1fa  mov     rax, cs:__security_cookie
0x18008b201  xor     rax, rsp
0x18008b204  mov     [rbp+57h+var_20], rax
0x18008b208  xor     r14d, r14d
0x18008b20b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008b213  lea     rax, aRegistryMachin_6; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008b21a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008b222  mov     [rbp+57h+var_80], rax
0x18008b226  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008b22a  lea     rax, aSupplierpackag; "SupplierPackage"
0x18008b231  mov     [rbp+57h+var_88], 0E000DEh
0x18008b239  mov     [rbp+57h+ValueName.Buffer], rax
0x18008b23d  mov     rdi, rdx
0x18008b240  lea     rax, [rbp+57h+var_88]
0x18008b244  mov     qword ptr [rbp+57h+ValueName.Length], 20001Eh
0x18008b24c  mov     rsi, rcx
0x18008b24f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008b253  xorps   xmm0, xmm0
0x18008b256  mov     [rbp+57h+KeyHandle], r14
0x18008b25a  mov     edx, 20019h; DesiredAccess
0x18008b25f  mov     [rbp+57h+Handle], r14
0x18008b263  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008b267  mov     [rbp+57h+var_A0], 14h
0x18008b26e  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x18008b272  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008b277  call    cs:__imp_ZwOpenKey
0x18008b27e  nop     dword ptr [rax+rax+00h]
0x18008b283  mov     ebx, eax
0x18008b285  test    eax, eax
0x18008b287  js      loc_18008B35A
0x18008b28d  mov     rax, [rbp+57h+KeyHandle]
0x18008b291  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008b295  xorps   xmm0, xmm0
0x18008b298  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008b29c  mov     edx, 20019h; DesiredAccess
0x18008b2a1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008b2a8  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18008b2ac  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008b2b3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008b2b8  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18008b2bc  call    cs:__imp_ZwOpenKey
0x18008b2c3  nop     dword ptr [rax+rax+00h]
0x18008b2c8  mov     ebx, eax
0x18008b2ca  test    eax, eax
0x18008b2cc  js      loc_18008B35A
0x18008b2d2  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008b2d6  lea     rax, [rbp+57h+var_A0]
0x18008b2da  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x18008b2df  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008b2e3  mov     eax, [rbp+57h+var_A0]
0x18008b2e6  lea     r8d, [r14+2]; KeyValueInformationClass
0x18008b2ea  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18008b2ee  mov     [rsp+0D0h+Length], eax; Length
0x18008b2f2  call    cs:__imp_ZwQueryValueKey
0x18008b2f9  nop     dword ptr [rax+rax+00h]
0x18008b2fe  mov     ebx, eax
0x18008b300  test    eax, eax
0x18008b302  js      short loc_18008B35A
0x18008b304  cmp     [rbp+57h+var_34], 4
0x18008b308  jnz     short loc_18008B355
0x18008b30a  cmp     [rbp+57h+var_30], 4
0x18008b30e  jb      short loc_18008B355
0x18008b310  cmp     word ptr [rdi+2], 12h
0x18008b315  jnb     short loc_18008B31E
0x18008b317  mov     ebx, 0C0000023h
0x18008b31c  jmp     short loc_18008B35A
0x18008b31e  mov     ecx, [rbp+57h+Value]; Value
0x18008b321  mov     r8, rdi; String
0x18008b324  mov     edx, 10h; Base
0x18008b329  call    cs:__imp_RtlIntegerToUnicodeString
0x18008b330  nop     dword ptr [rax+rax+00h]
0x18008b335  mov     ebx, eax
0x18008b337  test    eax, eax
0x18008b339  js      short loc_18008B35A
0x18008b33b  mov     rcx, [rdi+8]
0x18008b33f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008b343  inc     rax
0x18008b346  cmp     [rcx+rax*2], r14w
0x18008b34b  jnz     short loc_18008B343
0x18008b34d  add     ax, ax
0x18008b350  mov     [rdi], ax
0x18008b353  jmp     short loc_18008B35A
0x18008b355  mov     ebx, 0C0000024h
0x18008b35a  mov     rcx, [rbp+57h+Handle]; Handle
0x18008b35e  test    rcx, rcx
0x18008b361  jz      short loc_18008B36F
0x18008b363  call    cs:__imp_ZwClose
0x18008b36a  nop     dword ptr [rax+rax+00h]
0x18008b36f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008b373  test    rcx, rcx
0x18008b376  jz      short loc_18008B384
0x18008b378  call    cs:__imp_ZwClose
0x18008b37f  nop     dword ptr [rax+rax+00h]
0x18008b384  mov     eax, ebx
0x18008b386  mov     rcx, [rbp+57h+var_20]
0x18008b38a  xor     rcx, rsp; StackCookie
0x18008b38d  call    __security_check_cookie
0x18008b392  lea     r11, [rsp+0D0h+var_10]
0x18008b39a  mov     rbx, [r11+30h]
0x18008b39e  mov     rsi, [r11+38h]
0x18008b3a2  mov     rsp, r11
0x18008b3a5  pop     r14
0x18008b3a7  pop     rdi
0x18008b3a8  pop     rbp
0x18008b3a9  retn
```
