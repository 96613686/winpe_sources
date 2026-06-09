# ConfigUnregister(x,x,x,x)

- ea: `0x100252b0`
- end: `0x100254a5`
- name: `_ConfigUnregister@16`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10006840`

## callees

- `0x10006400`
- `0x10018b80`
- `0x100252b0`
- `0x100331da`
- `0x10033488`
- `0x1003363d`
- `0x1003399e`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100253a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10025421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10025498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x100253a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10025421`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10025498`

## pseudocode

```c
int __stdcall ConfigUnregister(int a1, int **a2)
{
  LPCWSTR *v3; // edi
  int InfoKeyW; // esi
  int v6; // esi
  int v7; // [esp+Ch] [ebp-218h] BYREF
  HKEY hKey; // [esp+10h] [ebp-214h] BYREF
  WCHAR SubKey[262]; // [esp+14h] [ebp-210h] BYREF

  v3 = (LPCWSTR *)off_10038830;
  WCSCPY2(SubKey, L"Software\\Microsoft\\Jet\\4.0", 0x105u);
  WCSCAT2(SubKey, L"\\", 0x105u);
  WCSCAT2(SubKey, L"Engines", 0x105u);
  WCSCAT2(SubKey, L"\\", 0x105u);
  WCSCAT2(SubKey, lpSubKey, 0x105u);
  if ( JetRegOpenKeyW(HKEY_LOCAL_MACHINE, SubKey, &hKey) )
    return -1;
  while ( 1 )
  {
    a2 = (int **)*a2;
    if ( !a2 )
      break;
    JetRegDeleteValueW(hKey, (LPCWSTR)a2[2]);
  }
  JetRegDeleteValueW(hKey, L"win32");
  InfoKeyW = JetRegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, (int)&v7, 0, 0, 0, 0);
  RegCloseKey(hKey);
  if ( InfoKeyW )
    return -1;
  if ( !v7 )
  {
    WCSCPY2(SubKey, L"Software\\Microsoft\\Jet\\4.0", 0x105u);
    WCSCAT2(SubKey, L"\\", 0x105u);
    WCSCAT2(SubKey, L"Engines", 0x105u);
    if ( JetRegOpenKeyW(HKEY_LOCAL_MACHINE, SubKey, &hKey) )
      return -1;
    JetRegDeleteKeyW(hKey, lpSubKey);
    RegCloseKey(hKey);
  }
  WCSCPY2(SubKey, L"Software\\Microsoft\\Jet\\4.0", 0x105u);
  WCSCAT2(SubKey, L"\\", 0x105u);
  WCSCAT2(SubKey, L"ISAM Formats", 0x105u);
  if ( JetRegOpenKeyW(HKEY_LOCAL_MACHINE, SubKey, &hKey) )
    return -1;
  v6 = 4;
  do
  {
    JetRegDeleteKeyW(hKey, *v3);
    v3 += 13;
    --v6;
  }
  while ( v6 );
  RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x100252b0  mov     edi, edi
0x100252b2  push    ebp
0x100252b3  mov     ebp, esp
0x100252b5  sub     esp, 218h
0x100252bb  mov     eax, ___security_cookie
0x100252c0  xor     eax, ebp
0x100252c2  mov     [ebp+var_4], eax
0x100252c5  push    ebx
0x100252c6  push    esi
0x100252c7  mov     esi, [ebp+arg_4]
0x100252ca  lea     ecx, [ebp+SubKey]
0x100252d0  push    edi
0x100252d1  mov     ebx, 105h
0x100252d6  mov     edx, offset aSoftwareMicros; "Software\\Microsoft\\Jet\\4.0"
0x100252db  push    ebx
0x100252dc  mov     edi, offset off_10038830; "Excel 5.0"
0x100252e1  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100252e6  push    ebx
0x100252e7  mov     edx, offset asc_1000539C; "\\"
0x100252ec  lea     ecx, [ebp+SubKey]
0x100252f2  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100252f7  push    ebx
0x100252f8  mov     edx, offset aEngines_0; "Engines"
0x100252fd  lea     ecx, [ebp+SubKey]
0x10025303  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10025308  push    ebx
0x10025309  mov     edx, offset asc_1000539C; "\\"
0x1002530e  lea     ecx, [ebp+SubKey]
0x10025314  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10025319  mov     edx, lpSubKey
0x1002531f  lea     ecx, [ebp+SubKey]
0x10025325  push    ebx
0x10025326  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002532b  lea     eax, [ebp+hKey]
0x10025331  push    eax; phkResult
0x10025332  lea     eax, [ebp+SubKey]
0x10025338  push    eax; lpSubKey
0x10025339  push    80000002h; hKey
0x1002533e  call    _JetRegOpenKeyW@12; JetRegOpenKeyW(x,x,x)
0x10025343  test    eax, eax
0x10025345  jz      short loc_10025369
0x10025347  or      eax, 0FFFFFFFFh
0x1002534a  mov     ecx, [ebp+var_4]
0x1002534d  pop     edi
0x1002534e  pop     esi
0x1002534f  xor     ecx, ebp; StackCookie
0x10025351  pop     ebx
0x10025352  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10025357  leave
0x10025358  retn    8
0x1002535b  push    dword ptr [esi+8]; lpValueName
0x1002535e  push    [ebp+hKey]; hKey
0x10025364  call    _JetRegDeleteValueW@8; JetRegDeleteValueW(x,x)
0x10025369  mov     esi, [esi]
0x1002536b  test    esi, esi
0x1002536d  jnz     short loc_1002535B
0x1002536f  push    offset aWin32; "win32"
0x10025374  push    [ebp+hKey]; hKey
0x1002537a  call    _JetRegDeleteValueW@8; JetRegDeleteValueW(x,x)
0x1002537f  xor     ecx, ecx
0x10025381  lea     eax, [ebp+var_218]
0x10025387  push    ecx; int
0x10025388  push    ecx; int
0x10025389  push    ecx; int
0x1002538a  push    ecx; int
0x1002538b  push    eax; int
0x1002538c  push    ecx; int
0x1002538d  push    ecx; lpcbMaxSubKeyLen
0x1002538e  push    ecx; int
0x1002538f  push    ecx; lpReserved
0x10025390  push    ecx; lpcchClass
0x10025391  push    ecx; lpClass
0x10025392  push    [ebp+hKey]; hKey
0x10025398  call    _JetRegQueryInfoKeyW@48; JetRegQueryInfoKeyW(x,x,x,x,x,x,x,x,x,x,x,x)
0x1002539d  push    [ebp+hKey]; hKey
0x100253a3  mov     esi, eax
0x100253a5  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100253ab  test    esi, esi
0x100253ad  jnz     short loc_10025347
0x100253af  cmp     [ebp+var_218], esi
0x100253b5  jnz     short loc_10025427
0x100253b7  push    ebx
0x100253b8  mov     edx, offset aSoftwareMicros; "Software\\Microsoft\\Jet\\4.0"
0x100253bd  lea     ecx, [ebp+SubKey]
0x100253c3  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100253c8  push    ebx
0x100253c9  mov     edx, offset asc_1000539C; "\\"
0x100253ce  lea     ecx, [ebp+SubKey]
0x100253d4  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100253d9  push    ebx
0x100253da  mov     edx, offset aEngines_0; "Engines"
0x100253df  lea     ecx, [ebp+SubKey]
0x100253e5  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100253ea  lea     eax, [ebp+hKey]
0x100253f0  push    eax; phkResult
0x100253f1  lea     eax, [ebp+SubKey]
0x100253f7  push    eax; lpSubKey
0x100253f8  push    80000002h; hKey
0x100253fd  call    _JetRegOpenKeyW@12; JetRegOpenKeyW(x,x,x)
0x10025402  test    eax, eax
0x10025404  jnz     loc_10025347
0x1002540a  push    lpSubKey; lpSubKey
0x10025410  push    [ebp+hKey]; hKey
0x10025416  call    _JetRegDeleteKeyW@8; JetRegDeleteKeyW(x,x)
0x1002541b  push    [ebp+hKey]; hKey
0x10025421  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10025427  push    ebx
0x10025428  mov     edx, offset aSoftwareMicros; "Software\\Microsoft\\Jet\\4.0"
0x1002542d  lea     ecx, [ebp+SubKey]
0x10025433  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10025438  push    ebx
0x10025439  mov     edx, offset asc_1000539C; "\\"
0x1002543e  lea     ecx, [ebp+SubKey]
0x10025444  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10025449  push    ebx
0x1002544a  mov     edx, offset aIsamFormats; "ISAM Formats"
0x1002544f  lea     ecx, [ebp+SubKey]
0x10025455  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002545a  lea     eax, [ebp+hKey]
0x10025460  push    eax; phkResult
0x10025461  lea     eax, [ebp+SubKey]
0x10025467  push    eax; lpSubKey
0x10025468  push    80000002h; hKey
0x1002546d  call    _JetRegOpenKeyW@12; JetRegOpenKeyW(x,x,x)
0x10025472  test    eax, eax
0x10025474  jnz     loc_10025347
0x1002547a  push    4
0x1002547c  pop     esi
0x1002547d  push    dword ptr [edi]; lpSubKey
0x1002547f  push    [ebp+hKey]; hKey
0x10025485  call    _JetRegDeleteKeyW@8; JetRegDeleteKeyW(x,x)
0x1002548a  lea     edi, [edi+34h]
0x1002548d  sub     esi, 1
0x10025490  jnz     short loc_1002547D
0x10025492  push    [ebp+hKey]; hKey
0x10025498  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1002549e  xor     eax, eax
0x100254a0  jmp     loc_1002534A
```
