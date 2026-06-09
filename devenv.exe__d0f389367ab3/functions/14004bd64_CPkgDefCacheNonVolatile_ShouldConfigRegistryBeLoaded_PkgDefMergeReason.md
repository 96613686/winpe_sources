# CPkgDefCacheNonVolatile::ShouldConfigRegistryBeLoaded(PkgDefMergeReason *)

- ea: `0x14004bd64`
- end: `0x14004bffa`
- name: `?ShouldConfigRegistryBeLoaded@CPkgDefCacheNonVolatile@@IEAA_NPEAW4PkgDefMergeReason@@@Z`
- size: `662`
- prototype: `bool __fastcall(CPkgDefCacheNonVolatile *__hidden this, enum PkgDefMergeReason *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400147e0`

## callees

- `0x140001020`
- `0x140002c10`
- `0x1400084f4`
- `0x140008b10`
- `0x1400095f4`
- `0x140033ab0`
- `0x1400473a0`
- `0x14004a7b8`
- `0x14004bd64`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004bfbe`
- `ADVAPI32!RegCloseKey` at `0x14004bfbe`
- `ADVAPI32!RegOpenKeyExW` at `0x14004be00`
- `ADVAPI32!RegOpenKeyExW` at `0x14004be00`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004bdbe`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14004bdbe`
- `ADVAPI32!RevertToSelf` at `0x14004bfaf`
- `ADVAPI32!RevertToSelf` at `0x14004bfaf`

## string_xrefs

- `0x14004be6b`: `Checking age of HKEY_CURRENT_USER vs PkgDef cache`
- `0x14004be72`: `Checking age of HKEY_LOCAL_MACHINE vs PkgDef cache`
- `0x14004bf4c`: `PkgDef configuration cache is OUT OF DATE`
- `0x14004bf53`: `PkgDef configuration cache is OK`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CPkgDefCacheNonVolatile::ShouldConfigRegistryBeLoaded(
        CPkgDefCacheNonVolatile *this,
        enum PkgDefMergeReason *a2)
{
  HKEY v4; // r12
  bool v5; // di
  HKEY v6; // rcx
  LSTATUS v7; // eax
  int v8; // edx
  unsigned int v9; // eax
  char v10; // si
  HKEY ConfigTime; // rbx
  const unsigned __int16 *v12; // rcx
  struct ATL::IAtlStringMgr *Instance; // rax
  char v14; // si
  unsigned int v15; // r15d
  bool v16; // al
  const unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rdx
  HKEY phkResult; // [rsp+48h] [rbp-38h] BYREF
  __int128 v21; // [rsp+50h] [rbp-30h]
  __int64 v22; // [rsp+60h] [rbp-20h]
  int v23[2]; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v24; // [rsp+70h] [rbp-10h] BYREF

  if ( a2 )
    *(_DWORD *)a2 = 0;
  v22 = 0;
  v4 = 0;
  v21 = 0u;
  v5 = ImpersonateLoggedOnUser(*((HANDLE *)this + 28));
  v6 = hKey;
  if ( *((_QWORD *)this + 29) )
    v6 = (HKEY)*((_QWORD *)this + 29);
  phkResult = 0;
  v7 = RegOpenKeyExW(v6, *((LPCWSTR *)this + 23), 0, 0x2001Fu, &phkResult);
  if ( !v7 )
  {
    v4 = phkResult;
    *(_QWORD *)&v21 = phkResult;
    DWORD2(v21) = 0;
  }
  v8 = v7 != 0 ? v7 : 0;
  v9 = (unsigned __int16)(v7 != 0 ? v7 : 0) | 0x80070000;
  if ( v8 <= 0 )
    v9 = v8;
  if ( v9 )
  {
    if ( a2 )
      *(_DWORD *)a2 = 16;
    v10 = 1;
  }
  else
  {
    *(_QWORD *)v23 = 0;
    ConfigTime = (HKEY)GetConfigTime(HKEY_CURRENT_USER, *((HANDLE *)this + 28), *((LPCWSTR *)this + 20));
    phkResult = ConfigTime;
    v12 = L"Checking age of HKEY_LOCAL_MACHINE vs PkgDef cache";
    if ( *((_QWORD *)this + 48) == -2147483647 )
      v12 = L"Checking age of HKEY_CURRENT_USER vs PkgDef cache";
    CLogger::LogInfo(v12, 0, *((const unsigned __int16 **)this + 49));
    CodeMarker(9207);
    v24 = 0;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    v24 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                             + 24);
    CPkgDefCache::CheckRegistryScanOverrides(this);
    v14 = *((_BYTE *)this + 217);
    CPkgDefCache::CheckRegistryScanOverrides(this);
    anonymous_namespace_::GetRegChangeTime(
      *((HKEY *)this + 48),
      0,
      *((const WCHAR **)this + 49),
      (FILETIME *)v23,
      *((HANDLE *)this + 28),
      (__int64)&v24,
      *((_DWORD *)this + 12),
      v14);
    CLogger::LogInfo(L"Newest node in merge source", 0, v24);
    CodeMarker(9208);
    v10 = 1;
    v15 = HIDWORD(phkResult);
    v16 = v23[1] > HIDWORD(phkResult) || v23[1] >= HIDWORD(phkResult) && v23[0] > (unsigned int)ConfigTime;
    v17 = L"PkgDef configuration cache is OK";
    if ( v16 )
      v17 = L"PkgDef configuration cache is OUT OF DATE";
    CLogger::LogInfo(v17, 0, 0);
    if ( *(_QWORD *)v23 <= __PAIR64__(v15, (unsigned int)ConfigTime) )
    {
      v10 = 0;
    }
    else if ( a2 )
    {
      *(_DWORD *)a2 = 19;
    }
    v18 = v24 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 - 2, 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    }
  }
  if ( v5 )
    RevertToSelf();
  if ( v4 )
    RegCloseKey(v4);
  return v10;
}

```

## disassembly

```asm
0x14004bd64  mov     [rsp-28h+arg_10], rbx
0x14004bd69  mov     [rsp-28h+arg_18], rsi
0x14004bd6e  push    rbp
0x14004bd6f  push    rdi
0x14004bd70  push    r12
0x14004bd72  push    r14
0x14004bd74  push    r15
0x14004bd76  mov     rbp, rsp
0x14004bd79  sub     rsp, 80h
0x14004bd80  mov     rax, cs:__security_cookie
0x14004bd87  xor     rax, rsp
0x14004bd8a  mov     [rbp+var_8], rax
0x14004bd8e  mov     r14, rdx
0x14004bd91  mov     r15, rcx
0x14004bd94  test    rdx, rdx
0x14004bd97  jz      short loc_14004BD9C
0x14004bd99  and     dword ptr [rdx], 0
0x14004bd9c  xorps   xmm0, xmm0
0x14004bd9f  xor     eax, eax
0x14004bda1  movups  [rbp+var_30], xmm0
0x14004bda5  mov     [rbp+var_20], rax
0x14004bda9  xor     r12d, r12d
0x14004bdac  mov     qword ptr [rbp+var_30], r12
0x14004bdb0  and     dword ptr [rbp+var_30+8], eax
0x14004bdb3  and     [rbp+var_20], rax
0x14004bdb7  mov     rcx, [rcx+0E0h]; hToken
0x14004bdbe  call    cs:__imp_ImpersonateLoggedOnUser
0x14004bdc4  test    eax, eax
0x14004bdc6  setnz   dil
0x14004bdca  mov     [rbp+var_40], dil
0x14004bdce  mov     rax, [r15+0E8h]
0x14004bdd5  mov     rcx, cs:hKey
0x14004bddc  test    rax, rax
0x14004bddf  cmovnz  rcx, rax; hKey
0x14004bde3  and     [rbp+var_38], r12
0x14004bde7  lea     rax, [rbp+var_38]
0x14004bdeb  mov     [rsp+80h+phkResult], rax; phkResult
0x14004bdf0  mov     r9d, 2001Fh; samDesired
0x14004bdf6  xor     r8d, r8d; ulOptions
0x14004bdf9  mov     rdx, [r15+0B8h]; lpSubKey
0x14004be00  call    cs:__imp_RegOpenKeyExW
0x14004be06  test    eax, eax
0x14004be08  jnz     short loc_14004BE15
0x14004be0a  mov     r12, [rbp+var_38]
0x14004be0e  mov     qword ptr [rbp+var_30], r12
0x14004be12  and     dword ptr [rbp+var_30+8], eax
0x14004be15  mov     ecx, eax
0x14004be17  neg     ecx
0x14004be19  sbb     edx, edx
0x14004be1b  and     edx, eax
0x14004be1d  movzx   eax, dx
0x14004be20  or      eax, 80070000h
0x14004be25  test    edx, edx
0x14004be27  cmovle  eax, edx
0x14004be2a  test    eax, eax
0x14004be2c  jz      short loc_14004BE42
0x14004be2e  test    r14, r14
0x14004be31  jz      short loc_14004BE3A
0x14004be33  mov     dword ptr [r14], 10h
0x14004be3a  mov     sil, 1
0x14004be3d  jmp     loc_14004BFAA
0x14004be42  and     qword ptr [rbp+var_18], 0
0x14004be47  mov     r8, [r15+0A0h]; lpSubKey
0x14004be4e  mov     rdx, [r15+0E0h]; hToken
0x14004be55  mov     rsi, 0FFFFFFFF80000001h
0x14004be5c  mov     rcx, rsi; hKey
0x14004be5f  call    ?GetConfigTime@@YA?AU_FILETIME@@PEAUHKEY__@@PEAXPEBG@Z; GetConfigTime(HKEY__ *,void *,ushort const *)
0x14004be64  mov     rbx, rax
0x14004be67  mov     [rbp+var_38], rax
0x14004be6b  lea     rax, aCheckingAgeOfH; "Checking age of HKEY_CURRENT_USER vs Pk"...
0x14004be72  lea     rcx, aCheckingAgeOfH_0; "Checking age of HKEY_LOCAL_MACHINE vs P"...
0x14004be79  cmp     [r15+180h], rsi
0x14004be80  cmovz   rcx, rax; unsigned __int16 *
0x14004be84  mov     r8, [r15+188h]; unsigned __int16 *
0x14004be8b  xor     edx, edx; int
0x14004be8d  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14004be92  mov     ecx, 23F7h
0x14004be97  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x14004be9c  and     [rbp+var_10], 0
0x14004bea1  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14004bea6  mov     rcx, rax
0x14004bea9  test    rax, rax
0x14004beac  jz      loc_14004BFEF
0x14004beb2  mov     rax, [rax]
0x14004beb5  call    qword ptr [rax+18h]
0x14004beb8  add     rax, 18h
0x14004bebc  mov     [rbp+var_10], rax
0x14004bec0  mov     rcx, r15; this
0x14004bec3  call    ?CheckRegistryScanOverrides@CPkgDefCache@@IEAAXXZ; CPkgDefCache::CheckRegistryScanOverrides(void)
0x14004bec8  mov     sil, [r15+0D9h]
0x14004becf  mov     rcx, r15; this
0x14004bed2  call    ?CheckRegistryScanOverrides@CPkgDefCache@@IEAAXXZ; CPkgDefCache::CheckRegistryScanOverrides(void)
0x14004bed7  mov     rdx, [r15+0E0h]
0x14004bede  mov     [rsp+80h+var_48], sil; char
0x14004bee3  mov     eax, [r15+30h]
0x14004bee7  mov     [rsp+80h+var_50], eax; int
0x14004beeb  lea     rax, [rbp+var_10]
0x14004beef  mov     [rsp+80h+var_58], rax; __int64
0x14004bef4  mov     [rsp+80h+phkResult], rdx; hToken
0x14004bef9  lea     r9, [rbp+var_18]; int
0x14004befd  mov     r8, [r15+188h]; int
0x14004bf04  xor     edx, edx; int
0x14004bf06  mov     rcx, [r15+180h]; int
0x14004bf0d  call    _anonymous_namespace___GetRegChangeTime
0x14004bf12  mov     r8, [rbp+var_10]; unsigned __int16 *
0x14004bf16  xor     edx, edx; int
0x14004bf18  lea     rcx, aNewestNodeInMe; "Newest node in merge source"
0x14004bf1f  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14004bf24  mov     ecx, 23F8h
0x14004bf29  call    ?CodeMarker@@YAXW4CodeMarkerEvent@Performance@Internal@Microsoft@@@Z; CodeMarker(Microsoft::Internal::Performance::CodeMarkerEvent)
0x14004bf2e  mov     sil, 1
0x14004bf31  mov     r15d, dword ptr [rbp+var_38+4]
0x14004bf35  cmp     [rbp+var_18+4], r15d
0x14004bf39  jbe     short loc_14004BF40
0x14004bf3b  mov     al, sil
0x14004bf3e  jmp     short loc_14004BF4C
0x14004bf40  jnb     short loc_14004BF46
0x14004bf42  xor     al, al
0x14004bf44  jmp     short loc_14004BF4C
0x14004bf46  cmp     [rbp+var_18], ebx
0x14004bf49  setnbe  al
0x14004bf4c  lea     rdx, aPkgdefConfigur; "PkgDef configuration cache is OUT OF DA"...
0x14004bf53  lea     rcx, aPkgdefConfigur_1; "PkgDef configuration cache is OK"
0x14004bf5a  test    al, al
0x14004bf5c  cmovnz  rcx, rdx; unsigned __int16 *
0x14004bf60  xor     r8d, r8d; unsigned __int16 *
0x14004bf63  xor     edx, edx; int
0x14004bf65  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14004bf6a  cmp     [rbp+var_18+4], r15d
0x14004bf6e  ja      short loc_14004BF77
0x14004bf70  jb      short loc_14004BF85
0x14004bf72  cmp     [rbp+var_18], ebx
0x14004bf75  jbe     short loc_14004BF85
0x14004bf77  test    r14, r14
0x14004bf7a  jz      short loc_14004BF88
0x14004bf7c  mov     dword ptr [r14], 13h
0x14004bf83  jmp     short loc_14004BF88
0x14004bf85  xor     sil, sil
0x14004bf88  mov     rdx, [rbp+var_10]
0x14004bf8c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004bf90  or      eax, 0FFFFFFFFh
0x14004bf93  lock xadd [rdx+10h], eax
0x14004bf98  sub     eax, 1
0x14004bf9b  jg      short loc_14004BFAA
0x14004bf9d  lfence
0x14004bfa0  mov     rcx, [rdx]
0x14004bfa3  mov     rax, [rcx]
0x14004bfa6  call    qword ptr [rax+8]
0x14004bfa9  nop
0x14004bfaa  test    dil, dil
0x14004bfad  jz      short loc_14004BFB6
0x14004bfaf  call    cs:__imp_RevertToSelf
0x14004bfb5  nop
0x14004bfb6  test    r12, r12
0x14004bfb9  jz      short loc_14004BFC4
0x14004bfbb  mov     rcx, r12; hKey
0x14004bfbe  call    cs:__imp_RegCloseKey
0x14004bfc4  mov     al, sil
0x14004bfc7  mov     rcx, [rbp+var_8]
0x14004bfcb  xor     rcx, rsp; StackCookie
0x14004bfce  call    __security_check_cookie
0x14004bfd3  lea     r11, [rsp+80h+var_s0]
0x14004bfdb  mov     rbx, [r11+40h]
0x14004bfdf  mov     rsi, [r11+48h]
0x14004bfe3  mov     rsp, r11
0x14004bfe6  pop     r15
0x14004bfe8  pop     r14
0x14004bfea  pop     r12
0x14004bfec  pop     rdi
0x14004bfed  pop     rbp
0x14004bfee  retn
0x14004bfef  mov     ecx, 80004005h; int
0x14004bff4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
