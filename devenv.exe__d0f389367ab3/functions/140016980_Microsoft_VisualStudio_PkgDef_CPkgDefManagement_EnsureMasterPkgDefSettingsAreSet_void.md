# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::EnsureMasterPkgDefSettingsAreSet(void)

- ea: `0x140016980`
- end: `0x140016be9`
- name: `?EnsureMasterPkgDefSettingsAreSet@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJXZ`
- size: `617`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140016668`

## callees

- `0x140002c10`
- `0x140002f00`
- `0x140004950`
- `0x140007740`
- `0x1400095f4`
- `0x140016980`
- `0x140016bec`
- `0x140018048`
- `0x14001c440`
- `0x140029a18`
- `0x140033ab0`
- `0x1400464b0`

## import_xrefs

- `VCRUNTIME140!wcsstr` at `0x140016aac`
- `VCRUNTIME140!wcsstr` at `0x140016aac`

## string_xrefs

- `0x140016b0c`: `PkgDefSearchPath`
- `0x140016b21`: `ImageManifestSearchPath`
- `0x140016b32`: `ApplicationExtensionsFolder`
- `0x140016b71`: `MergeRegistry`
- `0x1400169f0`: `$RootFolder$Common7\IDE\Extensions`
- `0x140016a15`: `$ApplicationExtensionsFolder$;$RootFolder$Common7\IDE\CommonExtensions`
- `0x140016ac7`: `PkgDef configuration error. ApplicationExtensionsFolder omitted from PkgDefSearchPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::EnsureMasterPkgDefSettingsAreSet(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this)
{
  unsigned int v2; // edi
  __int64 result; // rax
  const wchar_t **v4; // r14
  const wchar_t **v5; // rsi
  char *v6; // rcx
  char *v7; // rax
  char *v8; // rcx
  char *v9; // rcx
  char *v10; // rax
  char *v11; // rcx
  wchar_t *v12; // rax
  struct ATL::IAtlStringMgr *Instance; // rax
  unsigned __int16 *v14; // rbx
  int v15; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v16; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  CLogger::LogInfo(L"Double-checking master pkgdef file", 0, 0);
  if ( (Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ShouldMasterPkgDefBeLoaded(this)
     || (int)Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ReadConfigInitializationFromRegistry(this) < 0)
    && (result = Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ScanMasterPkgDefForInitializationFields(this),
        v2 = result,
        (int)result < 0) )
  {
    _mm_lfence();
  }
  else
  {
    v4 = (const wchar_t **)((char *)this + 160);
    if ( !*(_DWORD *)(*((_QWORD *)this + 20) - 16LL) )
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 160, L"$RootFolder$Common7\\IDE\\Extensions");
    v5 = (const wchar_t **)((char *)this + 144);
    if ( !*(_DWORD *)(*((_QWORD *)this + 18) - 16LL) )
      ATL::CSimpleStringT<unsigned short,0>::SetString(
        (char *)this + 144,
        L"$ApplicationExtensionsFolder$;$RootFolder$Common7\\IDE\\CommonExtensions");
    v6 = (char *)*((_QWORD *)this + 2);
    if ( *(_DWORD *)(*((_QWORD *)this + 13) - 16LL) )
    {
      v8 = v6 + 112;
      v7 = (char *)this + 104;
    }
    else
    {
      v7 = (char *)(*(__int64 (__fastcall **)(char *, char *))(*(_QWORD *)v6 + 48LL))(v6, (char *)this + 80);
      v8 = (char *)this + 104;
    }
    ATL::CSimpleStringT<unsigned short,0>::operator=(v8, v7);
    v9 = (char *)*((_QWORD *)this + 2);
    if ( *(_DWORD *)(*((_QWORD *)this + 12) - 16LL) )
    {
      v11 = v9 + 104;
      v10 = (char *)this + 96;
    }
    else
    {
      v10 = (char *)(*(__int64 (__fastcall **)(char *, char *, char *))(*(_QWORD *)v9 + 40LL))(
                      v9,
                      (char *)this + 96,
                      (char *)this + 80);
      v11 = (char *)this + 96;
    }
    ATL::CSimpleStringT<unsigned short,0>::operator=(v11, v10);
    Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ExpandTokens(this);
    if ( CLogger::ms_bLoggingOn )
    {
      if ( !*v4 || *((int *)*v5 - 4) < 0 || (v12 = wcsstr(*v5, *v4)) == 0 || (unsigned int)(v12 - *v5) == -1 )
        CLogger::LogWarn(L"PkgDef configuration error. ApplicationExtensionsFolder omitted from PkgDefSearchPath", 0, 0);
      CLogger::LogInfo(L"PkgDefManagement initialized", 0, 0);
      CLogger::LogInfo(L"RootFolder", 0, *((const unsigned __int16 **)this + 12));
      CLogger::LogInfo(L"ShellFolder", 0, *((const unsigned __int16 **)this + 13));
      CLogger::LogInfo(L"PkgDefSearchPath", 0, *v5);
      CLogger::LogInfo(L"ImageManifestSearchPath", 0, *((const unsigned __int16 **)this + 22));
      CLogger::LogInfo(L"ApplicationExtensionsFolder", 0, *v4);
      Instance = ATL::CAtlStringMgr::GetInstance();
      if ( !Instance )
        ATL::AtlThrowImpl(-2147467259);
      v16 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                               + 24);
      v15 = *((_DWORD *)this + 17);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v16,
        L"\"%s\" = dword:%d, \"%s\" = dword:%d",
        L"ZeroImpact",
        (*((_DWORD *)this + 15) >> 4) & 1,
        L"MergeRegistry",
        v15);
      v14 = v16;
      CLogger::LogInfo(v16, 0, 0);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
      }
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x140016980  mov     [rsp+arg_0], rbx
0x140016985  mov     [rsp+arg_10], rbp
0x14001698a  push    rsi
0x14001698b  push    rdi
0x14001698c  push    r12
0x14001698e  push    r14
0x140016990  push    r15
0x140016992  sub     rsp, 30h
0x140016996  mov     rbx, rcx
0x140016999  xor     edi, edi
0x14001699b  xor     r8d, r8d; unsigned __int16 *
0x14001699e  xor     edx, edx; int
0x1400169a0  lea     rcx, aDoubleChecking; "Double-checking master pkgdef file"
0x1400169a7  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x1400169ac  mov     rcx, rbx; this
0x1400169af  call    ?ShouldMasterPkgDefBeLoaded@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAA_NXZ; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ShouldMasterPkgDefBeLoaded(void)
0x1400169b4  test    al, al
0x1400169b6  jnz     short loc_1400169C4
0x1400169b8  mov     rcx, rbx; this
0x1400169bb  call    ?ReadConfigInitializationFromRegistry@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJXZ; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ReadConfigInitializationFromRegistry(void)
0x1400169c0  test    eax, eax
0x1400169c2  jns     short loc_1400169DA
0x1400169c4  mov     rcx, rbx; this
0x1400169c7  call    ?ScanMasterPkgDefForInitializationFields@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJXZ; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ScanMasterPkgDefForInitializationFields(void)
0x1400169cc  mov     edi, eax
0x1400169ce  test    eax, eax
0x1400169d0  jns     short loc_1400169DA
0x1400169d2  lfence
0x1400169d5  jmp     loc_140016BC7
0x1400169da  lea     r14, [rbx+0A0h]
0x1400169e1  mov     rax, [r14]
0x1400169e4  cmp     dword ptr [rax-10h], 0
0x1400169e8  jnz     short loc_1400169FF
0x1400169ea  mov     r8d, 22h ; '"'
0x1400169f0  lea     rdx, aRootfolderComm; "$RootFolder$Common7\\IDE\\Extensions"
0x1400169f7  mov     rcx, r14
0x1400169fa  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400169ff  lea     rsi, [rbx+90h]
0x140016a06  mov     rax, [rsi]
0x140016a09  cmp     dword ptr [rax-10h], 0
0x140016a0d  jnz     short loc_140016A24
0x140016a0f  mov     r8d, 46h ; 'F'
0x140016a15  lea     rdx, aApplicationext_0; "$ApplicationExtensionsFolder$;$RootFold"...
0x140016a1c  mov     rcx, rsi
0x140016a1f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140016a24  lea     rbp, [rbx+68h]
0x140016a28  mov     rcx, [rbx+10h]
0x140016a2c  mov     rax, [rbp+0]
0x140016a30  cmp     dword ptr [rax-10h], 0
0x140016a34  jnz     short loc_140016A45
0x140016a36  mov     rax, [rcx]
0x140016a39  lea     rdx, [rbx+50h]
0x140016a3d  call    qword ptr [rax+30h]
0x140016a40  mov     rcx, rbp
0x140016a43  jmp     short loc_140016A4C
0x140016a45  add     rcx, 70h ; 'p'
0x140016a49  mov     rax, rbp
0x140016a4c  mov     rdx, rax
0x140016a4f  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140016a54  lea     r15, [rbx+60h]
0x140016a58  mov     rcx, [rbx+10h]
0x140016a5c  mov     rax, [r15]
0x140016a5f  cmp     dword ptr [rax-10h], 0
0x140016a63  jnz     short loc_140016A77
0x140016a65  mov     rax, [rcx]
0x140016a68  lea     r8, [rbx+50h]
0x140016a6c  mov     rdx, r15
0x140016a6f  call    qword ptr [rax+28h]
0x140016a72  mov     rcx, r15
0x140016a75  jmp     short loc_140016A7E
0x140016a77  add     rcx, 68h ; 'h'
0x140016a7b  mov     rax, r15
0x140016a7e  mov     rdx, rax
0x140016a81  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140016a86  mov     rcx, rbx; this
0x140016a89  call    ?ExpandTokens@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAXXZ; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ExpandTokens(void)
0x140016a8e  cmp     cs:?ms_bLoggingOn@CLogger@@0_NA, 0; bool CLogger::ms_bLoggingOn
0x140016a95  jz      loc_140016BC5
0x140016a9b  mov     rdx, [r14]; SubStr
0x140016a9e  test    rdx, rdx
0x140016aa1  jz      short loc_140016AC2
0x140016aa3  mov     rcx, [rsi]; Str
0x140016aa6  cmp     dword ptr [rcx-10h], 0
0x140016aaa  jl      short loc_140016AC2
0x140016aac  call    cs:__imp_wcsstr
0x140016ab2  test    rax, rax
0x140016ab5  jz      short loc_140016AC2
0x140016ab7  sub     rax, [rsi]
0x140016aba  sar     rax, 1
0x140016abd  cmp     eax, 0FFFFFFFFh
0x140016ac0  jnz     short loc_140016AD3
0x140016ac2  xor     r8d, r8d; unsigned __int16 *
0x140016ac5  xor     edx, edx; int
0x140016ac7  lea     rcx, aPkgdefConfigur_0; "PkgDef configuration error. Application"...
0x140016ace  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x140016ad3  xor     r8d, r8d; unsigned __int16 *
0x140016ad6  xor     edx, edx; int
0x140016ad8  lea     rcx, aPkgdefmanageme_2; "PkgDefManagement initialized"
0x140016adf  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140016ae4  mov     r8, [r15]; unsigned __int16 *
0x140016ae7  xor     edx, edx; int
0x140016ae9  lea     rcx, aRootfolder_0; "RootFolder"
0x140016af0  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140016af5  mov     r8, [rbp+0]; unsigned __int16 *
0x140016af9  xor     edx, edx; int
0x140016afb  lea     rcx, aShellfolder; "ShellFolder"
0x140016b02  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140016b07  mov     r8, [rsi]; unsigned __int16 *
0x140016b0a  xor     edx, edx; int
0x140016b0c  lea     rcx, aPkgdefsearchpa; "PkgDefSearchPath"
0x140016b13  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140016b18  mov     r8, [rbx+0B0h]; unsigned __int16 *
0x140016b1f  xor     edx, edx; int
0x140016b21  lea     rcx, aImagemanifests; "ImageManifestSearchPath"
0x140016b28  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140016b2d  mov     r8, [r14]; unsigned __int16 *
0x140016b30  xor     edx, edx; int
0x140016b32  lea     rcx, aApplicationext; "ApplicationExtensionsFolder"
0x140016b39  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140016b3e  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140016b43  mov     rcx, rax
0x140016b46  test    rax, rax
0x140016b49  jz      loc_140016BDE
0x140016b4f  mov     rax, [rax]
0x140016b52  call    qword ptr [rax+18h]
0x140016b55  add     rax, 18h
0x140016b59  mov     [rsp+58h+arg_8], rax
0x140016b5e  mov     r9d, [rbx+3Ch]
0x140016b62  shr     r9d, 4
0x140016b66  and     r9d, 1
0x140016b6a  mov     eax, [rbx+44h]
0x140016b6d  mov     [rsp+58h+var_30], eax
0x140016b71  lea     rax, aMergeregistry; "MergeRegistry"
0x140016b78  mov     [rsp+58h+var_38], rax
0x140016b7d  lea     r8, aZeroimpact; "ZeroImpact"
0x140016b84  lea     rdx, aSDwordDSDwordD; "\"%s\" = dword:%d, \"%s\" = dword:%d"
0x140016b8b  lea     rcx, [rsp+58h+arg_8]
0x140016b90  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x140016b95  xor     r8d, r8d; unsigned __int16 *
0x140016b98  xor     edx, edx; int
0x140016b9a  mov     rbx, [rsp+58h+arg_8]
0x140016b9f  mov     rcx, rbx; unsigned __int16 *
0x140016ba2  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x140016ba7  nop
0x140016ba8  lea     rdx, [rbx-18h]
0x140016bac  or      eax, 0FFFFFFFFh
0x140016baf  lock xadd [rdx+10h], eax
0x140016bb4  sub     eax, 1
0x140016bb7  jg      short loc_140016BC5
0x140016bb9  lfence
0x140016bbc  mov     rcx, [rdx]
0x140016bbf  mov     rax, [rcx]
0x140016bc2  call    qword ptr [rax+8]
0x140016bc5  mov     eax, edi
0x140016bc7  mov     rbx, [rsp+58h+arg_0]
0x140016bcc  mov     rbp, [rsp+58h+arg_10]
0x140016bd1  add     rsp, 30h
0x140016bd5  pop     r15
0x140016bd7  pop     r14
0x140016bd9  pop     r12
0x140016bdb  pop     rdi
0x140016bdc  pop     rsi
0x140016bdd  retn
0x140016bde  mov     ecx, 80004005h; int
0x140016be3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
