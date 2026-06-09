# PssNtWin32LiveSystemProvider::Initialize(void)

- ea: `0x180021950`
- end: `0x180021c37`
- name: `?Initialize@PssNtWin32LiveSystemProvider@@UEAAJXZ`
- size: `743`
- prototype: `__int64 __fastcall(PssNtWin32LiveSystemProvider *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180021950`
- `0x180025290`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002197a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021992`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800219aa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021a1e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021a3e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021a5e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021a7e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021aa2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021ac2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021ae6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021b06`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021b2a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021b4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021b8c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002197a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021992`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800219aa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021a1e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021a3e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021a5e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021a7e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021aa2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021ac2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021ae6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021b06`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021b2a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021b4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180021b8c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1800219c3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1800219e1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180021b6c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1800219c3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1800219e1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180021b6c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180021c24`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180021c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219fd`

## string_xrefs

- `0x180021b63`: `ntdll.dll`
- `0x1800219d8`: `kernel32.dll`
- `0x180021973`: `RtlCreateQueryDebugBuffer`
- `0x1800219ba`: `api-ms-win-core-processsnapshot-l1-1-0.dll`
- `0x180021a57`: `PssWalkMarkerCreate`

## pseudocode

```c
signed int __fastcall PssNtWin32LiveSystemProvider::Initialize(PssNtWin32LiveSystemProvider *this)
{
  signed int result; // eax
  HMODULE v3; // rcx
  FARPROC ProcAddress; // rax
  HMODULE v5; // rcx
  FARPROC v6; // rax
  HMODULE v7; // rcx
  HMODULE Library; // rax
  bool v9; // cc
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  FARPROC v19; // rax
  HMODULE v20; // rax
  FARPROC v21; // rax

  result = NtWin32LiveSystemProvider::Initialize(this);
  if ( !result )
  {
    v3 = (HMODULE)*((_QWORD *)this + 14);
    if ( v3 )
    {
      ProcAddress = GetProcAddress(v3, "RtlCreateQueryDebugBuffer");
      v5 = (HMODULE)*((_QWORD *)this + 14);
      *((_QWORD *)this + 138) = ProcAddress;
      v6 = GetProcAddress(v5, "RtlDestroyQueryDebugBuffer");
      v7 = (HMODULE)*((_QWORD *)this + 14);
      *((_QWORD *)this + 139) = v6;
      *((_QWORD *)this + 140) = GetProcAddress(v7, "RtlQueryProcessDebugInformation");
    }
    Library = LoadLibraryExA("api-ms-win-core-processsnapshot-l1-1-0.dll", 0, 0);
    *((_QWORD *)this + 141) = Library;
    if ( !Library )
    {
      Library = LoadLibraryExA("kernel32.dll", 0, 0);
      *((_QWORD *)this + 141) = Library;
      if ( !Library )
        goto LABEL_6;
    }
    v10 = GetProcAddress(Library, "PssQuerySnapshot");
    *((_QWORD *)this + 142) = v10;
    if ( !v10 )
      goto LABEL_6;
    v11 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkSnapshot");
    *((_QWORD *)this + 143) = v11;
    if ( !v11 )
      goto LABEL_6;
    v12 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkMarkerCreate");
    *((_QWORD *)this + 144) = v12;
    if ( !v12 )
      goto LABEL_6;
    v13 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkMarkerFree");
    *((_QWORD *)this + 145) = v13;
    if ( !v13 )
      goto LABEL_6;
    v14 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkMarkerTell");
    *((_QWORD *)this + 146) = v14;
    if ( !v14 )
    {
      v15 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkMarkerGetPosition");
      *((_QWORD *)this + 146) = v15;
      if ( !v15 )
        goto LABEL_6;
    }
    v16 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkMarkerSeek");
    *((_QWORD *)this + 147) = v16;
    if ( !v16 )
    {
      v17 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkMarkerSetPosition");
      *((_QWORD *)this + 147) = v17;
      if ( !v17 )
        goto LABEL_6;
    }
    v18 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkMarkerRewind");
    *((_QWORD *)this + 148) = v18;
    if ( !v18 )
    {
      v19 = GetProcAddress(*((HMODULE *)this + 141), "PssWalkMarkerSeekToBeginning");
      *((_QWORD *)this + 148) = v19;
      if ( !v19 )
        goto LABEL_6;
    }
    v20 = LoadLibraryExA("ntdll.dll", 0, 0);
    *((_QWORD *)this + 149) = v20;
    if ( v20 && (v21 = GetProcAddress(v20, "PssNtQuerySnapshot"), (*((_QWORD *)this + 150) = v21) != 0) )
    {
      result = (*((__int64 (__fastcall **)(char *, char *))this + 144))((char *)this + 1272, (char *)this + 1232);
      v9 = result <= 0;
      if ( !result )
      {
        result = (*((__int64 (__fastcall **)(char *, char *))this + 144))((char *)this + 1272, (char *)this + 1240);
        v9 = result <= 0;
        if ( !result )
        {
          result = (*((__int64 (__fastcall **)(char *, char *))this + 144))((char *)this + 1272, (char *)this + 1248);
          v9 = result <= 0;
          if ( !result )
          {
            result = (*((__int64 (__fastcall **)(char *, char *))this + 144))((char *)this + 1272, (char *)this + 1256);
            v9 = result <= 0;
            if ( !result )
            {
              InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1296));
              return 0;
            }
          }
        }
      }
    }
    else
    {
LABEL_6:
      if ( !GetLastError() )
        return -2147467259;
      result = GetLastError();
      v9 = result <= 0;
    }
    if ( !v9 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180021950  mov     [rsp+arg_0], rbx
0x180021955  push    rdi
0x180021956  sub     rsp, 20h
0x18002195a  mov     rbx, rcx
0x18002195d  call    ?Initialize@NtWin32LiveSystemProvider@@UEAAJXZ; NtWin32LiveSystemProvider::Initialize(void)
0x180021962  test    eax, eax
0x180021964  jnz     loc_180021C2C
0x18002196a  mov     rcx, [rbx+70h]; hModule
0x18002196e  test    rcx, rcx
0x180021971  jz      short loc_1800219B7
0x180021973  lea     rdx, aRtlcreatequery; "RtlCreateQueryDebugBuffer"
0x18002197a  call    cs:__imp_GetProcAddress
0x180021980  mov     rcx, [rbx+70h]; hModule
0x180021984  lea     rdx, aRtldestroyquer; "RtlDestroyQueryDebugBuffer"
0x18002198b  mov     [rbx+450h], rax
0x180021992  call    cs:__imp_GetProcAddress
0x180021998  mov     rcx, [rbx+70h]; hModule
0x18002199c  lea     rdx, aRtlqueryproces; "RtlQueryProcessDebugInformation"
0x1800219a3  mov     [rbx+458h], rax
0x1800219aa  call    cs:__imp_GetProcAddress
0x1800219b0  mov     [rbx+460h], rax
0x1800219b7  xor     r8d, r8d; dwFlags
0x1800219ba  lea     rcx, aApiMsWinCorePr_6; "api-ms-win-core-processsnapshot-l1-1-0."...
0x1800219c1  xor     edx, edx; hFile
0x1800219c3  call    cs:__imp_LoadLibraryExA
0x1800219c9  mov     [rbx+468h], rax
0x1800219d0  test    rax, rax
0x1800219d3  jnz     short loc_180021A14
0x1800219d5  xor     r8d, r8d; dwFlags
0x1800219d8  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800219df  xor     edx, edx; hFile
0x1800219e1  call    cs:__imp_LoadLibraryExA
0x1800219e7  mov     [rbx+468h], rax
0x1800219ee  test    rax, rax
0x1800219f1  jnz     short loc_180021A14
0x1800219f3  call    cs:__imp_GetLastError
0x1800219f9  test    eax, eax
0x1800219fb  jz      short loc_180021A0A
0x1800219fd  call    cs:__imp_GetLastError
0x180021a03  test    eax, eax
0x180021a05  jmp     loc_180021BC3
0x180021a0a  mov     eax, 80004005h
0x180021a0f  jmp     loc_180021C2C
0x180021a14  lea     rdx, aPssquerysnapsh; "PssQuerySnapshot"
0x180021a1b  mov     rcx, rax; hModule
0x180021a1e  call    cs:__imp_GetProcAddress
0x180021a24  mov     [rbx+470h], rax
0x180021a2b  test    rax, rax
0x180021a2e  jz      short loc_1800219F3
0x180021a30  mov     rcx, [rbx+468h]; hModule
0x180021a37  lea     rdx, aPsswalksnapsho; "PssWalkSnapshot"
0x180021a3e  call    cs:__imp_GetProcAddress
0x180021a44  mov     [rbx+478h], rax
0x180021a4b  test    rax, rax
0x180021a4e  jz      short loc_1800219F3
0x180021a50  mov     rcx, [rbx+468h]; hModule
0x180021a57  lea     rdx, aPsswalkmarkerc; "PssWalkMarkerCreate"
0x180021a5e  call    cs:__imp_GetProcAddress
0x180021a64  mov     [rbx+480h], rax
0x180021a6b  test    rax, rax
0x180021a6e  jz      short loc_1800219F3
0x180021a70  mov     rcx, [rbx+468h]; hModule
0x180021a77  lea     rdx, aPsswalkmarkerf; "PssWalkMarkerFree"
0x180021a7e  call    cs:__imp_GetProcAddress
0x180021a84  mov     [rbx+488h], rax
0x180021a8b  test    rax, rax
0x180021a8e  jz      loc_1800219F3
0x180021a94  mov     rcx, [rbx+468h]; hModule
0x180021a9b  lea     rdx, aPsswalkmarkert; "PssWalkMarkerTell"
0x180021aa2  call    cs:__imp_GetProcAddress
0x180021aa8  mov     [rbx+490h], rax
0x180021aaf  test    rax, rax
0x180021ab2  jnz     short loc_180021AD8
0x180021ab4  mov     rcx, [rbx+468h]; hModule
0x180021abb  lea     rdx, aPsswalkmarkerg; "PssWalkMarkerGetPosition"
0x180021ac2  call    cs:__imp_GetProcAddress
0x180021ac8  mov     [rbx+490h], rax
0x180021acf  test    rax, rax
0x180021ad2  jz      loc_1800219F3
0x180021ad8  mov     rcx, [rbx+468h]; hModule
0x180021adf  lea     rdx, aPsswalkmarkers_0; "PssWalkMarkerSeek"
0x180021ae6  call    cs:__imp_GetProcAddress
0x180021aec  mov     [rbx+498h], rax
0x180021af3  test    rax, rax
0x180021af6  jnz     short loc_180021B1C
0x180021af8  mov     rcx, [rbx+468h]; hModule
0x180021aff  lea     rdx, aPsswalkmarkers; "PssWalkMarkerSetPosition"
0x180021b06  call    cs:__imp_GetProcAddress
0x180021b0c  mov     [rbx+498h], rax
0x180021b13  test    rax, rax
0x180021b16  jz      loc_1800219F3
0x180021b1c  mov     rcx, [rbx+468h]; hModule
0x180021b23  lea     rdx, aPsswalkmarkerr; "PssWalkMarkerRewind"
0x180021b2a  call    cs:__imp_GetProcAddress
0x180021b30  mov     [rbx+4A0h], rax
0x180021b37  test    rax, rax
0x180021b3a  jnz     short loc_180021B60
0x180021b3c  mov     rcx, [rbx+468h]; hModule
0x180021b43  lea     rdx, aPsswalkmarkers_1; "PssWalkMarkerSeekToBeginning"
0x180021b4a  call    cs:__imp_GetProcAddress
0x180021b50  mov     [rbx+4A0h], rax
0x180021b57  test    rax, rax
0x180021b5a  jz      loc_1800219F3
0x180021b60  xor     r8d, r8d; dwFlags
0x180021b63  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180021b6a  xor     edx, edx; hFile
0x180021b6c  call    cs:__imp_LoadLibraryExA
0x180021b72  mov     [rbx+4A8h], rax
0x180021b79  test    rax, rax
0x180021b7c  jz      loc_1800219F3
0x180021b82  lea     rdx, aPssntquerysnap; "PssNtQuerySnapshot"
0x180021b89  mov     rcx, rax; hModule
0x180021b8c  call    cs:__imp_GetProcAddress
0x180021b92  mov     [rbx+4B0h], rax
0x180021b99  test    rax, rax
0x180021b9c  jz      loc_1800219F3
0x180021ba2  mov     rax, [rbx+480h]
0x180021ba9  lea     rdi, [rbx+4F8h]
0x180021bb0  mov     rcx, rdi
0x180021bb3  lea     rdx, [rbx+4D0h]
0x180021bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bbf  test    eax, eax
0x180021bc1  jz      short loc_180021BCF
0x180021bc3  jle     short loc_180021C2C
0x180021bc5  movzx   eax, ax
0x180021bc8  or      eax, 80070000h
0x180021bcd  jmp     short loc_180021C2C
0x180021bcf  mov     rax, [rbx+480h]
0x180021bd6  lea     rdx, [rbx+4D8h]
0x180021bdd  mov     rcx, rdi
0x180021be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021be5  test    eax, eax
0x180021be7  jnz     short loc_180021BC3
0x180021be9  mov     rax, [rbx+480h]
0x180021bf0  lea     rdx, [rbx+4E0h]
0x180021bf7  mov     rcx, rdi
0x180021bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bff  test    eax, eax
0x180021c01  jnz     short loc_180021BC3
0x180021c03  mov     rax, [rbx+480h]
0x180021c0a  lea     rdx, [rbx+4E8h]
0x180021c11  mov     rcx, rdi
0x180021c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c19  test    eax, eax
0x180021c1b  jnz     short loc_180021BC3
0x180021c1d  lea     rcx, [rbx+510h]; lpCriticalSection
0x180021c24  call    cs:__imp_InitializeCriticalSection
0x180021c2a  xor     eax, eax
0x180021c2c  mov     rbx, [rsp+28h+arg_0]
0x180021c31  add     rsp, 20h
0x180021c35  pop     rdi
0x180021c36  retn
```
