# ProviderContext::LoadAndInitializeDll(void)

- ea: `0x1800628d0`
- end: `0x180062a47`
- name: `?LoadAndInitializeDll@ProviderContext@@IEAAJXZ`
- size: `375`
- prototype: `__int64 __fastcall(ProviderContext *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180020168`
- `0x180026120`

## callees

- `0x180061c40`
- `0x1800626a0`
- `0x1800628d0`
- `0x1800632c0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006294b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800629fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006294b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800629fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800629df`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800629df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800628e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800628e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800628f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800628f5`

## string_xrefs

- `0x180062941`: `DllGetClassObject`
- `0x1800629ef`: `DllCanUnloadNow`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProviderContext::LoadAndInitializeDll(ProviderContext *this)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  int v4; // edx
  int v5; // r8d
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  HMODULE v11; // rcx
  FARPROC v12; // rax

  Library = LoadLibraryExW(*((LPCWSTR *)this + 5), 0, 0);
  *((_QWORD *)this + 14) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllGetClassObject");
    *((_QWORD *)this + 17) = ProcAddress;
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(char *, GUID *, char *))ProcAddress)(
             (char *)this + 24,
             &IID_IClassFactory,
             (char *)this + 152);
      if ( (v6 & 0x80000000) == 0 )
      {
        v12 = GetProcAddress(*((HMODULE *)this + 14), "DllCanUnloadNow");
        *((_QWORD *)this + 18) = v12;
        if ( !v12 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_91edd21030e531619c269f99d7a31287_Traceguids);
        return v6;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 20;
        v10 = v6;
        goto LABEL_17;
      }
    }
    else
    {
      v6 = -2147024770;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 19;
        v10 = 2147942526LL;
LABEL_17:
        WPP_SF_D(v8[2], v9, &WPP_91edd21030e531619c269f99d7a31287_Traceguids, v10);
      }
    }
LABEL_18:
    v11 = (HMODULE)*((_QWORD *)this + 14);
    if ( v11 )
    {
      FreeLibrary(v11);
      *((_QWORD *)this + 14) = 0;
    }
    return v6;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, *((_QWORD *)this + 5), v6);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_18;
  return v6;
}

```

## disassembly

```asm
0x1800628d0  mov     [rsp+arg_0], rbx
0x1800628d5  push    rdi
0x1800628d6  sub     rsp, 30h
0x1800628da  mov     rdi, rcx
0x1800628dd  xor     r8d, r8d; dwFlags
0x1800628e0  xor     edx, edx; hFile
0x1800628e2  mov     rcx, [rcx+28h]; lpLibFileName
0x1800628e6  call    cs:__imp_LoadLibraryExW
0x1800628ec  mov     [rdi+70h], rax
0x1800628f0  test    rax, rax
0x1800628f3  jnz     short loc_180062941
0x1800628f5  call    cs:__imp_GetLastError
0x1800628fb  mov     ebx, eax
0x1800628fd  test    eax, eax
0x1800628ff  jle     short loc_18006290A
0x180062901  movzx   ebx, ax
0x180062904  or      ebx, 80070000h
0x18006290a  lea     rax, WPP_GLOBAL_Control
0x180062911  mov     rcx, cs:WPP_GLOBAL_Control
0x180062918  cmp     rcx, rax
0x18006291b  jz      short loc_180062934
0x18006291d  cmp     byte ptr [rcx+19h], 2
0x180062921  jb      short loc_180062934
0x180062923  mov     [rsp+38h+var_18], ebx
0x180062927  mov     r9, [rdi+28h]
0x18006292b  mov     rcx, [rcx+10h]
0x18006292f  call    WPP_SF_SD
0x180062934  test    ebx, ebx
0x180062936  jns     loc_180062A3A
0x18006293c  jmp     loc_1800629D6
0x180062941  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x180062948  mov     rcx, rax; hModule
0x18006294b  call    cs:__imp_GetProcAddress
0x180062951  mov     [rdi+88h], rax
0x180062958  test    rax, rax
0x18006295b  jnz     short loc_180062988
0x18006295d  mov     ebx, 8007007Eh
0x180062962  lea     rax, WPP_GLOBAL_Control
0x180062969  mov     rcx, cs:WPP_GLOBAL_Control
0x180062970  cmp     rcx, rax
0x180062973  jz      short loc_1800629D6
0x180062975  cmp     byte ptr [rcx+19h], 2
0x180062979  jb      short loc_1800629D6
0x18006297b  mov     edx, 13h
0x180062980  mov     r9d, 8007007Eh
0x180062986  jmp     short loc_1800629C6
0x180062988  lea     r8, [rdi+98h]
0x18006298f  lea     rcx, [rdi+18h]
0x180062993  lea     rdx, IID_IClassFactory
0x18006299a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006299f  mov     ebx, eax
0x1800629a1  test    eax, eax
0x1800629a3  jns     short loc_1800629EF
0x1800629a5  lea     rax, WPP_GLOBAL_Control
0x1800629ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629b3  cmp     rcx, rax
0x1800629b6  jz      short loc_1800629D6
0x1800629b8  cmp     byte ptr [rcx+19h], 2
0x1800629bc  jb      short loc_1800629D6
0x1800629be  mov     edx, 14h
0x1800629c3  mov     r9d, ebx
0x1800629c6  lea     r8, WPP_91edd21030e531619c269f99d7a31287_Traceguids
0x1800629cd  mov     rcx, [rcx+10h]
0x1800629d1  call    WPP_SF_D
0x1800629d6  mov     rcx, [rdi+70h]; hLibModule
0x1800629da  test    rcx, rcx
0x1800629dd  jz      short loc_180062A3A
0x1800629df  call    cs:__imp_FreeLibrary
0x1800629e5  mov     qword ptr [rdi+70h], 0
0x1800629ed  jmp     short loc_180062A3A
0x1800629ef  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x1800629f6  mov     rcx, [rdi+70h]; hModule
0x1800629fa  call    cs:__imp_GetProcAddress
0x180062a00  mov     [rdi+90h], rax
0x180062a07  test    rax, rax
0x180062a0a  jnz     short loc_180062A3A
0x180062a0c  lea     rax, WPP_GLOBAL_Control
0x180062a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180062a1a  cmp     rcx, rax
0x180062a1d  jz      short loc_180062A3A
0x180062a1f  cmp     byte ptr [rcx+19h], 3
0x180062a23  jb      short loc_180062A3A
0x180062a25  mov     edx, 15h
0x180062a2a  lea     r8, WPP_91edd21030e531619c269f99d7a31287_Traceguids
0x180062a31  mov     rcx, [rcx+10h]
0x180062a35  call    WPP_SF_
0x180062a3a  mov     eax, ebx
0x180062a3c  mov     rbx, [rsp+38h+arg_0]
0x180062a41  add     rsp, 30h
0x180062a45  pop     rdi
0x180062a46  retn
```
