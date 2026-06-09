# GetKeyRing

- ea: `0x1400eb078`
- end: `0x1400eb676`
- name: `GetKeyRing`
- size: `1534`
- prototype: `__int64 __fastcall(PVOID ClientIdentificationAddress)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400eb6e0`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x14000af48`
- `0x1400120d0`
- `0x140012954`
- `0x1400218c0`
- `0x14002e59c`
- `0x1400eb078`
- `0x1400ec17c`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400eb5d9`
- `ntoskrnl!KeBugCheckEx` at `0x1400eb5d9`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400eb436`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400eb5ec`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400eb436`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400eb5ec`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400eb3f1`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400eb44e`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400eb3f1`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400eb44e`
- `ntoskrnl!ZwOpenKey` at `0x1400eb19e`
- `ntoskrnl!ZwOpenKey` at `0x1400eb19e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eb60c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eb60c`
- `ntoskrnl!ZwClose` at `0x1400eb2b8`
- `ntoskrnl!ZwClose` at `0x1400eb2b8`
- `ntoskrnl!wcsstr` at `0x1400eb323`
- `ntoskrnl!wcsstr` at `0x1400eb323`
- `ntoskrnl!ExAllocatePool2` at `0x1400eb26d`
- `ntoskrnl!ExAllocatePool2` at `0x1400eb26d`
- `ntoskrnl!ZwQueryValueKey` at `0x1400eb22d`
- `ntoskrnl!ZwQueryValueKey` at `0x1400eb2a6`
- `ntoskrnl!ZwQueryValueKey` at `0x1400eb22d`
- `ntoskrnl!ZwQueryValueKey` at `0x1400eb2a6`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400eb117`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400eb117`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400eb163`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400eb200`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400eb163`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400eb200`

## string_xrefs

- `0x1400eb158`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall GetKeyRing(struct _DRIVER_OBJECT *ClientIdentificationAddress)
{
  int IsValid; // ebx
  _QWORD *DriverObjectExtension; // rax
  ULONG_PTR v4; // rdi
  int KeyRingFromKsr; // eax
  NTSTATUS v6; // eax
  __int64 Pool2; // r13
  NTSTATUS v8; // esi
  ULONG Length; // esi
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  wchar_t *v13; // rax
  unsigned __int16 *v14; // rdx
  __int64 i; // r14
  unsigned __int16 v16; // ax
  _DWORD *v17; // rax
  _DWORD *v18; // rsi
  unsigned int v19; // r15d
  _DWORD *v20; // rax
  __int64 v21; // rdx
  int CachedVmkTargetType; // eax
  ULONG_PTR v23; // rsi
  ULONG_PTR v24; // r14
  __int64 v25; // rcx
  __int64 v26; // rdx
  _WORD v28[2]; // [rsp+30h] [rbp-49h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-45h] BYREF
  ULONG_PTR BugCheckParameter4; // [rsp+38h] [rbp-41h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+48h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp+Fh] BYREF
  __int128 KeyValueInformation; // [rsp+98h] [rbp+1Fh] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_d2beded7854932e8f171fa85139856d9_Traceguids);
  }
  IsValid = 0;
  ResultLength = 0;
  v28[0] = 0;
  LODWORD(BugCheckParameter4) = 0;
  DriverObjectExtension = IoGetDriverObjectExtension(ClientIdentificationAddress, ClientIdentificationAddress);
  v4 = (ULONG_PTR)DriverObjectExtension;
  if ( DriverObjectExtension[85] )
    goto LABEL_75;
  if ( *((_BYTE *)DriverObjectExtension + 9769) && *((_BYTE *)DriverObjectExtension + 9770) )
  {
    KeyRingFromKsr = GetKeyRingFromKsr(DriverObjectExtension);
    if ( KeyRingFromKsr != -1073741275 )
      IsValid = KeyRingFromKsr;
    goto LABEL_75;
  }
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v6 >= 0 )
  {
    Pool2 = 0;
    RtlInitUnicodeString(&ValueName, L"SystemStartOptions");
    v8 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147483643 )
    {
      if ( DWORD1(KeyValueInformation) == 1 )
      {
        Length = ResultLength;
        Pool2 = ExAllocatePool2(64, ResultLength + 2LL, 809850438);
        if ( Pool2 )
          v8 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, (PVOID)Pool2, Length, &ResultLength);
        else
          v8 = -1073741801;
      }
      else
      {
        v8 = -1073741811;
      }
    }
    ZwClose(KeyHandle);
    if ( v8 >= 0 )
    {
      *(_WORD *)(*(unsigned int *)(Pool2 + 8) + Pool2 + 12) = 0;
      v13 = wcsstr((const wchar_t *)(Pool2 + 12), L"FVEBOOT=");
      if ( !v13 )
        goto LABEL_73;
      v14 = v13 + 8;
      for ( i = 0; ; i = v16 + 2 * (5 * i - 24) )
      {
        v16 = *v14;
        if ( *v14 < 0x30u || v16 > 0x39u )
          break;
        ++v14;
      }
      if ( (*v14 & 0xFFDF) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_d2beded7854932e8f171fa85139856d9_Traceguids);
        }
        goto LABEL_73;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_Ii(WPP_GLOBAL_Control->AttachedDevice, v14, 48, i, i);
      }
      v17 = (_DWORD *)MmMapIoSpaceEx(i, 4096, 4);
      v18 = v17;
      if ( !v17 )
      {
        IsValid = -1073741670;
        goto LABEL_73;
      }
      v19 = 4096;
      IsValid = FveKeyringIsValid(v17);
      if ( IsValid < 0 )
        goto LABEL_72;
      v19 = v18[2];
      MmUnmapIoSpace(v18, 0x1000u);
      v20 = (_DWORD *)MmMapIoSpaceEx(i, v19, 4);
      v18 = v20;
      if ( !v20 )
      {
        IsValid = -1073741670;
        goto LABEL_73;
      }
      IsValid = FveKeyringIsValid(v20);
      if ( IsValid < 0 )
      {
LABEL_72:
        MmUnmapIoSpace(v18, v19);
      }
      else
      {
        *(_QWORD *)(v4 + 680) = v18;
        *(_BYTE *)(v4 + 776) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_d2beded7854932e8f171fa85139856d9_Traceguids,
            (unsigned int)v18[2]);
        }
        if ( *(_DWORD *)(v4 + 9692) )
          goto LABEL_73;
        CachedVmkTargetType = FveKeyringGetCachedVmkTargetType(*(_QWORD *)(v4 + 680), v21, v28, &BugCheckParameter4);
        if ( CachedVmkTargetType >= 0 )
        {
          v23 = v28[0];
          v24 = (unsigned int)BugCheckParameter4;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              33,
              WPP_d2beded7854932e8f171fa85139856d9_Traceguids,
              v28[0],
              BugCheckParameter4);
          }
          if ( (v23 & 0x1000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_d2beded7854932e8f171fa85139856d9_Traceguids);
            }
            if ( (*(_DWORD *)(v4 + 9680) & 0x2000) != 0 )
            {
              v25 = *(_QWORD *)(v4 + 680);
              v26 = *(unsigned int *)(v25 + 8);
              if ( (unsigned int)v26 < 0x4000 )
                v26 = 0x4000;
              FveSecureZeroAndFlush(v25, v26);
              KeBugCheckEx(0x120u, 0x11u, v4, v23, v24);
            }
          }
          goto LABEL_73;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v11 = 32;
          v12 = (unsigned int)CachedVmkTargetType;
          goto LABEL_28;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v11 = 28;
        v12 = (unsigned int)v8;
LABEL_28:
        WPP_SF_d(v10->AttachedDevice, v11, WPP_d2beded7854932e8f171fa85139856d9_Traceguids, v12);
      }
    }
LABEL_73:
    if ( Pool2 )
      ExFreePoolWithTag((PVOID)Pool2, 0x30455646u);
    goto LABEL_75;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return (unsigned int)IsValid;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_d2beded7854932e8f171fa85139856d9_Traceguids, (unsigned int)v6);
LABEL_75:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      35,
      WPP_d2beded7854932e8f171fa85139856d9_Traceguids,
      (unsigned int)IsValid);
  }
  return (unsigned int)IsValid;
}

```

## disassembly

```asm
0x1400eb078  mov     [rsp-8+arg_8], rbx
0x1400eb07d  mov     [rsp-8+arg_10], rsi
0x1400eb082  push    rbp
0x1400eb083  push    rdi
0x1400eb084  push    r13
0x1400eb086  push    r14
0x1400eb088  push    r15
0x1400eb08a  lea     rbp, [rsp-37h]
0x1400eb08f  sub     rsp, 0B0h
0x1400eb096  mov     rax, cs:__security_cookie
0x1400eb09d  xor     rax, rsp
0x1400eb0a0  mov     [rbp+57h+var_28], rax
0x1400eb0a4  xorps   xmm0, xmm0
0x1400eb0a7  xor     eax, eax
0x1400eb0a9  xorps   xmm1, xmm1
0x1400eb0ac  mov     [rbp+57h+KeyHandle], rax
0x1400eb0b0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400eb0b4  mov     rdi, rcx
0x1400eb0b7  mov     [rbp+57h+var_9C], eax
0x1400eb0ba  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400eb0be  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400eb0c2  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1400eb0c6  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400eb0ca  movups  [rbp+57h+KeyValueInformation], xmm0
0x1400eb0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb0d5  lea     r15, WPP_GLOBAL_Control
0x1400eb0dc  cmp     rcx, r15
0x1400eb0df  jz      short loc_1400EB103
0x1400eb0e1  test    dword ptr [rcx+2Ch], 8000h
0x1400eb0e8  jz      short loc_1400EB103
0x1400eb0ea  cmp     byte ptr [rcx+29h], 5
0x1400eb0ee  jb      short loc_1400EB103
0x1400eb0f0  mov     rcx, [rcx+18h]
0x1400eb0f4  lea     edx, [rax+1Ah]
0x1400eb0f7  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400eb0fe  call    WPP_SF_
0x1400eb103  xor     eax, eax
0x1400eb105  xor     ebx, ebx
0x1400eb107  mov     rdx, rdi; ClientIdentificationAddress
0x1400eb10a  mov     [rbp+57h+var_9C], ebx
0x1400eb10d  mov     rcx, rdi; DriverObject
0x1400eb110  mov     [rbp+57h+var_A0], ax
0x1400eb114  mov     dword ptr [rbp+57h+BugCheckParameter4], eax
0x1400eb117  call    cs:__imp_IoGetDriverObjectExtension
0x1400eb11e  nop     dword ptr [rax+rax+00h]
0x1400eb123  mov     rdi, rax
0x1400eb126  cmp     [rax+2A8h], rbx
0x1400eb12d  jnz     loc_1400EB618
0x1400eb133  cmp     [rax+2629h], bl
0x1400eb139  jz      short loc_1400EB158
0x1400eb13b  cmp     [rax+262Ah], bl
0x1400eb141  jz      short loc_1400EB158
0x1400eb143  mov     rcx, rax
0x1400eb146  call    GetKeyRingFromKsr
0x1400eb14b  cmp     eax, 0C0000225h
0x1400eb150  cmovnz  ebx, eax
0x1400eb153  jmp     loc_1400EB618
0x1400eb158  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400eb15f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400eb163  call    cs:__imp_RtlInitUnicodeString
0x1400eb16a  nop     dword ptr [rax+rax+00h]
0x1400eb16f  lea     rax, [rbp+57h+DestinationString]
0x1400eb173  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400eb17a  xorps   xmm0, xmm0
0x1400eb17d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400eb181  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400eb185  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1400eb189  mov     edx, 20019h; DesiredAccess
0x1400eb18e  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400eb195  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400eb199  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400eb19e  call    cs:__imp_ZwOpenKey
0x1400eb1a5  nop     dword ptr [rax+rax+00h]
0x1400eb1aa  mov     r9d, eax
0x1400eb1ad  test    eax, eax
0x1400eb1af  jns     short loc_1400EB1F2
0x1400eb1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb1b8  cmp     rcx, r15
0x1400eb1bb  jz      loc_1400EB64B
0x1400eb1c1  test    dword ptr [rcx+2Ch], 8000h
0x1400eb1c8  jz      loc_1400EB618
0x1400eb1ce  cmp     byte ptr [rcx+29h], 2
0x1400eb1d2  jb      loc_1400EB618
0x1400eb1d8  mov     rcx, [rcx+18h]
0x1400eb1dc  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400eb1e3  mov     edx, 1Bh
0x1400eb1e8  call    WPP_SF_d
0x1400eb1ed  jmp     loc_1400EB618
0x1400eb1f2  lea     rdx, aSystemstartopt; "SystemStartOptions"
0x1400eb1f9  xor     r13d, r13d
0x1400eb1fc  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1400eb200  call    cs:__imp_RtlInitUnicodeString
0x1400eb207  nop     dword ptr [rax+rax+00h]
0x1400eb20c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400eb210  lea     rax, [rbp+57h+var_9C]
0x1400eb214  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1400eb219  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400eb21d  lea     r8d, [r13+2]; KeyValueInformationClass
0x1400eb221  mov     [rsp+0D0h+Length], 10h; Length
0x1400eb229  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400eb22d  call    cs:__imp_ZwQueryValueKey
0x1400eb234  nop     dword ptr [rax+rax+00h]
0x1400eb239  mov     ecx, 80000000h
0x1400eb23e  mov     esi, eax
0x1400eb240  add     eax, ecx
0x1400eb242  test    ecx, eax
0x1400eb244  jnz     short loc_1400EB24E
0x1400eb246  cmp     esi, 80000005h
0x1400eb24c  jnz     short loc_1400EB2B4
0x1400eb24e  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 1
0x1400eb252  jz      short loc_1400EB25B
0x1400eb254  mov     esi, 0C000000Dh
0x1400eb259  jmp     short loc_1400EB2B4
0x1400eb25b  mov     esi, [rbp+57h+var_9C]
0x1400eb25e  mov     ecx, 40h ; '@'
0x1400eb263  mov     r8d, 30455646h
0x1400eb269  lea     rdx, [rsi+2]
0x1400eb26d  call    cs:__imp_ExAllocatePool2
0x1400eb274  nop     dword ptr [rax+rax+00h]
0x1400eb279  mov     r13, rax
0x1400eb27c  test    rax, rax
0x1400eb27f  jnz     short loc_1400EB288
0x1400eb281  mov     esi, 0C0000017h
0x1400eb286  jmp     short loc_1400EB2B4
0x1400eb288  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400eb28c  lea     rax, [rbp+57h+var_9C]
0x1400eb290  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1400eb295  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400eb299  mov     r9, r13; KeyValueInformation
0x1400eb29c  mov     [rsp+0D0h+Length], esi; Length
0x1400eb2a0  mov     r8d, 2; KeyValueInformationClass
0x1400eb2a6  call    cs:__imp_ZwQueryValueKey
0x1400eb2ad  nop     dword ptr [rax+rax+00h]
0x1400eb2b2  mov     esi, eax
0x1400eb2b4  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400eb2b8  call    cs:__imp_ZwClose
0x1400eb2bf  nop     dword ptr [rax+rax+00h]
0x1400eb2c4  test    esi, esi
0x1400eb2c6  jns     short loc_1400EB30C
0x1400eb2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb2cf  cmp     rcx, r15
0x1400eb2d2  jz      loc_1400EB5FF
0x1400eb2d8  test    dword ptr [rcx+2Ch], 8000h
0x1400eb2df  jz      loc_1400EB5FF
0x1400eb2e5  cmp     byte ptr [rcx+29h], 2
0x1400eb2e9  jb      loc_1400EB5FF
0x1400eb2ef  mov     edx, 1Ch
0x1400eb2f4  mov     r9d, esi
0x1400eb2f7  mov     rcx, [rcx+18h]
0x1400eb2fb  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400eb302  call    WPP_SF_d
0x1400eb307  jmp     loc_1400EB5FF
0x1400eb30c  mov     eax, [r13+8]
0x1400eb310  lea     rdx, aFveboot; "FVEBOOT="
0x1400eb317  xor     ecx, ecx
0x1400eb319  mov     [rax+r13+0Ch], cx
0x1400eb31f  lea     rcx, [r13+0Ch]; Str
0x1400eb323  call    cs:__imp_wcsstr
0x1400eb32a  nop     dword ptr [rax+rax+00h]
0x1400eb32f  mov     rdx, rax
0x1400eb332  test    rax, rax
0x1400eb335  jz      loc_1400EB5FF
0x1400eb33b  add     rdx, 10h
0x1400eb33f  xor     r14d, r14d
0x1400eb342  lea     r8d, [r14+30h]
0x1400eb346  jmp     short loc_1400EB361
0x1400eb348  cmp     ax, 39h ; '9'
0x1400eb34c  ja      short loc_1400EB36A
0x1400eb34e  lea     r14, [r14+r14*4]
0x1400eb352  movzx   eax, ax
0x1400eb355  lea     r14, [r14-18h]
0x1400eb359  add     rdx, 2
0x1400eb35d  lea     r14, [rax+r14*2]
0x1400eb361  movzx   eax, word ptr [rdx]
0x1400eb364  cmp     ax, r8w
0x1400eb368  jnb     short loc_1400EB348
0x1400eb36a  mov     ecx, 0FFDFh
0x1400eb36f  test    [rdx], cx
0x1400eb372  jz      short loc_1400EB3B5
0x1400eb374  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb37b  cmp     rcx, r15
0x1400eb37e  jz      loc_1400EB5FF
0x1400eb384  test    dword ptr [rcx+2Ch], 8000h
0x1400eb38b  jz      loc_1400EB5FF
0x1400eb391  cmp     byte ptr [rcx+29h], 3
0x1400eb395  jb      loc_1400EB5FF
0x1400eb39b  mov     rcx, [rcx+18h]
0x1400eb39f  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400eb3a6  mov     edx, 1Dh
0x1400eb3ab  call    WPP_SF_
0x1400eb3b0  jmp     loc_1400EB5FF
0x1400eb3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb3bc  cmp     rcx, r15
0x1400eb3bf  jz      short loc_1400EB3E1
0x1400eb3c1  test    dword ptr [rcx+2Ch], 8000h
0x1400eb3c8  jz      short loc_1400EB3E1
0x1400eb3ca  cmp     byte ptr [rcx+29h], 5
0x1400eb3ce  jb      short loc_1400EB3E1
0x1400eb3d0  mov     rcx, [rcx+18h]
0x1400eb3d4  mov     r9, r14
0x1400eb3d7  mov     qword ptr [rsp+0D0h+Length], r14
0x1400eb3dc  call    WPP_SF_Ii
0x1400eb3e1  mov     ebx, 1000h
0x1400eb3e6  mov     r8d, 4
0x1400eb3ec  mov     edx, ebx
0x1400eb3ee  mov     rcx, r14
0x1400eb3f1  call    cs:__imp_MmMapIoSpaceEx
0x1400eb3f8  nop     dword ptr [rax+rax+00h]
0x1400eb3fd  mov     rsi, rax
0x1400eb400  test    rax, rax
0x1400eb403  jnz     short loc_1400EB40F
0x1400eb405  mov     ebx, 0C000009Ah
0x1400eb40a  jmp     loc_1400EB5FF
0x1400eb40f  mov     r8b, 1
0x1400eb412  mov     rdx, rbx
0x1400eb415  mov     rcx, rsi; Source1
0x1400eb418  mov     r15d, ebx
0x1400eb41b  call    FveKeyringIsValid
0x1400eb420  mov     ebx, eax
0x1400eb422  test    eax, eax
0x1400eb424  js      loc_1400EB5E6
0x1400eb42a  mov     r15d, [rsi+8]
0x1400eb42e  mov     edx, 1000h; NumberOfBytes
0x1400eb433  mov     rcx, rsi; BaseAddress
0x1400eb436  call    cs:__imp_MmUnmapIoSpace
0x1400eb43d  nop     dword ptr [rax+rax+00h]
0x1400eb442  mov     r8d, 4
0x1400eb448  mov     edx, r15d
0x1400eb44b  mov     rcx, r14
0x1400eb44e  call    cs:__imp_MmMapIoSpaceEx
0x1400eb455  nop     dword ptr [rax+rax+00h]
0x1400eb45a  mov     rsi, rax
0x1400eb45d  test    rax, rax
0x1400eb460  jnz     short loc_1400EB46C
0x1400eb462  mov     ebx, 0C000009Ah
0x1400eb467  jmp     loc_1400EB5F8
0x1400eb46c  xor     r8d, r8d
0x1400eb46f  mov     rdx, r15
0x1400eb472  mov     rcx, rsi; Source1
0x1400eb475  call    FveKeyringIsValid
0x1400eb47a  mov     ebx, eax
0x1400eb47c  test    eax, eax
0x1400eb47e  js      loc_1400EB5E6
0x1400eb484  mov     [rdi+2A8h], rsi
0x1400eb48b  mov     byte ptr [rdi+308h], 0
0x1400eb492  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb499  lea     r15, WPP_GLOBAL_Control
0x1400eb4a0  cmp     rcx, r15
0x1400eb4a3  jz      short loc_1400EB4CB
0x1400eb4a5  mov     eax, [rcx+2Ch]
0x1400eb4a8  test    al, 4
0x1400eb4aa  jz      short loc_1400EB4CB
0x1400eb4ac  cmp     byte ptr [rcx+29h], 5
0x1400eb4b0  jb      short loc_1400EB4CB
0x1400eb4b2  mov     r9d, [rsi+8]
0x1400eb4b6  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400eb4bd  mov     rcx, [rcx+18h]
0x1400eb4c1  mov     edx, 1Fh
0x1400eb4c6  call    WPP_SF_d
0x1400eb4cb  cmp     dword ptr [rdi+25DCh], 0
0x1400eb4d2  jnz     loc_1400EB5FF
0x1400eb4d8  mov     rcx, [rdi+2A8h]
0x1400eb4df  lea     r9, [rbp+57h+BugCheckParameter4]
0x1400eb4e3  lea     r8, [rbp+57h+var_A0]
0x1400eb4e7  call    FveKeyringGetCachedVmkTargetType
0x1400eb4ec  test    eax, eax
0x1400eb4ee  jns     short loc_1400EB524
0x1400eb4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb4f7  cmp     rcx, r15
0x1400eb4fa  jz      loc_1400EB5FF
0x1400eb500  test    dword ptr [rcx+2Ch], 8000h
0x1400eb507  jz      loc_1400EB5FF
0x1400eb50d  cmp     byte ptr [rcx+29h], 2
0x1400eb511  jb      loc_1400EB5FF
0x1400eb517  mov     edx, 20h ; ' '
0x1400eb51c  mov     r9d, eax
0x1400eb51f  jmp     loc_1400EB2F7
0x1400eb524  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb52b  movzx   esi, [rbp+57h+var_A0]
0x1400eb52f  mov     r14d, dword ptr [rbp+57h+BugCheckParameter4]
0x1400eb533  cmp     rcx, r15
0x1400eb536  jz      short loc_1400EB564
0x1400eb538  test    dword ptr [rcx+2Ch], 8000h
0x1400eb53f  jz      short loc_1400EB564
0x1400eb541  cmp     byte ptr [rcx+29h], 5
0x1400eb545  jb      short loc_1400EB564
0x1400eb547  mov     rcx, [rcx+18h]
0x1400eb54b  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400eb552  mov     r9d, esi
0x1400eb555  mov     [rsp+0D0h+Length], r14d
0x1400eb55a  mov     edx, 21h ; '!'
0x1400eb55f  call    WPP_SF_Dd
0x1400eb564  bt      si, 0Ch
0x1400eb569  jnb     loc_1400EB5FF
0x1400eb56f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400eb576  cmp     rcx, r15
0x1400eb579  jz      short loc_1400EB59F
0x1400eb57b  test    dword ptr [rcx+2Ch], 8000h
0x1400eb582  jz      short loc_1400EB59F
0x1400eb584  cmp     byte ptr [rcx+29h], 3
  ... truncated ...
```
