# CContentDirectoryChangeListenerForDms::AddClientRef(ushort const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180022a48`
- end: `0x180022b6c`
- name: `?AddClientRef@CContentDirectoryChangeListenerForDms@@QEAAJPEBGPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(CContentDirectoryChangeListenerForDms *__hidden this, const unsigned __int16 *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180024c9c`

## callees

- `0x180001710`
- `0x180002c00`
- `0x180007840`
- `0x180008430`
- `0x18001073c`
- `0x18001e6f4`
- `0x180022a48`
- `0x180024084`
- `0x180024cd0`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x180022a83`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x180022a83`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDirectoryChangeListenerForDms::AddClientRef(
        CContentDirectoryChangeListenerForDms *this,
        const unsigned __int16 *a2,
        const ITEMIDLIST *a3)
{
  int Server; // ebx
  _BYTE v8[56]; // [rsp+20h] [rbp-38h] BYREF
  struct Windows::Media::Streaming::Internal::IMediaServer *v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = 0;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
    (__int64)v8,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 72),
    1);
  Server = -2147024809;
  if ( a3 )
  {
    v9 = (struct Windows::Media::Streaming::Internal::IMediaServer *)ILClone(a3);
    if ( v9 )
    {
      try
      {
        Server = 0;
        ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::RBInsert(
          (char *)this + 120,
          a2,
          &v9);
      }
      catch ( std::bad_alloc )
      {
        ILFree((LPITEMIDLIST)v9);
        LODWORD(v9) = -2147024882;
        Server = -2147024882;
        goto LABEL_14;
      }
      catch ( ... )
      {
        ILFree((LPITEMIDLIST)v9);
        LODWORD(v9) = -2147418113;
        Server = -2147418113;
        goto LABEL_14;
      }
    }
    else
    {
      Server = -2147024882;
    }
  }
  if ( Server >= 0 && ++*((_DWORD *)this + 47) == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids, this);
    }
    v9 = 0;
    CMediaServerCollectionChangeListener::AddClientRef(*((CMediaServerCollectionChangeListener **)this + 22));
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v9);
    Server = CContentDirectoryChangeListenerForDms::GetServer(this, 0, &v9);
    if ( Server < 0 )
      Server = 0;
    else
      CContentDirectoryChangeListenerForDms::_SubscribeToEvents(this, v9);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v9);
  }
LABEL_14:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v8);
  return (unsigned int)Server;
}

```

## disassembly

```asm
0x180022a48  push    rbx
0x180022a4a  push    rsi
0x180022a4b  push    rdi
0x180022a4c  push    r14
0x180022a4e  sub     rsp, 38h
0x180022a52  mov     rsi, r8
0x180022a55  mov     r14, rdx
0x180022a58  mov     rdi, rcx
0x180022a5b  mov     [rsp+58h+arg_0], 0
0x180022a64  lea     rdx, [rcx+48h]
0x180022a68  mov     r8b, 1
0x180022a6b  lea     rcx, [rsp+58h+var_38]
0x180022a70  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x180022a75  nop
0x180022a76  mov     ebx, 80070057h
0x180022a7b  test    rsi, rsi
0x180022a7e  jz      short loc_180022AAD
0x180022a80  mov     rcx, rsi; pidl
0x180022a83  call    cs:__imp_ILClone
0x180022a89  mov     [rsp+58h+arg_0], rax
0x180022a8e  test    rax, rax
0x180022a91  jz      short loc_180022AA8
0x180022a93  xor     ebx, ebx
0x180022a95  lea     rcx, [rdi+78h]
0x180022a99  lea     r8, [rsp+58h+arg_0]
0x180022a9e  mov     rdx, r14
0x180022aa1  call    ?RBInsert@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_ITEMIDLIST_ABSOLUTE@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAU_ITEMIDLIST_ABSOLUTE@@@2@@ATL@@IEAAPEAVCNode@12@PEBGAEBQEAU_ITEMIDLIST_ABSOLUTE@@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_ITEMIDLIST_ABSOLUTE *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<_ITEMIDLIST_ABSOLUTE *>>::RBInsert(ushort const *,_ITEMIDLIST_ABSOLUTE * const &)
0x180022aa6  jmp     short loc_180022AAD
0x180022aa8  mov     ebx, 8007000Eh
0x180022aad  test    ebx, ebx
0x180022aaf  js      loc_180022B56
0x180022ab5  inc     dword ptr [rdi+0BCh]
0x180022abb  cmp     dword ptr [rdi+0BCh], 1
0x180022ac2  jnz     loc_180022B56
0x180022ac8  lea     rax, WPP_GLOBAL_Control
0x180022acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ad6  cmp     rcx, rax
0x180022ad9  jz      short loc_180022AFF
0x180022adb  test    byte ptr [rcx+1Ch], 40h
0x180022adf  jz      short loc_180022AFF
0x180022ae1  cmp     byte ptr [rcx+19h], 4
0x180022ae5  jb      short loc_180022AFF
0x180022ae7  mov     edx, 1Eh
0x180022aec  mov     r9, rdi
0x180022aef  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x180022af6  mov     rcx, [rcx+10h]
0x180022afa  call    WPP_SF_q
0x180022aff  mov     [rsp+58h+arg_0], 0
0x180022b08  mov     rcx, [rdi+0B0h]; this
0x180022b0f  call    ?AddClientRef@CMediaServerCollectionChangeListener@@QEAAXXZ; CMediaServerCollectionChangeListener::AddClientRef(void)
0x180022b14  lea     rcx, [rsp+58h+arg_0]
0x180022b19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180022b1e  lea     r8, [rsp+58h+arg_0]; struct Windows::Media::Streaming::Internal::IMediaServer **
0x180022b23  xor     edx, edx; bool
0x180022b25  mov     rcx, rdi; this
0x180022b28  call    ?GetServer@CContentDirectoryChangeListenerForDms@@QEAAJ_NPEAPEAUIMediaServer@Internal@Streaming@Media@Windows@@@Z; CContentDirectoryChangeListenerForDms::GetServer(bool,Windows::Media::Streaming::Internal::IMediaServer * *)
0x180022b2d  mov     ebx, eax
0x180022b2f  test    eax, eax
0x180022b31  js      short loc_180022B42
0x180022b33  mov     rdx, [rsp+58h+arg_0]; struct Windows::Media::Streaming::Internal::IMediaServer *
0x180022b38  mov     rcx, rdi; this
0x180022b3b  call    ?_SubscribeToEvents@CContentDirectoryChangeListenerForDms@@AEAAXPEAUIMediaServer@Internal@Streaming@Media@Windows@@@Z; CContentDirectoryChangeListenerForDms::_SubscribeToEvents(Windows::Media::Streaming::Internal::IMediaServer *)
0x180022b40  jmp     short loc_180022B44
0x180022b42  xor     ebx, ebx
0x180022b44  lea     rcx, [rsp+58h+arg_0]
0x180022b49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180022b4e  jmp     short loc_180022B56
0x180022b50  jmp     short $+2
0x180022b52  mov     ebx, dword ptr [rsp+58h+arg_0]
0x180022b56  lea     rcx, [rsp+58h+var_38]
0x180022b5b  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180022b60  mov     eax, ebx
0x180022b62  add     rsp, 38h
0x180022b66  pop     r14
0x180022b68  pop     rdi
0x180022b69  pop     rsi
0x180022b6a  pop     rbx
0x180022b6b  retn
```
