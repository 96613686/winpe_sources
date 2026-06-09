# UpdateProperty(ulong,ushort const *,ushort const *)

- ea: `0x180026d98`
- end: `0x180026edc`
- name: `?UpdateProperty@@YAJKPEBG0@Z`
- size: `324`
- prototype: `__int64 __fastcall(MSIHANDLE hDatabase, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18002673c`

## callees

- `0x180009ee0`
- `0x18001a6c8`
- `0x180026d98`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x180026e9e`
- `msi!__imp_MsiCloseHandle` at `0x180026e9e`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026e82`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180026e82`
- `msi!__imp_MsiViewExecute` at `0x180026e93`
- `msi!__imp_MsiViewExecute` at `0x180026e93`

## string_xrefs

- `0x180026dc0`: `UPDATE Property SET Value = '%s' WHERE Property = '%s'`

## pseudocode

```c
__int64 __fastcall UpdateProperty(MSIHANDLE hDatabase, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v5; // eax
  __int64 v6; // r8
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  __int64 result; // rax
  signed int v13; // ebx
  bool v14; // cc
  WCHAR szQuery[2]; // [rsp+30h] [rbp+0h] BYREF
  unsigned __int16 v16[8]; // [rsp+40h] [rbp+10h] BYREF
  __int128 v17; // [rsp+50h] [rbp+20h]
  __int128 v18; // [rsp+60h] [rbp+30h]
  __int128 v19; // [rsp+70h] [rbp+40h]
  __int128 v20; // [rsp+80h] [rbp+50h]
  _OWORD v21[2]; // [rsp+90h] [rbp+60h]

  *(_OWORD *)v16 = *(_OWORD *)L"UPDATE Property SET Value = '%s' WHERE Property = '%s'";
  v18 = *(_OWORD *)L"SET Value = '%s' WHERE Property = '%s'";
  v17 = *(_OWORD *)L"roperty SET Value = '%s' WHERE Property = '%s'";
  v20 = *(_OWORD *)L" WHERE Property = '%s'";
  v19 = *(_OWORD *)L"e = '%s' WHERE Property = '%s'";
  v21[0] = *(_OWORD *)L"roperty = '%s'";
  *(_OWORD *)((char *)v21 + 14) = *(_OWORD *)L" = '%s'";
  safe_lstrlenW(a3);
  v5 = safe_lstrlenW(a2);
  v7 = v6 + v5 + 56LL;
  v8 = 2 * v7 + 15;
  if ( v8 <= 2 * v7 )
    v8 = 0xFFFFFFFFFFFFFF0LL;
  v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
  v10 = alloca(v9);
  v11 = alloca(v9);
  result = StringCchPrintfW(szQuery, v7, v16);
  if ( (int)result >= 0 )
  {
    *(_DWORD *)szQuery = 0;
    v13 = MsiDatabaseOpenViewW(hDatabase, szQuery, (MSIHANDLE *)szQuery);
    if ( v13 )
    {
      v14 = v13 < 0;
    }
    else
    {
      v13 = MsiViewExecute(*(MSIHANDLE *)szQuery, 0);
      MsiCloseHandle(*(MSIHANDLE *)szQuery);
      v14 = v13 <= 0;
      if ( !v13 )
        return 0;
    }
    if ( !v14 )
      return (unsigned __int16)v13 | 0x80070000;
    return (unsigned int)v13;
  }
  return result;
}

```

## disassembly

```asm
0x180026d98  push    rbp
0x180026d9a  push    rsi
0x180026d9b  push    rdi
0x180026d9c  sub     rsp, 0C0h
0x180026da3  lea     rbp, [rsp+30h]
0x180026da8  mov     [rbp+0A0h+arg_18], rbx
0x180026daf  mov     rax, cs:__security_cookie
0x180026db6  xor     rax, rbp
0x180026db9  mov     [rbp+0A0h+var_20], rax
0x180026dc0  movaps  xmm0, xmmword ptr cs:aUpdateProperty; "UPDATE Property SET Value = '%s' WHERE "...
0x180026dc7  mov     edi, ecx
0x180026dc9  movaps  xmm1, xmmword ptr cs:aUpdateProperty+10h; "roperty SET Value = '%s' WHERE Property"...
0x180026dd0  mov     rcx, r8; unsigned __int16 *
0x180026dd3  movaps  xmmword ptr [rbp+0A0h+var_90], xmm0
0x180026dd7  mov     r9, r8
0x180026dda  movaps  xmm0, xmmword ptr cs:aUpdateProperty+20h; "SET Value = '%s' WHERE Property = '%s'"
0x180026de1  mov     rsi, rdx
0x180026de4  movaps  [rbp+0A0h+var_70], xmm0
0x180026de8  movaps  xmm0, xmmword ptr cs:aUpdateProperty+40h; " WHERE Property = '%s'"
0x180026def  movaps  [rbp+0A0h+var_80], xmm1
0x180026df3  movaps  xmm1, xmmword ptr cs:aUpdateProperty+30h; "e = '%s' WHERE Property = '%s'"
0x180026dfa  movaps  [rbp+0A0h+var_50], xmm0
0x180026dfe  movups  xmm0, xmmword ptr cs:aUpdateProperty+5Eh; " = '%s'"
0x180026e05  movaps  [rbp+0A0h+var_60], xmm1
0x180026e09  movaps  xmm1, xmmword ptr cs:aUpdateProperty+50h; "roperty = '%s'"
0x180026e10  movaps  xmmword ptr [rbp+0A0h+var_40], xmm1
0x180026e14  movups  xmmword ptr [rbp+0A0h+var_40+0Eh], xmm0
0x180026e18  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180026e1d  mov     rcx, rsi; unsigned __int16 *
0x180026e20  movsxd  r8, eax
0x180026e23  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180026e28  movsxd  rdx, eax
0x180026e2b  add     rdx, 38h ; '8'
0x180026e2f  add     rdx, r8
0x180026e32  lea     rax, [rdx+rdx]
0x180026e36  lea     rcx, [rax+0Fh]
0x180026e3a  cmp     rcx, rax
0x180026e3d  ja      short loc_180026E49
0x180026e3f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180026e49  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180026e4d  mov     rax, rcx
0x180026e50  call    _alloca_probe
0x180026e55  sub     rsp, rcx
0x180026e58  lea     r8, [rbp+0A0h+var_90]; unsigned __int16 *
0x180026e5c  lea     rbx, [rsp+0D0h+szQuery]
0x180026e61  mov     [rsp+0D0h+var_B0], rsi
0x180026e66  mov     rcx, rbx; unsigned __int16 *
0x180026e69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026e6e  test    eax, eax
0x180026e70  js      short loc_180026EBB
0x180026e72  lea     r8, [rbp+0A0h+szQuery]; phView
0x180026e76  mov     dword ptr [rbp+0A0h+szQuery], 0
0x180026e7d  mov     rdx, rbx; szQuery
0x180026e80  mov     ecx, edi; hDatabase
0x180026e82  call    cs:__imp_MsiDatabaseOpenViewW
0x180026e88  mov     ebx, eax
0x180026e8a  test    eax, eax
0x180026e8c  jnz     short loc_180026EAC
0x180026e8e  mov     ecx, dword ptr [rbp+0A0h+szQuery]; hView
0x180026e91  xor     edx, edx; hRecord
0x180026e93  call    cs:__imp_MsiViewExecute
0x180026e99  mov     ecx, dword ptr [rbp+0A0h+szQuery]; hAny
0x180026e9c  mov     ebx, eax
0x180026e9e  call    cs:__imp_MsiCloseHandle
0x180026ea4  test    ebx, ebx
0x180026ea6  jnz     short loc_180026EAE
0x180026ea8  xor     eax, eax
0x180026eaa  jmp     short loc_180026EBB
0x180026eac  test    ebx, ebx
0x180026eae  jle     short loc_180026EB9
0x180026eb0  movzx   ebx, bx
0x180026eb3  or      ebx, 80070000h
0x180026eb9  mov     eax, ebx
0x180026ebb  mov     rcx, [rbp+0A0h+var_20]
0x180026ec2  xor     rcx, rbp; StackCookie
0x180026ec5  call    __security_check_cookie
0x180026eca  mov     rbx, [rbp+0A0h+arg_18]
0x180026ed1  lea     rsp, [rbp+90h]
0x180026ed8  pop     rdi
0x180026ed9  pop     rsi
0x180026eda  pop     rbp
0x180026edb  retn
```
