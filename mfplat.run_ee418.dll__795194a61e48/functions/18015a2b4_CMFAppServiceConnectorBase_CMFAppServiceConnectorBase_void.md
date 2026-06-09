# CMFAppServiceConnectorBase::~CMFAppServiceConnectorBase(void)

- ea: `0x18015a2b4`
- end: `0x18015a327`
- name: `??1CMFAppServiceConnectorBase@@UEAA@XZ`
- size: `115`
- prototype: `void __fastcall(CMFAppServiceConnectorBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011b8d0`
- `0x18015a5e0`

## callees

- `0x180004870`
- `0x18015a920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18015a320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a2dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a2ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a300`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a2dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a2ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a300`

## pseudocode

```c
void __fastcall CMFAppServiceConnectorBase::~CMFAppServiceConnectorBase(CMFAppServiceConnectorBase *this)
{
  *(_QWORD *)this = &CMFAppServiceConnectorBase::`vftable';
  CMFAppServiceConnectorBase::CloseConnection(this);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 128);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18015a2b4  push    rbx
0x18015a2b6  sub     rsp, 20h
0x18015a2ba  lea     rax, ??_7CMFAppServiceConnectorBase@@6B@; const CMFAppServiceConnectorBase::`vftable'
0x18015a2c1  mov     rbx, rcx
0x18015a2c4  mov     [rcx], rax
0x18015a2c7  call    ?CloseConnection@CMFAppServiceConnectorBase@@MEAAXXZ; CMFAppServiceConnectorBase::CloseConnection(void)
0x18015a2cc  lea     rcx, [rbx+80h]
0x18015a2d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015a2d8  mov     rcx, [rbx+60h]; string
0x18015a2dc  call    cs:__imp_WindowsDeleteString
0x18015a2e2  mov     qword ptr [rbx+60h], 0
0x18015a2ea  mov     rcx, [rbx+58h]; string
0x18015a2ee  call    cs:__imp_WindowsDeleteString
0x18015a2f4  mov     qword ptr [rbx+58h], 0
0x18015a2fc  mov     rcx, [rbx+50h]; string
0x18015a300  call    cs:__imp_WindowsDeleteString
0x18015a306  lea     rcx, [rbx+40h]
0x18015a30a  mov     qword ptr [rbx+50h], 0
0x18015a312  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015a317  lea     rcx, [rbx+18h]
0x18015a31b  add     rsp, 20h
0x18015a31f  pop     rbx
0x18015a320  jmp     cs:__imp_DeleteCriticalSection
```
