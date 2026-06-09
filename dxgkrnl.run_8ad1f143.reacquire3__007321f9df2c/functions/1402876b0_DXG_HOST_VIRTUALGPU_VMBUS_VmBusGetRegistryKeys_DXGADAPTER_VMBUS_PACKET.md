# DXG_HOST_VIRTUALGPU_VMBUS::VmBusGetRegistryKeys(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x1402876b0`
- end: `0x140287db4`
- name: `?VmBusGetRegistryKeys@DXG_HOST_VIRTUALGPU_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `1796`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x14001ab20`
- `0x14001b890`
- `0x14001e338`
- `0x1400491a8`
- `0x14005cddc`
- `0x1400681e8`
- `0x140072f58`
- `0x14007d7a4`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x140234ad0`
- `0x140234b14`
- `0x140236708`
- `0x140236e9c`
- `0x1402876b0`
- `0x1403dc3f4`

## import_xrefs

- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140287844`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x140287844`
- `ntoskrnl!ObfDereferenceObject` at `0x140287879`
- `ntoskrnl!ObfDereferenceObject` at `0x140287879`
- `ntoskrnl!ZwOpenKey` at `0x1402879f3`
- `ntoskrnl!ZwOpenKey` at `0x1402879f3`
- `ntoskrnl!ZwQueryKey` at `0x140287a2a`
- `ntoskrnl!ZwQueryKey` at `0x140287a2a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140287ab8`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140287ab8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140287867`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140287867`
- `watchdog!WdLogSingleEntry0` at `0x140287706`
- `watchdog!WdLogSingleEntry0` at `0x1402877e5`
- `watchdog!WdLogSingleEntry0` at `0x140287c4a`
- `watchdog!WdLogSingleEntry0` at `0x140287706`
- `watchdog!WdLogSingleEntry0` at `0x1402877e5`
- `watchdog!WdLogSingleEntry0` at `0x140287c4a`
- `watchdog!WdLogSingleEntry1` at `0x14028788e`
- `watchdog!WdLogSingleEntry1` at `0x1402878f9`
- `watchdog!WdLogSingleEntry1` at `0x140287935`
- `watchdog!WdLogSingleEntry1` at `0x140287972`
- `watchdog!WdLogSingleEntry1` at `0x140287bb3`
- `watchdog!WdLogSingleEntry1` at `0x140287bdb`
- `watchdog!WdLogSingleEntry1` at `0x140287c1e`
- `watchdog!WdLogSingleEntry1` at `0x140287c90`
- `watchdog!WdLogSingleEntry1` at `0x140287cb4`
- `watchdog!WdLogSingleEntry1` at `0x140287cd8`
- `watchdog!WdLogSingleEntry1` at `0x14028788e`
- `watchdog!WdLogSingleEntry1` at `0x1402878f9`
- `watchdog!WdLogSingleEntry1` at `0x140287935`
- `watchdog!WdLogSingleEntry1` at `0x140287972`
- `watchdog!WdLogSingleEntry1` at `0x140287bb3`
- `watchdog!WdLogSingleEntry1` at `0x140287bdb`
- `watchdog!WdLogSingleEntry1` at `0x140287c1e`
- `watchdog!WdLogSingleEntry1` at `0x140287c90`
- `watchdog!WdLogSingleEntry1` at `0x140287cb4`
- `watchdog!WdLogSingleEntry1` at `0x140287cd8`

## string_xrefs

- `0x140287c9c`: `Failed to query key for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140287717`: `The adapter is already closed by the guest`
- `0x1402877f4`: `Cannot allocate memory for DXGKVMB_COMMAND_GETREGISTRYKEYS_RETURN`
- `0x140287905`: `Failed to copy root registry key name for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028789a`: `Failed to read PnP registry key name for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140287941`: `Failed to append null char to CurrentRegistryPath for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140287ce4`: `Failed to initialize subkey string for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028797e`: `Failed to insert root registry key name into list for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140287cc0`: `Failed to open PnP registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140287bbf`: `Failed to Enumerate Value for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140287bf9`: `Maximum number of KeyValues reached, aborting VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140287c2a`: `Failed to Append SubKeys for VmBusGetRegistryKeys (status = 0x%I64x).`

## pseudocode

```c
char __fastcall DXG_HOST_VIRTUALGPU_VMBUS::VmBusGetRegistryKeys(struct DXGADAPTER_VMBUS_PACKET *a1)
{
  char v2; // bl
  __int64 v4; // r13
  unsigned int v5; // esi
  _DWORD *v6; // r15
  unsigned int *v7; // r14
  __int64 v8; // rdi
  struct _DEVICE_OBJECT *DeviceAttachmentBaseRef; // rbx
  const wchar_t *v10; // r9
  int v11; // eax
  ULONG v12; // r13d
  int v13; // eax
  int inserted; // eax
  int v15; // eax
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  ULONG v18; // ebx
  NTSTATUS v19; // eax
  unsigned int *v20; // rbx
  int appended; // eax
  const wchar_t *v22; // r9
  unsigned int v23; // eax
  __int64 ResultLength; // [rsp+20h] [rbp-E0h]
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v26; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[2]; // [rsp+68h] [rbp-98h] BYREF
  ULONG v28; // [rsp+78h] [rbp-88h] BYREF
  ULONG v29; // [rsp+7Ch] [rbp-84h] BYREF
  ULONG v30; // [rsp+80h] [rbp-80h]
  void *DeviceRegKey; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[24]; // [rsp+C0h] [rbp-40h] BYREF
  struct _KEY_FULL_INFORMATION KeyInformation; // [rsp+D8h] [rbp-28h] BYREF
  char v35; // [rsp+110h] [rbp+10h] BYREF

  DXGAUTOPUSHLOCKSHARED::DXGAUTOPUSHLOCKSHARED(
    (DXGAUTOPUSHLOCKSHARED *)v33,
    (struct DXGPUSHLOCK *const)(*((_QWORD *)a1 + 10) + 248LL));
  v2 = 0;
  if ( !*(_BYTE *)(*((_QWORD *)a1 + 10) + 173LL) )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 6065;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"The adapter is already closed by the guest",
      6065,
      0,
      0,
      0,
      0);
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v33);
    return 0;
  }
  v4 = CastToVmBusCommand<DXGKVMB_COMMAND_GETREGISTRYKEYS>(a1);
  if ( v4 )
  {
    DeviceRegKey = 0;
    KeyHandle = 0;
    v26.Buffer = (wchar_t *)&v35;
    v5 = 130040;
    *(_QWORD *)&v26.Length = 34078720;
    v27[1] = v27;
    v27[0] = v27;
    memset(&KeyInformation, 0, sizeof(KeyInformation));
    v6 = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v7 = (unsigned int *)operator new[](130040, 1265072196, 64);
    if ( !v7 )
    {
      LODWORD(v8) = -1073741801;
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 6085;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Cannot allocate memory for DXGKVMB_COMMAND_GETREGISTRYKEYS_RETURN",
        6085,
        0,
        0,
        0,
        0);
LABEL_41:
      CloseRegistrySubkey(DeviceRegKey);
      CloseRegistrySubkey(KeyHandle);
      v2 = 0;
      if ( v7 )
      {
        v23 = *v7;
        v7[1] = v8;
        if ( v23 < 0x2A )
          v5 = 3096 * v23 + 8;
        VmBusCompletePacket(*((struct VMBPACKETCOMPLETION__ **)a1 + 16), v7, v5);
        v2 = 1;
      }
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v7);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v6);
      DXG_REGISTRY_KEY_LIST::~DXG_REGISTRY_KEY_LIST((DXG_REGISTRY_KEY_LIST *)v27);
      goto LABEL_46;
    }
    DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(*(PDEVICE_OBJECT *)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 16LL)
                                                                             + 216LL));
    v8 = IoOpenDeviceRegistryKey(DeviceAttachmentBaseRef, 2u, 0x20019u, &DeviceRegKey);
    ObfDereferenceObject(DeviceAttachmentBaseRef);
    if ( (int)v8 < 0 )
    {
      WdLogSingleEntry1(2);
      v10 = L"Failed to read PnP registry key name for VmBusGetRegistryKeys (status = 0x%I64x).";
      WdLogGlobalForLineNumber = 6099;
      goto LABEL_8;
    }
    v11 = RtlUnicodeStringCopyString(&v26, (const unsigned __int16 *)(v4 + 24));
    v12 = 0;
    v8 = v11;
    if ( v11 < 0 )
    {
      WdLogSingleEntry1(2);
      v10 = L"Failed to copy root registry key name for VmBusGetRegistryKeys (status = 0x%I64x).";
      WdLogGlobalForLineNumber = 6108;
      goto LABEL_8;
    }
    v13 = RtlUnicodeStringCatString(&v26, &qword_140126320);
    v8 = v13;
    if ( v13 < 0 )
    {
      WdLogSingleEntry1(2);
      v10 = L"Failed to append null char to CurrentRegistryPath for VmBusGetRegistryKeys (status = 0x%I64x).";
      WdLogGlobalForLineNumber = 6116;
      goto LABEL_8;
    }
    inserted = DXG_REGISTRY_KEY_LIST::InsertHead((DXG_REGISTRY_KEY_LIST *)v27, &v26);
    v8 = inserted;
    if ( inserted < 0 )
    {
      WdLogSingleEntry1(2);
      v10 = L"Failed to insert root registry key name into list for VmBusGetRegistryKeys (status = 0x%I64x).";
      WdLogGlobalForLineNumber = 6124;
LABEL_8:
      ResultLength = v8;
LABEL_9:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v10, ResultLength, 0, 0, 0, 0);
      goto LABEL_40;
    }
    while ( 2 )
    {
      if ( (_QWORD *)v27[0] != v27 )
      {
        v15 = DXG_REGISTRY_KEY_LIST::ReadNextPath((DXG_REGISTRY_KEY_LIST *)v27, &v26);
        v8 = v15;
        if ( v15 < 0 )
        {
          WdLogSingleEntry1(2);
          v22 = L"Failed to initialize subkey string for VmBusGetRegistryKeys (status = 0x%I64x).";
          WdLogGlobalForLineNumber = 6135;
        }
        else
        {
          ObjectAttributes.RootDirectory = DeviceRegKey;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &v26;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v16 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
          v8 = v16;
          if ( v16 < 0 )
          {
            WdLogSingleEntry1(2);
            v22 = L"Failed to open PnP registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).";
            WdLogGlobalForLineNumber = 6149;
          }
          else
          {
            v28 = 0;
            v17 = ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &v28);
            v8 = v17;
            if ( v17 >= 0 )
            {
              v18 = KeyInformation.MaxValueDataLen + 2 * (KeyInformation.MaxValueNameLen + 12);
              v30 = v18;
              v6 = (_DWORD *)operator new[](v18, 1265072196, 256);
              if ( v6 )
              {
                while ( v12 < KeyInformation.Values )
                {
                  if ( *v7 == 42 )
                  {
                    WdLogSingleEntry1(2);
                    WdLogGlobalForLineNumber = 6185;
                    v10 = L"Maximum number of KeyValues reached, aborting VmBusGetRegistryKeys (status = 0x%I64x).";
                    ResultLength = (unsigned int)v8;
                    goto LABEL_9;
                  }
                  memset(v6, 0, v18);
                  v29 = 0;
                  v19 = ZwEnumerateValueKey(KeyHandle, v12, KeyValueFullInformation, v6, v18, &v29);
                  v8 = v19;
                  if ( v19 < 0 )
                  {
                    WdLogSingleEntry1(2);
                    v10 = L"Failed to Enumerate Value for VmBusGetRegistryKeys (status = 0x%I64x).";
                    WdLogGlobalForLineNumber = 6201;
                    goto LABEL_8;
                  }
                  v20 = &v7[774 * *v7];
                  RtlStringCbCopyUnicodeString((unsigned __int16 *)v20 + 1028, 0x208u, &v26);
                  memmove(v20 + 644, v6 + 5, (unsigned int)v6[4]);
                  memmove(v20 + 2, (char *)v6 + (unsigned int)v6[2], (unsigned int)v6[3]);
                  v20[774] = v6[1];
                  v20[775] = v6[3];
                  ++*v7;
                  v18 = v30;
                  ++v12;
                }
                v12 = 0;
                if ( !KeyInformation.SubKeys && !KeyInformation.Values )
                {
                  RtlStringCbCopyUnicodeString((unsigned __int16 *)&v7[774 * *v7 + 514], 0x208u, &v26);
                  ++*v7;
                }
                appended = DXG_REGISTRY_KEY_LIST::AppendSubKeys(
                             (DXG_REGISTRY_KEY_LIST *)v27,
                             KeyHandle,
                             &KeyInformation,
                             &v26);
                v8 = appended;
                if ( appended >= 0 )
                {
                  CloseRegistrySubkey(KeyHandle);
                  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v6);
                  KeyHandle = 0;
                  continue;
                }
                WdLogSingleEntry1(2);
                v10 = L"Failed to Append SubKeys for VmBusGetRegistryKeys (status = 0x%I64x).";
                WdLogGlobalForLineNumber = 6227;
                goto LABEL_8;
              }
              LODWORD(v8) = -1073741801;
              WdLogSingleEntry0(6);
              WdLogGlobalForLineNumber = 6175;
              DxgkLogInternalTriageEvent(
                0,
                262145,
                -1,
                (unsigned int)L"Cannot allocate memory for KEY_VALUE_FULL_INFORMATION",
                6175,
                0,
                0,
                0,
                0);
LABEL_40:
              v5 = 130040;
              goto LABEL_41;
            }
            WdLogSingleEntry1(2);
            v22 = L"Failed to query key for VmBusGetRegistryKeys (status = 0x%I64x).";
            WdLogGlobalForLineNumber = 6164;
          }
        }
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v22, v8, 0, 0, 0, 0);
      }
      break;
    }
    v6 = 0;
    goto LABEL_40;
  }
LABEL_46:
  DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v33);
  return v2;
}

```

## disassembly

```asm
0x1402876b0  push    rbp
0x1402876b2  push    rbx
0x1402876b3  push    rsi
0x1402876b4  push    rdi
0x1402876b5  push    r12
0x1402876b7  push    r13
0x1402876b9  push    r14
0x1402876bb  push    r15
0x1402876bd  lea     rbp, [rsp-238h]
0x1402876c5  sub     rsp, 338h
0x1402876cc  mov     rax, cs:__security_cookie
0x1402876d3  xor     rax, rsp
0x1402876d6  mov     [rbp+270h+var_50], rax
0x1402876dd  mov     rdx, [rcx+50h]
0x1402876e1  mov     r12, rcx
0x1402876e4  add     rdx, 0F8h; struct DXGPUSHLOCK *
0x1402876eb  lea     rcx, [rbp+270h+var_2B0]; this
0x1402876ef  call    ??0DXGAUTOPUSHLOCKSHARED@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKSHARED::DXGAUTOPUSHLOCKSHARED(DXGPUSHLOCK * const)
0x1402876f4  mov     rax, [r12+50h]
0x1402876f9  xor     ebx, ebx
0x1402876fb  cmp     [rax+0ADh], bl
0x140287701  jnz     short loc_14028775D
0x140287703  lea     ecx, [rbx+2]
0x140287706  call    cs:__imp_WdLogSingleEntry0
0x14028770d  nop     dword ptr [rax+rax+00h]
0x140287712  mov     [rsp+370h+var_330], rbx
0x140287717  lea     r9, aTheAdapterIsAl; "The adapter is already closed by the gu"...
0x14028771e  mov     [rsp+370h+var_338], rbx
0x140287723  mov     eax, 17B1h
0x140287728  mov     [rsp+370h+var_340], rbx
0x14028772d  or      r8d, 0FFFFFFFFh
0x140287731  mov     [rsp+370h+var_348], rbx
0x140287736  mov     edx, 40000h
0x14028773b  xor     ecx, ecx
0x14028773d  mov     [rsp+370h+ResultLength], rax
0x140287742  mov     cs:WdLogGlobalForLineNumber, eax
0x140287748  call    DxgkLogInternalTriageEvent
0x14028774d  lea     rcx, [rbp+270h+var_2B0]; this
0x140287751  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x140287756  xor     al, al
0x140287758  jmp     loc_140287D90
0x14028775d  mov     rcx, r12
0x140287760  call    ??$CastToVmBusCommand@UDXGKVMB_COMMAND_GETREGISTRYKEYS@@@@YAPEAUDXGKVMB_COMMAND_GETREGISTRYKEYS@@PEAUDXGADAPTER_VMBUS_PACKET@@@Z; CastToVmBusCommand<DXGKVMB_COMMAND_GETREGISTRYKEYS>(DXGADAPTER_VMBUS_PACKET *)
0x140287765  mov     r13, rax
0x140287768  test    rax, rax
0x14028776b  jz      loc_140287D85
0x140287771  xorps   xmm0, xmm0
0x140287774  mov     [rbp+270h+DeviceRegKey], rbx
0x140287778  lea     rax, [rbp+270h+var_260]
0x14028777c  mov     [rsp+370h+KeyHandle], rbx
0x140287781  mov     [rsp+370h+var_318.Buffer], rax
0x140287786  mov     esi, 1FBF8h
0x14028778b  lea     rax, [rsp+370h+var_308]
0x140287790  mov     qword ptr [rsp+370h+var_318.Length], 2080000h
0x140287799  mov     [rsp+370h+var_300], rax
0x14028779e  mov     edx, 4B677844h
0x1402877a3  lea     rax, [rsp+370h+var_308]
0x1402877a8  mov     r8d, 40h ; '@'
0x1402877ae  mov     ecx, esi
0x1402877b0  mov     [rsp+370h+var_308], rax
0x1402877b5  movups  [rbp+270h+KeyInformation], xmm0
0x1402877b9  mov     r15, rbx
0x1402877bc  movups  [rbp+270h+var_288], xmm0
0x1402877c0  movups  [rbp+270h+var_278], xmm0
0x1402877c4  movups  xmmword ptr [rbp+270h+ObjectAttributes.Length], xmm0
0x1402877c8  movups  xmmword ptr [rbp+270h+ObjectAttributes.ObjectName], xmm0
0x1402877cc  movups  xmmword ptr [rbp+270h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402877d0  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1402877d5  mov     r14, rax
0x1402877d8  test    rax, rax
0x1402877db  jnz     short loc_140287834
0x1402877dd  mov     edi, 0C0000017h
0x1402877e2  lea     ecx, [rax+6]
0x1402877e5  call    cs:__imp_WdLogSingleEntry0
0x1402877ec  nop     dword ptr [rax+rax+00h]
0x1402877f1  xor     r13d, r13d
0x1402877f4  lea     r9, aCannotAllocate_4; "Cannot allocate memory for DXGKVMB_COMM"...
0x1402877fb  mov     [rsp+370h+var_330], r13
0x140287800  mov     eax, 17C5h
0x140287805  mov     [rsp+370h+var_338], r13
0x14028780a  or      r8d, 0FFFFFFFFh
0x14028780e  mov     [rsp+370h+var_340], r13
0x140287813  mov     edx, 40001h
0x140287818  mov     [rsp+370h+var_348], r13
0x14028781d  xor     ecx, ecx
0x14028781f  mov     [rsp+370h+ResultLength], rax
0x140287824  mov     cs:WdLogGlobalForLineNumber, eax
0x14028782a  call    DxgkLogInternalTriageEvent
0x14028782f  jmp     loc_140287D26
0x140287834  mov     rax, [r12+50h]
0x140287839  mov     rcx, [rax+10h]
0x14028783d  mov     rcx, [rcx+0D8h]; DeviceObject
0x140287844  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x14028784b  nop     dword ptr [rax+rax+00h]
0x140287850  mov     esi, 2
0x140287855  lea     r9, [rbp+270h+DeviceRegKey]; DeviceRegKey
0x140287859  mov     edx, esi; DevInstKeyType
0x14028785b  mov     rcx, rax; DeviceObject
0x14028785e  mov     r8d, 20019h; DesiredAccess
0x140287864  mov     rbx, rax
0x140287867  call    cs:__imp_IoOpenDeviceRegistryKey
0x14028786e  nop     dword ptr [rax+rax+00h]
0x140287873  mov     rcx, rbx; Object
0x140287876  movsxd  rdi, eax
0x140287879  call    cs:__imp_ObfDereferenceObject
0x140287880  nop     dword ptr [rax+rax+00h]
0x140287885  test    edi, edi
0x140287887  jns     short loc_1402878DC
0x140287889  mov     rdx, rdi
0x14028788c  mov     ecx, esi
0x14028788e  call    cs:__imp_WdLogSingleEntry1
0x140287895  nop     dword ptr [rax+rax+00h]
0x14028789a  lea     r9, aFailedToReadPn_0; "Failed to read PnP registry key name fo"...
0x1402878a1  mov     cs:WdLogGlobalForLineNumber, 17D3h
0x1402878ab  xor     r13d, r13d
0x1402878ae  mov     [rsp+370h+var_330], r13
0x1402878b3  mov     [rsp+370h+var_338], r13
0x1402878b8  mov     [rsp+370h+var_340], r13
0x1402878bd  mov     [rsp+370h+var_348], r13
0x1402878c2  mov     [rsp+370h+ResultLength], rdi
0x1402878c7  mov     edx, 40000h
0x1402878cc  or      r8d, 0FFFFFFFFh
0x1402878d0  xor     ecx, ecx
0x1402878d2  call    DxgkLogInternalTriageEvent
0x1402878d7  jmp     loc_140287D21
0x1402878dc  lea     rdx, [r13+18h]; unsigned __int16 *
0x1402878e0  lea     rcx, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x1402878e5  call    ?RtlUnicodeStringCopyString@@YAJPEAU_UNICODE_STRING@@PEBG@Z; RtlUnicodeStringCopyString(_UNICODE_STRING *,ushort const *)
0x1402878ea  xor     r13d, r13d
0x1402878ed  movsxd  rdi, eax
0x1402878f0  test    eax, eax
0x1402878f2  jns     short loc_140287918
0x1402878f4  mov     rdx, rdi
0x1402878f7  mov     ecx, esi
0x1402878f9  call    cs:__imp_WdLogSingleEntry1
0x140287900  nop     dword ptr [rax+rax+00h]
0x140287905  lea     r9, aFailedToCopyRo; "Failed to copy root registry key name f"...
0x14028790c  mov     cs:WdLogGlobalForLineNumber, 17DCh
0x140287916  jmp     short loc_1402878AE
0x140287918  lea     rdx, qword_140126320; unsigned __int16 *
0x14028791f  lea     rcx, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x140287924  call    ?RtlUnicodeStringCatString@@YAJPEAU_UNICODE_STRING@@PEBG@Z; RtlUnicodeStringCatString(_UNICODE_STRING *,ushort const *)
0x140287929  movsxd  rdi, eax
0x14028792c  test    eax, eax
0x14028792e  jns     short loc_140287957
0x140287930  mov     rdx, rdi
0x140287933  mov     ecx, esi
0x140287935  call    cs:__imp_WdLogSingleEntry1
0x14028793c  nop     dword ptr [rax+rax+00h]
0x140287941  lea     r9, aFailedToAppend_1; "Failed to append null char to CurrentRe"...
0x140287948  mov     cs:WdLogGlobalForLineNumber, 17E4h
0x140287952  jmp     loc_1402878AE
0x140287957  lea     rdx, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x14028795c  lea     rcx, [rsp+370h+var_308]; this
0x140287961  call    ?InsertHead@DXG_REGISTRY_KEY_LIST@@QEAAJPEAU_UNICODE_STRING@@@Z; DXG_REGISTRY_KEY_LIST::InsertHead(_UNICODE_STRING *)
0x140287966  movsxd  rdi, eax
0x140287969  test    eax, eax
0x14028796b  jns     short loc_140287994
0x14028796d  mov     rdx, rdi
0x140287970  mov     ecx, esi
0x140287972  call    cs:__imp_WdLogSingleEntry1
0x140287979  nop     dword ptr [rax+rax+00h]
0x14028797e  lea     r9, aFailedToInsert_3; "Failed to insert root registry key name"...
0x140287985  mov     cs:WdLogGlobalForLineNumber, 17ECh
0x14028798f  jmp     loc_1402878AE
0x140287994  lea     rax, [rsp+370h+var_308]
0x140287999  cmp     [rsp+370h+var_308], rax
0x14028799e  jz      loc_140287D1E
0x1402879a4  lea     rdx, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x1402879a9  lea     rcx, [rsp+370h+var_308]; this
0x1402879ae  call    ?ReadNextPath@DXG_REGISTRY_KEY_LIST@@QEAAJPEAU_UNICODE_STRING@@@Z; DXG_REGISTRY_KEY_LIST::ReadNextPath(_UNICODE_STRING *)
0x1402879b3  movsxd  rdi, eax
0x1402879b6  test    eax, eax
0x1402879b8  js      loc_140287CD3
0x1402879be  mov     rax, [rbp+270h+DeviceRegKey]
0x1402879c2  lea     r8, [rbp+270h+ObjectAttributes]; ObjectAttributes
0x1402879c6  mov     [rbp+270h+ObjectAttributes.RootDirectory], rax
0x1402879ca  lea     rcx, [rsp+370h+KeyHandle]; KeyHandle
0x1402879cf  lea     rax, [rsp+370h+var_318]
0x1402879d4  mov     [rbp+270h+ObjectAttributes.Length], 30h ; '0'
0x1402879db  xorps   xmm0, xmm0
0x1402879de  mov     [rbp+270h+ObjectAttributes.ObjectName], rax
0x1402879e2  mov     edx, 20019h; DesiredAccess
0x1402879e7  mov     [rbp+270h+ObjectAttributes.Attributes], 240h
0x1402879ee  movdqu  xmmword ptr [rbp+270h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402879f3  call    cs:__imp_ZwOpenKey
0x1402879fa  nop     dword ptr [rax+rax+00h]
0x1402879ff  movsxd  rdi, eax
0x140287a02  test    eax, eax
0x140287a04  js      loc_140287CAF
0x140287a0a  mov     rcx, [rsp+370h+KeyHandle]; KeyHandle
0x140287a0f  lea     rax, [rsp+370h+var_2F8]
0x140287a14  mov     r9d, 30h ; '0'; Length
0x140287a1a  mov     [rsp+370h+ResultLength], rax; ResultLength
0x140287a1f  lea     r8, [rbp+270h+KeyInformation]; KeyInformation
0x140287a23  mov     [rsp+370h+var_2F8], r13d
0x140287a28  mov     edx, esi; KeyInformationClass
0x140287a2a  call    cs:__imp_ZwQueryKey
0x140287a31  nop     dword ptr [rax+rax+00h]
0x140287a36  movsxd  rdi, eax
0x140287a39  test    eax, eax
0x140287a3b  js      loc_140287C8B
0x140287a41  mov     ecx, dword ptr [rbp+270h+var_278+8]
0x140287a44  mov     edx, 4B677844h
0x140287a49  mov     eax, dword ptr [rbp+270h+var_278+4]
0x140287a4c  mov     r8d, 100h
0x140287a52  add     eax, 0Ch
0x140287a55  lea     ebx, [rcx+rax*2]
0x140287a58  mov     ecx, ebx
0x140287a5a  mov     [rbp+270h+var_2F0], ebx
0x140287a5d  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140287a62  mov     r15, rax
0x140287a65  test    rax, rax
0x140287a68  jz      loc_140287C40
0x140287a6e  mov     eax, dword ptr [rbp+270h+var_278]
0x140287a71  cmp     r13d, eax
0x140287a74  jnb     loc_140287B3C
0x140287a7a  cmp     dword ptr [r14], 2Ah ; '*'
0x140287a7e  jz      loc_140287BD5
0x140287a84  mov     r8d, ebx; Size
0x140287a87  xor     edx, edx; Val
0x140287a89  mov     rcx, r15; void *
0x140287a8c  call    memset
0x140287a91  mov     rcx, [rsp+370h+KeyHandle]; KeyHandle
0x140287a96  lea     rax, [rsp+370h+var_2F4]
0x140287a9b  mov     [rsp+370h+var_348], rax; ResultLength
0x140287aa0  mov     r9, r15; KeyValueInformation
0x140287aa3  mov     r8d, 1; KeyValueInformationClass
0x140287aa9  mov     dword ptr [rsp+370h+ResultLength], ebx; Length
0x140287aad  mov     edx, r13d; Index
0x140287ab0  mov     [rsp+370h+var_2F4], 0
0x140287ab8  call    cs:__imp_ZwEnumerateValueKey
0x140287abf  nop     dword ptr [rax+rax+00h]
0x140287ac4  movsxd  rdi, eax
0x140287ac7  test    eax, eax
0x140287ac9  js      loc_140287BAE
0x140287acf  mov     eax, [r14]
0x140287ad2  lea     r8, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x140287ad7  imul    rbx, rax, 0C18h
0x140287ade  mov     edx, 208h; unsigned __int64
0x140287ae3  add     rbx, r14
0x140287ae6  lea     rcx, [rbx+808h]; unsigned __int16 *
0x140287aed  call    ?RtlStringCbCopyUnicodeString@@YAJPEAG_KPEBU_UNICODE_STRING@@@Z; RtlStringCbCopyUnicodeString(ushort *,unsigned __int64,_UNICODE_STRING const *)
0x140287af2  mov     r8d, [r15+10h]; Size
0x140287af6  lea     rdx, [r15+14h]; Src
0x140287afa  lea     rcx, [rbx+0A10h]; void *
0x140287b01  call    memmove
0x140287b06  mov     edx, [r15+8]
0x140287b0a  lea     rcx, [rbx+8]; void *
0x140287b0e  mov     r8d, [r15+0Ch]; Size
0x140287b12  add     rdx, r15; Src
0x140287b15  call    memmove
0x140287b1a  mov     eax, [r15+4]
0x140287b1e  mov     [rbx+0C18h], eax
0x140287b24  mov     eax, [r15+0Ch]
0x140287b28  mov     [rbx+0C1Ch], eax
0x140287b2e  inc     dword ptr [r14]
0x140287b31  mov     ebx, [rbp+270h+var_2F0]
0x140287b34  inc     r13d
0x140287b37  jmp     loc_140287A6E
0x140287b3c  xor     r13d, r13d
0x140287b3f  cmp     dword ptr [rbp+270h+var_288+4], r13d
0x140287b43  jnz     short loc_140287B6F
0x140287b45  test    eax, eax
0x140287b47  jnz     short loc_140287B6F
0x140287b49  mov     eax, [r14]
0x140287b4c  lea     r8, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x140287b51  imul    rcx, rax, 0C18h
0x140287b58  mov     edx, 208h; unsigned __int64
0x140287b5d  add     rcx, 808h
0x140287b64  add     rcx, r14; unsigned __int16 *
0x140287b67  call    ?RtlStringCbCopyUnicodeString@@YAJPEAG_KPEBU_UNICODE_STRING@@@Z; RtlStringCbCopyUnicodeString(ushort *,unsigned __int64,_UNICODE_STRING const *)
0x140287b6c  inc     dword ptr [r14]
0x140287b6f  mov     rdx, [rsp+370h+KeyHandle]; void *
0x140287b74  lea     r9, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x140287b79  lea     r8, [rbp+270h+KeyInformation]; struct _KEY_FULL_INFORMATION *
0x140287b7d  lea     rcx, [rsp+370h+var_308]; this
0x140287b82  call    ?AppendSubKeys@DXG_REGISTRY_KEY_LIST@@QEAAJPEAXPEAU_KEY_FULL_INFORMATION@@PEAU_UNICODE_STRING@@@Z; DXG_REGISTRY_KEY_LIST::AppendSubKeys(void *,_KEY_FULL_INFORMATION *,_UNICODE_STRING *)
0x140287b87  movsxd  rdi, eax
0x140287b8a  test    eax, eax
0x140287b8c  js      loc_140287C19
0x140287b92  mov     rcx, [rsp+370h+KeyHandle]; void *
0x140287b97  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x140287b9c  mov     rcx, r15; void *
0x140287b9f  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x140287ba4  mov     [rsp+370h+KeyHandle], r13
0x140287ba9  jmp     loc_140287994
0x140287bae  mov     rdx, rdi
0x140287bb1  mov     ecx, esi
0x140287bb3  call    cs:__imp_WdLogSingleEntry1
0x140287bba  nop     dword ptr [rax+rax+00h]
0x140287bbf  lea     r9, aFailedToEnumer_4; "Failed to Enumerate Value for VmBusGetR"...
0x140287bc6  mov     cs:WdLogGlobalForLineNumber, 1839h
0x140287bd0  jmp     loc_1402878AB
0x140287bd5  mov     edx, edi
0x140287bd7  mov     ecx, esi
0x140287bd9  mov     ebx, edi
0x140287bdb  call    cs:__imp_WdLogSingleEntry1
0x140287be2  nop     dword ptr [rax+rax+00h]
0x140287be7  xor     r13d, r13d
  ... truncated ...
```
