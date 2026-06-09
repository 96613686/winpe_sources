# Microsoft::VisualStudio::PkgDef::BindingRedirects::ReadEntries<Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase>(HKEY__ *,ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14004e36c`
- end: `0x14004e671`
- name: `??$ReadEntries@VCCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@BindingRedirects@PkgDef@VisualStudio@Microsoft@@YAJPEAUHKEY__@@AEAV?$CAtlList@VCCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@V?$CElementTraits@VCCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@6@@Z`
- size: `773`
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
- `0x14004e36c`
- `0x14004ee20`
- `0x14004f990`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004e5f1`
- `ADVAPI32!RegCloseKey` at `0x14004e604`
- `ADVAPI32!RegCloseKey` at `0x14004e637`
- `ADVAPI32!RegCloseKey` at `0x14004e5f1`
- `ADVAPI32!RegCloseKey` at `0x14004e604`
- `ADVAPI32!RegCloseKey` at `0x14004e637`
- `ADVAPI32!RegOpenKeyExW` at `0x14004e3e3`
- `ADVAPI32!RegOpenKeyExW` at `0x14004e4ec`
- `ADVAPI32!RegOpenKeyExW` at `0x14004e3e3`
- `ADVAPI32!RegOpenKeyExW` at `0x14004e4ec`
- `ADVAPI32!RegEnumKeyExW` at `0x14004e48a`
- `ADVAPI32!RegEnumKeyExW` at `0x14004e48a`
- `ole32!CLSIDFromString` at `0x14004e49f`
- `ole32!CLSIDFromString` at `0x14004e49f`

## string_xrefs

- `0x14004e5a0`: `Binding Redirect / CodeBase entry from configuration hive is malformed, ignoring.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::VisualStudio::PkgDef::BindingRedirects::ReadEntries<Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase>(
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
  DWORD cchName; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+98h] [rbp-68h] BYREF
  CLSID pclsid; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v28[8]; // [rsp+B0h] [rbp-50h] BYREF
  CLSID v29; // [rsp+B8h] [rbp-48h]

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
    cchName = 50;
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
      if ( RegEnumKeyExW(v8, v9, v12, &cchName, 0, 0, 0, &ftLastWriteTime) )
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
      memset_0(v28, 0, 0x50u);
      Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase((Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)v28);
      v29 = pclsid;
      Values = Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::ReadValues(
                 (Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)v28,
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
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
        }
        v8 = hKeya;
      }
      else
      {
        ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase>>::AddTail(
          a2,
          v28);
      }
      ++v9;
      cchName = 50;
      Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::~CCodeBase((Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase *)v28);
      if ( v20[0] )
        RegCloseKey(v20[0]);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
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
0x14004e36c  mov     [rsp-8+arg_18], rbx
0x14004e371  push    rbp
0x14004e372  push    rsi
0x14004e373  push    rdi
0x14004e374  push    r12
0x14004e376  push    r13
0x14004e378  push    r14
0x14004e37a  push    r15
0x14004e37c  lea     rbp, [rsp-10h]
0x14004e381  sub     rsp, 110h
0x14004e388  mov     rax, cs:__security_cookie
0x14004e38f  xor     rax, rsp
0x14004e392  mov     [rbp+40h+var_40], rax
0x14004e396  mov     rdi, r8
0x14004e399  mov     [rsp+140h+var_D0], r8
0x14004e39e  mov     r13, rdx
0x14004e3a1  mov     rbx, rcx
0x14004e3a4  xor     r14d, r14d
0x14004e3a7  mov     esi, r14d
0x14004e3aa  mov     rcx, rdx
0x14004e3ad  call    ?RemoveAll@?$CAtlList@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@V?$CElementTraits@VCBindingRedirect@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CBindingRedirect>>::RemoveAll(void)
0x14004e3b2  xorps   xmm0, xmm0
0x14004e3b5  movups  [rsp+140h+var_C8], xmm0
0x14004e3ba  mov     r15d, r14d
0x14004e3bd  mov     dword ptr [rbp+40h+var_C8+8], r14d
0x14004e3c1  mov     [rbp+40h+var_B8], r14
0x14004e3c5  mov     [rsp+140h+hKey], r14
0x14004e3ca  lea     rax, [rsp+140h+hKey]
0x14004e3cf  mov     [rsp+140h+phkResult], rax; lpReserved
0x14004e3d4  mov     r9d, 20019h; samDesired
0x14004e3da  xor     r8d, r8d; ulOptions
0x14004e3dd  mov     rdx, [rdi]; lpSubKey
0x14004e3e0  mov     rcx, rbx; hKey
0x14004e3e3  call    cs:__imp_RegOpenKeyExW
0x14004e3e9  test    eax, eax
0x14004e3eb  jnz     loc_14004E62A
0x14004e3f1  mov     r14, [rsp+140h+hKey]
0x14004e3f6  mov     r15, r14
0x14004e3f9  mov     qword ptr [rsp+140h+var_C8], r14
0x14004e3fe  and     dword ptr [rbp+40h+var_C8+8], eax
0x14004e401  xor     r12d, r12d
0x14004e404  lea     ebx, [rax+32h]
0x14004e407  mov     [rbp+40h+cchName], ebx
0x14004e40a  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004e40f  mov     rcx, rax
0x14004e412  test    rax, rax
0x14004e415  jz      loc_14004E666
0x14004e41b  mov     rax, [rax]
0x14004e41e  call    qword ptr [rax+18h]
0x14004e421  lea     rdi, [rax+18h]
0x14004e425  mov     [rsp+140h+var_F8], rdi
0x14004e42a  lea     ecx, [rbx-31h]
0x14004e42d  sub     ecx, [rdi-8]
0x14004e430  mov     eax, [rdi-0Ch]
0x14004e433  sub     eax, ebx
0x14004e435  or      eax, ecx
0x14004e437  jge     short loc_14004E44A
0x14004e439  mov     edx, ebx
0x14004e43b  lea     rcx, [rsp+140h+var_F8]
0x14004e440  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14004e445  mov     rdi, [rsp+140h+var_F8]
0x14004e44a  cmp     dword ptr [rdi-8], 1
0x14004e44e  jle     short loc_14004E462
0x14004e450  mov     edx, [rdi-10h]
0x14004e453  lea     rcx, [rsp+140h+var_F8]
0x14004e458  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x14004e45d  mov     rdi, [rsp+140h+var_F8]
0x14004e462  lea     rax, [rbp+40h+ftLastWriteTime]
0x14004e466  mov     [rsp+140h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14004e46b  and     [rsp+140h+var_110], 0
0x14004e471  and     [rsp+140h+var_118], 0
0x14004e477  and     [rsp+140h+phkResult], 0
0x14004e47d  lea     r9, [rbp+40h+cchName]; lpcchName
0x14004e481  mov     r8, rdi; lpName
0x14004e484  mov     edx, r12d; dwIndex
0x14004e487  mov     rcx, r14; hKey
0x14004e48a  call    cs:__imp_RegEnumKeyExW
0x14004e490  test    eax, eax
0x14004e492  jnz     loc_14004E60B
0x14004e498  lea     rdx, [rbp+40h+pclsid]; pclsid
0x14004e49c  mov     rcx, rdi; lpsz
0x14004e49f  call    cs:__imp_CLSIDFromString
0x14004e4a5  mov     esi, eax
0x14004e4a7  test    eax, eax
0x14004e4a9  js      loc_14004E60B
0x14004e4af  xorps   xmm0, xmm0
0x14004e4b2  xor     eax, eax
0x14004e4b4  movups  xmmword ptr [rsp+140h+var_E8], xmm0
0x14004e4b9  mov     [rsp+140h+var_D8], rax
0x14004e4be  xor     ebx, ebx
0x14004e4c0  mov     [rsp+140h+var_E8], rbx
0x14004e4c5  and     dword ptr [rsp+140h+var_E8+8], eax
0x14004e4c9  and     [rsp+140h+var_D8], rax
0x14004e4ce  and     [rsp+140h+var_100], rbx
0x14004e4d3  lea     rax, [rsp+140h+var_100]
0x14004e4d8  mov     [rsp+140h+phkResult], rax; phkResult
0x14004e4dd  mov     r9d, 20019h; samDesired
0x14004e4e3  xor     r8d, r8d; ulOptions
0x14004e4e6  mov     rdx, rdi; lpSubKey
0x14004e4e9  mov     rcx, r14; hKey
0x14004e4ec  call    cs:__imp_RegOpenKeyExW
0x14004e4f2  test    eax, eax
0x14004e4f4  jnz     short loc_14004E504
0x14004e4f6  mov     rbx, [rsp+140h+var_100]
0x14004e4fb  mov     [rsp+140h+var_E8], rbx
0x14004e500  and     dword ptr [rsp+140h+var_E8+8], eax
0x14004e504  mov     ecx, eax
0x14004e506  neg     ecx
0x14004e508  sbb     edx, edx
0x14004e50a  and     edx, eax
0x14004e50c  movzx   esi, dx
0x14004e50f  or      esi, 80070000h
0x14004e515  test    edx, edx
0x14004e517  cmovle  esi, edx
0x14004e51a  test    esi, esi
0x14004e51c  js      loc_14004E5FC
0x14004e522  xor     edx, edx; Val
0x14004e524  lea     r8d, [rdx+50h]; Size
0x14004e528  lea     rcx, [rbp+40h+var_90]; void *
0x14004e52c  call    memset_0
0x14004e531  lea     rcx, [rbp+40h+var_90]; this
0x14004e535  call    ??0CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@QEAA@XZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::CCodeBase(void)
0x14004e53a  movups  xmm0, xmmword ptr [rbp+40h+pclsid.Data1]
0x14004e53e  movdqu  [rbp+40h+var_88], xmm0
0x14004e543  lea     rdx, [rsp+140h+var_E8]; struct ATL::CRegKey *
0x14004e548  lea     rcx, [rbp+40h+var_90]; this
0x14004e54c  call    ?ReadValues@CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@UEAAJAEAVCRegKey@ATL@@@Z; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::ReadValues(ATL::CRegKey &)
0x14004e551  mov     esi, eax
0x14004e553  test    eax, eax
0x14004e555  js      short loc_14004E565
0x14004e557  lea     rdx, [rbp+40h+var_90]
0x14004e55b  mov     rcx, r13
0x14004e55e  call    ?AddTail@?$CAtlList@VCCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@V?$CElementTraits@VCCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBVCCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@@Z; ATL::CAtlList<Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase,ATL::CElementTraits<Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase>>::AddTail(Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase const &)
0x14004e563  jmp     short loc_14004E5D0
0x14004e565  lfence
0x14004e568  mov     rax, [rsp+140h+var_D0]
0x14004e56d  mov     rcx, [rax]
0x14004e570  sub     rcx, 18h
0x14004e574  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14004e579  add     rax, 18h
0x14004e57d  mov     [rsp+140h+var_100], rax
0x14004e582  mov     r8, rdi
0x14004e585  lea     rdx, aS_4; "\\%s"
0x14004e58c  lea     rcx, [rsp+140h+var_100]
0x14004e591  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14004e596  mov     rbx, [rsp+140h+var_100]
0x14004e59b  mov     r8, rbx; unsigned __int16 *
0x14004e59e  mov     edx, esi; int
0x14004e5a0  lea     rcx, aBindingRedirec_0; "Binding Redirect / CodeBase entry from "...
0x14004e5a7  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14004e5ac  xor     esi, esi
0x14004e5ae  lea     rdx, [rbx-18h]
0x14004e5b2  or      eax, 0FFFFFFFFh
0x14004e5b5  lock xadd [rdx+10h], eax
0x14004e5ba  sub     eax, 1
0x14004e5bd  jg      short loc_14004E5CB
0x14004e5bf  lfence
0x14004e5c2  mov     rcx, [rdx]
0x14004e5c5  mov     rax, [rcx]
0x14004e5c8  call    qword ptr [rax+8]
0x14004e5cb  mov     r14, [rsp+140h+hKey]
0x14004e5d0  inc     r12d
0x14004e5d3  mov     [rbp+40h+cchName], 32h ; '2'
0x14004e5da  lea     rcx, [rbp+40h+var_90]; this
0x14004e5de  call    ??1CCodeBase@BindingRedirects@PkgDef@VisualStudio@Microsoft@@UEAA@XZ; Microsoft::VisualStudio::PkgDef::BindingRedirects::CCodeBase::~CCodeBase(void)
0x14004e5e3  mov     rcx, [rsp+140h+var_E8]; hKey
0x14004e5e8  test    rcx, rcx
0x14004e5eb  jz      loc_14004E44A
0x14004e5f1  call    cs:__imp_RegCloseKey
0x14004e5f7  jmp     loc_14004E44A
0x14004e5fc  test    rbx, rbx
0x14004e5ff  jz      short loc_14004E60B
0x14004e601  mov     rcx, rbx; hKey
0x14004e604  call    cs:__imp_RegCloseKey
0x14004e60a  nop
0x14004e60b  lea     rdx, [rdi-18h]
0x14004e60f  or      eax, 0FFFFFFFFh
0x14004e612  lock xadd [rdx+10h], eax
0x14004e617  sub     eax, 1
0x14004e61a  jg      short loc_14004E62F
0x14004e61c  lfence
0x14004e61f  mov     rcx, [rdx]
0x14004e622  mov     rax, [rcx]
0x14004e625  call    qword ptr [rax+8]
0x14004e628  jmp     short loc_14004E62F
0x14004e62a  mov     esi, 1
0x14004e62f  test    r15, r15
0x14004e632  jz      short loc_14004E63D
0x14004e634  mov     rcx, r15; hKey
0x14004e637  call    cs:__imp_RegCloseKey
0x14004e63d  mov     eax, esi
0x14004e63f  mov     rcx, [rbp+40h+var_40]
0x14004e643  xor     rcx, rsp; StackCookie
0x14004e646  call    __security_check_cookie
0x14004e64b  mov     rbx, [rsp+140h+arg_18]
0x14004e653  add     rsp, 110h
0x14004e65a  pop     r15
0x14004e65c  pop     r14
0x14004e65e  pop     r13
0x14004e660  pop     r12
0x14004e662  pop     rdi
0x14004e663  pop     rsi
0x14004e664  pop     rbp
0x14004e665  retn
0x14004e666  mov     ecx, 80004005h; int
0x14004e66b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
