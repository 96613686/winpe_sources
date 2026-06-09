# GetPropertiesFromPrinter(_INIPRINTER *,ushort const *,_DEVPROPERTY * *,ulong *,_DEVPROPERTY * *,ulong *,NCoreLibrary::TString *)

- ea: `0x1800c4420`
- end: `0x1800c4f18`
- name: `?GetPropertiesFromPrinter@@YAJPEAU_INIPRINTER@@PEBGPEAPEAU_DEVPROPERTY@@PEAK23PEAVTString@NCoreLibrary@@@Z`
- size: `2808`
- prototype: `__int64 __usercall@<rax>(struct _INIPRINTER *@<rcx>, PCWSTR DeviceInstanceId@<rdx>, struct _DEVPROPERTY **@<r8>, unsigned int *@<r9>, struct _DEVPROPERTY **, unsigned int *, struct TString *)`
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c674`
- `0x1800c52f0`

## callees

- `0x18000b600`
- `0x18000c380`
- `0x180014d44`
- `0x18001683c`
- `0x18001b058`
- `0x180020b14`
- `0x180029180`
- `0x180029d10`
- `0x18003e984`
- `0x18003ea2c`
- `0x180046650`
- `0x180046aa0`
- `0x180047330`
- `0x180054638`
- `0x180071fb0`
- `0x1800c2d74`
- `0x1800c39e8`
- `0x1800c42f4`
- `0x1800c4420`
- `0x1800c4f20`
- `0x1800cb884`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800c4c51`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800c4c51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c45ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c45ea`
- `SPOOLSS!DllFreeSplStr` at `0x1800c4caf`
- `SPOOLSS!DllFreeSplStr` at `0x1800c4caf`
- `SPOOLSS!DllFreeSplMem` at `0x1800c4eb6`
- `SPOOLSS!DllFreeSplMem` at `0x1800c4ec0`
- `SPOOLSS!DllFreeSplMem` at `0x1800c4eb6`
- `SPOOLSS!DllFreeSplMem` at `0x1800c4ec0`
- `SPOOLSS!DllAllocSplMem` at `0x1800c461f`
- `SPOOLSS!DllAllocSplMem` at `0x1800c4a78`
- `SPOOLSS!DllAllocSplMem` at `0x1800c4e26`
- `SPOOLSS!DllAllocSplMem` at `0x1800c461f`
- `SPOOLSS!DllAllocSplMem` at `0x1800c4a78`
- `SPOOLSS!DllAllocSplMem` at `0x1800c4e26`
- `SPOOLSS!AllocSplStr` at `0x1800c4c3a`
- `SPOOLSS!AllocSplStr` at `0x1800c4c3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetPropertiesFromPrinter(
        struct _INIPRINTER *a1,
        PCWSTR DeviceInstanceId,
        struct _DEVPROPERTY **a3,
        unsigned int *a4,
        struct _DEVPROPERTY **a5,
        unsigned int *a6,
        struct TString *a7)
{
  struct _DEVPROPERTY *v9; // r13
  signed int BidiPropertiesForDevnode; // esi
  bool v11; // zf
  void *v12; // rax
  struct _DEVPROPERTY *v13; // rbx
  const wchar_t *v14; // r9
  signed int LastError; // eax
  struct _DEVPROPERTY *v16; // rax
  __int64 v17; // rcx
  OLECHAR *v18; // rbx
  OLECHAR *v19; // rdi
  unsigned int v20; // r12d
  unsigned int v21; // r10d
  unsigned int v22; // r15d
  int v23; // ecx
  int v24; // r9d
  void **v25; // rax
  void *v26; // r8
  unsigned int v27; // r13d
  __int64 v28; // r8
  int v29; // eax
  int v30; // ecx
  unsigned int v31; // eax
  struct _DEVPROPERTY *v32; // rcx
  struct _DEVPROPERTY *v33; // r12
  const wchar_t *v34; // rax
  wchar_t *v35; // rdx
  const unsigned __int16 *v36; // rax
  struct _DEVPROPERTY *v37; // r12
  void *v38; // rax
  unsigned int v39; // eax
  NCoreLibrary::TString *v40; // rcx
  NCoreLibrary::TString *v41; // rcx
  unsigned int v43; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v44; // [rsp+44h] [rbp-BCh] BYREF
  void *v45; // [rsp+48h] [rbp-B8h] BYREF
  void *v46; // [rsp+50h] [rbp-B0h] BYREF
  int v47; // [rsp+58h] [rbp-A8h]
  int v48; // [rsp+5Ch] [rbp-A4h]
  DEVPROPKEY v49; // [rsp+60h] [rbp-A0h] BYREF
  int v50; // [rsp+74h] [rbp-8Ch]
  void *v51; // [rsp+78h] [rbp-88h]
  struct _DEVPROPERTY *v52; // [rsp+80h] [rbp-80h] BYREF
  void *v53; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *PrinterCategory; // [rsp+90h] [rbp-70h]
  struct _DEVPROPERTY **v55; // [rsp+98h] [rbp-68h]
  unsigned int *v56; // [rsp+A0h] [rbp-60h]
  struct _DEVPROPERTY **v57; // [rsp+A8h] [rbp-58h]
  unsigned int *v58; // [rsp+B0h] [rbp-50h]
  DEVPROPKEY v59; // [rsp+C0h] [rbp-40h] BYREF
  int v60; // [rsp+D4h] [rbp-2Ch]
  void *v61; // [rsp+D8h] [rbp-28h]
  DEVPROPKEY v62; // [rsp+E0h] [rbp-20h]
  int v63; // [rsp+F4h] [rbp-Ch]
  struct _DEVPROPERTY *v64; // [rsp+F8h] [rbp-8h]
  DEVPROPKEY v65; // [rsp+100h] [rbp+0h]
  int v66; // [rsp+114h] [rbp+14h]
  void *v67; // [rsp+118h] [rbp+18h]
  DEVPROPKEY v68; // [rsp+120h] [rbp+20h]
  int v69; // [rsp+134h] [rbp+34h]
  void *v70; // [rsp+138h] [rbp+38h]
  GUID fmtid; // [rsp+140h] [rbp+40h]
  int v72; // [rsp+150h] [rbp+50h]
  int v73; // [rsp+154h] [rbp+54h]
  unsigned __int16 *v74; // [rsp+158h] [rbp+58h]
  GUID v75; // [rsp+160h] [rbp+60h]
  int v76; // [rsp+170h] [rbp+70h]
  int v77; // [rsp+174h] [rbp+74h]
  int v78; // [rsp+178h] [rbp+78h]
  DEVPROPKEY v79; // [rsp+180h] [rbp+80h]
  int v80; // [rsp+194h] [rbp+94h]
  unsigned int v81; // [rsp+198h] [rbp+98h]
  GUID v82; // [rsp+1A0h] [rbp+A0h]
  int v83; // [rsp+1B0h] [rbp+B0h]
  int v84; // [rsp+1B4h] [rbp+B4h]
  int v85; // [rsp+1B8h] [rbp+B8h]
  __int128 v86; // [rsp+1C0h] [rbp+C0h]
  int v87; // [rsp+1D0h] [rbp+D0h]
  int v88; // [rsp+1D4h] [rbp+D4h]
  int v89; // [rsp+1D8h] [rbp+D8h]
  DEVPROPKEY v90; // [rsp+1E0h] [rbp+E0h]
  int v91; // [rsp+1F4h] [rbp+F4h]
  const unsigned __int16 *v92; // [rsp+1F8h] [rbp+F8h]
  DEVPROPKEY v93; // [rsp+200h] [rbp+100h]
  int v94; // [rsp+214h] [rbp+114h]
  int v95; // [rsp+218h] [rbp+118h]
  __int128 v96; // [rsp+220h] [rbp+120h]
  int v97; // [rsp+230h] [rbp+130h]
  int v98; // [rsp+234h] [rbp+134h]
  int v99; // [rsp+238h] [rbp+138h]
  __int128 v100; // [rsp+240h] [rbp+140h]
  int v101; // [rsp+250h] [rbp+150h]
  int v102; // [rsp+254h] [rbp+154h]
  int v103; // [rsp+258h] [rbp+158h]
  DEVPROPKEY v104; // [rsp+260h] [rbp+160h]
  int v105; // [rsp+274h] [rbp+174h]
  int v106; // [rsp+278h] [rbp+178h]
  __int128 v107; // [rsp+280h] [rbp+180h]
  int v108; // [rsp+290h] [rbp+190h]
  int v109; // [rsp+294h] [rbp+194h]
  int v110; // [rsp+298h] [rbp+198h]
  GUID v111; // [rsp+2A0h] [rbp+1A0h]
  int v112; // [rsp+2B0h] [rbp+1B0h]
  int v113; // [rsp+2B4h] [rbp+1B4h]
  unsigned __int16 *v114; // [rsp+2B8h] [rbp+1B8h]
  unsigned __int16 v115[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v56 = a4;
  v55 = a3;
  v57 = a5;
  v58 = a6;
  v9 = 0;
  if ( a1 && a3 && a4 && a5 && a6 )
  {
    BidiPropertiesForDevnode = 0;
    *a3 = 0;
    *a4 = 0;
    *a5 = 0;
    *a6 = 0;
  }
  else
  {
    BidiPropertiesForDevnode = -2147024809;
  }
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 35) + 168LL) & 0x4000000) != 0 || (v11 = *((_DWORD *)a1 + 134) == 0, v47 = 0, !v11) )
    v47 = 1;
  v48 = 0;
  if ( DeviceInstanceId )
  {
    v44 = 49;
    v12 = operator new[](0x31u);
    NCoreLibrary::TAutoPtr<unsigned char>::TAutoPtr<unsigned char>(&v52, v12);
    v13 = v52;
    if ( (int)DeviceObject::GetProperty(DeviceInstanceId, (DEVPROPKEY *)&stru_18011FB18, v52, 0x31u, &v44) >= 0
      && v13->Type == 17 )
    {
      if ( *(_BYTE *)v13->Buffer == 0xFF )
      {
        v48 = 1;
        v14 = L"true";
      }
      else
      {
        v48 = 0;
        v14 = L"false";
      }
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "GetPropertiesFromPrinter",
        L"isFaxDevice for %ws is %ws",
        DeviceInstanceId,
        v14);
    }
    NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtr<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v52);
  }
  memset_0(v115, 0, 0x208u);
  if ( BidiPropertiesForDevnode >= 0 )
  {
    v44 = 520;
    if ( (unsigned int)SplGetPrinterDriverDirectory(
                         0,
                         (unsigned int)L"Windows x64",
                         1,
                         (unsigned int)v115,
                         8,
                         (char)&v44,
                         *((_QWORD *)a1 + 35)) )
    {
      BidiPropertiesForDevnode = StringCchCatW(v115, 0x104u, L"\\3\\");
    }
    else
    {
      LastError = GetLastError();
      BidiPropertiesForDevnode = LastError;
      if ( LastError > 0 )
        BidiPropertiesForDevnode = (unsigned __int16)LastError | 0x80070000;
    }
  }
  v52 = 0;
  if ( BidiPropertiesForDevnode >= 0 )
  {
    v43 = 0;
    GetPrinterPorts(a1, 0, &v43);
    v16 = (struct _DEVPROPERTY *)DllAllocSplMem(v43);
    v52 = v16;
    if ( v16 )
      GetPrinterPorts(a1, v16, &v43);
    else
      BidiPropertiesForDevnode = -2147024882;
  }
  PrinterCategory = GetPrinterCategory(a1);
  v17 = *((_QWORD *)a1 + 11);
  if ( !v17 || (v11 = (*(_DWORD *)(v17 + 200) & 0x1000) == 0, v44 = 2, v11) )
    v44 = 1;
  v18 = &NCoreLibrary::TString::gszNullState;
  v46 = &NCoreLibrary::TString::gszNullState;
  v19 = &NCoreLibrary::TString::gszNullState;
  v45 = &NCoreLibrary::TString::gszNullState;
  if ( BidiPropertiesForDevnode >= 0 && IsBidiSupported(a1) )
  {
    BidiPropertiesForDevnode = GetBidiPropertiesForDevnode(
                                 *((const unsigned __int16 **)a1 + 3),
                                 (struct TString *)&v46,
                                 (struct TString *)&v45,
                                 a7);
    if ( BidiPropertiesForDevnode < 0 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "GetPropertiesFromPrinter",
        L"The device %ws is offline or does not support Model ID and Presentation URL",
        *((_QWORD *)a1 + 3));
      BidiPropertiesForDevnode = 0;
      v20 = -1;
      v43 = -1;
      v18 = (OLECHAR *)v46;
      v19 = (OLECHAR *)v45;
      goto LABEL_37;
    }
    v18 = (OLECHAR *)v46;
    v19 = (OLECHAR *)v45;
  }
  v20 = -1;
  v43 = -1;
  if ( BidiPropertiesForDevnode < 0 )
    goto LABEL_41;
LABEL_37:
  if ( (*((_DWORD *)a1 + 38) & 0x8000) == 0
    || (v20 = *((_DWORD *)a1 + 133)) != 0
    || (BidiPropertiesForDevnode = FindRedirectedPrinterSessionId(a1, &v43),
        v20 = v43,
        BidiPropertiesForDevnode != -2147024894) )
  {
LABEL_41:
    v53 = 0;
    if ( BidiPropertiesForDevnode < 0 )
      goto LABEL_44;
    goto LABEL_42;
  }
  BidiPropertiesForDevnode = 0;
  v53 = 0;
LABEL_42:
  v21 = v47;
  if ( v47 )
    goto LABEL_45;
  BidiPropertiesForDevnode = ConvertPrinterSDToRestrictedDeviceSD(*((void **)a1 + 24), &v53);
LABEL_44:
  v21 = v47;
LABEL_45:
  v22 = 0;
  v23 = *((_DWORD *)a1 + 38);
  v24 = v23 & 0x400000;
  v25 = (void **)((char *)a1 + 544);
  if ( (v23 & 0x400000) == 0 )
    v25 = (void **)((char *)a1 + 24);
  v26 = *v25;
  v46 = *v25;
  v43 = 7;
  if ( BidiPropertiesForDevnode >= 0 )
  {
    v27 = 0;
    if ( v21 )
      v26 = (void *)*((_QWORD *)a1 + 10);
    v59 = DEVPKEY_Device_FriendlyName;
    v60 = 18;
    v61 = v26;
    v62 = DEVPKEY_Device_FriendlyNameAttributes;
    v63 = 7;
    LODWORD(v64) = 2;
    v28 = *((_QWORD *)a1 + 11);
    v65 = DEVPKEY_Device_Manufacturer;
    v66 = 18;
    v67 = *(void **)(v28 + 128);
    v68 = DEVPKEY_DrvPkg_Model;
    v69 = 18;
    v70 = *(void **)(v28 + 24);
    v73 = 17;
    fmtid = PKEY_DeviceDisplay_IsNotWorkingProperly.fmtid;
    v72 = 83;
    LODWORD(v74) = (*((_DWORD *)a1 + 105) & 0xA0005A) != 0;
    if ( v21 || (v29 = 1, (v23 & 8) == 0) )
      v29 = 0;
    v77 = 17;
    v75 = PKEY_DeviceDisplay_IsSharedDevice.fmtid;
    v76 = 84;
    v78 = v29;
    v79 = DEVPKEY_DeviceContainer_IsNetworkDevice;
    v80 = 17;
    v81 = v21;
    v84 = 17;
    v82 = PKEY_DeviceDisplay_IsDefaultDevice.fmtid;
    v83 = 86;
    v85 = 0;
    v88 = 17;
    v86 = xmmword_18011FAA8;
    v87 = 1;
    v89 = 1;
    v90 = DEVPKEY_DeviceContainer_Category;
    v91 = 8210;
    v92 = PrinterCategory;
    v93 = DEVPKEY_DeviceContainer_IsShowInDisconnectedState;
    v94 = 17;
    v95 = 1;
    v96 = DEVPKEY_Device_PersistSystemGeneralize;
    v97 = 5;
    v98 = 17;
    v99 = 1;
    v102 = 7;
    v100 = xmmword_18011FAD0;
    v101 = 7;
    v103 = *(_DWORD *)(v28 + 236);
    v104 = DEVPKEY_Device_NoConnectSound;
    v105 = 17;
    v106 = 1;
    v109 = 17;
    v107 = xmmword_18011FA48;
    v108 = 1;
    v110 = *((_DWORD *)a1 + 35) & 1;
    v113 = 18;
    v111 = PKEY_DeviceInterface_PrinterDriverDirectory.fmtid;
    v112 = 14;
    v114 = v115;
    v30 = (*v18 != 0) + 16;
    if ( *v19 )
      v30 = (*v18 != 0) + 17;
    if ( v20 != -1 )
      ++v30;
    if ( v53 )
      ++v30;
    v31 = v30 + 1;
    if ( !v24 )
      v31 = v30;
    v22 = v31 + 1;
    if ( !v48 )
      v22 = v31;
    v32 = (struct _DEVPROPERTY *)DllAllocSplMem(48 * v22);
    v45 = v32;
    if ( !v32 )
    {
      BidiPropertiesForDevnode = -2147024882;
      v9 = 0;
LABEL_92:
      v26 = v46;
      goto LABEL_93;
    }
    while ( v27 < 0x10 )
    {
      BidiPropertiesForDevnode = ConvertPrintQueuePropertyToDevProperty(
                                   (struct _PrintQueueProperty *)((char *)&v59 + 32 * v27),
                                   &v32[v27]);
      ++v27;
      v32 = (struct _DEVPROPERTY *)v45;
      if ( BidiPropertiesForDevnode < 0 )
      {
        v9 = (struct _DEVPROPERTY *)v45;
        goto LABEL_92;
      }
    }
    if ( *v18 )
    {
      v50 = 18;
      v49.fmtid = PKEY_Device_ModelId.fmtid;
      v49.pid = 2;
      v51 = v18;
      BidiPropertiesForDevnode = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v49, &v32[v27]);
      if ( BidiPropertiesForDevnode < 0 )
        goto LABEL_91;
      ++v27;
      v32 = (struct _DEVPROPERTY *)v45;
    }
    if ( *v19 )
    {
      v50 = 18;
      v49.fmtid = PKEY_Device_PrinterURL.fmtid;
      v49.pid = 15;
      v51 = v19;
      BidiPropertiesForDevnode = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v49, &v32[v27]);
      if ( BidiPropertiesForDevnode < 0 )
        goto LABEL_91;
      ++v27;
    }
    if ( v20 == -1 )
    {
      v33 = (struct _DEVPROPERTY *)v45;
    }
    else
    {
      v49 = DEVPKEY_Device_SessionId;
      v50 = 7;
      LODWORD(v51) = v20;
      v33 = (struct _DEVPROPERTY *)v45;
      BidiPropertiesForDevnode = ConvertPrintQueuePropertyToDevProperty(
                                   (struct _PrintQueueProperty *)&v49,
                                   (struct _DEVPROPERTY *)v45 + v27);
      if ( BidiPropertiesForDevnode < 0 )
      {
        v9 = v33;
        goto LABEL_92;
      }
      ++v27;
    }
    if ( v53 )
    {
      v49.fmtid = (DEVPROPGUID)DEVPKEY_Device_RestrictedSD;
      v49.pid = 100;
      v50 = 19;
      v51 = v53;
      BidiPropertiesForDevnode = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v49, &v33[v27]);
      if ( BidiPropertiesForDevnode < 0 )
        goto LABEL_91;
      ++v27;
    }
    if ( (*((_DWORD *)a1 + 38) & 0x400000) != 0 )
    {
      v34 = (const wchar_t *)AllocSplStr(*((_QWORD *)a1 + 3));
      PrinterCategory = v34;
      if ( v34 )
      {
        v35 = wcschr(v34, 0x3Au);
        if ( v35 )
        {
          v36 = PrinterCategory;
          PrinterCategory[v35 - PrinterCategory] = 0;
          v50 = 18;
          v49.fmtid = (DEVPROPGUID)xmmword_18011FB30;
          v49.pid = 6;
          v51 = (void *)v36;
          BidiPropertiesForDevnode = ConvertPrintQueuePropertyToDevProperty(
                                       (struct _PrintQueueProperty *)&v49,
                                       &v33[v27]);
        }
        DllFreeSplStr(PrinterCategory);
      }
      if ( BidiPropertiesForDevnode < 0 )
        goto LABEL_91;
      ++v27;
    }
    if ( v48 )
    {
      v50 = 17;
      v49.fmtid = stru_18011FB18.fmtid;
      v49.pid = 8;
      LODWORD(v51) = v48;
      BidiPropertiesForDevnode = ConvertPrintQueuePropertyToDevProperty((struct _PrintQueueProperty *)&v49, &v33[v27]);
    }
LABEL_91:
    v9 = (struct _DEVPROPERTY *)v45;
    goto LABEL_92;
  }
LABEL_93:
  v37 = 0;
  if ( BidiPropertiesForDevnode < 0 )
  {
    v43 = 0;
    goto LABEL_107;
  }
  v60 = 18;
  v59.fmtid = PKEY_DeviceInterface_PrinterDriverName.fmtid;
  v59.pid = 11;
  v61 = *(void **)(*((_QWORD *)a1 + 11) + 24LL);
  v63 = 18;
  v62.fmtid = PKEY_DeviceInterface_PrinterPortName.fmtid;
  v62.pid = 12;
  v64 = v52;
  if ( v47 )
    v38 = (void *)*((_QWORD *)a1 + 10);
  else
    v38 = v26;
  v66 = 18;
  v65.fmtid = PKEY_DeviceInterface_PrinterName.fmtid;
  v65.pid = 10;
  v67 = v38;
  if ( v47 )
    v26 = (void *)*((_QWORD *)a1 + 10);
  v69 = 18;
  v68.fmtid = PKEY_DeviceInterface_FriendlyName.fmtid;
  v68.pid = 2;
  v70 = v26;
  v73 = 18;
  fmtid = PKEY_DeviceInterface_PrinterDriverDirectory.fmtid;
  v72 = 14;
  v74 = v115;
  v77 = 17;
  v75 = (GUID)xmmword_18011FA30;
  v76 = 2;
  v78 = v47;
  v80 = 7;
  v79.fmtid = (DEVPROPGUID)xmmword_18011FA18;
  v79.pid = 3;
  v81 = v44;
  v37 = (struct _DEVPROPERTY *)DllAllocSplMem(336);
  v39 = 0;
  if ( !v37 )
  {
    BidiPropertiesForDevnode = -2147024882;
LABEL_107:
    FreeDevPropertyList(v9, v22);
    FreeDevPropertyList(v37, v43);
    goto LABEL_108;
  }
  v44 = 0;
  while ( v39 < 7 )
  {
    BidiPropertiesForDevnode = ConvertPrintQueuePropertyToDevProperty(
                                 (struct _PrintQueueProperty *)((char *)&v59 + 32 * v39),
                                 &v37[v39]);
    v39 = ++v44;
    if ( BidiPropertiesForDevnode < 0 )
      goto LABEL_107;
  }
  *v55 = v9;
  *v56 = v22;
  *v57 = v37;
  *v58 = 7;
LABEL_108:
  DllFreeSplMem(v52);
  DllFreeSplMem(v53);
  if ( BidiPropertiesForDevnode < 0 )
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "GetPropertiesFromPrinter",
      L"Devnode property retrieval failed for printer %ws",
      *((_QWORD *)a1 + 3));
  NCoreLibrary::TString::vFree(v40, v19);
  NCoreLibrary::TString::vFree(v41, v18);
  return (unsigned int)BidiPropertiesForDevnode;
}

```

## disassembly

```asm
0x1800c4420  push    rbp
0x1800c4422  push    rbx
0x1800c4423  push    rsi
0x1800c4424  push    rdi
0x1800c4425  push    r12
0x1800c4427  push    r13
0x1800c4429  push    r14
0x1800c442b  push    r15
0x1800c442d  lea     rbp, [rsp-3E8h]
0x1800c4435  sub     rsp, 4E8h
0x1800c443c  mov     rax, cs:__security_cookie
0x1800c4443  xor     rax, rsp
0x1800c4446  mov     [rbp+420h+var_50], rax
0x1800c444d  mov     [rbp+420h+var_480], r9
0x1800c4451  mov     rax, r8
0x1800c4454  mov     [rbp+420h+var_488], rax
0x1800c4458  mov     rdi, rdx
0x1800c445b  mov     r14, rcx
0x1800c445e  mov     rcx, [rbp+420h+arg_20]
0x1800c4465  mov     [rbp+420h+var_478], rcx
0x1800c4469  mov     rdx, [rbp+420h+arg_28]
0x1800c4470  mov     [rbp+420h+var_470], rdx
0x1800c4474  mov     r15, [rbp+420h+arg_30]
0x1800c447b  xor     r13d, r13d
0x1800c447e  test    r14, r14
0x1800c4481  jz      short loc_1800C44A8
0x1800c4483  test    rax, rax
0x1800c4486  jz      short loc_1800C44A8
0x1800c4488  test    r9, r9
0x1800c448b  jz      short loc_1800C44A8
0x1800c448d  test    rcx, rcx
0x1800c4490  jz      short loc_1800C44A8
0x1800c4492  test    rdx, rdx
0x1800c4495  jz      short loc_1800C44A8
0x1800c4497  mov     esi, r13d
0x1800c449a  mov     [r8], r13
0x1800c449d  mov     [r9], r13d
0x1800c44a0  mov     [rcx], r13
0x1800c44a3  mov     [rdx], r13d
0x1800c44a6  jmp     short loc_1800C44AD
0x1800c44a8  mov     esi, 80070057h
0x1800c44ad  mov     rax, [r14+118h]
0x1800c44b4  test    dword ptr [rax+0A8h], 4000000h
0x1800c44be  jnz     short loc_1800C44CE
0x1800c44c0  cmp     [r14+218h], r13d
0x1800c44c7  mov     [rsp+520h+var_4C8], r13d
0x1800c44cc  jz      short loc_1800C44D6
0x1800c44ce  mov     [rsp+520h+var_4C8], 1
0x1800c44d6  mov     [rsp+520h+var_4C4], r13d
0x1800c44db  test    rdi, rdi
0x1800c44de  jz      loc_1800C4577
0x1800c44e4  mov     r12d, 31h ; '1'
0x1800c44ea  mov     [rsp+520h+var_4DC], r12d
0x1800c44ef  mov     ecx, r12d; unsigned __int64
0x1800c44f2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c44f7  mov     rdx, rax
0x1800c44fa  lea     rcx, [rbp+420h+var_4A0]
0x1800c44fe  call    ??0?$TAutoPtr@E@NCoreLibrary@@QEAA@PEAE@Z; NCoreLibrary::TAutoPtr<uchar>::TAutoPtr<uchar>(uchar *)
0x1800c4503  nop
0x1800c4504  mov     rbx, [rbp+420h+var_4A0]
0x1800c4508  lea     rax, [rsp+520h+var_4DC]
0x1800c450d  mov     [rsp+520h+var_500], rax; unsigned int *
0x1800c4512  mov     r9d, r12d; unsigned int
0x1800c4515  mov     r8, rbx; struct _DEVPROPERTY *
0x1800c4518  lea     rdx, stru_18011FB18; PropertyKey
0x1800c451f  mov     rcx, rdi; DeviceInstanceId
0x1800c4522  call    ?GetProperty@DeviceObject@@SAJPEBGPEBU_DEVPROPKEY@@PEAU_DEVPROPERTY@@KPEAK@Z; DeviceObject::GetProperty(ushort const *,_DEVPROPKEY const *,_DEVPROPERTY *,ulong,ulong *)
0x1800c4527  test    eax, eax
0x1800c4529  js      short loc_1800C456E
0x1800c452b  cmp     dword ptr [rbx+20h], 11h
0x1800c452f  jnz     short loc_1800C456E
0x1800c4531  mov     rax, [rbx+28h]
0x1800c4535  cmp     byte ptr [rax], 0FFh
0x1800c4538  jnz     short loc_1800C454B
0x1800c453a  mov     [rsp+520h+var_4C4], 1
0x1800c4542  lea     r9, aTrue; "true"
0x1800c4549  jmp     short loc_1800C4557
0x1800c454b  mov     [rsp+520h+var_4C4], r13d
0x1800c4550  lea     r9, aFalse; "false"
0x1800c4557  mov     r8, rdi
0x1800c455a  lea     rdx, aIsfaxdeviceFor; "isFaxDevice for %ws is %ws"
0x1800c4561  lea     rcx, aGetpropertiesf_0; "GetPropertiesFromPrinter"
0x1800c4568  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c456d  nop
0x1800c456e  lea     rcx, [rbp+420h+var_4A0]
0x1800c4572  call    ?Reset@?$TGenericSP@EV?$TAutoPtr@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtr<uchar>,uchar *,0,uchar const *>::Reset(void)
0x1800c4577  mov     ebx, 208h
0x1800c457c  mov     r8d, ebx; Size
0x1800c457f  xor     edx, edx; Val
0x1800c4581  lea     rcx, [rbp+420h+var_260]; void *
0x1800c4588  call    memset_0
0x1800c458d  test    esi, esi
0x1800c458f  js      short loc_1800C45FF
0x1800c4591  mov     [rsp+520h+var_4DC], ebx
0x1800c4595  mov     rax, [r14+118h]
0x1800c459c  mov     [rsp+520h+var_4F0], rax
0x1800c45a1  lea     rax, [rsp+520h+var_4DC]
0x1800c45a6  mov     [rsp+520h+var_4F8], rax
0x1800c45ab  mov     dword ptr [rsp+520h+var_500], ebx
0x1800c45af  lea     r9, [rbp+420h+var_260]
0x1800c45b6  mov     r8d, 1
0x1800c45bc  lea     rdx, aWindowsX64_0; "Windows x64"
0x1800c45c3  xor     ecx, ecx
0x1800c45c5  call    SplGetPrinterDriverDirectory
0x1800c45ca  test    eax, eax
0x1800c45cc  jz      short loc_1800C45EA
0x1800c45ce  lea     r8, a3_0; "\\3\\"
0x1800c45d5  mov     edx, 104h; unsigned __int64
0x1800c45da  lea     rcx, [rbp+420h+var_260]; unsigned __int16 *
0x1800c45e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c45e6  mov     esi, eax
0x1800c45e8  jmp     short loc_1800C45FF
0x1800c45ea  call    cs:__imp_GetLastError
0x1800c45f0  mov     esi, eax
0x1800c45f2  test    eax, eax
0x1800c45f4  jle     short loc_1800C45FF
0x1800c45f6  movzx   esi, ax
0x1800c45f9  or      esi, 80070000h
0x1800c45ff  mov     [rbp+420h+var_4A0], r13
0x1800c4603  test    esi, esi
0x1800c4605  js      short loc_1800C4645
0x1800c4607  mov     [rsp+520h+var_4E0], r13d
0x1800c460c  lea     r8, [rsp+520h+var_4E0]
0x1800c4611  xor     edx, edx
0x1800c4613  mov     rcx, r14
0x1800c4616  call    GetPrinterPorts
0x1800c461b  mov     ecx, [rsp+520h+var_4E0]
0x1800c461f  call    cs:__imp_DllAllocSplMem
0x1800c4625  mov     [rbp+420h+var_4A0], rax
0x1800c4629  test    rax, rax
0x1800c462c  jz      short loc_1800C4640
0x1800c462e  lea     r8, [rsp+520h+var_4E0]
0x1800c4633  mov     rdx, rax
0x1800c4636  mov     rcx, r14
0x1800c4639  call    GetPrinterPorts
0x1800c463e  jmp     short loc_1800C4645
0x1800c4640  mov     esi, 8007000Eh
0x1800c4645  mov     rcx, r14; struct _INIPRINTER *
0x1800c4648  call    ?GetPrinterCategory@@YAPEBGPEAU_INIPRINTER@@@Z; GetPrinterCategory(_INIPRINTER *)
0x1800c464d  mov     [rbp+420h+var_490], rax
0x1800c4651  mov     rcx, [r14+58h]
0x1800c4655  test    rcx, rcx
0x1800c4658  jz      short loc_1800C466E
0x1800c465a  test    dword ptr [rcx+0C8h], 1000h
0x1800c4664  mov     [rsp+520h+var_4DC], 2
0x1800c466c  jnz     short loc_1800C4676
0x1800c466e  mov     [rsp+520h+var_4DC], 1
0x1800c4676  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1800c467d  mov     [rsp+520h+var_4D0], rbx
0x1800c4682  mov     rdi, rbx
0x1800c4685  mov     [rsp+520h+var_4D8], rbx
0x1800c468a  test    esi, esi
0x1800c468c  js      short loc_1800C46EF
0x1800c468e  mov     rcx, r14; struct _INIPRINTER *
0x1800c4691  call    ?IsBidiSupported@@YA_NPEAU_INIPRINTER@@@Z; IsBidiSupported(_INIPRINTER *)
0x1800c4696  test    al, al
0x1800c4698  jz      short loc_1800C46EF
0x1800c469a  mov     r9, r15; struct TString *
0x1800c469d  lea     r8, [rsp+520h+var_4D8]; struct TString *
0x1800c46a2  lea     rdx, [rsp+520h+var_4D0]; struct TString *
0x1800c46a7  mov     rcx, [r14+18h]; unsigned __int16 *
0x1800c46ab  call    ?GetBidiPropertiesForDevnode@@YAJPEBGPEAVTString@NCoreLibrary@@11@Z; GetBidiPropertiesForDevnode(ushort const *,NCoreLibrary::TString *,NCoreLibrary::TString *,NCoreLibrary::TString *)
0x1800c46b0  mov     esi, eax
0x1800c46b2  test    eax, eax
0x1800c46b4  jns     short loc_1800C46E5
0x1800c46b6  mov     r8, [r14+18h]
0x1800c46ba  lea     rdx, aTheDeviceWsIsO; "The device %ws is offline or does not s"...
0x1800c46c1  lea     rcx, aGetpropertiesf_0; "GetPropertiesFromPrinter"
0x1800c46c8  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800c46cd  mov     esi, r13d
0x1800c46d0  or      r12d, 0FFFFFFFFh
0x1800c46d4  mov     [rsp+520h+var_4E0], r12d
0x1800c46d9  mov     rbx, [rsp+520h+var_4D0]
0x1800c46de  mov     rdi, [rsp+520h+var_4D8]
0x1800c46e3  jmp     short loc_1800C46FC
0x1800c46e5  mov     rbx, [rsp+520h+var_4D0]
0x1800c46ea  mov     rdi, [rsp+520h+var_4D8]
0x1800c46ef  or      r12d, 0FFFFFFFFh
0x1800c46f3  mov     [rsp+520h+var_4E0], r12d
0x1800c46f8  test    esi, esi
0x1800c46fa  js      short loc_1800C4739
0x1800c46fc  test    dword ptr [r14+98h], 8000h
0x1800c4707  jz      short loc_1800C4739
0x1800c4709  mov     r12d, [r14+214h]
0x1800c4710  test    r12d, r12d
0x1800c4713  jnz     short loc_1800C4739
0x1800c4715  lea     rdx, [rsp+520h+var_4E0]; unsigned int *
0x1800c471a  mov     rcx, r14; struct _INIPRINTER *
0x1800c471d  call    ?FindRedirectedPrinterSessionId@@YAJPEAU_INIPRINTER@@PEAK@Z; FindRedirectedPrinterSessionId(_INIPRINTER *,ulong *)
0x1800c4722  mov     esi, eax
0x1800c4724  mov     r12d, [rsp+520h+var_4E0]
0x1800c4729  cmp     eax, 80070002h
0x1800c472e  jnz     short loc_1800C4739
0x1800c4730  mov     esi, r13d
0x1800c4733  mov     [rbp+420h+var_498], r13
0x1800c4737  jmp     short loc_1800C4741
0x1800c4739  mov     [rbp+420h+var_498], r13
0x1800c473d  test    esi, esi
0x1800c473f  js      short loc_1800C475D
0x1800c4741  mov     r10d, [rsp+520h+var_4C8]
0x1800c4746  test    r10d, r10d
0x1800c4749  jnz     short loc_1800C4762
0x1800c474b  lea     rdx, [rbp+420h+var_498]; void **
0x1800c474f  mov     rcx, [r14+0C0h]; Src
0x1800c4756  call    ?ConvertPrinterSDToRestrictedDeviceSD@@YAJPEAXPEAPEAX@Z; ConvertPrinterSDToRestrictedDeviceSD(void *,void * *)
0x1800c475b  mov     esi, eax
0x1800c475d  mov     r10d, [rsp+520h+var_4C8]
0x1800c4762  mov     r15d, r13d
0x1800c4765  mov     ecx, [r14+98h]
0x1800c476c  mov     r9d, ecx
0x1800c476f  and     r9d, 400000h
0x1800c4776  lea     rax, [r14+220h]
0x1800c477d  jnz     short loc_1800C4783
0x1800c477f  lea     rax, [r14+18h]
0x1800c4783  mov     r8, [rax]
0x1800c4786  mov     [rsp+520h+var_4D0], r8
0x1800c478b  mov     edx, 7
0x1800c4790  mov     [rsp+520h+var_4E0], edx
0x1800c4794  test    esi, esi
0x1800c4796  js      loc_1800C4D0E
0x1800c479c  xor     r13d, r13d
0x1800c479f  test    r10d, r10d
0x1800c47a2  jz      short loc_1800C47A8
0x1800c47a4  mov     r8, [r14+50h]
0x1800c47a8  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x1800c47af  movaps  [rbp+420h+var_460], xmm0
0x1800c47b3  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x1800c47b9  mov     [rbp+420h+var_450], eax
0x1800c47bc  mov     [rbp+420h+var_44C], 12h
0x1800c47c3  mov     [rbp+420h+var_448], r8
0x1800c47c7  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyNameAttributes.fmtid.Data1
0x1800c47ce  movaps  [rbp+420h+var_440], xmm0
0x1800c47d2  mov     eax, cs:DEVPKEY_Device_FriendlyNameAttributes.pid
0x1800c47d8  mov     [rbp+420h+var_430], eax
0x1800c47db  mov     [rbp+420h+var_42C], edx
0x1800c47de  mov     dword ptr [rbp+420h+var_428], 2
0x1800c47e5  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_Manufacturer.fmtid.Data1
0x1800c47ec  mov     eax, cs:DEVPKEY_Device_Manufacturer.pid
0x1800c47f2  mov     r8, [r14+58h]
0x1800c47f6  movaps  [rbp+420h+var_420], xmm0
0x1800c47fa  mov     [rbp+420h+var_410], eax
0x1800c47fd  mov     [rbp+420h+var_40C], 12h
0x1800c4804  mov     rax, [r8+80h]
0x1800c480b  mov     [rbp+420h+var_408], rax
0x1800c480f  movups  xmm0, xmmword ptr cs:DEVPKEY_DrvPkg_Model.fmtid.Data1
0x1800c4816  mov     eax, cs:DEVPKEY_DrvPkg_Model.pid
0x1800c481c  movaps  [rbp+420h+var_400], xmm0
0x1800c4820  mov     [rbp+420h+var_3F0], eax
0x1800c4823  mov     [rbp+420h+var_3EC], 12h
0x1800c482a  mov     rax, [r8+18h]
0x1800c482e  mov     [rbp+420h+var_3E8], rax
0x1800c4832  mov     r11d, 11h
0x1800c4838  mov     [rbp+420h+var_3CC], r11d
0x1800c483c  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsNotWorkingProperly.fmtid.Data1
0x1800c4843  movdqu  [rbp+420h+var_3E0], xmm0
0x1800c4848  mov     [rbp+420h+var_3D0], 53h ; 'S'
0x1800c484f  test    dword ptr [r14+1A4h], 0A0005Ah
0x1800c485a  mov     eax, r13d
0x1800c485d  setnz   al
0x1800c4860  mov     dword ptr [rbp+420h+var_3C8], eax
0x1800c4863  test    r10d, r10d
0x1800c4866  jnz     short loc_1800C4871
0x1800c4868  test    cl, 8
0x1800c486b  lea     eax, [r11-10h]
0x1800c486f  jnz     short loc_1800C4874
0x1800c4871  mov     eax, r13d
0x1800c4874  mov     [rbp+420h+var_3AC], r11d
0x1800c4878  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsSharedDevice.fmtid.Data1
0x1800c487f  movdqu  [rbp+420h+var_3C0], xmm0
0x1800c4884  mov     [rbp+420h+var_3B0], 54h ; 'T'
0x1800c488b  mov     [rbp+420h+var_3A8], eax
0x1800c488e  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsNetworkDevice.fmtid.Data1
0x1800c4895  movaps  [rbp+420h+var_3A0], xmm0
0x1800c489c  mov     eax, cs:DEVPKEY_DeviceContainer_IsNetworkDevice.pid
0x1800c48a2  mov     [rbp+420h+var_390], eax
0x1800c48a8  mov     [rbp+420h+var_38C], r11d
0x1800c48af  mov     [rbp+420h+var_388], r10d
0x1800c48b6  mov     [rbp+420h+var_36C], r11d
0x1800c48bd  movups  xmm0, xmmword ptr cs:PKEY_DeviceDisplay_IsDefaultDevice.fmtid.Data1
0x1800c48c4  movdqu  [rbp+420h+var_380], xmm0
0x1800c48cc  mov     [rbp+420h+var_370], 56h ; 'V'
0x1800c48d6  mov     [rbp+420h+var_368], r13d
0x1800c48dd  mov     [rbp+420h+var_34C], r11d
0x1800c48e4  movups  xmm0, cs:xmmword_18011FAA8
0x1800c48eb  movdqu  [rbp+420h+var_360], xmm0
0x1800c48f3  mov     r10d, 1
0x1800c48f9  mov     [rbp+420h+var_350], r10d
0x1800c4900  mov     [rbp+420h+var_348], r10d
0x1800c4907  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_Category.fmtid.Data1
0x1800c490e  movaps  [rbp+420h+var_340], xmm0
0x1800c4915  mov     eax, cs:DEVPKEY_DeviceContainer_Category.pid
0x1800c491b  mov     [rbp+420h+var_330], eax
0x1800c4921  mov     [rbp+420h+var_32C], 2012h
0x1800c492b  mov     rax, [rbp+420h+var_490]
0x1800c492f  mov     [rbp+420h+var_328], rax
0x1800c4936  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsShowInDisconnectedState.fmtid.Data1
0x1800c493d  movaps  [rbp+420h+var_320], xmm0
0x1800c4944  mov     eax, cs:DEVPKEY_DeviceContainer_IsShowInDisconnectedState.pid
0x1800c494a  mov     [rbp+420h+var_310], eax
0x1800c4950  mov     [rbp+420h+var_30C], r11d
  ... truncated ...
```
