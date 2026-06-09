# RemoveAClass(wchar_t const *)

- ea: `0x180020304`
- end: `0x1800205f3`
- name: `?RemoveAClass@@YAJPEB_W@Z`
- size: `751`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180020854`

## callees

- `0x180011324`
- `0x180014130`
- `0x1800145a0`
- `0x180020304`
- `0x1800205fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800204c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800204c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002049c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002049c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800204a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800204a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020588`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020401`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002057b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020401`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002057b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002036a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800203ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002045c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020518`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002036a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800203ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002045c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020518`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020382`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020535`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020540`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020382`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020535`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020540`

## string_xrefs

- `0x180020428`: `\CLSID`
- `0x180020354`: `CLSID`
- `0x180020529`: `CLSID`

## pseudocode

```c
__int64 __fastcall RemoveAClass(LPCWSTR lpSubKey)
{
  unsigned int v2; // r14d
  unsigned int v3; // edi
  LSTATUS v4; // esi
  DWORD v5; // r15d
  LSTATUS v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  LSTATUS v10; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Name[264]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[528]; // [rsp+280h] [rbp+180h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v2 = 0;
  v3 = 0;
  v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2001Fu, &hKey);
  if ( !v4 )
  {
    v2 = RegDeleteKeyW(hKey, lpSubKey);
    RegCloseKey(hKey);
    v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, 0, 0, 0x2001Fu, &hKey);
    if ( !v4 )
    {
      v5 = 0;
      while ( !v3 )
      {
        cchName = 260;
        ftLastWriteTime = 0;
        v6 = RegEnumKeyExW(hKey, v5++, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
        v3 = v6;
        if ( !v6 )
        {
          v7 = -1;
          do
            ++v7;
          while ( Name[v7] );
          StringCchCatW(Name, 260 - v7, L"\\CLSID");
          phkResult = 0;
          if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, Name, 0, 0x2001Fu, &phkResult) )
          {
            v4 = 0;
          }
          else
          {
            Type = 0;
            cchName = 520;
            v4 = RegQueryValueExW(phkResult, 0, 0, &Type, Data, &cchName);
            RegCloseKey(phkResult);
            if ( !v4 && !(unsigned int)_o__wcsicmp(Data) )
            {
              v8 = -1;
              do
                ++v8;
              while ( Name[v8] );
              v9 = 2 * v8 - 12;
              if ( v9 >= 0x208 )
                _report_rangecheckfailure();
              *(wchar_t *)((char *)Name + v9) = 0;
              v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Name, 0, 0x2001Fu, &phkResult);
              if ( !v4 )
              {
                if ( v2 )
                  RegDeleteKeyW(phkResult, L"CLSID");
                else
                  v2 = RegDeleteKeyW(phkResult, L"CLSID");
                v5 = 0;
              }
              cchName = 260;
              v10 = RegEnumKeyExW(phkResult, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
              RegCloseKey(phkResult);
              if ( v10 == 259 )
                RemoveAClassName(Name);
            }
          }
        }
      }
    }
  }
  if ( v3 == 259 )
    v3 = v4;
  if ( v3 )
    return v3;
  return v2;
}

```

## disassembly

```asm
0x180020304  push    rbp
0x180020306  push    rbx
0x180020307  push    rsi
0x180020308  push    rdi
0x180020309  push    r12
0x18002030b  push    r13
0x18002030d  push    r14
0x18002030f  push    r15
0x180020311  lea     rbp, [rsp-3A8h]
0x180020319  sub     rsp, 4A8h
0x180020320  mov     rax, cs:__security_cookie
0x180020327  xor     rax, rsp
0x18002032a  mov     [rbp+3E0h+var_50], rax
0x180020331  mov     r12, rcx
0x180020334  mov     [rsp+4E0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002033d  xor     r13d, r13d
0x180020340  lea     rax, [rsp+4E0h+hKey]
0x180020345  mov     rbx, 0FFFFFFFF80000000h
0x18002034c  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180020351  mov     rcx, rbx; hKey
0x180020354  lea     rdx, aClsid_1; "CLSID"
0x18002035b  mov     r9d, 2001Fh; samDesired
0x180020361  xor     r8d, r8d; ulOptions
0x180020364  mov     r14d, r13d
0x180020367  mov     edi, r13d
0x18002036a  call    cs:__imp_RegOpenKeyExW
0x180020370  mov     esi, eax
0x180020372  test    eax, eax
0x180020374  jnz     loc_1800205BE
0x18002037a  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18002037f  mov     rdx, r12; lpSubKey
0x180020382  call    cs:__imp_RegDeleteKeyW
0x180020388  mov     rcx, [rsp+4E0h+hKey]; hKey
0x18002038d  mov     r14d, eax
0x180020390  call    cs:__imp_RegCloseKey
0x180020396  lea     rax, [rsp+4E0h+hKey]
0x18002039b  mov     r9d, 2001Fh; samDesired
0x1800203a1  xor     r8d, r8d; ulOptions
0x1800203a4  mov     [rsp+4E0h+phkResult], rax; phkResult
0x1800203a9  xor     edx, edx; lpSubKey
0x1800203ab  mov     rcx, rbx; hKey
0x1800203ae  call    cs:__imp_RegOpenKeyExW
0x1800203b4  mov     esi, eax
0x1800203b6  test    eax, eax
0x1800203b8  jnz     loc_1800205BE
0x1800203be  mov     r15d, r13d
0x1800203c1  test    edi, edi
0x1800203c3  jnz     loc_1800205BE
0x1800203c9  mov     rcx, [rsp+4E0h+hKey]; hKey
0x1800203ce  lea     rax, [rsp+4E0h+ftLastWriteTime]
0x1800203d3  mov     [rsp+4E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800203d8  lea     r9, [rsp+4E0h+cchName]; lpcchName
0x1800203dd  mov     [rsp+4E0h+lpcchClass], r13; lpcchClass
0x1800203e2  lea     r8, [rsp+4E0h+Name]; lpName
0x1800203e7  mov     [rsp+4E0h+lpClass], r13; lpClass
0x1800203ec  mov     edx, r15d; dwIndex
0x1800203ef  mov     [rsp+4E0h+phkResult], r13; lpReserved
0x1800203f4  mov     [rsp+4E0h+cchName], 104h
0x1800203fc  mov     qword ptr [rsp+4E0h+ftLastWriteTime.dwLowDateTime], r13
0x180020401  call    cs:__imp_RegEnumKeyExW
0x180020407  inc     r15d
0x18002040a  mov     edi, eax
0x18002040c  test    eax, eax
0x18002040e  jnz     short loc_1800203C1
0x180020410  lea     rcx, [rsp+4E0h+Name]
0x180020415  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020419  inc     rax
0x18002041c  cmp     [rcx+rax*2], r13w
0x180020421  jnz     short loc_180020419
0x180020423  mov     edx, 104h
0x180020428  lea     r8, aClsid_0; "\\CLSID"
0x18002042f  sub     rdx, rax; unsigned __int64
0x180020432  lea     rcx, [rsp+4E0h+Name]; wchar_t *
0x180020437  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002043c  lea     rax, [rsp+4E0h+var_498]
0x180020441  mov     [rsp+4E0h+var_498], r13
0x180020446  mov     r9d, 2001Fh; samDesired
0x18002044c  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180020451  xor     r8d, r8d; ulOptions
0x180020454  lea     rdx, [rsp+4E0h+Name]; lpSubKey
0x180020459  mov     rcx, rbx; hKey
0x18002045c  call    cs:__imp_RegOpenKeyExW
0x180020462  test    eax, eax
0x180020464  jnz     loc_1800205B0
0x18002046a  mov     rcx, [rsp+4E0h+var_498]; hKey
0x18002046f  lea     rax, [rsp+4E0h+cchName]
0x180020474  mov     [rsp+4E0h+lpClass], rax; lpcbData
0x180020479  lea     r9, [rsp+4E0h+Type]; lpType
0x18002047e  lea     rax, [rbp+3E0h+Data]
0x180020485  mov     [rsp+4E0h+Type], r13d
0x18002048a  xor     r8d, r8d; lpReserved
0x18002048d  mov     [rsp+4E0h+phkResult], rax; lpData
0x180020492  xor     edx, edx; lpValueName
0x180020494  mov     [rsp+4E0h+cchName], 208h
0x18002049c  call    cs:__imp_RegQueryValueExW
0x1800204a2  mov     rcx, [rsp+4E0h+var_498]; hKey
0x1800204a7  mov     esi, eax
0x1800204a9  call    cs:__imp_RegCloseKey
0x1800204af  test    esi, esi
0x1800204b1  jnz     loc_1800203C1
0x1800204b7  mov     rdx, r12
0x1800204ba  lea     rcx, [rbp+3E0h+Data]
0x1800204c1  call    cs:__imp__o__wcsicmp
0x1800204c7  test    eax, eax
0x1800204c9  jnz     loc_1800203C1
0x1800204cf  lea     rcx, [rsp+4E0h+Name]
0x1800204d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800204d8  inc     rax
0x1800204db  cmp     [rcx+rax*2], r13w
0x1800204e0  jnz     short loc_1800204D8
0x1800204e2  lea     rcx, ds:0FFFFFFFFFFFFFFF4h[rax*2]
0x1800204ea  cmp     rcx, 208h
0x1800204f1  jnb     loc_1800205B8
0x1800204f7  mov     [rsp+rcx+4E0h+Name], r13w
0x1800204fd  lea     rax, [rsp+4E0h+var_498]
0x180020502  mov     rcx, rbx; hKey
0x180020505  mov     [rsp+4E0h+phkResult], rax; phkResult
0x18002050a  mov     r9d, 2001Fh; samDesired
0x180020510  lea     rdx, [rsp+4E0h+Name]; lpSubKey
0x180020515  xor     r8d, r8d; ulOptions
0x180020518  call    cs:__imp_RegOpenKeyExW
0x18002051e  mov     esi, eax
0x180020520  test    eax, eax
0x180020522  jnz     short loc_180020549
0x180020524  mov     rcx, [rsp+4E0h+var_498]; hKey
0x180020529  lea     rdx, aClsid_1; "CLSID"
0x180020530  test    r14d, r14d
0x180020533  jnz     short loc_180020540
0x180020535  call    cs:__imp_RegDeleteKeyW
0x18002053b  mov     r14d, eax
0x18002053e  jmp     short loc_180020546
0x180020540  call    cs:__imp_RegDeleteKeyW
0x180020546  mov     r15d, r13d
0x180020549  mov     rcx, [rsp+4E0h+var_498]; hKey
0x18002054e  lea     rax, [rsp+4E0h+ftLastWriteTime]
0x180020553  mov     [rsp+4E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180020558  lea     r9, [rsp+4E0h+cchName]; lpcchName
0x18002055d  mov     [rsp+4E0h+lpcchClass], r13; lpcchClass
0x180020562  lea     r8, [rsp+4E0h+Name]; lpName
0x180020567  mov     [rsp+4E0h+lpClass], r13; lpClass
0x18002056c  xor     edx, edx; dwIndex
0x18002056e  mov     [rsp+4E0h+phkResult], r13; lpReserved
0x180020573  mov     [rsp+4E0h+cchName], 104h
0x18002057b  call    cs:__imp_RegEnumKeyExW
0x180020581  mov     rcx, [rsp+4E0h+var_498]; hKey
0x180020586  mov     ebx, eax
0x180020588  call    cs:__imp_RegCloseKey
0x18002058e  cmp     ebx, 103h
0x180020594  mov     rbx, 0FFFFFFFF80000000h
0x18002059b  jnz     loc_1800203C1
0x1800205a1  lea     rcx, [rsp+4E0h+Name]; lpSubKey
0x1800205a6  call    ?RemoveAClassName@@YAJPEB_W@Z; RemoveAClassName(wchar_t const *)
0x1800205ab  jmp     loc_1800203C1
0x1800205b0  mov     esi, r13d
0x1800205b3  jmp     loc_1800203C1
0x1800205b8  call    __report_rangecheckfailure
0x1800205be  cmp     edi, 103h
0x1800205c4  cmovz   edi, esi
0x1800205c7  test    edi, edi
0x1800205c9  cmovnz  r14d, edi
0x1800205cd  mov     eax, r14d
0x1800205d0  mov     rcx, [rbp+3E0h+var_50]
0x1800205d7  xor     rcx, rsp; StackCookie
0x1800205da  call    __security_check_cookie
0x1800205df  add     rsp, 4A8h
0x1800205e6  pop     r15
0x1800205e8  pop     r14
0x1800205ea  pop     r13
0x1800205ec  pop     r12
0x1800205ee  pop     rdi
0x1800205ef  pop     rsi
0x1800205f0  pop     rbx
0x1800205f1  pop     rbp
0x1800205f2  retn
```
