# NtWin32LiveSystemProvider::EnumFunctionTables(unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong *,void *,ulong,void * *,MiniDumpProviderCallbacks *,ushort *)

- ea: `0x180023560`
- end: `0x18002391a`
- name: `?EnumFunctionTables@NtWin32LiveSystemProvider@@UEAAJPEA_K00PEAKPEAXKPEAPEAXPEAVMiniDumpProviderCallbacks@@PEAG@Z`
- size: `954`
- prototype: `__int64 __fastcall(NtWin32LiveSystemProvider *this, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned int *, _QWORD *, unsigned int, void **, struct MiniDumpProviderCallbacks *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001710`
- `0x180001b70`
- `0x180003424`
- `0x180016198`
- `0x18001bec8`
- `0x180023560`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800237e3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800237e3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180023809`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180023809`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180023832`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800238c3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180023832`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800238c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800237f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800237f4`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x180023740`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x180023740`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180023783`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180023783`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x180023776`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x180023776`

## string_xrefs

- `0x180023736`: `Software\Microsoft\Windows NT\CurrentVersion\KnownFunctionTableDlls`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::EnumFunctionTables(
        NtWin32LiveSystemProvider *this,
        unsigned __int64 *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4,
        unsigned int *a5,
        _QWORD *a6,
        unsigned int a7,
        void **a8,
        struct MiniDumpProviderCallbacks *a9,
        unsigned __int16 *a10)
{
  unsigned __int64 *v10; // rbx
  unsigned __int64 *v11; // r15
  unsigned int IsTrusted; // edi
  __int64 v14; // r12
  int v15; // eax
  unsigned __int64 *v16; // rax
  bool v17; // zf
  void *v18; // r15
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned __int64 v22; // rcx
  LSTATUS v23; // ebx
  unsigned __int16 *v24; // rcx
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  void *v28; // rax
  unsigned int v30; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+4Ch] [rbp-B4h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  void *v35; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 *v36; // [rsp+60h] [rbp-A0h]
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 *v38; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v39; // [rsp+78h] [rbp-88h]
  unsigned __int64 *v40; // [rsp+80h] [rbp-80h]
  struct MiniDumpProviderCallbacks *v41; // [rsp+88h] [rbp-78h]
  void **v42; // [rsp+90h] [rbp-70h]
  WCHAR ValueName[360]; // [rsp+A0h] [rbp-60h] BYREF

  v10 = a2;
  v11 = a3;
  v42 = a8;
  v36 = a2;
  v41 = a9;
  v38 = a4;
  v40 = a3;
  v39 = a10;
  if ( a7 == 136 )
  {
    v14 = *((_QWORD *)this + 130);
    if ( !v14 )
      return 1;
    v15 = 0;
    while ( 1 )
    {
      if ( v14 == *((_QWORD *)this + 129) )
        return 1;
      v33 = v15 + 1;
      if ( (unsigned int)(v15 + 1) > 0x10000 )
        return (unsigned int)-805305826;
      IsTrusted = (*(__int64 (__fastcall **)(NtWin32LiveSystemProvider *, _QWORD, __int64, _QWORD *, int))(*(_QWORD *)this + 240LL))(
                    this,
                    *((_QWORD *)this + 82),
                    v14,
                    a6,
                    136);
      if ( IsTrusted )
        return IsTrusted;
      v16 = v38;
      *((_QWORD *)this + 130) = *a6;
      *v10 = a6[4];
      *v11 = a6[5];
      *v16 = a6[6];
      v17 = *((_DWORD *)a6 + 20) == 2;
      Src = 0;
      if ( !v17 )
      {
        *a5 = *((_DWORD *)a6 + 21);
        return IsTrusted;
      }
      v18 = 0;
      hKey = 0;
      Type = 0;
      cbData = 0;
      v30 = 0;
      v35 = 0;
      if ( !*((_QWORD *)this + 112) )
        return (unsigned int)-2147467263;
      v19 = a6[9];
      if ( v19
        && !(*(unsigned int (__fastcall **)(NtWin32LiveSystemProvider *, _QWORD, __int64, WCHAR *, int, unsigned int *))(*(_QWORD *)this + 232LL))(
              this,
              *((_QWORD *)this + 82),
              v19,
              ValueName,
              718,
              &v30) )
      {
        if ( v30 > 0x2CE )
          return (unsigned int)-2147467259;
        v22 = v30 & 0xFFFFFFFE;
        if ( v22 >= 0x2D0 )
          _report_rangecheckfailure(v22, v20, v21, 0);
        *(WCHAR *)((char *)ValueName + v22) = 0;
        if ( !RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "Software\\Microsoft\\Windows NT\\CurrentVersion\\KnownFunctionTableDlls",
                0,
                0x20019u,
                &hKey) )
          break;
      }
LABEL_29:
      v14 = *((_QWORD *)this + 130);
      if ( !v14 )
        return 1;
      v15 = v33;
      v11 = v40;
    }
    cbData = 0;
    v23 = RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    if ( v23 )
    {
      IsTrusted = Win32LiveSystemProvider::VerifyModuleIsTrusted(this, ValueName, &v35);
      if ( IsTrusted )
      {
        v24 = v39;
        while ( *v24++ )
          ;
        if ( v24 - v39 == 1 )
        {
LABEL_28:
          v10 = v36;
          goto LABEL_29;
        }
        GenStrCopyNW(ValueName, v39, 360);
        IsTrusted = 0;
      }
      v18 = v35;
    }
    Library = LoadLibraryExW(ValueName, 0, 0);
    if ( v18 )
      CloseHandle(v18);
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "OutOfProcessFunctionTableCallback");
      if ( ProcAddress
        && ((int (__fastcall *)(_QWORD, __int64, unsigned int *, void **))ProcAddress)(
             *((_QWORD *)this + 82),
             v14,
             a5,
             &Src) >= 0 )
      {
        v28 = (void *)(*(__int64 (__fastcall **)(struct MiniDumpProviderCallbacks *, _QWORD))(*(_QWORD *)v41 + 8LL))(
                        v41,
                        12 * *a5);
        *v42 = v28;
        if ( v28 )
          memcpy_0(v28, Src, 12LL * *a5);
        else
          IsTrusted = -2147024882;
        (*((void (__fastcall **)(PVOID, _QWORD, void *))this + 112))(NtCurrentPeb()->ProcessHeap, 0, Src);
        FreeLibrary(Library);
        return IsTrusted;
      }
      FreeLibrary(Library);
    }
    goto LABEL_28;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180023560  push    rbp
0x180023562  push    rbx
0x180023563  push    rsi
0x180023564  push    rdi
0x180023565  push    r12
0x180023567  push    r13
0x180023569  push    r14
0x18002356b  push    r15
0x18002356d  lea     rbp, [rsp-288h]
0x180023575  sub     rsp, 388h
0x18002357c  mov     rax, cs:__security_cookie
0x180023583  xor     rax, rsp
0x180023586  mov     [rbp+2C0h+var_50], rax
0x18002358d  cmp     [rbp+2C0h+arg_30], 88h
0x180023597  mov     rbx, rdx
0x18002359a  mov     rax, [rbp+2C0h+arg_38]
0x1800235a1  mov     r15, r8
0x1800235a4  mov     r14, [rbp+2C0h+arg_28]
0x1800235ab  mov     rsi, rcx
0x1800235ae  mov     r13, [rbp+2C0h+arg_20]
0x1800235b5  mov     [rbp+2C0h+var_330], rax
0x1800235b9  mov     rax, [rbp+2C0h+arg_40]
0x1800235c0  mov     [rsp+3C0h+var_360], rdx
0x1800235c5  mov     rdx, [rbp+2C0h+arg_48]
0x1800235cc  mov     [rbp+2C0h+var_338], rax
0x1800235d0  mov     [rsp+3C0h+var_350], r9
0x1800235d5  mov     [rbp+2C0h+var_340], r8
0x1800235d9  mov     [rsp+3C0h+var_348], rdx
0x1800235de  jz      short loc_1800235EA
0x1800235e0  mov     edi, 80070057h
0x1800235e5  jmp     loc_1800238EF
0x1800235ea  mov     r12, [rcx+410h]
0x1800235f1  xor     r9d, r9d
0x1800235f4  test    r12, r12
0x1800235f7  jz      loc_1800238EA
0x1800235fd  mov     eax, r9d
0x180023600  cmp     r12, [rsi+408h]
0x180023607  jz      loc_1800238EA
0x18002360d  inc     eax
0x18002360f  mov     [rsp+3C0h+var_374], eax
0x180023613  cmp     eax, 10000h
0x180023618  ja      loc_1800238E3
0x18002361e  mov     rax, [rsi]
0x180023621  mov     r9, r14
0x180023624  mov     rdx, [rsi+290h]
0x18002362b  mov     r8, r12
0x18002362e  mov     rcx, rsi
0x180023631  mov     dword ptr [rsp+3C0h+phkResult], 88h
0x180023639  mov     rax, [rax+0F0h]
0x180023640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023645  xor     r9d, r9d
0x180023648  mov     edi, eax
0x18002364a  test    eax, eax
0x18002364c  jnz     loc_1800238EF
0x180023652  mov     rcx, [r14]
0x180023655  mov     rax, [rsp+3C0h+var_350]
0x18002365a  mov     [rsi+410h], rcx
0x180023661  mov     rcx, [r14+20h]
0x180023665  mov     [rbx], rcx
0x180023668  mov     rcx, [r14+28h]
0x18002366c  mov     [r15], rcx
0x18002366f  mov     rcx, [r14+30h]
0x180023673  mov     [rax], rcx
0x180023676  cmp     dword ptr [r14+50h], 2
0x18002367b  mov     [rsp+3C0h+Src], r9
0x180023680  jnz     loc_1800238D9
0x180023686  mov     r15d, r9d
0x180023689  mov     [rsp+3C0h+hKey], r9
0x18002368e  mov     [rsp+3C0h+Type], r9d
0x180023693  mov     [rsp+3C0h+cbData], r9d
0x180023698  mov     [rsp+3C0h+var_380], r9d
0x18002369d  mov     [rsp+3C0h+var_368], r9
0x1800236a2  cmp     [rsi+380h], r9
0x1800236a9  jz      loc_1800238D2
0x1800236af  mov     r8, [r14+48h]
0x1800236b3  test    r8, r8
0x1800236b6  jz      loc_18002383D
0x1800236bc  mov     rax, [rsi]
0x1800236bf  lea     rcx, [rsp+3C0h+var_380]
0x1800236c4  mov     rdx, [rsi+290h]
0x1800236cb  lea     r9, [rbp+2C0h+ValueName]
0x1800236cf  mov     [rsp+3C0h+lpcbData], rcx
0x1800236d4  mov     rcx, rsi
0x1800236d7  mov     dword ptr [rsp+3C0h+phkResult], 2CEh
0x1800236df  mov     rax, [rax+0E8h]
0x1800236e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236eb  xor     r9d, r9d
0x1800236ee  test    eax, eax
0x1800236f0  jnz     loc_18002383D
0x1800236f6  cmp     [rsp+3C0h+var_380], 2CEh
0x1800236fe  ja      loc_1800238CB
0x180023704  mov     ecx, [rsp+3C0h+var_380]
0x180023708  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18002370c  cmp     rcx, 2D0h
0x180023713  jnb     loc_180023914
0x180023719  mov     [rbp+rcx+2C0h+ValueName], r9w
0x18002371f  lea     rax, [rsp+3C0h+hKey]
0x180023724  mov     r9d, 20019h; samDesired
0x18002372a  mov     [rsp+3C0h+phkResult], rax; phkResult
0x18002372f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023736  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002373d  xor     r8d, r8d; ulOptions
0x180023740  call    cs:__imp_RegOpenKeyExA
0x180023746  xor     r9d, r9d
0x180023749  test    eax, eax
0x18002374b  jnz     loc_18002383D
0x180023751  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180023756  lea     rax, [rsp+3C0h+cbData]
0x18002375b  mov     [rsp+3C0h+lpcbData], rax; lpcbData
0x180023760  lea     rdx, [rbp+2C0h+ValueName]; lpValueName
0x180023764  mov     [rsp+3C0h+phkResult], r9; lpData
0x180023769  xor     r8d, r8d; lpReserved
0x18002376c  mov     [rsp+3C0h+cbData], r9d
0x180023771  lea     r9, [rsp+3C0h+Type]; lpType
0x180023776  call    cs:__imp_RegQueryValueExW
0x18002377c  mov     rcx, [rsp+3C0h+hKey]; hKey
0x180023781  mov     ebx, eax
0x180023783  call    cs:__imp_RegCloseKey
0x180023789  test    ebx, ebx
0x18002378b  jz      short loc_1800237DA
0x18002378d  lea     r8, [rsp+3C0h+var_368]; void **
0x180023792  mov     rcx, rsi; this
0x180023795  lea     rdx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x180023799  call    ?VerifyModuleIsTrusted@Win32LiveSystemProvider@@IEAAJPEBGPEAPEAX@Z; Win32LiveSystemProvider::VerifyModuleIsTrusted(ushort const *,void * *)
0x18002379e  mov     edi, eax
0x1800237a0  test    eax, eax
0x1800237a2  jz      short loc_1800237D5
0x1800237a4  mov     rdx, [rsp+3C0h+var_348]; unsigned __int16 *
0x1800237a9  mov     rcx, rdx
0x1800237ac  movzx   eax, word ptr [rcx]
0x1800237af  add     rcx, 2
0x1800237b3  test    ax, ax
0x1800237b6  jnz     short loc_1800237AC
0x1800237b8  sub     rcx, rdx
0x1800237bb  sar     rcx, 1
0x1800237be  cmp     rcx, 1
0x1800237c2  jz      short loc_180023838
0x1800237c4  mov     r8d, 168h; int
0x1800237ca  lea     rcx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x1800237ce  call    ?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z; GenStrCopyNW(ushort *,ushort const *,int)
0x1800237d3  xor     edi, edi
0x1800237d5  mov     r15, [rsp+3C0h+var_368]
0x1800237da  xor     r8d, r8d; dwFlags
0x1800237dd  lea     rcx, [rbp+2C0h+ValueName]; lpLibFileName
0x1800237e1  xor     edx, edx; hFile
0x1800237e3  call    cs:__imp_LoadLibraryExW
0x1800237e9  mov     rbx, rax
0x1800237ec  test    r15, r15
0x1800237ef  jz      short loc_1800237FA
0x1800237f1  mov     rcx, r15; hObject
0x1800237f4  call    cs:__imp_CloseHandle
0x1800237fa  test    rbx, rbx
0x1800237fd  jz      short loc_180023838
0x1800237ff  lea     rdx, aOutofprocessfu; "OutOfProcessFunctionTableCallback"
0x180023806  mov     rcx, rbx; hModule
0x180023809  call    cs:__imp_GetProcAddress
0x18002380f  test    rax, rax
0x180023812  jz      short loc_18002382F
0x180023814  mov     rcx, [rsi+290h]
0x18002381b  lea     r9, [rsp+3C0h+Src]
0x180023820  mov     r8, r13
0x180023823  mov     rdx, r12
0x180023826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002382b  test    eax, eax
0x18002382d  jns     short loc_18002385A
0x18002382f  mov     rcx, rbx; hLibModule
0x180023832  call    cs:__imp_FreeLibrary
0x180023838  mov     rbx, [rsp+3C0h+var_360]
0x18002383d  mov     r12, [rsi+410h]
0x180023844  test    r12, r12
0x180023847  jz      loc_1800238EA
0x18002384d  mov     eax, [rsp+3C0h+var_374]
0x180023851  mov     r15, [rbp+2C0h+var_340]
0x180023855  jmp     loc_180023600
0x18002385a  mov     eax, [r13+0]
0x18002385e  mov     rcx, [rbp+2C0h+var_338]
0x180023862  lea     edx, [rax+rax*2]
0x180023865  mov     r8, [rcx]
0x180023868  shl     edx, 2
0x18002386b  mov     rax, [r8+8]
0x18002386f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023874  mov     rcx, [rbp+2C0h+var_330]
0x180023878  mov     [rcx], rax
0x18002387b  test    rax, rax
0x18002387e  jz      short loc_18002389B
0x180023880  mov     ecx, [r13+0]
0x180023884  mov     rdx, [rsp+3C0h+Src]; Src
0x180023889  lea     r8, [rcx+rcx*2]
0x18002388d  mov     rcx, rax; void *
0x180023890  shl     r8, 2; Size
0x180023894  call    memcpy_0
0x180023899  jmp     short loc_1800238A0
0x18002389b  mov     edi, 8007000Eh
0x1800238a0  mov     rcx, gs:60h
0x1800238a9  xor     edx, edx
0x1800238ab  mov     r8, [rsp+3C0h+Src]
0x1800238b0  mov     rax, [rsi+380h]
0x1800238b7  mov     rcx, [rcx+30h]
0x1800238bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238c0  mov     rcx, rbx; hLibModule
0x1800238c3  call    cs:__imp_FreeLibrary
0x1800238c9  jmp     short loc_1800238EF
0x1800238cb  mov     edi, 80004005h
0x1800238d0  jmp     short loc_1800238EF
0x1800238d2  mov     edi, 80004001h
0x1800238d7  jmp     short loc_1800238EF
0x1800238d9  mov     eax, [r14+54h]
0x1800238dd  mov     [r13+0], eax
0x1800238e1  jmp     short loc_1800238EF
0x1800238e3  mov     edi, 0D000021Eh
0x1800238e8  jmp     short loc_1800238EF
0x1800238ea  mov     edi, 1
0x1800238ef  mov     eax, edi
0x1800238f1  mov     rcx, [rbp+2C0h+var_50]
0x1800238f8  xor     rcx, rsp; StackCookie
0x1800238fb  call    __security_check_cookie
0x180023900  add     rsp, 388h
0x180023907  pop     r15
0x180023909  pop     r14
0x18002390b  pop     r13
0x18002390d  pop     r12
0x18002390f  pop     rdi
0x180023910  pop     rsi
0x180023911  pop     rbx
0x180023912  pop     rbp
0x180023913  retn
0x180023914  call    __report_rangecheckfailure
```
