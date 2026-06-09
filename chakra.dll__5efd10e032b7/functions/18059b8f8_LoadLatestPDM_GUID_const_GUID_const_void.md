# LoadLatestPDM(_GUID const &,_GUID const &,void * *)

- ea: `0x18059b8f8`
- end: `0x18059bb94`
- name: `?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `668`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18041ff30`
- `0x180420748`
- `0x18043ce30`

## callees

- `0x180308fb8`
- `0x18059b5d4`
- `0x18059b6b4`
- `0x18059b7a4`
- `0x18059b8f8`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18059b9b0`
- `msvcrt!_wcsicmp` at `0x18059b9b0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18059ba77`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18059ba77`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18059ba99`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18059ba99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059bb09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059bb09`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18059ba30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18059bb3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18059ba30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18059bb3f`

## string_xrefs

- `0x18059ba8f`: `DllGetClassObject`

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
  unsigned __int8 *v15; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int8 *v16; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t String2[264]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t String1[264]; // [rsp+268h] [rbp+160h] BYREF

  v16 = 0;
  v15 = 0;
  if ( dword_180740E38 )
  {
    if ( dword_180740E30 )
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
      if ( (int)GetFixedVersionInfo(String2, &v14, &v15) < 0 )
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
    Library = hLibModule;
    if ( (hLibModule || (Library = LoadLibraryExW(String2, 0, 8u), (hLibModule = Library) != 0))
      && (ProcAddress = GetProcAddress(Library, "DllGetClassObject")) != 0 )
    {
      v13 = 0;
      dword_180740E30 = 1;
      dword_180740E38 = 1;
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
      dword_180740E38 = 1;
      LocalPDMPath = CoCreateInstance(a1, 0, 1u, a2, a3);
    }
    goto LABEL_25;
  }
  dword_180740E38 = 1;
LABEL_25:
  if ( v15 )
    operator delete(v15);
  if ( v16 )
    operator delete(v16);
  return (unsigned int)LocalPDMPath;
}

```

## disassembly

```asm
0x18059b8f8  mov     rax, rsp
0x18059b8fb  mov     [rax+20h], rbx
0x18059b8ff  mov     [rax+18h], r8
0x18059b903  mov     [rax+10h], rdx
0x18059b907  mov     [rax+8], rcx
0x18059b90b  push    rbp
0x18059b90c  push    rsi
0x18059b90d  push    rdi
0x18059b90e  push    r12
0x18059b910  push    r14
0x18059b912  lea     rbp, [rax-3A8h]
0x18059b919  sub     rsp, 480h
0x18059b920  mov     rax, cs:__security_cookie
0x18059b927  xor     rax, rsp
0x18059b92a  mov     [rbp+3A0h+var_30], rax
0x18059b931  cmp     cs:dword_180740E38, 0
0x18059b938  mov     r12d, 1
0x18059b93e  mov     rdi, [rbp+3A0h+rclsid]
0x18059b945  mov     rsi, [rbp+3A0h+riid]
0x18059b94c  mov     r14, [rbp+3A0h+ppv]
0x18059b953  mov     [rsp+4A0h+var_458], 0
0x18059b95c  mov     [rsp+4A0h+var_460], 0
0x18059b965  jz      short loc_18059B979
0x18059b967  cmp     cs:dword_180740E30, 0
0x18059b96e  jnz     loc_18059BA60
0x18059b974  jmp     loc_18059BA20
0x18059b979  lea     rcx, [rsp+4A0h+String2]; pszPath
0x18059b97e  call    ?GetLocalPDMPath@@YAJPEAGK@Z; GetLocalPDMPath(ushort *,ulong)
0x18059b983  mov     ebx, eax
0x18059b985  test    eax, eax
0x18059b987  js      loc_18059BB6B
0x18059b98d  lea     rdx, [rbp+3A0h+String1]; unsigned __int16 *
0x18059b994  mov     rcx, rdi; struct _GUID *
0x18059b997  call    ?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z; GetRegisterdPDMPath(_GUID const &,ushort *,ulong)
0x18059b99c  test    eax, eax
0x18059b99e  js      loc_18059BA60
0x18059b9a4  lea     rdx, [rsp+4A0h+String2]; String2
0x18059b9a9  lea     rcx, [rbp+3A0h+String1]; String1
0x18059b9b0  call    cs:__imp__wcsicmp
0x18059b9b7  nop     dword ptr [rax+rax+00h]
0x18059b9bc  test    eax, eax
0x18059b9be  jz      short loc_18059BA20
0x18059b9c0  lea     r8, [rsp+4A0h+var_460]; unsigned __int8 **
0x18059b9c5  mov     [rsp+4A0h+var_470], 0
0x18059b9ce  lea     rdx, [rsp+4A0h+var_468]; struct tagVS_FIXEDFILEINFO **
0x18059b9d3  mov     [rsp+4A0h+var_468], 0
0x18059b9dc  lea     rcx, [rsp+4A0h+String2]; lpwstrFilename
0x18059b9e1  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x18059b9e6  test    eax, eax
0x18059b9e8  js      short loc_18059BA60
0x18059b9ea  lea     r8, [rsp+4A0h+var_458]; unsigned __int8 **
0x18059b9ef  lea     rdx, [rsp+4A0h+var_470]; struct tagVS_FIXEDFILEINFO **
0x18059b9f4  lea     rcx, [rbp+3A0h+String1]; lpwstrFilename
0x18059b9fb  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x18059ba00  test    eax, eax
0x18059ba02  js      short loc_18059BA60
0x18059ba04  mov     rdx, [rsp+4A0h+var_468]
0x18059ba09  mov     rcx, [rsp+4A0h+var_470]
0x18059ba0e  mov     eax, [rdx+8]
0x18059ba11  cmp     eax, [rcx+8]
0x18059ba14  ja      short loc_18059BA60
0x18059ba16  jnz     short loc_18059BA20
0x18059ba18  mov     eax, [rcx+0Ch]
0x18059ba1b  cmp     [rdx+0Ch], eax
0x18059ba1e  ja      short loc_18059BA60
0x18059ba20  mov     r9, rsi; riid
0x18059ba23  mov     [rsp+20h], r14; ppv
0x18059ba28  mov     r8d, r12d; dwClsContext
0x18059ba2b  xor     edx, edx; pUnkOuter
0x18059ba2d  mov     rcx, rdi; rclsid
0x18059ba30  call    cs:__imp_CoCreateInstance
0x18059ba37  nop     dword ptr [rax+rax+00h]
0x18059ba3c  mov     ebx, eax
0x18059ba3e  test    eax, eax
0x18059ba40  jnz     short loc_18059BA4E
0x18059ba42  mov     cs:dword_180740E38, r12d
0x18059ba49  jmp     loc_18059BB4D
0x18059ba4e  cmp     eax, 80070241h
0x18059ba53  jz      short loc_18059BA60
0x18059ba55  cmp     eax, 8007007Eh
0x18059ba5a  jnz     loc_18059BB4D
0x18059ba60  mov     rax, cs:hLibModule
0x18059ba67  test    rax, rax
0x18059ba6a  jnz     short loc_18059BA8F
0x18059ba6c  xor     edx, edx; hFile
0x18059ba6e  lea     r8d, [rax+8]; dwFlags
0x18059ba72  lea     rcx, [rsp+4A0h+String2]; lpLibFileName
0x18059ba77  call    cs:__imp_LoadLibraryExW
0x18059ba7e  nop     dword ptr [rax+rax+00h]
0x18059ba83  mov     cs:hLibModule, rax
0x18059ba8a  test    rax, rax
0x18059ba8d  jz      short loc_18059BB09
0x18059ba8f  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18059ba96  mov     rcx, rax; hModule
0x18059ba99  call    cs:__imp_GetProcAddress
0x18059baa0  nop     dword ptr [rax+rax+00h]
0x18059baa5  test    rax, rax
0x18059baa8  jz      short loc_18059BB09
0x18059baaa  lea     r8, [rsp+4A0h+var_470]
0x18059baaf  mov     [rsp+4A0h+var_470], 0
0x18059bab8  lea     rdx, IID_IClassFactory
0x18059babf  mov     cs:dword_180740E30, r12d
0x18059bac6  mov     rcx, rdi
0x18059bac9  mov     cs:dword_180740E38, r12d
0x18059bad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059bad5  mov     ebx, eax
0x18059bad7  test    eax, eax
0x18059bad9  js      short loc_18059BB24
0x18059badb  mov     rcx, [rsp+4A0h+var_470]
0x18059bae0  mov     r9, r14
0x18059bae3  mov     r8, rsi
0x18059bae6  xor     edx, edx
0x18059bae8  mov     rax, [rcx]
0x18059baeb  mov     rax, [rax+18h]
0x18059baef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059baf4  mov     rcx, [rsp+4A0h+var_470]
0x18059baf9  mov     ebx, eax
0x18059bafb  mov     rax, [rcx]
0x18059bafe  mov     rax, [rax+10h]
0x18059bb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059bb07  jmp     short loc_18059BB24
0x18059bb09  call    cs:__imp_GetLastError
0x18059bb10  nop     dword ptr [rax+rax+00h]
0x18059bb15  mov     ebx, eax
0x18059bb17  test    eax, eax
0x18059bb19  jle     short loc_18059BB24
0x18059bb1b  movzx   ebx, ax
0x18059bb1e  or      ebx, 80070000h
0x18059bb24  test    ebx, ebx
0x18059bb26  jz      short loc_18059BB4D
0x18059bb28  mov     r9, rsi; riid
0x18059bb2b  mov     cs:dword_180740E38, r12d
0x18059bb32  mov     r8d, r12d; dwClsContext
0x18059bb35  mov     [rsp+20h], r14; ppv
0x18059bb3a  xor     edx, edx; pUnkOuter
0x18059bb3c  mov     rcx, rdi; rclsid
0x18059bb3f  call    cs:__imp_CoCreateInstance
0x18059bb46  nop     dword ptr [rax+rax+00h]
0x18059bb4b  mov     ebx, eax
0x18059bb4d  mov     rcx, [rsp+4A0h+var_460]; void *
0x18059bb52  test    rcx, rcx
0x18059bb55  jz      short loc_18059BB5C
0x18059bb57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18059bb5c  mov     rcx, [rsp+4A0h+var_458]; void *
0x18059bb61  test    rcx, rcx
0x18059bb64  jz      short loc_18059BB6B
0x18059bb66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18059bb6b  mov     eax, ebx
0x18059bb6d  mov     rcx, [rbp+3A0h+var_30]
0x18059bb74  xor     rcx, rsp; StackCookie
0x18059bb77  call    __security_check_cookie
0x18059bb7c  mov     rbx, [rsp+4A0h+arg_18]
0x18059bb84  add     rsp, 480h
0x18059bb8b  pop     r14
0x18059bb8d  pop     r12
0x18059bb8f  pop     rdi
0x18059bb90  pop     rsi
0x18059bb91  pop     rbp
0x18059bb92  retn
```
