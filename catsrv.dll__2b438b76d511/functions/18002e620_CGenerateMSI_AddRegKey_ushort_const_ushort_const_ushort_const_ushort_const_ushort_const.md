# CGenerateMSI::_AddRegKey(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002e620`
- end: `0x18002e700`
- name: `?_AddRegKey@CGenerateMSI@@QEAAJPEBG0000@Z`
- size: `224`
- prototype: `__int64 __fastcall(CGenerateMSI *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b820`
- `0x18002c300`
- `0x18002cae0`

## callees

- `0x180009ee0`
- `0x18002e620`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x18002e6cb`
- `msi!__imp_MsiCloseHandle` at `0x18002e6cb`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e6ad`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e6ad`
- `msi!__imp_MsiViewExecute` at `0x18002e6bd`
- `msi!__imp_MsiViewExecute` at `0x18002e6bd`

## string_xrefs

- `0x18002e676`: `INSERT INTO Registry (Registry, Root, `Key`, Name, Value, Component_) VALUES ('%s', %d, '%s', '%s', '%s', '%s')`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::_AddRegKey(
        CGenerateMSI *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  int v7; // ebx
  signed int v8; // eax
  bool v9; // cc
  MSIHANDLE phView[4]; // [rsp+50h] [rbp-1038h] BYREF
  WCHAR szQuery[2048]; // [rsp+60h] [rbp-1028h] BYREF

  phView[0] = 0;
  v7 = StringCchPrintfW(
         szQuery,
         0x800u,
         L"INSERT INTO Registry (Registry, Root, `Key`, Name, Value, Component_) VALUES ('%s', %d, '%s', '%s', '%s', '%s')",
         a2,
         0,
         a3,
         a4,
         a5,
         a6);
  if ( v7 >= 0 )
  {
    v8 = MsiDatabaseOpenViewW(*((_DWORD *)this + 16), szQuery, phView);
    v9 = v8 <= 0;
    if ( v8
      || (v8 = MsiViewExecute(phView[0], 0), v9 = v8 <= 0, v8)
      || (v8 = MsiCloseHandle(phView[0]), v9 = v8 <= 0, v8) )
    {
      if ( v9 )
        return (unsigned int)v8;
      else
        return (unsigned __int16)v8 | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002e620  push    rbx
0x18002e622  push    rdi
0x18002e623  mov     eax, 1078h
0x18002e628  call    _alloca_probe
0x18002e62d  sub     rsp, rax
0x18002e630  mov     rax, cs:__security_cookie
0x18002e637  xor     rax, rsp
0x18002e63a  mov     [rsp+1088h+var_28], rax
0x18002e642  mov     rax, [rsp+1088h+arg_28]
0x18002e64a  mov     rdi, rcx
0x18002e64d  mov     rcx, [rsp+1088h+arg_20]
0x18002e655  mov     [rsp+1088h+var_1048], rax
0x18002e65a  mov     [rsp+1088h+var_1050], rcx
0x18002e65f  lea     rcx, [rsp+1088h+szQuery]; unsigned __int16 *
0x18002e664  mov     [rsp+1088h+var_1058], r9
0x18002e669  mov     r9, rdx
0x18002e66c  mov     [rsp+1088h+var_1060], r8
0x18002e671  mov     edx, 800h; unsigned __int64
0x18002e676  lea     r8, aInsertIntoRegi; "INSERT INTO Registry (Registry, Root, `"...
0x18002e67d  mov     [rsp+1088h+phView], 0
0x18002e685  mov     [rsp+1088h+var_1068], 0
0x18002e68e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e693  mov     ebx, eax
0x18002e695  test    eax, eax
0x18002e697  jns     short loc_18002E6A0
0x18002e699  mov     ebx, 80070057h
0x18002e69e  jmp     short loc_18002E6E4
0x18002e6a0  mov     ecx, [rdi+40h]; hDatabase
0x18002e6a3  lea     r8, [rsp+1088h+phView]; phView
0x18002e6a8  lea     rdx, [rsp+1088h+szQuery]; szQuery
0x18002e6ad  call    cs:__imp_MsiDatabaseOpenViewW
0x18002e6b3  test    eax, eax
0x18002e6b5  jnz     short loc_18002E6D5
0x18002e6b7  mov     ecx, [rsp+1088h+phView]; hView
0x18002e6bb  xor     edx, edx; hRecord
0x18002e6bd  call    cs:__imp_MsiViewExecute
0x18002e6c3  test    eax, eax
0x18002e6c5  jnz     short loc_18002E6D5
0x18002e6c7  mov     ecx, [rsp+1088h+phView]; hAny
0x18002e6cb  call    cs:__imp_MsiCloseHandle
0x18002e6d1  test    eax, eax
0x18002e6d3  jz      short loc_18002E6E4
0x18002e6d5  jg      short loc_18002E6DB
0x18002e6d7  mov     ebx, eax
0x18002e6d9  jmp     short loc_18002E6E4
0x18002e6db  movzx   ebx, ax
0x18002e6de  or      ebx, 80070000h
0x18002e6e4  mov     eax, ebx
0x18002e6e6  mov     rcx, [rsp+1088h+var_28]
0x18002e6ee  xor     rcx, rsp; StackCookie
0x18002e6f1  call    __security_check_cookie
0x18002e6f6  add     rsp, 1078h
0x18002e6fd  pop     rdi
0x18002e6fe  pop     rbx
0x18002e6ff  retn
```
