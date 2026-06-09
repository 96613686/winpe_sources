# OfflineRegistry::GetHivePathByFamilyName(void *,ushort const *)

- ea: `0x180076f74`
- end: `0x18007716e`
- name: `?GetHivePathByFamilyName@OfflineRegistry@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXPEBG@Z`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18006fabc`
- `0x180088994`

## callees

- `0x180005794`
- `0x180009484`
- `0x180010a84`
- `0x18001366c`
- `0x18001513c`
- `0x18002031c`
- `0x1800217f0`
- `0x180024030`
- `0x180076f74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077047`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800770d9`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800770d9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800770e9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800770e9`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataFolder` at `0x180076fcd`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataFolder` at `0x180077038`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataFolder` at `0x180076fcd`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataFolder` at `0x180077038`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180077107`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180077107`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180076f9a`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180076f9a`

## string_xrefs

- `0x180077132`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`
- `0x180077144`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`
- `0x180077159`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OfflineRegistry::GetHivePathByFamilyName(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  const char *v4; // r9
  signed int LastError; // eax
  char v6; // cl
  void *v7; // rsi
  int SystemAppDataFolder; // r14d
  signed int v9; // eax
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+3Ch] [rbp-C4h]
  _QWORD v15[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v18[120]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[104]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  unsigned int v21; // [rsp+178h] [rbp+78h] BYREF

  v3 = OpenStateExplicit(a2);
  if ( !v3 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      v4);
  v21 = 0;
  GetSystemAppDataFolder(v3, 0, &v21);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v6 = 0;
  }
  else
  {
    v6 = 1;
    if ( LastError <= 0 )
      goto LABEL_6;
  }
  LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_6:
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      (const char *)(unsigned int)LastError,
      v13);
  v7 = operator new[](saturated_mul(v21, 2u));
  SystemAppDataFolder = GetSystemAppDataFolder(v3, v7, &v21);
  v9 = GetLastError();
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  if ( SystemAppDataFolder != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp",
      (const char *)(unsigned int)v9,
      v13);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v15);
  v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16, v7);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, L"\\Helium");
  std::basic_stringbuf<unsigned short>::str(v17, a1);
  *(_QWORD *)((char *)v15 + *(int *)(v15[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(int *)((char *)&v14 + *(int *)(v15[0] + 4LL)) = *(_DWORD *)(v15[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v17);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v18);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v19);
  operator delete(v7, v11);
  CloseState(v3);
  return a1;
}

```

## disassembly

```asm
0x180076f74  mov     [rsp-8+arg_0], rbx
0x180076f79  mov     [rsp-8+arg_8], rsi
0x180076f7e  push    rbp
0x180076f7f  push    rdi
0x180076f80  push    r14
0x180076f82  lea     rbp, [rsp-40h]
0x180076f87  sub     rsp, 140h
0x180076f8e  mov     rax, rdx
0x180076f91  mov     rdi, rcx
0x180076f94  mov     rdx, r8
0x180076f97  mov     rcx, rax
0x180076f9a  call    cs:__imp_OpenStateExplicit
0x180076fa1  nop     dword ptr [rax+rax+00h]
0x180076fa6  mov     rbx, rax
0x180076fa9  mov     [rsp+150h+var_128], rax
0x180076fae  test    rax, rax
0x180076fb1  setnz   al
0x180076fb4  mov     rcx, [rbp+58h]; this
0x180076fb8  test    al, al
0x180076fba  jz      loc_180077144
0x180076fc0  and     [rbp+50h+arg_18], 0
0x180076fc4  lea     r8, [rbp+50h+arg_18]
0x180076fc8  xor     edx, edx
0x180076fca  mov     rcx, rbx
0x180076fcd  call    cs:__imp_GetSystemAppDataFolder
0x180076fd4  nop     dword ptr [rax+rax+00h]
0x180076fd9  call    cs:__imp_GetLastError
0x180076fe0  nop     dword ptr [rax+rax+00h]
0x180076fe5  cmp     eax, 7Ah ; 'z'
0x180076fe8  jnz     short loc_180076FEE
0x180076fea  xor     cl, cl
0x180076fec  jmp     short loc_180076FF4
0x180076fee  mov     cl, 1
0x180076ff0  test    eax, eax
0x180076ff2  jle     short loc_180076FFC
0x180076ff4  movzx   eax, ax
0x180076ff7  or      eax, 80070000h
0x180076ffc  mov     r10, [rbp+58h]
0x180077000  test    cl, cl
0x180077002  jnz     loc_180077156
0x180077008  mov     ecx, [rbp+50h+arg_18]
0x18007700b  mov     eax, 2
0x180077010  mul     rcx
0x180077013  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007701a  cmovo   rax, rcx
0x18007701e  mov     rcx, rax; unsigned __int64
0x180077021  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180077026  mov     rsi, rax
0x180077029  mov     [rsp+150h+var_120], rax
0x18007702e  lea     r8, [rbp+50h+arg_18]
0x180077032  mov     rdx, rax
0x180077035  mov     rcx, rbx
0x180077038  call    cs:__imp_GetSystemAppDataFolder
0x18007703f  nop     dword ptr [rax+rax+00h]
0x180077044  mov     r14d, eax
0x180077047  call    cs:__imp_GetLastError
0x18007704e  nop     dword ptr [rax+rax+00h]
0x180077053  test    eax, eax
0x180077055  jle     short loc_18007705F
0x180077057  movzx   eax, ax
0x18007705a  or      eax, 80070000h
0x18007705f  mov     rcx, [rbp+58h]; this
0x180077063  cmp     r14d, 1
0x180077067  jnz     loc_18007712F
0x18007706d  lea     rcx, [rsp+150h+var_110]
0x180077072  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180077077  nop
0x180077078  mov     rdx, rsi
0x18007707b  lea     rcx, [rsp+150h+var_100]
0x180077080  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180077085  mov     rcx, rax
0x180077088  lea     rdx, aHelium; "\\Helium"
0x18007708f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180077094  mov     rdx, rdi
0x180077097  lea     rcx, [rsp+150h+var_F8]
0x18007709c  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800770a1  nop
0x1800770a2  mov     rax, [rsp+150h+var_110]
0x1800770a7  movsxd  rcx, dword ptr [rax+4]
0x1800770ab  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x1800770b2  mov     [rsp+rcx+150h+var_110], rax
0x1800770b7  mov     rax, [rsp+150h+var_110]
0x1800770bc  movsxd  rcx, dword ptr [rax+4]
0x1800770c0  lea     edx, [rcx-98h]
0x1800770c6  mov     [rsp+rcx+150h+var_114], edx
0x1800770ca  lea     rcx, [rsp+150h+var_F8]
0x1800770cf  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x1800770d4  lea     rcx, [rsp+150h+var_F0]
0x1800770d9  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x1800770e0  nop     dword ptr [rax+rax+00h]
0x1800770e5  lea     rcx, [rbp+50h+var_78]
0x1800770e9  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x1800770f0  nop     dword ptr [rax+rax+00h]
0x1800770f5  nop
0x1800770f6  mov     rcx, rsi; void *
0x1800770f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800770fe  nop
0x1800770ff  test    rbx, rbx
0x180077102  jz      short loc_180077113
0x180077104  mov     rcx, rbx
0x180077107  call    cs:__imp_CloseState
0x18007710e  nop     dword ptr [rax+rax+00h]
0x180077113  mov     rax, rdi
0x180077116  lea     r11, [rsp+150h+var_10]
0x18007711e  mov     rbx, [r11+20h]
0x180077122  mov     rsi, [r11+28h]
0x180077126  mov     rsp, r11
0x180077129  pop     r14
0x18007712b  pop     rdi
0x18007712c  pop     rbp
0x18007712d  retn
0x18007712f  mov     r9d, eax; char *
0x180077132  lea     r8, aOnecoreBaseApp_39; "onecore\\base\\appmodel\\execmodel\\des"...
0x180077139  mov     edx, 1Ah; void *
0x18007713e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180077144  lea     r8, aOnecoreBaseApp_39; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007714b  mov     edx, 11h; void *
0x180077150  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180077156  mov     r9d, eax; char *
0x180077159  lea     r8, aOnecoreBaseApp_39; "onecore\\base\\appmodel\\execmodel\\des"...
0x180077160  mov     edx, 16h; void *
0x180077165  mov     rcx, r10; this
0x180077168  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
