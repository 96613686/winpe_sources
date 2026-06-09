# CipSetSmartlockerRegEnabled

- ea: `0x1800736b8`
- end: `0x1800738bd`
- name: `CipSetSmartlockerRegEnabled`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800701b0`

## callees

- `0x18002bef0`
- `0x1800736b8`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18007378b`
- `ntoskrnl!ZwCreateKey` at `0x18007378b`
- `ntoskrnl!ZwQueryValueKey` at `0x1800737c4`
- `ntoskrnl!ZwQueryValueKey` at `0x1800737c4`
- `ntoskrnl!ZwClose` at `0x18007388d`
- `ntoskrnl!ZwClose` at `0x18007388d`
- `ntoskrnl!ZwSetValueKey` at `0x180073842`
- `ntoskrnl!ZwSetValueKey` at `0x180073876`
- `ntoskrnl!ZwSetValueKey` at `0x180073842`
- `ntoskrnl!ZwSetValueKey` at `0x180073876`

## string_xrefs

- `0x1800736e9`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

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
0x1800736b8  mov     [rsp-8+arg_0], rbx
0x1800736bd  mov     [rsp-8+arg_8], rdi
0x1800736c2  push    rbp
0x1800736c3  lea     rbp, [rsp-57h]
0x1800736c8  sub     rsp, 0E0h
0x1800736cf  mov     rax, cs:__security_cookie
0x1800736d6  xor     rax, rsp
0x1800736d9  mov     [rbp+57h+var_8], rax
0x1800736dd  xorps   xmm0, xmm0
0x1800736e0  mov     [rsp+0E0h+Disposition], 0; Disposition
0x1800736e9  lea     rax, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x1800736f0  mov     [rsp+0E0h+CreateOptions], 0; CreateOptions
0x1800736f8  mov     [rbp+57h+var_68], rax
0x1800736fc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180073700  lea     rax, aEnabled; "ENABLED"
0x180073707  mov     [rbp+57h+var_70], 0A600A4h
0x18007370f  mov     [rbp+57h+ValueName.Buffer], rax
0x180073713  mov     dil, cl
0x180073716  lea     rax, aStartPending; "START_PENDING"
0x18007371d  mov     qword ptr [rbp+57h+ValueName.Length], 10000Eh
0x180073725  mov     [rbp+57h+var_60.Buffer], rax
0x180073729  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18007372d  xor     eax, eax
0x18007372f  mov     qword ptr [rbp+57h+var_60.Length], 1C001Ah
0x180073737  mov     [rbp+57h+var_10], rax
0x18007373b  xor     r9d, r9d; TitleIndex
0x18007373e  mov     [rbp+57h+ResultLength], eax
0x180073741  mov     edx, 20006h; DesiredAccess
0x180073746  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18007374a  lea     rax, [rbp+57h+var_70]
0x18007374e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180073752  mov     [rbp+57h+Data], 0
0x18007375a  mov     [rbp+57h+var_A0], 0
0x180073761  mov     [rbp+57h+KeyHandle], 0
0x180073769  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180073771  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180073779  movups  [rbp+57h+KeyValueInformation], xmm0
0x18007377d  mov     [rsp+0E0h+Class], 0; Class
0x180073786  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007378b  call    cs:__imp_ZwCreateKey
0x180073792  nop     dword ptr [rax+rax+00h]
0x180073797  mov     ebx, eax
0x180073799  test    eax, eax
0x18007379b  js      loc_180073884
0x1800737a1  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800737a5  lea     rax, [rbp+57h+ResultLength]
0x1800737a9  mov     qword ptr [rsp+0E0h+CreateOptions], rax; ResultLength
0x1800737ae  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800737b2  mov     r8d, 2; KeyValueInformationClass
0x1800737b8  mov     dword ptr [rsp+0E0h+Class], 18h; Length
0x1800737c0  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1800737c4  call    cs:__imp_ZwQueryValueKey
0x1800737cb  nop     dword ptr [rax+rax+00h]
0x1800737d0  mov     r9d, 0Bh; Type
0x1800737d6  cmp     eax, 0C0000034h
0x1800737db  jz      short loc_1800737ED
0x1800737dd  test    eax, eax
0x1800737df  js      short loc_180073805
0x1800737e1  cmp     dword ptr [rbp+57h+KeyValueInformation+4], r9d
0x1800737e5  jnz     short loc_180073805
0x1800737e7  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 8
0x1800737eb  jnz     short loc_180073805
0x1800737ed  mov     rax, qword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1800737f1  mov     rcx, rax
0x1800737f4  mov     [rbp+57h+Data], rax
0x1800737f8  and     ecx, 4
0x1800737fb  test    dil, dil
0x1800737fe  jnz     short loc_180073811
0x180073800  test    rcx, rcx
0x180073803  jnz     short loc_180073809
0x180073805  xor     ebx, ebx
0x180073807  jmp     short loc_180073884
0x180073809  xor     ecx, ecx
0x18007380b  and     rax, 0FFFFFFFFFFFFFFFBh
0x18007380f  jmp     short loc_18007381F
0x180073811  test    rcx, rcx
0x180073814  jnz     short loc_180073805
0x180073816  mov     ecx, 1
0x18007381b  or      rax, 4
0x18007381f  mov     [rbp+57h+Data], rax
0x180073823  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180073827  lea     rax, [rbp+57h+Data]
0x18007382b  mov     [rbp+57h+var_A0], ecx
0x18007382e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180073832  xor     r8d, r8d; TitleIndex
0x180073835  mov     [rsp+0E0h+CreateOptions], 8; DataSize
0x18007383d  mov     [rsp+0E0h+Class], rax; Data
0x180073842  call    cs:__imp_ZwSetValueKey
0x180073849  nop     dword ptr [rax+rax+00h]
0x18007384e  mov     ebx, eax
0x180073850  test    eax, eax
0x180073852  js      short loc_180073884
0x180073854  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180073858  lea     rax, [rbp+57h+var_A0]
0x18007385c  mov     [rsp+0E0h+CreateOptions], 4; DataSize
0x180073864  lea     rdx, [rbp+57h+var_60]; ValueName
0x180073868  mov     r9d, 4; Type
0x18007386e  mov     [rsp+0E0h+Class], rax; Data
0x180073873  xor     r8d, r8d; TitleIndex
0x180073876  call    cs:__imp_ZwSetValueKey
0x18007387d  nop     dword ptr [rax+rax+00h]
0x180073882  mov     ebx, eax
0x180073884  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180073888  test    rcx, rcx
0x18007388b  jz      short loc_180073899
0x18007388d  call    cs:__imp_ZwClose
0x180073894  nop     dword ptr [rax+rax+00h]
0x180073899  mov     eax, ebx
0x18007389b  mov     rcx, [rbp+57h+var_8]
0x18007389f  xor     rcx, rsp; StackCookie
0x1800738a2  call    __security_check_cookie
0x1800738a7  lea     r11, [rsp+0E0h+var_s0]
0x1800738af  mov     rbx, [r11+10h]
0x1800738b3  mov     rdi, [r11+18h]
0x1800738b7  mov     rsp, r11
0x1800738ba  pop     rbp
0x1800738bb  retn
```
