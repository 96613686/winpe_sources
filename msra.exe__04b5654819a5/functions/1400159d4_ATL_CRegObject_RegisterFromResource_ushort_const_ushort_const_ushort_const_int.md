# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1400159d4`
- end: `0x140015bd3`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `511`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140018254`

## callees

- `0x1400044f8`
- `0x14000d9fc`
- `0x14000e4f8`
- `0x1400105d8`
- `0x140015830`
- `0x1400159d4`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!LoadResource` at `0x140015a71`
- `KERNEL32!LoadResource` at `0x140015a71`
- `KERNEL32!FindResourceExW` at `0x140015a4d`
- `KERNEL32!FindResourceExW` at `0x140015a4d`
- `KERNEL32!LoadLibraryExW` at `0x140015a1b`
- `KERNEL32!LoadLibraryExW` at `0x140015a1b`
- `KERNEL32!MultiByteToWideChar` at `0x140015b41`
- `KERNEL32!MultiByteToWideChar` at `0x140015b41`
- `KERNEL32!SizeofResource` at `0x140015a90`
- `KERNEL32!SizeofResource` at `0x140015a90`
- `KERNEL32!FreeLibrary` at `0x140015b7c`
- `KERNEL32!FreeLibrary` at `0x140015b7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v7; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v10; // rsi
  unsigned int v11; // eax
  const CHAR *v12; // r14
  DWORD cchWideChar; // esi
  DWORD v14; // eax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  _QWORD v19[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v20; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v21[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19[2] = 0;
  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  v18 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
  v10 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v12 = (const CHAR *)LoadResource(v7, Resource);
  if ( !v12 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v7, v10);
  v14 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v14 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v21;
        v20 = (LPWSTR)v21;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2LL * v14);
        lpWideCharStr = v20;
      }
    }
    catch ( ... )
    {
      v7 = v18;
      lpWideCharStr = v20;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v7);
      goto LABEL_21;
    }
    v17 = MultiByteToWideChar(3u, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v20[v17] = 0;
      v11 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1400159d4  mov     [rsp+arg_0], rbx
0x1400159d9  push    rsi
0x1400159da  push    rdi
0x1400159db  push    r14
0x1400159dd  sub     rsp, 480h
0x1400159e4  mov     rax, cs:__security_cookie
0x1400159eb  xor     rax, rsp
0x1400159ee  mov     [rsp+498h+var_28], rax
0x1400159f6  mov     rsi, r9
0x1400159f9  mov     rax, rdx
0x1400159fc  xor     ebx, ebx
0x1400159fe  mov     [rsp+498h+var_440], rbx
0x140015a03  mov     [rsp+498h+var_448], rcx
0x140015a08  mov     [rsp+498h+var_450], rbx
0x140015a0d  mov     [rsp+498h+var_438], rbx
0x140015a12  xor     edx, edx; hFile
0x140015a14  lea     r8d, [rbx+2]; dwFlags
0x140015a18  mov     rcx, rax; lpLibFileName
0x140015a1b  call    cs:__imp_LoadLibraryExW
0x140015a22  nop     dword ptr [rax+rax+00h]
0x140015a27  mov     rdi, rax
0x140015a2a  mov     [rsp+498h+var_460], rax
0x140015a2f  test    rax, rax
0x140015a32  jnz     short loc_140015A40
0x140015a34  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140015a39  mov     ebx, eax
0x140015a3b  jmp     loc_140015B89
0x140015a40  xor     r9d, r9d; wLanguage
0x140015a43  lea     r8d, [r9+65h]; lpName
0x140015a47  mov     rdx, rsi; lpType
0x140015a4a  mov     rcx, rdi; hModule
0x140015a4d  call    cs:__imp_FindResourceExW
0x140015a54  nop     dword ptr [rax+rax+00h]
0x140015a59  mov     rsi, rax
0x140015a5c  test    rax, rax
0x140015a5f  jnz     short loc_140015A6B
0x140015a61  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140015a66  jmp     loc_140015B77
0x140015a6b  mov     rdx, rsi; hResInfo
0x140015a6e  mov     rcx, rdi; hModule
0x140015a71  call    cs:__imp_LoadResource
0x140015a78  nop     dword ptr [rax+rax+00h]
0x140015a7d  mov     r14, rax
0x140015a80  mov     [rsp+498h+var_458], rax
0x140015a85  test    rax, rax
0x140015a88  jz      short loc_140015A61
0x140015a8a  mov     rdx, rsi; hResInfo
0x140015a8d  mov     rcx, rdi; hModule
0x140015a90  call    cs:__imp_SizeofResource
0x140015a97  nop     dword ptr [rax+rax+00h]
0x140015a9c  mov     esi, eax
0x140015a9e  mov     [rsp+498h+var_468], eax
0x140015aa2  inc     eax
0x140015aa4  cmp     eax, esi
0x140015aa6  jnb     short loc_140015AC9
0x140015aa8  lea     rax, [rsp+498h+var_430]
0x140015aad  cmp     [rsp+498h+var_438], rax
0x140015ab2  jz      short loc_140015ABF
0x140015ab4  lea     rcx, [rsp+498h+var_438]
0x140015ab9  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140015abe  nop
0x140015abf  mov     eax, 8007000Eh
0x140015ac4  jmp     loc_140015BA2
0x140015ac9  test    eax, eax
0x140015acb  jz      short loc_140015B00
0x140015acd  mov     ecx, eax
0x140015acf  xor     edx, edx
0x140015ad1  or      rax, 0FFFFFFFFFFFFFFFFh
0x140015ad5  div     rcx
0x140015ad8  cmp     rax, 2
0x140015adc  jb      loc_140015BC7
0x140015ae2  lea     rdx, [rcx+rcx]
0x140015ae6  cmp     rdx, 400h
0x140015aed  jbe     short loc_140015B00
0x140015aef  lea     rcx, [rsp+498h+var_438]
0x140015af4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140015af9  mov     rax, [rsp+498h+var_438]
0x140015afe  jmp     short loc_140015B0A
0x140015b00  lea     rax, [rsp+498h+var_430]
0x140015b05  mov     [rsp+498h+var_438], rax
0x140015b0a  jmp     short loc_140015B21
0x140015b0c  xor     ebx, ebx
0x140015b0e  mov     rdi, [rsp+498h+var_460]
0x140015b13  mov     r14, [rsp+498h+var_458]
0x140015b18  mov     esi, [rsp+498h+var_468]
0x140015b1c  mov     rax, [rsp+498h+var_438]
0x140015b21  test    rax, rax
0x140015b24  jnz     short loc_140015B2D
0x140015b26  mov     ebx, 8007000Eh
0x140015b2b  jmp     short loc_140015B79
0x140015b2d  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x140015b31  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x140015b36  mov     r9d, esi; cbMultiByte
0x140015b39  mov     r8, r14; lpMultiByteStr
0x140015b3c  xor     edx, edx; dwFlags
0x140015b3e  lea     ecx, [rdx+3]; CodePage
0x140015b41  call    cs:__imp_MultiByteToWideChar
0x140015b48  nop     dword ptr [rax+rax+00h]
0x140015b4d  test    eax, eax
0x140015b4f  jz      loc_140015A61
0x140015b55  mov     ecx, eax
0x140015b57  mov     rax, [rsp+498h+var_438]
0x140015b5c  mov     [rax+rcx*2], bx
0x140015b60  mov     r8d, [rsp+498h+arg_20]; int
0x140015b68  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x140015b6d  lea     rcx, [rsp+498h+var_450]; this
0x140015b72  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140015b77  mov     ebx, eax
0x140015b79  mov     rcx, rdi; hLibModule
0x140015b7c  call    cs:__imp_FreeLibrary
0x140015b83  nop     dword ptr [rax+rax+00h]
0x140015b88  nop
0x140015b89  lea     rax, [rsp+498h+var_430]
0x140015b8e  cmp     [rsp+498h+var_438], rax
0x140015b93  jz      short loc_140015BA0
0x140015b95  lea     rcx, [rsp+498h+var_438]
0x140015b9a  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140015b9f  nop
0x140015ba0  mov     eax, ebx
0x140015ba2  mov     rcx, [rsp+498h+var_28]
0x140015baa  xor     rcx, rsp; StackCookie
0x140015bad  call    __security_check_cookie
0x140015bb2  mov     rbx, [rsp+498h+arg_0]
0x140015bba  add     rsp, 480h
0x140015bc1  pop     r14
0x140015bc3  pop     rdi
0x140015bc4  pop     rsi
0x140015bc5  retn
0x140015bc7  mov     ecx, 80070057h; int
0x140015bcc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
