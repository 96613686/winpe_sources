# CMediaServerFolder::DeviceControllerAdd(Windows::Media::Streaming::IBasicDevice *)

- ea: `0x180003cbc`
- end: `0x180003e5f`
- name: `?DeviceControllerAdd@CMediaServerFolder@@QEAAJPEAUIBasicDevice@Streaming@Media@Windows@@@Z`
- size: `419`
- prototype: `int(CMediaServerFolder *__hidden this, struct Windows::Media::Streaming::IBasicDevice *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800024f0`

## callees

- `0x180001710`
- `0x180003890`
- `0x180003cbc`
- `0x18000e9cc`
- `0x18001568c`
- `0x1800204f4`
- `0x1800333e8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003df8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003df8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e47`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMediaServerFolder::DeviceControllerAdd(
        CMediaServerFolder *this,
        struct Windows::Media::Streaming::IBasicDevice *a2)
{
  int v4; // ebx
  __int64 v5; // rsi
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rbx
  void *v9; // rax
  struct IPropertyStore *v10; // rcx
  LPVOID pv; // [rsp+20h] [rbp-28h] BYREF
  void *Src; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v14[3]; // [rsp+30h] [rbp-18h] BYREF
  size_t Size; // [rsp+60h] [rbp+18h] BYREF
  struct IPropertyStore *v16; // [rsp+68h] [rbp+20h] BYREF

  pv = 0;
  CMediaServerFolder::_ReformatFriendlyName(a2);
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v16);
  v4 = CMediaServerFolder::CreateMediaServerPropertyStore(a2, &v16);
  if ( v4 >= 0 )
  {
    v5 = *((_QWORD *)this + 13);
    pv = 0;
    Src = 0;
    v6 = 0;
    LODWORD(Size) = 0;
    if ( v16 )
    {
      v14[0] = 0;
      v4 = ((__int64 (__fastcall *)(struct IPropertyStore *, GUID *, _QWORD *))v16->lpVtbl->QueryInterface)(
             v16,
             &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
             v14);
      if ( v4 < 0 )
        goto LABEL_12;
      v4 = (*(__int64 (__fastcall **)(_QWORD, void **, size_t *))(*(_QWORD *)v14[0] + 40LL))(v14[0], &Src, &Size);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 16LL))(v14[0]);
      if ( v4 < 0 )
        goto LABEL_12;
      v6 = Size;
    }
    v7 = CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_Alloc((unsigned int)(v6 + 12) + 2LL, v5);
    v8 = v7;
    if ( v7 )
    {
      *(_DWORD *)(v7 + 6) = 1159165815;
      *(_WORD *)(v7 + 10) = Size;
      *(_WORD *)(v7 + 12) = 4;
      *(_DWORD *)(v7 + 14) = 1;
      v9 = Src;
      if ( Src )
      {
        memcpy_0((void *)(v8 + 18), Src, (unsigned int)Size);
        v9 = Src;
      }
      pv = (LPVOID)v8;
      v4 = 0;
    }
    else
    {
      v4 = -2147024882;
      v9 = Src;
    }
    CoTaskMemFree(v9);
  }
LABEL_12:
  v10 = v16;
  if ( v16 )
  {
    v16 = 0;
    ((void (__fastcall *)(struct IPropertyStore *))v10->lpVtbl->Release)(v10);
  }
  if ( v4 >= 0 )
  {
    try
    {
      ATL::CAtlArray<_ITEMID_CHILD *,ATL::CElementTraits<_ITEMID_CHILD *>>::Add((char *)this + 120, &pv);
      pv = 0;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(Size) = -2147024882;
      v4 = Size;
    }
    catch ( ... )
    {
      LODWORD(Size) = -2147418113;
      v4 = Size;
    }
  }
  CoTaskMemFree(pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003cbc  mov     [rsp+arg_0], rbx
0x180003cc1  mov     [rsp+arg_8], rsi
0x180003cc6  push    rdi
0x180003cc7  sub     rsp, 40h
0x180003ccb  mov     rbx, rdx
0x180003cce  mov     rdi, rcx
0x180003cd1  mov     [rsp+48h+pv], 0
0x180003cda  mov     rcx, rdx; struct Windows::Media::Streaming::IBasicDevice *
0x180003cdd  call    ?_ReformatFriendlyName@CMediaServerFolder@@CAJPEAUIBasicDevice@Streaming@Media@Windows@@@Z; CMediaServerFolder::_ReformatFriendlyName(Windows::Media::Streaming::IBasicDevice *)
0x180003ce2  mov     [rsp+48h+arg_18], 0
0x180003ceb  lea     rcx, [rsp+48h+arg_18]
0x180003cf0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180003cf5  lea     rdx, [rsp+48h+arg_18]; struct IPropertyStore **
0x180003cfa  mov     rcx, rbx; struct Windows::Media::Streaming::IBasicDevice *
0x180003cfd  call    ?CreateMediaServerPropertyStore@CMediaServerFolder@@SAJPEAUIBasicDevice@Streaming@Media@Windows@@PEAPEAUIPropertyStore@@@Z; CMediaServerFolder::CreateMediaServerPropertyStore(Windows::Media::Streaming::IBasicDevice *,IPropertyStore * *)
0x180003d02  mov     ebx, eax
0x180003d04  test    eax, eax
0x180003d06  js      loc_180003DFF
0x180003d0c  mov     rcx, [rsp+48h+arg_18]
0x180003d11  mov     rsi, [rdi+68h]
0x180003d15  mov     [rsp+48h+pv], 0
0x180003d1e  mov     [rsp+48h+Src], 0
0x180003d27  xor     eax, eax
0x180003d29  mov     dword ptr [rsp+48h+Size], eax
0x180003d2d  test    rcx, rcx
0x180003d30  jz      short loc_180003D8E
0x180003d32  mov     [rsp+48h+var_18], rax
0x180003d37  mov     rax, [rcx]
0x180003d3a  lea     r8, [rsp+48h+var_18]
0x180003d3f  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180003d46  mov     rax, [rax]
0x180003d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4e  mov     ebx, eax
0x180003d50  test    eax, eax
0x180003d52  js      loc_180003DFF
0x180003d58  mov     rcx, [rsp+48h+var_18]
0x180003d5d  mov     rax, [rcx]
0x180003d60  lea     r8, [rsp+48h+Size]
0x180003d65  lea     rdx, [rsp+48h+Src]
0x180003d6a  mov     rax, [rax+28h]
0x180003d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d73  mov     ebx, eax
0x180003d75  mov     rcx, [rsp+48h+var_18]
0x180003d7a  mov     rax, [rcx]
0x180003d7d  mov     rax, [rax+10h]
0x180003d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d86  test    ebx, ebx
0x180003d88  js      short loc_180003DFF
0x180003d8a  mov     eax, dword ptr [rsp+48h+Size]
0x180003d8e  lea     ecx, [rax+0Ch]
0x180003d91  add     rcx, 2
0x180003d95  mov     rdx, rsi
0x180003d98  call    ?s_Alloc@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@CAPEAUCHILDITEMID@1@_KPEAUIMalloc@@@Z; CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_Alloc(unsigned __int64,IMalloc *)
0x180003d9d  mov     rbx, rax
0x180003da0  test    rax, rax
0x180003da3  jz      short loc_180003DEB
0x180003da5  mov     dword ptr [rax+6], 45177777h
0x180003dac  movzx   ecx, word ptr [rsp+48h+Size]
0x180003db1  mov     [rax+0Ah], cx
0x180003db5  mov     word ptr [rax+0Ch], 4
0x180003dbb  mov     dword ptr [rax+0Eh], 1
0x180003dc2  mov     rax, [rsp+48h+Src]
0x180003dc7  test    rax, rax
0x180003dca  jz      short loc_180003DE2
0x180003dcc  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x180003dd1  lea     rcx, [rbx+12h]; void *
0x180003dd5  mov     rdx, rax; Src
0x180003dd8  call    memcpy_0
0x180003ddd  mov     rax, [rsp+48h+Src]
0x180003de2  mov     [rsp+48h+pv], rbx
0x180003de7  xor     ebx, ebx
0x180003de9  jmp     short loc_180003DF5
0x180003deb  mov     ebx, 8007000Eh
0x180003df0  mov     rax, [rsp+48h+Src]
0x180003df5  mov     rcx, rax; pv
0x180003df8  call    cs:__imp_CoTaskMemFree
0x180003dfe  nop
0x180003dff  mov     rcx, [rsp+48h+arg_18]
0x180003e04  test    rcx, rcx
0x180003e07  jz      short loc_180003E1F
0x180003e09  mov     [rsp+48h+arg_18], 0
0x180003e12  mov     rax, [rcx]
0x180003e15  mov     rax, [rax+10h]
0x180003e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1e  nop
0x180003e1f  test    ebx, ebx
0x180003e21  js      short loc_180003E42
0x180003e23  lea     rcx, [rdi+78h]
0x180003e27  lea     rdx, [rsp+48h+pv]
0x180003e2c  call    ?Add@?$CAtlArray@PEAU_ITEMID_CHILD@@V?$CElementTraits@PEAU_ITEMID_CHILD@@@ATL@@@ATL@@QEAA_KAEBQEAU_ITEMID_CHILD@@@Z; ATL::CAtlArray<_ITEMID_CHILD *,ATL::CElementTraits<_ITEMID_CHILD *>>::Add(_ITEMID_CHILD * const &)
0x180003e31  mov     [rsp+48h+pv], 0
0x180003e3a  jmp     short loc_180003E42
0x180003e3c  jmp     short $+2
0x180003e3e  mov     ebx, dword ptr [rsp+48h+Size]
0x180003e42  mov     rcx, [rsp+48h+pv]; pv
0x180003e47  call    cs:__imp_CoTaskMemFree
0x180003e4d  mov     eax, ebx
0x180003e4f  mov     rbx, [rsp+48h+arg_0]
0x180003e54  mov     rsi, [rsp+48h+arg_8]
0x180003e59  add     rsp, 40h
0x180003e5d  pop     rdi
0x180003e5e  retn
```
