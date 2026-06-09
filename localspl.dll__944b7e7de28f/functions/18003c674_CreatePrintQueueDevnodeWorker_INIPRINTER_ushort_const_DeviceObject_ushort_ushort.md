# CreatePrintQueueDevnodeWorker(_INIPRINTER *,ushort const *,DeviceObject * *,ushort * *,ushort * *)

- ea: `0x18003c674`
- end: `0x18003ce12`
- name: `?CreatePrintQueueDevnodeWorker@@YAJPEAU_INIPRINTER@@PEBGPEAPEAVDeviceObject@@PEAPEAG3@Z`
- size: `1950`
- prototype: `__int64 __usercall@<rax>(struct _INIPRINTER *@<rcx>, PCWSTR DeviceInstanceId@<rdx>, struct DeviceObject **@<r8>, unsigned __int16 **@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003c444`

## callees

- `0x180011e64`
- `0x180011ed0`
- `0x180014ce0`
- `0x180014d44`
- `0x180014d9c`
- `0x180014dd4`
- `0x180015e28`
- `0x1800164d8`
- `0x1800166b4`
- `0x18001683c`
- `0x180017ee0`
- `0x180019c90`
- `0x18001b058`
- `0x180029d10`
- `0x180031550`
- `0x18003c674`
- `0x18003e984`
- `0x18003ea2c`
- `0x180046a5c`
- `0x180046aa0`
- `0x180054638`
- `0x1800c2d74`
- `0x1800c2e60`
- `0x1800c3c4c`
- `0x1800c3dd4`
- `0x1800c40dc`
- `0x1800c4420`
- `0x1800cf268`
- `0x1800cf2bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c8a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003c8a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003c84a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003c84a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003cb55`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003cb55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003cc72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003cc72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cc85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cc85`
- `SPOOLSS!DllFreeSplStr` at `0x18003cd48`
- `SPOOLSS!DllFreeSplStr` at `0x18003cd5f`
- `SPOOLSS!DllFreeSplStr` at `0x18003cd48`
- `SPOOLSS!DllFreeSplStr` at `0x18003cd5f`
- `SPOOLSS!RevertToPrinterSelf` at `0x18003c73c`
- `SPOOLSS!RevertToPrinterSelf` at `0x18003c73c`
- `SPOOLSS!AllocSplStr` at `0x18003cd11`
- `SPOOLSS!AllocSplStr` at `0x18003cdf5`
- `SPOOLSS!AllocSplStr` at `0x18003cd11`
- `SPOOLSS!AllocSplStr` at `0x18003cdf5`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18003ccba`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18003ccba`

## string_xrefs

- `0x18003c6c7`: `CreatePrintQueueDevnodeWorker`
- `0x18003c770`: `CreatePrintQueueDevnodeWorker`
- `0x18003c7bd`: `CreatePrintQueueDevnodeWorker`
- `0x18003c820`: `CreatePrintQueueDevnodeWorker`
- `0x18003c915`: `CreatePrintQueueDevnodeWorker`
- `0x18003c943`: `CreatePrintQueueDevnodeWorker`
- `0x18003ca0e`: `CreatePrintQueueDevnodeWorker`
- `0x18003ca35`: `CreatePrintQueueDevnodeWorker`
- `0x18003cd89`: `CreatePrintQueueDevnodeWorker`
- `0x18003c7b6`: `ParentInstancePath : %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CreatePrintQueueDevnodeWorker(
        struct _INIPRINTER *a1,
        PCWSTR DeviceInstanceId,
        struct DeviceObject **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  signed int PropertiesFromPrinter; // ebx
  struct TString *v9; // rdx
  NCoreLibrary *v10; // rcx
  char Data1; // r15
  int v12; // r12d
  void *v13; // rax
  struct _DEVPROPERTY *v14; // rsi
  __int64 v15; // rsi
  void *v16; // rax
  struct _DEVPROPERTY *v17; // rbx
  void *v18; // rax
  __int64 v19; // rbx
  struct TString *v20; // r8
  __int64 v21; // rax
  const unsigned __int16 *v22; // rcx
  char v23; // r12
  const unsigned __int16 *v24; // rdx
  struct TString *v25; // rdx
  NCoreLibrary::TString *v26; // rcx
  int v27; // eax
  const unsigned __int16 *v28; // rdx
  const unsigned __int16 *v29; // rcx
  void *v30; // rsi
  HANDLE EventW; // rax
  NCoreLibrary *v32; // rcx
  const wchar_t *v33; // r10
  const unsigned __int16 *v34; // r8
  __int64 v35; // rdx
  const wchar_t *v36; // rcx
  void *v37; // rcx
  DWORD v38; // eax
  signed int LastError; // eax
  NCoreLibrary *v40; // rcx
  unsigned int v41; // edx
  unsigned __int16 **v42; // r14
  struct DeviceObject **v43; // r15
  unsigned __int16 *v44; // rax
  NCoreLibrary::TString *v45; // rcx
  NCoreLibrary::TString *v46; // rcx
  NCoreLibrary::TString *v47; // rcx
  __int64 v49; // rcx
  __int64 v50; // rax
  unsigned int v51; // [rsp+80h] [rbp-41h] BYREF
  struct _GUID v52; // [rsp+88h] [rbp-39h] BYREF
  struct _GUID v53; // [rsp+98h] [rbp-29h] BYREF
  struct _DEVPROPERTY *v54; // [rsp+A8h] [rbp-19h] BYREF
  struct DeviceObject *v55; // [rsp+B0h] [rbp-11h] BYREF
  void *v56; // [rsp+B8h] [rbp-9h] BYREF
  struct _DEVPROPERTY *v57; // [rsp+C0h] [rbp-1h] BYREF
  struct _DEVPROPERTY *v58; // [rsp+C8h] [rbp+7h] BYREF
  HANDLE hToken; // [rsp+D0h] [rbp+Fh]
  struct _GUID v60; // [rsp+120h] [rbp+5Fh] BYREF
  struct DeviceObject **v61; // [rsp+130h] [rbp+6Fh]

  v61 = a3;
  if ( a1 && a3 )
    PropertiesFromPrinter = 0;
  else
    PropertiesFromPrinter = -2147024809;
  v55 = 0;
  LocalSpoolerTelemetry::WriteDbgTraceInfo("CreatePrintQueueDevnodeWorker", L"pName: %ws", *((_QWORD *)a1 + 3));
  v54 = 0;
  *(_DWORD *)v52.Data4 = 0;
  *(_QWORD *)v53.Data4 = 0;
  v51 = 0;
  v56 = &NCoreLibrary::TString::gszNullState;
  if ( PropertiesFromPrinter >= 0 )
    PropertiesFromPrinter = GetPropertiesFromPrinter(
                              a1,
                              DeviceInstanceId,
                              &v54,
                              (unsigned int *)v52.Data4,
                              (struct _DEVPROPERTY **)v53.Data4,
                              &v51,
                              (struct TString *)&v56);
  hToken = 0;
  if ( PropertiesFromPrinter >= 0 )
  {
    hToken = RevertToPrinterSelf();
    if ( !hToken )
      PropertiesFromPrinter = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v10);
  }
  Data1 = 0;
  LOBYTE(v60.Data1) = 0;
  if ( PropertiesFromPrinter >= 0 && *((_QWORD *)a1 + 63) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo("CreatePrintQueueDevnodeWorker", L"%QueueInstanceId : %ws");
    PropertiesFromPrinter = DeviceObject::DoesDeviceExist(*((const unsigned __int16 **)a1 + 63), (bool *)&v60);
    Data1 = v60.Data1;
  }
  v12 = 0;
  *(_QWORD *)&v52.Data1 = &NCoreLibrary::TString::gszNullState;
  if ( PropertiesFromPrinter >= 0 && !Data1 && DeviceInstanceId )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "CreatePrintQueueDevnodeWorker",
      L"ParentInstancePath : %ws",
      DeviceInstanceId);
    v60.Data1 = 52;
    v13 = operator new[](0x34u);
    NCoreLibrary::TAutoPtr<unsigned char>::TAutoPtr<unsigned char>(&v57, v13);
    v14 = v57;
    PropertiesFromPrinter = DeviceObject::GetProperty(
                              DeviceInstanceId,
                              (DEVPROPKEY *)&DEVPKEY_Device_DevNodeStatus,
                              v57,
                              0x34u,
                              &v60.Data1);
    if ( PropertiesFromPrinter < 0
      || (v15 = *(unsigned int *)v14->Buffer,
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "CreatePrintQueueDevnodeWorker",
            L"DevNodeStatus for %ws is %u",
            DeviceInstanceId,
            v15),
          (v15 & 8) == 0)
      && ((v15 & 1) != 0 || !(unsigned int)_o__wcsnicmp(DeviceInstanceId, L"USBPRINT", 8)) )
    {
      v60.Data1 = 308;
      v16 = operator new[](0x134u);
      NCoreLibrary::TAutoPtr<unsigned char>::TAutoPtr<unsigned char>(&v58, v16);
      v17 = v58;
      if ( (int)DeviceObject::GetProperty(
                  DeviceInstanceId,
                  (DEVPROPKEY *)&DEVPKEY_Device_Parent,
                  v58,
                  0x134u,
                  &v60.Data1) >= 0
        && (unsigned int)_o__wcsicmp(v17->Buffer, L"HTREE\\ROOT\\0") )
      {
        v60.Data1 = 64;
        v18 = operator new[](0x40u);
        NCoreLibrary::TAutoPtr<unsigned char>::TAutoPtr<unsigned char>(&v53, v18);
        v19 = *(_QWORD *)&v53.Data1;
        if ( (int)DeviceObject::GetProperty(
                    DeviceInstanceId,
                    (DEVPROPKEY *)&DEVPKEY_Device_ContainerId,
                    *(struct _DEVPROPERTY **)&v53.Data1,
                    0x40u,
                    &v60.Data1) >= 0 )
        {
          if ( NCoreLibrary::ClsidToString(*(NCoreLibrary **)(v19 + 40), &v52, v20) < 0 )
          {
            NCoreLibrary::TString::Update((NCoreLibrary::TString *)&v52, 0);
          }
          else
          {
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "CreatePrintQueueDevnodeWorker",
              L"Using container id: %ws",
              *(_QWORD *)&v52.Data1);
            v12 = 1;
          }
        }
        NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtr<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v53);
      }
      LocalSpoolerTelemetry::WriteDbgTraceWarning("CreatePrintQueueDevnodeWorker", L"Clearing parent information!");
      DeviceInstanceId = 0;
      PropertiesFromPrinter = 0;
      NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtr<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v58);
    }
    NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtr<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v57);
  }
  *(_QWORD *)&v53.Data1 = &NCoreLibrary::TString::gszNullState;
  if ( PropertiesFromPrinter < 0 )
    goto LABEL_47;
  if ( *((_QWORD *)a1 + 63) )
  {
LABEL_42:
    v23 = 0;
    goto LABEL_43;
  }
  PropertiesFromPrinter = NCoreLibrary::GetGuidString(&v53, v9);
  if ( PropertiesFromPrinter < 0 )
  {
LABEL_47:
    v23 = 0;
    goto LABEL_48;
  }
  if ( DeviceInstanceId )
    goto LABEL_42;
  if ( v12 )
  {
    v23 = 0;
  }
  else
  {
    v21 = *((_QWORD *)a1 + 11);
    v22 = *(const unsigned __int16 **)(v21 + 144);
    v23 = 0;
    if ( !v22 )
      v22 = *(const unsigned __int16 **)(v21 + 24);
    v24 = 0;
    if ( *((_DWORD *)a1 + 77) )
      v24 = *(const unsigned __int16 **)(**((_QWORD **)a1 + 39) + 24LL);
    PropertiesFromPrinter = GenerateContainerIdFromString(v22, v24, &v52);
    if ( PropertiesFromPrinter < 0 )
    {
      PropertiesFromPrinter = NCoreLibrary::GetGuidString(&v52, v25);
      if ( PropertiesFromPrinter < 0 )
        goto LABEL_48;
LABEL_43:
      if ( DeviceInstanceId )
        goto LABEL_48;
    }
  }
  *(_QWORD *)&v60.Data1 = &NCoreLibrary::TString::gszNullState;
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "CreatePrintQueueDevnodeWorker",
    L"Checking for Migrated ContainerId for: %ws",
    *((_QWORD *)a1 + 3));
  if ( !(unsigned int)CheckAndRetrieveMigratedContainerId(a1, &v60) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "CreatePrintQueueDevnodeWorker",
      L"Migrated Container Id retrieved successfully for: %ws ",
      *((_QWORD *)a1 + 3));
    NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v52, *(const unsigned __int16 **)&v60.Data1);
  }
  NCoreLibrary::TString::vFree(v26, *(void **)&v60.Data1);
LABEL_48:
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 35) + 168LL) & 0x4000000) != 0 || (v27 = 0, *((_DWORD *)a1 + 134)) )
    v27 = 1;
  if ( PropertiesFromPrinter >= 0 && *((_QWORD *)a1 + 63) && v27 )
    GenerateContainerId(a1, (struct TString *)&v52);
  NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(&v60, 0);
  if ( PropertiesFromPrinter >= 0 && !Data1 )
  {
    if ( DeviceInstanceId )
    {
      v28 = 0;
      v29 = 0;
    }
    else
    {
      v28 = *(const unsigned __int16 **)(*((_QWORD *)a1 + 11) + 144LL);
      v29 = (const unsigned __int16 *)((unsigned __int64)v56 & -(__int64)(*(_WORD *)v56 != 0));
    }
    PropertiesFromPrinter = GenerateHardwareIdList(v29, v28, (unsigned __int16 **)&v60);
  }
  v30 = 0;
  if ( PropertiesFromPrinter >= 0 )
  {
    v30 = operator new(0x28u);
    v57 = (struct _DEVPROPERTY *)v30;
    *(_QWORD *)v30 = -1;
    *((_QWORD *)v30 + 1) = 0;
    *((_DWORD *)v30 + 4) = 0;
    *((_BYTE *)v30 + 20) = 0;
    *((_DWORD *)v30 + 6) = -2147467259;
    *((_QWORD *)v30 + 4) = 0;
    NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(v30);
    *(_QWORD *)v30 = -1;
    *((_QWORD *)v30 + 1) = *(_QWORD *)v53.Data4;
    *(_QWORD *)v53.Data4 = 0;
    *((_DWORD *)v30 + 4) = v51;
    v51 = 0;
    *((_DWORD *)v30 + 6) = 0;
    *((_QWORD *)v30 + 4) = 0;
    *((_BYTE *)v30 + 20) = 0;
    EventW = CreateEventW(0, 1, 0, 0);
    if ( EventW )
    {
      NCoreLibrary::TAutoHandleNT::operator=(v30, EventW);
    }
    else
    {
      PropertiesFromPrinter = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v32);
      if ( PropertiesFromPrinter < 0 )
        goto LABEL_87;
    }
    if ( Data1 && *((_QWORD *)a1 + 64) )
      v23 = 1;
    *((_BYTE *)v30 + 20) = v23;
    v33 = L"GenPrintQueue";
    if ( Data1 )
    {
      v33 = 0;
      v34 = 0;
    }
    else
    {
      v34 = *(const unsigned __int16 **)&v60.Data1;
      if ( !*(_QWORD *)&v60.Data1 )
        v34 = L"PRINTENUM\\LocalPrintQueue";
    }
    v35 = *(_QWORD *)&v53.Data1;
    if ( *((_QWORD *)a1 + 63) )
      v35 = *((_QWORD *)a1 + 63);
    v36 = L"SWD\\PRINTENUM\\PrintQueues";
    if ( DeviceInstanceId )
      v36 = DeviceInstanceId;
    PropertiesFromPrinter = DeviceObject::Create(
                              v36,
                              v35,
                              v34,
                              v33,
                              *(_QWORD *)&v52.Data1 & -(__int64)(**(_WORD **)&v52.Data1 != 0),
                              0,
                              *((_QWORD *)a1 + 18),
                              *((_QWORD *)a1 + 24),
                              DeviceInstanceId == 0,
                              v54,
                              *(_DWORD *)v52.Data4,
                              PrintQueueDevnodeCreationCallback,
                              v30,
                              0,
                              &v55);
    if ( PropertiesFromPrinter >= 0 )
    {
      if ( v23 )
      {
        v30 = 0;
      }
      else
      {
        v37 = *(void **)v30;
        if ( *(_QWORD *)v30 == -1 )
          v37 = 0;
        v38 = WaitForSingleObject(v37, 0xFFFFFFFF);
        if ( v38 )
        {
          if ( v38 == -1 )
          {
            LastError = GetLastError();
            PropertiesFromPrinter = LastError;
            if ( LastError > 0 )
              PropertiesFromPrinter = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            PropertiesFromPrinter = -2147418113;
          }
        }
        else
        {
          PropertiesFromPrinter = *((_DWORD *)v30 + 6);
        }
      }
    }
  }
LABEL_87:
  if ( hToken && !ImpersonatePrinterClient(hToken) && PropertiesFromPrinter >= 0 )
    PropertiesFromPrinter = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v40);
  FreeDevPropertyList(v54, *(unsigned int *)v52.Data4);
  FreeDevPropertyList(*(struct _DEVPROPERTY **)v53.Data4, v51);
  v42 = a5;
  v43 = v61;
  if ( PropertiesFromPrinter >= 0 )
  {
    *v61 = v55;
    if ( !**(_WORD **)&v53.Data1
      || !a4
      || (v44 = (unsigned __int16 *)AllocSplStr(*(_QWORD *)&v53.Data1), (*a4 = v44) != 0) )
    {
      if ( !v30 )
        goto LABEL_107;
      v49 = *((_QWORD *)v30 + 4);
      if ( v49 )
      {
        if ( v42 )
        {
          v50 = AllocSplStr(v49);
          *v42 = (unsigned __int16 *)v50;
          if ( !v50 )
            PropertiesFromPrinter = -2147024882;
        }
      }
LABEL_97:
      PrintQueueDevnodeCreationCallbackContext::`scalar deleting destructor'(
        (PrintQueueDevnodeCreationCallbackContext *)v30,
        v41);
      if ( PropertiesFromPrinter >= 0 )
        goto LABEL_107;
      goto LABEL_98;
    }
    PropertiesFromPrinter = -2147024882;
  }
  if ( v30 )
    goto LABEL_97;
LABEL_98:
  if ( a4 && *a4 )
  {
    DllFreeSplStr(*a4);
    *a4 = 0;
  }
  if ( v42 && *v42 )
  {
    DllFreeSplStr(*v42);
    *v42 = 0;
  }
  if ( v55 )
  {
    ReleasePrintQueueDevnode(v55, 1);
    *v43 = 0;
  }
  LocalSpoolerTelemetry::WriteDbgTraceError(
    "CreatePrintQueueDevnodeWorker",
    L"Devnode creation failed for printer %ws",
    *((_QWORD *)a1 + 3));
LABEL_107:
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v60);
  NCoreLibrary::TString::vFree(v45, *(void **)&v53.Data1);
  NCoreLibrary::TString::vFree(v46, *(void **)&v52.Data1);
  NCoreLibrary::TString::vFree(v47, v56);
  return (unsigned int)PropertiesFromPrinter;
}

```

## disassembly

```asm
0x18003c674  mov     qword ptr [rsp-8+arg_0.Data4], rbx
0x18003c679  mov     [rsp-8+arg_10], r8
0x18003c67e  push    rbp
0x18003c67f  push    rsi
0x18003c680  push    rdi
0x18003c681  push    r12
0x18003c683  push    r13
0x18003c685  push    r14
0x18003c687  push    r15
0x18003c689  lea     rbp, [rsp-1Fh]
0x18003c68e  sub     rsp, 0E0h
0x18003c695  mov     r13, r9
0x18003c698  mov     rax, r8
0x18003c69b  mov     r14, rdx
0x18003c69e  mov     rdi, rcx
0x18003c6a1  test    rcx, rcx
0x18003c6a4  jz      short loc_18003C6AF
0x18003c6a6  test    rax, rax
0x18003c6a9  jz      short loc_18003C6AF
0x18003c6ab  xor     ebx, ebx
0x18003c6ad  jmp     short loc_18003C6B4
0x18003c6af  mov     ebx, 80070057h
0x18003c6b4  mov     [rbp+4Fh+var_60], 0
0x18003c6bc  mov     r8, [rcx+18h]
0x18003c6c0  lea     rdx, aPnameWs; "pName: %ws"
0x18003c6c7  lea     rcx, aCreateprintque_2; "CreatePrintQueueDevnodeWorker"
0x18003c6ce  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003c6d3  mov     [rbp+4Fh+var_68], 0
0x18003c6db  mov     dword ptr [rbp+4Fh+var_88.Data4], 0
0x18003c6e2  mov     qword ptr [rbp+4Fh+var_78.Data4], 0
0x18003c6ea  mov     [rbp+4Fh+var_90], 0
0x18003c6f1  lea     rsi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18003c6f8  mov     [rbp+4Fh+var_58], rsi
0x18003c6fc  test    ebx, ebx
0x18003c6fe  js      short loc_18003C730
0x18003c700  lea     rax, [rbp+4Fh+var_58]
0x18003c704  mov     [rsp+110h+var_E0], rax; struct TString *
0x18003c709  lea     rax, [rbp+4Fh+var_90]
0x18003c70d  mov     [rsp+110h+var_E8], rax; unsigned int *
0x18003c712  lea     rax, [rbp+4Fh+var_78.Data4]
0x18003c716  mov     [rsp+110h+var_F0], rax; struct _DEVPROPERTY **
0x18003c71b  lea     r9, [rbp+4Fh+var_88.Data4]; unsigned int *
0x18003c71f  lea     r8, [rbp+4Fh+var_68]; struct _DEVPROPERTY **
0x18003c723  mov     rdx, r14; DeviceInstanceId
0x18003c726  mov     rcx, rdi; struct _INIPRINTER *
0x18003c729  call    ?GetPropertiesFromPrinter@@YAJPEAU_INIPRINTER@@PEBGPEAPEAU_DEVPROPERTY@@PEAK23PEAVTString@NCoreLibrary@@@Z; GetPropertiesFromPrinter(_INIPRINTER *,ushort const *,_DEVPROPERTY * *,ulong *,_DEVPROPERTY * *,ulong *,NCoreLibrary::TString *)
0x18003c72e  mov     ebx, eax
0x18003c730  mov     [rbp+4Fh+hToken], 0
0x18003c738  test    ebx, ebx
0x18003c73a  js      short loc_18003C752
0x18003c73c  call    cs:__imp_RevertToPrinterSelf
0x18003c742  mov     [rbp+4Fh+hToken], rax
0x18003c746  test    rax, rax
0x18003c749  jnz     short loc_18003C752
0x18003c74b  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x18003c750  mov     ebx, eax
0x18003c752  xor     r15b, r15b
0x18003c755  mov     byte ptr [rbp+4Fh+arg_0.Data1], r15b
0x18003c759  test    ebx, ebx
0x18003c75b  js      short loc_18003C792
0x18003c75d  mov     r8, [rdi+1F8h]
0x18003c764  test    r8, r8
0x18003c767  jz      short loc_18003C792
0x18003c769  lea     rdx, aQueueinstancei; "%QueueInstanceId : %ws"
0x18003c770  lea     rcx, aCreateprintque_2; "CreatePrintQueueDevnodeWorker"
0x18003c777  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003c77c  lea     rdx, [rbp+4Fh+arg_0]; bool *
0x18003c780  mov     rcx, [rdi+1F8h]; unsigned __int16 *
0x18003c787  call    ?DoesDeviceExist@DeviceObject@@SAJPEBGPEA_N@Z; DeviceObject::DoesDeviceExist(ushort const *,bool *)
0x18003c78c  mov     ebx, eax
0x18003c78e  mov     r15b, byte ptr [rbp+4Fh+arg_0.Data1]
0x18003c792  xor     r12d, r12d
0x18003c795  mov     qword ptr [rbp+4Fh+var_88.Data1], rsi
0x18003c799  test    ebx, ebx
0x18003c79b  js      loc_18003C96E
0x18003c7a1  test    r15b, r15b
0x18003c7a4  jnz     loc_18003C96E
0x18003c7aa  test    r14, r14
0x18003c7ad  jz      loc_18003C96E
0x18003c7b3  mov     r8, r14
0x18003c7b6  lea     rdx, aParentinstance; "ParentInstancePath : %ws"
0x18003c7bd  lea     rcx, aCreateprintque_2; "CreatePrintQueueDevnodeWorker"
0x18003c7c4  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003c7c9  lea     ebx, [r12+34h]
0x18003c7ce  mov     [rbp+4Fh+arg_0.Data1], ebx
0x18003c7d1  mov     ecx, ebx; unsigned __int64
0x18003c7d3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c7d8  mov     rdx, rax
0x18003c7db  lea     rcx, [rbp+4Fh+var_50]
0x18003c7df  call    ??0?$TAutoPtr@E@NCoreLibrary@@QEAA@PEAE@Z; NCoreLibrary::TAutoPtr<uchar>::TAutoPtr<uchar>(uchar *)
0x18003c7e4  nop
0x18003c7e5  mov     rsi, [rbp+4Fh+var_50]
0x18003c7e9  lea     rax, [rbp+4Fh+arg_0]
0x18003c7ed  mov     [rsp+110h+var_F0], rax; unsigned int *
0x18003c7f2  mov     r9d, ebx; unsigned int
0x18003c7f5  mov     r8, rsi; struct _DEVPROPERTY *
0x18003c7f8  lea     rdx, DEVPKEY_Device_DevNodeStatus; PropertyKey
0x18003c7ff  mov     rcx, r14; DeviceInstanceId
0x18003c802  call    ?GetProperty@DeviceObject@@SAJPEBGPEBU_DEVPROPKEY@@PEAU_DEVPROPERTY@@KPEAK@Z; DeviceObject::GetProperty(ushort const *,_DEVPROPKEY const *,_DEVPROPERTY *,ulong,ulong *)
0x18003c807  mov     ebx, eax
0x18003c809  test    eax, eax
0x18003c80b  js      short loc_18003C858
0x18003c80d  mov     rax, [rsi+28h]
0x18003c811  mov     esi, [rax]
0x18003c813  mov     r9d, esi
0x18003c816  mov     r8, r14
0x18003c819  lea     rdx, aDevnodestatusF; "DevNodeStatus for %ws is %u"
0x18003c820  lea     rcx, aCreateprintque_2; "CreatePrintQueueDevnodeWorker"
0x18003c827  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003c82c  lea     r8d, [r12+8]
0x18003c831  test    r8b, sil
0x18003c834  jnz     loc_18003C95E
0x18003c83a  test    sil, 1
0x18003c83e  jnz     short loc_18003C858
0x18003c840  lea     rdx, aUsbprint; "USBPRINT"
0x18003c847  mov     rcx, r14
0x18003c84a  call    cs:__imp__o__wcsnicmp
0x18003c850  test    eax, eax
0x18003c852  jnz     loc_18003C95E
0x18003c858  mov     esi, 134h
0x18003c85d  mov     [rbp+4Fh+arg_0.Data1], esi
0x18003c860  mov     ecx, esi; unsigned __int64
0x18003c862  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c867  mov     rdx, rax
0x18003c86a  lea     rcx, [rbp+4Fh+var_48]
0x18003c86e  call    ??0?$TAutoPtr@E@NCoreLibrary@@QEAA@PEAE@Z; NCoreLibrary::TAutoPtr<uchar>::TAutoPtr<uchar>(uchar *)
0x18003c873  nop
0x18003c874  mov     rbx, [rbp+4Fh+var_48]
0x18003c878  lea     rax, [rbp+4Fh+arg_0]
0x18003c87c  mov     [rsp+110h+var_F0], rax; unsigned int *
0x18003c881  mov     r9d, esi; unsigned int
0x18003c884  mov     r8, rbx; struct _DEVPROPERTY *
0x18003c887  lea     rdx, DEVPKEY_Device_Parent; PropertyKey
0x18003c88e  mov     rcx, r14; DeviceInstanceId
0x18003c891  call    ?GetProperty@DeviceObject@@SAJPEBGPEBU_DEVPROPKEY@@PEAU_DEVPROPERTY@@KPEAK@Z; DeviceObject::GetProperty(ushort const *,_DEVPROPKEY const *,_DEVPROPERTY *,ulong,ulong *)
0x18003c896  test    eax, eax
0x18003c898  js      loc_18003C93C
0x18003c89e  lea     rdx, aHtreeRoot0_0; "HTREE\\ROOT\\0"
0x18003c8a5  mov     rcx, [rbx+28h]
0x18003c8a9  call    cs:__imp__o__wcsicmp
0x18003c8af  test    eax, eax
0x18003c8b1  jz      loc_18003C93C
0x18003c8b7  mov     esi, 40h ; '@'
0x18003c8bc  mov     [rbp+4Fh+arg_0.Data1], esi
0x18003c8bf  mov     ecx, esi; unsigned __int64
0x18003c8c1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c8c6  mov     rdx, rax
0x18003c8c9  lea     rcx, [rbp+4Fh+var_78]
0x18003c8cd  call    ??0?$TAutoPtr@E@NCoreLibrary@@QEAA@PEAE@Z; NCoreLibrary::TAutoPtr<uchar>::TAutoPtr<uchar>(uchar *)
0x18003c8d2  nop
0x18003c8d3  mov     rbx, qword ptr [rbp+4Fh+var_78.Data1]
0x18003c8d7  lea     rax, [rbp+4Fh+arg_0]
0x18003c8db  mov     [rsp+110h+var_F0], rax; unsigned int *
0x18003c8e0  mov     r9d, esi; unsigned int
0x18003c8e3  mov     r8, rbx; struct _DEVPROPERTY *
0x18003c8e6  lea     rdx, DEVPKEY_Device_ContainerId; PropertyKey
0x18003c8ed  mov     rcx, r14; DeviceInstanceId
0x18003c8f0  call    ?GetProperty@DeviceObject@@SAJPEBGPEBU_DEVPROPKEY@@PEAU_DEVPROPERTY@@KPEAK@Z; DeviceObject::GetProperty(ushort const *,_DEVPROPKEY const *,_DEVPROPERTY *,ulong,ulong *)
0x18003c8f5  test    eax, eax
0x18003c8f7  js      short loc_18003C933
0x18003c8f9  lea     rdx, [rbp+4Fh+var_88]; struct _GUID *
0x18003c8fd  mov     rcx, [rbx+28h]; this
0x18003c901  call    ?ClsidToString@NCoreLibrary@@YAJAEBU_GUID@@AEAVTString@1@@Z; NCoreLibrary::ClsidToString(_GUID const &,NCoreLibrary::TString &)
0x18003c906  test    eax, eax
0x18003c908  js      short loc_18003C927
0x18003c90a  mov     r8, qword ptr [rbp+4Fh+var_88.Data1]
0x18003c90e  lea     rdx, aUsingContainer; "Using container id: %ws"
0x18003c915  lea     rcx, aCreateprintque_2; "CreatePrintQueueDevnodeWorker"
0x18003c91c  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003c921  lea     r12d, [rsi-3Fh]
0x18003c925  jmp     short loc_18003C933
0x18003c927  xor     edx, edx; unsigned __int16 *
0x18003c929  lea     rcx, [rbp+4Fh+var_88]; this
0x18003c92d  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x18003c932  nop
0x18003c933  lea     rcx, [rbp+4Fh+var_78]
0x18003c937  call    ?Reset@?$TGenericSP@EV?$TAutoPtr@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtr<uchar>,uchar *,0,uchar const *>::Reset(void)
0x18003c93c  lea     rdx, aClearingParent; "Clearing parent information!"
0x18003c943  lea     rcx, aCreateprintque_2; "CreatePrintQueueDevnodeWorker"
0x18003c94a  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18003c94f  xor     r14d, r14d
0x18003c952  xor     ebx, ebx
0x18003c954  lea     rcx, [rbp+4Fh+var_48]
0x18003c958  call    ?Reset@?$TGenericSP@EV?$TAutoPtr@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtr<uchar>,uchar *,0,uchar const *>::Reset(void)
0x18003c95d  nop
0x18003c95e  lea     rcx, [rbp+4Fh+var_50]
0x18003c962  call    ?Reset@?$TGenericSP@EV?$TAutoPtr@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtr<uchar>,uchar *,0,uchar const *>::Reset(void)
0x18003c967  lea     rsi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18003c96e  mov     qword ptr [rbp+4Fh+var_78.Data1], rsi
0x18003c972  test    ebx, ebx
0x18003c974  js      loc_18003CA59
0x18003c97a  cmp     qword ptr [rdi+1F8h], 0
0x18003c982  jnz     short loc_18003C9F7
0x18003c984  lea     rcx, [rbp+4Fh+var_78]; this
0x18003c988  call    ?GetGuidString@NCoreLibrary@@YAJAEAVTString@1@@Z; NCoreLibrary::GetGuidString(NCoreLibrary::TString &)
0x18003c98d  mov     ebx, eax
0x18003c98f  test    eax, eax
0x18003c991  js      loc_18003CA59
0x18003c997  test    r14, r14
0x18003c99a  jnz     short loc_18003C9F7
0x18003c99c  test    r12d, r12d
0x18003c99f  jnz     short loc_18003C9F2
0x18003c9a1  mov     rax, [rdi+58h]
0x18003c9a5  mov     rcx, [rax+90h]
0x18003c9ac  xor     r12d, r12d
0x18003c9af  test    rcx, rcx
0x18003c9b2  jnz     short loc_18003C9B8
0x18003c9b4  mov     rcx, [rax+18h]; unsigned __int16 *
0x18003c9b8  mov     rdx, r12
0x18003c9bb  cmp     [rdi+134h], r12d
0x18003c9c2  jbe     short loc_18003C9D2
0x18003c9c4  mov     rax, [rdi+138h]
0x18003c9cb  mov     rdx, [rax]
0x18003c9ce  mov     rdx, [rdx+18h]; unsigned __int16 *
0x18003c9d2  lea     r8, [rbp+4Fh+var_88]; struct _GUID *
0x18003c9d6  call    ?GenerateContainerIdFromString@@YAJPEBG0AEAVTString@NCoreLibrary@@@Z; GenerateContainerIdFromString(ushort const *,ushort const *,NCoreLibrary::TString &)
0x18003c9db  mov     ebx, eax
0x18003c9dd  test    eax, eax
0x18003c9df  jns     short loc_18003C9FF
0x18003c9e1  lea     rcx, [rbp+4Fh+var_88]; this
0x18003c9e5  call    ?GetGuidString@NCoreLibrary@@YAJAEAVTString@1@@Z; NCoreLibrary::GetGuidString(NCoreLibrary::TString &)
0x18003c9ea  mov     ebx, eax
0x18003c9ec  test    eax, eax
0x18003c9ee  jns     short loc_18003C9FA
0x18003c9f0  jmp     short loc_18003CA5C
0x18003c9f2  xor     r12d, r12d
0x18003c9f5  jmp     short loc_18003C9FF
0x18003c9f7  xor     r12d, r12d
0x18003c9fa  test    r14, r14
0x18003c9fd  jnz     short loc_18003CA5C
0x18003c9ff  mov     qword ptr [rbp+4Fh+arg_0.Data1], rsi
0x18003ca03  mov     r8, [rdi+18h]
0x18003ca07  lea     rdx, aCheckingForMig_0; "Checking for Migrated ContainerId for: "...
0x18003ca0e  lea     rcx, aCreateprintque_2; "CreatePrintQueueDevnodeWorker"
0x18003ca15  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003ca1a  lea     rdx, [rbp+4Fh+arg_0]; struct _GUID *
0x18003ca1e  mov     rcx, rdi; struct _INIPRINTER *
0x18003ca21  call    ?CheckAndRetrieveMigratedContainerId@@YAJPEAU_INIPRINTER@@AEAVTString@NCoreLibrary@@@Z; CheckAndRetrieveMigratedContainerId(_INIPRINTER *,NCoreLibrary::TString &)
0x18003ca26  test    eax, eax
0x18003ca28  jnz     short loc_18003CA4E
0x18003ca2a  mov     r8, [rdi+18h]
0x18003ca2e  lea     rdx, aMigratedContai_0; "Migrated Container Id retrieved success"...
0x18003ca35  lea     rcx, aCreateprintque_2; "CreatePrintQueueDevnodeWorker"
0x18003ca3c  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003ca41  mov     rdx, qword ptr [rbp+4Fh+arg_0.Data1]; unsigned __int16 *
0x18003ca45  lea     rcx, [rbp+4Fh+var_88]; this
0x18003ca49  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x18003ca4e  mov     rdx, qword ptr [rbp+4Fh+arg_0.Data1]; void *
0x18003ca52  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x18003ca57  jmp     short loc_18003CA5C
0x18003ca59  xor     r12d, r12d
0x18003ca5c  mov     rax, [rdi+118h]
0x18003ca63  test    dword ptr [rax+0A8h], 4000000h
0x18003ca6d  jnz     short loc_18003CA7B
0x18003ca6f  cmp     [rdi+218h], r12d
0x18003ca76  mov     eax, r12d
0x18003ca79  jz      short loc_18003CA80
0x18003ca7b  mov     eax, 1
0x18003ca80  test    ebx, ebx
0x18003ca82  js      short loc_18003CA9D
0x18003ca84  cmp     [rdi+1F8h], r12
0x18003ca8b  jz      short loc_18003CA9D
0x18003ca8d  test    eax, eax
0x18003ca8f  jz      short loc_18003CA9D
0x18003ca91  lea     rdx, [rbp+4Fh+var_88]; struct TString *
0x18003ca95  mov     rcx, rdi; struct _INIPRINTER *
0x18003ca98  call    ?GenerateContainerId@@YAJPEAU_INIPRINTER@@AEAVTString@NCoreLibrary@@@Z; GenerateContainerId(_INIPRINTER *,NCoreLibrary::TString &)
0x18003ca9d  xor     edx, edx
0x18003ca9f  lea     rcx, [rbp+4Fh+arg_0]
0x18003caa3  call    ??0?$TAutoPtrArray@UPrintNamedProperty@@@NCoreLibrary@@QEAA@PEAUPrintNamedProperty@@@Z; NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(PrintNamedProperty *)
0x18003caa8  nop
0x18003caa9  test    ebx, ebx
0x18003caab  js      short loc_18003CAE3
0x18003caad  test    r15b, r15b
0x18003cab0  jnz     short loc_18003CAE3
0x18003cab2  lea     r8, [rbp+4Fh+arg_0]; unsigned __int16 **
0x18003cab6  test    r14, r14
0x18003cab9  jz      short loc_18003CAC1
0x18003cabb  xor     edx, edx
0x18003cabd  xor     ecx, ecx
0x18003cabf  jmp     short loc_18003CADC
0x18003cac1  mov     rax, [rdi+58h]
0x18003cac5  mov     rdx, [rax+90h]; unsigned __int16 *
0x18003cacc  mov     rax, [rbp+4Fh+var_58]
0x18003cad0  movzx   ecx, word ptr [rax]
0x18003cad3  neg     cx
0x18003cad6  sbb     rcx, rcx
0x18003cad9  and     rcx, rax; unsigned __int16 *
0x18003cadc  call    ?GenerateHardwareIdList@@YAJPEBG0PEAPEAG@Z; GenerateHardwareIdList(ushort const *,ushort const *,ushort * *)
0x18003cae1  mov     ebx, eax
0x18003cae3  mov     rsi, r12
0x18003cae6  test    ebx, ebx
0x18003cae8  js      loc_18003CCAE
0x18003caee  mov     ecx, 28h ; '('; Size
0x18003caf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003caf8  mov     rsi, rax
0x18003cafb  mov     [rbp+4Fh+var_50], rax
0x18003caff  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003cb03  mov     [rax], rbx
0x18003cb06  mov     [rax+8], r12
  ... truncated ...
```
