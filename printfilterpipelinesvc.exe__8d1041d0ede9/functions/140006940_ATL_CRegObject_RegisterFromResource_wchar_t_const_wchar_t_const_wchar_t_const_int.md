# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x140006940`
- end: `0x140006ae8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140007880`

## callees

- `0x140002070`
- `0x1400042a8`
- `0x140004528`
- `0x1400045f4`
- `0x1400050a0`
- `0x140005358`
- `0x1400067cc`
- `0x140006940`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140006aa6`
- `KERNEL32!FreeLibrary` at `0x140006aa6`
- `KERNEL32!LoadLibraryExW` at `0x140006987`
- `KERNEL32!LoadLibraryExW` at `0x140006987`
- `KERNEL32!FindResourceExW` at `0x1400069b5`
- `KERNEL32!FindResourceExW` at `0x1400069b5`
- `KERNEL32!LoadResource` at `0x1400069d3`
- `KERNEL32!LoadResource` at `0x1400069d3`
- `KERNEL32!SizeofResource` at `0x1400069ec`
- `KERNEL32!SizeofResource` at `0x1400069ec`
- `KERNEL32!MultiByteToWideChar` at `0x140006a71`
- `KERNEL32!MultiByteToWideChar` at `0x140006a71`

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
  NCoreLibrary *v7; // rcx
  HMODULE v8; // rdi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  NCoreLibrary *v11; // rcx
  HRSRC v12; // rsi
  unsigned int LastErrorAsHResult; // eax
  const CHAR *v14; // r14
  DWORD cchWideChar; // esi
  unsigned __int64 v16; // rax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  HMODULE v20; // [rsp+38h] [rbp-460h]
  __int64 v21; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v23; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v24[1032]; // [rsp+68h] [rbp-430h] BYREF

  v21 = 0;
  v22[1] = this;
  v22[0] = 0;
  v23 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v20 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, (LPCWSTR)0x462, 0);
    v12 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v14 = (const CHAR *)LoadResource(v8, Resource);
    if ( !v14 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v8, v12);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v9 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v16 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v16 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v24;
        v23 = (LPWSTR)v24;
      }
      else
      {
        ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v23, v16);
        lpWideCharStr = v23;
      }
    }
    catch ( ... )
    {
      v8 = v20;
      lpWideCharStr = v23;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v18 = MultiByteToWideChar(3u, 0, v14, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v23[v18] = 0;
      LastErrorAsHResult = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v22, v23, a5);
    }
    else
    {
LABEL_4:
      LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v11);
    }
    v9 = LastErrorAsHResult;
    goto LABEL_16;
  }
  v9 = NCoreLibrary::GetLastErrorAsHResult(v7);
LABEL_17:
  ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&v23);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
  return v9;
}

```

## disassembly

```asm
0x140006940  mov     [rsp+arg_0], rbx
0x140006945  push    rsi
0x140006946  push    rdi
0x140006947  push    r14
0x140006949  sub     rsp, 480h
0x140006950  mov     rax, cs:__security_cookie
0x140006957  xor     rax, rsp
0x14000695a  mov     [rsp+498h+var_28], rax
0x140006962  mov     rsi, r9
0x140006965  mov     rax, rdx
0x140006968  xor     ebx, ebx
0x14000696a  mov     [rsp+498h+var_450], rbx
0x14000696f  mov     [rsp+498h+var_440], rcx
0x140006974  mov     [rsp+498h+var_448], rbx
0x140006979  mov     [rsp+498h+var_438], rbx
0x14000697e  xor     edx, edx; hFile
0x140006980  lea     r8d, [rbx+2]; dwFlags
0x140006984  mov     rcx, rax; lpLibFileName
0x140006987  call    cs:__imp_LoadLibraryExW
0x14000698d  mov     rdi, rax
0x140006990  mov     [rsp+498h+var_460], rax
0x140006995  test    rax, rax
0x140006998  jnz     short loc_1400069A6
0x14000699a  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14000699f  mov     ebx, eax
0x1400069a1  jmp     loc_140006AAD
0x1400069a6  xor     r9d, r9d; wLanguage
0x1400069a9  mov     r8d, 462h; lpName
0x1400069af  mov     rdx, rsi; lpType
0x1400069b2  mov     rcx, rdi; hModule
0x1400069b5  call    cs:__imp_FindResourceExW
0x1400069bb  mov     rsi, rax
0x1400069be  test    rax, rax
0x1400069c1  jnz     short loc_1400069CD
0x1400069c3  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x1400069c8  jmp     loc_140006AA1
0x1400069cd  mov     rdx, rsi; hResInfo
0x1400069d0  mov     rcx, rdi; hModule
0x1400069d3  call    cs:__imp_LoadResource
0x1400069d9  mov     r14, rax
0x1400069dc  mov     [rsp+498h+var_458], rax
0x1400069e1  test    rax, rax
0x1400069e4  jz      short loc_1400069C3
0x1400069e6  mov     rdx, rsi; hResInfo
0x1400069e9  mov     rcx, rdi; hModule
0x1400069ec  call    cs:__imp_SizeofResource
0x1400069f2  mov     esi, eax
0x1400069f4  mov     [rsp+498h+var_468], eax
0x1400069f8  inc     eax
0x1400069fa  cmp     eax, esi
0x1400069fc  jnb     short loc_140006A08
0x1400069fe  mov     ebx, 8007000Eh
0x140006a03  jmp     loc_140006AAD
0x140006a08  mov     ecx, eax
0x140006a0a  mov     edx, 2
0x140006a0f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140006a14  cmp     rax, 400h
0x140006a1a  jbe     short loc_140006A30
0x140006a1c  mov     rdx, rax
0x140006a1f  lea     rcx, [rsp+498h+var_438]
0x140006a24  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140006a29  mov     rax, [rsp+498h+var_438]
0x140006a2e  jmp     short loc_140006A3A
0x140006a30  lea     rax, [rsp+498h+var_430]
0x140006a35  mov     [rsp+498h+var_438], rax
0x140006a3a  jmp     short loc_140006A51
0x140006a3c  xor     ebx, ebx
0x140006a3e  mov     rdi, [rsp+498h+var_460]
0x140006a43  mov     r14, [rsp+498h+var_458]
0x140006a48  mov     esi, [rsp+498h+var_468]
0x140006a4c  mov     rax, [rsp+498h+var_438]
0x140006a51  test    rax, rax
0x140006a54  jnz     short loc_140006A5D
0x140006a56  mov     ebx, 8007000Eh
0x140006a5b  jmp     short loc_140006AA3
0x140006a5d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x140006a61  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x140006a66  mov     r9d, esi; cbMultiByte
0x140006a69  mov     r8, r14; lpMultiByteStr
0x140006a6c  xor     edx, edx; dwFlags
0x140006a6e  lea     ecx, [rdx+3]; CodePage
0x140006a71  call    cs:__imp_MultiByteToWideChar
0x140006a77  test    eax, eax
0x140006a79  jz      loc_1400069C3
0x140006a7f  mov     ecx, eax
0x140006a81  mov     rax, [rsp+498h+var_438]
0x140006a86  mov     [rax+rcx*2], bx
0x140006a8a  mov     r8d, [rsp+498h+arg_20]; int
0x140006a92  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x140006a97  lea     rcx, [rsp+498h+var_448]; this
0x140006a9c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x140006aa1  mov     ebx, eax
0x140006aa3  mov     rcx, rdi; hLibModule
0x140006aa6  call    cs:__imp_FreeLibrary
0x140006aac  nop
0x140006aad  lea     rcx, [rsp+498h+var_438]
0x140006ab2  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x140006ab7  nop
0x140006ab8  lea     rcx, [rsp+498h+var_450]
0x140006abd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140006ac2  mov     eax, ebx
0x140006ac4  mov     rcx, [rsp+498h+var_28]
0x140006acc  xor     rcx, rsp; StackCookie
0x140006acf  call    __security_check_cookie
0x140006ad4  mov     rbx, [rsp+498h+arg_0]
0x140006adc  add     rsp, 480h
0x140006ae3  pop     r14
0x140006ae5  pop     rdi
0x140006ae6  pop     rsi
0x140006ae7  retn
```
