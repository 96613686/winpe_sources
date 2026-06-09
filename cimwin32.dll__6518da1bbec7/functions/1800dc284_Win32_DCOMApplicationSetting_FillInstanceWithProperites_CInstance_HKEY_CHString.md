# Win32_DCOMApplicationSetting::FillInstanceWithProperites(CInstance *,HKEY__ *,CHString &)

- ea: `0x1800dc284`
- end: `0x1800dc594`
- name: `?FillInstanceWithProperites@Win32_DCOMApplicationSetting@@IEAAJPEAVCInstance@@PEAUHKEY__@@AEAVCHString@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(Win32_DCOMApplicationSetting *__hidden this, struct CInstance *, HKEY, struct CHString *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800dc050`
- `0x1800dc5a0`

## callees

- `0x1800127e0`
- `0x180017680`
- `0x1800dc284`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800dc2fb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800dc2fb`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800dc2c5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800dc2c5`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800dc4a1`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800dc4a1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800dc2d7`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800dc318`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800dc2d7`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800dc318`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800dc4f1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800dc4f1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc34a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc375`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc38a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc3dc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc426`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc465`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc521`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc551`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc34a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc375`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc38a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc3dc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc426`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc465`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc521`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800dc551`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800dc3b8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800dc3e7`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800dc4bd`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800dc3b8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800dc3e7`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800dc4bd`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800dc2b9`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800dc2b9`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800dc56f`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800dc56f`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800dc32f`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800dc32f`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAK@Z` at `0x1800dc4d8`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAK@Z` at `0x1800dc4d8`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800dc3c3`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800dc40d`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800dc44c`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800dc48b`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800dc3c3`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800dc40d`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800dc44c`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x1800dc48b`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc35c`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc3a1`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc3fe`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc43d`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc47c`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc508`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc538`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc35c`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc3a1`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc3fe`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc43d`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc47c`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc508`
- `framedynos!?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z` at `0x1800dc538`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800dc563`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800dc563`

## string_xrefs

- `0x1800dc4fc`: `LocalService`
- `0x1800dc517`: `LocalService`
- `0x1800dc395`: `DllSurrogate`
- `0x1800dc52c`: `ServiceParameters`
- `0x1800dc547`: `ServiceParameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Win32_DCOMApplicationSetting::FillInstanceWithProperites(
        Win32_DCOMApplicationSetting *this,
        struct CInstance *a2,
        HKEY a3,
        struct CHString *a4)
{
  const unsigned __int16 *v7; // rax
  const OLECHAR *v8; // rcx
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // rax
  bool v11; // r8
  _BYTE v13[8]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v14; // [rsp+28h] [rbp-D8h] BYREF
  GUID pclsid; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[608]; // [rsp+40h] [rbp-C0h] BYREF

  CRegistry::CRegistry((CRegistry *)v16);
  CHString::CHString((CHString *)v13);
  pclsid = 0;
  v7 = (const unsigned __int16 *)CHString::operator unsigned short const *(a4);
  v8 = *(const OLECHAR **)_bstr_t::_bstr_t((_bstr_t *)&v14, v7);
  if ( v8 )
    v8 = *(const OLECHAR **)v8;
  v9 = CLSIDFromString(v8, &pclsid);
  _bstr_t::_Free((_bstr_t *)&v14);
  if ( v9
    || (v10 = (const unsigned __int16 *)CHString::operator unsigned short const *(a4),
        CRegistry::Open((CRegistry *)v16, a3, v10, 0x20019u)) )
  {
    v9 = -2147217406;
  }
  else
  {
    CInstance::SetCHString(a2, L"AppID", a4);
    if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v16, 0, (struct CHString *)v13) )
    {
      CInstance::SetCHString(a2, L"Caption", (const struct CHString *)v13);
      CInstance::SetCHString(a2, L"Description", (const struct CHString *)v13);
    }
    if ( CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"DllSurrogate", (struct CHString *)v13) )
    {
      CInstance::Setbool(a2, L"UseSurrogate", 0);
    }
    else
    {
      CInstance::Setbool(a2, L"UseSurrogate", 1);
      if ( !CHString::IsEmpty((CHString *)v13) )
        CInstance::SetCHString(a2, L"CustomSurrogate", (const struct CHString *)v13);
    }
    if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"RemoteServerName", (struct CHString *)v13)
      && !CHString::IsEmpty((CHString *)v13) )
    {
      CInstance::SetCHString(a2, L"RemoteServerName", (const struct CHString *)v13);
    }
    if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"RunAs", (struct CHString *)v13)
      && !CHString::IsEmpty((CHString *)v13) )
    {
      CInstance::SetCHString(a2, L"RunAsUser", (const struct CHString *)v13);
    }
    v11 = !CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"ActivateAtStorage", (struct CHString *)v13)
       && !CHString::IsEmpty((CHString *)v13)
       && !CHString::CompareNoCase((CHString *)v13, L"Y");
    CInstance::Setbool(a2, L"EnableAtStorageActivation", v11);
    v14 = 0;
    if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"AuthenticationLevel", &v14) )
      CInstance::SetDWORD(a2, L"AuthenticationLevel", v14);
    if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"LocalService", (struct CHString *)v13) )
      CInstance::SetCHString(a2, L"LocalService", (const struct CHString *)v13);
    if ( !CRegistry::GetCurrentKeyValue((CRegistry *)v16, L"ServiceParameters", (struct CHString *)v13) )
      CInstance::SetCHString(a2, L"ServiceParameters", (const struct CHString *)v13);
  }
  CHString::~CHString((CHString *)v13);
  CRegistry::~CRegistry((CRegistry *)v16);
  return v9;
}

```

## disassembly

```asm
0x1800dc284  push    rbp
0x1800dc286  push    rbx
0x1800dc287  push    rsi
0x1800dc288  push    rdi
0x1800dc289  push    r14
0x1800dc28b  lea     rbp, [rsp-1B0h]
0x1800dc293  sub     rsp, 2B0h
0x1800dc29a  mov     rax, cs:__security_cookie
0x1800dc2a1  xor     rax, rsp
0x1800dc2a4  mov     [rbp+1D0h+var_30], rax
0x1800dc2ab  mov     rsi, r9
0x1800dc2ae  mov     r14, r8
0x1800dc2b1  mov     rdi, rdx
0x1800dc2b4  lea     rcx, [rsp+2D0h+var_290]
0x1800dc2b9  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x1800dc2bf  nop
0x1800dc2c0  lea     rcx, [rsp+2D0h+var_2B0]
0x1800dc2c5  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800dc2cb  nop
0x1800dc2cc  xorps   xmm0, xmm0
0x1800dc2cf  movups  xmmword ptr [rsp+2D0h+pclsid.Data1], xmm0
0x1800dc2d4  mov     rcx, rsi
0x1800dc2d7  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800dc2dd  mov     rdx, rax; unsigned __int16 *
0x1800dc2e0  lea     rcx, [rsp+2D0h+var_2A8]; this
0x1800dc2e5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800dc2ea  nop
0x1800dc2eb  mov     rcx, [rax]
0x1800dc2ee  test    rcx, rcx
0x1800dc2f1  jz      short loc_1800DC2F6
0x1800dc2f3  mov     rcx, [rcx]; lpsz
0x1800dc2f6  lea     rdx, [rsp+2D0h+pclsid]; pclsid
0x1800dc2fb  call    cs:__imp_CLSIDFromString
0x1800dc301  mov     ebx, eax
0x1800dc303  lea     rcx, [rsp+2D0h+var_2A8]; this
0x1800dc308  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800dc30d  test    ebx, ebx
0x1800dc30f  jnz     loc_1800DC559
0x1800dc315  mov     rcx, rsi
0x1800dc318  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800dc31e  mov     r8, rax
0x1800dc321  mov     r9d, 20019h
0x1800dc327  mov     rdx, r14
0x1800dc32a  lea     rcx, [rsp+2D0h+var_290]
0x1800dc32f  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x1800dc335  test    eax, eax
0x1800dc337  jnz     loc_1800DC559
0x1800dc33d  mov     r8, rsi
0x1800dc340  lea     rdx, aAppid; "AppID"
0x1800dc347  mov     rcx, rdi
0x1800dc34a  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800dc350  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc355  xor     edx, edx
0x1800dc357  lea     rcx, [rsp+2D0h+var_290]
0x1800dc35c  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800dc362  test    eax, eax
0x1800dc364  jnz     short loc_1800DC390
0x1800dc366  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc36b  lea     rdx, aCaption; "Caption"
0x1800dc372  mov     rcx, rdi
0x1800dc375  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800dc37b  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc380  lea     rdx, aDescription; "Description"
0x1800dc387  mov     rcx, rdi
0x1800dc38a  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800dc390  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc395  lea     rdx, aDllsurrogate; "DllSurrogate"
0x1800dc39c  lea     rcx, [rsp+2D0h+var_290]
0x1800dc3a1  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800dc3a7  lea     rdx, aUsesurrogate; "UseSurrogate"
0x1800dc3ae  mov     rcx, rdi
0x1800dc3b1  test    eax, eax
0x1800dc3b3  jnz     short loc_1800DC3E4
0x1800dc3b5  mov     r8b, 1
0x1800dc3b8  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800dc3be  lea     rcx, [rsp+2D0h+var_2B0]
0x1800dc3c3  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800dc3c9  test    eax, eax
0x1800dc3cb  jnz     short loc_1800DC3ED
0x1800dc3cd  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc3d2  lea     rdx, aCustomsurrogat; "CustomSurrogate"
0x1800dc3d9  mov     rcx, rdi
0x1800dc3dc  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800dc3e2  jmp     short loc_1800DC3ED
0x1800dc3e4  xor     r8d, r8d
0x1800dc3e7  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800dc3ed  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc3f2  lea     rdx, aRemoteserverna; "RemoteServerName"
0x1800dc3f9  lea     rcx, [rsp+2D0h+var_290]
0x1800dc3fe  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800dc404  test    eax, eax
0x1800dc406  jnz     short loc_1800DC42C
0x1800dc408  lea     rcx, [rsp+2D0h+var_2B0]
0x1800dc40d  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800dc413  test    eax, eax
0x1800dc415  jnz     short loc_1800DC42C
0x1800dc417  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc41c  lea     rdx, aRemoteserverna; "RemoteServerName"
0x1800dc423  mov     rcx, rdi
0x1800dc426  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800dc42c  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc431  lea     rdx, aRunas; "RunAs"
0x1800dc438  lea     rcx, [rsp+2D0h+var_290]
0x1800dc43d  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800dc443  test    eax, eax
0x1800dc445  jnz     short loc_1800DC46B
0x1800dc447  lea     rcx, [rsp+2D0h+var_2B0]
0x1800dc44c  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800dc452  test    eax, eax
0x1800dc454  jnz     short loc_1800DC46B
0x1800dc456  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc45b  lea     rdx, aRunasuser; "RunAsUser"
0x1800dc462  mov     rcx, rdi
0x1800dc465  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800dc46b  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc470  lea     rdx, aActivateatstor; "ActivateAtStorage"
0x1800dc477  lea     rcx, [rsp+2D0h+var_290]
0x1800dc47c  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800dc482  test    eax, eax
0x1800dc484  jnz     short loc_1800DC4B0
0x1800dc486  lea     rcx, [rsp+2D0h+var_2B0]
0x1800dc48b  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x1800dc491  test    eax, eax
0x1800dc493  jnz     short loc_1800DC4B0
0x1800dc495  lea     rdx, aY; "Y"
0x1800dc49c  lea     rcx, [rsp+2D0h+var_2B0]
0x1800dc4a1  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x1800dc4a7  test    eax, eax
0x1800dc4a9  jnz     short loc_1800DC4B0
0x1800dc4ab  mov     r8b, 1
0x1800dc4ae  jmp     short loc_1800DC4B3
0x1800dc4b0  xor     r8d, r8d
0x1800dc4b3  lea     rdx, aEnableatstorag; "EnableAtStorageActivation"
0x1800dc4ba  mov     rcx, rdi
0x1800dc4bd  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800dc4c3  mov     [rsp+2D0h+var_2A8], ebx
0x1800dc4c7  lea     r8, [rsp+2D0h+var_2A8]
0x1800dc4cc  lea     rdx, aAuthentication_0; "AuthenticationLevel"
0x1800dc4d3  lea     rcx, [rsp+2D0h+var_290]
0x1800dc4d8  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAK@Z; CRegistry::GetCurrentKeyValue(ushort const *,ulong &)
0x1800dc4de  test    eax, eax
0x1800dc4e0  jnz     short loc_1800DC4F7
0x1800dc4e2  mov     r8d, [rsp+2D0h+var_2A8]
0x1800dc4e7  lea     rdx, aAuthentication_0; "AuthenticationLevel"
0x1800dc4ee  mov     rcx, rdi
0x1800dc4f1  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800dc4f7  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc4fc  lea     rdx, aLocalservice; "LocalService"
0x1800dc503  lea     rcx, [rsp+2D0h+var_290]
0x1800dc508  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800dc50e  test    eax, eax
0x1800dc510  jnz     short loc_1800DC527
0x1800dc512  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc517  lea     rdx, aLocalservice; "LocalService"
0x1800dc51e  mov     rcx, rdi
0x1800dc521  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800dc527  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc52c  lea     rdx, aServiceparamet; "ServiceParameters"
0x1800dc533  lea     rcx, [rsp+2D0h+var_290]
0x1800dc538  call    cs:__imp_?GetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::GetCurrentKeyValue(ushort const *,CHString &)
0x1800dc53e  test    eax, eax
0x1800dc540  jnz     short loc_1800DC55E
0x1800dc542  lea     r8, [rsp+2D0h+var_2B0]
0x1800dc547  lea     rdx, aServiceparamet; "ServiceParameters"
0x1800dc54e  mov     rcx, rdi
0x1800dc551  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x1800dc557  jmp     short loc_1800DC55E
0x1800dc559  mov     ebx, 80041002h
0x1800dc55e  lea     rcx, [rsp+2D0h+var_2B0]
0x1800dc563  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800dc569  nop
0x1800dc56a  lea     rcx, [rsp+2D0h+var_290]
0x1800dc56f  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800dc575  mov     eax, ebx
0x1800dc577  mov     rcx, [rbp+1D0h+var_30]
0x1800dc57e  xor     rcx, rsp; StackCookie
0x1800dc581  call    __security_check_cookie
0x1800dc586  add     rsp, 2B0h
0x1800dc58d  pop     r14
0x1800dc58f  pop     rdi
0x1800dc590  pop     rsi
0x1800dc591  pop     rbx
0x1800dc592  pop     rbp
0x1800dc593  retn
```
