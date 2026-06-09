# P2P_PEER_DIST_API::GetPeerDistDLLPath(ushort *,uint)

- ea: `0x180093c60`
- end: `0x180093dbb`
- name: `?GetPeerDistDLLPath@P2P_PEER_DIST_API@@AEAAKPEAGI@Z`
- size: `347`
- prototype: `__int64 __fastcall(P2P_PEER_DIST_API *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180084f90`

## callees

- `0x180093c60`
- `0x1800a3420`
- `0x1800f9960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180093cee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180093cee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093d1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093d1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093cb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180093cb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180093d31`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180093d31`

## string_xrefs

- `0x180093c94`: `Software\Microsoft\Windows NT\CurrentVersion\PeerDist\Extension`
- `0x180093ce2`: `PeerdistDllName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall P2P_PEER_DIST_API::GetPeerDistDLLPath(P2P_PEER_DIST_API *this, unsigned __int16 *a2)
{
  DWORD v3; // edi
  unsigned int ValueW; // ebx
  UINT SystemDirectoryW; // eax
  __int64 v6; // rbx
  DWORD v7; // esi
  DWORD pcbData; // [rsp+40h] [rbp-258h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-250h] BYREF
  _BYTE Src[528]; // [rsp+50h] [rbp-248h] BYREF

  pcbData = 520;
  *a2 = 0;
  hkey = 0;
  v3 = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist\\Extension",
             0,
             0x20119u,
             &hkey);
  if ( !ValueW )
  {
    ValueW = RegGetValueW(hkey, 0, L"PeerdistDllName", 2u, 0, Src, &pcbData);
    if ( !ValueW )
    {
      if ( (pcbData & 1) != 0 || !pcbData )
        ValueW = 13;
      else
        v3 = (pcbData >> 1) - 1;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  if ( !ValueW )
  {
    SystemDirectoryW = GetSystemDirectoryW(a2, 0x104u);
    v6 = SystemDirectoryW;
    if ( SystemDirectoryW )
    {
      if ( SystemDirectoryW > 0x104 || v3 + SystemDirectoryW + 2 > 0x104 )
      {
        return 122;
      }
      else
      {
        if ( a2[SystemDirectoryW - 1] != 92 )
        {
          a2[SystemDirectoryW] = 92;
          v6 = SystemDirectoryW + 1;
        }
        v7 = 0;
        if ( v3 )
        {
          memcpy_0(&a2[v6], Src, 2LL * v3);
          do
          {
            v6 = (unsigned int)(v6 + 1);
            ++v7;
          }
          while ( v7 < v3 );
        }
        a2[v6] = 0;
        return 0;
      }
    }
    else
    {
      return GetLastError();
    }
  }
  return ValueW;
}

```

## disassembly

```asm
0x180093c60  push    rbx
0x180093c62  push    rsi
0x180093c63  push    rdi
0x180093c64  push    r14
0x180093c66  sub     rsp, 278h
0x180093c6d  mov     rax, cs:__security_cookie
0x180093c74  xor     rax, rsp
0x180093c77  mov     [rsp+298h+var_38], rax
0x180093c7f  xor     eax, eax
0x180093c81  mov     [rsp+298h+var_258], 208h
0x180093c89  mov     [rdx], ax
0x180093c8c  mov     r14, rdx
0x180093c8f  mov     [rsp+298h+hkey], rax
0x180093c94  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180093c9b  lea     rax, [rsp+298h+hkey]
0x180093ca0  mov     r9d, 20119h; samDesired
0x180093ca6  xor     r8d, r8d; ulOptions
0x180093ca9  mov     [rsp+298h+phkResult], rax; phkResult
0x180093cae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180093cb5  xor     edi, edi
0x180093cb7  call    cs:__imp_RegOpenKeyExW
0x180093cbd  mov     ebx, eax
0x180093cbf  test    eax, eax
0x180093cc1  jnz     short loc_180093D13
0x180093cc3  mov     rcx, [rsp+298h+hkey]; hkey
0x180093cc8  lea     rax, [rsp+298h+var_258]
0x180093ccd  mov     [rsp+298h+pcbData], rax; pcbData
0x180093cd2  lea     r9d, [rdi+2]; dwFlags
0x180093cd6  lea     rax, [rsp+298h+Src]
0x180093cdb  xor     edx, edx; lpSubKey
0x180093cdd  mov     [rsp+298h+pvData], rax; pvData
0x180093ce2  lea     r8, Value; "PeerdistDllName"
0x180093ce9  mov     [rsp+298h+phkResult], rdi; pdwType
0x180093cee  call    cs:__imp_RegGetValueW
0x180093cf4  mov     ebx, eax
0x180093cf6  test    eax, eax
0x180093cf8  jnz     short loc_180093D13
0x180093cfa  mov     eax, [rsp+298h+var_258]
0x180093cfe  test    al, 1
0x180093d00  jnz     short loc_180093D0E
0x180093d02  test    eax, eax
0x180093d04  jz      short loc_180093D0E
0x180093d06  mov     edi, eax
0x180093d08  shr     edi, 1
0x180093d0a  dec     edi
0x180093d0c  jmp     short loc_180093D13
0x180093d0e  mov     ebx, 0Dh
0x180093d13  mov     rcx, [rsp+298h+hkey]; hKey
0x180093d18  test    rcx, rcx
0x180093d1b  jz      short loc_180093D23
0x180093d1d  call    cs:__imp_RegCloseKey
0x180093d23  test    ebx, ebx
0x180093d25  jnz     short loc_180093D9C
0x180093d27  mov     esi, 104h
0x180093d2c  mov     rcx, r14; lpBuffer
0x180093d2f  mov     edx, esi; uSize
0x180093d31  call    cs:__imp_GetSystemDirectoryW
0x180093d37  mov     ebx, eax
0x180093d39  test    eax, eax
0x180093d3b  jnz     short loc_180093D47
0x180093d3d  call    cs:__imp_GetLastError
0x180093d43  mov     ebx, eax
0x180093d45  jmp     short loc_180093D9C
0x180093d47  cmp     ebx, esi
0x180093d49  ja      short loc_180093D97
0x180093d4b  lea     eax, [rbx+2]
0x180093d4e  add     eax, edi
0x180093d50  cmp     eax, esi
0x180093d52  ja      short loc_180093D97
0x180093d54  lea     eax, [rbx-1]
0x180093d57  mov     edx, 5Ch ; '\'
0x180093d5c  cmp     [r14+rax*2], dx
0x180093d61  jz      short loc_180093D6A
0x180093d63  mov     [r14+rbx*2], dx
0x180093d68  inc     ebx
0x180093d6a  xor     esi, esi
0x180093d6c  test    edi, edi
0x180093d6e  jz      short loc_180093D8C
0x180093d70  mov     r8d, edi
0x180093d73  lea     rcx, [r14+rbx*2]; void *
0x180093d77  add     r8, r8; Size
0x180093d7a  lea     rdx, [rsp+298h+Src]; Src
0x180093d7f  call    memcpy_0
0x180093d84  inc     ebx
0x180093d86  inc     esi
0x180093d88  cmp     esi, edi
0x180093d8a  jb      short loc_180093D84
0x180093d8c  xor     eax, eax
0x180093d8e  mov     [r14+rbx*2], ax
0x180093d93  xor     ebx, ebx
0x180093d95  jmp     short loc_180093D9C
0x180093d97  mov     ebx, 7Ah ; 'z'
0x180093d9c  mov     eax, ebx
0x180093d9e  mov     rcx, [rsp+298h+var_38]
0x180093da6  xor     rcx, rsp; StackCookie
0x180093da9  call    __security_check_cookie
0x180093dae  add     rsp, 278h
0x180093db5  pop     r14
0x180093db7  pop     rdi
0x180093db8  pop     rsi
0x180093db9  pop     rbx
0x180093dba  retn
```
