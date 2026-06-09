# CompileIfNeeded(ushort *,ushort *,int *,CEtwTracer *)

- ea: `0x18001b98c`
- end: `0x18001be05`
- name: `?CompileIfNeeded@@YAJPEAG0PEAHPEAVCEtwTracer@@@Z`
- size: `1145`
- prototype: `__int64 __fastcall(LPCWSTR lpString, unsigned __int16 *, int *, struct CEtwTracer *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021c40`

## callees

- `0x18001b98c`
- `0x18001be0c`
- `0x18001be78`
- `0x180020e0c`
- `0x180027534`
- `0x18002da58`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18001bb12`
- `KERNEL32!GetFileAttributesW` at `0x18001bb12`
- `IisRTL!PuDbgPrintW` at `0x18001ba96`
- `IisRTL!PuDbgPrintW` at `0x18001bbdf`
- `IisRTL!PuDbgPrintW` at `0x18001bc1e`
- `IisRTL!PuDbgPrintW` at `0x18001bc59`
- `IisRTL!PuDbgPrintW` at `0x18001bce6`
- `IisRTL!PuDbgPrintW` at `0x18001bd5f`
- `IisRTL!PuDbgPrintW` at `0x18001bdc1`
- `IisRTL!PuDbgPrintW` at `0x18001ba96`
- `IisRTL!PuDbgPrintW` at `0x18001bbdf`
- `IisRTL!PuDbgPrintW` at `0x18001bc1e`
- `IisRTL!PuDbgPrintW` at `0x18001bc59`
- `IisRTL!PuDbgPrintW` at `0x18001bce6`
- `IisRTL!PuDbgPrintW` at `0x18001bd5f`
- `IisRTL!PuDbgPrintW` at `0x18001bdc1`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18001ba0c`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18001ba0c`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001b9e9`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001ba55`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001bac5`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001b9e9`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001ba55`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18001bac5`

## string_xrefs

- `0x18001bdaf`: `[CompileIfNeeded] UpdateTimeStamp failed with hr = 0x%x.\n`
- `0x18001ba75`: `[CompileIfNeeded] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18001ba83`: `CompileIfNeeded`
- `0x18001bba8`: `CompileIfNeeded`
- `0x18001bbfa`: `CompileIfNeeded`
- `0x18001bc40`: `CompileIfNeeded`
- `0x18001bccd`: `CompileIfNeeded`
- `0x18001bd3b`: `CompileIfNeeded`
- `0x18001bd9d`: `CompileIfNeeded`
- `0x18001bb03`: `[CompileIfNeeded] QueryInterface on compiler failed with hr = 0x%x.\n`
- `0x18001bbc2`: `[CompileIfNeeded] Schema file: %s found. Schema bin file: %s is valid, and its timestamp matches what is stored in data file %s. No compilation reqired.\n`
- `0x18001bc0c`: `[CompileIfNeeded] Unable to get the the bin file name. (Assuming file is missing or invalid). InitializeGlobalISTHelper failed with hr = 0x%x.\n`
- `0x18001bc34`: `[CompileIfNeeded] Compiling from schema file %s\n`
- `0x18001bcc6`: `[CompileIfNeeded] Schema file not found or compile from it failed. Compiling from shipped schema\n`
- `0x18001bd4d`: `[CompileIfNeeded] Unable to get the the bin file name. (Assuming file is invalid). InitializeGlobalISTHelper failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CompileIfNeeded(LPCWSTR lpString, unsigned __int16 *a2, int *a3, struct CEtwTracer *a4)
{
  _BYTE *v4; // rbx
  _DWORD *v9; // rdi
  int SimpleObjectByIDEx; // eax
  int v11; // ecx
  int v12; // eax
  CWriterGlobalHelper *v13; // r8
  int GlobalHelper; // eax
  __int64 v15; // r8
  CWriterGlobalHelper *v16; // rdx
  int v17; // eax
  int updated; // eax
  __int64 v20; // [rsp+28h] [rbp-40h]
  int v21; // [rsp+40h] [rbp-28h] BYREF
  struct IMetabaseSchemaCompiler *v22; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v23[3]; // [rsp+50h] [rbp-18h] BYREF
  int matched; // [rsp+C8h] [rbp+60h] BYREF

  v4 = (char *)a4 + 40;
  matched = 0;
  v23[0] = 0;
  v22 = 0;
  if ( *((_DWORD *)a4 + 2) && (*v4 & 1) != 0 )
  {
    v9 = (_DWORD *)((char *)a4 + 44);
    if ( *((_DWORD *)a4 + 11) >= 4u )
      CEtwTracer::EtwTraceEvent(a4, (const struct _GUID *)IISAdminStatupGuid, 0x1Eu, 0, 0);
  }
  else
  {
    v9 = (_DWORD *)((char *)a4 + 44);
  }
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, v23, L"IIS");
  v11 = *((_DWORD *)a4 + 2);
  matched = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx < 0 )
  {
    if ( v11 && (*v4 & 1) != 0 && *v9 >= 2u )
      CEtwTracer::EtwTraceEvent(a4, (const struct _GUID *)IISAdminStatupGuid, 0x1Fu, &matched, 4, 0, 0);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v20) = matched;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        12790,
        "CompileIfNeeded",
        L"[CompileIfNeeded] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
        v20);
    }
    goto LABEL_44;
  }
  if ( v11 && (*v4 & 1) != 0 && *v9 >= 4u )
    CEtwTracer::EtwTraceEvent(a4, (const struct _GUID *)IISAdminStatupGuid, 0x20u);
  v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IMetabaseSchemaCompiler **))v23[0])(
          v23[0],
          &IID_IMetabaseSchemaCompiler,
          &v22);
  matched = v12;
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        12810,
        "CompileIfNeeded",
        L"[CompileIfNeeded] QueryInterface on compiler failed with hr = 0x%x.\n",
        v12);
    goto LABEL_44;
  }
  if ( GetFileAttributesW(a2) != -1 )
  {
    v13 = g_pGlobalISTHelper;
    v21 = 0;
    *a3 = 0;
    if ( v13 )
    {
      matched = MatchTimeStamp(lpString, a2, *((LPCWSTR *)v13 + 31), &v21);
      if ( matched < 0 )
        goto LABEL_44;
      if ( v21 )
      {
        if ( (g_dwDebugFlags & 3) == 0 )
          goto LABEL_44;
        v15 = 12890;
LABEL_29:
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          v15,
          "CompileIfNeeded",
          L"[CompileIfNeeded] Schema file: %s found. Schema bin file: %s is valid, and its timestamp matches what is store"
           "d in data file %s. No compilation reqired.\n",
          a2,
          *((_QWORD *)g_pGlobalISTHelper + 31),
          lpString);
        goto LABEL_44;
      }
    }
    else
    {
      GlobalHelper = GetGlobalHelper(1, &g_pGlobalISTHelper);
      matched = GlobalHelper;
      if ( GlobalHelper < 0 )
      {
        if ( (g_dwDebugFlags & 3) == 0 )
          goto LABEL_34;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          12863,
          "CompileIfNeeded",
          L"[CompileIfNeeded] Unable to get the the bin file name. (Assuming file is missing or invalid). InitializeGlobal"
           "ISTHelper failed with hr = 0x%x.\n",
          GlobalHelper);
      }
      else if ( g_pGlobalISTHelper )
      {
        matched = MatchTimeStamp(lpString, a2, *((LPCWSTR *)g_pGlobalISTHelper + 31), &v21);
        if ( matched < 0 )
          goto LABEL_44;
        if ( v21 )
        {
          if ( (g_dwDebugFlags & 3) == 0 )
            goto LABEL_44;
          v15 = 12854;
          goto LABEL_29;
        }
      }
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        12906,
        "CompileIfNeeded",
        L"[CompileIfNeeded] Compiling from schema file %s\n",
        a2);
LABEL_34:
    matched = CompileIntoBinFromSchemaFile(v22, a2);
    if ( matched >= 0 )
      goto LABEL_44;
    goto LABEL_41;
  }
  *a3 = 1;
LABEL_41:
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      12927,
      "CompileIfNeeded",
      L"[CompileIfNeeded] Schema file not found or compile from it failed. Compiling from shipped schema\n");
  matched = CompileIntoBin(v22, 0, a2);
LABEL_44:
  if ( matched >= 0 )
  {
    v16 = g_pGlobalISTHelper;
    if ( !g_pGlobalISTHelper )
    {
      v17 = GetGlobalHelper(1, &g_pGlobalISTHelper);
      matched = v17;
      if ( v17 < 0 && (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v20) = v17;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          12947,
          "CompileIfNeeded",
          L"[CompileIfNeeded] Unable to get the the bin file name. (Assuming file is invalid). InitializeGlobalISTHelper f"
           "ailed with hr = 0x%x.\n",
          v20);
      }
      v16 = g_pGlobalISTHelper;
    }
    if ( matched >= 0 )
    {
      if ( v16 )
      {
        updated = UpdateTimeStamp(a2, *((unsigned __int16 **)v16 + 31));
        matched = updated;
        if ( updated < 0 && (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v20) = updated;
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
            12961,
            "CompileIfNeeded",
            L"[CompileIfNeeded] UpdateTimeStamp failed with hr = 0x%x.\n",
            v20);
        }
      }
    }
  }
  if ( v22 )
    (*(void (__fastcall **)(struct IMetabaseSchemaCompiler *))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v23[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x18001b98c  push    rbp
0x18001b98e  push    rbx
0x18001b98f  push    rsi
0x18001b990  push    rdi
0x18001b991  push    r12
0x18001b993  push    r13
0x18001b995  push    r14
0x18001b997  push    r15
0x18001b999  mov     rbp, rsp
0x18001b99c  sub     rsp, 68h
0x18001b9a0  xor     r13d, r13d
0x18001b9a3  lea     rbx, [r9+28h]
0x18001b9a7  mov     rsi, r9
0x18001b9aa  mov     r15, r8
0x18001b9ad  mov     r14, rdx
0x18001b9b0  mov     r12, rcx
0x18001b9b3  mov     [rbp+arg_18], r13d
0x18001b9b7  mov     [rbp+var_18], r13
0x18001b9bb  mov     [rbp+var_20], r13
0x18001b9bf  cmp     [r9+8], r13d
0x18001b9c3  jz      short loc_18001B9F1
0x18001b9c5  test    byte ptr [rbx], 1
0x18001b9c8  jz      short loc_18001B9F1
0x18001b9ca  lea     rdi, [r9+2Ch]
0x18001b9ce  cmp     dword ptr [rdi], 4
0x18001b9d1  jb      short loc_18001B9F5
0x18001b9d3  xor     r9d, r9d
0x18001b9d6  mov     [rsp+68h+var_48], r13
0x18001b9db  lea     r8d, [r13+1Eh]
0x18001b9df  mov     rcx, rsi
0x18001b9e2  lea     rdx, IISAdminStatupGuid
0x18001b9e9  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18001b9ef  jmp     short loc_18001B9F5
0x18001b9f1  lea     rdi, [r9+2Ch]
0x18001b9f5  lea     r9, aIis; "IIS"
0x18001b9fc  mov     ecx, 1
0x18001ba01  lea     r8, [rbp+var_18]
0x18001ba05  lea     rdx, IID_ISimpleTableDispenser2
0x18001ba0c  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18001ba12  mov     ecx, [rsi+8]
0x18001ba15  mov     [rbp+arg_18], eax
0x18001ba18  test    eax, eax
0x18001ba1a  jns     loc_18001BAA1
0x18001ba20  test    ecx, ecx
0x18001ba22  jz      short loc_18001BA5B
0x18001ba24  test    byte ptr [rbx], 1
0x18001ba27  jz      short loc_18001BA5B
0x18001ba29  cmp     dword ptr [rdi], 2
0x18001ba2c  jb      short loc_18001BA5B
0x18001ba2e  mov     [rsp+68h+var_38], r13
0x18001ba33  lea     r9, [rbp+arg_18]
0x18001ba37  mov     [rsp+68h+var_40], r13
0x18001ba3c  lea     rdx, IISAdminStatupGuid
0x18001ba43  mov     r8d, 1Fh
0x18001ba49  mov     [rsp+68h+var_48], 4
0x18001ba52  mov     rcx, rsi
0x18001ba55  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18001ba5b  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ba62  jz      loc_18001BCFD
0x18001ba68  mov     eax, [rbp+arg_18]
0x18001ba6b  mov     r8d, 31F6h
0x18001ba71  mov     dword ptr [rsp+68h+var_40], eax
0x18001ba75  lea     rax, aCompileifneede; "[CompileIfNeeded] DllGetSimpleObjectByI"...
0x18001ba7c  mov     rcx, cs:g_pDebug
0x18001ba83  lea     r9, aCompileifneede_7; "CompileIfNeeded"
0x18001ba8a  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001ba91  mov     [rsp+68h+var_48], rax
0x18001ba96  call    cs:__imp_PuDbgPrintW
0x18001ba9c  jmp     loc_18001BCFD
0x18001baa1  test    ecx, ecx
0x18001baa3  jz      short loc_18001BACB
0x18001baa5  test    byte ptr [rbx], 1
0x18001baa8  jz      short loc_18001BACB
0x18001baaa  cmp     dword ptr [rdi], 4
0x18001baad  jb      short loc_18001BACB
0x18001baaf  xor     r9d, r9d
0x18001bab2  mov     [rsp+68h+var_48], r13
0x18001bab7  lea     rdx, IISAdminStatupGuid
0x18001babe  mov     rcx, rsi
0x18001bac1  lea     r8d, [r9+20h]
0x18001bac5  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18001bacb  mov     rcx, [rbp+var_18]
0x18001bacf  lea     r8, [rbp+var_20]
0x18001bad3  lea     rdx, IID_IMetabaseSchemaCompiler
0x18001bada  mov     rax, [rcx]
0x18001badd  mov     rax, [rax]
0x18001bae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bae5  mov     [rbp+arg_18], eax
0x18001bae8  test    eax, eax
0x18001baea  jns     short loc_18001BB0F
0x18001baec  test    byte ptr cs:g_dwDebugFlags, 3
0x18001baf3  jz      loc_18001BCFD
0x18001baf9  mov     dword ptr [rsp+68h+var_40], eax
0x18001bafd  mov     r8d, 320Ah
0x18001bb03  lea     rax, aCompileifneede_8; "[CompileIfNeeded] QueryInterface on com"...
0x18001bb0a  jmp     loc_18001BA7C
0x18001bb0f  mov     rcx, r14; lpFileName
0x18001bb12  call    cs:__imp_GetFileAttributesW
0x18001bb18  cmp     eax, 0FFFFFFFFh
0x18001bb1b  jz      loc_18001BCAF
0x18001bb21  mov     r8, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18001bb28  mov     [rbp+var_28], r13d
0x18001bb2c  mov     [r15], r13d
0x18001bb2f  test    r8, r8
0x18001bb32  jnz     loc_18001BC78
0x18001bb38  lea     rdx, ?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; struct CWriterGlobalHelper **
0x18001bb3f  lea     ecx, [r8+1]; int
0x18001bb43  call    ?GetGlobalHelper@@YAJHPEAPEAVCWriterGlobalHelper@@@Z; GetGlobalHelper(int,CWriterGlobalHelper * *)
0x18001bb48  mov     [rbp+arg_18], eax
0x18001bb4b  test    eax, eax
0x18001bb4d  js      loc_18001BBEA
0x18001bb53  mov     r8, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18001bb5a  test    r8, r8
0x18001bb5d  jz      loc_18001BC24
0x18001bb63  mov     r8, [r8+0F8h]; LPCWSTR
0x18001bb6a  lea     r9, [rbp+var_28]; int *
0x18001bb6e  mov     rdx, r14; lpFileName
0x18001bb71  mov     rcx, r12; lpString
0x18001bb74  call    ?MatchTimeStamp@@YAJPEAG00PEAH@Z; MatchTimeStamp(ushort *,ushort *,ushort *,int *)
0x18001bb79  mov     [rbp+arg_18], eax
0x18001bb7c  test    eax, eax
0x18001bb7e  js      loc_18001BCFD
0x18001bb84  cmp     [rbp+var_28], r13d
0x18001bb88  jz      loc_18001BC24
0x18001bb8e  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bb95  jz      loc_18001BCFD
0x18001bb9b  mov     r8d, 3236h
0x18001bba1  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18001bba8  lea     r9, aCompileifneede_7; "CompileIfNeeded"
0x18001bbaf  mov     [rsp+68h+var_30], r12
0x18001bbb4  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001bbbb  mov     rcx, [rax+0F8h]
0x18001bbc2  lea     rax, aCompileifneede_1; "[CompileIfNeeded] Schema file: %s found"...
0x18001bbc9  mov     [rsp+68h+var_38], rcx
0x18001bbce  mov     rcx, cs:g_pDebug
0x18001bbd5  mov     [rsp+68h+var_40], r14
0x18001bbda  mov     [rsp+68h+var_48], rax
0x18001bbdf  call    cs:__imp_PuDbgPrintW
0x18001bbe5  jmp     loc_18001BCFD
0x18001bbea  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bbf1  jz      short loc_18001BC5F
0x18001bbf3  mov     rcx, cs:g_pDebug
0x18001bbfa  lea     r9, aCompileifneede_7; "CompileIfNeeded"
0x18001bc01  mov     dword ptr [rsp+68h+var_40], eax
0x18001bc05  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001bc0c  lea     rax, aCompileifneede_0; "[CompileIfNeeded] Unable to get the the"...
0x18001bc13  mov     r8d, 323Fh
0x18001bc19  mov     [rsp+68h+var_48], rax
0x18001bc1e  call    cs:__imp_PuDbgPrintW
0x18001bc24  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bc2b  jz      short loc_18001BC5F
0x18001bc2d  mov     rcx, cs:g_pDebug
0x18001bc34  lea     rax, aCompileifneede_4; "[CompileIfNeeded] Compiling from schema"...
0x18001bc3b  mov     [rsp+68h+var_40], r14
0x18001bc40  lea     r9, aCompileifneede_7; "CompileIfNeeded"
0x18001bc47  mov     r8d, 326Ah
0x18001bc4d  mov     [rsp+68h+var_48], rax
0x18001bc52  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001bc59  call    cs:__imp_PuDbgPrintW
0x18001bc5f  mov     rcx, [rbp+var_20]; struct IMetabaseSchemaCompiler *
0x18001bc63  mov     rdx, r14; unsigned __int16 *
0x18001bc66  call    ?CompileIntoBinFromSchemaFile@@YAJPEAUIMetabaseSchemaCompiler@@PEBG@Z; CompileIntoBinFromSchemaFile(IMetabaseSchemaCompiler *,ushort const *)
0x18001bc6b  mov     [rbp+arg_18], eax
0x18001bc6e  test    eax, eax
0x18001bc70  jns     loc_18001BCFD
0x18001bc76  jmp     short loc_18001BCB6
0x18001bc78  mov     r8, [r8+0F8h]; LPCWSTR
0x18001bc7f  lea     r9, [rbp+var_28]; int *
0x18001bc83  mov     rdx, r14; lpFileName
0x18001bc86  mov     rcx, r12; lpString
0x18001bc89  call    ?MatchTimeStamp@@YAJPEAG00PEAH@Z; MatchTimeStamp(ushort *,ushort *,ushort *,int *)
0x18001bc8e  mov     [rbp+arg_18], eax
0x18001bc91  test    eax, eax
0x18001bc93  js      short loc_18001BCFD
0x18001bc95  cmp     [rbp+var_28], r13d
0x18001bc99  jz      short loc_18001BC24
0x18001bc9b  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bca2  jz      short loc_18001BCFD
0x18001bca4  mov     r8d, 325Ah
0x18001bcaa  jmp     loc_18001BBA1
0x18001bcaf  mov     dword ptr [r15], 1
0x18001bcb6  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bcbd  jz      short loc_18001BCEC
0x18001bcbf  mov     rcx, cs:g_pDebug
0x18001bcc6  lea     rax, aCompileifneede_6; "[CompileIfNeeded] Schema file not found"...
0x18001bccd  lea     r9, aCompileifneede_7; "CompileIfNeeded"
0x18001bcd4  mov     [rsp+68h+var_48], rax
0x18001bcd9  mov     r8d, 327Fh
0x18001bcdf  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001bce6  call    cs:__imp_PuDbgPrintW
0x18001bcec  mov     rcx, [rbp+var_20]; struct IMetabaseSchemaCompiler *
0x18001bcf0  mov     r8, r14; unsigned __int16 *
0x18001bcf3  xor     edx, edx; unsigned __int16 *
0x18001bcf5  call    ?CompileIntoBin@@YAJPEAUIMetabaseSchemaCompiler@@PEBG1@Z; CompileIntoBin(IMetabaseSchemaCompiler *,ushort const *,ushort const *)
0x18001bcfa  mov     [rbp+arg_18], eax
0x18001bcfd  cmp     [rbp+arg_18], r13d
0x18001bd01  jl      loc_18001BDC7
0x18001bd07  mov     rdx, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18001bd0e  test    rdx, rdx
0x18001bd11  jnz     short loc_18001BD6C
0x18001bd13  lea     rdx, ?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; struct CWriterGlobalHelper **
0x18001bd1a  mov     ecx, 1; int
0x18001bd1f  call    ?GetGlobalHelper@@YAJHPEAPEAVCWriterGlobalHelper@@@Z; GetGlobalHelper(int,CWriterGlobalHelper * *)
0x18001bd24  mov     [rbp+arg_18], eax
0x18001bd27  test    eax, eax
0x18001bd29  jns     short loc_18001BD65
0x18001bd2b  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bd32  jz      short loc_18001BD65
0x18001bd34  mov     rcx, cs:g_pDebug
0x18001bd3b  lea     r9, aCompileifneede_7; "CompileIfNeeded"
0x18001bd42  mov     dword ptr [rsp+68h+var_40], eax
0x18001bd46  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001bd4d  lea     rax, aCompileifneede_3; "[CompileIfNeeded] Unable to get the the"...
0x18001bd54  mov     r8d, 3293h
0x18001bd5a  mov     [rsp+68h+var_48], rax
0x18001bd5f  call    cs:__imp_PuDbgPrintW
0x18001bd65  mov     rdx, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18001bd6c  cmp     [rbp+arg_18], r13d
0x18001bd70  jl      short loc_18001BDC7
0x18001bd72  test    rdx, rdx
0x18001bd75  jz      short loc_18001BDC7
0x18001bd77  mov     rdx, [rdx+0F8h]; unsigned __int16 *
0x18001bd7e  mov     rcx, r14; unsigned __int16 *
0x18001bd81  call    ?UpdateTimeStamp@@YAJPEAG0@Z; UpdateTimeStamp(ushort *,ushort *)
0x18001bd86  mov     [rbp+arg_18], eax
0x18001bd89  test    eax, eax
0x18001bd8b  jns     short loc_18001BDC7
0x18001bd8d  test    byte ptr cs:g_dwDebugFlags, 3
0x18001bd94  jz      short loc_18001BDC7
0x18001bd96  mov     rcx, cs:g_pDebug
0x18001bd9d  lea     r9, aCompileifneede_7; "CompileIfNeeded"
0x18001bda4  mov     dword ptr [rsp+68h+var_40], eax
0x18001bda8  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001bdaf  lea     rax, aCompileifneede_5; "[CompileIfNeeded] UpdateTimeStamp faile"...
0x18001bdb6  mov     r8d, 32A1h
0x18001bdbc  mov     [rsp+68h+var_48], rax
0x18001bdc1  call    cs:__imp_PuDbgPrintW
0x18001bdc7  mov     rcx, [rbp+var_20]
0x18001bdcb  test    rcx, rcx
0x18001bdce  jz      short loc_18001BDDC
0x18001bdd0  mov     rax, [rcx]
0x18001bdd3  mov     rax, [rax+10h]
0x18001bdd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bddc  mov     rcx, [rbp+var_18]
0x18001bde0  test    rcx, rcx
0x18001bde3  jz      short loc_18001BDF1
0x18001bde5  mov     rax, [rcx]
0x18001bde8  mov     rax, [rax+10h]
0x18001bdec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdf1  mov     eax, [rbp+arg_18]
0x18001bdf4  add     rsp, 68h
0x18001bdf8  pop     r15
0x18001bdfa  pop     r14
0x18001bdfc  pop     r13
0x18001bdfe  pop     r12
0x18001be00  pop     rdi
0x18001be01  pop     rsi
0x18001be02  pop     rbx
0x18001be03  pop     rbp
0x18001be04  retn
```
