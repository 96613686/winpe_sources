# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x1800105b0`
- end: `0x180010756`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `422`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180010f84`

## callees

- `0x1800017a0`
- `0x18000ee0c`
- `0x18000ee68`
- `0x18000eec0`
- `0x18000f864`
- `0x18000fac0`
- `0x18001043c`
- `0x1800105b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800105f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800105f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180010641`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180010641`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180010623`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180010623`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010714`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010714`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001065a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001065a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800106df`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800106df`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v7; // rdi
  unsigned int v8; // ebx
  HRSRC Resource; // rax
  HRSRC v10; // rsi
  unsigned int Error; // eax
  const CHAR *v12; // r14
  DWORD cchWideChar; // esi
  size_t v14; // rax
  WCHAR *lpWideCharStr; // rax
  int v16; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  __int64 v19; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v22[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19 = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  v18 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, (LPCWSTR)1, 0);
    v10 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v12 = (const CHAR *)LoadResource(v7, Resource);
    if ( !v12 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v7, v10);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v8 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v14 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v14 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v22;
        v21 = (LPWSTR)v22;
      }
      else
      {
        ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, v14);
        lpWideCharStr = v21;
      }
    }
    catch ( ... )
    {
      v7 = v18;
      lpWideCharStr = v21;
    }
    if ( !lpWideCharStr )
    {
      v8 = -2147024882;
LABEL_16:
      FreeLibrary(v7);
      goto LABEL_17;
    }
    v16 = MultiByteToWideChar(3u, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v16 )
    {
      v21[v16] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v8 = Error;
    goto LABEL_16;
  }
  v8 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&v21);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v8;
}

```

## disassembly

```asm
0x1800105b0  mov     [rsp+arg_0], rbx
0x1800105b5  push    rsi
0x1800105b6  push    rdi
0x1800105b7  push    r14
0x1800105b9  sub     rsp, 480h
0x1800105c0  mov     rax, cs:__security_cookie
0x1800105c7  xor     rax, rsp
0x1800105ca  mov     [rsp+498h+var_28], rax
0x1800105d2  mov     rsi, r9
0x1800105d5  mov     rax, rdx
0x1800105d8  xor     ebx, ebx
0x1800105da  mov     [rsp+498h+var_450], rbx
0x1800105df  mov     [rsp+498h+var_440], rcx
0x1800105e4  mov     [rsp+498h+var_448], rbx
0x1800105e9  mov     [rsp+498h+var_438], rbx
0x1800105ee  xor     edx, edx; hFile
0x1800105f0  lea     r8d, [rbx+2]; dwFlags
0x1800105f4  mov     rcx, rax; lpLibFileName
0x1800105f7  call    cs:__imp_LoadLibraryExW
0x1800105fd  mov     rdi, rax
0x180010600  mov     [rsp+498h+var_460], rax
0x180010605  test    rax, rax
0x180010608  jnz     short loc_180010616
0x18001060a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001060f  mov     ebx, eax
0x180010611  jmp     loc_18001071B
0x180010616  xor     r9d, r9d; wLanguage
0x180010619  lea     r8d, [r9+1]; lpName
0x18001061d  mov     rdx, rsi; lpType
0x180010620  mov     rcx, rdi; hModule
0x180010623  call    cs:__imp_FindResourceExW
0x180010629  mov     rsi, rax
0x18001062c  test    rax, rax
0x18001062f  jnz     short loc_18001063B
0x180010631  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010636  jmp     loc_18001070F
0x18001063b  mov     rdx, rsi; hResInfo
0x18001063e  mov     rcx, rdi; hModule
0x180010641  call    cs:__imp_LoadResource
0x180010647  mov     r14, rax
0x18001064a  mov     [rsp+498h+var_458], rax
0x18001064f  test    rax, rax
0x180010652  jz      short loc_180010631
0x180010654  mov     rdx, rsi; hResInfo
0x180010657  mov     rcx, rdi; hModule
0x18001065a  call    cs:__imp_SizeofResource
0x180010660  mov     esi, eax
0x180010662  mov     [rsp+498h+var_468], eax
0x180010666  inc     eax
0x180010668  cmp     eax, esi
0x18001066a  jnb     short loc_180010676
0x18001066c  mov     ebx, 8007000Eh
0x180010671  jmp     loc_18001071B
0x180010676  mov     ecx, eax
0x180010678  mov     edx, 2
0x18001067d  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180010682  cmp     rax, 400h
0x180010688  jbe     short loc_18001069E
0x18001068a  mov     rdx, rax
0x18001068d  lea     rcx, [rsp+498h+var_438]
0x180010692  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180010697  mov     rax, [rsp+498h+var_438]
0x18001069c  jmp     short loc_1800106A8
0x18001069e  lea     rax, [rsp+498h+var_430]
0x1800106a3  mov     [rsp+498h+var_438], rax
0x1800106a8  jmp     short loc_1800106BF
0x1800106aa  xor     ebx, ebx
0x1800106ac  mov     rdi, [rsp+498h+var_460]
0x1800106b1  mov     r14, [rsp+498h+var_458]
0x1800106b6  mov     esi, [rsp+498h+var_468]
0x1800106ba  mov     rax, [rsp+498h+var_438]
0x1800106bf  test    rax, rax
0x1800106c2  jnz     short loc_1800106CB
0x1800106c4  mov     ebx, 8007000Eh
0x1800106c9  jmp     short loc_180010711
0x1800106cb  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x1800106cf  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1800106d4  mov     r9d, esi; cbMultiByte
0x1800106d7  mov     r8, r14; lpMultiByteStr
0x1800106da  xor     edx, edx; dwFlags
0x1800106dc  lea     ecx, [rdx+3]; CodePage
0x1800106df  call    cs:__imp_MultiByteToWideChar
0x1800106e5  test    eax, eax
0x1800106e7  jz      loc_180010631
0x1800106ed  mov     ecx, eax
0x1800106ef  mov     rax, [rsp+498h+var_438]
0x1800106f4  mov     [rax+rcx*2], bx
0x1800106f8  mov     r8d, [rsp+498h+arg_20]; int
0x180010700  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x180010705  lea     rcx, [rsp+498h+var_448]; this
0x18001070a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18001070f  mov     ebx, eax
0x180010711  mov     rcx, rdi; hLibModule
0x180010714  call    cs:__imp_FreeLibrary
0x18001071a  nop
0x18001071b  lea     rcx, [rsp+498h+var_438]
0x180010720  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x180010725  nop
0x180010726  lea     rcx, [rsp+498h+var_450]
0x18001072b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010730  mov     eax, ebx
0x180010732  mov     rcx, [rsp+498h+var_28]
0x18001073a  xor     rcx, rsp; StackCookie
0x18001073d  call    __security_check_cookie
0x180010742  mov     rbx, [rsp+498h+arg_0]
0x18001074a  add     rsp, 480h
0x180010751  pop     r14
0x180010753  pop     rdi
0x180010754  pop     rsi
0x180010755  retn
```
