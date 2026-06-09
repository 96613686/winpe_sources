# CCOMComponentRegistrar::IsClrManagedComponent(__MIDL___MIDL_itf_registrar_0000_0000_0001,ushort const *)

- ea: `0x18002f8e0`
- end: `0x18002fa53`
- name: `?IsClrManagedComponent@CCOMComponentRegistrar@@AEAAJW4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEBG@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bf60`

## callees

- `0x18000717c`
- `0x18002f8e0`
- `0x180055880`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002fa0d`
- `msvcrt!_wcsicmp` at `0x18002fa0d`
- `msvcrt!wcsrchr` at `0x18002f9dd`
- `msvcrt!wcsrchr` at `0x18002f9ef`
- `msvcrt!wcsrchr` at `0x18002f9dd`
- `msvcrt!wcsrchr` at `0x18002f9ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f979`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f979`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f9bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f9bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa24`

## string_xrefs

- `0x18002fa06`: `mscoree.dll`
- `0x18002f941`: `Software\Classes\CLSID\%s\InprocServer32`

## pseudocode

```c
__int64 __fastcall CCOMComponentRegistrar::IsClrManagedComponent(__int64 a1, int a2, __int64 a3)
{
  REGSAM v3; // ebx
  __int64 result; // rax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  wchar_t *v7; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[79]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v11; // [rsp+DEh] [rbp-22h] BYREF
  BYTE Data[2]; // [rsp+E0h] [rbp-20h] BYREF

  hKey = 0;
  cbData = 0;
  if ( !a3 || (unsigned int)(a2 - 1) > 1 )
    return 2147942487LL;
  v3 = 131609;
  if ( a2 != 1 )
    v3 = 131097;
  result = StringCchPrintfW(SubKey, 0x50u, L"Software\\Classes\\CLSID\\%s\\InprocServer32", a3);
  if ( (int)result >= 0 )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, v3, &hKey) )
    {
      v5 = -2147221164;
    }
    else
    {
      *(_WORD *)Data = 0;
      cbData = 520;
      v6 = RegQueryValueExW(hKey, 0, 0, 0, Data, &cbData);
      v5 = v6;
      if ( v6 )
      {
        if ( v6 > 0 )
          v5 = (unsigned __int16)v6 | 0x80070000;
      }
      else
      {
        v7 = wcsrchr((const wchar_t *)Data, 0x5Cu);
        if ( !v7 )
        {
          v7 = wcsrchr((const wchar_t *)Data, 0x2Fu);
          if ( !v7 )
            v7 = (wchar_t *)&v11;
        }
        v5 = _wcsicmp(v7 + 1, L"mscoree.dll") != 0;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002f8e0  mov     [rsp-8+arg_0], rbx
0x18002f8e5  push    rbp
0x18002f8e6  lea     rbp, [rsp-200h]
0x18002f8ee  sub     rsp, 300h
0x18002f8f5  mov     rax, cs:__security_cookie
0x18002f8fc  xor     rax, rsp
0x18002f8ff  mov     [rbp+200h+var_10], rax
0x18002f906  mov     [rsp+300h+hKey], 0
0x18002f90f  mov     [rsp+300h+cbData], 0
0x18002f917  test    r8, r8
0x18002f91a  jz      loc_18002FA2E
0x18002f920  lea     eax, [rdx-1]
0x18002f923  cmp     eax, 1
0x18002f926  ja      loc_18002FA2E
0x18002f92c  cmp     edx, 1
0x18002f92f  lea     rcx, [rsp+300h+SubKey]; unsigned __int16 *
0x18002f934  mov     eax, 20019h
0x18002f939  mov     r9, r8
0x18002f93c  mov     ebx, 20219h
0x18002f941  lea     r8, aSoftwareClasse_0; "Software\\Classes\\CLSID\\%s\\InprocSer"...
0x18002f948  mov     edx, 50h ; 'P'; unsigned __int64
0x18002f94d  cmovnz  ebx, eax
0x18002f950  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f955  test    eax, eax
0x18002f957  js      loc_18002FA33
0x18002f95d  lea     rax, [rsp+300h+hKey]
0x18002f962  mov     r9d, ebx; samDesired
0x18002f965  xor     r8d, r8d; ulOptions
0x18002f968  mov     [rsp+300h+phkResult], rax; phkResult
0x18002f96d  lea     rdx, [rsp+300h+SubKey]; lpSubKey
0x18002f972  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f979  call    cs:__imp_RegOpenKeyExW
0x18002f97f  test    eax, eax
0x18002f981  jz      short loc_18002F98D
0x18002f983  mov     ebx, 80040154h
0x18002f988  jmp     loc_18002FA1A
0x18002f98d  mov     rcx, [rsp+300h+hKey]; hKey
0x18002f992  xor     eax, eax
0x18002f994  mov     word ptr [rbp+200h+Data], ax
0x18002f998  xor     r9d, r9d; lpType
0x18002f99b  lea     rax, [rsp+300h+cbData]
0x18002f9a0  mov     [rsp+300h+cbData], 208h
0x18002f9a8  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18002f9ad  xor     r8d, r8d; lpReserved
0x18002f9b0  lea     rax, [rbp+200h+Data]
0x18002f9b4  xor     edx, edx; lpValueName
0x18002f9b6  mov     [rsp+300h+phkResult], rax; lpData
0x18002f9bb  call    cs:__imp_RegQueryValueExW
0x18002f9c1  mov     ebx, eax
0x18002f9c3  test    eax, eax
0x18002f9c5  jz      short loc_18002F9D4
0x18002f9c7  jle     short loc_18002FA1A
0x18002f9c9  movzx   ebx, ax
0x18002f9cc  or      ebx, 80070000h
0x18002f9d2  jmp     short loc_18002FA1A
0x18002f9d4  mov     edx, 5Ch ; '\'; Ch
0x18002f9d9  lea     rcx, [rbp+200h+Data]; Str
0x18002f9dd  call    cs:__imp_wcsrchr
0x18002f9e3  test    rax, rax
0x18002f9e6  jnz     short loc_18002FA02
0x18002f9e8  lea     edx, [rax+2Fh]; Ch
0x18002f9eb  lea     rcx, [rbp+200h+Data]; Str
0x18002f9ef  call    cs:__imp_wcsrchr
0x18002f9f5  test    rax, rax
0x18002f9f8  jnz     short loc_18002FA02
0x18002f9fa  lea     rax, [rbp+200h+Data]
0x18002f9fe  sub     rax, 2
0x18002fa02  lea     rcx, [rax+2]; String1
0x18002fa06  lea     rdx, aMscoreeDll; "mscoree.dll"
0x18002fa0d  call    cs:__imp__wcsicmp
0x18002fa13  xor     ebx, ebx
0x18002fa15  test    eax, eax
0x18002fa17  setnz   bl
0x18002fa1a  mov     rcx, [rsp+300h+hKey]; hKey
0x18002fa1f  test    rcx, rcx
0x18002fa22  jz      short loc_18002FA2A
0x18002fa24  call    cs:__imp_RegCloseKey
0x18002fa2a  mov     eax, ebx
0x18002fa2c  jmp     short loc_18002FA33
0x18002fa2e  mov     eax, 80070057h
0x18002fa33  mov     rcx, [rbp+200h+var_10]
0x18002fa3a  xor     rcx, rsp; StackCookie
0x18002fa3d  call    __security_check_cookie
0x18002fa42  mov     rbx, [rsp+300h+arg_0]
0x18002fa4a  add     rsp, 300h
0x18002fa51  pop     rbp
0x18002fa52  retn
```
