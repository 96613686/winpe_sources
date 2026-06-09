# _ApplySecurityToRegistryTreeEx(HKEY__ *,void *,void *,int,int,int)

- ea: `0x180005864`
- end: `0x180005a43`
- name: `?_ApplySecurityToRegistryTreeEx@@YAJPEAUHKEY__@@PEAX1HHH@Z`
- size: `479`
- prototype: `__int64 __fastcall(HKEY, void *, void *, int, int, DWORD cbMaxSubKeyLen)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005864`
- `0x180040460`

## callees

- `0x180004170`
- `0x180005864`
- `0x180005a50`
- `0x180024898`
- `0x1800403dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800059c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800059c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005900`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180005900`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a0a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005987`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005987`

## pseudocode

```c
__int64 __fastcall _ApplySecurityToRegistryTreeEx(HKEY a1, void *a2, void *a3, int a4, int a5, DWORD cbMaxSubKeyLen)
{
  void *v6; // r13
  DWORD v8; // edi
  int v11; // eax
  signed int v12; // ebx
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  DWORD v16; // eax
  DWORD cchName; // [rsp+60h] [rbp-20h] BYREF
  LPWSTR lpName; // [rsp+68h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  DWORD cSubKeys; // [rsp+C8h] [rbp+48h] BYREF

  v6 = a2;
  v8 = 0;
  if ( !a4 )
    a2 = a3;
  v11 = MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(a1, a2, cbMaxSubKeyLen);
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v12 >= 0 && a5 )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v13 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v12 = v13;
    if ( v13 > 0 )
      v12 = (unsigned __int16)v13 | 0x80070000;
    if ( v12 >= 0 )
    {
      if ( cSubKeys )
      {
        lpName = 0;
        v12 = ResultFromHeapAllocArray<unsigned short>(++cbMaxSubKeyLen, &lpName);
        if ( v12 >= 0 )
        {
          if ( cSubKeys )
          {
            do
            {
              cchName = cbMaxSubKeyLen;
              v14 = RegEnumKeyExW(a1, v8, lpName, &cchName, 0, 0, 0, 0);
              v12 = v14;
              if ( v14 > 0 )
                v12 = (unsigned __int16)v14 | 0x80070000;
              if ( v12 >= 0 )
              {
                hKey = 0;
                v15 = RegOpenKeyExW(a1, lpName, 0, 0x60019u, &hKey);
                v12 = v15;
                if ( v15 > 0 )
                  v12 = (unsigned __int16)v15 | 0x80070000;
                if ( v12 >= 0 )
                {
                  v16 = _AllowDaclMerging(a4, lpName);
                  v12 = _ApplySecurityToRegistryTreeEx(hKey, v6, a3, 0, 1, v16);
                  RegCloseKey(hKey);
                }
              }
              ++v8;
            }
            while ( v8 < cSubKeys );
          }
          ResultFromHeapFree(lpName);
        }
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005864  mov     [rsp-28h+arg_0], rbx
0x180005869  mov     [rsp-28h+arg_8], rdi
0x18000586e  push    rbp
0x18000586f  push    r12
0x180005871  push    r13
0x180005873  push    r14
0x180005875  push    r15
0x180005877  mov     rbp, rsp
0x18000587a  sub     rsp, 80h
0x180005881  mov     r13, rdx
0x180005884  mov     r12, r8
0x180005887  xor     edi, edi
0x180005889  mov     r15d, r9d
0x18000588c  test    r9d, r9d
0x18000588f  mov     r14, rcx
0x180005892  cmovz   rdx, r8; void *
0x180005896  mov     r8d, [rbp+cbMaxSubKeyLen]; int
0x18000589a  call    ?MergeDefaultWithCustomSecurityAndApplyToRegistryKey_@@YAJPEAUHKEY__@@PEAXH@Z; MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY__ *,void *,int)
0x18000589f  mov     ebx, eax
0x1800058a1  test    eax, eax
0x1800058a3  jle     short loc_1800058AE
0x1800058a5  movzx   ebx, ax
0x1800058a8  or      ebx, 80070000h
0x1800058ae  test    ebx, ebx
0x1800058b0  js      loc_180005A24
0x1800058b6  cmp     [rbp+arg_20], edi
0x1800058b9  jz      loc_180005A24
0x1800058bf  mov     [rsp+80h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800058c4  lea     rax, [rbp+cbMaxSubKeyLen]
0x1800058c8  mov     [rsp+80h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800058cd  xor     r9d, r9d; lpReserved
0x1800058d0  mov     [rsp+80h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800058d5  xor     r8d, r8d; lpcchClass
0x1800058d8  mov     [rsp+80h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800058dd  xor     edx, edx; lpClass
0x1800058df  mov     [rsp+80h+lpcValues], rdi; lpcValues
0x1800058e4  mov     rcx, r14; hKey
0x1800058e7  mov     [rsp+80h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800058ec  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800058f1  lea     rax, [rbp+cSubKeys]
0x1800058f5  mov     [rsp+80h+lpcSubKeys], rax; lpcSubKeys
0x1800058fa  mov     [rbp+cSubKeys], edi
0x1800058fd  mov     [rbp+cbMaxSubKeyLen], edi
0x180005900  call    cs:__imp_RegQueryInfoKeyW
0x180005906  mov     ebx, eax
0x180005908  test    eax, eax
0x18000590a  jle     short loc_180005915
0x18000590c  movzx   ebx, ax
0x18000590f  or      ebx, 80070000h
0x180005915  test    ebx, ebx
0x180005917  js      loc_180005A24
0x18000591d  cmp     [rbp+cSubKeys], edi
0x180005920  jbe     loc_180005A24
0x180005926  mov     eax, [rbp+cbMaxSubKeyLen]
0x180005929  lea     rdx, [rbp+lpName]
0x18000592d  inc     eax
0x18000592f  mov     [rbp+lpName], rdi
0x180005933  mov     ecx, eax
0x180005935  mov     [rbp+cbMaxSubKeyLen], eax
0x180005938  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18000593d  mov     ebx, eax
0x18000593f  test    eax, eax
0x180005941  js      loc_180005A24
0x180005947  cmp     [rbp+cSubKeys], edi
0x18000594a  jbe     loc_180005A1B
0x180005950  mov     eax, [rbp+cbMaxSubKeyLen]
0x180005953  lea     r9, [rbp+cchName]; lpcchName
0x180005957  mov     r8, [rbp+lpName]; lpName
0x18000595b  mov     edx, edi; dwIndex
0x18000595d  mov     [rsp+80h+lpcValues], 0; lpftLastWriteTime
0x180005966  mov     rcx, r14; hKey
0x180005969  mov     [rsp+80h+lpcbMaxClassLen], 0; lpcchClass
0x180005972  mov     [rsp+80h+lpcbMaxSubKeyLen], 0; lpClass
0x18000597b  mov     [rsp+80h+lpcSubKeys], 0; lpReserved
0x180005984  mov     [rbp+cchName], eax
0x180005987  call    cs:__imp_RegEnumKeyExW
0x18000598d  mov     ebx, eax
0x18000598f  test    eax, eax
0x180005991  jle     short loc_18000599C
0x180005993  movzx   ebx, ax
0x180005996  or      ebx, 80070000h
0x18000599c  test    ebx, ebx
0x18000599e  js      short loc_180005A10
0x1800059a0  mov     rdx, [rbp+lpName]; lpSubKey
0x1800059a4  lea     rax, [rbp+hKey]
0x1800059a8  mov     r9d, 60019h; samDesired
0x1800059ae  mov     [rsp+80h+lpcSubKeys], rax; phkResult
0x1800059b3  xor     r8d, r8d; ulOptions
0x1800059b6  mov     [rbp+hKey], 0
0x1800059be  mov     rcx, r14; hKey
0x1800059c1  call    cs:__imp_RegOpenKeyExW
0x1800059c7  mov     ebx, eax
0x1800059c9  test    eax, eax
0x1800059cb  jle     short loc_1800059D6
0x1800059cd  movzx   ebx, ax
0x1800059d0  or      ebx, 80070000h
0x1800059d6  test    ebx, ebx
0x1800059d8  js      short loc_180005A10
0x1800059da  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x1800059de  mov     ecx, r15d; int
0x1800059e1  call    ?_AllowDaclMerging@@YAHHPEAG@Z; _AllowDaclMerging(int,ushort *)
0x1800059e6  mov     rcx, [rbp+hKey]; HKEY
0x1800059ea  xor     r9d, r9d; int
0x1800059ed  mov     dword ptr [rsp+80h+lpcbMaxSubKeyLen], eax; cbMaxSubKeyLen
0x1800059f1  mov     r8, r12; void *
0x1800059f4  mov     rdx, r13; void *
0x1800059f7  mov     dword ptr [rsp+80h+lpcSubKeys], 1; int
0x1800059ff  call    ?_ApplySecurityToRegistryTreeEx@@YAJPEAUHKEY__@@PEAX1HHH@Z; _ApplySecurityToRegistryTreeEx(HKEY__ *,void *,void *,int,int,int)
0x180005a04  mov     rcx, [rbp+hKey]; hKey
0x180005a08  mov     ebx, eax
0x180005a0a  call    cs:__imp_RegCloseKey
0x180005a10  inc     edi
0x180005a12  cmp     edi, [rbp+cSubKeys]
0x180005a15  jb      loc_180005950
0x180005a1b  mov     rcx, [rbp+lpName]; lpMem
0x180005a1f  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180005a24  lea     r11, [rsp+80h+var_s0]
0x180005a2c  mov     eax, ebx
0x180005a2e  mov     rbx, [r11+30h]
0x180005a32  mov     rdi, [r11+38h]
0x180005a36  mov     rsp, r11
0x180005a39  pop     r15
0x180005a3b  pop     r14
0x180005a3d  pop     r13
0x180005a3f  pop     r12
0x180005a41  pop     rbp
0x180005a42  retn
```
