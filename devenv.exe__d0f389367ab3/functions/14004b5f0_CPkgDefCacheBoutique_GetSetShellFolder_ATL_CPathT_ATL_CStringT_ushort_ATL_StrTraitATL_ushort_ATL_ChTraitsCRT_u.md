# CPkgDefCacheBoutique::GetSetShellFolder(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> const &)

- ea: `0x14004b5f0`
- end: `0x14004b85c`
- name: `?GetSetShellFolder@CPkgDefCacheBoutique@@UEAAAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@AEBV23@@Z`
- size: `620`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140002c10`
- `0x140003160`
- `0x140004950`
- `0x140008120`
- `0x14001c8f8`
- `0x14002a644`
- `0x140033ab0`
- `0x14004b1b0`
- `0x14004b5f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004b819`
- `ADVAPI32!RegCloseKey` at `0x14004b819`
- `ADVAPI32!RegOpenKeyExW` at `0x14004b6fc`
- `ADVAPI32!RegOpenKeyExW` at `0x14004b6fc`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004b6c9`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004b6c9`
- `ADVAPI32!RevertToSelf` at `0x14004b7c4`
- `ADVAPI32!RevertToSelf` at `0x14004b7c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPkgDefCacheBoutique::GetSetShellFolder(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rax
  _QWORD *v5; // rdx
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v7; // rax
  bool v8; // bl
  LPCWSTR v9; // rdi
  LSTATUS v10; // eax
  int RegistryValue; // r14d
  HKEY v12; // rdx
  HKEY v13; // rdx
  _QWORD *v14; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h]
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  __int64 v20; // [rsp+90h] [rbp+40h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp+48h] BYREF

  v3 = a1 + 112;
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 112) - 16LL) )
    return v3;
  v4 = RemoveCommon7IDE(&v19, *a2);
  ATL::CSimpleStringT<unsigned short,0>::operator=(v3, v4);
  v5 = (_QWORD *)(v19 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v19 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  }
  *(_OWORD *)hKey = 0;
  v18 = 0;
  hKey[0] = 0;
  LODWORD(hKey[1]) = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v20 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  v7 = ATL::CAtlStringMgr::GetInstance();
  if ( !v7 )
    ATL::AtlThrowImpl(-2147467259);
  lpSubKey = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v7 + 24LL))(v7) + 24);
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
    &lpSubKey,
    L"Software\\Microsoft\\AppEnv",
    *(_QWORD *)(a1 + 384));
  v8 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 224));
  LOBYTE(v19) = v8;
  phkResult = 0;
  v9 = lpSubKey;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v10 )
  {
    hKey[0] = phkResult;
    LODWORD(hKey[1]) = 0;
LABEL_9:
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &phkResult,
      L"ShellFolder");
    RegistryValue = GetRegistryValue(hKey, &phkResult, &v20);
    v12 = phkResult - 6;
    if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
    }
    if ( RegistryValue >= 0 )
    {
      if ( *(_DWORD *)(v20 - 16) )
      {
        if ( (int)GetCanonicalName(&v20) >= 0 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &phkResult,
            v20);
          ATL::CSimpleStringT<unsigned short,0>::operator=(v3, &phkResult);
          v13 = phkResult - 6;
          if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
          }
        }
      }
    }
    goto LABEL_16;
  }
  if ( v10 >= 0 )
    goto LABEL_9;
LABEL_16:
  if ( v8 )
    RevertToSelf();
  if ( _InterlockedDecrement((volatile signed __int32 *)v9 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 - 3) + 8LL))(*((_QWORD *)v9 - 3));
  }
  v14 = (_QWORD *)(v20 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v20 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v3;
}

```

## disassembly

```asm
0x14004b5f0  mov     [rsp-28h+arg_8], rbx
0x14004b5f5  push    rbp
0x14004b5f6  push    rsi
0x14004b5f7  push    rdi
0x14004b5f8  push    r12
0x14004b5fa  push    r14
0x14004b5fc  mov     rbp, rsp
0x14004b5ff  sub     rsp, 50h
0x14004b603  mov     rbx, rcx
0x14004b606  lea     rsi, [rcx+70h]
0x14004b60a  mov     rax, [rsi]
0x14004b60d  cmp     dword ptr [rax-10h], 0
0x14004b611  jnz     loc_14004B81F
0x14004b617  mov     rdx, [rdx]
0x14004b61a  lea     rcx, [rbp+arg_0]
0x14004b61e  call    ?RemoveCommon7IDE@@YA?AV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@PEBG@Z; RemoveCommon7IDE(ushort const *)
0x14004b623  mov     rdx, rax
0x14004b626  mov     rcx, rsi
0x14004b629  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14004b62e  mov     rdx, [rbp+arg_0]
0x14004b632  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004b636  or      r12d, 0FFFFFFFFh
0x14004b63a  mov     eax, r12d
0x14004b63d  lock xadd [rdx+10h], eax
0x14004b642  add     eax, r12d
0x14004b645  test    eax, eax
0x14004b647  jg      short loc_14004B655
0x14004b649  lfence
0x14004b64c  mov     rcx, [rdx]
0x14004b64f  mov     rax, [rcx]
0x14004b652  call    qword ptr [rax+8]
0x14004b655  xorps   xmm0, xmm0
0x14004b658  xor     eax, eax
0x14004b65a  movups  xmmword ptr [rbp+hKey], xmm0
0x14004b65e  mov     [rbp+var_8], rax
0x14004b662  and     [rbp+hKey], rax
0x14004b666  and     dword ptr [rbp+hKey+8], eax
0x14004b669  and     [rbp+var_8], rax
0x14004b66d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004b672  mov     rcx, rax
0x14004b675  test    rax, rax
0x14004b678  jz      loc_14004B851
0x14004b67e  mov     rax, [rax]
0x14004b681  call    qword ptr [rax+18h]
0x14004b684  add     rax, 18h
0x14004b688  mov     [rbp+arg_10], rax
0x14004b68c  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004b691  mov     rcx, rax
0x14004b694  test    rax, rax
0x14004b697  jz      loc_14004B836
0x14004b69d  mov     rax, [rax]
0x14004b6a0  call    qword ptr [rax+18h]
0x14004b6a3  add     rax, 18h
0x14004b6a7  mov     [rbp+lpSubKey], rax
0x14004b6ab  mov     r8, [rbx+180h]
0x14004b6b2  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\AppEnv"
0x14004b6b9  lea     rcx, [rbp+lpSubKey]
0x14004b6bd  call    ?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)
0x14004b6c2  mov     rcx, [rbx+0E0h]; hToken
0x14004b6c9  call    cs:__imp_ImpersonateLoggedOnUser
0x14004b6cf  test    eax, eax
0x14004b6d1  setnz   bl
0x14004b6d4  mov     byte ptr [rbp+arg_0], bl
0x14004b6d7  and     [rbp+var_20], 0
0x14004b6dc  lea     rax, [rbp+var_20]
0x14004b6e0  mov     [rsp+50h+phkResult], rax; phkResult
0x14004b6e5  mov     r9d, 20019h; samDesired
0x14004b6eb  xor     r8d, r8d; ulOptions
0x14004b6ee  mov     rdi, [rbp+lpSubKey]
0x14004b6f2  mov     rdx, rdi; lpSubKey
0x14004b6f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004b6fc  call    cs:__imp_RegOpenKeyExW
0x14004b702  test    eax, eax
0x14004b704  jnz     short loc_14004B714
0x14004b706  mov     rax, [rbp+var_20]
0x14004b70a  mov     [rbp+hKey], rax
0x14004b70e  and     dword ptr [rbp+hKey+8], 0
0x14004b712  jmp     short loc_14004B71A
0x14004b714  js      loc_14004B7C0
0x14004b71a  lea     rdx, aShellfolder; "ShellFolder"
0x14004b721  lea     rcx, [rbp+var_20]
0x14004b725  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004b72a  lea     r8, [rbp+arg_10]
0x14004b72e  lea     rdx, [rbp+var_20]
0x14004b732  lea     rcx, [rbp+hKey]
0x14004b736  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14004b73b  mov     r14d, eax
0x14004b73e  mov     rdx, [rbp+var_20]
0x14004b742  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004b746  mov     ecx, r12d
0x14004b749  lock xadd [rdx+10h], ecx
0x14004b74e  add     ecx, r12d
0x14004b751  test    ecx, ecx
0x14004b753  jg      short loc_14004B762
0x14004b755  lfence
0x14004b758  mov     rcx, [rdx]
0x14004b75b  mov     r8, [rcx]
0x14004b75e  call    qword ptr [r8+8]
0x14004b762  test    r14d, r14d
0x14004b765  js      short loc_14004B7C0
0x14004b767  mov     rax, [rbp+arg_10]
0x14004b76b  cmp     dword ptr [rax-10h], 0
0x14004b76f  jz      short loc_14004B7C0
0x14004b771  lea     rcx, [rbp+arg_10]
0x14004b775  call    ?GetCanonicalName@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetCanonicalName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14004b77a  test    eax, eax
0x14004b77c  js      short loc_14004B7C0
0x14004b77e  mov     rdx, [rbp+arg_10]
0x14004b782  lea     rcx, [rbp+var_20]
0x14004b786  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004b78b  nop
0x14004b78c  lea     rdx, [rbp+var_20]
0x14004b790  mov     rcx, rsi
0x14004b793  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14004b798  nop
0x14004b799  mov     rdx, [rbp+var_20]
0x14004b79d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004b7a1  mov     eax, r12d
0x14004b7a4  lock xadd [rdx+10h], eax
0x14004b7a9  add     eax, r12d
0x14004b7ac  test    eax, eax
0x14004b7ae  jg      short loc_14004B7C0
0x14004b7b0  lfence
0x14004b7b3  mov     rcx, [rdx]
0x14004b7b6  mov     rax, [rcx]
0x14004b7b9  call    qword ptr [rax+8]
0x14004b7bc  nop
0x14004b7bd  nop     dword ptr [rax]
0x14004b7c0  test    bl, bl
0x14004b7c2  jz      short loc_14004B7CB
0x14004b7c4  call    cs:__imp_RevertToSelf
0x14004b7ca  nop
0x14004b7cb  lea     rdx, [rdi-18h]
0x14004b7cf  mov     eax, r12d
0x14004b7d2  lock xadd [rdx+10h], eax
0x14004b7d7  add     eax, r12d
0x14004b7da  test    eax, eax
0x14004b7dc  jg      short loc_14004B7EB
0x14004b7de  lfence
0x14004b7e1  mov     rcx, [rdx]
0x14004b7e4  mov     rax, [rcx]
0x14004b7e7  call    qword ptr [rax+8]
0x14004b7ea  nop
0x14004b7eb  mov     rdx, [rbp+arg_10]
0x14004b7ef  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004b7f3  mov     eax, r12d
0x14004b7f6  lock xadd [rdx+10h], eax
0x14004b7fb  add     eax, r12d
0x14004b7fe  test    eax, eax
0x14004b800  jg      short loc_14004B810
0x14004b802  lfence
0x14004b805  mov     rcx, [rdx]
0x14004b808  mov     r8, [rcx]
0x14004b80b  call    qword ptr [r8+8]
0x14004b80f  nop
0x14004b810  mov     rcx, [rbp+hKey]; hKey
0x14004b814  test    rcx, rcx
0x14004b817  jz      short loc_14004B81F
0x14004b819  call    cs:__imp_RegCloseKey
0x14004b81f  mov     rax, rsi
0x14004b822  mov     rbx, [rsp+50h+arg_8]
0x14004b82a  add     rsp, 50h
0x14004b82e  pop     r14
0x14004b830  pop     r12
0x14004b832  pop     rdi
0x14004b833  pop     rsi
0x14004b834  pop     rbp
0x14004b835  retn
0x14004b836  mov     ecx, 80004005h; int
0x14004b83b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004b851  mov     ecx, 80004005h; int
0x14004b856  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
