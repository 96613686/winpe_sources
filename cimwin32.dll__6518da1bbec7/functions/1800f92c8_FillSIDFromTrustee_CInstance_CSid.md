# FillSIDFromTrustee(CInstance *,CSid &)

- ea: `0x1800f92c8`
- end: `0x1800f96f7`
- name: `?FillSIDFromTrustee@@YAKPEAVCInstance@@AEAVCSid@@@Z`
- size: `1071`
- prototype: `unsigned int __fastcall(struct CInstance *, struct CSid *)`
- caller_count: `10`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081c90`
- `0x18008292c`
- `0x1800caa88`
- `0x1800dd6f8`
- `0x1800ecc88`
- `0x1800ed8e8`
- `0x1800ee448`
- `0x1800eeb7c`
- `0x1800f7c4c`
- `0x1800f8d80`

## callees

- `0x1800226b4`
- `0x180022a70`
- `0x180023594`
- `0x180032fd8`
- `0x18005b394`
- `0x18007a604`
- `0x18007c2dc`
- `0x18008bbb6`
- `0x1800f7c00`
- `0x1800f7c24`
- `0x1800f92c8`
- `0x1800f9924`

## import_xrefs

- `msvcrt!free` at `0x1800f948c`
- `msvcrt!free` at `0x1800f948c`
- `msvcrt!malloc` at `0x1800f9434`
- `msvcrt!malloc` at `0x1800f9434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f95be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f95be`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800f9679`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800f9679`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f9547`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800f94d7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800f95d6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800f95e5`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800f94d7`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800f95d6`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800f95e5`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800f94f0`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800f95fe`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800f9616`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800f94f0`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800f95fe`
- `framedynos!?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z` at `0x1800f9616`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800f9524`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800f963a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800f964b`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800f9524`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800f963a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800f964b`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800f9506`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800f9628`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800f9506`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x1800f9628`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800f9333`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800f9333`
- `framedynos!?GetClassObjectInterface@CInstance@@QEAAPEAUIWbemClassObject@@XZ` at `0x1800f92fa`
- `framedynos!?GetClassObjectInterface@CInstance@@QEAAPEAUIWbemClassObject@@XZ` at `0x1800f92fa`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800f935f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800f96a6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800f96b5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800f96c4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800f935f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800f96a6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800f96b5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800f96c4`
- `OLEAUT32!__imp_VariantClear` at `0x1800f94b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800f94b8`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800f938a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800f938a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800f93cc`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800f93cc`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800f93b7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800f93b7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f93e1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f93e1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f945c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f945c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f9535`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f9535`

## string_xrefs

- `0x1800f94e6`: `SIDString`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FillSIDFromTrustee(struct CInstance *a1, struct CSid *a2)
{
  DWORD LastError; // edi
  struct IWbemClassObject *ClassObjectInterface; // rbx
  char v6; // r15
  unsigned int *v7; // rax
  unsigned int v8; // r13d
  void *v9; // rax
  void *v10; // rbx
  CSid *v11; // rax
  const WCHAR *v12; // rax
  CSid *v13; // rax
  const unsigned __int16 *v14; // rbx
  const unsigned __int16 *v15; // rax
  struct IWbemClassObject *v17; // [rsp+30h] [rbp-C8h] BYREF
  VARIANTARG psa; // [rsp+38h] [rbp-C0h] BYREF
  void *ppvData; // [rsp+50h] [rbp-A8h] BYREF
  PSID pSid[5]; // [rsp+58h] [rbp-A0h] BYREF
  int v21; // [rsp+80h] [rbp-78h]
  void *v22[14]; // [rsp+88h] [rbp-70h] BYREF
  PSID plUbound; // [rsp+100h] [rbp+8h] BYREF
  LONG plLbound; // [rsp+110h] [rbp+18h] BYREF
  unsigned int v25; // [rsp+118h] [rbp+20h] BYREF

  v17 = 0;
  if ( !a1 )
    goto LABEL_27;
  LastError = 0;
  ClassObjectInterface = CInstance::GetClassObjectInterface(a1);
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v17);
  v17 = ClassObjectInterface;
  memset(&psa, 0, sizeof(psa));
  v6 = 0;
  CHString::CHString((CHString *)&plUbound, L"SID");
  LOBYTE(ClassObjectInterface) = GetArray(ClassObjectInterface, (const struct CHString *)&plUbound, &psa, 0x2011u);
  CHString::~CHString((CHString *)&plUbound);
  if ( !(_BYTE)ClassObjectInterface )
    goto LABEL_12;
  if ( psa.vt != 1 && psa.llVal )
  {
    if ( SafeArrayGetDim(psa.parray) == 1
      && (plLbound = 0,
          LODWORD(plUbound) = 0,
          SafeArrayGetLBound(psa.parray, 1u, &plLbound),
          SafeArrayGetUBound(psa.parray, 1u, (LONG *)&plUbound),
          ppvData = 0,
          SafeArrayAccessData(psa.parray, &ppvData) >= 0) )
    {
      SafeInt<unsigned long>::SafeInt<unsigned long>(&v25, (unsigned int)plUbound);
      v7 = (unsigned int *)SafeInt<unsigned long>::MixedSizeSubtraction<long>(&v25, v25, (unsigned int)plLbound);
      v8 = *(_DWORD *)SafeInt<unsigned long>::MixedSizeAddition<int>(&v25, *v7);
      v9 = malloc(v8);
      v10 = v9;
      if ( v9 )
      {
        try
        {
          memcpy_0(v9, ppvData, v8);
          SafeArrayUnaccessData(psa.parray);
          v11 = CSid::CSid((CSid *)pSid, v10, 0);
          CSid::operator=(a2, v11);
          CSid::~CSid(pSid);
          free(v10);
          v6 = 1;
        }
        catch ( ... )
        {
          free(0);
          throw;
        }
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      LastError = 87;
    }
  }
  VariantClear(&psa);
  if ( !v6 && !LastError )
  {
LABEL_12:
    CHString::CHString((CHString *)&plLbound);
    if ( CInstance::GetCHString(a1, L"SIDString", (struct CHString *)&plLbound)
      && (int)CHString::GetLength((CHString *)&plLbound) > 0 )
    {
      plUbound = 0;
      v12 = (const WCHAR *)CHString::operator unsigned short const *(&plLbound);
      if ( ConvertStringSidToSidW(v12, &plUbound) )
      {
        LOBYTE(pSid[0]) = 0;
        pSid[1] = LocalFree;
        pSid[2] = plUbound;
        v13 = CSid::CSid((CSid *)v22, plUbound, 0);
        CSid::operator=(a2, v13);
        CSid::~CSid(v22);
        v6 = 1;
        ScopeGuardImpl1<void * (*)(void *),unsigned short *>::~ScopeGuardImpl1<void * (*)(void *),unsigned short *>((__int64)pSid);
        goto LABEL_25;
      }
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_25;
    }
    CHString::CHString((CHString *)&v25);
    CHString::CHString((CHString *)&plUbound);
    CInstance::GetCHString(a1, L"Domain", (struct CHString *)&v25);
    if ( CInstance::GetCHString(a1, L"Name", (struct CHString *)&plUbound)
      && (int)CHString::GetLength((CHString *)&plUbound) > 0 )
    {
      v14 = (const unsigned __int16 *)CHString::operator unsigned short const *(&plUbound);
      v15 = (const unsigned __int16 *)CHString::operator unsigned short const *(&v25);
      CSid::CSid((CSid *)pSid, v15, v14, 0);
      if ( !v21 && pSid[0] && IsValidSid(pSid[0]) )
      {
        CSid::operator=(a2, pSid);
        v6 = 1;
      }
      CSid::~CSid(pSid);
    }
    CHString::~CHString((CHString *)&plUbound);
    CHString::~CHString((CHString *)&v25);
LABEL_25:
    CHString::~CHString((CHString *)&plLbound);
    if ( !v6 && !LastError )
LABEL_27:
      LastError = 87;
  }
  _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v17);
  return LastError;
}

```

## disassembly

```asm
0x1800f92c8  push    rbx
0x1800f92ca  push    rsi
0x1800f92cb  push    rdi
0x1800f92cc  push    r12
0x1800f92ce  push    r13
0x1800f92d0  push    r14
0x1800f92d2  push    r15
0x1800f92d4  sub     rsp, 0C0h
0x1800f92db  mov     r12, rdx
0x1800f92de  mov     r14, rcx
0x1800f92e1  xor     r13d, r13d
0x1800f92e4  mov     [rsp+0F8h+var_D8], r13d
0x1800f92e9  mov     [rsp+0F8h+var_C8], r13
0x1800f92ee  test    rcx, rcx
0x1800f92f1  jz      loc_1800F96D3
0x1800f92f7  mov     edi, r13d
0x1800f92fa  call    cs:__imp_?GetClassObjectInterface@CInstance@@QEAAPEAUIWbemClassObject@@XZ; CInstance::GetClassObjectInterface(void)
0x1800f9300  mov     rbx, rax
0x1800f9303  lea     rcx, [rsp+0F8h+var_C8]
0x1800f9308  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x1800f930d  mov     [rsp+0F8h+var_C8], rbx
0x1800f9312  xorps   xmm0, xmm0
0x1800f9315  xor     eax, eax
0x1800f9317  movups  xmmword ptr [rsp+0F8h+psa], xmm0
0x1800f931c  mov     [rsp+0F8h+var_B0], rax
0x1800f9321  mov     r15b, r13b
0x1800f9324  lea     rdx, aSid_0; "SID"
0x1800f932b  lea     rcx, [rsp+0F8h+plUbound]
0x1800f9333  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800f9339  nop
0x1800f933a  mov     r9d, 2011h; unsigned __int16
0x1800f9340  lea     r8, [rsp+0F8h+psa]; struct tagVARIANT *
0x1800f9345  lea     rdx, [rsp+0F8h+plUbound]; struct CHString *
0x1800f934d  mov     rcx, rbx; struct IWbemClassObject *
0x1800f9350  call    ?GetArray@@YA_NPEAUIWbemClassObject@@AEBVCHString@@AEAUtagVARIANT@@G@Z; GetArray(IWbemClassObject *,CHString const &,tagVARIANT &,ushort)
0x1800f9355  mov     bl, al
0x1800f9357  lea     rcx, [rsp+0F8h+plUbound]
0x1800f935f  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800f9365  lea     esi, [r13+1]
0x1800f9369  test    bl, bl
0x1800f936b  jz      loc_1800F94CF
0x1800f9371  cmp     word ptr [rsp+0F8h+psa], si
0x1800f9376  jz      loc_1800F94B3
0x1800f937c  mov     rcx, [rsp+0F8h+psa+8]; psa
0x1800f9381  test    rcx, rcx
0x1800f9384  jz      loc_1800F94B3
0x1800f938a  call    cs:__imp_SafeArrayGetDim
0x1800f9390  cmp     eax, esi
0x1800f9392  jnz     loc_1800F94AE
0x1800f9398  mov     [rsp+0F8h+plLbound], r13d
0x1800f93a0  mov     dword ptr [rsp+0F8h+plUbound], r13d
0x1800f93a8  lea     r8, [rsp+0F8h+plLbound]; plLbound
0x1800f93b0  mov     edx, esi; nDim
0x1800f93b2  mov     rcx, [rsp+0F8h+psa+8]; psa
0x1800f93b7  call    cs:__imp_SafeArrayGetLBound
0x1800f93bd  lea     r8, [rsp+0F8h+plUbound]; plUbound
0x1800f93c5  mov     edx, esi; nDim
0x1800f93c7  mov     rcx, [rsp+0F8h+psa+8]; psa
0x1800f93cc  call    cs:__imp_SafeArrayGetUBound
0x1800f93d2  mov     [rsp+0F8h+ppvData], r13
0x1800f93d7  lea     rdx, [rsp+0F8h+ppvData]; ppvData
0x1800f93dc  mov     rcx, [rsp+0F8h+psa+8]; psa
0x1800f93e1  call    cs:__imp_SafeArrayAccessData
0x1800f93e7  test    eax, eax
0x1800f93e9  js      loc_1800F94AE
0x1800f93ef  mov     edx, dword ptr [rsp+0F8h+plUbound]
0x1800f93f6  lea     rcx, [rsp+0F8h+arg_18]
0x1800f93fe  call    ??$?0J@?$SafeInt@K@@QEAA@J@Z; SafeInt<ulong>::SafeInt<ulong>(long)
0x1800f9403  mov     r8d, [rsp+0F8h+plLbound]
0x1800f940b  mov     edx, [rsp+0F8h+arg_18]
0x1800f9412  lea     rcx, [rsp+0F8h+arg_18]
0x1800f941a  call    ??$MixedSizeSubtraction@J@?$SafeInt@K@@CA?AV0@V0@J@Z; SafeInt<ulong>::MixedSizeSubtraction<long>(SafeInt<ulong>,long)
0x1800f941f  mov     edx, [rax]
0x1800f9421  lea     rcx, [rsp+0F8h+arg_18]
0x1800f9429  call    ??$MixedSizeAddition@H@?$SafeInt@K@@CA?AV0@V0@H@Z; SafeInt<ulong>::MixedSizeAddition<int>(SafeInt<ulong>,int)
0x1800f942e  mov     r13d, [rax]
0x1800f9431  mov     ecx, r13d; Size
0x1800f9434  call    cs:__imp_malloc
0x1800f943a  mov     rbx, rax
0x1800f943d  mov     [rsp+0F8h+var_D0], rax
0x1800f9442  test    rax, rax
0x1800f9445  jz      short loc_1800F94A4
0x1800f9447  mov     r8d, r13d; Size
0x1800f944a  mov     rdx, [rsp+0F8h+ppvData]; Src
0x1800f944f  mov     rcx, rax; void *
0x1800f9452  call    memcpy_0
0x1800f9457  mov     rcx, [rsp+0F8h+psa+8]; psa
0x1800f945c  call    cs:__imp_SafeArrayUnaccessData
0x1800f9462  xor     r8d, r8d; unsigned __int16 *
0x1800f9465  mov     rdx, rbx; void *
0x1800f9468  lea     rcx, [rsp+0F8h+pSid]; this
0x1800f946d  call    ??0CSid@@QEAA@PEAXPEBG@Z; CSid::CSid(void *,ushort const *)
0x1800f9472  nop
0x1800f9473  mov     rdx, rax
0x1800f9476  mov     rcx, r12
0x1800f9479  call    ??4CSid@@QEAAAEAV0@AEBV0@@Z; CSid::operator=(CSid const &)
0x1800f947e  nop
0x1800f947f  lea     rcx, [rsp+0F8h+pSid]; this
0x1800f9484  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x1800f9489  mov     rcx, rbx; Block
0x1800f948c  call    cs:__imp_free
0x1800f9492  xor     r13d, r13d
0x1800f9495  mov     [rsp+0F8h+var_D0], r13
0x1800f949a  mov     r15b, sil
0x1800f949d  mov     [rsp+0F8h+var_D4], sil
0x1800f94a2  jmp     short loc_1800F94B3
0x1800f94a4  mov     edi, 8
0x1800f94a9  xor     r13d, r13d
0x1800f94ac  jmp     short loc_1800F94B3
0x1800f94ae  mov     edi, 57h ; 'W'
0x1800f94b3  lea     rcx, [rsp+0F8h+psa]; pvarg
0x1800f94b8  call    cs:__imp_VariantClear
0x1800f94be  test    r15b, r15b
0x1800f94c1  jnz     loc_1800F96D8
0x1800f94c7  test    edi, edi
0x1800f94c9  jnz     loc_1800F96D8
0x1800f94cf  lea     rcx, [rsp+0F8h+plLbound]
0x1800f94d7  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800f94dd  nop
0x1800f94de  lea     r8, [rsp+0F8h+plLbound]
0x1800f94e6  lea     rdx, aSidstring; "SIDString"
0x1800f94ed  mov     rcx, r14
0x1800f94f0  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800f94f6  test    al, al
0x1800f94f8  jz      loc_1800F95CE
0x1800f94fe  lea     rcx, [rsp+0F8h+plLbound]
0x1800f9506  call    cs:__imp_?GetLength@CHString@@QEBAHXZ; CHString::GetLength(void)
0x1800f950c  test    eax, eax
0x1800f950e  jle     loc_1800F95CE
0x1800f9514  mov     [rsp+0F8h+plUbound], r13
0x1800f951c  lea     rcx, [rsp+0F8h+plLbound]
0x1800f9524  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800f952a  mov     rcx, rax; StringSid
0x1800f952d  lea     rdx, [rsp+0F8h+plUbound]; Sid
0x1800f9535  call    cs:__imp_ConvertStringSidToSidW
0x1800f953b  test    eax, eax
0x1800f953d  jz      short loc_1800F95BE
0x1800f953f  mov     rcx, [rsp+0F8h+plUbound]
0x1800f9547  mov     rax, cs:__imp_LocalFree
0x1800f954e  mov     byte ptr [rsp+0F8h+pSid], r13b
0x1800f9553  mov     [rsp+0F8h+var_98], rax
0x1800f9558  mov     [rsp+0F8h+var_90], rcx
0x1800f955d  mov     ebx, 2
0x1800f9562  mov     [rsp+0F8h+var_D8], ebx
0x1800f9566  and     ebx, 0FFFFFFFDh
0x1800f9569  mov     [rsp+0F8h+var_D8], ebx
0x1800f956d  or      ebx, esi
0x1800f956f  mov     [rsp+0F8h+var_D8], ebx
0x1800f9573  xor     r8d, r8d; unsigned __int16 *
0x1800f9576  mov     rdx, [rsp+0F8h+plUbound]; void *
0x1800f957e  lea     rcx, [rsp+0F8h+var_70]; this
0x1800f9586  call    ??0CSid@@QEAA@PEAXPEBG@Z; CSid::CSid(void *,ushort const *)
0x1800f958b  nop
0x1800f958c  mov     rdx, rax
0x1800f958f  mov     rcx, r12
0x1800f9592  call    ??4CSid@@QEAAAEAV0@AEBV0@@Z; CSid::operator=(CSid const &)
0x1800f9597  nop
0x1800f9598  lea     rcx, [rsp+0F8h+var_70]; this
0x1800f95a0  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x1800f95a5  mov     r15b, sil
0x1800f95a8  and     ebx, 0FFFFFFFEh
0x1800f95ab  mov     [rsp+0F8h+var_D8], ebx
0x1800f95af  lea     rcx, [rsp+0F8h+pSid]
0x1800f95b4  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@@QEAA@XZ; ScopeGuardImpl1<void * (*)(void *),ushort *>::~ScopeGuardImpl1<void * (*)(void *),ushort *>(void)
0x1800f95b9  jmp     loc_1800F96BC
0x1800f95be  call    cs:__imp_GetLastError
0x1800f95c4  mov     edi, eax
0x1800f95c6  test    eax, eax
0x1800f95c8  jnz     loc_1800F96BC
0x1800f95ce  lea     rcx, [rsp+0F8h+arg_18]
0x1800f95d6  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800f95dc  nop
0x1800f95dd  lea     rcx, [rsp+0F8h+plUbound]
0x1800f95e5  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800f95eb  nop
0x1800f95ec  lea     r8, [rsp+0F8h+arg_18]
0x1800f95f4  lea     rdx, aDomain_0; "Domain"
0x1800f95fb  mov     rcx, r14
0x1800f95fe  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800f9604  lea     r8, [rsp+0F8h+plUbound]
0x1800f960c  lea     rdx, aName; "Name"
0x1800f9613  mov     rcx, r14
0x1800f9616  call    cs:__imp_?GetCHString@CInstance@@QEBA_NPEBGAEAVCHString@@@Z; CInstance::GetCHString(ushort const *,CHString &)
0x1800f961c  test    al, al
0x1800f961e  jz      short loc_1800F969E
0x1800f9620  lea     rcx, [rsp+0F8h+plUbound]
0x1800f9628  call    cs:__imp_?GetLength@CHString@@QEBAHXZ; CHString::GetLength(void)
0x1800f962e  test    eax, eax
0x1800f9630  jle     short loc_1800F969E
0x1800f9632  lea     rcx, [rsp+0F8h+plUbound]
0x1800f963a  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800f9640  mov     rbx, rax
0x1800f9643  lea     rcx, [rsp+0F8h+arg_18]
0x1800f964b  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800f9651  xor     r9d, r9d; unsigned __int16 *
0x1800f9654  mov     r8, rbx; unsigned __int16 *
0x1800f9657  mov     rdx, rax; unsigned __int16 *
0x1800f965a  lea     rcx, [rsp+0F8h+pSid]; this
0x1800f965f  call    ??0CSid@@QEAA@PEBG00@Z; CSid::CSid(ushort const *,ushort const *,ushort const *)
0x1800f9664  nop
0x1800f9665  cmp     [rsp+0F8h+var_78], r13d
0x1800f966d  jnz     short loc_1800F9693
0x1800f966f  mov     rcx, [rsp+0F8h+pSid]; pSid
0x1800f9674  test    rcx, rcx
0x1800f9677  jz      short loc_1800F9693
0x1800f9679  call    cs:__imp_IsValidSid
0x1800f967f  test    eax, eax
0x1800f9681  jz      short loc_1800F9693
0x1800f9683  lea     rdx, [rsp+0F8h+pSid]
0x1800f9688  mov     rcx, r12
0x1800f968b  call    ??4CSid@@QEAAAEAV0@AEBV0@@Z; CSid::operator=(CSid const &)
0x1800f9690  mov     r15b, sil
0x1800f9693  lea     rcx, [rsp+0F8h+pSid]; this
0x1800f9698  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x1800f969d  nop
0x1800f969e  lea     rcx, [rsp+0F8h+plUbound]
0x1800f96a6  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800f96ac  nop
0x1800f96ad  lea     rcx, [rsp+0F8h+arg_18]
0x1800f96b5  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800f96bb  nop
0x1800f96bc  lea     rcx, [rsp+0F8h+plLbound]
0x1800f96c4  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800f96ca  test    r15b, r15b
0x1800f96cd  jnz     short loc_1800F96D8
0x1800f96cf  test    edi, edi
0x1800f96d1  jnz     short loc_1800F96D8
0x1800f96d3  mov     edi, 57h ; 'W'
0x1800f96d8  lea     rcx, [rsp+0F8h+var_C8]
0x1800f96dd  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x1800f96e2  mov     eax, edi
0x1800f96e4  add     rsp, 0C0h
0x1800f96eb  pop     r15
0x1800f96ed  pop     r14
0x1800f96ef  pop     r13
0x1800f96f1  pop     r12
0x1800f96f3  pop     rdi
0x1800f96f4  pop     rsi
0x1800f96f5  pop     rbx
0x1800f96f6  retn
```
