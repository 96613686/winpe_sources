# CipSetSmartlockerRegEnabled

- ea: `0x180074968`
- end: `0x180074b6d`
- name: `CipSetSmartlockerRegEnabled`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180071460`

## callees

- `0x18002bf20`
- `0x180074968`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180074a3b`
- `ntoskrnl!ZwCreateKey` at `0x180074a3b`
- `ntoskrnl!ZwQueryValueKey` at `0x180074a74`
- `ntoskrnl!ZwQueryValueKey` at `0x180074a74`
- `ntoskrnl!ZwClose` at `0x180074b3d`
- `ntoskrnl!ZwClose` at `0x180074b3d`
- `ntoskrnl!ZwSetValueKey` at `0x180074af2`
- `ntoskrnl!ZwSetValueKey` at `0x180074b26`
- `ntoskrnl!ZwSetValueKey` at `0x180074af2`
- `ntoskrnl!ZwSetValueKey` at `0x180074b26`

## string_xrefs

- `0x180074999`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

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
0x180074968  mov     [rsp-8+arg_0], rbx
0x18007496d  mov     [rsp-8+arg_8], rdi
0x180074972  push    rbp
0x180074973  lea     rbp, [rsp-57h]
0x180074978  sub     rsp, 0E0h
0x18007497f  mov     rax, cs:__security_cookie
0x180074986  xor     rax, rsp
0x180074989  mov     [rbp+57h+var_8], rax
0x18007498d  xorps   xmm0, xmm0
0x180074990  mov     [rsp+0E0h+Disposition], 0; Disposition
0x180074999  lea     rax, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x1800749a0  mov     [rsp+0E0h+CreateOptions], 0; CreateOptions
0x1800749a8  mov     [rbp+57h+var_68], rax
0x1800749ac  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800749b0  lea     rax, aEnabled; "ENABLED"
0x1800749b7  mov     [rbp+57h+var_70], 0A600A4h
0x1800749bf  mov     [rbp+57h+ValueName.Buffer], rax
0x1800749c3  mov     dil, cl
0x1800749c6  lea     rax, aStartPending; "START_PENDING"
0x1800749cd  mov     qword ptr [rbp+57h+ValueName.Length], 10000Eh
0x1800749d5  mov     [rbp+57h+var_60.Buffer], rax
0x1800749d9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800749dd  xor     eax, eax
0x1800749df  mov     qword ptr [rbp+57h+var_60.Length], 1C001Ah
0x1800749e7  mov     [rbp+57h+var_10], rax
0x1800749eb  xor     r9d, r9d; TitleIndex
0x1800749ee  mov     [rbp+57h+ResultLength], eax
0x1800749f1  mov     edx, 20006h; DesiredAccess
0x1800749f6  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800749fa  lea     rax, [rbp+57h+var_70]
0x1800749fe  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180074a02  mov     [rbp+57h+Data], 0
0x180074a0a  mov     [rbp+57h+var_A0], 0
0x180074a11  mov     [rbp+57h+KeyHandle], 0
0x180074a19  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180074a21  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180074a29  movups  [rbp+57h+KeyValueInformation], xmm0
0x180074a2d  mov     [rsp+0E0h+Class], 0; Class
0x180074a36  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074a3b  call    cs:__imp_ZwCreateKey
0x180074a42  nop     dword ptr [rax+rax+00h]
0x180074a47  mov     ebx, eax
0x180074a49  test    eax, eax
0x180074a4b  js      loc_180074B34
0x180074a51  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074a55  lea     rax, [rbp+57h+ResultLength]
0x180074a59  mov     qword ptr [rsp+0E0h+CreateOptions], rax; ResultLength
0x180074a5e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180074a62  mov     r8d, 2; KeyValueInformationClass
0x180074a68  mov     dword ptr [rsp+0E0h+Class], 18h; Length
0x180074a70  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180074a74  call    cs:__imp_ZwQueryValueKey
0x180074a7b  nop     dword ptr [rax+rax+00h]
0x180074a80  mov     r9d, 0Bh; Type
0x180074a86  cmp     eax, 0C0000034h
0x180074a8b  jz      short loc_180074A9D
0x180074a8d  test    eax, eax
0x180074a8f  js      short loc_180074AB5
0x180074a91  cmp     dword ptr [rbp+57h+KeyValueInformation+4], r9d
0x180074a95  jnz     short loc_180074AB5
0x180074a97  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 8
0x180074a9b  jnz     short loc_180074AB5
0x180074a9d  mov     rax, qword ptr [rbp+57h+KeyValueInformation+0Ch]
0x180074aa1  mov     rcx, rax
0x180074aa4  mov     [rbp+57h+Data], rax
0x180074aa8  and     ecx, 4
0x180074aab  test    dil, dil
0x180074aae  jnz     short loc_180074AC1
0x180074ab0  test    rcx, rcx
0x180074ab3  jnz     short loc_180074AB9
0x180074ab5  xor     ebx, ebx
0x180074ab7  jmp     short loc_180074B34
0x180074ab9  xor     ecx, ecx
0x180074abb  and     rax, 0FFFFFFFFFFFFFFFBh
0x180074abf  jmp     short loc_180074ACF
0x180074ac1  test    rcx, rcx
0x180074ac4  jnz     short loc_180074AB5
0x180074ac6  mov     ecx, 1
0x180074acb  or      rax, 4
0x180074acf  mov     [rbp+57h+Data], rax
0x180074ad3  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180074ad7  lea     rax, [rbp+57h+Data]
0x180074adb  mov     [rbp+57h+var_A0], ecx
0x180074ade  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074ae2  xor     r8d, r8d; TitleIndex
0x180074ae5  mov     [rsp+0E0h+CreateOptions], 8; DataSize
0x180074aed  mov     [rsp+0E0h+Class], rax; Data
0x180074af2  call    cs:__imp_ZwSetValueKey
0x180074af9  nop     dword ptr [rax+rax+00h]
0x180074afe  mov     ebx, eax
0x180074b00  test    eax, eax
0x180074b02  js      short loc_180074B34
0x180074b04  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180074b08  lea     rax, [rbp+57h+var_A0]
0x180074b0c  mov     [rsp+0E0h+CreateOptions], 4; DataSize
0x180074b14  lea     rdx, [rbp+57h+var_60]; ValueName
0x180074b18  mov     r9d, 4; Type
0x180074b1e  mov     [rsp+0E0h+Class], rax; Data
0x180074b23  xor     r8d, r8d; TitleIndex
0x180074b26  call    cs:__imp_ZwSetValueKey
0x180074b2d  nop     dword ptr [rax+rax+00h]
0x180074b32  mov     ebx, eax
0x180074b34  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180074b38  test    rcx, rcx
0x180074b3b  jz      short loc_180074B49
0x180074b3d  call    cs:__imp_ZwClose
0x180074b44  nop     dword ptr [rax+rax+00h]
0x180074b49  mov     eax, ebx
0x180074b4b  mov     rcx, [rbp+57h+var_8]
0x180074b4f  xor     rcx, rsp; StackCookie
0x180074b52  call    __security_check_cookie
0x180074b57  lea     r11, [rsp+0E0h+var_s0]
0x180074b5f  mov     rbx, [r11+10h]
0x180074b63  mov     rdi, [r11+18h]
0x180074b67  mov     rsp, r11
0x180074b6a  pop     rbp
0x180074b6b  retn
```
