# CMapiSession::~CMapiSession(void)

- ea: `0x1800329f4`
- end: `0x180032a69`
- name: `??1CMapiSession@@UEAA@XZ`
- size: `117`
- prototype: `void __fastcall(CMapiSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180032a70`

## callees

- `0x180004208`
- `0x180005210`
- `0x1800329f4`
- `0x180032e5c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180032a46`
- `OLEAUT32!__imp_SysFreeString` at `0x180032a50`
- `OLEAUT32!__imp_SysFreeString` at `0x180032a46`
- `OLEAUT32!__imp_SysFreeString` at `0x180032a50`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032a1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032a1b`

## pseudocode

```c
void __fastcall CMapiSession::~CMapiSession(CMapiSession *this)
{
  *(_QWORD *)this = &CMapiSession::`vftable';
  if ( *((_QWORD *)this + 3) )
    CMapiSession::Logoff(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)this + 22);
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)this + 21);
  ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::RemoveAll((char *)this + 48);
  SysFreeString(*((BSTR *)this + 5));
  SysFreeString(*((BSTR *)this + 4));
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)this + 3);
}

```

## disassembly

```asm
0x1800329f4  mov     [rsp+arg_0], rbx
0x1800329f9  push    rdi
0x1800329fa  sub     rsp, 20h
0x1800329fe  mov     rbx, rcx
0x180032a01  lea     rax, ??_7CMapiSession@@6B@; const CMapiSession::`vftable'
0x180032a08  mov     [rcx], rax
0x180032a0b  cmp     qword ptr [rcx+18h], 0
0x180032a10  jz      short loc_180032A17
0x180032a12  call    ?Logoff@CMapiSession@@QEAAJXZ; CMapiSession::Logoff(void)
0x180032a17  lea     rcx, [rbx+78h]; lpCriticalSection
0x180032a1b  call    cs:__imp_DeleteCriticalSection
0x180032a21  lea     rcx, [rbx+0B0h]
0x180032a28  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180032a2d  lea     rcx, [rbx+0A8h]
0x180032a34  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180032a39  lea     rcx, [rbx+30h]
0x180032a3d  call    ?RemoveAll@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiStore@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiStore@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::RemoveAll(void)
0x180032a42  mov     rcx, [rbx+28h]; bstrString
0x180032a46  call    cs:__imp_SysFreeString
0x180032a4c  mov     rcx, [rbx+20h]; bstrString
0x180032a50  call    cs:__imp_SysFreeString
0x180032a56  lea     rcx, [rbx+18h]
0x180032a5a  mov     rbx, [rsp+28h+arg_0]
0x180032a5f  add     rsp, 20h
0x180032a63  pop     rdi
0x180032a64  jmp     ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
```
