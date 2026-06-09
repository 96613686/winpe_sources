# Dfdll::CSubscription::InitializeIsolation(void)

- ea: `0x18000d59c`
- end: `0x18000d8de`
- name: `?InitializeIsolation@CSubscription@Dfdll@@IEAAJXZ`
- size: `834`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a040`

## callees

- `0x180002238`
- `0x1800077d0`
- `0x18000d59c`
- `0x180012b30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d77b`
- `KERNEL32!GetLastError` at `0x18000d77b`
- `KERNEL32!FreeLibrary` at `0x18000d7be`
- `KERNEL32!FreeLibrary` at `0x18000d7be`
- `KERNEL32!GetProcAddress` at `0x18000d81b`
- `KERNEL32!GetProcAddress` at `0x18000d83d`
- `KERNEL32!GetProcAddress` at `0x18000d85f`
- `KERNEL32!GetProcAddress` at `0x18000d881`
- `KERNEL32!GetProcAddress` at `0x18000d81b`
- `KERNEL32!GetProcAddress` at `0x18000d83d`
- `KERNEL32!GetProcAddress` at `0x18000d85f`
- `KERNEL32!GetProcAddress` at `0x18000d881`
- `KERNEL32!LoadLibraryExW` at `0x18000d770`
- `KERNEL32!LoadLibraryExW` at `0x18000d770`

## string_xrefs

- `0x18000d635`: `clr.dll`
- `0x18000d6f9`: `clr.dll`
- `0x18000d732`: `clr.dll`
- `0x18000d873`: `ParseManifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Dfdll::CSubscription::InitializeIsolation(Dfdll::CSubscription *this)
{
  HMODULE v1; // rcx
  __int64 v2; // rdx
  signed int ModuleFolderPath; // ebx
  WCHAR *v4; // r9
  const unsigned __int16 *v5; // rax
  unsigned int v6; // r8d
  const unsigned __int16 *v7; // rax
  int v8; // eax
  const unsigned __int16 *v9; // rax
  HMODULE Library; // rax
  const struct std::nothrow_t *v11; // rdx
  signed int LastError; // eax
  HMODULE v13; // rax
  void **v15; // [rsp+20h] [rbp-30h] BYREF
  void **v16; // [rsp+28h] [rbp-28h]
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-20h]
  int v18; // [rsp+38h] [rbp-18h]
  int v19; // [rsp+40h] [rbp-10h]

  v1 = Dfdll::CSubscription::_hClr;
  if ( Dfdll::CSubscription::_hClr )
    goto LABEL_42;
  v15 = &Dfdll::CString::`vftable';
  lpLibFileName = 0;
  v18 = 0;
  v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
  v19 = 0;
  ModuleFolderPath = Dfdll::CModule::GetModuleFolderPath(g_hModule, (struct Dfdll::CString *)&v15);
  if ( ModuleFolderPath < 0 )
  {
    v15 = &Dfdll::CString::`vftable';
    v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpLibFileName )
      operator delete((void *)lpLibFileName, (const struct std::nothrow_t *)v2);
    return (unsigned int)ModuleFolderPath;
  }
  v4 = (WCHAR *)lpLibFileName;
  if ( !lpLibFileName )
  {
    ModuleFolderPath = -2147024809;
    goto LABEL_27;
  }
  v2 = 0x7FFFFFFF;
  v5 = L"clr.dll";
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v2;
  }
  while ( v2 );
  v6 = v2 == 0 ? 0x80070057 : 0;
  if ( !v2 )
    goto LABEL_12;
  if ( (v2 != 0 ? 0x7FFFFFFF - (_DWORD)v2 : 0) != 0 )
  {
    if ( v19 && lpLibFileName[v19 - 1] != 92 )
    {
      v2 = 0x7FFFFFFF;
      v7 = L"\\";
      do
      {
        if ( !*v7 )
          break;
        ++v7;
        --v2;
      }
      while ( v2 );
      v6 = v2 == 0 ? 0x80070057 : 0;
      if ( !v2 )
      {
LABEL_12:
        ModuleFolderPath = v6;
        goto LABEL_27;
      }
      v8 = Dfdll::CString::Append((Dfdll::CString *)&v15, L"\\", v2 != 0 ? 0x7FFFFFFF - v2 : 0);
      v4 = (WCHAR *)lpLibFileName;
      if ( v8 < 0 )
      {
        ModuleFolderPath = v8;
        goto LABEL_27;
      }
    }
    v2 = 0x7FFFFFFF;
    v9 = L"clr.dll";
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v2;
    }
    while ( v2 );
    ModuleFolderPath = v2 == 0 ? 0x80070057 : 0;
    if ( !v2
      || (ModuleFolderPath = Dfdll::CString::Append((Dfdll::CString *)&v15, L"clr.dll", v2 != 0 ? 0x7FFFFFFF - v2 : 0),
          v4 = (WCHAR *)lpLibFileName,
          ModuleFolderPath < 0) )
    {
LABEL_27:
      v15 = &Dfdll::CString::`vftable';
      v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( v4 )
        operator delete(v4, (const struct std::nothrow_t *)v2);
      return (unsigned int)ModuleFolderPath;
    }
  }
  Library = LoadLibraryExW(v4, 0, 8u);
  if ( Library )
  {
    v13 = (HMODULE)_InterlockedExchange64((volatile __int64 *)&Dfdll::CSubscription::_hClr, (__int64)Library);
    if ( v13 )
      FreeLibrary(v13);
LABEL_39:
    v15 = &Dfdll::CString::`vftable';
    v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
    if ( lpLibFileName )
      operator delete((void *)lpLibFileName, v11);
    v1 = Dfdll::CSubscription::_hClr;
    if ( !Dfdll::CSubscription::_hClr )
      return 0;
LABEL_42:
    if ( !Dfdll::CSubscription::_pfnGetAppIdAuthority
      || !Dfdll::CSubscription::_pfnGetIdentityAuthority
      || !Dfdll::CSubscription::_pfnGetUserStore
      || !Dfdll::CSubscription::_pfnParseManifest )
    {
      _InterlockedCompareExchange64(
        (volatile signed __int64 *)&Dfdll::CSubscription::_pfnGetAppIdAuthority,
        (signed __int64)GetProcAddress(v1, "GetAppIdAuthority"),
        0);
      _InterlockedCompareExchange64(
        (volatile signed __int64 *)&Dfdll::CSubscription::_pfnGetIdentityAuthority,
        (signed __int64)GetProcAddress(Dfdll::CSubscription::_hClr, "GetIdentityAuthority"),
        0);
      _InterlockedCompareExchange64(
        (volatile signed __int64 *)&Dfdll::CSubscription::_pfnGetUserStore,
        (signed __int64)GetProcAddress(Dfdll::CSubscription::_hClr, "GetUserStore"),
        0);
      _InterlockedCompareExchange64(
        (volatile signed __int64 *)&Dfdll::CSubscription::_pfnParseManifest,
        (signed __int64)GetProcAddress(Dfdll::CSubscription::_hClr, "ParseManifest"),
        0);
      if ( !Dfdll::CSubscription::_pfnGetAppIdAuthority
        || !Dfdll::CSubscription::_pfnGetIdentityAuthority
        || !Dfdll::CSubscription::_pfnGetUserStore
        || !Dfdll::CSubscription::_pfnParseManifest )
      {
        return (unsigned int)-2147024769;
      }
    }
    return 0;
  }
  LastError = GetLastError();
  ModuleFolderPath = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    ModuleFolderPath = LastError;
  if ( ModuleFolderPath >= 0 )
    goto LABEL_39;
  v15 = &Dfdll::CString::`vftable';
  v16 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( lpLibFileName )
    operator delete((void *)lpLibFileName, v11);
  return (unsigned int)ModuleFolderPath;
}

```

## disassembly

```asm
0x18000d59c  mov     [rsp-18h+arg_0], rbx
0x18000d5a1  mov     [rsp-18h+arg_8], rsi
0x18000d5a6  mov     [rsp-18h+arg_10], rdi
0x18000d5ab  push    rbp
0x18000d5ac  push    r14
0x18000d5ae  push    r15
0x18000d5b0  mov     rbp, rsp
0x18000d5b3  sub     rsp, 50h
0x18000d5b7  mov     rcx, cs:?_hClr@CSubscription@Dfdll@@1PEAUHINSTANCE__@@EA; HINSTANCE__ * Dfdll::CSubscription::_hClr
0x18000d5be  xor     esi, esi
0x18000d5c0  test    rcx, rcx
0x18000d5c3  jnz     loc_18000D7EC
0x18000d5c9  lea     r14, ??_7CString@Dfdll@@6B@; const Dfdll::CString::`vftable'
0x18000d5d0  mov     [rbp+var_30], r14
0x18000d5d4  mov     [rbp+lpLibFileName], rsi
0x18000d5d8  mov     [rbp+var_18], esi
0x18000d5db  lea     r15, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000d5e2  mov     [rbp+var_28], r15
0x18000d5e6  mov     [rbp+var_10], esi
0x18000d5e9  lea     rdx, [rbp+var_30]; struct Dfdll::CString *
0x18000d5ed  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18000d5f4  call    ?GetModuleFolderPath@CModule@Dfdll@@SAJPEAUHINSTANCE__@@AEAVCString@2@@Z; Dfdll::CModule::GetModuleFolderPath(HINSTANCE__ *,Dfdll::CString &)
0x18000d5f9  mov     ebx, eax
0x18000d5fb  test    eax, eax
0x18000d5fd  jns     short loc_18000D61B
0x18000d5ff  mov     [rbp+var_30], r14
0x18000d603  mov     [rbp+var_28], r15
0x18000d607  mov     rcx, [rbp+lpLibFileName]; void *
0x18000d60b  test    rcx, rcx
0x18000d60e  jz      short loc_18000D616
0x18000d610  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d615  nop
0x18000d616  jmp     loc_18000D8C2
0x18000d61b  mov     r9, [rbp+lpLibFileName]
0x18000d61f  test    r9, r9
0x18000d622  jnz     short loc_18000D62E
0x18000d624  mov     ebx, 80070057h
0x18000d629  jmp     loc_18000D74C
0x18000d62e  mov     edi, 7FFFFFFFh
0x18000d633  mov     edx, edi
0x18000d635  lea     rax, aClrDll; "clr.dll"
0x18000d63c  cmp     [rax], si
0x18000d63f  jz      short loc_18000D64B
0x18000d641  add     rax, 2
0x18000d645  sub     rdx, 1
0x18000d649  jnz     short loc_18000D63C
0x18000d64b  mov     rax, rdx
0x18000d64e  neg     rax
0x18000d651  sbb     r8d, r8d
0x18000d654  not     r8d
0x18000d657  mov     ebx, 80070057h
0x18000d65c  and     r8d, ebx
0x18000d65f  mov     rax, rdx
0x18000d662  mov     rcx, rdi
0x18000d665  sub     rcx, rdx
0x18000d668  neg     rax
0x18000d66b  sbb     r10, r10
0x18000d66e  and     r10, rcx
0x18000d671  test    rdx, rdx
0x18000d674  jnz     short loc_18000D67E
0x18000d676  mov     ebx, r8d
0x18000d679  jmp     loc_18000D74C
0x18000d67e  test    r10d, r10d
0x18000d681  jz      loc_18000D767
0x18000d687  mov     eax, [rbp+var_10]
0x18000d68a  test    eax, eax
0x18000d68c  jz      short loc_18000D6F6
0x18000d68e  dec     eax
0x18000d690  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x18000d696  jz      short loc_18000D6F6
0x18000d698  mov     rdx, rdi
0x18000d69b  lea     rax, asc_180020AE0; "\\"
0x18000d6a2  cmp     [rax], si
0x18000d6a5  jz      short loc_18000D6B1
0x18000d6a7  add     rax, 2
0x18000d6ab  sub     rdx, 1
0x18000d6af  jnz     short loc_18000D6A2
0x18000d6b1  mov     rax, rdx
0x18000d6b4  neg     rax
0x18000d6b7  sbb     r8d, r8d
0x18000d6ba  not     r8d
0x18000d6bd  and     r8d, ebx
0x18000d6c0  mov     rax, rdx
0x18000d6c3  mov     rcx, rdi
0x18000d6c6  sub     rcx, rdx
0x18000d6c9  neg     rax
0x18000d6cc  sbb     r10, r10
0x18000d6cf  and     r10, rcx
0x18000d6d2  test    rdx, rdx
0x18000d6d5  jz      short loc_18000D676
0x18000d6d7  mov     r8d, r10d; unsigned int
0x18000d6da  lea     rdx, asc_180020AE0; "\\"
0x18000d6e1  lea     rcx, [rbp+var_30]; this
0x18000d6e5  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x18000d6ea  mov     r9, [rbp+lpLibFileName]
0x18000d6ee  test    eax, eax
0x18000d6f0  jns     short loc_18000D6F6
0x18000d6f2  mov     ebx, eax
0x18000d6f4  jmp     short loc_18000D74C
0x18000d6f6  mov     rdx, rdi
0x18000d6f9  lea     rax, aClrDll; "clr.dll"
0x18000d700  cmp     [rax], si
0x18000d703  jz      short loc_18000D70F
0x18000d705  add     rax, 2
0x18000d709  sub     rdx, 1
0x18000d70d  jnz     short loc_18000D700
0x18000d70f  mov     rax, rdx
0x18000d712  neg     rax
0x18000d715  sbb     ecx, ecx
0x18000d717  not     ecx
0x18000d719  and     ebx, ecx
0x18000d71b  mov     rax, rdx
0x18000d71e  sub     rdi, rdx
0x18000d721  neg     rax
0x18000d724  sbb     rcx, rcx
0x18000d727  and     rcx, rdi
0x18000d72a  test    rdx, rdx
0x18000d72d  jz      short loc_18000D74C
0x18000d72f  mov     r8d, ecx; unsigned int
0x18000d732  lea     rdx, aClrDll; "clr.dll"
0x18000d739  lea     rcx, [rbp+var_30]; this
0x18000d73d  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x18000d742  mov     ebx, eax
0x18000d744  mov     r9, [rbp+lpLibFileName]
0x18000d748  test    eax, eax
0x18000d74a  jns     short loc_18000D767
0x18000d74c  mov     [rbp+var_30], r14
0x18000d750  mov     [rbp+var_28], r15
0x18000d754  test    r9, r9
0x18000d757  jz      short loc_18000D762
0x18000d759  mov     rcx, r9; void *
0x18000d75c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d761  nop
0x18000d762  jmp     loc_18000D8C2
0x18000d767  xor     edx, edx; hFile
0x18000d769  lea     r8d, [rdx+8]; dwFlags
0x18000d76d  mov     rcx, r9; lpLibFileName
0x18000d770  call    cs:__imp_LoadLibraryExW
0x18000d776  test    rax, rax
0x18000d779  jnz     short loc_18000D7AF
0x18000d77b  call    cs:__imp_GetLastError
0x18000d781  movzx   ebx, ax
0x18000d784  or      ebx, 80070000h
0x18000d78a  test    eax, eax
0x18000d78c  cmovle  ebx, eax
0x18000d78f  test    ebx, ebx
0x18000d791  jns     short loc_18000D7C5
0x18000d793  mov     [rbp+var_30], r14
0x18000d797  mov     [rbp+var_28], r15
0x18000d79b  mov     rcx, [rbp+lpLibFileName]; void *
0x18000d79f  test    rcx, rcx
0x18000d7a2  jz      short loc_18000D7AA
0x18000d7a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d7a9  nop
0x18000d7aa  jmp     loc_18000D8C2
0x18000d7af  xchg    rax, cs:?_hClr@CSubscription@Dfdll@@1PEAUHINSTANCE__@@EA; HINSTANCE__ * Dfdll::CSubscription::_hClr
0x18000d7b6  test    rax, rax
0x18000d7b9  jz      short loc_18000D7C5
0x18000d7bb  mov     rcx, rax; hLibModule
0x18000d7be  call    cs:__imp_FreeLibrary
0x18000d7c4  nop
0x18000d7c5  mov     [rbp+var_30], r14
0x18000d7c9  mov     [rbp+var_28], r15
0x18000d7cd  mov     rcx, [rbp+lpLibFileName]; void *
0x18000d7d1  test    rcx, rcx
0x18000d7d4  jz      short loc_18000D7DC
0x18000d7d6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d7db  nop
0x18000d7dc  mov     rcx, cs:?_hClr@CSubscription@Dfdll@@1PEAUHINSTANCE__@@EA; hModule
0x18000d7e3  test    rcx, rcx
0x18000d7e6  jz      loc_18000D8B9
0x18000d7ec  cmp     cs:?_pfnGetAppIdAuthority@CSubscription@Dfdll@@1P6AJPEAPEAUIAppIdAuthority@@@ZEA, rsi; long (*Dfdll::CSubscription::_pfnGetAppIdAuthority)(IAppIdAuthority * *)
0x18000d7f3  jz      short loc_18000D814
0x18000d7f5  cmp     cs:?_pfnGetIdentityAuthority@CSubscription@Dfdll@@1P6AJPEAPEAUIIdentityAuthority@@@ZEA, rsi; long (*Dfdll::CSubscription::_pfnGetIdentityAuthority)(IIdentityAuthority * *)
0x18000d7fc  jz      short loc_18000D814
0x18000d7fe  cmp     cs:?_pfnGetUserStore@CSubscription@Dfdll@@1P6AJKPEAXAEBU_GUID@@PEAPEAUIStore@@@ZEA, rsi; long (*Dfdll::CSubscription::_pfnGetUserStore)(ulong,void *,_GUID const &,IStore * *)
0x18000d805  jz      short loc_18000D814
0x18000d807  cmp     cs:?_pfnParseManifest@CSubscription@Dfdll@@1P6AJPEBGPEAUIManifestParseErrorCallback@@AEBU_GUID@@PEAPEAUIUnknown@@@ZEA, rsi; long (*Dfdll::CSubscription::_pfnParseManifest)(ushort const *,IManifestParseErrorCallback *,_GUID const &,IUnknown * *)
0x18000d80e  jnz     loc_18000D8B9
0x18000d814  lea     rdx, aGetappidauthor; "GetAppIdAuthority"
0x18000d81b  call    cs:__imp_GetProcAddress
0x18000d821  mov     rcx, rax
0x18000d824  xor     eax, eax
0x18000d826  lock cmpxchg cs:?_pfnGetAppIdAuthority@CSubscription@Dfdll@@1P6AJPEAPEAUIAppIdAuthority@@@ZEA, rcx; long (*Dfdll::CSubscription::_pfnGetAppIdAuthority)(IAppIdAuthority * *)
0x18000d82f  lea     rdx, aGetidentityaut; "GetIdentityAuthority"
0x18000d836  mov     rcx, cs:?_hClr@CSubscription@Dfdll@@1PEAUHINSTANCE__@@EA; hModule
0x18000d83d  call    cs:__imp_GetProcAddress
0x18000d843  mov     rcx, rax
0x18000d846  xor     eax, eax
0x18000d848  lock cmpxchg cs:?_pfnGetIdentityAuthority@CSubscription@Dfdll@@1P6AJPEAPEAUIIdentityAuthority@@@ZEA, rcx; long (*Dfdll::CSubscription::_pfnGetIdentityAuthority)(IIdentityAuthority * *)
0x18000d851  lea     rdx, aGetuserstore; "GetUserStore"
0x18000d858  mov     rcx, cs:?_hClr@CSubscription@Dfdll@@1PEAUHINSTANCE__@@EA; hModule
0x18000d85f  call    cs:__imp_GetProcAddress
0x18000d865  mov     rcx, rax
0x18000d868  xor     eax, eax
0x18000d86a  lock cmpxchg cs:?_pfnGetUserStore@CSubscription@Dfdll@@1P6AJKPEAXAEBU_GUID@@PEAPEAUIStore@@@ZEA, rcx; long (*Dfdll::CSubscription::_pfnGetUserStore)(ulong,void *,_GUID const &,IStore * *)
0x18000d873  lea     rdx, aParsemanifest; "ParseManifest"
0x18000d87a  mov     rcx, cs:?_hClr@CSubscription@Dfdll@@1PEAUHINSTANCE__@@EA; hModule
0x18000d881  call    cs:__imp_GetProcAddress
0x18000d887  mov     rcx, rax
0x18000d88a  xor     eax, eax
0x18000d88c  lock cmpxchg cs:?_pfnParseManifest@CSubscription@Dfdll@@1P6AJPEBGPEAUIManifestParseErrorCallback@@AEBU_GUID@@PEAPEAUIUnknown@@@ZEA, rcx; long (*Dfdll::CSubscription::_pfnParseManifest)(ushort const *,IManifestParseErrorCallback *,_GUID const &,IUnknown * *)
0x18000d895  cmp     cs:?_pfnGetAppIdAuthority@CSubscription@Dfdll@@1P6AJPEAPEAUIAppIdAuthority@@@ZEA, rsi; long (*Dfdll::CSubscription::_pfnGetAppIdAuthority)(IAppIdAuthority * *)
0x18000d89c  jz      short loc_18000D8BD
0x18000d89e  cmp     cs:?_pfnGetIdentityAuthority@CSubscription@Dfdll@@1P6AJPEAPEAUIIdentityAuthority@@@ZEA, rsi; long (*Dfdll::CSubscription::_pfnGetIdentityAuthority)(IIdentityAuthority * *)
0x18000d8a5  jz      short loc_18000D8BD
0x18000d8a7  cmp     cs:?_pfnGetUserStore@CSubscription@Dfdll@@1P6AJKPEAXAEBU_GUID@@PEAPEAUIStore@@@ZEA, rsi; long (*Dfdll::CSubscription::_pfnGetUserStore)(ulong,void *,_GUID const &,IStore * *)
0x18000d8ae  jz      short loc_18000D8BD
0x18000d8b0  cmp     cs:?_pfnParseManifest@CSubscription@Dfdll@@1P6AJPEBGPEAUIManifestParseErrorCallback@@AEBU_GUID@@PEAPEAUIUnknown@@@ZEA, rsi; long (*Dfdll::CSubscription::_pfnParseManifest)(ushort const *,IManifestParseErrorCallback *,_GUID const &,IUnknown * *)
0x18000d8b7  jz      short loc_18000D8BD
0x18000d8b9  mov     ebx, esi
0x18000d8bb  jmp     short loc_18000D8C2
0x18000d8bd  mov     ebx, 8007007Fh
0x18000d8c2  mov     eax, ebx
0x18000d8c4  lea     r11, [rsp+50h+var_s0]
0x18000d8c9  mov     rbx, [r11+20h]
0x18000d8cd  mov     rsi, [r11+28h]
0x18000d8d1  mov     rdi, [r11+30h]
0x18000d8d5  mov     rsp, r11
0x18000d8d8  pop     r15
0x18000d8da  pop     r14
0x18000d8dc  pop     rbp
0x18000d8dd  retn
```
