# SaveGlobalsToXML(CWriter *,_IIS_CRYPTO_BLOB *,bool)

- ea: `0x180024388`
- end: `0x18002469d`
- name: `?SaveGlobalsToXML@@YAJPEAVCWriter@@PEFAU_IIS_CRYPTO_BLOB@@_N@Z`
- size: `789`
- prototype: `int(struct CWriter *, struct _IIS_CRYPTO_BLOB *, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023df4`
- `0x180024e90`

## callees

- `0x180006204`
- `0x1800074e4`
- `0x1800083f4`
- `0x180009b58`
- `0x18001c100`
- `0x180024388`
- `0x18002e380`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x1800244ba`
- `IisRTL!PuDbgPrintW` at `0x180024675`
- `IisRTL!PuDbgPrintW` at `0x1800244ba`
- `IisRTL!PuDbgPrintW` at `0x180024675`

## string_xrefs

- `0x1800243e2`: `[SaveGlobalsToXML] GetLocationWriter failed with hr = 0x%x.\n`
- `0x1800244a7`: `SaveGlobalsToXML`
- `0x180024662`: `SaveGlobalsToXML`
- `0x180024433`: `[SaveGlobalsToXML] InitializeKeyType failed with hr = 0x%x.\n`
- `0x1800244a0`: `[SaveGlobalsToXML] AddProperty for ID: %d failed with hr = 0x%x.\n`
- `0x180024654`: `[SaveGlobalsToXML] WriteLocation failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SaveGlobalsToXML(struct CWriter *a1, struct _IIS_CRYPTO_BLOB *a2, char a3)
{
  int LocationWriter; // eax
  unsigned int v6; // edx
  CLocationWriter *v7; // rdi
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  __int64 v11; // r8
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned __int8 *v18; // [rsp+28h] [rbp-40h]
  unsigned __int8 *v19; // [rsp+28h] [rbp-40h]
  unsigned int v20; // [rsp+30h] [rbp-38h]
  __int64 v21; // [rsp+30h] [rbp-38h]
  CLocationWriter *v22; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v23; // [rsp+88h] [rbp+20h] BYREF

  v22 = 0;
  v23 = 0;
  LocationWriter = CWriter::GetLocationWriter(a1, &v22, L".");
  v7 = v22;
  v8 = LocationWriter;
  if ( LocationWriter < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        11293,
        "SaveGlobalsToXML",
        L"[SaveGlobalsToXML] GetLocationWriter failed with hr = 0x%x.\n",
        LocationWriter);
    goto LABEL_28;
  }
  v9 = CLocationWriter::InitializeKeyType(v22, v6, 0, 1u, 2u, (unsigned __int8 *)L"IIS_Global", v20);
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v18) = v9;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        11309,
        "SaveGlobalsToXML",
        L"[SaveGlobalsToXML] InitializeKeyType failed with hr = 0x%x.\n",
        v18);
    }
    goto LABEL_28;
  }
  if ( !a3 )
  {
    v10 = CLocationWriter::AddProperty(v7, 0x270Du, 0, 1u, 1u, &g_dwSystemChangeNumber, 4u);
    v8 = v10;
    if ( v10 < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_28;
      LODWORD(v21) = v10;
      v11 = 11334;
      LODWORD(v19) = 9997;
      goto LABEL_11;
    }
    ComputeNewHistoryVersionNumber();
    v23 = g_ulHistoryMajorVersionNumber;
    v12 = CLocationWriter::AddProperty(v7, 0x270Au, 0, 1u, 1u, (unsigned __int8 *)&v23, 4u);
    v8 = v12;
    if ( v12 < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_28;
      LODWORD(v21) = v12;
      v11 = 11361;
      LODWORD(v19) = 9994;
      goto LABEL_11;
    }
  }
  v13 = CLocationWriter::AddProperty(v7, 0x270Fu, 0, 1u, 3u, (unsigned __int8 *)a2, *((_DWORD *)a2 + 1) + 8);
  v8 = v13;
  if ( v13 < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_28;
    LODWORD(v21) = v13;
    v11 = 11385;
    LODWORD(v19) = 9999;
    goto LABEL_11;
  }
  if ( !a3 )
  {
    v14 = CLocationWriter::AddProperty(v7, 0x2708u, 0, 1u, 3u, &g_XMLSchemaFileTimeStamp, 8u);
    v8 = v14;
    if ( v14 < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_28;
      LODWORD(v21) = v14;
      v11 = 11411;
      LODWORD(v19) = 9992;
      goto LABEL_11;
    }
    v15 = CLocationWriter::AddProperty(v7, 0x2707u, 0, 1u, 3u, &g_BINSchemaFileTimeStamp, 8u);
    v8 = v15;
    if ( v15 < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_28;
      LODWORD(v21) = v15;
      v11 = 11434;
      LODWORD(v19) = 9991;
LABEL_11:
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        v11,
        "SaveGlobalsToXML",
        L"[SaveGlobalsToXML] AddProperty for ID: %d failed with hr = 0x%x.\n",
        v19,
        v21);
      goto LABEL_28;
    }
  }
  v16 = CLocationWriter::WriteLocation(v7, v6);
  v8 = v16;
  if ( v16 < 0 && (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v19) = v16;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      11445,
      "SaveGlobalsToXML",
      L"[SaveGlobalsToXML] WriteLocation failed with hr = 0x%x.\n",
      v19);
  }
LABEL_28:
  if ( v7 )
    CLocationWriter::`scalar deleting destructor'(v7, v6);
  return v8;
}

```

## disassembly

```asm
0x180024388  mov     rax, rsp
0x18002438b  mov     [rax+8], rbx
0x18002438f  mov     [rax+10h], rbp
0x180024393  push    rsi
0x180024394  push    rdi
0x180024395  push    r14
0x180024397  sub     rsp, 50h
0x18002439b  mov     sil, r8b
0x18002439e  mov     qword ptr [rax-28h], 0
0x1800243a6  mov     rbp, rdx
0x1800243a9  mov     dword ptr [rax+20h], 0
0x1800243b0  lea     r8, String; "."
0x1800243b7  lea     rdx, [rax-28h]; struct CLocationWriter **
0x1800243bb  call    ?GetLocationWriter@CWriter@@QEAAJPEAPEAVCLocationWriter@@PEBG@Z; CWriter::GetLocationWriter(CLocationWriter * *,ushort const *)
0x1800243c0  mov     rdi, [rsp+68h+var_28]
0x1800243c5  mov     ebx, eax
0x1800243c7  test    eax, eax
0x1800243c9  jns     short loc_1800243EE
0x1800243cb  test    byte ptr cs:g_dwDebugFlags, 3
0x1800243d2  jz      loc_18002467B
0x1800243d8  mov     dword ptr [rsp+68h+var_40], eax
0x1800243dc  mov     r8d, 2C1Dh
0x1800243e2  lea     rax, aSaveglobalstox_0; "[SaveGlobalsToXML] GetLocationWriter fa"...
0x1800243e9  jmp     loc_18002465B
0x1800243ee  lea     rax, aIisGlobal; "IIS_Global"
0x1800243f5  mov     r14d, 1
0x1800243fb  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x180024400  mov     r9d, r14d; unsigned int
0x180024403  xor     r8d, r8d; unsigned int
0x180024406  mov     [rsp+68h+var_48], 2; unsigned int
0x18002440e  mov     rcx, rdi; this
0x180024411  call    ?InitializeKeyType@CLocationWriter@@QEAAJKKKKPEAEK@Z; CLocationWriter::InitializeKeyType(ulong,ulong,ulong,ulong,uchar *,ulong)
0x180024416  mov     ebx, eax
0x180024418  test    eax, eax
0x18002441a  jns     short loc_18002443F
0x18002441c  test    byte ptr cs:g_dwDebugFlags, 3
0x180024423  jz      loc_18002467B
0x180024429  mov     dword ptr [rsp+68h+var_40], eax
0x18002442d  mov     r8d, 2C2Dh
0x180024433  lea     rax, aSaveglobalstox_3; "[SaveGlobalsToXML] InitializeKeyType fa"...
0x18002443a  jmp     loc_18002465B
0x18002443f  test    sil, sil
0x180024442  jnz     loc_18002452E
0x180024448  lea     rax, ?g_dwSystemChangeNumber@@3KA; ulong g_dwSystemChangeNumber
0x18002444f  mov     [rsp+68h+var_38], 4; unsigned int
0x180024457  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x18002445c  mov     r9d, r14d; unsigned int
0x18002445f  xor     r8d, r8d; unsigned int
0x180024462  mov     [rsp+68h+var_48], r14d; unsigned int
0x180024467  mov     edx, 270Dh; unsigned int
0x18002446c  mov     rcx, rdi; this
0x18002446f  call    ?AddProperty@CLocationWriter@@QEAAJKKKKPEAEK@Z; CLocationWriter::AddProperty(ulong,ulong,ulong,ulong,uchar *,ulong)
0x180024474  mov     ebx, eax
0x180024476  test    eax, eax
0x180024478  jns     short loc_1800244C5
0x18002447a  test    byte ptr cs:g_dwDebugFlags, 3
0x180024481  jz      loc_18002467B
0x180024487  mov     [rsp+68h+var_38], eax
0x18002448b  mov     r8d, 2C46h
0x180024491  mov     dword ptr [rsp+68h+var_40], 270Dh
0x180024499  mov     rcx, cs:g_pDebug
0x1800244a0  lea     rax, aSaveglobalstox_2; "[SaveGlobalsToXML] AddProperty for ID: "...
0x1800244a7  lea     r9, aSaveglobalstox; "SaveGlobalsToXML"
0x1800244ae  mov     qword ptr [rsp+68h+var_48], rax
0x1800244b3  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x1800244ba  call    cs:__imp_PuDbgPrintW
0x1800244c0  jmp     loc_18002467B
0x1800244c5  call    ?ComputeNewHistoryVersionNumber@@YAJXZ; ComputeNewHistoryVersionNumber(void)
0x1800244ca  mov     eax, cs:?g_ulHistoryMajorVersionNumber@@3KA; ulong g_ulHistoryMajorVersionNumber
0x1800244d0  mov     r9d, r14d; unsigned int
0x1800244d3  mov     [rsp+68h+arg_18], eax
0x1800244da  xor     r8d, r8d; unsigned int
0x1800244dd  lea     rax, [rsp+68h+arg_18]
0x1800244e5  mov     [rsp+68h+var_38], 4; unsigned int
0x1800244ed  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x1800244f2  mov     edx, 270Ah; unsigned int
0x1800244f7  mov     rcx, rdi; this
0x1800244fa  mov     [rsp+68h+var_48], r14d; unsigned int
0x1800244ff  call    ?AddProperty@CLocationWriter@@QEAAJKKKKPEAEK@Z; CLocationWriter::AddProperty(ulong,ulong,ulong,ulong,uchar *,ulong)
0x180024504  mov     ebx, eax
0x180024506  test    eax, eax
0x180024508  jns     short loc_18002452E
0x18002450a  test    byte ptr cs:g_dwDebugFlags, 3
0x180024511  jz      loc_18002467B
0x180024517  mov     [rsp+68h+var_38], eax
0x18002451b  mov     r8d, 2C61h
0x180024521  mov     dword ptr [rsp+68h+var_40], 270Ah
0x180024529  jmp     loc_180024499
0x18002452e  mov     eax, [rbp+4]
0x180024531  mov     r9d, r14d; unsigned int
0x180024534  add     eax, 8
0x180024537  xor     r8d, r8d; unsigned int
0x18002453a  mov     [rsp+68h+var_38], eax; unsigned int
0x18002453e  mov     rcx, rdi; this
0x180024541  mov     [rsp+68h+var_40], rbp; unsigned __int8 *
0x180024546  mov     ebp, 270Fh
0x18002454b  mov     edx, ebp; unsigned int
0x18002454d  mov     [rsp+68h+var_48], 3; unsigned int
0x180024555  call    ?AddProperty@CLocationWriter@@QEAAJKKKKPEAEK@Z; CLocationWriter::AddProperty(ulong,ulong,ulong,ulong,uchar *,ulong)
0x18002455a  mov     ebx, eax
0x18002455c  test    eax, eax
0x18002455e  jns     short loc_180024580
0x180024560  test    byte ptr cs:g_dwDebugFlags, 3
0x180024567  jz      loc_18002467B
0x18002456d  mov     [rsp+68h+var_38], eax
0x180024571  mov     r8d, 2C79h
0x180024577  mov     dword ptr [rsp+68h+var_40], ebp
0x18002457b  jmp     loc_180024499
0x180024580  test    sil, sil
0x180024583  jnz     loc_180024633
0x180024589  lea     rax, ?g_XMLSchemaFileTimeStamp@@3U_FILETIME@@A; _FILETIME g_XMLSchemaFileTimeStamp
0x180024590  mov     [rsp+68h+var_38], 8; unsigned int
0x180024598  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x18002459d  mov     esi, 2708h
0x1800245a2  mov     edx, esi; unsigned int
0x1800245a4  mov     [rsp+68h+var_48], 3; unsigned int
0x1800245ac  mov     r9d, r14d; unsigned int
0x1800245af  xor     r8d, r8d; unsigned int
0x1800245b2  mov     rcx, rdi; this
0x1800245b5  call    ?AddProperty@CLocationWriter@@QEAAJKKKKPEAEK@Z; CLocationWriter::AddProperty(ulong,ulong,ulong,ulong,uchar *,ulong)
0x1800245ba  mov     ebx, eax
0x1800245bc  test    eax, eax
0x1800245be  jns     short loc_1800245E0
0x1800245c0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800245c7  jz      loc_18002467B
0x1800245cd  mov     [rsp+68h+var_38], eax
0x1800245d1  mov     r8d, 2C93h
0x1800245d7  mov     dword ptr [rsp+68h+var_40], esi
0x1800245db  jmp     loc_180024499
0x1800245e0  lea     rax, ?g_BINSchemaFileTimeStamp@@3U_FILETIME@@A; _FILETIME g_BINSchemaFileTimeStamp
0x1800245e7  mov     [rsp+68h+var_38], 8; unsigned int
0x1800245ef  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x1800245f4  mov     esi, 2707h
0x1800245f9  mov     edx, esi; unsigned int
0x1800245fb  mov     [rsp+68h+var_48], 3; unsigned int
0x180024603  mov     r9d, r14d; unsigned int
0x180024606  xor     r8d, r8d; unsigned int
0x180024609  mov     rcx, rdi; this
0x18002460c  call    ?AddProperty@CLocationWriter@@QEAAJKKKKPEAEK@Z; CLocationWriter::AddProperty(ulong,ulong,ulong,ulong,uchar *,ulong)
0x180024611  mov     ebx, eax
0x180024613  test    eax, eax
0x180024615  jns     short loc_180024633
0x180024617  test    byte ptr cs:g_dwDebugFlags, 3
0x18002461e  jz      short loc_18002467B
0x180024620  mov     [rsp+68h+var_38], eax
0x180024624  mov     r8d, 2CAAh
0x18002462a  mov     dword ptr [rsp+68h+var_40], esi
0x18002462e  jmp     loc_180024499
0x180024633  mov     rcx, rdi; this
0x180024636  call    ?WriteLocation@CLocationWriter@@QEAAJH@Z; CLocationWriter::WriteLocation(int)
0x18002463b  mov     ebx, eax
0x18002463d  test    eax, eax
0x18002463f  jns     short loc_18002467B
0x180024641  test    byte ptr cs:g_dwDebugFlags, 3
0x180024648  jz      short loc_18002467B
0x18002464a  mov     dword ptr [rsp+68h+var_40], eax
0x18002464e  mov     r8d, 2CB5h
0x180024654  lea     rax, aSaveglobalstox_1; "[SaveGlobalsToXML] WriteLocation failed"...
0x18002465b  mov     rcx, cs:g_pDebug
0x180024662  lea     r9, aSaveglobalstox; "SaveGlobalsToXML"
0x180024669  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180024670  mov     qword ptr [rsp+68h+var_48], rax
0x180024675  call    cs:__imp_PuDbgPrintW
0x18002467b  test    rdi, rdi
0x18002467e  jz      short loc_180024688
0x180024680  mov     rcx, rdi; this
0x180024683  call    ??_GCLocationWriter@@QEAAPEAXI@Z; CLocationWriter::`scalar deleting destructor'(uint)
0x180024688  mov     rbp, [rsp+68h+arg_8]
0x18002468d  mov     eax, ebx
0x18002468f  mov     rbx, [rsp+68h+arg_0]
0x180024694  add     rsp, 50h
0x180024698  pop     r14
0x18002469a  pop     rdi
0x18002469b  pop     rsi
0x18002469c  retn
```
