# CMUILanguages::CMUILanguages(ulong)

- ea: `0x180042598`
- end: `0x1800426fb`
- name: `??0CMUILanguages@@QEAA@K@Z`
- size: `355`
- prototype: `CMUILanguages *__fastcall(CMUILanguages *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800269d0`

## callees

- `0x180002a64`
- `0x18000f460`
- `0x180042598`
- `0x180067190`
- `0x180075c5a`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetUserDefaultUILanguage` at `0x1800426aa`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800426aa`
- `KERNEL32!WideCharToMultiByte` at `0x1800426a0`
- `KERNEL32!WideCharToMultiByte` at `0x1800426a0`
- `KERNEL32!FreeLibrary` at `0x18004265e`
- `KERNEL32!FreeLibrary` at `0x18004265e`
- `KERNEL32!GetProcAddress` at `0x180042609`
- `KERNEL32!GetProcAddress` at `0x180042609`

## string_xrefs

- `0x1800425bc`: `kernel32.dll`
- `0x1800425ff`: `GetThreadPreferredUILanguages`

## pseudocode

```c
CMUILanguages *__fastcall CMUILanguages::CMUILanguages(CMUILanguages *this, __int64 a2)
{
  HMODULE LibraryA; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rbx
  int v5; // ebx
  LANGID UserDefaultUILanguage; // ax
  int v8; // [rsp+40h] [rbp-1F8h] BYREF
  int cchWideChar[3]; // [rsp+44h] [rbp-1F4h] BYREF
  WCHAR WideCharStr[96]; // [rsp+50h] [rbp-1E8h] BYREF
  CHAR LibFileName[272]; // [rsp+110h] [rbp-128h] BYREF

  MultiByteStr = 0;
  if ( !GetPathToSystemBinary(LibFileName, a2, "kernel32.dll") )
    goto LABEL_7;
  LibraryA = IsolationAwareLoadLibraryA(LibFileName);
  v3 = LibraryA;
  if ( !LibraryA
    || (ProcAddress = GetProcAddress(LibraryA, "GetThreadPreferredUILanguages")) == 0
    || (memset_0(WideCharStr, 0, 0xB8u),
        cchWideChar[0] = 92,
        v8 = 0,
        v5 = ((__int64 (__fastcall *)(__int64, int *, WCHAR *, int *))ProcAddress)(52, &v8, WideCharStr, cchWideChar),
        FreeLibrary(v3),
        v5 != 1)
    || !v8
    || !WideCharToMultiByte(0, 0x400u, WideCharStr, cchWideChar[0], &MultiByteStr, 92, 0, 0) )
  {
LABEL_7:
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    if ( (int)StringCchPrintfA(&MultiByteStr, 0x5Cu, "%04X", UserDefaultUILanguage) < 0 )
      MultiByteStr = 0;
  }
  return (CMUILanguages *)&MultiByteStr;
}

```

## disassembly

```asm
0x180042598  mov     [rsp+arg_0], rbx
0x18004259d  mov     [rsp+arg_8], rbp
0x1800425a2  push    rdi
0x1800425a3  sub     rsp, 230h
0x1800425aa  mov     rax, cs:__security_cookie
0x1800425b1  xor     rax, rsp
0x1800425b4  mov     [rsp+238h+var_18], rax
0x1800425bc  lea     r8, aKernel32Dll_0; "kernel32.dll"
0x1800425c3  mov     cs:MultiByteStr, 0
0x1800425ca  lea     rcx, [rsp+238h+LibFileName]; char *
0x1800425d2  call    ?GetPathToSystemBinary@@YA_NPEADKPEBD@Z; GetPathToSystemBinary(char *,ulong,char const *)
0x1800425d7  lea     rbp, MultiByteStr
0x1800425de  cmp     al, 1
0x1800425e0  jnz     loc_1800426AA
0x1800425e6  lea     rcx, [rsp+238h+LibFileName]; lpLibFileName
0x1800425ee  call    IsolationAwareLoadLibraryA
0x1800425f3  mov     rdi, rax
0x1800425f6  test    rax, rax
0x1800425f9  jz      loc_1800426AA
0x1800425ff  lea     rdx, aGetthreadprefe; "GetThreadPreferredUILanguages"
0x180042606  mov     rcx, rax; hModule
0x180042609  call    cs:__imp_GetProcAddress
0x18004260f  mov     rbx, rax
0x180042612  test    rax, rax
0x180042615  jz      loc_1800426AA
0x18004261b  xor     edx, edx; Val
0x18004261d  lea     rcx, [rsp+238h+WideCharStr]; void *
0x180042622  mov     r8d, 0B8h; Size
0x180042628  call    memset_0
0x18004262d  lea     r9, [rsp+238h+cchWideChar]
0x180042632  mov     [rsp+238h+cchWideChar], 5Ch ; '\'
0x18004263a  lea     r8, [rsp+238h+WideCharStr]
0x18004263f  mov     [rsp+238h+var_1F8], 0
0x180042647  lea     rdx, [rsp+238h+var_1F8]
0x18004264c  mov     ecx, 34h ; '4'
0x180042651  mov     rax, rbx
0x180042654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042659  mov     rcx, rdi; hLibModule
0x18004265c  mov     ebx, eax
0x18004265e  call    cs:__imp_FreeLibrary
0x180042664  cmp     ebx, 1
0x180042667  jnz     short loc_1800426AA
0x180042669  cmp     [rsp+238h+var_1F8], 0
0x18004266e  jbe     short loc_1800426AA
0x180042670  mov     r9d, [rsp+238h+cchWideChar]; cchWideChar
0x180042675  lea     r8, [rsp+238h+WideCharStr]; lpWideCharStr
0x18004267a  mov     [rsp+238h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180042683  mov     edx, 400h; dwFlags
0x180042688  mov     [rsp+238h+lpDefaultChar], 0; lpDefaultChar
0x180042691  xor     ecx, ecx; CodePage
0x180042693  mov     [rsp+238h+cbMultiByte], 5Ch ; '\'; cbMultiByte
0x18004269b  mov     [rsp+238h+lpMultiByteStr], rbp; lpMultiByteStr
0x1800426a0  call    cs:__imp_WideCharToMultiByte
0x1800426a6  test    eax, eax
0x1800426a8  jnz     short loc_1800426D3
0x1800426aa  call    cs:__imp_GetUserDefaultUILanguage
0x1800426b0  movzx   r9d, ax
0x1800426b4  lea     r8, a04x; "%04X"
0x1800426bb  mov     edx, 5Ch ; '\'; unsigned __int64
0x1800426c0  mov     rcx, rbp; char *
0x1800426c3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800426c8  test    eax, eax
0x1800426ca  jns     short loc_1800426D3
0x1800426cc  mov     cs:MultiByteStr, 0
0x1800426d3  mov     rax, rbp
0x1800426d6  mov     rcx, [rsp+238h+var_18]
0x1800426de  xor     rcx, rsp; StackCookie
0x1800426e1  call    __security_check_cookie
0x1800426e6  lea     r11, [rsp+238h+var_8]
0x1800426ee  mov     rbx, [r11+10h]
0x1800426f2  mov     rbp, [r11+18h]
0x1800426f6  mov     rsp, r11
0x1800426f9  pop     rdi
0x1800426fa  retn
```
