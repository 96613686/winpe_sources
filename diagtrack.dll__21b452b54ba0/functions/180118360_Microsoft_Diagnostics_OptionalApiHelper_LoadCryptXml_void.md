# Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(void)

- ea: `0x180118360`
- end: `0x180118479`
- name: `?LoadCryptXml@OptionalApiHelper@Diagnostics@Microsoft@@AEAAXXZ`
- size: `281`
- prototype: `void __fastcall(Microsoft::Diagnostics::OptionalApiHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801179ec`

## callees

- `0x180024558`
- `0x180118360`
- `0x1801ce3c4`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180118390`
- `msvcp_win!_Mtx_unlock` at `0x180118390`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801183dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801183f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18011840b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180118422`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180118439`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180118450`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180118467`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801183dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801183f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18011840b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180118422`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180118439`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180118450`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180118467`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801183b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801183b7`

## string_xrefs

- `0x1801183a3`: `cryptxml.dll`
- `0x1801183d6`: `CryptXmlClose`
- `0x1801183fd`: `CryptXmlGetDocContext`
- `0x1801183e6`: `CryptXmlOpenToDecode`
- `0x18011842b`: `CryptXmlGetSignature`
- `0x180118414`: `CryptXmlVerifySignature`
- `0x180118459`: `CryptXmlGetStatus`
- `0x180118442`: `CryptXmlGetReference`

## pseudocode

```c
void __fastcall Microsoft::Diagnostics::OptionalApiHelper::LoadCryptXml(HMODULE *this)
{
  HMODULE *v2; // rdi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v5; // rcx
  FARPROC v6; // rax
  HMODULE v7; // rcx
  FARPROC v8; // rax
  HMODULE v9; // rcx
  FARPROC v10; // rax
  HMODULE v11; // rcx
  FARPROC v12; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  HMODULE v15; // rcx
  _Mtx_t v16; // [rsp+20h] [rbp-18h] BYREF
  char v17; // [rsp+28h] [rbp-10h]

  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v16, this + 31);
  if ( !*((_BYTE *)this + 3) )
  {
    v2 = this + 54;
    Library = LoadLibraryExW(L"cryptxml.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      this + 54,
      Library);
    if ( this[54] )
    {
      ProcAddress = GetProcAddress(this[54], "CryptXmlClose");
      v5 = *v2;
      this[58] = (HMODULE)ProcAddress;
      v6 = GetProcAddress(v5, "CryptXmlOpenToDecode");
      v7 = *v2;
      this[59] = (HMODULE)v6;
      v8 = GetProcAddress(v7, "CryptXmlGetDocContext");
      v9 = *v2;
      this[60] = (HMODULE)v8;
      v10 = GetProcAddress(v9, "CryptXmlVerifySignature");
      v11 = *v2;
      this[61] = (HMODULE)v10;
      v12 = GetProcAddress(v11, "CryptXmlGetSignature");
      v13 = *v2;
      this[62] = (HMODULE)v12;
      v14 = GetProcAddress(v13, "CryptXmlGetReference");
      v15 = *v2;
      this[63] = (HMODULE)v14;
      this[64] = (HMODULE)GetProcAddress(v15, "CryptXmlGetStatus");
    }
    *((_BYTE *)this + 3) = 1;
  }
  if ( v17 )
    _Mtx_unlock(v16);
}

```

## disassembly

```asm
0x180118360  mov     [rsp+arg_0], rbx
0x180118365  push    rdi
0x180118366  sub     rsp, 30h
0x18011836a  mov     rbx, rcx
0x18011836d  lea     rdx, [rcx+0F8h]
0x180118374  lea     rcx, [rsp+38h+var_18]
0x180118379  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18011837e  cmp     byte ptr [rbx+3], 0
0x180118382  jz      short loc_1801183A1
0x180118384  cmp     [rsp+38h+var_10], 0
0x180118389  jz      short loc_180118396
0x18011838b  mov     rcx, [rsp+38h+var_18]; _Mtx_t
0x180118390  call    cs:__imp__Mtx_unlock
0x180118396  mov     rbx, [rsp+38h+arg_0]
0x18011839b  add     rsp, 30h
0x18011839f  pop     rdi
0x1801183a0  retn
0x1801183a1  xor     edx, edx; hFile
0x1801183a3  lea     rcx, aCryptxmlDll; "cryptxml.dll"
0x1801183aa  mov     r8d, 800h; dwFlags
0x1801183b0  lea     rdi, [rbx+1B0h]
0x1801183b7  call    cs:__imp_LoadLibraryExW
0x1801183bd  mov     rdx, rax
0x1801183c0  mov     rcx, rdi
0x1801183c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1801183c8  mov     rcx, [rdi]; hModule
0x1801183cb  test    rcx, rcx
0x1801183ce  jnz     short loc_1801183D6
0x1801183d0  mov     byte ptr [rbx+3], 1
0x1801183d4  jmp     short loc_180118384
0x1801183d6  lea     rdx, aCryptxmlclose; "CryptXmlClose"
0x1801183dd  call    cs:__imp_GetProcAddress
0x1801183e3  mov     rcx, [rdi]; hModule
0x1801183e6  lea     rdx, aCryptxmlopento; "CryptXmlOpenToDecode"
0x1801183ed  mov     [rbx+1D0h], rax
0x1801183f4  call    cs:__imp_GetProcAddress
0x1801183fa  mov     rcx, [rdi]; hModule
0x1801183fd  lea     rdx, aCryptxmlgetdoc; "CryptXmlGetDocContext"
0x180118404  mov     [rbx+1D8h], rax
0x18011840b  call    cs:__imp_GetProcAddress
0x180118411  mov     rcx, [rdi]; hModule
0x180118414  lea     rdx, aCryptxmlverify; "CryptXmlVerifySignature"
0x18011841b  mov     [rbx+1E0h], rax
0x180118422  call    cs:__imp_GetProcAddress
0x180118428  mov     rcx, [rdi]; hModule
0x18011842b  lea     rdx, aCryptxmlgetsig; "CryptXmlGetSignature"
0x180118432  mov     [rbx+1E8h], rax
0x180118439  call    cs:__imp_GetProcAddress
0x18011843f  mov     rcx, [rdi]; hModule
0x180118442  lea     rdx, aCryptxmlgetref; "CryptXmlGetReference"
0x180118449  mov     [rbx+1F0h], rax
0x180118450  call    cs:__imp_GetProcAddress
0x180118456  mov     rcx, [rdi]; hModule
0x180118459  lea     rdx, aCryptxmlgetsta; "CryptXmlGetStatus"
0x180118460  mov     [rbx+1F8h], rax
0x180118467  call    cs:__imp_GetProcAddress
0x18011846d  mov     [rbx+200h], rax
0x180118474  jmp     loc_1801183D0
```
