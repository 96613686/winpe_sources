# CellStateFromKey(HKEY__ *)

- ea: `0x18000fe50`
- end: `0x18001007d`
- name: `?CellStateFromKey@@YA?AVCellState@@PEAUHKEY__@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(__int64, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180011060`

## callees

- `0x180002c08`
- `0x18000fe50`
- `0x1800114a0`
- `0x180012390`
- `0x1800128a4`
- `0x1800386fc`
- `0x18003f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001001a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001001a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ffd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ffd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000fee0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000fee0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ff56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ff56`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010006`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010006`

## pseudocode

```c
__int64 __fastcall CellStateFromKey(__int64 a1, HKEY a2)
{
  unsigned int v4; // eax
  DWORD v5; // eax
  WCHAR *v6; // rbx
  DWORD v7; // r14d
  DWORD i; // edx
  unsigned int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rax
  volatile signed __int32 *v12; // rdi
  unsigned int v13; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-49h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-49h]
  unsigned int lpcSubKeysb; // [rsp+20h] [rbp-49h]
  HKEY phkResult[2]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v19[8]; // [rsp+78h] [rbp+Fh] BYREF
  volatile signed __int32 *v20; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cbMaxSubKeyLen; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cchName; // [rsp+E8h] [rbp+7Fh] BYREF

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 24) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::shared_ptr<Modem>>>>::_Buyheadnode();
  *(_DWORD *)(a1 + 40) = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(a2, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x239,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)v4,
      lpcSubKeys);
  v5 = cbMaxSubKeyLen;
  if ( cbMaxSubKeyLen )
  {
    ++cbMaxSubKeyLen;
    v6 = (WCHAR *)operator new[](saturated_mul(v5 + 1, 2u));
    phkResult[1] = (HKEY)v6;
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      cchName = cbMaxSubKeyLen;
      v13 = RegEnumKeyExW(a2, i, v6, &cchName, 0, 0, 0, 0);
      if ( v13 == 259 )
        break;
      if ( v13 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x24B,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
          (const char *)v13,
          lpcSubKeysb);
      phkResult[0] = 0;
      v9 = RegOpenKeyExW(a2, v6, 0, 0x20019u, phkResult);
      if ( v9 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x24F,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
          (const char *)v9,
          lpcSubKeysa);
      LOBYTE(v10) = v7 == 0;
      v11 = ModemFromKey(v19, phkResult[0], v6, v10);
      CellState::operator+=(a1, v11);
      v12 = v20;
      if ( v20 )
      {
        if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      if ( phkResult[0] )
        RegCloseKey(phkResult[0]);
      ++v7;
    }
    operator delete[](v6);
  }
  return a1;
}

```

## disassembly

```asm
0x18000fe50  mov     [rsp-8+arg_8], rbx
0x18000fe55  mov     [rsp-8+arg_0], rcx
0x18000fe5a  push    rbp
0x18000fe5b  push    rsi
0x18000fe5c  push    rdi
0x18000fe5d  push    r12
0x18000fe5f  push    r13
0x18000fe61  push    r14
0x18000fe63  push    r15
0x18000fe65  lea     rbp, [rsp-27h]
0x18000fe6a  sub     rsp, 90h
0x18000fe71  mov     r15, rdx
0x18000fe74  mov     rsi, rcx
0x18000fe77  xor     r12d, r12d
0x18000fe7a  mov     [rbp+57h+var_60], r12d
0x18000fe7e  mov     [rcx], r12
0x18000fe81  mov     [rcx+8], r12
0x18000fe85  mov     [rcx+10h], r12
0x18000fe89  mov     [rcx+18h], r12
0x18000fe8d  mov     [rcx+20h], r12
0x18000fe91  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UModem@@@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::shared_ptr<Modem>>>>::_Buyheadnode(void)
0x18000fe96  mov     [rsi+18h], rax
0x18000fe9a  mov     [rsi+28h], r12d
0x18000fe9e  mov     [rbp+57h+var_60], 1
0x18000fea5  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x18000fea9  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000feae  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000feb3  mov     [rsp+0C0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18000feb8  mov     [rsp+0C0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18000febd  mov     [rsp+0C0h+lpcValues], r12; lpcValues
0x18000fec2  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000fec7  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000fecb  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000fed0  mov     [rsp+0C0h+lpcSubKeys], r12; unsigned int
0x18000fed5  xor     r9d, r9d; lpReserved
0x18000fed8  xor     r8d, r8d; lpcchClass
0x18000fedb  xor     edx, edx; lpClass
0x18000fedd  mov     rcx, r15; hKey
0x18000fee0  call    cs:__imp_RegQueryInfoKeyW
0x18000fee6  mov     rcx, [rbp+5Fh]; this
0x18000feea  test    eax, eax
0x18000feec  jnz     loc_180010068
0x18000fef2  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000fef5  test    eax, eax
0x18000fef7  jz      loc_180010020
0x18000fefd  inc     eax
0x18000feff  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x18000ff02  mov     ecx, eax
0x18000ff04  lea     eax, [r12+2]
0x18000ff09  mul     rcx
0x18000ff0c  lea     r13, [r12-1]
0x18000ff11  cmovb   rax, r13
0x18000ff15  mov     rcx, rax; unsigned __int64
0x18000ff18  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ff1d  mov     rbx, rax
0x18000ff20  mov     [rbp+57h+var_50], rax
0x18000ff24  mov     r14d, r12d
0x18000ff27  xor     edx, edx
0x18000ff29  jmp     loc_18000FFE2
0x18000ff2e  mov     rcx, [rbp+5Fh]; this
0x18000ff32  test    eax, eax
0x18000ff34  jnz     loc_180010053
0x18000ff3a  mov     [rbp+57h+phkResult], r12
0x18000ff3e  lea     rax, [rbp+57h+phkResult]
0x18000ff42  mov     [rsp+0C0h+lpcSubKeys], rax; unsigned int
0x18000ff47  mov     r9d, 20019h; samDesired
0x18000ff4d  xor     r8d, r8d; ulOptions
0x18000ff50  mov     rdx, rbx; lpSubKey
0x18000ff53  mov     rcx, r15; hKey
0x18000ff56  call    cs:__imp_RegOpenKeyExW
0x18000ff5c  mov     rcx, [rbp+5Fh]; this
0x18000ff60  test    eax, eax
0x18000ff62  jnz     loc_18001003E
0x18000ff68  test    r14d, r14d
0x18000ff6b  setz    r9b
0x18000ff6f  mov     r8, rbx
0x18000ff72  mov     rdx, [rbp+57h+phkResult]
0x18000ff76  lea     rcx, [rbp+57h+var_48]
0x18000ff7a  call    ?ModemFromKey@@YA?AV?$shared_ptr@UModem@@@std@@PEAUHKEY__@@PEBG_N@Z; ModemFromKey(HKEY__ *,ushort const *,bool)
0x18000ff7f  nop
0x18000ff80  mov     rdx, rax
0x18000ff83  mov     rcx, rsi
0x18000ff86  call    ??YCellState@@QEAAAEAV0@AEBV?$shared_ptr@UModem@@@std@@@Z; CellState::operator+=(std::shared_ptr<Modem> const &)
0x18000ff8b  nop
0x18000ff8c  mov     rdi, [rbp+57h+var_40]
0x18000ff90  test    rdi, rdi
0x18000ff93  jz      short loc_18000FFCD
0x18000ff95  mov     eax, r13d
0x18000ff98  lock xadd [rdi+8], eax
0x18000ff9d  add     eax, r13d
0x18000ffa0  jnz     short loc_18000FFCD
0x18000ffa2  mov     rax, [rdi]
0x18000ffa5  mov     rcx, rdi
0x18000ffa8  mov     rax, [rax]
0x18000ffab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb0  mov     eax, r13d
0x18000ffb3  lock xadd [rdi+0Ch], eax
0x18000ffb8  add     eax, r13d
0x18000ffbb  jnz     short loc_18000FFCD
0x18000ffbd  mov     rax, [rdi]
0x18000ffc0  mov     rcx, rdi
0x18000ffc3  mov     rax, [rax+8]
0x18000ffc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffcc  nop
0x18000ffcd  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000ffd1  test    rcx, rcx
0x18000ffd4  jz      short loc_18000FFDC
0x18000ffd6  call    cs:__imp_RegCloseKey
0x18000ffdc  inc     r14d
0x18000ffdf  mov     edx, r14d; dwIndex
0x18000ffe2  mov     [rsp+0C0h+lpcValues], r12; lpftLastWriteTime
0x18000ffe7  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcchClass
0x18000ffec  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12; lpClass
0x18000fff1  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000fff4  mov     [rsp+0C0h+lpcSubKeys], r12; unsigned int
0x18000fff9  mov     [rbp+57h+cchName], eax
0x18000fffc  lea     r9, [rbp+57h+cchName]; lpcchName
0x180010000  mov     r8, rbx; lpName
0x180010003  mov     rcx, r15; hKey
0x180010006  call    cs:__imp_RegEnumKeyExW
0x18001000c  cmp     eax, 103h
0x180010011  jnz     loc_18000FF2E
0x180010017  mov     rcx, rbx
0x18001001a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010020  mov     rax, rsi
0x180010023  mov     rbx, [rsp+0C0h+arg_8]
0x18001002b  add     rsp, 90h
0x180010032  pop     r15
0x180010034  pop     r14
0x180010036  pop     r13
0x180010038  pop     r12
0x18001003a  pop     rdi
0x18001003b  pop     rsi
0x18001003c  pop     rbp
0x18001003d  retn
0x18001003e  mov     r9d, eax; char *
0x180010041  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180010048  mov     edx, 24Fh; void *
0x18001004d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180010053  mov     r9d, eax; char *
0x180010056  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001005d  mov     edx, 24Bh; void *
0x180010062  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180010068  mov     r9d, eax; char *
0x18001006b  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180010072  mov     edx, 239h; void *
0x180010077  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
