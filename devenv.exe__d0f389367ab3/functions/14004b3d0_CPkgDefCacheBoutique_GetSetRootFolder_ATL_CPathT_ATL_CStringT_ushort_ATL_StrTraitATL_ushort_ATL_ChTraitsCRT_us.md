# CPkgDefCacheBoutique::GetSetRootFolder(ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> const &,ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>> const &)

- ea: `0x14004b3d0`
- end: `0x14004b5e2`
- name: `?GetSetRootFolder@CPkgDefCacheBoutique@@UEAAAEAV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@AEBV23@0@Z`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140002c10`
- `0x140003160`
- `0x140004950`
- `0x14001c8f8`
- `0x14002a644`
- `0x140033ab0`
- `0x14004b1b0`
- `0x14004b3d0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004b5b9`
- `ADVAPI32!RegCloseKey` at `0x14004b5b9`
- `ADVAPI32!RegOpenKeyExW` at `0x14004b4c2`
- `ADVAPI32!RegOpenKeyExW` at `0x14004b4c2`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004b48f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004b48f`
- `ADVAPI32!RevertToSelf` at `0x14004b585`
- `ADVAPI32!RevertToSelf` at `0x14004b585`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CPkgDefCacheBoutique::GetSetRootFolder(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v4; // rdi
  __int64 v5; // rax
  _QWORD *v6; // rdx
  struct ATL::IAtlStringMgr *Instance; // rax
  bool v8; // bl
  LSTATUS v9; // eax
  int RegistryValue; // esi
  HKEY v11; // rdx
  HKEY v12; // rdx
  _QWORD *v13; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v17; // [rsp+48h] [rbp-8h]
  __int64 v18; // [rsp+70h] [rbp+20h] BYREF
  __int64 v19; // [rsp+88h] [rbp+38h] BYREF

  v4 = a1 + 104;
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 104) - 16LL) )
    return v4;
  if ( *(_DWORD *)(*a2 - 16LL) )
  {
    ATL::CSimpleStringT<unsigned short,0>::operator=(a1 + 104, a2);
    return v4;
  }
  v5 = RemoveCommon7IDE(&v18, *a3);
  ATL::CSimpleStringT<unsigned short,0>::operator=(v4, v5);
  v6 = (_QWORD *)(v18 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
  }
  *(_OWORD *)hKey = 0;
  v17 = 0;
  hKey[0] = 0;
  LODWORD(hKey[1]) = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v19 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  v8 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 224));
  LOBYTE(v18) = v8;
  phkResult = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(a1 + 136), 0, 0x20019u, &phkResult);
  if ( !v9 )
  {
    hKey[0] = phkResult;
    LODWORD(hKey[1]) = 0;
LABEL_10:
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &phkResult,
      L"RootFolder");
    RegistryValue = GetRegistryValue(hKey, &phkResult, &v19);
    v11 = phkResult - 6;
    if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
    }
    if ( RegistryValue >= 0 )
    {
      if ( *(_DWORD *)(v19 - 16) )
      {
        if ( (int)GetCanonicalName(&v19) >= 0 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &phkResult,
            v19);
          ATL::CSimpleStringT<unsigned short,0>::operator=(v4, &phkResult);
          v12 = phkResult - 6;
          if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
          }
        }
      }
    }
    goto LABEL_17;
  }
  if ( v9 >= 0 )
    goto LABEL_10;
LABEL_17:
  if ( v8 )
    RevertToSelf();
  v13 = (_QWORD *)(v19 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v19 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v4;
}

```

## disassembly

```asm
0x14004b3d0  mov     [rsp-18h+arg_8], rbx
0x14004b3d5  mov     [rsp-18h+arg_10], rsi
0x14004b3da  push    rbp
0x14004b3db  push    rdi
0x14004b3dc  push    r15
0x14004b3de  mov     rbp, rsp
0x14004b3e1  sub     rsp, 50h
0x14004b3e5  mov     rsi, rcx
0x14004b3e8  lea     rdi, [rcx+68h]
0x14004b3ec  mov     r9, [rdi]
0x14004b3ef  cmp     dword ptr [r9-10h], 0
0x14004b3f4  jnz     loc_14004B5BF
0x14004b3fa  mov     r9, [rdx]
0x14004b3fd  cmp     dword ptr [r9-10h], 0
0x14004b402  jz      short loc_14004B411
0x14004b404  mov     rcx, rdi
0x14004b407  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14004b40c  jmp     loc_14004B5BF
0x14004b411  mov     rdx, [r8]
0x14004b414  lea     rcx, [rbp+arg_0]
0x14004b418  call    ?RemoveCommon7IDE@@YA?AV?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@PEBG@Z; RemoveCommon7IDE(ushort const *)
0x14004b41d  nop
0x14004b41e  mov     rdx, rax
0x14004b421  mov     rcx, rdi
0x14004b424  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14004b429  nop
0x14004b42a  mov     rdx, [rbp+arg_0]
0x14004b42e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004b432  or      r15d, 0FFFFFFFFh
0x14004b436  mov     eax, r15d
0x14004b439  lock xadd [rdx+10h], eax
0x14004b43e  add     eax, r15d
0x14004b441  test    eax, eax
0x14004b443  jg      short loc_14004B451
0x14004b445  lfence
0x14004b448  mov     rcx, [rdx]
0x14004b44b  mov     rax, [rcx]
0x14004b44e  call    qword ptr [rax+8]
0x14004b451  xorps   xmm0, xmm0
0x14004b454  xor     eax, eax
0x14004b456  movups  xmmword ptr [rbp+hKey], xmm0
0x14004b45a  mov     [rbp+var_8], rax
0x14004b45e  and     [rbp+hKey], rax
0x14004b462  and     dword ptr [rbp+hKey+8], eax
0x14004b465  and     [rbp+var_8], rax
0x14004b469  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004b46e  mov     rcx, rax
0x14004b471  test    rax, rax
0x14004b474  jz      loc_14004B5D7
0x14004b47a  mov     rax, [rax]
0x14004b47d  call    qword ptr [rax+18h]
0x14004b480  add     rax, 18h
0x14004b484  mov     [rbp+arg_18], rax
0x14004b488  mov     rcx, [rsi+0E0h]; hToken
0x14004b48f  call    cs:__imp_ImpersonateLoggedOnUser
0x14004b495  test    eax, eax
0x14004b497  setnz   bl
0x14004b49a  mov     byte ptr [rbp+arg_0], bl
0x14004b49d  and     [rbp+var_20], 0
0x14004b4a2  lea     rax, [rbp+var_20]
0x14004b4a6  mov     [rsp+50h+phkResult], rax; phkResult
0x14004b4ab  mov     r9d, 20019h; samDesired
0x14004b4b1  xor     r8d, r8d; ulOptions
0x14004b4b4  mov     rdx, [rsi+88h]; lpSubKey
0x14004b4bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004b4c2  call    cs:__imp_RegOpenKeyExW
0x14004b4c8  test    eax, eax
0x14004b4ca  jnz     short loc_14004B4DA
0x14004b4cc  mov     rax, [rbp+var_20]
0x14004b4d0  mov     [rbp+hKey], rax
0x14004b4d4  and     dword ptr [rbp+hKey+8], 0
0x14004b4d8  jmp     short loc_14004B4E0
0x14004b4da  js      loc_14004B581
0x14004b4e0  lea     rdx, aRootfolder_0; "RootFolder"
0x14004b4e7  lea     rcx, [rbp+var_20]
0x14004b4eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004b4f0  lea     r8, [rbp+arg_18]
0x14004b4f4  lea     rdx, [rbp+var_20]
0x14004b4f8  lea     rcx, [rbp+hKey]
0x14004b4fc  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14004b501  mov     esi, eax
0x14004b503  mov     rdx, [rbp+var_20]
0x14004b507  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004b50b  mov     ecx, r15d
0x14004b50e  lock xadd [rdx+10h], ecx
0x14004b513  add     ecx, r15d
0x14004b516  test    ecx, ecx
0x14004b518  jg      short loc_14004B527
0x14004b51a  lfence
0x14004b51d  mov     rcx, [rdx]
0x14004b520  mov     r8, [rcx]
0x14004b523  call    qword ptr [r8+8]
0x14004b527  test    esi, esi
0x14004b529  js      short loc_14004B581
0x14004b52b  mov     rax, [rbp+arg_18]
0x14004b52f  cmp     dword ptr [rax-10h], 0
0x14004b533  jz      short loc_14004B581
0x14004b535  lea     rcx, [rbp+arg_18]
0x14004b539  call    ?GetCanonicalName@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetCanonicalName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14004b53e  test    eax, eax
0x14004b540  js      short loc_14004B581
0x14004b542  mov     rdx, [rbp+arg_18]
0x14004b546  lea     rcx, [rbp+var_20]
0x14004b54a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14004b54f  nop
0x14004b550  lea     rdx, [rbp+var_20]
0x14004b554  mov     rcx, rdi
0x14004b557  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14004b55c  nop
0x14004b55d  mov     rdx, [rbp+var_20]
0x14004b561  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004b565  mov     eax, r15d
0x14004b568  lock xadd [rdx+10h], eax
0x14004b56d  add     eax, r15d
0x14004b570  test    eax, eax
0x14004b572  jg      short loc_14004B581
0x14004b574  lfence
0x14004b577  mov     rcx, [rdx]
0x14004b57a  mov     rax, [rcx]
0x14004b57d  call    qword ptr [rax+8]
0x14004b580  nop
0x14004b581  test    bl, bl
0x14004b583  jz      short loc_14004B58C
0x14004b585  call    cs:__imp_RevertToSelf
0x14004b58b  nop
0x14004b58c  mov     rdx, [rbp+arg_18]
0x14004b590  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004b594  mov     eax, r15d
0x14004b597  lock xadd [rdx+10h], eax
0x14004b59c  add     eax, r15d
0x14004b59f  test    eax, eax
0x14004b5a1  jg      short loc_14004B5B0
0x14004b5a3  lfence
0x14004b5a6  mov     rcx, [rdx]
0x14004b5a9  mov     rax, [rcx]
0x14004b5ac  call    qword ptr [rax+8]
0x14004b5af  nop
0x14004b5b0  mov     rcx, [rbp+hKey]; hKey
0x14004b5b4  test    rcx, rcx
0x14004b5b7  jz      short loc_14004B5BF
0x14004b5b9  call    cs:__imp_RegCloseKey
0x14004b5bf  mov     rax, rdi
0x14004b5c2  lea     r11, [rsp+50h+var_s0]
0x14004b5c7  mov     rbx, [r11+28h]
0x14004b5cb  mov     rsi, [r11+30h]
0x14004b5cf  mov     rsp, r11
0x14004b5d2  pop     r15
0x14004b5d4  pop     rdi
0x14004b5d5  pop     rbp
0x14004b5d6  retn
0x14004b5d7  mov     ecx, 80004005h; int
0x14004b5dc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
