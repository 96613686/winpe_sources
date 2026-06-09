# DXG_HOST_VIRTUALGPU_VMBUS::VmBusGetRegistryKeys(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x14028e2c0`
- end: `0x14028e9c4`
- name: `?VmBusGetRegistryKeys@DXG_HOST_VIRTUALGPU_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `1796`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001e508`
- `0x1400493a8`
- `0x14005d190`
- `0x1400686b8`
- `0x140073598`
- `0x14007e0a4`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140237640`
- `0x140237684`
- `0x140239268`
- `0x1402399fc`
- `0x14028e2c0`
- `0x1403dc814`

## import_xrefs

- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14028e454`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14028e454`
- `ntoskrnl!ObfDereferenceObject` at `0x14028e489`
- `ntoskrnl!ObfDereferenceObject` at `0x14028e489`
- `ntoskrnl!ZwOpenKey` at `0x14028e603`
- `ntoskrnl!ZwOpenKey` at `0x14028e603`
- `ntoskrnl!ZwQueryKey` at `0x14028e63a`
- `ntoskrnl!ZwQueryKey` at `0x14028e63a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14028e6c8`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14028e6c8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14028e477`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14028e477`
- `watchdog!WdLogSingleEntry0` at `0x14028e316`
- `watchdog!WdLogSingleEntry0` at `0x14028e3f5`
- `watchdog!WdLogSingleEntry0` at `0x14028e85a`
- `watchdog!WdLogSingleEntry0` at `0x14028e316`
- `watchdog!WdLogSingleEntry0` at `0x14028e3f5`
- `watchdog!WdLogSingleEntry0` at `0x14028e85a`
- `watchdog!WdLogSingleEntry1` at `0x14028e49e`
- `watchdog!WdLogSingleEntry1` at `0x14028e509`
- `watchdog!WdLogSingleEntry1` at `0x14028e545`
- `watchdog!WdLogSingleEntry1` at `0x14028e582`
- `watchdog!WdLogSingleEntry1` at `0x14028e7c3`
- `watchdog!WdLogSingleEntry1` at `0x14028e7eb`
- `watchdog!WdLogSingleEntry1` at `0x14028e82e`
- `watchdog!WdLogSingleEntry1` at `0x14028e8a0`
- `watchdog!WdLogSingleEntry1` at `0x14028e8c4`
- `watchdog!WdLogSingleEntry1` at `0x14028e8e8`
- `watchdog!WdLogSingleEntry1` at `0x14028e49e`
- `watchdog!WdLogSingleEntry1` at `0x14028e509`
- `watchdog!WdLogSingleEntry1` at `0x14028e545`
- `watchdog!WdLogSingleEntry1` at `0x14028e582`
- `watchdog!WdLogSingleEntry1` at `0x14028e7c3`
- `watchdog!WdLogSingleEntry1` at `0x14028e7eb`
- `watchdog!WdLogSingleEntry1` at `0x14028e82e`
- `watchdog!WdLogSingleEntry1` at `0x14028e8a0`
- `watchdog!WdLogSingleEntry1` at `0x14028e8c4`
- `watchdog!WdLogSingleEntry1` at `0x14028e8e8`

## string_xrefs

- `0x14028e8ac`: `Failed to query key for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e327`: `The adapter is already closed by the guest`
- `0x14028e404`: `Cannot allocate memory for DXGKVMB_COMMAND_GETREGISTRYKEYS_RETURN`
- `0x14028e515`: `Failed to copy root registry key name for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e4aa`: `Failed to read PnP registry key name for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e551`: `Failed to append null char to CurrentRegistryPath for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e8f4`: `Failed to initialize subkey string for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e58e`: `Failed to insert root registry key name into list for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e8d0`: `Failed to open PnP registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e7cf`: `Failed to Enumerate Value for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e809`: `Maximum number of KeyValues reached, aborting VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028e83a`: `Failed to Append SubKeys for VmBusGetRegistryKeys (status = 0x%I64x).`

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
    WdLogGlobalForLineNumber = 6063;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"The adapter is already closed by the guest",
      6063,
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
      WdLogGlobalForLineNumber = 6083;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Cannot allocate memory for DXGKVMB_COMMAND_GETREGISTRYKEYS_RETURN",
        6083,
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
      WdLogGlobalForLineNumber = 6097;
      goto LABEL_8;
    }
    v11 = RtlUnicodeStringCopyString(&v26, (const unsigned __int16 *)(v4 + 24));
    v12 = 0;
    v8 = v11;
    if ( v11 < 0 )
    {
      WdLogSingleEntry1(2);
      v10 = L"Failed to copy root registry key name for VmBusGetRegistryKeys (status = 0x%I64x).";
      WdLogGlobalForLineNumber = 6106;
      goto LABEL_8;
    }
    v13 = RtlUnicodeStringCatString(&v26, &qword_1401294D0);
    v8 = v13;
    if ( v13 < 0 )
    {
      WdLogSingleEntry1(2);
      v10 = L"Failed to append null char to CurrentRegistryPath for VmBusGetRegistryKeys (status = 0x%I64x).";
      WdLogGlobalForLineNumber = 6114;
      goto LABEL_8;
    }
    inserted = DXG_REGISTRY_KEY_LIST::InsertHead((DXG_REGISTRY_KEY_LIST *)v27, &v26);
    v8 = inserted;
    if ( inserted < 0 )
    {
      WdLogSingleEntry1(2);
      v10 = L"Failed to insert root registry key name into list for VmBusGetRegistryKeys (status = 0x%I64x).";
      WdLogGlobalForLineNumber = 6122;
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
          WdLogGlobalForLineNumber = 6133;
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
            WdLogGlobalForLineNumber = 6147;
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
                    WdLogGlobalForLineNumber = 6183;
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
                    WdLogGlobalForLineNumber = 6199;
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
                WdLogGlobalForLineNumber = 6225;
                goto LABEL_8;
              }
              LODWORD(v8) = -1073741801;
              WdLogSingleEntry0(6);
              WdLogGlobalForLineNumber = 6173;
              DxgkLogInternalTriageEvent(
                0,
                262145,
                -1,
                (unsigned int)L"Cannot allocate memory for KEY_VALUE_FULL_INFORMATION",
                6173,
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
            WdLogGlobalForLineNumber = 6162;
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
0x14028e2c0  push    rbp
0x14028e2c2  push    rbx
0x14028e2c3  push    rsi
0x14028e2c4  push    rdi
0x14028e2c5  push    r12
0x14028e2c7  push    r13
0x14028e2c9  push    r14
0x14028e2cb  push    r15
0x14028e2cd  lea     rbp, [rsp-238h]
0x14028e2d5  sub     rsp, 338h
0x14028e2dc  mov     rax, cs:__security_cookie
0x14028e2e3  xor     rax, rsp
0x14028e2e6  mov     [rbp+270h+var_50], rax
0x14028e2ed  mov     rdx, [rcx+50h]
0x14028e2f1  mov     r12, rcx
0x14028e2f4  add     rdx, 0F8h; struct DXGPUSHLOCK *
0x14028e2fb  lea     rcx, [rbp+270h+var_2B0]; this
0x14028e2ff  call    ??0DXGAUTOPUSHLOCKSHARED@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKSHARED::DXGAUTOPUSHLOCKSHARED(DXGPUSHLOCK * const)
0x14028e304  mov     rax, [r12+50h]
0x14028e309  xor     ebx, ebx
0x14028e30b  cmp     [rax+0ADh], bl
0x14028e311  jnz     short loc_14028E36D
0x14028e313  lea     ecx, [rbx+2]
0x14028e316  call    cs:__imp_WdLogSingleEntry0
0x14028e31d  nop     dword ptr [rax+rax+00h]
0x14028e322  mov     [rsp+370h+var_330], rbx
0x14028e327  lea     r9, aTheAdapterIsAl; "The adapter is already closed by the gu"...
0x14028e32e  mov     [rsp+370h+var_338], rbx
0x14028e333  mov     eax, 17AFh
0x14028e338  mov     [rsp+370h+var_340], rbx
0x14028e33d  or      r8d, 0FFFFFFFFh
0x14028e341  mov     [rsp+370h+var_348], rbx
0x14028e346  mov     edx, 40000h
0x14028e34b  xor     ecx, ecx
0x14028e34d  mov     [rsp+370h+ResultLength], rax
0x14028e352  mov     cs:WdLogGlobalForLineNumber, eax
0x14028e358  call    DxgkLogInternalTriageEvent
0x14028e35d  lea     rcx, [rbp+270h+var_2B0]; this
0x14028e361  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x14028e366  xor     al, al
0x14028e368  jmp     loc_14028E9A0
0x14028e36d  mov     rcx, r12
0x14028e370  call    ??$CastToVmBusCommand@UDXGKVMB_COMMAND_GETREGISTRYKEYS@@@@YAPEAUDXGKVMB_COMMAND_GETREGISTRYKEYS@@PEAUDXGADAPTER_VMBUS_PACKET@@@Z; CastToVmBusCommand<DXGKVMB_COMMAND_GETREGISTRYKEYS>(DXGADAPTER_VMBUS_PACKET *)
0x14028e375  mov     r13, rax
0x14028e378  test    rax, rax
0x14028e37b  jz      loc_14028E995
0x14028e381  xorps   xmm0, xmm0
0x14028e384  mov     [rbp+270h+DeviceRegKey], rbx
0x14028e388  lea     rax, [rbp+270h+var_260]
0x14028e38c  mov     [rsp+370h+KeyHandle], rbx
0x14028e391  mov     [rsp+370h+var_318.Buffer], rax
0x14028e396  mov     esi, 1FBF8h
0x14028e39b  lea     rax, [rsp+370h+var_308]
0x14028e3a0  mov     qword ptr [rsp+370h+var_318.Length], 2080000h
0x14028e3a9  mov     [rsp+370h+var_300], rax
0x14028e3ae  mov     edx, 4B677844h
0x14028e3b3  lea     rax, [rsp+370h+var_308]
0x14028e3b8  mov     r8d, 40h ; '@'
0x14028e3be  mov     ecx, esi
0x14028e3c0  mov     [rsp+370h+var_308], rax
0x14028e3c5  movups  [rbp+270h+KeyInformation], xmm0
0x14028e3c9  mov     r15, rbx
0x14028e3cc  movups  [rbp+270h+var_288], xmm0
0x14028e3d0  movups  [rbp+270h+var_278], xmm0
0x14028e3d4  movups  xmmword ptr [rbp+270h+ObjectAttributes.Length], xmm0
0x14028e3d8  movups  xmmword ptr [rbp+270h+ObjectAttributes.ObjectName], xmm0
0x14028e3dc  movups  xmmword ptr [rbp+270h+ObjectAttributes.SecurityDescriptor], xmm0
0x14028e3e0  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14028e3e5  mov     r14, rax
0x14028e3e8  test    rax, rax
0x14028e3eb  jnz     short loc_14028E444
0x14028e3ed  mov     edi, 0C0000017h
0x14028e3f2  lea     ecx, [rax+6]
0x14028e3f5  call    cs:__imp_WdLogSingleEntry0
0x14028e3fc  nop     dword ptr [rax+rax+00h]
0x14028e401  xor     r13d, r13d
0x14028e404  lea     r9, aCannotAllocate_4; "Cannot allocate memory for DXGKVMB_COMM"...
0x14028e40b  mov     [rsp+370h+var_330], r13
0x14028e410  mov     eax, 17C3h
0x14028e415  mov     [rsp+370h+var_338], r13
0x14028e41a  or      r8d, 0FFFFFFFFh
0x14028e41e  mov     [rsp+370h+var_340], r13
0x14028e423  mov     edx, 40001h
0x14028e428  mov     [rsp+370h+var_348], r13
0x14028e42d  xor     ecx, ecx
0x14028e42f  mov     [rsp+370h+ResultLength], rax
0x14028e434  mov     cs:WdLogGlobalForLineNumber, eax
0x14028e43a  call    DxgkLogInternalTriageEvent
0x14028e43f  jmp     loc_14028E936
0x14028e444  mov     rax, [r12+50h]
0x14028e449  mov     rcx, [rax+10h]
0x14028e44d  mov     rcx, [rcx+0D8h]; DeviceObject
0x14028e454  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x14028e45b  nop     dword ptr [rax+rax+00h]
0x14028e460  mov     esi, 2
0x14028e465  lea     r9, [rbp+270h+DeviceRegKey]; DeviceRegKey
0x14028e469  mov     edx, esi; DevInstKeyType
0x14028e46b  mov     rcx, rax; DeviceObject
0x14028e46e  mov     r8d, 20019h; DesiredAccess
0x14028e474  mov     rbx, rax
0x14028e477  call    cs:__imp_IoOpenDeviceRegistryKey
0x14028e47e  nop     dword ptr [rax+rax+00h]
0x14028e483  mov     rcx, rbx; Object
0x14028e486  movsxd  rdi, eax
0x14028e489  call    cs:__imp_ObfDereferenceObject
0x14028e490  nop     dword ptr [rax+rax+00h]
0x14028e495  test    edi, edi
0x14028e497  jns     short loc_14028E4EC
0x14028e499  mov     rdx, rdi
0x14028e49c  mov     ecx, esi
0x14028e49e  call    cs:__imp_WdLogSingleEntry1
0x14028e4a5  nop     dword ptr [rax+rax+00h]
0x14028e4aa  lea     r9, aFailedToReadPn_0; "Failed to read PnP registry key name fo"...
0x14028e4b1  mov     cs:WdLogGlobalForLineNumber, 17D1h
0x14028e4bb  xor     r13d, r13d
0x14028e4be  mov     [rsp+370h+var_330], r13
0x14028e4c3  mov     [rsp+370h+var_338], r13
0x14028e4c8  mov     [rsp+370h+var_340], r13
0x14028e4cd  mov     [rsp+370h+var_348], r13
0x14028e4d2  mov     [rsp+370h+ResultLength], rdi
0x14028e4d7  mov     edx, 40000h
0x14028e4dc  or      r8d, 0FFFFFFFFh
0x14028e4e0  xor     ecx, ecx
0x14028e4e2  call    DxgkLogInternalTriageEvent
0x14028e4e7  jmp     loc_14028E931
0x14028e4ec  lea     rdx, [r13+18h]; unsigned __int16 *
0x14028e4f0  lea     rcx, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x14028e4f5  call    ?RtlUnicodeStringCopyString@@YAJPEAU_UNICODE_STRING@@PEBG@Z; RtlUnicodeStringCopyString(_UNICODE_STRING *,ushort const *)
0x14028e4fa  xor     r13d, r13d
0x14028e4fd  movsxd  rdi, eax
0x14028e500  test    eax, eax
0x14028e502  jns     short loc_14028E528
0x14028e504  mov     rdx, rdi
0x14028e507  mov     ecx, esi
0x14028e509  call    cs:__imp_WdLogSingleEntry1
0x14028e510  nop     dword ptr [rax+rax+00h]
0x14028e515  lea     r9, aFailedToCopyRo; "Failed to copy root registry key name f"...
0x14028e51c  mov     cs:WdLogGlobalForLineNumber, 17DAh
0x14028e526  jmp     short loc_14028E4BE
0x14028e528  lea     rdx, qword_1401294D0; unsigned __int16 *
0x14028e52f  lea     rcx, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x14028e534  call    ?RtlUnicodeStringCatString@@YAJPEAU_UNICODE_STRING@@PEBG@Z; RtlUnicodeStringCatString(_UNICODE_STRING *,ushort const *)
0x14028e539  movsxd  rdi, eax
0x14028e53c  test    eax, eax
0x14028e53e  jns     short loc_14028E567
0x14028e540  mov     rdx, rdi
0x14028e543  mov     ecx, esi
0x14028e545  call    cs:__imp_WdLogSingleEntry1
0x14028e54c  nop     dword ptr [rax+rax+00h]
0x14028e551  lea     r9, aFailedToAppend_1; "Failed to append null char to CurrentRe"...
0x14028e558  mov     cs:WdLogGlobalForLineNumber, 17E2h
0x14028e562  jmp     loc_14028E4BE
0x14028e567  lea     rdx, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x14028e56c  lea     rcx, [rsp+370h+var_308]; this
0x14028e571  call    ?InsertHead@DXG_REGISTRY_KEY_LIST@@QEAAJPEAU_UNICODE_STRING@@@Z; DXG_REGISTRY_KEY_LIST::InsertHead(_UNICODE_STRING *)
0x14028e576  movsxd  rdi, eax
0x14028e579  test    eax, eax
0x14028e57b  jns     short loc_14028E5A4
0x14028e57d  mov     rdx, rdi
0x14028e580  mov     ecx, esi
0x14028e582  call    cs:__imp_WdLogSingleEntry1
0x14028e589  nop     dword ptr [rax+rax+00h]
0x14028e58e  lea     r9, aFailedToInsert_3; "Failed to insert root registry key name"...
0x14028e595  mov     cs:WdLogGlobalForLineNumber, 17EAh
0x14028e59f  jmp     loc_14028E4BE
0x14028e5a4  lea     rax, [rsp+370h+var_308]
0x14028e5a9  cmp     [rsp+370h+var_308], rax
0x14028e5ae  jz      loc_14028E92E
0x14028e5b4  lea     rdx, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x14028e5b9  lea     rcx, [rsp+370h+var_308]; this
0x14028e5be  call    ?ReadNextPath@DXG_REGISTRY_KEY_LIST@@QEAAJPEAU_UNICODE_STRING@@@Z; DXG_REGISTRY_KEY_LIST::ReadNextPath(_UNICODE_STRING *)
0x14028e5c3  movsxd  rdi, eax
0x14028e5c6  test    eax, eax
0x14028e5c8  js      loc_14028E8E3
0x14028e5ce  mov     rax, [rbp+270h+DeviceRegKey]
0x14028e5d2  lea     r8, [rbp+270h+ObjectAttributes]; ObjectAttributes
0x14028e5d6  mov     [rbp+270h+ObjectAttributes.RootDirectory], rax
0x14028e5da  lea     rcx, [rsp+370h+KeyHandle]; KeyHandle
0x14028e5df  lea     rax, [rsp+370h+var_318]
0x14028e5e4  mov     [rbp+270h+ObjectAttributes.Length], 30h ; '0'
0x14028e5eb  xorps   xmm0, xmm0
0x14028e5ee  mov     [rbp+270h+ObjectAttributes.ObjectName], rax
0x14028e5f2  mov     edx, 20019h; DesiredAccess
0x14028e5f7  mov     [rbp+270h+ObjectAttributes.Attributes], 240h
0x14028e5fe  movdqu  xmmword ptr [rbp+270h+ObjectAttributes.SecurityDescriptor], xmm0
0x14028e603  call    cs:__imp_ZwOpenKey
0x14028e60a  nop     dword ptr [rax+rax+00h]
0x14028e60f  movsxd  rdi, eax
0x14028e612  test    eax, eax
0x14028e614  js      loc_14028E8BF
0x14028e61a  mov     rcx, [rsp+370h+KeyHandle]; KeyHandle
0x14028e61f  lea     rax, [rsp+370h+var_2F8]
0x14028e624  mov     r9d, 30h ; '0'; Length
0x14028e62a  mov     [rsp+370h+ResultLength], rax; ResultLength
0x14028e62f  lea     r8, [rbp+270h+KeyInformation]; KeyInformation
0x14028e633  mov     [rsp+370h+var_2F8], r13d
0x14028e638  mov     edx, esi; KeyInformationClass
0x14028e63a  call    cs:__imp_ZwQueryKey
0x14028e641  nop     dword ptr [rax+rax+00h]
0x14028e646  movsxd  rdi, eax
0x14028e649  test    eax, eax
0x14028e64b  js      loc_14028E89B
0x14028e651  mov     ecx, dword ptr [rbp+270h+var_278+8]
0x14028e654  mov     edx, 4B677844h
0x14028e659  mov     eax, dword ptr [rbp+270h+var_278+4]
0x14028e65c  mov     r8d, 100h
0x14028e662  add     eax, 0Ch
0x14028e665  lea     ebx, [rcx+rax*2]
0x14028e668  mov     ecx, ebx
0x14028e66a  mov     [rbp+270h+var_2F0], ebx
0x14028e66d  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14028e672  mov     r15, rax
0x14028e675  test    rax, rax
0x14028e678  jz      loc_14028E850
0x14028e67e  mov     eax, dword ptr [rbp+270h+var_278]
0x14028e681  cmp     r13d, eax
0x14028e684  jnb     loc_14028E74C
0x14028e68a  cmp     dword ptr [r14], 2Ah ; '*'
0x14028e68e  jz      loc_14028E7E5
0x14028e694  mov     r8d, ebx; Size
0x14028e697  xor     edx, edx; Val
0x14028e699  mov     rcx, r15; void *
0x14028e69c  call    memset
0x14028e6a1  mov     rcx, [rsp+370h+KeyHandle]; KeyHandle
0x14028e6a6  lea     rax, [rsp+370h+var_2F4]
0x14028e6ab  mov     [rsp+370h+var_348], rax; ResultLength
0x14028e6b0  mov     r9, r15; KeyValueInformation
0x14028e6b3  mov     r8d, 1; KeyValueInformationClass
0x14028e6b9  mov     dword ptr [rsp+370h+ResultLength], ebx; Length
0x14028e6bd  mov     edx, r13d; Index
0x14028e6c0  mov     [rsp+370h+var_2F4], 0
0x14028e6c8  call    cs:__imp_ZwEnumerateValueKey
0x14028e6cf  nop     dword ptr [rax+rax+00h]
0x14028e6d4  movsxd  rdi, eax
0x14028e6d7  test    eax, eax
0x14028e6d9  js      loc_14028E7BE
0x14028e6df  mov     eax, [r14]
0x14028e6e2  lea     r8, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x14028e6e7  imul    rbx, rax, 0C18h
0x14028e6ee  mov     edx, 208h; unsigned __int64
0x14028e6f3  add     rbx, r14
0x14028e6f6  lea     rcx, [rbx+808h]; unsigned __int16 *
0x14028e6fd  call    ?RtlStringCbCopyUnicodeString@@YAJPEAG_KPEBU_UNICODE_STRING@@@Z; RtlStringCbCopyUnicodeString(ushort *,unsigned __int64,_UNICODE_STRING const *)
0x14028e702  mov     r8d, [r15+10h]; Size
0x14028e706  lea     rdx, [r15+14h]; Src
0x14028e70a  lea     rcx, [rbx+0A10h]; void *
0x14028e711  call    memmove
0x14028e716  mov     edx, [r15+8]
0x14028e71a  lea     rcx, [rbx+8]; void *
0x14028e71e  mov     r8d, [r15+0Ch]; Size
0x14028e722  add     rdx, r15; Src
0x14028e725  call    memmove
0x14028e72a  mov     eax, [r15+4]
0x14028e72e  mov     [rbx+0C18h], eax
0x14028e734  mov     eax, [r15+0Ch]
0x14028e738  mov     [rbx+0C1Ch], eax
0x14028e73e  inc     dword ptr [r14]
0x14028e741  mov     ebx, [rbp+270h+var_2F0]
0x14028e744  inc     r13d
0x14028e747  jmp     loc_14028E67E
0x14028e74c  xor     r13d, r13d
0x14028e74f  cmp     dword ptr [rbp+270h+var_288+4], r13d
0x14028e753  jnz     short loc_14028E77F
0x14028e755  test    eax, eax
0x14028e757  jnz     short loc_14028E77F
0x14028e759  mov     eax, [r14]
0x14028e75c  lea     r8, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x14028e761  imul    rcx, rax, 0C18h
0x14028e768  mov     edx, 208h; unsigned __int64
0x14028e76d  add     rcx, 808h
0x14028e774  add     rcx, r14; unsigned __int16 *
0x14028e777  call    ?RtlStringCbCopyUnicodeString@@YAJPEAG_KPEBU_UNICODE_STRING@@@Z; RtlStringCbCopyUnicodeString(ushort *,unsigned __int64,_UNICODE_STRING const *)
0x14028e77c  inc     dword ptr [r14]
0x14028e77f  mov     rdx, [rsp+370h+KeyHandle]; void *
0x14028e784  lea     r9, [rsp+370h+var_318]; struct _UNICODE_STRING *
0x14028e789  lea     r8, [rbp+270h+KeyInformation]; struct _KEY_FULL_INFORMATION *
0x14028e78d  lea     rcx, [rsp+370h+var_308]; this
0x14028e792  call    ?AppendSubKeys@DXG_REGISTRY_KEY_LIST@@QEAAJPEAXPEAU_KEY_FULL_INFORMATION@@PEAU_UNICODE_STRING@@@Z; DXG_REGISTRY_KEY_LIST::AppendSubKeys(void *,_KEY_FULL_INFORMATION *,_UNICODE_STRING *)
0x14028e797  movsxd  rdi, eax
0x14028e79a  test    eax, eax
0x14028e79c  js      loc_14028E829
0x14028e7a2  mov     rcx, [rsp+370h+KeyHandle]; void *
0x14028e7a7  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x14028e7ac  mov     rcx, r15; void *
0x14028e7af  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14028e7b4  mov     [rsp+370h+KeyHandle], r13
0x14028e7b9  jmp     loc_14028E5A4
0x14028e7be  mov     rdx, rdi
0x14028e7c1  mov     ecx, esi
0x14028e7c3  call    cs:__imp_WdLogSingleEntry1
0x14028e7ca  nop     dword ptr [rax+rax+00h]
0x14028e7cf  lea     r9, aFailedToEnumer_4; "Failed to Enumerate Value for VmBusGetR"...
0x14028e7d6  mov     cs:WdLogGlobalForLineNumber, 1837h
0x14028e7e0  jmp     loc_14028E4BB
0x14028e7e5  mov     edx, edi
0x14028e7e7  mov     ecx, esi
0x14028e7e9  mov     ebx, edi
0x14028e7eb  call    cs:__imp_WdLogSingleEntry1
0x14028e7f2  nop     dword ptr [rax+rax+00h]
0x14028e7f7  xor     r13d, r13d
  ... truncated ...
```
