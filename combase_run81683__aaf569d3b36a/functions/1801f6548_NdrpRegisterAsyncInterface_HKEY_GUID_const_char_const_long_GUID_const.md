# NdrpRegisterAsyncInterface(HKEY__ *,_GUID const &,char const *,long,_GUID const &)

- ea: `0x1801f6548`
- end: `0x1801f67fa`
- name: `?NdrpRegisterAsyncInterface@@YAJPEAUHKEY__@@AEBU_GUID@@PEBDJ1@Z`
- size: `690`
- prototype: `HRESULT __fastcall(HKEY__ *hKeyInterface, const _GUID *riid, const char *pszSyncInterfaceName, int SyncNumMethods, const _GUID *riidAsync)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18015abf0`

## callees

- `0x1801020cc`
- `0x1801999b0`
- `0x1801f6548`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x1801f66d1`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x1801f66d1`
- `RPCRT4!I_RpcFree` at `0x1801f6666`
- `RPCRT4!I_RpcFree` at `0x1801f6666`
- `RPCRT4!I_RpcAllocate` at `0x1801f6607`
- `RPCRT4!I_RpcAllocate` at `0x1801f6607`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1801f65dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1801f66ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1801f675d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1801f65dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1801f66ad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1801f675d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1801f665b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1801f670a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1801f67a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1801f665b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1801f670a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1801f67a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f67b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f67bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f6716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f67b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801f67bc`

## pseudocode

```c
__int64 __fastcall NdrpRegisterAsyncInterface(
        HKEY hKeyInterface,
        const _GUID *riid,
        const char *pszSyncInterfaceName,
        int SyncNumMethods,
        const _GUID *riidAsync)
{
  LSTATUS v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rax
  DWORD v12; // ebx
  char *v13; // rsi
  __int64 v14; // rax
  bool v15; // cc
  unsigned int dwDisposition; // [rsp+50h] [rbp-41h] BYREF
  HKEY__ *hKey; // [rsp+58h] [rbp-39h] BYREF
  HKEY__ *hKeyIID; // [rsp+60h] [rbp-31h] BYREF
  BYTE szNumMethods[8]; // [rsp+68h] [rbp-29h] BYREF
  BYTE szIID[40]; // [rsp+70h] [rbp-21h] BYREF

  dwDisposition = 0;
  hKey = 0;
  hKeyIID = 0;
  memset(szIID, 0, 39);
  NdrStringFromIID(riidAsync, (char *)szIID);
  v9 = RegCreateKeyExA(hKeyInterface, (LPCSTR)szIID, 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKeyIID, &dwDisposition);
  if ( v9 )
  {
    v15 = v9 < 0;
    goto LABEL_19;
  }
  v10 = -1;
  if ( !pszSyncInterfaceName )
    goto LABEL_8;
  v11 = -1;
  do
    ++v11;
  while ( pszSyncInterfaceName[v11] );
  v12 = v11 + 6;
  v13 = (char *)I_RpcAllocate((int)v11 + 6);
  if ( !v13 )
  {
    v9 = 14;
    goto LABEL_16;
  }
  qmemcpy(v13, "Async", 5);
  memcpy_0(v13 + 5, pszSyncInterfaceName, v12 - 5);
  v9 = RegSetValueExA(hKeyIID, Description4, 0, 1u, (const BYTE *)v13, v12);
  I_RpcFree(v13);
  if ( !v9 )
  {
LABEL_8:
    v9 = RegCreateKeyExA(hKeyIID, "NumMethods", 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKey, &dwDisposition);
    if ( !v9 )
    {
      _o__itoa_s((unsigned int)(2 * SyncNumMethods - 3), szNumMethods, 6, 10);
      v14 = -1;
      do
        ++v14;
      while ( szNumMethods[v14] );
      v9 = RegSetValueExA(hKey, Description4, 0, 1u, szNumMethods, v14 + 1);
      RegCloseKey(hKey);
      if ( !v9 )
      {
        v9 = RegCreateKeyExA(hKeyIID, "SynchronousInterface", 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKey, &dwDisposition);
        if ( !v9 )
        {
          NdrStringFromIID(riid, (char *)szIID);
          do
            ++v10;
          while ( szIID[v10] );
          v9 = RegSetValueExA(hKey, Description4, 0, 1u, szIID, v10 + 1);
          RegCloseKey(hKey);
        }
      }
    }
  }
LABEL_16:
  RegCloseKey(hKeyIID);
  v15 = v9 <= 0;
  if ( !v9 )
    return 0;
LABEL_19:
  if ( !v15 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1801f6548  push    rbp
0x1801f654a  push    rbx
0x1801f654b  push    rsi
0x1801f654c  push    rdi
0x1801f654d  push    r12
0x1801f654f  push    r13
0x1801f6551  push    r14
0x1801f6553  push    r15
0x1801f6555  lea     rbp, [rsp-17h]
0x1801f655a  sub     rsp, 0A8h
0x1801f6561  mov     rax, cs:__security_cookie
0x1801f6568  xor     rax, rsp
0x1801f656b  mov     [rbp+4Fh+var_48], rax
0x1801f656f  xorps   xmm0, xmm0
0x1801f6572  xor     r13d, r13d
0x1801f6575  mov     r12, riid
0x1801f6578  mov     [rbp+4Fh+dwDisposition], r13d
0x1801f657c  mov     rbx, hKeyInterface
0x1801f657f  mov     [rbp+4Fh+hKey], r13
0x1801f6583  mov     hKeyInterface, [rbp+4Fh+rclsid]; rclsid
0x1801f6587  lea     riid, [rbp+4Fh+szIID]; lpsz
0x1801f658b  xor     eax, eax
0x1801f658d  mov     [rbp+4Fh+hKeyIID], r13
0x1801f6591  movups  xmmword ptr [rbp+4Fh+szIID+10h], xmm0
0x1801f6595  mov     qword ptr [rbp+4Fh+szIID+1Fh], rax
0x1801f6599  mov     r15d, SyncNumMethods
0x1801f659c  mov     r14, pszSyncInterfaceName
0x1801f659f  movups  xmmword ptr [rbp+4Fh+szIID], xmm0
0x1801f65a3  call    NdrStringFromIID
0x1801f65a8  lea     rax, [rbp+4Fh+dwDisposition]
0x1801f65ac  xor     r8d, r8d; Reserved
0x1801f65af  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x1801f65b4  lea     r9, Class; "REG_SZ"
0x1801f65bb  lea     rax, [rbp+4Fh+hKeyIID]
0x1801f65bf  mov     hKeyInterface, rbx; hKey
0x1801f65c2  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1801f65c7  lea     riid, [rbp+4Fh+szIID]; lpSubKey
0x1801f65cb  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1801f65d0  mov     [rsp+0E0h+samDesired], 20006h; samDesired
0x1801f65d8  mov     [rsp+0E0h+dwOptions], r13d; dwOptions
0x1801f65dd  call    cs:__imp_RegCreateKeyExA
0x1801f65e3  mov     ebx, eax
0x1801f65e5  test    eax, eax
0x1801f65e7  jnz     loc_1801F67CB
0x1801f65ed  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801f65f1  test    r14, r14
0x1801f65f4  jz      short loc_1801F6674
0x1801f65f6  mov     rax, rdi
0x1801f65f9  inc     rax
0x1801f65fc  cmp     [r14+rax], r13b
0x1801f6600  jnz     short loc_1801F65F9
0x1801f6602  lea     ebx, [rax+6]
0x1801f6605  mov     ecx, ebx; Size
0x1801f6607  call    cs:__imp_I_RpcAllocate
0x1801f660d  mov     rsi, rax
0x1801f6610  test    rax, rax
0x1801f6613  jnz     short loc_1801F661D
0x1801f6615  lea     ebx, [rax+0Eh]
0x1801f6618  jmp     loc_1801F67B8
0x1801f661d  mov     eax, dword ptr cs:aAsync; "Async"
0x1801f6623  lea     r8d, [rbx-5]; Size
0x1801f6627  mov     [rsi], eax
0x1801f6629  lea     hKeyInterface, [rsi+5]; void *
0x1801f662d  mov     al, byte ptr cs:aAsync+4; "c"
0x1801f6633  mov     riid, r14; Src
0x1801f6636  mov     [rsi+4], al
0x1801f6639  call    memcpy_0
0x1801f663e  mov     hKeyInterface, [rbp+4Fh+hKeyIID]; hKey
0x1801f6642  lea     riid, Description4; lpValueName
0x1801f6649  mov     SyncNumMethods, 1; dwType
0x1801f664f  mov     [rsp+0E0h+samDesired], ebx; cbData
0x1801f6653  xor     r8d, r8d; Reserved
0x1801f6656  mov     qword ptr [rsp+0E0h+dwOptions], rsi; lpData
0x1801f665b  call    cs:__imp_RegSetValueExA
0x1801f6661  mov     hKeyInterface, rsi; Object
0x1801f6664  mov     ebx, eax
0x1801f6666  call    cs:__imp_I_RpcFree
0x1801f666c  test    ebx, ebx
0x1801f666e  jnz     loc_1801F67B8
0x1801f6674  mov     hKeyInterface, [rbp+4Fh+hKeyIID]; hKey
0x1801f6678  lea     rax, [rbp+4Fh+dwDisposition]
0x1801f667c  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x1801f6681  lea     r9, Class; "REG_SZ"
0x1801f6688  lea     rax, [rbp+4Fh+hKey]
0x1801f668c  xor     r8d, r8d; Reserved
0x1801f668f  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1801f6694  lea     riid, aNummethods; "NumMethods"
0x1801f669b  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1801f66a0  mov     [rsp+0E0h+samDesired], 20006h; samDesired
0x1801f66a8  mov     [rsp+0E0h+dwOptions], r13d; dwOptions
0x1801f66ad  call    cs:__imp_RegCreateKeyExA
0x1801f66b3  mov     ebx, eax
0x1801f66b5  test    eax, eax
0x1801f66b7  jnz     loc_1801F67B8
0x1801f66bd  lea     ecx, ds:0FFFFFFFFFFFFFFFDh[r15*2]
0x1801f66c5  lea     SyncNumMethods, [rax+0Ah]
0x1801f66c9  lea     r8d, [rax+6]
0x1801f66cd  lea     riid, [rbp+4Fh+szNumMethods]
0x1801f66d1  call    cs:__imp__o__itoa_s
0x1801f66d7  lea     hKeyInterface, [rbp+4Fh+szNumMethods]
0x1801f66db  mov     rax, rdi
0x1801f66de  inc     rax
0x1801f66e1  cmp     [hKeyInterface+rax], r13b
0x1801f66e5  jnz     short loc_1801F66DE
0x1801f66e7  mov     hKeyInterface, [rbp+4Fh+hKey]; hKey
0x1801f66eb  lea     riid, Description4; lpValueName
0x1801f66f2  inc     eax
0x1801f66f4  mov     SyncNumMethods, 1; dwType
0x1801f66fa  mov     [rsp+0E0h+samDesired], eax; cbData
0x1801f66fe  xor     r8d, r8d; Reserved
0x1801f6701  lea     rax, [rbp+4Fh+szNumMethods]
0x1801f6705  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x1801f670a  call    cs:__imp_RegSetValueExA
0x1801f6710  mov     hKeyInterface, [rbp+4Fh+hKey]; hKey
0x1801f6714  mov     ebx, eax
0x1801f6716  call    cs:__imp_RegCloseKey
0x1801f671c  test    ebx, ebx
0x1801f671e  jnz     loc_1801F67B8
0x1801f6724  mov     hKeyInterface, [rbp+4Fh+hKeyIID]; hKey
0x1801f6728  lea     rax, [rbp+4Fh+dwDisposition]
0x1801f672c  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x1801f6731  lea     r9, Class; "REG_SZ"
0x1801f6738  lea     rax, [rbp+4Fh+hKey]
0x1801f673c  xor     r8d, r8d; Reserved
0x1801f673f  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1801f6744  lea     riid, aSynchronousint_1; "SynchronousInterface"
0x1801f674b  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1801f6750  mov     [rsp+0E0h+samDesired], 20006h; samDesired
0x1801f6758  mov     [rsp+0E0h+dwOptions], r13d; dwOptions
0x1801f675d  call    cs:__imp_RegCreateKeyExA
0x1801f6763  mov     ebx, eax
0x1801f6765  test    eax, eax
0x1801f6767  jnz     short loc_1801F67B8
0x1801f6769  lea     riid, [rbp+4Fh+szIID]; lpsz
0x1801f676d  mov     hKeyInterface, r12; rclsid
0x1801f6770  call    NdrStringFromIID
0x1801f6775  lea     rax, [rbp+4Fh+szIID]
0x1801f6779  inc     rdi
0x1801f677c  cmp     [rax+rdi], r13b
0x1801f6780  jnz     short loc_1801F6779
0x1801f6782  mov     hKeyInterface, [rbp+4Fh+hKey]; hKey
0x1801f6786  lea     eax, [rdi+1]
0x1801f6789  mov     [rsp+0E0h+samDesired], eax; cbData
0x1801f678d  lea     riid, Description4; lpValueName
0x1801f6794  lea     rax, [rbp+4Fh+szIID]
0x1801f6798  mov     SyncNumMethods, 1; dwType
0x1801f679e  xor     r8d, r8d; Reserved
0x1801f67a1  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x1801f67a6  call    cs:__imp_RegSetValueExA
0x1801f67ac  mov     hKeyInterface, [rbp+4Fh+hKey]; hKey
0x1801f67b0  mov     ebx, eax
0x1801f67b2  call    cs:__imp_RegCloseKey
0x1801f67b8  mov     hKeyInterface, [rbp+4Fh+hKeyIID]; hKey
0x1801f67bc  call    cs:__imp_RegCloseKey
0x1801f67c2  test    ebx, ebx
0x1801f67c4  jnz     short loc_1801F67CD
0x1801f67c6  mov     ebx, r13d
0x1801f67c9  jmp     short loc_1801F67D8
0x1801f67cb  test    ebx, ebx
0x1801f67cd  jle     short loc_1801F67D8
0x1801f67cf  movzx   ebx, bx
0x1801f67d2  or      ebx, 80070000h
0x1801f67d8  mov     eax, ebx
0x1801f67da  mov     hKeyInterface, [rbp+4Fh+var_48]
0x1801f67de  xor     hKeyInterface, rsp; StackCookie
0x1801f67e1  call    __security_check_cookie
0x1801f67e6  add     rsp, 0A8h
0x1801f67ed  pop     r15
0x1801f67ef  pop     r14
0x1801f67f1  pop     r13
0x1801f67f3  pop     r12
0x1801f67f5  pop     rdi
0x1801f67f6  pop     rsi
0x1801f67f7  pop     rbx
0x1801f67f8  pop     rbp
0x1801f67f9  retn
```
