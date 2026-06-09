# CGlobalPersistence::LoadAll(CDeliveryOptimizationManager const &)

- ea: `0x18009f3b8`
- end: `0x18009f63a`
- name: `?LoadAll@CGlobalPersistence@@SAXAEBVCDeliveryOptimizationManager@@@Z`
- size: `642`
- prototype: `void __fastcall(const struct CDeliveryOptimizationManager *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18007d520`

## callees

- `0x1800095a0`
- `0x18000d228`
- `0x1800199fc`
- `0x180019b18`
- `0x180096370`
- `0x18009b290`
- `0x18009f3b8`
- `0x18009f848`
- `0x18009ff78`
- `0x1800a0100`
- `0x1800a0288`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x18009f49a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x18009f5b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x18009f5f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x18009f49a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x18009f5b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x18009f5f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeA` at `0x18009f633`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall CGlobalPersistence::LoadAll(const struct CDeliveryOptimizationManager *a1)
{
  const char *SwarmsRegPath; // rbx
  struct CPersistenceLocation *v3; // rax
  CDownloadManager *v4; // rdi
  const char *JobsRegPath; // rbx
  struct CPersistenceLocation *v6; // rax
  const CHAR *v7; // rbx
  struct CPersistenceLocation *v8; // rax
  struct CPersistenceLocation *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rcx
  __int128 *p_Src; // rax
  __int128 *appended; // rax
  __int64 v14; // rax
  const CHAR *v15; // rbx
  struct CPersistenceLocation *v16; // rax
  const CHAR *v17; // rbx
  struct CPersistenceLocation *v18; // rax
  const CHAR *SourcesRegPath; // rbx
  struct CPersistenceLocation *v20; // rax
  __int128 Src; // [rsp+38h] [rbp-9h] BYREF
  __int128 v22; // [rsp+48h] [rbp+7h]
  LPCSTR lpSubKey[2]; // [rsp+58h] [rbp+17h] BYREF
  __int128 v24; // [rsp+68h] [rbp+27h]
  __int128 v25; // [rsp+78h] [rbp+37h] BYREF
  __int128 v26; // [rsp+88h] [rbp+47h]

  *(_QWORD *)&Src = *((_QWORD *)a1 + 22);
  *((_QWORD *)&Src + 1) = *((_QWORD *)a1 + 4);
  CCorePersistence::LoadSwarms_::_2_::_lambda_1_::operator()(&Src, CAppRegistryHive::_shDOSubKey, "Swarms");
  SwarmsRegPath = CSysRegistryEntityLocation::GetSwarmsRegPath();
  v3 = CPersistenceLocation::Instance();
  CCorePersistence::LoadSwarms_::_2_::_lambda_1_::operator()(
    &Src,
    -(__int64)(*((_BYTE *)v3 + 160) != 0) - 2147483645,
    SwarmsRegPath);
  CDownloadManager::ReloadDownloads(*((CDownloadManager **)a1 + 5), CAppRegistryHive::_shDOSubKey, "Jobs");
  if ( CAppRegistryHive::_fUsingPrivateHive )
  {
    v4 = (CDownloadManager *)*((_QWORD *)a1 + 5);
    JobsRegPath = CSysRegistryEntityLocation::GetJobsRegPath();
    v6 = CPersistenceLocation::Instance();
    CDownloadManager::ReloadDownloads(v4, (HKEY)(-2147483645LL - (*((_BYTE *)v6 + 160) != 0)), JobsRegPath);
    v7 = CSysRegistryEntityLocation::GetJobsRegPath();
    v8 = CPersistenceLocation::Instance();
    RegDeleteTreeA((HKEY)(-2147483645LL - (*((_BYTE *)v8 + 160) != 0)), v7);
    v9 = CPersistenceLocation::Instance();
    if ( *((_QWORD *)v9 + 3) > 0xFu )
      v9 = *(struct CPersistenceLocation **)v9;
    Src = 0;
    v22 = 0;
    v10 = -1;
    do
      ++v10;
    while ( *((_BYTE *)v9 + v10) );
    std::string::_Construct<1,char const *>(&Src, v9);
    v11 = v22;
    if ( *((_QWORD *)&v22 + 1) == (_QWORD)v22 )
    {
      appended = (__int128 *)____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD_K___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEBD0_Z_PEBD_K_Z(
                               &Src,
                               1u);
    }
    else
    {
      *(_QWORD *)&v22 = v22 + 1;
      p_Src = &Src;
      if ( *((_QWORD *)&v22 + 1) > 0xFu )
        p_Src = (__int128 *)Src;
      *(_WORD *)((char *)p_Src + v11) = 92;
      appended = &Src;
    }
    v25 = 0;
    v26 = 0;
    v25 = *appended;
    v26 = appended[1];
    *((_QWORD *)appended + 3) = 15;
    *(_BYTE *)appended = 0;
    *((_QWORD *)appended + 2) = 0;
    v14 = std::string::append(&v25);
    *(_OWORD *)lpSubKey = 0;
    v24 = 0;
    *(_OWORD *)lpSubKey = *(_OWORD *)v14;
    v24 = *(_OWORD *)(v14 + 16);
    *(_BYTE *)v14 = 0;
    *(_QWORD *)(v14 + 16) = 0;
    *(_QWORD *)(v14 + 24) = 15;
    v15 = (const CHAR *)lpSubKey;
    if ( *((_QWORD *)&v24 + 1) > 0xFu )
      v15 = lpSubKey[0];
    v16 = CPersistenceLocation::Instance();
    RegDeleteTreeA((HKEY)(-2147483645LL - (*((_BYTE *)v16 + 160) != 0)), v15);
    std::string::~string(lpSubKey);
    std::string::~string(&v25);
    std::string::~string(&Src);
  }
  v17 = CSysRegistryEntityLocation::GetSwarmsRegPath();
  v18 = CPersistenceLocation::Instance();
  RegDeleteTreeA((HKEY)(-2147483645LL - (*((_BYTE *)v18 + 160) != 0)), v17);
  SourcesRegPath = CSysRegistryEntityLocation::GetSourcesRegPath();
  v20 = CPersistenceLocation::Instance();
  RegDeleteTreeA((HKEY)(-2147483645LL - (*((_BYTE *)v20 + 160) != 0)), SourcesRegPath);
}

```

## disassembly

```asm
0x18009f3b8  mov     rax, rsp
0x18009f3bb  mov     [rax+10h], rbx
0x18009f3bf  mov     [rax+18h], rdi
0x18009f3c3  mov     [rax+20h], r14
0x18009f3c7  push    rbp
0x18009f3c8  lea     rbp, [rax-5Fh]
0x18009f3cc  sub     rsp, 90h
0x18009f3d3  mov     rdi, rcx
0x18009f3d6  mov     rax, [rcx+0B0h]
0x18009f3dd  mov     qword ptr [rbp+57h+Src], rax
0x18009f3e1  mov     rax, [rcx+20h]
0x18009f3e5  mov     qword ptr [rbp+57h+Src+8], rax
0x18009f3e9  lea     r8, aSwarms; "Swarms"
0x18009f3f0  mov     rdx, cs:?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> CAppRegistryHive::_shDOSubKey
0x18009f3f7  lea     rcx, [rbp+57h+Src]
0x18009f3fb  call    _CCorePersistence__LoadSwarms____2____lambda_1___operator__
0x18009f400  call    ?GetSwarmsRegPath@CSysRegistryEntityLocation@@SAPEBDXZ; CSysRegistryEntityLocation::GetSwarmsRegPath(void)
0x18009f405  mov     rbx, rax
0x18009f408  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18009f40d  mov     cl, [rax+0A0h]
0x18009f413  neg     cl
0x18009f415  sbb     rdx, rdx
0x18009f418  mov     r14, 0FFFFFFFF80000003h
0x18009f41f  add     rdx, r14
0x18009f422  mov     r8, rbx
0x18009f425  lea     rcx, [rbp+57h+Src]
0x18009f429  call    _CCorePersistence__LoadSwarms____2____lambda_1___operator__
0x18009f42e  lea     r8, aJobs_0; "Jobs"
0x18009f435  mov     rdx, cs:?_shDOSubKey@CAppRegistryHive@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; HKEY
0x18009f43c  mov     rcx, [rdi+28h]; this
0x18009f440  call    ?ReloadDownloads@CDownloadManager@@QEAAXPEAUHKEY__@@PEBD@Z; CDownloadManager::ReloadDownloads(HKEY__ *,char const *)
0x18009f445  cmp     cs:?_fUsingPrivateHive@CAppRegistryHive@@0_NA, 0; bool CAppRegistryHive::_fUsingPrivateHive
0x18009f44c  jz      loc_18009F5D9
0x18009f452  mov     rdi, [rdi+28h]
0x18009f456  call    ?GetJobsRegPath@CSysRegistryEntityLocation@@SAPEBDXZ; CSysRegistryEntityLocation::GetJobsRegPath(void)
0x18009f45b  mov     rbx, rax
0x18009f45e  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18009f463  mov     dl, [rax+0A0h]
0x18009f469  neg     dl
0x18009f46b  sbb     rdx, rdx
0x18009f46e  add     rdx, r14; HKEY
0x18009f471  mov     r8, rbx; char *
0x18009f474  mov     rcx, rdi; this
0x18009f477  call    ?ReloadDownloads@CDownloadManager@@QEAAXPEAUHKEY__@@PEBD@Z; CDownloadManager::ReloadDownloads(HKEY__ *,char const *)
0x18009f47c  call    ?GetJobsRegPath@CSysRegistryEntityLocation@@SAPEBDXZ; CSysRegistryEntityLocation::GetJobsRegPath(void)
0x18009f481  mov     rbx, rax
0x18009f484  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18009f489  mov     cl, [rax+0A0h]
0x18009f48f  neg     cl
0x18009f491  sbb     rcx, rcx
0x18009f494  add     rcx, r14; hKey
0x18009f497  mov     rdx, rbx; lpSubKey
0x18009f49a  call    cs:__imp_RegDeleteTreeA
0x18009f4a0  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18009f4a5  mov     edi, 0Fh
0x18009f4aa  cmp     [rax+18h], rdi
0x18009f4ae  jbe     short loc_18009F4B3
0x18009f4b0  mov     rax, [rax]
0x18009f4b3  xorps   xmm0, xmm0
0x18009f4b6  movups  [rbp+57h+Src], xmm0
0x18009f4ba  xorps   xmm1, xmm1
0x18009f4bd  movdqu  [rbp+57h+var_50], xmm1
0x18009f4c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009f4c6  inc     r8
0x18009f4c9  cmp     byte ptr [rax+r8], 0
0x18009f4ce  jnz     short loc_18009F4C6
0x18009f4d0  mov     rdx, rax
0x18009f4d3  lea     rcx, [rbp+57h+Src]
0x18009f4d7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18009f4dc  nop
0x18009f4dd  mov     rcx, qword ptr [rbp+57h+var_50]
0x18009f4e1  mov     rax, qword ptr [rbp+57h+var_50+8]
0x18009f4e5  sub     rax, rcx
0x18009f4e8  mov     edx, 1
0x18009f4ed  cmp     rax, rdx
0x18009f4f0  jb      short loc_18009F513
0x18009f4f2  lea     rax, [rcx+1]
0x18009f4f6  mov     qword ptr [rbp+57h+var_50], rax
0x18009f4fa  lea     rax, [rbp+57h+Src]
0x18009f4fe  cmp     qword ptr [rbp+57h+var_50+8], rdi
0x18009f502  cmova   rax, qword ptr [rbp+57h+Src]
0x18009f507  mov     word ptr [rcx+rax], 5Ch ; '\'
0x18009f50d  lea     rax, [rbp+57h+Src]
0x18009f511  jmp     short loc_18009F528
0x18009f513  mov     [rsp+90h+Size], rdx; Size
0x18009f518  lea     r9, asc_180137948; "\\"
0x18009f51f  lea     rcx, [rbp+57h+Src]; Src
0x18009f523  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEBD0@Z@PEBD_K@Z; std::string::_Reallocate_grow_by<`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64>(unsigned __int64,`std::string::append(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *,unsigned __int64)
0x18009f528  xorps   xmm0, xmm0
0x18009f52b  movups  [rbp+57h+var_20], xmm0
0x18009f52f  xorps   xmm1, xmm1
0x18009f532  movdqu  [rbp+57h+var_10], xmm1
0x18009f537  movups  xmm0, xmmword ptr [rax]
0x18009f53a  movups  [rbp+57h+var_20], xmm0
0x18009f53e  movups  xmm1, xmmword ptr [rax+10h]
0x18009f542  movups  [rbp+57h+var_10], xmm1
0x18009f546  mov     [rax+18h], rdi
0x18009f54a  mov     byte ptr [rax], 0
0x18009f54d  mov     qword ptr [rax+10h], 0
0x18009f555  lea     rdx, aSwarms; "Swarms"
0x18009f55c  lea     rcx, [rbp+57h+var_20]; Src
0x18009f560  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::append(char const * const)
0x18009f565  xorps   xmm0, xmm0
0x18009f568  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18009f56c  xorps   xmm1, xmm1
0x18009f56f  movdqu  [rbp+57h+var_30], xmm1
0x18009f574  movups  xmm0, xmmword ptr [rax]
0x18009f577  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18009f57b  movups  xmm1, xmmword ptr [rax+10h]
0x18009f57f  movups  [rbp+57h+var_30], xmm1
0x18009f583  mov     byte ptr [rax], 0
0x18009f586  mov     qword ptr [rax+10h], 0
0x18009f58e  mov     [rax+18h], rdi
0x18009f592  lea     rbx, [rbp+57h+lpSubKey]
0x18009f596  cmp     qword ptr [rbp+57h+var_30+8], rdi
0x18009f59a  cmova   rbx, [rbp+57h+lpSubKey]
0x18009f59f  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18009f5a4  mov     cl, [rax+0A0h]
0x18009f5aa  neg     cl
0x18009f5ac  sbb     rcx, rcx
0x18009f5af  add     rcx, r14; hKey
0x18009f5b2  mov     rdx, rbx; lpSubKey
0x18009f5b5  call    cs:__imp_RegDeleteTreeA
0x18009f5bb  nop
0x18009f5bc  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18009f5c0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18009f5c5  nop
0x18009f5c6  lea     rcx, [rbp+57h+var_20]; void *
0x18009f5ca  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18009f5cf  nop
0x18009f5d0  lea     rcx, [rbp+57h+Src]; void *
0x18009f5d4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18009f5d9  call    ?GetSwarmsRegPath@CSysRegistryEntityLocation@@SAPEBDXZ; CSysRegistryEntityLocation::GetSwarmsRegPath(void)
0x18009f5de  mov     rbx, rax
0x18009f5e1  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18009f5e6  mov     cl, [rax+0A0h]
0x18009f5ec  neg     cl
0x18009f5ee  sbb     rcx, rcx
0x18009f5f1  add     rcx, r14; hKey
0x18009f5f4  mov     rdx, rbx; lpSubKey
0x18009f5f7  call    cs:__imp_RegDeleteTreeA
0x18009f5fd  call    ?GetSourcesRegPath@CSysRegistryEntityLocation@@SAPEBDXZ; CSysRegistryEntityLocation::GetSourcesRegPath(void)
0x18009f602  mov     rbx, rax
0x18009f605  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18009f60a  mov     cl, [rax+0A0h]
0x18009f610  neg     cl
0x18009f612  sbb     rcx, rcx
0x18009f615  add     rcx, r14
0x18009f618  mov     rdx, rbx
0x18009f61b  lea     r11, [rsp+90h+var_s0]
0x18009f623  mov     rbx, [r11+18h]
0x18009f627  mov     rdi, [r11+20h]
0x18009f62b  mov     r14, [r11+28h]
0x18009f62f  mov     rsp, r11
0x18009f632  pop     rbp
0x18009f633  jmp     cs:__imp_RegDeleteTreeA
```
