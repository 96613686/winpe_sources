# ReadMultiChannelContraintParameters

- ea: `0x14002a900`
- end: `0x14002b243`
- name: `ReadMultiChannelContraintParameters`
- size: `2371`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14008fb70`
- `0x1400926ac`

## callees

- `0x14002a900`
- `0x14003838c`
- `0x140059dc0`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x14002ade9`
- `ntoskrnl!RtlGUIDFromString` at `0x14002af25`
- `ntoskrnl!RtlGUIDFromString` at `0x14002ade9`
- `ntoskrnl!RtlGUIDFromString` at `0x14002af25`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14002ac2d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14002ac73`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14002acf4`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14002ad65`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14002ac2d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14002ac73`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14002acf4`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14002ad65`
- `ntoskrnl!ZwOpenKey` at `0x14002abf5`
- `ntoskrnl!ZwOpenKey` at `0x14002abf5`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14002a9d3`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14002a9d3`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14002a97d`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14002a97d`
- `ntoskrnl!ExAllocatePool2` at `0x14002aca5`
- `ntoskrnl!ExAllocatePool2` at `0x14002ad2a`
- `ntoskrnl!ExAllocatePool2` at `0x14002ae96`
- `ntoskrnl!ExAllocatePool2` at `0x14002aec0`
- `ntoskrnl!ExAllocatePool2` at `0x14002aca5`
- `ntoskrnl!ExAllocatePool2` at `0x14002ad2a`
- `ntoskrnl!ExAllocatePool2` at `0x14002ae96`
- `ntoskrnl!ExAllocatePool2` at `0x14002aec0`
- `ntoskrnl!ZwClose` at `0x14002b185`
- `ntoskrnl!ZwClose` at `0x14002b185`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002b16d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14002b16d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002b098`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002b098`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002af9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b0db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b0fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b125`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b1b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b1d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b1fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b213`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002af9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b0db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b0fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b125`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b1b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b1d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b1fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b213`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x14002ae1c`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x14002af50`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x14002ae1c`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x14002af50`
- `NETIO!ConvertInterfaceGuidToLuid` at `0x14002ae02`
- `NETIO!ConvertInterfaceGuidToLuid` at `0x14002af3a`
- `NETIO!ConvertInterfaceGuidToLuid` at `0x14002ae02`
- `NETIO!ConvertInterfaceGuidToLuid` at `0x14002af3a`

## string_xrefs

- `0x14002a9b2`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`
- `0x14002aa7d`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanWorkStation\Parameters`

## pseudocode

```c
void ReadMultiChannelContraintParameters()
{
  int PersistedStateLocation; // r13d
  char *v1; // r12
  char v2; // si
  _DWORD *v3; // r14
  ULONG v4; // r15d
  __int64 v5; // rbx
  unsigned __int16 v6; // ax
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  const wchar_t *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // r8
  char *v13; // r10
  __int16 v14; // ax
  unsigned __int64 v15; // r10
  const wchar_t *v16; // rcx
  char *v17; // r9
  __int16 v18; // dx
  unsigned __int64 v19; // rax
  __int64 v20; // rdi
  NTSTATUS v21; // eax
  unsigned int v22; // esi
  wchar_t *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  bool v26; // zf
  char v27; // al
  __int64 v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rax
  __int16 v32; // ax
  void *v33; // rcx
  __int64 v34; // rsi
  wchar_t *v35; // rbx
  __int64 v36; // rax
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  unsigned int i; // edi
  char *v40; // rbx
  void *v41; // rcx
  char *v42; // rsi
  ULONG j; // edi
  char *v44; // rbx
  void *v45; // rcx
  char v46; // [rsp+40h] [rbp-C0h]
  char v47; // [rsp+41h] [rbp-BFh]
  ULONG v48; // [rsp+44h] [rbp-BCh]
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG InterfaceIndex; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 Pool2; // [rsp+50h] [rbp-B0h]
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  char *v53; // [rsp+60h] [rbp-A0h]
  void *KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  NET_LUID InterfaceLuid; // [rsp+70h] [rbp-90h] BYREF
  UNICODE_STRING GuidString; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+88h] [rbp-78h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  GUID Guid; // [rsp+C0h] [rbp-40h] BYREF
  char v60; // [rsp+D0h] [rbp-30h] BYREF

  PersistedStateLocation = 0;
  v52 = 34078720;
  KeyHandle = 0;
  v48 = 0;
  ResultLength = 0;
  v1 = 0;
  v53 = &v60;
  v2 = 0;
  v47 = 0;
  memset(&ObjectAttributes, 0, 44);
  v3 = 0;
  v4 = 0;
  v46 = 0;
  InterfaceIndex = 0;
  v5 = 0x7FFF;
  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"LanmanWorkStationParameters",
                               0,
                               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters",
                               0,
                               v53,
                               WORD1(v52),
                               &InterfaceIndex);
    if ( PersistedStateLocation >= 0 )
    {
      v6 = InterfaceIndex - 2;
      LOWORD(v52) = InterfaceIndex - 2;
      goto LABEL_20;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_85;
    }
    v8 = 34;
    v9 = (unsigned int)PersistedStateLocation;
LABEL_84:
    WPP_SF_d(v7->AttachedDevice, v8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v9);
LABEL_85:
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_92;
    }
    v38 = 36;
LABEL_78:
    WPP_SF_d(
      v37->AttachedDevice,
      v38,
      WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
      (unsigned int)PersistedStateLocation);
    goto LABEL_92;
  }
  if ( !v53 )
  {
    PersistedStateLocation = -1073741811;
LABEL_80:
    v9 = (unsigned int)PersistedStateLocation;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_85;
    }
    v8 = 35;
    goto LABEL_84;
  }
  v10 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanWorkStation\\Parameters";
  v11 = (unsigned __int64)WORD1(v52) >> 1;
  v12 = 0x7FFF;
  v13 = v53;
  v14 = 0;
  if ( v11 )
  {
    while ( v12 && *v10 )
    {
      *(_WORD *)v13 = *v10++;
      v13 += 2;
      --v12;
      ++v14;
      if ( !--v11 )
      {
        if ( !v12 || !*v10 )
          break;
        goto LABEL_18;
      }
    }
  }
  else
  {
LABEL_18:
    PersistedStateLocation = -2147483643;
  }
  v6 = 2 * v14;
  LOWORD(v52) = v6;
  if ( PersistedStateLocation < 0 )
    goto LABEL_80;
LABEL_20:
  if ( (unsigned __int64)v6 + 2 > WORD1(v52) )
  {
    PersistedStateLocation = -1073741789;
    goto LABEL_85;
  }
  *(_WORD *)&v53[v6] = 0;
  if ( (v52 & 1) != 0
    || (v52 & 0x10000) != 0
    || (unsigned __int16)v52 > WORD1(v52)
    || WORD1(v52) == 0xFFFF
    || !v53 && (_DWORD)v52 )
  {
    PersistedStateLocation = -1073741811;
LABEL_74:
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_92;
    }
    v38 = 37;
    goto LABEL_78;
  }
  v15 = (unsigned __int64)(unsigned __int16)v52 >> 1;
  v16 = L"\\MultichannelConstraint";
  PersistedStateLocation = 0;
  v17 = &v53[2 * v15];
  v18 = 0;
  v19 = ((unsigned __int64)WORD1(v52) >> 1) - v15;
  if ( v19 )
  {
    while ( v5 && *v16 )
    {
      *(_WORD *)v17 = *v16++;
      v17 += 2;
      --v5;
      ++v18;
      if ( !--v19 )
      {
        if ( !v5 || !*v16 )
          break;
        goto LABEL_35;
      }
    }
  }
  else
  {
LABEL_35:
    PersistedStateLocation = -2147483643;
  }
  LOWORD(v52) = 2 * (v15 + v18);
  if ( PersistedStateLocation < 0 )
    goto LABEL_74;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v52;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    v47 = 1;
    if ( ZwEnumerateValueKey(KeyHandle, 0, KeyValueFullInformation, 0, 0, &ResultLength) != -2147483622 )
    {
      do
        LODWORD(v1) = (_DWORD)v1 + 1;
      while ( ZwEnumerateValueKey(KeyHandle, (ULONG)v1, KeyValueFullInformation, 0, 0, &ResultLength) != -2147483622 );
      v57 = (int)v1;
      if ( (_DWORD)v1 )
      {
        Pool2 = ExAllocatePool2(64, 32LL * (unsigned int)v1, 1665366098);
        v20 = Pool2;
        if ( Pool2 )
        {
          while ( 1 )
          {
            v21 = ZwEnumerateValueKey(KeyHandle, v4, KeyValueFullInformation, 0, 0, &ResultLength);
            if ( v21 == -2147483622 )
            {
LABEL_72:
              v4 = v48;
              v2 = 1;
              v1 = (char *)Pool2;
              v3 = 0;
              v46 = 1;
              goto LABEL_92;
            }
            if ( v21 == -2147483643 || v21 == -1073741789 )
            {
              v3 = (_DWORD *)ExAllocatePool2(258, ResultLength, 1665366098);
              if ( !v3 || ZwEnumerateValueKey(KeyHandle, v4, KeyValueFullInformation, v3, ResultLength, &ResultLength) )
              {
LABEL_89:
                v4 = v48;
                v2 = 0;
                v1 = (char *)Pool2;
                goto LABEL_92;
              }
              if ( v3[1] == 7 )
              {
                v22 = 0;
                v23 = (wchar_t *)((char *)v3 + (unsigned int)v3[2]);
                InterfaceLuid.Value = 0;
                InterfaceIndex = 0;
                GuidString = 0;
                Guid = 0;
                if ( *v23 )
                {
                  while ( 1 )
                  {
                    v24 = -1;
                    do
                      ++v24;
                    while ( v23[v24] );
                    if ( v24 != 38 )
                      break;
                    *(_DWORD *)&GuidString.Length = 4980812;
                    GuidString.Buffer = v23;
                    if ( RtlGUIDFromString(&GuidString, &Guid) < 0
                      || ConvertInterfaceGuidToLuid(&Guid, &InterfaceLuid) < 0
                      || ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex) < 0 )
                    {
                      break;
                    }
                    ++v22;
                    v25 = -1;
                    do
                      v26 = v23[++v25] == 0;
                    while ( !v26 );
                    v23 += v25 + 1;
                    if ( !*v23 )
                    {
                      v27 = 0;
                      goto LABEL_60;
                    }
                  }
                  v27 = 1;
LABEL_60:
                  if ( v22 && !v27 )
                  {
                    v28 = 32LL * v48++;
                    v29 = v28 + v20;
                    v30 = ExAllocatePool2(64, (unsigned int)v3[4], 1665366098);
                    *(_QWORD *)(v29 + 24) = v30;
                    if ( !v30 )
                      goto LABEL_89;
                    v31 = ExAllocatePool2(64, 4LL * v22, 1665366098);
                    *(_QWORD *)v29 = v31;
                    if ( !v31 )
                      goto LABEL_89;
                    v32 = *((_WORD *)v3 + 8);
                    v33 = *(void **)(v29 + 24);
                    *(_WORD *)(v29 + 18) = v32;
                    *(_WORD *)(v29 + 16) = v32;
                    memmove(v33, v3 + 5, (unsigned int)v3[4]);
                    *(_DWORD *)(v29 + 8) = v22;
                    v34 = 0;
                    v35 = (wchar_t *)((char *)v3 + (unsigned int)v3[2]);
                    if ( *v35 )
                    {
                      do
                      {
                        *(_DWORD *)&GuidString.Length = 4980812;
                        GuidString.Buffer = v35;
                        RtlGUIDFromString(&GuidString, &Guid);
                        ConvertInterfaceGuidToLuid(&Guid, &InterfaceLuid);
                        ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
                        *(_DWORD *)(*(_QWORD *)v29 + 4 * v34) = InterfaceIndex;
                        v34 = (unsigned int)(v34 + 1);
                        v36 = -1;
                        do
                          v26 = v35[++v36] == 0;
                        while ( !v26 );
                        v35 += v36 + 1;
                      }
                      while ( *v35 );
                      LODWORD(v1) = v57;
                    }
                    v20 = Pool2;
                  }
                }
              }
              ExFreePoolWithTag(v3, 0x63437852u);
            }
            if ( ++v4 >= (unsigned int)v1 )
              goto LABEL_72;
          }
        }
        v1 = 0;
      }
      else
      {
        v1 = 0;
      }
    }
  }
LABEL_92:
  ExAcquirePushLockExclusiveEx(&qword_14007D0D8, 0);
  if ( P )
  {
    for ( i = 0; i < dword_14007D0E8; ++i )
    {
      v40 = (char *)P + 32 * i;
      v41 = (void *)*((_QWORD *)v40 + 3);
      if ( v41 )
      {
        ExFreePoolWithTag(v41, 0x63437852u);
        *((_QWORD *)v40 + 3) = 0;
      }
      if ( *(_QWORD *)v40 )
      {
        ExFreePoolWithTag(*(PVOID *)v40, 0x63437852u);
        *(_QWORD *)v40 = 0;
      }
    }
    ExFreePoolWithTag(P, 0x63437852u);
    P = 0;
    dword_14007D0E8 = 0;
  }
  if ( v2 )
  {
    P = v1;
    dword_14007D0E8 = v4;
  }
  v42 = 0;
  if ( !v46 )
    v42 = v1;
  ExReleasePushLockExclusiveEx(&qword_14007D0D8, 0);
  if ( v47 )
    ZwClose(KeyHandle);
  if ( v42 )
  {
    for ( j = 0; j < v4; ++j )
    {
      v44 = &v42[32 * j];
      v45 = (void *)*((_QWORD *)v44 + 3);
      if ( v45 )
      {
        ExFreePoolWithTag(v45, 0x63437852u);
        *((_QWORD *)v44 + 3) = 0;
      }
      if ( *(_QWORD *)v44 )
      {
        ExFreePoolWithTag(*(PVOID *)v44, 0x63437852u);
        *(_QWORD *)v44 = 0;
      }
    }
    ExFreePoolWithTag(v42, 0x63437852u);
  }
  if ( v3 )
    ExFreePoolWithTag(v3, 0x63437852u);
}

```

## disassembly

```asm
0x14002a900  push    rbp
0x14002a902  push    rbx
0x14002a903  push    rsi
0x14002a904  push    rdi
0x14002a905  push    r12
0x14002a907  push    r13
0x14002a909  push    r14
0x14002a90b  push    r15
0x14002a90d  lea     rbp, [rsp-1F8h]
0x14002a915  sub     rsp, 2F8h
0x14002a91c  mov     rax, cs:__security_cookie
0x14002a923  xor     rax, rsp
0x14002a926  mov     [rbp+230h+var_50], rax
0x14002a92d  xor     r13d, r13d
0x14002a930  mov     [rsp+330h+var_2D8], 2080000h
0x14002a939  xorps   xmm0, xmm0
0x14002a93c  mov     [rsp+330h+KeyHandle], r13
0x14002a941  xor     eax, eax
0x14002a943  mov     [rsp+330h+var_2EC], r13d
0x14002a948  lea     rax, [rbp+230h+var_260]
0x14002a94c  mov     [rsp+330h+var_2E8], r13d
0x14002a951  movups  xmmword ptr [rbp+230h+ObjectAttributes.ObjectName], xmm0
0x14002a955  mov     r12d, r13d
0x14002a958  mov     [rsp+330h+var_2D0], rax
0x14002a95d  xor     sil, sil
0x14002a960  mov     [rsp+330h+var_2EF], r12b
0x14002a965  movups  xmmword ptr [rbp+230h+ObjectAttributes.Length], xmm0
0x14002a969  mov     r14d, r13d
0x14002a96c  mov     r15d, r13d
0x14002a96f  movups  xmmword ptr [rbp+230h+ObjectAttributes+1Ch], xmm0
0x14002a973  mov     [rsp+330h+var_2F0], sil
0x14002a978  mov     [rsp+330h+InterfaceIndex], r13d
0x14002a97d  call    cs:__imp_RtlIsStateSeparationEnabled
0x14002a984  nop     dword ptr [rax+rax+00h]
0x14002a989  lea     rdi, WPP_GLOBAL_Control
0x14002a990  mov     ebx, 7FFFh
0x14002a995  mov     r11d, 0FFFEh
0x14002a99b  test    al, al
0x14002a99d  jz      loc_14002AA31
0x14002a9a3  movzx   eax, word ptr [rsp+330h+var_2D8+2]
0x14002a9a8  lea     rcx, [rsp+330h+InterfaceIndex]
0x14002a9ad  mov     [rsp+330h+var_300], rcx
0x14002a9b2  lea     r8, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002a9b9  mov     dword ptr [rsp+330h+ResultLength], eax
0x14002a9bd  lea     rcx, aLanmanworkstat; "LanmanWorkStationParameters"
0x14002a9c4  mov     rax, [rsp+330h+var_2D0]
0x14002a9c9  xor     r9d, r9d
0x14002a9cc  xor     edx, edx
0x14002a9ce  mov     qword ptr [rsp+330h+Length], rax
0x14002a9d3  call    cs:__imp_RtlGetPersistedStateLocation
0x14002a9da  nop     dword ptr [rax+rax+00h]
0x14002a9df  mov     r13d, eax
0x14002a9e2  test    eax, eax
0x14002a9e4  js      short loc_14002A9FF
0x14002a9e6  movzx   eax, word ptr [rsp+330h+InterfaceIndex]
0x14002a9eb  mov     r11d, 0FFFEh
0x14002a9f1  sub     ax, 2
0x14002a9f5  mov     word ptr [rsp+330h+var_2D8], ax
0x14002a9fa  jmp     loc_14002AAE4
0x14002a9ff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002aa06  cmp     rcx, rdi
0x14002aa09  jz      loc_14002B058
0x14002aa0f  mov     eax, [rcx+2Ch]
0x14002aa12  test    al, 1
0x14002aa14  jz      loc_14002B058
0x14002aa1a  cmp     byte ptr [rcx+29h], 1
0x14002aa1e  jb      loc_14002B058
0x14002aa24  mov     edx, 22h ; '"'
0x14002aa29  mov     r9d, r13d
0x14002aa2c  jmp     loc_14002B048
0x14002aa31  movzx   ecx, word ptr [rsp+330h+var_2D8]
0x14002aa36  test    cl, 1
0x14002aa39  jnz     loc_14002B021
0x14002aa3f  movzx   eax, word ptr [rsp+330h+var_2D8+2]
0x14002aa44  test    al, 1
0x14002aa46  jnz     loc_14002B021
0x14002aa4c  cmp     cx, ax
0x14002aa4f  ja      loc_14002B021
0x14002aa55  cmp     ax, r11w
0x14002aa59  ja      loc_14002B021
0x14002aa5f  cmp     [rsp+330h+var_2D0], r12
0x14002aa64  jnz     short loc_14002AA78
0x14002aa66  test    cx, cx
0x14002aa69  jnz     loc_14002B021
0x14002aa6f  test    ax, ax
0x14002aa72  jnz     loc_14002B021
0x14002aa78  movzx   edx, word ptr [rsp+330h+var_2D8+2]
0x14002aa7d  lea     rcx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002aa84  shr     rdx, 1
0x14002aa87  mov     r8, rbx
0x14002aa8a  mov     r10, [rsp+330h+var_2D0]
0x14002aa8f  mov     rax, r12
0x14002aa92  jz      short loc_14002AACD
0x14002aa94  test    r8, r8
0x14002aa97  jz      short loc_14002AAD3
0x14002aa99  movzx   r9d, word ptr [rcx]
0x14002aa9d  test    r9w, r9w
0x14002aaa1  jz      short loc_14002AABD
0x14002aaa3  mov     [r10], r9w
0x14002aaa7  add     rcx, 2
0x14002aaab  add     r10, 2
0x14002aaaf  dec     r8
0x14002aab2  inc     rax
0x14002aab5  sub     rdx, 1
0x14002aab9  jnz     short loc_14002AA94
0x14002aabb  jmp     short loc_14002AAC2
0x14002aabd  test    rdx, rdx
0x14002aac0  jnz     short loc_14002AAD3
0x14002aac2  test    r8, r8
0x14002aac5  jz      short loc_14002AAD3
0x14002aac7  cmp     [rcx], r12w
0x14002aacb  jz      short loc_14002AAD3
0x14002aacd  mov     r13d, 80000005h
0x14002aad3  add     ax, ax
0x14002aad6  mov     word ptr [rsp+330h+var_2D8], ax
0x14002aadb  test    r13d, r13d
0x14002aade  js      loc_14002B027
0x14002aae4  movzx   edx, ax
0x14002aae7  movzx   eax, word ptr [rsp+330h+var_2D8+2]
0x14002aaec  lea     rcx, [rdx+2]
0x14002aaf0  cmp     rcx, rax
0x14002aaf3  ja      loc_14002B019
0x14002aaf9  mov     rax, [rsp+330h+var_2D0]
0x14002aafe  xor     ecx, ecx
0x14002ab00  mov     [rdx+rax], cx
0x14002ab04  movzx   ecx, word ptr [rsp+330h+var_2D8]
0x14002ab09  test    cl, 1
0x14002ab0c  jnz     loc_14002AFCD
0x14002ab12  movzx   eax, word ptr [rsp+330h+var_2D8+2]
0x14002ab17  test    al, 1
0x14002ab19  jnz     loc_14002AFCD
0x14002ab1f  cmp     cx, ax
0x14002ab22  ja      loc_14002AFCD
0x14002ab28  cmp     ax, r11w
0x14002ab2c  ja      loc_14002AFCD
0x14002ab32  mov     rdx, [rsp+330h+var_2D0]
0x14002ab37  test    rdx, rdx
0x14002ab3a  jnz     short loc_14002AB4E
0x14002ab3c  test    cx, cx
0x14002ab3f  jnz     loc_14002AFCD
0x14002ab45  test    ax, ax
0x14002ab48  jnz     loc_14002AFCD
0x14002ab4e  mov     r10, rcx
0x14002ab51  shr     rax, 1
0x14002ab54  shr     r10, 1
0x14002ab57  lea     rcx, aMultichannelco; "\\MultichannelConstraint"
0x14002ab5e  mov     r13d, r12d
0x14002ab61  lea     r9, [rdx+r10*2]
0x14002ab65  mov     rdx, r12
0x14002ab68  sub     rax, r10
0x14002ab6b  jz      short loc_14002ABA9
0x14002ab6d  nop     dword ptr [rax]
0x14002ab70  test    rbx, rbx
0x14002ab73  jz      short loc_14002ABAF
0x14002ab75  movzx   r8d, word ptr [rcx]
0x14002ab79  test    r8w, r8w
0x14002ab7d  jz      short loc_14002AB99
0x14002ab7f  mov     [r9], r8w
0x14002ab83  add     rcx, 2
0x14002ab87  add     r9, 2
0x14002ab8b  dec     rbx
0x14002ab8e  inc     rdx
0x14002ab91  sub     rax, 1
0x14002ab95  jnz     short loc_14002AB70
0x14002ab97  jmp     short loc_14002AB9E
0x14002ab99  test    rax, rax
0x14002ab9c  jnz     short loc_14002ABAF
0x14002ab9e  test    rbx, rbx
0x14002aba1  jz      short loc_14002ABAF
0x14002aba3  cmp     [rcx], r12w
0x14002aba7  jz      short loc_14002ABAF
0x14002aba9  mov     r13d, 80000005h
0x14002abaf  add     dx, r10w
0x14002abb3  add     dx, dx
0x14002abb6  mov     word ptr [rsp+330h+var_2D8], dx
0x14002abbb  test    r13d, r13d
0x14002abbe  js      loc_14002AFD3
0x14002abc4  lea     rax, [rsp+330h+var_2D8]
0x14002abc9  mov     [rbp+230h+ObjectAttributes.Length], 30h ; '0'
0x14002abd0  xorps   xmm0, xmm0
0x14002abd3  mov     [rbp+230h+ObjectAttributes.ObjectName], rax
0x14002abd7  lea     r8, [rbp+230h+ObjectAttributes]; ObjectAttributes
0x14002abdb  mov     [rbp+230h+ObjectAttributes.RootDirectory], r12
0x14002abdf  mov     edx, 20019h; DesiredAccess
0x14002abe4  mov     [rbp+230h+ObjectAttributes.Attributes], 240h
0x14002abeb  lea     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x14002abf0  movdqu  xmmword ptr [rbp+230h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002abf5  call    cs:__imp_ZwOpenKey
0x14002abfc  nop     dword ptr [rax+rax+00h]
0x14002ac01  test    eax, eax
0x14002ac03  js      loc_14002B08F
0x14002ac09  mov     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x14002ac0e  lea     rax, [rsp+330h+var_2E8]
0x14002ac13  mov     [rsp+330h+ResultLength], rax; ResultLength
0x14002ac18  xor     r9d, r9d; KeyValueInformation
0x14002ac1b  xor     edx, edx; Index
0x14002ac1d  mov     [rsp+330h+Length], r12d; Length
0x14002ac22  mov     r8d, 1; KeyValueInformationClass
0x14002ac28  mov     [rsp+330h+var_2EF], 1
0x14002ac2d  call    cs:__imp_ZwEnumerateValueKey
0x14002ac34  nop     dword ptr [rax+rax+00h]
0x14002ac39  cmp     eax, 8000001Ah
0x14002ac3e  jz      loc_14002B08F
0x14002ac44  nop     dword ptr [rax+00h]
0x14002ac48  nop     dword ptr [rax+rax+00000000h]
0x14002ac50  mov     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x14002ac55  lea     rax, [rsp+330h+var_2E8]
0x14002ac5a  mov     [rsp+330h+ResultLength], rax; ResultLength
0x14002ac5f  inc     r12d
0x14002ac62  mov     edx, r12d; Index
0x14002ac65  mov     [rsp+330h+Length], r14d; Length
0x14002ac6a  xor     r9d, r9d; KeyValueInformation
0x14002ac6d  mov     r8d, 1; KeyValueInformationClass
0x14002ac73  call    cs:__imp_ZwEnumerateValueKey
0x14002ac7a  nop     dword ptr [rax+rax+00h]
0x14002ac7f  cmp     eax, 8000001Ah
0x14002ac84  jnz     short loc_14002AC50
0x14002ac86  mov     [rbp+230h+var_2A8], r12d
0x14002ac8a  test    r12d, r12d
0x14002ac8d  jz      loc_14002B08C
0x14002ac93  mov     edx, r12d
0x14002ac96  mov     ecx, 40h ; '@'
0x14002ac9b  shl     rdx, 5
0x14002ac9f  mov     r8d, 63437852h
0x14002aca5  call    cs:__imp_ExAllocatePool2
0x14002acac  nop     dword ptr [rax+rax+00h]
0x14002acb1  mov     [rsp+330h+var_2E0], rax
0x14002acb6  mov     rdi, rax
0x14002acb9  test    rax, rax
0x14002acbc  jz      loc_14002B087
0x14002acc2  test    r12d, r12d
0x14002acc5  jz      loc_14002AFB3
0x14002accb  mov     r13d, 0C0000023h
0x14002acd1  mov     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x14002acd6  lea     rax, [rsp+330h+var_2E8]
0x14002acdb  mov     [rsp+330h+ResultLength], rax; ResultLength
0x14002ace0  xor     r9d, r9d; KeyValueInformation
0x14002ace3  mov     r8d, 1; KeyValueInformationClass
0x14002ace9  mov     [rsp+330h+Length], 0; Length
0x14002acf1  mov     edx, r15d; Index
0x14002acf4  call    cs:__imp_ZwEnumerateValueKey
0x14002acfb  nop     dword ptr [rax+rax+00h]
0x14002ad00  cmp     eax, 8000001Ah
0x14002ad05  jz      loc_14002AFB3
0x14002ad0b  cmp     eax, 80000005h
0x14002ad10  jz      short loc_14002AD1B
0x14002ad12  cmp     eax, r13d
0x14002ad15  jnz     loc_14002AFA7
0x14002ad1b  mov     edx, [rsp+330h+var_2E8]
0x14002ad1f  mov     ecx, 102h
0x14002ad24  mov     r8d, 63437852h
0x14002ad2a  call    cs:__imp_ExAllocatePool2
0x14002ad31  nop     dword ptr [rax+rax+00h]
0x14002ad36  mov     r14, rax
0x14002ad39  test    rax, rax
0x14002ad3c  jz      loc_14002B078
0x14002ad42  mov     ecx, [rsp+330h+var_2E8]
0x14002ad46  lea     rax, [rsp+330h+var_2E8]
0x14002ad4b  mov     [rsp+330h+ResultLength], rax; ResultLength
0x14002ad50  mov     r9, r14; KeyValueInformation
0x14002ad53  mov     [rsp+330h+Length], ecx; Length
0x14002ad57  mov     r8d, 1; KeyValueInformationClass
0x14002ad5d  mov     rcx, [rsp+330h+KeyHandle]; KeyHandle
0x14002ad62  mov     edx, r15d; Index
0x14002ad65  call    cs:__imp_ZwEnumerateValueKey
0x14002ad6c  nop     dword ptr [rax+rax+00h]
0x14002ad71  test    eax, eax
0x14002ad73  jnz     loc_14002B078
0x14002ad79  cmp     dword ptr [r14+4], 7
0x14002ad7e  jnz     loc_14002AF93
0x14002ad84  mov     ebx, [r14+8]
0x14002ad88  xor     esi, esi
0x14002ad8a  add     rbx, r14
0x14002ad8d  mov     qword ptr [rsp+330h+InterfaceLuid], rsi
0x14002ad92  xorps   xmm0, xmm0
0x14002ad95  mov     [rsp+330h+InterfaceIndex], esi
0x14002ad99  xorps   xmm1, xmm1
0x14002ad9c  movups  xmmword ptr [rsp+330h+GuidString.Length], xmm0
0x14002ada1  movups  xmmword ptr [rbp+230h+Guid.Data1], xmm1
0x14002ada5  cmp     [rbx], si
0x14002ada8  jz      loc_14002AF93
0x14002adae  xchg    ax, ax
0x14002adb0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14002adb7  nop     word ptr [rax+rax+00000000h]
0x14002adc0  inc     rax
0x14002adc3  cmp     word ptr [rbx+rax*2], 0
0x14002adc8  jnz     short loc_14002ADC0
0x14002adca  cmp     rax, 26h ; '&'
0x14002adce  jnz     loc_14002AE62
0x14002add4  lea     rdx, [rbp+230h+Guid]; Guid
0x14002add8  mov     dword ptr [rsp+330h+GuidString.Length], 4C004Ch
0x14002ade0  lea     rcx, [rsp+330h+GuidString]; GuidString
0x14002ade5  mov     [rbp+230h+GuidString.Buffer], rbx
0x14002ade9  call    cs:__imp_RtlGUIDFromString
0x14002adf0  nop     dword ptr [rax+rax+00h]
0x14002adf5  test    eax, eax
0x14002adf7  js      short loc_14002AE62
0x14002adf9  lea     rdx, [rsp+330h+InterfaceLuid]; InterfaceLuid
0x14002adfe  lea     rcx, [rbp+230h+Guid]; InterfaceGuid
0x14002ae02  call    cs:__imp_ConvertInterfaceGuidToLuid
  ... truncated ...
```
