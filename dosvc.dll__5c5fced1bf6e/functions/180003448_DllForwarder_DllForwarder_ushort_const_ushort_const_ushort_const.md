# DllForwarder::DllForwarder(ushort const *,ushort const *,ushort const *)

- ea: `0x180003448`
- end: `0x18000354f`
- name: `??0DllForwarder@@QEAA@PEBG00@Z`
- size: `263`
- prototype: `DllForwarder *__fastcall(DllForwarder *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180001f60`

## callees

- `0x180002610`
- `0x180003448`
- `0x180003558`
- `0x180003590`
- `0x1800035b0`
- `0x1800036b4`
- `0x180003b68`
- `0x180005020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800034d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000351f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800034d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000351f`

## string_xrefs

- `0x180003518`: `doclient.dll`

## pseudocode

```c
DllForwarder *__fastcall DllForwarder::DllForwarder(
        DllForwarder *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  DllForwarder *v4; // rbx
  _QWORD *v5; // rdi
  __int64 *v6; // rax
  __int64 v7; // rdx
  const WCHAR *v8; // rcx
  HMODULE Library; // rax
  HMODULE v10; // rax
  _BYTE v12[8]; // [rsp+28h] [rbp-50h] BYREF
  DllForwarder *v13; // [rsp+30h] [rbp-48h]
  char *v14; // [rsp+38h] [rbp-40h]
  LPCWSTR lpLibFileName[4]; // [rsp+40h] [rbp-38h] BYREF

  v4 = this;
  v13 = this;
  *(_QWORD *)this = 0;
  v5 = (_QWORD *)((char *)this + 8);
  v14 = (char *)this + 8;
  *((_QWORD *)this + 1) = 0;
  try
  {
    v6 = (__int64 *)std::make_unique<uus::Session,unsigned short const * &,0>(v12);
    v7 = *v6;
    *v6 = 0;
    std::unique_ptr<uus::Session>::reset(v4, v7);
    std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(v12);
    uus::Session::GetFullPath(*(_QWORD *)v4, lpLibFileName);
    v8 = (const WCHAR *)lpLibFileName;
    if ( lpLibFileName[3] > (LPCWSTR)7 )
      v8 = lpLibFileName[0];
    Library = LoadLibraryExW(v8, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v5,
      Library);
    std::wstring::_Tidy_deallocate(lpLibFileName);
  }
  catch ( ... )
  {
    v4 = v13;
    v5 = v14;
  }
  if ( !*v5 )
  {
    std::unique_ptr<uus::Session>::reset(v4, 0);
    v10 = LoadLibraryExW(L"doclient.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v5,
      v10);
  }
  return v4;
}

```

## disassembly

```asm
0x180003448  mov     r11, rsp
0x18000344b  mov     [r11+10h], rbx
0x18000344f  push    rdi
0x180003450  sub     rsp, 70h
0x180003454  mov     rax, cs:__security_cookie
0x18000345b  xor     rax, rsp
0x18000345e  mov     [rsp+78h+var_18], rax
0x180003463  mov     rbx, rcx
0x180003466  mov     [r11-48h], rcx
0x18000346a  lea     rax, aDeliveryoptimi; "deliveryoptimization"
0x180003471  mov     [r11-58h], rax
0x180003475  mov     qword ptr [rcx], 0
0x18000347c  lea     rdi, [rcx+8]
0x180003480  mov     [rsp+78h+var_40], rdi
0x180003485  mov     qword ptr [rdi], 0
0x18000348c  lea     rdx, [r11-58h]
0x180003490  lea     rcx, [r11-50h]
0x180003494  call    ??$make_unique@USession@uus@@AEAPEBG$0A@@std@@YA?AV?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@0@AEAPEBG@Z; std::make_unique<uus::Session,ushort const * &,0>(ushort const * &)
0x180003499  mov     rdx, [rax]
0x18000349c  mov     qword ptr [rax], 0
0x1800034a3  mov     rcx, rbx
0x1800034a6  call    ?reset@?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAAXPEAUSession@uus@@@Z; std::unique_ptr<uus::Session>::reset(uus::Session *)
0x1800034ab  lea     rcx, [rsp+78h+var_50]
0x1800034b0  call    ??1?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAA@XZ; std::unique_ptr<uus::Session>::~unique_ptr<uus::Session>(void)
0x1800034b5  lea     rdx, [rsp+78h+lpLibFileName]
0x1800034ba  mov     rcx, [rbx]
0x1800034bd  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEBG@Z; uus::Session::GetFullPath(ushort const *)
0x1800034c2  lea     rcx, [rsp+78h+lpLibFileName]
0x1800034c7  cmp     [rsp+78h+var_20], 7
0x1800034cd  cmova   rcx, [rsp+78h+lpLibFileName]; lpLibFileName
0x1800034d3  xor     r8d, r8d; dwFlags
0x1800034d6  xor     edx, edx; hFile
0x1800034d8  call    cs:__imp_LoadLibraryExW
0x1800034de  mov     rdx, rax
0x1800034e1  mov     rcx, rdi
0x1800034e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800034e9  lea     rcx, [rsp+78h+lpLibFileName]
0x1800034ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800034f3  nop
0x1800034f4  jmp     short loc_180003500
0x1800034f6  mov     rbx, [rsp+78h+var_48]
0x1800034fb  mov     rdi, [rsp+78h+var_40]
0x180003500  cmp     qword ptr [rdi], 0
0x180003504  jnz     short loc_180003531
0x180003506  xor     edx, edx
0x180003508  mov     rcx, rbx
0x18000350b  call    ?reset@?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAAXPEAUSession@uus@@@Z; std::unique_ptr<uus::Session>::reset(uus::Session *)
0x180003510  xor     edx, edx; hFile
0x180003512  mov     r8d, 800h; dwFlags
0x180003518  lea     rcx, aDoclientDll; "doclient.dll"
0x18000351f  call    cs:__imp_LoadLibraryExW
0x180003525  mov     rdx, rax
0x180003528  mov     rcx, rdi
0x18000352b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180003530  nop
0x180003531  mov     rax, rbx
0x180003534  mov     rcx, [rsp+78h+var_18]
0x180003539  xor     rcx, rsp; StackCookie
0x18000353c  call    __security_check_cookie
0x180003541  mov     rbx, [rsp+78h+arg_8]
0x180003549  add     rsp, 70h
0x18000354d  pop     rdi
0x18000354e  retn
```
