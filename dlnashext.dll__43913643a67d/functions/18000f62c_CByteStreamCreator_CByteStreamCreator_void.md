# CByteStreamCreator::~CByteStreamCreator(void)

- ea: `0x18000f62c`
- end: `0x18000f660`
- name: `??1CByteStreamCreator@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(CByteStreamCreator *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f40c`
- `0x1800154f0`
- `0x180019298`
- `0x180033d2c`
- `0x1800341cf`

## callees

- `0x180001710`
- `0x180005f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f643`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f643`

## pseudocode

```c
void __fastcall CByteStreamCreator::~CByteStreamCreator(CByteStreamCreator *this)
{
  *(_QWORD *)this = &CByteStreamCreator::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 8);
}

```

## disassembly

```asm
0x18000f62c  push    rbx
0x18000f62e  sub     rsp, 20h
0x18000f632  lea     rax, ??_7CByteStreamCreator@@6B@; const CByteStreamCreator::`vftable'
0x18000f639  mov     rbx, rcx
0x18000f63c  mov     [rcx], rax
0x18000f63f  add     rcx, 18h; lpCriticalSection
0x18000f643  call    cs:__imp_DeleteCriticalSection
0x18000f649  lea     rcx, [rbx+10h]
0x18000f64d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f652  lea     rcx, [rbx+8]
0x18000f656  add     rsp, 20h
0x18000f65a  pop     rbx
0x18000f65b  jmp     ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
```
