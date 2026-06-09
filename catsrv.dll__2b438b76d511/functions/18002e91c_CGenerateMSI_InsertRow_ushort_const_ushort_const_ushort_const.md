# CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)

- ea: `0x18002e91c`
- end: `0x18002ea29`
- name: `?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ`
- size: `269`
- prototype: `__int64(CGenerateMSI *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `9`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18002b600`
- `0x18002b820`
- `0x18002c050`
- `0x18002c300`
- `0x18002cc60`
- `0x18002cef0`
- `0x18002d400`
- `0x18002d600`
- `0x18002e888`

## callees

- `0x180009ee0`
- `0x18002e288`
- `0x18002e91c`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x18002e9e1`
- `msi!__imp_MsiCloseHandle` at `0x18002ea00`
- `msi!__imp_MsiCloseHandle` at `0x18002e9e1`
- `msi!__imp_MsiCloseHandle` at `0x18002ea00`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e9b8`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002e9b8`
- `msi!__imp_MsiViewExecute` at `0x18002e9d1`
- `msi!__imp_MsiViewExecute` at `0x18002e9d1`

## pseudocode

```c
__int64 CGenerateMSI::_InsertRow(
        CGenerateMSI *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        ...)
{
  signed int v5; // eax
  signed int v6; // ebx
  bool v7; // sf
  MSIHANDLE phView[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v10[2048]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szQuery[2048]; // [rsp+1040h] [rbp+F40h] BYREF
  va_list va; // [rsp+2090h] [rbp+1F90h] BYREF

  va_start(va, a4);
  *(_QWORD *)phView = 0;
  if ( (int)StringCchPrintfW(v10, 0x800u, L"INSERT INTO %s (%s) VALUES (%s)", a2, a3, a4) >= 0
    && (int)StringCchVPrintfW(szQuery, 0x800u, v10, va) >= 0 )
  {
    v5 = MsiDatabaseOpenViewW(*((_DWORD *)this + 16), szQuery, phView);
    v6 = v5;
    if ( v5 )
    {
      if ( v5 <= 0 )
      {
LABEL_10:
        v7 = v6 < 0;
        goto LABEL_11;
      }
      v6 = (unsigned __int16)v5;
    }
    else
    {
      v6 = MsiViewExecute(phView[0], 0);
      if ( !v6 )
      {
        v6 = 0;
        goto LABEL_14;
      }
      MsiCloseHandle(phView[0]);
      v7 = v6 < 0;
      if ( v6 <= 0 )
      {
LABEL_11:
        if ( v7 )
          return (unsigned int)v6;
LABEL_14:
        MsiCloseHandle(phView[0]);
        return (unsigned int)v6;
      }
      v6 = (unsigned __int16)v6;
    }
    v6 |= 0x80070000;
    goto LABEL_10;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002e91c  mov     [rsp-8+arg_18], r9
0x18002e921  push    rbp
0x18002e922  push    rbx
0x18002e923  push    rsi
0x18002e924  lea     rbp, [rsp-1F50h]
0x18002e92c  mov     eax, 2050h
0x18002e931  call    _alloca_probe
0x18002e936  sub     rsp, rax
0x18002e939  mov     rax, cs:__security_cookie
0x18002e940  xor     rax, rsp
0x18002e943  mov     [rbp+1F60h+var_20], rax
0x18002e94a  mov     [rsp+2060h+var_2038], r9
0x18002e94f  lea     rsi, [rbp+1F60h+arg_20]
0x18002e956  mov     [rsp+2060h+var_2040], r8
0x18002e95b  mov     r9, rdx
0x18002e95e  mov     rbx, rcx
0x18002e961  mov     qword ptr [rsp+2060h+phView], 0
0x18002e96a  lea     r8, aInsertIntoSSVa; "INSERT INTO %s (%s) VALUES (%s)"
0x18002e971  mov     [rsp+2060h+phView], 0
0x18002e979  mov     edx, 800h; unsigned __int64
0x18002e97e  lea     rcx, [rsp+2060h+var_2020]; unsigned __int16 *
0x18002e983  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e988  test    eax, eax
0x18002e98a  js      short loc_18002EA0A
0x18002e98c  mov     r9, rsi; char *
0x18002e98f  lea     r8, [rsp+2060h+var_2020]; unsigned __int16 *
0x18002e994  mov     edx, 800h; unsigned __int64
0x18002e999  lea     rcx, [rbp+1F60h+szQuery]; unsigned __int16 *
0x18002e9a0  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18002e9a5  test    eax, eax
0x18002e9a7  js      short loc_18002EA0A
0x18002e9a9  mov     ecx, [rbx+40h]; hDatabase
0x18002e9ac  lea     r8, [rsp+2060h+phView]; phView
0x18002e9b1  lea     rdx, [rbp+1F60h+szQuery]; szQuery
0x18002e9b8  call    cs:__imp_MsiDatabaseOpenViewW
0x18002e9be  mov     ebx, eax
0x18002e9c0  test    eax, eax
0x18002e9c2  jz      short loc_18002E9CB
0x18002e9c4  jle     short loc_18002E9F4
0x18002e9c6  movzx   ebx, ax
0x18002e9c9  jmp     short loc_18002E9EE
0x18002e9cb  mov     ecx, [rsp+2060h+phView]; hView
0x18002e9cf  xor     edx, edx; hRecord
0x18002e9d1  call    cs:__imp_MsiViewExecute
0x18002e9d7  mov     ebx, eax
0x18002e9d9  test    eax, eax
0x18002e9db  jz      short loc_18002E9FA
0x18002e9dd  mov     ecx, [rsp+2060h+phView]; hAny
0x18002e9e1  call    cs:__imp_MsiCloseHandle
0x18002e9e7  test    ebx, ebx
0x18002e9e9  jle     short loc_18002E9F6
0x18002e9eb  movzx   ebx, bx
0x18002e9ee  or      ebx, 80070000h
0x18002e9f4  test    ebx, ebx
0x18002e9f6  js      short loc_18002EA06
0x18002e9f8  jmp     short loc_18002E9FC
0x18002e9fa  xor     ebx, ebx
0x18002e9fc  mov     ecx, [rsp+2060h+phView]; hAny
0x18002ea00  call    cs:__imp_MsiCloseHandle
0x18002ea06  mov     eax, ebx
0x18002ea08  jmp     short loc_18002EA0F
0x18002ea0a  mov     eax, 80070057h
0x18002ea0f  mov     rcx, [rbp+1F60h+var_20]
0x18002ea16  xor     rcx, rsp; StackCookie
0x18002ea19  call    __security_check_cookie
0x18002ea1e  add     rsp, 2050h
0x18002ea25  pop     rsi
0x18002ea26  pop     rbx
0x18002ea27  pop     rbp
0x18002ea28  retn
```
