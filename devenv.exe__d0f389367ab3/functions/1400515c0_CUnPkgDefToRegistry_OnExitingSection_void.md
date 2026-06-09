# CUnPkgDefToRegistry::OnExitingSection(void)

- ea: `0x1400515c0`
- end: `0x1400519a7`
- name: `?OnExitingSection@CUnPkgDefToRegistry@@MEAAJXZ`
- size: `999`
- prototype: `__int64 __fastcall(CUnPkgDefToRegistry *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config`

## callees

- `0x140001020`
- `0x140004950`
- `0x1400095f4`
- `0x14000fe10`
- `0x1400102a0`
- `0x140011b10`
- `0x140035330`
- `0x140035488`
- `0x140046514`
- `0x1400515c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005163b`
- `ADVAPI32!RegCloseKey` at `0x1400517b6`
- `ADVAPI32!RegCloseKey` at `0x14005195d`
- `ADVAPI32!RegCloseKey` at `0x14005163b`
- `ADVAPI32!RegCloseKey` at `0x1400517b6`
- `ADVAPI32!RegCloseKey` at `0x14005195d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140051904`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140051904`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14005161b`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140051792`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14005161b`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140051792`
- `ADVAPI32!RevertToSelf` at `0x140051785`
- `ADVAPI32!RevertToSelf` at `0x140051972`
- `ADVAPI32!RevertToSelf` at `0x140051785`
- `ADVAPI32!RevertToSelf` at `0x140051972`
- `VCRUNTIME140!wcsrchr` at `0x140051659`
- `VCRUNTIME140!wcsrchr` at `0x1400517e7`
- `VCRUNTIME140!wcsrchr` at `0x140051659`
- `VCRUNTIME140!wcsrchr` at `0x1400517e7`

## string_xrefs

- `0x14005170c`: `PkgUnDef: error occurred trying to delete full key`
- `0x140051743`: `PkgUnDef: Deleted key`
- `0x140051890`: `PkgUnDef: Deleted key`
- `0x140051929`: `PkgUnDef: error occurred trying to delete key`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUnPkgDefToRegistry::OnExitingSection(CUnPkgDefToRegistry *this)
{
  bool v3; // di
  HKEY v4; // rcx
  const unsigned __int16 **v5; // r14
  wchar_t *v6; // rax
  __int64 v7; // rbx
  const unsigned __int16 *v8; // rsi
  int v9; // r13d
  unsigned __int16 *v10; // rbx
  const unsigned __int16 *v11; // r8
  signed int v12; // ebx
  bool v13; // zf
  bool v14; // si
  HKEY *v15; // r14
  const unsigned __int16 **v16; // r12
  wchar_t *v17; // rax
  __int64 v18; // rbx
  unsigned __int16 *v19; // rdi
  int v20; // r13d
  unsigned __int16 *v21; // rbx
  const unsigned __int16 *v22; // r8
  LSTATUS v23; // eax
  unsigned __int16 *v24; // [rsp+70h] [rbp+Fh] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp+17h] BYREF
  DWORD cSubKeys[2]; // [rsp+80h] [rbp+1Fh] BYREF
  DWORD cValues; // [rsp+88h] [rbp+27h] BYREF

  if ( *((_BYTE *)this + 249) )
    return 0;
  if ( *((_BYTE *)this + 248) )
    goto LABEL_20;
  v3 = ImpersonateLoggedOnUser(*((HANDLE *)this + 22));
  v4 = (HKEY)*((_QWORD *)this + 27);
  if ( v4 )
  {
    RegCloseKey(v4);
    *((_QWORD *)this + 27) = 0;
  }
  *((_DWORD *)this + 56) = 0;
  v5 = (const unsigned __int16 **)((char *)this + 240);
  v6 = wcsrchr(*((const wchar_t **)this + 30), 0x5Cu);
  if ( v6 )
    v7 = v6 - *v5;
  else
    LODWORD(v7) = -1;
  *(_QWORD *)cSubKeys = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
    (char *)this + 240,
    cSubKeys,
    (unsigned int)v7);
  v8 = *(const unsigned __int16 **)cSubKeys;
  v9 = ATL::CRegKey::Open(
         (CUnPkgDefToRegistry *)((char *)this + 216),
         *((HKEY *)this + 26),
         *(const unsigned __int16 **)cSubKeys,
         0x2001Fu);
  if ( !v9 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
      (char *)this + 240,
      &v24,
      (unsigned int)(v7 + 1),
      (unsigned int)(*((_DWORD *)*v5 - 4) - (v7 + 1)));
    v10 = v24;
    v9 = ATL::CRegKey::RecurseDeleteKey((CUnPkgDefToRegistry *)((char *)this + 216), v24);
    if ( _InterlockedDecrement((volatile signed __int32 *)v10 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
    }
  }
  v11 = *v5;
  if ( !v9 )
  {
    CLogger::LogInfo(L"PkgUnDef: Deleted key", 0, v11);
    ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 240, cSubKeys);
    if ( _InterlockedDecrement((volatile signed __int32 *)v8 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
    }
    if ( v3 )
      RevertToSelf();
LABEL_20:
    v14 = ImpersonateLoggedOnUser(*((HANDLE *)this + 22));
    v15 = (HKEY *)((char *)this + 216);
    while ( 1 )
    {
      v23 = RegQueryInfoKeyW(*v15, 0, 0, 0, cSubKeys, 0, 0, &cValues, 0, 0, 0, 0);
      v12 = (unsigned __int16)v23 | 0x80070000;
      if ( v23 <= 0 )
        v12 = v23;
      if ( v12 < 0 )
        break;
      if ( *v15 )
      {
        RegCloseKey(*v15);
        *v15 = 0;
      }
      *((_DWORD *)this + 56) = 0;
      if ( cSubKeys[0] || cValues )
      {
        if ( *v15 )
        {
          RegCloseKey(*v15);
          *v15 = 0;
        }
        *((_DWORD *)this + 56) = 0;
        v12 = 0;
        break;
      }
      v16 = (const unsigned __int16 **)((char *)this + 240);
      v17 = wcsrchr(*((const wchar_t **)this + 30), 0x5Cu);
      if ( v17 )
        v18 = v17 - *v16;
      else
        LODWORD(v18) = -1;
      v24 = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
        (char *)this + 240,
        &v24,
        (unsigned int)v18);
      v19 = v24;
      v20 = ATL::CRegKey::Open((CUnPkgDefToRegistry *)((char *)this + 216), *((HKEY *)this + 26), v24, 0x2001Fu);
      if ( !v20 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
          (char *)this + 240,
          &v25,
          (unsigned int)(v18 + 1),
          (unsigned int)(*((_DWORD *)*v16 - 4) - (v18 + 1)));
        v21 = v25;
        v20 = ATL::CRegKey::DeleteSubKey((CUnPkgDefToRegistry *)((char *)this + 216), v25);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 - 3) + 8LL))(*((_QWORD *)v21 - 3));
        }
      }
      v22 = *v16;
      if ( v20 )
      {
        v12 = -2147467259;
        CLogger::LogError(L"PkgUnDef: error occurred trying to delete key", -2147467259, v22);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 - 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 - 3) + 8LL))(*((_QWORD *)v19 - 3));
        }
        break;
      }
      CLogger::LogInfo(L"PkgUnDef: Deleted key", 0, v22);
      ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 240, &v24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 - 2, 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v19 - 3) + 8LL))(*((_QWORD *)v19 - 3));
      }
    }
    v13 = !v14;
    goto LABEL_44;
  }
  v12 = -2147467259;
  CLogger::LogError(L"PkgUnDef: error occurred trying to delete full key", -2147467259, v11);
  if ( _InterlockedDecrement((volatile signed __int32 *)v8 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  }
  v13 = !v3;
LABEL_44:
  if ( !v13 )
    RevertToSelf();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400515c0  mov     rax, rsp
0x1400515c3  mov     [rax+10h], rbx
0x1400515c7  mov     [rax+18h], rsi
0x1400515cb  mov     [rax+20h], rdi
0x1400515cf  push    rbp
0x1400515d0  push    r12
0x1400515d2  push    r13
0x1400515d4  push    r14
0x1400515d6  push    r15
0x1400515d8  lea     rbp, [rax-5Fh]
0x1400515dc  sub     rsp, 90h
0x1400515e3  mov     rax, cs:__security_cookie
0x1400515ea  xor     rax, rsp
0x1400515ed  mov     [rbp+57h+var_28], rax
0x1400515f1  mov     r15, rcx
0x1400515f4  xor     r13d, r13d
0x1400515f7  cmp     [rcx+0F9h], r13b
0x1400515fe  jz      short loc_140051607
0x140051600  xor     eax, eax
0x140051602  jmp     loc_14005197A
0x140051607  cmp     [rcx+0F8h], r13b
0x14005160e  jnz     loc_14005178B
0x140051614  mov     rcx, [rcx+0B0h]; hToken
0x14005161b  call    cs:__imp_ImpersonateLoggedOnUser
0x140051621  test    eax, eax
0x140051623  setnz   dil
0x140051627  mov     [rbp+57h+var_50], dil
0x14005162b  lea     r12, [r15+0D8h]
0x140051632  mov     rcx, [r12]; hKey
0x140051636  test    rcx, rcx
0x140051639  jz      short loc_140051645
0x14005163b  call    cs:__imp_RegCloseKey
0x140051641  mov     [r12], r13
0x140051645  mov     [r12+8], r13d
0x14005164a  lea     r14, [r15+0F0h]
0x140051651  mov     edx, 5Ch ; '\'; Ch
0x140051656  mov     rcx, [r14]; Str
0x140051659  call    cs:__imp_wcsrchr
0x14005165f  mov     rbx, rax
0x140051662  test    rax, rax
0x140051665  jnz     short loc_14005166C
0x140051667  or      ebx, 0FFFFFFFFh
0x14005166a  jmp     short loc_140051672
0x14005166c  sub     rbx, [r14]
0x14005166f  sar     rbx, 1
0x140051672  mov     qword ptr [rbp+57h+cSubKeys], r13
0x140051676  mov     r8d, ebx
0x140051679  lea     rdx, [rbp+57h+cSubKeys]
0x14005167d  mov     rcx, r14
0x140051680  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140051685  mov     r9d, 2001Fh; unsigned int
0x14005168b  mov     rsi, qword ptr [rbp+57h+cSubKeys]
0x14005168f  mov     r8, rsi; unsigned __int16 *
0x140051692  mov     rdx, [r15+0D0h]; HKEY
0x140051699  mov     rcx, r12; this
0x14005169c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400516a1  mov     r13d, eax
0x1400516a4  test    eax, eax
0x1400516a6  jnz     short loc_1400516F9
0x1400516a8  lea     r8d, [rbx+1]
0x1400516ac  mov     rax, [r14]
0x1400516af  mov     r9d, [rax-10h]
0x1400516b3  sub     r9d, r8d
0x1400516b6  lea     rdx, [rbp+57h+var_48]
0x1400516ba  mov     rcx, r14
0x1400516bd  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x1400516c2  mov     rbx, [rbp+57h+var_48]
0x1400516c6  mov     rdx, rbx; unsigned __int16 *
0x1400516c9  mov     rcx, r12; this
0x1400516cc  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1400516d1  mov     r13d, eax
0x1400516d4  lea     rdx, [rbx-18h]
0x1400516d8  or      r12d, 0FFFFFFFFh
0x1400516dc  mov     eax, r12d
0x1400516df  lock xadd [rdx+10h], eax
0x1400516e4  add     eax, r12d
0x1400516e7  test    eax, eax
0x1400516e9  jg      short loc_1400516FD
0x1400516eb  lfence
0x1400516ee  mov     rcx, [rdx]
0x1400516f1  mov     rax, [rcx]
0x1400516f4  call    qword ptr [rax+8]
0x1400516f7  jmp     short loc_1400516FD
0x1400516f9  or      r12d, 0FFFFFFFFh
0x1400516fd  mov     r8, [r14]; unsigned __int16 *
0x140051700  test    r13d, r13d
0x140051703  jz      short loc_140051741
0x140051705  mov     ebx, 80004005h
0x14005170a  mov     edx, ebx; int
0x14005170c  lea     rcx, aPkgundefErrorO; "PkgUnDef: error occurred trying to dele"...
0x140051713  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140051718  nop
0x140051719  lea     rdx, [rsi-18h]
0x14005171d  mov     eax, r12d
0x140051720  lock xadd [rdx+10h], eax
0x140051725  add     eax, r12d
0x140051728  test    eax, eax
0x14005172a  jg      short loc_140051739
0x14005172c  lfence
0x14005172f  mov     rcx, [rdx]
0x140051732  mov     rax, [rcx]
0x140051735  call    qword ptr [rax+8]
0x140051738  nop
0x140051739  test    dil, dil
0x14005173c  jmp     loc_140051970
0x140051741  xor     edx, edx; int
0x140051743  lea     rcx, aPkgundefDelete; "PkgUnDef: Deleted key"
0x14005174a  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14005174f  lea     rdx, [rbp+57h+cSubKeys]
0x140051753  mov     rcx, r14
0x140051756  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14005175b  nop
0x14005175c  lea     rdx, [rsi-18h]
0x140051760  mov     eax, r12d
0x140051763  lock xadd [rdx+10h], eax
0x140051768  add     eax, r12d
0x14005176b  xor     r13d, r13d
0x14005176e  test    eax, eax
0x140051770  jg      short loc_140051780
0x140051772  lfence
0x140051775  mov     rcx, [rdx]
0x140051778  mov     rax, [rcx]
0x14005177b  call    qword ptr [rax+8]
0x14005177e  nop
0x14005177f  nop
0x140051780  test    dil, dil
0x140051783  jz      short loc_14005178B
0x140051785  call    cs:__imp_RevertToSelf
0x14005178b  mov     rcx, [r15+0B0h]; hToken
0x140051792  call    cs:__imp_ImpersonateLoggedOnUser
0x140051798  test    eax, eax
0x14005179a  setnz   sil
0x14005179e  mov     [rbp+57h+var_50], sil
0x1400517a2  lea     r14, [r15+0D8h]
0x1400517a9  jmp     loc_1400518C9
0x1400517ae  mov     rcx, [r14]; hKey
0x1400517b1  test    rcx, rcx
0x1400517b4  jz      short loc_1400517BF
0x1400517b6  call    cs:__imp_RegCloseKey
0x1400517bc  mov     [r14], r13
0x1400517bf  mov     [r14+8], r13d
0x1400517c3  cmp     [rbp+57h+cSubKeys], r13d
0x1400517c7  ja      loc_140051955
0x1400517cd  cmp     [rbp+57h+cValues], r13d
0x1400517d1  ja      loc_140051955
0x1400517d7  lea     r12, [r15+0F0h]
0x1400517de  mov     edx, 5Ch ; '\'; Ch
0x1400517e3  mov     rcx, [r12]; Str
0x1400517e7  call    cs:__imp_wcsrchr
0x1400517ed  mov     rbx, rax
0x1400517f0  test    rax, rax
0x1400517f3  jnz     short loc_1400517FA
0x1400517f5  or      ebx, 0FFFFFFFFh
0x1400517f8  jmp     short loc_140051801
0x1400517fa  sub     rbx, [r12]
0x1400517fe  sar     rbx, 1
0x140051801  mov     [rbp+57h+var_48], r13
0x140051805  mov     r8d, ebx
0x140051808  lea     rdx, [rbp+57h+var_48]
0x14005180c  mov     rcx, r12
0x14005180f  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x140051814  mov     r9d, 2001Fh; unsigned int
0x14005181a  mov     rdi, [rbp+57h+var_48]
0x14005181e  mov     r8, rdi; unsigned __int16 *
0x140051821  mov     rdx, [r15+0D0h]; HKEY
0x140051828  mov     rcx, r14; this
0x14005182b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140051830  mov     r13d, eax
0x140051833  test    eax, eax
0x140051835  jnz     short loc_140051881
0x140051837  lea     r8d, [rbx+1]
0x14005183b  mov     rax, [r12]
0x14005183f  mov     r9d, [rax-10h]
0x140051843  sub     r9d, r8d
0x140051846  lea     rdx, [rbp+57h+var_40]
0x14005184a  mov     rcx, r12
0x14005184d  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x140051852  mov     rbx, [rbp+57h+var_40]
0x140051856  mov     rdx, rbx; unsigned __int16 *
0x140051859  mov     rcx, r14; this
0x14005185c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140051861  mov     r13d, eax
0x140051864  lea     rdx, [rbx-18h]
0x140051868  or      eax, 0FFFFFFFFh
0x14005186b  lock xadd [rdx+10h], eax
0x140051870  sub     eax, 1
0x140051873  jg      short loc_140051881
0x140051875  lfence
0x140051878  mov     rcx, [rdx]
0x14005187b  mov     rax, [rcx]
0x14005187e  call    qword ptr [rax+8]
0x140051881  mov     r8, [r12]; unsigned __int16 *
0x140051885  test    r13d, r13d
0x140051888  jnz     loc_140051922
0x14005188e  xor     edx, edx; int
0x140051890  lea     rcx, aPkgundefDelete; "PkgUnDef: Deleted key"
0x140051897  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14005189c  lea     rdx, [rbp+57h+var_48]
0x1400518a0  mov     rcx, r12
0x1400518a3  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1400518a8  nop
0x1400518a9  lea     rdx, [rdi-18h]
0x1400518ad  or      eax, 0FFFFFFFFh
0x1400518b0  lock xadd [rdx+10h], eax
0x1400518b5  xor     r13d, r13d
0x1400518b8  sub     eax, 1
0x1400518bb  jg      short loc_1400518C9
0x1400518bd  lfence
0x1400518c0  mov     rcx, [rdx]
0x1400518c3  mov     rax, [rcx]
0x1400518c6  call    qword ptr [rax+8]
0x1400518c9  mov     [rsp+0B0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1400518ce  mov     [rsp+0B0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1400518d3  mov     [rsp+0B0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1400518d8  mov     [rsp+0B0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1400518dd  lea     rax, [rbp+57h+cValues]
0x1400518e1  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x1400518e6  mov     [rsp+0B0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1400518eb  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1400518f0  lea     rax, [rbp+57h+cSubKeys]
0x1400518f4  mov     [rsp+0B0h+lpcSubKeys], rax; lpcSubKeys
0x1400518f9  xor     r9d, r9d; lpReserved
0x1400518fc  xor     r8d, r8d; lpcchClass
0x1400518ff  xor     edx, edx; lpClass
0x140051901  mov     rcx, [r14]; hKey
0x140051904  call    cs:__imp_RegQueryInfoKeyW
0x14005190a  movzx   ebx, ax
0x14005190d  or      ebx, 80070000h
0x140051913  test    eax, eax
0x140051915  cmovle  ebx, eax
0x140051918  test    ebx, ebx
0x14005191a  jns     loc_1400517AE
0x140051920  jmp     short loc_14005196D
0x140051922  mov     ebx, 80004005h
0x140051927  mov     edx, ebx; int
0x140051929  lea     rcx, aPkgundefErrorO_1; "PkgUnDef: error occurred trying to dele"...
0x140051930  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x140051935  nop
0x140051936  lea     rdx, [rdi-18h]
0x14005193a  or      eax, 0FFFFFFFFh
0x14005193d  lock xadd [rdx+10h], eax
0x140051942  sub     eax, 1
0x140051945  jg      short loc_14005196D
0x140051947  lfence
0x14005194a  mov     rcx, [rdx]
0x14005194d  mov     rax, [rcx]
0x140051950  call    qword ptr [rax+8]
0x140051953  jmp     short loc_14005196D
0x140051955  mov     rcx, [r14]; hKey
0x140051958  test    rcx, rcx
0x14005195b  jz      short loc_140051966
0x14005195d  call    cs:__imp_RegCloseKey
0x140051963  mov     [r14], r13
0x140051966  mov     [r14+8], r13d
0x14005196a  mov     ebx, r13d
0x14005196d  test    sil, sil
0x140051970  jz      short loc_140051978
0x140051972  call    cs:__imp_RevertToSelf
0x140051978  mov     eax, ebx
0x14005197a  mov     rcx, [rbp+57h+var_28]
0x14005197e  xor     rcx, rsp; StackCookie
0x140051981  call    __security_check_cookie
0x140051986  lea     r11, [rsp+0B0h+var_20]
0x14005198e  mov     rbx, [r11+38h]
0x140051992  mov     rsi, [r11+40h]
0x140051996  mov     rdi, [r11+48h]
0x14005199a  mov     rsp, r11
0x14005199d  pop     r15
0x14005199f  pop     r14
0x1400519a1  pop     r13
0x1400519a3  pop     r12
0x1400519a5  pop     rbp
0x1400519a6  retn
```
