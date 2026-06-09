# CSchemaCache::_BuildCacheFromXML(SCHEMA_REGISTRATION_DATA const *,ushort const *,int,int *,IMemoryMappedCache * *)

- ea: `0x18006d3e0`
- end: `0x18006d58a`
- name: `?_BuildCacheFromXML@CSchemaCache@@AEAAJPEBUSCHEMA_REGISTRATION_DATA@@PEBGHPEAHPEAPEAUIMemoryMappedCache@@@Z`
- size: `426`
- prototype: `int(CSchemaCache *__hidden this, const struct SCHEMA_REGISTRATION_DATA *, const unsigned __int16 *, int, int *, struct IMemoryMappedCache **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003b48`
- `0x180091974`

## callees

- `0x180008814`
- `0x18001a3fc`
- `0x18006d3e0`
- `0x18006d590`
- `0x18006dc00`
- `0x18006ed20`
- `0x18009011c`
- `0x180091cd0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18006d4b2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18006d4b2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18006d4bf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18006d4bf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18006d4a2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18006d4a2`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18006d4dc`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18006d4dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSchemaCache::_BuildCacheFromXML(
        IUnknown **this,
        const struct SCHEMA_REGISTRATION_DATA *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        int *a5,
        struct IMemoryMappedCache **a6)
{
  HINSTANCE v10; // rdx
  CSchemaCache *v11; // rcx
  HRESULT v12; // ebx
  int v13; // r8d
  const unsigned __int16 *v14; // r9
  __int64 v15; // rax
  IStream *v16; // rdi
  const WCHAR *ExtensionW; // rax
  CSchemaCache *v18; // rcx
  IStream *ppstm[2]; // [rsp+30h] [rbp-58h] BYREF

  if ( (byte_1800F1382 & 0x10) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)ShellTraceId_PropertySchema_SaveAsBinaryForm_Start,
      (_DWORD)a3,
      1,
      (__int64)ppstm);
  ppstm[0] = 0;
  v12 = CCacheFileBuilder<SCHEMA_HEADER,CSchemaBuilder>::Create(this[2]);
  if ( v12 >= 0 )
  {
    v15 = *(_QWORD *)a2 - *(_QWORD *)&CACHEID_SystemSchema.Data1;
    if ( *(_QWORD *)a2 == *(_QWORD *)&CACHEID_SystemSchema.Data1 )
      v15 = *((_QWORD *)a2 + 1) - *(_QWORD *)CACHEID_SystemSchema.Data4;
    v16 = ppstm[0];
    if ( v15 )
    {
      v12 = -2147024809;
      ExtensionW = PathFindExtensionW(a3);
      if ( StrCmpICW(L".propdesc", ExtensionW) || !PathFileExistsW(a3) )
      {
LABEL_17:
        if ( v16 )
          (**(void (__fastcall ***)(IStream *, __int64))v16)(v16, 1);
        goto LABEL_19;
      }
      ppstm[0] = 0;
      v12 = SHCreateStreamOnFileW(a3, 0, ppstm);
      if ( v12 >= 0 )
        v12 = CSchemaCache::_AddStreamToPropertyCache(v18, ppstm[0], a2, v16, 0);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppstm);
    }
    else
    {
      v12 = CSchemaCache::_AddResourceToPropertyCache(v11, v10, a3, v14, a2, ppstm[0]);
    }
    if ( v12 >= 0 )
    {
      v12 = CCacheFileBuilder<SCHEMA_HEADER,CSchemaBuilder>::Commit(v16, a6, a4);
      if ( v12 >= 0 )
      {
        if ( a5 )
          *a5 = *((_DWORD *)v16 + 16);
      }
    }
    goto LABEL_17;
  }
LABEL_19:
  if ( (byte_1800F1382 & 0x10) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)v11,
      (unsigned int)ShellTraceId_PropertySchema_SaveAsBinaryForm_Stop,
      v13,
      1,
      (__int64)ppstm);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006d3e0  push    rbx
0x18006d3e2  push    rbp
0x18006d3e3  push    rsi
0x18006d3e4  push    rdi
0x18006d3e5  push    r12
0x18006d3e7  push    r14
0x18006d3e9  push    r15
0x18006d3eb  sub     rsp, 50h
0x18006d3ef  mov     rax, cs:__security_cookie
0x18006d3f6  xor     rax, rsp
0x18006d3f9  mov     [rsp+88h+var_48], rax
0x18006d3fe  mov     r15d, r9d
0x18006d401  mov     rbp, r8
0x18006d404  mov     rsi, rdx
0x18006d407  mov     rbx, rcx
0x18006d40a  mov     r14, [rsp+88h+arg_20]
0x18006d412  mov     r12, [rsp+88h+arg_28]
0x18006d41a  test    cs:byte_1800F1382, 10h
0x18006d421  jz      short loc_18006D43F
0x18006d423  lea     rax, [rsp+88h+ppstm]
0x18006d428  mov     [rsp+88h+var_68], rax
0x18006d42d  mov     r9d, 1
0x18006d433  lea     rdx, ShellTraceId_PropertySchema_SaveAsBinaryForm_Start
0x18006d43a  call    McGenEventWrite_EtwEventWriteTransfer
0x18006d43f  mov     [rsp+88h+ppstm], 0
0x18006d448  lea     r8, [rsp+88h+ppstm]
0x18006d44d  mov     rdx, rsi
0x18006d450  mov     rcx, [rbx+10h]; punk
0x18006d454  call    ?Create@?$CCacheFileBuilder@USCHEMA_HEADER@@VCSchemaBuilder@@@@SAJPEAUIMemoryMappedCacheMgr@@AEBU_GUID@@PEAPEAVCSchemaBuilder@@@Z; CCacheFileBuilder<SCHEMA_HEADER,CSchemaBuilder>::Create(IMemoryMappedCacheMgr *,_GUID const &,CSchemaBuilder * *)
0x18006d459  mov     ebx, eax
0x18006d45b  test    eax, eax
0x18006d45d  js      loc_18006D547
0x18006d463  mov     rax, [rsi]
0x18006d466  sub     rax, qword ptr cs:CACHEID_SystemSchema.Data1
0x18006d46d  jnz     short loc_18006D47A
0x18006d46f  mov     rax, [rsi+8]
0x18006d473  sub     rax, qword ptr cs:CACHEID_SystemSchema.Data4
0x18006d47a  mov     rdi, [rsp+88h+ppstm]
0x18006d47f  test    rax, rax
0x18006d482  jnz     short loc_18006D49A
0x18006d484  mov     [rsp+88h+var_60], rdi; struct CSchemaBuilder *
0x18006d489  mov     [rsp+88h+var_68], rsi; struct SCHEMA_REGISTRATION_DATA *
0x18006d48e  mov     r8, rbp; unsigned __int16 *
0x18006d491  call    ?_AddResourceToPropertyCache@CSchemaCache@@AEAAJPEAUHINSTANCE__@@PEBG1PEBUSCHEMA_REGISTRATION_DATA@@PEAVCSchemaBuilder@@@Z; CSchemaCache::_AddResourceToPropertyCache(HINSTANCE__ *,ushort const *,ushort const *,SCHEMA_REGISTRATION_DATA const *,CSchemaBuilder *)
0x18006d496  mov     ebx, eax
0x18006d498  jmp     short loc_18006D50C
0x18006d49a  mov     ebx, 80070057h
0x18006d49f  mov     rcx, rbp; pszPath
0x18006d4a2  call    cs:__imp_PathFindExtensionW
0x18006d4a8  mov     rdx, rax; pszStr2
0x18006d4ab  lea     rcx, pszStr1; ".propdesc"
0x18006d4b2  call    cs:__imp_StrCmpICW
0x18006d4b8  test    eax, eax
0x18006d4ba  jnz     short loc_18006D52F
0x18006d4bc  mov     rcx, rbp; pszPath
0x18006d4bf  call    cs:__imp_PathFileExistsW
0x18006d4c5  test    eax, eax
0x18006d4c7  jz      short loc_18006D52F
0x18006d4c9  mov     [rsp+88h+ppstm], 0
0x18006d4d2  lea     r8, [rsp+88h+ppstm]; ppstm
0x18006d4d7  xor     edx, edx; grfMode
0x18006d4d9  mov     rcx, rbp; pszFile
0x18006d4dc  call    cs:__imp_SHCreateStreamOnFileW
0x18006d4e2  mov     ebx, eax
0x18006d4e4  test    eax, eax
0x18006d4e6  js      short loc_18006D502
0x18006d4e8  mov     dword ptr [rsp+88h+var_68], 0; int
0x18006d4f0  mov     r9, rdi; struct CSchemaBuilder *
0x18006d4f3  mov     r8, rsi; struct SCHEMA_REGISTRATION_DATA *
0x18006d4f6  mov     rdx, [rsp+88h+ppstm]; struct IStream *
0x18006d4fb  call    ?_AddStreamToPropertyCache@CSchemaCache@@AEAAJPEAUIStream@@PEBUSCHEMA_REGISTRATION_DATA@@PEAVCSchemaBuilder@@H@Z; CSchemaCache::_AddStreamToPropertyCache(IStream *,SCHEMA_REGISTRATION_DATA const *,CSchemaBuilder *,int)
0x18006d500  mov     ebx, eax
0x18006d502  lea     rcx, [rsp+88h+ppstm]
0x18006d507  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006d50c  test    ebx, ebx
0x18006d50e  js      short loc_18006D52F
0x18006d510  mov     r8d, r15d
0x18006d513  mov     rdx, r12
0x18006d516  mov     rcx, rdi
0x18006d519  call    ?Commit@?$CCacheFileBuilder@USCHEMA_HEADER@@VCSchemaBuilder@@@@QEAAJPEAPEAUIMemoryMappedCache@@H@Z; CCacheFileBuilder<SCHEMA_HEADER,CSchemaBuilder>::Commit(IMemoryMappedCache * *,int)
0x18006d51e  mov     ebx, eax
0x18006d520  test    eax, eax
0x18006d522  js      short loc_18006D52F
0x18006d524  test    r14, r14
0x18006d527  jz      short loc_18006D52F
0x18006d529  mov     eax, [rdi+40h]
0x18006d52c  mov     [r14], eax
0x18006d52f  test    rdi, rdi
0x18006d532  jz      short loc_18006D547
0x18006d534  mov     rax, [rdi]
0x18006d537  mov     edx, 1
0x18006d53c  mov     rcx, rdi
0x18006d53f  mov     rax, [rax]
0x18006d542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d547  test    cs:byte_1800F1382, 10h
0x18006d54e  jz      short loc_18006D56C
0x18006d550  lea     rax, [rsp+88h+ppstm]
0x18006d555  mov     [rsp+88h+var_68], rax
0x18006d55a  mov     r9d, 1
0x18006d560  lea     rdx, ShellTraceId_PropertySchema_SaveAsBinaryForm_Stop
0x18006d567  call    McGenEventWrite_EtwEventWriteTransfer
0x18006d56c  mov     eax, ebx
0x18006d56e  mov     rcx, [rsp+88h+var_48]
0x18006d573  xor     rcx, rsp; StackCookie
0x18006d576  call    __security_check_cookie
0x18006d57b  add     rsp, 50h
0x18006d57f  pop     r15
0x18006d581  pop     r14
0x18006d583  pop     r12
0x18006d585  pop     rdi
0x18006d586  pop     rsi
0x18006d587  pop     rbp
0x18006d588  pop     rbx
0x18006d589  retn
```
