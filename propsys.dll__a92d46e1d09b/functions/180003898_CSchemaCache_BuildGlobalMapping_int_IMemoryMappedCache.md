# CSchemaCache::_BuildGlobalMapping(int *,IMemoryMappedCache * *)

- ea: `0x180003898`
- end: `0x180003b41`
- name: `?_BuildGlobalMapping@CSchemaCache@@AEAAJPEAHPEAPEAUIMemoryMappedCache@@@Z`
- size: `681`
- prototype: `__int64 __fastcall(CSchemaCache *__hidden this, int *, struct IMemoryMappedCache **)`
- caller_count: `5`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800362d0`
- `0x180037120`
- `0x180037c70`
- `0x1800387e0`
- `0x1800920ec`

## callees

- `0x180003898`
- `0x180003b48`
- `0x180003c70`
- `0x180003f94`
- `0x180004168`
- `0x1800209d0`
- `0x180024240`
- `0x1800242b0`
- `0x180024418`
- `0x18002f9e0`
- `0x180049780`
- `0x18006c7c0`
- `0x18007c36c`
- `0x1800902e8`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000396b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000396b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ae6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ae6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800039ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800039ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003af3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003af3`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x180003a03`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x180003a03`

## string_xrefs

- `0x180003907`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180003994`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x1800039d0`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180003a44`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x180003a7c`: `onecoreuap\shell\propsys\schemacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSchemaCache::_BuildGlobalMapping(IUnknown **this, unsigned int *a2, struct IMemoryMappedCache **a3)
{
  struct _DPA *v5; // rbx
  int Error; // edi
  int v7; // eax
  const unsigned __int16 **v8; // r13
  struct CSchemaData **v9; // rdi
  int v10; // esi
  int v11; // eax
  wil::details::in1diag3 *v12; // rcx
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  HANDLE MutexW; // r15
  unsigned int v16; // edx
  DWORD v17; // eax
  int v18; // eax
  int v19; // eax
  struct _GUID *v20; // rbx
  int v21; // eax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  _BOOL8 v24; // r8
  int v26; // [rsp+20h] [rbp-20h]
  int v27; // [rsp+20h] [rbp-20h]
  BOOL v28; // [rsp+30h] [rbp-10h] BYREF
  HDPA v29; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  struct _GUID *v32; // [rsp+98h] [rbp+58h] BYREF

  v5 = g_pfn_DPA_Create(16);
  v29 = v5;
  if ( !v5 )
  {
    Error = -2147024882;
    goto LABEL_38;
  }
  v32 = 0;
  v7 = SCHEMA_REGISTRATION_DATA::GenerateWithSchemaId(
         L"WindowsPropertyDescriptions",
         &CACHEID_SystemSchema,
         (struct SCHEMA_REGISTRATION_DATA **)&v32);
  Error = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)(unsigned int)v7,
      v26);
    goto LABEL_38;
  }
  v8 = (const unsigned __int16 **)v32;
  v9 = (struct CSchemaData **)&v32[10];
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32[10]);
  v10 = 1;
  v11 = CSchemaCache::_LoadOrBuildCachedSchema(
          (CSchemaCache *)this,
          (const struct SCHEMA_REGISTRATION_DATA *)v8,
          v8[2],
          1,
          v9);
  Error = v11;
  v12 = retaddr;
  if ( v11 < 0 )
  {
    v13 = (unsigned int)v11;
    v14 = 263;
LABEL_12:
    wil::details::in1diag3::_Log_Hr(
      v12,
      (void *)v14,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)v13,
      v27);
    goto LABEL_36;
  }
  MutexW = CreateMutexW(0, 0, L"GeneratingSchemaGlobalMapping");
  if ( MutexW )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  v12 = retaddr;
  if ( Error < 0 )
  {
    v13 = (unsigned int)Error;
    v14 = 268;
    goto LABEL_12;
  }
  v17 = WaitForSingleObject(MutexW, 0x1388u);
  if ( !v17 || v17 == 128 || (v18 = ResultFromKnownLastError(), Error = v18, v18 >= 0) )
  {
    v28 = 1;
    LODWORD(v32) = 1;
    CSchemaCache::_EnumRegisteredSchemaFiles((CSchemaCache *)this, 0, &v29, &v28);
    if ( IsOS(0x28u) )
    {
      CSchemaCache::_EnumRegisteredSchemaFiles((CSchemaCache *)this, 1, &v29, (BOOL *)&v32);
      v10 = (int)v32;
    }
    v32 = 0;
    v19 = CCacheFileBuilder<GLOBAL_MAPPING_HEADER,CGlobalMappingBuilder>::Create(this[2]);
    Error = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
        (const char *)(unsigned int)v19,
        v27);
LABEL_34:
      ReleaseMutex(MutexW);
      v5 = v29;
      goto LABEL_35;
    }
    v20 = v32;
    v21 = CGlobalMappingBuilder::BuildGlobalMapping((CGlobalMappingBuilder *)v32, (struct _GUID *)v8);
    Error = v21;
    v22 = retaddr;
    if ( v21 >= 0 )
    {
      v24 = v28 && v10;
      v21 = CCacheFileBuilder<GLOBAL_MAPPING_HEADER,CGlobalMappingBuilder>::Commit(v20, a3, v24);
      Error = v21;
      v22 = retaddr;
      if ( v21 >= 0 )
      {
        if ( a2 )
          *a2 = v20[4].Data1;
        goto LABEL_32;
      }
      v23 = 307;
    }
    else
    {
      v23 = 304;
    }
    wil::details::in1diag3::_Log_Hr(
      v22,
      (void *)v23,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
      (const char *)(unsigned int)v21,
      v27);
LABEL_32:
    if ( v20 )
      (**(void (__fastcall ***)(struct _GUID *, __int64))&v20->Data1)(v20, 1);
    goto LABEL_34;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x118,
    (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
    (const char *)(unsigned int)v18,
    v27);
LABEL_35:
  CloseHandle(MutexW);
LABEL_36:
  if ( v8 )
    SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'((SCHEMA_REGISTRATION_DATA *)v8, v16);
LABEL_38:
  if ( v5 )
  {
    g_pfn_DPA_DestroyCallback(
      v5,
      CDPA_Base<SCHEMA_REGISTRATION_DATA,CTContainer_PolicyRelease<SCHEMA_REGISTRATION_DATA>>::_StandardDestroyCB,
      0);
    DPA_Destroy(0);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180003898  mov     [rsp-38h+arg_0], rbx
0x18000389d  mov     [rsp-38h+arg_10], r8
0x1800038a2  push    rbp
0x1800038a3  push    rsi
0x1800038a4  push    rdi
0x1800038a5  push    r12
0x1800038a7  push    r13
0x1800038a9  push    r14
0x1800038ab  push    r15
0x1800038ad  mov     rbp, rsp
0x1800038b0  sub     rsp, 40h
0x1800038b4  mov     r12, rdx
0x1800038b7  mov     r14, rcx
0x1800038ba  mov     ecx, 10h; cItemGrow
0x1800038bf  call    cs:g_pfn_DPA_Create
0x1800038c5  mov     rbx, rax
0x1800038c8  mov     [rbp+var_8], rax
0x1800038cc  test    rax, rax
0x1800038cf  jnz     short loc_1800038DB
0x1800038d1  mov     edi, 8007000Eh
0x1800038d6  jmp     loc_180003B07
0x1800038db  mov     [rbp+arg_18], 0
0x1800038e3  lea     r8, [rbp+arg_18]; struct SCHEMA_REGISTRATION_DATA **
0x1800038e7  lea     rdx, CACHEID_SystemSchema; struct _GUID *
0x1800038ee  lea     rcx, aWindowspropert; "WindowsPropertyDescriptions"
0x1800038f5  call    ?GenerateWithSchemaId@SCHEMA_REGISTRATION_DATA@@SAJPEBGAEBU_GUID@@PEAPEAU1@@Z; SCHEMA_REGISTRATION_DATA::GenerateWithSchemaId(ushort const *,_GUID const &,SCHEMA_REGISTRATION_DATA * *)
0x1800038fa  mov     edi, eax
0x1800038fc  mov     rcx, [rbp+38h]; this
0x180003900  test    eax, eax
0x180003902  jns     short loc_18000391D
0x180003904  mov     r9d, eax; char *
0x180003907  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x18000390e  mov     edx, 102h; void *
0x180003913  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003918  jmp     loc_180003B07
0x18000391d  mov     r13, [rbp+arg_18]
0x180003921  lea     rdi, [r13+0A0h]
0x180003928  mov     rcx, rdi
0x18000392b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180003930  mov     qword ptr [rsp+40h+var_20], rdi; int
0x180003935  mov     esi, 1
0x18000393a  mov     r9d, esi; int
0x18000393d  mov     r8, [r13+10h]; unsigned __int16 *
0x180003941  mov     rdx, r13; struct SCHEMA_REGISTRATION_DATA *
0x180003944  mov     rcx, r14; this
0x180003947  call    ?_LoadOrBuildCachedSchema@CSchemaCache@@AEAAJPEBUSCHEMA_REGISTRATION_DATA@@PEBGHPEAPEAVCSchemaData@@@Z; CSchemaCache::_LoadOrBuildCachedSchema(SCHEMA_REGISTRATION_DATA const *,ushort const *,int,CSchemaData * *)
0x18000394c  mov     edi, eax
0x18000394e  mov     rcx, [rbp+38h]
0x180003952  test    eax, eax
0x180003954  jns     short loc_180003960
0x180003956  mov     r9d, eax
0x180003959  mov     edx, 107h
0x18000395e  jmp     short loc_180003994
0x180003960  lea     r8, Name; "GeneratingSchemaGlobalMapping"
0x180003967  xor     edx, edx; bInitialOwner
0x180003969  xor     ecx, ecx; lpMutexAttributes
0x18000396b  call    cs:__imp_CreateMutexW
0x180003971  mov     r15, rax
0x180003974  test    rax, rax
0x180003977  jz      short loc_18000397D
0x180003979  xor     edi, edi
0x18000397b  jmp     short loc_180003984
0x18000397d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003982  mov     edi, eax
0x180003984  mov     rcx, [rbp+38h]; this
0x180003988  test    edi, edi
0x18000398a  jns     short loc_1800039A5
0x18000398c  mov     r9d, edi; char *
0x18000398f  mov     edx, 10Ch; void *
0x180003994  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x18000399b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800039a0  jmp     loc_180003AF9
0x1800039a5  mov     edx, 1388h; dwMilliseconds
0x1800039aa  mov     rcx, r15; hHandle
0x1800039ad  call    cs:__imp_WaitForSingleObject
0x1800039b3  test    eax, eax
0x1800039b5  jz      short loc_1800039E6
0x1800039b7  cmp     eax, 80h
0x1800039bc  jz      short loc_1800039E6
0x1800039be  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800039c3  mov     edi, eax
0x1800039c5  mov     rcx, [rbp+38h]; this
0x1800039c9  test    eax, eax
0x1800039cb  jns     short loc_1800039E6
0x1800039cd  mov     r9d, eax; char *
0x1800039d0  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x1800039d7  mov     edx, 118h; void *
0x1800039dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800039e1  jmp     loc_180003AF0
0x1800039e6  mov     [rbp+var_10], esi
0x1800039e9  mov     dword ptr [rbp+arg_18], esi
0x1800039ec  lea     r9, [rbp+var_10]
0x1800039f0  lea     r8, [rbp+var_8]
0x1800039f4  xor     edx, edx
0x1800039f6  mov     rcx, r14
0x1800039f9  call    ?_EnumRegisteredSchemaFiles@CSchemaCache@@AEAAXHPEAV?$CDPARelease@USCHEMA_REGISTRATION_DATA@@V?$CTContainer_PolicyRelease@USCHEMA_REGISTRATION_DATA@@@@@@PEAH@Z; CSchemaCache::_EnumRegisteredSchemaFiles(int,CDPARelease<SCHEMA_REGISTRATION_DATA,CTContainer_PolicyRelease<SCHEMA_REGISTRATION_DATA>> *,int *)
0x1800039fe  mov     ecx, 28h ; '('; dwOS
0x180003a03  call    cs:__imp_IsOS
0x180003a09  test    eax, eax
0x180003a0b  jz      short loc_180003A22
0x180003a0d  lea     r9, [rbp+arg_18]
0x180003a11  lea     r8, [rbp+var_8]
0x180003a15  mov     edx, esi
0x180003a17  mov     rcx, r14
0x180003a1a  call    ?_EnumRegisteredSchemaFiles@CSchemaCache@@AEAAXHPEAV?$CDPARelease@USCHEMA_REGISTRATION_DATA@@V?$CTContainer_PolicyRelease@USCHEMA_REGISTRATION_DATA@@@@@@PEAH@Z; CSchemaCache::_EnumRegisteredSchemaFiles(int,CDPARelease<SCHEMA_REGISTRATION_DATA,CTContainer_PolicyRelease<SCHEMA_REGISTRATION_DATA>> *,int *)
0x180003a1f  mov     esi, dword ptr [rbp+arg_18]
0x180003a22  mov     [rbp+arg_18], 0
0x180003a2a  lea     r8, [rbp+arg_18]
0x180003a2e  mov     rcx, [r14+10h]; punk
0x180003a32  call    ?Create@?$CCacheFileBuilder@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingBuilder@@@@SAJPEAUIMemoryMappedCacheMgr@@AEBU_GUID@@PEAPEAVCGlobalMappingBuilder@@@Z; CCacheFileBuilder<GLOBAL_MAPPING_HEADER,CGlobalMappingBuilder>::Create(IMemoryMappedCacheMgr *,_GUID const &,CGlobalMappingBuilder * *)
0x180003a37  mov     edi, eax
0x180003a39  mov     rcx, [rbp+38h]; this
0x180003a3d  test    eax, eax
0x180003a3f  jns     short loc_180003A5A
0x180003a41  mov     r9d, eax; char *
0x180003a44  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180003a4b  mov     edx, 12Dh; void *
0x180003a50  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003a55  jmp     loc_180003AE3
0x180003a5a  lea     r8, [rbp+var_8]
0x180003a5e  mov     rdx, r13; struct _GUID *
0x180003a61  mov     rbx, [rbp+arg_18]
0x180003a65  mov     rcx, rbx; this
0x180003a68  call    ?BuildGlobalMapping@CGlobalMappingBuilder@@QEAAJPEAUSCHEMA_REGISTRATION_DATA@@AEBV?$CDPARelease@USCHEMA_REGISTRATION_DATA@@V?$CTContainer_PolicyRelease@USCHEMA_REGISTRATION_DATA@@@@@@@Z; CGlobalMappingBuilder::BuildGlobalMapping(SCHEMA_REGISTRATION_DATA *,CDPARelease<SCHEMA_REGISTRATION_DATA,CTContainer_PolicyRelease<SCHEMA_REGISTRATION_DATA>> const &)
0x180003a6d  mov     edi, eax
0x180003a6f  mov     rcx, [rbp+38h]; this
0x180003a73  test    eax, eax
0x180003a75  jns     short loc_180003A8D
0x180003a77  mov     edx, 130h; void *
0x180003a7c  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x180003a83  mov     r9d, eax; char *
0x180003a86  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003a8b  jmp     short loc_180003ACB
0x180003a8d  cmp     [rbp+var_10], 0
0x180003a91  jz      short loc_180003A9F
0x180003a93  test    esi, esi
0x180003a95  jz      short loc_180003A9F
0x180003a97  mov     r8d, 1
0x180003a9d  jmp     short loc_180003AA2
0x180003a9f  xor     r8d, r8d
0x180003aa2  mov     rdx, [rbp+arg_10]
0x180003aa6  mov     rcx, rbx
0x180003aa9  call    ?Commit@?$CCacheFileBuilder@UGLOBAL_MAPPING_HEADER@@VCGlobalMappingBuilder@@@@QEAAJPEAPEAUIMemoryMappedCache@@H@Z; CCacheFileBuilder<GLOBAL_MAPPING_HEADER,CGlobalMappingBuilder>::Commit(IMemoryMappedCache * *,int)
0x180003aae  mov     edi, eax
0x180003ab0  mov     rcx, [rbp+38h]
0x180003ab4  test    eax, eax
0x180003ab6  jns     short loc_180003ABF
0x180003ab8  mov     edx, 133h
0x180003abd  jmp     short loc_180003A7C
0x180003abf  test    r12, r12
0x180003ac2  jz      short loc_180003ACB
0x180003ac4  mov     eax, [rbx+40h]
0x180003ac7  mov     [r12], eax
0x180003acb  test    rbx, rbx
0x180003ace  jz      short loc_180003AE3
0x180003ad0  mov     rax, [rbx]
0x180003ad3  mov     edx, 1
0x180003ad8  mov     rcx, rbx
0x180003adb  mov     rax, [rax]
0x180003ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae3  mov     rcx, r15; hMutex
0x180003ae6  call    cs:__imp_ReleaseMutex
0x180003aec  mov     rbx, [rbp+var_8]
0x180003af0  mov     rcx, r15; hObject
0x180003af3  call    cs:__imp_CloseHandle
0x180003af9  test    r13, r13
0x180003afc  jz      short loc_180003B07
0x180003afe  mov     rcx, r13; this
0x180003b01  call    ??_GSCHEMA_REGISTRATION_DATA@@QEAAPEAXI@Z; SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(uint)
0x180003b06  nop
0x180003b07  test    rbx, rbx
0x180003b0a  jz      short loc_180003B27
0x180003b0c  xor     r8d, r8d; pData
0x180003b0f  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@USCHEMA_REGISTRATION_DATA@@V?$CTContainer_PolicyRelease@USCHEMA_REGISTRATION_DATA@@@@@@CAHPEAUSCHEMA_REGISTRATION_DATA@@PEAX@Z; pfnCB
0x180003b16  mov     rcx, rbx; hdpa
0x180003b19  call    cs:g_pfn_DPA_DestroyCallback
0x180003b1f  xor     ecx, ecx; hdpa
0x180003b21  call    cs:__imp_DPA_Destroy
0x180003b27  mov     eax, edi
0x180003b29  mov     rbx, [rsp+40h+arg_0]
0x180003b31  add     rsp, 40h
0x180003b35  pop     r15
0x180003b37  pop     r14
0x180003b39  pop     r13
0x180003b3b  pop     r12
0x180003b3d  pop     rdi
0x180003b3e  pop     rsi
0x180003b3f  pop     rbp
0x180003b40  retn
```
