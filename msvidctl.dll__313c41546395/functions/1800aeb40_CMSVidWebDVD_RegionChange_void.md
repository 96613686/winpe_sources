# CMSVidWebDVD::RegionChange(void)

- ea: `0x1800aeb40`
- end: `0x1800aec96`
- name: `?RegionChange@CMSVidWebDVD@@UEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(CMSVidWebDVD *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004640`
- `0x18000bcf0`
- `0x1800acd00`
- `0x1800acfe4`
- `0x1800aeb40`
- `0x1800eeda0`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800aec2e`
- `KERNEL32!LoadLibraryW` at `0x1800aec2e`
- `KERNEL32!GetSystemDirectoryW` at `0x1800aec12`
- `KERNEL32!GetSystemDirectoryW` at `0x1800aec12`
- `KERNEL32!FreeLibrary` at `0x1800aec63`
- `KERNEL32!FreeLibrary` at `0x1800aec63`
- `KERNEL32!GetProcAddress` at `0x1800aec49`
- `KERNEL32!GetProcAddress` at `0x1800aec49`
- `KERNEL32!WideCharToMultiByte` at `0x1800aebf4`
- `KERNEL32!WideCharToMultiByte` at `0x1800aebf4`

## string_xrefs

- `0x1800aec18`: `\storprop.dll`

## pseudocode

```c
__int64 __fastcall CMSVidWebDVD::RegionChange(CMSVidWebDVD *this)
{
  CMSVidWebDVD *v1; // rcx
  int DVDDriveLetter; // ebx
  __int64 v4; // rax
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rcx
  void *v7; // rsp
  void *v8; // rsp
  _BYTE *v9; // rsi
  HMODULE LibraryW; // rax
  HMODULE v11; // rdi
  int v12; // r14d
  FARPROC ProcAddress; // rax
  __int64 v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-40h] BYREF
  WCHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp+10h] BYREF

  DVDDriveLetter = CMSVidWebDVD::GetDVDDriveLetter((CMSVidWebDVD *)((char *)this - 48), MultiByteStr);
  if ( DVDDriveLetter < 0 )
    return CMSVidWebDVD::HandleError(v1, DVDDriveLetter);
  v4 = -1;
  do
    ++v4;
  while ( MultiByteStr[v4] );
  v5 = 2 * (int)v4 + 17LL;
  if ( v5 <= 2 * (int)v4 + 2LL )
    v5 = 0xFFFFFFFFFFFFFF0LL;
  v6 = v5 & 0xFFFFFFFFFFFFFFF0uLL;
  v7 = alloca(v6);
  v8 = alloca(v6);
  if ( &v15 == (__int64 *)-64LL )
  {
    v9 = 0;
  }
  else
  {
    LOBYTE(MultiByteStr[0]) = 0;
    v9 = (_BYTE *)((unsigned __int64)MultiByteStr
                 & -(__int64)(WideCharToMultiByte(0, 0, MultiByteStr, -1, (LPSTR)MultiByteStr, 2 * v4 + 2, 0, 0) != 0));
  }
  GetSystemDirectoryW(Buffer, 0x104u);
  StringCchCatW(Buffer, 0x104u, L"\\storprop.dll");
  LibraryW = LoadLibraryW(Buffer);
  v11 = LibraryW;
  if ( !LibraryW )
    return 2147749874LL;
  v12 = 0;
  ProcAddress = GetProcAddress(LibraryW, "DvdLauncher");
  if ( ProcAddress )
  {
    LOBYTE(v14) = *v9;
    v12 = ((__int64 (__fastcall *)(_QWORD, __int64))ProcAddress)(0, v14);
  }
  FreeLibrary(v11);
  if ( v12 )
    return CMSVidWebDVD::HandleError(v1, DVDDriveLetter);
  else
    return 2147749874LL;
}

```

## disassembly

```asm
0x1800aeb40  push    rbp
0x1800aeb42  push    rbx
0x1800aeb43  push    rsi
0x1800aeb44  push    rdi
0x1800aeb45  push    r14
0x1800aeb47  push    r15
0x1800aeb49  sub     rsp, 278h
0x1800aeb50  lea     rbp, [rsp+40h]
0x1800aeb55  mov     rax, cs:__security_cookie
0x1800aeb5c  xor     rax, rbp
0x1800aeb5f  mov     [rbp+260h+var_40], rax
0x1800aeb66  add     rcx, 0FFFFFFFFFFFFFFD0h; this
0x1800aeb6a  lea     rdx, [rbp+260h+MultiByteStr]; unsigned __int16 *
0x1800aeb6e  call    ?GetDVDDriveLetter@CMSVidWebDVD@@AEAAJPEAG@Z; CMSVidWebDVD::GetDVDDriveLetter(ushort *)
0x1800aeb73  xor     r15d, r15d
0x1800aeb76  mov     ebx, eax
0x1800aeb78  test    eax, eax
0x1800aeb7a  jns     short loc_1800AEB88
0x1800aeb7c  mov     edx, ebx; int
0x1800aeb7e  call    ?HandleError@CMSVidWebDVD@@AEAAJJ@Z; CMSVidWebDVD::HandleError(long)
0x1800aeb83  jmp     loc_1800AEC77
0x1800aeb88  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800aeb8c  lea     rcx, [rbp+260h+MultiByteStr]
0x1800aeb90  mov     rax, r9
0x1800aeb93  inc     rax
0x1800aeb96  cmp     [rcx+rax*2], r15w
0x1800aeb9b  jnz     short loc_1800AEB93
0x1800aeb9d  lea     edx, [rax+rax]
0x1800aeba0  movsxd  rax, edx
0x1800aeba3  add     rax, 2
0x1800aeba7  lea     rcx, [rax+0Fh]
0x1800aebab  cmp     rcx, rax
0x1800aebae  ja      short loc_1800AEBBA
0x1800aebb0  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800aebba  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800aebbe  mov     rax, rcx
0x1800aebc1  call    _alloca_probe
0x1800aebc6  sub     rsp, rcx
0x1800aebc9  lea     rdi, [rsp+2A0h+MultiByteStr]
0x1800aebce  test    rdi, rdi
0x1800aebd1  jz      short loc_1800AEC04
0x1800aebd3  lea     eax, [rdx+2]
0x1800aebd6  mov     [rsp+2A0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800aebdb  mov     [rsp+2A0h+lpDefaultChar], r15; lpDefaultChar
0x1800aebe0  lea     r8, [rbp+260h+MultiByteStr]; lpWideCharStr
0x1800aebe4  mov     [rsp+2A0h+cbMultiByte], eax; cbMultiByte
0x1800aebe8  xor     edx, edx; dwFlags
0x1800aebea  xor     ecx, ecx; CodePage
0x1800aebec  mov     [rsp+2A0h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800aebf1  mov     [rdi], r15b
0x1800aebf4  call    cs:__imp_WideCharToMultiByte
0x1800aebfa  neg     eax
0x1800aebfc  sbb     rsi, rsi
0x1800aebff  and     rsi, rdi
0x1800aec02  jmp     short loc_1800AEC07
0x1800aec04  mov     rsi, r15
0x1800aec07  mov     edi, 104h
0x1800aec0c  lea     rcx, [rbp+260h+Buffer]; lpBuffer
0x1800aec10  mov     edx, edi; uSize
0x1800aec12  call    cs:__imp_GetSystemDirectoryW
0x1800aec18  lea     r8, aStorpropDll; "\\storprop.dll"
0x1800aec1f  mov     edx, edi; unsigned __int64
0x1800aec21  lea     rcx, [rbp+260h+Buffer]; unsigned __int16 *
0x1800aec25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800aec2a  lea     rcx, [rbp+260h+Buffer]; lpLibFileName
0x1800aec2e  call    cs:__imp_LoadLibraryW
0x1800aec34  mov     rdi, rax
0x1800aec37  test    rax, rax
0x1800aec3a  jz      short loc_1800AEC72
0x1800aec3c  lea     rdx, aDvdlauncher; "DvdLauncher"
0x1800aec43  mov     rcx, rax; hModule
0x1800aec46  mov     r14d, r15d
0x1800aec49  call    cs:__imp_GetProcAddress
0x1800aec4f  test    rax, rax
0x1800aec52  jz      short loc_1800AEC60
0x1800aec54  mov     dl, [rsi]
0x1800aec56  xor     ecx, ecx
0x1800aec58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec5d  mov     r14d, eax
0x1800aec60  mov     rcx, rdi; hLibModule
0x1800aec63  call    cs:__imp_FreeLibrary
0x1800aec69  test    r14d, r14d
0x1800aec6c  jnz     loc_1800AEB7C
0x1800aec72  mov     eax, 80040FF2h
0x1800aec77  mov     rcx, [rbp+260h+var_40]
0x1800aec7e  xor     rcx, rbp; StackCookie
0x1800aec81  call    __security_check_cookie
0x1800aec86  lea     rsp, [rbp+238h]
0x1800aec8d  pop     r15
0x1800aec8f  pop     r14
0x1800aec91  pop     rdi
0x1800aec92  pop     rsi
0x1800aec93  pop     rbx
0x1800aec94  pop     rbp
0x1800aec95  retn
```
