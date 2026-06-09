# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180010bb8`
- end: `0x180010cc5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180010bb8`
- `0x1800110f4`

## callees

- `0x18000fa64`
- `0x18000fffc`
- `0x180010818`
- `0x180010bb8`
- `0x18002e230`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180010c76`
- `ADVAPI32!RegEnumKeyExW` at `0x180010c76`

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
        goto LABEL_6;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_6:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x180010bb8  mov     [rsp-8+arg_10], rbx
0x180010bbd  push    rbp
0x180010bbe  push    rsi
0x180010bbf  push    rdi
0x180010bc0  lea     rbp, [rsp-180h]
0x180010bc8  sub     rsp, 280h
0x180010bcf  mov     rax, cs:__security_cookie
0x180010bd6  xor     rax, rsp
0x180010bd9  mov     [rbp+190h+var_20], rax
0x180010be0  mov     rsi, rdx
0x180010be3  mov     [rsp+290h+hKey], 0
0x180010bec  mov     r8, rdx; lpSubKey
0x180010bef  mov     [rsp+290h+var_240], 0
0x180010bf8  mov     rdx, [rcx]; hKey
0x180010bfb  mov     rdi, rcx
0x180010bfe  lea     rcx, [rsp+290h+hKey]; this
0x180010c03  mov     [rsp+290h+var_238], 0
0x180010c0c  mov     r9d, 2001Fh; unsigned int
0x180010c12  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180010c17  mov     ebx, eax
0x180010c19  test    eax, eax
0x180010c1b  jnz     short loc_180010C97
0x180010c1d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180010c26  jmp     short loc_180010C38
0x180010c28  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180010c2d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180010c32  mov     ebx, eax
0x180010c34  test    eax, eax
0x180010c36  jnz     short loc_180010C97
0x180010c38  mov     rcx, [rsp+290h+hKey]; hKey
0x180010c3d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180010c42  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180010c47  lea     r9, [rsp+290h+cchName]; lpcchName
0x180010c4c  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180010c55  lea     r8, [rsp+290h+Name]; lpName
0x180010c5a  mov     [rsp+290h+lpClass], 0; lpClass
0x180010c63  xor     edx, edx; dwIndex
0x180010c65  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180010c6e  mov     [rsp+290h+cchName], 100h
0x180010c76  call    cs:__imp_RegEnumKeyExW
0x180010c7c  lea     rcx, [rsp+290h+hKey]; this
0x180010c81  test    eax, eax
0x180010c83  jz      short loc_180010C28
0x180010c85  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010c8a  mov     rdx, rsi; unsigned __int16 *
0x180010c8d  mov     rcx, rdi; this
0x180010c90  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180010c95  mov     ebx, eax
0x180010c97  lea     rcx, [rsp+290h+hKey]; this
0x180010c9c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010ca1  mov     eax, ebx
0x180010ca3  mov     rcx, [rbp+190h+var_20]
0x180010caa  xor     rcx, rsp; StackCookie
0x180010cad  call    __security_check_cookie
0x180010cb2  mov     rbx, [rsp+290h+arg_10]
0x180010cba  add     rsp, 280h
0x180010cc1  pop     rdi
0x180010cc2  pop     rsi
0x180010cc3  pop     rbp
0x180010cc4  retn
```
