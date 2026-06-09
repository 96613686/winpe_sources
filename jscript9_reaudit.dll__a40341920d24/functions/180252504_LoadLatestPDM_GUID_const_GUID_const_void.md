# LoadLatestPDM(_GUID const &,_GUID const &,void * *)

- ea: `0x180252504`
- end: `0x18025277b`
- name: `?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `631`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180111564`
- `0x1801b82e0`
- `0x180218bc0`

## callees

- `0x1801c812c`
- `0x180252240`
- `0x180252304`
- `0x1802523d0`
- `0x180252504`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1802525bc`
- `msvcrt!_wcsicmp` at `0x1802525bc`
- `KERNEL32!LoadLibraryExW` at `0x180252677`
- `KERNEL32!LoadLibraryExW` at `0x180252677`
- `KERNEL32!GetProcAddress` at `0x180252693`
- `KERNEL32!GetProcAddress` at `0x180252693`
- `KERNEL32!GetLastError` at `0x1802526fd`
- `KERNEL32!GetLastError` at `0x1802526fd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180252636`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18025272d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180252636`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18025272d`

## string_xrefs

- `0x180252689`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall LoadLatestPDM(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  int LocalPDMPath; // ebx
  DWORD dwFileVersionMS; // eax
  HRESULT Instance; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  struct tagVS_FIXEDFILEINFO *v13; // [rsp+38h] [rbp-D0h] BYREF
  struct tagVS_FIXEDFILEINFO *v14; // [rsp+40h] [rbp-C8h] BYREF
  void *Block; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int8 *v16; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t String2[264]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t String1[264]; // [rsp+268h] [rbp+160h] BYREF

  v16 = 0;
  Block = 0;
  if ( dword_18043D930 )
  {
    if ( dword_18043D928 )
      goto LABEL_16;
  }
  else
  {
    LocalPDMPath = GetLocalPDMPath(String2);
    if ( LocalPDMPath < 0 )
      return (unsigned int)LocalPDMPath;
    if ( (int)GetRegisterdPDMPath(a1, (BYTE *)String1) < 0 )
      goto LABEL_16;
    if ( _wcsicmp(String1, String2) )
    {
      v13 = 0;
      v14 = 0;
      if ( (int)GetFixedVersionInfo(String2, &v14, (unsigned __int8 **)&Block) < 0 )
        goto LABEL_16;
      if ( (int)GetFixedVersionInfo(String1, &v13, &v16) < 0 )
        goto LABEL_16;
      dwFileVersionMS = v14->dwFileVersionMS;
      if ( dwFileVersionMS > v13->dwFileVersionMS
        || dwFileVersionMS == v13->dwFileVersionMS && v14->dwFileVersionLS > v13->dwFileVersionLS )
      {
        goto LABEL_16;
      }
    }
  }
  Instance = CoCreateInstance(a1, 0, 1u, a2, a3);
  LocalPDMPath = Instance;
  if ( Instance )
  {
    if ( Instance != -2147024319 && Instance != -2147024770 )
      goto LABEL_25;
LABEL_16:
    Library = hModule;
    if ( (hModule || (Library = LoadLibraryExW(String2, 0, 8u), (hModule = Library) != 0))
      && (ProcAddress = GetProcAddress(Library, "DllGetClassObject")) != 0 )
    {
      v13 = 0;
      dword_18043D928 = 1;
      dword_18043D930 = 1;
      LocalPDMPath = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, struct tagVS_FIXEDFILEINFO **))ProcAddress)(
                       a1,
                       &IID_IClassFactory,
                       &v13);
      if ( LocalPDMPath >= 0 )
      {
        LocalPDMPath = (*(__int64 (__fastcall **)(struct tagVS_FIXEDFILEINFO *, _QWORD, const struct _GUID *, void **))(*(_QWORD *)&v13->dwSignature + 24LL))(
                         v13,
                         0,
                         a2,
                         a3);
        (*(void (__fastcall **)(struct tagVS_FIXEDFILEINFO *))(*(_QWORD *)&v13->dwSignature + 16LL))(v13);
      }
    }
    else
    {
      LastError = GetLastError();
      LocalPDMPath = LastError;
      if ( LastError > 0 )
        LocalPDMPath = (unsigned __int16)LastError | 0x80070000;
    }
    if ( LocalPDMPath )
    {
      dword_18043D930 = 1;
      LocalPDMPath = CoCreateInstance(a1, 0, 1u, a2, a3);
    }
    goto LABEL_25;
  }
  dword_18043D930 = 1;
LABEL_25:
  if ( Block )
    operator delete(Block);
  if ( v16 )
    operator delete(v16);
  return (unsigned int)LocalPDMPath;
}

```

## disassembly

```asm
0x180252504  mov     rax, rsp
0x180252507  mov     [rax+20h], rbx
0x18025250b  mov     [rax+18h], r8
0x18025250f  mov     [rax+10h], rdx
0x180252513  mov     [rax+8], rcx
0x180252517  push    rbp
0x180252518  push    rsi
0x180252519  push    rdi
0x18025251a  push    r12
0x18025251c  push    r14
0x18025251e  lea     rbp, [rax-3A8h]
0x180252525  sub     rsp, 480h
0x18025252c  mov     rax, cs:__security_cookie
0x180252533  xor     rax, rsp
0x180252536  mov     [rbp+3A0h+var_30], rax
0x18025253d  cmp     cs:dword_18043D930, 0
0x180252544  mov     r12d, 1
0x18025254a  mov     rdi, [rbp+3A0h+rclsid]
0x180252551  mov     rsi, [rbp+3A0h+riid]
0x180252558  mov     r14, [rbp+3A0h+ppv]
0x18025255f  mov     [rsp+4A0h+var_458], 0
0x180252568  mov     [rsp+4A0h+Block], 0
0x180252571  jz      short loc_180252585
0x180252573  cmp     cs:dword_18043D928, 0
0x18025257a  jnz     loc_180252660
0x180252580  jmp     loc_180252626
0x180252585  lea     rcx, [rsp+4A0h+String2]; pszPathIn
0x18025258a  call    ?GetLocalPDMPath@@YAJPEAGK@Z; GetLocalPDMPath(ushort *,ulong)
0x18025258f  mov     ebx, eax
0x180252591  test    eax, eax
0x180252593  js      loc_180252753
0x180252599  lea     rdx, [rbp+3A0h+String1]; unsigned __int16 *
0x1802525a0  mov     rcx, rdi; struct _GUID *
0x1802525a3  call    ?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z; GetRegisterdPDMPath(_GUID const &,ushort *,ulong)
0x1802525a8  test    eax, eax
0x1802525aa  js      loc_180252660
0x1802525b0  lea     rdx, [rsp+4A0h+String2]; String2
0x1802525b5  lea     rcx, [rbp+3A0h+String1]; String1
0x1802525bc  call    cs:__imp__wcsicmp
0x1802525c2  test    eax, eax
0x1802525c4  jz      short loc_180252626
0x1802525c6  lea     r8, [rsp+4A0h+Block]; unsigned __int8 **
0x1802525cb  mov     [rsp+4A0h+var_470], 0
0x1802525d4  lea     rdx, [rsp+4A0h+var_468]; struct tagVS_FIXEDFILEINFO **
0x1802525d9  mov     [rsp+4A0h+var_468], 0
0x1802525e2  lea     rcx, [rsp+4A0h+String2]; lpwstrFilename
0x1802525e7  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x1802525ec  test    eax, eax
0x1802525ee  js      short loc_180252660
0x1802525f0  lea     r8, [rsp+4A0h+var_458]; unsigned __int8 **
0x1802525f5  lea     rdx, [rsp+4A0h+var_470]; struct tagVS_FIXEDFILEINFO **
0x1802525fa  lea     rcx, [rbp+3A0h+String1]; lpwstrFilename
0x180252601  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x180252606  test    eax, eax
0x180252608  js      short loc_180252660
0x18025260a  mov     rdx, [rsp+4A0h+var_468]
0x18025260f  mov     rcx, [rsp+4A0h+var_470]
0x180252614  mov     eax, [rdx+8]
0x180252617  cmp     eax, [rcx+8]
0x18025261a  ja      short loc_180252660
0x18025261c  jnz     short loc_180252626
0x18025261e  mov     eax, [rcx+0Ch]
0x180252621  cmp     [rdx+0Ch], eax
0x180252624  ja      short loc_180252660
0x180252626  mov     r9, rsi; riid
0x180252629  mov     [rsp+20h], r14; ppv
0x18025262e  mov     r8d, r12d; dwClsContext
0x180252631  xor     edx, edx; pUnkOuter
0x180252633  mov     rcx, rdi; rclsid
0x180252636  call    cs:__imp_CoCreateInstance
0x18025263c  mov     ebx, eax
0x18025263e  test    eax, eax
0x180252640  jnz     short loc_18025264E
0x180252642  mov     cs:dword_18043D930, r12d
0x180252649  jmp     loc_180252735
0x18025264e  cmp     eax, 80070241h
0x180252653  jz      short loc_180252660
0x180252655  cmp     eax, 8007007Eh
0x18025265a  jnz     loc_180252735
0x180252660  mov     rax, cs:hModule
0x180252667  test    rax, rax
0x18025266a  jnz     short loc_180252689
0x18025266c  xor     edx, edx; hFile
0x18025266e  lea     r8d, [rax+8]; dwFlags
0x180252672  lea     rcx, [rsp+4A0h+String2]; lpLibFileName
0x180252677  call    cs:__imp_LoadLibraryExW
0x18025267d  mov     cs:hModule, rax
0x180252684  test    rax, rax
0x180252687  jz      short loc_1802526FD
0x180252689  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180252690  mov     rcx, rax; hModule
0x180252693  call    cs:__imp_GetProcAddress
0x180252699  test    rax, rax
0x18025269c  jz      short loc_1802526FD
0x18025269e  lea     r8, [rsp+4A0h+var_470]
0x1802526a3  mov     [rsp+4A0h+var_470], 0
0x1802526ac  lea     rdx, IID_IClassFactory
0x1802526b3  mov     cs:dword_18043D928, r12d
0x1802526ba  mov     rcx, rdi
0x1802526bd  mov     cs:dword_18043D930, r12d
0x1802526c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802526c9  mov     ebx, eax
0x1802526cb  test    eax, eax
0x1802526cd  js      short loc_180252712
0x1802526cf  mov     rcx, [rsp+4A0h+var_470]
0x1802526d4  mov     r9, r14
0x1802526d7  mov     r8, rsi
0x1802526da  xor     edx, edx
0x1802526dc  mov     rax, [rcx]
0x1802526df  mov     rax, [rax+18h]
0x1802526e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802526e8  mov     rcx, [rsp+4A0h+var_470]
0x1802526ed  mov     ebx, eax
0x1802526ef  mov     rax, [rcx]
0x1802526f2  mov     rax, [rax+10h]
0x1802526f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802526fb  jmp     short loc_180252712
0x1802526fd  call    cs:__imp_GetLastError
0x180252703  mov     ebx, eax
0x180252705  test    eax, eax
0x180252707  jle     short loc_180252712
0x180252709  movzx   ebx, ax
0x18025270c  or      ebx, 80070000h
0x180252712  test    ebx, ebx
0x180252714  jz      short loc_180252735
0x180252716  mov     r9, rsi; riid
0x180252719  mov     cs:dword_18043D930, r12d
0x180252720  mov     r8d, r12d; dwClsContext
0x180252723  mov     [rsp+20h], r14; ppv
0x180252728  xor     edx, edx; pUnkOuter
0x18025272a  mov     rcx, rdi; rclsid
0x18025272d  call    cs:__imp_CoCreateInstance
0x180252733  mov     ebx, eax
0x180252735  mov     rcx, [rsp+4A0h+Block]; Block
0x18025273a  test    rcx, rcx
0x18025273d  jz      short loc_180252744
0x18025273f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180252744  mov     rcx, [rsp+4A0h+var_458]; Block
0x180252749  test    rcx, rcx
0x18025274c  jz      short loc_180252753
0x18025274e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180252753  mov     eax, ebx
0x180252755  mov     rcx, [rbp+3A0h+var_30]
0x18025275c  xor     rcx, rsp; StackCookie
0x18025275f  call    __security_check_cookie
0x180252764  mov     rbx, [rsp+4A0h+arg_18]
0x18025276c  add     rsp, 480h
0x180252773  pop     r14
0x180252775  pop     r12
0x180252777  pop     rdi
0x180252778  pop     rsi
0x180252779  pop     rbp
0x18025277a  retn
```
