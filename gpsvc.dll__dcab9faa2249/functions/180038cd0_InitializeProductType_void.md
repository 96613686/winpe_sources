# InitializeProductType(void)

- ea: `0x180038cd0`
- end: `0x180038ffb`
- name: `?InitializeProductType@@YAXXZ`
- size: `811`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038b40`

## callees

- `0x180038cd0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180038dac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180038ecf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180038f0e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180038dac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180038ecf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180038f0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038d75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038d75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038d25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038d25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038d68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038d68`

## string_xrefs

- `0x180038e02`: `InitializeProductType: Failed to open registry (%d)`
- `0x180038e2d`: `InitializeProductType: Failed to open registry (%d)`

## pseudocode

```c
void InitializeProductType(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  DWORD cbData; // [rsp+30h] [rbp-98h] BYREF
  DWORD Type; // [rsp+34h] [rbp-94h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-90h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-88h] BYREF

  g_ProductType = 1;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProductOptions", 0, 0x20019u, &hKey);
  if ( v0 )
  {
    if ( !*(_DWORD *)&g_dwDebugLevel )
      return;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"InitializeProductType: Failed to open registry (%d)", v0);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"InitializeProductType: Failed to open registry (%d)", v0);
    }
  }
  else
  {
    cbData = 50;
    *(_WORD *)Data = 0;
    v1 = RegQueryValueExW(hKey, L"ProductType", 0, &Type, Data, &cbData);
    RegCloseKey(hKey);
    if ( v1 )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        return;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"InitializeProductType: Failed to query product type (%d)", v1);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"InitializeProductType: Failed to query product type (%d)", v1);
      }
    }
    else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"WinNT", -1) == 2 )
    {
      g_ProductType = 1;
    }
    else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"ServerNT", -1) == 2 )
    {
      g_ProductType = 2;
    }
    else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, L"LanmanNT", -1) == 2 )
    {
      g_ProductType = 4;
    }
    else
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        return;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"InitializeProductType: Unknown product type! <%s>", Data);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"InitializeProductType: Unknown product type! <%s>", Data);
      }
    }
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"InitializeProductType: Product Type: %d", g_ProductType);
    }
    else if ( g_lpDebugMsgContextInstance )
    {
      if ( g_lpDebugMsgContext )
        RedirectDebugMsg(4u, L"InitializeProductType: Product Type: %d", g_ProductType);
    }
  }
}

```

## disassembly

```asm
0x180038cd0  push    rbx
0x180038cd2  sub     rsp, 0C0h
0x180038cd9  mov     rax, cs:__security_cookie
0x180038ce0  xor     rax, rsp
0x180038ce3  mov     [rsp+0C8h+var_18], rax
0x180038ceb  xor     ebx, ebx
0x180038ced  mov     cs:?g_ProductType@@3W4NTPRODUCTTYPE@@A, 1; NTPRODUCTTYPE g_ProductType
0x180038cf7  lea     rax, [rsp+0C8h+hKey]
0x180038cfc  mov     [rsp+0C8h+hKey], rbx
0x180038d01  mov     r9d, 20019h; samDesired
0x180038d07  mov     [rsp+0C8h+Type], ebx
0x180038d0b  xor     r8d, r8d; ulOptions
0x180038d0e  mov     [rsp+0C8h+cbData], ebx
0x180038d12  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Pro"...
0x180038d19  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180038d1e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038d25  call    cs:__imp_RegOpenKeyExW
0x180038d2b  test    eax, eax
0x180038d2d  jnz     loc_180038DEB
0x180038d33  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180038d38  lea     rax, [rsp+0C8h+cbData]
0x180038d3d  mov     [rsp+0C8h+lpcbData], rax; lpcbData
0x180038d42  lea     r9, [rsp+0C8h+Type]; lpType
0x180038d47  lea     rax, [rsp+0C8h+Data]
0x180038d4c  mov     [rsp+0C8h+cbData], 32h ; '2'
0x180038d54  xor     r8d, r8d; lpReserved
0x180038d57  mov     [rsp+0C8h+phkResult], rax; lpData
0x180038d5c  lea     rdx, aProducttype; "ProductType"
0x180038d63  mov     word ptr [rsp+0C8h+Data], bx
0x180038d68  call    cs:__imp_RegQueryValueExW
0x180038d6e  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180038d73  mov     ebx, eax
0x180038d75  call    cs:__imp_RegCloseKey
0x180038d7b  test    ebx, ebx
0x180038d7d  jnz     loc_180038E40
0x180038d83  lea     rax, aWinnt; "WinNT"
0x180038d8a  mov     dword ptr [rsp+0C8h+lpcbData], 0FFFFFFFFh; cchCount2
0x180038d92  mov     r9d, 0FFFFFFFFh; cchCount1
0x180038d98  mov     [rsp+0C8h+phkResult], rax; lpString2
0x180038d9d  lea     r8, [rsp+0C8h+Data]; lpString1
0x180038da2  mov     edx, 1; dwCmpFlags
0x180038da7  mov     ecx, 7Fh; Locale
0x180038dac  call    cs:__imp_CompareStringW
0x180038db2  cmp     eax, 2
0x180038db5  jnz     loc_180038EA6
0x180038dbb  mov     cs:?g_ProductType@@3W4NTPRODUCTTYPE@@A, 1; NTPRODUCTTYPE g_ProductType
0x180038dc5  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180038dcc  jnz     loc_180038F96
0x180038dd2  mov     rcx, [rsp+0C8h+var_18]
0x180038dda  xor     rcx, rsp; StackCookie
0x180038ddd  call    __security_check_cookie
0x180038de2  add     rsp, 0C0h
0x180038de9  pop     rbx
0x180038dea  retn
0x180038deb  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x180038df1  jz      short loc_180038DD2
0x180038df3  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180038dfa  test    r9, r9
0x180038dfd  jz      short loc_180038E18
0x180038dff  mov     r8d, eax
0x180038e02  lea     rdx, aInitializeprod_2; "InitializeProductType: Failed to open r"...
0x180038e09  mov     rax, r9
0x180038e0c  mov     ecx, 2
0x180038e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e16  jmp     short loc_180038DC5
0x180038e18  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rbx; void * g_lpDebugMsgContextInstance
0x180038e1f  jz      short loc_180038DC5
0x180038e21  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rbx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180038e28  jz      short loc_180038DC5
0x180038e2a  mov     r8d, eax
0x180038e2d  lea     rdx, aInitializeprod_2; "InitializeProductType: Failed to open r"...
0x180038e34  mov     ecx, 2; unsigned int
0x180038e39  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180038e3e  jmp     short loc_180038DC5
0x180038e40  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180038e47  jz      short loc_180038DD2
0x180038e49  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180038e50  test    r9, r9
0x180038e53  jz      short loc_180038E71
0x180038e55  mov     r8d, ebx
0x180038e58  lea     rdx, aInitializeprod_1; "InitializeProductType: Failed to query "...
0x180038e5f  mov     ecx, 2
0x180038e64  mov     rax, r9
0x180038e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e6c  jmp     loc_180038DC5
0x180038e71  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180038e79  jz      loc_180038DC5
0x180038e7f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180038e87  jz      loc_180038DC5
0x180038e8d  mov     r8d, ebx
0x180038e90  lea     rdx, aInitializeprod_1; "InitializeProductType: Failed to query "...
0x180038e97  mov     ecx, 2; unsigned int
0x180038e9c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180038ea1  jmp     loc_180038DC5
0x180038ea6  lea     rax, aServernt; "ServerNT"
0x180038ead  mov     dword ptr [rsp+0C8h+lpcbData], 0FFFFFFFFh; cchCount2
0x180038eb5  mov     r9d, 0FFFFFFFFh; cchCount1
0x180038ebb  mov     [rsp+0C8h+phkResult], rax; lpString2
0x180038ec0  lea     r8, [rsp+0C8h+Data]; lpString1
0x180038ec5  mov     edx, 1; dwCmpFlags
0x180038eca  mov     ecx, 7Fh; Locale
0x180038ecf  call    cs:__imp_CompareStringW
0x180038ed5  cmp     eax, 2
0x180038ed8  jnz     short loc_180038EE5
0x180038eda  mov     cs:?g_ProductType@@3W4NTPRODUCTTYPE@@A, eax; NTPRODUCTTYPE g_ProductType
0x180038ee0  jmp     loc_180038DC5
0x180038ee5  lea     rax, aLanmannt; "LanmanNT"
0x180038eec  mov     dword ptr [rsp+0C8h+lpcbData], 0FFFFFFFFh; cchCount2
0x180038ef4  mov     r9d, 0FFFFFFFFh; cchCount1
0x180038efa  mov     [rsp+0C8h+phkResult], rax; lpString2
0x180038eff  lea     r8, [rsp+0C8h+Data]; lpString1
0x180038f04  mov     edx, 1; dwCmpFlags
0x180038f09  mov     ecx, 7Fh; Locale
0x180038f0e  call    cs:__imp_CompareStringW
0x180038f14  cmp     eax, 2
0x180038f17  jnz     short loc_180038F28
0x180038f19  mov     cs:?g_ProductType@@3W4NTPRODUCTTYPE@@A, 4; NTPRODUCTTYPE g_ProductType
0x180038f23  jmp     loc_180038DC5
0x180038f28  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180038f2f  jz      loc_180038DD2
0x180038f35  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180038f3c  test    r9, r9
0x180038f3f  jz      short loc_180038F5F
0x180038f41  lea     r8, [rsp+0C8h+Data]
0x180038f46  mov     ecx, 2
0x180038f4b  lea     rdx, aInitializeprod_0; "InitializeProductType: Unknown product "...
0x180038f52  mov     rax, r9
0x180038f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f5a  jmp     loc_180038DC5
0x180038f5f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180038f67  jz      loc_180038DC5
0x180038f6d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180038f75  jz      loc_180038DC5
0x180038f7b  lea     r8, [rsp+0C8h+Data]
0x180038f80  mov     ecx, 2; unsigned int
0x180038f85  lea     rdx, aInitializeprod_0; "InitializeProductType: Unknown product "...
0x180038f8c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180038f91  jmp     loc_180038DC5
0x180038f96  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180038f9d  test    r9, r9
0x180038fa0  jz      short loc_180038FC2
0x180038fa2  mov     r8d, cs:?g_ProductType@@3W4NTPRODUCTTYPE@@A; NTPRODUCTTYPE g_ProductType
0x180038fa9  lea     rdx, aInitializeprod; "InitializeProductType: Product Type: %d"
0x180038fb0  mov     ecx, 4
0x180038fb5  mov     rax, r9
0x180038fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fbd  jmp     loc_180038DD2
0x180038fc2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180038fca  jz      loc_180038DD2
0x180038fd0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180038fd8  jz      loc_180038DD2
0x180038fde  mov     r8d, cs:?g_ProductType@@3W4NTPRODUCTTYPE@@A; NTPRODUCTTYPE g_ProductType
0x180038fe5  lea     rdx, aInitializeprod; "InitializeProductType: Product Type: %d"
0x180038fec  mov     ecx, 4; unsigned int
0x180038ff1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180038ff6  jmp     loc_180038DD2
```
