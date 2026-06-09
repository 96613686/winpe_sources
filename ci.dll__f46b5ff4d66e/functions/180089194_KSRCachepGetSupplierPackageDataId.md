# KSRCachepGetSupplierPackageDataId

- ea: `0x180089194`
- end: `0x18008935f`
- name: `KSRCachepGetSupplierPackageDataId`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180088558`

## callees

- `0x18002bef0`
- `0x180089194`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1800892a6`
- `ntoskrnl!ZwQueryValueKey` at `0x1800892a6`
- `ntoskrnl!ZwClose` at `0x180089317`
- `ntoskrnl!ZwClose` at `0x18008932c`
- `ntoskrnl!ZwClose` at `0x180089317`
- `ntoskrnl!ZwClose` at `0x18008932c`
- `ntoskrnl!ZwOpenKey` at `0x18008922b`
- `ntoskrnl!ZwOpenKey` at `0x180089270`
- `ntoskrnl!ZwOpenKey` at `0x18008922b`
- `ntoskrnl!ZwOpenKey` at `0x180089270`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800892dd`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800892dd`

## string_xrefs

- `0x1800891c7`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\DependencyGraph\Data`

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
0x180089194  mov     [rsp-8+arg_10], rbx
0x180089199  mov     [rsp-8+arg_18], rsi
0x18008919e  push    rbp
0x18008919f  push    rdi
0x1800891a0  push    r14
0x1800891a2  lea     rbp, [rsp-47h]
0x1800891a7  sub     rsp, 0C0h
0x1800891ae  mov     rax, cs:__security_cookie
0x1800891b5  xor     rax, rsp
0x1800891b8  mov     [rbp+57h+var_20], rax
0x1800891bc  xor     r14d, r14d
0x1800891bf  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800891c7  lea     rax, aRegistryMachin_6; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800891ce  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800891d6  mov     [rbp+57h+var_80], rax
0x1800891da  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800891de  lea     rax, aSupplierpackag; "SupplierPackage"
0x1800891e5  mov     [rbp+57h+var_88], 0E000DEh
0x1800891ed  mov     [rbp+57h+ValueName.Buffer], rax
0x1800891f1  mov     rdi, rdx
0x1800891f4  lea     rax, [rbp+57h+var_88]
0x1800891f8  mov     qword ptr [rbp+57h+ValueName.Length], 20001Eh
0x180089200  mov     rsi, rcx
0x180089203  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180089207  xorps   xmm0, xmm0
0x18008920a  mov     [rbp+57h+KeyHandle], r14
0x18008920e  mov     edx, 20019h; DesiredAccess
0x180089213  mov     [rbp+57h+Handle], r14
0x180089217  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008921b  mov     [rbp+57h+var_A0], 14h
0x180089222  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180089226  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008922b  call    cs:__imp_ZwOpenKey
0x180089232  nop     dword ptr [rax+rax+00h]
0x180089237  mov     ebx, eax
0x180089239  test    eax, eax
0x18008923b  js      loc_18008930E
0x180089241  mov     rax, [rbp+57h+KeyHandle]
0x180089245  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180089249  xorps   xmm0, xmm0
0x18008924c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180089250  mov     edx, 20019h; DesiredAccess
0x180089255  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008925c  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180089260  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180089267  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008926c  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180089270  call    cs:__imp_ZwOpenKey
0x180089277  nop     dword ptr [rax+rax+00h]
0x18008927c  mov     ebx, eax
0x18008927e  test    eax, eax
0x180089280  js      loc_18008930E
0x180089286  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008928a  lea     rax, [rbp+57h+var_A0]
0x18008928e  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x180089293  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180089297  mov     eax, [rbp+57h+var_A0]
0x18008929a  lea     r8d, [r14+2]; KeyValueInformationClass
0x18008929e  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800892a2  mov     [rsp+0D0h+Length], eax; Length
0x1800892a6  call    cs:__imp_ZwQueryValueKey
0x1800892ad  nop     dword ptr [rax+rax+00h]
0x1800892b2  mov     ebx, eax
0x1800892b4  test    eax, eax
0x1800892b6  js      short loc_18008930E
0x1800892b8  cmp     [rbp+57h+var_34], 4
0x1800892bc  jnz     short loc_180089309
0x1800892be  cmp     [rbp+57h+var_30], 4
0x1800892c2  jb      short loc_180089309
0x1800892c4  cmp     word ptr [rdi+2], 12h
0x1800892c9  jnb     short loc_1800892D2
0x1800892cb  mov     ebx, 0C0000023h
0x1800892d0  jmp     short loc_18008930E
0x1800892d2  mov     ecx, [rbp+57h+Value]; Value
0x1800892d5  mov     r8, rdi; String
0x1800892d8  mov     edx, 10h; Base
0x1800892dd  call    cs:__imp_RtlIntegerToUnicodeString
0x1800892e4  nop     dword ptr [rax+rax+00h]
0x1800892e9  mov     ebx, eax
0x1800892eb  test    eax, eax
0x1800892ed  js      short loc_18008930E
0x1800892ef  mov     rcx, [rdi+8]
0x1800892f3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800892f7  inc     rax
0x1800892fa  cmp     [rcx+rax*2], r14w
0x1800892ff  jnz     short loc_1800892F7
0x180089301  add     ax, ax
0x180089304  mov     [rdi], ax
0x180089307  jmp     short loc_18008930E
0x180089309  mov     ebx, 0C0000024h
0x18008930e  mov     rcx, [rbp+57h+Handle]; Handle
0x180089312  test    rcx, rcx
0x180089315  jz      short loc_180089323
0x180089317  call    cs:__imp_ZwClose
0x18008931e  nop     dword ptr [rax+rax+00h]
0x180089323  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180089327  test    rcx, rcx
0x18008932a  jz      short loc_180089338
0x18008932c  call    cs:__imp_ZwClose
0x180089333  nop     dword ptr [rax+rax+00h]
0x180089338  mov     eax, ebx
0x18008933a  mov     rcx, [rbp+57h+var_20]
0x18008933e  xor     rcx, rsp; StackCookie
0x180089341  call    __security_check_cookie
0x180089346  lea     r11, [rsp+0D0h+var_10]
0x18008934e  mov     rbx, [r11+30h]
0x180089352  mov     rsi, [r11+38h]
0x180089356  mov     rsp, r11
0x180089359  pop     r14
0x18008935b  pop     rdi
0x18008935c  pop     rbp
0x18008935d  retn
```
