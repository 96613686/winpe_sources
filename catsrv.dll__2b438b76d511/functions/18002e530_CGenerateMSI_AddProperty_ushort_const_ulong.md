# CGenerateMSI::_AddProperty(ushort const *,ulong)

- ea: `0x18002e530`
- end: `0x18002e61a`
- name: `?_AddProperty@CGenerateMSI@@QEAAJPEBGK@Z`
- size: `234`
- prototype: `__int64 __fastcall(CGenerateMSI *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18002d600`

## callees

- `0x180009ee0`
- `0x18002e530`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x18002e5ce`
- `msi!__imp_MsiCloseHandle` at `0x18002e5f1`
- `msi!__imp_MsiCloseHandle` at `0x18002e5ce`
- `msi!__imp_MsiCloseHandle` at `0x18002e5f1`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e59b`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e59b`
- `msi!__imp_MsiViewExecute` at `0x18002e5c0`
- `msi!__imp_MsiViewExecute` at `0x18002e5c0`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::_AddProperty(CGenerateMSI *this, const unsigned __int16 *a2)
{
  signed int v3; // ebx
  signed int v5; // eax
  bool v6; // cc
  MSIHANDLE v7; // ecx
  signed int v8; // eax
  int v9; // [rsp+20h] [rbp-1038h]
  MSIHANDLE phView[4]; // [rsp+30h] [rbp-1028h] BYREF
  WCHAR szQuery[2048]; // [rsp+40h] [rbp-1018h] BYREF

  phView[0] = 0;
  v9 = 1;
  v3 = StringCchPrintfW(szQuery, 0x800u, L"INSERT INTO Property (Property, Value) VALUES ('%s', %d)", a2, v9);
  if ( v3 < 0 )
    return 2147942487LL;
  v5 = MsiDatabaseOpenViewW(*((_DWORD *)this + 16), szQuery, phView);
  v6 = v5 <= 0;
  if ( v5 || (v5 = MsiViewExecute(phView[0], 0), v6 = v5 <= 0, v5) )
  {
    if ( v6 )
      v3 = v5;
    else
      v3 = (unsigned __int16)v5 | 0x80070000;
    v7 = phView[0];
    goto LABEL_13;
  }
  v8 = MsiCloseHandle(phView[0]);
  v7 = 0;
  phView[0] = 0;
  if ( v8 )
  {
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    else
      v3 = v8;
LABEL_13:
    if ( v7 )
      MsiCloseHandle(v7);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002e530  mov     [rsp+arg_10], rbx
0x18002e535  push    rdi
0x18002e536  mov     eax, 1050h
0x18002e53b  call    _alloca_probe
0x18002e540  sub     rsp, rax
0x18002e543  mov     rax, cs:__security_cookie
0x18002e54a  xor     rax, rsp
0x18002e54d  mov     [rsp+1058h+var_18], rax
0x18002e555  mov     rdi, rcx
0x18002e558  mov     [rsp+1058h+phView], 0
0x18002e560  mov     r9, rdx
0x18002e563  mov     [rsp+1058h+var_1038], 1
0x18002e56b  mov     edx, 800h; unsigned __int64
0x18002e570  lea     rcx, [rsp+1058h+szQuery]; unsigned __int16 *
0x18002e575  lea     r8, aInsertIntoProp; "INSERT INTO Property (Property, Value) "...
0x18002e57c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e581  mov     ebx, eax
0x18002e583  test    eax, eax
0x18002e585  jns     short loc_18002E58E
0x18002e587  mov     eax, 80070057h
0x18002e58c  jmp     short loc_18002E5F9
0x18002e58e  mov     ecx, [rdi+40h]; hDatabase
0x18002e591  lea     r8, [rsp+1058h+phView]; phView
0x18002e596  lea     rdx, [rsp+1058h+szQuery]; szQuery
0x18002e59b  call    cs:__imp_MsiDatabaseOpenViewW
0x18002e5a1  test    eax, eax
0x18002e5a3  jz      short loc_18002E5BA
0x18002e5a5  jg      short loc_18002E5AB
0x18002e5a7  mov     ebx, eax
0x18002e5a9  jmp     short loc_18002E5B4
0x18002e5ab  movzx   ebx, ax
0x18002e5ae  or      ebx, 80070000h
0x18002e5b4  mov     ecx, [rsp+1058h+phView]
0x18002e5b8  jmp     short loc_18002E5ED
0x18002e5ba  mov     ecx, [rsp+1058h+phView]; hView
0x18002e5be  xor     edx, edx; hRecord
0x18002e5c0  call    cs:__imp_MsiViewExecute
0x18002e5c6  test    eax, eax
0x18002e5c8  jnz     short loc_18002E5A5
0x18002e5ca  mov     ecx, [rsp+1058h+phView]; hAny
0x18002e5ce  call    cs:__imp_MsiCloseHandle
0x18002e5d4  xor     ecx, ecx; hAny
0x18002e5d6  mov     [rsp+1058h+phView], ecx
0x18002e5da  test    eax, eax
0x18002e5dc  jz      short loc_18002E5F7
0x18002e5de  jg      short loc_18002E5E4
0x18002e5e0  mov     ebx, eax
0x18002e5e2  jmp     short loc_18002E5ED
0x18002e5e4  movzx   ebx, ax
0x18002e5e7  or      ebx, 80070000h
0x18002e5ed  test    ecx, ecx
0x18002e5ef  jz      short loc_18002E5F7
0x18002e5f1  call    cs:__imp_MsiCloseHandle
0x18002e5f7  mov     eax, ebx
0x18002e5f9  mov     rcx, [rsp+1058h+var_18]
0x18002e601  xor     rcx, rsp; StackCookie
0x18002e604  call    __security_check_cookie
0x18002e609  mov     rbx, [rsp+1058h+arg_10]
0x18002e611  add     rsp, 1050h
0x18002e618  pop     rdi
0x18002e619  retn
```
