# CDimSetup::CDimSetup(void)

- ea: `0x180030744`
- end: `0x180030868`
- name: `??0CDimSetup@@QEAA@XZ`
- size: `292`
- prototype: `CDimSetup *__fastcall(CDimSetup *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180011a44`

## callees

- `0x180030744`

## import_xrefs

- `USER32!LoadStringW` at `0x1800307a6`
- `USER32!LoadStringW` at `0x1800307c1`
- `USER32!LoadStringW` at `0x1800307a6`
- `USER32!LoadStringW` at `0x1800307c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030786`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030786`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800307ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800307ca`
- `ADVAPI32!RegOpenKeyExW` at `0x1800307f0`
- `ADVAPI32!RegOpenKeyExW` at `0x1800307f0`
- `ADVAPI32!RegCloseKey` at `0x180030857`
- `ADVAPI32!RegCloseKey` at `0x180030857`
- `ADVAPI32!RegQueryValueExW` at `0x180030825`
- `ADVAPI32!RegQueryValueExW` at `0x180030825`

## string_xrefs

- `0x1800307e2`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18003075a`: `mprmsg.dll`

## pseudocode

```c
CDimSetup *__fastcall CDimSetup::CDimSetup(CDimSetup *this)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  bool v4; // zf
  BOOL v5; // eax
  int Data; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  *(_QWORD *)((char *)this + 4) = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  Library = LoadLibraryExW(L"mprmsg.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    LoadStringW(Library, 0x4A38u, (LPWSTR)this + 6, 256);
    LoadStringW(v3, 0x4A39u, (LPWSTR)this + 262, 256);
    FreeLibrary(v3);
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"RouterType", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v4 = (Data & 7) == 0;
      *(_DWORD *)this = 1;
      v5 = !v4;
      v4 = (Data & 0x38) == 0;
      *((_DWORD *)this + 1) = v5;
      *((_DWORD *)this + 2) = !v4;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return this;
}

```

## disassembly

```asm
0x180030744  push    rbp
0x180030746  push    rbx
0x180030747  push    rdi
0x180030748  mov     rbp, rsp
0x18003074b  sub     rsp, 30h
0x18003074f  mov     rbx, rcx
0x180030752  mov     qword ptr [rcx+4], 0
0x18003075a  lea     rcx, LibFileName; "mprmsg.dll"
0x180030761  mov     [rbp+hKey], 0
0x180030769  xor     edx, edx; hFile
0x18003076b  mov     [rbp+Type], 0
0x180030772  mov     r8d, 800h; dwFlags
0x180030778  mov     [rbp+cbData], 0
0x18003077f  mov     [rbp+Data], 0
0x180030786  call    cs:__imp_LoadLibraryExW
0x18003078c  mov     rdi, rax
0x18003078f  test    rax, rax
0x180030792  jz      short loc_1800307D0
0x180030794  lea     r8, [rbx+0Ch]; lpBuffer
0x180030798  mov     edx, 4A38h; uID
0x18003079d  mov     r9d, 100h; cchBufferMax
0x1800307a3  mov     rcx, rax; hInstance
0x1800307a6  call    cs:__imp_LoadStringW
0x1800307ac  lea     r8, [rbx+20Ch]; lpBuffer
0x1800307b3  mov     edx, 4A39h; uID
0x1800307b8  mov     r9d, 100h; cchBufferMax
0x1800307be  mov     rcx, rdi; hInstance
0x1800307c1  call    cs:__imp_LoadStringW
0x1800307c7  mov     rcx, rdi; hLibModule
0x1800307ca  call    cs:__imp_FreeLibrary
0x1800307d0  lea     rax, [rbp+hKey]
0x1800307d4  mov     r9d, 20019h; samDesired
0x1800307da  xor     r8d, r8d; ulOptions
0x1800307dd  mov     [rsp+30h+phkResult], rax; phkResult
0x1800307e2  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Re"...
0x1800307e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800307f0  call    cs:__imp_RegOpenKeyExW
0x1800307f6  test    eax, eax
0x1800307f8  jnz     short loc_18003084E
0x1800307fa  mov     rcx, [rbp+hKey]; hKey
0x1800307fe  lea     rax, [rbp+cbData]
0x180030802  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180030807  lea     r9, [rbp+Type]; lpType
0x18003080b  lea     rax, [rbp+Data]
0x18003080f  mov     [rbp+cbData], 4
0x180030816  xor     r8d, r8d; lpReserved
0x180030819  mov     [rsp+30h+phkResult], rax; lpData
0x18003081e  lea     rdx, aRoutertype; "RouterType"
0x180030825  call    cs:__imp_RegQueryValueExW
0x18003082b  test    eax, eax
0x18003082d  jnz     short loc_18003084E
0x18003082f  test    byte ptr [rbp+Data], 7
0x180030833  mov     dword ptr [rbx], 1
0x180030839  setnz   al
0x18003083c  test    byte ptr [rbp+Data], 38h
0x180030840  mov     [rbx+4], eax
0x180030843  mov     eax, 0
0x180030848  setnz   al
0x18003084b  mov     [rbx+8], eax
0x18003084e  mov     rcx, [rbp+hKey]; hKey
0x180030852  test    rcx, rcx
0x180030855  jz      short loc_18003085D
0x180030857  call    cs:__imp_RegCloseKey
0x18003085d  mov     rax, rbx
0x180030860  add     rsp, 30h
0x180030864  pop     rdi
0x180030865  pop     rbx
0x180030866  pop     rbp
0x180030867  retn
```
