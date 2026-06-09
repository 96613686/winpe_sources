# CheckAndCopyEssentialCameraMetadata

- ea: `0x180062458`
- end: `0x180062998`
- name: `CheckAndCopyEssentialCameraMetadata`
- size: `1344`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180062378`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180019bd0`
- `0x18001a000`
- `0x180062458`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800628df`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800628df`
- `ntoskrnl!RtlInitUnicodeString` at `0x180062763`
- `ntoskrnl!RtlInitUnicodeString` at `0x180062763`
- `ntoskrnl!ZwClose` at `0x1800628b8`
- `ntoskrnl!ZwClose` at `0x1800628ce`
- `ntoskrnl!ZwClose` at `0x1800628b8`
- `ntoskrnl!ZwClose` at `0x1800628ce`
- `ntoskrnl!ZwSetValueKey` at `0x180062710`
- `ntoskrnl!ZwSetValueKey` at `0x180062791`
- `ntoskrnl!ZwSetValueKey` at `0x180062710`
- `ntoskrnl!ZwSetValueKey` at `0x180062791`
- `ntoskrnl!ZwQueryKey` at `0x18006257b`
- `ntoskrnl!ZwQueryKey` at `0x1800625cc`
- `ntoskrnl!ZwQueryKey` at `0x18006257b`
- `ntoskrnl!ZwQueryKey` at `0x1800625cc`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18006254a`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18006259b`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18006254a`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18006259b`
- `ntoskrnl!IoGetDeviceInterfaceAlias` at `0x180062523`
- `ntoskrnl!IoGetDeviceInterfaceAlias` at `0x180062523`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006262e`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1800626be`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006262e`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1800626be`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062723`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062723`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180062661`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180062661`

## pseudocode

```c
void __fastcall CheckAndCopyEssentialCameraMetadata(__int64 a1)
{
  NTSTATUS v2; // esi
  ULONG v3; // edi
  NTSTATUS v4; // eax
  ULONG v5; // r14d
  char *PoolWithTag; // rax
  char *v7; // rbx
  unsigned __int16 v8; // ax
  ULONG v9; // r9d
  char *v10; // rcx
  char v11; // al
  PDEVICE_OBJECT v12; // rcx
  int v13; // r9d
  PDEVICE_OBJECT v14; // rcx
  int v15; // r9d
  ULONG Data; // [rsp+30h] [rbp-D0h] BYREF
  ULONG Length; // [rsp+34h] [rbp-CCh] BYREF
  void *DeviceInterfaceRegKey; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG v21; // [rsp+4Ch] [rbp-B4h] BYREF
  UNICODE_STRING ValueName; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING AliasSymbolicLinkName; // [rsp+60h] [rbp-A0h] BYREF
  GUID AliasInterfaceClassGuid; // [rsp+70h] [rbp-90h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h]
  _OWORD KeyInformation[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v28; // [rsp+B8h] [rbp-48h]
  _OWORD v29[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v30; // [rsp+E8h] [rbp-18h]

  memset(KeyInformation, 0, sizeof(KeyInformation));
  LOBYTE(v2) = 0;
  ResultLength = 0;
  v28 = 0;
  DeviceInterfaceRegKey = 0;
  v21 = 0;
  KeyHandle = 0;
  AliasInterfaceClassGuid = GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196;
  AliasSymbolicLinkName = 0;
  memset(v29, 0, sizeof(v29));
  v30 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      25,
      (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids);
  if ( a1 )
  {
    if ( IoGetDeviceInterfaceAlias((PUNICODE_STRING)(a1 + 24), &AliasInterfaceClassGuid, &AliasSymbolicLinkName) >= 0 )
    {
      if ( IoOpenDeviceInterfaceRegistryKey(&AliasSymbolicLinkName, 0x1F0000u, &DeviceInterfaceRegKey) < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_42;
        v12 = WPP_GLOBAL_Control;
        if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_42;
        v13 = 31;
      }
      else if ( ZwQueryKey(DeviceInterfaceRegKey, KeyFullInformation, KeyInformation, 0x30u, &ResultLength) < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_42;
        v12 = WPP_GLOBAL_Control;
        if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_42;
        v13 = 30;
      }
      else if ( IoOpenDeviceInterfaceRegistryKey((PUNICODE_STRING)(a1 + 24), 0x1F0000u, &KeyHandle) < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_42;
        v12 = WPP_GLOBAL_Control;
        if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_42;
        v13 = 29;
      }
      else
      {
        if ( ZwQueryKey(KeyHandle, KeyFullInformation, v29, 0x30u, &v21) >= 0 )
        {
          if ( (_DWORD)v28 != (_DWORD)v30 )
          {
            Data = 0;
            v26 = 0;
            v3 = 0;
            KeyValueInformation = 0;
            if ( !(_DWORD)v28 )
              goto LABEL_23;
            while ( 1 )
            {
              Length = 0;
              v4 = ZwEnumerateValueKey(
                     DeviceInterfaceRegKey,
                     v3,
                     KeyValueFullInformation,
                     &KeyValueInformation,
                     0x18u,
                     &Length);
              v2 = v4;
              if ( v4 == -1073741789 || v4 == -2147483643 )
              {
                v5 = Length;
                PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, Length, 0x6964534Bu);
                v7 = PoolWithTag;
                if ( ExPoolZeroingNativelySupported )
                {
                  if ( PoolWithTag )
                    goto LABEL_18;
                }
                else if ( PoolWithTag )
                {
                  memset(PoolWithTag, 0, v5);
LABEL_18:
                  Data = 0;
                  if ( ZwEnumerateValueKey(DeviceInterfaceRegKey, v3, KeyValueFullInformation, v7, Length, &Data) >= 0 )
                  {
                    v8 = *((_WORD *)v7 + 8);
                    v9 = *((_DWORD *)v7 + 1);
                    v10 = &v7[*((unsigned int *)v7 + 2)];
                    *(_DWORD *)(&ValueName.MaximumLength + 1) = 0;
                    ValueName.Length = v8;
                    ValueName.MaximumLength = v8;
                    ValueName.Buffer = (wchar_t *)(v7 + 20);
                    v2 = ZwSetValueKey(KeyHandle, &ValueName, 0, v9, v10, *((_DWORD *)v7 + 3));
                  }
                  ExFreePoolWithTag(v7, 0);
                }
              }
              if ( ++v3 >= (unsigned int)v28 )
              {
                if ( v2 >= 0 )
                  goto LABEL_23;
                goto LABEL_42;
              }
            }
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              5,
              1,
              26,
              (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids);
          }
LABEL_23:
          Data = 1;
          ValueName = 0;
          RtlInitUnicodeString(&ValueName, L"MSCameraFlags");
          v11 = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
          LOBYTE(v2) = v11;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              5,
              1,
              27,
              (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids,
              v11);
          }
LABEL_42:
          if ( DeviceInterfaceRegKey )
            ZwClose(DeviceInterfaceRegKey);
          if ( KeyHandle )
            ZwClose(KeyHandle);
          RtlFreeUnicodeString(&AliasSymbolicLinkName);
          goto LABEL_54;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_42;
        v12 = WPP_GLOBAL_Control;
        if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          goto LABEL_42;
        v13 = 28;
      }
      WPP_RECORDER_SF_(v12->DeviceExtension, 5, 1, v13, (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids);
      goto LABEL_42;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    v14 = WPP_GLOBAL_Control;
    if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_54;
    v15 = 32;
    goto LABEL_53;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return;
  v14 = WPP_GLOBAL_Control;
  if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v15 = 33;
LABEL_53:
    WPP_RECORDER_SF_(v14->DeviceExtension, 5, 1, v15, (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids);
  }
LABEL_54:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        34,
        (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids,
        v2);
  }
}

```

## disassembly

```asm
0x180062458  push    rbp
0x18006245a  push    rbx
0x18006245b  push    rsi
0x18006245c  push    rdi
0x18006245d  push    r12
0x18006245f  push    r13
0x180062461  push    r14
0x180062463  push    r15
0x180062465  lea     rbp, [rsp-8]
0x18006246a  sub     rsp, 108h
0x180062471  mov     rax, cs:__security_cookie
0x180062478  xor     rax, rsp
0x18006247b  mov     [rbp+40h+var_48], rax
0x18006247f  xorps   xmm0, xmm0
0x180062482  xor     r15d, r15d
0x180062485  movups  [rbp+40h+KeyInformation], xmm0
0x180062489  mov     rbx, rcx
0x18006248c  mov     esi, r15d
0x18006248f  movups  [rbp+40h+var_98], xmm0
0x180062493  mov     [rsp+140h+var_F8], r15d
0x180062498  movups  [rbp+40h+var_88], xmm0
0x18006249c  mov     [rsp+140h+DeviceInterfaceRegKey], r15
0x1800624a1  movups  xmm0, xmmword ptr cs:_GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196.Data1
0x1800624a8  mov     [rsp+140h+var_F4], r15d
0x1800624ad  mov     [rsp+140h+KeyHandle], r15
0x1800624b2  movdqu  xmmword ptr [rsp+140h+AliasInterfaceClassGuid.Data1], xmm0
0x1800624b8  xorps   xmm0, xmm0
0x1800624bb  movups  xmmword ptr [rsp+140h+AliasSymbolicLinkName.Length], xmm0
0x1800624c0  movups  [rbp+40h+var_78], xmm0
0x1800624c4  movups  [rbp+40h+var_68], xmm0
0x1800624c8  movups  [rbp+40h+var_58], xmm0
0x1800624cc  lea     r13, WPP_RECORDER_INITIALIZED
0x1800624d3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800624da  lea     rdi, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x1800624e1  lea     r12d, [r15+1]
0x1800624e5  jz      short loc_18006250C
0x1800624e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800624ee  cmp     [rcx+48h], r15w
0x1800624f3  jz      short loc_18006250C
0x1800624f5  mov     rcx, [rcx+40h]
0x1800624f9  lea     r9d, [r15+19h]
0x1800624fd  mov     r8d, r12d
0x180062500  mov     [rsp+140h+ResultLength], rdi
0x180062505  mov     dl, 5
0x180062507  call    WPP_RECORDER_SF_
0x18006250c  test    rbx, rbx
0x18006250f  jz      loc_180062913
0x180062515  lea     r8, [rsp+140h+AliasSymbolicLinkName]; AliasSymbolicLinkName
0x18006251a  lea     rdx, [rsp+140h+AliasInterfaceClassGuid]; AliasInterfaceClassGuid
0x18006251f  lea     rcx, [rbx+18h]; SymbolicLinkName
0x180062523  call    cs:__imp_IoGetDeviceInterfaceAlias
0x18006252a  nop     dword ptr [rax+rax+00h]
0x18006252f  test    eax, eax
0x180062531  js      loc_1800628F4
0x180062537  mov     r14d, 1F0000h
0x18006253d  lea     r8, [rsp+140h+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x180062542  mov     edx, r14d; DesiredAccess
0x180062545  lea     rcx, [rsp+140h+AliasSymbolicLinkName]; SymbolicLinkName
0x18006254a  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x180062551  nop     dword ptr [rax+rax+00h]
0x180062556  test    eax, eax
0x180062558  js      loc_18006287E
0x18006255e  mov     rcx, [rsp+140h+DeviceInterfaceRegKey]; KeyHandle
0x180062563  lea     rax, [rsp+140h+var_F8]
0x180062568  mov     r9d, 30h ; '0'; Length
0x18006256e  mov     [rsp+140h+ResultLength], rax; ResultLength
0x180062573  lea     r8, [rbp+40h+KeyInformation]; KeyInformation
0x180062577  lea     edx, [r9-2Eh]; KeyInformationClass
0x18006257b  call    cs:__imp_ZwQueryKey
0x180062582  nop     dword ptr [rax+rax+00h]
0x180062587  test    eax, eax
0x180062589  js      loc_18006285F
0x18006258f  lea     r8, [rsp+140h+KeyHandle]; DeviceInterfaceRegKey
0x180062594  mov     edx, r14d; DesiredAccess
0x180062597  lea     rcx, [rbx+18h]; SymbolicLinkName
0x18006259b  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x1800625a2  nop     dword ptr [rax+rax+00h]
0x1800625a7  test    eax, eax
0x1800625a9  js      loc_180062840
0x1800625af  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x1800625b4  lea     rax, [rsp+140h+var_F4]
0x1800625b9  mov     r9d, 30h ; '0'; Length
0x1800625bf  mov     [rsp+140h+ResultLength], rax; ResultLength
0x1800625c4  lea     r8, [rbp+40h+var_78]; KeyInformation
0x1800625c8  lea     edx, [r9-2Eh]; KeyInformationClass
0x1800625cc  call    cs:__imp_ZwQueryKey
0x1800625d3  nop     dword ptr [rax+rax+00h]
0x1800625d8  test    eax, eax
0x1800625da  js      loc_18006281D
0x1800625e0  mov     eax, dword ptr [rbp+40h+var_88]
0x1800625e3  cmp     eax, dword ptr [rbp+40h+var_58]
0x1800625e6  jz      loc_1800627E0
0x1800625ec  xor     ecx, ecx
0x1800625ee  mov     [rsp+140h+Data], r15d
0x1800625f3  mov     [rbp+40h+var_B0], rcx
0x1800625f7  xorps   xmm0, xmm0
0x1800625fa  mov     edi, r15d
0x1800625fd  movups  [rbp+40h+KeyValueInformation], xmm0
0x180062601  test    eax, eax
0x180062603  jz      loc_180062743
0x180062609  mov     rcx, [rsp+140h+DeviceInterfaceRegKey]; KeyHandle
0x18006260e  lea     rax, [rsp+140h+Length]
0x180062613  mov     [rsp+140h+var_118], rax; ResultLength
0x180062618  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x18006261c  mov     r8d, r12d; KeyValueInformationClass
0x18006261f  mov     dword ptr [rsp+140h+ResultLength], 18h; Length
0x180062627  mov     edx, edi; Index
0x180062629  mov     [rsp+140h+Length], r15d
0x18006262e  call    cs:__imp_ZwEnumerateValueKey
0x180062635  nop     dword ptr [rax+rax+00h]
0x18006263a  mov     esi, eax
0x18006263c  cmp     eax, 0C0000023h
0x180062641  jz      short loc_18006264E
0x180062643  cmp     eax, 80000005h
0x180062648  jnz     loc_18006272F
0x18006264e  mov     r14d, [rsp+140h+Length]
0x180062653  mov     r8d, 6964534Bh; Tag
0x180062659  mov     edx, r14d; NumberOfBytes
0x18006265c  mov     ecx, 600h; PoolType
0x180062661  call    cs:__imp_ExAllocatePoolWithTag
0x180062668  nop     dword ptr [rax+rax+00h]
0x18006266d  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x180062674  mov     rbx, rax
0x180062677  jnz     short loc_180062691
0x180062679  test    rax, rax
0x18006267c  jz      loc_18006272F
0x180062682  mov     r8d, r14d; Size
0x180062685  xor     edx, edx; Val
0x180062687  mov     rcx, rax; void *
0x18006268a  call    memset
0x18006268f  jmp     short loc_18006269A
0x180062691  test    rbx, rbx
0x180062694  jz      loc_18006272F
0x18006269a  mov     rcx, [rsp+140h+DeviceInterfaceRegKey]; KeyHandle
0x18006269f  lea     rax, [rsp+140h+Data]
0x1800626a4  mov     [rsp+140h+var_118], rax; ResultLength
0x1800626a9  mov     r9, rbx; KeyValueInformation
0x1800626ac  mov     eax, [rsp+140h+Length]
0x1800626b0  mov     r8d, r12d; KeyValueInformationClass
0x1800626b3  mov     edx, edi; Index
0x1800626b5  mov     dword ptr [rsp+140h+ResultLength], eax; Length
0x1800626b9  mov     [rsp+140h+Data], r15d
0x1800626be  call    cs:__imp_ZwEnumerateValueKey
0x1800626c5  nop     dword ptr [rax+rax+00h]
0x1800626ca  test    eax, eax
0x1800626cc  js      short loc_18006271E
0x1800626ce  movzx   eax, word ptr [rbx+10h]
0x1800626d2  lea     rdx, [rsp+140h+ValueName]; ValueName
0x1800626d7  mov     ecx, [rbx+8]
0x1800626da  xorps   xmm0, xmm0
0x1800626dd  mov     r9d, [rbx+4]; Type
0x1800626e1  add     rcx, rbx
0x1800626e4  movups  xmmword ptr [rsp+140h+ValueName.Length], xmm0
0x1800626e9  mov     [rsp+140h+ValueName.Length], ax
0x1800626ee  xor     r8d, r8d; TitleIndex
0x1800626f1  mov     [rsp+140h+ValueName.MaximumLength], ax
0x1800626f6  lea     rax, [rbx+14h]
0x1800626fa  mov     [rsp+140h+ValueName.Buffer], rax
0x1800626ff  mov     eax, [rbx+0Ch]
0x180062702  mov     dword ptr [rsp+140h+var_118], eax; DataSize
0x180062706  mov     [rsp+140h+ResultLength], rcx; Data
0x18006270b  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x180062710  call    cs:__imp_ZwSetValueKey
0x180062717  nop     dword ptr [rax+rax+00h]
0x18006271c  mov     esi, eax
0x18006271e  xor     edx, edx; Tag
0x180062720  mov     rcx, rbx; P
0x180062723  call    cs:__imp_ExFreePoolWithTag
0x18006272a  nop     dword ptr [rax+rax+00h]
0x18006272f  add     edi, r12d
0x180062732  cmp     edi, dword ptr [rbp+40h+var_88]
0x180062735  jb      loc_180062609
0x18006273b  test    esi, esi
0x18006273d  js      loc_1800628AE
0x180062743  lea     rdi, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x18006274a  xorps   xmm0, xmm0
0x18006274d  mov     [rsp+140h+Data], r12d
0x180062752  lea     rdx, aMscameraflags; "MSCameraFlags"
0x180062759  lea     rcx, [rsp+140h+ValueName]; DestinationString
0x18006275e  movups  xmmword ptr [rsp+140h+ValueName.Length], xmm0
0x180062763  call    cs:__imp_RtlInitUnicodeString
0x18006276a  nop     dword ptr [rax+rax+00h]
0x18006276f  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x180062774  lea     rax, [rsp+140h+Data]
0x180062779  mov     r9d, 4; Type
0x18006277f  lea     rdx, [rsp+140h+ValueName]; ValueName
0x180062784  mov     dword ptr [rsp+140h+var_118], r9d; DataSize
0x180062789  xor     r8d, r8d; TitleIndex
0x18006278c  mov     [rsp+140h+ResultLength], rax; Data
0x180062791  call    cs:__imp_ZwSetValueKey
0x180062798  nop     dword ptr [rax+rax+00h]
0x18006279d  mov     esi, eax
0x18006279f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800627a6  jz      loc_1800628AE
0x1800627ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800627b3  cmp     [rcx+48h], r15w
0x1800627b8  jz      loc_1800628AE
0x1800627be  mov     rcx, [rcx+40h]
0x1800627c2  mov     r9d, 1Bh
0x1800627c8  mov     dword ptr [rsp+140h+var_118], eax
0x1800627cc  mov     r8d, r12d
0x1800627cf  mov     dl, 5
0x1800627d1  mov     [rsp+140h+ResultLength], rdi
0x1800627d6  call    WPP_RECORDER_SF_D
0x1800627db  jmp     loc_1800628AE
0x1800627e0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800627e7  jz      loc_18006274A
0x1800627ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800627f4  cmp     [rcx+48h], r15w
0x1800627f9  jz      loc_18006274A
0x1800627ff  mov     rcx, [rcx+40h]
0x180062803  mov     r9d, 1Ah
0x180062809  mov     r8d, r12d
0x18006280c  mov     [rsp+140h+ResultLength], rdi
0x180062811  mov     dl, 5
0x180062813  call    WPP_RECORDER_SF_
0x180062818  jmp     loc_18006274A
0x18006281d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180062824  jz      loc_1800628AE
0x18006282a  mov     rcx, cs:WPP_GLOBAL_Control
0x180062831  cmp     [rcx+48h], r15w
0x180062836  jz      short loc_1800628AE
0x180062838  mov     r9d, 1Ch
0x18006283e  jmp     short loc_18006289B
0x180062840  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180062847  jz      short loc_1800628AE
0x180062849  mov     rcx, cs:WPP_GLOBAL_Control
0x180062850  cmp     [rcx+48h], r15w
0x180062855  jz      short loc_1800628AE
0x180062857  mov     r9d, 1Dh
0x18006285d  jmp     short loc_18006289B
0x18006285f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180062866  jz      short loc_1800628AE
0x180062868  mov     rcx, cs:WPP_GLOBAL_Control
0x18006286f  cmp     [rcx+48h], r15w
0x180062874  jz      short loc_1800628AE
0x180062876  mov     r9d, 1Eh
0x18006287c  jmp     short loc_18006289B
0x18006287e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180062885  jz      short loc_1800628AE
0x180062887  mov     rcx, cs:WPP_GLOBAL_Control
0x18006288e  cmp     [rcx+48h], r15w
0x180062893  jz      short loc_1800628AE
0x180062895  mov     r9d, 1Fh
0x18006289b  mov     rcx, [rcx+40h]
0x18006289f  mov     r8d, r12d
0x1800628a2  mov     dl, 5
0x1800628a4  mov     [rsp+140h+ResultLength], rdi
0x1800628a9  call    WPP_RECORDER_SF_
0x1800628ae  mov     rcx, [rsp+140h+DeviceInterfaceRegKey]; Handle
0x1800628b3  test    rcx, rcx
0x1800628b6  jz      short loc_1800628C4
0x1800628b8  call    cs:__imp_ZwClose
0x1800628bf  nop     dword ptr [rax+rax+00h]
0x1800628c4  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x1800628c9  test    rcx, rcx
0x1800628cc  jz      short loc_1800628DA
0x1800628ce  call    cs:__imp_ZwClose
0x1800628d5  nop     dword ptr [rax+rax+00h]
0x1800628da  lea     rcx, [rsp+140h+AliasSymbolicLinkName]; UnicodeString
0x1800628df  call    cs:__imp_RtlFreeUnicodeString
0x1800628e6  nop     dword ptr [rax+rax+00h]
0x1800628eb  lea     rdi, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x1800628f2  jmp     short loc_180062943
0x1800628f4  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800628fb  jz      short loc_180062977
0x1800628fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180062904  cmp     [rcx+48h], r15w
0x180062909  jz      short loc_180062943
0x18006290b  mov     r9d, 20h ; ' '
0x180062911  jmp     short loc_180062930
0x180062913  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18006291a  jz      short loc_180062977
0x18006291c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062923  cmp     [rcx+48h], r15w
0x180062928  jz      short loc_180062943
0x18006292a  mov     r9d, 21h ; '!'
0x180062930  mov     rcx, [rcx+40h]
0x180062934  mov     r8d, r12d
0x180062937  mov     dl, 5
0x180062939  mov     [rsp+140h+ResultLength], rdi
0x18006293e  call    WPP_RECORDER_SF_
0x180062943  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18006294a  jz      short loc_180062977
0x18006294c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062953  cmp     [rcx+48h], r15w
0x180062958  jz      short loc_180062977
0x18006295a  mov     rcx, [rcx+40h]
0x18006295e  mov     r9d, 22h ; '"'
0x180062964  mov     dword ptr [rsp+140h+var_118], esi
0x180062968  mov     r8d, r12d
0x18006296b  mov     dl, 5
0x18006296d  mov     [rsp+140h+ResultLength], rdi
0x180062972  call    WPP_RECORDER_SF_D
0x180062977  mov     rcx, [rbp+40h+var_48]
0x18006297b  xor     rcx, rsp; StackCookie
0x18006297e  call    __security_check_cookie
0x180062983  add     rsp, 108h
0x18006298a  pop     r15
0x18006298c  pop     r14
  ... truncated ...
```
