# CRemoteLockNode::GetLockMessage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18006939c`
- end: `0x1800694de`
- name: `?GetLockMessage@CRemoteLockNode@@AEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18006997c`

## callees

- `0x180002714`
- `0x180008de0`
- `0x180009cc4`
- `0x1800239a4`
- `0x180062e30`
- `0x1800634fc`
- `0x18006939c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006943e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006943e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800693d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800693d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800693f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006944e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800693f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006944e`

## string_xrefs

- `0x1800693cd`: `DMAppsRes.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteLockNode::GetLockMessage(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  HINSTANCE v4; // rbx
  signed int LastError; // ebx
  int v6; // r8d
  int v7; // r9d
  __int16 *v8; // rdx
  __int64 v9; // r8
  signed int v11; // [rsp+30h] [rbp-D0h] BYREF
  HINSTANCE hInstance; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[128]; // [rsp+40h] [rbp-C0h] BYREF

  hInstance = 0;
  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x822u);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    &hInstance,
    Library);
  v4 = hInstance;
  if ( !hInstance )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180155BA8 <= 2 )
      goto LABEL_8;
    v8 = word_180133E42;
    goto LABEL_7;
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( LoadStringW(v4, 0x65ECu, Buffer, 128) )
  {
    v9 = -1;
    do
      ++v9;
    while ( Buffer[v9] );
    std::wstring::_Assign<unsigned short>(a2, Buffer);
    LastError = 0;
    goto LABEL_13;
  }
  LastError = GetLastError();
  if ( (unsigned int)dword_180155BA8 > 2 )
  {
    v8 = (__int16 *)byte_180133E15;
LABEL_7:
    v11 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180155BA8,
      (_DWORD)v8,
      v6,
      v7,
      (__int64)&v11);
  }
LABEL_8:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hInstance);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18006939c  push    rbp
0x18006939e  push    rbx
0x18006939f  push    rsi
0x1800693a0  push    rdi
0x1800693a1  lea     rbp, [rsp-58h]
0x1800693a6  sub     rsp, 158h
0x1800693ad  mov     rax, cs:__security_cookie
0x1800693b4  xor     rax, rsp
0x1800693b7  mov     [rbp+70h+var_30], rax
0x1800693bb  mov     rdi, rdx
0x1800693be  xor     esi, esi
0x1800693c0  mov     [rsp+170h+hInstance], rsi
0x1800693c5  xor     edx, edx; hFile
0x1800693c7  mov     r8d, 822h; dwFlags
0x1800693cd  lea     rcx, aDmappsresDll; "DMAppsRes.dll"
0x1800693d4  call    cs:__imp_LoadLibraryExW
0x1800693db  nop     dword ptr [rax+rax+00h]
0x1800693e0  mov     rdx, rax
0x1800693e3  lea     rcx, [rsp+170h+hInstance]
0x1800693e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800693ed  mov     rbx, [rsp+170h+hInstance]
0x1800693f2  test    rbx, rbx
0x1800693f5  jnz     short loc_180069419
0x1800693f7  call    cs:__imp_GetLastError
0x1800693fe  nop     dword ptr [rax+rax+00h]
0x180069403  mov     ebx, eax
0x180069405  mov     ecx, cs:dword_180155BA8
0x18006940b  cmp     ecx, 2
0x18006940e  jbe     short loc_180069488
0x180069410  lea     rdx, word_180133E42
0x180069417  jmp     short loc_18006946E
0x180069419  xor     edx, edx; Val
0x18006941b  mov     r8d, 100h; Size
0x180069421  lea     rcx, [rsp+170h+Buffer]; void *
0x180069426  call    memset_0
0x18006942b  mov     r9d, 80h; cchBufferMax
0x180069431  lea     r8, [rsp+170h+Buffer]; lpBuffer
0x180069436  mov     edx, 65ECh; uID
0x18006943b  mov     rcx, rbx; hInstance
0x18006943e  call    cs:__imp_LoadStringW
0x180069445  nop     dword ptr [rax+rax+00h]
0x18006944a  test    eax, eax
0x18006944c  jnz     short loc_180069497
0x18006944e  call    cs:__imp_GetLastError
0x180069455  nop     dword ptr [rax+rax+00h]
0x18006945a  mov     ebx, eax
0x18006945c  mov     ecx, cs:dword_180155BA8
0x180069462  cmp     ecx, 2
0x180069465  jbe     short loc_180069488
0x180069467  lea     rdx, byte_180133E15
0x18006946e  lea     rax, [rsp+170h+var_140]
0x180069473  mov     [rsp+170h+var_150], rax
0x180069478  mov     [rsp+170h+var_140], ebx
0x18006947c  lea     rcx, dword_180155BA8
0x180069483  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180069488  test    ebx, ebx
0x18006948a  jle     short loc_1800694B9
0x18006948c  movzx   ebx, bx
0x18006948f  or      ebx, 80070000h
0x180069495  jmp     short loc_1800694B9
0x180069497  lea     rax, [rsp+170h+Buffer]
0x18006949c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800694a0  inc     r8
0x1800694a3  cmp     [rax+r8*2], si
0x1800694a8  jnz     short loc_1800694A0
0x1800694aa  lea     rdx, [rsp+170h+Buffer]
0x1800694af  mov     rcx, rdi
0x1800694b2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800694b7  mov     ebx, esi
0x1800694b9  lea     rcx, [rsp+170h+hInstance]
0x1800694be  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800694c3  mov     eax, ebx
0x1800694c5  mov     rcx, [rbp+70h+var_30]
0x1800694c9  xor     rcx, rsp; StackCookie
0x1800694cc  call    __security_check_cookie
0x1800694d1  add     rsp, 158h
0x1800694d8  pop     rdi
0x1800694d9  pop     rsi
0x1800694da  pop     rbx
0x1800694db  pop     rbp
0x1800694dc  retn
```
