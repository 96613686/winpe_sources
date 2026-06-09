# EapLm::Peer::BaseEapMethodRuntime::Initialize(void)

- ea: `0x180019200`
- end: `0x180019266`
- name: `?Initialize@BaseEapMethodRuntime@Peer@EapLm@@UEAAXXZ`
- size: `102`
- prototype: `void __fastcall(EapLm::Peer::BaseEapMethodRuntime *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180013e00`
- `0x180016850`

## callees

- `0x1800118e8`
- `0x180019200`
- `0x18001926c`
- `0x18001dcbc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180019224`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180019224`

## string_xrefs

- `0x180019241`: `LoadLibrary`

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
0x180019200  mov     [rsp+arg_0], rbx
0x180019205  push    rdi
0x180019206  sub     rsp, 20h
0x18001920a  mov     rbx, rcx
0x18001920d  call    ?LoadConfig@BaseEapMethodRuntime@Peer@EapLm@@IEAAXXZ; EapLm::Peer::BaseEapMethodRuntime::LoadConfig(void)
0x180019212  lea     rdi, [rbx+90h]
0x180019219  mov     rcx, rdi
0x18001921c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180019221  mov     rcx, rax; lpLibFileName
0x180019224  call    cs:__imp_LoadLibraryW
0x18001922a  mov     [rbx+80h], rax
0x180019231  test    rax, rax
0x180019234  jnz     short loc_180019254
0x180019236  mov     rcx, rdi
0x180019239  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001923e  mov     rdx, rax; wchar_t *
0x180019241  lea     rcx, aLoadlibrary; "LoadLibrary"
0x180019248  mov     r8d, 80070057h; int
0x18001924e  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180019254  mov     byte ptr [rbx+88h], 1
0x18001925b  mov     rbx, [rsp+28h+arg_0]
0x180019260  add     rsp, 20h
0x180019264  pop     rdi
0x180019265  retn
```
