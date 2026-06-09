# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800078c8`
- end: `0x1800079d5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800078c8`
- `0x180007e04`

## callees

- `0x180004f44`
- `0x1800063fc`
- `0x18000747c`
- `0x1800078c8`
- `0x18002b4a0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180007986`
- `ADVAPI32!RegEnumKeyExW` at `0x180007986`

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
0x1800078c8  mov     [rsp-8+arg_10], rbx
0x1800078cd  push    rbp
0x1800078ce  push    rsi
0x1800078cf  push    rdi
0x1800078d0  lea     rbp, [rsp-180h]
0x1800078d8  sub     rsp, 280h
0x1800078df  mov     rax, cs:__security_cookie
0x1800078e6  xor     rax, rsp
0x1800078e9  mov     [rbp+190h+var_20], rax
0x1800078f0  mov     rsi, rdx
0x1800078f3  mov     [rsp+290h+hKey], 0
0x1800078fc  mov     r8, rdx; lpSubKey
0x1800078ff  mov     [rsp+290h+var_240], 0
0x180007908  mov     rdx, [rcx]; hKey
0x18000790b  mov     rdi, rcx
0x18000790e  lea     rcx, [rsp+290h+hKey]; this
0x180007913  mov     [rsp+290h+var_238], 0
0x18000791c  mov     r9d, 2001Fh; unsigned int
0x180007922  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007927  mov     ebx, eax
0x180007929  test    eax, eax
0x18000792b  jnz     short loc_1800079A7
0x18000792d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180007936  jmp     short loc_180007948
0x180007938  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000793d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007942  mov     ebx, eax
0x180007944  test    eax, eax
0x180007946  jnz     short loc_1800079A7
0x180007948  mov     rcx, [rsp+290h+hKey]; hKey
0x18000794d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180007952  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007957  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000795c  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180007965  lea     r8, [rsp+290h+Name]; lpName
0x18000796a  mov     [rsp+290h+lpClass], 0; lpClass
0x180007973  xor     edx, edx; dwIndex
0x180007975  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000797e  mov     [rsp+290h+cchName], 100h
0x180007986  call    cs:__imp_RegEnumKeyExW
0x18000798c  lea     rcx, [rsp+290h+hKey]; this
0x180007991  test    eax, eax
0x180007993  jz      short loc_180007938
0x180007995  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000799a  mov     rdx, rsi; unsigned __int16 *
0x18000799d  mov     rcx, rdi; this
0x1800079a0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800079a5  mov     ebx, eax
0x1800079a7  lea     rcx, [rsp+290h+hKey]; this
0x1800079ac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800079b1  mov     eax, ebx
0x1800079b3  mov     rcx, [rbp+190h+var_20]
0x1800079ba  xor     rcx, rsp; StackCookie
0x1800079bd  call    __security_check_cookie
0x1800079c2  mov     rbx, [rsp+290h+arg_10]
0x1800079ca  add     rsp, 280h
0x1800079d1  pop     rdi
0x1800079d2  pop     rsi
0x1800079d3  pop     rbp
0x1800079d4  retn
```
