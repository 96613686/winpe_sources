# isocom_ParseManifest(ushort const *,IManifestParseErrorCallback *,_GUID const &,IUnknown * *)

- ea: `0x180013770`
- end: `0x180013d61`
- name: `?isocom_ParseManifest@@YAJPEBGPEAUIManifestParseErrorCallback@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `1521`
- prototype: `__int64 __fastcall(struct _RTL_ALLOCATION_LIST *, struct IManifestParseErrorCallback *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800069b5`
- `0x1800069c1`
- `0x180012b1c`
- `0x180012b38`
- `0x180013770`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800199b4`
- `0x1800237b8`
- `0x18002f364`
- `0x180030344`
- `0x180036704`
- `0x18004f2dc`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180013816`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180013a7e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180013816`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180013a7e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800138a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800139be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013b2c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013c29`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013cfb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800138a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800139be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013b2c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013c29`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013cfb`

## string_xrefs

- `0x180013795`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\globalfunctions.cpp`
- `0x180013851`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18001396d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180013acb`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180013bc8`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180013c9a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`

## pseudocode

```c
__int64 __fastcall isocom_ParseManifest(
        struct _RTL_ALLOCATION_LIST *a1,
        struct IManifestParseErrorCallback *a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  unsigned int v7; // edi
  int v8; // eax
  struct _LUNICODE_STRING *v9; // r9
  unsigned int v10; // ebx
  int v11; // edx
  __int64 v12; // r10
  unsigned int *v13; // r11
  signed int v14; // ecx
  void (__fastcall *v15)(LPVOID *); // rax
  HANDLE v16; // rax
  LPVOID *v17; // rbx
  int v18; // eax
  __int64 v19; // r8
  int v20; // r9d
  __int64 v21; // r10
  unsigned int *v22; // r11
  signed int v23; // ecx
  void (__fastcall *v24)(LPVOID *); // rax
  HANDLE v25; // rax
  LPVOID *v26; // rbx
  __int64 v27; // rbx
  int v28; // eax
  unsigned int v29; // edi
  int v30; // edx
  unsigned int *v31; // r10
  signed int v32; // ecx
  void (__fastcall *v33)(LPVOID *); // rax
  HANDLE v34; // rax
  LPVOID *v35; // rbx
  int v36; // eax
  int v37; // r9d
  unsigned int *v38; // r10
  signed int v39; // ecx
  void (__fastcall *v40)(LPVOID *); // rax
  HANDLE v41; // rax
  LPVOID *v42; // rbx
  unsigned int *v43; // r10
  signed int v44; // ecx
  void (__fastcall *v45)(LPVOID *); // rax
  HANDLE ProcessHeap_0; // rax
  LPVOID *v47; // rbx
  unsigned int v49; // [rsp+20h] [rbp-39h]
  LPVOID lpMem[2]; // [rsp+30h] [rbp-29h] BYREF
  const char *v51; // [rsp+40h] [rbp-19h] BYREF
  __int64 v52; // [rsp+48h] [rbp-11h]
  DWORD dwExceptionCode[2]; // [rsp+50h] [rbp-9h]
  int v54; // [rsp+58h] [rbp-1h]
  __int128 v55; // [rsp+60h] [rbp+7h]
  unsigned __int16 v56[8]; // [rsp+70h] [rbp+17h] BYREF
  __int64 v57; // [rsp+80h] [rbp+27h]
  __int64 v58; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v59; // [rsp+D8h] [rbp+7Fh] BYREF

  dwExceptionCode[0] = -2147023537;
  v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp";
  if ( a4 )
    *a4 = 0;
  if ( !a1 )
  {
    LODWORD(v52) = 458;
LABEL_5:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v51);
    return dwExceptionCode[0];
  }
  if ( !a4 )
  {
    LODWORD(v52) = 459;
    goto LABEL_5;
  }
  v59 = 0;
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
  v8 = RtlCreateDirectIsolatedFilesystem(a1, &v59);
  v10 = v8;
  if ( v8 >= 0 )
  {
    v58 = 0;
    v57 = 0;
    *(_OWORD *)v56 = 0;
    v18 = IsolationImplementation::Com::ConvertFilePathIn((IsolationImplementation::Com *)lpMem, a1, v56, v9);
    v7 = v18;
    if ( v18 >= 0 )
    {
      v27 = v59;
      *(_QWORD *)dwExceptionCode = v56;
      v51 = (const char *)48;
      v52 = 0;
      v54 = 64;
      v55 = 0;
      v28 = RtlCompileCdfFromIsolatedFilesystemFile(v59, &v51, v19, &v58);
      v29 = v28;
      if ( v28 >= 0 )
      {
        v36 = IsolationImplementation::Com::CopyOut(v58, a3, a4);
        v7 = v36;
        if ( v36 >= 0 )
        {
          v7 = 0;
          if ( v58 )
          {
            CdfCloseHandle();
            v58 = 0;
          }
          if ( v27 )
          {
            ++g_nRtlCloseIsolatedFilesystemHandle;
            dwExceptionCode[0] = -1073741595;
            v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v27) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v43 + 4))(*v43, v27);
              v44 = 0;
            }
            else
            {
              LODWORD(v52) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v51);
              v44 = dwExceptionCode[0];
            }
            if ( v44 < 0 )
              RaiseException(v44, 1u, 0, 0);
          }
          while ( 1 )
          {
            v47 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v47 == lpMem )
              break;
            v45 = (void (__fastcall *)(LPVOID *))v47[2];
            if ( v45 )
              v45(v47 + 3);
            ProcessHeap_0 = GetProcessHeap_0();
            HeapFree_0(ProcessHeap_0, 0, v47);
          }
        }
        else
        {
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
            (const char *)0x1E5,
            v36,
            v37);
          if ( v58 )
          {
            CdfCloseHandle();
            v58 = 0;
          }
          if ( v27 )
          {
            ++g_nRtlCloseIsolatedFilesystemHandle;
            dwExceptionCode[0] = -1073741595;
            v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v27) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v38 + 4))(*v38, v27);
              v39 = 0;
            }
            else
            {
              LODWORD(v52) = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v51);
              v39 = dwExceptionCode[0];
            }
            if ( v39 < 0 )
              RaiseException(v39, 1u, 0, 0);
          }
          while ( 1 )
          {
            v42 = (LPVOID *)lpMem[0];
            lpMem[0] = *(LPVOID *)lpMem[0];
            *((_QWORD *)lpMem[0] + 1) = lpMem;
            if ( v42 == lpMem )
              break;
            v40 = (void (__fastcall *)(LPVOID *))v42[2];
            if ( v40 )
              v40(v42 + 3);
            v41 = GetProcessHeap_0();
            HeapFree_0(v41, 0, v42);
          }
        }
      }
      else
      {
        if ( v28 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
          (const char *)0x1E1,
          v29,
          (unsigned int)comglobalfunctions_ManifestParseErrorCallback);
        v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v29, v30);
        if ( v58 )
        {
          CdfCloseHandle();
          v58 = 0;
        }
        if ( v27 )
        {
          ++g_nRtlCloseIsolatedFilesystemHandle;
          dwExceptionCode[0] = -1073741595;
          v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v27) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v31 + 4))(*v31, v27);
            v32 = 0;
          }
          else
          {
            LODWORD(v52) = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v51);
            v32 = dwExceptionCode[0];
          }
          if ( v32 < 0 )
            RaiseException(v32, 1u, 0, 0);
        }
        while ( 1 )
        {
          v35 = (LPVOID *)lpMem[0];
          lpMem[0] = *(LPVOID *)lpMem[0];
          *((_QWORD *)lpMem[0] + 1) = lpMem;
          if ( v35 == lpMem )
            break;
          v33 = (void (__fastcall *)(LPVOID *))v35[2];
          if ( v33 )
            v33(v35 + 3);
          v34 = GetProcessHeap_0();
          HeapFree_0(v34, 0, v35);
        }
      }
    }
    else
    {
      Windows::ErrorHandling::COM::ReportErrorPropagation(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
        (const char *)0x1D6,
        v18,
        v20);
      if ( v58 )
      {
        CdfCloseHandle();
        v58 = 0;
      }
      if ( v59 )
      {
        ++g_nRtlCloseIsolatedFilesystemHandle;
        dwExceptionCode[0] = -1073741595;
        v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v59) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v22 + 4))(*v22, v21);
          v23 = 0;
        }
        else
        {
          LODWORD(v52) = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v51);
          v23 = dwExceptionCode[0];
        }
        if ( v23 < 0 )
          RaiseException(v23, 1u, 0, 0);
      }
      while ( 1 )
      {
        v26 = (LPVOID *)lpMem[0];
        lpMem[0] = *(LPVOID *)lpMem[0];
        *((_QWORD *)lpMem[0] + 1) = lpMem;
        if ( v26 == lpMem )
          break;
        v24 = (void (__fastcall *)(LPVOID *))v26[2];
        if ( v24 )
          v24(v26 + 3);
        v25 = GetProcessHeap_0();
        HeapFree_0(v25, 0, v26);
      }
    }
  }
  else
  {
    if ( v8 == g_NTSTATUS_to_break_on_propagate )
      DebugBreak();
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\globalfunctions.cpp",
      (const char *)0x1D1,
      v10,
      v49);
    v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v10, v11);
    if ( v59 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      dwExceptionCode[0] = -1073741595;
      v51 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v59) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v13 + 4))(*v13, v12);
        v14 = 0;
      }
      else
      {
        LODWORD(v52) = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v51);
        v14 = dwExceptionCode[0];
      }
      if ( v14 < 0 )
        RaiseException(v14, 1u, 0, 0);
    }
    while ( 1 )
    {
      v17 = (LPVOID *)lpMem[0];
      lpMem[0] = *(LPVOID *)lpMem[0];
      *((_QWORD *)lpMem[0] + 1) = lpMem;
      if ( v17 == lpMem )
        break;
      v15 = (void (__fastcall *)(LPVOID *))v17[2];
      if ( v15 )
        v15(v17 + 3);
      v16 = GetProcessHeap_0();
      HeapFree_0(v16, 0, v17);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180013770  mov     [rsp-8+arg_8], rbx
0x180013775  mov     [rsp-8+arg_10], rsi
0x18001377a  push    rbp
0x18001377b  push    rdi
0x18001377c  push    r13
0x18001377e  push    r14
0x180013780  push    r15
0x180013782  lea     rbp, [rsp-37h]
0x180013787  sub     rsp, 90h
0x18001378e  mov     [rbp+57h+dwExceptionCode], 8007054Fh
0x180013795  lea     r13, aOnecoreComNetf_38; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001379c  mov     [rbp+57h+var_70], r13
0x1800137a0  mov     rsi, r9
0x1800137a3  mov     r14, r8
0x1800137a6  mov     r15, rdx
0x1800137a9  mov     rdi, rcx
0x1800137ac  test    r9, r9
0x1800137af  jz      short loc_1800137B8
0x1800137b1  mov     qword ptr [r9], 0
0x1800137b8  test    rdi, rdi
0x1800137bb  jnz     short loc_1800137D5
0x1800137bd  mov     dword ptr [rbp+57h+var_68], 1CAh
0x1800137c4  lea     rcx, [rbp+57h+var_70]
0x1800137c8  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800137cd  mov     edi, [rbp+57h+dwExceptionCode]
0x1800137d0  jmp     loc_180013D43
0x1800137d5  test    rsi, rsi
0x1800137d8  jnz     short loc_1800137E3
0x1800137da  mov     dword ptr [rbp+57h+var_68], 1CBh
0x1800137e1  jmp     short loc_1800137C4
0x1800137e3  lea     rax, [rbp+57h+lpMem]
0x1800137e7  mov     [rbp+57h+arg_18], 0
0x1800137ef  mov     [rbp+57h+var_78], rax
0x1800137f3  lea     rdx, [rbp+57h+arg_18]
0x1800137f7  lea     rax, [rbp+57h+lpMem]
0x1800137fb  mov     [rbp+57h+lpMem], rax
0x1800137ff  call    RtlCreateDirectIsolatedFilesystem
0x180013804  mov     ebx, eax
0x180013806  test    eax, eax
0x180013808  jns     loc_180013904
0x18001380e  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180013814  jnz     short loc_18001381C
0x180013816  call    cs:__imp_DebugBreak
0x18001381c  mov     r9d, ebx; int
0x18001381f  lea     rcx, aStatusPropagat; "Status propagated"
0x180013826  mov     r8d, 1D1h; char *
0x18001382c  mov     rdx, r13; char *
0x18001382f  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180013834  mov     ecx, ebx; this
0x180013836  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18001383b  mov     r10, [rbp+57h+arg_18]
0x18001383f  mov     edi, eax
0x180013841  test    r10, r10
0x180013844  jz      loc_1800138E3
0x18001384a  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x180013851  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180013858  mov     [rbp+57h+dwExceptionCode], 0C00000E5h
0x18001385f  mov     [rbp+57h+var_70], rcx
0x180013863  test    r10, r10
0x180013866  jz      short loc_180013892
0x180013868  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18001386f  test    r11, r11
0x180013872  jz      short loc_1800138AA
0x180013874  mov     rdx, r11
0x180013877  mov     rcx, r10
0x18001387a  call    RtlIsTypeSafeHandleValid
0x18001387f  test    al, al
0x180013881  jz      short loc_1800138AA
0x180013883  mov     ecx, [r11]
0x180013886  mov     rdx, r10
0x180013889  mov     rax, [r11+20h]
0x18001388d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013892  xor     ecx, ecx; dwExceptionCode
0x180013894  test    ecx, ecx
0x180013896  jns     short loc_1800138E3
0x180013898  xor     r9d, r9d; lpArguments
0x18001389b  xor     r8d, r8d; nNumberOfArguments
0x18001389e  lea     edx, [r9+1]; dwExceptionFlags
0x1800138a2  call    cs:__imp_RaiseException
0x1800138a8  jmp     short loc_1800138E3
0x1800138aa  mov     dword ptr [rbp+57h+var_68], 124h
0x1800138b1  lea     rcx, [rbp+57h+var_70]
0x1800138b5  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800138ba  mov     ecx, [rbp+57h+dwExceptionCode]
0x1800138bd  jmp     short loc_180013894
0x1800138bf  mov     rax, [rbx+10h]
0x1800138c3  test    rax, rax
0x1800138c6  jz      short loc_1800138D1
0x1800138c8  lea     rcx, [rbx+18h]
0x1800138cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d1  call    GetProcessHeap_0
0x1800138d6  mov     r8, rbx; lpMem
0x1800138d9  xor     edx, edx; dwFlags
0x1800138db  mov     rcx, rax; hHeap
0x1800138de  call    HeapFree_0
0x1800138e3  mov     rbx, [rbp+57h+lpMem]
0x1800138e7  lea     rcx, [rbp+57h+lpMem]
0x1800138eb  mov     rax, [rbx]
0x1800138ee  mov     [rbp+57h+lpMem], rax
0x1800138f2  mov     [rax+8], rcx
0x1800138f6  lea     rax, [rbp+57h+lpMem]
0x1800138fa  cmp     rbx, rax
0x1800138fd  jnz     short loc_1800138BF
0x1800138ff  jmp     loc_180013D43
0x180013904  xorps   xmm0, xmm0
0x180013907  mov     [rbp+57h+arg_0], 0
0x18001390f  xor     eax, eax
0x180013911  lea     r8, [rbp+57h+var_40]; unsigned __int16 *
0x180013915  mov     rdx, rdi; struct _RTL_ALLOCATION_LIST *
0x180013918  mov     [rbp+57h+var_30], rax
0x18001391c  lea     rcx, [rbp+57h+lpMem]; this
0x180013920  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180013924  call    ?ConvertFilePathIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBGAEAU_LUNICODE_STRING@@@Z; IsolationImplementation::Com::ConvertFilePathIn(_RTL_ALLOCATION_LIST *,ushort const *,_LUNICODE_STRING &)
0x180013929  mov     edi, eax
0x18001392b  test    eax, eax
0x18001392d  jns     loc_180013A20
0x180013933  mov     r8d, eax; int
0x180013936  mov     edx, 1D6h; char *
0x18001393b  mov     rcx, r13; this
0x18001393e  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180013943  mov     rcx, [rbp+57h+arg_0]
0x180013947  test    rcx, rcx
0x18001394a  jz      short loc_180013959
0x18001394c  call    CdfCloseHandle
0x180013951  mov     [rbp+57h+arg_0], 0
0x180013959  mov     r10, [rbp+57h+arg_18]
0x18001395d  test    r10, r10
0x180013960  jz      loc_1800139FF
0x180013966  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x18001396d  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180013974  mov     [rbp+57h+dwExceptionCode], 0C00000E5h
0x18001397b  mov     [rbp+57h+var_70], rcx
0x18001397f  test    r10, r10
0x180013982  jz      short loc_1800139AE
0x180013984  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18001398b  test    r11, r11
0x18001398e  jz      short loc_1800139C6
0x180013990  mov     rdx, r11
0x180013993  mov     rcx, r10
0x180013996  call    RtlIsTypeSafeHandleValid
0x18001399b  test    al, al
0x18001399d  jz      short loc_1800139C6
0x18001399f  mov     ecx, [r11]
0x1800139a2  mov     rdx, r10
0x1800139a5  mov     rax, [r11+20h]
0x1800139a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139ae  xor     ecx, ecx; dwExceptionCode
0x1800139b0  test    ecx, ecx
0x1800139b2  jns     short loc_1800139FF
0x1800139b4  xor     r9d, r9d; lpArguments
0x1800139b7  xor     r8d, r8d; nNumberOfArguments
0x1800139ba  lea     edx, [r9+1]; dwExceptionFlags
0x1800139be  call    cs:__imp_RaiseException
0x1800139c4  jmp     short loc_1800139FF
0x1800139c6  mov     dword ptr [rbp+57h+var_68], 124h
0x1800139cd  lea     rcx, [rbp+57h+var_70]
0x1800139d1  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800139d6  mov     ecx, [rbp+57h+dwExceptionCode]
0x1800139d9  jmp     short loc_1800139B0
0x1800139db  mov     rax, [rbx+10h]
0x1800139df  test    rax, rax
0x1800139e2  jz      short loc_1800139ED
0x1800139e4  lea     rcx, [rbx+18h]
0x1800139e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139ed  call    GetProcessHeap_0
0x1800139f2  mov     r8, rbx; lpMem
0x1800139f5  xor     edx, edx; dwFlags
0x1800139f7  mov     rcx, rax; hHeap
0x1800139fa  call    HeapFree_0
0x1800139ff  mov     rbx, [rbp+57h+lpMem]
0x180013a03  lea     rcx, [rbp+57h+lpMem]
0x180013a07  mov     rax, [rbx]
0x180013a0a  mov     [rbp+57h+lpMem], rax
0x180013a0e  mov     [rax+8], rcx
0x180013a12  lea     rax, [rbp+57h+lpMem]
0x180013a16  cmp     rbx, rax
0x180013a19  jnz     short loc_1800139DB
0x180013a1b  jmp     loc_180013D43
0x180013a20  mov     rbx, [rbp+57h+arg_18]
0x180013a24  lea     rax, [rbp+57h+var_40]
0x180013a28  mov     qword ptr [rbp+57h+dwExceptionCode], rax
0x180013a2c  lea     r9, [rbp+57h+arg_0]
0x180013a30  lea     rax, comglobalfunctions_ManifestParseErrorCallback
0x180013a37  mov     [rsp+0B0h+var_88], r15
0x180013a3c  xorps   xmm0, xmm0
0x180013a3f  mov     qword ptr [rsp+0B0h+var_90], rax; unsigned int
0x180013a44  lea     rdx, [rbp+57h+var_70]
0x180013a48  mov     [rbp+57h+var_70], 30h ; '0'
0x180013a50  mov     rcx, rbx
0x180013a53  mov     [rbp+57h+var_68], 0
0x180013a5b  mov     [rbp+57h+var_58], 40h ; '@'
0x180013a62  movdqu  [rbp+57h+var_50], xmm0
0x180013a67  call    RtlCompileCdfFromIsolatedFilesystemFile
0x180013a6c  mov     edi, eax
0x180013a6e  test    eax, eax
0x180013a70  jns     loc_180013B79
0x180013a76  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180013a7c  jnz     short loc_180013A84
0x180013a7e  call    cs:__imp_DebugBreak
0x180013a84  mov     r9d, edi; int
0x180013a87  lea     rcx, aStatusPropagat; "Status propagated"
0x180013a8e  mov     r8d, 1E1h; char *
0x180013a94  mov     rdx, r13; char *
0x180013a97  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180013a9c  mov     ecx, edi; this
0x180013a9e  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180013aa3  mov     rcx, [rbp+57h+arg_0]
0x180013aa7  mov     edi, eax
0x180013aa9  test    rcx, rcx
0x180013aac  jz      short loc_180013ABB
0x180013aae  call    CdfCloseHandle
0x180013ab3  mov     [rbp+57h+arg_0], 0
0x180013abb  test    rbx, rbx
0x180013abe  jz      loc_180013B58
0x180013ac4  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x180013acb  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180013ad2  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x180013ad9  mov     [rbp+57h+dwExceptionCode], 0C00000E5h
0x180013ae0  mov     [rbp+57h+var_70], rcx
0x180013ae4  test    r10, r10
0x180013ae7  jz      short loc_180013B0B
0x180013ae9  mov     rdx, r10
0x180013aec  mov     rcx, rbx
0x180013aef  call    RtlIsTypeSafeHandleValid
0x180013af4  test    al, al
0x180013af6  jz      short loc_180013B0B
0x180013af8  mov     ecx, [r10]
0x180013afb  mov     rdx, rbx
0x180013afe  mov     rax, [r10+20h]
0x180013b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b07  xor     ecx, ecx
0x180013b09  jmp     short loc_180013B1E
0x180013b0b  mov     dword ptr [rbp+57h+var_68], 124h
0x180013b12  lea     rcx, [rbp+57h+var_70]
0x180013b16  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180013b1b  mov     ecx, [rbp+57h+dwExceptionCode]; dwExceptionCode
0x180013b1e  test    ecx, ecx
0x180013b20  jns     short loc_180013B58
0x180013b22  xor     r9d, r9d; lpArguments
0x180013b25  xor     r8d, r8d; nNumberOfArguments
0x180013b28  lea     edx, [r9+1]; dwExceptionFlags
0x180013b2c  call    cs:__imp_RaiseException
0x180013b32  jmp     short loc_180013B58
0x180013b34  mov     rax, [rbx+10h]
0x180013b38  test    rax, rax
0x180013b3b  jz      short loc_180013B46
0x180013b3d  lea     rcx, [rbx+18h]
0x180013b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b46  call    GetProcessHeap_0
0x180013b4b  mov     r8, rbx; lpMem
0x180013b4e  xor     edx, edx; dwFlags
0x180013b50  mov     rcx, rax; hHeap
0x180013b53  call    HeapFree_0
0x180013b58  mov     rbx, [rbp+57h+lpMem]
0x180013b5c  lea     rcx, [rbp+57h+lpMem]
0x180013b60  mov     rax, [rbx]
0x180013b63  mov     [rbp+57h+lpMem], rax
0x180013b67  mov     [rax+8], rcx
0x180013b6b  lea     rax, [rbp+57h+lpMem]
0x180013b6f  cmp     rbx, rax
0x180013b72  jnz     short loc_180013B34
0x180013b74  jmp     loc_180013D43
0x180013b79  mov     rcx, [rbp+57h+arg_0]
0x180013b7d  mov     r8, rsi
0x180013b80  mov     rdx, r14
0x180013b83  call    ?CopyOut@Com@IsolationImplementation@@YAJU_CDF@Rtl@Cdf@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CopyOut(Windows::Cdf::Rtl::_CDF,_GUID const &,IUnknown * *)
0x180013b88  mov     edi, eax
0x180013b8a  test    eax, eax
0x180013b8c  jns     loc_180013C76
0x180013b92  mov     r8d, eax; int
0x180013b95  mov     edx, 1E5h; char *
0x180013b9a  mov     rcx, r13; this
0x180013b9d  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180013ba2  mov     rcx, [rbp+57h+arg_0]
0x180013ba6  test    rcx, rcx
0x180013ba9  jz      short loc_180013BB8
0x180013bab  call    CdfCloseHandle
0x180013bb0  mov     [rbp+57h+arg_0], 0
0x180013bb8  test    rbx, rbx
0x180013bbb  jz      loc_180013C55
0x180013bc1  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x180013bc8  lea     rcx, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180013bcf  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x180013bd6  mov     [rbp+57h+dwExceptionCode], 0C00000E5h
0x180013bdd  mov     [rbp+57h+var_70], rcx
0x180013be1  test    r10, r10
0x180013be4  jz      short loc_180013C08
0x180013be6  mov     rdx, r10
0x180013be9  mov     rcx, rbx
0x180013bec  call    RtlIsTypeSafeHandleValid
0x180013bf1  test    al, al
0x180013bf3  jz      short loc_180013C08
0x180013bf5  mov     ecx, [r10]
0x180013bf8  mov     rdx, rbx
0x180013bfb  mov     rax, [r10+20h]
0x180013bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c04  xor     ecx, ecx
0x180013c06  jmp     short loc_180013C1B
0x180013c08  mov     dword ptr [rbp+57h+var_68], 124h
0x180013c0f  lea     rcx, [rbp+57h+var_70]
  ... truncated ...
```
