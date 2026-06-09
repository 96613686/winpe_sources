# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180012d14`
- end: `0x180012e21`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180012d14`
- `0x180013134`

## callees

- `0x180011c94`
- `0x180011e84`
- `0x1800128c0`
- `0x180012d14`
- `0x180049880`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180012dc0`
- `ADVAPI32!RegEnumKeyExW` at `0x180012dc0`

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
0x180012d14  mov     [rsp-8+arg_10], rbx
0x180012d19  push    rbp
0x180012d1a  push    rsi
0x180012d1b  push    rdi
0x180012d1c  lea     rbp, [rsp-180h]
0x180012d24  sub     rsp, 280h
0x180012d2b  mov     rax, cs:__security_cookie
0x180012d32  xor     rax, rsp
0x180012d35  mov     [rbp+190h+var_20], rax
0x180012d3c  mov     rsi, rdx
0x180012d3f  mov     [rsp+290h+hKey], 0
0x180012d48  mov     r8, rdx; lpSubKey
0x180012d4b  mov     [rsp+290h+var_240], 0
0x180012d54  mov     rdx, [rcx]; hKey
0x180012d57  mov     rdi, rcx
0x180012d5a  lea     rcx, [rsp+290h+hKey]; this
0x180012d5f  mov     [rsp+290h+var_238], 0
0x180012d68  mov     r9d, 2001Fh; unsigned int
0x180012d6e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180012d73  mov     ebx, eax
0x180012d75  test    eax, eax
0x180012d77  jnz     short loc_180012DF3
0x180012d79  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180012d82  mov     rcx, [rsp+290h+hKey]; hKey
0x180012d87  lea     rax, [rsp+290h+ftLastWriteTime]
0x180012d8c  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180012d91  lea     r9, [rsp+290h+cchName]; lpcchName
0x180012d96  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180012d9f  lea     r8, [rsp+290h+Name]; lpName
0x180012da4  mov     [rsp+290h+lpClass], 0; lpClass
0x180012dad  xor     edx, edx; dwIndex
0x180012daf  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180012db8  mov     [rsp+290h+cchName], 100h
0x180012dc0  call    cs:__imp_RegEnumKeyExW
0x180012dc6  lea     rcx, [rsp+290h+hKey]; this
0x180012dcb  test    eax, eax
0x180012dcd  jnz     short loc_180012DE1
0x180012dcf  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180012dd4  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180012dd9  mov     ebx, eax
0x180012ddb  test    eax, eax
0x180012ddd  jnz     short loc_180012DF3
0x180012ddf  jmp     short loc_180012D82
0x180012de1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180012de6  mov     rdx, rsi; unsigned __int16 *
0x180012de9  mov     rcx, rdi; this
0x180012dec  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180012df1  mov     ebx, eax
0x180012df3  lea     rcx, [rsp+290h+hKey]; this
0x180012df8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180012dfd  mov     eax, ebx
0x180012dff  mov     rcx, [rbp+190h+var_20]
0x180012e06  xor     rcx, rsp; StackCookie
0x180012e09  call    __security_check_cookie
0x180012e0e  mov     rbx, [rsp+290h+arg_10]
0x180012e16  add     rsp, 280h
0x180012e1d  pop     rdi
0x180012e1e  pop     rsi
0x180012e1f  pop     rbp
0x180012e20  retn
```
