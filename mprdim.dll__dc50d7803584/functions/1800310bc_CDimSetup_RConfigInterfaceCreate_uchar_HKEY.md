# CDimSetup::RConfigInterfaceCreate(uchar *,HKEY__ * *)

- ea: `0x1800310bc`
- end: `0x180031432`
- name: `?RConfigInterfaceCreate@CDimSetup@@AEAAKPEAEPEAPEAUHKEY__@@@Z`
- size: `886`
- prototype: `unsigned int(CDimSetup *__hidden this, unsigned __int8 *, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180030a18`

## callees

- `0x18001851c`
- `0x1800310bc`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003119d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003119d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800313f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800313f0`
- `KERNEL32!lstrcmpiW` at `0x180031265`
- `KERNEL32!lstrcmpiW` at `0x180031265`
- `ADVAPI32!RegOpenKeyExW` at `0x180031212`
- `ADVAPI32!RegOpenKeyExW` at `0x180031212`
- `ADVAPI32!RegSetValueExW` at `0x18003133d`
- `ADVAPI32!RegSetValueExW` at `0x180031380`
- `ADVAPI32!RegSetValueExW` at `0x1800313ae`
- `ADVAPI32!RegSetValueExW` at `0x1800313dc`
- `ADVAPI32!RegSetValueExW` at `0x18003133d`
- `ADVAPI32!RegSetValueExW` at `0x180031380`
- `ADVAPI32!RegSetValueExW` at `0x1800313ae`
- `ADVAPI32!RegSetValueExW` at `0x1800313dc`
- `ADVAPI32!RegCloseKey` at `0x180031274`
- `ADVAPI32!RegCloseKey` at `0x180031300`
- `ADVAPI32!RegCloseKey` at `0x1800313ff`
- `ADVAPI32!RegCloseKey` at `0x180031274`
- `ADVAPI32!RegCloseKey` at `0x180031300`
- `ADVAPI32!RegCloseKey` at `0x1800313ff`
- `ADVAPI32!RegQueryValueExW` at `0x18003124a`
- `ADVAPI32!RegQueryValueExW` at `0x18003124a`
- `ADVAPI32!RegEnumKeyExW` at `0x1800311ea`
- `ADVAPI32!RegEnumKeyExW` at `0x1800311ea`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180031173`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180031173`
- `ADVAPI32!RegOpenKeyW` at `0x180031125`
- `ADVAPI32!RegOpenKeyW` at `0x180031125`
- `ADVAPI32!RegCreateKeyExW` at `0x1800312eb`
- `ADVAPI32!RegCreateKeyExW` at `0x1800312eb`

## string_xrefs

- `0x180031104`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`

## pseudocode

```c
__int64 __fastcall CDimSetup::RConfigInterfaceCreate(CDimSetup *this, unsigned __int8 *a2, HKEY *a3)
{
  unsigned int v5; // ebx
  WCHAR *v6; // r14
  DWORD i; // edi
  DWORD v8; // eax
  __int64 v9; // rax
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v15; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  DWORD Type; // [rsp+8Ch] [rbp-74h] BYREF
  BYTE v19[8]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t pszDest[12]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Data[257]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v22; // [rsp+2B2h] [rbp+1B2h]

  phkResult = 0;
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  Type = 0;
  cchName = 0;
  v5 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces", &phkResult);
  if ( !v5 )
  {
    v5 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v5 )
    {
      v5 = 8;
      v6 = (WCHAR *)HeapAlloc(hHeap, 8u, 2 * cbMaxSubKeyLen + 2);
      if ( v6 )
      {
        for ( i = 0; ; ++i )
        {
          v8 = cSubKeys;
          if ( i >= cSubKeys )
            break;
          cchName = cbMaxSubKeyLen + 1;
          if ( !RegEnumKeyExW(phkResult, i, v6, &cchName, 0, 0, 0, 0)
            && !RegOpenKeyExW(phkResult, v6, 0, 0x3001Fu, &hKey) )
          {
            cchName = 514;
            v5 = RegQueryValueExW(hKey, L"InterfaceName", 0, &Type, (LPBYTE)Data, &cchName);
            if ( !v5 )
            {
              v22 = 0;
              if ( !lstrcmpiW(Data, (LPCWSTR)a2) )
              {
                *a3 = hKey;
                goto LABEL_24;
              }
            }
            RegCloseKey(hKey);
            hKey = 0;
          }
        }
        dwDisposition = 0;
        *(_DWORD *)v19 = 0;
        while ( 1 )
        {
          v15 = 0;
          StringCbPrintfW(pszDest, 0x14u, L"%d", v8);
          if ( RegCreateKeyExW(phkResult, pszDest, 0, 0, 0, 0x3001Fu, 0, &v15, &dwDisposition) )
            break;
          if ( dwDisposition == 1 )
          {
            *a3 = v15;
            break;
          }
          RegCloseKey(v15);
          v8 = ++cSubKeys;
        }
        v5 = RegSetValueExW(phkResult, L"Stamp", 0, 4u, v19, 4u);
        if ( !v5 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)&a2[2 * v9] );
          v5 = RegSetValueExW(v15, L"InterfaceName", 0, 1u, a2, 2 * v9 + 2);
          if ( !v5 )
          {
            v5 = RegSetValueExW(v15, L"Type", 0, 4u, a2 + 532, 4u);
            if ( !v5 )
              v5 = RegSetValueExW(v15, L"Enabled", 0, 4u, a2 + 528, 4u);
          }
        }
LABEL_24:
        HeapFree(hHeap, 0, v6);
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v5;
}

```

## disassembly

```asm
0x1800310bc  mov     [rsp-8+arg_0], rbx
0x1800310c1  mov     [rsp-8+arg_18], rsi
0x1800310c6  push    rbp
0x1800310c7  push    rdi
0x1800310c8  push    r12
0x1800310ca  push    r14
0x1800310cc  push    r15
0x1800310ce  lea     rbp, [rsp-1D0h]
0x1800310d6  sub     rsp, 2D0h
0x1800310dd  mov     rax, cs:__security_cookie
0x1800310e4  xor     rax, rsp
0x1800310e7  mov     [rbp+1F0h+var_30], rax
0x1800310ee  xor     r12d, r12d
0x1800310f1  mov     r15, r8
0x1800310f4  mov     rsi, rdx
0x1800310f7  mov     [rbp+1F0h+phkResult], r12
0x1800310fb  lea     r8, [rbp+1F0h+phkResult]; phkResult
0x1800310ff  mov     [rsp+2F0h+hKey], r12
0x180031104  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x18003110b  mov     [rsp+2F0h+cSubKeys], r12d
0x180031110  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031117  mov     [rsp+2F0h+cbMaxSubKeyLen], r12d
0x18003111c  mov     [rbp+1F0h+Type], r12d
0x180031120  mov     [rsp+2F0h+cchName], r12d
0x180031125  call    cs:__imp_RegOpenKeyW
0x18003112b  mov     ebx, eax
0x18003112d  test    eax, eax
0x18003112f  jnz     loc_1800313F6
0x180031135  mov     rcx, [rbp+1F0h+phkResult]; hKey
0x180031139  lea     rax, [rsp+2F0h+cbMaxSubKeyLen]
0x18003113e  mov     [rsp+2F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180031143  xor     r9d, r9d; lpReserved
0x180031146  mov     [rsp+2F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18003114b  xor     r8d, r8d; lpcchClass
0x18003114e  mov     [rsp+2F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180031153  xor     edx, edx; lpClass
0x180031155  mov     [rsp+2F0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18003115a  mov     [rsp+2F0h+lpcValues], r12; lpcValues
0x18003115f  mov     [rsp+2F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180031164  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180031169  lea     rax, [rsp+2F0h+cSubKeys]
0x18003116e  mov     [rsp+2F0h+lpcSubKeys], rax; lpcSubKeys
0x180031173  call    cs:__imp_RegQueryInfoKeyW
0x180031179  mov     ebx, eax
0x18003117b  test    eax, eax
0x18003117d  jnz     loc_1800313F6
0x180031183  mov     eax, [rsp+2F0h+cbMaxSubKeyLen]
0x180031187  lea     ebx, [r12+8]
0x18003118c  mov     rcx, cs:hHeap; hHeap
0x180031193  mov     edx, ebx; dwFlags
0x180031195  lea     r8d, ds:2[rax*2]; dwBytes
0x18003119d  call    cs:__imp_HeapAlloc
0x1800311a3  mov     r14, rax
0x1800311a6  test    rax, rax
0x1800311a9  jz      loc_1800313F6
0x1800311af  mov     edi, r12d
0x1800311b2  mov     eax, [rsp+2F0h+cSubKeys]
0x1800311b6  cmp     edi, eax
0x1800311b8  jnb     loc_180031293
0x1800311be  mov     eax, [rsp+2F0h+cbMaxSubKeyLen]
0x1800311c2  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x1800311c7  mov     rcx, [rbp+1F0h+phkResult]; hKey
0x1800311cb  inc     eax
0x1800311cd  mov     [rsp+2F0h+lpcValues], r12; lpftLastWriteTime
0x1800311d2  mov     r8, r14; lpName
0x1800311d5  mov     [rsp+2F0h+lpcbMaxClassLen], r12; lpcchClass
0x1800311da  mov     edx, edi; dwIndex
0x1800311dc  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r12; lpClass
0x1800311e1  mov     [rsp+2F0h+cchName], eax
0x1800311e5  mov     [rsp+2F0h+lpcSubKeys], r12; lpReserved
0x1800311ea  call    cs:__imp_RegEnumKeyExW
0x1800311f0  test    eax, eax
0x1800311f2  jnz     loc_18003127F
0x1800311f8  mov     rcx, [rbp+1F0h+phkResult]; hKey
0x1800311fc  lea     rax, [rsp+2F0h+hKey]
0x180031201  mov     r9d, 3001Fh; samDesired
0x180031207  mov     [rsp+2F0h+lpcSubKeys], rax; phkResult
0x18003120c  xor     r8d, r8d; ulOptions
0x18003120f  mov     rdx, r14; lpSubKey
0x180031212  call    cs:__imp_RegOpenKeyExW
0x180031218  test    eax, eax
0x18003121a  jnz     short loc_18003127F
0x18003121c  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180031221  lea     rax, [rsp+2F0h+cchName]
0x180031226  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003122b  lea     r9, [rbp+1F0h+Type]; lpType
0x18003122f  lea     rax, [rbp+1F0h+Data]
0x180031233  mov     [rsp+2F0h+cchName], 202h
0x18003123b  xor     r8d, r8d; lpReserved
0x18003123e  mov     [rsp+2F0h+lpcSubKeys], rax; lpData
0x180031243  lea     rdx, aInterfacename_0; "InterfaceName"
0x18003124a  call    cs:__imp_RegQueryValueExW
0x180031250  mov     ebx, eax
0x180031252  test    eax, eax
0x180031254  jnz     short loc_18003126F
0x180031256  mov     rdx, rsi; lpString2
0x180031259  mov     [rbp+1F0h+var_3E], r12w
0x180031261  lea     rcx, [rbp+1F0h+Data]; lpString1
0x180031265  call    cs:__imp_lstrcmpiW
0x18003126b  test    eax, eax
0x18003126d  jz      short loc_180031286
0x18003126f  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180031274  call    cs:__imp_RegCloseKey
0x18003127a  mov     [rsp+2F0h+hKey], r12
0x18003127f  inc     edi
0x180031281  jmp     loc_1800311B2
0x180031286  mov     rax, [rsp+2F0h+hKey]
0x18003128b  mov     [r15], rax
0x18003128e  jmp     loc_1800313E4
0x180031293  mov     [rbp+1F0h+dwDisposition], r12d
0x180031297  mov     dword ptr [rbp+1F0h+var_260], r12d
0x18003129b  mov     r9d, eax
0x18003129e  mov     [rsp+2F0h+var_278], r12
0x1800312a3  lea     r8, aD; "%d"
0x1800312aa  mov     edx, 14h; cbDest
0x1800312af  lea     rcx, [rbp+1F0h+pszDest]; pszDest
0x1800312b3  call    StringCbPrintfW
0x1800312b8  mov     rcx, [rbp+1F0h+phkResult]; hKey
0x1800312bc  lea     rax, [rbp+1F0h+dwDisposition]
0x1800312c0  mov     [rsp+2F0h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x1800312c5  lea     rdx, [rbp+1F0h+pszDest]; lpSubKey
0x1800312c9  lea     rax, [rsp+2F0h+var_278]
0x1800312ce  xor     r9d, r9d; lpClass
0x1800312d1  mov     [rsp+2F0h+lpcValues], rax; phkResult
0x1800312d6  xor     r8d, r8d; Reserved
0x1800312d9  mov     [rsp+2F0h+lpcbMaxClassLen], r12; lpSecurityAttributes
0x1800312de  mov     dword ptr [rsp+2F0h+lpcbMaxSubKeyLen], 3001Fh; samDesired
0x1800312e6  mov     dword ptr [rsp+2F0h+lpcSubKeys], r12d; dwOptions
0x1800312eb  call    cs:__imp_RegCreateKeyExW
0x1800312f1  test    eax, eax
0x1800312f3  jnz     short loc_18003131A
0x1800312f5  cmp     [rbp+1F0h+dwDisposition], 1
0x1800312f9  jz      short loc_180031312
0x1800312fb  mov     rcx, [rsp+2F0h+var_278]; hKey
0x180031300  call    cs:__imp_RegCloseKey
0x180031306  mov     eax, [rsp+2F0h+cSubKeys]
0x18003130a  inc     eax
0x18003130c  mov     [rsp+2F0h+cSubKeys], eax
0x180031310  jmp     short loc_18003129B
0x180031312  mov     rax, [rsp+2F0h+var_278]
0x180031317  mov     [r15], rax
0x18003131a  mov     rcx, [rbp+1F0h+phkResult]; hKey
0x18003131e  lea     rax, [rbp+1F0h+var_260]
0x180031322  mov     edi, 4
0x180031327  lea     rdx, aStamp; "Stamp"
0x18003132e  mov     dword ptr [rsp+2F0h+lpcbMaxSubKeyLen], edi; cbData
0x180031332  mov     r9d, edi; dwType
0x180031335  xor     r8d, r8d; Reserved
0x180031338  mov     [rsp+2F0h+lpcSubKeys], rax; lpData
0x18003133d  call    cs:__imp_RegSetValueExW
0x180031343  mov     ebx, eax
0x180031345  test    eax, eax
0x180031347  jnz     loc_1800313E4
0x18003134d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031351  inc     rax
0x180031354  cmp     [rsi+rax*2], r12w
0x180031359  jnz     short loc_180031351
0x18003135b  mov     rcx, [rsp+2F0h+var_278]; hKey
0x180031360  lea     eax, ds:2[rax*2]
0x180031367  mov     dword ptr [rsp+2F0h+lpcbMaxSubKeyLen], eax; cbData
0x18003136b  lea     rdx, aInterfacename_0; "InterfaceName"
0x180031372  mov     r9d, 1; dwType
0x180031378  mov     [rsp+2F0h+lpcSubKeys], rsi; lpData
0x18003137d  xor     r8d, r8d; Reserved
0x180031380  call    cs:__imp_RegSetValueExW
0x180031386  mov     ebx, eax
0x180031388  test    eax, eax
0x18003138a  jnz     short loc_1800313E4
0x18003138c  mov     rcx, [rsp+2F0h+var_278]; hKey
0x180031391  lea     rax, [rsi+214h]
0x180031398  mov     dword ptr [rsp+2F0h+lpcbMaxSubKeyLen], edi; cbData
0x18003139c  lea     rdx, aType_0; "Type"
0x1800313a3  mov     r9d, edi; dwType
0x1800313a6  mov     [rsp+2F0h+lpcSubKeys], rax; lpData
0x1800313ab  xor     r8d, r8d; Reserved
0x1800313ae  call    cs:__imp_RegSetValueExW
0x1800313b4  mov     ebx, eax
0x1800313b6  test    eax, eax
0x1800313b8  jnz     short loc_1800313E4
0x1800313ba  mov     rcx, [rsp+2F0h+var_278]; hKey
0x1800313bf  lea     rax, [rsi+210h]
0x1800313c6  mov     dword ptr [rsp+2F0h+lpcbMaxSubKeyLen], edi; cbData
0x1800313ca  lea     rdx, aEnabled_0; "Enabled"
0x1800313d1  mov     r9d, edi; dwType
0x1800313d4  mov     [rsp+2F0h+lpcSubKeys], rax; lpData
0x1800313d9  xor     r8d, r8d; Reserved
0x1800313dc  call    cs:__imp_RegSetValueExW
0x1800313e2  mov     ebx, eax
0x1800313e4  mov     rcx, cs:hHeap; hHeap
0x1800313eb  mov     r8, r14; lpMem
0x1800313ee  xor     edx, edx; dwFlags
0x1800313f0  call    cs:__imp_HeapFree
0x1800313f6  mov     rcx, [rbp+1F0h+phkResult]; hKey
0x1800313fa  test    rcx, rcx
0x1800313fd  jz      short loc_180031405
0x1800313ff  call    cs:__imp_RegCloseKey
0x180031405  mov     eax, ebx
0x180031407  mov     rcx, [rbp+1F0h+var_30]
0x18003140e  xor     rcx, rsp; StackCookie
0x180031411  call    __security_check_cookie
0x180031416  lea     r11, [rsp+2F0h+var_20]
0x18003141e  mov     rbx, [r11+30h]
0x180031422  mov     rsi, [r11+48h]
0x180031426  mov     rsp, r11
0x180031429  pop     r15
0x18003142b  pop     r14
0x18003142d  pop     r12
0x18003142f  pop     rdi
0x180031430  pop     rbp
0x180031431  retn
```
