# MPCCursorManager::MPCCursorManager(void)

- ea: `0x180095b24`
- end: `0x180095c8b`
- name: `??0MPCCursorManager@@QEAA@XZ`
- size: `359`
- prototype: `MPCCursorManager *__fastcall(MPCCursorManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800e1778`

## callees

- `0x180030260`
- `0x18008e194`
- `0x180095b24`
- `0x180095eb0`
- `0x180097c60`
- `0x180097c80`
- `0x180109040`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180095be0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180095be0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095c18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095c18`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180095bc1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180095bc1`
- `win32u!NtMITEnableMouseIntercept` at `0x180095c55`
- `win32u!NtMITEnableMouseIntercept` at `0x180095c55`

## string_xrefs

- `0x180095bba`: `User32.dll`

## pseudocode

```c
MPCCursorManager *__fastcall MPCCursorManager::MPCCursorManager(
        MPCCursorManager *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  struct ISMTestMode *v4; // rax
  HMODULE LibraryW; // rax
  const char *v7; // r9
  HMODULE v8; // rsi
  HMODULE v9; // rdi
  FARPROC ProcAddress; // rax
  const char *v11; // r9
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v15; // [rsp+30h] [rbp+8h] BYREF

  v4 = ISMTestMode::s_instance;
  *((_DWORD *)this + 8) = 0;
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_BYTE *)this + 56) = 0;
  *((_DWORD *)this + 15) = 1;
  *((_WORD *)this + 32) = 0;
  *((_BYTE *)this + 66) = 0;
  if ( !v4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\ismstatics\\system\\ismtestmode.cpp",
      a4);
  if ( !*(_BYTE *)v4 )
  {
    if ( !IsEdition(0xAu) || IsHyperVGuestOS() )
    {
      if ( IsEdition(0x400u) )
      {
        if ( !(unsigned int)NtMITEnableMouseIntercept(1) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x38,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\mpc\\lib\\mpccursormanager.cpp",
            v12);
        *((_BYTE *)this + 66) = 1;
      }
    }
    else
    {
      LibraryW = LoadLibraryW(L"User32.dll");
      v8 = (HMODULE)*((_QWORD *)this + 5);
      v9 = LibraryW;
      if ( v8 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
        FreeLibrary(v8);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
      }
      *((_QWORD *)this + 5) = v9;
      if ( !v9 )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\mpc\\lib\\mpccursormanager.cpp",
          v7);
      ProcAddress = GetProcAddress(v9, "ShowSystemCursor");
      *((_QWORD *)this + 6) = ProcAddress;
      if ( !ProcAddress )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\mpc\\lib\\mpccursormanager.cpp",
          v11);
      *((_BYTE *)this + 64) = 1;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180095b24  mov     [rsp+arg_8], rbx
0x180095b29  mov     [rsp+arg_10], rsi
0x180095b2e  push    rdi
0x180095b2f  sub     rsp, 20h
0x180095b33  mov     rax, cs:?s_instance@ISMTestMode@@0PEAV1@EA; ISMTestMode * ISMTestMode::s_instance
0x180095b3a  xorps   xmm0, xmm0
0x180095b3d  mov     dword ptr [rcx+20h], 0
0x180095b44  xorps   xmm1, xmm1
0x180095b47  mov     rbx, rcx
0x180095b4a  movdqu  xmmword ptr [rcx], xmm0
0x180095b4e  movdqu  xmmword ptr [rcx+10h], xmm1
0x180095b53  mov     qword ptr [rcx+28h], 0
0x180095b5b  mov     qword ptr [rcx+30h], 0
0x180095b63  mov     byte ptr [rcx+38h], 0
0x180095b67  mov     dword ptr [rcx+3Ch], 1
0x180095b6e  mov     word ptr [rcx+40h], 0
0x180095b74  mov     byte ptr [rcx+42h], 0
0x180095b78  test    rax, rax
0x180095b7b  jnz     short loc_180095B92
0x180095b7d  mov     rcx, [rsp+28h]; this
0x180095b82  lea     r8, aOnecoreuapWind_223; "onecoreuap\\windows\\moderncore\\inputv"...
0x180095b89  lea     edx, [rax+21h]; void *
0x180095b8c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180095b92  cmp     byte ptr [rax], 0
0x180095b95  jnz     loc_180095C78
0x180095b9b  mov     ecx, 0Ah; unsigned __int64
0x180095ba0  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x180095ba5  test    al, al
0x180095ba7  jz      loc_180095C42
0x180095bad  call    ?IsHyperVGuestOS@@YA_NXZ; IsHyperVGuestOS(void)
0x180095bb2  test    al, al
0x180095bb4  jnz     loc_180095C42
0x180095bba  lea     rcx, aUser32Dll; "User32.dll"
0x180095bc1  call    cs:__imp_LoadLibraryW
0x180095bc7  mov     rsi, [rbx+28h]
0x180095bcb  mov     rdi, rax
0x180095bce  test    rsi, rsi
0x180095bd1  jz      short loc_180095BF0
0x180095bd3  lea     rcx, [rsp+28h+arg_0]; this
0x180095bd8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180095bdd  mov     rcx, rsi; hLibModule
0x180095be0  call    cs:__imp_FreeLibrary
0x180095be6  lea     rcx, [rsp+28h+arg_0]; this
0x180095beb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180095bf0  mov     rcx, [rsp+28h]; this
0x180095bf5  mov     [rbx+28h], rdi
0x180095bf9  test    rdi, rdi
0x180095bfc  jnz     short loc_180095C0E
0x180095bfe  lea     r8, aOnecoreuapWind_70; "onecoreuap\\windows\\moderncore\\inputv"...
0x180095c05  lea     edx, [rdi+2Fh]; void *
0x180095c08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180095c0e  lea     rdx, aShowsystemcurs; "ShowSystemCursor"
0x180095c15  mov     rcx, rdi; hModule
0x180095c18  call    cs:__imp_GetProcAddress
0x180095c1e  mov     [rbx+30h], rax
0x180095c22  test    rax, rax
0x180095c25  jnz     short loc_180095C3C
0x180095c27  mov     rcx, [rsp+28h]; this
0x180095c2c  lea     r8, aOnecoreuapWind_70; "onecoreuap\\windows\\moderncore\\inputv"...
0x180095c33  lea     edx, [rax+32h]; void *
0x180095c36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180095c3c  mov     byte ptr [rbx+40h], 1
0x180095c40  jmp     short loc_180095C78
0x180095c42  mov     ecx, 400h; unsigned __int64
0x180095c47  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x180095c4c  test    al, al
0x180095c4e  jz      short loc_180095C78
0x180095c50  mov     ecx, 1
0x180095c55  call    cs:__imp_NtMITEnableMouseIntercept
0x180095c5b  test    eax, eax
0x180095c5d  jnz     short loc_180095C74
0x180095c5f  mov     rcx, [rsp+28h]; this
0x180095c64  lea     r8, aOnecoreuapWind_70; "onecoreuap\\windows\\moderncore\\inputv"...
0x180095c6b  lea     edx, [rax+38h]; void *
0x180095c6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180095c74  mov     byte ptr [rbx+42h], 1
0x180095c78  mov     rsi, [rsp+28h+arg_10]
0x180095c7d  mov     rax, rbx
0x180095c80  mov     rbx, [rsp+28h+arg_8]
0x180095c85  add     rsp, 20h
0x180095c89  pop     rdi
0x180095c8a  retn
```
