# UpdatePrintQueueDevnode(_INIPRINTER *,int)

- ea: `0x1800c52f0`
- end: `0x1800c56c5`
- name: `?UpdatePrintQueueDevnode@@YAJPEAU_INIPRINTER@@H@Z`
- size: `981`
- prototype: `__int64 __fastcall(struct _INIPRINTER *, int)`
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180051998`
- `0x180058d8c`
- `0x18006eb10`
- `0x1800c30d0`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180014d44`
- `0x1800159d8`
- `0x180015e28`
- `0x180019ba8`
- `0x18001bb38`
- `0x18002049c`
- `0x180025a08`
- `0x180027fcc`
- `0x180031550`
- `0x18003e984`
- `0x18003ea2c`
- `0x180042b7c`
- `0x1800c4420`
- `0x1800c52f0`
- `0x1800cbffc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c5602`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800c5602`
- `SPOOLSS!DllFreeSplStr` at `0x1800c5637`
- `SPOOLSS!DllFreeSplStr` at `0x1800c5637`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800c5454`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800c5454`
- `SPOOLSS!AllocSplStr` at `0x1800c5611`
- `SPOOLSS!AllocSplStr` at `0x1800c5641`
- `SPOOLSS!AllocSplStr` at `0x1800c5611`
- `SPOOLSS!AllocSplStr` at `0x1800c5641`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800c557f`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800c557f`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x1800c566a`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x1800c566a`
- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x1800c549d`
- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x1800c549d`

## string_xrefs

- `0x1800c5485`: `This is a connection installation, wait for the FriendlyName is ready`
- `0x1800c531a`: `UpdatePrintQueueDevnode`
- `0x1800c534f`: `UpdatePrintQueueDevnode`
- `0x1800c53c6`: `UpdatePrintQueueDevnode`
- `0x1800c5442`: `UpdatePrintQueueDevnode`
- `0x1800c548c`: `UpdatePrintQueueDevnode`
- `0x1800c54be`: `UpdatePrintQueueDevnode`
- `0x1800c54d8`: `UpdatePrintQueueDevnode`
- `0x1800c5502`: `UpdatePrintQueueDevnode`
- `0x1800c5569`: `UpdatePrintQueueDevnode`
- `0x1800c5684`: `UpdatePrintQueueDevnode`
- `0x1800c569f`: `UpdatePrintQueueDevnode`
- `0x1800c5698`: `Devnode update failed for printer %ws`
- `0x1800c54aa`: `The time-out interval elapsed, and installation activities are still pending`
- `0x1800c54b7`: `There are no pending installation activities`
- `0x1800c54d1`: `CM_WaitNoPendingInstallEvents failed`

## pseudocode

```c
__int64 __fastcall UpdatePrintQueueDevnode(struct _INIPRINTER *a1, int a2)
{
  __int64 LastErrorAsHResult; // rbx
  unsigned __int16 *v5; // r15
  __int64 v6; // rsi
  signed __int32 v7; // eax
  _DWORD *v8; // r14
  __int64 v9; // rcx
  struct _INIPRINTER *v10; // r13
  const unsigned __int16 *v11; // r8
  NCoreLibrary *v12; // rcx
  DWORD v13; // eax
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // eax
  unsigned __int16 *v16; // rdx
  BOOL v17; // eax
  NCoreLibrary *v18; // rcx
  const wchar_t *DeviceInstanceId; // rax
  wchar_t *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int16 *v24; // [rsp+40h] [rbp-20h] BYREF
  struct _DEVPROPERTY *v25; // [rsp+48h] [rbp-18h] BYREF
  struct _INIPRINTER *v26; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v28; // [rsp+B0h] [rbp+50h] BYREF
  struct _DEVPROPERTY *v29; // [rsp+B8h] [rbp+58h] BYREF

  LODWORD(LastErrorAsHResult) = a1 != 0 ? 0 : 0x80070057;
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "UpdatePrintQueueDevnode",
    L"Enter. hr - 0x%x",
    (unsigned int)LastErrorAsHResult);
  v5 = 0;
  if ( a1 )
  {
    LastErrorAsHResult = (unsigned int)WaitForPrintQueueDevnode(a1, 0);
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "UpdatePrintQueueDevnode",
      L"WaitForPrintQueueDevnode returned with hr -0x%x",
      LastErrorAsHResult);
  }
  if ( (int)LastErrorAsHResult >= 0 )
  {
    v6 = *((_QWORD *)a1 + 62);
    if ( v6 )
    {
      if ( *(_QWORD *)(v6 + 16) )
      {
        do
          v7 = *(_DWORD *)(v6 + 8);
        while ( v7 != 0x7FFFFFFF && v7 != _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 8), v7 + 1, v7) );
        v26 = 0;
        if ( !(unsigned int)CloneIniPrinter(a1, &v26, 1, 4294855518LL) )
        {
          LastErrorAsHResult = (unsigned int)GetLastErrorAsHResult();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "UpdatePrintQueueDevnode",
            L"CloneIniPrinter failed with hr - 0x%x",
            LastErrorAsHResult);
LABEL_49:
          ReleasePrintQueueDevnode((struct DeviceObject *)v6, 0);
          goto LABEL_50;
        }
        v8 = (_DWORD *)((char *)a1 + 16);
        if ( SafeIncrementReference((unsigned int *)a1 + 4) > *((_DWORD *)a1 + 62) )
          *((_DWORD *)a1 + 62) = *v8;
        LeaveSplSem(v9);
        v10 = v26;
        v25 = 0;
        v28 = 0;
        v29 = 0;
        v27 = 0;
        LastErrorAsHResult = (unsigned int)GetPropertiesFromPrinter(v26, 0, &v25, &v28, &v29, &v27, 0);
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "UpdatePrintQueueDevnode",
          L"GetPropertiesFromPrinter returned with hr - 0x%x",
          LastErrorAsHResult);
        if ( (int)LastErrorAsHResult >= 0 )
        {
          v5 = (unsigned __int16 *)RevertToPrinterSelf();
          if ( !v5 )
            LODWORD(LastErrorAsHResult) = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v12);
        }
        if ( (*(_DWORD *)(*((_QWORD *)a1 + 35) + 168LL) & 0x4000000) != 0 || *((_DWORD *)a1 + 134) )
        {
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "UpdatePrintQueueDevnode",
            L"This is a connection installation, wait for the FriendlyName is ready");
          v13 = CMP_WaitNoPendingInstallEvents(0xEA60u);
          if ( v13 == 258 )
          {
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "UpdatePrintQueueDevnode",
              L"The time-out interval elapsed, and installation activities are still pending");
          }
          else if ( v13 )
          {
            if ( v13 == -1 )
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "UpdatePrintQueueDevnode",
                L"CM_WaitNoPendingInstallEvents failed");
          }
          else
          {
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "UpdatePrintQueueDevnode",
              L"There are no pending installation activities");
          }
        }
        if ( (int)LastErrorAsHResult >= 0 )
        {
          LastErrorAsHResult = (unsigned int)DeviceObject::SetProperties((DeviceObject *)v6, v25, v28);
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "UpdatePrintQueueDevnode",
            L"SetProperties returned with hr - 0x%x",
            LastErrorAsHResult);
        }
        v24 = 0;
        if ( (int)LastErrorAsHResult >= 0 )
        {
          v14 = (const unsigned __int16 *)*((_QWORD *)v10 + 64);
          if ( v14 )
          {
            v15 = DeviceObject::SetDeviceInterfaceProperties((DeviceObject *)v6, v14, v29, v27);
            v16 = L"SetDeviceInterfaceProperties returned with hr - 0x%x";
          }
          else
          {
            v15 = DeviceObject::RegisterDeviceInterface((DeviceObject *)v6, 0, v11, v29, v27, a2, &v24);
            v16 = L"RegisterDeviceInterface returned with hr - 0x%x";
          }
          LODWORD(LastErrorAsHResult) = v15;
          LocalSpoolerTelemetry::WriteDbgTraceInfo("UpdatePrintQueueDevnode", v16, v15);
        }
        if ( v5 )
        {
          v17 = ImpersonatePrinterClient(v5);
          v5 = 0;
          if ( !v17 && (int)LastErrorAsHResult >= 0 )
            LODWORD(LastErrorAsHResult) = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v18);
        }
        FreeDevPropertyList(v25, v28);
        FreeDevPropertyList(v29, v27);
        FreeClonedIniPrinterWithMask(v10, 1, 4294855518LL);
        EnterSplSem(0);
        if ( *v8 != (_DWORD)v5 )
          SafeDecrementReference((unsigned int *)a1 + 4);
        if ( (int)LastErrorAsHResult < 0 )
        {
LABEL_47:
          if ( v24 )
            SwMemFree();
          goto LABEL_49;
        }
        if ( *((unsigned __int16 **)a1 + 63) == v5 )
        {
          DeviceInstanceId = DeviceObject::GetDeviceInstanceId((DeviceObject *)v6);
          v20 = wcsrchr(DeviceInstanceId, 0x5Cu);
          if ( v20 )
          {
            v21 = AllocSplStr(v20 + 1);
            *((_QWORD *)a1 + 63) = v21;
            if ( !v21 )
            {
LABEL_46:
              LODWORD(LastErrorAsHResult) = -2147024882;
              goto LABEL_47;
            }
            *((_DWORD *)a1 + 100) &= ~0x8000u;
          }
        }
        if ( v24 == v5 )
          goto LABEL_49;
        DllFreeSplStr(*((_QWORD *)a1 + 64));
        v22 = AllocSplStr(v24);
        *((_QWORD *)a1 + 64) = v22;
        if ( v22 )
        {
          *((_DWORD *)a1 + 100) &= ~0x8000u;
          goto LABEL_47;
        }
        goto LABEL_46;
      }
    }
  }
LABEL_50:
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "UpdatePrintQueueDevnode",
    L"Exit with hr - 0x%x",
    (unsigned int)LastErrorAsHResult);
  if ( (int)LastErrorAsHResult < 0 )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "UpdatePrintQueueDevnode",
      L"Devnode update failed for printer %ws",
      *((_QWORD *)a1 + 3));
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x1800c52f0  mov     [rsp-38h+arg_8], rbx
0x1800c52f5  push    rbp
0x1800c52f6  push    rsi
0x1800c52f7  push    rdi
0x1800c52f8  push    r12
0x1800c52fa  push    r13
0x1800c52fc  push    r14
0x1800c52fe  push    r15
0x1800c5300  mov     rbp, rsp
0x1800c5303  sub     rsp, 60h
0x1800c5307  mov     rax, rcx
0x1800c530a  mov     r12d, edx
0x1800c530d  neg     rax
0x1800c5310  lea     rdx, aEnterHr0xX; "Enter. hr - 0x%x"
0x1800c5317  mov     rdi, rcx
0x1800c531a  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c5321  sbb     ebx, ebx
0x1800c5323  not     ebx
0x1800c5325  and     ebx, 80070057h
0x1800c532b  mov     r8d, ebx
0x1800c532e  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c5333  xor     r15d, r15d
0x1800c5336  test    rdi, rdi
0x1800c5339  jz      short loc_1800C535D
0x1800c533b  xor     edx, edx; int
0x1800c533d  mov     rcx, rdi; struct _INIPRINTER *
0x1800c5340  call    ?WaitForPrintQueueDevnode@@YAJPEAU_INIPRINTER@@H@Z; WaitForPrintQueueDevnode(_INIPRINTER *,int)
0x1800c5345  mov     r8d, eax
0x1800c5348  lea     rdx, aWaitforprintqu; "WaitForPrintQueueDevnode returned with "...
0x1800c534f  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c5356  mov     ebx, eax
0x1800c5358  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c535d  test    ebx, ebx
0x1800c535f  js      loc_1800C567A
0x1800c5365  mov     rsi, [rdi+1F0h]
0x1800c536c  test    rsi, rsi
0x1800c536f  jz      loc_1800C567A
0x1800c5375  cmp     [rsi+10h], r15
0x1800c5379  jz      loc_1800C567A
0x1800c537f  mov     edx, 7FFFFFFFh
0x1800c5384  jmp     short loc_1800C5390
0x1800c5386  lea     ecx, [rax+1]
0x1800c5389  lock cmpxchg [rsi+8], ecx
0x1800c538e  jz      short loc_1800C5397
0x1800c5390  mov     eax, [rsi+8]
0x1800c5393  cmp     eax, edx
0x1800c5395  jnz     short loc_1800C5386
0x1800c5397  mov     r9d, 0FFFE4B5Eh
0x1800c539d  mov     [rbp+var_10], r15
0x1800c53a1  mov     r8d, 1
0x1800c53a7  lea     rdx, [rbp+var_10]
0x1800c53ab  mov     rcx, rdi
0x1800c53ae  call    CloneIniPrinter
0x1800c53b3  test    eax, eax
0x1800c53b5  jnz     short loc_1800C53D9
0x1800c53b7  call    GetLastErrorAsHResult
0x1800c53bc  mov     r8d, eax
0x1800c53bf  lea     rdx, aCloneiniprinte; "CloneIniPrinter failed with hr - 0x%x"
0x1800c53c6  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c53cd  mov     ebx, eax
0x1800c53cf  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c53d4  jmp     loc_1800C5670
0x1800c53d9  lea     r14, [rdi+10h]
0x1800c53dd  mov     rcx, r14; unsigned int *
0x1800c53e0  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x1800c53e5  cmp     eax, [rdi+0F8h]
0x1800c53eb  jbe     short loc_1800C53F6
0x1800c53ed  mov     eax, [r14]
0x1800c53f0  mov     [rdi+0F8h], eax
0x1800c53f6  call    LeaveSplSem
0x1800c53fb  mov     r13, [rbp+var_10]
0x1800c53ff  lea     rax, [rbp+arg_0]
0x1800c5403  mov     [rsp+60h+var_30], r15; struct TString *
0x1800c5408  lea     r9, [rbp+arg_10]; unsigned int *
0x1800c540c  mov     [rsp+60h+var_38], rax; unsigned int *
0x1800c5411  lea     r8, [rbp+var_18]; struct _DEVPROPERTY **
0x1800c5415  lea     rax, [rbp+arg_18]
0x1800c5419  mov     [rbp+var_18], r15
0x1800c541d  xor     edx, edx; DeviceInstanceId
0x1800c541f  mov     [rsp+60h+var_40], rax; struct _DEVPROPERTY **
0x1800c5424  mov     rcx, r13; struct _INIPRINTER *
0x1800c5427  mov     [rbp+arg_10], r15d
0x1800c542b  mov     [rbp+arg_18], r15
0x1800c542f  mov     [rbp+arg_0], r15d
0x1800c5433  call    ?GetPropertiesFromPrinter@@YAJPEAU_INIPRINTER@@PEBGPEAPEAU_DEVPROPERTY@@PEAK23PEAVTString@NCoreLibrary@@@Z; GetPropertiesFromPrinter(_INIPRINTER *,ushort const *,_DEVPROPERTY * *,ulong *,_DEVPROPERTY * *,ulong *,NCoreLibrary::TString *)
0x1800c5438  mov     r8d, eax
0x1800c543b  lea     rdx, aGetpropertiesf; "GetPropertiesFromPrinter returned with "...
0x1800c5442  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c5449  mov     ebx, eax
0x1800c544b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c5450  test    ebx, ebx
0x1800c5452  js      short loc_1800C5469
0x1800c5454  call    cs:__imp_RevertToPrinterSelf
0x1800c545a  mov     r15, rax
0x1800c545d  test    rax, rax
0x1800c5460  jnz     short loc_1800C5469
0x1800c5462  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800c5467  mov     ebx, eax
0x1800c5469  mov     rcx, [rdi+118h]
0x1800c5470  test    dword ptr [rcx+0A8h], 4000000h
0x1800c547a  jnz     short loc_1800C5485
0x1800c547c  cmp     dword ptr [rdi+218h], 0
0x1800c5483  jz      short loc_1800C54E4
0x1800c5485  lea     rdx, aThisIsAConnect; "This is a connection installation, wait"...
0x1800c548c  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c5493  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c5498  mov     ecx, 0EA60h; dwTimeout
0x1800c549d  call    cs:__imp_CMP_WaitNoPendingInstallEvents
0x1800c54a3  cmp     eax, 102h
0x1800c54a8  jnz     short loc_1800C54B3
0x1800c54aa  lea     rdx, aTheTimeOutInte; "The time-out interval elapsed, and inst"...
0x1800c54b1  jmp     short loc_1800C54BE
0x1800c54b3  test    eax, eax
0x1800c54b5  jnz     short loc_1800C54CC
0x1800c54b7  lea     rdx, aThereAreNoPend; "There are no pending installation activ"...
0x1800c54be  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c54c5  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c54ca  jmp     short loc_1800C54E4
0x1800c54cc  cmp     eax, 0FFFFFFFFh
0x1800c54cf  jnz     short loc_1800C54E4
0x1800c54d1  lea     rdx, aCmWaitnopendin; "CM_WaitNoPendingInstallEvents failed"
0x1800c54d8  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c54df  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c54e4  test    ebx, ebx
0x1800c54e6  js      short loc_1800C5510
0x1800c54e8  mov     r8d, [rbp+arg_10]; unsigned int
0x1800c54ec  mov     rcx, rsi; this
0x1800c54ef  mov     rdx, [rbp+var_18]; struct _DEVPROPERTY *
0x1800c54f3  call    ?SetProperties@DeviceObject@@QEAAJPEBU_DEVPROPERTY@@K@Z; DeviceObject::SetProperties(_DEVPROPERTY const *,ulong)
0x1800c54f8  mov     r8d, eax
0x1800c54fb  lea     rdx, aSetpropertiesR; "SetProperties returned with hr - 0x%x"
0x1800c5502  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c5509  mov     ebx, eax
0x1800c550b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c5510  mov     [rbp+var_20], 0
0x1800c5518  test    ebx, ebx
0x1800c551a  js      short loc_1800C5577
0x1800c551c  mov     rdx, [r13+200h]; struct _GUID *
0x1800c5523  mov     rcx, rsi; this
0x1800c5526  test    rdx, rdx
0x1800c5529  jz      short loc_1800C5541
0x1800c552b  mov     r9d, [rbp+arg_0]; unsigned int
0x1800c552f  mov     r8, [rbp+arg_18]; struct _DEVPROPERTY *
0x1800c5533  call    ?SetDeviceInterfaceProperties@DeviceObject@@QEAAJPEBGPEBU_DEVPROPERTY@@K@Z; DeviceObject::SetDeviceInterfaceProperties(ushort const *,_DEVPROPERTY const *,ulong)
0x1800c5538  lea     rdx, aSetdeviceinter; "SetDeviceInterfaceProperties returned w"...
0x1800c553f  jmp     short loc_1800C5566
0x1800c5541  mov     r9, [rbp+arg_18]; struct _DEVPROPERTY *
0x1800c5545  lea     rax, [rbp+var_20]
0x1800c5549  mov     [rsp+60h+var_30], rax; unsigned __int16 **
0x1800c554e  mov     eax, [rbp+arg_0]
0x1800c5551  mov     dword ptr [rsp+60h+var_38], r12d; int
0x1800c5556  mov     dword ptr [rsp+60h+var_40], eax; unsigned int
0x1800c555a  call    ?RegisterDeviceInterface@DeviceObject@@QEAAJPEBU_GUID@@PEBGPEBU_DEVPROPERTY@@KHPEAPEAG@Z; DeviceObject::RegisterDeviceInterface(_GUID const *,ushort const *,_DEVPROPERTY const *,ulong,int,ushort * *)
0x1800c555f  lea     rdx, aRegisterdevice; "RegisterDeviceInterface returned with h"...
0x1800c5566  mov     r8d, eax
0x1800c5569  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c5570  mov     ebx, eax
0x1800c5572  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c5577  test    r15, r15
0x1800c557a  jz      short loc_1800C5597
0x1800c557c  mov     rcx, r15; hToken
0x1800c557f  call    cs:__imp_ImpersonatePrinterClient
0x1800c5585  xor     r15d, r15d
0x1800c5588  test    eax, eax
0x1800c558a  jnz     short loc_1800C5597
0x1800c558c  test    ebx, ebx
0x1800c558e  js      short loc_1800C5597
0x1800c5590  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800c5595  mov     ebx, eax
0x1800c5597  mov     edx, [rbp+arg_10]; unsigned int
0x1800c559a  mov     rcx, [rbp+var_18]; struct _DEVPROPERTY *
0x1800c559e  call    ?FreeDevPropertyList@@YAXPEAU_DEVPROPERTY@@K@Z; FreeDevPropertyList(_DEVPROPERTY *,ulong)
0x1800c55a3  mov     edx, [rbp+arg_0]; unsigned int
0x1800c55a6  mov     rcx, [rbp+arg_18]; struct _DEVPROPERTY *
0x1800c55aa  call    ?FreeDevPropertyList@@YAXPEAU_DEVPROPERTY@@K@Z; FreeDevPropertyList(_DEVPROPERTY *,ulong)
0x1800c55af  mov     edx, 1
0x1800c55b4  mov     r8d, 0FFFE4B5Eh
0x1800c55ba  mov     rcx, r13
0x1800c55bd  call    FreeClonedIniPrinterWithMask
0x1800c55c2  xor     ecx, ecx
0x1800c55c4  call    EnterSplSem
0x1800c55c9  cmp     [r14], r15d
0x1800c55cc  jz      short loc_1800C55D6
0x1800c55ce  mov     rcx, r14; unsigned int *
0x1800c55d1  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800c55d6  test    ebx, ebx
0x1800c55d8  js      loc_1800C5661
0x1800c55de  mov     r12d, 0FFFF7FFFh
0x1800c55e4  cmp     [rdi+1F8h], r15
0x1800c55eb  jnz     short loc_1800C562A
0x1800c55ed  mov     rcx, rsi; this
0x1800c55f0  mov     r14d, 5Ch ; '\'
0x1800c55f6  call    ?GetDeviceInstanceId@DeviceObject@@QEBAPEBGXZ; DeviceObject::GetDeviceInstanceId(void)
0x1800c55fb  mov     rcx, rax; Str
0x1800c55fe  movzx   edx, r14w; Ch
0x1800c5602  call    cs:__imp_wcsrchr
0x1800c5608  test    rax, rax
0x1800c560b  jz      short loc_1800C562A
0x1800c560d  lea     rcx, [rax+2]
0x1800c5611  call    cs:__imp_AllocSplStr
0x1800c5617  mov     [rdi+1F8h], rax
0x1800c561e  test    rax, rax
0x1800c5621  jz      short loc_1800C565C
0x1800c5623  and     [rdi+190h], r12d
0x1800c562a  cmp     [rbp+var_20], r15
0x1800c562e  jz      short loc_1800C5670
0x1800c5630  mov     rcx, [rdi+200h]
0x1800c5637  call    cs:__imp_DllFreeSplStr
0x1800c563d  mov     rcx, [rbp+var_20]
0x1800c5641  call    cs:__imp_AllocSplStr
0x1800c5647  mov     [rdi+200h], rax
0x1800c564e  test    rax, rax
0x1800c5651  jz      short loc_1800C565C
0x1800c5653  and     [rdi+190h], r12d
0x1800c565a  jmp     short loc_1800C5661
0x1800c565c  mov     ebx, 8007000Eh
0x1800c5661  mov     rcx, [rbp+var_20]
0x1800c5665  test    rcx, rcx
0x1800c5668  jz      short loc_1800C5670
0x1800c566a  call    cs:__imp_SwMemFree
0x1800c5670  xor     edx, edx; int
0x1800c5672  mov     rcx, rsi; this
0x1800c5675  call    ?ReleasePrintQueueDevnode@@YAJPEAVDeviceObject@@H@Z; ReleasePrintQueueDevnode(DeviceObject *,int)
0x1800c567a  mov     r8d, ebx
0x1800c567d  lea     rdx, aExitWithHr0xX; "Exit with hr - 0x%x"
0x1800c5684  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c568b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c5690  test    ebx, ebx
0x1800c5692  jns     short loc_1800C56AB
0x1800c5694  mov     r8, [rdi+18h]
0x1800c5698  lea     rdx, aDevnodeUpdateF; "Devnode update failed for printer %ws"
0x1800c569f  lea     rcx, aUpdateprintque; "UpdatePrintQueueDevnode"
0x1800c56a6  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800c56ab  mov     eax, ebx
0x1800c56ad  mov     rbx, [rsp+60h+arg_8]
0x1800c56b5  add     rsp, 60h
0x1800c56b9  pop     r15
0x1800c56bb  pop     r14
0x1800c56bd  pop     r13
0x1800c56bf  pop     r12
0x1800c56c1  pop     rdi
0x1800c56c2  pop     rsi
0x1800c56c3  pop     rbp
0x1800c56c4  retn
```
