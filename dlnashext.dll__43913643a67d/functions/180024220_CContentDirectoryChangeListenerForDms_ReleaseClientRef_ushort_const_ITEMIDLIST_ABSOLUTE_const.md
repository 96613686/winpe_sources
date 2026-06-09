# CContentDirectoryChangeListenerForDms::ReleaseClientRef(ushort const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180024220`
- end: `0x1800244f0`
- name: `?ReleaseClientRef@CContentDirectoryChangeListenerForDms@@QEAAXPEBGPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `720`
- prototype: `void __fastcall(CContentDirectoryChangeListenerForDms *__hidden this, const unsigned __int16 *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002260c`
- `0x180024eb8`

## callees

- `0x180001710`
- `0x1800030b0`
- `0x180007840`
- `0x180008430`
- `0x18001073c`
- `0x18001e6f4`
- `0x180022e5c`
- `0x180023e00`
- `0x180024220`
- `0x180024b4c`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024393`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024393`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800242d2`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1800242d2`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1800242ba`
- `api-ms-win-shell-namespace-l1-1-0!ILIsEqual` at `0x1800242ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CContentDirectoryChangeListenerForDms::ReleaseClientRef(
        CMediaServerCollectionChangeListener **this,
        char *a2,
        const ITEMIDLIST *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // r13
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  const ITEMIDLIST *v9; // r13
  __int64 v10; // r12
  __int64 v11; // rdi
  char **v12; // rax
  char *v13; // rax
  char *v14; // r8
  int v15; // edx
  int v16; // ecx
  ITEMIDLIST *v17; // rdi
  CMediaServerCollectionChangeListener *v19; // rbx
  CMediaServerCollectionChangeListener *v20; // rdi
  CMediaServerCollectionChangeListener *v21; // rsi
  CMediaServerCollectionChangeListener *v22; // r14
  struct Windows::Media::Streaming::Internal::IMediaServer *v23; // r12
  int (__fastcall *v24)(struct Windows::Media::Streaming::Internal::IMediaServer *, __int64 *); // r15
  struct Windows::Media::Streaming::Internal::IMediaServer *v25; // rbx
  int (__fastcall *v26)(struct Windows::Media::Streaming::Internal::IMediaServer *, GUID *, __int64 *); // rdi
  struct Windows::Media::Streaming::Internal::IMediaServer *v27; // rdi
  int (__fastcall *v28)(struct Windows::Media::Streaming::Internal::IMediaServer *, __int64 *); // rbx
  __int64 v29; // [rsp+20h] [rbp-20h] BYREF
  __int64 v30; // [rsp+28h] [rbp-18h] BYREF
  _BYTE v31[16]; // [rsp+30h] [rbp-10h] BYREF
  struct Windows::Media::Streaming::Internal::IMediaServer *v32; // [rsp+80h] [rbp+40h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+90h] [rbp+50h]
  __int64 v34; // [rsp+98h] [rbp+58h] BYREF

  pidl2 = a3;
  v5 = (struct _RTL_CRITICAL_SECTION *)(this + 9);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
    (__int64)v31,
    (struct _RTL_CRITICAL_SECTION *)(this + 9),
    1);
  v6 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::Find(
         this + 15,
         a2);
  if ( v6 )
  {
    v9 = pidl2;
    do
    {
      v10 = v6;
      v11 = v6;
      v12 = (char **)ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::Successor(
                       this + 15,
                       v6,
                       v7,
                       v8);
      v6 = (__int64)v12;
      if ( !v12 )
        goto LABEL_8;
      v13 = *v12;
      v14 = (char *)(a2 - v13);
      do
      {
        v15 = *(unsigned __int16 *)&v14[(_QWORD)v13];
        v16 = *(unsigned __int16 *)v13 - v15;
        if ( v16 )
          break;
        v13 += 2;
      }
      while ( v15 );
      if ( v16 )
LABEL_8:
        v6 = 0;
      v17 = *(ITEMIDLIST **)(v11 + 8);
      if ( ILIsEqual(v17, v9) )
      {
        ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::RBDelete(
          this + 15,
          v10);
        ILFree(v17);
      }
    }
    while ( v6 );
    v5 = (struct _RTL_CRITICAL_SECTION *)(this + 9);
  }
  if ( (*((_DWORD *)this + 47))-- == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids, this);
    }
    CMediaServerCollectionChangeListener::ReleaseClientRef(this[22]);
    v32 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v32);
    if ( (int)CContentDirectoryChangeListenerForDms::GetServer((CContentDirectoryChangeListenerForDms *)this, 0, &v32) >= 0 )
    {
      v19 = this[28];
      v20 = this[27];
      v21 = this[25];
      v22 = this[26];
      this[28] = 0;
      this[27] = 0;
      this[25] = 0;
      this[26] = 0;
      LeaveCriticalSection(v5);
      v34 = 0;
      v23 = v32;
      v24 = *(int (__fastcall **)(struct Windows::Media::Streaming::Internal::IMediaServer *, __int64 *))(*(_QWORD *)v32 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v34);
      if ( v24(v23, &v34) >= 0 )
      {
        if ( v19 )
          (*(void (__fastcall **)(__int64, CMediaServerCollectionChangeListener *))(*(_QWORD *)v34 + 136LL))(v34, v19);
        if ( v20 )
          (*(void (__fastcall **)(__int64, CMediaServerCollectionChangeListener *))(*(_QWORD *)v34 + 120LL))(v34, v20);
        if ( v21 )
        {
          v29 = 0;
          v25 = v32;
          v26 = **(int (__fastcall ***)(struct Windows::Media::Streaming::Internal::IMediaServer *, GUID *, __int64 *))v32;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v29);
          if ( v26(v25, &GUID_f4f26cbb_7962_48b7_80f7_c3a5d753bcb0, &v29) >= 0 )
            (*(void (__fastcall **)(__int64, CMediaServerCollectionChangeListener *))(*(_QWORD *)v29 + 208LL))(v29, v21);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v29);
        }
      }
      v30 = 0;
      v27 = v32;
      v28 = *(int (__fastcall **)(struct Windows::Media::Streaming::Internal::IMediaServer *, __int64 *))(*(_QWORD *)v32 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v30);
      if ( v28(v27, &v30) >= 0 && v22 )
        (*(void (__fastcall **)(__int64, CMediaServerCollectionChangeListener *))(*(_QWORD *)v30 + 72LL))(v30, v22);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v34);
      EnterCriticalSection(v5);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v32);
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v31);
}

```

## disassembly

```asm
0x180024220  mov     [rsp-38h+arg_8], rbx
0x180024225  mov     [rsp-38h+pidl2], r8
0x18002422a  push    rbp
0x18002422b  push    rsi
0x18002422c  push    rdi
0x18002422d  push    r12
0x18002422f  push    r13
0x180024231  push    r14
0x180024233  push    r15
0x180024235  mov     rbp, rsp
0x180024238  sub     rsp, 40h
0x18002423c  mov     r14, rdx
0x18002423f  mov     r15, rcx
0x180024242  lea     r13, [rcx+48h]
0x180024246  mov     r8b, 1
0x180024249  mov     rdx, r13
0x18002424c  lea     rcx, [rbp+var_10]
0x180024250  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x180024255  nop
0x180024256  lea     rsi, [r15+78h]
0x18002425a  mov     rdx, r14
0x18002425d  mov     rcx, rsi
0x180024260  call    ?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_ITEMIDLIST_ABSOLUTE@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAU_ITEMIDLIST_ABSOLUTE@@@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::Find(ushort const *)
0x180024265  mov     rbx, rax
0x180024268  xor     r12d, r12d
0x18002426b  test    rax, rax
0x18002426e  jz      short loc_1800242E4
0x180024270  mov     r13, [rbp+pidl2]
0x180024274  mov     r12, rbx
0x180024277  mov     rdi, rbx
0x18002427a  mov     rdx, rbx
0x18002427d  mov     rcx, rsi
0x180024280  call    ?Successor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_ITEMIDLIST_ABSOLUTE@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAU_ITEMIDLIST_ABSOLUTE@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::Successor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::CNode *)
0x180024285  mov     rbx, rax
0x180024288  test    rax, rax
0x18002428b  jz      short loc_1800242AE
0x18002428d  mov     rax, [rax]
0x180024290  mov     r8, r14
0x180024293  sub     r8, rax
0x180024296  movzx   ecx, word ptr [rax]
0x180024299  movzx   edx, word ptr [rax+r8]
0x18002429e  sub     ecx, edx
0x1800242a0  jnz     short loc_1800242AA
0x1800242a2  add     rax, 2
0x1800242a6  test    edx, edx
0x1800242a8  jnz     short loc_180024296
0x1800242aa  test    ecx, ecx
0x1800242ac  jz      short loc_1800242B0
0x1800242ae  xor     ebx, ebx
0x1800242b0  mov     rdi, [rdi+8]
0x1800242b4  mov     rdx, r13; pidl2
0x1800242b7  mov     rcx, rdi; pidl1
0x1800242ba  call    cs:__imp_ILIsEqual
0x1800242c0  test    eax, eax
0x1800242c2  jz      short loc_1800242D8
0x1800242c4  mov     rdx, r12
0x1800242c7  mov     rcx, rsi
0x1800242ca  call    ?RBDelete@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_ITEMIDLIST_ABSOLUTE@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAU_ITEMIDLIST_ABSOLUTE@@@2@@ATL@@AEAA_NPEAVCNode@12@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::RBDelete(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::CNode *)
0x1800242cf  mov     rcx, rdi; pidl
0x1800242d2  call    cs:__imp_ILFree
0x1800242d8  xor     r12d, r12d
0x1800242db  test    rbx, rbx
0x1800242de  jnz     short loc_180024274
0x1800242e0  lea     r13, [r15+48h]
0x1800242e4  add     dword ptr [r15+0BCh], 0FFFFFFFFh
0x1800242ec  jnz     loc_1800244CF
0x1800242f2  lea     rax, WPP_GLOBAL_Control
0x1800242f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024300  cmp     rcx, rax
0x180024303  jz      short loc_180024329
0x180024305  test    byte ptr [rcx+1Ch], 40h
0x180024309  jz      short loc_180024329
0x18002430b  cmp     byte ptr [rcx+19h], 4
0x18002430f  jb      short loc_180024329
0x180024311  mov     edx, 1Fh
0x180024316  mov     r9, r15
0x180024319  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x180024320  mov     rcx, [rcx+10h]
0x180024324  call    WPP_SF_q
0x180024329  mov     rcx, [r15+0B0h]; this
0x180024330  call    ?ReleaseClientRef@CMediaServerCollectionChangeListener@@QEAAXXZ; CMediaServerCollectionChangeListener::ReleaseClientRef(void)
0x180024335  mov     [rbp+arg_0], r12
0x180024339  lea     rcx, [rbp+arg_0]
0x18002433d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180024342  lea     r8, [rbp+arg_0]; struct Windows::Media::Streaming::Internal::IMediaServer **
0x180024346  xor     edx, edx; bool
0x180024348  mov     rcx, r15; this
0x18002434b  call    ?GetServer@CContentDirectoryChangeListenerForDms@@QEAAJ_NPEAPEAUIMediaServer@Internal@Streaming@Media@Windows@@@Z; CContentDirectoryChangeListenerForDms::GetServer(bool,Windows::Media::Streaming::Internal::IMediaServer * *)
0x180024350  test    eax, eax
0x180024352  js      loc_1800244C5
0x180024358  mov     rbx, [r15+0E0h]
0x18002435f  mov     rdi, [r15+0D8h]
0x180024366  mov     rsi, [r15+0C8h]
0x18002436d  mov     r14, [r15+0D0h]
0x180024374  mov     [r15+0E0h], r12
0x18002437b  mov     [r15+0D8h], r12
0x180024382  mov     [r15+0C8h], r12
0x180024389  mov     [r15+0D0h], r12
0x180024390  mov     rcx, r13; lpCriticalSection
0x180024393  call    cs:__imp_LeaveCriticalSection
0x180024399  mov     [rbp+arg_18], r12
0x18002439d  mov     r12, [rbp+arg_0]
0x1800243a1  mov     rax, [r12]
0x1800243a5  mov     r15, [rax+38h]
0x1800243a9  lea     rcx, [rbp+arg_18]
0x1800243ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800243b2  lea     rdx, [rbp+arg_18]
0x1800243b6  mov     rcx, r12
0x1800243b9  mov     rax, r15
0x1800243bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243c1  test    eax, eax
0x1800243c3  js      loc_180024457
0x1800243c9  test    rbx, rbx
0x1800243cc  jz      short loc_1800243E4
0x1800243ce  mov     rcx, [rbp+arg_18]
0x1800243d2  mov     rax, [rcx]
0x1800243d5  mov     rdx, rbx
0x1800243d8  mov     rax, [rax+88h]
0x1800243df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243e4  test    rdi, rdi
0x1800243e7  jz      short loc_1800243FC
0x1800243e9  mov     rcx, [rbp+arg_18]
0x1800243ed  mov     rax, [rcx]
0x1800243f0  mov     rdx, rdi
0x1800243f3  mov     rax, [rax+78h]
0x1800243f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243fc  test    rsi, rsi
0x1800243ff  jz      short loc_180024457
0x180024401  mov     [rbp+var_20], 0
0x180024409  mov     rbx, [rbp+arg_0]
0x18002440d  mov     rax, [rbx]
0x180024410  mov     rdi, [rax]
0x180024413  lea     rcx, [rbp+var_20]
0x180024417  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002441c  lea     r8, [rbp+var_20]
0x180024420  lea     rdx, _GUID_f4f26cbb_7962_48b7_80f7_c3a5d753bcb0
0x180024427  mov     rcx, rbx
0x18002442a  mov     rax, rdi
0x18002442d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024432  nop
0x180024433  test    eax, eax
0x180024435  js      short loc_18002444E
0x180024437  mov     rcx, [rbp+var_20]
0x18002443b  mov     rax, [rcx]
0x18002443e  mov     rdx, rsi
0x180024441  mov     rax, [rax+0D0h]
0x180024448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002444d  nop
0x18002444e  lea     rcx, [rbp+var_20]
0x180024452  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180024457  mov     [rbp+var_18], 0
0x18002445f  mov     rdi, [rbp+arg_0]
0x180024463  mov     rax, [rdi]
0x180024466  mov     rbx, [rax+40h]
0x18002446a  lea     rcx, [rbp+var_18]
0x18002446e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180024473  lea     rdx, [rbp+var_18]
0x180024477  mov     rcx, rdi
0x18002447a  mov     rax, rbx
0x18002447d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024482  test    eax, eax
0x180024484  js      short loc_18002449E
0x180024486  test    r14, r14
0x180024489  jz      short loc_18002449E
0x18002448b  mov     rcx, [rbp+var_18]
0x18002448f  mov     rax, [rcx]
0x180024492  mov     rdx, r14
0x180024495  mov     rax, [rax+48h]
0x180024499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002449e  lea     rcx, [rbp+arg_0]
0x1800244a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800244a7  nop
0x1800244a8  lea     rcx, [rbp+var_18]
0x1800244ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800244b1  nop
0x1800244b2  lea     rcx, [rbp+arg_18]
0x1800244b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800244bb  mov     rcx, r13; lpCriticalSection
0x1800244be  call    cs:__imp_EnterCriticalSection
0x1800244c4  nop
0x1800244c5  lea     rcx, [rbp+arg_0]
0x1800244c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800244ce  nop
0x1800244cf  lea     rcx, [rbp+var_10]
0x1800244d3  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800244d8  mov     rbx, [rsp+40h+arg_8]
0x1800244e0  add     rsp, 40h
0x1800244e4  pop     r15
0x1800244e6  pop     r14
0x1800244e8  pop     r13
0x1800244ea  pop     r12
0x1800244ec  pop     rdi
0x1800244ed  pop     rsi
0x1800244ee  pop     rbp
0x1800244ef  retn
```
