# CONFIG_PATH_MAPPER::GetFxInstallPathByRegistry(STRU *,int)

- ea: `0x180052acc`
- end: `0x180052c4e`
- name: `?GetFxInstallPathByRegistry@CONFIG_PATH_MAPPER@@CAJPEAVSTRU@@H@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct STRU *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180052c54`

## callees

- `0x180052acc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052b70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052bbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052b70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052bbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052b37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052b37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052c39`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180052ae6`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180052ae6`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180052c2a`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180052c2a`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180052b83`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180052c08`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180052b83`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180052c08`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052b4a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052b96`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052bed`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052c17`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052b4a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052b96`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052bed`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052c17`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180052aef`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180052aef`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180052afe`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180052bc9`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180052afe`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180052bc9`

## string_xrefs

- `0x180052b64`: `InstallRoot`
- `0x180052bb0`: `InstallRoot`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::GetFxInstallPathByRegistry(struct STRU *a1, int a2)
{
  BUFFER *Buffer; // rax
  DWORD Size; // eax
  int v6; // ebx
  const WCHAR *v7; // rdx
  int v8; // ebx
  BYTE *Str; // rax
  LSTATUS v10; // eax
  BYTE *v11; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rax
  DWORD cbData; // [rsp+58h] [rbp+28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  hKey = 0;
  Buffer = STRU::QueryBuffer(a1);
  Size = BUFFER::QuerySize(Buffer);
  Type = 0;
  cbData = Size;
  STRU::Reset(a1);
  v6 = -a2;
  v7 = L"Software\\Microsoft\\.NETFramework";
  if ( ((unsigned __int64)L"SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework" & -(__int64)(v6 != 0)) != 0 )
    v7 = (const WCHAR *)((unsigned __int64)L"SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework" & -(__int64)(v6 != 0));
  v8 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey) )
  {
    Str = (BYTE *)STRU::QueryStr(a1);
    v10 = RegQueryValueExW(hKey, L"InstallRoot", 0, &Type, Str, &cbData);
    if ( v10 == 234 )
    {
      v8 = STRU::Resize(a1, cbData);
      if ( v8 < 0 )
        goto LABEL_16;
      v11 = (BYTE *)STRU::QueryStr(a1);
      v10 = RegQueryValueExW(hKey, L"InstallRoot", 0, &Type, v11, &cbData);
    }
    if ( v10 )
    {
      STRU::Reset(a1);
      v8 = 0;
      goto LABEL_16;
    }
    if ( Type - 1 > 1 || cbData < 2 )
    {
      v8 = -2147024883;
      goto LABEL_16;
    }
    v12 = STRU::QueryStr(a1);
    if ( v12[((unsigned __int64)cbData >> 1) - 1] )
    {
      v8 = STRU::Resize(a1, cbData + 2);
      if ( v8 < 0 )
        goto LABEL_16;
      v13 = STRU::QueryStr(a1);
      v13[(unsigned __int64)cbData >> 1] = 0;
    }
    STRU::SyncWithBuffer(a1);
  }
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180052acc  mov     [rsp-18h+arg_0], rbx
0x180052ad1  push    rbp
0x180052ad2  push    rsi
0x180052ad3  push    rdi
0x180052ad4  mov     rbp, rsp
0x180052ad7  sub     rsp, 30h
0x180052adb  xor     esi, esi
0x180052add  mov     ebx, edx
0x180052adf  mov     [rbp+hKey], rsi
0x180052ae3  mov     rdi, rcx
0x180052ae6  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180052aec  mov     rcx, rax
0x180052aef  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180052af5  mov     rcx, rdi
0x180052af8  mov     [rbp+Type], esi
0x180052afb  mov     [rbp+cbData], eax
0x180052afe  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180052b04  neg     ebx
0x180052b06  lea     rcx, aSoftwareWow643; "SOFTWARE\\Wow6432Node\\Microsoft\\.NETF"...
0x180052b0d  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\.NETFramework"
0x180052b14  mov     r9d, 20019h; samDesired
0x180052b1a  sbb     rax, rax
0x180052b1d  and     rax, rcx
0x180052b20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052b27  cmovnz  rdx, rax; lpSubKey
0x180052b2b  lea     rax, [rbp+hKey]
0x180052b2f  xor     r8d, r8d; ulOptions
0x180052b32  mov     [rsp+30h+phkResult], rax; phkResult
0x180052b37  call    cs:__imp_RegOpenKeyExW
0x180052b3d  mov     ebx, esi
0x180052b3f  test    eax, eax
0x180052b41  jnz     loc_180052C30
0x180052b47  mov     rcx, rdi
0x180052b4a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052b50  lea     rcx, [rbp+cbData]
0x180052b54  xor     r8d, r8d; lpReserved
0x180052b57  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180052b5c  lea     r9, [rbp+Type]; lpType
0x180052b60  mov     rcx, [rbp+hKey]; hKey
0x180052b64  lea     rdx, aInstallroot; "InstallRoot"
0x180052b6b  mov     [rsp+30h+phkResult], rax; lpData
0x180052b70  call    cs:__imp_RegQueryValueExW
0x180052b76  cmp     eax, 0EAh
0x180052b7b  jnz     short loc_180052BC2
0x180052b7d  mov     edx, [rbp+cbData]
0x180052b80  mov     rcx, rdi
0x180052b83  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180052b89  mov     ebx, eax
0x180052b8b  test    eax, eax
0x180052b8d  js      loc_180052C30
0x180052b93  mov     rcx, rdi
0x180052b96  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052b9c  lea     rcx, [rbp+cbData]
0x180052ba0  xor     r8d, r8d; lpReserved
0x180052ba3  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180052ba8  lea     r9, [rbp+Type]; lpType
0x180052bac  mov     rcx, [rbp+hKey]; hKey
0x180052bb0  lea     rdx, aInstallroot; "InstallRoot"
0x180052bb7  mov     [rsp+30h+phkResult], rax; lpData
0x180052bbc  call    cs:__imp_RegQueryValueExW
0x180052bc2  test    eax, eax
0x180052bc4  jz      short loc_180052BD3
0x180052bc6  mov     rcx, rdi
0x180052bc9  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180052bcf  mov     ebx, esi
0x180052bd1  jmp     short loc_180052C30
0x180052bd3  mov     eax, [rbp+Type]
0x180052bd6  dec     eax
0x180052bd8  cmp     eax, 1
0x180052bdb  jbe     short loc_180052BE4
0x180052bdd  mov     ebx, 8007000Dh
0x180052be2  jmp     short loc_180052C30
0x180052be4  cmp     [rbp+cbData], 2
0x180052be8  jb      short loc_180052BDD
0x180052bea  mov     rcx, rdi
0x180052bed  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052bf3  mov     edx, [rbp+cbData]
0x180052bf6  mov     ecx, edx
0x180052bf8  shr     rcx, 1
0x180052bfb  cmp     [rax+rcx*2-2], si
0x180052c00  jz      short loc_180052C27
0x180052c02  add     edx, 2
0x180052c05  mov     rcx, rdi
0x180052c08  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180052c0e  mov     ebx, eax
0x180052c10  test    eax, eax
0x180052c12  js      short loc_180052C30
0x180052c14  mov     rcx, rdi
0x180052c17  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052c1d  mov     edx, [rbp+cbData]
0x180052c20  shr     rdx, 1
0x180052c23  mov     [rax+rdx*2], si
0x180052c27  mov     rcx, rdi
0x180052c2a  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180052c30  mov     rcx, [rbp+hKey]; hKey
0x180052c34  test    rcx, rcx
0x180052c37  jz      short loc_180052C3F
0x180052c39  call    cs:__imp_RegCloseKey
0x180052c3f  mov     eax, ebx
0x180052c41  mov     rbx, [rsp+30h+arg_0]
0x180052c46  add     rsp, 30h
0x180052c4a  pop     rdi
0x180052c4b  pop     rsi
0x180052c4c  pop     rbp
0x180052c4d  retn
```
