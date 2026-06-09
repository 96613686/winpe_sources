# IsolationImplementation::Com::CEnumSTORE_DEPLOYMENT_METADATA::IEnumSTORE_DEPLOYMENT_METADATA_Next(ulong,IDefinitionAppId * * const,ulong *)

- ea: `0x18010bdec`
- end: `0x18010c099`
- name: `?IEnumSTORE_DEPLOYMENT_METADATA_Next@CEnumSTORE_DEPLOYMENT_METADATA@Com@IsolationImplementation@@IEAAJKQEAPEAUIDefinitionAppId@@PEAK@Z`
- size: `685`
- prototype: `int(IsolationImplementation::Com::CEnumSTORE_DEPLOYMENT_METADATA *__hidden this, unsigned int, struct IDefinitionAppId **const, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18010c7b0`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x180012910`
- `0x180012b38`
- `0x180013e50`
- `0x180013ed0`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x1800a78e4`
- `0x18010aedc`
- `0x18010bdec`
- `0x18012a020`
- `0x18012a030`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010bef1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010bf83`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010c045`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010bef1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010bf83`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18010c045`

## string_xrefs

- `0x18010be0f`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`
- `0x18010c025`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`
- `0x18010c057`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\enumdeploymentmetadata.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::CEnumSTORE_DEPLOYMENT_METADATA::IEnumSTORE_DEPLOYMENT_METADATA_Next(
        IsolationImplementation::Com::CEnumSTORE_DEPLOYMENT_METADATA *this,
        unsigned int a2,
        struct IDefinitionAppId **const a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rbx
  unsigned int v7; // ebx
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rdi
  int v11; // ebx
  __int64 v12; // rbx
  HANDLE ProcessHeap_0; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // r14
  int v16; // r9d
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rcx
  int v23; // eax
  int v24; // r9d
  int v25; // edx
  unsigned int v27; // [rsp+20h] [rbp-49h]
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
  __int64 v29; // [rsp+38h] [rbp-31h] BYREF
  __int128 v30; // [rsp+40h] [rbp-29h]
  const char *v31; // [rsp+50h] [rbp-19h] BYREF
  int v32; // [rsp+58h] [rbp-11h]
  unsigned int v33; // [rsp+60h] [rbp-9h]
  __int128 v34; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v35; // [rsp+78h] [rbp+Fh]
  unsigned __int64 v36; // [rsp+80h] [rbp+17h]
  Windows::ErrorHandling::COM *v38; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 v39; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = a2;
  v31 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploymentmetadata.cpp";
  v33 = -2147023537;
  if ( a3 && a2 )
    memset_thunk_772440563353939046(a3, 0, 8LL * a2);
  if ( a4 )
    *a4 = 0;
  if ( a3 )
  {
    v8 = 0;
    v39 = 0;
    v9 = 0;
    v35 = 0;
    v36 = 0;
    v10 = v4;
    v34 = 0;
    if ( (_DWORD)v4 )
    {
      v28 = 0;
      BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(&v38, 8, v4, &v28);
      v11 = (int)v38;
      if ( (int)v38 >= 0 )
      {
        v12 = v28;
        ProcessHeap_0 = GetProcessHeap_0();
        v14 = HeapAlloc_0(ProcessHeap_0, 0, v12 + 8);
        v15 = v14;
        if ( v14 )
        {
          *((_QWORD *)&v34 + 1) = v14;
          v8 = v10;
          v35 = v10;
          goto LABEL_20;
        }
        v11 = -1073741801;
      }
      if ( v11 < 0 )
      {
        if ( v11 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        v16 = v11;
        v17 = 87;
        goto LABEL_44;
      }
    }
    v15 = (_QWORD *)*((_QWORD *)&v34 + 1);
LABEL_20:
    v29 = 0;
    v30 = 0;
    v18 = *((_QWORD *)this + 2);
    if ( v8 )
      v9 = v8;
    v36 = v9;
    v11 = Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<CComponentStoreMetadataDeploymentEnumeratorTraits>::Attach(
            &v29,
            v18);
    if ( v11 >= 0
      && (v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD *, unsigned __int64 *))(**(_QWORD **)v30
                                                                                                  + 16LL))(
                  *(_QWORD *)v30,
                  v10,
                  v15,
                  &v39),
          v11 >= 0) )
    {
      v19 = *((_QWORD *)&v30 + 1);
      if ( *((_QWORD *)&v30 + 1) )
        (*(void (__fastcall **)(__int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
                                        + 48))(v29);
      v20 = v39;
      if ( v39 > v10 )
      {
        v32 = 95;
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v34);
        Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
          &v31,
          &v31);
        return v33;
      }
      v21 = 0;
      if ( v39 )
      {
        while ( 1 )
        {
          v22 = v15[v21];
          if ( v9 < v8 )
            v9 = v8;
          v36 = v9;
          v23 = IsolationImplementation::Com::CDefinitionAppId::Create(v22, v19, &a3[v21]);
          v7 = v23;
          if ( v23 < 0 )
            break;
          v20 = v39;
          if ( ++v21 == v39 )
            goto LABEL_38;
        }
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploy"
                                         "mentmetadata.cpp",
          (const char *)0x62,
          v23,
          v24);
        goto LABEL_45;
      }
LABEL_38:
      if ( v20 <= 0xFFFFFFFF )
      {
        *a4 = v20;
        v7 = 0;
LABEL_45:
        BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(&v34);
        return v7;
      }
      v11 = -1073741675;
      if ( g_NTSTATUS_to_break_on_propagate == -1073741675 )
        DebugBreak();
      v16 = -1073741675;
      v17 = 100;
    }
    else
    {
      if ( *((_QWORD *)&v30 + 1) )
        (*(void (__fastcall **)(__int64))(Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
                                        + 48))(v29);
      if ( v11 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      v16 = v11;
      v17 = 93;
    }
LABEL_44:
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\enumdeploymentmetadata.cpp",
      (const char *)v17,
      v16,
      v27);
    v7 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)(unsigned int)v11, v25);
    goto LABEL_45;
  }
  v32 = 82;
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v31);
  return v33;
}

```

## disassembly

```asm
0x18010bdec  mov     [rsp-8+arg_8], rbx
0x18010bdf1  mov     [rsp-8+arg_0], rcx
0x18010bdf6  push    rbp
0x18010bdf7  push    rsi
0x18010bdf8  push    rdi
0x18010bdf9  push    r12
0x18010bdfb  push    r13
0x18010bdfd  push    r14
0x18010bdff  push    r15
0x18010be01  lea     rbp, [rsp-27h]
0x18010be06  sub     rsp, 90h
0x18010be0d  mov     ebx, edx
0x18010be0f  lea     rax, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010be16  mov     [rbp+57h+var_70], rax
0x18010be1a  mov     r13, r9
0x18010be1d  mov     [rbp+57h+var_60], 8007054Fh
0x18010be24  mov     r12, r8
0x18010be27  test    r8, r8
0x18010be2a  jz      short loc_18010BE41
0x18010be2c  mov     r8d, ebx
0x18010be2f  test    edx, edx
0x18010be31  jz      short loc_18010BE41
0x18010be33  shl     r8, 3; Size
0x18010be37  xor     edx, edx; Val
0x18010be39  mov     rcx, r12; void *
0x18010be3c  call    memset$thunk$772440563353939046
0x18010be41  test    r13, r13
0x18010be44  jz      short loc_18010BE4E
0x18010be46  mov     dword ptr [r13+0], 0
0x18010be4e  test    r12, r12
0x18010be51  jnz     short loc_18010BE6B
0x18010be53  lea     rcx, [rbp+57h+var_70]
0x18010be57  mov     [rbp+57h+var_68], 52h ; 'R'
0x18010be5e  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18010be63  mov     ebx, [rbp+57h+var_60]
0x18010be66  jmp     loc_18010C07C
0x18010be6b  xor     r15d, r15d
0x18010be6e  mov     [rbp+57h+arg_18], 0
0x18010be76  xor     esi, esi
0x18010be78  mov     [rbp+57h+var_48], r15
0x18010be7c  mov     [rbp+57h+var_40], rsi
0x18010be80  xorps   xmm0, xmm0
0x18010be83  mov     rdi, rbx
0x18010be86  movdqu  [rbp+57h+var_58], xmm0
0x18010be8b  test    ebx, ebx
0x18010be8d  jz      short loc_18010BF05
0x18010be8f  lea     r9, [rbp+57h+var_90]
0x18010be93  mov     [rbp+57h+var_90], rsi
0x18010be97  mov     r8, rbx
0x18010be9a  lea     edx, [rsi+8]
0x18010be9d  lea     rcx, [rbp+57h+arg_10]
0x18010bea1  call    ??$MultiplyWithOverflowCheck@VCCallDisposition@Rtl@BUCL@@_K@BUCL@@YA?AVCCallDisposition@Rtl@0@_K0AEA_K@Z; BUCL::MultiplyWithOverflowCheck<BUCL::Rtl::CCallDisposition,unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x18010bea6  mov     ebx, dword ptr [rbp+57h+arg_10]
0x18010bea9  test    ebx, ebx
0x18010beab  jns     short loc_18010BEC1
0x18010bead  xor     r14d, r14d
0x18010beb0  test    ebx, ebx
0x18010beb2  js      short loc_18010BEE5
0x18010beb4  mov     qword ptr [rbp+57h+var_58+8], r14
0x18010beb8  mov     r15, rdi
0x18010bebb  mov     [rbp+57h+var_48], rdi
0x18010bebf  jmp     short loc_18010BF09
0x18010bec1  mov     rbx, [rbp+57h+var_90]
0x18010bec5  call    GetProcessHeap_0
0x18010beca  mov     rcx, rax; hHeap
0x18010becd  lea     r8, [rbx+8]; dwBytes
0x18010bed1  xor     edx, edx; dwFlags
0x18010bed3  call    HeapAlloc_0
0x18010bed8  mov     r14, rax
0x18010bedb  test    rax, rax
0x18010bede  jnz     short loc_18010BEB4
0x18010bee0  mov     ebx, 0C0000017h
0x18010bee5  test    ebx, ebx
0x18010bee7  jns     short loc_18010BF05
0x18010bee9  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18010beef  jnz     short loc_18010BEF7
0x18010bef1  call    cs:__imp_DebugBreak
0x18010bef7  mov     r9d, ebx
0x18010befa  mov     r8d, 57h ; 'W'
0x18010bf00  jmp     loc_18010C057
0x18010bf05  mov     r14, qword ptr [rbp+57h+var_58+8]
0x18010bf09  mov     rdx, [rbp+57h+arg_0]
0x18010bf0d  lea     rcx, [rbp+57h+var_88]
0x18010bf11  xorps   xmm0, xmm0
0x18010bf14  mov     [rbp+57h+var_88], 0
0x18010bf1c  test    r15, r15
0x18010bf1f  movdqu  [rbp+57h+var_80], xmm0
0x18010bf24  mov     rdx, [rdx+10h]
0x18010bf28  cmovnz  rsi, r15
0x18010bf2c  mov     [rbp+57h+var_40], rsi
0x18010bf30  call    ?Attach@?$CTypeSafeHandlePointer@VCComponentStoreMetadataDeploymentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@QEAAJU_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR@2Isolation@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTypeSafeHandlePointer<CComponentStoreMetadataDeploymentEnumeratorTraits>::Attach(Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR)
0x18010bf35  mov     ebx, eax
0x18010bf37  test    eax, eax
0x18010bf39  js      short loc_18010BF5E
0x18010bf3b  mov     rax, qword ptr [rbp+57h+var_80]
0x18010bf3f  lea     r9, [rbp+57h+arg_18]
0x18010bf43  mov     r8, r14
0x18010bf46  mov     rdx, rdi
0x18010bf49  mov     rcx, [rax]
0x18010bf4c  mov     rax, [rcx]
0x18010bf4f  mov     rax, [rax+10h]
0x18010bf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bf58  mov     ebx, eax
0x18010bf5a  test    eax, eax
0x18010bf5c  jns     short loc_18010BF97
0x18010bf5e  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x18010bf62  test    rdx, rdx
0x18010bf65  jz      short loc_18010BF7B
0x18010bf67  mov     rax, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentEnumerator@@VCComponentStoreMetadataDeploymentEnumeratorCD@@VCComponentStoreMetadataDeploymentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
0x18010bf6e  mov     rcx, [rbp+57h+var_88]
0x18010bf72  mov     rax, [rax+30h]
0x18010bf76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bf7b  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x18010bf81  jnz     short loc_18010BF89
0x18010bf83  call    cs:__imp_DebugBreak
0x18010bf89  mov     r9d, ebx
0x18010bf8c  mov     r8d, 5Dh ; ']'
0x18010bf92  jmp     loc_18010C057
0x18010bf97  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x18010bf9b  test    rdx, rdx
0x18010bf9e  jz      short loc_18010BFB4
0x18010bfa0  mov     rax, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR@Rtl@Isolation@Windows@@VCComponentStoreMetadataDeploymentEnumerator@@VCComponentStoreMetadataDeploymentEnumeratorCD@@VCComponentStoreMetadataDeploymentEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE_METADATA_DEPLOYMENT_ENUMERATOR,CComponentStoreMetadataDeploymentEnumerator,CComponentStoreMetadataDeploymentEnumeratorCD,CComponentStoreMetadataDeploymentEnumeratorTraits>::ms_ptti
0x18010bfa7  mov     rcx, [rbp+57h+var_88]
0x18010bfab  mov     rax, [rax+30h]
0x18010bfaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bfb4  mov     rax, [rbp+57h+arg_18]
0x18010bfb8  cmp     rax, rdi
0x18010bfbb  jbe     short loc_18010BFDF
0x18010bfbd  lea     rcx, [rbp+57h+var_58]
0x18010bfc1  mov     [rbp+57h+var_68], 5Fh ; '_'
0x18010bfc8  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_DEFINITION_APPID@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x18010bfcd  lea     rdx, [rbp+57h+var_70]
0x18010bfd1  lea     rcx, [rbp+57h+var_70]
0x18010bfd5  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18010bfda  jmp     loc_18010BE63
0x18010bfdf  xor     edi, edi
0x18010bfe1  test    rax, rax
0x18010bfe4  jz      short loc_18010C010
0x18010bfe6  mov     rcx, [r14+rdi*8]
0x18010bfea  lea     r8, [r12+rdi*8]
0x18010bfee  cmp     rsi, r15
0x18010bff1  cmovb   rsi, r15
0x18010bff5  mov     [rbp+57h+var_40], rsi
0x18010bff9  call    ?Create@CDefinitionAppId@Com@IsolationImplementation@@KAJU_DEFINITION_APPID@Rtl@Isolation@Windows@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; IsolationImplementation::Com::CDefinitionAppId::Create(Windows::Isolation::Rtl::_DEFINITION_APPID,_GUID const &,IUnknown * *)
0x18010bffe  mov     ebx, eax
0x18010c000  test    eax, eax
0x18010c002  js      short loc_18010C022
0x18010c004  mov     rax, [rbp+57h+arg_18]
0x18010c008  inc     rdi
0x18010c00b  cmp     rdi, rax
0x18010c00e  jnz     short loc_18010BFE6
0x18010c010  mov     ecx, 0FFFFFFFFh
0x18010c015  cmp     rax, rcx
0x18010c018  ja      short loc_18010C038
0x18010c01a  mov     [r13+0], eax
0x18010c01e  xor     ebx, ebx
0x18010c020  jmp     short loc_18010C073
0x18010c022  mov     r8d, eax; int
0x18010c025  lea     rcx, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010c02c  mov     edx, 62h ; 'b'; char *
0x18010c031  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x18010c036  jmp     short loc_18010C073
0x18010c038  mov     ebx, 0C0000095h
0x18010c03d  cmp     cs:g_NTSTATUS_to_break_on_propagate, ebx
0x18010c043  jnz     short loc_18010C04B
0x18010c045  call    cs:__imp_DebugBreak
0x18010c04b  mov     r9d, 0C0000095h; int
0x18010c051  mov     r8d, 64h ; 'd'; char *
0x18010c057  lea     rdx, aOnecoreComNetf_29; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18010c05e  lea     rcx, aStatusPropagat; "Status propagated"
0x18010c065  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18010c06a  mov     ecx, ebx; this
0x18010c06c  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18010c071  mov     ebx, eax
0x18010c073  lea     rcx, [rbp+57h+var_58]
0x18010c077  call    ??1?$CSmartArrayHolder@V?$CDefaultObjectTraits@U_DEFINITION_APPID@Rtl@Isolation@Windows@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@2@VCCallDisposition@42@@BCL@@QEAA@XZ; BCL::CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>::~CSmartArrayHolder<BCL::CDefaultObjectTraits<Windows::Isolation::Rtl::_DEFINITION_APPID,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>,BCL::Nt::CCallDisposition>(void)
0x18010c07c  mov     eax, ebx
0x18010c07e  mov     rbx, [rsp+0C0h+arg_8]
0x18010c086  add     rsp, 90h
0x18010c08d  pop     r15
0x18010c08f  pop     r14
0x18010c091  pop     r13
0x18010c093  pop     r12
0x18010c095  pop     rdi
0x18010c096  pop     rsi
0x18010c097  pop     rbp
0x18010c098  retn
```
