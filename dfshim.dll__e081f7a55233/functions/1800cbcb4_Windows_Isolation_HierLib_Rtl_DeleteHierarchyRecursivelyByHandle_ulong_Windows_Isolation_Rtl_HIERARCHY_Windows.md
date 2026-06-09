# Windows::Isolation::HierLib::Rtl::DeleteHierarchyRecursivelyByHandle(ulong,Windows::Isolation::Rtl::_HIERARCHY,Windows::Isolation::HierLib::Rtl::_DELETE_HIERARCHY_RECURSIVELY_BY_HANDLE_DISPOSITION *)

- ea: `0x1800cbcb4`
- end: `0x1800cc1e7`
- name: `?DeleteHierarchyRecursivelyByHandle@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@PEAU_DELETE_HIERARCHY_RECURSIVELY_BY_HANDLE_DISPOSITION@1234@@Z`
- size: `1331`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800cbb68`
- `0x1800ccb28`
- `0x1800cd028`

## callees

- `0x180012b1c`
- `0x18002a844`
- `0x180042f10`
- `0x18004f2dc`
- `0x1800cb9c4`
- `0x1800cba44`
- `0x1800cbcb4`
- `0x1800cc1f0`
- `0x1800cc2ac`
- `0x180113cfc`
- `0x180114224`
- `0x1801142f0`
- `0x180127dc0`
- `0x18012a020`
- `0x18012a030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cbeaf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cc0a0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cc18d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cbeaf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cc0a0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cc18d`

## string_xrefs

- `0x1800cbda9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cbe53`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cc03e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cc055`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cc0d1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cc0f9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800cbcef`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\hier_library.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::HierLib::Rtl::DeleteHierarchyRecursivelyByHandle(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v5; // rdx
  int HierarchyEnumeratorData; // ebx
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r15
  __int64 v11; // rsi
  __int64 v12; // r10
  unsigned int *v13; // r11
  signed int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // r15
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r10
  unsigned int *v24; // r11
  signed int v25; // ecx
  __int64 v26; // r10
  signed int v27; // ecx
  __int64 v28; // r10
  unsigned int *v29; // r11
  __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  const char *v32; // [rsp+38h] [rbp-C8h] BYREF
  int v33; // [rsp+40h] [rbp-C0h]
  unsigned int v34; // [rsp+48h] [rbp-B8h]
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v36[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+78h] [rbp-88h]
  _DWORD v39[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h]
  int v42; // [rsp+9Ch] [rbp-64h]
  __int128 v43; // [rsp+A0h] [rbp-60h]
  __int128 v44; // [rsp+B0h] [rbp-50h]
  __int128 v45; // [rsp+C0h] [rbp-40h]
  _QWORD v46[96]; // [rsp+D0h] [rbp-30h] BYREF

  v34 = -1073741595;
  v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\hier_library.cpp";
  if ( a3 )
  {
    v5 = *a3;
    if ( a3 + 1 <= (__int64 *)((char *)a3 + *a3) && v5 != 8 )
      memset_thunk_772440563353939046(a3 + 1, 0, v5 - 8);
    if ( *a3 != 24 )
    {
      v33 = 160;
LABEL_69:
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v32);
      return v34;
    }
  }
  if ( !Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY,Windows::Isolation::Hierarchy::Private::CHierarchy,Windows::Isolation::Hierarchy::Private::CConstructorData,Windows::Isolation::Hierarchy::Private::CHierarchyObjectTraits>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(a2) )
  {
    v33 = 164;
    goto LABEL_69;
  }
  v37 = 0;
  v36[0] = v36;
  v38 = 0;
  v36[1] = v36;
  v36[2] = v36;
  HierarchyEnumeratorData = CHierarchyHandleQueue::AddToHead(v36, a2);
  if ( HierarchyEnumeratorData >= 0 )
  {
    while ( 1 )
    {
      v7 = v36[0];
      if ( (_QWORD *)v36[0] == v36 )
      {
        HierarchyEnumeratorData = 0;
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v36[0] + 32LL);
      v31 = 0;
      v35 = 0;
      HierarchyEnumeratorData = RtlEnumerateHierarchy(2, v8, 0, &v31);
      if ( HierarchyEnumeratorData < 0 )
        break;
      HierarchyEnumeratorData = RtlFetchHierarchyEnumeratorData(v31, 32, v46, &v35);
      if ( HierarchyEnumeratorData < 0 )
        break;
      v10 = v35;
      v11 = 0;
      if ( v35 )
      {
        do
        {
          HierarchyEnumeratorData = Windows::Isolation::HierLib::Rtl::RtlDeleteHierarchyValue(
                                      v9,
                                      *(_QWORD *)(v7 + 32),
                                      &v46[3 * v11],
                                      0);
          if ( HierarchyEnumeratorData < 0 )
            goto LABEL_49;
          if ( a3 )
            ++a3[1];
        }
        while ( ++v11 != v10 );
      }
      if ( v31 )
      {
        v34 = -1073741595;
        v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v31) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v13 + 4))(*v13, v12);
          v14 = 0;
        }
        else
        {
          v33 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v32);
          v14 = v34;
        }
        if ( v14 < 0 )
          RaiseException(v14, 1u, 0, 0);
      }
      v15 = *(_QWORD *)(v7 + 32);
      v31 = 0;
      HierarchyEnumeratorData = RtlEnumerateHierarchy(1, v15, 0, &v31);
      if ( HierarchyEnumeratorData < 0
        || (v35 = 0,
            HierarchyEnumeratorData = RtlFetchHierarchyEnumeratorData(v31, 32, v46, &v35),
            HierarchyEnumeratorData < 0) )
      {
        v26 = v31;
        if ( !v31 )
          goto LABEL_10;
        v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        goto LABEL_56;
      }
      v16 = v35;
      if ( v35 )
      {
        v17 = 0;
        while ( 1 )
        {
          v18 = *(_QWORD *)(v7 + 32);
          v35 = 0;
          v39[0] = 0;
          HierarchyEnumeratorData = Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(
                                      4,
                                      v18,
                                      3221291008LL,
                                      &v46[3 * v17],
                                      &v35,
                                      v39);
          if ( HierarchyEnumeratorData < 0 )
            break;
          HierarchyEnumeratorData = CHierarchyHandleQueue::AddToHead(v36, v35);
          if ( HierarchyEnumeratorData < 0 )
            break;
          Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v35);
          if ( ++v17 == v16 )
            goto LABEL_42;
        }
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(&v35);
LABEL_49:
        v26 = v31;
        if ( !v31 )
          goto LABEL_10;
        v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        goto LABEL_60;
      }
      v19 = *(_QWORD *)(v7 + 32);
      v40 = 64;
      v43 = 0;
      DWORD2(v43) = 0;
      v44 = 0u;
      v41 = 0;
      v42 = 8;
      v45 = 0;
      HierarchyEnumeratorData = RtlPerformHierarchyOperation(v19, &v40);
      if ( HierarchyEnumeratorData < 0 )
      {
        v26 = v31;
        if ( !v31 )
          goto LABEL_10;
        v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
LABEL_56:
        v34 = -1073741595;
        goto LABEL_61;
      }
      if ( a3 )
        ++a3[2];
      v20 = (_QWORD *)v36[0];
      if ( (_QWORD *)v36[0] != v36 && v36[0] )
      {
        if ( *(_QWORD **)(v36[0] + 16LL) == v36 )
        {
          **(_QWORD **)(v36[0] + 8LL) = *(_QWORD *)v36[0];
          *(_QWORD *)(*v20 + 8LL) = v20[1];
          --v38;
        }
        Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(v20 + 4);
        v20[2] = 0;
        RtlFreeHeap(v22, v21, v20);
      }
LABEL_42:
      if ( v31 )
      {
        v34 = -1073741595;
        v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
        if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
          && (unsigned __int8)RtlIsTypeSafeHandleValid(v31) )
        {
          (*((void (__fastcall **)(_QWORD, __int64))v24 + 4))(*v24, v23);
          v25 = 0;
        }
        else
        {
          v33 = 292;
          Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v32);
          v25 = v34;
        }
        if ( v25 < 0 )
          RaiseException(v25, 1u, 0, 0);
      }
    }
    v26 = v31;
    if ( !v31 )
      goto LABEL_10;
    v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
LABEL_60:
    v34 = -1073741595;
LABEL_61:
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v26) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v29 + 4))(*v29, v28);
      v27 = 0;
    }
    else
    {
      v33 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v32);
      v27 = v34;
    }
    if ( v27 < 0 )
      RaiseException(v27, 1u, 0, 0);
    v31 = 0;
  }
LABEL_10:
  CDequeWithCleanup<CQueuedHierarchyHandle,0>::~CDequeWithCleanup<CQueuedHierarchyHandle,0>(v36);
  return (unsigned int)HierarchyEnumeratorData;
}

```

## disassembly

```asm
0x1800cbcb4  mov     [rsp-8+arg_0], rbx
0x1800cbcb9  push    rbp
0x1800cbcba  push    rsi
0x1800cbcbb  push    rdi
0x1800cbcbc  push    r12
0x1800cbcbe  push    r13
0x1800cbcc0  push    r14
0x1800cbcc2  push    r15
0x1800cbcc4  lea     rbp, [rsp-2E0h]
0x1800cbccc  sub     rsp, 3E0h
0x1800cbcd3  mov     rax, cs:__security_cookie
0x1800cbcda  xor     rax, rsp
0x1800cbcdd  mov     [rbp+310h+var_40], rax
0x1800cbce4  xor     r12d, r12d
0x1800cbce7  mov     [rsp+410h+var_3C8], 0C00000E5h
0x1800cbcef  lea     rax, aOnecoreComNetf_78; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cbcf6  mov     rdi, r8
0x1800cbcf9  mov     [rsp+410h+var_3D8], rax
0x1800cbcfe  mov     rbx, rdx
0x1800cbd01  test    r8, r8
0x1800cbd04  jz      short loc_1800CBD39
0x1800cbd06  mov     rdx, [r8]
0x1800cbd09  lea     rcx, [r8+8]; void *
0x1800cbd0d  lea     rax, [r8+rdx]
0x1800cbd11  cmp     rcx, rax
0x1800cbd14  ja      short loc_1800CBD26
0x1800cbd16  lea     r8, [rdx-8]; Size
0x1800cbd1a  test    r8, r8
0x1800cbd1d  jz      short loc_1800CBD26
0x1800cbd1f  xor     edx, edx; Val
0x1800cbd21  call    memset$thunk$772440563353939046
0x1800cbd26  cmp     qword ptr [rdi], 18h
0x1800cbd2a  jz      short loc_1800CBD39
0x1800cbd2c  mov     [rsp+410h+var_3D0], 0A0h
0x1800cbd34  jmp     loc_1800CC1AD
0x1800cbd39  mov     rdx, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY@Rtl@Isolation@Windows@@VCHierarchy@Private@Hierarchy@34@VCConstructorData@6734@VCHierarchyObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY,Windows::Isolation::Hierarchy::Private::CHierarchy,Windows::Isolation::Hierarchy::Private::CConstructorData,Windows::Isolation::Hierarchy::Private::CHierarchyObjectTraits>::ms_ptti
0x1800cbd40  test    rdx, rdx
0x1800cbd43  jz      loc_1800CC1A5
0x1800cbd49  mov     rcx, rbx
0x1800cbd4c  call    RtlIsTypeSafeHandleValid
0x1800cbd51  test    al, al
0x1800cbd53  jz      loc_1800CC1A5
0x1800cbd59  lea     rax, [rsp+410h+var_3B8]
0x1800cbd5e  mov     [rsp+410h+var_3A0], r12d
0x1800cbd63  mov     [rsp+410h+var_3B8], rax
0x1800cbd68  lea     rcx, [rsp+410h+var_3B8]
0x1800cbd6d  lea     rax, [rsp+410h+var_3B8]
0x1800cbd72  mov     [rsp+410h+var_398], r12
0x1800cbd77  mov     [rsp+410h+var_3B0], rax
0x1800cbd7c  mov     rdx, rbx
0x1800cbd7f  lea     rax, [rsp+410h+var_3B8]
0x1800cbd84  mov     [rsp+410h+var_3A8], rax
0x1800cbd89  call    ?AddToHead@CHierarchyHandleQueue@@QEAAJU_HIERARCHY@Rtl@Isolation@Windows@@@Z; CHierarchyHandleQueue::AddToHead(Windows::Isolation::Rtl::_HIERARCHY)
0x1800cbd8e  mov     ebx, eax
0x1800cbd90  test    eax, eax
0x1800cbd92  jns     short loc_1800CBDA3
0x1800cbd94  lea     rcx, [rsp+410h+var_3B8]
0x1800cbd99  call    ??1?$CDequeWithCleanup@VCQueuedHierarchyHandle@@$0A@@@QEAA@XZ; CDequeWithCleanup<CQueuedHierarchyHandle,0>::~CDequeWithCleanup<CQueuedHierarchyHandle,0>(void)
0x1800cbd9e  jmp     loc_1800CC1BB
0x1800cbda3  mov     r13d, 1
0x1800cbda9  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cbdb0  mov     r14, [rsp+410h+var_3B8]
0x1800cbdb5  lea     rax, [rsp+410h+var_3B8]
0x1800cbdba  cmp     r14, rax
0x1800cbdbd  jz      loc_1800CC19D
0x1800cbdc3  mov     rdx, [r14+20h]
0x1800cbdc7  lea     r9, [rsp+410h+var_3E0]
0x1800cbdcc  xor     r8d, r8d
0x1800cbdcf  mov     [rsp+410h+var_3E0], r12
0x1800cbdd4  mov     [rsp+410h+var_3C0], r12
0x1800cbdd9  lea     ecx, [r8+2]
0x1800cbddd  call    RtlEnumerateHierarchy
0x1800cbde2  mov     ebx, eax
0x1800cbde4  test    eax, eax
0x1800cbde6  js      loc_1800CC138
0x1800cbdec  mov     rcx, [rsp+410h+var_3E0]
0x1800cbdf1  lea     r9, [rsp+410h+var_3C0]
0x1800cbdf6  lea     r8, [rbp+310h+var_340]
0x1800cbdfa  mov     edx, 20h ; ' '
0x1800cbdff  call    RtlFetchHierarchyEnumeratorData
0x1800cbe04  mov     ebx, eax
0x1800cbe06  test    eax, eax
0x1800cbe08  js      loc_1800CC138
0x1800cbe0e  mov     r15, [rsp+410h+var_3C0]
0x1800cbe13  mov     rsi, r12
0x1800cbe16  test    r15, r15
0x1800cbe19  jz      short loc_1800CBE4E
0x1800cbe1b  mov     rdx, [r14+20h]
0x1800cbe1f  lea     rax, [rsi+rsi*2]
0x1800cbe23  lea     r8, [rbp+310h+var_340]
0x1800cbe27  xor     r9d, r9d
0x1800cbe2a  lea     r8, [r8+rax*8]
0x1800cbe2e  call    ?RtlDeleteHierarchyValue@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@PEBU_LUNICODE_STRING@@PEAK@Z; Windows::Isolation::HierLib::Rtl::RtlDeleteHierarchyValue(ulong,Windows::Isolation::Rtl::_HIERARCHY,_LUNICODE_STRING const *,ulong *)
0x1800cbe33  mov     ebx, eax
0x1800cbe35  test    eax, eax
0x1800cbe37  js      loc_1800CC0C3
0x1800cbe3d  test    rdi, rdi
0x1800cbe40  jz      short loc_1800CBE46
0x1800cbe42  add     [rdi+8], r13
0x1800cbe46  add     rsi, r13
0x1800cbe49  cmp     rsi, r15
0x1800cbe4c  jnz     short loc_1800CBE1B
0x1800cbe4e  mov     r10, [rsp+410h+var_3E0]
0x1800cbe53  lea     r15, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cbe5a  mov     esi, 0C00000E5h
0x1800cbe5f  test    r10, r10
0x1800cbe62  jz      short loc_1800CBEB5
0x1800cbe64  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cbe6b  mov     [rsp+410h+var_3C8], esi
0x1800cbe6f  mov     [rsp+410h+var_3D8], r15
0x1800cbe74  test    r11, r11
0x1800cbe77  jz      loc_1800CBF86
0x1800cbe7d  mov     rdx, r11
0x1800cbe80  mov     rcx, r10
0x1800cbe83  call    RtlIsTypeSafeHandleValid
0x1800cbe88  test    al, al
0x1800cbe8a  jz      loc_1800CBF86
0x1800cbe90  mov     ecx, [r11]
0x1800cbe93  mov     rdx, r10
0x1800cbe96  mov     rax, [r11+20h]
0x1800cbe9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cbe9f  mov     ecx, r12d; dwExceptionCode
0x1800cbea2  test    ecx, ecx
0x1800cbea4  jns     short loc_1800CBEB5
0x1800cbea6  xor     r9d, r9d; lpArguments
0x1800cbea9  xor     r8d, r8d; nNumberOfArguments
0x1800cbeac  mov     edx, r13d; dwExceptionFlags
0x1800cbeaf  call    cs:__imp_RaiseException
0x1800cbeb5  mov     rdx, [r14+20h]
0x1800cbeb9  lea     r9, [rsp+410h+var_3E0]
0x1800cbebe  xor     r8d, r8d
0x1800cbec1  mov     [rsp+410h+var_3E0], r12
0x1800cbec6  mov     ecx, r13d
0x1800cbec9  call    RtlEnumerateHierarchy
0x1800cbece  mov     ebx, eax
0x1800cbed0  test    eax, eax
0x1800cbed2  js      loc_1800CC107
0x1800cbed8  mov     rcx, [rsp+410h+var_3E0]
0x1800cbedd  lea     r9, [rsp+410h+var_3C0]
0x1800cbee2  lea     r8, [rbp+310h+var_340]
0x1800cbee6  mov     [rsp+410h+var_3C0], r12
0x1800cbeeb  mov     edx, 20h ; ' '
0x1800cbef0  call    RtlFetchHierarchyEnumeratorData
0x1800cbef5  mov     ebx, eax
0x1800cbef7  test    eax, eax
0x1800cbef9  js      loc_1800CC107
0x1800cbeff  mov     r15, [rsp+410h+var_3C0]
0x1800cbf04  test    r15, r15
0x1800cbf07  jz      loc_1800CBFA1
0x1800cbf0d  mov     rsi, r12
0x1800cbf10  mov     rdx, [r14+20h]
0x1800cbf14  lea     rax, [rsi+rsi*2]
0x1800cbf18  lea     r9, [rbp+310h+var_340]
0x1800cbf1c  mov     [rsp+410h+var_3C0], r12
0x1800cbf21  lea     r9, [r9+rax*8]
0x1800cbf25  mov     [rbp+310h+var_390], r12d
0x1800cbf29  lea     rax, [rbp+310h+var_390]
0x1800cbf2d  mov     r8d, 0C0010000h
0x1800cbf33  mov     [rsp+410h+var_3E8], rax
0x1800cbf38  mov     ecx, 4
0x1800cbf3d  lea     rax, [rsp+410h+var_3C0]
0x1800cbf42  mov     [rsp+410h+var_3F0], rax
0x1800cbf47  call    ?RtlOpenHierarchy@Rtl@HierLib@Isolation@Windows@@YAJKU_HIERARCHY@134@KPEBU_LUNICODE_STRING@@PEAU5134@PEAK@Z; Windows::Isolation::HierLib::Rtl::RtlOpenHierarchy(ulong,Windows::Isolation::Rtl::_HIERARCHY,ulong,_LUNICODE_STRING const *,Windows::Isolation::Rtl::_HIERARCHY *,ulong *)
0x1800cbf4c  mov     ebx, eax
0x1800cbf4e  test    eax, eax
0x1800cbf50  js      loc_1800CC0DF
0x1800cbf56  mov     rdx, [rsp+410h+var_3C0]
0x1800cbf5b  lea     rcx, [rsp+410h+var_3B8]
0x1800cbf60  call    ?AddToHead@CHierarchyHandleQueue@@QEAAJU_HIERARCHY@Rtl@Isolation@Windows@@@Z; CHierarchyHandleQueue::AddToHead(Windows::Isolation::Rtl::_HIERARCHY)
0x1800cbf65  lea     rcx, [rsp+410h+var_3C0]
0x1800cbf6a  mov     ebx, eax
0x1800cbf6c  test    eax, eax
0x1800cbf6e  js      loc_1800CC0E4
0x1800cbf74  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800cbf79  add     rsi, r13
0x1800cbf7c  cmp     rsi, r15
0x1800cbf7f  jnz     short loc_1800CBF10
0x1800cbf81  jmp     loc_1800CC039
0x1800cbf86  mov     [rsp+410h+var_3D0], 124h
0x1800cbf8e  lea     rcx, [rsp+410h+var_3D8]
0x1800cbf93  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cbf98  mov     ecx, [rsp+410h+var_3C8]
0x1800cbf9c  jmp     loc_1800CBEA2
0x1800cbfa1  mov     rcx, [r14+20h]
0x1800cbfa5  lea     rdx, [rbp+310h+var_380]
0x1800cbfa9  xorps   xmm0, xmm0
0x1800cbfac  mov     [rbp+310h+var_380], 40h ; '@'
0x1800cbfb4  movups  [rbp+310h+var_370], xmm0
0x1800cbfb8  mov     dword ptr [rbp+310h+var_370+8], r12d
0x1800cbfbc  movups  [rbp+310h+var_360], xmm0
0x1800cbfc0  mov     qword ptr [rbp+310h+var_360], r12
0x1800cbfc4  mov     [rbp+310h+var_378], r12d
0x1800cbfc8  mov     [rbp+310h+var_374], 8
0x1800cbfcf  movups  [rbp+310h+var_350], xmm0
0x1800cbfd3  call    RtlPerformHierarchyOperation
0x1800cbfd8  mov     ebx, eax
0x1800cbfda  test    eax, eax
0x1800cbfdc  js      loc_1800CC0EB
0x1800cbfe2  test    rdi, rdi
0x1800cbfe5  jz      short loc_1800CBFEB
0x1800cbfe7  add     [rdi+10h], r13
0x1800cbfeb  mov     rbx, [rsp+410h+var_3B8]
0x1800cbff0  lea     rax, [rsp+410h+var_3B8]
0x1800cbff5  cmp     rbx, rax
0x1800cbff8  jz      short loc_1800CC039
0x1800cbffa  test    rbx, rbx
0x1800cbffd  jz      short loc_1800CC039
0x1800cbfff  lea     rax, [rsp+410h+var_3B8]
0x1800cc004  cmp     [rbx+10h], rax
0x1800cc008  jnz     short loc_1800CC024
0x1800cc00a  mov     rcx, [rbx+8]
0x1800cc00e  mov     rax, [rbx]
0x1800cc011  mov     [rcx], rax
0x1800cc014  mov     rcx, [rbx]
0x1800cc017  mov     rax, [rbx+8]
0x1800cc01b  mov     [rcx+8], rax
0x1800cc01f  sub     [rsp+410h+var_398], r13
0x1800cc024  lea     rcx, [rbx+20h]
0x1800cc028  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800cc02d  mov     r8, rbx
0x1800cc030  mov     [rbx+10h], r12
0x1800cc034  call    RtlFreeHeap
0x1800cc039  mov     r10, [rsp+410h+var_3E0]
0x1800cc03e  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cc045  test    r10, r10
0x1800cc048  jz      loc_1800CBDB0
0x1800cc04e  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cc055  lea     rsi, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cc05c  mov     [rsp+410h+var_3C8], 0C00000E5h
0x1800cc064  mov     [rsp+410h+var_3D8], rsi
0x1800cc069  test    r11, r11
0x1800cc06c  jz      short loc_1800CC0AB
0x1800cc06e  mov     rdx, r11
0x1800cc071  mov     rcx, r10
0x1800cc074  call    RtlIsTypeSafeHandleValid
0x1800cc079  test    al, al
0x1800cc07b  jz      short loc_1800CC0AB
0x1800cc07d  mov     ecx, [r11]
0x1800cc080  mov     rdx, r10
0x1800cc083  mov     rax, [r11+20h]
0x1800cc087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc08c  mov     ecx, r12d; dwExceptionCode
0x1800cc08f  test    ecx, ecx
0x1800cc091  jns     loc_1800CBDB0
0x1800cc097  xor     r9d, r9d; lpArguments
0x1800cc09a  xor     r8d, r8d; nNumberOfArguments
0x1800cc09d  mov     edx, r13d; dwExceptionFlags
0x1800cc0a0  call    cs:__imp_RaiseException
0x1800cc0a6  jmp     loc_1800CBDB0
0x1800cc0ab  mov     [rsp+410h+var_3D0], 124h
0x1800cc0b3  lea     rcx, [rsp+410h+var_3D8]
0x1800cc0b8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cc0bd  mov     ecx, [rsp+410h+var_3C8]
0x1800cc0c1  jmp     short loc_1800CC08F
0x1800cc0c3  mov     r10, [rsp+410h+var_3E0]
0x1800cc0c8  test    r10, r10
0x1800cc0cb  jz      loc_1800CBD94
0x1800cc0d1  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cc0d8  mov     [rsp+410h+var_3D8], rax
0x1800cc0dd  jmp     short loc_1800CC14B
0x1800cc0df  lea     rcx, [rsp+410h+var_3C0]
0x1800cc0e4  call    ?Close@?$CTSHANDLE@VCHIERARCHY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CHIERARCHY_Traits>::Close(void)
0x1800cc0e9  jmp     short loc_1800CC0C3
0x1800cc0eb  mov     r10, [rsp+410h+var_3E0]
0x1800cc0f0  test    r10, r10
0x1800cc0f3  jz      loc_1800CBD94
0x1800cc0f9  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800cc100  mov     [rsp+410h+var_3D8], rax
0x1800cc105  jmp     short loc_1800CC11A
0x1800cc107  mov     r10, [rsp+410h+var_3E0]
0x1800cc10c  test    r10, r10
0x1800cc10f  jz      loc_1800CBD94
0x1800cc115  mov     [rsp+410h+var_3D8], r15
0x1800cc11a  mov     [rsp+410h+var_3C8], esi
0x1800cc11e  jmp     short loc_1800CC153
0x1800cc120  mov     [rsp+410h+var_3D0], 124h
0x1800cc128  lea     rcx, [rsp+410h+var_3D8]
0x1800cc12d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800cc132  mov     ecx, [rsp+410h+var_3C8]
0x1800cc136  jmp     short loc_1800CC180
0x1800cc138  mov     r10, [rsp+410h+var_3E0]
0x1800cc13d  test    r10, r10
0x1800cc140  jz      loc_1800CBD94
0x1800cc146  mov     [rsp+410h+var_3D8], rsi
0x1800cc14b  mov     [rsp+410h+var_3C8], 0C00000E5h
0x1800cc153  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_HIERARCHY_ENUMERATOR@Rtl@Isolation@Windows@@VCHierarchyEnumerator@Private@Hierarchy@34@UHIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA@6734@VCHierarchyEnumeratorObjectTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_HIERARCHY_ENUMERATOR,Windows::Isolation::Hierarchy::Private::CHierarchyEnumerator,Windows::Isolation::Hierarchy::Private::HIERARCHY_ENUMERATOR_CONSTRUCTOR_DATA,Windows::Isolation::Hierarchy::Private::CHierarchyEnumeratorObjectTraits>::ms_ptti
0x1800cc15a  test    r11, r11
0x1800cc15d  jz      short loc_1800CC120
0x1800cc15f  mov     rdx, r11
0x1800cc162  mov     rcx, r10
0x1800cc165  call    RtlIsTypeSafeHandleValid
0x1800cc16a  test    al, al
0x1800cc16c  jz      short loc_1800CC120
0x1800cc16e  mov     ecx, [r11]
0x1800cc171  mov     rdx, r10
0x1800cc174  mov     rax, [r11+20h]
0x1800cc178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc17d  mov     ecx, r12d; dwExceptionCode
0x1800cc180  test    ecx, ecx
0x1800cc182  jns     short loc_1800CC193
  ... truncated ...
```
