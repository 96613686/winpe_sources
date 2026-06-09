# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800054d8`
- end: `0x1800055e5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800054d8`
- `0x180005910`

## callees

- `0x180002270`
- `0x180004c64`
- `0x180004d4c`
- `0x180005190`
- `0x1800054d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005584`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180005584`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
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
0x1800054d8  mov     [rsp-8+arg_10], rbx
0x1800054dd  push    rbp
0x1800054de  push    rsi
0x1800054df  push    rdi
0x1800054e0  lea     rbp, [rsp-180h]
0x1800054e8  sub     rsp, 280h
0x1800054ef  mov     rax, cs:__security_cookie
0x1800054f6  xor     rax, rsp
0x1800054f9  mov     [rbp+190h+var_20], rax
0x180005500  mov     rsi, rdx
0x180005503  mov     [rsp+290h+hKey], 0
0x18000550c  mov     r8, rdx; lpSubKey
0x18000550f  mov     [rsp+290h+var_240], 0
0x180005518  mov     rdx, [rcx]; hKey
0x18000551b  mov     rdi, rcx
0x18000551e  lea     rcx, [rsp+290h+hKey]; this
0x180005523  mov     [rsp+290h+var_238], 0
0x18000552c  mov     r9d, 2001Fh; unsigned int
0x180005532  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005537  mov     ebx, eax
0x180005539  test    eax, eax
0x18000553b  jnz     short loc_1800055B7
0x18000553d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180005546  mov     rcx, [rsp+290h+hKey]; hKey
0x18000554b  lea     rax, [rsp+290h+ftLastWriteTime]
0x180005550  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180005555  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000555a  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180005563  lea     r8, [rsp+290h+Name]; lpName
0x180005568  mov     [rsp+290h+lpClass], 0; lpClass
0x180005571  xor     edx, edx; dwIndex
0x180005573  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000557c  mov     [rsp+290h+cchName], 100h
0x180005584  call    cs:__imp_RegEnumKeyExW
0x18000558a  lea     rcx, [rsp+290h+hKey]; this
0x18000558f  test    eax, eax
0x180005591  jnz     short loc_1800055A5
0x180005593  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180005598  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000559d  mov     ebx, eax
0x18000559f  test    eax, eax
0x1800055a1  jnz     short loc_1800055B7
0x1800055a3  jmp     short loc_180005546
0x1800055a5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800055aa  mov     rdx, rsi; unsigned __int16 *
0x1800055ad  mov     rcx, rdi; this
0x1800055b0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800055b5  mov     ebx, eax
0x1800055b7  lea     rcx, [rsp+290h+hKey]; this
0x1800055bc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800055c1  mov     eax, ebx
0x1800055c3  mov     rcx, [rbp+190h+var_20]
0x1800055ca  xor     rcx, rsp; StackCookie
0x1800055cd  call    __security_check_cookie
0x1800055d2  mov     rbx, [rsp+290h+arg_10]
0x1800055da  add     rsp, 280h
0x1800055e1  pop     rdi
0x1800055e2  pop     rsi
0x1800055e3  pop     rbp
0x1800055e4  retn
```
