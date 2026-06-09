# CipSetSmartlockerRegEnabled

- ea: `0x180074c48`
- end: `0x180074e4d`
- name: `CipSetSmartlockerRegEnabled`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180071740`

## callees

- `0x18002c0d0`
- `0x180074c48`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180074d1b`
- `ntoskrnl!ZwCreateKey` at `0x180074d1b`
- `ntoskrnl!ZwQueryValueKey` at `0x180074d54`
- `ntoskrnl!ZwQueryValueKey` at `0x180074d54`
- `ntoskrnl!ZwClose` at `0x180074e1d`
- `ntoskrnl!ZwClose` at `0x180074e1d`
- `ntoskrnl!ZwSetValueKey` at `0x180074dd2`
- `ntoskrnl!ZwSetValueKey` at `0x180074e06`
- `ntoskrnl!ZwSetValueKey` at `0x180074dd2`
- `ntoskrnl!ZwSetValueKey` at `0x180074e06`

## string_xrefs

- `0x180074c79`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
__int64 __fastcall CipSetSmartlockerRegEnabled(char a1)
{
  NTSTATUS v2; // ebx
  NTSTATUS v3; // eax
  int v4; // ecx
  unsigned __int64 v5; // rax
  int v7; // [rsp+40h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-41h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int64 Data; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v12[2]; // [rsp+70h] [rbp-19h] BYREF
  struct _UNICODE_STRING v13; // [rsp+80h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[24]; // [rsp+C0h] [rbp+37h] BYREF

  v12[1] = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  v12[0] = 10879140;
  ValueName.Buffer = L"ENABLED";
  *(_QWORD *)&ValueName.Length = 1048590;
  v13.Buffer = L"START_PENDING";
  *(_QWORD *)&v13.Length = 1835034;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
  Data = 0;
  v7 = 0;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  memset(KeyValueInformation, 0, sizeof(KeyValueInformation));
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
  if ( v2 >= 0 )
  {
    v3 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x18u, &ResultLength);
    if ( v3 != -1073741772 && (v3 < 0 || *(_QWORD *)&KeyValueInformation[4] != 0x80000000BLL) )
      goto LABEL_7;
    Data = *(_QWORD *)&KeyValueInformation[12];
    if ( a1 )
    {
      if ( (KeyValueInformation[12] & 4) != 0 )
        goto LABEL_7;
      v4 = 1;
      v5 = *(_QWORD *)&KeyValueInformation[12] | 4LL;
    }
    else
    {
      if ( (KeyValueInformation[12] & 4) == 0 )
      {
LABEL_7:
        v2 = 0;
        goto LABEL_13;
      }
      v4 = 0;
      v5 = *(_QWORD *)&KeyValueInformation[12] & 0xFFFFFFFFFFFFFFFBuLL;
    }
    Data = v5;
    v7 = v4;
    v2 = ZwSetValueKey(KeyHandle, &ValueName, 0, 0xBu, &Data, 8u);
    if ( v2 >= 0 )
      v2 = ZwSetValueKey(KeyHandle, &v13, 0, 4u, &v7, 4u);
  }
LABEL_13:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180074c48  mov     [rsp-8+arg_0], rbx
0x180074c4d  mov     [rsp-8+arg_8], rdi
0x180074c52  push    rbp
0x180074c53  lea     rbp, [rsp-57h]
0x180074c58  sub     rsp, 0E0h
0x180074c5f  mov     rax, cs:__security_cookie
0x180074c66  xor     rax, rsp
0x180074c69  mov     [rbp+57h+var_8], rax
0x180074c6d  xorps   xmm0, xmm0
0x180074c70  mov     [rsp+0E0h+Disposition], 0; Disposition
0x180074c79  lea     rax, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x180074c80  mov     [rsp+0E0h+CreateOptions], 0; CreateOptions
0x180074c88  mov     [rbp+57h+var_68], rax
0x180074c8c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180074c90  lea     rax, aEnabled; "ENABLED"
0x180074c97  mov     [rbp+57h+var_70], 0A600A4h
0x180074c9f  mov     [rbp+57h+ValueName.Buffer], rax
0x180074ca3  mov     dil, cl
0x180074ca6  lea     rax, aStartPending; "START_PENDING"
0x180074cad  mov     qword ptr [rbp+57h+ValueName.Length], 10000Eh
0x180074cb5  mov     [rbp+57h+var_60.Buffer], rax
0x180074cb9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074cbd  xor     eax, eax
0x180074cbf  mov     qword ptr [rbp+57h+var_60.Length], 1C001Ah
0x180074cc7  mov     [rbp+57h+var_10], rax
0x180074ccb  xor     r9d, r9d; TitleIndex
0x180074cce  mov     [rbp+57h+ResultLength], eax
0x180074cd1  mov     edx, 20006h; DesiredAccess
0x180074cd6  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180074cda  lea     rax, [rbp+57h+var_70]
0x180074cde  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180074ce2  mov     [rbp+57h+Data], 0
0x180074cea  mov     [rbp+57h+var_A0], 0
0x180074cf1  mov     [rbp+57h+KeyHandle], 0
0x180074cf9  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180074d01  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180074d09  movups  [rbp+57h+KeyValueInformation], xmm0
0x180074d0d  mov     [rsp+0E0h+Class], 0; Class
0x180074d16  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074d1b  call    cs:__imp_ZwCreateKey
0x180074d22  nop     dword ptr [rax+rax+00h]
0x180074d27  mov     ebx, eax
0x180074d29  test    eax, eax
0x180074d2b  js      loc_180074E14
0x180074d31  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074d35  lea     rax, [rbp+57h+ResultLength]
0x180074d39  mov     qword ptr [rsp+0E0h+CreateOptions], rax; ResultLength
0x180074d3e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180074d42  mov     r8d, 2; KeyValueInformationClass
0x180074d48  mov     dword ptr [rsp+0E0h+Class], 18h; Length
0x180074d50  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180074d54  call    cs:__imp_ZwQueryValueKey
0x180074d5b  nop     dword ptr [rax+rax+00h]
0x180074d60  mov     r9d, 0Bh; Type
0x180074d66  cmp     eax, 0C0000034h
0x180074d6b  jz      short loc_180074D7D
0x180074d6d  test    eax, eax
0x180074d6f  js      short loc_180074D95
0x180074d71  cmp     dword ptr [rbp+57h+KeyValueInformation+4], r9d
0x180074d75  jnz     short loc_180074D95
0x180074d77  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 8
0x180074d7b  jnz     short loc_180074D95
0x180074d7d  mov     rax, qword ptr [rbp+57h+KeyValueInformation+0Ch]
0x180074d81  mov     rcx, rax
0x180074d84  mov     [rbp+57h+Data], rax
0x180074d88  and     ecx, 4
0x180074d8b  test    dil, dil
0x180074d8e  jnz     short loc_180074DA1
0x180074d90  test    rcx, rcx
0x180074d93  jnz     short loc_180074D99
0x180074d95  xor     ebx, ebx
0x180074d97  jmp     short loc_180074E14
0x180074d99  xor     ecx, ecx
0x180074d9b  and     rax, 0FFFFFFFFFFFFFFFBh
0x180074d9f  jmp     short loc_180074DAF
0x180074da1  test    rcx, rcx
0x180074da4  jnz     short loc_180074D95
0x180074da6  mov     ecx, 1
0x180074dab  or      rax, 4
0x180074daf  mov     [rbp+57h+Data], rax
0x180074db3  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180074db7  lea     rax, [rbp+57h+Data]
0x180074dbb  mov     [rbp+57h+var_A0], ecx
0x180074dbe  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074dc2  xor     r8d, r8d; TitleIndex
0x180074dc5  mov     [rsp+0E0h+CreateOptions], 8; DataSize
0x180074dcd  mov     [rsp+0E0h+Class], rax; Data
0x180074dd2  call    cs:__imp_ZwSetValueKey
0x180074dd9  nop     dword ptr [rax+rax+00h]
0x180074dde  mov     ebx, eax
0x180074de0  test    eax, eax
0x180074de2  js      short loc_180074E14
0x180074de4  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074de8  lea     rax, [rbp+57h+var_A0]
0x180074dec  mov     [rsp+0E0h+CreateOptions], 4; DataSize
0x180074df4  lea     rdx, [rbp+57h+var_60]; ValueName
0x180074df8  mov     r9d, 4; Type
0x180074dfe  mov     [rsp+0E0h+Class], rax; Data
0x180074e03  xor     r8d, r8d; TitleIndex
0x180074e06  call    cs:__imp_ZwSetValueKey
0x180074e0d  nop     dword ptr [rax+rax+00h]
0x180074e12  mov     ebx, eax
0x180074e14  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180074e18  test    rcx, rcx
0x180074e1b  jz      short loc_180074E29
0x180074e1d  call    cs:__imp_ZwClose
0x180074e24  nop     dword ptr [rax+rax+00h]
0x180074e29  mov     eax, ebx
0x180074e2b  mov     rcx, [rbp+57h+var_8]
0x180074e2f  xor     rcx, rsp; StackCookie
0x180074e32  call    __security_check_cookie
0x180074e37  lea     r11, [rsp+0E0h+var_s0]
0x180074e3f  mov     rbx, [r11+10h]
0x180074e43  mov     rdi, [r11+18h]
0x180074e47  mov     rsp, r11
0x180074e4a  pop     rbp
0x180074e4b  retn
```
