# _ApplySecurityToRegistryTreeEx(HKEY__ *,void *,void *,int,int,int)

- ea: `0x18000e640`
- end: `0x18000e86d`
- name: `?_ApplySecurityToRegistryTreeEx@@YAJPEAUHKEY__@@PEAX1HHH@Z`
- size: `557`
- prototype: `__int64 __fastcall(HKEY, void *, void *, int, int, DWORD cbMaxSubKeyLen)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e640`
- `0x180012388`

## callees

- `0x180007c60`
- `0x18000a6d0`
- `0x18000e640`
- `0x18000e874`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e7fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e7fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e831`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e831`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e796`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e796`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e75c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e75c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000e6e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000e6e4`

## pseudocode

```c
__int64 __fastcall _ApplySecurityToRegistryTreeEx(HKEY a1, void *a2, void *a3, int a4, int a5, DWORD cbMaxSubKeyLen)
{
  int v9; // eax
  int v10; // ebx
  LSTATUS v11; // eax
  DWORD i; // edi
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  DWORD v15; // r14d
  __int64 j; // rbx
  DWORD cchName; // [rsp+68h] [rbp-19h] BYREF
  LPWSTR lpName; // [rsp+70h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-9h] BYREF
  _QWORD v21[5]; // [rsp+80h] [rbp-1h]
  void *v22; // [rsp+E0h] [rbp+5Fh]
  DWORD cSubKeys; // [rsp+F0h] [rbp+6Fh] BYREF

  v22 = a2;
  if ( !a4 )
    a2 = a3;
  v9 = MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(a1, a2, cbMaxSubKeyLen);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 && a5 )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v11 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v10 = v11;
    if ( v11 > 0 )
      v10 = (unsigned __int16)v11 | 0x80070000;
    if ( v10 >= 0 )
    {
      if ( cSubKeys )
      {
        lpName = 0;
        v10 = ResultFromHeapAllocArray<unsigned short>(++cbMaxSubKeyLen, &lpName);
        if ( v10 >= 0 )
        {
          for ( i = 0; i < cSubKeys; ++i )
          {
            cchName = cbMaxSubKeyLen;
            v13 = RegEnumKeyExW(a1, i, lpName, &cchName, 0, 0, 0, 0);
            v10 = v13;
            if ( v13 > 0 )
              v10 = (unsigned __int16)v13 | 0x80070000;
            if ( v10 >= 0 )
            {
              hKey = 0;
              v14 = RegOpenKeyExW(a1, lpName, 0, 0x60019u, &hKey);
              v10 = v14;
              if ( v14 > 0 )
                v10 = (unsigned __int16)v14 | 0x80070000;
              if ( v10 >= 0 )
              {
                v15 = 1;
                v21[0] = L"Console";
                v21[1] = L"Network";
                v21[2] = L"Software";
                v21[3] = L"System";
                if ( a4 )
                {
                  for ( j = 0; (unsigned int)j < 4; j = (unsigned int)(j + 1) )
                  {
                    if ( !(unsigned int)_o__wcsicmp(v21[j], lpName) )
                    {
                      v15 = 0;
                      break;
                    }
                  }
                }
                v10 = _ApplySecurityToRegistryTreeEx(hKey, v22, a3, 0, 1, v15);
                RegCloseKey(hKey);
              }
            }
          }
          ResultFromHeapFree(lpName);
        }
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000e640  mov     rax, rsp
0x18000e643  mov     [rax+8], rbx
0x18000e647  mov     [rax+18h], rdi
0x18000e64b  mov     [rax+10h], rdx
0x18000e64f  push    rbp
0x18000e650  push    r12
0x18000e652  push    r13
0x18000e654  push    r14
0x18000e656  push    r15
0x18000e658  lea     rbp, [rax-4Fh]
0x18000e65c  sub     rsp, 0A0h
0x18000e663  mov     r13, r8
0x18000e666  xor     r14d, r14d
0x18000e669  test    r9d, r9d
0x18000e66c  mov     r12d, r9d
0x18000e66f  mov     r15, rcx
0x18000e672  cmovz   rdx, r8; void *
0x18000e676  mov     r8d, [rbp+47h+cbMaxSubKeyLen]; int
0x18000e67a  call    ?MergeDefaultWithCustomSecurityAndApplyToRegistryKey_@@YAJPEAUHKEY__@@PEAXH@Z; MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY__ *,void *,int)
0x18000e67f  mov     ebx, eax
0x18000e681  mov     edi, 80070000h
0x18000e686  test    eax, eax
0x18000e688  jle     short loc_18000E68F
0x18000e68a  movzx   ebx, ax
0x18000e68d  or      ebx, edi
0x18000e68f  test    ebx, ebx
0x18000e691  js      loc_18000E84E
0x18000e697  cmp     [rbp+47h+arg_20], r14d
0x18000e69b  jz      loc_18000E84E
0x18000e6a1  mov     [rsp+0C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000e6a6  lea     rax, [rbp+47h+cbMaxSubKeyLen]
0x18000e6aa  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000e6af  xor     r9d, r9d; lpReserved
0x18000e6b2  mov     [rsp+0C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18000e6b7  xor     r8d, r8d; lpcchClass
0x18000e6ba  mov     [rsp+0C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18000e6bf  xor     edx, edx; lpClass
0x18000e6c1  mov     [rsp+0C0h+lpcValues], r14; lpcValues
0x18000e6c6  mov     rcx, r15; hKey
0x18000e6c9  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18000e6ce  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000e6d3  lea     rax, [rbp+47h+cSubKeys]
0x18000e6d7  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x18000e6dc  mov     [rbp+47h+cSubKeys], r14d
0x18000e6e0  mov     [rbp+47h+cbMaxSubKeyLen], r14d
0x18000e6e4  call    cs:__imp_RegQueryInfoKeyW
0x18000e6ea  mov     ebx, eax
0x18000e6ec  test    eax, eax
0x18000e6ee  jle     short loc_18000E6F5
0x18000e6f0  movzx   ebx, ax
0x18000e6f3  or      ebx, edi
0x18000e6f5  test    ebx, ebx
0x18000e6f7  js      loc_18000E84E
0x18000e6fd  cmp     [rbp+47h+cSubKeys], r14d
0x18000e701  jbe     loc_18000E84E
0x18000e707  mov     eax, [rbp+47h+cbMaxSubKeyLen]
0x18000e70a  lea     rdx, [rbp+47h+lpName]
0x18000e70e  inc     eax
0x18000e710  mov     [rbp+47h+lpName], r14
0x18000e714  mov     ecx, eax
0x18000e716  mov     [rbp+47h+cbMaxSubKeyLen], eax
0x18000e719  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18000e71e  mov     ebx, eax
0x18000e720  test    eax, eax
0x18000e722  js      loc_18000E84E
0x18000e728  mov     edi, r14d
0x18000e72b  cmp     [rbp+47h+cSubKeys], r14d
0x18000e72f  jbe     loc_18000E845
0x18000e735  mov     eax, [rbp+47h+cbMaxSubKeyLen]
0x18000e738  lea     r9, [rbp+47h+cchName]; lpcchName
0x18000e73c  mov     r8, [rbp+47h+lpName]; lpName
0x18000e740  mov     edx, edi; dwIndex
0x18000e742  mov     [rsp+0C0h+lpcValues], r14; lpftLastWriteTime
0x18000e747  mov     rcx, r15; hKey
0x18000e74a  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcchClass
0x18000e74f  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r14; lpClass
0x18000e754  mov     [rsp+0C0h+lpcSubKeys], r14; lpReserved
0x18000e759  mov     [rbp+47h+cchName], eax
0x18000e75c  call    cs:__imp_RegEnumKeyExW
0x18000e762  mov     ebx, eax
0x18000e764  test    eax, eax
0x18000e766  jle     short loc_18000E771
0x18000e768  movzx   ebx, ax
0x18000e76b  or      ebx, 80070000h
0x18000e771  test    ebx, ebx
0x18000e773  js      loc_18000E83A
0x18000e779  mov     rdx, [rbp+47h+lpName]; lpSubKey
0x18000e77d  lea     rax, [rbp+47h+hKey]
0x18000e781  mov     r9d, 60019h; samDesired
0x18000e787  mov     [rsp+0C0h+lpcSubKeys], rax; phkResult
0x18000e78c  xor     r8d, r8d; ulOptions
0x18000e78f  mov     [rbp+47h+hKey], r14
0x18000e793  mov     rcx, r15; hKey
0x18000e796  call    cs:__imp_RegOpenKeyExW
0x18000e79c  mov     ebx, eax
0x18000e79e  test    eax, eax
0x18000e7a0  jle     short loc_18000E7AB
0x18000e7a2  movzx   ebx, ax
0x18000e7a5  or      ebx, 80070000h
0x18000e7ab  test    ebx, ebx
0x18000e7ad  js      loc_18000E83A
0x18000e7b3  lea     rax, aConsole; "Console"
0x18000e7ba  mov     r14d, 1
0x18000e7c0  mov     [rbp+47h+var_48], rax
0x18000e7c4  lea     rax, aNetwork; "Network"
0x18000e7cb  mov     [rbp+47h+var_40], rax
0x18000e7cf  lea     rax, aSoftware_0; "Software"
0x18000e7d6  mov     [rbp+47h+var_38], rax
0x18000e7da  lea     rax, aSystem; "System"
0x18000e7e1  mov     [rbp+47h+var_30], rax
0x18000e7e5  test    r12d, r12d
0x18000e7e8  jz      short loc_18000E80B
0x18000e7ea  xor     ebx, ebx
0x18000e7ec  cmp     ebx, 4
0x18000e7ef  jnb     short loc_18000E80B
0x18000e7f1  mov     rdx, [rbp+47h+lpName]
0x18000e7f5  mov     rcx, [rbp+rbx*8+47h+var_48]
0x18000e7fa  call    cs:__imp__o__wcsicmp
0x18000e800  test    eax, eax
0x18000e802  jz      short loc_18000E808
0x18000e804  inc     ebx
0x18000e806  jmp     short loc_18000E7EC
0x18000e808  xor     r14d, r14d
0x18000e80b  mov     rdx, [rbp+47h+arg_8]; void *
0x18000e80f  xor     r9d, r9d; int
0x18000e812  mov     rcx, [rbp+47h+hKey]; HKEY
0x18000e816  mov     r8, r13; void *
0x18000e819  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], r14d; cbMaxSubKeyLen
0x18000e81e  mov     dword ptr [rsp+0C0h+lpcSubKeys], 1; int
0x18000e826  call    ?_ApplySecurityToRegistryTreeEx@@YAJPEAUHKEY__@@PEAX1HHH@Z; _ApplySecurityToRegistryTreeEx(HKEY__ *,void *,void *,int,int,int)
0x18000e82b  mov     rcx, [rbp+47h+hKey]; hKey
0x18000e82f  mov     ebx, eax
0x18000e831  call    cs:__imp_RegCloseKey
0x18000e837  xor     r14d, r14d
0x18000e83a  inc     edi
0x18000e83c  cmp     edi, [rbp+47h+cSubKeys]
0x18000e83f  jb      loc_18000E735
0x18000e845  mov     rcx, [rbp+47h+lpName]; lpMem
0x18000e849  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000e84e  lea     r11, [rsp+0C0h+var_20]
0x18000e856  mov     eax, ebx
0x18000e858  mov     rbx, [r11+30h]
0x18000e85c  mov     rdi, [r11+40h]
0x18000e860  mov     rsp, r11
0x18000e863  pop     r15
0x18000e865  pop     r14
0x18000e867  pop     r13
0x18000e869  pop     r12
0x18000e86b  pop     rbp
0x18000e86c  retn
```
