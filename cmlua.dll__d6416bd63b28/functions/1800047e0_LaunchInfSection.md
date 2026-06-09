# _LaunchInfSection

- ea: `0x1800047e0`
- end: `0x180004aa4`
- name: `_LaunchInfSection`
- size: `708`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPCWCH lpWideCharStr, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003550`

## callees

- `0x180001ec0`
- `0x1800047e0`
- `0x180004e1c`
- `0x18000510c`
- `0x1800054b0`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x180004a33`
- `cmutil!CmFree` at `0x180004a3c`
- `cmutil!CmFree` at `0x180004a45`
- `cmutil!CmFree` at `0x180004a53`
- `cmutil!CmFree` at `0x180004a5c`
- `cmutil!CmFree` at `0x180004a65`
- `cmutil!CmFree` at `0x180004a33`
- `cmutil!CmFree` at `0x180004a3c`
- `cmutil!CmFree` at `0x180004a45`
- `cmutil!CmFree` at `0x180004a53`
- `cmutil!CmFree` at `0x180004a5c`
- `cmutil!CmFree` at `0x180004a65`
- `cmutil!CmMalloc` at `0x180004923`
- `cmutil!CmMalloc` at `0x18000492e`
- `cmutil!CmMalloc` at `0x180004939`
- `cmutil!CmMalloc` at `0x180004923`
- `cmutil!CmMalloc` at `0x18000492e`
- `cmutil!CmMalloc` at `0x180004939`
- `KERNEL32!FreeLibrary` at `0x1800048b2`
- `KERNEL32!FreeLibrary` at `0x180004a6e`
- `KERNEL32!FreeLibrary` at `0x1800048b2`
- `KERNEL32!FreeLibrary` at `0x180004a6e`
- `KERNEL32!WideCharToMultiByte` at `0x18000498e`
- `KERNEL32!WideCharToMultiByte` at `0x1800049bf`
- `KERNEL32!WideCharToMultiByte` at `0x1800049ed`
- `KERNEL32!WideCharToMultiByte` at `0x18000498e`
- `KERNEL32!WideCharToMultiByte` at `0x1800049bf`
- `KERNEL32!WideCharToMultiByte` at `0x1800049ed`
- `KERNEL32!LoadLibraryExW` at `0x180004826`
- `KERNEL32!LoadLibraryExW` at `0x180004826`
- `KERNEL32!GetProcAddress` at `0x180004873`
- `KERNEL32!GetProcAddress` at `0x180004873`
- `KERNEL32!GetLastError` at `0x180004834`
- `KERNEL32!GetLastError` at `0x180004881`
- `KERNEL32!GetLastError` at `0x180004834`
- `KERNEL32!GetLastError` at `0x180004881`
- `KERNEL32!CloseHandle` at `0x180004a2a`
- `KERNEL32!CloseHandle` at `0x180004a2a`

## string_xrefs

- `0x18000481c`: `advpack.dll`
- `0x180004899`: `advpack.dll`
- `0x18000484c`: `RunSetupCommand`
- `0x180004869`: `RunSetupCommand`
- `0x1800048a0`: `LoadLibrary of %s failed with error, hResult = 0x%x.`

## pseudocode

```c
__int64 __fastcall LaunchInfSection(unsigned __int16 *a1, LPCWCH lpWideCharStr, const WCHAR *a3, int a4)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  signed int LastError; // eax
  unsigned int v10; // ebx
  FARPROC ProcAddress; // r15
  signed int v13; // eax
  int v14; // ebx
  CHAR *lpMultiByteStr; // r14
  CHAR *v16; // rsi
  CHAR *v17; // rax
  CHAR *v18; // rbp
  HANDLE hObject; // [rsp+50h] [rbp-988h] BYREF
  LPCWCH lpWideCharStra; // [rsp+58h] [rbp-980h]
  _BYTE v21[522]; // [rsp+60h] [rbp-978h] BYREF
  wchar_t v22[5]; // [rsp+26Ah] [rbp-76Eh] BYREF
  wchar_t v23[774]; // [rsp+274h] [rbp-764h] BYREF
  char Buffer[272]; // [rsp+880h] [rbp-158h] BYREF

  lpWideCharStra = a3;
  Library = LoadLibraryExW(L"advpack.dll", 0, 0x800u);
  v8 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress of %S failed with error, hResult = 0x%x.", "RunSetupCommand", v10);
    return v10;
  }
  ProcAddress = GetProcAddress(Library, "RunSetupCommand");
  if ( !ProcAddress )
  {
    v13 = GetLastError();
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary of %s failed with error, hResult = 0x%x.", L"advpack.dll", v10);
    goto LABEL_10;
  }
  v14 = a4 != 0 ? 5 : 1;
  CFileNameParts::CFileNameParts((CFileNameParts *)v21, a1);
  CmStringCchPrintfExA(Buffer, 0x105u, 0, 0, 0x900u, "%S%S", v22, v23);
  hObject = 0;
  lpMultiByteStr = (CHAR *)CmMalloc(0x105u);
  v16 = (CHAR *)CmMalloc(0x105u);
  v17 = (CHAR *)CmMalloc(0x105u);
  v18 = v17;
  if ( lpMultiByteStr && v16 && v17 )
  {
    WideCharToMultiByte(0, 0x400u, a1, -1, lpMultiByteStr, 260, 0, 0);
    WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, v16, 260, 0, 0);
    WideCharToMultiByte(0, 0x400u, lpWideCharStra, -1, v18, 260, 0, 0);
    v10 = ((__int64 (__fastcall *)(_QWORD, CHAR *, CHAR *, char *, CHAR *, HANDLE *, int, _QWORD))ProcAddress)(
            0,
            lpMultiByteStr,
            v16,
            Buffer,
            v18,
            &hObject,
            v14,
            0);
    CloseHandle(hObject);
    CmFree(lpMultiByteStr);
    CmFree(v16);
    CmFree(v18);
LABEL_10:
    FreeLibrary(v8);
    return v10;
  }
  CmFree(lpMultiByteStr);
  CmFree(v16);
  CmFree(v18);
  FreeLibrary(v8);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800047e0  mov     [rsp+arg_18], rbx
0x1800047e5  push    rbp
0x1800047e6  push    rsi
0x1800047e7  push    rdi
0x1800047e8  push    r12
0x1800047ea  push    r13
0x1800047ec  push    r14
0x1800047ee  push    r15
0x1800047f0  sub     rsp, 9A0h
0x1800047f7  mov     rax, cs:__security_cookie
0x1800047fe  xor     rax, rsp
0x180004801  mov     [rsp+9D8h+var_48], rax
0x180004809  mov     [rsp+9D8h+lpWideCharStr], r8
0x18000480e  mov     r13, rdx
0x180004811  mov     r12, rcx
0x180004814  xor     edx, edx; hFile
0x180004816  mov     r8d, 800h; dwFlags
0x18000481c  lea     rcx, aAdvpackDll; "advpack.dll"
0x180004823  mov     ebx, r9d
0x180004826  call    cs:__imp_LoadLibraryExW
0x18000482c  mov     rdi, rax
0x18000482f  test    rax, rax
0x180004832  jnz     short loc_180004869
0x180004834  call    cs:__imp_GetLastError
0x18000483a  mov     ebx, eax
0x18000483c  test    eax, eax
0x18000483e  jle     short loc_180004849
0x180004840  movzx   ebx, ax
0x180004843  or      ebx, 80070000h
0x180004849  mov     r9d, ebx
0x18000484c  lea     r8, aRunsetupcomman; "RunSetupCommand"
0x180004853  lea     rdx, aGetprocaddress; "GetProcAddress of %S failed with error,"...
0x18000485a  or      ecx, 0FFFFFFFFh
0x18000485d  call    MyDbgPrintfW
0x180004862  mov     eax, ebx
0x180004864  jmp     loc_180004A79
0x180004869  lea     rdx, aRunsetupcomman; "RunSetupCommand"
0x180004870  mov     rcx, rdi; hModule
0x180004873  call    cs:__imp_GetProcAddress
0x180004879  mov     r15, rax
0x18000487c  test    rax, rax
0x18000487f  jnz     short loc_1800048BA
0x180004881  call    cs:__imp_GetLastError
0x180004887  mov     ebx, eax
0x180004889  test    eax, eax
0x18000488b  jle     short loc_180004896
0x18000488d  movzx   ebx, ax
0x180004890  or      ebx, 80070000h
0x180004896  mov     r9d, ebx
0x180004899  lea     r8, aAdvpackDll; "advpack.dll"
0x1800048a0  lea     rdx, aLoadlibraryOfS; "LoadLibrary of %s failed with error, hR"...
0x1800048a7  or      ecx, 0FFFFFFFFh
0x1800048aa  call    MyDbgPrintfW
0x1800048af  mov     rcx, rdi; hLibModule
0x1800048b2  call    cs:__imp_FreeLibrary
0x1800048b8  jmp     short loc_180004862
0x1800048ba  neg     ebx
0x1800048bc  lea     rcx, [rsp+9D8h+var_978]; this
0x1800048c1  mov     rdx, r12; unsigned __int16 *
0x1800048c4  sbb     ebx, ebx
0x1800048c6  and     ebx, 4
0x1800048c9  inc     ebx
0x1800048cb  call    ??0CFileNameParts@@QEAA@PEBG@Z; CFileNameParts::CFileNameParts(ushort const *)
0x1800048d0  lea     rax, [rsp+9D8h+var_764]
0x1800048d8  mov     ebp, 105h
0x1800048dd  mov     [rsp+9D8h+lpUsedDefaultChar], rax
0x1800048e2  lea     rcx, [rsp+9D8h+Buffer]; Buffer
0x1800048ea  lea     rax, [rsp+9D8h+var_76E]
0x1800048f2  xor     r9d, r9d; unsigned __int64 *
0x1800048f5  mov     [rsp+9D8h+lpDefaultChar], rax
0x1800048fa  xor     r8d, r8d; char **
0x1800048fd  lea     rax, aSS; "%S%S"
0x180004904  mov     edx, ebp; cbDest
0x180004906  mov     qword ptr [rsp+9D8h+cbMultiByte], rax; char *
0x18000490b  mov     dword ptr [rsp+9D8h+lpMultiByteStr], 900h; unsigned int
0x180004913  call    ?CmStringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; CmStringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180004918  mov     ecx, ebp
0x18000491a  mov     [rsp+9D8h+hObject], 0
0x180004923  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180004929  mov     ecx, ebp
0x18000492b  mov     r14, rax
0x18000492e  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180004934  mov     ecx, ebp
0x180004936  mov     rsi, rax
0x180004939  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x18000493f  mov     rbp, rax
0x180004942  test    r14, r14
0x180004945  jz      loc_180004A50
0x18000494b  test    rsi, rsi
0x18000494e  jz      loc_180004A50
0x180004954  test    rax, rax
0x180004957  jz      loc_180004A50
0x18000495d  mov     [rsp+9D8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180004966  mov     r8, r12; lpWideCharStr
0x180004969  mov     [rsp+9D8h+lpDefaultChar], 0; lpDefaultChar
0x180004972  mov     r12d, 400h
0x180004978  mov     edx, r12d; dwFlags
0x18000497b  mov     [rsp+9D8h+cbMultiByte], 104h; cbMultiByte
0x180004983  or      r9d, 0FFFFFFFFh; cchWideChar
0x180004987  mov     [rsp+9D8h+lpMultiByteStr], r14; lpMultiByteStr
0x18000498c  xor     ecx, ecx; CodePage
0x18000498e  call    cs:__imp_WideCharToMultiByte
0x180004994  mov     [rsp+9D8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000499d  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800049a1  mov     [rsp+9D8h+lpDefaultChar], 0; lpDefaultChar
0x1800049aa  mov     r8, r13; lpWideCharStr
0x1800049ad  mov     [rsp+9D8h+cbMultiByte], 104h; cbMultiByte
0x1800049b5  mov     edx, r12d; dwFlags
0x1800049b8  xor     ecx, ecx; CodePage
0x1800049ba  mov     [rsp+9D8h+lpMultiByteStr], rsi; lpMultiByteStr
0x1800049bf  call    cs:__imp_WideCharToMultiByte
0x1800049c5  mov     r8, [rsp+9D8h+lpWideCharStr]; lpWideCharStr
0x1800049ca  xor     r13d, r13d
0x1800049cd  mov     [rsp+9D8h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800049d2  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800049d6  mov     [rsp+9D8h+lpDefaultChar], r13; lpDefaultChar
0x1800049db  mov     edx, r12d; dwFlags
0x1800049de  mov     [rsp+9D8h+cbMultiByte], 104h; cbMultiByte
0x1800049e6  xor     ecx, ecx; CodePage
0x1800049e8  mov     [rsp+9D8h+lpMultiByteStr], rbp; lpMultiByteStr
0x1800049ed  call    cs:__imp_WideCharToMultiByte
0x1800049f3  mov     [rsp+9D8h+lpUsedDefaultChar], r13
0x1800049f8  lea     rax, [rsp+9D8h+hObject]
0x1800049fd  mov     dword ptr [rsp+9D8h+lpDefaultChar], ebx
0x180004a01  lea     r9, [rsp+9D8h+Buffer]
0x180004a09  mov     qword ptr [rsp+9D8h+cbMultiByte], rax
0x180004a0e  mov     r8, rsi
0x180004a11  mov     rax, r15
0x180004a14  mov     [rsp+9D8h+lpMultiByteStr], rbp
0x180004a19  mov     rdx, r14
0x180004a1c  xor     ecx, ecx
0x180004a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a23  mov     rcx, [rsp+9D8h+hObject]; hObject
0x180004a28  mov     ebx, eax
0x180004a2a  call    cs:__imp_CloseHandle
0x180004a30  mov     rcx, r14
0x180004a33  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180004a39  mov     rcx, rsi
0x180004a3c  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180004a42  mov     rcx, rbp
0x180004a45  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180004a4b  jmp     loc_1800048AF
0x180004a50  mov     rcx, r14
0x180004a53  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180004a59  mov     rcx, rsi
0x180004a5c  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180004a62  mov     rcx, rbp
0x180004a65  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180004a6b  mov     rcx, rdi; hLibModule
0x180004a6e  call    cs:__imp_FreeLibrary
0x180004a74  mov     eax, 8007000Eh
0x180004a79  mov     rcx, [rsp+9D8h+var_48]
0x180004a81  xor     rcx, rsp; StackCookie
0x180004a84  call    __security_check_cookie
0x180004a89  mov     rbx, [rsp+9D8h+arg_18]
0x180004a91  add     rsp, 9A0h
0x180004a98  pop     r15
0x180004a9a  pop     r14
0x180004a9c  pop     r13
0x180004a9e  pop     r12
0x180004aa0  pop     rdi
0x180004aa1  pop     rsi
0x180004aa2  pop     rbp
0x180004aa3  retn
```
