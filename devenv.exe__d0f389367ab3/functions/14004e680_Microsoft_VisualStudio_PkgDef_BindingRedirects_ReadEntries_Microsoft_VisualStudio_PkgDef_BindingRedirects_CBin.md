# Microsoft::VisualStudio::PkgDef::BindingRedirects::ReadEntries<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect>(HKEY__ *,ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14004e680`
- end: `0x14004e9b3`
- name: `??$ReadEntries@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@BindingRedirects@PkgDef@VisualStudio@Microsoft@@YAJPEAUHKEY__@@AEAV?$CAtlList@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@V?$CElementTraits@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@6@@Z`
- size: `819`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004df90`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002c10`
- `0x140002dd0`
- `0x140002e30`
- `0x140003070`
- `0x14001e390`
- `0x140030dd8`
- `0x140033ab0`
- `0x1400451e0`
- `0x140046514`
- `0x14004cfd8`
- `0x14004e680`
- `0x14004ef1c`
- `0x14005fb50`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004e931`
- `ADVAPI32!RegCloseKey` at `0x14004e944`
- `ADVAPI32!RegCloseKey` at `0x14004e979`
- `ADVAPI32!RegCloseKey` at `0x14004e931`
- `ADVAPI32!RegCloseKey` at `0x14004e944`
- `ADVAPI32!RegCloseKey` at `0x14004e979`
- `ADVAPI32!RegOpenKeyExW` at `0x14004e6f7`
- `ADVAPI32!RegOpenKeyExW` at `0x14004e803`
- `ADVAPI32!RegOpenKeyExW` at `0x14004e6f7`
- `ADVAPI32!RegOpenKeyExW` at `0x14004e803`
- `ADVAPI32!RegEnumKeyExW` at `0x14004e7a1`
- `ADVAPI32!RegEnumKeyExW` at `0x14004e7a1`
- `ole32!CLSIDFromString` at `0x14004e7b6`
- `ole32!CLSIDFromString` at `0x14004e7b6`

## string_xrefs

- `0x14004e8dd`: `Binding Redirect / CodeBase entry from configuration hive is malformed, ignoring.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VisualStudio::PkgDef::BindingRedirects::ReadEntries<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect>(
        HKEY hKey,
        __int64 a2,
        LPCWSTR *a3)
{
  int Values; // esi
  HKEY v7; // r15
  HKEY v8; // r14
  DWORD v9; // r12d
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v11; // rax
  WCHAR *v12; // rdi
  HKEY v13; // rbx
  LSTATUS v14; // eax
  HKEY v15; // rbx
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v18; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v20[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  LPCWSTR *v22; // [rsp+70h] [rbp-90h]
  __int128 v23; // [rsp+78h] [rbp-88h]
  __int64 v24; // [rsp+88h] [rbp-78h]
  DWORD cchName[4]; // [rsp+90h] [rbp-70h] BYREF
  void **v26; // [rsp+A0h] [rbp-60h] BYREF
  CLSID v27; // [rsp+A8h] [rbp-58h]
  int v28; // [rsp+F0h] [rbp-10h]
  int v29; // [rsp+F4h] [rbp-Ch]
  int v30; // [rsp+F8h] [rbp-8h]
  int v31; // [rsp+FCh] [rbp-4h]
  int v32; // [rsp+100h] [rbp+0h]
  int v33; // [rsp+104h] [rbp+4h]
  int v34; // [rsp+108h] [rbp+8h]
  int v35; // [rsp+10Ch] [rbp+Ch]
  struct _FILETIME ftLastWriteTime; // [rsp+110h] [rbp+10h] BYREF
  CLSID pclsid; // [rsp+118h] [rbp+18h] BYREF

  v22 = a3;
  Values = 0;
  ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect>>::RemoveAll(a2);
  v23 = 0;
  v7 = 0;
  DWORD2(v23) = 0;
  v24 = 0;
  hKeya = 0;
  if ( RegOpenKeyExW(hKey, *a3, 0, 0x20019u, &hKeya) )
  {
    Values = 1;
  }
  else
  {
    v8 = hKeya;
    v7 = hKeya;
    *(_QWORD *)&v23 = hKeya;
    DWORD2(v23) = 0;
    v9 = 0;
    cchName[0] = 50;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    v11 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance);
    v12 = (WCHAR *)(v11 + 24);
    v18 = (WCHAR *)(v11 + 24);
    if ( ((1 - *(_DWORD *)(v11 + 16)) | (*(_DWORD *)(v11 + 12) - 50)) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v18, 50);
      v12 = v18;
    }
    while ( 1 )
    {
      if ( *((int *)v12 - 2) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&v18, *((unsigned int *)v12 - 4));
        v12 = v18;
      }
      if ( RegEnumKeyExW(v8, v9, v12, cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      Values = CLSIDFromString(v12, &pclsid);
      if ( Values < 0 )
        break;
      v21 = 0;
      v13 = 0;
      v20[0] = 0;
      v20[1] = 0;
      phkResult = 0;
      v14 = RegOpenKeyExW(v8, v12, 0, 0x20019u, &phkResult);
      if ( !v14 )
      {
        v13 = phkResult;
        v20[0] = phkResult;
        LODWORD(v20[1]) = 0;
      }
      Values = (unsigned __int16)(v14 != 0 ? v14 : 0) | 0x80070000;
      if ( (v14 != 0 ? v14 : 0) <= 0 )
        Values = v14 != 0 ? v14 : 0;
      if ( Values < 0 )
      {
        if ( v13 )
          RegCloseKey(v13);
        break;
      }
      memset_0(&v26, 0, 0x70u);
      Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase((Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)&v26);
      v26 = &Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect::`vftable';
      v31 = -1;
      v30 = -1;
      v29 = -1;
      v28 = -1;
      v35 = -1;
      v34 = -1;
      v33 = -1;
      v32 = -1;
      v27 = pclsid;
      Values = Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect::ReadValues(
                 (Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect *)&v26,
                 (struct ATL::CRegKey *)v20);
      if ( Values < 0 )
      {
        _mm_lfence();
        phkResult = (HKEY)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*v22 - 12) + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &phkResult,
          L"\\%s",
          v12);
        v15 = phkResult;
        CLogger::LogError(
          L"Binding Redirect / CodeBase entry from configuration hive is malformed, ignoring.",
          Values,
          (const unsigned __int16 *)phkResult);
        Values = 0;
        if ( _InterlockedDecrement((volatile signed __int32 *)v15 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
        }
        v8 = hKeya;
      }
      else
      {
        ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect>>::AddTail(
          a2,
          &v26);
      }
      ++v9;
      cchName[0] = 50;
      Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::~CCodeBase((Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)&v26);
      if ( v20[0] )
        RegCloseKey(v20[0]);
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)v12 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    }
  }
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)Values;
}

```

## disassembly

```asm
0x14004e680  mov     [rsp-8+arg_18], rbx
0x14004e685  push    rbp
0x14004e686  push    rsi
0x14004e687  push    rdi
0x14004e688  push    r12
0x14004e68a  push    r13
0x14004e68c  push    r14
0x14004e68e  push    r15
0x14004e690  lea     rbp, [rsp-30h]
0x14004e695  sub     rsp, 130h
0x14004e69c  mov     rax, cs:__security_cookie
0x14004e6a3  xor     rax, rsp
0x14004e6a6  mov     [rbp+60h+var_38], rax
0x14004e6aa  mov     rdi, r8
0x14004e6ad  mov     [rsp+160h+var_F0], r8
0x14004e6b2  mov     r13, rdx
0x14004e6b5  mov     rbx, rcx
0x14004e6b8  xor     r14d, r14d
0x14004e6bb  mov     esi, r14d
0x14004e6be  mov     rcx, rdx
0x14004e6c1  call    ?RemoveAll@?$CAtlList@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@V?$CElementTraits@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect>>::RemoveAll(void)
0x14004e6c6  xorps   xmm0, xmm0
0x14004e6c9  movups  [rsp+160h+var_E8], xmm0
0x14004e6ce  mov     r15d, r14d
0x14004e6d1  mov     dword ptr [rbp+60h+var_E8+8], r14d
0x14004e6d5  mov     [rbp+60h+var_D8], r14
0x14004e6d9  mov     [rsp+160h+hKey], r14
0x14004e6de  lea     rax, [rsp+160h+hKey]
0x14004e6e3  mov     [rsp+160h+phkResult], rax; lpReserved
0x14004e6e8  mov     r9d, 20019h; samDesired
0x14004e6ee  xor     r8d, r8d; ulOptions
0x14004e6f1  mov     rdx, [rdi]; lpSubKey
0x14004e6f4  mov     rcx, rbx; hKey
0x14004e6f7  call    cs:__imp_RegOpenKeyExW
0x14004e6fd  test    eax, eax
0x14004e6ff  jnz     loc_14004E96C
0x14004e705  mov     r14, [rsp+160h+hKey]
0x14004e70a  mov     r15, r14
0x14004e70d  mov     qword ptr [rsp+160h+var_E8], r14
0x14004e712  and     dword ptr [rbp+60h+var_E8+8], eax
0x14004e715  xor     r12d, r12d
0x14004e718  lea     ebx, [rax+32h]
0x14004e71b  mov     [rbp+60h+cchName], ebx
0x14004e71e  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004e723  mov     rcx, rax
0x14004e726  test    rax, rax
0x14004e729  jz      loc_14004E9A8
0x14004e72f  mov     rax, [rax]
0x14004e732  call    qword ptr [rax+18h]
0x14004e735  lea     rdi, [rax+18h]
0x14004e739  mov     [rsp+160h+var_118], rdi
0x14004e73e  lea     ecx, [rbx-31h]
0x14004e741  sub     ecx, [rdi-8]
0x14004e744  mov     eax, [rdi-0Ch]
0x14004e747  sub     eax, ebx
0x14004e749  or      eax, ecx
0x14004e74b  jge     short loc_14004E75E
0x14004e74d  mov     edx, ebx
0x14004e74f  lea     rcx, [rsp+160h+var_118]
0x14004e754  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14004e759  mov     rdi, [rsp+160h+var_118]
0x14004e75e  or      ebx, 0FFFFFFFFh
0x14004e761  cmp     dword ptr [rdi-8], 1
0x14004e765  jle     short loc_14004E779
0x14004e767  mov     edx, [rdi-10h]
0x14004e76a  lea     rcx, [rsp+160h+var_118]
0x14004e76f  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x14004e774  mov     rdi, [rsp+160h+var_118]
0x14004e779  lea     rax, [rbp+60h+ftLastWriteTime]
0x14004e77d  mov     [rsp+160h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14004e782  and     [rsp+160h+var_130], 0
0x14004e788  and     [rsp+160h+var_138], 0
0x14004e78e  and     [rsp+160h+phkResult], 0
0x14004e794  lea     r9, [rbp+60h+cchName]; lpcchName
0x14004e798  mov     r8, rdi; lpName
0x14004e79b  mov     edx, r12d; dwIndex
0x14004e79e  mov     rcx, r14; hKey
0x14004e7a1  call    cs:__imp_RegEnumKeyExW
0x14004e7a7  test    eax, eax
0x14004e7a9  jnz     loc_14004E94D
0x14004e7af  lea     rdx, [rbp+60h+pclsid]; pclsid
0x14004e7b3  mov     rcx, rdi; lpsz
0x14004e7b6  call    cs:__imp_CLSIDFromString
0x14004e7bc  mov     esi, eax
0x14004e7be  test    eax, eax
0x14004e7c0  js      loc_14004E94D
0x14004e7c6  xorps   xmm0, xmm0
0x14004e7c9  xor     eax, eax
0x14004e7cb  movups  xmmword ptr [rsp+160h+var_108], xmm0
0x14004e7d0  mov     [rsp+160h+var_F8], rax
0x14004e7d5  xor     ebx, ebx
0x14004e7d7  mov     [rsp+160h+var_108], rbx
0x14004e7dc  and     dword ptr [rsp+160h+var_108+8], eax
0x14004e7e0  and     [rsp+160h+var_F8], rax
0x14004e7e5  and     [rsp+160h+var_120], rbx
0x14004e7ea  lea     rax, [rsp+160h+var_120]
0x14004e7ef  mov     [rsp+160h+phkResult], rax; phkResult
0x14004e7f4  mov     r9d, 20019h; samDesired
0x14004e7fa  xor     r8d, r8d; ulOptions
0x14004e7fd  mov     rdx, rdi; lpSubKey
0x14004e800  mov     rcx, r14; hKey
0x14004e803  call    cs:__imp_RegOpenKeyExW
0x14004e809  test    eax, eax
0x14004e80b  jnz     short loc_14004E81B
0x14004e80d  mov     rbx, [rsp+160h+var_120]
0x14004e812  mov     [rsp+160h+var_108], rbx
0x14004e817  and     dword ptr [rsp+160h+var_108+8], eax
0x14004e81b  mov     ecx, eax
0x14004e81d  neg     ecx
0x14004e81f  sbb     edx, edx
0x14004e821  and     edx, eax
0x14004e823  movzx   esi, dx
0x14004e826  or      esi, 80070000h
0x14004e82c  test    edx, edx
0x14004e82e  cmovle  esi, edx
0x14004e831  test    esi, esi
0x14004e833  js      loc_14004E93C
0x14004e839  xor     edx, edx; Val
0x14004e83b  lea     r8d, [rdx+70h]; Size
0x14004e83f  lea     rcx, [rbp+60h+var_C0]; void *
0x14004e843  call    memset_0
0x14004e848  lea     rcx, [rbp+60h+var_C0]; this
0x14004e84c  call    ??0CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAA@XZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase(void)
0x14004e851  lea     rax, ??_7CBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@6B@; const Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect::`vftable'
0x14004e858  mov     [rbp+60h+var_C0], rax
0x14004e85c  or      ebx, 0FFFFFFFFh
0x14004e85f  mov     [rbp+60h+var_64], ebx
0x14004e862  mov     [rbp+60h+var_68], ebx
0x14004e865  mov     [rbp+60h+var_6C], ebx
0x14004e868  mov     [rbp+60h+var_70], ebx
0x14004e86b  mov     [rbp+60h+var_54], ebx
0x14004e86e  mov     [rbp+60h+var_58], ebx
0x14004e871  mov     [rbp+60h+var_5C], ebx
0x14004e874  mov     [rbp+60h+var_60], ebx
0x14004e877  movups  xmm0, xmmword ptr [rbp+60h+pclsid.Data1]
0x14004e87b  movdqu  [rbp+60h+var_B8], xmm0
0x14004e880  lea     rdx, [rsp+160h+var_108]; struct ATL::CRegKey *
0x14004e885  lea     rcx, [rbp+60h+var_C0]; this
0x14004e889  call    ?ReadValues@CBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@UEAAJAEAVCRegKey@ATL@@@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect::ReadValues(ATL::CRegKey &)
0x14004e88e  mov     esi, eax
0x14004e890  test    eax, eax
0x14004e892  js      short loc_14004E8A2
0x14004e894  lea     rdx, [rbp+60h+var_C0]
0x14004e898  mov     rcx, r13
0x14004e89b  call    ?AddTail@?$CAtlList@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@V?$CElementTraits@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBVCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@Z; ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect>>::AddTail(Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect const &)
0x14004e8a0  jmp     short loc_14004E910
0x14004e8a2  lfence
0x14004e8a5  mov     rax, [rsp+160h+var_F0]
0x14004e8aa  mov     rcx, [rax]
0x14004e8ad  sub     rcx, 18h
0x14004e8b1  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14004e8b6  add     rax, 18h
0x14004e8ba  mov     [rsp+160h+var_120], rax
0x14004e8bf  mov     r8, rdi
0x14004e8c2  lea     rdx, aS_4; "\\%s"
0x14004e8c9  lea     rcx, [rsp+160h+var_120]
0x14004e8ce  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14004e8d3  mov     rbx, [rsp+160h+var_120]
0x14004e8d8  mov     r8, rbx; unsigned __int16 *
0x14004e8db  mov     edx, esi; int
0x14004e8dd  lea     rcx, aBindingRedirec_0; "Binding Redirect / CodeBase entry from "...
0x14004e8e4  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14004e8e9  xor     esi, esi
0x14004e8eb  lea     rdx, [rbx-18h]
0x14004e8ef  or      ebx, 0FFFFFFFFh
0x14004e8f2  mov     eax, ebx
0x14004e8f4  lock xadd [rdx+10h], eax
0x14004e8f9  add     eax, ebx
0x14004e8fb  test    eax, eax
0x14004e8fd  jg      short loc_14004E90B
0x14004e8ff  lfence
0x14004e902  mov     rcx, [rdx]
0x14004e905  mov     rax, [rcx]
0x14004e908  call    qword ptr [rax+8]
0x14004e90b  mov     r14, [rsp+160h+hKey]
0x14004e910  inc     r12d
0x14004e913  mov     [rbp+60h+cchName], 32h ; '2'
0x14004e91a  lea     rcx, [rbp+60h+var_C0]; this
0x14004e91e  call    ??1CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@UEAA@XZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::~CCodeBase(void)
0x14004e923  mov     rcx, [rsp+160h+var_108]; hKey
0x14004e928  test    rcx, rcx
0x14004e92b  jz      loc_14004E761
0x14004e931  call    cs:__imp_RegCloseKey
0x14004e937  jmp     loc_14004E761
0x14004e93c  test    rbx, rbx
0x14004e93f  jz      short loc_14004E94A
0x14004e941  mov     rcx, rbx; hKey
0x14004e944  call    cs:__imp_RegCloseKey
0x14004e94a  or      ebx, 0FFFFFFFFh
0x14004e94d  lea     rdx, [rdi-18h]
0x14004e951  mov     eax, ebx
0x14004e953  lock xadd [rdx+10h], eax
0x14004e958  add     eax, ebx
0x14004e95a  test    eax, eax
0x14004e95c  jg      short loc_14004E971
0x14004e95e  lfence
0x14004e961  mov     rcx, [rdx]
0x14004e964  mov     rax, [rcx]
0x14004e967  call    qword ptr [rax+8]
0x14004e96a  jmp     short loc_14004E971
0x14004e96c  mov     esi, 1
0x14004e971  test    r15, r15
0x14004e974  jz      short loc_14004E97F
0x14004e976  mov     rcx, r15; hKey
0x14004e979  call    cs:__imp_RegCloseKey
0x14004e97f  mov     eax, esi
0x14004e981  mov     rcx, [rbp+60h+var_38]
0x14004e985  xor     rcx, rsp; StackCookie
0x14004e988  call    __security_check_cookie
0x14004e98d  mov     rbx, [rsp+160h+arg_18]
0x14004e995  add     rsp, 130h
0x14004e99c  pop     r15
0x14004e99e  pop     r14
0x14004e9a0  pop     r13
0x14004e9a2  pop     r12
0x14004e9a4  pop     rdi
0x14004e9a5  pop     rsi
0x14004e9a6  pop     rbp
0x14004e9a7  retn
0x14004e9a8  mov     ecx, 80004005h; int
0x14004e9ad  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
