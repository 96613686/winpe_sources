# CipCatDbAlwaysUseResultsRunOnce

- ea: `0x1800e25a0`
- end: `0x1800e26c2`
- name: `CipCatDbAlwaysUseResultsRunOnce`
- size: `290`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18002bf20`
- `0x1800e25a0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1800e2666`
- `ntoskrnl!ZwQueryValueKey` at `0x1800e2666`
- `ntoskrnl!ZwClose` at `0x1800e268c`
- `ntoskrnl!ZwClose` at `0x1800e268c`
- `ntoskrnl!ZwOpenKey` at `0x1800e2635`
- `ntoskrnl!ZwOpenKey` at `0x1800e2635`

## string_xrefs

- `0x1800e25ec`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Setup`

## pseudocode

```c
__int64 __fastcall CipCatDbAlwaysUseResultsRunOnce(PRTL_RUN_ONCE a1, PVOID a2, PVOID *a3)
{
  __int64 v4; // rbx
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v8[2]; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v12; // [rsp+94h] [rbp+3Bh]
  unsigned int v13; // [rsp+98h] [rbp+3Fh]
  int v14; // [rsp+9Ch] [rbp+43h]

  KeyHandle = 0;
  ValueName.Buffer = L"MinimizeFootprint";
  *(_QWORD *)&ValueName.Length = 2359330;
  ResultLength = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v8[1] = L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Setup";
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v8;
  v8[0] = 8650882;
  v4 = 4;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength) >= 0
      && v12 == 4
      && v13 >= 4
      && v14 )
    {
      v4 = 0;
    }
    ZwClose(KeyHandle);
  }
  *a3 = (PVOID)v4;
  return 1;
}

```

## disassembly

```asm
0x1800e25a0  mov     [rsp-8+arg_0], rbx
0x1800e25a5  mov     [rsp-8+arg_8], rdi
0x1800e25aa  push    rbp
0x1800e25ab  lea     rbp, [rsp-57h]
0x1800e25b0  sub     rsp, 0B0h
0x1800e25b7  mov     rax, cs:__security_cookie
0x1800e25be  xor     rax, rsp
0x1800e25c1  mov     [rbp+57h+var_8], rax
0x1800e25c5  lea     rax, aMinimizefootpr; "MinimizeFootprint"
0x1800e25cc  mov     [rbp+57h+KeyHandle], 0
0x1800e25d4  mov     [rbp+57h+ValueName.Buffer], rax
0x1800e25d8  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800e25dc  xor     eax, eax
0x1800e25de  mov     qword ptr [rbp+57h+ValueName.Length], 240022h
0x1800e25e6  mov     [rbp+57h+var_80], eax
0x1800e25e9  mov     rdi, r8
0x1800e25ec  lea     rax, aRegistryMachin_9; "\\Registry\\Machine\\Software\\Microsof"...
0x1800e25f3  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800e25fb  mov     [rbp+57h+var_68], rax
0x1800e25ff  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800e2603  lea     rax, [rbp+57h+var_70]
0x1800e2607  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800e260f  xorps   xmm0, xmm0
0x1800e2612  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800e2616  mov     edx, 20019h; DesiredAccess
0x1800e261b  mov     [rbp+57h+var_70], 840082h
0x1800e2623  mov     ebx, 4
0x1800e2628  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800e2630  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e2635  call    cs:__imp_ZwOpenKey
0x1800e263c  nop     dword ptr [rax+rax+00h]
0x1800e2641  test    eax, eax
0x1800e2643  js      short loc_1800E2698
0x1800e2645  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800e2649  lea     rax, [rbp+57h+var_80]
0x1800e264d  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x1800e2652  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800e2656  lea     r8d, [rbx-2]; KeyValueInformationClass
0x1800e265a  mov     [rsp+0B0h+Length], 14h; Length
0x1800e2662  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800e2666  call    cs:__imp_ZwQueryValueKey
0x1800e266d  nop     dword ptr [rax+rax+00h]
0x1800e2672  test    eax, eax
0x1800e2674  js      short loc_1800E2688
0x1800e2676  cmp     [rbp+57h+var_1C], ebx
0x1800e2679  jnz     short loc_1800E2688
0x1800e267b  cmp     [rbp+57h+var_18], ebx
0x1800e267e  jb      short loc_1800E2688
0x1800e2680  xor     eax, eax
0x1800e2682  cmp     [rbp+57h+var_14], eax
0x1800e2685  cmovnz  ebx, eax
0x1800e2688  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800e268c  call    cs:__imp_ZwClose
0x1800e2693  nop     dword ptr [rax+rax+00h]
0x1800e2698  mov     [rdi], rbx
0x1800e269b  mov     eax, 1
0x1800e26a0  mov     rcx, [rbp+57h+var_8]
0x1800e26a4  xor     rcx, rsp; StackCookie
0x1800e26a7  call    __security_check_cookie
0x1800e26ac  lea     r11, [rsp+0B0h+var_s0]
0x1800e26b4  mov     rbx, [r11+10h]
0x1800e26b8  mov     rdi, [r11+18h]
0x1800e26bc  mov     rsp, r11
0x1800e26bf  pop     rbp
0x1800e26c0  retn
```
