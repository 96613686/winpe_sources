# SREffectRenderPassDx12::CDSRProvider::CacheExtensionDllPath(void)

- ea: `0x1800689fc`
- end: `0x180068c42`
- name: `?CacheExtensionDllPath@CDSRProvider@SREffectRenderPassDx12@@IEAAXXZ`
- size: `582`
- prototype: `void __fastcall(SREffectRenderPassDx12::CDSRProvider *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180068718`

## callees

- `0x18000c6b0`
- `0x1800405a4`
- `0x1800689fc`
- `0x180068c48`
- `0x180068fc0`
- `0x18006989c`
- `0x180069930`
- `0x180073794`
- `0x180075fa0`
- `0x1800b480c`
- `0x1800b981c`
- `0x1800bd280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068bc2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180068bb2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180068bb2`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x180068ab7`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableA` at `0x180068ab7`
- `api-ms-win-core-kernel32-legacy-ansi-l1-1-0!SetDllDirectoryA` at `0x180068b77`
- `api-ms-win-core-kernel32-legacy-ansi-l1-1-0!SetDllDirectoryA` at `0x180068b77`

## string_xrefs

- `0x180068b94`: `SuperResExt.dll`
- `0x180068c08`: `SuperResExt.dll`
- `0x180068b63`: `LoadFromPath override: %s`
- `0x180068bf1`: `onecoreuap\windows\directx\dxg\common\upscaleeffect\lib\sreffectdx12.cpp`
- `0x180068bd4`: `Failed to load extension DLL or dependencies`
- `0x180068bea`: `Failed to load the extension DLL or dependencies`
- `0x180068ab0`: `SREXTPATH`
- `0x180068b26`: `Ext path env var not found, err 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SREffectRenderPassDx12::CDSRProvider::CacheExtensionDllPath(struct PACKAGE_VERSION *this)
{
  struct PACKAGE_VERSION *v2; // rbx
  unsigned int v3; // r8d
  CModule *v4; // rcx
  bool v5; // r9
  const CHAR *v6; // rcx
  __int64 v7; // r8
  struct PACKAGE_VERSION *Version; // rcx
  DWORD LastError; // eax
  const char *v10; // rdx
  void *v11; // rdx
  unsigned int v12; // r8d
  const char *v13; // r9
  const CHAR *v14; // rcx
  signed int v15; // eax
  CModule *v16; // rcx
  bool v17; // r9
  int v18; // [rsp+20h] [rbp-68h]
  __int64 v19; // [rsp+0h] [rbp-88h] BYREF
  char *LibraryA; // [rsp+20h] [rbp-68h] BYREF
  CHAR Buffer[64]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = this + 1;
  if ( !this[3].Version )
  {
    try
    {
      std::string::reserve();
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Log_Hr(retaddr, &v19, v3, (const char *)0x8007000ELL, v18);
      return;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_LoadFromPath>::__private_IsEnabled()
      && *(&g_AutoSRConfig + 10) )
    {
      if ( GetEnvironmentVariableA("SREXTPATH", Buffer, 0x40u) - 1 > 0x3E )
      {
        if ( *(&g_AutoSRConfig + 6) )
        {
          LastError = GetLastError();
          DebugPrint("Ext path env var not found, err 0x%x", LastError);
        }
        std::string::_Assign<char>(v2, "C:\\srext\\", 9);
      }
      else
      {
        v7 = -1;
        do
          ++v7;
        while ( Buffer[v7] );
        std::string::_Assign<char>(v2, Buffer, v7);
        if ( v2[3].Version <= 0xF )
          Version = v2;
        else
          Version = (struct PACKAGE_VERSION *)v2->Version;
        if ( *((_BYTE *)Version + v2[2].Version - 1) != 92 )
          std::string::_Append<char>(v2);
      }
      if ( *(&g_AutoSRConfig + 6) )
      {
        if ( v2[3].Version <= 0xF )
          v10 = (const char *)v2;
        else
          v10 = (const char *)v2->Version;
        DebugPrint("LoadFromPath override: %s", v10);
      }
    }
    else if ( (int)GetExtensionPackagePath(v2, this + 5) < 0 )
    {
      CModule::RecordJournalImpl(v4, 0x80070490, "Model package not found", v5);
      if ( *(&g_AutoSRConfig + 6) )
        DebugPrint("Model package not found");
    }
    if ( this[3].Version )
    {
      v6 = v2[3].Version <= 0xF ? (const CHAR *)v2 : (const CHAR *)v2->Version;
      if ( !SetDllDirectoryA(v6) )
        wil::details::in1diag3::_Log_GetLastError(retaddr, v11, v12, v13);
    }
    std::string::_Append<char>(v2);
    if ( v2[3].Version <= 0xF )
      v14 = (const CHAR *)v2;
    else
      v14 = (const CHAR *)v2->Version;
    LibraryA = (char *)LoadLibraryA(v14);
    if ( !LibraryA )
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      CModule::RecordJournalImpl(v16, v15, "Failed to load extension DLL or dependencies", v17);
      wil::details::in1diag3::Log_GetLastErrorMsg(
        retaddr,
        (void *)0x2D0,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\upscaleeffect\\lib\\sreffectdx12.cpp",
        "Failed to load the extension DLL or dependencies",
        LibraryA);
      std::string::_Assign<char>(v2, "SuperResExt.dll", 15);
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&LibraryA);
  }
}

```

## disassembly

```asm
0x1800689fc  mov     [rsp+arg_8], rbx
0x180068a01  push    rdi
0x180068a02  sub     rsp, 80h
0x180068a09  mov     rax, cs:__security_cookie
0x180068a10  xor     rax, rsp
0x180068a13  mov     [rsp+88h+var_18], rax
0x180068a18  mov     rdi, rcx
0x180068a1b  lea     rbx, [rcx+8]
0x180068a1f  cmp     qword ptr [rbx+10h], 0
0x180068a24  jnz     loc_180068C24
0x180068a2a  mov     edx, 104h
0x180068a2f  mov     rcx, rbx
0x180068a32  call    ?reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::reserve(unsigned __int64)
0x180068a37  nop
0x180068a38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_LoadFromPath@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_LoadFromPath@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_LoadFromPath> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_LoadFromPath>::GetImpl(void)'::`2'::impl
0x180068a3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_LoadFromPath@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_LoadFromPath>::__private_IsEnabled(void)
0x180068a44  test    al, al
0x180068a46  jz      short loc_180068A51
0x180068a48  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+0Ah, 0; AutoSRConfig g_AutoSRConfig
0x180068a4f  jnz     short loc_180068AA5
0x180068a51  lea     rdx, [rdi+28h]; struct PACKAGE_VERSION *
0x180068a55  mov     rcx, rbx; Src
0x180068a58  call    ?GetExtensionPackagePath@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAUPACKAGE_VERSION@@@Z; GetExtensionPackagePath(std::string &,PACKAGE_VERSION &)
0x180068a5d  test    eax, eax
0x180068a5f  jns     short loc_180068A87
0x180068a61  lea     r8, aModelPackageNo; "Model package not found"
0x180068a68  mov     edx, 80070490h; unsigned int
0x180068a6d  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180068a72  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x180068a79  jz      short loc_180068A87
0x180068a7b  lea     rcx, aModelPackageNo; "Model package not found"
0x180068a82  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x180068a87  cmp     qword ptr [rdi+18h], 0
0x180068a8c  jz      loc_180068B8E
0x180068a92  cmp     qword ptr [rbx+18h], 0Fh
0x180068a97  jbe     loc_180068B74
0x180068a9d  mov     rcx, [rbx]
0x180068aa0  jmp     loc_180068B77
0x180068aa5  mov     r8d, 40h ; '@'; nSize
0x180068aab  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x180068ab0  lea     rcx, aSrextpath; "SREXTPATH"
0x180068ab7  call    cs:__imp_GetEnvironmentVariableA
0x180068abd  dec     eax
0x180068abf  cmp     eax, 3Eh ; '>'
0x180068ac2  ja      short loc_180068B15
0x180068ac4  lea     rax, [rsp+88h+Buffer]
0x180068ac9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180068acd  inc     r8
0x180068ad0  cmp     byte ptr [rax+r8], 0
0x180068ad5  jnz     short loc_180068ACD
0x180068ad7  lea     rdx, [rsp+88h+Buffer]
0x180068adc  mov     rcx, rbx
0x180068adf  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180068ae4  cmp     qword ptr [rbx+18h], 0Fh
0x180068ae9  jbe     short loc_180068AF0
0x180068aeb  mov     rcx, [rbx]
0x180068aee  jmp     short loc_180068AF3
0x180068af0  mov     rcx, rbx
0x180068af3  mov     rax, [rbx+10h]
0x180068af7  cmp     byte ptr [rax+rcx-1], 5Ch ; '\'
0x180068afc  jz      short loc_180068B47
0x180068afe  mov     r8d, 1
0x180068b04  lea     rdx, asc_1800DD008; "\\"
0x180068b0b  mov     rcx, rbx; Src
0x180068b0e  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180068b13  jmp     short loc_180068B47
0x180068b15  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x180068b1c  jz      short loc_180068B32
0x180068b1e  call    cs:__imp_GetLastError
0x180068b24  mov     edx, eax
0x180068b26  lea     rcx, aExtPathEnvVarN; "Ext path env var not found, err 0x%x"
0x180068b2d  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x180068b32  mov     r8d, 9
0x180068b38  lea     rdx, aCSrext; "C:\\srext\\"
0x180068b3f  mov     rcx, rbx
0x180068b42  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180068b47  cmp     byte ptr cs:?g_AutoSRConfig@@3UAutoSRConfig@@A+6, 0; AutoSRConfig g_AutoSRConfig
0x180068b4e  jz      loc_180068A87
0x180068b54  cmp     qword ptr [rbx+18h], 0Fh
0x180068b59  jbe     short loc_180068B60
0x180068b5b  mov     rdx, [rbx]
0x180068b5e  jmp     short loc_180068B63
0x180068b60  mov     rdx, rbx
0x180068b63  lea     rcx, aLoadfrompathOv; "LoadFromPath override: %s"
0x180068b6a  call    ?DebugPrint@@YAXPEBDZZ; DebugPrint(char const *,...)
0x180068b6f  jmp     loc_180068A87
0x180068b74  mov     rcx, rbx; lpPathName
0x180068b77  call    cs:__imp_SetDllDirectoryA
0x180068b7d  mov     rcx, [rsp+88h]; this
0x180068b85  test    eax, eax
0x180068b87  jnz     short loc_180068B8E
0x180068b89  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180068b8e  mov     r8d, 0Fh
0x180068b94  lea     rdx, aSuperresextDll; "SuperResExt.dll"
0x180068b9b  mov     rcx, rbx; Src
0x180068b9e  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180068ba3  cmp     qword ptr [rbx+18h], 0Fh
0x180068ba8  jbe     short loc_180068BAF
0x180068baa  mov     rcx, [rbx]
0x180068bad  jmp     short loc_180068BB2
0x180068baf  mov     rcx, rbx; lpLibFileName
0x180068bb2  call    cs:__imp_LoadLibraryA
0x180068bb8  mov     [rsp+88h+var_68], rax; char *
0x180068bbd  test    rax, rax
0x180068bc0  jnz     short loc_180068C18
0x180068bc2  call    cs:__imp_GetLastError
0x180068bc8  test    eax, eax
0x180068bca  jle     short loc_180068BD4
0x180068bcc  movzx   eax, ax
0x180068bcf  or      eax, 80070000h
0x180068bd4  lea     r8, aFailedToLoadEx; "Failed to load extension DLL or depende"...
0x180068bdb  mov     edx, eax; unsigned int
0x180068bdd  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180068be2  mov     rcx, [rsp+88h]; this
0x180068bea  lea     r9, aFailedToLoadTh; "Failed to load the extension DLL or dep"...
0x180068bf1  lea     r8, aOnecoreuapWind_15; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180068bf8  mov     edx, 2D0h; void *
0x180068bfd  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180068c02  mov     r8d, 0Fh
0x180068c08  lea     rdx, aSuperresextDll; "SuperResExt.dll"
0x180068c0f  mov     rcx, rbx
0x180068c12  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180068c17  nop
0x180068c18  lea     rcx, [rsp+88h+var_68]
0x180068c1d  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180068c22  jmp     short $+2
0x180068c24  mov     rcx, [rsp+88h+var_18]
0x180068c29  xor     rcx, rsp; StackCookie
0x180068c2c  call    __security_check_cookie
0x180068c31  mov     rbx, [rsp+88h+arg_8]
0x180068c39  add     rsp, 80h
0x180068c40  pop     rdi
0x180068c41  retn
```
