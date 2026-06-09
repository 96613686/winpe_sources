# CDimSetup::RConfigInterfaceExists(uchar *)

- ea: `0x180031438`
- end: `0x180031640`
- name: `?RConfigInterfaceExists@CDimSetup@@AEAAHPEAE@Z`
- size: `520`
- prototype: `int(CDimSetup *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180031db4`

## callees

- `0x180031438`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003150c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003150c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031609`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031609`
- `KERNEL32!lstrcmpiW` at `0x1800315e7`
- `KERNEL32!lstrcmpiW` at `0x1800315e7`
- `ADVAPI32!RegOpenKeyExW` at `0x180031584`
- `ADVAPI32!RegOpenKeyExW` at `0x180031584`
- `ADVAPI32!RegCloseKey` at `0x1800315c9`
- `ADVAPI32!RegCloseKey` at `0x180031619`
- `ADVAPI32!RegCloseKey` at `0x1800315c9`
- `ADVAPI32!RegCloseKey` at `0x180031619`
- `ADVAPI32!RegQueryValueExW` at `0x1800315bc`
- `ADVAPI32!RegQueryValueExW` at `0x1800315bc`
- `ADVAPI32!RegEnumKeyExW` at `0x18003155b`
- `ADVAPI32!RegEnumKeyExW` at `0x18003155b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800314e7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800314e7`
- `ADVAPI32!RegOpenKeyW` at `0x18003149a`
- `ADVAPI32!RegOpenKeyW` at `0x18003149a`

## string_xrefs

- `0x180031471`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`

## pseudocode

```c
__int64 __fastcall CDimSetup::RConfigInterfaceExists(CDimSetup *this, const WCHAR *a2)
{
  unsigned int v3; // ebx
  WCHAR *v4; // rsi
  DWORD i; // edi
  LSTATUS v6; // ebx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type[4]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Data[257]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v15; // [rsp+292h] [rbp+192h]

  phkResult = 0;
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v3 = 0;
  Type[0] = 0;
  cchName = 0;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces", &phkResult)
    && !RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0) )
  {
    v4 = (WCHAR *)HeapAlloc(hHeap, 8u, 2 * cbMaxSubKeyLen + 2);
    if ( v4 )
    {
      for ( i = 0; ; ++i )
      {
        v3 = 0;
        if ( i >= cSubKeys )
          break;
        cchName = cbMaxSubKeyLen + 1;
        if ( !RegEnumKeyExW(phkResult, i, v4, &cchName, 0, 0, 0, 0) && !RegOpenKeyExW(phkResult, v4, 0, 0x3001Fu, &hKey) )
        {
          cchName = 514;
          v6 = RegQueryValueExW(hKey, L"InterfaceName", 0, Type, (LPBYTE)Data, &cchName);
          RegCloseKey(hKey);
          hKey = 0;
          if ( !v6 )
          {
            v15 = 0;
            if ( !lstrcmpiW(Data, a2) )
            {
              v3 = 1;
              break;
            }
          }
        }
      }
      HeapFree(hHeap, 0, v4);
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v3;
}

```

## disassembly

```asm
0x180031438  push    rbp
0x18003143a  push    rbx
0x18003143b  push    rsi
0x18003143c  push    rdi
0x18003143d  push    r14
0x18003143f  push    r15
0x180031441  lea     rbp, [rsp-1B8h]
0x180031449  sub     rsp, 2B8h
0x180031450  mov     rax, cs:__security_cookie
0x180031457  xor     rax, rsp
0x18003145a  mov     [rbp+1E0h+var_40], rax
0x180031461  xor     r15d, r15d
0x180031464  lea     r8, [rsp+2E0h+phkResult]; phkResult
0x180031469  mov     r14, rdx
0x18003146c  mov     [rsp+2E0h+phkResult], r15
0x180031471  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x180031478  mov     [rsp+2E0h+hKey], r15
0x18003147d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031484  mov     [rsp+2E0h+cSubKeys], r15d
0x180031489  mov     [rsp+2E0h+cbMaxSubKeyLen], r15d
0x18003148e  mov     ebx, r15d
0x180031491  mov     [rbp+1E0h+Type], r15d
0x180031495  mov     [rsp+2E0h+cchName], r15d
0x18003149a  call    cs:__imp_RegOpenKeyW
0x1800314a0  test    eax, eax
0x1800314a2  jnz     loc_18003160F
0x1800314a8  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x1800314ad  lea     rax, [rsp+2E0h+cbMaxSubKeyLen]
0x1800314b2  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800314b7  xor     r9d, r9d; lpReserved
0x1800314ba  mov     [rsp+2E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800314bf  xor     r8d, r8d; lpcchClass
0x1800314c2  mov     [rsp+2E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800314c7  xor     edx, edx; lpClass
0x1800314c9  mov     [rsp+2E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800314ce  mov     [rsp+2E0h+lpcValues], r15; lpcValues
0x1800314d3  mov     [rsp+2E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800314d8  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800314dd  lea     rax, [rsp+2E0h+cSubKeys]
0x1800314e2  mov     [rsp+2E0h+lpcSubKeys], rax; lpcSubKeys
0x1800314e7  call    cs:__imp_RegQueryInfoKeyW
0x1800314ed  test    eax, eax
0x1800314ef  jnz     loc_18003160F
0x1800314f5  mov     eax, [rsp+2E0h+cbMaxSubKeyLen]
0x1800314f9  lea     edx, [r15+8]; dwFlags
0x1800314fd  mov     rcx, cs:hHeap; hHeap
0x180031504  lea     r8d, ds:2[rax*2]; dwBytes
0x18003150c  call    cs:__imp_HeapAlloc
0x180031512  mov     rsi, rax
0x180031515  test    rax, rax
0x180031518  jz      loc_18003160F
0x18003151e  mov     edi, r15d
0x180031521  mov     ebx, r15d
0x180031524  cmp     edi, [rsp+2E0h+cSubKeys]
0x180031528  jnb     loc_1800315FD
0x18003152e  mov     ecx, [rsp+2E0h+cbMaxSubKeyLen]
0x180031532  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180031537  inc     ecx
0x180031539  mov     [rsp+2E0h+lpcValues], r15; lpftLastWriteTime
0x18003153e  mov     [rsp+2E0h+cchName], ecx
0x180031542  mov     r8, rsi; lpName
0x180031545  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x18003154a  mov     edx, edi; dwIndex
0x18003154c  mov     [rsp+2E0h+lpcbMaxClassLen], r15; lpcchClass
0x180031551  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r15; lpClass
0x180031556  mov     [rsp+2E0h+lpcSubKeys], r15; lpReserved
0x18003155b  call    cs:__imp_RegEnumKeyExW
0x180031561  test    eax, eax
0x180031563  jnz     loc_1800315F1
0x180031569  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x18003156e  lea     rax, [rsp+2E0h+hKey]
0x180031573  mov     r9d, 3001Fh; samDesired
0x180031579  mov     [rsp+2E0h+lpcSubKeys], rax; phkResult
0x18003157e  xor     r8d, r8d; ulOptions
0x180031581  mov     rdx, rsi; lpSubKey
0x180031584  call    cs:__imp_RegOpenKeyExW
0x18003158a  test    eax, eax
0x18003158c  jnz     short loc_1800315F1
0x18003158e  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180031593  lea     rax, [rsp+2E0h+cchName]
0x180031598  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003159d  lea     r9, [rbp+1E0h+Type]; lpType
0x1800315a1  lea     rax, [rbp+1E0h+Data]
0x1800315a5  mov     [rsp+2E0h+cchName], 202h
0x1800315ad  xor     r8d, r8d; lpReserved
0x1800315b0  mov     [rsp+2E0h+lpcSubKeys], rax; lpData
0x1800315b5  lea     rdx, aInterfacename_0; "InterfaceName"
0x1800315bc  call    cs:__imp_RegQueryValueExW
0x1800315c2  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800315c7  mov     ebx, eax
0x1800315c9  call    cs:__imp_RegCloseKey
0x1800315cf  mov     [rsp+2E0h+hKey], r15
0x1800315d4  test    ebx, ebx
0x1800315d6  jnz     short loc_1800315F1
0x1800315d8  mov     rdx, r14; lpString2
0x1800315db  mov     [rbp+1E0h+var_4E], r15w
0x1800315e3  lea     rcx, [rbp+1E0h+Data]; lpString1
0x1800315e7  call    cs:__imp_lstrcmpiW
0x1800315ed  test    eax, eax
0x1800315ef  jz      short loc_1800315F8
0x1800315f1  inc     edi
0x1800315f3  jmp     loc_180031521
0x1800315f8  mov     ebx, 1
0x1800315fd  mov     rcx, cs:hHeap; hHeap
0x180031604  mov     r8, rsi; lpMem
0x180031607  xor     edx, edx; dwFlags
0x180031609  call    cs:__imp_HeapFree
0x18003160f  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x180031614  test    rcx, rcx
0x180031617  jz      short loc_18003161F
0x180031619  call    cs:__imp_RegCloseKey
0x18003161f  mov     eax, ebx
0x180031621  mov     rcx, [rbp+1E0h+var_40]
0x180031628  xor     rcx, rsp; StackCookie
0x18003162b  call    __security_check_cookie
0x180031630  add     rsp, 2B8h
0x180031637  pop     r15
0x180031639  pop     r14
0x18003163b  pop     rdi
0x18003163c  pop     rsi
0x18003163d  pop     rbx
0x18003163e  pop     rbp
0x18003163f  retn
```
