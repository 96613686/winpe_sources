# LiveUserDebugServices::GetOutOfProcessFunctionTableW(unsigned __int64,ushort *,int,unsigned __int64,unsigned __int64,void *,ulong,ulong *,unsigned __int64 *)

- ea: `0x1804210c0`
- end: `0x1804212fd`
- name: `?GetOutOfProcessFunctionTableW@LiveUserDebugServices@@UEAAJ_KPEAGH00PEAXKPEAKPEA_K@Z`
- size: `573`
- prototype: `int(LiveUserDebugServices *__hidden this, unsigned __int64, unsigned __int16 *, int, unsigned __int64, unsigned __int64, void *, unsigned int, unsigned int *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800e39c8`
- `0x1804210c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18042113b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18042113b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1804211fa`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1804211fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180421103`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180421103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180421118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180421212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042122c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180421250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180421118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180421212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042122c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180421250`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1804211d8`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1804211d8`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1804211c6`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1804211c6`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x180421193`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x180421193`

## string_xrefs

- `0x18042117e`: `Software\Microsoft\Windows NT\CurrentVersion\KnownFunctionTableDlls`

## pseudocode

```c
__int64 __fastcall LiveUserDebugServices::GetOutOfProcessFunctionTableW(
        LiveUserDebugServices *this,
        __int64 a2,
        unsigned __int16 *a3,
        int a4,
        HMODULE hModule,
        unsigned __int64 a6,
        void *a7,
        unsigned int a8,
        unsigned int *a9,
        unsigned __int64 *a10)
{
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v15; // ebx
  LSTATUS v16; // ebx
  signed int LastError; // eax
  signed int v18; // eax
  int v19; // ebx
  int v20; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+34h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  void *Src; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+30h] BYREF

  v20 = 0;
  Src = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( hModule )
  {
    Library = hModule;
    goto LABEL_5;
  }
  if ( !a4
    || (hKey = 0,
        Type = 0,
        cbData = 0,
        !RegOpenKeyExA(
           HKEY_LOCAL_MACHINE,
           "Software\\Microsoft\\Windows NT\\CurrentVersion\\KnownFunctionTableDlls",
           0,
           0x20019u,
           &hKey))
    && (cbData = 0, v16 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v16) )
  {
    Library = LoadLibraryExW(a3, 0, 0);
    if ( !Library )
    {
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        return (unsigned int)-2147467259;
      }
      return v15;
    }
LABEL_5:
    ProcAddress = GetProcAddress(Library, "OutOfProcessFunctionTableCallback");
    if ( ProcAddress )
    {
      v19 = ((__int64 (__fastcall *)(__int64, unsigned __int64, int *, void **))ProcAddress)(a2, a6, &v20, &Src);
      if ( v19 >= 0 )
      {
        if ( !Src )
        {
          v15 = -2147467262;
          goto LABEL_8;
        }
        v15 = FillDataBuffer(Src, 12 * v20, a7, a8, a9);
        MEMORY[0](NtCurrentPeb()->ProcessHeap, 0, Src);
      }
      else
      {
        v15 = v19 | 0x10000000;
      }
    }
    else
    {
      if ( !GetLastError() )
      {
        v15 = -2147467259;
        goto LABEL_8;
      }
      v18 = GetLastError();
      v15 = v18;
      if ( v18 > 0 )
        v15 = (unsigned __int16)v18 | 0x80070000;
    }
    if ( (v15 & 0x80000000) == 0 && a10 )
    {
      *a10 = (unsigned __int64)Library;
      return v15;
    }
LABEL_8:
    if ( !hModule )
      FreeLibrary(Library);
    return v15;
  }
  return 2147942405LL;
}

```

## disassembly

```asm
0x1804210c0  push    rbp
0x1804210c2  push    rbx
0x1804210c3  push    rdi
0x1804210c4  push    r14
0x1804210c6  mov     rbp, rsp
0x1804210c9  sub     rsp, 58h
0x1804210cd  mov     [rbp+var_28], 0
0x1804210d4  mov     rdi, r8
0x1804210d7  mov     [rbp+Src], 0
0x1804210df  mov     r14, rdx
0x1804210e2  test    rdx, rdx
0x1804210e5  jnz     short loc_1804210EE
0x1804210e7  mov     eax, 80070057h
0x1804210ec  jmp     short loc_180421149
0x1804210ee  cmp     [rbp+hModule], 0
0x1804210f3  jz      short loc_180421154
0x1804210f5  mov     rdi, [rbp+hModule]
0x1804210f9  lea     rdx, aOutofprocessfu; "OutOfProcessFunctionTableCallback"
0x180421100  mov     rcx, rdi; hModule
0x180421103  call    cs:__imp_GetProcAddress
0x18042110a  nop     dword ptr [rax+rax+00h]
0x18042110f  test    rax, rax
0x180421112  jnz     loc_18042126D
0x180421118  call    cs:__imp_GetLastError
0x18042111f  nop     dword ptr [rax+rax+00h]
0x180421124  test    eax, eax
0x180421126  jnz     loc_180421250
0x18042112c  mov     ebx, 80004005h
0x180421131  cmp     [rbp+hModule], 0
0x180421136  jnz     short loc_180421147
0x180421138  mov     rcx, rdi; hLibModule
0x18042113b  call    cs:__imp_FreeLibrary
0x180421142  nop     dword ptr [rax+rax+00h]
0x180421147  mov     eax, ebx
0x180421149  add     rsp, 58h
0x18042114d  pop     r14
0x18042114f  pop     rdi
0x180421150  pop     rbx
0x180421151  pop     rbp
0x180421152  retn
0x180421154  test    r9d, r9d
0x180421157  jz      loc_1804211F2
0x18042115d  lea     rax, [rbp+hKey]
0x180421161  mov     [rbp+hKey], 0
0x180421169  mov     r9d, 20019h; samDesired
0x18042116f  mov     [rsp+58h+phkResult], rax; phkResult
0x180421174  xor     r8d, r8d; ulOptions
0x180421177  mov     [rbp+Type], 0
0x18042117e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180421185  mov     [rbp+cbData], 0
0x18042118c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180421193  call    cs:__imp_RegOpenKeyExA
0x18042119a  nop     dword ptr [rax+rax+00h]
0x18042119f  test    eax, eax
0x1804211a1  jnz     short loc_1804211E8
0x1804211a3  mov     rcx, [rbp+hKey]; hKey
0x1804211a7  lea     r9, [rbp+Type]; lpType
0x1804211ab  mov     [rbp+cbData], eax
0x1804211ae  xor     r8d, r8d; lpReserved
0x1804211b1  lea     rax, [rbp+cbData]
0x1804211b5  mov     rdx, rdi; lpValueName
0x1804211b8  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1804211bd  mov     [rsp+58h+phkResult], 0; lpData
0x1804211c6  call    cs:__imp_RegQueryValueExW
0x1804211cd  nop     dword ptr [rax+rax+00h]
0x1804211d2  mov     rcx, [rbp+hKey]; hKey
0x1804211d6  mov     ebx, eax
0x1804211d8  call    cs:__imp_RegCloseKey
0x1804211df  nop     dword ptr [rax+rax+00h]
0x1804211e4  test    ebx, ebx
0x1804211e6  jz      short loc_1804211F2
0x1804211e8  mov     eax, 80070005h
0x1804211ed  jmp     loc_180421149
0x1804211f2  xor     r8d, r8d; dwFlags
0x1804211f5  xor     edx, edx; hFile
0x1804211f7  mov     rcx, rdi; lpLibFileName
0x1804211fa  call    cs:__imp_LoadLibraryExW
0x180421201  nop     dword ptr [rax+rax+00h]
0x180421206  mov     rdi, rax
0x180421209  test    rax, rax
0x18042120c  jnz     loc_1804210F9
0x180421212  call    cs:__imp_GetLastError
0x180421219  nop     dword ptr [rax+rax+00h]
0x18042121e  test    eax, eax
0x180421220  jnz     short loc_18042122C
0x180421222  mov     ebx, 80004005h
0x180421227  jmp     loc_180421147
0x18042122c  call    cs:__imp_GetLastError
0x180421233  nop     dword ptr [rax+rax+00h]
0x180421238  mov     ebx, eax
0x18042123a  test    eax, eax
0x18042123c  jle     loc_180421147
0x180421242  movzx   ebx, ax
0x180421245  or      ebx, 80070000h
0x18042124b  jmp     loc_180421147
0x180421250  call    cs:__imp_GetLastError
0x180421257  nop     dword ptr [rax+rax+00h]
0x18042125c  mov     ebx, eax
0x18042125e  test    eax, eax
0x180421260  jle     short loc_1804212E0
0x180421262  movzx   ebx, ax
0x180421265  or      ebx, 80070000h
0x18042126b  jmp     short loc_1804212E0
0x18042126d  mov     rdx, [rbp+arg_28]
0x180421271  lea     r9, [rbp+Src]
0x180421275  lea     r8, [rbp+var_28]
0x180421279  mov     rcx, r14
0x18042127c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180421281  mov     ebx, eax
0x180421283  test    eax, eax
0x180421285  jns     short loc_18042128D
0x180421287  bts     ebx, 1Ch
0x18042128b  jmp     short loc_1804212E0
0x18042128d  mov     rcx, [rbp+Src]; Src
0x180421291  test    rcx, rcx
0x180421294  jnz     short loc_1804212A0
0x180421296  mov     ebx, 80004002h
0x18042129b  jmp     loc_180421131
0x1804212a0  mov     eax, [rbp+var_28]
0x1804212a3  mov     r9d, [rbp+arg_38]; unsigned int
0x1804212a7  mov     r8, [rbp+arg_30]; void *
0x1804212ab  lea     edx, [rax+rax*2]
0x1804212ae  mov     rax, [rbp+arg_40]
0x1804212b2  shl     edx, 2; unsigned int
0x1804212b5  mov     [rsp+58h+phkResult], rax; unsigned int *
0x1804212ba  call    ?FillDataBuffer@@YAJPEAXK0KPEAK@Z; FillDataBuffer(void *,ulong,void *,ulong,ulong *)
0x1804212bf  mov     ebx, eax
0x1804212c1  xor     edx, edx
0x1804212c3  mov     rax, cs:qword_18082DD08
0x1804212ca  mov     rcx, gs:60h
0x1804212d3  mov     r8, [rbp+Src]
0x1804212d7  mov     rcx, [rcx+30h]
0x1804212db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804212e0  test    ebx, ebx
0x1804212e2  js      loc_180421131
0x1804212e8  mov     rax, [rbp+arg_48]
0x1804212ec  test    rax, rax
0x1804212ef  jz      loc_180421131
0x1804212f5  mov     [rax], rdi
0x1804212f8  jmp     loc_180421147
```
