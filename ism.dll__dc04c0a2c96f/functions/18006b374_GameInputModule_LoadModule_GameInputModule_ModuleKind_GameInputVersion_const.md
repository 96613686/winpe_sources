# GameInputModule::LoadModule(GameInputModule::ModuleKind,GameInputVersion const &)

- ea: `0x18006b374`
- end: `0x18006b4ef`
- name: `?LoadModule@GameInputModule@@AEAAJW4ModuleKind@1@AEBUGameInputVersion@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18006b278`

## callees

- `0x18006b374`
- `0x18006b4f8`
- `0x1800f0a90`
- `0x1801415cc`
- `0x180141764`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b4da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006b4da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b487`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b49f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b4b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b487`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b49f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006b4b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006b45f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006b45f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b39d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b39d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b3fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b3fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b433`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006b3ce`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006b3ce`

## string_xrefs

- `0x18006b3b7`: `GameInput.dll`
- `0x18006b47d`: `GameInputCreate`
- `0x18006b495`: `DllCanUnloadNow`
- `0x18006b4ad`: `DllGetClassObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GameInputModule::LoadModule(__int64 a1, __int64 a2, const WCHAR *a3)
{
  int v3; // edi
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  const struct std::nothrow_t *v6; // rdx
  int SystemDirPath; // edi
  DWORD FileAttributesW; // eax
  const struct GameInputVersion *v9; // rdx
  bool v10; // zf
  HMODULE Library; // rax
  HMODULE v13; // rdi
  FARPROC ProcAddress; // r14
  FARPROC v15; // r15
  FARPROC v16; // rax
  LPCWSTR lpFileName; // [rsp+50h] [rbp+18h] BYREF

  lpFileName = a3;
  v3 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 )
    goto LABEL_8;
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v3 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 )
  {
LABEL_7:
    LeaveCriticalSection(v5);
LABEL_8:
    if ( v3 == 1 )
      return *(_QWORD *)(a1 + 32) == 0;
    else
      return 2147549183LL;
  }
  lpFileName = 0;
  SystemDirPath = GameInputModule::GetSystemDirPath(L"GameInput.dll", &lpFileName);
  if ( SystemDirPath >= 0 )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW != -1
      && (FileAttributesW & 0x550) == 0
      && (int)GameInputModule::ValidateModuleCertChain(lpFileName) >= 0 )
    {
      Library = LoadLibraryExW(lpFileName, 0, 0x800u);
      v13 = Library;
      if ( Library )
      {
        if ( GameInputModule::ValidateModuleVersion(Library, v9)
          && (ProcAddress = GetProcAddress(v13, "GameInputCreate")) != 0
          && (v15 = GetProcAddress(v13, "DllCanUnloadNow")) != 0
          && (v16 = GetProcAddress(v13, "DllGetClassObject")) != 0 )
        {
          *(_QWORD *)(a1 + 8) = ProcAddress;
          *(_QWORD *)(a1 + 16) = v15;
          *(_QWORD *)(a1 + 24) = v16;
          *(_QWORD *)(a1 + 32) = v13;
        }
        else
        {
          FreeLibrary(v13);
        }
      }
    }
    v10 = lpFileName == 0;
    *(_DWORD *)a1 = 1;
    v3 = 1;
    if ( !v10 )
      operator delete((void *)lpFileName, v9);
    goto LABEL_7;
  }
  if ( lpFileName )
    operator delete((void *)lpFileName, v6);
  LeaveCriticalSection(v5);
  return (unsigned int)SystemDirPath;
}

```

## disassembly

```asm
0x18006b374  mov     [rsp+arg_0], rbx
0x18006b379  mov     [rsp+arg_8], rbp
0x18006b37e  mov     [rsp+lpFileName], r8
0x18006b383  push    rdi
0x18006b384  push    r14
0x18006b386  push    r15
0x18006b388  sub     rsp, 20h
0x18006b38c  mov     edi, [rcx]
0x18006b38e  mov     rbx, rcx
0x18006b391  nop
0x18006b392  test    edi, edi
0x18006b394  jnz     short loc_18006B400
0x18006b396  lea     rbp, [rcx+28h]
0x18006b39a  mov     rcx, rbp; lpCriticalSection
0x18006b39d  call    cs:__imp_EnterCriticalSection
0x18006b3a3  mov     edi, [rbx]
0x18006b3a5  test    edi, edi
0x18006b3a7  jnz     short loc_18006B3F7
0x18006b3a9  lea     rdx, [rsp+38h+lpFileName]
0x18006b3ae  mov     [rsp+38h+lpFileName], 0
0x18006b3b7  lea     rcx, aGameinputDll; "GameInput.dll"
0x18006b3be  call    ?GetSystemDirPath@GameInputModule@@CAJPEBGAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z; GameInputModule::GetSystemDirPath(ushort const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)
0x18006b3c3  mov     rcx, [rsp+38h+lpFileName]; void *
0x18006b3c8  mov     edi, eax
0x18006b3ca  test    eax, eax
0x18006b3cc  js      short loc_18006B426
0x18006b3ce  call    cs:__imp_GetFileAttributesW
0x18006b3d4  cmp     eax, 0FFFFFFFFh
0x18006b3d7  jnz     short loc_18006B43D
0x18006b3d9  cmp     [rsp+38h+lpFileName], 0
0x18006b3df  nop
0x18006b3e0  mov     dword ptr [rbx], 1
0x18006b3e6  mov     edi, 1
0x18006b3eb  jz      short loc_18006B3F7
0x18006b3ed  mov     rcx, [rsp+38h+lpFileName]; void *
0x18006b3f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b3f7  mov     rcx, rbp; lpCriticalSection
0x18006b3fa  call    cs:__imp_LeaveCriticalSection
0x18006b400  cmp     edi, 1
0x18006b403  jnz     loc_18006B4E5
0x18006b409  xor     eax, eax
0x18006b40b  cmp     [rbx+20h], rax
0x18006b40f  setz    al
0x18006b412  mov     rbx, [rsp+38h+arg_0]
0x18006b417  mov     rbp, [rsp+38h+arg_8]
0x18006b41c  add     rsp, 20h
0x18006b420  pop     r15
0x18006b422  pop     r14
0x18006b424  pop     rdi
0x18006b425  retn
0x18006b426  test    rcx, rcx
0x18006b429  jz      short loc_18006B430
0x18006b42b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006b430  mov     rcx, rbp; lpCriticalSection
0x18006b433  call    cs:__imp_LeaveCriticalSection
0x18006b439  mov     eax, edi
0x18006b43b  jmp     short loc_18006B412
0x18006b43d  test    eax, 550h
0x18006b442  jnz     short loc_18006B3D9
0x18006b444  mov     rcx, [rsp+38h+lpFileName]; unsigned __int16 *
0x18006b449  call    ?ValidateModuleCertChain@GameInputModule@@CAJPEBG@Z; GameInputModule::ValidateModuleCertChain(ushort const *)
0x18006b44e  test    eax, eax
0x18006b450  js      short loc_18006B3D9
0x18006b452  mov     rcx, [rsp+38h+lpFileName]; lpLibFileName
0x18006b457  xor     edx, edx; hFile
0x18006b459  mov     r8d, 800h; dwFlags
0x18006b45f  call    cs:__imp_LoadLibraryExW
0x18006b465  mov     rdi, rax
0x18006b468  test    rax, rax
0x18006b46b  jz      loc_18006B3D9
0x18006b471  mov     rcx, rax; HINSTANCE
0x18006b474  call    ?ValidateModuleVersion@GameInputModule@@CA_NPEAUHINSTANCE__@@AEBUGameInputVersion@@@Z; GameInputModule::ValidateModuleVersion(HINSTANCE__ *,GameInputVersion const &)
0x18006b479  test    al, al
0x18006b47b  jz      short loc_18006B4D7
0x18006b47d  lea     rdx, ProcName; "GameInputCreate"
0x18006b484  mov     rcx, rdi; hModule
0x18006b487  call    cs:__imp_GetProcAddress
0x18006b48d  mov     r14, rax
0x18006b490  test    rax, rax
0x18006b493  jz      short loc_18006B4D7
0x18006b495  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x18006b49c  mov     rcx, rdi; hModule
0x18006b49f  call    cs:__imp_GetProcAddress
0x18006b4a5  mov     r15, rax
0x18006b4a8  test    rax, rax
0x18006b4ab  jz      short loc_18006B4D7
0x18006b4ad  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x18006b4b4  mov     rcx, rdi; hModule
0x18006b4b7  call    cs:__imp_GetProcAddress
0x18006b4bd  test    rax, rax
0x18006b4c0  jz      short loc_18006B4D7
0x18006b4c2  mov     [rbx+8], r14
0x18006b4c6  mov     [rbx+10h], r15
0x18006b4ca  mov     [rbx+18h], rax
0x18006b4ce  mov     [rbx+20h], rdi
0x18006b4d2  jmp     loc_18006B3D9
0x18006b4d7  mov     rcx, rdi; hLibModule
0x18006b4da  call    cs:__imp_FreeLibrary
0x18006b4e0  jmp     loc_18006B3D9
0x18006b4e5  mov     eax, 8000FFFFh
0x18006b4ea  jmp     loc_18006B412
```
