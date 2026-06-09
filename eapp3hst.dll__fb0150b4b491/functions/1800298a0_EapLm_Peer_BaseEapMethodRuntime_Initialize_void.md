# EapLm::Peer::BaseEapMethodRuntime::Initialize(void)

- ea: `0x1800298a0`
- end: `0x180029906`
- name: `?Initialize@BaseEapMethodRuntime@Peer@EapLm@@UEAAXXZ`
- size: `102`
- prototype: `void __fastcall(EapLm::Peer::BaseEapMethodRuntime *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800247e0`
- `0x1800270e0`

## callees

- `0x18000eb74`
- `0x180015534`
- `0x1800298a0`
- `0x18002990c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800298c4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800298c4`

## string_xrefs

- `0x1800298e1`: `LoadLibrary`

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
0x1800298a0  mov     [rsp+arg_0], rbx
0x1800298a5  push    rdi
0x1800298a6  sub     rsp, 20h
0x1800298aa  mov     rbx, rcx
0x1800298ad  call    ?LoadConfig@BaseEapMethodRuntime@Peer@EapLm@@IEAAXXZ; EapLm::Peer::BaseEapMethodRuntime::LoadConfig(void)
0x1800298b2  lea     rdi, [rbx+90h]
0x1800298b9  mov     rcx, rdi
0x1800298bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800298c1  mov     rcx, rax; lpLibFileName
0x1800298c4  call    cs:__imp_LoadLibraryW
0x1800298ca  mov     [rbx+80h], rax
0x1800298d1  test    rax, rax
0x1800298d4  jnz     short loc_1800298F4
0x1800298d6  mov     rcx, rdi
0x1800298d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800298de  mov     rdx, rax; wchar_t *
0x1800298e1  lea     rcx, aLoadlibrary; "LoadLibrary"
0x1800298e8  mov     r8d, 80070057h; int
0x1800298ee  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x1800298f4  mov     byte ptr [rbx+88h], 1
0x1800298fb  mov     rbx, [rsp+28h+arg_0]
0x180029900  add     rsp, 20h
0x180029904  pop     rdi
0x180029905  retn
```
