# CheckAndCopyEssentialCameraMetadata

- ea: `0x1800622b8`
- end: `0x1800627f8`
- name: `CheckAndCopyEssentialCameraMetadata`
- size: `1344`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1800621d8`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180019b80`
- `0x180019fc0`
- `0x1800622b8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006273f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006273f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800625c3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800625c3`
- `ntoskrnl!ZwClose` at `0x180062718`
- `ntoskrnl!ZwClose` at `0x18006272e`
- `ntoskrnl!ZwClose` at `0x180062718`
- `ntoskrnl!ZwClose` at `0x18006272e`
- `ntoskrnl!ZwSetValueKey` at `0x180062570`
- `ntoskrnl!ZwSetValueKey` at `0x1800625f1`
- `ntoskrnl!ZwSetValueKey` at `0x180062570`
- `ntoskrnl!ZwSetValueKey` at `0x1800625f1`
- `ntoskrnl!ZwQueryKey` at `0x1800623db`
- `ntoskrnl!ZwQueryKey` at `0x18006242c`
- `ntoskrnl!ZwQueryKey` at `0x1800623db`
- `ntoskrnl!ZwQueryKey` at `0x18006242c`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800623aa`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800623fb`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800623aa`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x1800623fb`
- `ntoskrnl!IoGetDeviceInterfaceAlias` at `0x180062383`
- `ntoskrnl!IoGetDeviceInterfaceAlias` at `0x180062383`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006248e`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006251e`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006248e`
- `ntoskrnl!ZwEnumerateValueKey` at `0x18006251e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062583`
- `ntoskrnl!ExFreePoolWithTag` at `0x180062583`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800624c1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800624c1`

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
  NTSTATUS v11; // eax
  PDEVICE_OBJECT v12; // rcx
  int v13; // r9d
  PDEVICE_OBJECT v14; // rcx
  int v15; // r9d
  PULONG v16; // [rsp+28h] [rbp-D8h]
  ULONG Data; // [rsp+30h] [rbp-D0h] BYREF
  ULONG Length; // [rsp+34h] [rbp-CCh] BYREF
  void *DeviceInterfaceRegKey; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG v22; // [rsp+4Ch] [rbp-B4h] BYREF
  UNICODE_STRING ValueName; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING AliasSymbolicLinkName; // [rsp+60h] [rbp-A0h] BYREF
  GUID AliasInterfaceClassGuid; // [rsp+70h] [rbp-90h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+90h] [rbp-70h]
  _OWORD KeyInformation[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v29; // [rsp+B8h] [rbp-48h]
  _OWORD v30[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v31; // [rsp+E8h] [rbp-18h]

  memset(KeyInformation, 0, sizeof(KeyInformation));
  v2 = 0;
  ResultLength = 0;
  v29 = 0;
  DeviceInterfaceRegKey = 0;
  v22 = 0;
  KeyHandle = 0;
  AliasInterfaceClassGuid = GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196;
  AliasSymbolicLinkName = 0;
  memset(v30, 0, sizeof(v30));
  v31 = 0;
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
        if ( ZwQueryKey(KeyHandle, KeyFullInformation, v30, 0x30u, &v22) >= 0 )
        {
          if ( (_DWORD)v29 != (_DWORD)v31 )
          {
            Data = 0;
            v27 = 0;
            v3 = 0;
            KeyValueInformation = 0;
            if ( !(_DWORD)v29 )
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
              if ( ++v3 >= (unsigned int)v29 )
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
          v2 = v11;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LODWORD(v16) = v11;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              5,
              1,
              27,
              (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids,
              v16);
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
    {
      LODWORD(v16) = v2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        34,
        (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids,
        v16);
    }
  }
}

```

## disassembly

```asm
0x1800622b8  push    rbp
0x1800622ba  push    rbx
0x1800622bb  push    rsi
0x1800622bc  push    rdi
0x1800622bd  push    r12
0x1800622bf  push    r13
0x1800622c1  push    r14
0x1800622c3  push    r15
0x1800622c5  lea     rbp, [rsp-8]
0x1800622ca  sub     rsp, 108h
0x1800622d1  mov     rax, cs:__security_cookie
0x1800622d8  xor     rax, rsp
0x1800622db  mov     [rbp+40h+var_48], rax
0x1800622df  xorps   xmm0, xmm0
0x1800622e2  xor     r15d, r15d
0x1800622e5  movups  [rbp+40h+KeyInformation], xmm0
0x1800622e9  mov     rbx, rcx
0x1800622ec  mov     esi, r15d
0x1800622ef  movups  [rbp+40h+var_98], xmm0
0x1800622f3  mov     [rsp+140h+var_F8], r15d
0x1800622f8  movups  [rbp+40h+var_88], xmm0
0x1800622fc  mov     [rsp+140h+DeviceInterfaceRegKey], r15
0x180062301  movups  xmm0, xmmword ptr cs:_GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196.Data1
0x180062308  mov     [rsp+140h+var_F4], r15d
0x18006230d  mov     [rsp+140h+KeyHandle], r15
0x180062312  movdqu  xmmword ptr [rsp+140h+AliasInterfaceClassGuid.Data1], xmm0
0x180062318  xorps   xmm0, xmm0
0x18006231b  movups  xmmword ptr [rsp+140h+AliasSymbolicLinkName.Length], xmm0
0x180062320  movups  [rbp+40h+var_78], xmm0
0x180062324  movups  [rbp+40h+var_68], xmm0
0x180062328  movups  [rbp+40h+var_58], xmm0
0x18006232c  lea     r13, WPP_RECORDER_INITIALIZED
0x180062333  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18006233a  lea     rdi, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x180062341  lea     r12d, [r15+1]
0x180062345  jz      short loc_18006236C
0x180062347  mov     rcx, cs:WPP_GLOBAL_Control
0x18006234e  cmp     [rcx+48h], r15w
0x180062353  jz      short loc_18006236C
0x180062355  mov     rcx, [rcx+40h]
0x180062359  lea     r9d, [r15+19h]
0x18006235d  mov     r8d, r12d
0x180062360  mov     [rsp+140h+ResultLength], rdi
0x180062365  mov     dl, 5
0x180062367  call    WPP_RECORDER_SF_
0x18006236c  test    rbx, rbx
0x18006236f  jz      loc_180062773
0x180062375  lea     r8, [rsp+140h+AliasSymbolicLinkName]; AliasSymbolicLinkName
0x18006237a  lea     rdx, [rsp+140h+AliasInterfaceClassGuid]; AliasInterfaceClassGuid
0x18006237f  lea     rcx, [rbx+18h]; SymbolicLinkName
0x180062383  call    cs:__imp_IoGetDeviceInterfaceAlias
0x18006238a  nop     dword ptr [rax+rax+00h]
0x18006238f  test    eax, eax
0x180062391  js      loc_180062754
0x180062397  mov     r14d, 1F0000h
0x18006239d  lea     r8, [rsp+140h+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x1800623a2  mov     edx, r14d; DesiredAccess
0x1800623a5  lea     rcx, [rsp+140h+AliasSymbolicLinkName]; SymbolicLinkName
0x1800623aa  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x1800623b1  nop     dword ptr [rax+rax+00h]
0x1800623b6  test    eax, eax
0x1800623b8  js      loc_1800626DE
0x1800623be  mov     rcx, [rsp+140h+DeviceInterfaceRegKey]; KeyHandle
0x1800623c3  lea     rax, [rsp+140h+var_F8]
0x1800623c8  mov     r9d, 30h ; '0'; Length
0x1800623ce  mov     [rsp+140h+ResultLength], rax; ResultLength
0x1800623d3  lea     r8, [rbp+40h+KeyInformation]; KeyInformation
0x1800623d7  lea     edx, [r9-2Eh]; KeyInformationClass
0x1800623db  call    cs:__imp_ZwQueryKey
0x1800623e2  nop     dword ptr [rax+rax+00h]
0x1800623e7  test    eax, eax
0x1800623e9  js      loc_1800626BF
0x1800623ef  lea     r8, [rsp+140h+KeyHandle]; DeviceInterfaceRegKey
0x1800623f4  mov     edx, r14d; DesiredAccess
0x1800623f7  lea     rcx, [rbx+18h]; SymbolicLinkName
0x1800623fb  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x180062402  nop     dword ptr [rax+rax+00h]
0x180062407  test    eax, eax
0x180062409  js      loc_1800626A0
0x18006240f  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x180062414  lea     rax, [rsp+140h+var_F4]
0x180062419  mov     r9d, 30h ; '0'; Length
0x18006241f  mov     [rsp+140h+ResultLength], rax; ResultLength
0x180062424  lea     r8, [rbp+40h+var_78]; KeyInformation
0x180062428  lea     edx, [r9-2Eh]; KeyInformationClass
0x18006242c  call    cs:__imp_ZwQueryKey
0x180062433  nop     dword ptr [rax+rax+00h]
0x180062438  test    eax, eax
0x18006243a  js      loc_18006267D
0x180062440  mov     eax, dword ptr [rbp+40h+var_88]
0x180062443  cmp     eax, dword ptr [rbp+40h+var_58]
0x180062446  jz      loc_180062640
0x18006244c  xor     ecx, ecx
0x18006244e  mov     [rsp+140h+Data], r15d
0x180062453  mov     [rbp+40h+var_B0], rcx
0x180062457  xorps   xmm0, xmm0
0x18006245a  mov     edi, r15d
0x18006245d  movups  [rbp+40h+KeyValueInformation], xmm0
0x180062461  test    eax, eax
0x180062463  jz      loc_1800625A3
0x180062469  mov     rcx, [rsp+140h+DeviceInterfaceRegKey]; KeyHandle
0x18006246e  lea     rax, [rsp+140h+Length]
0x180062473  mov     [rsp+140h+var_118], rax; ResultLength
0x180062478  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x18006247c  mov     r8d, r12d; KeyValueInformationClass
0x18006247f  mov     dword ptr [rsp+140h+ResultLength], 18h; Length
0x180062487  mov     edx, edi; Index
0x180062489  mov     [rsp+140h+Length], r15d
0x18006248e  call    cs:__imp_ZwEnumerateValueKey
0x180062495  nop     dword ptr [rax+rax+00h]
0x18006249a  mov     esi, eax
0x18006249c  cmp     eax, 0C0000023h
0x1800624a1  jz      short loc_1800624AE
0x1800624a3  cmp     eax, 80000005h
0x1800624a8  jnz     loc_18006258F
0x1800624ae  mov     r14d, [rsp+140h+Length]
0x1800624b3  mov     r8d, 6964534Bh; Tag
0x1800624b9  mov     edx, r14d; NumberOfBytes
0x1800624bc  mov     ecx, 600h; PoolType
0x1800624c1  call    cs:__imp_ExAllocatePoolWithTag
0x1800624c8  nop     dword ptr [rax+rax+00h]
0x1800624cd  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x1800624d4  mov     rbx, rax
0x1800624d7  jnz     short loc_1800624F1
0x1800624d9  test    rax, rax
0x1800624dc  jz      loc_18006258F
0x1800624e2  mov     r8d, r14d; Size
0x1800624e5  xor     edx, edx; Val
0x1800624e7  mov     rcx, rax; void *
0x1800624ea  call    memset
0x1800624ef  jmp     short loc_1800624FA
0x1800624f1  test    rbx, rbx
0x1800624f4  jz      loc_18006258F
0x1800624fa  mov     rcx, [rsp+140h+DeviceInterfaceRegKey]; KeyHandle
0x1800624ff  lea     rax, [rsp+140h+Data]
0x180062504  mov     [rsp+140h+var_118], rax; ResultLength
0x180062509  mov     r9, rbx; KeyValueInformation
0x18006250c  mov     eax, [rsp+140h+Length]
0x180062510  mov     r8d, r12d; KeyValueInformationClass
0x180062513  mov     edx, edi; Index
0x180062515  mov     dword ptr [rsp+140h+ResultLength], eax; Length
0x180062519  mov     [rsp+140h+Data], r15d
0x18006251e  call    cs:__imp_ZwEnumerateValueKey
0x180062525  nop     dword ptr [rax+rax+00h]
0x18006252a  test    eax, eax
0x18006252c  js      short loc_18006257E
0x18006252e  movzx   eax, word ptr [rbx+10h]
0x180062532  lea     rdx, [rsp+140h+ValueName]; ValueName
0x180062537  mov     ecx, [rbx+8]
0x18006253a  xorps   xmm0, xmm0
0x18006253d  mov     r9d, [rbx+4]; Type
0x180062541  add     rcx, rbx
0x180062544  movups  xmmword ptr [rsp+140h+ValueName.Length], xmm0
0x180062549  mov     [rsp+140h+ValueName.Length], ax
0x18006254e  xor     r8d, r8d; TitleIndex
0x180062551  mov     [rsp+140h+ValueName.MaximumLength], ax
0x180062556  lea     rax, [rbx+14h]
0x18006255a  mov     [rsp+140h+ValueName.Buffer], rax
0x18006255f  mov     eax, [rbx+0Ch]
0x180062562  mov     dword ptr [rsp+140h+var_118], eax; DataSize
0x180062566  mov     [rsp+140h+ResultLength], rcx; Data
0x18006256b  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x180062570  call    cs:__imp_ZwSetValueKey
0x180062577  nop     dword ptr [rax+rax+00h]
0x18006257c  mov     esi, eax
0x18006257e  xor     edx, edx; Tag
0x180062580  mov     rcx, rbx; P
0x180062583  call    cs:__imp_ExFreePoolWithTag
0x18006258a  nop     dword ptr [rax+rax+00h]
0x18006258f  add     edi, r12d
0x180062592  cmp     edi, dword ptr [rbp+40h+var_88]
0x180062595  jb      loc_180062469
0x18006259b  test    esi, esi
0x18006259d  js      loc_18006270E
0x1800625a3  lea     rdi, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x1800625aa  xorps   xmm0, xmm0
0x1800625ad  mov     [rsp+140h+Data], r12d
0x1800625b2  lea     rdx, aMscameraflags; "MSCameraFlags"
0x1800625b9  lea     rcx, [rsp+140h+ValueName]; DestinationString
0x1800625be  movups  xmmword ptr [rsp+140h+ValueName.Length], xmm0
0x1800625c3  call    cs:__imp_RtlInitUnicodeString
0x1800625ca  nop     dword ptr [rax+rax+00h]
0x1800625cf  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x1800625d4  lea     rax, [rsp+140h+Data]
0x1800625d9  mov     r9d, 4; Type
0x1800625df  lea     rdx, [rsp+140h+ValueName]; ValueName
0x1800625e4  mov     dword ptr [rsp+140h+var_118], r9d; DataSize
0x1800625e9  xor     r8d, r8d; TitleIndex
0x1800625ec  mov     [rsp+140h+ResultLength], rax; Data
0x1800625f1  call    cs:__imp_ZwSetValueKey
0x1800625f8  nop     dword ptr [rax+rax+00h]
0x1800625fd  mov     esi, eax
0x1800625ff  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180062606  jz      loc_18006270E
0x18006260c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062613  cmp     [rcx+48h], r15w
0x180062618  jz      loc_18006270E
0x18006261e  mov     rcx, [rcx+40h]
0x180062622  mov     r9d, 1Bh
0x180062628  mov     dword ptr [rsp+140h+var_118], eax
0x18006262c  mov     r8d, r12d
0x18006262f  mov     dl, 5
0x180062631  mov     [rsp+140h+ResultLength], rdi
0x180062636  call    WPP_RECORDER_SF_D
0x18006263b  jmp     loc_18006270E
0x180062640  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180062647  jz      loc_1800625AA
0x18006264d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062654  cmp     [rcx+48h], r15w
0x180062659  jz      loc_1800625AA
0x18006265f  mov     rcx, [rcx+40h]
0x180062663  mov     r9d, 1Ah
0x180062669  mov     r8d, r12d
0x18006266c  mov     [rsp+140h+ResultLength], rdi
0x180062671  mov     dl, 5
0x180062673  call    WPP_RECORDER_SF_
0x180062678  jmp     loc_1800625AA
0x18006267d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180062684  jz      loc_18006270E
0x18006268a  mov     rcx, cs:WPP_GLOBAL_Control
0x180062691  cmp     [rcx+48h], r15w
0x180062696  jz      short loc_18006270E
0x180062698  mov     r9d, 1Ch
0x18006269e  jmp     short loc_1800626FB
0x1800626a0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800626a7  jz      short loc_18006270E
0x1800626a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800626b0  cmp     [rcx+48h], r15w
0x1800626b5  jz      short loc_18006270E
0x1800626b7  mov     r9d, 1Dh
0x1800626bd  jmp     short loc_1800626FB
0x1800626bf  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800626c6  jz      short loc_18006270E
0x1800626c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800626cf  cmp     [rcx+48h], r15w
0x1800626d4  jz      short loc_18006270E
0x1800626d6  mov     r9d, 1Eh
0x1800626dc  jmp     short loc_1800626FB
0x1800626de  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800626e5  jz      short loc_18006270E
0x1800626e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800626ee  cmp     [rcx+48h], r15w
0x1800626f3  jz      short loc_18006270E
0x1800626f5  mov     r9d, 1Fh
0x1800626fb  mov     rcx, [rcx+40h]
0x1800626ff  mov     r8d, r12d
0x180062702  mov     dl, 5
0x180062704  mov     [rsp+140h+ResultLength], rdi
0x180062709  call    WPP_RECORDER_SF_
0x18006270e  mov     rcx, [rsp+140h+DeviceInterfaceRegKey]; Handle
0x180062713  test    rcx, rcx
0x180062716  jz      short loc_180062724
0x180062718  call    cs:__imp_ZwClose
0x18006271f  nop     dword ptr [rax+rax+00h]
0x180062724  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x180062729  test    rcx, rcx
0x18006272c  jz      short loc_18006273A
0x18006272e  call    cs:__imp_ZwClose
0x180062735  nop     dword ptr [rax+rax+00h]
0x18006273a  lea     rcx, [rsp+140h+AliasSymbolicLinkName]; UnicodeString
0x18006273f  call    cs:__imp_RtlFreeUnicodeString
0x180062746  nop     dword ptr [rax+rax+00h]
0x18006274b  lea     rdi, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x180062752  jmp     short loc_1800627A3
0x180062754  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18006275b  jz      short loc_1800627D7
0x18006275d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062764  cmp     [rcx+48h], r15w
0x180062769  jz      short loc_1800627A3
0x18006276b  mov     r9d, 20h ; ' '
0x180062771  jmp     short loc_180062790
0x180062773  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18006277a  jz      short loc_1800627D7
0x18006277c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062783  cmp     [rcx+48h], r15w
0x180062788  jz      short loc_1800627A3
0x18006278a  mov     r9d, 21h ; '!'
0x180062790  mov     rcx, [rcx+40h]
0x180062794  mov     r8d, r12d
0x180062797  mov     dl, 5
0x180062799  mov     [rsp+140h+ResultLength], rdi
0x18006279e  call    WPP_RECORDER_SF_
0x1800627a3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800627aa  jz      short loc_1800627D7
0x1800627ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800627b3  cmp     [rcx+48h], r15w
0x1800627b8  jz      short loc_1800627D7
0x1800627ba  mov     rcx, [rcx+40h]
0x1800627be  mov     r9d, 22h ; '"'
0x1800627c4  mov     dword ptr [rsp+140h+var_118], esi
0x1800627c8  mov     r8d, r12d
0x1800627cb  mov     dl, 5
0x1800627cd  mov     [rsp+140h+ResultLength], rdi
0x1800627d2  call    WPP_RECORDER_SF_D
0x1800627d7  mov     rcx, [rbp+40h+var_48]
0x1800627db  xor     rcx, rsp; StackCookie
0x1800627de  call    __security_check_cookie
0x1800627e3  add     rsp, 108h
0x1800627ea  pop     r15
0x1800627ec  pop     r14
  ... truncated ...
```
