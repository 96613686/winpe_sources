# KSRCachepGetSupplierPackageDataId

- ea: `0x18008a7c4`
- end: `0x18008a98f`
- name: `KSRCachepGetSupplierPackageDataId`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089b88`

## callees

- `0x18002bf20`
- `0x18008a7c4`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18008a8d6`
- `ntoskrnl!ZwQueryValueKey` at `0x18008a8d6`
- `ntoskrnl!ZwClose` at `0x18008a947`
- `ntoskrnl!ZwClose` at `0x18008a95c`
- `ntoskrnl!ZwClose` at `0x18008a947`
- `ntoskrnl!ZwClose` at `0x18008a95c`
- `ntoskrnl!ZwOpenKey` at `0x18008a85b`
- `ntoskrnl!ZwOpenKey` at `0x18008a8a0`
- `ntoskrnl!ZwOpenKey` at `0x18008a85b`
- `ntoskrnl!ZwOpenKey` at `0x18008a8a0`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18008a90d`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18008a90d`

## string_xrefs

- `0x18008a7f7`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\DependencyGraph\Data`

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
0x18008a7c4  mov     [rsp-8+arg_10], rbx
0x18008a7c9  mov     [rsp-8+arg_18], rsi
0x18008a7ce  push    rbp
0x18008a7cf  push    rdi
0x18008a7d0  push    r14
0x18008a7d2  lea     rbp, [rsp-47h]
0x18008a7d7  sub     rsp, 0C0h
0x18008a7de  mov     rax, cs:__security_cookie
0x18008a7e5  xor     rax, rsp
0x18008a7e8  mov     [rbp+57h+var_20], rax
0x18008a7ec  xor     r14d, r14d
0x18008a7ef  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008a7f7  lea     rax, aRegistryMachin_6; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008a7fe  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a806  mov     [rbp+57h+var_80], rax
0x18008a80a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008a80e  lea     rax, aSupplierpackag; "SupplierPackage"
0x18008a815  mov     [rbp+57h+var_88], 0E000DEh
0x18008a81d  mov     [rbp+57h+ValueName.Buffer], rax
0x18008a821  mov     rdi, rdx
0x18008a824  lea     rax, [rbp+57h+var_88]
0x18008a828  mov     qword ptr [rbp+57h+ValueName.Length], 20001Eh
0x18008a830  mov     rsi, rcx
0x18008a833  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008a837  xorps   xmm0, xmm0
0x18008a83a  mov     [rbp+57h+KeyHandle], r14
0x18008a83e  mov     edx, 20019h; DesiredAccess
0x18008a843  mov     [rbp+57h+Handle], r14
0x18008a847  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008a84b  mov     [rbp+57h+var_A0], 14h
0x18008a852  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x18008a856  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a85b  call    cs:__imp_ZwOpenKey
0x18008a862  nop     dword ptr [rax+rax+00h]
0x18008a867  mov     ebx, eax
0x18008a869  test    eax, eax
0x18008a86b  js      loc_18008A93E
0x18008a871  mov     rax, [rbp+57h+KeyHandle]
0x18008a875  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008a879  xorps   xmm0, xmm0
0x18008a87c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008a880  mov     edx, 20019h; DesiredAccess
0x18008a885  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008a88c  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18008a890  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a897  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008a89c  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18008a8a0  call    cs:__imp_ZwOpenKey
0x18008a8a7  nop     dword ptr [rax+rax+00h]
0x18008a8ac  mov     ebx, eax
0x18008a8ae  test    eax, eax
0x18008a8b0  js      loc_18008A93E
0x18008a8b6  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008a8ba  lea     rax, [rbp+57h+var_A0]
0x18008a8be  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x18008a8c3  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18008a8c7  mov     eax, [rbp+57h+var_A0]
0x18008a8ca  lea     r8d, [r14+2]; KeyValueInformationClass
0x18008a8ce  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18008a8d2  mov     [rsp+0D0h+Length], eax; Length
0x18008a8d6  call    cs:__imp_ZwQueryValueKey
0x18008a8dd  nop     dword ptr [rax+rax+00h]
0x18008a8e2  mov     ebx, eax
0x18008a8e4  test    eax, eax
0x18008a8e6  js      short loc_18008A93E
0x18008a8e8  cmp     [rbp+57h+var_34], 4
0x18008a8ec  jnz     short loc_18008A939
0x18008a8ee  cmp     [rbp+57h+var_30], 4
0x18008a8f2  jb      short loc_18008A939
0x18008a8f4  cmp     word ptr [rdi+2], 12h
0x18008a8f9  jnb     short loc_18008A902
0x18008a8fb  mov     ebx, 0C0000023h
0x18008a900  jmp     short loc_18008A93E
0x18008a902  mov     ecx, [rbp+57h+Value]; Value
0x18008a905  mov     r8, rdi; String
0x18008a908  mov     edx, 10h; Base
0x18008a90d  call    cs:__imp_RtlIntegerToUnicodeString
0x18008a914  nop     dword ptr [rax+rax+00h]
0x18008a919  mov     ebx, eax
0x18008a91b  test    eax, eax
0x18008a91d  js      short loc_18008A93E
0x18008a91f  mov     rcx, [rdi+8]
0x18008a923  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008a927  inc     rax
0x18008a92a  cmp     [rcx+rax*2], r14w
0x18008a92f  jnz     short loc_18008A927
0x18008a931  add     ax, ax
0x18008a934  mov     [rdi], ax
0x18008a937  jmp     short loc_18008A93E
0x18008a939  mov     ebx, 0C0000024h
0x18008a93e  mov     rcx, [rbp+57h+Handle]; Handle
0x18008a942  test    rcx, rcx
0x18008a945  jz      short loc_18008A953
0x18008a947  call    cs:__imp_ZwClose
0x18008a94e  nop     dword ptr [rax+rax+00h]
0x18008a953  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008a957  test    rcx, rcx
0x18008a95a  jz      short loc_18008A968
0x18008a95c  call    cs:__imp_ZwClose
0x18008a963  nop     dword ptr [rax+rax+00h]
0x18008a968  mov     eax, ebx
0x18008a96a  mov     rcx, [rbp+57h+var_20]
0x18008a96e  xor     rcx, rsp; StackCookie
0x18008a971  call    __security_check_cookie
0x18008a976  lea     r11, [rsp+0D0h+var_10]
0x18008a97e  mov     rbx, [r11+30h]
0x18008a982  mov     rsi, [r11+38h]
0x18008a986  mov     rsp, r11
0x18008a989  pop     r14
0x18008a98b  pop     rdi
0x18008a98c  pop     rbp
0x18008a98d  retn
```
