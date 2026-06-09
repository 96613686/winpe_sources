# IsolationImplementation::Com::CEnumSTORE_DEPLOYMENT_METADATA_PROPERTY::IEnumSTORE_DEPLOYMENT_METADATA_PROPERTY_Next(ulong,_STORE_DEPLOYMENT_METADATA_PROPERTY * const,ulong *)

- ea: `0x18010c0a0`
- end: `0x18010c372`
- name: `?IEnumSTORE_DEPLOYMENT_METADATA_PROPERTY_Next@CEnumSTORE_DEPLOYMENT_METADATA_PROPERTY@Com@IsolationImplementation@@IEAAJKQEAU_STORE_DEPLOYMENT_METADATA_PROPERTY@@PEAK@Z`
- size: `722`
- prototype: `__int64 __fastcall(IsolationImplementation::Com::CEnumSTORE_DEPLOYMENT_METADATA_PROPERTY *__hidden this, unsigned int, struct _STORE_DEPLOYMENT_METADATA_PROPERTY *const, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18010c7c0`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x180012910`
- `0x180012b38`
- `0x180013e50`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18010af84`
- `0x18010b750`
- `0x18010b978`
- `0x18010c0a0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010c1c0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010c252`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010c31e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010c1c0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010c252`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010c31e`

## string_xrefs

- `0x18010c0c1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`
- `0x18010c2fe`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`
- `0x18010c330`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CEnumSTORE_DEPLOYMENT_METADATA_PROPERTY::IEnumSTORE_DEPLOYMENT_METADATA_PROPERTY_Next(
        IsolationImplementation::Com::CEnumSTORE_DEPLOYMENT_METADATA_PROPERTY *this,
        unsigned int a2,
        struct _STORE_DEPLOYMENT_METADATA_PROPERTY *const a3,
        unsigned int *a4)
{
  __int64 v6; // rcx
  __int64 v7; // xmm1_8
  __int64 v8; // rax
  unsigned int v9; // ebx
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rdi
  int v13; // ebx
  __int64 v14; // rbx
  HANDLE ProcessHeap_0; // rax
  char *v16; // rax
  char *v17; // rsi
  int v18; // r9d
  __int64 v19; // r8
  __int64 v20; // rdx
  struct _STORE_DEPLOYMENT_METADATA_PROPERTY *v21; // r8
  unsigned __int64 v22; // rax
  __int64 v23; // rdi
  int v24; // eax
  int v25; // r9d
  int v26; // edx
  unsigned int v28; // [rsp+20h] [rbp-49h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  __int64 v30; // [rsp+38h] [rbp-31h] BYREF
  __int128 v31; // [rsp+40h] [rbp-29h]
  const char *v32; // [rsp+50h] [rbp-19h] BYREF
  int v33; // [rsp+58h] [rbp-11h]
  unsigned int v34; // [rsp+60h] [rbp-9h]
  __int128 v35; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v36; // [rsp+78h] [rbp+Fh]
  unsigned __int64 v37; // [rsp+80h] [rbp+17h]
  __int64 v38; // [rsp+88h] [rbp+1Fh]
  Windows::ErrorHandling::COM *v40; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 v41; // [rsp+E8h] [rbp+7Fh] BYREF

  v34 = -2147023537;
  v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploymentmetadata.cpp";
  v38 = 0;
  if ( a3 )
  {
    v6 = 0;
    if ( a2 )
    {
      v7 = v38;
      do
      {
        v8 = 5 * v6++;
        *(_OWORD *)((char *)a3 + 8 * v8) = 0;
        *(_OWORD *)((char *)a3 + 8 * v8 + 16) = 0;
        *((_QWORD *)a3 + v8 + 4) = v7;
      }
      while ( v6 != a2 );
    }
  }
  if ( a4 )
    *a4 = 0;
  if ( a3 )
  {
    v10 = 0;
    v41 = 0;
    v11 = 0;
    v36 = 0;
    v37 = 0;
    v12 = a2;
    v35 = 0;
    if ( a2 )
    {
      v29 = 0;
      BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(&v40, 64, a2, &v29);
      v13 = (int)v40;
      if ( (int)v40 >= 0 )
      {
        v14 = v29;
        ProcessHeap_0 = GetProcessHeap_0();
        v16 = (char *)HeapAlloc_0(ProcessHeap_0, 0, v14 + 8);
        v17 = v16;
        if ( v16 )
        {
          *((_QWORD *)&v35 + 1) = v16;
          v10 = v12;
          v36 = v12;
          goto LABEL_21;
        }
        v13 = -1073741801;
      }
      if ( v13 < 0 )
      {
        if ( v13 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        v18 = v13;
        v19 = 249;
        goto LABEL_45;
      }
    }
    v17 = (char *)*((_QWORD *)&v35 + 1);
LABEL_21:
    v30 = 0;
    v31 = 0;
    v20 = *((_QWORD *)this + 2);
    if ( v10 )
      v11 = v10;
    v37 = v11;
    v13 = Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::Attach(
            &v30,
            v20);
    if ( v13 >= 0
      && (v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, char *, unsigned __int64 *))(**(_QWORD **)v31 + 16LL))(
                  *(_QWORD *)v31,
                  v12,
                  v17,
                  &v41),
          v13 >= 0) )
    {
      if ( *((_QWORD *)&v31 + 1) )
        (*(void (__fastcall **)(__int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
                                        + 48))(v30);
      v22 = v41;
      if ( v41 > v12 )
      {
        v33 = 257;
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v35);
        Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
          &v32,
          &v32);
        return v34;
      }
      v23 = 0;
      if ( v41 )
      {
        while ( 1 )
        {
          if ( v11 < v10 )
            v11 = v10;
          v37 = v11;
          v24 = IsolationImplementation::Com::CopyOut(
                  (IsolationImplementation::Com *)&v17[64 * v23],
                  (struct IMalloc **)a3 + 5 * v23,
                  v21);
          v9 = v24;
          if ( v24 < 0 )
            break;
          v22 = v41;
          if ( ++v23 == v41 )
            goto LABEL_39;
        }
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploy"
                                         "mentmetadata.cpp",
          (const char *)0x104,
          v24,
          v25);
        goto LABEL_46;
      }
LABEL_39:
      if ( v22 <= 0xFFFFFFFF )
      {
        *a4 = v22;
        v9 = 0;
LABEL_46:
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v35);
        return v9;
      }
      v13 = -1073741675;
      if ( g_NTSTATUS_to_break_on_propagate == -1073741675 )
        DebugBreak();
      v18 = -1073741675;
      v19 = 262;
    }
    else
    {
      if ( *((_QWORD *)&v31 + 1) )
        (*(void (__fastcall **)(__int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
                                        + 48))(v30);
      if ( v13 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      v18 = v13;
      v19 = 255;
    }
LABEL_45:
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploymentmetadata.cpp",
      (const char *)v19,
      v18,
      v28);
    v9 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v13, v26);
    goto LABEL_46;
  }
  v33 = 244;
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v32);
  return v34;
}

```

## disassembly

```asm
0x18010c0a0  mov     [rsp-8+arg_8], rbx
0x18010c0a5  mov     [rsp-8+arg_0], rcx
0x18010c0aa  push    rbp
0x18010c0ab  push    rsi
0x18010c0ac  push    rdi
0x18010c0ad  push    r12
0x18010c0af  push    r13
0x18010c0b1  push    r14
0x18010c0b3  push    r15
0x18010c0b5  lea     rbp, [rsp-27h]
0x18010c0ba  sub     rsp, 90h
0x18010c0c1  lea     rax, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010c0c8  mov     [rbp+57h+var_60], 8007054Fh
0x18010c0cf  mov     r12, r8
0x18010c0d2  mov     [rbp+57h+var_70], rax
0x18010c0d6  xor     eax, eax
0x18010c0d8  mov     r8d, edx
0x18010c0db  mov     [rbp+57h+var_38], rax
0x18010c0df  mov     r13, r9
0x18010c0e2  xorps   xmm0, xmm0
0x18010c0e5  test    r12, r12
0x18010c0e8  jz      short loc_18010C113
0x18010c0ea  xor     ecx, ecx
0x18010c0ec  test    edx, edx
0x18010c0ee  jz      short loc_18010C113
0x18010c0f0  movsd   xmm1, [rbp+57h+var_38]
0x18010c0f5  lea     rax, [rcx+rcx*4]
0x18010c0f9  inc     rcx
0x18010c0fc  movups  xmmword ptr [r12+rax*8], xmm0
0x18010c101  movups  xmmword ptr [r12+rax*8+10h], xmm0
0x18010c107  movsd   qword ptr [r12+rax*8+20h], xmm1
0x18010c10e  cmp     rcx, r8
0x18010c111  jnz     short loc_18010C0F5
0x18010c113  test    r13, r13
0x18010c116  jz      short loc_18010C11F
0x18010c118  mov     dword ptr [r9], 0
0x18010c11f  test    r12, r12
0x18010c122  jnz     short loc_18010C13C
0x18010c124  lea     rcx, [rbp+57h+var_70]
0x18010c128  mov     [rbp+57h+var_68], 0F4h
0x18010c12f  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18010c134  mov     ebx, [rbp+57h+var_60]
0x18010c137  jmp     loc_18010C355
0x18010c13c  xor     r14d, r14d
0x18010c13f  mov     [rbp+57h+arg_18], 0
0x18010c147  xor     r15d, r15d
0x18010c14a  mov     [rbp+57h+var_48], r14
0x18010c14e  mov     [rbp+57h+var_40], r15
0x18010c152  xorps   xmm0, xmm0
0x18010c155  mov     rdi, r8
0x18010c158  movdqu  [rbp+57h+var_58], xmm0
0x18010c15d  test    edx, edx
0x18010c15f  jz      short loc_18010C1D4
0x18010c161  lea     r9, [rbp+57h+var_90]
0x18010c165  mov     [rbp+57h+var_90], r14
0x18010c169  lea     edx, [r14+40h]
0x18010c16d  lea     rcx, [rbp+57h+arg_10]
0x18010c171  call    ??$MultiplyWithOverflowCheck@VCCallDisposition@Rtl@BUCL@@_K@BUCL@@YA?AVCCallDisposition@Rtl@0@_K0AEA_K@Z; BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x18010c176  mov     ebx, dword ptr [rbp+57h+arg_10]
0x18010c179  test    ebx, ebx
0x18010c17b  jns     short loc_18010C190
0x18010c17d  xor     esi, esi
0x18010c17f  test    ebx, ebx
0x18010c181  js      short loc_18010C1B4
0x18010c183  mov     qword ptr [rbp+57h+var_58+8], rsi
0x18010c187  mov     r14, rdi
0x18010c18a  mov     [rbp+57h+var_48], rdi
0x18010c18e  jmp     short loc_18010C1D8
0x18010c190  mov     rbx, [rbp+57h+var_90]
0x18010c194  call    GetProcessHeap_0
0x18010c199  mov     rcx, rax; hHeap
0x18010c19c  lea     r8, [rbx+8]; dwBytes
0x18010c1a0  xor     edx, edx; dwFlags
0x18010c1a2  call    HeapAlloc_0
0x18010c1a7  mov     rsi, rax
0x18010c1aa  test    rax, rax
0x18010c1ad  jnz     short loc_18010C183
0x18010c1af  mov     ebx, 0C0000017h
0x18010c1b4  test    ebx, ebx
0x18010c1b6  jns     short loc_18010C1D4
0x18010c1b8  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18010c1be  jnz     short loc_18010C1C6
0x18010c1c0  call    cs:__imp_DebugBreak
0x18010c1c6  mov     r9d, ebx
0x18010c1c9  mov     r8d, 0F9h
0x18010c1cf  jmp     loc_18010C330
0x18010c1d4  mov     rsi, qword ptr [rbp+57h+var_58+8]
0x18010c1d8  mov     rdx, [rbp+57h+arg_0]
0x18010c1dc  lea     rcx, [rbp+57h+var_88]
0x18010c1e0  xorps   xmm0, xmm0
0x18010c1e3  mov     [rbp+57h+var_88], 0
0x18010c1eb  test    r14, r14
0x18010c1ee  movdqu  [rbp+57h+var_80], xmm0
0x18010c1f3  mov     rdx, [rdx+10h]
0x18010c1f7  cmovnz  r15, r14
0x18010c1fb  mov     [rbp+57h+var_40], r15
0x18010c1ff  call    ?Attach@?$CTypeSafeHandlePointer@VCComponentStoreMetadataDeploymentPropertyEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR@2Isolation@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::Attach(Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR)
0x18010c204  mov     ebx, eax
0x18010c206  test    eax, eax
0x18010c208  js      short loc_18010C22D
0x18010c20a  mov     rax, qword ptr [rbp+57h+var_80]
0x18010c20e  lea     r9, [rbp+57h+arg_18]
0x18010c212  mov     r8, rsi
0x18010c215  mov     rdx, rdi
0x18010c218  mov     rcx, [rax]
0x18010c21b  mov     rax, [rcx]
0x18010c21e  mov     rax, [rax+10h]
0x18010c222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c227  mov     ebx, eax
0x18010c229  test    eax, eax
0x18010c22b  jns     short loc_18010C266
0x18010c22d  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x18010c231  test    rdx, rdx
0x18010c234  jz      short loc_18010C24A
0x18010c236  mov     rax, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentPropertyEnumerator@@VCComponentStoreMetadataDeploymentPropertyEnumeratorCD@@VCComponentStoreMetadataDeploymentPropertyEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
0x18010c23d  mov     rcx, [rbp+57h+var_88]
0x18010c241  mov     rax, [rax+30h]
0x18010c245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c24a  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18010c250  jnz     short loc_18010C258
0x18010c252  call    cs:__imp_DebugBreak
0x18010c258  mov     r9d, ebx
0x18010c25b  mov     r8d, 0FFh
0x18010c261  jmp     loc_18010C330
0x18010c266  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x18010c26a  test    rdx, rdx
0x18010c26d  jz      short loc_18010C283
0x18010c26f  mov     rax, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentPropertyEnumerator@@VCComponentStoreMetadataDeploymentPropertyEnumeratorCD@@VCComponentStoreMetadataDeploymentPropertyEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_PROPERTY_ENUMERATOR,CComponentStoreMetadataDeploymentPropertyEnumerator,CComponentStoreMetadataDeploymentPropertyEnumeratorCD,CComponentStoreMetadataDeploymentPropertyEnumeratorTraits>::ms_ptti
0x18010c276  mov     rcx, [rbp+57h+var_88]
0x18010c27a  mov     rax, [rax+30h]
0x18010c27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c283  mov     rax, [rbp+57h+arg_18]
0x18010c287  cmp     rax, rdi
0x18010c28a  jbe     short loc_18010C2AE
0x18010c28c  lea     rcx, [rbp+57h+var_58]
0x18010c290  mov     [rbp+57h+var_68], 101h
0x18010c297  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x18010c29c  lea     rdx, [rbp+57h+var_70]
0x18010c2a0  lea     rcx, [rbp+57h+var_70]
0x18010c2a4  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18010c2a9  jmp     loc_18010C134
0x18010c2ae  xor     edi, edi
0x18010c2b0  test    rax, rax
0x18010c2b3  jz      short loc_18010C2E9
0x18010c2b5  lea     rax, [rdi+rdi*4]
0x18010c2b9  cmp     r15, r14
0x18010c2bc  mov     rcx, rdi
0x18010c2bf  lea     rdx, [r12+rax*8]; struct Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_ *
0x18010c2c3  cmovb   r15, r14
0x18010c2c7  shl     rcx, 6
0x18010c2cb  add     rcx, rsi; this
0x18010c2ce  mov     [rbp+57h+var_40], r15
0x18010c2d2  call    ?CopyOut@Com@IsolationImplementation@@YAJAEBU_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_@Rtl@Isolation@Windows@@AEAU_STORE_DEPLOYMENT_METADATA_PROPERTY@@@Z; IsolationImplementation::Com::CopyOut(Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_ const &,_STORE_DEPLOYMENT_METADATA_PROPERTY &)
0x18010c2d7  mov     ebx, eax
0x18010c2d9  test    eax, eax
0x18010c2db  js      short loc_18010C2FB
0x18010c2dd  mov     rax, [rbp+57h+arg_18]
0x18010c2e1  inc     rdi
0x18010c2e4  cmp     rdi, rax
0x18010c2e7  jnz     short loc_18010C2B5
0x18010c2e9  mov     ecx, 0FFFFFFFFh
0x18010c2ee  cmp     rax, rcx
0x18010c2f1  ja      short loc_18010C311
0x18010c2f3  mov     [r13+0], eax
0x18010c2f7  xor     ebx, ebx
0x18010c2f9  jmp     short loc_18010C34C
0x18010c2fb  mov     r8d, eax; int
0x18010c2fe  lea     rcx, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010c305  mov     edx, 104h; char *
0x18010c30a  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18010c30f  jmp     short loc_18010C34C
0x18010c311  mov     ebx, 0C0000095h
0x18010c316  cmp     cs:g_NTSTATUS_to_break_on_propagate, ebx
0x18010c31c  jnz     short loc_18010C324
0x18010c31e  call    cs:__imp_DebugBreak
0x18010c324  mov     r9d, 0C0000095h; int
0x18010c32a  mov     r8d, 106h; char *
0x18010c330  lea     rdx, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010c337  lea     rcx, aStatusPropagat; "Status propagated"
0x18010c33e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18010c343  mov     ecx, ebx; this
0x18010c345  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18010c34a  mov     ebx, eax
0x18010c34c  lea     rcx, [rbp+57h+var_58]
0x18010c350  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x18010c355  mov     eax, ebx
0x18010c357  mov     rbx, [rsp+0C0h+arg_8]
0x18010c35f  add     rsp, 90h
0x18010c366  pop     r15
0x18010c368  pop     r14
0x18010c36a  pop     r13
0x18010c36c  pop     r12
0x18010c36e  pop     rdi
0x18010c36f  pop     rsi
0x18010c370  pop     rbp
0x18010c371  retn
```
