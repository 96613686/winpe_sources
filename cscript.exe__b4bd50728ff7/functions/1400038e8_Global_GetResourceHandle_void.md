# Global::GetResourceHandle(void)

- ea: `0x1400038e8`
- end: `0x140003d1c`
- name: `?GetResourceHandle@Global@@CAPEAUHINSTANCE__@@XZ`
- size: `1076`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000380c`

## callees

- `0x1400038e8`
- `0x14000dba4`
- `0x140014880`
- `0x140016182`
- `0x1400161d0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x140003b3d`
- `msvcrt!sprintf_s` at `0x140003c40`
- `msvcrt!sprintf_s` at `0x140003b3d`
- `msvcrt!sprintf_s` at `0x140003c40`
- `msvcrt!strcpy_s` at `0x140003abf`
- `msvcrt!strcpy_s` at `0x140003bbc`
- `msvcrt!strcpy_s` at `0x140003cbd`
- `msvcrt!strcpy_s` at `0x140003abf`
- `msvcrt!strcpy_s` at `0x140003bbc`
- `msvcrt!strcpy_s` at `0x140003cbd`
- `KERNEL32!GetModuleFileNameA` at `0x140003a3c`
- `KERNEL32!GetModuleFileNameA` at `0x140003a3c`
- `KERNEL32!FreeLibrary` at `0x14000399f`
- `KERNEL32!FreeLibrary` at `0x14000399f`
- `KERNEL32!LoadLibraryExA` at `0x140003ad7`
- `KERNEL32!LoadLibraryExA` at `0x140003aef`
- `KERNEL32!LoadLibraryExA` at `0x140003bce`
- `KERNEL32!LoadLibraryExA` at `0x140003be6`
- `KERNEL32!LoadLibraryExA` at `0x140003ccf`
- `KERNEL32!LoadLibraryExA` at `0x140003ce3`
- `KERNEL32!LoadLibraryExA` at `0x140003ad7`
- `KERNEL32!LoadLibraryExA` at `0x140003aef`
- `KERNEL32!LoadLibraryExA` at `0x140003bce`
- `KERNEL32!LoadLibraryExA` at `0x140003be6`
- `KERNEL32!LoadLibraryExA` at `0x140003ccf`
- `KERNEL32!LoadLibraryExA` at `0x140003ce3`
- `KERNEL32!GetUserDefaultLCID` at `0x140003921`
- `KERNEL32!GetUserDefaultLCID` at `0x140003bf5`
- `KERNEL32!GetUserDefaultLCID` at `0x140003921`
- `KERNEL32!GetUserDefaultLCID` at `0x140003bf5`
- `KERNEL32!GetLocaleInfoA` at `0x1400039c1`
- `KERNEL32!GetLocaleInfoA` at `0x140003c13`
- `KERNEL32!GetLocaleInfoA` at `0x1400039c1`
- `KERNEL32!GetLocaleInfoA` at `0x140003c13`
- `KERNEL32!GetLocaleInfoW` at `0x140003943`
- `KERNEL32!GetLocaleInfoW` at `0x140003943`
- `USER32!LoadStringA` at `0x140003a00`
- `USER32!LoadStringA` at `0x140003a00`
- `USER32!CharNextA` at `0x140003a64`
- `USER32!CharNextA` at `0x140003b65`
- `USER32!CharNextA` at `0x140003c68`
- `USER32!CharNextA` at `0x140003a64`
- `USER32!CharNextA` at `0x140003b65`
- `USER32!CharNextA` at `0x140003c68`

## string_xrefs

- `0x140003a1d`: `%s%s.DLL`
- `0x140003b2f`: `%s%s.DLL`
- `0x140003c35`: `%s%s.DLL`

## pseudocode

```c
HINSTANCE Global::GetResourceHandle(void)
{
  HINSTANCE result; // rax
  LCID UserDefaultLCID; // eax
  unsigned int v2; // ebx
  CHAR v3; // cl
  CHAR *v4; // rbx
  CHAR *v5; // rax
  size_t v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  CHAR v10; // cl
  CHAR *v11; // rbx
  CHAR *v12; // rax
  size_t v13; // rbx
  __int64 v14; // rax
  __int16 v15; // ax
  CHAR v16; // cl
  CHAR *v17; // rbx
  CHAR *v18; // rax
  size_t v19; // rbx
  WCHAR LCData[2]; // [rsp+30h] [rbp-D0h] BYREF
  CHAR v21[12]; // [rsp+34h] [rbp-CCh] BYREF
  CHAR Filename[272]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR Source[272]; // [rsp+150h] [rbp+50h] BYREF
  CHAR LibFileName[272]; // [rsp+260h] [rbp+160h] BYREF
  CHAR Buffer[272]; // [rsp+370h] [rbp+270h] BYREF

  result = Global::g_hResource;
  if ( Global::g_hResource )
    return result;
  UserDefaultLCID = GetUserDefaultLCID();
  *(_DWORD *)LCData = 0;
  v2 = UserDefaultLCID;
  if ( GetLocaleInfoW(UserDefaultLCID, 0x20000070u, LCData, 2)
    && *(_DWORD *)LCData == 1
    && Global::g_lResourceBase == 2000
    || Global::g_fWindowsVista
    || (v2 & 0x3FF) == 9 )
  {
    return Global::g_hInstance;
  }
  result = LoadMUI((HINSTANCE)9, v2);
  if ( result == Global::g_hInstance )
  {
    FreeLibrary(result);
  }
  else if ( result )
  {
    return result;
  }
  if ( !GetLocaleInfoA(v2, 3u, v21, 5) || !LoadStringA(Global::g_hInstance, 0x3E9u, Buffer, 260) )
    goto LABEL_11;
  StringCchPrintfA(Source, 0x104u, "%s%s.DLL", Buffer, v21);
  GetModuleFileNameA(Global::g_hInstance, Filename, 0x104u);
  v3 = Filename[0];
  v4 = Filename;
  if ( Filename[0] )
  {
    v5 = Filename;
    do
    {
      if ( v3 == 92 )
        v4 = ++v5;
      else
        v5 = CharNextA(v5);
      v3 = *v5;
    }
    while ( *v5 );
  }
  v6 = v4 - Filename;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( Source[v8] );
  if ( v6 + v8 + 1 <= 0x104 )
  {
    memcpy_0(LibFileName, Filename, v6);
    strcpy_s(&LibFileName[v6], 260 - v6, Source);
  }
  result = LoadLibraryExA(LibFileName, 0, 0x60u);
  if ( !result )
  {
    result = LoadLibraryExA(Source, 0, 0x60u);
    if ( !result )
    {
      v9 = -1;
      do
        ++v9;
      while ( v21[v9] );
      if ( v9 <= 2 )
        goto LABEL_42;
      v21[2] = 0;
      sprintf_s(Source, 0x104u, "%s%s.DLL", Buffer, v21);
      v10 = Filename[0];
      v11 = Filename;
      if ( Filename[0] )
      {
        v12 = Filename;
        do
        {
          if ( v10 == 92 )
            v11 = ++v12;
          else
            v12 = CharNextA(v12);
          v10 = *v12;
        }
        while ( *v12 );
      }
      v13 = v11 - Filename;
      v14 = -1;
      do
        ++v14;
      while ( Source[v14] );
      if ( v13 + v14 + 1 <= 0x104 )
      {
        memcpy_0(LibFileName, Filename, v13);
        strcpy_s(&LibFileName[v13], 260 - v13, Source);
      }
      result = LoadLibraryExA(LibFileName, 0, 0x60u);
      if ( !result )
      {
        result = LoadLibraryExA(Source, 0, 0x60u);
        if ( !result )
        {
LABEL_42:
          v15 = GetUserDefaultLCID();
          if ( GetLocaleInfoA(v15 & 0x3FF | 0x400, 3u, v21, 5) )
          {
            sprintf_s(Source, 0x104u, "%s%s.DLL", Buffer, v21);
            v16 = Filename[0];
            v17 = Filename;
            if ( Filename[0] )
            {
              v18 = Filename;
              do
              {
                if ( v16 == 92 )
                  v17 = ++v18;
                else
                  v18 = CharNextA(v18);
                v16 = *v18;
              }
              while ( *v18 );
            }
            v19 = v17 - Filename;
            do
              ++v7;
            while ( Source[v7] );
            if ( v19 + v7 + 1 <= 0x104 )
            {
              memcpy_0(LibFileName, Filename, v19);
              strcpy_s(&LibFileName[v19], 260 - v19, Source);
            }
            result = LoadLibraryExA(LibFileName, 0, 0x60u);
            if ( !result )
            {
              result = LoadLibraryExA(Source, 0, 0x60u);
              if ( !result )
                return Global::g_hInstance;
            }
            return result;
          }
LABEL_11:
          result = Global::g_hInstance;
          if ( Global::g_hResource )
            return Global::g_hResource;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400038e8  push    rbp
0x1400038ea  push    rbx
0x1400038eb  push    rsi
0x1400038ec  push    rdi
0x1400038ed  push    r13
0x1400038ef  push    r15
0x1400038f1  lea     rbp, [rsp-398h]
0x1400038f9  sub     rsp, 498h
0x140003900  mov     rax, cs:__security_cookie
0x140003907  xor     rax, rsp
0x14000390a  mov     [rbp+3C0h+var_40], rax
0x140003911  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x140003918  test    rax, rax
0x14000391b  jnz     loc_140003CFD
0x140003921  call    cs:__imp_GetUserDefaultLCID
0x140003927  mov     r9d, 2; cchData
0x14000392d  mov     dword ptr [rsp+4C0h+LCData], 0
0x140003935  mov     ecx, eax; Locale
0x140003937  lea     r8, [rsp+4C0h+LCData]; lpLCData
0x14000393c  mov     edx, 20000070h; LCType
0x140003941  mov     ebx, eax
0x140003943  call    cs:__imp_GetLocaleInfoW
0x140003949  test    eax, eax
0x14000394b  jz      short loc_140003964
0x14000394d  cmp     dword ptr [rsp+4C0h+LCData], 1
0x140003952  jnz     short loc_140003964
0x140003954  cmp     cs:?g_lResourceBase@Global@@2JA, 7D0h; long Global::g_lResourceBase
0x14000395e  jz      loc_140003CF6
0x140003964  cmp     cs:?g_fWindowsVista@Global@@2_NA, 0; bool Global::g_fWindowsVista
0x14000396b  jnz     loc_140003CF6
0x140003971  movzx   eax, bx
0x140003974  mov     r13d, 3FFh
0x14000397a  and     ax, r13w
0x14000397e  mov     ecx, 9; HINSTANCE
0x140003983  cmp     cx, ax
0x140003986  jz      loc_140003CF6
0x14000398c  mov     edx, ebx; unsigned int
0x14000398e  call    ?LoadMUI@@YAPEAUHINSTANCE__@@PEAU1@K@Z; LoadMUI(HINSTANCE__ *,ulong)
0x140003993  cmp     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x14000399a  jnz     short loc_1400039A7
0x14000399c  mov     rcx, rax; hLibModule
0x14000399f  call    cs:__imp_FreeLibrary
0x1400039a5  jmp     short loc_1400039B0
0x1400039a7  test    rax, rax
0x1400039aa  jnz     loc_140003CFD
0x1400039b0  mov     r9d, 5; cchData
0x1400039b6  lea     r8, [rsp+4C0h+var_48C]; lpLCData
0x1400039bb  mov     ecx, ebx; Locale
0x1400039bd  lea     edx, [r9-2]; LCType
0x1400039c1  call    cs:__imp_GetLocaleInfoA
0x1400039c7  test    eax, eax
0x1400039c9  jnz     short loc_1400039E5
0x1400039cb  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x1400039d2  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x1400039d9  test    rcx, rcx
0x1400039dc  cmovnz  rax, rcx
0x1400039e0  jmp     loc_140003CFD
0x1400039e5  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x1400039ec  lea     r8, [rbp+3C0h+Buffer]; lpBuffer
0x1400039f3  mov     edi, 104h
0x1400039f8  mov     edx, 3E9h; uID
0x1400039fd  mov     r9d, edi; cchBufferMax
0x140003a00  call    cs:__imp_LoadStringA
0x140003a06  test    eax, eax
0x140003a08  jz      short loc_1400039CB
0x140003a0a  lea     rax, [rsp+4C0h+var_48C]
0x140003a0f  mov     edx, edi; unsigned __int64
0x140003a11  lea     r9, [rbp+3C0h+Buffer]
0x140003a18  mov     [rsp+4C0h+var_4A0], rax
0x140003a1d  lea     r8, Format; "%s%s.DLL"
0x140003a24  lea     rcx, [rbp+3C0h+Source]; char *
0x140003a28  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140003a2d  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x140003a34  lea     rdx, [rsp+4C0h+Filename]; lpFilename
0x140003a39  mov     r8d, edi; nSize
0x140003a3c  call    cs:__imp_GetModuleFileNameA
0x140003a42  mov     cl, [rsp+4C0h+Filename]
0x140003a46  lea     rbx, [rsp+4C0h+Filename]
0x140003a4b  test    cl, cl
0x140003a4d  jz      short loc_140003A70
0x140003a4f  lea     rax, [rsp+4C0h+Filename]
0x140003a54  cmp     cl, 5Ch ; '\'
0x140003a57  jnz     short loc_140003A61
0x140003a59  inc     rax
0x140003a5c  mov     rbx, rax
0x140003a5f  jmp     short loc_140003A6A
0x140003a61  mov     rcx, rax; lpsz
0x140003a64  call    cs:__imp_CharNextA
0x140003a6a  mov     cl, [rax]
0x140003a6c  test    cl, cl
0x140003a6e  jnz     short loc_140003A54
0x140003a70  lea     rax, [rsp+4C0h+Filename]
0x140003a75  sub     rbx, rax
0x140003a78  lea     rcx, [rbp+3C0h+Source]
0x140003a7c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140003a80  mov     rax, rsi
0x140003a83  inc     rax
0x140003a86  cmp     byte ptr [rcx+rax], 0
0x140003a8a  jnz     short loc_140003A83
0x140003a8c  inc     rax
0x140003a8f  add     rax, rbx
0x140003a92  cmp     rax, rdi
0x140003a95  ja      short loc_140003AC5
0x140003a97  mov     r8, rbx; Size
0x140003a9a  lea     rdx, [rsp+4C0h+Filename]; Src
0x140003a9f  lea     rcx, [rbp+3C0h+LibFileName]; void *
0x140003aa6  call    memcpy_0
0x140003aab  mov     rdx, rdi
0x140003aae  lea     rcx, [rbp+3C0h+LibFileName]
0x140003ab5  sub     rdx, rbx; SizeInBytes
0x140003ab8  lea     r8, [rbp+3C0h+Source]; Source
0x140003abc  add     rcx, rbx; Destination
0x140003abf  call    cs:__imp_strcpy_s
0x140003ac5  mov     r15d, 60h ; '`'
0x140003acb  lea     rcx, [rbp+3C0h+LibFileName]; lpLibFileName
0x140003ad2  mov     r8d, r15d; dwFlags
0x140003ad5  xor     edx, edx; hFile
0x140003ad7  call    cs:__imp_LoadLibraryExA
0x140003add  test    rax, rax
0x140003ae0  jnz     loc_140003CFD
0x140003ae6  mov     r8d, r15d; dwFlags
0x140003ae9  lea     rcx, [rbp+3C0h+Source]; lpLibFileName
0x140003aed  xor     edx, edx; hFile
0x140003aef  call    cs:__imp_LoadLibraryExA
0x140003af5  test    rax, rax
0x140003af8  jnz     loc_140003CFD
0x140003afe  lea     rcx, [rsp+4C0h+var_48C]
0x140003b03  mov     rax, rsi
0x140003b06  inc     rax
0x140003b09  cmp     byte ptr [rcx+rax], 0
0x140003b0d  jnz     short loc_140003B06
0x140003b0f  cmp     rax, 2
0x140003b13  jbe     loc_140003BF5
0x140003b19  lea     rax, [rsp+4C0h+var_48C]
0x140003b1e  mov     [rsp+4C0h+var_48A], 0
0x140003b23  lea     r9, [rbp+3C0h+Buffer]
0x140003b2a  mov     [rsp+4C0h+var_4A0], rax
0x140003b2f  lea     r8, Format; "%s%s.DLL"
0x140003b36  mov     rdx, rdi; BufferCount
0x140003b39  lea     rcx, [rbp+3C0h+Source]; Buffer
0x140003b3d  call    cs:__imp_sprintf_s
0x140003b43  mov     cl, [rsp+4C0h+Filename]
0x140003b47  lea     rbx, [rsp+4C0h+Filename]
0x140003b4c  test    cl, cl
0x140003b4e  jz      short loc_140003B71
0x140003b50  lea     rax, [rsp+4C0h+Filename]
0x140003b55  cmp     cl, 5Ch ; '\'
0x140003b58  jnz     short loc_140003B62
0x140003b5a  inc     rax
0x140003b5d  mov     rbx, rax
0x140003b60  jmp     short loc_140003B6B
0x140003b62  mov     rcx, rax; lpsz
0x140003b65  call    cs:__imp_CharNextA
0x140003b6b  mov     cl, [rax]
0x140003b6d  test    cl, cl
0x140003b6f  jnz     short loc_140003B55
0x140003b71  lea     rax, [rsp+4C0h+Filename]
0x140003b76  sub     rbx, rax
0x140003b79  lea     rcx, [rbp+3C0h+Source]
0x140003b7d  mov     rax, rsi
0x140003b80  inc     rax
0x140003b83  cmp     byte ptr [rcx+rax], 0
0x140003b87  jnz     short loc_140003B80
0x140003b89  inc     rax
0x140003b8c  add     rax, rbx
0x140003b8f  cmp     rax, rdi
0x140003b92  ja      short loc_140003BC2
0x140003b94  mov     r8, rbx; Size
0x140003b97  lea     rdx, [rsp+4C0h+Filename]; Src
0x140003b9c  lea     rcx, [rbp+3C0h+LibFileName]; void *
0x140003ba3  call    memcpy_0
0x140003ba8  mov     rdx, rdi
0x140003bab  lea     rcx, [rbp+3C0h+LibFileName]
0x140003bb2  sub     rdx, rbx; SizeInBytes
0x140003bb5  lea     r8, [rbp+3C0h+Source]; Source
0x140003bb9  add     rcx, rbx; Destination
0x140003bbc  call    cs:__imp_strcpy_s
0x140003bc2  mov     r8d, r15d; dwFlags
0x140003bc5  lea     rcx, [rbp+3C0h+LibFileName]; lpLibFileName
0x140003bcc  xor     edx, edx; hFile
0x140003bce  call    cs:__imp_LoadLibraryExA
0x140003bd4  test    rax, rax
0x140003bd7  jnz     loc_140003CFD
0x140003bdd  mov     r8d, r15d; dwFlags
0x140003be0  lea     rcx, [rbp+3C0h+Source]; lpLibFileName
0x140003be4  xor     edx, edx; hFile
0x140003be6  call    cs:__imp_LoadLibraryExA
0x140003bec  test    rax, rax
0x140003bef  jnz     loc_140003CFD
0x140003bf5  call    cs:__imp_GetUserDefaultLCID
0x140003bfb  mov     r9d, 5; cchData
0x140003c01  lea     r8, [rsp+4C0h+var_48C]; lpLCData
0x140003c06  and     eax, r13d
0x140003c09  bts     eax, 0Ah
0x140003c0d  mov     ecx, eax; Locale
0x140003c0f  lea     edx, [r9-2]; LCType
0x140003c13  call    cs:__imp_GetLocaleInfoA
0x140003c19  test    eax, eax
0x140003c1b  jz      loc_1400039CB
0x140003c21  lea     rax, [rsp+4C0h+var_48C]
0x140003c26  mov     rdx, rdi; BufferCount
0x140003c29  lea     r9, [rbp+3C0h+Buffer]
0x140003c30  mov     [rsp+4C0h+var_4A0], rax
0x140003c35  lea     r8, Format; "%s%s.DLL"
0x140003c3c  lea     rcx, [rbp+3C0h+Source]; Buffer
0x140003c40  call    cs:__imp_sprintf_s
0x140003c46  mov     cl, [rsp+4C0h+Filename]
0x140003c4a  lea     rbx, [rsp+4C0h+Filename]
0x140003c4f  test    cl, cl
0x140003c51  jz      short loc_140003C74
0x140003c53  lea     rax, [rsp+4C0h+Filename]
0x140003c58  cmp     cl, 5Ch ; '\'
0x140003c5b  jnz     short loc_140003C65
0x140003c5d  inc     rax
0x140003c60  mov     rbx, rax
0x140003c63  jmp     short loc_140003C6E
0x140003c65  mov     rcx, rax; lpsz
0x140003c68  call    cs:__imp_CharNextA
0x140003c6e  mov     cl, [rax]
0x140003c70  test    cl, cl
0x140003c72  jnz     short loc_140003C58
0x140003c74  lea     rax, [rsp+4C0h+Filename]
0x140003c79  sub     rbx, rax
0x140003c7c  lea     rax, [rbp+3C0h+Source]
0x140003c80  inc     rsi
0x140003c83  cmp     byte ptr [rax+rsi], 0
0x140003c87  jnz     short loc_140003C80
0x140003c89  lea     rax, [rsi+1]
0x140003c8d  add     rax, rbx
0x140003c90  cmp     rax, rdi
0x140003c93  ja      short loc_140003CC3
0x140003c95  mov     r8, rbx; Size
0x140003c98  lea     rdx, [rsp+4C0h+Filename]; Src
0x140003c9d  lea     rcx, [rbp+3C0h+LibFileName]; void *
0x140003ca4  call    memcpy_0
0x140003ca9  sub     rdi, rbx
0x140003cac  lea     rcx, [rbp+3C0h+LibFileName]
0x140003cb3  add     rcx, rbx; Destination
0x140003cb6  lea     r8, [rbp+3C0h+Source]; Source
0x140003cba  mov     rdx, rdi; SizeInBytes
0x140003cbd  call    cs:__imp_strcpy_s
0x140003cc3  mov     r8d, r15d; dwFlags
0x140003cc6  lea     rcx, [rbp+3C0h+LibFileName]; lpLibFileName
0x140003ccd  xor     edx, edx; hFile
0x140003ccf  call    cs:__imp_LoadLibraryExA
0x140003cd5  test    rax, rax
0x140003cd8  jnz     short loc_140003CFD
0x140003cda  mov     r8d, r15d; dwFlags
0x140003cdd  lea     rcx, [rbp+3C0h+Source]; lpLibFileName
0x140003ce1  xor     edx, edx; hFile
0x140003ce3  call    cs:__imp_LoadLibraryExA
0x140003ce9  test    rax, rax
0x140003cec  cmovz   rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x140003cf4  jmp     short loc_140003CFD
0x140003cf6  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x140003cfd  mov     rcx, [rbp+3C0h+var_40]
0x140003d04  xor     rcx, rsp; StackCookie
0x140003d07  call    __security_check_cookie
0x140003d0c  add     rsp, 498h
0x140003d13  pop     r15
0x140003d15  pop     r13
0x140003d17  pop     rdi
0x140003d18  pop     rsi
0x140003d19  pop     rbx
0x140003d1a  pop     rbp
0x140003d1b  retn
```
