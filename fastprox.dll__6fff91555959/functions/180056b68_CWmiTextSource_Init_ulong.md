# CWmiTextSource::Init(ulong)

- ea: `0x180056b68`
- end: `0x180056e82`
- name: `?Init@CWmiTextSource@@QEAAJK@Z`
- size: `794`
- prototype: `__int64 __fastcall(CWmiTextSource *__hidden this, unsigned int Value)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800569f0`

## callees

- `0x180037120`
- `0x180056b68`
- `0x180056f20`
- `0x180056f74`
- `0x1800919b0`

## import_xrefs

- `msvcrt!_ultow` at `0x180056ba8`
- `msvcrt!_ultow` at `0x180056ba8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180056d31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180056d31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180056e76`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180056e76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056d89`
- `wbemcomn!GetMemLogObject` at `0x180056cec`
- `wbemcomn!GetMemLogObject` at `0x180056cec`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180056cd1`
- `wbemcomn!??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z` at `0x180056cd1`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180056dfe`
- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180056dfe`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180056d18`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180056d18`
- `wbemcomn!?GetLastError@Registry@@QEAAJXZ` at `0x180056cdd`
- `wbemcomn!?GetLastError@Registry@@QEAAJXZ` at `0x180056cdd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056cf7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180056cf7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180056dd8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180056dd8`

## string_xrefs

- `0x180056d0c`: `TextSourceDll`
- `0x180056d43`: `OpenWbemTextSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWmiTextSource::Init(CWmiTextSource *this, unsigned int Value)
{
  __int64 v4; // r10
  __int64 v5; // rcx
  const wchar_t *v6; // r9
  __int64 v7; // r8
  unsigned __int16 *v8; // rax
  wchar_t v9; // r11
  unsigned __int16 *v10; // rcx
  __int64 v11; // r8
  unsigned __int16 *v12; // rax
  __int64 v13; // r9
  const wchar_t *v14; // rcx
  __int64 v15; // rax
  unsigned __int16 *v16; // r8
  wchar_t v17; // r9
  unsigned __int16 *v18; // rcx
  __int64 v19; // r8
  unsigned __int16 *v20; // rax
  __int64 v21; // r9
  int v22; // ebx
  CMemoryLog *MemLogObject; // rax
  HMODULE Library; // rax
  HMODULE v25; // rdi
  FARPROC ProcAddress; // rax
  int v27; // edx
  size_t v29; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v31[24]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[64]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v33[256]; // [rsp+D0h] [rbp-30h] BYREF

  _ultow(Value, Buffer, 10);
  v4 = 2147483646;
  v5 = 2147483646;
  v6 = L"Software\\Microsoft\\WBEM\\TextSource";
  v7 = 256;
  v8 = v33;
  do
  {
    if ( !v5 )
      break;
    v9 = *v6;
    if ( !*v6 )
      break;
    ++v6;
    *v8++ = v9;
    --v5;
    --v7;
  }
  while ( v7 );
  v10 = v8 - 1;
  if ( v7 )
    v10 = v8;
  *v10 = 0;
  v11 = 256;
  v12 = v33;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (256 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"\\";
    v15 = 256 - v13;
    v16 = &v33[v13];
    if ( v13 != 256 )
    {
      do
      {
        if ( !v4 )
          break;
        v17 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v16++ = v17;
        --v4;
        --v15;
      }
      while ( v15 );
    }
    v18 = v16 - 1;
    if ( v15 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = 256;
  v20 = v33;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  if ( v19 )
  {
    v21 = (256 - v19) & -(__int64)(v19 != 0);
    StringCopyWorkerW(&v33[v21], 256 - v21, (size_t *)v19, Buffer, v29);
  }
  Registry::Registry((Registry *)v31, HKEY_LOCAL_MACHINE, 0x20019u, v33);
  if ( Registry::GetLastError((Registry *)v31) )
  {
    v22 = -2147217406;
LABEL_25:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v22);
    goto LABEL_36;
  }
  lpLibFileName = 0;
  if ( Registry::GetStr((Registry *)v31, L"TextSourceDll", (unsigned __int16 **)&lpLibFileName) )
  {
    v25 = 0;
    v22 = -2147217406;
  }
  else
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    v25 = Library;
    if ( Library
      && (*((_QWORD *)this + 3) = GetProcAddress(Library, "OpenWbemTextSource"),
          *((_QWORD *)this + 4) = GetProcAddress(v25, "CloseWbemTextSource"),
          *((_QWORD *)this + 5) = GetProcAddress(v25, "WbemObjectToText"),
          ProcAddress = GetProcAddress(v25, "TextToWbemObject"),
          *((_QWORD *)this + 6) = ProcAddress,
          *((_QWORD *)this + 3))
      && *((_QWORD *)this + 4)
      && *((_QWORD *)this + 5)
      && ProcAddress )
    {
      *((_DWORD *)this + 1) = Value;
      v22 = CWmiTextSource::OpenTextSource(this, v27);
      if ( v22 >= 0 )
      {
        *((_QWORD *)this + 2) = v25;
        *((_BYTE *)this + 8) = 1;
      }
    }
    else
    {
      v22 = -2147217407;
    }
    CWin32DefaultArena::WbemMemFree((void *)lpLibFileName);
  }
  if ( v22 < 0 )
  {
    if ( v25 )
      FreeLibrary(v25);
    goto LABEL_25;
  }
LABEL_36:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_08fb07ad22c93285551a9445812e54f9_Traceguids,
      (unsigned int)v22);
  }
  Registry::~Registry((Registry *)v31);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180056b68  mov     [rsp-8+arg_10], rbx
0x180056b6d  mov     [rsp-8+arg_18], rsi
0x180056b72  push    rbp
0x180056b73  push    rdi
0x180056b74  push    r14
0x180056b76  lea     rbp, [rsp-1E0h]
0x180056b7e  sub     rsp, 2E0h
0x180056b85  mov     rax, cs:__security_cookie
0x180056b8c  xor     rax, rsp
0x180056b8f  mov     [rbp+1F0h+var_20], rax
0x180056b96  mov     ebx, edx
0x180056b98  mov     rsi, rcx
0x180056b9b  mov     r8d, 0Ah; Radix
0x180056ba1  lea     rdx, [rsp+2F0h+Buffer]; Buffer
0x180056ba6  mov     ecx, ebx; Value
0x180056ba8  call    cs:__imp__ultow
0x180056bae  mov     r10d, 7FFFFFFEh
0x180056bb4  mov     ecx, r10d
0x180056bb7  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\WBEM\\TextSource"
0x180056bbe  mov     edx, 100h
0x180056bc3  mov     r8d, edx
0x180056bc6  lea     rax, [rbp+1F0h+var_220]
0x180056bca  xor     r14d, r14d
0x180056bcd  test    rcx, rcx
0x180056bd0  jz      short loc_180056BF1
0x180056bd2  movzx   r11d, word ptr [r9]
0x180056bd6  test    r11w, r11w
0x180056bda  jz      short loc_180056BF1
0x180056bdc  add     r9, 2
0x180056be0  mov     [rax], r11w
0x180056be4  add     rax, 2
0x180056be8  dec     rcx
0x180056beb  sub     r8, 1
0x180056bef  jnz     short loc_180056BCD
0x180056bf1  lea     rcx, [rax-2]
0x180056bf5  test    r8, r8
0x180056bf8  cmovnz  rcx, rax
0x180056bfc  mov     [rcx], r14w
0x180056c00  mov     r8, rdx
0x180056c03  lea     rax, [rbp+1F0h+var_220]
0x180056c07  cmp     [rax], r14w
0x180056c0b  jz      short loc_180056C17
0x180056c0d  add     rax, 2
0x180056c11  sub     r8, 1
0x180056c15  jnz     short loc_180056C07
0x180056c17  mov     rax, r8
0x180056c1a  mov     rcx, rdx
0x180056c1d  sub     rcx, r8
0x180056c20  neg     rax
0x180056c23  sbb     r9, r9
0x180056c26  and     r9, rcx
0x180056c29  test    r8, r8
0x180056c2c  jz      short loc_180056C78
0x180056c2e  lea     rcx, asc_1800A7328; "\\"
0x180056c35  mov     rax, rdx
0x180056c38  sub     rax, r9
0x180056c3b  lea     r8, [rbp+1F0h+var_220]
0x180056c3f  lea     r8, [r8+r9*2]
0x180056c43  jz      short loc_180056C69
0x180056c45  test    r10, r10
0x180056c48  jz      short loc_180056C69
0x180056c4a  movzx   r9d, word ptr [rcx]
0x180056c4e  test    r9w, r9w
0x180056c52  jz      short loc_180056C69
0x180056c54  add     rcx, 2
0x180056c58  mov     [r8], r9w
0x180056c5c  add     r8, 2
0x180056c60  dec     r10
0x180056c63  sub     rax, 1
0x180056c67  jnz     short loc_180056C45
0x180056c69  lea     rcx, [r8-2]
0x180056c6d  test    rax, rax
0x180056c70  cmovnz  rcx, r8
0x180056c74  mov     [rcx], r14w
0x180056c78  mov     r8, rdx
0x180056c7b  lea     rax, [rbp+1F0h+var_220]
0x180056c7f  cmp     [rax], r14w
0x180056c83  jz      short loc_180056C8F
0x180056c85  add     rax, 2
0x180056c89  sub     r8, 1; pcchNewDestLength
0x180056c8d  jnz     short loc_180056C7F
0x180056c8f  mov     rax, r8
0x180056c92  mov     rcx, rdx
0x180056c95  sub     rcx, r8
0x180056c98  neg     rax
0x180056c9b  sbb     r9, r9
0x180056c9e  and     r9, rcx
0x180056ca1  test    r8, r8
0x180056ca4  jz      short loc_180056CBB
0x180056ca6  sub     rdx, r9; cchDest
0x180056ca9  lea     rcx, [rbp+1F0h+var_220]
0x180056cad  lea     rcx, [rcx+r9*2]; pszDest
0x180056cb1  lea     r9, [rsp+2F0h+Buffer]; pszSrc
0x180056cb6  call    StringCopyWorkerW
0x180056cbb  lea     r9, [rbp+1F0h+var_220]
0x180056cbf  mov     rdx, 0FFFFFFFF80000002h
0x180056cc6  mov     r8d, 20019h
0x180056ccc  lea     rcx, [rsp+2F0h+var_2B8]
0x180056cd1  call    cs:__imp_??0Registry@@QEAA@PEAUHKEY__@@KPEBG@Z; Registry::Registry(HKEY__ *,ulong,ushort const *)
0x180056cd7  nop
0x180056cd8  lea     rcx, [rsp+2F0h+var_2B8]
0x180056cdd  call    cs:__imp_?GetLastError@Registry@@QEAAJXZ; Registry::GetLastError(void)
0x180056ce3  test    eax, eax
0x180056ce5  jz      short loc_180056D02
0x180056ce7  mov     ebx, 80041002h
0x180056cec  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180056cf2  mov     edx, ebx
0x180056cf4  mov     rcx, rax
0x180056cf7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180056cfd  jmp     loc_180056DE6
0x180056d02  mov     [rsp+2F0h+lpLibFileName], r14
0x180056d07  lea     r8, [rsp+2F0h+lpLibFileName]
0x180056d0c  lea     rdx, aTextsourcedll; "TextSourceDll"
0x180056d13  lea     rcx, [rsp+2F0h+var_2B8]
0x180056d18  call    cs:__imp_?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z; Registry::GetStr(ushort const *,ushort * *)
0x180056d1e  test    eax, eax
0x180056d20  jnz     loc_180056E5D
0x180056d26  xor     edx, edx; hFile
0x180056d28  lea     r8d, [rax+8]; dwFlags
0x180056d2c  mov     rcx, [rsp+2F0h+lpLibFileName]; lpLibFileName
0x180056d31  call    cs:__imp_LoadLibraryExW
0x180056d37  mov     rdi, rax
0x180056d3a  test    rax, rax
0x180056d3d  jz      loc_180056E53
0x180056d43  lea     rdx, aOpenwbemtextso; "OpenWbemTextSource"
0x180056d4a  mov     rcx, rax; hModule
0x180056d4d  call    cs:__imp_GetProcAddress
0x180056d53  mov     [rsi+18h], rax
0x180056d57  lea     rdx, aClosewbemtexts; "CloseWbemTextSource"
0x180056d5e  mov     rcx, rdi; hModule
0x180056d61  call    cs:__imp_GetProcAddress
0x180056d67  mov     [rsi+20h], rax
0x180056d6b  lea     rdx, aWbemobjecttote; "WbemObjectToText"
0x180056d72  mov     rcx, rdi; hModule
0x180056d75  call    cs:__imp_GetProcAddress
0x180056d7b  mov     [rsi+28h], rax
0x180056d7f  lea     rdx, aTexttowbemobje; "TextToWbemObject"
0x180056d86  mov     rcx, rdi; hModule
0x180056d89  call    cs:__imp_GetProcAddress
0x180056d8f  mov     [rsi+30h], rax
0x180056d93  cmp     [rsi+18h], r14
0x180056d97  jz      loc_180056E53
0x180056d9d  cmp     [rsi+20h], r14
0x180056da1  jz      loc_180056E53
0x180056da7  cmp     [rsi+28h], r14
0x180056dab  jz      loc_180056E53
0x180056db1  test    rax, rax
0x180056db4  jz      loc_180056E53
0x180056dba  mov     [rsi+4], ebx
0x180056dbd  mov     rcx, rsi; this
0x180056dc0  call    ?OpenTextSource@CWmiTextSource@@QEAAJJ@Z; CWmiTextSource::OpenTextSource(long)
0x180056dc5  mov     ebx, eax
0x180056dc7  test    eax, eax
0x180056dc9  js      short loc_180056DD3
0x180056dcb  mov     [rsi+10h], rdi
0x180056dcf  mov     byte ptr [rsi+8], 1
0x180056dd3  mov     rcx, [rsp+2F0h+lpLibFileName]
0x180056dd8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180056dde  test    ebx, ebx
0x180056de0  js      loc_180056E6A
0x180056de6  lea     rax, WPP_GLOBAL_Control
0x180056ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180056df4  cmp     rcx, rax
0x180056df7  jnz     short loc_180056E2D
0x180056df9  lea     rcx, [rsp+2F0h+var_2B8]
0x180056dfe  call    cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
0x180056e04  mov     eax, ebx
0x180056e06  mov     rcx, [rbp+1F0h+var_20]
0x180056e0d  xor     rcx, rsp; StackCookie
0x180056e10  call    __security_check_cookie
0x180056e15  lea     r11, [rsp+2F0h+var_10]
0x180056e1d  mov     rbx, [r11+30h]
0x180056e21  mov     rsi, [r11+38h]
0x180056e25  mov     rsp, r11
0x180056e28  pop     r14
0x180056e2a  pop     rdi
0x180056e2b  pop     rbp
0x180056e2c  retn
0x180056e2d  test    byte ptr [rcx+1Ch], 1
0x180056e31  jz      short loc_180056DF9
0x180056e33  cmp     byte ptr [rcx+19h], 2
0x180056e37  jb      short loc_180056DF9
0x180056e39  mov     edx, 0Ah
0x180056e3e  mov     r9d, ebx
0x180056e41  lea     r8, WPP_08fb07ad22c93285551a9445812e54f9_Traceguids
0x180056e48  mov     rcx, [rcx+10h]
0x180056e4c  call    WPP_SF_d
0x180056e51  jmp     short loc_180056DF9
0x180056e53  mov     ebx, 80041001h
0x180056e58  jmp     loc_180056DD3
0x180056e5d  mov     rdi, r14
0x180056e60  mov     ebx, 80041002h
0x180056e65  jmp     loc_180056DDE
0x180056e6a  test    rdi, rdi
0x180056e6d  jz      loc_180056CEC
0x180056e73  mov     rcx, rdi; hLibModule
0x180056e76  call    cs:__imp_FreeLibrary
0x180056e7c  jmp     loc_180056CEC
```
