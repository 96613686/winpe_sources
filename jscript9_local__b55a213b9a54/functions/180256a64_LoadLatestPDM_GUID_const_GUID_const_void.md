# LoadLatestPDM(_GUID const &,_GUID const &,void * *)

- ea: `0x180256a64`
- end: `0x180256d00`
- name: `?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `668`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180135cd0`
- `0x1801baa64`
- `0x18021c4e8`

## callees

- `0x1801caacc`
- `0x180256740`
- `0x180256820`
- `0x180256910`
- `0x180256a64`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180256b1c`
- `msvcrt!_wcsicmp` at `0x180256b1c`
- `KERNEL32!LoadLibraryExW` at `0x180256be3`
- `KERNEL32!LoadLibraryExW` at `0x180256be3`
- `KERNEL32!GetProcAddress` at `0x180256c05`
- `KERNEL32!GetProcAddress` at `0x180256c05`
- `KERNEL32!GetLastError` at `0x180256c75`
- `KERNEL32!GetLastError` at `0x180256c75`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180256b9c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180256cab`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180256b9c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x180256cab`

## string_xrefs

- `0x180256bfb`: `DllGetClassObject`

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
  if ( dword_180443930 )
  {
    if ( dword_180443928 )
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
    Library = hLibModule;
    if ( (hLibModule || (Library = LoadLibraryExW(String2, 0, 8u), (hLibModule = Library) != 0))
      && (ProcAddress = GetProcAddress(Library, "DllGetClassObject")) != 0 )
    {
      v13 = 0;
      dword_180443928 = 1;
      dword_180443930 = 1;
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
      dword_180443930 = 1;
      LocalPDMPath = CoCreateInstance(a1, 0, 1u, a2, a3);
    }
    goto LABEL_25;
  }
  dword_180443930 = 1;
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
0x180256a64  mov     rax, rsp
0x180256a67  mov     [rax+20h], rbx
0x180256a6b  mov     [rax+18h], r8
0x180256a6f  mov     [rax+10h], rdx
0x180256a73  mov     [rax+8], rcx
0x180256a77  push    rbp
0x180256a78  push    rsi
0x180256a79  push    rdi
0x180256a7a  push    r12
0x180256a7c  push    r14
0x180256a7e  lea     rbp, [rax-3A8h]
0x180256a85  sub     rsp, 480h
0x180256a8c  mov     rax, cs:__security_cookie
0x180256a93  xor     rax, rsp
0x180256a96  mov     [rbp+3A0h+var_30], rax
0x180256a9d  cmp     cs:dword_180443930, 0
0x180256aa4  mov     r12d, 1
0x180256aaa  mov     rdi, [rbp+3A0h+rclsid]
0x180256ab1  mov     rsi, [rbp+3A0h+riid]
0x180256ab8  mov     r14, [rbp+3A0h+ppv]
0x180256abf  mov     [rsp+4A0h+var_458], 0
0x180256ac8  mov     [rsp+4A0h+Block], 0
0x180256ad1  jz      short loc_180256AE5
0x180256ad3  cmp     cs:dword_180443928, 0
0x180256ada  jnz     loc_180256BCC
0x180256ae0  jmp     loc_180256B8C
0x180256ae5  lea     rcx, [rsp+4A0h+String2]; pszPathIn
0x180256aea  call    ?GetLocalPDMPath@@YAJPEAGK@Z; GetLocalPDMPath(ushort *,ulong)
0x180256aef  mov     ebx, eax
0x180256af1  test    eax, eax
0x180256af3  js      loc_180256CD7
0x180256af9  lea     rdx, [rbp+3A0h+String1]; unsigned __int16 *
0x180256b00  mov     rcx, rdi; struct _GUID *
0x180256b03  call    ?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z; GetRegisterdPDMPath(_GUID const &,ushort *,ulong)
0x180256b08  test    eax, eax
0x180256b0a  js      loc_180256BCC
0x180256b10  lea     rdx, [rsp+4A0h+String2]; String2
0x180256b15  lea     rcx, [rbp+3A0h+String1]; String1
0x180256b1c  call    cs:__imp__wcsicmp
0x180256b23  nop     dword ptr [rax+rax+00h]
0x180256b28  test    eax, eax
0x180256b2a  jz      short loc_180256B8C
0x180256b2c  lea     r8, [rsp+4A0h+Block]; unsigned __int8 **
0x180256b31  mov     [rsp+4A0h+var_470], 0
0x180256b3a  lea     rdx, [rsp+4A0h+var_468]; struct tagVS_FIXEDFILEINFO **
0x180256b3f  mov     [rsp+4A0h+var_468], 0
0x180256b48  lea     rcx, [rsp+4A0h+String2]; lpwstrFilename
0x180256b4d  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x180256b52  test    eax, eax
0x180256b54  js      short loc_180256BCC
0x180256b56  lea     r8, [rsp+4A0h+var_458]; unsigned __int8 **
0x180256b5b  lea     rdx, [rsp+4A0h+var_470]; struct tagVS_FIXEDFILEINFO **
0x180256b60  lea     rcx, [rbp+3A0h+String1]; lpwstrFilename
0x180256b67  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x180256b6c  test    eax, eax
0x180256b6e  js      short loc_180256BCC
0x180256b70  mov     rdx, [rsp+4A0h+var_468]
0x180256b75  mov     rcx, [rsp+4A0h+var_470]
0x180256b7a  mov     eax, [rdx+8]
0x180256b7d  cmp     eax, [rcx+8]
0x180256b80  ja      short loc_180256BCC
0x180256b82  jnz     short loc_180256B8C
0x180256b84  mov     eax, [rcx+0Ch]
0x180256b87  cmp     [rdx+0Ch], eax
0x180256b8a  ja      short loc_180256BCC
0x180256b8c  mov     r9, rsi; riid
0x180256b8f  mov     [rsp+20h], r14; ppv
0x180256b94  mov     r8d, r12d; dwClsContext
0x180256b97  xor     edx, edx; pUnkOuter
0x180256b99  mov     rcx, rdi; rclsid
0x180256b9c  call    cs:__imp_CoCreateInstance
0x180256ba3  nop     dword ptr [rax+rax+00h]
0x180256ba8  mov     ebx, eax
0x180256baa  test    eax, eax
0x180256bac  jnz     short loc_180256BBA
0x180256bae  mov     cs:dword_180443930, r12d
0x180256bb5  jmp     loc_180256CB9
0x180256bba  cmp     eax, 80070241h
0x180256bbf  jz      short loc_180256BCC
0x180256bc1  cmp     eax, 8007007Eh
0x180256bc6  jnz     loc_180256CB9
0x180256bcc  mov     rax, cs:hLibModule
0x180256bd3  test    rax, rax
0x180256bd6  jnz     short loc_180256BFB
0x180256bd8  xor     edx, edx; hFile
0x180256bda  lea     r8d, [rax+8]; dwFlags
0x180256bde  lea     rcx, [rsp+4A0h+String2]; lpLibFileName
0x180256be3  call    cs:__imp_LoadLibraryExW
0x180256bea  nop     dword ptr [rax+rax+00h]
0x180256bef  mov     cs:hLibModule, rax
0x180256bf6  test    rax, rax
0x180256bf9  jz      short loc_180256C75
0x180256bfb  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180256c02  mov     rcx, rax; hModule
0x180256c05  call    cs:__imp_GetProcAddress
0x180256c0c  nop     dword ptr [rax+rax+00h]
0x180256c11  test    rax, rax
0x180256c14  jz      short loc_180256C75
0x180256c16  lea     r8, [rsp+4A0h+var_470]
0x180256c1b  mov     [rsp+4A0h+var_470], 0
0x180256c24  lea     rdx, IID_IClassFactory
0x180256c2b  mov     cs:dword_180443928, r12d
0x180256c32  mov     rcx, rdi
0x180256c35  mov     cs:dword_180443930, r12d
0x180256c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180256c41  mov     ebx, eax
0x180256c43  test    eax, eax
0x180256c45  js      short loc_180256C90
0x180256c47  mov     rcx, [rsp+4A0h+var_470]
0x180256c4c  mov     r9, r14
0x180256c4f  mov     r8, rsi
0x180256c52  xor     edx, edx
0x180256c54  mov     rax, [rcx]
0x180256c57  mov     rax, [rax+18h]
0x180256c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180256c60  mov     rcx, [rsp+4A0h+var_470]
0x180256c65  mov     ebx, eax
0x180256c67  mov     rax, [rcx]
0x180256c6a  mov     rax, [rax+10h]
0x180256c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180256c73  jmp     short loc_180256C90
0x180256c75  call    cs:__imp_GetLastError
0x180256c7c  nop     dword ptr [rax+rax+00h]
0x180256c81  mov     ebx, eax
0x180256c83  test    eax, eax
0x180256c85  jle     short loc_180256C90
0x180256c87  movzx   ebx, ax
0x180256c8a  or      ebx, 80070000h
0x180256c90  test    ebx, ebx
0x180256c92  jz      short loc_180256CB9
0x180256c94  mov     r9, rsi; riid
0x180256c97  mov     cs:dword_180443930, r12d
0x180256c9e  mov     r8d, r12d; dwClsContext
0x180256ca1  mov     [rsp+20h], r14; ppv
0x180256ca6  xor     edx, edx; pUnkOuter
0x180256ca8  mov     rcx, rdi; rclsid
0x180256cab  call    cs:__imp_CoCreateInstance
0x180256cb2  nop     dword ptr [rax+rax+00h]
0x180256cb7  mov     ebx, eax
0x180256cb9  mov     rcx, [rsp+4A0h+Block]; Block
0x180256cbe  test    rcx, rcx
0x180256cc1  jz      short loc_180256CC8
0x180256cc3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180256cc8  mov     rcx, [rsp+4A0h+var_458]; Block
0x180256ccd  test    rcx, rcx
0x180256cd0  jz      short loc_180256CD7
0x180256cd2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180256cd7  mov     eax, ebx
0x180256cd9  mov     rcx, [rbp+3A0h+var_30]
0x180256ce0  xor     rcx, rsp; StackCookie
0x180256ce3  call    __security_check_cookie
0x180256ce8  mov     rbx, [rsp+4A0h+arg_18]
0x180256cf0  add     rsp, 480h
0x180256cf7  pop     r14
0x180256cf9  pop     r12
0x180256cfb  pop     rdi
0x180256cfc  pop     rsi
0x180256cfd  pop     rbp
0x180256cfe  retn
```
