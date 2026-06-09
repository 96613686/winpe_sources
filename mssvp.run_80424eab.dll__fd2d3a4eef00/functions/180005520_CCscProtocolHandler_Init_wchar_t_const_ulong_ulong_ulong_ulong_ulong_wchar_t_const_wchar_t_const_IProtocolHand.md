# CCscProtocolHandler::Init(wchar_t const *,ulong,ulong,ulong,ulong,ulong,wchar_t const *,wchar_t const *,IProtocolHandlerSite *)

- ea: `0x180005520`
- end: `0x180005574`
- name: `?Init@CCscProtocolHandler@@UEAAJPEB_WKKKKK00PEAUIProtocolHandlerSite@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(CCscProtocolHandler *__hidden this, const wchar_t *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, const wchar_t *, const wchar_t *, struct IProtocolHandlerSite *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005520`
- `0x18000557c`
- `0x1800055a0`
- `0x180035c78`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180005548`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180005548`

## string_xrefs

- `0x180005541`: `cscapi.dll`

## pseudocode

```c
__int64 __fastcall CCscProtocolHandler::Init(CCscProtocolHandler *this, const wchar_t *a2)
{
  unsigned int v3; // edi
  HMODULE LibraryW; // rax

  v3 = 0;
  if ( !(unsigned int)GetPolicyDwordAsBool(L"PreventIndexingOfflineFiles", 0) )
  {
    LibraryW = LoadLibraryW(L"cscapi.dll");
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 64,
      LibraryW);
    if ( !*((_QWORD *)this + 8) )
      return (unsigned int)ResultFromLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x180005520  mov     [rsp+arg_0], rbx
0x180005525  push    rdi
0x180005526  sub     rsp, 20h
0x18000552a  mov     rbx, rcx
0x18000552d  xor     edx, edx; int
0x18000552f  lea     rcx, aPreventindexin_1; "PreventIndexingOfflineFiles"
0x180005536  xor     edi, edi
0x180005538  call    ?GetPolicyDwordAsBool@@YAHPEB_WH@Z; GetPolicyDwordAsBool(wchar_t const *,int)
0x18000553d  test    eax, eax
0x18000553f  jnz     short loc_180005567
0x180005541  lea     rcx, LibFileName; "cscapi.dll"
0x180005548  call    cs:__imp_LoadLibraryW
0x18000554e  mov     rdx, rax
0x180005551  lea     rcx, [rbx+40h]
0x180005555  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18000555a  cmp     [rbx+40h], rdi
0x18000555e  jnz     short loc_180005567
0x180005560  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180005565  mov     edi, eax
0x180005567  mov     rbx, [rsp+28h+arg_0]
0x18000556c  mov     eax, edi
0x18000556e  add     rsp, 20h
0x180005572  pop     rdi
0x180005573  retn
```
