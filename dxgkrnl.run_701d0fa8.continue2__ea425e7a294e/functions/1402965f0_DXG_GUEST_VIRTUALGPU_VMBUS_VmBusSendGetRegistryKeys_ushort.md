# DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendGetRegistryKeys(ushort *)

- ea: `0x1402965f0`
- end: `0x140296d31`
- name: `?VmBusSendGetRegistryKeys@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAG@Z`
- size: `1857`
- prototype: `__int64 __fastcall(DXG_GUEST_VIRTUALGPU_VMBUS *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1401e86a4`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001b9c0`
- `0x14002e2e0`
- `0x14002eec0`
- `0x140062800`
- `0x1400734c8`
- `0x14007e3d0`
- `0x14007f9ec`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x14020cd94`
- `0x14020cf2c`
- `0x1402965f0`
- `0x1402994b4`
- `0x14035f600`
- `0x1403dc814`
- `0x140401848`

## import_xrefs

- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1402968b7`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1402968b7`
- `ntoskrnl!ObfDereferenceObject` at `0x1402968da`
- `ntoskrnl!ObfDereferenceObject` at `0x1402968da`
- `ntoskrnl!RtlInitUnicodeString` at `0x140296b1c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140296b1c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140296997`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140296997`
- `ntoskrnl!ZwSetValueKey` at `0x140296b4d`
- `ntoskrnl!ZwSetValueKey` at `0x140296b4d`
- `watchdog!WdLogSingleEntry0` at `0x140296779`
- `watchdog!WdLogSingleEntry0` at `0x140296891`
- `watchdog!WdLogSingleEntry0` at `0x140296779`
- `watchdog!WdLogSingleEntry0` at `0x140296891`
- `watchdog!WdLogSingleEntry1` at `0x140296712`
- `watchdog!WdLogSingleEntry1` at `0x14029680a`
- `watchdog!WdLogSingleEntry1` at `0x140296841`
- `watchdog!WdLogSingleEntry1` at `0x1402968f2`
- `watchdog!WdLogSingleEntry1` at `0x14029694f`
- `watchdog!WdLogSingleEntry1` at `0x140296aba`
- `watchdog!WdLogSingleEntry1` at `0x140296b83`
- `watchdog!WdLogSingleEntry1` at `0x140296bc0`
- `watchdog!WdLogSingleEntry1` at `0x140296bfd`
- `watchdog!WdLogSingleEntry1` at `0x140296c24`
- `watchdog!WdLogSingleEntry1` at `0x140296c5e`
- `watchdog!WdLogSingleEntry1` at `0x140296c9b`
- `watchdog!WdLogSingleEntry1` at `0x140296712`
- `watchdog!WdLogSingleEntry1` at `0x14029680a`
- `watchdog!WdLogSingleEntry1` at `0x140296841`
- `watchdog!WdLogSingleEntry1` at `0x1402968f2`
- `watchdog!WdLogSingleEntry1` at `0x14029694f`
- `watchdog!WdLogSingleEntry1` at `0x140296aba`
- `watchdog!WdLogSingleEntry1` at `0x140296b83`
- `watchdog!WdLogSingleEntry1` at `0x140296bc0`
- `watchdog!WdLogSingleEntry1` at `0x140296bfd`
- `watchdog!WdLogSingleEntry1` at `0x140296c24`
- `watchdog!WdLogSingleEntry1` at `0x140296c5e`
- `watchdog!WdLogSingleEntry1` at `0x140296c9b`

## string_xrefs

- `0x14029678a`: `Cannot allocate memory for DXGKVMB_COMMAND_GETREGISTRYKEYS_RETURN`
- `0x1402968fe`: `Failed to read PnP registry key name for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296723`: `Failed to copy RegPathIn to VMBus Command for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296852`: `VmBusSendSyncMessage Output failed for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296816`: `VmBusSendSyncMessage failed for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296ba0`: `Failed to create registry key for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14029695b`: `Failed to concat \ to RegPathRoot for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296c7b`: `Failed to create registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296bdd`: `Failed to build registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296ad7`: `Failed to translate UmdFileNames in Multi String Type to VM namespace for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296c41`: `Failed to translate UmdFileName to VM namespace for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140296ca7`: `VmBusSendReadRegistryKeys failed: 0x%I64x`
- `0x140296c09`: `Failed to set value of reg key for VmBusGetRegistryKeys (status = 0x%I64x).`

## pseudocode

```c
__int64 __fastcall DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendGetRegistryKeys(
        DXG_GUEST_VIRTUALGPU_VMBUS *this,
        unsigned __int16 *a2)
{
  wchar_t *v4; // rax
  wchar_t *v5; // r14
  __int64 v6; // rcx
  int v7; // eax
  __int64 RegistryPathFromPDO; // rdi
  unsigned int *v9; // rax
  unsigned int *v10; // r15
  __int64 v12; // rcx
  const wchar_t *v13; // r9
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rbx
  int v15; // eax
  unsigned int v16; // r12d
  __int64 v17; // r13
  unsigned int *v18; // rbx
  unsigned __int64 v19; // r8
  __int64 i; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // eax
  int v26; // eax
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v32; // [rsp+78h] [rbp-88h] BYREF
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+98h] [rbp-68h] BYREF
  __int128 v35; // [rsp+B0h] [rbp-50h] BYREF
  int v36; // [rsp+C0h] [rbp-40h]

  v36 = 0;
  v35 = 0;
  DXGVMBUSMESSAGE::InitializeMessage((DXGVMBUSMESSAGE *)&v35, this, 0x220u, 0, 0, 0);
  if ( (_QWORD)v35 )
  {
    v4 = (wchar_t *)operator new(1560, 1265072196, 64);
    v5 = v4;
    if ( v4 )
    {
      memset(v4, 0, 0x618u);
      v6 = v35;
      DestinationString.Buffer = v5 + 260;
      *(_QWORD *)&SourceString.Length = 34078720;
      ValueName.Buffer = v5 + 520;
      SourceString.Buffer = v5;
      *(_QWORD *)&DestinationString.Length = 34078720;
      *(_QWORD *)&ValueName.Length = 34078720;
      *(_BYTE *)(v35 + 12) = 0;
      *(_DWORD *)(v6 + 12) &= 0x1FFu;
      *(_QWORD *)v6 = 0;
      *(_DWORD *)(v6 + 8) = 0;
      *(_QWORD *)(v6 + 16) = 63;
      KeyHandle = 0;
      v28 = 1;
      v7 = RtlStringCbCopyW((unsigned __int16 *)(v6 + 24), 0x208u, a2);
      RegistryPathFromPDO = v7;
      if ( v7 < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 13095;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to copy RegPathIn to VMBus Command for VmBusGetRegistryKeys (status = 0x%I64x).",
          RegistryPathFromPDO,
          0,
          0,
          0,
          0);
LABEL_7:
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v5);
        DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v35);
        return (unsigned int)RegistryPathFromPDO;
      }
      v27 = 130040;
      v9 = (unsigned int *)operator new[](130040, 1265072196, 64);
      v10 = v9;
      if ( !v9 )
      {
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 13105;
        DxgkLogInternalTriageEvent(
          0,
          262145,
          -1,
          (unsigned int)L"Cannot allocate memory for DXGKVMB_COMMAND_GETREGISTRYKEYS_RETURN",
          13105,
          0,
          0,
          0,
          0);
        LODWORD(RegistryPathFromPDO) = -1073741801;
        goto LABEL_7;
      }
      v12 = DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSyncMessage(this, (struct DXGVMBUSMESSAGE *)&v35, v9, &v27);
      if ( !v27 )
      {
        RegistryPathFromPDO = -1073741823;
        WdLogSingleEntry1(2);
        v13 = L"VmBusSendSyncMessage failed for VmBusGetRegistryKeys (status = 0x%I64x).";
        WdLogGlobalForLineNumber = 13115;
        goto LABEL_44;
      }
      if ( (v10[1] & 0x80000000) != 0 )
      {
        LODWORD(RegistryPathFromPDO) = v10[1];
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 13123;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"VmBusSendSyncMessage Output failed for VmBusGetRegistryKeys (status = 0x%I64x).",
          (int)RegistryPathFromPDO,
          0,
          0,
          0,
          0);
LABEL_45:
        CloseRegistrySubkey(KeyHandle);
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v10);
        goto LABEL_7;
      }
      RegistryPathFromPDO = v12;
      if ( (int)v12 < 0 )
      {
        WdLogSingleEntry1(2);
        v13 = L"VmBusSendReadRegistryKeys failed: 0x%I64x";
        WdLogGlobalForLineNumber = 13254;
        goto LABEL_44;
      }
      if ( !*v10 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 13131;
        goto LABEL_45;
      }
      DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(*(PDEVICE_OBJECT *)(*((_QWORD *)this + 9) + 216LL));
      RegistryPathFromPDO = (int)DpiGetRegistryPathFromPDO(DeviceAttachmentBaseRef, 0, &SourceString);
      ObfDereferenceObject(DeviceAttachmentBaseRef);
      if ( (int)RegistryPathFromPDO < 0 )
      {
        WdLogSingleEntry1(2);
        v13 = L"Failed to read PnP registry key name for VmBusGetRegistryKeys (status = 0x%I64x).";
        WdLogGlobalForLineNumber = 13142;
        goto LABEL_44;
      }
      v30 = *(_DWORD *)L"\\";
      *(_QWORD *)&v32.Length = 262146;
      v32.Buffer = (wchar_t *)&v30;
      v15 = RtlUnicodeStringCat(&SourceString, &v32);
      RegistryPathFromPDO = v15;
      if ( v15 < 0 )
      {
        WdLogSingleEntry1(2);
        v13 = L"Failed to concat \\ to RegPathRoot for VmBusGetRegistryKeys (status = 0x%I64x).";
        WdLogGlobalForLineNumber = 13150;
        goto LABEL_44;
      }
      v16 = 0;
      while ( 2 )
      {
        if ( v16 >= *v10 )
          goto LABEL_45;
        v17 = 774LL * v16;
        v18 = &v10[v17 + 2];
        RtlCopyUnicodeString(&DestinationString, &SourceString);
        for ( i = 0; ; i = v27 + 1 )
        {
          v27 = i;
          *(_QWORD *)&v32.Length = (char *)v18 + 2 * i + 2048;
          if ( !**(_WORD **)&v32.Length )
            break;
          if ( **(_WORD **)&v32.Length == 92 )
          {
            v28 = 1;
            v21 = OpenRegistrySubkey(&KeyHandle, 0x20006u, 0, &DestinationString, &v28);
            RegistryPathFromPDO = v21;
            if ( v21 < 0 )
            {
              WdLogSingleEntry1(2);
              WdLogGlobalForLineNumber = 13176;
              v13 = L"Failed to create registry key for VmBusGetRegistryKeys (status = 0x%I64x).";
              goto LABEL_44;
            }
            CloseRegistrySubkey(KeyHandle);
            KeyHandle = 0;
          }
          v22 = RtlUnicodeStringCchCatStringN(&DestinationString, *(const unsigned __int16 **)&v32.Length, v19);
          RegistryPathFromPDO = v22;
          if ( v22 < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 13187;
            v13 = L"Failed to build registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).";
            goto LABEL_44;
          }
        }
        v28 = 1;
        v23 = OpenRegistrySubkey(&KeyHandle, 0x20006u, 0, &DestinationString, &v28);
        RegistryPathFromPDO = v23;
        if ( v23 < 0 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 13202;
          v13 = L"Failed to create registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).";
          goto LABEL_44;
        }
        if ( v18 == (unsigned int *)-2568LL && !v10[v17 + 775] )
          goto LABEL_37;
        v24 = v10[v17 + 774];
        if ( v24 - 1 <= 1 )
        {
          v26 = TranslateUmdFileNameToVm((unsigned __int16 *)&v10[v17 + 2], 0x400u, v18 + 773);
          RegistryPathFromPDO = v26;
          if ( v26 < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 13217;
            v13 = L"Failed to translate UmdFileName to VM namespace for VmBusGetRegistryKeys (status = 0x%I64x).";
            goto LABEL_44;
          }
        }
        else if ( v24 == 7 )
        {
          v25 = TranslateUmdFileNameToVmMultiString((unsigned __int16 *)&v10[v17 + 2], 0x400u, v18 + 773);
          RegistryPathFromPDO = v25;
          if ( v25 < 0 )
          {
            WdLogSingleEntry1(2);
            WdLogGlobalForLineNumber = 13227;
            v13 = L"Failed to translate UmdFileNames in Multi String Type to VM namespace for VmBusGetRegistryKeys (status = 0x%I64x).";
            goto LABEL_44;
          }
        }
        RtlInitUnicodeString(&ValueName, (PCWSTR)v18 + 1284);
        RegistryPathFromPDO = ZwSetValueKey(KeyHandle, &ValueName, 0, v10[v17 + 774], &v10[v17 + 2], v10[v17 + 775]);
        CloseRegistrySubkey(KeyHandle);
        KeyHandle = 0;
        if ( (int)RegistryPathFromPDO >= 0 )
        {
LABEL_37:
          ++v16;
          continue;
        }
        break;
      }
      WdLogSingleEntry1(2);
      v13 = L"Failed to set value of reg key for VmBusGetRegistryKeys (status = 0x%I64x).";
      WdLogGlobalForLineNumber = 13245;
LABEL_44:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v13, RegistryPathFromPDO, 0, 0, 0, 0);
      goto LABEL_45;
    }
  }
  DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE((DXGVMBUSMESSAGE *)&v35);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1402965f0  mov     [rsp-8+arg_10], rbx
0x1402965f5  push    rbp
0x1402965f6  push    rsi
0x1402965f7  push    rdi
0x1402965f8  push    r12
0x1402965fa  push    r13
0x1402965fc  push    r14
0x1402965fe  push    r15
0x140296600  lea     rbp, [rsp-0E0h]
0x140296608  sub     rsp, 1E0h
0x14029660f  mov     rax, cs:__security_cookie
0x140296616  xor     rax, rsp
0x140296619  mov     [rbp+110h+var_40], rax
0x140296620  xor     r13d, r13d
0x140296623  mov     rdi, rdx
0x140296626  mov     rdx, rcx; struct DXG_VMBUS_CHANNEL_BASE *
0x140296629  mov     qword ptr [rsp+210h+DataSize], r13; unsigned int *
0x14029662e  mov     rbx, rcx
0x140296631  mov     [rsp+210h+Data], r13; unsigned int *
0x140296636  xorps   xmm0, xmm0
0x140296639  mov     [rbp+110h+var_150], r13d
0x14029663d  lea     rcx, [rbp+110h+var_160]; this
0x140296641  movdqa  [rbp+110h+var_160], xmm0
0x140296646  xor     r9d, r9d; unsigned int *
0x140296649  mov     r8d, 220h; unsigned int
0x14029664f  call    ?InitializeMessage@DXGVMBUSMESSAGE@@QEAAXPEAUDXG_VMBUS_CHANNEL_BASE@@IPEAI11@Z; DXGVMBUSMESSAGE::InitializeMessage(DXG_VMBUS_CHANNEL_BASE *,uint,uint *,uint *,uint *)
0x140296654  cmp     qword ptr [rbp+110h+var_160], r13
0x140296658  jz      loc_140296CF8
0x14029665e  lea     esi, [r13+40h]
0x140296662  mov     r15d, 4B677844h
0x140296668  mov     r12d, 618h
0x14029666e  mov     r8d, esi
0x140296671  mov     edx, r15d
0x140296674  mov     ecx, r12d
0x140296677  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14029667c  mov     r14, rax
0x14029667f  test    rax, rax
0x140296682  jz      loc_140296CF8
0x140296688  mov     r8d, r12d; Size
0x14029668b  xor     edx, edx; Val
0x14029668d  mov     rcx, rax; void *
0x140296690  call    memset
0x140296695  mov     rcx, qword ptr [rbp+110h+var_160]
0x140296699  lea     rax, [r14+208h]
0x1402966a0  mov     [rsp+210h+DestinationString.Buffer], rax
0x1402966a5  mov     edx, 208h; unsigned __int64
0x1402966aa  mov     qword ptr [rbp+110h+SourceString.Length], 2080000h
0x1402966b2  lea     rax, [r14+410h]
0x1402966b9  mov     [rbp+110h+ValueName.Buffer], rax
0x1402966bd  mov     r8, rdi; unsigned __int16 *
0x1402966c0  mov     [rbp+110h+SourceString.Buffer], r14
0x1402966c4  mov     qword ptr [rsp+210h+DestinationString.Length], 2080000h
0x1402966cd  mov     qword ptr [rbp+110h+ValueName.Length], 2080000h
0x1402966d5  mov     [rcx+0Ch], r13b
0x1402966d9  and     dword ptr [rcx+0Ch], 1FFh
0x1402966e0  mov     [rcx], r13
0x1402966e3  mov     [rcx+8], r13d
0x1402966e7  mov     qword ptr [rcx+10h], 3Fh ; '?'
0x1402966ef  add     rcx, 18h; unsigned __int16 *
0x1402966f3  mov     [rsp+210h+KeyHandle], r13
0x1402966f8  mov     [rsp+210h+var_1BC], 1
0x140296700  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140296705  movsxd  rdi, eax
0x140296708  test    eax, eax
0x14029670a  jns     short loc_14029675A
0x14029670c  mov     rdx, rdi
0x14029670f  lea     ecx, [rsi-3Eh]
0x140296712  call    cs:__imp_WdLogSingleEntry1
0x140296719  nop     dword ptr [rax+rax+00h]
0x14029671e  mov     [rsp+210h+var_1D0], r13
0x140296723  lea     r9, aFailedToCopyRe; "Failed to copy RegPathIn to VMBus Comma"...
0x14029672a  mov     [rsp+210h+var_1D8], r13
0x14029672f  or      r8d, 0FFFFFFFFh
0x140296733  mov     [rsp+210h+var_1E0], r13
0x140296738  mov     edx, 40000h
0x14029673d  mov     qword ptr [rsp+210h+DataSize], r13
0x140296742  xor     ecx, ecx
0x140296744  mov     [rsp+210h+Data], rdi
0x140296749  mov     cs:WdLogGlobalForLineNumber, 3327h
0x140296753  call    DxgkLogInternalTriageEvent
0x140296758  jmp     short loc_1402967C5
0x14029675a  mov     ecx, 1FBF8h
0x14029675f  mov     r8, rsi
0x140296762  mov     edx, r15d
0x140296765  mov     [rsp+210h+var_1C0], ecx
0x140296769  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14029676e  mov     r15, rax
0x140296771  test    rax, rax
0x140296774  jnz     short loc_1402967DD
0x140296776  lea     ecx, [rax+6]
0x140296779  call    cs:__imp_WdLogSingleEntry0
0x140296780  nop     dword ptr [rax+rax+00h]
0x140296785  mov     [rsp+210h+var_1D0], r13
0x14029678a  lea     r9, aCannotAllocate_4; "Cannot allocate memory for DXGKVMB_COMM"...
0x140296791  mov     [rsp+210h+var_1D8], r13
0x140296796  mov     eax, 3331h
0x14029679b  mov     [rsp+210h+var_1E0], r13
0x1402967a0  or      r8d, 0FFFFFFFFh
0x1402967a4  mov     qword ptr [rsp+210h+DataSize], r13
0x1402967a9  mov     edx, 40001h
0x1402967ae  xor     ecx, ecx
0x1402967b0  mov     [rsp+210h+Data], rax
0x1402967b5  mov     cs:WdLogGlobalForLineNumber, eax
0x1402967bb  call    DxgkLogInternalTriageEvent
0x1402967c0  mov     edi, 0C0000017h
0x1402967c5  mov     rcx, r14; void *
0x1402967c8  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1402967cd  lea     rcx, [rbp+110h+var_160]; this
0x1402967d1  call    ??1DXGVMBUSMESSAGE@@QEAA@XZ; DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE(void)
0x1402967d6  mov     eax, edi
0x1402967d8  jmp     loc_140296D06
0x1402967dd  lea     r9, [rsp+210h+var_1C0]; unsigned int *
0x1402967e2  mov     r8, r15; void *
0x1402967e5  lea     rdx, [rbp+110h+var_160]; struct DXGVMBUSMESSAGE *
0x1402967e9  mov     rcx, rbx; this
0x1402967ec  call    ?VmBusSendSyncMessage@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAUDXGVMBUSMESSAGE@@PEAXPEAI@Z; DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSyncMessage(DXGVMBUSMESSAGE *,void *,uint *)
0x1402967f1  movsxd  rcx, eax
0x1402967f4  cmp     [rsp+210h+var_1C0], r13d
0x1402967f9  jnz     short loc_14029682C
0x1402967fb  mov     rdi, 0FFFFFFFFC0000001h
0x140296802  mov     rdx, rdi
0x140296805  mov     ecx, 2
0x14029680a  call    cs:__imp_WdLogSingleEntry1
0x140296811  nop     dword ptr [rax+rax+00h]
0x140296816  lea     r9, aVmbussendsyncm_1; "VmBusSendSyncMessage failed for VmBusGe"...
0x14029681d  mov     cs:WdLogGlobalForLineNumber, 333Bh
0x140296827  jmp     loc_140296CB8
0x14029682c  movsxd  rax, dword ptr [r15+4]
0x140296830  test    eax, eax
0x140296832  jns     short loc_14029687C
0x140296834  mov     edi, eax
0x140296836  mov     rdx, rax
0x140296839  mov     ecx, 2
0x14029683e  mov     rbx, rax
0x140296841  call    cs:__imp_WdLogSingleEntry1
0x140296848  nop     dword ptr [rax+rax+00h]
0x14029684d  mov     [rsp+210h+var_1D0], r13
0x140296852  lea     r9, aVmbussendsyncm_2; "VmBusSendSyncMessage Output failed for "...
0x140296859  mov     [rsp+210h+var_1D8], r13
0x14029685e  mov     [rsp+210h+var_1E0], r13
0x140296863  mov     qword ptr [rsp+210h+DataSize], r13
0x140296868  mov     [rsp+210h+Data], rbx
0x14029686d  mov     cs:WdLogGlobalForLineNumber, 3343h
0x140296877  jmp     loc_140296CD1
0x14029687c  mov     rdi, rcx
0x14029687f  test    ecx, ecx
0x140296881  js      loc_140296C93
0x140296887  cmp     [r15], r13d
0x14029688a  jnz     short loc_1402968AC
0x14029688c  mov     ecx, 3
0x140296891  call    cs:__imp_WdLogSingleEntry0
0x140296898  nop     dword ptr [rax+rax+00h]
0x14029689d  mov     cs:WdLogGlobalForLineNumber, 334Bh
0x1402968a7  jmp     loc_140296CE1
0x1402968ac  mov     rcx, [rbx+48h]
0x1402968b0  mov     rcx, [rcx+0D8h]; DeviceObject
0x1402968b7  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x1402968be  nop     dword ptr [rax+rax+00h]
0x1402968c3  lea     r8, [rbp+110h+SourceString]
0x1402968c7  xor     edx, edx
0x1402968c9  mov     rcx, rax
0x1402968cc  mov     rbx, rax
0x1402968cf  call    DpiGetRegistryPathFromPDO
0x1402968d4  mov     rcx, rbx; Object
0x1402968d7  movsxd  rdi, eax
0x1402968da  call    cs:__imp_ObfDereferenceObject
0x1402968e1  nop     dword ptr [rax+rax+00h]
0x1402968e6  test    edi, edi
0x1402968e8  jns     short loc_140296914
0x1402968ea  mov     rdx, rdi
0x1402968ed  mov     ecx, 2
0x1402968f2  call    cs:__imp_WdLogSingleEntry1
0x1402968f9  nop     dword ptr [rax+rax+00h]
0x1402968fe  lea     r9, aFailedToReadPn_0; "Failed to read PnP registry key name fo"...
0x140296905  mov     cs:WdLogGlobalForLineNumber, 3356h
0x14029690f  jmp     loc_140296CB8
0x140296914  mov     eax, dword ptr cs:Source; "\\"
0x14029691a  lea     rdx, [rsp+210h+var_198]; struct _UNICODE_STRING *
0x14029691f  mov     [rsp+210h+var_1B0], eax
0x140296923  lea     rcx, [rbp+110h+SourceString]; struct _UNICODE_STRING *
0x140296927  lea     rax, [rsp+210h+var_1B0]
0x14029692c  mov     qword ptr [rsp+210h+var_198.Length], 40002h
0x140296935  mov     [rbp+110h+var_198.Buffer], rax
0x140296939  mov     esi, 2
0x14029693e  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x140296943  movsxd  rdi, eax
0x140296946  test    eax, eax
0x140296948  jns     short loc_140296971
0x14029694a  mov     rdx, rdi
0x14029694d  mov     ecx, esi
0x14029694f  call    cs:__imp_WdLogSingleEntry1
0x140296956  nop     dword ptr [rax+rax+00h]
0x14029695b  lea     r9, aFailedToConcat; "Failed to concat \\ to RegPathRoot for "...
0x140296962  mov     cs:WdLogGlobalForLineNumber, 335Eh
0x14029696c  jmp     loc_140296CB8
0x140296971  mov     r12d, r13d
0x140296974  cmp     r12d, [r15]
0x140296977  jnb     loc_140296CE1
0x14029697d  mov     eax, r12d
0x140296980  lea     rbx, [r15+8]
0x140296984  imul    r13, rax, 0C18h
0x14029698b  lea     rdx, [rbp+110h+SourceString]; SourceString
0x14029698f  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x140296994  add     rbx, r13
0x140296997  call    cs:__imp_RtlCopyUnicodeString
0x14029699e  nop     dword ptr [rax+rax+00h]
0x1402969a3  xor     ecx, ecx
0x1402969a5  mov     eax, ecx
0x1402969a7  mov     [rsp+210h+var_1C0], eax
0x1402969ab  lea     rax, [rax+400h]
0x1402969b2  lea     rax, [rbx+rax*2]
0x1402969b6  mov     qword ptr [rsp+210h+var_198.Length], rax
0x1402969bb  movzx   eax, word ptr [rax]
0x1402969be  test    ax, ax
0x1402969c1  jz      short loc_140296A35
0x1402969c3  cmp     ax, 5Ch ; '\'
0x1402969c7  jnz     short loc_140296A10
0x1402969c9  lea     rax, [rsp+210h+var_1BC]
0x1402969ce  mov     [rsp+210h+var_1BC], 1
0x1402969d6  lea     r9, [rsp+210h+DestinationString]; struct _UNICODE_STRING *
0x1402969db  mov     [rsp+210h+Data], rax; unsigned int *
0x1402969e0  xor     r8d, r8d; void *
0x1402969e3  lea     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x1402969e8  mov     edx, 20006h; DesiredAccess
0x1402969ed  call    ?OpenRegistrySubkey@@YAJPEAPEAXKPEAXAEBU_UNICODE_STRING@@PEAK@Z; OpenRegistrySubkey(void * *,ulong,void *,_UNICODE_STRING const &,ulong *)
0x1402969f2  movsxd  rdi, eax
0x1402969f5  test    eax, eax
0x1402969f7  js      loc_140296B7E
0x1402969fd  mov     rcx, [rsp+210h+KeyHandle]; void *
0x140296a02  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x140296a07  mov     [rsp+210h+KeyHandle], 0
0x140296a10  mov     rdx, qword ptr [rsp+210h+var_198.Length]; unsigned __int16 *
0x140296a15  lea     rcx, [rsp+210h+DestinationString]; struct _UNICODE_STRING *
0x140296a1a  call    ?RtlUnicodeStringCchCatStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCatStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x140296a1f  movsxd  rdi, eax
0x140296a22  test    eax, eax
0x140296a24  js      loc_140296BBB
0x140296a2a  mov     eax, [rsp+210h+var_1C0]
0x140296a2e  inc     eax
0x140296a30  jmp     loc_1402969A7
0x140296a35  lea     rax, [rsp+210h+var_1BC]
0x140296a3a  mov     [rsp+210h+var_1BC], 1
0x140296a42  lea     r9, [rsp+210h+DestinationString]; struct _UNICODE_STRING *
0x140296a47  mov     [rsp+210h+Data], rax; unsigned int *
0x140296a4c  xor     r8d, r8d; void *
0x140296a4f  lea     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x140296a54  mov     edx, 20006h; DesiredAccess
0x140296a59  call    ?OpenRegistrySubkey@@YAJPEAPEAXKPEAXAEBU_UNICODE_STRING@@PEAK@Z; OpenRegistrySubkey(void * *,ulong,void *,_UNICODE_STRING const &,ulong *)
0x140296a5e  xor     ecx, ecx
0x140296a60  movsxd  rdi, eax
0x140296a63  test    eax, eax
0x140296a65  js      loc_140296C59
0x140296a6b  lea     rax, [rbx+0A08h]
0x140296a72  test    rax, rax
0x140296a75  jnz     short loc_140296A85
0x140296a77  cmp     [r15+r13+0C1Ch], ecx
0x140296a7f  jz      loc_140296B76
0x140296a85  mov     ecx, [r15+r13+0C18h]
0x140296a8d  lea     eax, [rcx-1]
0x140296a90  cmp     eax, 1
0x140296a93  jbe     short loc_140296AF2
0x140296a95  cmp     ecx, 7
0x140296a98  jnz     short loc_140296B11
0x140296a9a  lea     r8, [rbx+0C14h]; unsigned int *
0x140296aa1  mov     edx, 400h; unsigned int
0x140296aa6  mov     rcx, rbx; unsigned __int16 *
0x140296aa9  call    ?TranslateUmdFileNameToVmMultiString@@YAJPEAGIPEAK@Z; TranslateUmdFileNameToVmMultiString(ushort *,uint,ulong *)
0x140296aae  movsxd  rdi, eax
0x140296ab1  test    eax, eax
0x140296ab3  jns     short loc_140296B11
0x140296ab5  mov     rdx, rdi
0x140296ab8  mov     ecx, esi
0x140296aba  call    cs:__imp_WdLogSingleEntry1
0x140296ac1  nop     dword ptr [rax+rax+00h]
0x140296ac6  xor     eax, eax
0x140296ac8  mov     cs:WdLogGlobalForLineNumber, 33ABh
0x140296ad2  mov     [rsp+210h+var_1D0], rax
0x140296ad7  lea     r9, aFailedToTransl_0; "Failed to translate UmdFileNames in Mul"...
0x140296ade  mov     [rsp+210h+var_1D8], rax
0x140296ae3  mov     [rsp+210h+var_1E0], rax
0x140296ae8  mov     qword ptr [rsp+210h+DataSize], rax
0x140296aed  jmp     loc_140296CCC
0x140296af2  lea     r8, [rbx+0C14h]; unsigned int *
0x140296af9  mov     edx, 400h; unsigned int
0x140296afe  mov     rcx, rbx; unsigned __int16 *
0x140296b01  call    ?TranslateUmdFileNameToVm@@YAJPEAGIPEAK@Z; TranslateUmdFileNameToVm(ushort *,uint,ulong *)
0x140296b06  movsxd  rdi, eax
0x140296b09  test    eax, eax
0x140296b0b  js      loc_140296C1F
0x140296b11  lea     rdx, [rbx+0A08h]; SourceString
0x140296b18  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x140296b1c  call    cs:__imp_RtlInitUnicodeString
0x140296b23  nop     dword ptr [rax+rax+00h]
0x140296b28  mov     eax, [r15+r13+0C1Ch]
0x140296b30  lea     rdx, [rbp+110h+ValueName]; ValueName
0x140296b34  mov     r9d, [r15+r13+0C18h]; Type
0x140296b3c  xor     r8d, r8d; TitleIndex
0x140296b3f  mov     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x140296b44  mov     [rsp+210h+DataSize], eax; DataSize
0x140296b48  mov     [rsp+210h+Data], rbx; Data
  ... truncated ...
```
