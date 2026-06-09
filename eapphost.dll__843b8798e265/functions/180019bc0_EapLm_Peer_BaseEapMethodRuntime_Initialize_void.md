# EapLm::Peer::BaseEapMethodRuntime::Initialize(void)

- ea: `0x180019bc0`
- end: `0x180019c2d`
- name: `?Initialize@BaseEapMethodRuntime@Peer@EapLm@@UEAAXXZ`
- size: `109`
- prototype: `void __fastcall(EapLm::Peer::BaseEapMethodRuntime *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800145f0`
- `0x1800170e0`

## callees

- `0x18001204c`
- `0x180019bc0`
- `0x180019c34`
- `0x18001e7c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180019be4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180019be4`

## string_xrefs

- `0x180019c07`: `LoadLibrary`

## pseudocode

```c
void __fastcall EapLm::Peer::BaseEapMethodRuntime::Initialize(EapLm::Peer::BaseEapMethodRuntime *this)
{
  const WCHAR *v2; // rax
  HMODULE LibraryW; // rax
  const wchar_t *v4; // rax

  EapLm::Peer::BaseEapMethodRuntime::LoadConfig(this);
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 144);
  LibraryW = LoadLibraryW(v2);
  *((_QWORD *)this + 16) = LibraryW;
  if ( !LibraryW )
  {
    v4 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 144);
    EapHost::EapException::Throw(L"LoadLibrary", v4, -2147024809);
  }
  *((_BYTE *)this + 136) = 1;
}

```

## disassembly

```asm
0x180019bc0  mov     [rsp+arg_0], rbx
0x180019bc5  push    rdi
0x180019bc6  sub     rsp, 20h
0x180019bca  mov     rbx, rcx
0x180019bcd  call    ?LoadConfig@BaseEapMethodRuntime@Peer@EapLm@@IEAAXXZ; EapLm::Peer::BaseEapMethodRuntime::LoadConfig(void)
0x180019bd2  lea     rdi, [rbx+90h]
0x180019bd9  mov     rcx, rdi
0x180019bdc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019be1  mov     rcx, rax; lpLibFileName
0x180019be4  call    cs:__imp_LoadLibraryW
0x180019beb  nop     dword ptr [rax+rax+00h]
0x180019bf0  mov     [rbx+80h], rax
0x180019bf7  test    rax, rax
0x180019bfa  jnz     short loc_180019C1A
0x180019bfc  mov     rcx, rdi
0x180019bff  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019c04  mov     rdx, rax; wchar_t *
0x180019c07  lea     rcx, aLoadlibrary; "LoadLibrary"
0x180019c0e  mov     r8d, 80070057h; int
0x180019c14  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180019c1a  mov     byte ptr [rbx+88h], 1
0x180019c21  mov     rbx, [rsp+28h+arg_0]
0x180019c26  add     rsp, 20h
0x180019c2a  pop     rdi
0x180019c2b  retn
```
