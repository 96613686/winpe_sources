# ProviderContext::LoadAndInitializeDll(void)

- ea: `0x140014e18`
- end: `0x140014f83`
- name: `?LoadAndInitializeDll@ProviderContext@@IEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(ProviderContext *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140014d74`

## callees

- `0x1400149a8`
- `0x140014e18`
- `0x1400158b4`
- `0x1400158f4`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140014e2e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140014e2e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140014f27`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140014f27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014f42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014e3d`

## string_xrefs

- `0x140014e89`: `DllGetClassObject`
- `0x140014f37`: `DllCanUnloadNow`

## pseudocode

```c
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
        if ( !v12 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2));
        return v6;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, *((_QWORD *)this + 5), v6);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_18;
  return v6;
}

```

## disassembly

```asm
0x140014e18  mov     [rsp+arg_0], rbx
0x140014e1d  push    rdi
0x140014e1e  sub     rsp, 30h
0x140014e22  mov     rdi, rcx
0x140014e25  xor     r8d, r8d; dwFlags
0x140014e28  xor     edx, edx; hFile
0x140014e2a  mov     rcx, [rcx+28h]; lpLibFileName
0x140014e2e  call    cs:__imp_LoadLibraryExW
0x140014e34  mov     [rdi+70h], rax
0x140014e38  test    rax, rax
0x140014e3b  jnz     short loc_140014E89
0x140014e3d  call    cs:__imp_GetLastError
0x140014e43  mov     ebx, eax
0x140014e45  test    eax, eax
0x140014e47  jle     short loc_140014E52
0x140014e49  movzx   ebx, ax
0x140014e4c  or      ebx, 80070000h
0x140014e52  lea     rax, WPP_GLOBAL_Control
0x140014e59  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e60  cmp     rcx, rax
0x140014e63  jz      short loc_140014E7C
0x140014e65  cmp     byte ptr [rcx+19h], 2
0x140014e69  jb      short loc_140014E7C
0x140014e6b  mov     [rsp+38h+var_18], ebx
0x140014e6f  mov     r9, [rdi+28h]
0x140014e73  mov     rcx, [rcx+10h]
0x140014e77  call    WPP_SF_SD
0x140014e7c  test    ebx, ebx
0x140014e7e  jns     loc_140014F76
0x140014e84  jmp     loc_140014F1E
0x140014e89  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x140014e90  mov     rcx, rax; hModule
0x140014e93  call    cs:__imp_GetProcAddress
0x140014e99  mov     [rdi+88h], rax
0x140014ea0  test    rax, rax
0x140014ea3  jnz     short loc_140014ED0
0x140014ea5  mov     ebx, 8007007Eh
0x140014eaa  lea     rax, WPP_GLOBAL_Control
0x140014eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eb8  cmp     rcx, rax
0x140014ebb  jz      short loc_140014F1E
0x140014ebd  cmp     byte ptr [rcx+19h], 2
0x140014ec1  jb      short loc_140014F1E
0x140014ec3  mov     edx, 13h
0x140014ec8  mov     r9d, 8007007Eh
0x140014ece  jmp     short loc_140014F0E
0x140014ed0  lea     r8, [rdi+98h]
0x140014ed7  lea     rcx, [rdi+18h]
0x140014edb  lea     rdx, IID_IClassFactory
0x140014ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ee7  mov     ebx, eax
0x140014ee9  test    eax, eax
0x140014eeb  jns     short loc_140014F37
0x140014eed  lea     rax, WPP_GLOBAL_Control
0x140014ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x140014efb  cmp     rcx, rax
0x140014efe  jz      short loc_140014F1E
0x140014f00  cmp     byte ptr [rcx+19h], 2
0x140014f04  jb      short loc_140014F1E
0x140014f06  mov     edx, 14h
0x140014f0b  mov     r9d, ebx
0x140014f0e  lea     r8, WPP_91edd21030e531619c269f99d7a31287_Traceguids
0x140014f15  mov     rcx, [rcx+10h]
0x140014f19  call    WPP_SF_D
0x140014f1e  mov     rcx, [rdi+70h]; hLibModule
0x140014f22  test    rcx, rcx
0x140014f25  jz      short loc_140014F76
0x140014f27  call    cs:__imp_FreeLibrary
0x140014f2d  mov     qword ptr [rdi+70h], 0
0x140014f35  jmp     short loc_140014F76
0x140014f37  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x140014f3e  mov     rcx, [rdi+70h]; hModule
0x140014f42  call    cs:__imp_GetProcAddress
0x140014f48  mov     [rdi+90h], rax
0x140014f4f  test    rax, rax
0x140014f52  jnz     short loc_140014F76
0x140014f54  lea     rax, WPP_GLOBAL_Control
0x140014f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f62  cmp     rcx, rax
0x140014f65  jz      short loc_140014F76
0x140014f67  cmp     byte ptr [rcx+19h], 3
0x140014f6b  jb      short loc_140014F76
0x140014f6d  mov     rcx, [rcx+10h]
0x140014f71  call    WPP_SF_
0x140014f76  mov     eax, ebx
0x140014f78  mov     rbx, [rsp+38h+arg_0]
0x140014f7d  add     rsp, 30h
0x140014f81  pop     rdi
0x140014f82  retn
```
