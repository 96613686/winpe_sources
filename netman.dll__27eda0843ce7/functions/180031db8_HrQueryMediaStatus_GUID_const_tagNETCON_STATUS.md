# HrQueryMediaStatus(_GUID const &,tagNETCON_STATUS &)

- ea: `0x180031db8`
- end: `0x180031f28`
- name: `?HrQueryMediaStatus@@YAJAEBU_GUID@@AEAW4tagNETCON_STATUS@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(const struct _GUID *, enum tagNETCON_STATUS *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020020`
- `0x180024db0`

## callees

- `0x180019c9c`
- `0x18002fe40`
- `0x180030434`
- `0x18003060c`
- `0x180031db8`
- `0x180036010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180031eea`
- `ADVAPI32!RegCloseKey` at `0x180031eea`
- `KERNEL32!FreeLibrary` at `0x180031e9d`
- `KERNEL32!FreeLibrary` at `0x180031eca`
- `KERNEL32!FreeLibrary` at `0x180031e9d`
- `KERNEL32!FreeLibrary` at `0x180031eca`
- `KERNEL32!LoadLibraryExW` at `0x180031e6a`
- `KERNEL32!LoadLibraryExW` at `0x180031e6a`
- `KERNEL32!GetProcAddress` at `0x180031e85`
- `KERNEL32!GetProcAddress` at `0x180031e85`

## pseudocode

```c
__int64 __fastcall HrQueryMediaStatus(const struct _GUID *a1, enum tagNETCON_STATUS *a2)
{
  int ValueWithAlloc; // ebx
  WCHAR *v5; // rsi
  const WCHAR *i; // rdi
  HMODULE Library; // rax
  FARPROC ProcAddress; // r15
  HMODULE v9; // r14
  __int64 v11; // rax
  unsigned int v12; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-1Ch] BYREF
  void *lpMem; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  ValueWithAlloc = HrRegOpenKeyEx(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Network\\Media", 0x20019u, &hKey);
  if ( ValueWithAlloc < 0 )
    return (unsigned int)ValueWithAlloc;
  v13 = 0;
  lpMem = 0;
  v12 = 0;
  ValueWithAlloc = HrRegGetValueWithAlloc(hKey, L"MediaManager", &v13, (unsigned __int8 **)&lpMem, &v12);
  if ( ValueWithAlloc )
    goto LABEL_5;
  if ( v13 != 7 )
  {
    MemFree(lpMem);
    ValueWithAlloc = -2147023092;
LABEL_5:
    v5 = 0;
    if ( ValueWithAlloc < 0 )
      goto LABEL_17;
    goto LABEL_6;
  }
  v5 = (WCHAR *)lpMem;
LABEL_6:
  v12 = 0;
  for ( i = v5; *i; i += v11 + 1 )
  {
    Library = LoadLibraryExW(i, 0, 0);
    ProcAddress = 0;
    v9 = Library;
    if ( !Library )
    {
      ValueWithAlloc = HrFromLastWin32Error();
LABEL_13:
      if ( ValueWithAlloc < 0 )
        goto LABEL_19;
      goto LABEL_14;
    }
    ProcAddress = GetProcAddress(Library, "QueryNetconStatus");
    if ( !ProcAddress )
    {
      ValueWithAlloc = HrFromLastWin32Error();
      FreeLibrary(v9);
      goto LABEL_13;
    }
LABEL_14:
    ValueWithAlloc = ((__int64 (__fastcall *)(const struct _GUID *, unsigned int *))ProcAddress)(a1, &v12);
    FreeLibrary(v9);
    if ( !ValueWithAlloc )
    {
      *a2 = v12;
      break;
    }
LABEL_19:
    v11 = -1;
    do
      ++v11;
    while ( i[v11] );
  }
  MemFree(v5);
LABEL_17:
  RegCloseKey(hKey);
  return (unsigned int)ValueWithAlloc;
}

```

## disassembly

```asm
0x180031db8  mov     [rsp-38h+arg_10], rbx
0x180031dbd  push    rbp
0x180031dbe  push    rsi
0x180031dbf  push    rdi
0x180031dc0  push    r12
0x180031dc2  push    r13
0x180031dc4  push    r14
0x180031dc6  push    r15
0x180031dc8  mov     rbp, rsp
0x180031dcb  sub     rsp, 50h
0x180031dcf  mov     r12, rdx
0x180031dd2  lea     r9, [rbp+hKey]; HKEY *
0x180031dd6  mov     r13, rcx
0x180031dd9  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Network\\Media"
0x180031de0  xor     r14d, r14d
0x180031de3  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180031dea  mov     r8d, 20019h; unsigned int
0x180031df0  mov     [rbp+hKey], r14
0x180031df4  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180031df9  mov     ebx, eax
0x180031dfb  test    eax, eax
0x180031dfd  js      loc_180031EF0
0x180031e03  mov     rcx, [rbp+hKey]; HKEY
0x180031e07  lea     rax, [rbp+var_20]
0x180031e0b  lea     r9, [rbp+lpMem]; unsigned __int8 **
0x180031e0f  mov     [rsp+50h+var_30], rax; unsigned int *
0x180031e14  lea     r8, [rbp+var_1C]; unsigned int *
0x180031e18  mov     [rbp+var_1C], r14d
0x180031e1c  lea     rdx, aMediamanager; "MediaManager"
0x180031e23  mov     [rbp+lpMem], r14
0x180031e27  mov     [rbp+var_20], r14d
0x180031e2b  call    ?HrRegGetValueWithAlloc@@YAJPEAUHKEY__@@PEBGPEAKPEAPEAE2@Z; HrRegGetValueWithAlloc(HKEY__ *,ushort const *,ulong *,uchar * *,ulong *)
0x180031e30  mov     ebx, eax
0x180031e32  test    eax, eax
0x180031e34  jnz     short loc_180031E4A
0x180031e36  cmp     [rbp+var_1C], 7
0x180031e3a  jz      short loc_180031EA5
0x180031e3c  mov     rcx, [rbp+lpMem]; lpMem
0x180031e40  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180031e45  mov     ebx, 8007070Ch
0x180031e4a  mov     rsi, r14
0x180031e4d  test    ebx, ebx
0x180031e4f  js      loc_180031EE6
0x180031e55  mov     [rbp+var_20], r14d
0x180031e59  mov     rdi, rsi
0x180031e5c  cmp     [rdi], r14w
0x180031e60  jz      short loc_180031EDE
0x180031e62  xor     r8d, r8d; dwFlags
0x180031e65  xor     edx, edx; hFile
0x180031e67  mov     rcx, rdi; lpLibFileName
0x180031e6a  call    cs:__imp_LoadLibraryExW
0x180031e70  xor     r15d, r15d
0x180031e73  mov     r14, rax
0x180031e76  test    rax, rax
0x180031e79  jz      short loc_180031EAB
0x180031e7b  lea     rdx, aQuerynetconsta; "QueryNetconStatus"
0x180031e82  mov     rcx, rax; hModule
0x180031e85  call    cs:__imp_GetProcAddress
0x180031e8b  mov     r15, rax
0x180031e8e  test    rax, rax
0x180031e91  jnz     short loc_180031EB6
0x180031e93  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031e98  mov     rcx, r14; hLibModule
0x180031e9b  mov     ebx, eax
0x180031e9d  call    cs:__imp_FreeLibrary
0x180031ea3  jmp     short loc_180031EB2
0x180031ea5  mov     rsi, [rbp+lpMem]
0x180031ea9  jmp     short loc_180031E55
0x180031eab  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031eb0  mov     ebx, eax
0x180031eb2  test    ebx, ebx
0x180031eb4  js      short loc_180031F0A
0x180031eb6  lea     rdx, [rbp+var_20]
0x180031eba  mov     rcx, r13
0x180031ebd  mov     rax, r15
0x180031ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ec5  mov     rcx, r14; hLibModule
0x180031ec8  mov     ebx, eax
0x180031eca  call    cs:__imp_FreeLibrary
0x180031ed0  xor     r14d, r14d
0x180031ed3  test    ebx, ebx
0x180031ed5  jnz     short loc_180031F0D
0x180031ed7  mov     eax, [rbp+var_20]
0x180031eda  mov     [r12], eax
0x180031ede  mov     rcx, rsi; lpMem
0x180031ee1  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180031ee6  mov     rcx, [rbp+hKey]; hKey
0x180031eea  call    cs:__imp_RegCloseKey
0x180031ef0  mov     eax, ebx
0x180031ef2  mov     rbx, [rsp+50h+arg_10]
0x180031efa  add     rsp, 50h
0x180031efe  pop     r15
0x180031f00  pop     r14
0x180031f02  pop     r13
0x180031f04  pop     r12
0x180031f06  pop     rdi
0x180031f07  pop     rsi
0x180031f08  pop     rbp
0x180031f09  retn
0x180031f0a  xor     r14d, r14d
0x180031f0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031f11  inc     rax
0x180031f14  cmp     [rdi+rax*2], r14w
0x180031f19  jnz     short loc_180031F11
0x180031f1b  lea     rdi, [rdi+rax*2]
0x180031f1f  add     rdi, 2
0x180031f23  jmp     loc_180031E5C
```
