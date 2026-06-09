# _ApplySecurityToRegistryTreeEx(HKEY__ *,void *,void *,int,int,int)

- ea: `0x180010da8`
- end: `0x180010fa0`
- name: `?_ApplySecurityToRegistryTreeEx@@YAJPEAUHKEY__@@PEAX1HHH@Z`
- size: `504`
- prototype: `__int64 __fastcall(HKEY, void *, void *, int, int, DWORD cbMaxSubKeyLen)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010da8`
- `0x180041c00`

## callees

- `0x180005370`
- `0x180010da8`
- `0x180010fb0`
- `0x180027220`
- `0x180041b74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010f11`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010e44`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180010e44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f60`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010ed1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010ed1`

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
0x180010da8  mov     [rsp-28h+arg_0], rbx
0x180010dad  mov     [rsp-28h+arg_8], rdi
0x180010db2  push    rbp
0x180010db3  push    r12
0x180010db5  push    r13
0x180010db7  push    r14
0x180010db9  push    r15
0x180010dbb  mov     rbp, rsp
0x180010dbe  sub     rsp, 80h
0x180010dc5  mov     r13, rdx
0x180010dc8  mov     r12, r8
0x180010dcb  xor     edi, edi
0x180010dcd  mov     r15d, r9d
0x180010dd0  test    r9d, r9d
0x180010dd3  mov     r14, rcx
0x180010dd6  cmovz   rdx, r8; void *
0x180010dda  mov     r8d, [rbp+cbMaxSubKeyLen]; int
0x180010dde  call    ?MergeDefaultWithCustomSecurityAndApplyToRegistryKey_@@YAJPEAUHKEY__@@PEAXH@Z; MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY__ *,void *,int)
0x180010de3  mov     ebx, eax
0x180010de5  test    eax, eax
0x180010de7  jle     short loc_180010DF2
0x180010de9  movzx   ebx, ax
0x180010dec  or      ebx, 80070000h
0x180010df2  test    ebx, ebx
0x180010df4  js      loc_180010F80
0x180010dfa  cmp     [rbp+arg_20], edi
0x180010dfd  jz      loc_180010F80
0x180010e03  mov     [rsp+80h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180010e08  lea     rax, [rbp+cbMaxSubKeyLen]
0x180010e0c  mov     [rsp+80h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180010e11  xor     r9d, r9d; lpReserved
0x180010e14  mov     [rsp+80h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180010e19  xor     r8d, r8d; lpcchClass
0x180010e1c  mov     [rsp+80h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180010e21  xor     edx, edx; lpClass
0x180010e23  mov     [rsp+80h+lpcValues], rdi; lpcValues
0x180010e28  mov     rcx, r14; hKey
0x180010e2b  mov     [rsp+80h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180010e30  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180010e35  lea     rax, [rbp+cSubKeys]
0x180010e39  mov     [rsp+80h+lpcSubKeys], rax; lpcSubKeys
0x180010e3e  mov     [rbp+cSubKeys], edi
0x180010e41  mov     [rbp+cbMaxSubKeyLen], edi
0x180010e44  call    cs:__imp_RegQueryInfoKeyW
0x180010e4b  nop     dword ptr [rax+rax+00h]
0x180010e50  mov     ebx, eax
0x180010e52  test    eax, eax
0x180010e54  jle     short loc_180010E5F
0x180010e56  movzx   ebx, ax
0x180010e59  or      ebx, 80070000h
0x180010e5f  test    ebx, ebx
0x180010e61  js      loc_180010F80
0x180010e67  cmp     [rbp+cSubKeys], edi
0x180010e6a  jbe     loc_180010F80
0x180010e70  mov     eax, [rbp+cbMaxSubKeyLen]
0x180010e73  lea     rdx, [rbp+lpName]
0x180010e77  inc     eax
0x180010e79  mov     [rbp+lpName], rdi
0x180010e7d  mov     ecx, eax
0x180010e7f  mov     [rbp+cbMaxSubKeyLen], eax
0x180010e82  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x180010e87  mov     ebx, eax
0x180010e89  test    eax, eax
0x180010e8b  js      loc_180010F80
0x180010e91  cmp     [rbp+cSubKeys], edi
0x180010e94  jbe     loc_180010F77
0x180010e9a  mov     eax, [rbp+cbMaxSubKeyLen]
0x180010e9d  lea     r9, [rbp+cchName]; lpcchName
0x180010ea1  mov     r8, [rbp+lpName]; lpName
0x180010ea5  mov     edx, edi; dwIndex
0x180010ea7  mov     [rsp+80h+lpcValues], 0; lpftLastWriteTime
0x180010eb0  mov     rcx, r14; hKey
0x180010eb3  mov     [rsp+80h+lpcbMaxClassLen], 0; lpcchClass
0x180010ebc  mov     [rsp+80h+lpcbMaxSubKeyLen], 0; lpClass
0x180010ec5  mov     [rsp+80h+lpcSubKeys], 0; lpReserved
0x180010ece  mov     [rbp+cchName], eax
0x180010ed1  call    cs:__imp_RegEnumKeyExW
0x180010ed8  nop     dword ptr [rax+rax+00h]
0x180010edd  mov     ebx, eax
0x180010edf  test    eax, eax
0x180010ee1  jle     short loc_180010EEC
0x180010ee3  movzx   ebx, ax
0x180010ee6  or      ebx, 80070000h
0x180010eec  test    ebx, ebx
0x180010eee  js      short loc_180010F6C
0x180010ef0  mov     rdx, [rbp+lpName]; lpSubKey
0x180010ef4  lea     rax, [rbp+hKey]
0x180010ef8  mov     r9d, 60019h; samDesired
0x180010efe  mov     [rsp+80h+lpcSubKeys], rax; phkResult
0x180010f03  xor     r8d, r8d; ulOptions
0x180010f06  mov     [rbp+hKey], 0
0x180010f0e  mov     rcx, r14; hKey
0x180010f11  call    cs:__imp_RegOpenKeyExW
0x180010f18  nop     dword ptr [rax+rax+00h]
0x180010f1d  mov     ebx, eax
0x180010f1f  test    eax, eax
0x180010f21  jle     short loc_180010F2C
0x180010f23  movzx   ebx, ax
0x180010f26  or      ebx, 80070000h
0x180010f2c  test    ebx, ebx
0x180010f2e  js      short loc_180010F6C
0x180010f30  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x180010f34  mov     ecx, r15d; int
0x180010f37  call    ?_AllowDaclMerging@@YAHHPEAG@Z; _AllowDaclMerging(int,ushort *)
0x180010f3c  mov     rcx, [rbp+hKey]; HKEY
0x180010f40  xor     r9d, r9d; int
0x180010f43  mov     dword ptr [rsp+80h+lpcbMaxSubKeyLen], eax; cbMaxSubKeyLen
0x180010f47  mov     r8, r12; void *
0x180010f4a  mov     rdx, r13; void *
0x180010f4d  mov     dword ptr [rsp+80h+lpcSubKeys], 1; int
0x180010f55  call    ?_ApplySecurityToRegistryTreeEx@@YAJPEAUHKEY__@@PEAX1HHH@Z; _ApplySecurityToRegistryTreeEx(HKEY__ *,void *,void *,int,int,int)
0x180010f5a  mov     rcx, [rbp+hKey]; hKey
0x180010f5e  mov     ebx, eax
0x180010f60  call    cs:__imp_RegCloseKey
0x180010f67  nop     dword ptr [rax+rax+00h]
0x180010f6c  inc     edi
0x180010f6e  cmp     edi, [rbp+cSubKeys]
0x180010f71  jb      loc_180010E9A
0x180010f77  mov     rcx, [rbp+lpName]; lpMem
0x180010f7b  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180010f80  lea     r11, [rsp+80h+var_s0]
0x180010f88  mov     eax, ebx
0x180010f8a  mov     rbx, [r11+30h]
0x180010f8e  mov     rdi, [r11+38h]
0x180010f92  mov     rsp, r11
0x180010f95  pop     r15
0x180010f97  pop     r14
0x180010f99  pop     r13
0x180010f9b  pop     r12
0x180010f9d  pop     rbp
0x180010f9e  retn
```
