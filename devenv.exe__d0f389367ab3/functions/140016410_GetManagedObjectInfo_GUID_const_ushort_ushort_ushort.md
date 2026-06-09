# GetManagedObjectInfo(_GUID const &,ushort * *,ushort * *,ushort * *)

- ea: `0x140016410`
- end: `0x14001663e`
- name: `?GetManagedObjectInfo@@YAHAEBU_GUID@@PEAPEAG11@Z`
- size: `558`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002d3e0`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140004950`
- `0x140016410`
- `0x14001c380`
- `0x14002fa90`
- `0x140033ab0`
- `0x14006ae20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400165dd`
- `ADVAPI32!RegCloseKey` at `0x1400165ec`
- `ADVAPI32!RegCloseKey` at `0x1400165dd`
- `ADVAPI32!RegCloseKey` at `0x1400165ec`
- `ADVAPI32!RegOpenKeyExW` at `0x140016512`
- `ADVAPI32!RegOpenKeyExW` at `0x140016569`
- `ADVAPI32!RegOpenKeyExW` at `0x140016512`
- `ADVAPI32!RegOpenKeyExW` at `0x140016569`
- `ole32!StringFromCLSID` at `0x140016476`
- `ole32!StringFromCLSID` at `0x140016476`
- `ole32!CoTaskMemFree` at `0x1400165ce`
- `ole32!CoTaskMemFree` at `0x1400165ce`

## string_xrefs

- `0x140016488`: `\CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetManagedObjectInfo(
        IID *rclsid,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  unsigned int v8; // r15d
  struct ATL::IAtlStringMgr *Instance; // rax
  const WCHAR *v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rdx
  __int64 v13; // r8
  HKEY v14; // rcx
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-20h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-18h] BYREF

  v8 = 0;
  hKey = 0;
  phkResult = 0;
  lpsz = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v10 = (const WCHAR *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                      + 24);
  lpSubKey = v10;
  if ( StringFromCLSID(rclsid, &lpsz) >= 0 )
  {
    v11 = ATL::operator+(&v17, &detail::strRegistryRoot, L"\\CLSID\\");
    ATL::CSimpleStringT<unsigned short,0>::operator=(&lpSubKey, v11);
    v12 = (_QWORD *)(v17 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v17 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
    }
    if ( lpsz )
    {
      v13 = -1;
      do
        ++v13;
      while ( lpsz[v13] );
    }
    else
    {
      v13 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, lpsz, v13);
    v10 = lpSubKey;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
      goto LABEL_16;
    if ( (unsigned int)GetResourceString(hKey, L"Class", a4) )
    {
      GetResourceString(hKey, L"Assembly", a3);
      v14 = hKey;
    }
    else
    {
      if ( RegOpenKeyExW(hKey, L"InprocServer32", 0, 0x20019u, &phkResult)
        || !(unsigned int)GetResourceString(phkResult, L"Class", a4) )
      {
LABEL_16:
        if ( *a4 && (*a3 || *a2) )
          v8 = 1;
        goto LABEL_20;
      }
      GetResourceString(phkResult, L"Assembly", a3);
      v14 = phkResult;
    }
    GetResourceString(v14, L"CodeBase", a2);
    goto LABEL_16;
  }
LABEL_20:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( _InterlockedDecrement((volatile signed __int32 *)v10 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
  }
  return v8;
}

```

## disassembly

```asm
0x140016410  push    rbp
0x140016412  push    rbx
0x140016413  push    rsi
0x140016414  push    rdi
0x140016415  push    r12
0x140016417  push    r13
0x140016419  push    r14
0x14001641b  push    r15
0x14001641d  mov     rbp, rsp
0x140016420  sub     rsp, 68h
0x140016424  mov     rax, cs:__security_cookie
0x14001642b  xor     rax, rsp
0x14001642e  mov     [rbp+var_10], rax
0x140016432  mov     rdi, r9
0x140016435  mov     r14, r8
0x140016438  mov     rsi, rdx
0x14001643b  mov     r12, rcx
0x14001643e  xor     r13d, r13d
0x140016441  mov     r15d, r13d
0x140016444  mov     [rbp+hKey], r13
0x140016448  mov     [rbp+var_20], r13
0x14001644c  mov     [rbp+lpsz], r13
0x140016450  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140016455  mov     rcx, rax
0x140016458  test    rax, rax
0x14001645b  jz      loc_140016633
0x140016461  mov     rax, [rax]
0x140016464  call    qword ptr [rax+18h]
0x140016467  lea     rbx, [rax+18h]
0x14001646b  mov     [rbp+lpSubKey], rbx
0x14001646f  lea     rdx, [rbp+lpsz]; lplpsz
0x140016473  mov     rcx, r12; rclsid
0x140016476  call    cs:__imp_StringFromCLSID
0x14001647c  or      r12, 0FFFFFFFFFFFFFFFFh
0x140016480  test    eax, eax
0x140016482  js      loc_1400165C5
0x140016488  lea     r8, aClsid_0; "\\CLSID\\"
0x14001648f  lea     rdx, ?strRegistryRoot@detail@@3V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@A; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> detail::strRegistryRoot
0x140016496  lea     rcx, [rbp+var_30]
0x14001649a  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001649f  mov     rdx, rax
0x1400164a2  lea     rcx, [rbp+lpSubKey]
0x1400164a6  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400164ab  mov     rdx, [rbp+var_30]
0x1400164af  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400164b3  mov     eax, r12d
0x1400164b6  lock xadd [rdx+10h], eax
0x1400164bb  add     eax, r12d
0x1400164be  test    eax, eax
0x1400164c0  jg      short loc_1400164CE
0x1400164c2  lfence
0x1400164c5  mov     rcx, [rdx]
0x1400164c8  mov     rax, [rcx]
0x1400164cb  call    qword ptr [rax+8]
0x1400164ce  mov     rdx, [rbp+lpsz]
0x1400164d2  test    rdx, rdx
0x1400164d5  jnz     short loc_1400164DC
0x1400164d7  mov     r8d, r13d
0x1400164da  jmp     short loc_1400164E9
0x1400164dc  mov     r8, r12
0x1400164df  inc     r8
0x1400164e2  cmp     [rdx+r8*2], r13w
0x1400164e7  jnz     short loc_1400164DF
0x1400164e9  lea     rcx, [rbp+lpSubKey]
0x1400164ed  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400164f2  lea     rax, [rbp+hKey]
0x1400164f6  mov     [rsp+68h+phkResult], rax; phkResult
0x1400164fb  mov     r9d, 20019h; samDesired
0x140016501  xor     r8d, r8d; ulOptions
0x140016504  mov     rbx, [rbp+lpSubKey]
0x140016508  mov     rdx, rbx; lpSubKey
0x14001650b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140016512  call    cs:__imp_RegOpenKeyExW
0x140016518  test    eax, eax
0x14001651a  jnz     loc_1400165B0
0x140016520  mov     r8, rdi; unsigned __int16 **
0x140016523  lea     rdx, aClass; "Class"
0x14001652a  mov     rcx, [rbp+hKey]; hKey
0x14001652e  call    ?GetResourceString@@YAHPEAUHKEY__@@PEBGPEAPEAG@Z; GetResourceString(HKEY__ *,ushort const *,ushort * *)
0x140016533  mov     rcx, [rbp+hKey]; hKey
0x140016537  test    eax, eax
0x140016539  jz      short loc_140016550
0x14001653b  mov     r8, r14; unsigned __int16 **
0x14001653e  lea     rdx, aAssembly; "Assembly"
0x140016545  call    ?GetResourceString@@YAHPEAUHKEY__@@PEBGPEAPEAG@Z; GetResourceString(HKEY__ *,ushort const *,ushort * *)
0x14001654a  mov     rcx, [rbp+hKey]
0x14001654e  jmp     short loc_1400165A1
0x140016550  lea     rax, [rbp+var_20]
0x140016554  mov     [rsp+68h+phkResult], rax; phkResult
0x140016559  mov     r9d, 20019h; samDesired
0x14001655f  xor     r8d, r8d; ulOptions
0x140016562  lea     rdx, aInprocserver32; "InprocServer32"
0x140016569  call    cs:__imp_RegOpenKeyExW
0x14001656f  test    eax, eax
0x140016571  jnz     short loc_1400165B0
0x140016573  mov     r8, rdi; unsigned __int16 **
0x140016576  lea     rdx, aClass; "Class"
0x14001657d  mov     rcx, [rbp+var_20]; hKey
0x140016581  call    ?GetResourceString@@YAHPEAUHKEY__@@PEBGPEAPEAG@Z; GetResourceString(HKEY__ *,ushort const *,ushort * *)
0x140016586  test    eax, eax
0x140016588  jz      short loc_1400165B0
0x14001658a  mov     r8, r14; unsigned __int16 **
0x14001658d  lea     rdx, aAssembly; "Assembly"
0x140016594  mov     rcx, [rbp+var_20]; hKey
0x140016598  call    ?GetResourceString@@YAHPEAUHKEY__@@PEBGPEAPEAG@Z; GetResourceString(HKEY__ *,ushort const *,ushort * *)
0x14001659d  mov     rcx, [rbp+var_20]; hKey
0x1400165a1  mov     r8, rsi; unsigned __int16 **
0x1400165a4  lea     rdx, aCodebase_0; "CodeBase"
0x1400165ab  call    ?GetResourceString@@YAHPEAUHKEY__@@PEBGPEAPEAG@Z; GetResourceString(HKEY__ *,ushort const *,ushort * *)
0x1400165b0  cmp     [rdi], r13
0x1400165b3  jz      short loc_1400165C5
0x1400165b5  cmp     [r14], r13
0x1400165b8  jnz     short loc_1400165BF
0x1400165ba  cmp     [rsi], r13
0x1400165bd  jz      short loc_1400165C5
0x1400165bf  mov     r15d, 1
0x1400165c5  mov     rcx, [rbp+lpsz]; pv
0x1400165c9  test    rcx, rcx
0x1400165cc  jz      short loc_1400165D4
0x1400165ce  call    cs:__imp_CoTaskMemFree
0x1400165d4  mov     rcx, [rbp+hKey]; hKey
0x1400165d8  test    rcx, rcx
0x1400165db  jz      short loc_1400165E3
0x1400165dd  call    cs:__imp_RegCloseKey
0x1400165e3  mov     rcx, [rbp+var_20]; hKey
0x1400165e7  test    rcx, rcx
0x1400165ea  jz      short loc_1400165F3
0x1400165ec  call    cs:__imp_RegCloseKey
0x1400165f2  nop
0x1400165f3  lea     rdx, [rbx-18h]
0x1400165f7  mov     ecx, r12d
0x1400165fa  lock xadd [rdx+10h], ecx
0x1400165ff  add     ecx, r12d
0x140016602  test    ecx, ecx
0x140016604  jg      short loc_140016613
0x140016606  lfence
0x140016609  mov     rcx, [rdx]
0x14001660c  mov     r8, [rcx]
0x14001660f  call    qword ptr [r8+8]
0x140016613  mov     eax, r15d
0x140016616  mov     rcx, [rbp+var_10]
0x14001661a  xor     rcx, rsp; StackCookie
0x14001661d  call    __security_check_cookie
0x140016622  add     rsp, 68h
0x140016626  pop     r15
0x140016628  pop     r14
0x14001662a  pop     r13
0x14001662c  pop     r12
0x14001662e  pop     rdi
0x14001662f  pop     rsi
0x140016630  pop     rbx
0x140016631  pop     rbp
0x140016632  retn
0x140016633  mov     ecx, 80004005h; int
0x140016638  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
