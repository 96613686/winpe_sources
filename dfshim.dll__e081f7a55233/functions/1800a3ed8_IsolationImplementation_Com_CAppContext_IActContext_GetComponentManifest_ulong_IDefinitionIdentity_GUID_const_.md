# IsolationImplementation::Com::CAppContext::IActContext_GetComponentManifest(ulong,IDefinitionIdentity *,_GUID const &,IUnknown * *)

- ea: `0x1800a3ed8`
- end: `0x1800a44b8`
- name: `?IActContext_GetComponentManifest@CAppContext@Com@IsolationImplementation@@IEAAJKPEAUIDefinitionIdentity@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `1504`
- prototype: `int(IsolationImplementation::Com::CAppContext *__hidden this, unsigned int, struct IDefinitionIdentity *, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a33b0`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012820`
- `0x180012acc`
- `0x180012b1c`
- `0x180012b38`
- `0x180015f7c`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800199b4`
- `0x180030674`
- `0x18003bab4`
- `0x18003bef0`
- `0x18003c148`
- `0x180043644`
- `0x18004f2dc`
- `0x1800a2970`
- `0x1800a3ed8`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a3f6d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a3fff`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a40e4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a43d0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a3f6d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a3fff`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a40e4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800a43d0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a407c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4165`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a42b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4367`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a407c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4165`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a42b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4367`

## string_xrefs

- `0x1800a4036`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a411f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a4273`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a4321`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800a3ef0`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\appcontext.cpp`
- `0x1800a40ed`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\appcontext.cpp`
- `0x1800a424f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\appcontext.cpp`
- `0x1800a43dc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\appcontext.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CAppContext::IActContext_GetComponentManifest(
        IsolationImplementation::Com::CAppContext *this,
        int a2,
        struct IDefinitionIdentity *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  struct IUnknown **v5; // r15
  unsigned int v8; // edi
  int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // ebx
  int v12; // edx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  int ApplicationContextComponentStore; // eax
  __int64 v17; // rcx
  unsigned int v18; // ebx
  int v19; // edx
  __int64 v20; // r10
  unsigned int *v21; // r11
  signed int v22; // ecx
  void *v23; // rcx
  __int64 v24; // rbx
  int ComponentStoreManifestPathForWhidbeyAvalonHack; // eax
  unsigned int v26; // esi
  int v27; // edx
  __int64 v28; // rcx
  __int64 v29; // r10
  unsigned int *v30; // r11
  signed int v31; // ecx
  void *v32; // rcx
  HANDLE ProcessHeap_0; // rax
  void **v34; // rax
  void **v35; // rsi
  __int128 v36; // xmm2
  void *v37; // xmm3_8
  int v38; // eax
  int v39; // r9d
  int v40; // r14d
  __int64 v41; // r10
  unsigned int *v42; // r11
  signed int v43; // ecx
  void *v44; // rcx
  HANDLE v45; // rax
  __int64 v46; // r10
  unsigned int *v47; // r11
  signed int v48; // ecx
  void *v49; // rcx
  __int64 v51; // rcx
  int DefinitionIdentitiesInApplicationContext; // edi
  int v53; // r8d
  int v54; // edx
  unsigned int v55; // [rsp+20h] [rbp-58h]
  __int64 v56; // [rsp+30h] [rbp-48h] BYREF
  __int64 v57; // [rsp+38h] [rbp-40h] BYREF
  __int128 v58; // [rsp+40h] [rbp-38h] BYREF
  void *lpMem; // [rsp+50h] [rbp-28h]
  const char *v60; // [rsp+58h] [rbp-20h] BYREF
  int v61; // [rsp+60h] [rbp-18h]
  int v62; // [rsp+68h] [rbp-10h]

  v5 = a5;
  *(_QWORD *)&v58 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp";
  LODWORD(lpMem) = -2147023537;
  if ( a5 )
    *a5 = 0;
  if ( a2 )
  {
    DWORD2(v58) = 554;
LABEL_88:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v58);
    return (unsigned int)lpMem;
  }
  if ( a3 )
  {
    if ( !v5 )
    {
      DWORD2(v58) = 556;
      goto LABEL_7;
    }
    v56 = 0;
    v9 = IsolationImplementation::Com::ConvertIn(a3, (struct IDefinitionIdentity *)&v56, a3);
    v11 = v9;
    if ( v9 < 0 )
    {
      if ( v9 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
        (const char *)0x230,
        v11,
        v55);
      v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v11, v12);
      goto LABEL_15;
    }
    v14 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_81c85208_fe61_4c15_b5bb_ff5ea66baad9.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_81c85208_fe61_4c15_b5bb_ff5ea66baad9.Data1 )
      v14 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_81c85208_fe61_4c15_b5bb_ff5ea66baad9.Data4;
    v15 = *((_QWORD *)this + 2);
    a5 = 0;
    if ( !v14 )
    {
      v58 = 0u;
      lpMem = 0;
      ApplicationContextComponentStore = RtlGetApplicationContextComponentStore(0, v15, v10, &a5);
      v18 = ApplicationContextComponentStore;
      if ( ApplicationContextComponentStore < 0 )
      {
        if ( ApplicationContextComponentStore == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
          (const char *)0x242,
          v18,
          v55);
        v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v18, v19);
        if ( a5 )
        {
          v62 = -1073741595;
          v60 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(a5) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v21 + 4))(*v21, v20);
            v22 = 0;
          }
          else
          {
            v61 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v60);
            v22 = v62;
          }
          if ( v22 < 0 )
            RaiseException(v22, 1u, 0, 0);
          a5 = 0;
        }
        v23 = lpMem;
        if ( lpMem )
        {
          v58 = 0u;
          lpMem = 0;
          IsolationFreeStringRoutine(v23);
        }
LABEL_15:
        v13 = v56;
        if ( !v56 )
          return v8;
LABEL_76:
        RtlCloseDefinitionIdentityHandle(v13);
        return v8;
      }
      v24 = v56;
      ComponentStoreManifestPathForWhidbeyAvalonHack = Windows::Isolation::Hacks::Rtl::RtlpGetComponentStoreManifestPathForWhidbeyAvalonHack(
                                                         v17,
                                                         a5,
                                                         v56,
                                                         &v58);
      v26 = ComponentStoreManifestPathForWhidbeyAvalonHack;
      if ( ComponentStoreManifestPathForWhidbeyAvalonHack < 0 )
      {
        if ( ComponentStoreManifestPathForWhidbeyAvalonHack == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
          (const char *)0x248,
          v26,
          v55);
        v28 = v26;
LABEL_37:
        v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v28, v27);
        if ( a5 )
        {
          v60 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          v62 = -1073741595;
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(a5) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v30 + 4))(*v30, v29);
            v31 = 0;
          }
          else
          {
            v61 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v60);
            v31 = v62;
          }
          if ( v31 < 0 )
            RaiseException(v31, 1u, 0, 0);
          a5 = 0;
        }
        v32 = lpMem;
        if ( lpMem )
        {
          v58 = 0u;
          lpMem = 0;
          IsolationFreeStringRoutine(v32);
        }
        goto LABEL_74;
      }
      ProcessHeap_0 = GetProcessHeap_0();
      v34 = (void **)HeapAlloc_0(ProcessHeap_0, 0, 0x40u);
      v35 = v34;
      if ( !v34 )
      {
        if ( g_NTSTATUS_to_break_on_propagate == -1073741801 )
          DebugBreak();
        Windows::ErrorHandling::COM::ReportError(
          (Windows::ErrorHandling::COM *)"Status propagated",
          "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
          (const char *)0x24A,
          -1073741801,
          v55);
        v28 = 3221225495LL;
        goto LABEL_37;
      }
      *((_DWORD *)v34 + 2) = 0;
      v34[3] = 0;
      v34[2] = 0;
      v34[4] = 0;
      v34[5] = 0;
      *v34 = &IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CManifestInformation>::`vftable';
      v34[6] = 0;
      v36 = v58;
      v37 = lpMem;
      v58 = *((_OWORD *)v34 + 1);
      lpMem = v34[4];
      *((_OWORD *)v34 + 1) = v36;
      v34[4] = v37;
      if ( v34[5] )
      {
        __debugbreak();
      }
      else if ( this )
      {
        (*(void (__fastcall **)(IsolationImplementation::Com::CAppContext *))(*(_QWORD *)this + 8LL))(this);
        v35[5] = this;
      }
      v38 = (*(__int64 (__fastcall **)(void **, const struct _GUID *, struct IUnknown **))*v35)(v35, a4, v5);
      v40 = v38;
      if ( v38 < 0 )
      {
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\appcontext.cpp",
          (const char *)0x24C,
          v38,
          v39);
        v8 = v40;
        if ( a5 )
        {
          v62 = -1073741595;
          v60 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(a5) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v42 + 4))(*v42, v41);
            v43 = 0;
          }
          else
          {
            v61 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v60);
            v43 = v62;
          }
          if ( v43 < 0 )
            RaiseException(v43, 1u, 0, 0);
          a5 = 0;
        }
        v44 = lpMem;
        if ( lpMem )
        {
          v58 = 0u;
          lpMem = 0;
          IsolationFreeStringRoutine(v44);
        }
        IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CManifestInformation>::~CComObject<IsolationImplementation::Com::CManifestInformation>(v35);
        v45 = GetProcessHeap_0();
        HeapFree_0(v45, 0, v35);
        goto LABEL_74;
      }
      if ( a5 )
      {
        v62 = -1073741595;
        v60 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(a5) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v47 + 4))(*v47, v46);
          v48 = 0;
        }
        else
        {
          v61 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v60);
          v48 = v62;
        }
        if ( v48 < 0 )
          RaiseException(v48, 1u, 0, 0);
        a5 = 0;
      }
      v49 = lpMem;
      if ( lpMem )
      {
        v58 = 0u;
        lpMem = 0;
        IsolationFreeStringRoutine(v49);
      }
      goto LABEL_73;
    }
    v24 = v56;
    v57 = 0;
    DefinitionIdentitiesInApplicationContext = RtlFindDefinitionIdentitiesInApplicationContext(v14, v15, v10, &v56, &a5);
    if ( DefinitionIdentitiesInApplicationContext >= 0 )
    {
      if ( a5 == (struct IUnknown **)0xFFFFFFFFLL )
      {
        DWORD2(v58) = 608;
        if ( v24 )
          RtlCloseDefinitionIdentityHandle(v24);
        goto LABEL_88;
      }
      DefinitionIdentitiesInApplicationContext = RtlGetComponentsFromApplicationContext(
                                                   v51,
                                                   *((_QWORD *)this + 2),
                                                   v53,
                                                   (unsigned int)&a5,
                                                   (__int64)&v57);
      if ( DefinitionIdentitiesInApplicationContext >= 0 )
      {
        DefinitionIdentitiesInApplicationContext = IsolationImplementation::Com::CopyOut(v57, a4, v5);
        if ( DefinitionIdentitiesInApplicationContext >= 0 )
        {
LABEL_73:
          v8 = 0;
LABEL_74:
          if ( !v24 )
            return v8;
          v13 = v24;
          goto LABEL_76;
        }
        DWORD2(v58) = 617;
      }
      else
      {
        DWORD2(v58) = 615;
      }
    }
    else
    {
      DWORD2(v58) = 606;
    }
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::FrameReportNtStatusErrorPropagation(
      v51,
      &v58,
      (unsigned int)DefinitionIdentitiesInApplicationContext);
    v8 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
           (Windows::ErrorHandling::COM *)(unsigned int)DefinitionIdentitiesInApplicationContext,
           v54);
    goto LABEL_74;
  }
  DWORD2(v58) = 555;
LABEL_7:
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v58);
  return (unsigned int)lpMem;
}

```

## disassembly

```asm
0x1800a3ed8  push    rbp
0x1800a3eda  push    rbx
0x1800a3edb  push    rsi
0x1800a3edc  push    rdi
0x1800a3edd  push    r12
0x1800a3edf  push    r13
0x1800a3ee1  push    r14
0x1800a3ee3  push    r15
0x1800a3ee5  mov     rbp, rsp
0x1800a3ee8  sub     rsp, 78h
0x1800a3eec  mov     r15, [rbp+arg_20]
0x1800a3ef0  lea     rsi, aOnecoreComNetf_59; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a3ef7  xor     r13d, r13d
0x1800a3efa  mov     qword ptr [rbp+var_38], rsi
0x1800a3efe  mov     edi, 8007054Fh
0x1800a3f03  mov     r12, r9
0x1800a3f06  mov     dword ptr [rbp+lpMem], edi
0x1800a3f09  mov     r14, rcx
0x1800a3f0c  test    r15, r15
0x1800a3f0f  jz      short loc_1800A3F14
0x1800a3f11  mov     [r15], r13
0x1800a3f14  test    edx, edx
0x1800a3f16  jz      short loc_1800A3F24
0x1800a3f18  mov     dword ptr [rbp+var_38+8], 22Ah
0x1800a3f1f  jmp     loc_1800A4460
0x1800a3f24  test    r8, r8
0x1800a3f27  jnz     short loc_1800A3F41
0x1800a3f29  mov     dword ptr [rbp+var_38+8], 22Bh
0x1800a3f30  lea     rcx, [rbp+var_38]
0x1800a3f34  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800a3f39  mov     edi, dword ptr [rbp+lpMem]
0x1800a3f3c  jmp     loc_1800A439B
0x1800a3f41  test    r15, r15
0x1800a3f44  jnz     short loc_1800A3F4F
0x1800a3f46  mov     dword ptr [rbp+var_38+8], 22Ch
0x1800a3f4d  jmp     short loc_1800A3F30
0x1800a3f4f  lea     rdx, [rbp+var_48]; struct IDefinitionIdentity *
0x1800a3f53  mov     [rbp+var_48], r13
0x1800a3f57  mov     rcx, r8; this
0x1800a3f5a  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionIdentity@@PEAU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionIdentity *,Windows::Isolation::Rtl::_DEFINITION_IDENTITY *)
0x1800a3f5f  mov     ebx, eax
0x1800a3f61  test    eax, eax
0x1800a3f63  jns     short loc_1800A3FA6
0x1800a3f65  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a3f6b  jnz     short loc_1800A3F73
0x1800a3f6d  call    cs:__imp_DebugBreak
0x1800a3f73  mov     r9d, ebx; int
0x1800a3f76  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a3f7d  mov     r8d, 230h; char *
0x1800a3f83  mov     rdx, rsi; char *
0x1800a3f86  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a3f8b  mov     ecx, ebx; this
0x1800a3f8d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a3f92  mov     edi, eax
0x1800a3f94  mov     rcx, [rbp+var_48]
0x1800a3f98  test    rcx, rcx
0x1800a3f9b  jz      loc_1800A439B
0x1800a3fa1  jmp     loc_1800A4396
0x1800a3fa6  mov     rcx, [r12]
0x1800a3faa  sub     rcx, qword ptr cs:_GUID_81c85208_fe61_4c15_b5bb_ff5ea66baad9.Data1
0x1800a3fb1  jnz     short loc_1800A3FBF
0x1800a3fb3  mov     rcx, [r12+8]
0x1800a3fb8  sub     rcx, qword ptr cs:_GUID_81c85208_fe61_4c15_b5bb_ff5ea66baad9.Data4
0x1800a3fbf  mov     rdx, [r14+10h]
0x1800a3fc3  test    rcx, rcx
0x1800a3fc6  mov     eax, r13d
0x1800a3fc9  mov     [rbp+arg_20], r13
0x1800a3fcd  setz    al
0x1800a3fd0  test    eax, eax
0x1800a3fd2  jz      loc_1800A43FC
0x1800a3fd8  lea     r9, [rbp+arg_20]
0x1800a3fdc  mov     qword ptr [rbp+var_38+8], r13
0x1800a3fe0  mov     qword ptr [rbp+var_38], r13
0x1800a3fe4  mov     [rbp+lpMem], r13
0x1800a3fe8  call    RtlGetApplicationContextComponentStore
0x1800a3fed  mov     ebx, eax
0x1800a3fef  test    eax, eax
0x1800a3ff1  jns     loc_1800A40BE
0x1800a3ff7  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a3ffd  jnz     short loc_1800A4005
0x1800a3fff  call    cs:__imp_DebugBreak
0x1800a4005  mov     r9d, ebx; int
0x1800a4008  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a400f  mov     r8d, 242h; char *
0x1800a4015  mov     rdx, rsi; char *
0x1800a4018  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a401d  mov     ecx, ebx; this
0x1800a401f  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a4024  mov     r10, [rbp+arg_20]
0x1800a4028  mov     edi, eax
0x1800a402a  test    r10, r10
0x1800a402d  jz      short loc_1800A4086
0x1800a402f  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a4036  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a403d  mov     [rbp+var_10], 0C00000E5h
0x1800a4044  mov     [rbp+var_20], rax
0x1800a4048  test    r11, r11
0x1800a404b  jz      short loc_1800A40A9
0x1800a404d  mov     rdx, r11
0x1800a4050  mov     rcx, r10
0x1800a4053  call    RtlIsTypeSafeHandleValid
0x1800a4058  test    al, al
0x1800a405a  jz      short loc_1800A40A9
0x1800a405c  mov     ecx, [r11]
0x1800a405f  mov     rdx, r10
0x1800a4062  mov     rax, [r11+20h]
0x1800a4066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a406b  mov     ecx, r13d; dwExceptionCode
0x1800a406e  test    ecx, ecx
0x1800a4070  jns     short loc_1800A4082
0x1800a4072  xor     r9d, r9d; lpArguments
0x1800a4075  xor     r8d, r8d; nNumberOfArguments
0x1800a4078  lea     edx, [r9+1]; dwExceptionFlags
0x1800a407c  call    cs:__imp_RaiseException
0x1800a4082  mov     [rbp+arg_20], r13
0x1800a4086  mov     rcx, [rbp+lpMem]; lpMem
0x1800a408a  test    rcx, rcx
0x1800a408d  jz      loc_1800A3F94
0x1800a4093  mov     qword ptr [rbp+var_38+8], r13
0x1800a4097  mov     qword ptr [rbp+var_38], r13
0x1800a409b  mov     [rbp+lpMem], r13
0x1800a409f  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800a40a4  jmp     loc_1800A3F94
0x1800a40a9  mov     [rbp+var_18], 124h
0x1800a40b0  lea     rcx, [rbp+var_20]
0x1800a40b4  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a40b9  mov     ecx, [rbp+var_10]
0x1800a40bc  jmp     short loc_1800A406E
0x1800a40be  mov     rbx, [rbp+var_48]
0x1800a40c2  lea     r9, [rbp+var_38]
0x1800a40c6  mov     rdx, [rbp+arg_20]
0x1800a40ca  mov     r8, rbx
0x1800a40cd  call    ?RtlpGetComponentStoreManifestPathForWhidbeyAvalonHack@Rtl@Hacks@Isolation@Windows@@YAJKU_COMPONENT_STORE@134@U_DEFINITION_IDENTITY@134@PEAU_LUNICODE_STRING@@@Z; Windows::Isolation::Hacks::Rtl::RtlpGetComponentStoreManifestPathForWhidbeyAvalonHack(ulong,Windows::Isolation::Rtl::_COMPONENT_STORE,Windows::Isolation::Rtl::_DEFINITION_IDENTITY,_LUNICODE_STRING *)
0x1800a40d2  mov     esi, eax
0x1800a40d4  test    eax, eax
0x1800a40d6  jns     loc_1800A41A7
0x1800a40dc  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800a40e2  jnz     short loc_1800A40EA
0x1800a40e4  call    cs:__imp_DebugBreak
0x1800a40ea  mov     r9d, esi; int
0x1800a40ed  lea     rdx, aOnecoreComNetf_59; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a40f4  mov     r8d, 248h; char *
0x1800a40fa  lea     rcx, aStatusPropagat; "Status propagated"
0x1800a4101  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800a4106  mov     ecx, esi; this
0x1800a4108  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800a410d  mov     r10, [rbp+arg_20]
0x1800a4111  mov     edi, eax
0x1800a4113  test    r10, r10
0x1800a4116  jz      short loc_1800A416F
0x1800a4118  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a411f  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a4126  mov     [rbp+var_20], rax
0x1800a412a  mov     [rbp+var_10], 0C00000E5h
0x1800a4131  test    r11, r11
0x1800a4134  jz      short loc_1800A4192
0x1800a4136  mov     rdx, r11
0x1800a4139  mov     rcx, r10
0x1800a413c  call    RtlIsTypeSafeHandleValid
0x1800a4141  test    al, al
0x1800a4143  jz      short loc_1800A4192
0x1800a4145  mov     ecx, [r11]
0x1800a4148  mov     rdx, r10
0x1800a414b  mov     rax, [r11+20h]
0x1800a414f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4154  mov     ecx, r13d; dwExceptionCode
0x1800a4157  test    ecx, ecx
0x1800a4159  jns     short loc_1800A416B
0x1800a415b  xor     r9d, r9d; lpArguments
0x1800a415e  xor     r8d, r8d; nNumberOfArguments
0x1800a4161  lea     edx, [r9+1]; dwExceptionFlags
0x1800a4165  call    cs:__imp_RaiseException
0x1800a416b  mov     [rbp+arg_20], r13
0x1800a416f  mov     rcx, [rbp+lpMem]; lpMem
0x1800a4173  test    rcx, rcx
0x1800a4176  jz      loc_1800A438E
0x1800a417c  mov     qword ptr [rbp+var_38+8], r13
0x1800a4180  mov     qword ptr [rbp+var_38], r13
0x1800a4184  mov     [rbp+lpMem], r13
0x1800a4188  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800a418d  jmp     loc_1800A438E
0x1800a4192  mov     [rbp+var_18], 124h
0x1800a4199  lea     rcx, [rbp+var_20]
0x1800a419d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a41a2  mov     ecx, [rbp+var_10]
0x1800a41a5  jmp     short loc_1800A4157
0x1800a41a7  call    GetProcessHeap_0
0x1800a41ac  xor     edx, edx; dwFlags
0x1800a41ae  mov     rcx, rax; hHeap
0x1800a41b1  lea     r8d, [rdx+40h]; dwBytes
0x1800a41b5  call    HeapAlloc_0
0x1800a41ba  mov     rsi, rax
0x1800a41bd  test    rax, rax
0x1800a41c0  jz      loc_1800A43C3
0x1800a41c6  mov     [rax+8], r13d
0x1800a41ca  mov     [rax+18h], r13
0x1800a41ce  mov     [rax+10h], r13
0x1800a41d2  mov     [rax+20h], r13
0x1800a41d6  mov     [rax+28h], r13
0x1800a41da  lea     rax, ??_7?$CComObject@VCManifestInformation@Com@IsolationImplementation@@@Com@IsolationImplementation@@6B@; const IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CManifestInformation>::`vftable'
0x1800a41e1  mov     [rsi], rax
0x1800a41e4  mov     [rsi+30h], r13
0x1800a41e8  movups  xmm0, xmmword ptr [rsi+10h]
0x1800a41ec  movups  xmm2, [rbp+var_38]
0x1800a41f0  movsd   xmm3, [rbp+lpMem]
0x1800a41f5  movups  [rbp+var_38], xmm0
0x1800a41f9  movsd   xmm1, qword ptr [rsi+20h]
0x1800a41fe  movsd   [rbp+lpMem], xmm1
0x1800a4203  movups  xmmword ptr [rsi+10h], xmm2
0x1800a4207  movsd   qword ptr [rsi+20h], xmm3
0x1800a420c  cmp     [rsi+28h], r13
0x1800a4210  jz      short loc_1800A4215
0x1800a4212  int     3; Trap to Debugger
0x1800a4213  jmp     short loc_1800A422D
0x1800a4215  test    r14, r14
0x1800a4218  jz      short loc_1800A422D
0x1800a421a  mov     rax, [r14]
0x1800a421d  mov     rcx, r14
0x1800a4220  mov     rax, [rax+8]
0x1800a4224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4229  mov     [rsi+28h], r14
0x1800a422d  mov     rax, [rsi]
0x1800a4230  mov     r8, r15
0x1800a4233  mov     rdx, r12
0x1800a4236  mov     rcx, rsi
0x1800a4239  mov     rax, [rax]
0x1800a423c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4241  mov     r14d, eax
0x1800a4244  test    eax, eax
0x1800a4246  jns     loc_1800A4311
0x1800a424c  mov     r8d, eax; int
0x1800a424f  lea     rcx, aOnecoreComNetf_59; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a4256  mov     edx, 24Ch; char *
0x1800a425b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800a4260  mov     r10, [rbp+arg_20]
0x1800a4264  mov     edi, r14d
0x1800a4267  test    r10, r10
0x1800a426a  jz      short loc_1800A42C3
0x1800a426c  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a4273  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a427a  mov     [rbp+var_10], 0C00000E5h
0x1800a4281  mov     [rbp+var_20], rax
0x1800a4285  test    r11, r11
0x1800a4288  jz      short loc_1800A42FC
0x1800a428a  mov     rdx, r11
0x1800a428d  mov     rcx, r10
0x1800a4290  call    RtlIsTypeSafeHandleValid
0x1800a4295  test    al, al
0x1800a4297  jz      short loc_1800A42FC
0x1800a4299  mov     ecx, [r11]
0x1800a429c  mov     rdx, r10
0x1800a429f  mov     rax, [r11+20h]
0x1800a42a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a42a8  mov     ecx, r13d; dwExceptionCode
0x1800a42ab  test    ecx, ecx
0x1800a42ad  jns     short loc_1800A42BF
0x1800a42af  xor     r9d, r9d; lpArguments
0x1800a42b2  xor     r8d, r8d; nNumberOfArguments
0x1800a42b5  lea     edx, [r9+1]; dwExceptionFlags
0x1800a42b9  call    cs:__imp_RaiseException
0x1800a42bf  mov     [rbp+arg_20], r13
0x1800a42c3  mov     rcx, [rbp+lpMem]; lpMem
0x1800a42c7  test    rcx, rcx
0x1800a42ca  jz      short loc_1800A42DD
0x1800a42cc  mov     qword ptr [rbp+var_38+8], r13
0x1800a42d0  mov     qword ptr [rbp+var_38], r13
0x1800a42d4  mov     [rbp+lpMem], r13
0x1800a42d8  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800a42dd  mov     rcx, rsi
0x1800a42e0  call    ??1?$CComObject@VCManifestInformation@Com@IsolationImplementation@@@Com@IsolationImplementation@@QEAA@XZ; IsolationImplementation::Com::CComObject<IsolationImplementation::Com::CManifestInformation>::~CComObject<IsolationImplementation::Com::CManifestInformation>(void)
0x1800a42e5  call    GetProcessHeap_0
0x1800a42ea  mov     r8, rsi; lpMem
0x1800a42ed  xor     edx, edx; dwFlags
0x1800a42ef  mov     rcx, rax; hHeap
0x1800a42f2  call    HeapFree_0
0x1800a42f7  jmp     loc_1800A438E
0x1800a42fc  mov     [rbp+var_18], 124h
0x1800a4303  lea     rcx, [rbp+var_20]
0x1800a4307  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800a430c  mov     ecx, [rbp+var_10]
0x1800a430f  jmp     short loc_1800A42AB
0x1800a4311  mov     r10, [rbp+arg_20]
0x1800a4315  test    r10, r10
0x1800a4318  jz      short loc_1800A4371
0x1800a431a  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800a4321  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800a4328  mov     [rbp+var_10], 0C00000E5h
0x1800a432f  mov     [rbp+var_20], rax
0x1800a4333  test    r11, r11
0x1800a4336  jz      short loc_1800A43AE
0x1800a4338  mov     rdx, r11
0x1800a433b  mov     rcx, r10
0x1800a433e  call    RtlIsTypeSafeHandleValid
0x1800a4343  test    al, al
0x1800a4345  jz      short loc_1800A43AE
0x1800a4347  mov     ecx, [r11]
0x1800a434a  mov     rdx, r10
0x1800a434d  mov     rax, [r11+20h]
0x1800a4351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4356  mov     ecx, r13d; dwExceptionCode
  ... truncated ...
```
