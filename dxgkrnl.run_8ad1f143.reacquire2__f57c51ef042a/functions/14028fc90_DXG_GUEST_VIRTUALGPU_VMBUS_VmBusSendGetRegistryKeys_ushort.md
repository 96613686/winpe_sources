# DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendGetRegistryKeys(ushort *)

- ea: `0x14028fc90`
- end: `0x1402903d1`
- name: `?VmBusSendGetRegistryKeys@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAG@Z`
- size: `1857`
- prototype: `__int64 __fastcall(DXG_GUEST_VIRTUALGPU_VMBUS *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1401e62cc`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x14001b890`
- `0x14002e110`
- `0x14002ecf0`
- `0x140062450`
- `0x140072e88`
- `0x14007dad0`
- `0x14007f0ec`
- `0x1400a0100`
- `0x1400a0540`
- `0x14020a744`
- `0x14020a8dc`
- `0x14028fc90`
- `0x140292b54`
- `0x14035f150`
- `0x1403dc3f4`
- `0x140403b40`

## import_xrefs

- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14028ff57`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14028ff57`
- `ntoskrnl!ObfDereferenceObject` at `0x14028ff7a`
- `ntoskrnl!ObfDereferenceObject` at `0x14028ff7a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402901bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402901bc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140290037`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140290037`
- `ntoskrnl!ZwSetValueKey` at `0x1402901ed`
- `ntoskrnl!ZwSetValueKey` at `0x1402901ed`
- `watchdog!WdLogSingleEntry0` at `0x14028fe19`
- `watchdog!WdLogSingleEntry0` at `0x14028ff31`
- `watchdog!WdLogSingleEntry0` at `0x14028fe19`
- `watchdog!WdLogSingleEntry0` at `0x14028ff31`
- `watchdog!WdLogSingleEntry1` at `0x14028fdb2`
- `watchdog!WdLogSingleEntry1` at `0x14028feaa`
- `watchdog!WdLogSingleEntry1` at `0x14028fee1`
- `watchdog!WdLogSingleEntry1` at `0x14028ff92`
- `watchdog!WdLogSingleEntry1` at `0x14028ffef`
- `watchdog!WdLogSingleEntry1` at `0x14029015a`
- `watchdog!WdLogSingleEntry1` at `0x140290223`
- `watchdog!WdLogSingleEntry1` at `0x140290260`
- `watchdog!WdLogSingleEntry1` at `0x14029029d`
- `watchdog!WdLogSingleEntry1` at `0x1402902c4`
- `watchdog!WdLogSingleEntry1` at `0x1402902fe`
- `watchdog!WdLogSingleEntry1` at `0x14029033b`
- `watchdog!WdLogSingleEntry1` at `0x14028fdb2`
- `watchdog!WdLogSingleEntry1` at `0x14028feaa`
- `watchdog!WdLogSingleEntry1` at `0x14028fee1`
- `watchdog!WdLogSingleEntry1` at `0x14028ff92`
- `watchdog!WdLogSingleEntry1` at `0x14028ffef`
- `watchdog!WdLogSingleEntry1` at `0x14029015a`
- `watchdog!WdLogSingleEntry1` at `0x140290223`
- `watchdog!WdLogSingleEntry1` at `0x140290260`
- `watchdog!WdLogSingleEntry1` at `0x14029029d`
- `watchdog!WdLogSingleEntry1` at `0x1402902c4`
- `watchdog!WdLogSingleEntry1` at `0x1402902fe`
- `watchdog!WdLogSingleEntry1` at `0x14029033b`

## string_xrefs

- `0x14028fe2a`: `Cannot allocate memory for DXGKVMB_COMMAND_GETREGISTRYKEYS_RETURN`
- `0x14028ff9e`: `Failed to read PnP registry key name for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028fdc3`: `Failed to copy RegPathIn to VMBus Command for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028fef2`: `VmBusSendSyncMessage Output failed for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028feb6`: `VmBusSendSyncMessage failed for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140290240`: `Failed to create registry key for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14028fffb`: `Failed to concat \ to RegPathRoot for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14029031b`: `Failed to create registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x14029027d`: `Failed to build registry subkey for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140290177`: `Failed to translate UmdFileNames in Multi String Type to VM namespace for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x1402902e1`: `Failed to translate UmdFileName to VM namespace for VmBusGetRegistryKeys (status = 0x%I64x).`
- `0x140290347`: `VmBusSendReadRegistryKeys failed: 0x%I64x`
- `0x1402902a9`: `Failed to set value of reg key for VmBusGetRegistryKeys (status = 0x%I64x).`

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
        WdLogGlobalForLineNumber = 13097;
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
        WdLogGlobalForLineNumber = 13107;
        DxgkLogInternalTriageEvent(
          0,
          262145,
          -1,
          (unsigned int)L"Cannot allocate memory for DXGKVMB_COMMAND_GETREGISTRYKEYS_RETURN",
          13107,
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
        WdLogGlobalForLineNumber = 13117;
        goto LABEL_44;
      }
      if ( (v10[1] & 0x80000000) != 0 )
      {
        LODWORD(RegistryPathFromPDO) = v10[1];
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 13125;
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
        WdLogGlobalForLineNumber = 13256;
        goto LABEL_44;
      }
      if ( !*v10 )
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 13133;
        goto LABEL_45;
      }
      DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(*(PDEVICE_OBJECT *)(*((_QWORD *)this + 9) + 216LL));
      RegistryPathFromPDO = (int)DpiGetRegistryPathFromPDO(DeviceAttachmentBaseRef, 0, &SourceString);
      ObfDereferenceObject(DeviceAttachmentBaseRef);
      if ( (int)RegistryPathFromPDO < 0 )
      {
        WdLogSingleEntry1(2);
        v13 = L"Failed to read PnP registry key name for VmBusGetRegistryKeys (status = 0x%I64x).";
        WdLogGlobalForLineNumber = 13144;
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
        WdLogGlobalForLineNumber = 13152;
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
              WdLogGlobalForLineNumber = 13178;
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
            WdLogGlobalForLineNumber = 13189;
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
          WdLogGlobalForLineNumber = 13204;
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
            WdLogGlobalForLineNumber = 13219;
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
            WdLogGlobalForLineNumber = 13229;
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
      WdLogGlobalForLineNumber = 13247;
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
0x14028fc90  mov     [rsp-8+arg_10], rbx
0x14028fc95  push    rbp
0x14028fc96  push    rsi
0x14028fc97  push    rdi
0x14028fc98  push    r12
0x14028fc9a  push    r13
0x14028fc9c  push    r14
0x14028fc9e  push    r15
0x14028fca0  lea     rbp, [rsp-0E0h]
0x14028fca8  sub     rsp, 1E0h
0x14028fcaf  mov     rax, cs:__security_cookie
0x14028fcb6  xor     rax, rsp
0x14028fcb9  mov     [rbp+110h+var_40], rax
0x14028fcc0  xor     r13d, r13d
0x14028fcc3  mov     rdi, rdx
0x14028fcc6  mov     rdx, rcx; struct DXG_VMBUS_CHANNEL_BASE *
0x14028fcc9  mov     qword ptr [rsp+210h+DataSize], r13; unsigned int *
0x14028fcce  mov     rbx, rcx
0x14028fcd1  mov     [rsp+210h+Data], r13; unsigned int *
0x14028fcd6  xorps   xmm0, xmm0
0x14028fcd9  mov     [rbp+110h+var_150], r13d
0x14028fcdd  lea     rcx, [rbp+110h+var_160]; this
0x14028fce1  movdqa  [rbp+110h+var_160], xmm0
0x14028fce6  xor     r9d, r9d; unsigned int *
0x14028fce9  mov     r8d, 220h; unsigned int
0x14028fcef  call    ?InitializeMessage@DXGVMBUSMESSAGE@@QEAAXPEAUDXG_VMBUS_CHANNEL_BASE@@IPEAI11@Z; DXGVMBUSMESSAGE::InitializeMessage(DXG_VMBUS_CHANNEL_BASE *,uint,uint *,uint *,uint *)
0x14028fcf4  cmp     qword ptr [rbp+110h+var_160], r13
0x14028fcf8  jz      loc_140290398
0x14028fcfe  lea     esi, [r13+40h]
0x14028fd02  mov     r15d, 4B677844h
0x14028fd08  mov     r12d, 618h
0x14028fd0e  mov     r8d, esi
0x14028fd11  mov     edx, r15d
0x14028fd14  mov     ecx, r12d
0x14028fd17  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14028fd1c  mov     r14, rax
0x14028fd1f  test    rax, rax
0x14028fd22  jz      loc_140290398
0x14028fd28  mov     r8d, r12d; Size
0x14028fd2b  xor     edx, edx; Val
0x14028fd2d  mov     rcx, rax; void *
0x14028fd30  call    memset
0x14028fd35  mov     rcx, qword ptr [rbp+110h+var_160]
0x14028fd39  lea     rax, [r14+208h]
0x14028fd40  mov     [rsp+210h+DestinationString.Buffer], rax
0x14028fd45  mov     edx, 208h; unsigned __int64
0x14028fd4a  mov     qword ptr [rbp+110h+SourceString.Length], 2080000h
0x14028fd52  lea     rax, [r14+410h]
0x14028fd59  mov     [rbp+110h+ValueName.Buffer], rax
0x14028fd5d  mov     r8, rdi; unsigned __int16 *
0x14028fd60  mov     [rbp+110h+SourceString.Buffer], r14
0x14028fd64  mov     qword ptr [rsp+210h+DestinationString.Length], 2080000h
0x14028fd6d  mov     qword ptr [rbp+110h+ValueName.Length], 2080000h
0x14028fd75  mov     [rcx+0Ch], r13b
0x14028fd79  and     dword ptr [rcx+0Ch], 1FFh
0x14028fd80  mov     [rcx], r13
0x14028fd83  mov     [rcx+8], r13d
0x14028fd87  mov     qword ptr [rcx+10h], 3Fh ; '?'
0x14028fd8f  add     rcx, 18h; unsigned __int16 *
0x14028fd93  mov     [rsp+210h+KeyHandle], r13
0x14028fd98  mov     [rsp+210h+var_1BC], 1
0x14028fda0  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14028fda5  movsxd  rdi, eax
0x14028fda8  test    eax, eax
0x14028fdaa  jns     short loc_14028FDFA
0x14028fdac  mov     rdx, rdi
0x14028fdaf  lea     ecx, [rsi-3Eh]
0x14028fdb2  call    cs:__imp_WdLogSingleEntry1
0x14028fdb9  nop     dword ptr [rax+rax+00h]
0x14028fdbe  mov     [rsp+210h+var_1D0], r13
0x14028fdc3  lea     r9, aFailedToCopyRe; "Failed to copy RegPathIn to VMBus Comma"...
0x14028fdca  mov     [rsp+210h+var_1D8], r13
0x14028fdcf  or      r8d, 0FFFFFFFFh
0x14028fdd3  mov     [rsp+210h+var_1E0], r13
0x14028fdd8  mov     edx, 40000h
0x14028fddd  mov     qword ptr [rsp+210h+DataSize], r13
0x14028fde2  xor     ecx, ecx
0x14028fde4  mov     [rsp+210h+Data], rdi
0x14028fde9  mov     cs:WdLogGlobalForLineNumber, 3329h
0x14028fdf3  call    DxgkLogInternalTriageEvent
0x14028fdf8  jmp     short loc_14028FE65
0x14028fdfa  mov     ecx, 1FBF8h
0x14028fdff  mov     r8, rsi
0x14028fe02  mov     edx, r15d
0x14028fe05  mov     [rsp+210h+var_1C0], ecx
0x14028fe09  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14028fe0e  mov     r15, rax
0x14028fe11  test    rax, rax
0x14028fe14  jnz     short loc_14028FE7D
0x14028fe16  lea     ecx, [rax+6]
0x14028fe19  call    cs:__imp_WdLogSingleEntry0
0x14028fe20  nop     dword ptr [rax+rax+00h]
0x14028fe25  mov     [rsp+210h+var_1D0], r13
0x14028fe2a  lea     r9, aCannotAllocate_4; "Cannot allocate memory for DXGKVMB_COMM"...
0x14028fe31  mov     [rsp+210h+var_1D8], r13
0x14028fe36  mov     eax, 3333h
0x14028fe3b  mov     [rsp+210h+var_1E0], r13
0x14028fe40  or      r8d, 0FFFFFFFFh
0x14028fe44  mov     qword ptr [rsp+210h+DataSize], r13
0x14028fe49  mov     edx, 40001h
0x14028fe4e  xor     ecx, ecx
0x14028fe50  mov     [rsp+210h+Data], rax
0x14028fe55  mov     cs:WdLogGlobalForLineNumber, eax
0x14028fe5b  call    DxgkLogInternalTriageEvent
0x14028fe60  mov     edi, 0C0000017h
0x14028fe65  mov     rcx, r14; void *
0x14028fe68  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14028fe6d  lea     rcx, [rbp+110h+var_160]; this
0x14028fe71  call    ??1DXGVMBUSMESSAGE@@QEAA@XZ; DXGVMBUSMESSAGE::~DXGVMBUSMESSAGE(void)
0x14028fe76  mov     eax, edi
0x14028fe78  jmp     loc_1402903A6
0x14028fe7d  lea     r9, [rsp+210h+var_1C0]; unsigned int *
0x14028fe82  mov     r8, r15; void *
0x14028fe85  lea     rdx, [rbp+110h+var_160]; struct DXGVMBUSMESSAGE *
0x14028fe89  mov     rcx, rbx; this
0x14028fe8c  call    ?VmBusSendSyncMessage@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAUDXGVMBUSMESSAGE@@PEAXPEAI@Z; DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendSyncMessage(DXGVMBUSMESSAGE *,void *,uint *)
0x14028fe91  movsxd  rcx, eax
0x14028fe94  cmp     [rsp+210h+var_1C0], r13d
0x14028fe99  jnz     short loc_14028FECC
0x14028fe9b  mov     rdi, 0FFFFFFFFC0000001h
0x14028fea2  mov     rdx, rdi
0x14028fea5  mov     ecx, 2
0x14028feaa  call    cs:__imp_WdLogSingleEntry1
0x14028feb1  nop     dword ptr [rax+rax+00h]
0x14028feb6  lea     r9, aVmbussendsyncm_1; "VmBusSendSyncMessage failed for VmBusGe"...
0x14028febd  mov     cs:WdLogGlobalForLineNumber, 333Dh
0x14028fec7  jmp     loc_140290358
0x14028fecc  movsxd  rax, dword ptr [r15+4]
0x14028fed0  test    eax, eax
0x14028fed2  jns     short loc_14028FF1C
0x14028fed4  mov     edi, eax
0x14028fed6  mov     rdx, rax
0x14028fed9  mov     ecx, 2
0x14028fede  mov     rbx, rax
0x14028fee1  call    cs:__imp_WdLogSingleEntry1
0x14028fee8  nop     dword ptr [rax+rax+00h]
0x14028feed  mov     [rsp+210h+var_1D0], r13
0x14028fef2  lea     r9, aVmbussendsyncm_2; "VmBusSendSyncMessage Output failed for "...
0x14028fef9  mov     [rsp+210h+var_1D8], r13
0x14028fefe  mov     [rsp+210h+var_1E0], r13
0x14028ff03  mov     qword ptr [rsp+210h+DataSize], r13
0x14028ff08  mov     [rsp+210h+Data], rbx
0x14028ff0d  mov     cs:WdLogGlobalForLineNumber, 3345h
0x14028ff17  jmp     loc_140290371
0x14028ff1c  mov     rdi, rcx
0x14028ff1f  test    ecx, ecx
0x14028ff21  js      loc_140290333
0x14028ff27  cmp     [r15], r13d
0x14028ff2a  jnz     short loc_14028FF4C
0x14028ff2c  mov     ecx, 3
0x14028ff31  call    cs:__imp_WdLogSingleEntry0
0x14028ff38  nop     dword ptr [rax+rax+00h]
0x14028ff3d  mov     cs:WdLogGlobalForLineNumber, 334Dh
0x14028ff47  jmp     loc_140290381
0x14028ff4c  mov     rcx, [rbx+48h]
0x14028ff50  mov     rcx, [rcx+0D8h]; DeviceObject
0x14028ff57  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x14028ff5e  nop     dword ptr [rax+rax+00h]
0x14028ff63  lea     r8, [rbp+110h+SourceString]
0x14028ff67  xor     edx, edx
0x14028ff69  mov     rcx, rax
0x14028ff6c  mov     rbx, rax
0x14028ff6f  call    DpiGetRegistryPathFromPDO
0x14028ff74  mov     rcx, rbx; Object
0x14028ff77  movsxd  rdi, eax
0x14028ff7a  call    cs:__imp_ObfDereferenceObject
0x14028ff81  nop     dword ptr [rax+rax+00h]
0x14028ff86  test    edi, edi
0x14028ff88  jns     short loc_14028FFB4
0x14028ff8a  mov     rdx, rdi
0x14028ff8d  mov     ecx, 2
0x14028ff92  call    cs:__imp_WdLogSingleEntry1
0x14028ff99  nop     dword ptr [rax+rax+00h]
0x14028ff9e  lea     r9, aFailedToReadPn_0; "Failed to read PnP registry key name fo"...
0x14028ffa5  mov     cs:WdLogGlobalForLineNumber, 3358h
0x14028ffaf  jmp     loc_140290358
0x14028ffb4  mov     eax, dword ptr cs:Source; "\\"
0x14028ffba  lea     rdx, [rsp+210h+var_198]; struct _UNICODE_STRING *
0x14028ffbf  mov     [rsp+210h+var_1B0], eax
0x14028ffc3  lea     rcx, [rbp+110h+SourceString]; struct _UNICODE_STRING *
0x14028ffc7  lea     rax, [rsp+210h+var_1B0]
0x14028ffcc  mov     qword ptr [rsp+210h+var_198.Length], 40002h
0x14028ffd5  mov     [rbp+110h+var_198.Buffer], rax
0x14028ffd9  mov     esi, 2
0x14028ffde  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x14028ffe3  movsxd  rdi, eax
0x14028ffe6  test    eax, eax
0x14028ffe8  jns     short loc_140290011
0x14028ffea  mov     rdx, rdi
0x14028ffed  mov     ecx, esi
0x14028ffef  call    cs:__imp_WdLogSingleEntry1
0x14028fff6  nop     dword ptr [rax+rax+00h]
0x14028fffb  lea     r9, aFailedToConcat; "Failed to concat \\ to RegPathRoot for "...
0x140290002  mov     cs:WdLogGlobalForLineNumber, 3360h
0x14029000c  jmp     loc_140290358
0x140290011  mov     r12d, r13d
0x140290014  cmp     r12d, [r15]
0x140290017  jnb     loc_140290381
0x14029001d  mov     eax, r12d
0x140290020  lea     rbx, [r15+8]
0x140290024  imul    r13, rax, 0C18h
0x14029002b  lea     rdx, [rbp+110h+SourceString]; SourceString
0x14029002f  lea     rcx, [rsp+210h+DestinationString]; DestinationString
0x140290034  add     rbx, r13
0x140290037  call    cs:__imp_RtlCopyUnicodeString
0x14029003e  nop     dword ptr [rax+rax+00h]
0x140290043  xor     ecx, ecx
0x140290045  mov     eax, ecx
0x140290047  mov     [rsp+210h+var_1C0], eax
0x14029004b  lea     rax, [rax+400h]
0x140290052  lea     rax, [rbx+rax*2]
0x140290056  mov     qword ptr [rsp+210h+var_198.Length], rax
0x14029005b  movzx   eax, word ptr [rax]
0x14029005e  test    ax, ax
0x140290061  jz      short loc_1402900D5
0x140290063  cmp     ax, 5Ch ; '\'
0x140290067  jnz     short loc_1402900B0
0x140290069  lea     rax, [rsp+210h+var_1BC]
0x14029006e  mov     [rsp+210h+var_1BC], 1
0x140290076  lea     r9, [rsp+210h+DestinationString]; struct _UNICODE_STRING *
0x14029007b  mov     [rsp+210h+Data], rax; unsigned int *
0x140290080  xor     r8d, r8d; void *
0x140290083  lea     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x140290088  mov     edx, 20006h; DesiredAccess
0x14029008d  call    ?OpenRegistrySubkey@@YAJPEAPEAXKPEAXAEBU_UNICODE_STRING@@PEAK@Z; OpenRegistrySubkey(void * *,ulong,void *,_UNICODE_STRING const &,ulong *)
0x140290092  movsxd  rdi, eax
0x140290095  test    eax, eax
0x140290097  js      loc_14029021E
0x14029009d  mov     rcx, [rsp+210h+KeyHandle]; void *
0x1402900a2  call    ?CloseRegistrySubkey@@YAXPEAX@Z; CloseRegistrySubkey(void *)
0x1402900a7  mov     [rsp+210h+KeyHandle], 0
0x1402900b0  mov     rdx, qword ptr [rsp+210h+var_198.Length]; unsigned __int16 *
0x1402900b5  lea     rcx, [rsp+210h+DestinationString]; struct _UNICODE_STRING *
0x1402900ba  call    ?RtlUnicodeStringCchCatStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCatStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x1402900bf  movsxd  rdi, eax
0x1402900c2  test    eax, eax
0x1402900c4  js      loc_14029025B
0x1402900ca  mov     eax, [rsp+210h+var_1C0]
0x1402900ce  inc     eax
0x1402900d0  jmp     loc_140290047
0x1402900d5  lea     rax, [rsp+210h+var_1BC]
0x1402900da  mov     [rsp+210h+var_1BC], 1
0x1402900e2  lea     r9, [rsp+210h+DestinationString]; struct _UNICODE_STRING *
0x1402900e7  mov     [rsp+210h+Data], rax; unsigned int *
0x1402900ec  xor     r8d, r8d; void *
0x1402900ef  lea     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x1402900f4  mov     edx, 20006h; DesiredAccess
0x1402900f9  call    ?OpenRegistrySubkey@@YAJPEAPEAXKPEAXAEBU_UNICODE_STRING@@PEAK@Z; OpenRegistrySubkey(void * *,ulong,void *,_UNICODE_STRING const &,ulong *)
0x1402900fe  xor     ecx, ecx
0x140290100  movsxd  rdi, eax
0x140290103  test    eax, eax
0x140290105  js      loc_1402902F9
0x14029010b  lea     rax, [rbx+0A08h]
0x140290112  test    rax, rax
0x140290115  jnz     short loc_140290125
0x140290117  cmp     [r15+r13+0C1Ch], ecx
0x14029011f  jz      loc_140290216
0x140290125  mov     ecx, [r15+r13+0C18h]
0x14029012d  lea     eax, [rcx-1]
0x140290130  cmp     eax, 1
0x140290133  jbe     short loc_140290192
0x140290135  cmp     ecx, 7
0x140290138  jnz     short loc_1402901B1
0x14029013a  lea     r8, [rbx+0C14h]; unsigned int *
0x140290141  mov     edx, 400h; unsigned int
0x140290146  mov     rcx, rbx; unsigned __int16 *
0x140290149  call    ?TranslateUmdFileNameToVmMultiString@@YAJPEAGIPEAK@Z; TranslateUmdFileNameToVmMultiString(ushort *,uint,ulong *)
0x14029014e  movsxd  rdi, eax
0x140290151  test    eax, eax
0x140290153  jns     short loc_1402901B1
0x140290155  mov     rdx, rdi
0x140290158  mov     ecx, esi
0x14029015a  call    cs:__imp_WdLogSingleEntry1
0x140290161  nop     dword ptr [rax+rax+00h]
0x140290166  xor     eax, eax
0x140290168  mov     cs:WdLogGlobalForLineNumber, 33ADh
0x140290172  mov     [rsp+210h+var_1D0], rax
0x140290177  lea     r9, aFailedToTransl_0; "Failed to translate UmdFileNames in Mul"...
0x14029017e  mov     [rsp+210h+var_1D8], rax
0x140290183  mov     [rsp+210h+var_1E0], rax
0x140290188  mov     qword ptr [rsp+210h+DataSize], rax
0x14029018d  jmp     loc_14029036C
0x140290192  lea     r8, [rbx+0C14h]; unsigned int *
0x140290199  mov     edx, 400h; unsigned int
0x14029019e  mov     rcx, rbx; unsigned __int16 *
0x1402901a1  call    ?TranslateUmdFileNameToVm@@YAJPEAGIPEAK@Z; TranslateUmdFileNameToVm(ushort *,uint,ulong *)
0x1402901a6  movsxd  rdi, eax
0x1402901a9  test    eax, eax
0x1402901ab  js      loc_1402902BF
0x1402901b1  lea     rdx, [rbx+0A08h]; SourceString
0x1402901b8  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x1402901bc  call    cs:__imp_RtlInitUnicodeString
0x1402901c3  nop     dword ptr [rax+rax+00h]
0x1402901c8  mov     eax, [r15+r13+0C1Ch]
0x1402901d0  lea     rdx, [rbp+110h+ValueName]; ValueName
0x1402901d4  mov     r9d, [r15+r13+0C18h]; Type
0x1402901dc  xor     r8d, r8d; TitleIndex
0x1402901df  mov     rcx, [rsp+210h+KeyHandle]; KeyHandle
0x1402901e4  mov     [rsp+210h+DataSize], eax; DataSize
0x1402901e8  mov     [rsp+210h+Data], rbx; Data
  ... truncated ...
```
