# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000a9f8`
- end: `0x18000ab05`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a9f8`
- `0x18000ae30`

## callees

- `0x180009a94`
- `0x18000a0ec`
- `0x18000a6d0`
- `0x18000a9f8`
- `0x18000c4f0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000aaa4`
- `ADVAPI32!RegEnumKeyExW` at `0x18000aaa4`

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
0x18000a9f8  mov     [rsp-8+arg_10], rbx
0x18000a9fd  push    rbp
0x18000a9fe  push    rsi
0x18000a9ff  push    rdi
0x18000aa00  lea     rbp, [rsp-180h]
0x18000aa08  sub     rsp, 280h
0x18000aa0f  mov     rax, cs:__security_cookie
0x18000aa16  xor     rax, rsp
0x18000aa19  mov     [rbp+190h+var_20], rax
0x18000aa20  mov     rsi, rdx
0x18000aa23  mov     [rsp+290h+hKey], 0
0x18000aa2c  mov     r8, rdx; lpSubKey
0x18000aa2f  mov     [rsp+290h+var_240], 0
0x18000aa38  mov     rdx, [rcx]; hKey
0x18000aa3b  mov     rdi, rcx
0x18000aa3e  lea     rcx, [rsp+290h+hKey]; this
0x18000aa43  mov     [rsp+290h+var_238], 0
0x18000aa4c  mov     r9d, 2001Fh; unsigned int
0x18000aa52  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000aa57  mov     ebx, eax
0x18000aa59  test    eax, eax
0x18000aa5b  jnz     short loc_18000AAD7
0x18000aa5d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18000aa66  mov     rcx, [rsp+290h+hKey]; hKey
0x18000aa6b  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000aa70  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000aa75  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000aa7a  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18000aa83  lea     r8, [rsp+290h+Name]; lpName
0x18000aa88  mov     [rsp+290h+lpClass], 0; lpClass
0x18000aa91  xor     edx, edx; dwIndex
0x18000aa93  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000aa9c  mov     [rsp+290h+cchName], 100h
0x18000aaa4  call    cs:__imp_RegEnumKeyExW
0x18000aaaa  lea     rcx, [rsp+290h+hKey]; this
0x18000aaaf  test    eax, eax
0x18000aab1  jnz     short loc_18000AAC5
0x18000aab3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000aab8  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000aabd  mov     ebx, eax
0x18000aabf  test    eax, eax
0x18000aac1  jnz     short loc_18000AAD7
0x18000aac3  jmp     short loc_18000AA66
0x18000aac5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000aaca  mov     rdx, rsi; unsigned __int16 *
0x18000aacd  mov     rcx, rdi; this
0x18000aad0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000aad5  mov     ebx, eax
0x18000aad7  lea     rcx, [rsp+290h+hKey]; this
0x18000aadc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000aae1  mov     eax, ebx
0x18000aae3  mov     rcx, [rbp+190h+var_20]
0x18000aaea  xor     rcx, rsp; StackCookie
0x18000aaed  call    __security_check_cookie
0x18000aaf2  mov     rbx, [rsp+290h+arg_10]
0x18000aafa  add     rsp, 280h
0x18000ab01  pop     rdi
0x18000ab02  pop     rsi
0x18000ab03  pop     rbp
0x18000ab04  retn
```
