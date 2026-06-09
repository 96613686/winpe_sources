# IDriverRemove

- ea: `0x180005760`
- end: `0x180005987`
- name: `IDriverRemove`
- size: `551`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800012a0`
- `0x180004b70`
- `0x1800063d0`
- `0x180008d00`

## callees

- `0x180005760`
- `0x180006310`
- `0x180007380`
- `0x180009270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800058b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800058b9`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180005847`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180005847`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180005881`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180005881`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005968`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005968`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005937`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005946`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005958`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005972`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005937`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005946`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005958`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005972`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000585a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000585a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800058ae`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800058ae`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000589a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000589a`

## pseudocode

```c
__int64 __fastcall IDriverRemove(__int64 a1, char a2)
{
  _QWORD *v2; // rdi
  WCHAR *v4; // rdx
  WCHAR *v5; // r8
  __int64 v6; // rax
  __int64 v7; // r9
  WCHAR *v8; // rcx
  bool v9; // zf
  __int64 result; // rax
  __int64 v11; // rax
  _QWORD *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  _DWORD *v16; // rax
  HKEY phkResult; // [rsp+30h] [rbp-398h] BYREF
  WCHAR Default[12]; // [rsp+38h] [rbp-390h] BYREF
  WCHAR KeyName[144]; // [rsp+50h] [rbp-378h] BYREF
  wchar_t pszDest[144]; // [rsp+170h] [rbp-258h] BYREF
  WCHAR ReturnedString[128]; // [rsp+290h] [rbp-138h] BYREF

  v2 = *(_QWORD **)(a1 + 4);
  if ( (a2 & 1) != 0 )
  {
    v4 = (WCHAR *)(a1 + 120);
    v5 = KeyName;
    phkResult = 0;
    v6 = 2147483646;
    wcscpy(Default, L" default ");
    v7 = 144;
    do
    {
      if ( !v6 )
        break;
      if ( !*v4 )
        break;
      *v5++ = *v4++;
      --v6;
      --v7;
    }
    while ( v7 );
    v8 = v5 - 1;
    if ( v7 )
      v8 = v5;
    v9 = (*(_DWORD *)(a1 + 52) & 0x40000000) == 0;
    *v8 = 0;
    if ( !v9 )
      return 512;
    StringCchCopyW(pszDest, 0x90u, *(STRSAFE_LPCWSTR *)(a1 + 112));
    GetPrivateProfileStringW(pszDest, KeyName, Default, ReturnedString, 0x80u, L"SYSTEM.INI");
    if ( !lstrcmpW(Default, ReturnedString) )
      return 6;
    WritePrivateProfileStringW(pszDest, KeyName, 0, L"SYSTEM.INI");
    if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\MediaResources\\acm", &phkResult) )
    {
      RegDeleteKeyW(phkResult, KeyName);
      RegCloseKey(phkResult);
    }
  }
  if ( (*(_DWORD *)(a1 + 56) & 1) == 0 || (result = IDriverFree(a1), !(_DWORD)result) || v2[13] == a1 )
  {
    v11 = v2[12];
    if ( a1 == v11 )
    {
      v2[12] = *(_QWORD *)(a1 + 20);
    }
    else
    {
      if ( !v11 )
        return 5;
      while ( 1 )
      {
        v12 = (_QWORD *)(v11 + 20);
        v11 = *(_QWORD *)(v11 + 20);
        if ( v11 == a1 )
          break;
        if ( !v11 )
          return 5;
      }
      *v12 = *(_QWORD *)(a1 + 20);
    }
    v13 = *(void **)(a1 + 68);
    *(_QWORD *)(a1 + 20) = 0;
    if ( v13 )
      LocalFree(v13);
    v14 = *(void **)(a1 + 80);
    if ( v14 )
      LocalFree(v14);
    v15 = *(void **)(a1 + 408);
    if ( v15 )
      LocalFree(v15);
    *(_DWORD *)a1 = 666;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 - 40));
    LocalFree((HLOCAL)(a1 - 40));
    v16 = (_DWORD *)v2[10];
    if ( v16 )
      ++*v16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005760  push    rbx
0x180005762  push    rbp
0x180005763  push    rsi
0x180005764  push    rdi
0x180005765  sub     rsp, 3A8h
0x18000576c  mov     rax, cs:__security_cookie
0x180005773  xor     rax, rsp
0x180005776  mov     [rsp+3C8h+var_38], rax
0x18000577e  mov     rdi, [rcx+4]
0x180005782  xor     esi, esi
0x180005784  mov     rbx, rcx
0x180005787  test    dl, 1
0x18000578a  jz      loc_1800058BF
0x180005790  mov     eax, dword ptr cs:aDefault+10h; " "
0x180005796  lea     rdx, [rcx+78h]
0x18000579a  movups  xmm0, xmmword ptr cs:aDefault; " default "
0x1800057a1  mov     [rsp+3C8h+var_380], eax
0x1800057a5  lea     r8, [rsp+3C8h+KeyName]
0x1800057aa  mov     [rsp+3C8h+phkResult], rsi
0x1800057af  mov     eax, 7FFFFFFEh
0x1800057b4  movups  xmmword ptr [rsp+3C8h+Default], xmm0
0x1800057b9  mov     r9d, 90h
0x1800057bf  nop
0x1800057c0  test    rax, rax
0x1800057c3  jz      short loc_1800057E2
0x1800057c5  movzx   ecx, word ptr [rdx]
0x1800057c8  test    cx, cx
0x1800057cb  jz      short loc_1800057E2
0x1800057cd  mov     [r8], cx
0x1800057d1  add     rdx, 2
0x1800057d5  add     r8, 2
0x1800057d9  dec     rax
0x1800057dc  sub     r9, 1
0x1800057e0  jnz     short loc_1800057C0
0x1800057e2  test    r9, r9
0x1800057e5  lea     rcx, [r8-2]
0x1800057e9  cmovnz  rcx, r8
0x1800057ed  test    dword ptr [rbx+34h], 40000000h
0x1800057f4  mov     [rcx], si
0x1800057f7  jz      short loc_180005803
0x1800057f9  mov     eax, 200h
0x1800057fe  jmp     loc_180005907
0x180005803  mov     r8, [rbx+70h]; pszSrc
0x180005807  lea     rcx, [rsp+3C8h+pszDest]; pszDest
0x18000580f  mov     edx, 90h; cchDest
0x180005814  call    StringCchCopyW
0x180005819  lea     rbp, gszIniSystem; "SYSTEM.INI"
0x180005820  mov     [rsp+3C8h+lpFileName], rbp; lpFileName
0x180005825  lea     r9, [rsp+3C8h+ReturnedString]; lpReturnedString
0x18000582d  lea     r8, [rsp+3C8h+Default]; lpDefault
0x180005832  mov     [rsp+3C8h+nSize], 80h; nSize
0x18000583a  lea     rdx, [rsp+3C8h+KeyName]; lpKeyName
0x18000583f  lea     rcx, [rsp+3C8h+pszDest]; lpAppName
0x180005847  call    cs:__imp_GetPrivateProfileStringW
0x18000584d  lea     rdx, [rsp+3C8h+ReturnedString]; lpString2
0x180005855  lea     rcx, [rsp+3C8h+Default]; lpString1
0x18000585a  call    cs:__imp_lstrcmpW
0x180005860  test    eax, eax
0x180005862  jnz     short loc_18000586E
0x180005864  mov     eax, 6
0x180005869  jmp     loc_180005907
0x18000586e  mov     r9, rbp; lpFileName
0x180005871  lea     rdx, [rsp+3C8h+KeyName]; lpKeyName
0x180005876  xor     r8d, r8d; lpString
0x180005879  lea     rcx, [rsp+3C8h+pszDest]; lpAppName
0x180005881  call    cs:__imp_WritePrivateProfileStringW
0x180005887  lea     r8, [rsp+3C8h+phkResult]; phkResult
0x18000588c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005893  lea     rdx, gszKeyDrivers; "System\\CurrentControlSet\\Control\\Med"...
0x18000589a  call    cs:__imp_RegOpenKeyW
0x1800058a0  test    eax, eax
0x1800058a2  jnz     short loc_1800058BF
0x1800058a4  mov     rcx, [rsp+3C8h+phkResult]; hKey
0x1800058a9  lea     rdx, [rsp+3C8h+KeyName]; lpSubKey
0x1800058ae  call    cs:__imp_RegDeleteKeyW
0x1800058b4  mov     rcx, [rsp+3C8h+phkResult]; hKey
0x1800058b9  call    cs:__imp_RegCloseKey
0x1800058bf  mov     eax, [rbx+38h]
0x1800058c2  test    al, 1
0x1800058c4  jz      short loc_1800058D8
0x1800058c6  mov     rcx, rbx
0x1800058c9  call    IDriverFree
0x1800058ce  test    eax, eax
0x1800058d0  jz      short loc_1800058D8
0x1800058d2  cmp     [rdi+68h], rbx
0x1800058d6  jnz     short loc_180005907
0x1800058d8  mov     rax, [rdi+60h]
0x1800058dc  cmp     rbx, rax
0x1800058df  jnz     short loc_1800058EB
0x1800058e1  mov     rax, [rbx+14h]
0x1800058e5  mov     [rdi+60h], rax
0x1800058e9  jmp     short loc_18000592A
0x1800058eb  test    rax, rax
0x1800058ee  jz      short loc_180005902
0x1800058f0  lea     rcx, [rax+14h]
0x1800058f4  mov     rax, [rax+14h]
0x1800058f8  cmp     rax, rbx
0x1800058fb  jz      short loc_180005923
0x1800058fd  test    rax, rax
0x180005900  jnz     short loc_1800058F0
0x180005902  mov     eax, 5
0x180005907  mov     rcx, [rsp+3C8h+var_38]
0x18000590f  xor     rcx, rsp; StackCookie
0x180005912  call    __security_check_cookie
0x180005917  add     rsp, 3A8h
0x18000591e  pop     rdi
0x18000591f  pop     rsi
0x180005920  pop     rbp
0x180005921  pop     rbx
0x180005922  retn
0x180005923  mov     rax, [rbx+14h]
0x180005927  mov     [rcx], rax
0x18000592a  mov     rcx, [rbx+44h]; hMem
0x18000592e  mov     [rbx+14h], rsi
0x180005932  test    rcx, rcx
0x180005935  jz      short loc_18000593D
0x180005937  call    cs:__imp_LocalFree
0x18000593d  mov     rcx, [rbx+50h]; hMem
0x180005941  test    rcx, rcx
0x180005944  jz      short loc_18000594C
0x180005946  call    cs:__imp_LocalFree
0x18000594c  mov     rcx, [rbx+198h]; hMem
0x180005953  test    rcx, rcx
0x180005956  jz      short loc_18000595E
0x180005958  call    cs:__imp_LocalFree
0x18000595e  lea     rcx, [rbx-28h]; lpCriticalSection
0x180005962  mov     dword ptr [rbx], 29Ah
0x180005968  call    cs:__imp_DeleteCriticalSection
0x18000596e  lea     rcx, [rbx-28h]; hMem
0x180005972  call    cs:__imp_LocalFree
0x180005978  mov     rax, [rdi+50h]
0x18000597c  test    rax, rax
0x18000597f  jz      short loc_180005983
0x180005981  inc     dword ptr [rax]
0x180005983  xor     eax, eax
0x180005985  jmp     short loc_180005907
```
