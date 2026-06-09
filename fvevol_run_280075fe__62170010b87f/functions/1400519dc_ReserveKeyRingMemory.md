# ReserveKeyRingMemory

- ea: `0x1400519dc`
- end: `0x14005202b`
- name: `ReserveKeyRingMemory`
- size: `1615`
- prototype: `__int64 __fastcall(PVOID ClientIdentificationAddress)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14009ec2c`
- `0x1400a0dec`

## callees

- `0x140006670`
- `0x1400074a4`
- `0x140007830`
- `0x140008dc0`
- `0x140008e44`
- `0x14000afa0`
- `0x140011b90`
- `0x1400218c0`
- `0x140021d00`
- `0x1400516f4`
- `0x1400519dc`
- `0x1400da91c`
- `0x1400daf2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140051fb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051fc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051fb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051fc9`
- `ntoskrnl!MmFreeContiguousMemory` at `0x140051f97`
- `ntoskrnl!MmFreeContiguousMemory` at `0x140051f97`
- `ntoskrnl!ZwClose` at `0x140051f7a`
- `ntoskrnl!ZwClose` at `0x140051f7a`
- `ntoskrnl!ZwSetValueKey` at `0x140051f0a`
- `ntoskrnl!ZwSetValueKey` at `0x140051f0a`
- `ntoskrnl!wcsstr` at `0x140051d79`
- `ntoskrnl!wcsstr` at `0x140051d79`
- `ntoskrnl!ExAllocatePool2` at `0x140051cc7`
- `ntoskrnl!ExAllocatePool2` at `0x140051deb`
- `ntoskrnl!ExAllocatePool2` at `0x140051e76`
- `ntoskrnl!ExAllocatePool2` at `0x140051cc7`
- `ntoskrnl!ExAllocatePool2` at `0x140051deb`
- `ntoskrnl!ExAllocatePool2` at `0x140051e76`
- `ntoskrnl!ZwQueryValueKey` at `0x140051c43`
- `ntoskrnl!ZwQueryValueKey` at `0x140051d0f`
- `ntoskrnl!ZwQueryValueKey` at `0x140051c43`
- `ntoskrnl!ZwQueryValueKey` at `0x140051d0f`
- `ntoskrnl!ZwCreateKey` at `0x140051baf`
- `ntoskrnl!ZwCreateKey` at `0x140051baf`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140051b44`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140051b44`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140051a06`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140051a06`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051b5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051c11`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051b5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051c11`

## string_xrefs

- `0x140051b50`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall ReserveKeyRingMemory(struct _DRIVER_OBJECT *ClientIdentificationAddress)
{
  char *DriverObjectExtension; // r14
  PVOID v2; // r15
  PVOID v3; // r12
  NTSTATUS KeyRingMemory; // edi
  wchar_t *v5; // r13
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  PVOID v9; // rcx
  PHYSICAL_ADDRESS PhysicalAddress; // rbx
  NTSTATUS v11; // eax
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  char *v15; // r12
  unsigned int v16; // eax
  unsigned int v17; // esi
  wchar_t *v18; // rax
  NTSTATUS v19; // eax
  wchar_t *Pool2; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  char *v25; // [rsp+48h] [rbp-B8h]
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  ULONG pulResult; // [rsp+58h] [rbp-A8h] BYREF
  PVOID BaseAddress; // [rsp+60h] [rbp-A0h] BYREF
  size_t pcbLength; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[64]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 KeyValueInformation; // [rsp+100h] [rbp+0h] BYREF

  DriverObjectExtension = (char *)IoGetDriverObjectExtension(ClientIdentificationAddress, ClientIdentificationAddress);
  memset(v33, 0, sizeof(v33));
  v2 = 0;
  KeyHandle = 0;
  v3 = 0;
  BaseAddress = 0;
  KeyRingMemory = 0;
  v25 = 0;
  ResultLength = 0;
  v5 = 0;
  pcbLength = 0;
  pulResult = 0;
  DestinationString = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_d2beded7854932e8f171fa85139856d9_Traceguids);
  }
  FvepLockAcquireLock((PFAST_MUTEX)(DriverObjectExtension + 688));
  if ( !*((_QWORD *)DriverObjectExtension + 85) )
  {
    v7 = *((_QWORD *)DriverObjectExtension + 84);
    if ( v7 )
      goto LABEL_14;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_d2beded7854932e8f171fa85139856d9_Traceguids);
    }
    KeyRingMemory = FvePreAllocateKeyRingMemory(DriverObjectExtension);
    if ( KeyRingMemory >= 0 )
    {
      v7 = *((_QWORD *)DriverObjectExtension + 84);
      if ( !v7 )
      {
        KeyRingMemory = -1073741670;
        goto LABEL_63;
      }
LABEL_14:
      v8 = FveKeyringCreate(v7, v6, &BaseAddress);
      v2 = BaseAddress;
      KeyRingMemory = v8;
      if ( v8 < 0 )
        goto LABEL_47;
      v9 = BaseAddress;
      *((_QWORD *)DriverObjectExtension + 84) = 0;
      PhysicalAddress = MmGetPhysicalAddress(v9);
      RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control");
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v11 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 1u, 0);
      KeyRingMemory = v11;
      if ( v11 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v13 = 20;
LABEL_20:
          v14 = (unsigned int)v11;
LABEL_21:
          WPP_SF_d(v12->AttachedDevice, v13, WPP_d2beded7854932e8f171fa85139856d9_Traceguids, v14);
          goto LABEL_47;
        }
        goto LABEL_47;
      }
      RtlInitUnicodeString(&ValueName, L"SystemStartOptions");
      KeyRingMemory = ZwQueryValueKey(
                        KeyHandle,
                        &ValueName,
                        KeyValuePartialInformation,
                        &KeyValueInformation,
                        0x10u,
                        &ResultLength);
      if ( (int)(KeyRingMemory + 0x80000000) >= 0 && KeyRingMemory != -2147483643 )
      {
        if ( KeyRingMemory != -1073741772 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v13 = 21;
            v14 = (unsigned int)KeyRingMemory;
            goto LABEL_21;
          }
          goto LABEL_47;
        }
LABEL_52:
        v17 = 82;
        Pool2 = (wchar_t *)ExAllocatePool2(256, 82, 809850438);
        v5 = Pool2;
        if ( Pool2 )
        {
          v19 = RtlStringCbPrintfW(Pool2, 0x52u, L" %s%I64u", L"FVEBOOT=", PhysicalAddress.QuadPart);
          goto LABEL_54;
        }
        goto LABEL_46;
      }
      if ( DWORD1(KeyValueInformation) == 1 )
      {
        v25 = (char *)ExAllocatePool2(256, ResultLength + 2LL, 809850438);
        v15 = v25;
        if ( !v25 )
        {
          KeyRingMemory = -1073741670;
          goto LABEL_47;
        }
        v11 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, v25, ResultLength, &ResultLength);
        KeyRingMemory = v11;
        if ( v11 == -1073741772 )
          goto LABEL_52;
        if ( v11 < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v13 = 22;
            goto LABEL_20;
          }
LABEL_47:
          if ( v2 )
          {
            v3 = v25;
            if ( !*((_QWORD *)DriverObjectExtension + 84) )
            {
              *((_QWORD *)DriverObjectExtension + 84) = v2;
              v2 = 0;
            }
            goto LABEL_63;
          }
LABEL_62:
          v3 = v25;
          goto LABEL_63;
        }
        *(_WORD *)&v15[*((unsigned int *)v15 + 2) + 12] = 0;
        if ( !wcsstr((const wchar_t *)v15 + 6, L"FVEBOOT=") )
        {
          v16 = *((_DWORD *)v15 + 2);
          v17 = v16 + 82;
          if ( v16 + 82 < v16 )
          {
            KeyRingMemory = -1073741675;
            goto LABEL_47;
          }
          v18 = (wchar_t *)ExAllocatePool2(256, v17, 809850438);
          v5 = v18;
          if ( v18 )
          {
            v19 = RtlStringCbPrintfW(v18, v17, L"%s  %s%I64u", v25 + 12, L"FVEBOOT=", PhysicalAddress.QuadPart);
LABEL_54:
            KeyRingMemory = v19;
            if ( v19 >= 0 )
            {
              KeyRingMemory = RtlStringCbLengthW(v5, v17, &pcbLength);
              if ( KeyRingMemory >= 0 )
              {
                KeyRingMemory = RtlULongLongToULong(pcbLength, &pulResult);
                if ( KeyRingMemory >= 0 )
                {
                  KeyRingMemory = ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, v5, pulResult + 2);
                  if ( KeyRingMemory >= 0 )
                  {
                    *((_QWORD *)DriverObjectExtension + 85) = v2;
                    v2 = 0;
                    DriverObjectExtension[776] = 0;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                    {
                      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_Iii)(
                        WPP_GLOBAL_Control->AttachedDevice,
                        v21,
                        v22,
                        (PHYSICAL_ADDRESS)PhysicalAddress.QuadPart,
                        (PHYSICAL_ADDRESS)PhysicalAddress.QuadPart);
                    }
                    goto LABEL_62;
                  }
                }
              }
            }
            goto LABEL_47;
          }
LABEL_46:
          KeyRingMemory = -1073741670;
          goto LABEL_47;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_d2beded7854932e8f171fa85139856d9_Traceguids);
        }
      }
      KeyRingMemory = -1073741811;
      goto LABEL_47;
    }
  }
LABEL_63:
  FvepLockReleaseLock(v33);
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    KeyHandle = 0;
  }
  if ( v2 )
    MmFreeContiguousMemory(v2);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x30455646u);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      25,
      WPP_d2beded7854932e8f171fa85139856d9_Traceguids,
      (unsigned int)KeyRingMemory);
  }
  return (unsigned int)KeyRingMemory;
}

```

## disassembly

```asm
0x1400519dc  push    rbp
0x1400519de  push    rbx
0x1400519df  push    rsi
0x1400519e0  push    rdi
0x1400519e1  push    r12
0x1400519e3  push    r13
0x1400519e5  push    r14
0x1400519e7  push    r15
0x1400519e9  lea     rbp, [rsp-28h]
0x1400519ee  sub     rsp, 128h
0x1400519f5  mov     rax, cs:__security_cookie
0x1400519fc  xor     rax, rsp
0x1400519ff  mov     [rbp+60h+var_50], rax
0x140051a03  mov     rdx, rcx; ClientIdentificationAddress
0x140051a06  call    cs:__imp_IoGetDriverObjectExtension
0x140051a0d  nop     dword ptr [rax+rax+00h]
0x140051a12  xor     edx, edx; Val
0x140051a14  lea     rcx, [rbp+60h+var_A0]; void *
0x140051a18  mov     r14, rax
0x140051a1b  lea     r8d, [rdx+40h]; Size
0x140051a1f  call    memset
0x140051a24  xorps   xmm0, xmm0
0x140051a27  xor     eax, eax
0x140051a29  xor     r15d, r15d
0x140051a2c  mov     [rsp+160h+KeyHandle], rax
0x140051a31  xor     r12d, r12d
0x140051a34  mov     [rsp+160h+BaseAddress], r15
0x140051a39  xor     edi, edi
0x140051a3b  mov     [rsp+160h+var_118], r12
0x140051a40  xorps   xmm1, xmm1
0x140051a43  mov     [rsp+160h+ResultLength], eax
0x140051a47  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x140051a4b  xor     r13d, r13d
0x140051a4e  mov     [rsp+160h+pcbLength], rax
0x140051a53  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x140051a57  mov     [rsp+160h+pulResult], eax
0x140051a5b  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x140051a5f  movups  xmmword ptr [rsp+160h+ValueName.Length], xmm1
0x140051a64  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x140051a68  movups  [rbp+60h+KeyValueInformation], xmm0
0x140051a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a73  lea     rsi, WPP_GLOBAL_Control
0x140051a7a  cmp     rcx, rsi
0x140051a7d  jz      short loc_140051A9F
0x140051a7f  bt      dword ptr [rcx+2Ch], 0Fh
0x140051a84  jnb     short loc_140051A9F
0x140051a86  cmp     byte ptr [rcx+29h], 5
0x140051a8a  jb      short loc_140051A9F
0x140051a8c  mov     rcx, [rcx+18h]
0x140051a90  lea     edx, [rdi+12h]
0x140051a93  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x140051a9a  call    WPP_SF_
0x140051a9f  lea     rcx, [r14+2B0h]; FastMutex
0x140051aa6  mov     r8b, 1
0x140051aa9  lea     rdx, [rbp+60h+var_A0]
0x140051aad  call    FvepLockAcquireLock
0x140051ab2  cmp     [r14+2A8h], rdi
0x140051ab9  jnz     loc_140051F67
0x140051abf  mov     rcx, [r14+2A0h]
0x140051ac6  test    rcx, rcx
0x140051ac9  jnz     short loc_140051B21
0x140051acb  mov     rcx, cs:WPP_GLOBAL_Control
0x140051ad2  cmp     rcx, rsi
0x140051ad5  jz      short loc_140051AF9
0x140051ad7  bt      dword ptr [rcx+2Ch], 0Fh
0x140051adc  jnb     short loc_140051AF9
0x140051ade  cmp     byte ptr [rcx+29h], 5
0x140051ae2  jb      short loc_140051AF9
0x140051ae4  mov     rcx, [rcx+18h]
0x140051ae8  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x140051aef  mov     edx, 13h
0x140051af4  call    WPP_SF_
0x140051af9  mov     rcx, r14
0x140051afc  call    FvePreAllocateKeyRingMemory
0x140051b01  mov     edi, eax
0x140051b03  test    eax, eax
0x140051b05  js      loc_140051F67
0x140051b0b  mov     rcx, [r14+2A0h]
0x140051b12  test    rcx, rcx
0x140051b15  jnz     short loc_140051B21
0x140051b17  mov     edi, 0C000009Ah
0x140051b1c  jmp     loc_140051F67
0x140051b21  lea     r8, [rsp+160h+BaseAddress]
0x140051b26  call    FveKeyringCreate
0x140051b2b  mov     r15, [rsp+160h+BaseAddress]
0x140051b30  mov     edi, eax
0x140051b32  test    eax, eax
0x140051b34  js      loc_140051E0B
0x140051b3a  mov     rcx, r15; BaseAddress
0x140051b3d  mov     [r14+2A0h], r12
0x140051b44  call    cs:__imp_MmGetPhysicalAddress
0x140051b4b  nop     dword ptr [rax+rax+00h]
0x140051b50  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140051b57  mov     rbx, rax
0x140051b5a  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x140051b5e  call    cs:__imp_RtlInitUnicodeString
0x140051b65  nop     dword ptr [rax+rax+00h]
0x140051b6a  lea     rax, [rbp+60h+DestinationString]
0x140051b6e  mov     [rsp+160h+Disposition], r12; Disposition
0x140051b73  xorps   xmm0, xmm0
0x140051b76  mov     [rsp+160h+CreateOptions], 1; CreateOptions
0x140051b7e  xor     r9d, r9d; TitleIndex
0x140051b81  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x140051b85  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x140051b89  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x140051b90  mov     edx, 0F003Fh; DesiredAccess
0x140051b95  mov     [rbp+60h+ObjectAttributes.RootDirectory], r12
0x140051b99  lea     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x140051b9e  mov     [rbp+60h+ObjectAttributes.Attributes], 240h
0x140051ba5  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x140051baa  mov     [rsp+160h+Class], r12; Class
0x140051baf  call    cs:__imp_ZwCreateKey
0x140051bb6  nop     dword ptr [rax+rax+00h]
0x140051bbb  mov     edi, eax
0x140051bbd  test    eax, eax
0x140051bbf  jns     short loc_140051C05
0x140051bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140051bc8  cmp     rcx, rsi
0x140051bcb  jz      loc_140051E0B
0x140051bd1  test    dword ptr [rcx+2Ch], 8000h
0x140051bd8  jz      loc_140051E0B
0x140051bde  cmp     byte ptr [rcx+29h], 2
0x140051be2  jb      loc_140051E0B
0x140051be8  mov     edx, 14h
0x140051bed  mov     r9d, eax
0x140051bf0  mov     rcx, [rcx+18h]
0x140051bf4  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x140051bfb  call    WPP_SF_d
0x140051c00  jmp     loc_140051E0B
0x140051c05  lea     rdx, aSystemstartopt; "SystemStartOptions"
0x140051c0c  lea     rcx, [rsp+160h+ValueName]; DestinationString
0x140051c11  call    cs:__imp_RtlInitUnicodeString
0x140051c18  nop     dword ptr [rax+rax+00h]
0x140051c1d  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x140051c22  lea     rax, [rsp+160h+ResultLength]
0x140051c27  mov     qword ptr [rsp+160h+CreateOptions], rax; ResultLength
0x140051c2c  lea     r9, [rbp+60h+KeyValueInformation]; KeyValueInformation
0x140051c30  mov     r8d, 2; KeyValueInformationClass
0x140051c36  mov     dword ptr [rsp+160h+Class], 10h; Length
0x140051c3e  lea     rdx, [rsp+160h+ValueName]; ValueName
0x140051c43  call    cs:__imp_ZwQueryValueKey
0x140051c4a  nop     dword ptr [rax+rax+00h]
0x140051c4f  mov     ecx, 80000000h
0x140051c54  mov     edi, eax
0x140051c56  add     eax, ecx
0x140051c58  test    ecx, eax
0x140051c5a  jnz     short loc_140051CA4
0x140051c5c  cmp     edi, 80000005h
0x140051c62  jz      short loc_140051CA4
0x140051c64  cmp     edi, 0C0000034h
0x140051c6a  jz      loc_140051E64
0x140051c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140051c77  cmp     rcx, rsi
0x140051c7a  jz      loc_140051E0B
0x140051c80  test    dword ptr [rcx+2Ch], 8000h
0x140051c87  jz      loc_140051E0B
0x140051c8d  cmp     byte ptr [rcx+29h], 2
0x140051c91  jb      loc_140051E0B
0x140051c97  mov     edx, 15h
0x140051c9c  mov     r9d, edi
0x140051c9f  jmp     loc_140051BF0
0x140051ca4  cmp     dword ptr [rbp+60h+KeyValueInformation+4], 1
0x140051ca8  jz      short loc_140051CB4
0x140051caa  mov     edi, 0C000000Dh
0x140051caf  jmp     loc_140051E0B
0x140051cb4  mov     edx, [rsp+160h+ResultLength]
0x140051cb8  mov     ecx, 100h
0x140051cbd  add     rdx, 2
0x140051cc1  mov     r8d, 30455646h
0x140051cc7  call    cs:__imp_ExAllocatePool2
0x140051cce  nop     dword ptr [rax+rax+00h]
0x140051cd3  mov     [rsp+160h+var_118], rax
0x140051cd8  mov     r12, rax
0x140051cdb  test    rax, rax
0x140051cde  jnz     short loc_140051CEA
0x140051ce0  mov     edi, 0C000009Ah
0x140051ce5  jmp     loc_140051E0B
0x140051cea  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x140051cef  lea     rax, [rsp+160h+ResultLength]
0x140051cf4  mov     qword ptr [rsp+160h+CreateOptions], rax; ResultLength
0x140051cf9  lea     rdx, [rsp+160h+ValueName]; ValueName
0x140051cfe  mov     eax, [rsp+160h+ResultLength]
0x140051d02  mov     r9, r12; KeyValueInformation
0x140051d05  mov     r8d, 2; KeyValueInformationClass
0x140051d0b  mov     dword ptr [rsp+160h+Class], eax; Length
0x140051d0f  call    cs:__imp_ZwQueryValueKey
0x140051d16  nop     dword ptr [rax+rax+00h]
0x140051d1b  mov     edi, eax
0x140051d1d  cmp     eax, 0C0000034h
0x140051d22  jz      loc_140051E64
0x140051d28  test    eax, eax
0x140051d2a  jns     short loc_140051D5D
0x140051d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140051d33  cmp     rcx, rsi
0x140051d36  jz      loc_140051E0B
0x140051d3c  test    dword ptr [rcx+2Ch], 8000h
0x140051d43  jz      loc_140051E0B
0x140051d49  cmp     byte ptr [rcx+29h], 2
0x140051d4d  jb      loc_140051E0B
0x140051d53  mov     edx, 16h
0x140051d58  jmp     loc_140051BED
0x140051d5d  mov     eax, [r12+8]
0x140051d62  lea     rdi, aFveboot; "FVEBOOT="
0x140051d69  xor     ecx, ecx
0x140051d6b  mov     rdx, rdi; SubStr
0x140051d6e  mov     [rax+r12+0Ch], cx
0x140051d74  lea     rcx, [r12+0Ch]; Str
0x140051d79  call    cs:__imp_wcsstr
0x140051d80  nop     dword ptr [rax+rax+00h]
0x140051d85  test    rax, rax
0x140051d88  jz      short loc_140051DCB
0x140051d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051d91  cmp     rcx, rsi
0x140051d94  jz      loc_140051CAA
0x140051d9a  test    dword ptr [rcx+2Ch], 8000h
0x140051da1  jz      loc_140051CAA
0x140051da7  cmp     byte ptr [rcx+29h], 2
0x140051dab  jb      loc_140051CAA
0x140051db1  mov     rcx, [rcx+18h]
0x140051db5  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x140051dbc  mov     edx, 17h
0x140051dc1  call    WPP_SF_
0x140051dc6  jmp     loc_140051CAA
0x140051dcb  mov     eax, [r12+8]
0x140051dd0  lea     esi, [rax+52h]
0x140051dd3  cmp     esi, eax
0x140051dd5  jb      loc_140051E5D
0x140051ddb  mov     r8d, 30455646h
0x140051de1  mov     edx, esi
0x140051de3  mov     ecx, 100h
0x140051de8  mov     r12d, esi
0x140051deb  call    cs:__imp_ExAllocatePool2
0x140051df2  nop     dword ptr [rax+rax+00h]
0x140051df7  mov     r13, rax
0x140051dfa  test    rax, rax
0x140051dfd  jnz     short loc_140051E36
0x140051dff  mov     edi, 0C000009Ah
0x140051e04  lea     rsi, WPP_GLOBAL_Control
0x140051e0b  test    r15, r15
0x140051e0e  jz      loc_140051F62
0x140051e14  cmp     qword ptr [r14+2A0h], 0
0x140051e1c  mov     r12, [rsp+160h+var_118]
0x140051e21  jnz     loc_140051F67
0x140051e27  mov     [r14+2A0h], r15
0x140051e2e  xor     r15d, r15d
0x140051e31  jmp     loc_140051F67
0x140051e36  mov     r9, [rsp+160h+var_118]
0x140051e3b  lea     r8, aSSI64u; "%s  %s%I64u"
0x140051e42  add     r9, 0Ch
0x140051e46  mov     qword ptr [rsp+160h+CreateOptions], rbx
0x140051e4b  mov     rdx, r12; cbDest
0x140051e4e  mov     [rsp+160h+Class], rdi
0x140051e53  mov     rcx, rax; pszDest
0x140051e56  call    RtlStringCbPrintfW
0x140051e5b  jmp     short loc_140051EAB
0x140051e5d  mov     edi, 0C0000095h
0x140051e62  jmp     short loc_140051E04
0x140051e64  mov     esi, 52h ; 'R'
0x140051e69  mov     r8d, 30455646h
0x140051e6f  mov     edx, esi
0x140051e71  mov     ecx, 100h
0x140051e76  call    cs:__imp_ExAllocatePool2
0x140051e7d  nop     dword ptr [rax+rax+00h]
0x140051e82  mov     r13, rax
0x140051e85  test    rax, rax
0x140051e88  jz      loc_140051DFF
0x140051e8e  lea     r9, aFveboot; "FVEBOOT="
0x140051e95  mov     [rsp+160h+Class], rbx
0x140051e9a  lea     r8, aSI64u; " %s%I64u"
0x140051ea1  mov     edx, esi; cbDest
0x140051ea3  mov     rcx, rax; pszDest
0x140051ea6  call    RtlStringCbPrintfW
0x140051eab  mov     edi, eax
0x140051ead  test    eax, eax
0x140051eaf  js      loc_140051E04
0x140051eb5  mov     edx, esi; cbMax
0x140051eb7  lea     r8, [rsp+160h+pcbLength]; pcbLength
0x140051ebc  mov     rcx, r13; psz
0x140051ebf  call    RtlStringCbLengthW
0x140051ec4  mov     edi, eax
0x140051ec6  test    eax, eax
0x140051ec8  js      loc_140051E04
0x140051ece  mov     rcx, [rsp+160h+pcbLength]; ullOperand
0x140051ed3  lea     rdx, [rsp+160h+pulResult]; pulResult
0x140051ed8  call    RtlULongLongToULong
0x140051edd  mov     edi, eax
0x140051edf  test    eax, eax
0x140051ee1  js      loc_140051E04
0x140051ee7  mov     eax, [rsp+160h+pulResult]
0x140051eeb  lea     rdx, [rsp+160h+ValueName]; ValueName
0x140051ef0  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x140051ef5  add     eax, 2
0x140051ef8  mov     [rsp+160h+CreateOptions], eax; DataSize
0x140051efc  mov     r9d, 1; Type
0x140051f02  xor     r8d, r8d; TitleIndex
0x140051f05  mov     [rsp+160h+Class], r13; Data
0x140051f0a  call    cs:__imp_ZwSetValueKey
0x140051f11  nop     dword ptr [rax+rax+00h]
0x140051f16  mov     edi, eax
0x140051f18  test    eax, eax
  ... truncated ...
```
