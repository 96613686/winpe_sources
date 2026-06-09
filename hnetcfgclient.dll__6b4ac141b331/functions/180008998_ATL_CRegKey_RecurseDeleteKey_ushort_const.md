# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180008998`
- end: `0x180008aa5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008998`
- `0x180008e68`

## callees

- `0x180007b74`
- `0x180007f70`
- `0x180008570`
- `0x180008998`
- `0x18002d200`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008a44`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180008a44`

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
  v4 = ATL::CRegKey::Open(hKey, *this, a2, 0x2001Fu);
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
    ATL::CRegKey::Close(hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close(hKey);
  return v4;
}

```

## disassembly

```asm
0x180008998  mov     [rsp-8+arg_10], rbx
0x18000899d  push    rbp
0x18000899e  push    rsi
0x18000899f  push    rdi
0x1800089a0  lea     rbp, [rsp-180h]
0x1800089a8  sub     rsp, 280h
0x1800089af  mov     rax, cs:__security_cookie
0x1800089b6  xor     rax, rsp
0x1800089b9  mov     [rbp+190h+var_20], rax
0x1800089c0  mov     rsi, rdx
0x1800089c3  mov     [rsp+290h+hKey], 0
0x1800089cc  mov     r8, rdx; lpSubKey
0x1800089cf  mov     [rsp+290h+var_240], 0
0x1800089d8  mov     rdx, [rcx]; hKey
0x1800089db  mov     rdi, rcx
0x1800089de  lea     rcx, [rsp+290h+hKey]; this
0x1800089e3  mov     [rsp+290h+var_238], 0
0x1800089ec  mov     r9d, 2001Fh; unsigned int
0x1800089f2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800089f7  mov     ebx, eax
0x1800089f9  test    eax, eax
0x1800089fb  jnz     short loc_180008A77
0x1800089fd  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180008a06  mov     rcx, [rsp+290h+hKey]; hKey
0x180008a0b  lea     rax, [rsp+290h+ftLastWriteTime]
0x180008a10  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180008a15  lea     r9, [rsp+290h+cchName]; lpcchName
0x180008a1a  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180008a23  lea     r8, [rsp+290h+Name]; lpName
0x180008a28  mov     [rsp+290h+lpClass], 0; lpClass
0x180008a31  xor     edx, edx; dwIndex
0x180008a33  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180008a3c  mov     [rsp+290h+cchName], 100h
0x180008a44  call    cs:__imp_RegEnumKeyExW
0x180008a4a  lea     rcx, [rsp+290h+hKey]; this
0x180008a4f  test    eax, eax
0x180008a51  jnz     short loc_180008A65
0x180008a53  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180008a58  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008a5d  mov     ebx, eax
0x180008a5f  test    eax, eax
0x180008a61  jnz     short loc_180008A77
0x180008a63  jmp     short loc_180008A06
0x180008a65  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008a6a  mov     rdx, rsi; unsigned __int16 *
0x180008a6d  mov     rcx, rdi; this
0x180008a70  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180008a75  mov     ebx, eax
0x180008a77  lea     rcx, [rsp+290h+hKey]; this
0x180008a7c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008a81  mov     eax, ebx
0x180008a83  mov     rcx, [rbp+190h+var_20]
0x180008a8a  xor     rcx, rsp; StackCookie
0x180008a8d  call    __security_check_cookie
0x180008a92  mov     rbx, [rsp+290h+arg_10]
0x180008a9a  add     rsp, 280h
0x180008aa1  pop     rdi
0x180008aa2  pop     rsi
0x180008aa3  pop     rbp
0x180008aa4  retn
```
