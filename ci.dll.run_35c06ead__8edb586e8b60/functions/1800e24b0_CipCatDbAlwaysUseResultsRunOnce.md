# CipCatDbAlwaysUseResultsRunOnce

- ea: `0x1800e24b0`
- end: `0x1800e25d2`
- name: `CipCatDbAlwaysUseResultsRunOnce`
- size: `290`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18002c0d0`
- `0x1800e24b0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1800e2576`
- `ntoskrnl!ZwQueryValueKey` at `0x1800e2576`
- `ntoskrnl!ZwClose` at `0x1800e259c`
- `ntoskrnl!ZwClose` at `0x1800e259c`
- `ntoskrnl!ZwOpenKey` at `0x1800e2545`
- `ntoskrnl!ZwOpenKey` at `0x1800e2545`

## string_xrefs

- `0x1800e24fc`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Setup`

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
0x1800e24b0  mov     [rsp-8+arg_0], rbx
0x1800e24b5  mov     [rsp-8+arg_8], rdi
0x1800e24ba  push    rbp
0x1800e24bb  lea     rbp, [rsp-57h]
0x1800e24c0  sub     rsp, 0B0h
0x1800e24c7  mov     rax, cs:__security_cookie
0x1800e24ce  xor     rax, rsp
0x1800e24d1  mov     [rbp+57h+var_8], rax
0x1800e24d5  lea     rax, aMinimizefootpr; "MinimizeFootprint"
0x1800e24dc  mov     [rbp+57h+KeyHandle], 0
0x1800e24e4  mov     [rbp+57h+ValueName.Buffer], rax
0x1800e24e8  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800e24ec  xor     eax, eax
0x1800e24ee  mov     qword ptr [rbp+57h+ValueName.Length], 240022h
0x1800e24f6  mov     [rbp+57h+var_80], eax
0x1800e24f9  mov     rdi, r8
0x1800e24fc  lea     rax, aRegistryMachin_9; "\\Registry\\Machine\\Software\\Microsof"...
0x1800e2503  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800e250b  mov     [rbp+57h+var_68], rax
0x1800e250f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800e2513  lea     rax, [rbp+57h+var_70]
0x1800e2517  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800e251f  xorps   xmm0, xmm0
0x1800e2522  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800e2526  mov     edx, 20019h; DesiredAccess
0x1800e252b  mov     [rbp+57h+var_70], 840082h
0x1800e2533  mov     ebx, 4
0x1800e2538  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800e2540  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800e2545  call    cs:__imp_ZwOpenKey
0x1800e254c  nop     dword ptr [rax+rax+00h]
0x1800e2551  test    eax, eax
0x1800e2553  js      short loc_1800E25A8
0x1800e2555  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800e2559  lea     rax, [rbp+57h+var_80]
0x1800e255d  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x1800e2562  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800e2566  lea     r8d, [rbx-2]; KeyValueInformationClass
0x1800e256a  mov     [rsp+0B0h+Length], 14h; Length
0x1800e2572  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800e2576  call    cs:__imp_ZwQueryValueKey
0x1800e257d  nop     dword ptr [rax+rax+00h]
0x1800e2582  test    eax, eax
0x1800e2584  js      short loc_1800E2598
0x1800e2586  cmp     [rbp+57h+var_1C], ebx
0x1800e2589  jnz     short loc_1800E2598
0x1800e258b  cmp     [rbp+57h+var_18], ebx
0x1800e258e  jb      short loc_1800E2598
0x1800e2590  xor     eax, eax
0x1800e2592  cmp     [rbp+57h+var_14], eax
0x1800e2595  cmovnz  ebx, eax
0x1800e2598  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800e259c  call    cs:__imp_ZwClose
0x1800e25a3  nop     dword ptr [rax+rax+00h]
0x1800e25a8  mov     [rdi], rbx
0x1800e25ab  mov     eax, 1
0x1800e25b0  mov     rcx, [rbp+57h+var_8]
0x1800e25b4  xor     rcx, rsp; StackCookie
0x1800e25b7  call    __security_check_cookie
0x1800e25bc  lea     r11, [rsp+0B0h+var_s0]
0x1800e25c4  mov     rbx, [r11+10h]
0x1800e25c8  mov     rdi, [r11+18h]
0x1800e25cc  mov     rsp, r11
0x1800e25cf  pop     rbp
0x1800e25d0  retn
```
