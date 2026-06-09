# ConvertDevModeToSpecifiedVersion

- ea: `0x180073054`
- end: `0x180073424`
- name: `ConvertDevModeToSpecifiedVersion`
- size: `976`
- prototype: `__int64 __usercall@<rax>(struct _INIPRINTER *@<rcx>, void *Src@<rdx>, int)`
- caller_count: `7`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180031d5c`
- `0x18004fe9c`
- `0x180057b58`
- `0x18005ab8c`
- `0x18007acf8`
- `0x18009cdac`
- `0x1800c27d8`

## callees

- `0x180008520`
- `0x180008560`
- `0x18003b010`
- `0x18003e984`
- `0x180042a80`
- `0x180042fd0`
- `0x180047318`
- `0x180073054`
- `0x180073be0`
- `0x1800d89c0`

## import_xrefs

- `SPOOLSS!CallDrvDevModeConversion` at `0x180073165`
- `SPOOLSS!CallDrvDevModeConversion` at `0x180073180`
- `SPOOLSS!CallDrvDevModeConversion` at `0x1800732bb`
- `SPOOLSS!CallDrvDevModeConversion` at `0x180073165`
- `SPOOLSS!CallDrvDevModeConversion` at `0x180073180`
- `SPOOLSS!CallDrvDevModeConversion` at `0x1800732bb`
- `SPOOLSS!DllFreeSplStr` at `0x1800733c0`
- `SPOOLSS!DllFreeSplStr` at `0x1800733e6`
- `SPOOLSS!DllFreeSplStr` at `0x1800733f4`
- `SPOOLSS!DllFreeSplStr` at `0x1800733c0`
- `SPOOLSS!DllFreeSplStr` at `0x1800733e6`
- `SPOOLSS!DllFreeSplStr` at `0x1800733f4`
- `SPOOLSS!DllFreeSplMem` at `0x180073328`
- `SPOOLSS!DllFreeSplMem` at `0x1800733b1`
- `SPOOLSS!DllFreeSplMem` at `0x180073402`
- `SPOOLSS!DllFreeSplMem` at `0x180073328`
- `SPOOLSS!DllFreeSplMem` at `0x1800733b1`
- `SPOOLSS!DllFreeSplMem` at `0x180073402`
- `SPOOLSS!DllAllocSplMem` at `0x180073107`
- `SPOOLSS!DllAllocSplMem` at `0x180073350`
- `SPOOLSS!DllAllocSplMem` at `0x180073107`
- `SPOOLSS!DllAllocSplMem` at `0x180073350`
- `SPOOLSS!AllocSplStr` at `0x1800732e0`
- `SPOOLSS!AllocSplStr` at `0x1800732e0`

## pseudocode

```c
struct _devicemodeW *__fastcall ConvertDevModeToSpecifiedVersion(
        struct _INIPRINTER *a1,
        struct _devicemodeW *Src,
        __int64 a3,
        const unsigned __int16 *a4,
        int a5)
{
  const unsigned __int16 *v7; // rbx
  __int64 v8; // r12
  __int64 v9; // rcx
  struct _devicemodeW *v10; // rdi
  __int64 ConfigFilePath; // r15
  const unsigned __int16 *PrinterName; // rsi
  struct _devicemodeW *v13; // rax
  unsigned int v14; // ebx
  unsigned int v15; // r12d
  BOOL v16; // edx
  __int64 v17; // rax
  __int64 v18; // rcx
  const unsigned __int16 *v19; // r12
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  struct _devicemodeW *v23; // rax
  struct _devicemodeW *v24; // rcx
  struct _devicemodeW *v26; // [rsp+40h] [rbp-10h] BYREF
  __int64 v27; // [rsp+48h] [rbp-8h] BYREF
  size_t Size; // [rsp+98h] [rbp+48h] BYREF
  __int64 v29; // [rsp+A0h] [rbp+50h]
  const unsigned __int16 *v30; // [rsp+A8h] [rbp+58h]

  v30 = a4;
  v29 = a3;
  v7 = a4;
  v8 = a3;
  LocalSpoolerTelemetry::WriteDbgTraceInfo("ConvertDevModeToSpecifiedVersion", L"Enter");
  v10 = 0;
  v26 = 0;
  LODWORD(Size) = 0;
  if ( v8 )
  {
    ConfigFilePath = v8;
  }
  else
  {
    ConfigFilePath = GetConfigFilePath(*((_QWORD *)a1 + 11), *((_QWORD *)a1 + 35));
    if ( !ConfigFilePath )
      goto LABEL_50;
  }
  PrinterName = v7;
  if ( v7 || (PrinterName = pszGetPrinterName(a1, 1, L"LocalOnly")) != 0 )
  {
    if ( !Src )
      goto LABEL_12;
    if ( Src != *((struct _devicemodeW **)a1 + 13) )
    {
      v10 = Src;
LABEL_12:
      LeaveSplSem(v9);
      LODWORD(Size) = 0;
      if ( a5 == 1 )
      {
        CallDrvDevModeConversion(ConfigFilePath, PrinterName, v10, &v26, &Size, 2, 1);
LABEL_45:
        EnterSplSem(0);
        goto LABEL_46;
      }
      if ( !(unsigned int)CallDrvDevModeConversion(ConfigFilePath, PrinterName, 0, &v26, &Size, 4, 1) )
      {
        v14 = 0;
        v15 = 0;
        if ( v10 )
        {
          if ( v10->dmDriverExtra > 4u )
          {
            v14 = *(_DWORD *)((char *)v10->dmDeviceName + v10->dmSize);
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "ConvertDevModeToSpecifiedVersion",
              L"We have a OldDevmode and the OldDevmode's Driver signature is %u",
              v14);
            if ( v14 != 1447645776 && v14 != 1431193924 )
            {
              v14 = 1;
              LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "ConvertDevModeToSpecifiedVersion",
                L"Driver signature of the OldDevMode is set to %u (UNKNOWN_SIGNATURE), since the driver signtaure did not "
                 "match to be that of unidrv or postscript.",
                1);
            }
          }
        }
        if ( v26 )
        {
          if ( v26->dmDriverExtra > 4u )
          {
            v15 = *(_DWORD *)((char *)v26->dmDeviceName + v26->dmSize);
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "ConvertDevModeToSpecifiedVersion",
              L"We have a NewDevmode and the NewDevmode's Driver signature is %u",
              v15);
            if ( v15 != 1447645776 && v15 != 1431193924 )
            {
              v15 = 1;
              LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "ConvertDevModeToSpecifiedVersion",
                L"Driver signature of the NewDevMode is set to %u (UNKNOWN_SIGNATURE), since the driver signtaure did not "
                 "match to be that of unidrv or postscript. ",
                1);
            }
          }
        }
        if ( !v10 )
          goto LABEL_44;
        v16 = 0;
        if ( v10->dmReserved1 == 877873479 )
          v16 = *(_DWORD *)(*((_QWORD *)a1 + 11) + 236LL) >= 4u;
        if ( v14 != v15 && !v16
          || (LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "ConvertDevModeToSpecifiedVersion",
                L"Both the drivers are using the same core driver, we go ahead and CallDrvDevModeConversion"),
              !(unsigned int)CallDrvDevModeConversion(ConfigFilePath, PrinterName, v10, &v26, &Size, 1, 0)) )
        {
LABEL_44:
          v8 = v29;
          v7 = v30;
          goto LABEL_45;
        }
      }
      v27 = 0;
      EnterSplSem(0);
      v17 = AllocSplStr(*(_QWORD *)(*((_QWORD *)a1 + 11) + 24LL));
      v18 = *((_QWORD *)a1 + 11);
      v19 = (const unsigned __int16 *)v17;
      v20 = *(_DWORD *)(v18 + 200);
      LeaveSplSem(v18);
      if ( sandbox::DocumentPropertiesAdapter::Initialize(
             (sandbox::DocumentPropertiesAdapter *)&v27,
             *(struct sandbox::SandboxManager **)(*((_QWORD *)a1 + 35) + 368LL),
             PrinterName,
             v19,
             v20) )
      {
        goto LABEL_42;
      }
      DllFreeSplMem(v26);
      v26 = 0;
      v21 = sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(
              (sandbox::DocumentPropertiesAdapter *)&v27,
              0,
              0,
              0,
              0);
      v22 = v21;
      if ( v21 > 0 )
      {
        v23 = (struct _devicemodeW *)DllAllocSplMem((unsigned int)v21);
        v26 = v23;
        if ( !v23 )
        {
LABEL_36:
          if ( v10
            && (int)sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(
                      (sandbox::DocumentPropertiesAdapter *)&v27,
                      v10,
                      0xAu,
                      v23,
                      v22) < 0 )
          {
            v24 = v26;
LABEL_41:
            DllFreeSplMem(v24);
            v26 = 0;
LABEL_43:
            sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v27);
            goto LABEL_44;
          }
LABEL_42:
          DllFreeSplStr(v19);
          goto LABEL_43;
        }
        if ( (int)sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(
                    (sandbox::DocumentPropertiesAdapter *)&v27,
                    0,
                    2u,
                    v23,
                    v22) >= 0 )
        {
          v23 = v26;
          goto LABEL_36;
        }
      }
      v23 = v26;
      if ( v26 )
      {
        v24 = v26;
        goto LABEL_41;
      }
      goto LABEL_36;
    }
    LODWORD(Size) = Src->dmSize + Src->dmDriverExtra;
    v13 = (struct _devicemodeW *)DllAllocSplMem((unsigned int)Size);
    v10 = v13;
    if ( v13 )
    {
      memcpy_0(v13, Src, (unsigned int)Size);
      goto LABEL_12;
    }
  }
LABEL_46:
  if ( ConfigFilePath != v8 )
    DllFreeSplStr(ConfigFilePath);
  if ( v7 != PrinterName )
    DllFreeSplStr(PrinterName);
LABEL_50:
  if ( v10 != Src )
    DllFreeSplMem(v10);
  return v26;
}

```

## disassembly

```asm
0x180073054  mov     [rsp-38h+arg_0], rbx
0x180073059  mov     [rsp-38h+arg_18], r9
0x18007305e  mov     [rsp-38h+arg_10], r8
0x180073063  push    rbp
0x180073064  push    rsi
0x180073065  push    rdi
0x180073066  push    r12
0x180073068  push    r13
0x18007306a  push    r14
0x18007306c  push    r15
0x18007306e  mov     rbp, rsp
0x180073071  sub     rsp, 50h
0x180073075  mov     r14, rdx
0x180073078  mov     r13, rcx
0x18007307b  lea     rdx, aEnter; "Enter"
0x180073082  mov     rbx, r9
0x180073085  lea     rcx, aConvertdevmode_1; "ConvertDevModeToSpecifiedVersion"
0x18007308c  mov     r12, r8
0x18007308f  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180073094  xor     edi, edi
0x180073096  mov     [rbp+var_10], 0
0x18007309e  mov     dword ptr [rbp+Size], edi
0x1800730a1  test    r12, r12
0x1800730a4  jnz     short loc_1800730C4
0x1800730a6  mov     rdx, [r13+118h]
0x1800730ad  mov     rcx, [r13+58h]
0x1800730b1  call    GetConfigFilePath
0x1800730b6  mov     r15, rax
0x1800730b9  test    rax, rax
0x1800730bc  jz      loc_1800733FA
0x1800730c2  jmp     short loc_1800730C7
0x1800730c4  mov     r15, r12
0x1800730c7  mov     rsi, rbx
0x1800730ca  test    rbx, rbx
0x1800730cd  jnz     short loc_1800730ED
0x1800730cf  lea     r8, aLocalonly_0; "LocalOnly"
0x1800730d6  mov     rcx, r13; struct _INIPRINTER *
0x1800730d9  lea     edx, [rbx+1]; int
0x1800730dc  call    ?pszGetPrinterName@@YAPEAGPEAU_INIPRINTER@@HPEBG@Z; pszGetPrinterName(_INIPRINTER *,int,ushort const *)
0x1800730e1  mov     rsi, rax
0x1800730e4  test    rax, rax
0x1800730e7  jz      loc_1800733DE
0x1800730ed  test    r14, r14
0x1800730f0  jz      short loc_18007312D
0x1800730f2  cmp     r14, [r13+68h]
0x1800730f6  jnz     short loc_18007312A
0x1800730f8  movzx   ecx, word ptr [r14+46h]
0x1800730fd  movzx   eax, word ptr [r14+44h]
0x180073102  add     ecx, eax
0x180073104  mov     dword ptr [rbp+Size], ecx
0x180073107  call    cs:__imp_DllAllocSplMem
0x18007310d  mov     rdi, rax
0x180073110  test    rax, rax
0x180073113  jz      loc_1800733DE
0x180073119  mov     r8d, dword ptr [rbp+Size]; Size
0x18007311d  mov     rdx, r14; Src
0x180073120  mov     rcx, rax; void *
0x180073123  call    memcpy_0
0x180073128  jmp     short loc_18007312D
0x18007312a  mov     rdi, r14
0x18007312d  call    LeaveSplSem
0x180073132  mov     eax, 1
0x180073137  mov     dword ptr [rbp+Size], 0
0x18007313e  cmp     [rbp+arg_20], eax
0x180073141  lea     r9, [rbp+var_10]
0x180073145  mov     [rsp+50h+var_20], eax
0x180073149  mov     rdx, rsi
0x18007314c  lea     rax, [rbp+Size]
0x180073150  mov     rcx, r15
0x180073153  jnz     short loc_180073170
0x180073155  mov     [rsp+50h+var_28], 2
0x18007315d  mov     r8, rdi
0x180073160  mov     qword ptr [rsp+50h+var_30], rax
0x180073165  call    cs:__imp_CallDrvDevModeConversion
0x18007316b  jmp     loc_1800733D7
0x180073170  mov     [rsp+50h+var_28], 4
0x180073178  xor     r8d, r8d
0x18007317b  mov     qword ptr [rsp+50h+var_30], rax
0x180073180  call    cs:__imp_CallDrvDevModeConversion
0x180073186  test    eax, eax
0x180073188  jnz     loc_1800732C9
0x18007318e  xor     ebx, ebx
0x180073190  xor     r12d, r12d
0x180073193  lea     eax, [rbx+4]
0x180073196  test    rdi, rdi
0x180073199  jz      short loc_1800731F0
0x18007319b  cmp     [rdi+46h], ax
0x18007319f  jbe     short loc_1800731F0
0x1800731a1  movzx   eax, word ptr [rdi+44h]
0x1800731a5  lea     rdx, aWeHaveAOlddevm; "We have a OldDevmode and the OldDevmode"...
0x1800731ac  lea     rcx, aConvertdevmode_1; "ConvertDevModeToSpecifiedVersion"
0x1800731b3  mov     ebx, [rax+rdi]
0x1800731b6  mov     r8d, ebx
0x1800731b9  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800731be  cmp     ebx, 56495250h
0x1800731c4  jz      short loc_1800731EB
0x1800731c6  cmp     ebx, 554E4944h
0x1800731cc  jz      short loc_1800731EB
0x1800731ce  lea     eax, [r12+1]
0x1800731d3  mov     r8d, eax
0x1800731d6  lea     rdx, aDriverSignatur; "Driver signature of the OldDevMode is s"...
0x1800731dd  lea     rcx, aConvertdevmode_1; "ConvertDevModeToSpecifiedVersion"
0x1800731e4  mov     ebx, eax
0x1800731e6  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800731eb  mov     eax, 4
0x1800731f0  mov     rcx, [rbp+var_10]
0x1800731f4  test    rcx, rcx
0x1800731f7  jz      short loc_18007324D
0x1800731f9  cmp     [rcx+46h], ax
0x1800731fd  jbe     short loc_18007324D
0x1800731ff  movzx   eax, word ptr [rcx+44h]
0x180073203  lea     rdx, aWeHaveANewdevm; "We have a NewDevmode and the NewDevmode"...
0x18007320a  mov     r12d, [rax+rcx]
0x18007320e  mov     r8d, r12d
0x180073211  lea     rcx, aConvertdevmode_1; "ConvertDevModeToSpecifiedVersion"
0x180073218  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007321d  cmp     r12d, 56495250h
0x180073224  jz      short loc_18007324D
0x180073226  cmp     r12d, 554E4944h
0x18007322d  jz      short loc_18007324D
0x18007322f  mov     eax, 1
0x180073234  lea     rdx, aDriverSignatur_0; "Driver signature of the NewDevMode is s"...
0x18007323b  mov     r8d, eax
0x18007323e  lea     rcx, aConvertdevmode_1; "ConvertDevModeToSpecifiedVersion"
0x180073245  mov     r12d, eax
0x180073248  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18007324d  test    rdi, rdi
0x180073250  jz      loc_1800733CF
0x180073256  xor     edx, edx
0x180073258  cmp     dword ptr [rdi+0CCh], 34534947h
0x180073262  jnz     short loc_180073275
0x180073264  mov     rax, [r13+58h]
0x180073268  cmp     dword ptr [rax+0ECh], 4
0x18007326f  lea     eax, [rdx+1]
0x180073272  cmovnb  edx, eax
0x180073275  cmp     ebx, r12d
0x180073278  jz      short loc_180073282
0x18007327a  test    edx, edx
0x18007327c  jz      loc_1800733CF
0x180073282  lea     rdx, aBothTheDrivers; "Both the drivers are using the same cor"...
0x180073289  lea     rcx, aConvertdevmode_1; "ConvertDevModeToSpecifiedVersion"
0x180073290  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180073295  lea     rax, [rbp+Size]
0x180073299  mov     [rsp+50h+var_20], 0
0x1800732a1  mov     [rsp+50h+var_28], 1
0x1800732a9  lea     r9, [rbp+var_10]
0x1800732ad  mov     r8, rdi
0x1800732b0  mov     qword ptr [rsp+50h+var_30], rax
0x1800732b5  mov     rdx, rsi
0x1800732b8  mov     rcx, r15
0x1800732bb  call    cs:__imp_CallDrvDevModeConversion
0x1800732c1  test    eax, eax
0x1800732c3  jz      loc_1800733CF
0x1800732c9  xor     ecx, ecx
0x1800732cb  mov     [rbp+var_8], 0
0x1800732d3  call    EnterSplSem
0x1800732d8  mov     rcx, [r13+58h]
0x1800732dc  mov     rcx, [rcx+18h]
0x1800732e0  call    cs:__imp_AllocSplStr
0x1800732e6  mov     rcx, [r13+58h]
0x1800732ea  mov     r12, rax
0x1800732ed  mov     ebx, [rcx+0C8h]
0x1800732f3  call    LeaveSplSem
0x1800732f8  mov     rdx, [r13+118h]
0x1800732ff  lea     rcx, [rbp+var_8]; this
0x180073303  mov     r9, r12; unsigned __int16 *
0x180073306  mov     [rsp+50h+var_30], ebx; unsigned int
0x18007330a  mov     r8, rsi; unsigned __int16 *
0x18007330d  mov     rdx, [rdx+170h]; struct sandbox::SandboxManager *
0x180073314  call    ?Initialize@DocumentPropertiesAdapter@sandbox@@QEAAKPEAVSandboxManager@2@PEBG1K@Z; sandbox::DocumentPropertiesAdapter::Initialize(sandbox::SandboxManager *,ushort const *,ushort const *,ulong)
0x180073319  xor     r13d, r13d
0x18007331c  test    eax, eax
0x18007331e  jnz     loc_1800733BD
0x180073324  mov     rcx, [rbp+var_10]
0x180073328  call    cs:__imp_DllFreeSplMem
0x18007332e  xor     r9d, r9d; struct _devicemodeW *
0x180073331  mov     [rbp+var_10], r13
0x180073335  xor     r8d, r8d; unsigned int
0x180073338  mov     [rsp+50h+var_30], r13d; unsigned int
0x18007333d  xor     edx, edx; struct _devicemodeW *
0x18007333f  lea     rcx, [rbp+var_8]; this
0x180073343  call    ?DocumentPropertiesW@DocumentPropertiesAdapter@sandbox@@QEAAJPEAU_devicemodeW@@K0K@Z; sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(_devicemodeW *,ulong,_devicemodeW *,ulong)
0x180073348  mov     ebx, eax
0x18007334a  test    eax, eax
0x18007334c  jle     short loc_1800733A5
0x18007334e  mov     ecx, eax
0x180073350  call    cs:__imp_DllAllocSplMem
0x180073356  mov     [rbp+var_10], rax
0x18007335a  test    rax, rax
0x18007335d  jz      short loc_18007337D
0x18007335f  mov     r9, rax; struct _devicemodeW *
0x180073362  mov     [rsp+50h+var_30], ebx; unsigned int
0x180073366  xor     edx, edx; struct _devicemodeW *
0x180073368  lea     r8d, [r13+2]; unsigned int
0x18007336c  lea     rcx, [rbp+var_8]; this
0x180073370  call    ?DocumentPropertiesW@DocumentPropertiesAdapter@sandbox@@QEAAJPEAU_devicemodeW@@K0K@Z; sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(_devicemodeW *,ulong,_devicemodeW *,ulong)
0x180073375  test    eax, eax
0x180073377  js      short loc_1800733A5
0x180073379  mov     rax, [rbp+var_10]
0x18007337d  test    rdi, rdi
0x180073380  jz      short loc_1800733BD
0x180073382  mov     r9, rax; struct _devicemodeW *
0x180073385  mov     [rsp+50h+var_30], ebx; unsigned int
0x180073389  mov     r8d, 0Ah; unsigned int
0x18007338f  lea     rcx, [rbp+var_8]; this
0x180073393  mov     rdx, rdi; struct _devicemodeW *
0x180073396  call    ?DocumentPropertiesW@DocumentPropertiesAdapter@sandbox@@QEAAJPEAU_devicemodeW@@K0K@Z; sandbox::DocumentPropertiesAdapter::DocumentPropertiesW(_devicemodeW *,ulong,_devicemodeW *,ulong)
0x18007339b  test    eax, eax
0x18007339d  jns     short loc_1800733BD
0x18007339f  mov     rcx, [rbp+var_10]
0x1800733a3  jmp     short loc_1800733B1
0x1800733a5  mov     rax, [rbp+var_10]
0x1800733a9  test    rax, rax
0x1800733ac  jz      short loc_18007337D
0x1800733ae  mov     rcx, rax
0x1800733b1  call    cs:__imp_DllFreeSplMem
0x1800733b7  mov     [rbp+var_10], r13
0x1800733bb  jmp     short loc_1800733C6
0x1800733bd  mov     rcx, r12
0x1800733c0  call    cs:__imp_DllFreeSplStr
0x1800733c6  lea     rcx, [rbp+var_8]; this
0x1800733ca  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1800733cf  mov     r12, [rbp+arg_10]
0x1800733d3  mov     rbx, [rbp+arg_18]
0x1800733d7  xor     ecx, ecx
0x1800733d9  call    EnterSplSem
0x1800733de  cmp     r15, r12
0x1800733e1  jz      short loc_1800733EC
0x1800733e3  mov     rcx, r15
0x1800733e6  call    cs:__imp_DllFreeSplStr
0x1800733ec  cmp     rbx, rsi
0x1800733ef  jz      short loc_1800733FA
0x1800733f1  mov     rcx, rsi
0x1800733f4  call    cs:__imp_DllFreeSplStr
0x1800733fa  cmp     rdi, r14
0x1800733fd  jz      short loc_180073408
0x1800733ff  mov     rcx, rdi
0x180073402  call    cs:__imp_DllFreeSplMem
0x180073408  mov     rax, [rbp+var_10]
0x18007340c  mov     rbx, [rsp+50h+arg_0]
0x180073414  add     rsp, 50h
0x180073418  pop     r15
0x18007341a  pop     r14
0x18007341c  pop     r13
0x18007341e  pop     r12
0x180073420  pop     rdi
0x180073421  pop     rsi
0x180073422  pop     rbp
0x180073423  retn
```
