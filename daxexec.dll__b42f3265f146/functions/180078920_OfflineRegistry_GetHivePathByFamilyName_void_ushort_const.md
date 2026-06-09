# OfflineRegistry::GetHivePathByFamilyName(void *,ushort const *)

- ea: `0x180078920`
- end: `0x180078b1d`
- name: `?GetHivePathByFamilyName@OfflineRegistry@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXPEBG@Z`
- size: `509`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18007161c`
- `0x180089fd8`

## callees

- `0x180005340`
- `0x18000afe4`
- `0x1800125f4`
- `0x18001544c`
- `0x180016da0`
- `0x1800210fc`
- `0x180022044`
- `0x180024924`
- `0x180078920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800789f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800789f6`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180078a88`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180078a88`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180078a98`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180078a98`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataFolder` at `0x18007897c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataFolder` at `0x1800789e7`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataFolder` at `0x18007897c`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataFolder` at `0x1800789e7`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180078946`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180078946`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180078ab6`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180078ab6`

## string_xrefs

- `0x180078ae1`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`
- `0x180078af3`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`
- `0x180078b08`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OfflineRegistry::GetHivePathByFamilyName(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbx
  const char *v5; // r9
  signed int LastError; // eax
  char v7; // cl
  void *v8; // rsi
  int SystemAppDataFolder; // r14d
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

  v4 = OpenStateExplicit(a2, a3);
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      v5);
  v22 = 0;
  GetSystemAppDataFolder(v4, 0, &v22);
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
      (void *)0x16,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      (const char *)(unsigned int)LastError,
      v14);
  v8 = operator new[](saturated_mul(v22, 2u));
  SystemAppDataFolder = GetSystemAppDataFolder(v4, v8, &v22);
  v10 = GetLastError();
  if ( v10 > 0 )
    v10 = (unsigned __int16)v10 | 0x80070000;
  if ( SystemAppDataFolder != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
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
0x180078920  mov     [rsp-8+arg_0], rbx
0x180078925  mov     [rsp-8+arg_8], rsi
0x18007892a  push    rbp
0x18007892b  push    rdi
0x18007892c  push    r14
0x18007892e  lea     rbp, [rsp-40h]
0x180078933  sub     rsp, 140h
0x18007893a  mov     rax, rdx
0x18007893d  mov     rdi, rcx
0x180078940  mov     rdx, r8
0x180078943  mov     rcx, rax
0x180078946  call    cs:__imp_OpenStateExplicit
0x18007894d  nop     dword ptr [rax+rax+00h]
0x180078952  mov     rbx, rax
0x180078955  mov     [rsp+150h+var_128], rax
0x18007895a  test    rax, rax
0x18007895d  setnz   al
0x180078960  mov     rcx, [rbp+58h]; this
0x180078964  test    al, al
0x180078966  jz      loc_180078AF3
0x18007896c  mov     [rbp+50h+arg_18], 0
0x180078973  lea     r8, [rbp+50h+arg_18]
0x180078977  xor     edx, edx
0x180078979  mov     rcx, rbx
0x18007897c  call    cs:__imp_GetSystemAppDataFolder
0x180078983  nop     dword ptr [rax+rax+00h]
0x180078988  call    cs:__imp_GetLastError
0x18007898f  nop     dword ptr [rax+rax+00h]
0x180078994  cmp     eax, 7Ah ; 'z'
0x180078997  jnz     short loc_18007899D
0x180078999  xor     cl, cl
0x18007899b  jmp     short loc_1800789A3
0x18007899d  mov     cl, 1
0x18007899f  test    eax, eax
0x1800789a1  jle     short loc_1800789AB
0x1800789a3  movzx   eax, ax
0x1800789a6  or      eax, 80070000h
0x1800789ab  mov     r10, [rbp+58h]
0x1800789af  test    cl, cl
0x1800789b1  jnz     loc_180078B05
0x1800789b7  mov     ecx, [rbp+50h+arg_18]
0x1800789ba  mov     eax, 2
0x1800789bf  mul     rcx
0x1800789c2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800789c9  cmovb   rax, rcx
0x1800789cd  mov     rcx, rax; unsigned __int64
0x1800789d0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800789d5  mov     rsi, rax
0x1800789d8  mov     [rsp+150h+var_120], rax
0x1800789dd  lea     r8, [rbp+50h+arg_18]
0x1800789e1  mov     rdx, rax
0x1800789e4  mov     rcx, rbx
0x1800789e7  call    cs:__imp_GetSystemAppDataFolder
0x1800789ee  nop     dword ptr [rax+rax+00h]
0x1800789f3  mov     r14d, eax
0x1800789f6  call    cs:__imp_GetLastError
0x1800789fd  nop     dword ptr [rax+rax+00h]
0x180078a02  test    eax, eax
0x180078a04  jle     short loc_180078A0E
0x180078a06  movzx   eax, ax
0x180078a09  or      eax, 80070000h
0x180078a0e  mov     rcx, [rbp+58h]; this
0x180078a12  cmp     r14d, 1
0x180078a16  jnz     loc_180078ADE
0x180078a1c  lea     rcx, [rsp+150h+var_110]
0x180078a21  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180078a26  nop
0x180078a27  mov     rdx, rsi
0x180078a2a  lea     rcx, [rsp+150h+var_100]
0x180078a2f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180078a34  mov     rcx, rax
0x180078a37  lea     rdx, aHelium; "\\Helium"
0x180078a3e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180078a43  mov     rdx, rdi
0x180078a46  lea     rcx, [rsp+150h+var_F8]
0x180078a4b  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180078a50  nop
0x180078a51  mov     rax, [rsp+150h+var_110]
0x180078a56  movsxd  rcx, dword ptr [rax+4]
0x180078a5a  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180078a61  mov     [rsp+rcx+150h+var_110], rax
0x180078a66  mov     rax, [rsp+150h+var_110]
0x180078a6b  movsxd  rcx, dword ptr [rax+4]
0x180078a6f  lea     edx, [rcx-98h]
0x180078a75  mov     [rsp+rcx+150h+var_114], edx
0x180078a79  lea     rcx, [rsp+150h+var_F8]
0x180078a7e  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x180078a83  lea     rcx, [rsp+150h+var_F0]
0x180078a88  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x180078a8f  nop     dword ptr [rax+rax+00h]
0x180078a94  lea     rcx, [rbp+50h+var_78]
0x180078a98  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180078a9f  nop     dword ptr [rax+rax+00h]
0x180078aa4  nop
0x180078aa5  mov     rcx, rsi; void *
0x180078aa8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180078aad  nop
0x180078aae  test    rbx, rbx
0x180078ab1  jz      short loc_180078AC2
0x180078ab3  mov     rcx, rbx
0x180078ab6  call    cs:__imp_CloseState
0x180078abd  nop     dword ptr [rax+rax+00h]
0x180078ac2  mov     rax, rdi
0x180078ac5  lea     r11, [rsp+150h+var_10]
0x180078acd  mov     rbx, [r11+20h]
0x180078ad1  mov     rsi, [r11+28h]
0x180078ad5  mov     rsp, r11
0x180078ad8  pop     r14
0x180078ada  pop     rdi
0x180078adb  pop     rbp
0x180078adc  retn
0x180078ade  mov     r9d, eax; char *
0x180078ae1  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\execmodel\\des"...
0x180078ae8  mov     edx, 1Ah; void *
0x180078aed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180078af3  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\execmodel\\des"...
0x180078afa  mov     edx, 11h; void *
0x180078aff  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180078b05  mov     r9d, eax; char *
0x180078b08  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\execmodel\\des"...
0x180078b0f  mov     edx, 16h; void *
0x180078b14  mov     rcx, r10; this
0x180078b17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
