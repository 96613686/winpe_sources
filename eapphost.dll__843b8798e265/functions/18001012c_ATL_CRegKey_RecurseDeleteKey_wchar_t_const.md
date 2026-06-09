# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x18001012c`
- end: `0x180010244`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `280`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001012c`
- `0x1800105a0`

## callees

- `0x180002af0`
- `0x18000f7b0`
- `0x18000f8e4`
- `0x18000fe08`
- `0x18001012c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800101dc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800101dc`

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
0x18001012c  mov     [rsp-8+arg_10], rbx
0x180010131  push    rbp
0x180010132  push    rsi
0x180010133  push    rdi
0x180010134  lea     rbp, [rsp-180h]
0x18001013c  sub     rsp, 280h
0x180010143  mov     rax, cs:__security_cookie
0x18001014a  xor     rax, rsp
0x18001014d  mov     [rbp+190h+var_20], rax
0x180010154  mov     rsi, rdx
0x180010157  mov     [rsp+290h+hKey], 0
0x180010160  mov     r8, rdx; lpSubKey
0x180010163  mov     [rsp+290h+var_240], 0
0x18001016c  mov     rdx, [rcx]; hKey
0x18001016f  mov     rdi, rcx
0x180010172  lea     rcx, [rsp+290h+hKey]; this
0x180010177  mov     [rsp+290h+var_238], 0
0x180010180  mov     r9d, 2001Fh; unsigned int
0x180010186  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001018b  mov     ebx, eax
0x18001018d  test    eax, eax
0x18001018f  jnz     loc_180010215
0x180010195  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18001019e  mov     rcx, [rsp+290h+hKey]; hKey
0x1800101a3  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800101a8  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800101ad  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800101b2  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x1800101bb  lea     r8, [rsp+290h+Name]; lpName
0x1800101c0  mov     [rsp+290h+lpClass], 0; lpClass
0x1800101c9  xor     edx, edx; dwIndex
0x1800101cb  mov     [rsp+290h+lpReserved], 0; lpReserved
0x1800101d4  mov     [rsp+290h+cchName], 100h
0x1800101dc  call    cs:__imp_RegEnumKeyExW
0x1800101e3  nop     dword ptr [rax+rax+00h]
0x1800101e8  lea     rcx, [rsp+290h+hKey]; this
0x1800101ed  test    eax, eax
0x1800101ef  jnz     short loc_180010203
0x1800101f1  lea     rdx, [rsp+290h+Name]; wchar_t *
0x1800101f6  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x1800101fb  mov     ebx, eax
0x1800101fd  test    eax, eax
0x1800101ff  jnz     short loc_180010215
0x180010201  jmp     short loc_18001019E
0x180010203  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010208  mov     rdx, rsi; wchar_t *
0x18001020b  mov     rcx, rdi; this
0x18001020e  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x180010213  mov     ebx, eax
0x180010215  lea     rcx, [rsp+290h+hKey]; this
0x18001021a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001021f  mov     eax, ebx
0x180010221  mov     rcx, [rbp+190h+var_20]
0x180010228  xor     rcx, rsp; StackCookie
0x18001022b  call    __security_check_cookie
0x180010230  mov     rbx, [rsp+290h+arg_10]
0x180010238  add     rsp, 280h
0x18001023f  pop     rdi
0x180010240  pop     rsi
0x180010241  pop     rbp
0x180010242  retn
```
