# dxc::TextConvertor::FontSubDll::TryLoadDll(void)

- ea: `0x18029e53c`
- end: `0x18029e66f`
- name: `?TryLoadDll@FontSubDll@TextConvertor@dxc@@QEAA_NXZ`
- size: `307`
- prototype: `bool __fastcall(dxc::TextConvertor::FontSubDll *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18029dba4`

## callees

- `0x18025b100`
- `0x18025bb98`
- `0x180299298`
- `0x18029b95c`
- `0x18029cf3c`
- `0x18029d4cc`
- `0x18029e53c`
- `0x18029ed7c`
- `0x18029f0dc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18029e60f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18029e60f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18029e5f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18029e5f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18029e58a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18029e58a`

## string_xrefs

- `0x18029e605`: `CreateFontPackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall dxc::TextConvertor::FontSubDll::TryLoadDll(dxc::TextConvertor::FontSubDll *this)
{
  const char *v2; // rdx
  UINT SystemDirectoryW; // edi
  int v4; // r8d
  dxc *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  const WCHAR *v12; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const char *v15; // rdx
  dxc *v16; // rcx
  int v17; // r8d
  int v18; // eax
  _BYTE v20[32]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !*((_DWORD *)this + 4) )
  {
    memset_0(Buffer, 0, 0x208u);
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    v5 = (dxc *)(SystemDirectoryW - 1);
    if ( (unsigned int)v5 > 0x102 || !Buffer[0] )
      dxc::ThrowLogicException(v5, v2, v4);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>(
      v20,
      Buffer);
    if ( *(_WORD *)(std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20, v6, v7, v8) + 2LL
                                                                                           * (SystemDirectoryW - 1)) != 92 )
      std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::push_back(v20);
    std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::operator+=(v20);
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20, v9, v10, v11);
    Library = LoadLibraryExW(v12, 0, 8u);
    *(_QWORD *)this = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "CreateFontPackage");
      *((_QWORD *)this + 1) = ProcAddress;
      if ( !ProcAddress )
        dxc::ThrowLogicException(v16, v15, v17);
      v18 = 1;
    }
    else
    {
      v18 = 2;
    }
    *((_DWORD *)this + 4) = v18;
    std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>(v20);
  }
  return *((_DWORD *)this + 4) == 1;
}

```

## disassembly

```asm
0x18029e53c  mov     [rsp+arg_8], rbx
0x18029e541  mov     [rsp+arg_10], rsi
0x18029e546  push    rdi
0x18029e547  sub     rsp, 260h
0x18029e54e  mov     rax, cs:__security_cookie
0x18029e555  xor     rax, rsp
0x18029e558  mov     [rsp+268h+var_18], rax
0x18029e560  mov     rbx, rcx
0x18029e563  xor     esi, esi
0x18029e565  cmp     [rcx+10h], esi
0x18029e568  jnz     loc_18029E63D
0x18029e56e  xor     edx, edx; Val
0x18029e570  mov     r8d, 208h; Size
0x18029e576  lea     rcx, [rsp+268h+Buffer]; void *
0x18029e57b  call    memset_0
0x18029e580  mov     edx, 104h; uSize
0x18029e585  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x18029e58a  call    cs:__imp_GetSystemDirectoryW
0x18029e590  mov     edi, eax
0x18029e592  lea     ecx, [rax-1]; this
0x18029e595  cmp     ecx, 102h
0x18029e59b  ja      loc_18029E669
0x18029e5a1  cmp     [rsp+268h+Buffer], si
0x18029e5a6  jz      loc_18029E669
0x18029e5ac  lea     rdx, [rsp+268h+Buffer]
0x18029e5b1  lea     rcx, [rsp+268h+var_248]
0x18029e5b6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>(wchar_t const * const)
0x18029e5bb  nop
0x18029e5bc  lea     rcx, [rsp+268h+var_248]
0x18029e5c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18029e5c6  lea     ecx, [rdi-1]
0x18029e5c9  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x18029e5ce  jz      short loc_18029E5DA
0x18029e5d0  lea     rcx, [rsp+268h+var_248]
0x18029e5d5  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAAX_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::push_back(wchar_t)
0x18029e5da  lea     rcx, [rsp+268h+var_248]
0x18029e5df  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAAAEAV01@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::operator+=(wchar_t const * const)
0x18029e5e4  lea     rcx, [rsp+268h+var_248]
0x18029e5e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18029e5ee  mov     rcx, rax; lpLibFileName
0x18029e5f1  xor     edx, edx; hFile
0x18029e5f3  lea     r8d, [rdx+8]; dwFlags
0x18029e5f7  call    cs:__imp_LoadLibraryExW
0x18029e5fd  mov     [rbx], rax
0x18029e600  test    rax, rax
0x18029e603  jz      short loc_18029E62B
0x18029e605  lea     rdx, aCreatefontpack; "CreateFontPackage"
0x18029e60c  mov     rcx, rax; hModule
0x18029e60f  call    cs:__imp_GetProcAddress
0x18029e615  mov     [rbx+8], rax
0x18029e619  test    rax, rax
0x18029e61c  jnz     short loc_18029E624
0x18029e61e  call    ?ThrowLogicException@dxc@@YAXPEBDH@Z; dxc::ThrowLogicException(char const *,int)
0x18029e624  mov     eax, 1
0x18029e629  jmp     short loc_18029E630
0x18029e62b  mov     eax, 2
0x18029e630  mov     [rbx+10h], eax
0x18029e633  lea     rcx, [rsp+268h+var_248]
0x18029e638  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$NonThrowingNewStlAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,NonThrowingNewStlAllocator<wchar_t>>(void)
0x18029e63d  cmp     dword ptr [rbx+10h], 1
0x18029e641  setz    al
0x18029e644  mov     rcx, [rsp+268h+var_18]
0x18029e64c  xor     rcx, rsp; StackCookie
0x18029e64f  call    __security_check_cookie
0x18029e654  lea     r11, [rsp+268h+var_8]
0x18029e65c  mov     rbx, [r11+18h]
0x18029e660  mov     rsi, [r11+20h]
0x18029e664  mov     rsp, r11
0x18029e667  pop     rdi
0x18029e668  retn
0x18029e669  call    ?ThrowLogicException@dxc@@YAXPEBDH@Z; dxc::ThrowLogicException(char const *,int)
```
