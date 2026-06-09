# CThumbnailRequest::~CThumbnailRequest(void)

- ea: `0x180020ae0`
- end: `0x180020b33`
- name: `??1CThumbnailRequest@@MEAA@XZ`
- size: `83`
- prototype: `void __fastcall(CThumbnailRequest *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020b80`

## callees

- `0x180001710`
- `0x18000ab48`
- `0x180020ae0`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180020afc`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180020afc`

## pseudocode

```c
void __fastcall CThumbnailRequest::~CThumbnailRequest(CThumbnailRequest *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CThumbnailRequest::`vftable';
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    DeleteObject(v2);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((char *)this + 72);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((char *)this + 64);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 48);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180020ae0  push    rbx
0x180020ae2  sub     rsp, 20h
0x180020ae6  lea     rax, ??_7CThumbnailRequest@@6B@; const CThumbnailRequest::`vftable'
0x180020aed  mov     rbx, rcx
0x180020af0  mov     [rcx], rax
0x180020af3  mov     rcx, [rcx+20h]; ho
0x180020af7  test    rcx, rcx
0x180020afa  jz      short loc_180020B02
0x180020afc  call    cs:__imp_DeleteObject
0x180020b02  lea     rcx, [rbx+48h]
0x180020b06  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180020b0b  lea     rcx, [rbx+40h]
0x180020b0f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180020b14  lea     rcx, [rbx+38h]
0x180020b18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180020b1d  lea     rcx, [rbx+30h]
0x180020b21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180020b26  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180020b2d  add     rsp, 20h
0x180020b31  pop     rbx
0x180020b32  retn
```
