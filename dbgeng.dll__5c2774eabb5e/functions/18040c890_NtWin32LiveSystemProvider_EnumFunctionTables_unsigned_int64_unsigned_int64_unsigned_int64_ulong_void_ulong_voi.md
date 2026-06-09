# NtWin32LiveSystemProvider::EnumFunctionTables(unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,ulong *,void *,ulong,void * *,MiniDumpProviderCallbacks *,ushort *)

- ea: `0x18040c890`
- end: `0x18040cc68`
- name: `?EnumFunctionTables@NtWin32LiveSystemProvider@@UEAAJPEA_K00PEAKPEAXKPEAPEAXPEAVMiniDumpProviderCallbacks@@PEAG@Z`
- size: `984`
- prototype: `__int64 __usercall@<rax>(NtWin32LiveSystemProvider *__hidden this@<rcx>, unsigned __int64 *@<rdx>, unsigned __int64 *@<r8>, unsigned __int64 *@<r9>, unsigned int *, void *, unsigned int, void **, struct MiniDumpProviderCallbacks *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800f0f40`
- `0x1800f17b0`
- `0x180402690`
- `0x1804083a0`
- `0x1804083ec`
- `0x18040c890`
- `0x1804da880`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18040cb73`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18040cc0a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18040cb73`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18040cc0a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18040cb12`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18040cb12`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040cb44`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040cb44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18040cb29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18040cb29`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x18040cab6`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x18040cab6`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18040caa3`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18040caa3`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x18040ca6a`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x18040ca6a`

## string_xrefs

- `0x18040ca49`: `Software\Microsoft\Windows NT\CurrentVersion\KnownFunctionTableDlls`

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
  unsigned __int64 *v11; // r15
  unsigned __int64 *v12; // rbx
  DWORD IsTrusted; // edi
  __int64 v14; // r12
  int v15; // eax
  unsigned __int64 *v16; // rax
  bool v17; // zf
  void *v18; // r15
  __int64 v19; // r8
  unsigned __int64 v20; // rcx
  LSTATUS v21; // ebx
  const unsigned __int16 *v22; // rcx
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  void *v25; // rax
  unsigned int v27; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+4Ch] [rbp-B4h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  void *v32; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 *v33; // [rsp+60h] [rbp-A0h]
  void *Src; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 *v35; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v36; // [rsp+78h] [rbp-88h]
  unsigned __int64 *v37; // [rsp+80h] [rbp-80h]
  struct MiniDumpProviderCallbacks *v38; // [rsp+88h] [rbp-78h]
  void **v39; // [rsp+90h] [rbp-70h]
  WCHAR ValueName[360]; // [rsp+A0h] [rbp-60h] BYREF

  v11 = a3;
  v12 = a2;
  v39 = a8;
  v38 = a9;
  v35 = a4;
  v37 = a3;
  v33 = a2;
  v36 = a10;
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
      v30 = v15 + 1;
      if ( (unsigned int)(v15 + 1) > 0x10000 )
        return (DWORD)-805305826;
      IsTrusted = (*(__int64 (__fastcall **)(NtWin32LiveSystemProvider *, _QWORD, __int64, _QWORD *, int))(*(_QWORD *)this + 240LL))(
                    this,
                    *((_QWORD *)this + 82),
                    v14,
                    a6,
                    136);
      if ( IsTrusted )
        return IsTrusted;
      v16 = v35;
      *((_QWORD *)this + 130) = *a6;
      *v12 = a6[4];
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
      Type = IsTrusted;
      cbData = IsTrusted;
      v27 = IsTrusted;
      v32 = 0;
      if ( !*((_QWORD *)this + 112) )
        return (DWORD)-2147467263;
      v19 = a6[9];
      if ( v19
        && !(*(unsigned int (__fastcall **)(NtWin32LiveSystemProvider *, _QWORD, __int64, WCHAR *, int, unsigned int *))(*(_QWORD *)this + 232LL))(
              this,
              *((_QWORD *)this + 82),
              v19,
              ValueName,
              718,
              &v27) )
      {
        if ( v27 > 0x2CE )
          return (DWORD)-2147467259;
        v20 = v27 & 0xFFFFFFFE;
        if ( v20 >= 0x2D0 )
          _report_rangecheckfailure();
        *(WCHAR *)((char *)ValueName + v20) = 0;
        if ( !RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "Software\\Microsoft\\Windows NT\\CurrentVersion\\KnownFunctionTableDlls",
                0,
                0x20019u,
                &hKey) )
          break;
      }
LABEL_27:
      v14 = *((_QWORD *)this + 130);
      if ( !v14 )
        return 1;
      v15 = v30;
      v11 = v37;
    }
    cbData = 0;
    v21 = RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    if ( v21 )
    {
      IsTrusted = Win32LiveSystemProvider::VerifyModuleIsTrusted(this, ValueName, &v32);
      if ( IsTrusted )
      {
        if ( !GenStrLengthW(v36) )
        {
LABEL_26:
          v12 = v33;
          goto LABEL_27;
        }
        GenStrCopyNW(ValueName, v22, 360);
        IsTrusted = 0;
      }
      v18 = v32;
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
        v25 = (void *)(*(__int64 (__fastcall **)(struct MiniDumpProviderCallbacks *, _QWORD))(*(_QWORD *)v38 + 8LL))(
                        v38,
                        12 * *a5);
        *v39 = v25;
        if ( v25 )
          memmove(v25, Src, 12LL * *a5);
        else
          IsTrusted = -2147024882;
        (*((void (__fastcall **)(PVOID, _QWORD, void *))this + 112))(NtCurrentPeb()->ProcessHeap, 0, Src);
        FreeLibrary(Library);
        return IsTrusted;
      }
      FreeLibrary(Library);
    }
    goto LABEL_26;
  }
  return (DWORD)-2147024809;
}

```

## disassembly

```asm
0x18040c890  push    rbp
0x18040c892  push    rbx
0x18040c893  push    rsi
0x18040c894  push    rdi
0x18040c895  push    r12
0x18040c897  push    r13
0x18040c899  push    r14
0x18040c89b  push    r15
0x18040c89d  lea     rbp, [rsp-288h]
0x18040c8a5  sub     rsp, 388h
0x18040c8ac  mov     rax, cs:__security_cookie
0x18040c8b3  xor     rax, rsp
0x18040c8b6  mov     [rbp+2C0h+var_50], rax
0x18040c8bd  cmp     [rbp+2C0h+arg_30], 88h
0x18040c8c7  mov     rsi, rcx
0x18040c8ca  mov     rax, [rbp+2C0h+arg_38]
0x18040c8d1  mov     r15, r8
0x18040c8d4  mov     rcx, [rbp+2C0h+arg_48]
0x18040c8db  mov     rbx, rdx
0x18040c8de  mov     r14, [rbp+2C0h+arg_28]
0x18040c8e5  mov     r13, [rbp+2C0h+arg_20]
0x18040c8ec  mov     [rbp+2C0h+var_330], rax
0x18040c8f0  mov     rax, [rbp+2C0h+arg_40]
0x18040c8f7  mov     [rbp+2C0h+var_338], rax
0x18040c8fb  mov     [rsp+3C0h+var_350], r9
0x18040c900  mov     [rbp+2C0h+var_340], r8
0x18040c904  mov     [rsp+3C0h+var_360], rdx
0x18040c909  mov     [rsp+3C0h+var_348], rcx
0x18040c90e  jz      short loc_18040C91A
0x18040c910  mov     edi, 80070057h
0x18040c915  jmp     loc_18040CC3C
0x18040c91a  mov     r12, [rsi+410h]
0x18040c921  test    r12, r12
0x18040c924  jz      loc_18040CC37
0x18040c92a  xor     eax, eax
0x18040c92c  cmp     r12, [rsi+408h]
0x18040c933  jz      loc_18040CC37
0x18040c939  inc     eax
0x18040c93b  mov     [rsp+3C0h+var_374], eax
0x18040c93f  cmp     eax, 10000h
0x18040c944  ja      loc_18040CC30
0x18040c94a  mov     rax, [rsi]
0x18040c94d  mov     r9, r14
0x18040c950  mov     rdx, [rsi+290h]
0x18040c957  mov     r8, r12
0x18040c95a  mov     rcx, rsi
0x18040c95d  mov     dword ptr [rsp+3C0h+phkResult], 88h
0x18040c965  mov     rax, [rax+0F0h]
0x18040c96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18040c971  mov     edi, eax
0x18040c973  test    eax, eax
0x18040c975  jnz     loc_18040CC3C
0x18040c97b  mov     rcx, [r14]
0x18040c97e  mov     rax, [rsp+3C0h+var_350]
0x18040c983  mov     [rsi+410h], rcx
0x18040c98a  mov     rcx, [r14+20h]
0x18040c98e  mov     [rbx], rcx
0x18040c991  mov     rcx, [r14+28h]
0x18040c995  mov     [r15], rcx
0x18040c998  mov     rcx, [r14+30h]
0x18040c99c  mov     [rax], rcx
0x18040c99f  cmp     dword ptr [r14+50h], 2
0x18040c9a4  mov     [rsp+3C0h+Src], 0
0x18040c9ad  jnz     loc_18040CC26
0x18040c9b3  xor     r15d, r15d
0x18040c9b6  mov     [rsp+3C0h+hKey], 0
0x18040c9bf  mov     [rsp+3C0h+Type], edi
0x18040c9c3  mov     [rsp+3C0h+cbData], edi
0x18040c9c7  mov     [rsp+3C0h+var_380], edi
0x18040c9cb  mov     [rsp+3C0h+var_368], r15
0x18040c9d0  cmp     [rsi+380h], r15
0x18040c9d7  jz      loc_18040CC1F
0x18040c9dd  mov     r8, [r14+48h]
0x18040c9e1  test    r8, r8
0x18040c9e4  jz      loc_18040CB84
0x18040c9ea  mov     rax, [rsi]
0x18040c9ed  lea     rcx, [rsp+3C0h+var_380]
0x18040c9f2  mov     rdx, [rsi+290h]
0x18040c9f9  lea     r9, [rbp+2C0h+ValueName]
0x18040c9fd  mov     [rsp+3C0h+lpcbData], rcx
0x18040ca02  mov     rcx, rsi
0x18040ca05  mov     dword ptr [rsp+3C0h+phkResult], 2CEh
0x18040ca0d  mov     rax, [rax+0E8h]
0x18040ca14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18040ca19  test    eax, eax
0x18040ca1b  jnz     loc_18040CB84
0x18040ca21  cmp     [rsp+3C0h+var_380], 2CEh
0x18040ca29  ja      loc_18040CC18
0x18040ca2f  mov     ecx, [rsp+3C0h+var_380]
0x18040ca33  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18040ca37  cmp     rcx, 2D0h
0x18040ca3e  jnb     loc_18040CC62
0x18040ca44  mov     [rbp+rcx+2C0h+ValueName], ax
0x18040ca49  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18040ca50  lea     rax, [rsp+3C0h+hKey]
0x18040ca55  mov     r9d, 20019h; samDesired
0x18040ca5b  xor     r8d, r8d; ulOptions
0x18040ca5e  mov     [rsp+3C0h+phkResult], rax; phkResult
0x18040ca63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18040ca6a  call    cs:__imp_RegOpenKeyExA
0x18040ca71  nop     dword ptr [rax+rax+00h]
0x18040ca76  test    eax, eax
0x18040ca78  jnz     loc_18040CB84
0x18040ca7e  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18040ca83  lea     rax, [rsp+3C0h+cbData]
0x18040ca88  mov     [rsp+3C0h+lpcbData], rax; lpcbData
0x18040ca8d  lea     r9, [rsp+3C0h+Type]; lpType
0x18040ca92  xor     r8d, r8d; lpReserved
0x18040ca95  mov     [rsp+3C0h+phkResult], r15; lpData
0x18040ca9a  lea     rdx, [rbp+2C0h+ValueName]; lpValueName
0x18040ca9e  mov     [rsp+3C0h+cbData], r15d
0x18040caa3  call    cs:__imp_RegQueryValueExW
0x18040caaa  nop     dword ptr [rax+rax+00h]
0x18040caaf  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18040cab4  mov     ebx, eax
0x18040cab6  call    cs:__imp_RegCloseKey
0x18040cabd  nop     dword ptr [rax+rax+00h]
0x18040cac2  test    ebx, ebx
0x18040cac4  jz      short loc_18040CB09
0x18040cac6  lea     r8, [rsp+3C0h+var_368]; void **
0x18040cacb  mov     rcx, rsi; this
0x18040cace  lea     rdx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18040cad2  call    ?VerifyModuleIsTrusted@Win32LiveSystemProvider@@IEAAJPEBGPEAPEAX@Z; Win32LiveSystemProvider::VerifyModuleIsTrusted(ushort const *,void * *)
0x18040cad7  mov     edi, eax
0x18040cad9  test    eax, eax
0x18040cadb  jz      short loc_18040CB04
0x18040cadd  mov     rcx, [rsp+3C0h+var_348]; unsigned __int16 *
0x18040cae2  call    ?GenStrLengthW@@YA_KPEBG@Z; GenStrLengthW(ushort const *)
0x18040cae7  test    rax, rax
0x18040caea  jz      loc_18040CB7F
0x18040caf0  mov     rdx, rcx; unsigned __int16 *
0x18040caf3  mov     r8d, 168h; int
0x18040caf9  lea     rcx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18040cafd  call    ?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z; GenStrCopyNW(ushort *,ushort const *,int)
0x18040cb02  xor     edi, edi
0x18040cb04  mov     r15, [rsp+3C0h+var_368]
0x18040cb09  xor     r8d, r8d; dwFlags
0x18040cb0c  lea     rcx, [rbp+2C0h+ValueName]; lpLibFileName
0x18040cb10  xor     edx, edx; hFile
0x18040cb12  call    cs:__imp_LoadLibraryExW
0x18040cb19  nop     dword ptr [rax+rax+00h]
0x18040cb1e  mov     rbx, rax
0x18040cb21  test    r15, r15
0x18040cb24  jz      short loc_18040CB35
0x18040cb26  mov     rcx, r15; hObject
0x18040cb29  call    cs:__imp_CloseHandle
0x18040cb30  nop     dword ptr [rax+rax+00h]
0x18040cb35  test    rbx, rbx
0x18040cb38  jz      short loc_18040CB7F
0x18040cb3a  lea     rdx, aOutofprocessfu; "OutOfProcessFunctionTableCallback"
0x18040cb41  mov     rcx, rbx; hModule
0x18040cb44  call    cs:__imp_GetProcAddress
0x18040cb4b  nop     dword ptr [rax+rax+00h]
0x18040cb50  test    rax, rax
0x18040cb53  jz      short loc_18040CB70
0x18040cb55  mov     rcx, [rsi+290h]
0x18040cb5c  lea     r9, [rsp+3C0h+Src]
0x18040cb61  mov     r8, r13
0x18040cb64  mov     rdx, r12
0x18040cb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18040cb6c  test    eax, eax
0x18040cb6e  jns     short loc_18040CBA1
0x18040cb70  mov     rcx, rbx; hLibModule
0x18040cb73  call    cs:__imp_FreeLibrary
0x18040cb7a  nop     dword ptr [rax+rax+00h]
0x18040cb7f  mov     rbx, [rsp+3C0h+var_360]
0x18040cb84  mov     r12, [rsi+410h]
0x18040cb8b  test    r12, r12
0x18040cb8e  jz      loc_18040CC37
0x18040cb94  mov     eax, [rsp+3C0h+var_374]
0x18040cb98  mov     r15, [rbp+2C0h+var_340]
0x18040cb9c  jmp     loc_18040C92C
0x18040cba1  mov     eax, [r13+0]
0x18040cba5  mov     rcx, [rbp+2C0h+var_338]
0x18040cba9  lea     edx, [rax+rax*2]
0x18040cbac  mov     r8, [rcx]
0x18040cbaf  shl     edx, 2
0x18040cbb2  mov     rax, [r8+8]
0x18040cbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18040cbbb  mov     rcx, [rbp+2C0h+var_330]
0x18040cbbf  mov     [rcx], rax
0x18040cbc2  test    rax, rax
0x18040cbc5  jz      short loc_18040CBE2
0x18040cbc7  mov     ecx, [r13+0]
0x18040cbcb  mov     rdx, [rsp+3C0h+Src]; Src
0x18040cbd0  lea     r8, [rcx+rcx*2]
0x18040cbd4  mov     rcx, rax; void *
0x18040cbd7  shl     r8, 2; Size
0x18040cbdb  call    memmove
0x18040cbe0  jmp     short loc_18040CBE7
0x18040cbe2  mov     edi, 8007000Eh
0x18040cbe7  mov     rcx, gs:60h
0x18040cbf0  xor     edx, edx
0x18040cbf2  mov     r8, [rsp+3C0h+Src]
0x18040cbf7  mov     rax, [rsi+380h]
0x18040cbfe  mov     rcx, [rcx+30h]
0x18040cc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18040cc07  mov     rcx, rbx; hLibModule
0x18040cc0a  call    cs:__imp_FreeLibrary
0x18040cc11  nop     dword ptr [rax+rax+00h]
0x18040cc16  jmp     short loc_18040CC3C
0x18040cc18  mov     edi, 80004005h
0x18040cc1d  jmp     short loc_18040CC3C
0x18040cc1f  mov     edi, 80004001h
0x18040cc24  jmp     short loc_18040CC3C
0x18040cc26  mov     eax, [r14+54h]
0x18040cc2a  mov     [r13+0], eax
0x18040cc2e  jmp     short loc_18040CC3C
0x18040cc30  mov     edi, 0D000021Eh
0x18040cc35  jmp     short loc_18040CC3C
0x18040cc37  mov     edi, 1
0x18040cc3c  mov     eax, edi
0x18040cc3e  mov     rcx, [rbp+2C0h+var_50]
0x18040cc45  xor     rcx, rsp; StackCookie
0x18040cc48  call    __security_check_cookie
0x18040cc4d  add     rsp, 388h
0x18040cc54  pop     r15
0x18040cc56  pop     r14
0x18040cc58  pop     r13
0x18040cc5a  pop     r12
0x18040cc5c  pop     rdi
0x18040cc5d  pop     rsi
0x18040cc5e  pop     rbx
0x18040cc5f  pop     rbp
0x18040cc60  retn
0x18040cc62  call    __report_rangecheckfailure
```
