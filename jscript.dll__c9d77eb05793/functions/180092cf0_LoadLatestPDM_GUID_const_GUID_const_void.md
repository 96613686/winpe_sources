# LoadLatestPDM(_GUID const &,_GUID const &,void * *)

- ea: `0x180092cf0`
- end: `0x180092f4d`
- name: `?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `605`
- prototype: `__int64 __fastcall(const struct _GUID *, IID *riid, LPVOID *ppv)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180003ff0`
- `0x18007857c`

## callees

- `0x180057694`
- `0x1800582fd`
- `0x180092a5c`
- `0x180092b10`
- `0x180092bd4`
- `0x180092cf0`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180092e49`
- `KERNEL32!LoadLibraryExW` at `0x180092e49`
- `KERNEL32!GetLastError` at `0x180092ecf`
- `KERNEL32!GetLastError` at `0x180092ecf`
- `KERNEL32!GetProcAddress` at `0x180092e65`
- `KERNEL32!GetProcAddress` at `0x180092e65`
- `ole32!CoCreateInstance` at `0x180092e08`
- `ole32!CoCreateInstance` at `0x180092eff`
- `ole32!CoCreateInstance` at `0x180092e08`
- `ole32!CoCreateInstance` at `0x180092eff`

## string_xrefs

- `0x180092e5b`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall LoadLatestPDM(const struct _GUID *a1, IID *riid, LPVOID *ppv)
{
  int LocalPDMPath; // ebx
  unsigned int v7; // eax
  HRESULT Instance; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  LPVOID v13; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v16; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t String2[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String1[264]; // [rsp+260h] [rbp+160h] BYREF

  v16 = 0;
  Block = 0;
  if ( dword_1800B6FA0 )
  {
    if ( dword_1800B6F9C )
      goto LABEL_16;
  }
  else
  {
    LocalPDMPath = GetLocalPDMPath(String2);
    if ( LocalPDMPath < 0 )
      return (unsigned int)LocalPDMPath;
    if ( (int)GetRegisterdPDMPath(a1, (BYTE *)String1) < 0 )
      goto LABEL_16;
    if ( wcsicmp_0(String1, String2) )
    {
      v13 = 0;
      lpBuffer = 0;
      if ( (int)GetFixedVersionInfo(String2, &lpBuffer, (unsigned __int8 **)&Block) < 0 )
        goto LABEL_16;
      if ( (int)GetFixedVersionInfo(String1, &v13, &v16) < 0 )
        goto LABEL_16;
      v7 = *((_DWORD *)lpBuffer + 2);
      if ( v7 > *((_DWORD *)v13 + 2) || v7 == *((_DWORD *)v13 + 2) && *((_DWORD *)lpBuffer + 3) > *((_DWORD *)v13 + 3) )
        goto LABEL_16;
    }
  }
  Instance = CoCreateInstance(a1, 0, 1u, riid, ppv);
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
      dword_1800B6F9C = 1;
      dword_1800B6FA0 = 1;
      LocalPDMPath = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, LPVOID *))ProcAddress)(
                       a1,
                       &IID_IClassFactory,
                       &v13);
      if ( LocalPDMPath >= 0 )
      {
        LocalPDMPath = (*(__int64 (__fastcall **)(LPVOID, _QWORD, IID *, LPVOID *))(*(_QWORD *)v13 + 24LL))(
                         v13,
                         0,
                         riid,
                         ppv);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
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
      dword_1800B6FA0 = 1;
      LocalPDMPath = CoCreateInstance(a1, 0, 1u, riid, ppv);
    }
    goto LABEL_25;
  }
  dword_1800B6FA0 = 1;
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
0x180092cf0  mov     [rsp-8+arg_18], rbx
0x180092cf5  push    rbp
0x180092cf6  push    rsi
0x180092cf7  push    rdi
0x180092cf8  push    r12
0x180092cfa  push    r14
0x180092cfc  lea     rbp, [rsp-380h]
0x180092d04  sub     rsp, 480h
0x180092d0b  mov     rax, cs:__security_cookie
0x180092d12  xor     rax, rsp
0x180092d15  mov     [rbp+3A0h+var_30], rax
0x180092d1c  cmp     cs:dword_1800B6FA0, 0
0x180092d23  mov     r14, r8
0x180092d26  mov     rsi, rdx
0x180092d29  mov     [rsp+4A0h+var_458], 0
0x180092d32  mov     rdi, rcx
0x180092d35  mov     [rsp+4A0h+Block], 0
0x180092d3e  mov     r12d, 1
0x180092d44  jz      short loc_180092D58
0x180092d46  cmp     cs:dword_1800B6F9C, 0
0x180092d4d  jnz     loc_180092E32
0x180092d53  jmp     loc_180092DF8
0x180092d58  lea     rcx, [rsp+4A0h+String2]; pszPathIn
0x180092d5d  call    ?GetLocalPDMPath@@YAJPEAGK@Z; GetLocalPDMPath(ushort *,ulong)
0x180092d62  mov     ebx, eax
0x180092d64  test    eax, eax
0x180092d66  js      loc_180092F25
0x180092d6c  lea     rdx, [rbp+3A0h+String1]; unsigned __int16 *
0x180092d73  mov     rcx, rdi; struct _GUID *
0x180092d76  call    ?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z; GetRegisterdPDMPath(_GUID const &,ushort *,ulong)
0x180092d7b  test    eax, eax
0x180092d7d  js      loc_180092E32
0x180092d83  lea     rdx, [rsp+4A0h+String2]; String2
0x180092d88  lea     rcx, [rbp+3A0h+String1]; String1
0x180092d8f  call    _wcsicmp_0
0x180092d94  test    eax, eax
0x180092d96  jz      short loc_180092DF8
0x180092d98  lea     r8, [rsp+4A0h+Block]; unsigned __int8 **
0x180092d9d  mov     [rsp+4A0h+var_470], 0
0x180092da6  lea     rdx, [rsp+4A0h+lpBuffer]; lplpBuffer
0x180092dab  mov     [rsp+4A0h+lpBuffer], 0
0x180092db4  lea     rcx, [rsp+4A0h+String2]; lpwstrFilename
0x180092db9  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x180092dbe  test    eax, eax
0x180092dc0  js      short loc_180092E32
0x180092dc2  lea     r8, [rsp+4A0h+var_458]; unsigned __int8 **
0x180092dc7  lea     rdx, [rsp+4A0h+var_470]; lplpBuffer
0x180092dcc  lea     rcx, [rbp+3A0h+String1]; lpwstrFilename
0x180092dd3  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x180092dd8  test    eax, eax
0x180092dda  js      short loc_180092E32
0x180092ddc  mov     rdx, [rsp+4A0h+lpBuffer]
0x180092de1  mov     rcx, [rsp+4A0h+var_470]
0x180092de6  mov     eax, [rdx+8]
0x180092de9  cmp     eax, [rcx+8]
0x180092dec  ja      short loc_180092E32
0x180092dee  jnz     short loc_180092DF8
0x180092df0  mov     eax, [rcx+0Ch]
0x180092df3  cmp     [rdx+0Ch], eax
0x180092df6  ja      short loc_180092E32
0x180092df8  mov     r9, rsi; riid
0x180092dfb  mov     [rsp+4A0h+ppv], r14; ppv
0x180092e00  mov     r8d, r12d; dwClsContext
0x180092e03  xor     edx, edx; pUnkOuter
0x180092e05  mov     rcx, rdi; rclsid
0x180092e08  call    cs:__imp_CoCreateInstance
0x180092e0e  mov     ebx, eax
0x180092e10  test    eax, eax
0x180092e12  jnz     short loc_180092E20
0x180092e14  mov     cs:dword_1800B6FA0, r12d
0x180092e1b  jmp     loc_180092F07
0x180092e20  cmp     eax, 80070241h
0x180092e25  jz      short loc_180092E32
0x180092e27  cmp     eax, 8007007Eh
0x180092e2c  jnz     loc_180092F07
0x180092e32  mov     rax, cs:hModule
0x180092e39  test    rax, rax
0x180092e3c  jnz     short loc_180092E5B
0x180092e3e  xor     edx, edx; hFile
0x180092e40  lea     r8d, [rax+8]; dwFlags
0x180092e44  lea     rcx, [rsp+4A0h+String2]; lpLibFileName
0x180092e49  call    cs:__imp_LoadLibraryExW
0x180092e4f  mov     cs:hModule, rax
0x180092e56  test    rax, rax
0x180092e59  jz      short loc_180092ECF
0x180092e5b  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180092e62  mov     rcx, rax; hModule
0x180092e65  call    cs:__imp_GetProcAddress
0x180092e6b  test    rax, rax
0x180092e6e  jz      short loc_180092ECF
0x180092e70  lea     r8, [rsp+4A0h+var_470]
0x180092e75  mov     [rsp+4A0h+var_470], 0
0x180092e7e  lea     rdx, IID_IClassFactory
0x180092e85  mov     cs:dword_1800B6F9C, r12d
0x180092e8c  mov     rcx, rdi
0x180092e8f  mov     cs:dword_1800B6FA0, r12d
0x180092e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092e9b  mov     ebx, eax
0x180092e9d  test    eax, eax
0x180092e9f  js      short loc_180092EE4
0x180092ea1  mov     rcx, [rsp+4A0h+var_470]
0x180092ea6  mov     r9, r14
0x180092ea9  mov     r8, rsi
0x180092eac  xor     edx, edx
0x180092eae  mov     rax, [rcx]
0x180092eb1  mov     rax, [rax+18h]
0x180092eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092eba  mov     rcx, [rsp+4A0h+var_470]
0x180092ebf  mov     ebx, eax
0x180092ec1  mov     rax, [rcx]
0x180092ec4  mov     rax, [rax+10h]
0x180092ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ecd  jmp     short loc_180092EE4
0x180092ecf  call    cs:__imp_GetLastError
0x180092ed5  mov     ebx, eax
0x180092ed7  test    eax, eax
0x180092ed9  jle     short loc_180092EE4
0x180092edb  movzx   ebx, ax
0x180092ede  or      ebx, 80070000h
0x180092ee4  test    ebx, ebx
0x180092ee6  jz      short loc_180092F07
0x180092ee8  mov     r9, rsi; riid
0x180092eeb  mov     cs:dword_1800B6FA0, r12d
0x180092ef2  mov     r8d, r12d; dwClsContext
0x180092ef5  mov     [rsp+4A0h+ppv], r14; ppv
0x180092efa  xor     edx, edx; pUnkOuter
0x180092efc  mov     rcx, rdi; rclsid
0x180092eff  call    cs:__imp_CoCreateInstance
0x180092f05  mov     ebx, eax
0x180092f07  mov     rcx, [rsp+4A0h+Block]; Block
0x180092f0c  test    rcx, rcx
0x180092f0f  jz      short loc_180092F16
0x180092f11  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180092f16  mov     rcx, [rsp+4A0h+var_458]; Block
0x180092f1b  test    rcx, rcx
0x180092f1e  jz      short loc_180092F25
0x180092f20  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180092f25  mov     eax, ebx
0x180092f27  mov     rcx, [rbp+3A0h+var_30]
0x180092f2e  xor     rcx, rsp; StackCookie
0x180092f31  call    __security_check_cookie
0x180092f36  mov     rbx, [rsp+4A0h+arg_18]
0x180092f3e  add     rsp, 480h
0x180092f45  pop     r14
0x180092f47  pop     r12
0x180092f49  pop     rdi
0x180092f4a  pop     rsi
0x180092f4b  pop     rbp
0x180092f4c  retn
```
