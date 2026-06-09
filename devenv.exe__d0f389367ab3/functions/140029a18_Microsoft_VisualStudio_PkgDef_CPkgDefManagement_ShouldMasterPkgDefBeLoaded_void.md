# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ShouldMasterPkgDefBeLoaded(void)

- ea: `0x140029a18`
- end: `0x140029d4a`
- name: `?ShouldMasterPkgDefBeLoaded@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAA_NXZ`
- size: `818`
- prototype: `bool __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140016980`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002190`
- `0x140002c10`
- `0x140003070`
- `0x140003160`
- `0x14001405c`
- `0x140014114`
- `0x140014564`
- `0x140017a38`
- `0x140029a18`
- `0x140029d50`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140029bc9`
- `ADVAPI32!RegCloseKey` at `0x140029bc9`
- `ADVAPI32!RegOpenKeyExW` at `0x140029b56`
- `ADVAPI32!RegOpenKeyExW` at `0x140029b56`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140029afa`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140029afa`
- `ADVAPI32!RevertToSelf` at `0x140029bae`
- `ADVAPI32!RevertToSelf` at `0x140029c90`
- `ADVAPI32!RevertToSelf` at `0x140029bae`
- `ADVAPI32!RevertToSelf` at `0x140029c90`

## string_xrefs

- `0x140029c28`: `ConfigPkgDefCacheMetaData`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ShouldMasterPkgDefBeLoaded(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this)
{
  char v3; // di
  struct ATL::IAtlStringMgr *Instance; // rax
  bool v5; // bl
  _QWORD *v6; // r15
  __int64 v7; // rax
  HKEY v8; // rcx
  LSTATUS v9; // eax
  const struct std::nothrow_t *v10; // rdx
  signed int v11; // esi
  _QWORD *v12; // rdx
  int RegistryValue; // esi
  unsigned int *v14; // r9
  __int64 v15; // rdx
  unsigned __int16 *v16; // rax
  int v17; // r9d
  int v18; // r8d
  volatile signed __int32 *hKey; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey_8[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-A0h]
  unsigned int v22[2]; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int8 *v23; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v24[2]; // [rsp+80h] [rbp-88h] BYREF
  int v25; // [rsp+90h] [rbp-78h]
  int v26; // [rsp+94h] [rbp-74h]
  _BYTE v27[32]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v28; // [rsp+B8h] [rbp-50h]

  if ( !*((_QWORD *)this + 2) )
    return 1;
  v3 = 1;
  if ( (*((_DWORD *)this + 15) & 4) != 0 )
    return 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v24[0] = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  memset_0(v27, 0, 0xA0u);
  CFileDiscovery::CFileDiscovery(
    (unsigned int)v27,
    0,
    0,
    (_DWORD)this + 248,
    (__int64)this + 296,
    (__int64)this + 344,
    0x7FFFFFFF);
  *(_OWORD *)hKey_8 = 0;
  v21 = 0;
  hKey_8[0] = 0;
  LODWORD(hKey_8[1]) = 0;
  v23 = 0;
  v5 = ImpersonateLoggedOnUser(*((HANDLE *)this + 24));
  v6 = (_QWORD *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)(*((_QWORD *)this + 2) + 184LL) - 24LL);
  v7 = *((_QWORD *)this + 2);
  v8 = ::hKey;
  if ( *(_QWORD *)(v7 + 232) )
    v8 = *(HKEY *)(v7 + 232);
  hKey = 0;
  v9 = RegOpenKeyExW(v8, (LPCWSTR)v6 + 12, 0, 0x2001Fu, (PHKEY)&hKey);
  if ( !v9 )
  {
    hKey_8[0] = (HKEY)hKey;
    LODWORD(hKey_8[1]) = 0;
  }
  v11 = (unsigned __int16)(v9 != 0 ? v9 : 0) | 0x80070000;
  if ( (v9 != 0 ? v9 : 0) <= 0 )
    v11 = v9 != 0 ? v9 : 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v6 + 8LL))(*v6, v6);
  }
  if ( v11 < 0 )
    goto LABEL_15;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &hKey,
    L"ConfigPkgDefCacheMetaData");
  RegistryValue = GetRegistryValue(hKey_8, &hKey, &v23, v22);
  v10 = (const struct std::nothrow_t *)(hKey - 6);
  if ( _InterlockedExchangeAdd(hKey - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
  }
  if ( RegistryValue >= 0 && (v10 = (const struct std::nothrow_t *)v22[0], v22[0]) )
  {
    if ( v5 )
    {
      RevertToSelf();
      LODWORD(v10) = v22[0];
    }
    if ( (int)ReadOneFileDiscoveryElementFromBinaryBlob(v23, (unsigned int)v10, (struct DiscoveredFile *)v24, v14) >= 0
      && (int)CFileDiscovery::Search(v27, (char *)this + 400) >= 0 )
    {
      if ( !v28 || (v15 = *(_QWORD *)(v28 + 16)) == 0 )
        ATL::AtlThrowImpl(-2147467259);
      v16 = (unsigned __int16 *)v24[0];
      v10 = (const struct std::nothrow_t *)(v15 - v24[0]);
      do
      {
        v17 = *(unsigned __int16 *)((char *)v10 + (_QWORD)v16);
        v18 = *v16 - v17;
        if ( v18 )
          break;
        ++v16;
      }
      while ( v17 );
      if ( !v18 && v24[1] == *(_QWORD *)(v28 + 24) && v26 == *(_DWORD *)(v28 + 36) && v25 == *(_DWORD *)(v28 + 32) )
        v3 = 0;
    }
  }
  else
  {
LABEL_15:
    if ( v5 )
      RevertToSelf();
  }
  operator delete(v23, v10);
  if ( hKey_8[0] )
    RegCloseKey(hKey_8[0]);
  CFileDiscovery::~CFileDiscovery((CFileDiscovery *)v27);
  v12 = (_QWORD *)(v24[0] - 24LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v24[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
  }
  return v3;
}

```

## disassembly

```asm
0x140029a18  mov     rax, rsp
0x140029a1b  mov     [rax+10h], rbx
0x140029a1f  mov     [rax+18h], rsi
0x140029a23  mov     [rax+20h], rdi
0x140029a27  push    rbp
0x140029a28  push    r14
0x140029a2a  push    r15
0x140029a2c  lea     rbp, [rax-58h]
0x140029a30  sub     rsp, 140h
0x140029a37  mov     rax, cs:__security_cookie
0x140029a3e  xor     rax, rsp
0x140029a41  mov     [rbp+50h+var_20], rax
0x140029a45  mov     r14, rcx
0x140029a48  cmp     qword ptr [rcx+10h], 0
0x140029a4d  jnz     short loc_140029A56
0x140029a4f  mov     al, 1
0x140029a51  jmp     loc_140029BFF
0x140029a56  mov     eax, [rcx+3Ch]
0x140029a59  shr     eax, 2
0x140029a5c  mov     dil, 1
0x140029a5f  test    dil, al
0x140029a62  jz      short loc_140029A6B
0x140029a64  xor     al, al
0x140029a66  jmp     loc_140029BFF
0x140029a6b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140029a70  mov     rcx, rax
0x140029a73  test    rax, rax
0x140029a76  jz      loc_140029D31
0x140029a7c  mov     rax, [rax]
0x140029a7f  call    qword ptr [rax+18h]
0x140029a82  add     rax, 18h
0x140029a86  mov     [rsp+150h+var_D8], rax
0x140029a8b  xor     edx, edx; Val
0x140029a8d  mov     r8d, 0A0h; Size
0x140029a93  lea     rcx, [rbp+50h+var_C0]; void *
0x140029a97  call    memset_0
0x140029a9c  lea     rax, [r14+158h]
0x140029aa3  lea     rcx, [r14+128h]
0x140029aaa  lea     r9, [r14+0F8h]
0x140029ab1  mov     [rsp+150h+var_120], 7FFFFFFFh
0x140029ab9  mov     qword ptr [rsp+150h+var_128], rax
0x140029abe  mov     [rsp+150h+phkResult], rcx
0x140029ac3  xor     r8d, r8d
0x140029ac6  xor     edx, edx
0x140029ac8  lea     rcx, [rbp+50h+var_C0]
0x140029acc  call    ??0CFileDiscovery@@QEAA@_N0AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV12@2H@Z; CFileDiscovery::CFileDiscovery(bool,bool,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,int)
0x140029ad1  xorps   xmm3, xmm3
0x140029ad4  xor     eax, eax
0x140029ad6  movups  xmmword ptr [rsp+150h+hKey+8], xmm3
0x140029adb  mov     [rsp+150h+var_F0], rax
0x140029ae0  and     [rsp+150h+hKey+8], rax
0x140029ae5  and     dword ptr [rsp+150h+var_F8], eax
0x140029ae9  and     [rsp+150h+var_F0], rax
0x140029aee  and     [rsp+150h+var_E0], rax
0x140029af3  mov     rcx, [r14+0C0h]; hToken
0x140029afa  call    cs:__imp_ImpersonateLoggedOnUser
0x140029b00  test    eax, eax
0x140029b02  setnz   bl
0x140029b05  mov     byte ptr [rsp+150h+var_110], bl
0x140029b09  mov     rax, [r14+10h]
0x140029b0d  mov     rcx, [rax+0B8h]
0x140029b14  sub     rcx, 18h
0x140029b18  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140029b1d  mov     r15, rax
0x140029b20  lea     rdx, [rax+18h]; lpSubKey
0x140029b24  mov     rax, [r14+10h]
0x140029b28  mov     r8, [rax+0E8h]
0x140029b2f  mov     rcx, cs:hKey
0x140029b36  test    r8, r8
0x140029b39  cmovnz  rcx, r8; hKey
0x140029b3d  and     [rsp+150h+hKey], 0
0x140029b43  lea     rax, [rsp+150h+hKey]
0x140029b48  mov     [rsp+150h+phkResult], rax; phkResult
0x140029b4d  mov     r9d, 2001Fh; samDesired
0x140029b53  xor     r8d, r8d; ulOptions
0x140029b56  call    cs:__imp_RegOpenKeyExW
0x140029b5c  test    eax, eax
0x140029b5e  jnz     short loc_140029B6E
0x140029b60  mov     rcx, [rsp+150h+hKey]
0x140029b65  mov     [rsp+150h+hKey+8], rcx
0x140029b6a  and     dword ptr [rsp+150h+var_F8], eax
0x140029b6e  mov     ecx, eax
0x140029b70  neg     ecx
0x140029b72  sbb     r8d, r8d
0x140029b75  and     r8d, eax
0x140029b78  movzx   esi, r8w
0x140029b7c  or      esi, 80070000h
0x140029b82  test    r8d, r8d
0x140029b85  cmovle  esi, r8d
0x140029b89  or      eax, 0FFFFFFFFh
0x140029b8c  lock xadd [r15+10h], eax
0x140029b92  sub     eax, 1
0x140029b95  jg      short loc_140029BA6
0x140029b97  lfence
0x140029b9a  mov     rcx, [r15]
0x140029b9d  mov     rax, [rcx]
0x140029ba0  mov     rdx, r15
0x140029ba3  call    qword ptr [rax+8]
0x140029ba6  test    esi, esi
0x140029ba8  jns     short loc_140029C28
0x140029baa  test    bl, bl
0x140029bac  jz      short loc_140029BB5
0x140029bae  call    cs:__imp_RevertToSelf
0x140029bb4  nop
0x140029bb5  mov     rcx, [rsp+150h+var_E0]; void *
0x140029bba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140029bbf  mov     rcx, [rsp+150h+hKey+8]; hKey
0x140029bc4  test    rcx, rcx
0x140029bc7  jz      short loc_140029BD0
0x140029bc9  call    cs:__imp_RegCloseKey
0x140029bcf  nop
0x140029bd0  lea     rcx, [rbp+50h+var_C0]; this
0x140029bd4  call    ??1CFileDiscovery@@UEAA@XZ; CFileDiscovery::~CFileDiscovery(void)
0x140029bd9  mov     rdx, [rsp+150h+var_D8]
0x140029bde  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140029be2  or      ecx, 0FFFFFFFFh
0x140029be5  lock xadd [rdx+10h], ecx
0x140029bea  sub     ecx, 1
0x140029bed  jg      short loc_140029BFC
0x140029bef  lfence
0x140029bf2  mov     rcx, [rdx]
0x140029bf5  mov     r8, [rcx]
0x140029bf8  call    qword ptr [r8+8]
0x140029bfc  mov     al, dil
0x140029bff  mov     rcx, [rbp+50h+var_20]
0x140029c03  xor     rcx, rsp; StackCookie
0x140029c06  call    __security_check_cookie
0x140029c0b  lea     r11, [rsp+150h+var_10]
0x140029c13  mov     rbx, [r11+28h]
0x140029c17  mov     rsi, [r11+30h]
0x140029c1b  mov     rdi, [r11+38h]
0x140029c1f  mov     rsp, r11
0x140029c22  pop     r15
0x140029c24  pop     r14
0x140029c26  pop     rbp
0x140029c27  retn
0x140029c28  lea     rdx, aConfigpkgdefca_0; "ConfigPkgDefCacheMetaData"
0x140029c2f  lea     rcx, [rsp+150h+hKey]
0x140029c34  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140029c39  nop
0x140029c3a  lea     r9, [rsp+150h+var_E8]
0x140029c3f  lea     r8, [rsp+150h+var_E0]
0x140029c44  lea     rdx, [rsp+150h+hKey]
0x140029c49  lea     rcx, [rsp+150h+hKey+8]
0x140029c4e  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV?$CAutoVectorPtr@E@2@AEAK@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAutoVectorPtr<uchar> &,ulong &)
0x140029c53  mov     esi, eax
0x140029c55  mov     rdx, [rsp+150h+hKey]
0x140029c5a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140029c5e  or      ecx, 0FFFFFFFFh
0x140029c61  lock xadd [rdx+10h], ecx
0x140029c66  sub     ecx, 1
0x140029c69  jg      short loc_140029C78
0x140029c6b  lfence
0x140029c6e  mov     rcx, [rdx]
0x140029c71  mov     r8, [rcx]
0x140029c74  call    qword ptr [r8+8]
0x140029c78  test    esi, esi
0x140029c7a  js      loc_140029BAA
0x140029c80  mov     edx, [rsp+150h+var_E8]
0x140029c84  test    edx, edx
0x140029c86  jz      loc_140029BAA
0x140029c8c  test    bl, bl
0x140029c8e  jz      short loc_140029C9A
0x140029c90  call    cs:__imp_RevertToSelf
0x140029c96  mov     edx, [rsp+150h+var_E8]; unsigned int
0x140029c9a  lea     r8, [rsp+150h+var_D8]; struct DiscoveredFile *
0x140029c9f  mov     rcx, [rsp+150h+var_E0]; unsigned __int8 *
0x140029ca4  call    ?ReadOneFileDiscoveryElementFromBinaryBlob@@YAJPEAEKAEAUDiscoveredFile@@PEAK@Z; ReadOneFileDiscoveryElementFromBinaryBlob(uchar *,ulong,DiscoveredFile &,ulong *)
0x140029ca9  test    eax, eax
0x140029cab  js      loc_140029BB5
0x140029cb1  lea     rdx, [r14+190h]
0x140029cb8  lea     rcx, [rbp+50h+var_C0]
0x140029cbc  call    ?Search@CFileDiscovery@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CFileDiscovery::Search(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140029cc1  test    eax, eax
0x140029cc3  js      loc_140029BB5
0x140029cc9  mov     rcx, [rbp+50h+var_A0]
0x140029ccd  test    rcx, rcx
0x140029cd0  jz      short loc_140029D3F
0x140029cd2  mov     rdx, [rcx+10h]
0x140029cd6  test    rdx, rdx
0x140029cd9  jz      short loc_140029D3F
0x140029cdb  mov     rax, [rsp+150h+var_D8]
0x140029ce0  sub     rdx, rax
0x140029ce3  movzx   r8d, word ptr [rax]
0x140029ce7  movzx   r9d, word ptr [rax+rdx]
0x140029cec  sub     r8d, r9d
0x140029cef  jnz     short loc_140029CFA
0x140029cf1  add     rax, 2
0x140029cf5  test    r9d, r9d
0x140029cf8  jnz     short loc_140029CE3
0x140029cfa  test    r8d, r8d
0x140029cfd  jnz     loc_140029BB5
0x140029d03  mov     rax, [rcx+18h]
0x140029d07  cmp     [rbp+50h+var_D0], rax
0x140029d0b  jnz     loc_140029BB5
0x140029d11  mov     eax, [rcx+24h]
0x140029d14  cmp     [rbp+50h+var_C4], eax
0x140029d17  jnz     loc_140029BB5
0x140029d1d  mov     eax, [rcx+20h]
0x140029d20  cmp     [rbp+50h+var_C8], eax
0x140029d23  jnz     loc_140029BB5
0x140029d29  xor     dil, dil
0x140029d2c  jmp     loc_140029BB5
0x140029d31  mov     ecx, 80004005h; int
0x140029d36  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140029d3c  jmp     short $+2
0x140029d3e  nop
0x140029d3f  mov     ecx, 80004005h; int
0x140029d44  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
