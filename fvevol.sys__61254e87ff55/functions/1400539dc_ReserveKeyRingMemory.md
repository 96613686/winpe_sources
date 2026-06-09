# ReserveKeyRingMemory

- ea: `0x1400539dc`
- end: `0x14005402b`
- name: `ReserveKeyRingMemory`
- size: `1615`
- prototype: `__int64 __fastcall(PVOID ClientIdentificationAddress)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14009fb70`
- `0x1400a1d38`

## callees

- `0x140006730`
- `0x140007564`
- `0x1400078f0`
- `0x140008e80`
- `0x140008f04`
- `0x14000b060`
- `0x140012548`
- `0x140022bf0`
- `0x140023040`
- `0x1400536f4`
- `0x1400539dc`
- `0x1400dd18c`
- `0x1400dd79c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140053fb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053fc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053fb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140053fc9`
- `ntoskrnl!MmFreeContiguousMemory` at `0x140053f97`
- `ntoskrnl!MmFreeContiguousMemory` at `0x140053f97`
- `ntoskrnl!ZwClose` at `0x140053f7a`
- `ntoskrnl!ZwClose` at `0x140053f7a`
- `ntoskrnl!ZwSetValueKey` at `0x140053f0a`
- `ntoskrnl!ZwSetValueKey` at `0x140053f0a`
- `ntoskrnl!wcsstr` at `0x140053d79`
- `ntoskrnl!wcsstr` at `0x140053d79`
- `ntoskrnl!ExAllocatePool2` at `0x140053cc7`
- `ntoskrnl!ExAllocatePool2` at `0x140053deb`
- `ntoskrnl!ExAllocatePool2` at `0x140053e76`
- `ntoskrnl!ExAllocatePool2` at `0x140053cc7`
- `ntoskrnl!ExAllocatePool2` at `0x140053deb`
- `ntoskrnl!ExAllocatePool2` at `0x140053e76`
- `ntoskrnl!ZwQueryValueKey` at `0x140053c43`
- `ntoskrnl!ZwQueryValueKey` at `0x140053d0f`
- `ntoskrnl!ZwQueryValueKey` at `0x140053c43`
- `ntoskrnl!ZwQueryValueKey` at `0x140053d0f`
- `ntoskrnl!ZwCreateKey` at `0x140053baf`
- `ntoskrnl!ZwCreateKey` at `0x140053baf`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140053b44`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140053b44`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140053a06`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140053a06`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053b5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053c11`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053b5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140053c11`

## string_xrefs

- `0x140053b50`: `\Registry\Machine\System\CurrentControlSet\Control`

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
0x1400539dc  push    rbp
0x1400539de  push    rbx
0x1400539df  push    rsi
0x1400539e0  push    rdi
0x1400539e1  push    r12
0x1400539e3  push    r13
0x1400539e5  push    r14
0x1400539e7  push    r15
0x1400539e9  lea     rbp, [rsp-28h]
0x1400539ee  sub     rsp, 128h
0x1400539f5  mov     rax, cs:__security_cookie
0x1400539fc  xor     rax, rsp
0x1400539ff  mov     [rbp+60h+var_50], rax
0x140053a03  mov     rdx, rcx; ClientIdentificationAddress
0x140053a06  call    cs:__imp_IoGetDriverObjectExtension
0x140053a0d  nop     dword ptr [rax+rax+00h]
0x140053a12  xor     edx, edx; Val
0x140053a14  lea     rcx, [rbp+60h+var_A0]; void *
0x140053a18  mov     r14, rax
0x140053a1b  lea     r8d, [rdx+40h]; Size
0x140053a1f  call    memset
0x140053a24  xorps   xmm0, xmm0
0x140053a27  xor     eax, eax
0x140053a29  xor     r15d, r15d
0x140053a2c  mov     [rsp+160h+KeyHandle], rax
0x140053a31  xor     r12d, r12d
0x140053a34  mov     [rsp+160h+BaseAddress], r15
0x140053a39  xor     edi, edi
0x140053a3b  mov     [rsp+160h+var_118], r12
0x140053a40  xorps   xmm1, xmm1
0x140053a43  mov     [rsp+160h+ResultLength], eax
0x140053a47  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x140053a4b  xor     r13d, r13d
0x140053a4e  mov     [rsp+160h+pcbLength], rax
0x140053a53  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x140053a57  mov     [rsp+160h+pulResult], eax
0x140053a5b  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x140053a5f  movups  xmmword ptr [rsp+160h+ValueName.Length], xmm1
0x140053a64  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x140053a68  movups  [rbp+60h+KeyValueInformation], xmm0
0x140053a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140053a73  lea     rsi, WPP_GLOBAL_Control
0x140053a7a  cmp     rcx, rsi
0x140053a7d  jz      short loc_140053A9F
0x140053a7f  bt      dword ptr [rcx+2Ch], 0Fh
0x140053a84  jnb     short loc_140053A9F
0x140053a86  cmp     byte ptr [rcx+29h], 5
0x140053a8a  jb      short loc_140053A9F
0x140053a8c  mov     rcx, [rcx+18h]
0x140053a90  lea     edx, [rdi+12h]
0x140053a93  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x140053a9a  call    WPP_SF_
0x140053a9f  lea     rcx, [r14+2B0h]; FastMutex
0x140053aa6  mov     r8b, 1
0x140053aa9  lea     rdx, [rbp+60h+var_A0]
0x140053aad  call    FvepLockAcquireLock
0x140053ab2  cmp     [r14+2A8h], rdi
0x140053ab9  jnz     loc_140053F67
0x140053abf  mov     rcx, [r14+2A0h]
0x140053ac6  test    rcx, rcx
0x140053ac9  jnz     short loc_140053B21
0x140053acb  mov     rcx, cs:WPP_GLOBAL_Control
0x140053ad2  cmp     rcx, rsi
0x140053ad5  jz      short loc_140053AF9
0x140053ad7  bt      dword ptr [rcx+2Ch], 0Fh
0x140053adc  jnb     short loc_140053AF9
0x140053ade  cmp     byte ptr [rcx+29h], 5
0x140053ae2  jb      short loc_140053AF9
0x140053ae4  mov     rcx, [rcx+18h]
0x140053ae8  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x140053aef  mov     edx, 13h
0x140053af4  call    WPP_SF_
0x140053af9  mov     rcx, r14
0x140053afc  call    FvePreAllocateKeyRingMemory
0x140053b01  mov     edi, eax
0x140053b03  test    eax, eax
0x140053b05  js      loc_140053F67
0x140053b0b  mov     rcx, [r14+2A0h]
0x140053b12  test    rcx, rcx
0x140053b15  jnz     short loc_140053B21
0x140053b17  mov     edi, 0C000009Ah
0x140053b1c  jmp     loc_140053F67
0x140053b21  lea     r8, [rsp+160h+BaseAddress]
0x140053b26  call    FveKeyringCreate
0x140053b2b  mov     r15, [rsp+160h+BaseAddress]
0x140053b30  mov     edi, eax
0x140053b32  test    eax, eax
0x140053b34  js      loc_140053E0B
0x140053b3a  mov     rcx, r15; BaseAddress
0x140053b3d  mov     [r14+2A0h], r12
0x140053b44  call    cs:__imp_MmGetPhysicalAddress
0x140053b4b  nop     dword ptr [rax+rax+00h]
0x140053b50  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140053b57  mov     rbx, rax
0x140053b5a  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x140053b5e  call    cs:__imp_RtlInitUnicodeString
0x140053b65  nop     dword ptr [rax+rax+00h]
0x140053b6a  lea     rax, [rbp+60h+DestinationString]
0x140053b6e  mov     [rsp+160h+Disposition], r12; Disposition
0x140053b73  xorps   xmm0, xmm0
0x140053b76  mov     [rsp+160h+CreateOptions], 1; CreateOptions
0x140053b7e  xor     r9d, r9d; TitleIndex
0x140053b81  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x140053b85  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x140053b89  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x140053b90  mov     edx, 0F003Fh; DesiredAccess
0x140053b95  mov     [rbp+60h+ObjectAttributes.RootDirectory], r12
0x140053b99  lea     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x140053b9e  mov     [rbp+60h+ObjectAttributes.Attributes], 240h
0x140053ba5  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x140053baa  mov     [rsp+160h+Class], r12; Class
0x140053baf  call    cs:__imp_ZwCreateKey
0x140053bb6  nop     dword ptr [rax+rax+00h]
0x140053bbb  mov     edi, eax
0x140053bbd  test    eax, eax
0x140053bbf  jns     short loc_140053C05
0x140053bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140053bc8  cmp     rcx, rsi
0x140053bcb  jz      loc_140053E0B
0x140053bd1  test    dword ptr [rcx+2Ch], 8000h
0x140053bd8  jz      loc_140053E0B
0x140053bde  cmp     byte ptr [rcx+29h], 2
0x140053be2  jb      loc_140053E0B
0x140053be8  mov     edx, 14h
0x140053bed  mov     r9d, eax
0x140053bf0  mov     rcx, [rcx+18h]
0x140053bf4  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x140053bfb  call    WPP_SF_d
0x140053c00  jmp     loc_140053E0B
0x140053c05  lea     rdx, aSystemstartopt; "SystemStartOptions"
0x140053c0c  lea     rcx, [rsp+160h+ValueName]; DestinationString
0x140053c11  call    cs:__imp_RtlInitUnicodeString
0x140053c18  nop     dword ptr [rax+rax+00h]
0x140053c1d  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x140053c22  lea     rax, [rsp+160h+ResultLength]
0x140053c27  mov     qword ptr [rsp+160h+CreateOptions], rax; ResultLength
0x140053c2c  lea     r9, [rbp+60h+KeyValueInformation]; KeyValueInformation
0x140053c30  mov     r8d, 2; KeyValueInformationClass
0x140053c36  mov     dword ptr [rsp+160h+Class], 10h; Length
0x140053c3e  lea     rdx, [rsp+160h+ValueName]; ValueName
0x140053c43  call    cs:__imp_ZwQueryValueKey
0x140053c4a  nop     dword ptr [rax+rax+00h]
0x140053c4f  mov     ecx, 80000000h
0x140053c54  mov     edi, eax
0x140053c56  add     eax, ecx
0x140053c58  test    ecx, eax
0x140053c5a  jnz     short loc_140053CA4
0x140053c5c  cmp     edi, 80000005h
0x140053c62  jz      short loc_140053CA4
0x140053c64  cmp     edi, 0C0000034h
0x140053c6a  jz      loc_140053E64
0x140053c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140053c77  cmp     rcx, rsi
0x140053c7a  jz      loc_140053E0B
0x140053c80  test    dword ptr [rcx+2Ch], 8000h
0x140053c87  jz      loc_140053E0B
0x140053c8d  cmp     byte ptr [rcx+29h], 2
0x140053c91  jb      loc_140053E0B
0x140053c97  mov     edx, 15h
0x140053c9c  mov     r9d, edi
0x140053c9f  jmp     loc_140053BF0
0x140053ca4  cmp     dword ptr [rbp+60h+KeyValueInformation+4], 1
0x140053ca8  jz      short loc_140053CB4
0x140053caa  mov     edi, 0C000000Dh
0x140053caf  jmp     loc_140053E0B
0x140053cb4  mov     edx, [rsp+160h+ResultLength]
0x140053cb8  mov     ecx, 100h
0x140053cbd  add     rdx, 2
0x140053cc1  mov     r8d, 30455646h
0x140053cc7  call    cs:__imp_ExAllocatePool2
0x140053cce  nop     dword ptr [rax+rax+00h]
0x140053cd3  mov     [rsp+160h+var_118], rax
0x140053cd8  mov     r12, rax
0x140053cdb  test    rax, rax
0x140053cde  jnz     short loc_140053CEA
0x140053ce0  mov     edi, 0C000009Ah
0x140053ce5  jmp     loc_140053E0B
0x140053cea  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x140053cef  lea     rax, [rsp+160h+ResultLength]
0x140053cf4  mov     qword ptr [rsp+160h+CreateOptions], rax; ResultLength
0x140053cf9  lea     rdx, [rsp+160h+ValueName]; ValueName
0x140053cfe  mov     eax, [rsp+160h+ResultLength]
0x140053d02  mov     r9, r12; KeyValueInformation
0x140053d05  mov     r8d, 2; KeyValueInformationClass
0x140053d0b  mov     dword ptr [rsp+160h+Class], eax; Length
0x140053d0f  call    cs:__imp_ZwQueryValueKey
0x140053d16  nop     dword ptr [rax+rax+00h]
0x140053d1b  mov     edi, eax
0x140053d1d  cmp     eax, 0C0000034h
0x140053d22  jz      loc_140053E64
0x140053d28  test    eax, eax
0x140053d2a  jns     short loc_140053D5D
0x140053d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140053d33  cmp     rcx, rsi
0x140053d36  jz      loc_140053E0B
0x140053d3c  test    dword ptr [rcx+2Ch], 8000h
0x140053d43  jz      loc_140053E0B
0x140053d49  cmp     byte ptr [rcx+29h], 2
0x140053d4d  jb      loc_140053E0B
0x140053d53  mov     edx, 16h
0x140053d58  jmp     loc_140053BED
0x140053d5d  mov     eax, [r12+8]
0x140053d62  lea     rdi, aFveboot; "FVEBOOT="
0x140053d69  xor     ecx, ecx
0x140053d6b  mov     rdx, rdi; SubStr
0x140053d6e  mov     [rax+r12+0Ch], cx
0x140053d74  lea     rcx, [r12+0Ch]; Str
0x140053d79  call    cs:__imp_wcsstr
0x140053d80  nop     dword ptr [rax+rax+00h]
0x140053d85  test    rax, rax
0x140053d88  jz      short loc_140053DCB
0x140053d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140053d91  cmp     rcx, rsi
0x140053d94  jz      loc_140053CAA
0x140053d9a  test    dword ptr [rcx+2Ch], 8000h
0x140053da1  jz      loc_140053CAA
0x140053da7  cmp     byte ptr [rcx+29h], 2
0x140053dab  jb      loc_140053CAA
0x140053db1  mov     rcx, [rcx+18h]
0x140053db5  lea     r8, WPP_d2beded7854932e8f171fa85139856d9_Traceguids
0x140053dbc  mov     edx, 17h
0x140053dc1  call    WPP_SF_
0x140053dc6  jmp     loc_140053CAA
0x140053dcb  mov     eax, [r12+8]
0x140053dd0  lea     esi, [rax+52h]
0x140053dd3  cmp     esi, eax
0x140053dd5  jb      loc_140053E5D
0x140053ddb  mov     r8d, 30455646h
0x140053de1  mov     edx, esi
0x140053de3  mov     ecx, 100h
0x140053de8  mov     r12d, esi
0x140053deb  call    cs:__imp_ExAllocatePool2
0x140053df2  nop     dword ptr [rax+rax+00h]
0x140053df7  mov     r13, rax
0x140053dfa  test    rax, rax
0x140053dfd  jnz     short loc_140053E36
0x140053dff  mov     edi, 0C000009Ah
0x140053e04  lea     rsi, WPP_GLOBAL_Control
0x140053e0b  test    r15, r15
0x140053e0e  jz      loc_140053F62
0x140053e14  cmp     qword ptr [r14+2A0h], 0
0x140053e1c  mov     r12, [rsp+160h+var_118]
0x140053e21  jnz     loc_140053F67
0x140053e27  mov     [r14+2A0h], r15
0x140053e2e  xor     r15d, r15d
0x140053e31  jmp     loc_140053F67
0x140053e36  mov     r9, [rsp+160h+var_118]
0x140053e3b  lea     r8, aSSI64u; "%s  %s%I64u"
0x140053e42  add     r9, 0Ch
0x140053e46  mov     qword ptr [rsp+160h+CreateOptions], rbx
0x140053e4b  mov     rdx, r12; cbDest
0x140053e4e  mov     [rsp+160h+Class], rdi
0x140053e53  mov     rcx, rax; pszDest
0x140053e56  call    RtlStringCbPrintfW
0x140053e5b  jmp     short loc_140053EAB
0x140053e5d  mov     edi, 0C0000095h
0x140053e62  jmp     short loc_140053E04
0x140053e64  mov     esi, 52h ; 'R'
0x140053e69  mov     r8d, 30455646h
0x140053e6f  mov     edx, esi
0x140053e71  mov     ecx, 100h
0x140053e76  call    cs:__imp_ExAllocatePool2
0x140053e7d  nop     dword ptr [rax+rax+00h]
0x140053e82  mov     r13, rax
0x140053e85  test    rax, rax
0x140053e88  jz      loc_140053DFF
0x140053e8e  lea     r9, aFveboot; "FVEBOOT="
0x140053e95  mov     [rsp+160h+Class], rbx
0x140053e9a  lea     r8, aSI64u; " %s%I64u"
0x140053ea1  mov     edx, esi; cbDest
0x140053ea3  mov     rcx, rax; pszDest
0x140053ea6  call    RtlStringCbPrintfW
0x140053eab  mov     edi, eax
0x140053ead  test    eax, eax
0x140053eaf  js      loc_140053E04
0x140053eb5  mov     edx, esi; cbMax
0x140053eb7  lea     r8, [rsp+160h+pcbLength]; pcbLength
0x140053ebc  mov     rcx, r13; psz
0x140053ebf  call    RtlStringCbLengthW
0x140053ec4  mov     edi, eax
0x140053ec6  test    eax, eax
0x140053ec8  js      loc_140053E04
0x140053ece  mov     rcx, [rsp+160h+pcbLength]; ullOperand
0x140053ed3  lea     rdx, [rsp+160h+pulResult]; pulResult
0x140053ed8  call    RtlULongLongToULong
0x140053edd  mov     edi, eax
0x140053edf  test    eax, eax
0x140053ee1  js      loc_140053E04
0x140053ee7  mov     eax, [rsp+160h+pulResult]
0x140053eeb  lea     rdx, [rsp+160h+ValueName]; ValueName
0x140053ef0  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x140053ef5  add     eax, 2
0x140053ef8  mov     [rsp+160h+CreateOptions], eax; DataSize
0x140053efc  mov     r9d, 1; Type
0x140053f02  xor     r8d, r8d; TitleIndex
0x140053f05  mov     [rsp+160h+Class], r13; Data
0x140053f0a  call    cs:__imp_ZwSetValueKey
0x140053f11  nop     dword ptr [rax+rax+00h]
0x140053f16  mov     edi, eax
0x140053f18  test    eax, eax
  ... truncated ...
```
