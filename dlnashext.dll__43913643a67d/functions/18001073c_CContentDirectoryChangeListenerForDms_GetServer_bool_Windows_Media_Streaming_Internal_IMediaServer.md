# CContentDirectoryChangeListenerForDms::GetServer(bool,Windows::Media::Streaming::Internal::IMediaServer * *)

- ea: `0x18001073c`
- end: `0x1800108ab`
- name: `?GetServer@CContentDirectoryChangeListenerForDms@@QEAAJ_NPEAPEAUIMediaServer@Internal@Streaming@Media@Windows@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(CContentDirectoryChangeListenerForDms *__hidden this, bool, struct Windows::Media::Streaming::Internal::IMediaServer **)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018b14`
- `0x180022a48`
- `0x180023730`
- `0x180024220`

## callees

- `0x180001710`
- `0x180007840`
- `0x180008430`
- `0x18000de58`
- `0x18001073c`
- `0x180024cd0`
- `0x180025860`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180010818`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180010818`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDirectoryChangeListenerForDms::GetServer(
        CContentDirectoryChangeListenerForDms *this,
        char a2,
        struct Windows::Media::Streaming::Internal::IMediaServer **a3)
{
  int MediaServerByUDN; // ebx
  __int64 *v7; // rsi
  struct Windows::Media::Streaming::Internal::IMediaServer *v8; // rax
  struct Windows::Media::Streaming::Internal::IMediaServer *v9; // r14
  __int64 v10; // rax
  __int64 v12[2]; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v13[16]; // [rsp+30h] [rbp-10h] BYREF
  struct Windows::Media::Streaming::Internal::IMediaServer *v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+88h] [rbp+48h] BYREF

  MediaServerByUDN = 0;
  v14 = 0;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
    (__int64)v12,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 72),
    1);
  v7 = (__int64 *)((char *)this + 192);
  if ( *((_QWORD *)this + 24) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v14);
    MediaServerByUDN = AgileGitPtr::CopyLocal(
                         (CContentDirectoryChangeListenerForDms *)((char *)this + 192),
                         &GUID_981630af_0907_4cd1_a098_008b0b9a4fac,
                         (void **)&v14);
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v12);
  v8 = v14;
  if ( v14 )
    goto LABEL_12;
  if ( !a2 )
  {
    MediaServerByUDN = -2147023728;
    goto LABEL_14;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v14);
  MediaServerByUDN = FindMediaServerByUDN((HSTRING *)this + 14, &v14);
  if ( MediaServerByUDN >= 0 )
  {
    ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
      (__int64)v13,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 72),
      1);
    v9 = v14;
    v10 = 0;
    v15 = 0;
    MediaServerByUDN = 0;
    if ( v14 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15);
      MediaServerByUDN = RoGetAgileReference(0, &GUID_981630af_0907_4cd1_a098_008b0b9a4fac, v9, &v15);
      v10 = v15;
    }
    v15 = 0;
    v12[0] = *v7;
    *v7 = v10;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15);
    if ( MediaServerByUDN >= 0 && *((_DWORD *)this + 47) )
      CContentDirectoryChangeListenerForDms::_SubscribeToEvents(this, v14);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v13);
    v8 = v14;
LABEL_12:
    if ( MediaServerByUDN >= 0 )
    {
      v14 = 0;
      *a3 = v8;
    }
  }
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v14);
  return (unsigned int)MediaServerByUDN;
}

```

## disassembly

```asm
0x18001073c  mov     [rsp-28h+arg_8], rbx
0x180010741  mov     [rsp-28h+arg_10], rsi
0x180010746  push    rbp
0x180010747  push    rdi
0x180010748  push    r12
0x18001074a  push    r14
0x18001074c  push    r15
0x18001074e  mov     rbp, rsp
0x180010751  sub     rsp, 40h
0x180010755  mov     r12, r8
0x180010758  mov     r14b, dl
0x18001075b  mov     rdi, rcx
0x18001075e  xor     ebx, ebx
0x180010760  mov     [rbp+arg_0], rbx
0x180010764  mov     r8b, 1
0x180010767  lea     rdx, [rcx+48h]
0x18001076b  lea     rcx, [rbp+var_20]
0x18001076f  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x180010774  lea     rsi, [rdi+0C0h]
0x18001077b  cmp     [rsi], rbx
0x18001077e  jz      short loc_18001079E
0x180010780  lea     rcx, [rbp+arg_0]
0x180010784  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010789  lea     r8, [rbp+arg_0]; void **
0x18001078d  lea     rdx, _GUID_981630af_0907_4cd1_a098_008b0b9a4fac; struct _GUID *
0x180010794  mov     rcx, rsi; this
0x180010797  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18001079c  mov     ebx, eax
0x18001079e  lea     rcx, [rbp+var_20]
0x1800107a2  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800107a7  mov     rax, [rbp+arg_0]
0x1800107ab  test    rax, rax
0x1800107ae  jnz     loc_18001086F
0x1800107b4  test    r14b, r14b
0x1800107b7  jz      loc_1800108A3
0x1800107bd  lea     rcx, [rbp+arg_0]
0x1800107c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800107c6  lea     rcx, [rdi+70h]; struct Windows::Internal::String *
0x1800107ca  lea     rdx, [rbp+arg_0]; struct Windows::Media::Streaming::Internal::IMediaServer **
0x1800107ce  call    ?FindMediaServerByUDN@@YAJAEBVString@Internal@Windows@@PEAPEAUIMediaServer@2Streaming@Media@3@@Z; FindMediaServerByUDN(Windows::Internal::String const &,Windows::Media::Streaming::Internal::IMediaServer * *)
0x1800107d3  mov     ebx, eax
0x1800107d5  test    eax, eax
0x1800107d7  js      loc_18001087F
0x1800107dd  mov     r8b, 1
0x1800107e0  lea     rdx, [rdi+48h]
0x1800107e4  lea     rcx, [rbp+var_10]
0x1800107e8  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x1800107ed  nop
0x1800107ee  mov     r14, [rbp+arg_0]
0x1800107f2  xor     eax, eax
0x1800107f4  mov     [rbp+arg_18], rax
0x1800107f8  xor     ebx, ebx
0x1800107fa  test    r14, r14
0x1800107fd  jz      short loc_180010824
0x1800107ff  lea     rcx, [rbp+arg_18]
0x180010803  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010808  lea     r9, [rbp+arg_18]
0x18001080c  mov     r8, r14
0x18001080f  lea     rdx, _GUID_981630af_0907_4cd1_a098_008b0b9a4fac
0x180010816  xor     ecx, ecx
0x180010818  call    cs:__imp_RoGetAgileReference
0x18001081e  mov     ebx, eax
0x180010820  mov     rax, [rbp+arg_18]
0x180010824  mov     [rbp+arg_18], 0
0x18001082c  mov     rcx, [rsi]
0x18001082f  mov     [rbp+var_20], rcx
0x180010833  mov     [rsi], rax
0x180010836  lea     rcx, [rbp+var_20]
0x18001083a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001083f  lea     rcx, [rbp+arg_18]
0x180010843  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010848  test    ebx, ebx
0x18001084a  js      short loc_180010862
0x18001084c  cmp     dword ptr [rdi+0BCh], 0
0x180010853  jbe     short loc_180010862
0x180010855  mov     rdx, [rbp+arg_0]; struct Windows::Media::Streaming::Internal::IMediaServer *
0x180010859  mov     rcx, rdi; this
0x18001085c  call    ?_SubscribeToEvents@CContentDirectoryChangeListenerForDms@@AEAAXPEAUIMediaServer@Internal@Streaming@Media@Windows@@@Z; CContentDirectoryChangeListenerForDms::_SubscribeToEvents(Windows::Media::Streaming::Internal::IMediaServer *)
0x180010861  nop
0x180010862  lea     rcx, [rbp+var_10]
0x180010866  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001086b  mov     rax, [rbp+arg_0]
0x18001086f  test    ebx, ebx
0x180010871  js      short loc_18001087F
0x180010873  mov     [rbp+arg_0], 0
0x18001087b  mov     [r12], rax
0x18001087f  lea     rcx, [rbp+arg_0]
0x180010883  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010888  mov     eax, ebx
0x18001088a  lea     r11, [rsp+40h+var_s0]
0x18001088f  mov     rbx, [r11+38h]
0x180010893  mov     rsi, [r11+40h]
0x180010897  mov     rsp, r11
0x18001089a  pop     r15
0x18001089c  pop     r14
0x18001089e  pop     r12
0x1800108a0  pop     rdi
0x1800108a1  pop     rbp
0x1800108a2  retn
0x1800108a3  mov     ebx, 80070490h
0x1800108a8  jmp     short loc_18001087F
```
