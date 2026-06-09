# QuerySpecialDeviceCap(ulong *)

- ea: `0x140020880`
- end: `0x1400209df`
- name: `?QuerySpecialDeviceCap@@YAJPEAK@Z`
- size: `351`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001fefc`

## callees

- `0x14000324c`
- `0x140006480`
- `0x140020880`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400208d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020935`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400208d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020935`
- `ntoskrnl!ZwOpenKey` at `0x140020914`
- `ntoskrnl!ZwOpenKey` at `0x140020914`
- `ntoskrnl!ZwQueryValueKey` at `0x140020963`
- `ntoskrnl!ZwQueryValueKey` at `0x140020963`
- `ntoskrnl!ZwClose` at `0x1400209af`
- `ntoskrnl!ZwClose` at `0x1400209af`

## string_xrefs

- `0x1400208be`: `\Registry\Machine\System\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp`

## pseudocode

```c
__int64 __fastcall QuerySpecialDeviceCap(unsigned int *a1)
{
  NTSTATUS v2; // ebx
  ULONG Length; // [rsp+30h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  _BYTE KeyValueInformation[56]; // [rsp+80h] [rbp+17h] BYREF

  KeyHandle = 0;
  Length = 28;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Terminal Server\\WinStations\\RDP-Tcp");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"SpecialTypeDeviceCap");
    v2 = ZwQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           Length,
           &Length);
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids);
    }
    else
    {
      *a1 = KeyValueInformation[12];
    }
    ZwClose(KeyHandle);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140020880  mov     [rsp-8+arg_8], rbx
0x140020885  mov     [rsp-8+arg_10], rdi
0x14002088a  push    rbp
0x14002088b  lea     rbp, [rsp-57h]
0x140020890  sub     rsp, 0C0h
0x140020897  mov     rax, cs:__security_cookie
0x14002089e  xor     rax, rsp
0x1400208a1  mov     [rbp+57h+var_8], rax
0x1400208a5  xorps   xmm0, xmm0
0x1400208a8  mov     [rbp+57h+KeyHandle], 0
0x1400208b0  mov     rdi, rcx
0x1400208b3  mov     [rbp+57h+var_90], 1Ch
0x1400208ba  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400208be  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400208c5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400208c9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400208cd  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400208d1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400208d5  call    cs:__imp_RtlInitUnicodeString
0x1400208dc  nop     dword ptr [rax+rax+00h]
0x1400208e1  lea     rax, [rbp+57h+DestinationString]
0x1400208e5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400208ec  xorps   xmm0, xmm0
0x1400208ef  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400208f3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400208f7  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400208ff  mov     edx, 80000000h; DesiredAccess
0x140020904  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002090b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002090f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140020914  call    cs:__imp_ZwOpenKey
0x14002091b  nop     dword ptr [rax+rax+00h]
0x140020920  mov     ebx, eax
0x140020922  test    eax, eax
0x140020924  js      loc_1400209BB
0x14002092a  lea     rdx, aSpecialtypedev; "SpecialTypeDeviceCap"
0x140020931  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140020935  call    cs:__imp_RtlInitUnicodeString
0x14002093c  nop     dword ptr [rax+rax+00h]
0x140020941  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140020945  lea     rax, [rbp+57h+var_90]
0x140020949  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14002094e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140020952  mov     eax, [rbp+57h+var_90]
0x140020955  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140020959  mov     r8d, 2; KeyValueInformationClass
0x14002095f  mov     [rsp+0C0h+Length], eax; Length
0x140020963  call    cs:__imp_ZwQueryValueKey
0x14002096a  nop     dword ptr [rax+rax+00h]
0x14002096f  mov     ebx, eax
0x140020971  test    eax, eax
0x140020973  js      short loc_14002097D
0x140020975  movzx   eax, [rbp+57h+var_34]
0x140020979  mov     [rdi], eax
0x14002097b  jmp     short loc_1400209AB
0x14002097d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020984  lea     rax, WPP_GLOBAL_Control
0x14002098b  cmp     rcx, rax
0x14002098e  jz      short loc_1400209AB
0x140020990  cmp     byte ptr [rcx+29h], 4
0x140020994  jb      short loc_1400209AB
0x140020996  mov     rcx, [rcx+18h]
0x14002099a  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x1400209a1  mov     edx, 0Ah
0x1400209a6  call    WPP_SF_
0x1400209ab  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400209af  call    cs:__imp_ZwClose
0x1400209b6  nop     dword ptr [rax+rax+00h]
0x1400209bb  mov     eax, ebx
0x1400209bd  mov     rcx, [rbp+57h+var_8]
0x1400209c1  xor     rcx, rsp; StackCookie
0x1400209c4  call    __security_check_cookie
0x1400209c9  lea     r11, [rsp+0C0h+var_s0]
0x1400209d1  mov     rbx, [r11+18h]
0x1400209d5  mov     rdi, [r11+20h]
0x1400209d9  mov     rsp, r11
0x1400209dc  pop     rbp
0x1400209dd  retn
```
