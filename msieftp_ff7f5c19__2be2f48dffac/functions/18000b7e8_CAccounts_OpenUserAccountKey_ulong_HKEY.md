# CAccounts::_OpenUserAccountKey(ulong,HKEY__ * *)

- ea: `0x18000b7e8`
- end: `0x18000b8de`
- name: `?_OpenUserAccountKey@CAccounts@@IEAAJKPEAPEAUHKEY__@@@Z`
- size: `246`
- prototype: `int(CAccounts *__hidden this, unsigned int, HKEY *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b4d4`
- `0x18000baa8`
- `0x18000bd14`

## callees

- `0x180002240`
- `0x18000b204`
- `0x18000b770`
- `0x18000b7e8`
- `0x180026f48`

## import_xrefs

- `SHLWAPI!UrlEscapeW` at `0x18000b882`
- `SHLWAPI!UrlEscapeW` at `0x18000b882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8b0`

## pseudocode

```c
__int64 __fastcall CAccounts::_OpenUserAccountKey(const WCHAR **this, unsigned int a2, HKEY *a3)
{
  char v4; // si
  LSTATUS v6; // ebx
  const WCHAR *v7; // rcx
  DWORD pcchEscaped; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR ppsz; // [rsp+28h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR psz[264]; // [rsp+40h] [rbp-C0h] BYREF

  *a3 = 0;
  v4 = a2;
  hKey = 0;
  v6 = CAccounts::_OpenAccountKey((CAccounts *)this, a2, &hKey);
  if ( v6 >= 0 )
  {
    v7 = this[1];
    pcchEscaped = 260;
    ppsz = 0;
    if ( !v7 )
    {
      Str_SetPtrW(&ppsz, psz);
      v7 = ppsz;
    }
    psz[0] = 0;
    if ( v7 && *v7 )
      UrlEscapeW(v7, psz, &pcchEscaped, 0x2000u);
    Str_SetPtrW(&ppsz, 0);
    v6 = SHRegCreateOrOpenKeyEx(hKey, psz, v4, a3);
    RegCloseKey(hKey);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b7e8  mov     [rsp-8+arg_18], rbx
0x18000b7ed  push    rbp
0x18000b7ee  push    rsi
0x18000b7ef  push    rdi
0x18000b7f0  push    r14
0x18000b7f2  push    r15
0x18000b7f4  lea     rbp, [rsp-160h]
0x18000b7fc  sub     rsp, 260h
0x18000b803  mov     rax, cs:__security_cookie
0x18000b80a  xor     rax, rsp
0x18000b80d  mov     [rbp+180h+var_30], rax
0x18000b814  xor     r15d, r15d
0x18000b817  mov     r14, r8
0x18000b81a  mov     [r8], r15
0x18000b81d  mov     esi, edx
0x18000b81f  lea     r8, [rsp+280h+hKey]; HKEY *
0x18000b824  mov     [rsp+280h+hKey], r15
0x18000b829  mov     rdi, rcx
0x18000b82c  call    ?_OpenAccountKey@CAccounts@@IEAAJKPEAPEAUHKEY__@@@Z; CAccounts::_OpenAccountKey(ulong,HKEY__ * *)
0x18000b831  mov     ebx, eax
0x18000b833  test    eax, eax
0x18000b835  js      short loc_18000B8B6
0x18000b837  mov     rcx, [rdi+8]
0x18000b83b  mov     [rsp+280h+pcchEscaped], 104h
0x18000b843  mov     [rsp+280h+ppsz], r15
0x18000b848  test    rcx, rcx
0x18000b84b  jnz     short loc_18000B861
0x18000b84d  lea     rdx, [rsp+280h+psz]; psz
0x18000b852  lea     rcx, [rsp+280h+ppsz]; ppsz
0x18000b857  call    Str_SetPtrW
0x18000b85c  mov     rcx, [rsp+280h+ppsz]; pszUrl
0x18000b861  mov     [rsp+280h+psz], r15w
0x18000b867  test    rcx, rcx
0x18000b86a  jz      short loc_18000B888
0x18000b86c  cmp     [rcx], r15w
0x18000b870  jz      short loc_18000B888
0x18000b872  mov     r9d, 2000h; dwFlags
0x18000b878  lea     r8, [rsp+280h+pcchEscaped]; pcchEscaped
0x18000b87d  lea     rdx, [rsp+280h+psz]; pszEscaped
0x18000b882  call    cs:__imp_UrlEscapeW
0x18000b888  xor     edx, edx; psz
0x18000b88a  lea     rcx, [rsp+280h+ppsz]; ppsz
0x18000b88f  call    Str_SetPtrW
0x18000b894  mov     rcx, [rsp+280h+hKey]; HKEY
0x18000b899  lea     rdx, [rsp+280h+psz]; unsigned __int16 *
0x18000b89e  mov     r9, r14; HKEY *
0x18000b8a1  mov     r8d, esi; unsigned int
0x18000b8a4  call    ?SHRegCreateOrOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; SHRegCreateOrOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000b8a9  mov     rcx, [rsp+280h+hKey]; hKey
0x18000b8ae  mov     ebx, eax
0x18000b8b0  call    cs:__imp_RegCloseKey
0x18000b8b6  mov     eax, ebx
0x18000b8b8  mov     rcx, [rbp+180h+var_30]
0x18000b8bf  xor     rcx, rsp; StackCookie
0x18000b8c2  call    __security_check_cookie
0x18000b8c7  mov     rbx, [rsp+280h+arg_18]
0x18000b8cf  add     rsp, 260h
0x18000b8d6  pop     r15
0x18000b8d8  pop     r14
0x18000b8da  pop     rdi
0x18000b8db  pop     rsi
0x18000b8dc  pop     rbp
0x18000b8dd  retn
```
