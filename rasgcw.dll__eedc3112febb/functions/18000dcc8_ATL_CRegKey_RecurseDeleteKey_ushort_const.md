# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000dcc8`
- end: `0x18000ddd5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000dcc8`
- `0x18000e1a8`

## callees

- `0x180007b44`
- `0x18000c05c`
- `0x18000c9f4`
- `0x18000dcc8`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000dd74`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000dd74`

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
0x18000dcc8  mov     [rsp-8+arg_10], rbx
0x18000dccd  push    rbp
0x18000dcce  push    rsi
0x18000dccf  push    rdi
0x18000dcd0  lea     rbp, [rsp-180h]
0x18000dcd8  sub     rsp, 280h
0x18000dcdf  mov     rax, cs:__security_cookie
0x18000dce6  xor     rax, rsp
0x18000dce9  mov     [rbp+190h+var_20], rax
0x18000dcf0  mov     rsi, rdx
0x18000dcf3  mov     [rsp+290h+hKey], 0
0x18000dcfc  mov     r8, rdx; lpSubKey
0x18000dcff  mov     [rsp+290h+var_240], 0
0x18000dd08  mov     rdx, [rcx]; hKey
0x18000dd0b  mov     rdi, rcx
0x18000dd0e  lea     rcx, [rsp+290h+hKey]; this
0x18000dd13  mov     [rsp+290h+var_238], 0
0x18000dd1c  mov     r9d, 2001Fh; unsigned int
0x18000dd22  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000dd27  mov     ebx, eax
0x18000dd29  test    eax, eax
0x18000dd2b  jnz     short loc_18000DDA7
0x18000dd2d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18000dd36  mov     rcx, [rsp+290h+hKey]; hKey
0x18000dd3b  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000dd40  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000dd45  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000dd4a  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18000dd53  lea     r8, [rsp+290h+Name]; lpName
0x18000dd58  mov     [rsp+290h+lpClass], 0; lpClass
0x18000dd61  xor     edx, edx; dwIndex
0x18000dd63  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000dd6c  mov     [rsp+290h+cchName], 100h
0x18000dd74  call    cs:__imp_RegEnumKeyExW
0x18000dd7a  lea     rcx, [rsp+290h+hKey]; this
0x18000dd7f  test    eax, eax
0x18000dd81  jnz     short loc_18000DD95
0x18000dd83  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000dd88  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000dd8d  mov     ebx, eax
0x18000dd8f  test    eax, eax
0x18000dd91  jnz     short loc_18000DDA7
0x18000dd93  jmp     short loc_18000DD36
0x18000dd95  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000dd9a  mov     rdx, rsi; unsigned __int16 *
0x18000dd9d  mov     rcx, rdi; this
0x18000dda0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000dda5  mov     ebx, eax
0x18000dda7  lea     rcx, [rsp+290h+hKey]; this
0x18000ddac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ddb1  mov     eax, ebx
0x18000ddb3  mov     rcx, [rbp+190h+var_20]
0x18000ddba  xor     rcx, rsp; StackCookie
0x18000ddbd  call    __security_check_cookie
0x18000ddc2  mov     rbx, [rsp+290h+arg_10]
0x18000ddca  add     rsp, 280h
0x18000ddd1  pop     rdi
0x18000ddd2  pop     rsi
0x18000ddd3  pop     rbp
0x18000ddd4  retn
```
