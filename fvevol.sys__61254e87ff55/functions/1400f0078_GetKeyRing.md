# GetKeyRing

- ea: `0x1400f0078`
- end: `0x1400f0676`
- name: `GetKeyRing`
- size: `1534`
- prototype: `__int64 __fastcall(PVOID ClientIdentificationAddress)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400f06e0`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x14000b008`
- `0x140012a88`
- `0x14001330c`
- `0x140022bf0`
- `0x14002f59c`
- `0x1400f0078`
- `0x1400f116c`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400f05d9`
- `ntoskrnl!KeBugCheckEx` at `0x1400f05d9`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400f0436`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400f05ec`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400f0436`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400f05ec`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400f03f1`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400f044e`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400f03f1`
- `ntoskrnl!MmMapIoSpaceEx` at `0x1400f044e`
- `ntoskrnl!ZwOpenKey` at `0x1400f019e`
- `ntoskrnl!ZwOpenKey` at `0x1400f019e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f060c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f060c`
- `ntoskrnl!ZwClose` at `0x1400f02b8`
- `ntoskrnl!ZwClose` at `0x1400f02b8`
- `ntoskrnl!wcsstr` at `0x1400f0323`
- `ntoskrnl!wcsstr` at `0x1400f0323`
- `ntoskrnl!ExAllocatePool2` at `0x1400f026d`
- `ntoskrnl!ExAllocatePool2` at `0x1400f026d`
- `ntoskrnl!ZwQueryValueKey` at `0x1400f022d`
- `ntoskrnl!ZwQueryValueKey` at `0x1400f02a6`
- `ntoskrnl!ZwQueryValueKey` at `0x1400f022d`
- `ntoskrnl!ZwQueryValueKey` at `0x1400f02a6`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400f0117`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400f0117`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f0163`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f0200`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f0163`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400f0200`

## string_xrefs

- `0x1400f0158`: `\Registry\Machine\System\CurrentControlSet\Control`

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
  if ( *((_BYTE *)DriverObjectExtension + 10017) && *((_BYTE *)DriverObjectExtension + 10018) )
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
        if ( *(_DWORD *)(v4 + 9940) )
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
            if ( (*(_DWORD *)(v4 + 9928) & 0x2000) != 0 )
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
0x1400f0078  mov     [rsp-8+arg_8], rbx
0x1400f007d  mov     [rsp-8+arg_10], rsi
0x1400f0082  push    rbp
0x1400f0083  push    rdi
0x1400f0084  push    r13
0x1400f0086  push    r14
0x1400f0088  push    r15
0x1400f008a  lea     rbp, [rsp-37h]
0x1400f008f  sub     rsp, 0B0h
0x1400f0096  mov     rax, cs:__security_cookie
0x1400f009d  xor     rax, rsp
0x1400f00a0  mov     [rbp+57h+var_28], rax
0x1400f00a4  xorps   xmm0, xmm0
0x1400f00a7  xor     eax, eax
0x1400f00a9  xorps   xmm1, xmm1
0x1400f00ac  mov     [rbp+57h+KeyHandle], rax
0x1400f00b0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400f00b4  mov     rdi, rcx
0x1400f00b7  mov     [rbp+57h+var_9C], eax
0x1400f00ba  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400f00be  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400f00c2  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1400f00c6  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400f00ca  movups  [rbp+57h+KeyValueInformation], xmm0
0x1400f00ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f00d5  lea     r15, WPP_GLOBAL_Control
0x1400f00dc  cmp     rcx, r15
0x1400f00df  jz      short loc_1400F0103
0x1400f00e1  test    dword ptr [rcx+2Ch], 8000h
0x1400f00e8  jz      short loc_1400F0103
0x1400f00ea  cmp     byte ptr [rcx+29h], 5
0x1400f00ee  jb      short loc_1400F0103
0x1400f00f0  mov     rcx, [rcx+18h]
0x1400f00f4  lea     edx, [rax+1Ah]
0x1400f00f7  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400f00fe  call    WPP_SF_
0x1400f0103  xor     eax, eax
0x1400f0105  xor     ebx, ebx
0x1400f0107  mov     rdx, rdi; ClientIdentificationAddress
0x1400f010a  mov     [rbp+57h+var_9C], ebx
0x1400f010d  mov     rcx, rdi; DriverObject
0x1400f0110  mov     [rbp+57h+var_A0], ax
0x1400f0114  mov     dword ptr [rbp+57h+BugCheckParameter4], eax
0x1400f0117  call    cs:__imp_IoGetDriverObjectExtension
0x1400f011e  nop     dword ptr [rax+rax+00h]
0x1400f0123  mov     rdi, rax
0x1400f0126  cmp     [rax+2A8h], rbx
0x1400f012d  jnz     loc_1400F0618
0x1400f0133  cmp     [rax+2721h], bl
0x1400f0139  jz      short loc_1400F0158
0x1400f013b  cmp     [rax+2722h], bl
0x1400f0141  jz      short loc_1400F0158
0x1400f0143  mov     rcx, rax
0x1400f0146  call    GetKeyRingFromKsr
0x1400f014b  cmp     eax, 0C0000225h
0x1400f0150  cmovnz  ebx, eax
0x1400f0153  jmp     loc_1400F0618
0x1400f0158  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400f015f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400f0163  call    cs:__imp_RtlInitUnicodeString
0x1400f016a  nop     dword ptr [rax+rax+00h]
0x1400f016f  lea     rax, [rbp+57h+DestinationString]
0x1400f0173  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400f017a  xorps   xmm0, xmm0
0x1400f017d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400f0181  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400f0185  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1400f0189  mov     edx, 20019h; DesiredAccess
0x1400f018e  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400f0195  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400f0199  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400f019e  call    cs:__imp_ZwOpenKey
0x1400f01a5  nop     dword ptr [rax+rax+00h]
0x1400f01aa  mov     r9d, eax
0x1400f01ad  test    eax, eax
0x1400f01af  jns     short loc_1400F01F2
0x1400f01b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f01b8  cmp     rcx, r15
0x1400f01bb  jz      loc_1400F064B
0x1400f01c1  test    dword ptr [rcx+2Ch], 8000h
0x1400f01c8  jz      loc_1400F0618
0x1400f01ce  cmp     byte ptr [rcx+29h], 2
0x1400f01d2  jb      loc_1400F0618
0x1400f01d8  mov     rcx, [rcx+18h]
0x1400f01dc  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400f01e3  mov     edx, 1Bh
0x1400f01e8  call    WPP_SF_d
0x1400f01ed  jmp     loc_1400F0618
0x1400f01f2  lea     rdx, aSystemstartopt; "SystemStartOptions"
0x1400f01f9  xor     r13d, r13d
0x1400f01fc  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1400f0200  call    cs:__imp_RtlInitUnicodeString
0x1400f0207  nop     dword ptr [rax+rax+00h]
0x1400f020c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400f0210  lea     rax, [rbp+57h+var_9C]
0x1400f0214  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1400f0219  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400f021d  lea     r8d, [r13+2]; KeyValueInformationClass
0x1400f0221  mov     [rsp+0D0h+Length], 10h; Length
0x1400f0229  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400f022d  call    cs:__imp_ZwQueryValueKey
0x1400f0234  nop     dword ptr [rax+rax+00h]
0x1400f0239  mov     ecx, 80000000h
0x1400f023e  mov     esi, eax
0x1400f0240  add     eax, ecx
0x1400f0242  test    ecx, eax
0x1400f0244  jnz     short loc_1400F024E
0x1400f0246  cmp     esi, 80000005h
0x1400f024c  jnz     short loc_1400F02B4
0x1400f024e  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 1
0x1400f0252  jz      short loc_1400F025B
0x1400f0254  mov     esi, 0C000000Dh
0x1400f0259  jmp     short loc_1400F02B4
0x1400f025b  mov     esi, [rbp+57h+var_9C]
0x1400f025e  mov     ecx, 40h ; '@'
0x1400f0263  mov     r8d, 30455646h
0x1400f0269  lea     rdx, [rsi+2]
0x1400f026d  call    cs:__imp_ExAllocatePool2
0x1400f0274  nop     dword ptr [rax+rax+00h]
0x1400f0279  mov     r13, rax
0x1400f027c  test    rax, rax
0x1400f027f  jnz     short loc_1400F0288
0x1400f0281  mov     esi, 0C0000017h
0x1400f0286  jmp     short loc_1400F02B4
0x1400f0288  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400f028c  lea     rax, [rbp+57h+var_9C]
0x1400f0290  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x1400f0295  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400f0299  mov     r9, r13; KeyValueInformation
0x1400f029c  mov     [rsp+0D0h+Length], esi; Length
0x1400f02a0  mov     r8d, 2; KeyValueInformationClass
0x1400f02a6  call    cs:__imp_ZwQueryValueKey
0x1400f02ad  nop     dword ptr [rax+rax+00h]
0x1400f02b2  mov     esi, eax
0x1400f02b4  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400f02b8  call    cs:__imp_ZwClose
0x1400f02bf  nop     dword ptr [rax+rax+00h]
0x1400f02c4  test    esi, esi
0x1400f02c6  jns     short loc_1400F030C
0x1400f02c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f02cf  cmp     rcx, r15
0x1400f02d2  jz      loc_1400F05FF
0x1400f02d8  test    dword ptr [rcx+2Ch], 8000h
0x1400f02df  jz      loc_1400F05FF
0x1400f02e5  cmp     byte ptr [rcx+29h], 2
0x1400f02e9  jb      loc_1400F05FF
0x1400f02ef  mov     edx, 1Ch
0x1400f02f4  mov     r9d, esi
0x1400f02f7  mov     rcx, [rcx+18h]
0x1400f02fb  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400f0302  call    WPP_SF_d
0x1400f0307  jmp     loc_1400F05FF
0x1400f030c  mov     eax, [r13+8]
0x1400f0310  lea     rdx, aFveboot; "FVEBOOT="
0x1400f0317  xor     ecx, ecx
0x1400f0319  mov     [rax+r13+0Ch], cx
0x1400f031f  lea     rcx, [r13+0Ch]; Str
0x1400f0323  call    cs:__imp_wcsstr
0x1400f032a  nop     dword ptr [rax+rax+00h]
0x1400f032f  mov     rdx, rax
0x1400f0332  test    rax, rax
0x1400f0335  jz      loc_1400F05FF
0x1400f033b  add     rdx, 10h
0x1400f033f  xor     r14d, r14d
0x1400f0342  lea     r8d, [r14+30h]
0x1400f0346  jmp     short loc_1400F0361
0x1400f0348  cmp     ax, 39h ; '9'
0x1400f034c  ja      short loc_1400F036A
0x1400f034e  lea     r14, [r14+r14*4]
0x1400f0352  movzx   eax, ax
0x1400f0355  lea     r14, [r14-18h]
0x1400f0359  add     rdx, 2
0x1400f035d  lea     r14, [rax+r14*2]
0x1400f0361  movzx   eax, word ptr [rdx]
0x1400f0364  cmp     ax, r8w
0x1400f0368  jnb     short loc_1400F0348
0x1400f036a  mov     ecx, 0FFDFh
0x1400f036f  test    [rdx], cx
0x1400f0372  jz      short loc_1400F03B5
0x1400f0374  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f037b  cmp     rcx, r15
0x1400f037e  jz      loc_1400F05FF
0x1400f0384  test    dword ptr [rcx+2Ch], 8000h
0x1400f038b  jz      loc_1400F05FF
0x1400f0391  cmp     byte ptr [rcx+29h], 3
0x1400f0395  jb      loc_1400F05FF
0x1400f039b  mov     rcx, [rcx+18h]
0x1400f039f  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400f03a6  mov     edx, 1Dh
0x1400f03ab  call    WPP_SF_
0x1400f03b0  jmp     loc_1400F05FF
0x1400f03b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f03bc  cmp     rcx, r15
0x1400f03bf  jz      short loc_1400F03E1
0x1400f03c1  test    dword ptr [rcx+2Ch], 8000h
0x1400f03c8  jz      short loc_1400F03E1
0x1400f03ca  cmp     byte ptr [rcx+29h], 5
0x1400f03ce  jb      short loc_1400F03E1
0x1400f03d0  mov     rcx, [rcx+18h]
0x1400f03d4  mov     r9, r14
0x1400f03d7  mov     qword ptr [rsp+0D0h+Length], r14
0x1400f03dc  call    WPP_SF_Ii
0x1400f03e1  mov     ebx, 1000h
0x1400f03e6  mov     r8d, 4
0x1400f03ec  mov     edx, ebx
0x1400f03ee  mov     rcx, r14
0x1400f03f1  call    cs:__imp_MmMapIoSpaceEx
0x1400f03f8  nop     dword ptr [rax+rax+00h]
0x1400f03fd  mov     rsi, rax
0x1400f0400  test    rax, rax
0x1400f0403  jnz     short loc_1400F040F
0x1400f0405  mov     ebx, 0C000009Ah
0x1400f040a  jmp     loc_1400F05FF
0x1400f040f  mov     r8b, 1
0x1400f0412  mov     rdx, rbx
0x1400f0415  mov     rcx, rsi; Source1
0x1400f0418  mov     r15d, ebx
0x1400f041b  call    FveKeyringIsValid
0x1400f0420  mov     ebx, eax
0x1400f0422  test    eax, eax
0x1400f0424  js      loc_1400F05E6
0x1400f042a  mov     r15d, [rsi+8]
0x1400f042e  mov     edx, 1000h; NumberOfBytes
0x1400f0433  mov     rcx, rsi; BaseAddress
0x1400f0436  call    cs:__imp_MmUnmapIoSpace
0x1400f043d  nop     dword ptr [rax+rax+00h]
0x1400f0442  mov     r8d, 4
0x1400f0448  mov     edx, r15d
0x1400f044b  mov     rcx, r14
0x1400f044e  call    cs:__imp_MmMapIoSpaceEx
0x1400f0455  nop     dword ptr [rax+rax+00h]
0x1400f045a  mov     rsi, rax
0x1400f045d  test    rax, rax
0x1400f0460  jnz     short loc_1400F046C
0x1400f0462  mov     ebx, 0C000009Ah
0x1400f0467  jmp     loc_1400F05F8
0x1400f046c  xor     r8d, r8d
0x1400f046f  mov     rdx, r15
0x1400f0472  mov     rcx, rsi; Source1
0x1400f0475  call    FveKeyringIsValid
0x1400f047a  mov     ebx, eax
0x1400f047c  test    eax, eax
0x1400f047e  js      loc_1400F05E6
0x1400f0484  mov     [rdi+2A8h], rsi
0x1400f048b  mov     byte ptr [rdi+308h], 0
0x1400f0492  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f0499  lea     r15, WPP_GLOBAL_Control
0x1400f04a0  cmp     rcx, r15
0x1400f04a3  jz      short loc_1400F04CB
0x1400f04a5  mov     eax, [rcx+2Ch]
0x1400f04a8  test    al, 4
0x1400f04aa  jz      short loc_1400F04CB
0x1400f04ac  cmp     byte ptr [rcx+29h], 5
0x1400f04b0  jb      short loc_1400F04CB
0x1400f04b2  mov     r9d, [rsi+8]
0x1400f04b6  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400f04bd  mov     rcx, [rcx+18h]
0x1400f04c1  mov     edx, 1Fh
0x1400f04c6  call    WPP_SF_d
0x1400f04cb  cmp     dword ptr [rdi+26D4h], 0
0x1400f04d2  jnz     loc_1400F05FF
0x1400f04d8  mov     rcx, [rdi+2A8h]
0x1400f04df  lea     r9, [rbp+57h+BugCheckParameter4]
0x1400f04e3  lea     r8, [rbp+57h+var_A0]
0x1400f04e7  call    FveKeyringGetCachedVmkTargetType
0x1400f04ec  test    eax, eax
0x1400f04ee  jns     short loc_1400F0524
0x1400f04f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f04f7  cmp     rcx, r15
0x1400f04fa  jz      loc_1400F05FF
0x1400f0500  test    dword ptr [rcx+2Ch], 8000h
0x1400f0507  jz      loc_1400F05FF
0x1400f050d  cmp     byte ptr [rcx+29h], 2
0x1400f0511  jb      loc_1400F05FF
0x1400f0517  mov     edx, 20h ; ' '
0x1400f051c  mov     r9d, eax
0x1400f051f  jmp     loc_1400F02F7
0x1400f0524  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f052b  movzx   esi, [rbp+57h+var_A0]
0x1400f052f  mov     r14d, dword ptr [rbp+57h+BugCheckParameter4]
0x1400f0533  cmp     rcx, r15
0x1400f0536  jz      short loc_1400F0564
0x1400f0538  test    dword ptr [rcx+2Ch], 8000h
0x1400f053f  jz      short loc_1400F0564
0x1400f0541  cmp     byte ptr [rcx+29h], 5
0x1400f0545  jb      short loc_1400F0564
0x1400f0547  mov     rcx, [rcx+18h]
0x1400f054b  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x1400f0552  mov     r9d, esi
0x1400f0555  mov     [rsp+0D0h+Length], r14d
0x1400f055a  mov     edx, 21h ; '!'
0x1400f055f  call    WPP_SF_Dd
0x1400f0564  bt      si, 0Ch
0x1400f0569  jnb     loc_1400F05FF
0x1400f056f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f0576  cmp     rcx, r15
0x1400f0579  jz      short loc_1400F059F
0x1400f057b  test    dword ptr [rcx+2Ch], 8000h
0x1400f0582  jz      short loc_1400F059F
0x1400f0584  cmp     byte ptr [rcx+29h], 3
  ... truncated ...
```
