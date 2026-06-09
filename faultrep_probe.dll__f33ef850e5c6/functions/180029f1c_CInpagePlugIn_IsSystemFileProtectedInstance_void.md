# CInpagePlugIn::IsSystemFileProtectedInstance(void)

- ea: `0x180029f1c`
- end: `0x18002a283`
- name: `?IsSystemFileProtectedInstance@CInpagePlugIn@@AEAAHXZ`
- size: `871`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180029c80`

## callees

- `0x180002890`
- `0x180003474`
- `0x180009ed8`
- `0x180019160`
- `0x180029f1c`
- `0x18002a28c`
- `0x180039cf4`
- `0x18004b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180029fb0`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180029fbf`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180029fb0`
- `api-ms-win-crt-private-l1-1-0!_o_tolower` at `0x180029fbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a00c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a063`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a07f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a00c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a063`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a07f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029ff3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a04a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a1fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a20b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029ff3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a04a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a1fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a20b`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180029f90`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180029f90`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002a21b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002a21b`

## string_xrefs

- `0x18002a020`: `kernel32.dll`
- `0x180029fcd`: `sfc_os.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInpagePlugIn::IsSystemFileProtectedInstance(CInpagePlugIn *this)
{
  __int64 v2; // r15
  HMODULE v3; // rsi
  HMODULE v4; // rdi
  unsigned int v5; // r12d
  __int64 v6; // r14
  int v7; // ebx
  HMODULE *v8; // rax
  HMODULE *v9; // rax
  FARPROC v10; // rbx
  __int64 v11; // rcx
  wchar_t *v12; // rdx
  wchar_t *v13; // rax
  wchar_t v14; // r8
  wchar_t *v15; // rcx
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  HMODULE hLibModule; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE v19; // [rsp+40h] [rbp-C0h]
  HMODULE v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  FARPROC ProcAddress; // [rsp+58h] [rbp-A8h]
  wchar_t v23[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(v23, 0, 0x208u);
  v2 = -1;
  v21 = -1;
  v3 = 0;
  v19 = 0;
  v4 = 0;
  v20 = 0;
  v5 = 0;
  v17 = 260;
  v6 = 258;
  if ( GetWindowsDirectoryW(Buffer, 0x104u) - 1 <= 0x102 )
  {
    v7 = _o_tolower(*((unsigned __int16 *)this + 24));
    if ( (unsigned int)_o_tolower(Buffer[0]) != v7 )
      goto LABEL_30;
    v8 = (HMODULE *)UtilLoadModFromSystem(&hLibModule, L"sfc_os.dll");
    v3 = *v8;
    *v8 = 0;
    v19 = v3;
    if ( hLibModule )
      FreeLibrary(hLibModule);
    if ( !v3 )
      goto LABEL_30;
    ProcAddress = GetProcAddress(v3, "SfcIsFileProtected");
    if ( !ProcAddress )
      goto LABEL_30;
    v9 = (HMODULE *)UtilLoadModFromSystem(&hLibModule, L"kernel32.dll");
    v4 = *v9;
    *v9 = 0;
    v20 = v4;
    if ( hLibModule )
      FreeLibrary(hLibModule);
    if ( !v4
      || (v10 = GetProcAddress(v4, "FindFirstFileNameW")) == 0
      || (hLibModule = (HMODULE)GetProcAddress(v4, "FindNextFileNameW")) == 0
      || (v2 = ((__int64 (__fastcall *)(char *, _QWORD, int *, wchar_t *))v10)((char *)this + 48, 0, &v17, v23),
          v21 = v2,
          v2 == -1) )
    {
LABEL_30:
      v5 = 0;
      goto LABEL_31;
    }
    while ( 1 )
    {
      if ( UtilFileExists(v23) )
      {
        if ( ((unsigned int (__fastcall *)(_QWORD, wchar_t *))ProcAddress)(0, v23)
          && !(unsigned int)CInpagePlugIn::IsWdiHostProcess(this) )
        {
          *((_WORD *)this + 284) = *((_WORD *)this + 24);
          *((_WORD *)this + 285) = 58;
          v11 = 2147483646;
          v12 = v23;
          v13 = (wchar_t *)((char *)this + 572);
          v5 = 0;
          do
          {
            if ( !v11 )
              break;
            v14 = *v12;
            if ( !*v12 )
              break;
            ++v12;
            *v13++ = v14;
            --v11;
            --v6;
          }
          while ( v6 );
          v15 = v13 - 1;
          if ( v6 )
            v15 = v13;
          *v15 = 0;
          if ( v6 )
          {
            v5 = 1;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
          }
          goto LABEL_31;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
      }
      memset_0(v23, 0, 0x208u);
      v17 = 260;
      if ( !((unsigned int (__fastcall *)(__int64, int *, wchar_t *))hLibModule)(v2, &v17, v23) )
        goto LABEL_30;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
LABEL_31:
  if ( v4 )
    FreeLibrary(v4);
  if ( v3 )
    FreeLibrary(v3);
  if ( v2 != -1 )
    FindClose((HANDLE)v2);
  return v5;
}

```

## disassembly

```asm
0x180029f1c  push    rbp
0x180029f1e  push    rbx
0x180029f1f  push    rsi
0x180029f20  push    rdi
0x180029f21  push    r12
0x180029f23  push    r13
0x180029f25  push    r14
0x180029f27  push    r15
0x180029f29  lea     rbp, [rsp-398h]
0x180029f31  sub     rsp, 498h
0x180029f38  mov     rax, cs:__security_cookie
0x180029f3f  xor     rax, rsp
0x180029f42  mov     [rbp+3D0h+var_50], rax
0x180029f49  mov     r13, rcx
0x180029f4c  xor     edx, edx; Val
0x180029f4e  mov     r8d, 208h; Size
0x180029f54  lea     rcx, [rsp+4D0h+var_470]; void *
0x180029f59  call    memset_0
0x180029f5e  or      r15, 0FFFFFFFFFFFFFFFFh
0x180029f62  mov     [rsp+4D0h+var_480], r15
0x180029f67  xor     eax, eax
0x180029f69  mov     esi, eax
0x180029f6b  mov     [rsp+4D0h+var_490], rax
0x180029f70  mov     edi, eax
0x180029f72  mov     [rsp+4D0h+var_488], rax
0x180029f77  mov     r12d, eax
0x180029f7a  mov     [rsp+4D0h+var_4A0], eax
0x180029f7e  mov     eax, 104h
0x180029f83  mov     [rsp+4D0h+var_49C], eax
0x180029f87  mov     edx, eax; uSize
0x180029f89  lea     rcx, [rbp+3D0h+Buffer]; lpBuffer
0x180029f90  call    cs:__imp_GetWindowsDirectoryW
0x180029f96  dec     eax
0x180029f98  mov     r14d, 102h
0x180029f9e  cmp     eax, r14d
0x180029fa1  ja      loc_18002A24F
0x180029fa7  lea     r12, [r13+30h]
0x180029fab  movzx   ecx, word ptr [r12]
0x180029fb0  call    cs:__imp__o_tolower
0x180029fb6  mov     ebx, eax
0x180029fb8  movzx   ecx, [rbp+3D0h+Buffer]
0x180029fbf  call    cs:__imp__o_tolower
0x180029fc5  cmp     eax, ebx
0x180029fc7  jnz     loc_18002A1EF
0x180029fcd  lea     rdx, aSfcOsDll; "sfc_os.dll"
0x180029fd4  lea     rcx, [rsp+4D0h+hLibModule]
0x180029fd9  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x180029fde  mov     rsi, [rax]
0x180029fe1  mov     [rax], rdi
0x180029fe4  mov     [rsp+4D0h+var_490], rsi
0x180029fe9  mov     rcx, [rsp+4D0h+hLibModule]; hLibModule
0x180029fee  test    rcx, rcx
0x180029ff1  jz      short loc_180029FF9
0x180029ff3  call    cs:__imp_FreeLibrary
0x180029ff9  test    rsi, rsi
0x180029ffc  jz      loc_18002A1EF
0x18002a002  lea     rdx, aSfcisfileprote; "SfcIsFileProtected"
0x18002a009  mov     rcx, rsi; hModule
0x18002a00c  call    cs:__imp_GetProcAddress
0x18002a012  mov     [rsp+4D0h+var_478], rax
0x18002a017  test    rax, rax
0x18002a01a  jz      loc_18002A1EF
0x18002a020  lea     rdx, aKernel32Dll; "kernel32.dll"
0x18002a027  lea     rcx, [rsp+4D0h+hLibModule]
0x18002a02c  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x18002a031  mov     rdi, [rax]
0x18002a034  mov     qword ptr [rax], 0
0x18002a03b  mov     [rsp+4D0h+var_488], rdi
0x18002a040  mov     rcx, [rsp+4D0h+hLibModule]; hLibModule
0x18002a045  test    rcx, rcx
0x18002a048  jz      short loc_18002A050
0x18002a04a  call    cs:__imp_FreeLibrary
0x18002a050  test    rdi, rdi
0x18002a053  jz      loc_18002A1EF
0x18002a059  lea     rdx, aFindfirstfilen; "FindFirstFileNameW"
0x18002a060  mov     rcx, rdi; hModule
0x18002a063  call    cs:__imp_GetProcAddress
0x18002a069  mov     rbx, rax
0x18002a06c  test    rax, rax
0x18002a06f  jz      loc_18002A1EF
0x18002a075  lea     rdx, aFindnextfilena; "FindNextFileNameW"
0x18002a07c  mov     rcx, rdi; hModule
0x18002a07f  call    cs:__imp_GetProcAddress
0x18002a085  mov     [rsp+4D0h+hLibModule], rax
0x18002a08a  test    rax, rax
0x18002a08d  jz      loc_18002A1EF
0x18002a093  lea     r9, [rsp+4D0h+var_470]
0x18002a098  lea     r8, [rsp+4D0h+var_49C]
0x18002a09d  xor     edx, edx
0x18002a09f  mov     rcx, r12
0x18002a0a2  mov     rax, rbx
0x18002a0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0aa  mov     r15, rax
0x18002a0ad  mov     [rsp+4D0h+var_480], rax
0x18002a0b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a0b6  jz      loc_18002A1EF
0x18002a0bc  lea     rbx, WPP_GLOBAL_Control
0x18002a0c3  lea     rcx, [rsp+4D0h+var_470]; wchar_t *
0x18002a0c8  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x18002a0cd  test    al, al
0x18002a0cf  jz      loc_18002A18F
0x18002a0d5  lea     rdx, [rsp+4D0h+var_470]
0x18002a0da  xor     ecx, ecx
0x18002a0dc  mov     rax, [rsp+4D0h+var_478]
0x18002a0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0e6  test    eax, eax
0x18002a0e8  jz      loc_18002A1B6
0x18002a0ee  mov     rcx, r13; this
0x18002a0f1  call    ?IsWdiHostProcess@CInpagePlugIn@@AEAAHXZ; CInpagePlugIn::IsWdiHostProcess(void)
0x18002a0f6  test    eax, eax
0x18002a0f8  jnz     loc_18002A1B6
0x18002a0fe  movzx   eax, word ptr [r12]
0x18002a103  mov     [r13+238h], ax
0x18002a10b  mov     word ptr [r13+23Ah], 3Ah ; ':'
0x18002a115  mov     ecx, 7FFFFFFEh
0x18002a11a  lea     rdx, [rsp+4D0h+var_470]
0x18002a11f  lea     rax, [r13+23Ch]
0x18002a126  xor     r12d, r12d
0x18002a129  test    rcx, rcx
0x18002a12c  jz      short loc_18002A14D
0x18002a12e  movzx   r8d, word ptr [rdx]
0x18002a132  test    r8w, r8w
0x18002a136  jz      short loc_18002A14D
0x18002a138  add     rdx, 2
0x18002a13c  mov     [rax], r8w
0x18002a140  add     rax, 2
0x18002a144  dec     rcx
0x18002a147  sub     r14, 1
0x18002a14b  jnz     short loc_18002A129
0x18002a14d  lea     rcx, [rax-2]
0x18002a151  test    r14, r14
0x18002a154  cmovnz  rcx, rax
0x18002a158  mov     [rcx], r12w
0x18002a15c  jnz     loc_18002A247
0x18002a162  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a169  cmp     rcx, rbx
0x18002a16c  jz      loc_18002A1F4
0x18002a172  test    byte ptr [rcx+1Ch], 1
0x18002a176  jz      short loc_18002A1F4
0x18002a178  mov     edx, 19h
0x18002a17d  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x18002a184  mov     rcx, [rcx+10h]
0x18002a188  call    WPP_SF_
0x18002a18d  jmp     short loc_18002A1F4
0x18002a18f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a196  cmp     rcx, rbx
0x18002a199  jz      short loc_18002A1B6
0x18002a19b  test    byte ptr [rcx+1Ch], 1
0x18002a19f  jz      short loc_18002A1B6
0x18002a1a1  mov     edx, 18h
0x18002a1a6  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x18002a1ad  mov     rcx, [rcx+10h]
0x18002a1b1  call    WPP_SF_
0x18002a1b6  xor     edx, edx; Val
0x18002a1b8  mov     r8d, 208h; Size
0x18002a1be  lea     rcx, [rsp+4D0h+var_470]; void *
0x18002a1c3  call    memset_0
0x18002a1c8  mov     [rsp+4D0h+var_49C], 104h
0x18002a1d0  lea     r8, [rsp+4D0h+var_470]
0x18002a1d5  lea     rdx, [rsp+4D0h+var_49C]
0x18002a1da  mov     rcx, r15
0x18002a1dd  mov     rax, [rsp+4D0h+hLibModule]
0x18002a1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1e7  test    eax, eax
0x18002a1e9  jnz     loc_18002A0C3
0x18002a1ef  mov     r12d, [rsp+4D0h+var_4A0]
0x18002a1f4  test    rdi, rdi
0x18002a1f7  jz      short loc_18002A203
0x18002a1f9  mov     rcx, rdi; hLibModule
0x18002a1fc  call    cs:__imp_FreeLibrary
0x18002a202  nop
0x18002a203  test    rsi, rsi
0x18002a206  jz      short loc_18002A212
0x18002a208  mov     rcx, rsi; hLibModule
0x18002a20b  call    cs:__imp_FreeLibrary
0x18002a211  nop
0x18002a212  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18002a216  jz      short loc_18002A221
0x18002a218  mov     rcx, r15; hFindFile
0x18002a21b  call    cs:__imp_FindClose
0x18002a221  mov     eax, r12d
0x18002a224  mov     rcx, [rbp+3D0h+var_50]
0x18002a22b  xor     rcx, rsp; StackCookie
0x18002a22e  call    __security_check_cookie
0x18002a233  add     rsp, 498h
0x18002a23a  pop     r15
0x18002a23c  pop     r14
0x18002a23e  pop     r13
0x18002a240  pop     r12
0x18002a242  pop     rdi
0x18002a243  pop     rsi
0x18002a244  pop     rbx
0x18002a245  pop     rbp
0x18002a246  retn
0x18002a247  mov     r12d, 1
0x18002a24d  jmp     short loc_18002A1F4
0x18002a24f  lea     rbx, WPP_GLOBAL_Control
0x18002a256  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a25d  cmp     rcx, rbx
0x18002a260  jz      short loc_18002A1F4
0x18002a262  test    byte ptr [rcx+1Ch], 1
0x18002a266  jz      short loc_18002A1F4
0x18002a268  mov     edx, 17h
0x18002a26d  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x18002a274  mov     rcx, [rcx+10h]
0x18002a278  call    WPP_SF_
0x18002a27d  jmp     loc_18002A1F4
```
