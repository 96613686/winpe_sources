# LoadLatestPDM(_GUID const &,_GUID const &,void * *)

- ea: `0x180095084`
- end: `0x180095300`
- name: `?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `636`
- prototype: `__int64 __fastcall(const struct _GUID *, IID *riid, LPVOID *ppv)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180032410`
- `0x180079b8c`

## callees

- `0x1800585c4`
- `0x18005924d`
- `0x180094d94`
- `0x180094e60`
- `0x180094f48`
- `0x180095084`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800951e3`
- `KERNEL32!LoadLibraryExW` at `0x1800951e3`
- `KERNEL32!GetLastError` at `0x180095275`
- `KERNEL32!GetLastError` at `0x180095275`
- `KERNEL32!GetProcAddress` at `0x180095205`
- `KERNEL32!GetProcAddress` at `0x180095205`
- `ole32!CoCreateInstance` at `0x18009519c`
- `ole32!CoCreateInstance` at `0x1800952ab`
- `ole32!CoCreateInstance` at `0x18009519c`
- `ole32!CoCreateInstance` at `0x1800952ab`

## string_xrefs

- `0x1800951fb`: `DllGetClassObject`

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
  if ( dword_1800B8FA0 )
  {
    if ( dword_1800B8F9C )
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
      dword_1800B8F9C = 1;
      dword_1800B8FA0 = 1;
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
      dword_1800B8FA0 = 1;
      LocalPDMPath = CoCreateInstance(a1, 0, 1u, riid, ppv);
    }
    goto LABEL_25;
  }
  dword_1800B8FA0 = 1;
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
0x180095084  mov     [rsp-8+arg_18], rbx
0x180095089  push    rbp
0x18009508a  push    rsi
0x18009508b  push    rdi
0x18009508c  push    r12
0x18009508e  push    r14
0x180095090  lea     rbp, [rsp-380h]
0x180095098  sub     rsp, 480h
0x18009509f  mov     rax, cs:__security_cookie
0x1800950a6  xor     rax, rsp
0x1800950a9  mov     [rbp+3A0h+var_30], rax
0x1800950b0  cmp     cs:dword_1800B8FA0, 0
0x1800950b7  mov     r14, r8
0x1800950ba  mov     rsi, rdx
0x1800950bd  mov     [rsp+4A0h+var_458], 0
0x1800950c6  mov     rdi, rcx
0x1800950c9  mov     [rsp+4A0h+Block], 0
0x1800950d2  mov     r12d, 1
0x1800950d8  jz      short loc_1800950EC
0x1800950da  cmp     cs:dword_1800B8F9C, 0
0x1800950e1  jnz     loc_1800951CC
0x1800950e7  jmp     loc_18009518C
0x1800950ec  lea     rcx, [rsp+4A0h+String2]; pszPathIn
0x1800950f1  call    ?GetLocalPDMPath@@YAJPEAGK@Z; GetLocalPDMPath(ushort *,ulong)
0x1800950f6  mov     ebx, eax
0x1800950f8  test    eax, eax
0x1800950fa  js      loc_1800952D7
0x180095100  lea     rdx, [rbp+3A0h+String1]; unsigned __int16 *
0x180095107  mov     rcx, rdi; struct _GUID *
0x18009510a  call    ?GetRegisterdPDMPath@@YAJAEBU_GUID@@PEAGK@Z; GetRegisterdPDMPath(_GUID const &,ushort *,ulong)
0x18009510f  test    eax, eax
0x180095111  js      loc_1800951CC
0x180095117  lea     rdx, [rsp+4A0h+String2]; String2
0x18009511c  lea     rcx, [rbp+3A0h+String1]; String1
0x180095123  call    _wcsicmp_0
0x180095128  test    eax, eax
0x18009512a  jz      short loc_18009518C
0x18009512c  lea     r8, [rsp+4A0h+Block]; unsigned __int8 **
0x180095131  mov     [rsp+4A0h+var_470], 0
0x18009513a  lea     rdx, [rsp+4A0h+lpBuffer]; lplpBuffer
0x18009513f  mov     [rsp+4A0h+lpBuffer], 0
0x180095148  lea     rcx, [rsp+4A0h+String2]; lpwstrFilename
0x18009514d  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x180095152  test    eax, eax
0x180095154  js      short loc_1800951CC
0x180095156  lea     r8, [rsp+4A0h+var_458]; unsigned __int8 **
0x18009515b  lea     rdx, [rsp+4A0h+var_470]; lplpBuffer
0x180095160  lea     rcx, [rbp+3A0h+String1]; lpwstrFilename
0x180095167  call    ?GetFixedVersionInfo@@YAJPEAGPEAPEAUtagVS_FIXEDFILEINFO@@PEAPEAE@Z; GetFixedVersionInfo(ushort *,tagVS_FIXEDFILEINFO * *,uchar * *)
0x18009516c  test    eax, eax
0x18009516e  js      short loc_1800951CC
0x180095170  mov     rdx, [rsp+4A0h+lpBuffer]
0x180095175  mov     rcx, [rsp+4A0h+var_470]
0x18009517a  mov     eax, [rdx+8]
0x18009517d  cmp     eax, [rcx+8]
0x180095180  ja      short loc_1800951CC
0x180095182  jnz     short loc_18009518C
0x180095184  mov     eax, [rcx+0Ch]
0x180095187  cmp     [rdx+0Ch], eax
0x18009518a  ja      short loc_1800951CC
0x18009518c  mov     r9, rsi; riid
0x18009518f  mov     [rsp+4A0h+ppv], r14; ppv
0x180095194  mov     r8d, r12d; dwClsContext
0x180095197  xor     edx, edx; pUnkOuter
0x180095199  mov     rcx, rdi; rclsid
0x18009519c  call    cs:__imp_CoCreateInstance
0x1800951a3  nop     dword ptr [rax+rax+00h]
0x1800951a8  mov     ebx, eax
0x1800951aa  test    eax, eax
0x1800951ac  jnz     short loc_1800951BA
0x1800951ae  mov     cs:dword_1800B8FA0, r12d
0x1800951b5  jmp     loc_1800952B9
0x1800951ba  cmp     eax, 80070241h
0x1800951bf  jz      short loc_1800951CC
0x1800951c1  cmp     eax, 8007007Eh
0x1800951c6  jnz     loc_1800952B9
0x1800951cc  mov     rax, cs:hModule
0x1800951d3  test    rax, rax
0x1800951d6  jnz     short loc_1800951FB
0x1800951d8  xor     edx, edx; hFile
0x1800951da  lea     r8d, [rax+8]; dwFlags
0x1800951de  lea     rcx, [rsp+4A0h+String2]; lpLibFileName
0x1800951e3  call    cs:__imp_LoadLibraryExW
0x1800951ea  nop     dword ptr [rax+rax+00h]
0x1800951ef  mov     cs:hModule, rax
0x1800951f6  test    rax, rax
0x1800951f9  jz      short loc_180095275
0x1800951fb  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180095202  mov     rcx, rax; hModule
0x180095205  call    cs:__imp_GetProcAddress
0x18009520c  nop     dword ptr [rax+rax+00h]
0x180095211  test    rax, rax
0x180095214  jz      short loc_180095275
0x180095216  lea     r8, [rsp+4A0h+var_470]
0x18009521b  mov     [rsp+4A0h+var_470], 0
0x180095224  lea     rdx, IID_IClassFactory
0x18009522b  mov     cs:dword_1800B8F9C, r12d
0x180095232  mov     rcx, rdi
0x180095235  mov     cs:dword_1800B8FA0, r12d
0x18009523c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095241  mov     ebx, eax
0x180095243  test    eax, eax
0x180095245  js      short loc_180095290
0x180095247  mov     rcx, [rsp+4A0h+var_470]
0x18009524c  mov     r9, r14
0x18009524f  mov     r8, rsi
0x180095252  xor     edx, edx
0x180095254  mov     rax, [rcx]
0x180095257  mov     rax, [rax+18h]
0x18009525b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095260  mov     rcx, [rsp+4A0h+var_470]
0x180095265  mov     ebx, eax
0x180095267  mov     rax, [rcx]
0x18009526a  mov     rax, [rax+10h]
0x18009526e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095273  jmp     short loc_180095290
0x180095275  call    cs:__imp_GetLastError
0x18009527c  nop     dword ptr [rax+rax+00h]
0x180095281  mov     ebx, eax
0x180095283  test    eax, eax
0x180095285  jle     short loc_180095290
0x180095287  movzx   ebx, ax
0x18009528a  or      ebx, 80070000h
0x180095290  test    ebx, ebx
0x180095292  jz      short loc_1800952B9
0x180095294  mov     r9, rsi; riid
0x180095297  mov     cs:dword_1800B8FA0, r12d
0x18009529e  mov     r8d, r12d; dwClsContext
0x1800952a1  mov     [rsp+4A0h+ppv], r14; ppv
0x1800952a6  xor     edx, edx; pUnkOuter
0x1800952a8  mov     rcx, rdi; rclsid
0x1800952ab  call    cs:__imp_CoCreateInstance
0x1800952b2  nop     dword ptr [rax+rax+00h]
0x1800952b7  mov     ebx, eax
0x1800952b9  mov     rcx, [rsp+4A0h+Block]; Block
0x1800952be  test    rcx, rcx
0x1800952c1  jz      short loc_1800952C8
0x1800952c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800952c8  mov     rcx, [rsp+4A0h+var_458]; Block
0x1800952cd  test    rcx, rcx
0x1800952d0  jz      short loc_1800952D7
0x1800952d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800952d7  mov     eax, ebx
0x1800952d9  mov     rcx, [rbp+3A0h+var_30]
0x1800952e0  xor     rcx, rsp; StackCookie
0x1800952e3  call    __security_check_cookie
0x1800952e8  mov     rbx, [rsp+4A0h+arg_18]
0x1800952f0  add     rsp, 480h
0x1800952f7  pop     r14
0x1800952f9  pop     r12
0x1800952fb  pop     rdi
0x1800952fc  pop     rsi
0x1800952fd  pop     rbp
0x1800952fe  retn
```
