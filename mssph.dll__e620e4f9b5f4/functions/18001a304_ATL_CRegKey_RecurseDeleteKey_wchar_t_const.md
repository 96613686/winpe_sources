# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x18001a304`
- end: `0x18001a411`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001a304`
- `0x18001a7d4`

## callees

- `0x18000fcd0`
- `0x180017ae4`
- `0x180017dac`
- `0x180019e30`
- `0x18001a304`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001a3b0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001a3b0`

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
0x18001a304  mov     [rsp-8+arg_10], rbx
0x18001a309  push    rbp
0x18001a30a  push    rsi
0x18001a30b  push    rdi
0x18001a30c  lea     rbp, [rsp-180h]
0x18001a314  sub     rsp, 280h
0x18001a31b  mov     rax, cs:__security_cookie
0x18001a322  xor     rax, rsp
0x18001a325  mov     [rbp+190h+var_20], rax
0x18001a32c  mov     rsi, rdx
0x18001a32f  mov     [rsp+290h+hKey], 0
0x18001a338  mov     r8, rdx; lpSubKey
0x18001a33b  mov     [rsp+290h+var_240], 0
0x18001a344  mov     rdx, [rcx]; hKey
0x18001a347  mov     rdi, rcx
0x18001a34a  lea     rcx, [rsp+290h+hKey]; this
0x18001a34f  mov     [rsp+290h+var_238], 0
0x18001a358  mov     r9d, 2001Fh; unsigned int
0x18001a35e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001a363  mov     ebx, eax
0x18001a365  test    eax, eax
0x18001a367  jnz     short loc_18001A3E3
0x18001a369  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18001a372  mov     rcx, [rsp+290h+hKey]; hKey
0x18001a377  lea     rax, [rsp+290h+ftLastWriteTime]
0x18001a37c  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001a381  lea     r9, [rsp+290h+cchName]; lpcchName
0x18001a386  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18001a38f  lea     r8, [rsp+290h+Name]; lpName
0x18001a394  mov     [rsp+290h+lpClass], 0; lpClass
0x18001a39d  xor     edx, edx; dwIndex
0x18001a39f  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18001a3a8  mov     [rsp+290h+cchName], 100h
0x18001a3b0  call    cs:__imp_RegEnumKeyExW
0x18001a3b6  lea     rcx, [rsp+290h+hKey]; this
0x18001a3bb  test    eax, eax
0x18001a3bd  jnz     short loc_18001A3D1
0x18001a3bf  lea     rdx, [rsp+290h+Name]; wchar_t *
0x18001a3c4  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18001a3c9  mov     ebx, eax
0x18001a3cb  test    eax, eax
0x18001a3cd  jnz     short loc_18001A3E3
0x18001a3cf  jmp     short loc_18001A372
0x18001a3d1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a3d6  mov     rdx, rsi; wchar_t *
0x18001a3d9  mov     rcx, rdi; this
0x18001a3dc  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18001a3e1  mov     ebx, eax
0x18001a3e3  lea     rcx, [rsp+290h+hKey]; this
0x18001a3e8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a3ed  mov     eax, ebx
0x18001a3ef  mov     rcx, [rbp+190h+var_20]
0x18001a3f6  xor     rcx, rsp; StackCookie
0x18001a3f9  call    __security_check_cookie
0x18001a3fe  mov     rbx, [rsp+290h+arg_10]
0x18001a406  add     rsp, 280h
0x18001a40d  pop     rdi
0x18001a40e  pop     rsi
0x18001a40f  pop     rbp
0x18001a410  retn
```
