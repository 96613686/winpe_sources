# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x18000fa68`
- end: `0x18000fb75`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000fa68`
- `0x18000fea0`

## callees

- `0x180002a90`
- `0x18000f1b4`
- `0x18000f2dc`
- `0x18000f788`
- `0x18000fa68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fb14`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fb14`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const wchar_t *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *this, a2, 0x2001Fu);
  if ( !v4 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey[0], 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_7;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x18000fa68  mov     [rsp-8+arg_10], rbx
0x18000fa6d  push    rbp
0x18000fa6e  push    rsi
0x18000fa6f  push    rdi
0x18000fa70  lea     rbp, [rsp-180h]
0x18000fa78  sub     rsp, 280h
0x18000fa7f  mov     rax, cs:__security_cookie
0x18000fa86  xor     rax, rsp
0x18000fa89  mov     [rbp+190h+var_20], rax
0x18000fa90  mov     rsi, rdx
0x18000fa93  mov     [rsp+290h+hKey], 0
0x18000fa9c  mov     r8, rdx; lpSubKey
0x18000fa9f  mov     [rsp+290h+var_240], 0
0x18000faa8  mov     rdx, [rcx]; hKey
0x18000faab  mov     rdi, rcx
0x18000faae  lea     rcx, [rsp+290h+hKey]; this
0x18000fab3  mov     [rsp+290h+var_238], 0
0x18000fabc  mov     r9d, 2001Fh; unsigned int
0x18000fac2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000fac7  mov     ebx, eax
0x18000fac9  test    eax, eax
0x18000facb  jnz     short loc_18000FB47
0x18000facd  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18000fad6  mov     rcx, [rsp+290h+hKey]; hKey
0x18000fadb  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000fae0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000fae5  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000faea  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18000faf3  lea     r8, [rsp+290h+Name]; lpName
0x18000faf8  mov     [rsp+290h+lpClass], 0; lpClass
0x18000fb01  xor     edx, edx; dwIndex
0x18000fb03  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000fb0c  mov     [rsp+290h+cchName], 100h
0x18000fb14  call    cs:__imp_RegEnumKeyExW
0x18000fb1a  lea     rcx, [rsp+290h+hKey]; this
0x18000fb1f  test    eax, eax
0x18000fb21  jnz     short loc_18000FB35
0x18000fb23  lea     rdx, [rsp+290h+Name]; wchar_t *
0x18000fb28  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18000fb2d  mov     ebx, eax
0x18000fb2f  test    eax, eax
0x18000fb31  jnz     short loc_18000FB47
0x18000fb33  jmp     short loc_18000FAD6
0x18000fb35  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fb3a  mov     rdx, rsi; wchar_t *
0x18000fb3d  mov     rcx, rdi; this
0x18000fb40  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18000fb45  mov     ebx, eax
0x18000fb47  lea     rcx, [rsp+290h+hKey]; this
0x18000fb4c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fb51  mov     eax, ebx
0x18000fb53  mov     rcx, [rbp+190h+var_20]
0x18000fb5a  xor     rcx, rsp; StackCookie
0x18000fb5d  call    __security_check_cookie
0x18000fb62  mov     rbx, [rsp+290h+arg_10]
0x18000fb6a  add     rsp, 280h
0x18000fb71  pop     rdi
0x18000fb72  pop     rsi
0x18000fb73  pop     rbp
0x18000fb74  retn
```
