# OfflineRegistry::GetSecureHivePathForFamilyAndUser(ushort const *,void *)

- ea: `0x180078d84`
- end: `0x180078f7b`
- name: `?GetSecureHivePathForFamilyAndUser@OfflineRegistry@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAX@Z`
- size: `503`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18007161c`
- `0x1800893f8`
- `0x1800899a0`

## callees

- `0x180005340`
- `0x18000afe4`
- `0x1800125f4`
- `0x18001544c`
- `0x180016da0`
- `0x1800210fc`
- `0x180022044`
- `0x180024924`
- `0x180078d84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078e54`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180078ee6`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180078ee6`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180078ef6`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180078ef6`
- `api-ms-win-appmodel-state-l1-2-0!GetSecureSystemAppDataFolder` at `0x180078dda`
- `api-ms-win-appmodel-state-l1-2-0!GetSecureSystemAppDataFolder` at `0x180078e45`
- `api-ms-win-appmodel-state-l1-2-0!GetSecureSystemAppDataFolder` at `0x180078dda`
- `api-ms-win-appmodel-state-l1-2-0!GetSecureSystemAppDataFolder` at `0x180078e45`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180078da4`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180078da4`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180078f14`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180078f14`

## string_xrefs

- `0x180078f3f`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`
- `0x180078f51`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`
- `0x180078f66`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OfflineRegistry::GetSecureHivePathForFamilyAndUser(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  const char *v5; // r9
  signed int LastError; // eax
  char v7; // cl
  void *v8; // rsi
  int SecureSystemAppDataFolder; // r14d
  signed int v10; // eax
  __int64 v11; // rax
  unsigned __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+3Ch] [rbp-C4h]
  _QWORD v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v19[120]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[104]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  unsigned int v22; // [rsp+178h] [rbp+78h] BYREF

  v4 = OpenStateExplicit(a3, a2);
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      v5);
  v22 = 0;
  GetSecureSystemAppDataFolder(v4, 0, &v22);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v7 = 0;
  }
  else
  {
    v7 = 1;
    if ( LastError <= 0 )
      goto LABEL_6;
  }
  LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_6:
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      (const char *)(unsigned int)LastError,
      v14);
  v8 = operator new[](saturated_mul(v22, 2u));
  SecureSystemAppDataFolder = GetSecureSystemAppDataFolder(v4, v8, &v22);
  v10 = GetLastError();
  if ( v10 > 0 )
    v10 = (unsigned __int16)v10 | 0x80070000;
  if ( SecureSystemAppDataFolder != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      (const char *)(unsigned int)v10,
      v14);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v16);
  v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, v8);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"\\Helium");
  std::basic_stringbuf<unsigned short>::str(v18, a1);
  *(_QWORD *)((char *)v16 + *(int *)(v16[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(int *)((char *)&v15 + *(int *)(v16[0] + 4LL)) = *(_DWORD *)(v16[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v18);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v19);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v20);
  operator delete(v8, v12);
  CloseState(v4);
  return a1;
}

```

## disassembly

```asm
0x180078d84  mov     [rsp-8+arg_0], rbx
0x180078d89  mov     [rsp-8+arg_8], rsi
0x180078d8e  push    rbp
0x180078d8f  push    rdi
0x180078d90  push    r14
0x180078d92  lea     rbp, [rsp-40h]
0x180078d97  sub     rsp, 140h
0x180078d9e  mov     rdi, rcx
0x180078da1  mov     rcx, r8
0x180078da4  call    cs:__imp_OpenStateExplicit
0x180078dab  nop     dword ptr [rax+rax+00h]
0x180078db0  mov     rbx, rax
0x180078db3  mov     [rsp+150h+var_128], rax
0x180078db8  test    rax, rax
0x180078dbb  setnz   al
0x180078dbe  mov     rcx, [rbp+58h]; this
0x180078dc2  test    al, al
0x180078dc4  jz      loc_180078F51
0x180078dca  mov     [rbp+50h+arg_18], 0
0x180078dd1  lea     r8, [rbp+50h+arg_18]
0x180078dd5  xor     edx, edx
0x180078dd7  mov     rcx, rbx
0x180078dda  call    cs:__imp_GetSecureSystemAppDataFolder
0x180078de1  nop     dword ptr [rax+rax+00h]
0x180078de6  call    cs:__imp_GetLastError
0x180078ded  nop     dword ptr [rax+rax+00h]
0x180078df2  cmp     eax, 7Ah ; 'z'
0x180078df5  jnz     short loc_180078DFB
0x180078df7  xor     cl, cl
0x180078df9  jmp     short loc_180078E01
0x180078dfb  mov     cl, 1
0x180078dfd  test    eax, eax
0x180078dff  jle     short loc_180078E09
0x180078e01  movzx   eax, ax
0x180078e04  or      eax, 80070000h
0x180078e09  mov     r10, [rbp+58h]
0x180078e0d  test    cl, cl
0x180078e0f  jnz     loc_180078F63
0x180078e15  mov     ecx, [rbp+50h+arg_18]
0x180078e18  mov     eax, 2
0x180078e1d  mul     rcx
0x180078e20  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180078e27  cmovb   rax, rcx
0x180078e2b  mov     rcx, rax; unsigned __int64
0x180078e2e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180078e33  mov     rsi, rax
0x180078e36  mov     [rsp+150h+var_120], rax
0x180078e3b  lea     r8, [rbp+50h+arg_18]
0x180078e3f  mov     rdx, rax
0x180078e42  mov     rcx, rbx
0x180078e45  call    cs:__imp_GetSecureSystemAppDataFolder
0x180078e4c  nop     dword ptr [rax+rax+00h]
0x180078e51  mov     r14d, eax
0x180078e54  call    cs:__imp_GetLastError
0x180078e5b  nop     dword ptr [rax+rax+00h]
0x180078e60  test    eax, eax
0x180078e62  jle     short loc_180078E6C
0x180078e64  movzx   eax, ax
0x180078e67  or      eax, 80070000h
0x180078e6c  mov     rcx, [rbp+58h]; this
0x180078e70  cmp     r14d, 1
0x180078e74  jnz     loc_180078F3C
0x180078e7a  lea     rcx, [rsp+150h+var_110]
0x180078e7f  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180078e84  nop
0x180078e85  mov     rdx, rsi
0x180078e88  lea     rcx, [rsp+150h+var_100]
0x180078e8d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180078e92  mov     rcx, rax
0x180078e95  lea     rdx, aHelium; "\\Helium"
0x180078e9c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180078ea1  mov     rdx, rdi
0x180078ea4  lea     rcx, [rsp+150h+var_F8]
0x180078ea9  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180078eae  nop
0x180078eaf  mov     rax, [rsp+150h+var_110]
0x180078eb4  movsxd  rcx, dword ptr [rax+4]
0x180078eb8  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180078ebf  mov     [rsp+rcx+150h+var_110], rax
0x180078ec4  mov     rax, [rsp+150h+var_110]
0x180078ec9  movsxd  rcx, dword ptr [rax+4]
0x180078ecd  lea     edx, [rcx-98h]
0x180078ed3  mov     [rsp+rcx+150h+var_114], edx
0x180078ed7  lea     rcx, [rsp+150h+var_F8]
0x180078edc  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x180078ee1  lea     rcx, [rsp+150h+var_F0]
0x180078ee6  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x180078eed  nop     dword ptr [rax+rax+00h]
0x180078ef2  lea     rcx, [rbp+50h+var_78]
0x180078ef6  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180078efd  nop     dword ptr [rax+rax+00h]
0x180078f02  nop
0x180078f03  mov     rcx, rsi; void *
0x180078f06  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180078f0b  nop
0x180078f0c  test    rbx, rbx
0x180078f0f  jz      short loc_180078F20
0x180078f11  mov     rcx, rbx
0x180078f14  call    cs:__imp_CloseState
0x180078f1b  nop     dword ptr [rax+rax+00h]
0x180078f20  mov     rax, rdi
0x180078f23  lea     r11, [rsp+150h+var_10]
0x180078f2b  mov     rbx, [r11+20h]
0x180078f2f  mov     rsi, [r11+28h]
0x180078f33  mov     rsp, r11
0x180078f36  pop     r14
0x180078f38  pop     rdi
0x180078f39  pop     rbp
0x180078f3a  retn
0x180078f3c  mov     r9d, eax; char *
0x180078f3f  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\execmodel\\des"...
0x180078f46  mov     edx, 43h ; 'C'; void *
0x180078f4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180078f51  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\execmodel\\des"...
0x180078f58  mov     edx, 3Ah ; ':'; void *
0x180078f5d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180078f63  mov     r9d, eax; char *
0x180078f66  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\execmodel\\des"...
0x180078f6d  mov     edx, 3Fh ; '?'; void *
0x180078f72  mov     rcx, r10; this
0x180078f75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
